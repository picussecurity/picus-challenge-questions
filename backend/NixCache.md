# Nix Binary Cache

## Introduction to Nix Package Manager

Nix is a purely functional and declarative package manager for Linux
and MacOS. Installation is very simple (but you may prefer to take a
look at install script beforehand):

```console
curl https://nixos.org/nix/install | sh
```

Please have a look at [Nix Manual](https://nixos.org/nix/manual/) and
read more about it's features. You can find some example expressions
written in nix at [Nixpkgs](https://github.com/nixos/nixpkgs)
repository which is the main source of NixOS distribution. Also, some
of the guidelines can be found at [Nixpkgs
Manual](https://nixos.org/nixpkgs/manual).

Installation creates `/nix` folder and stores all packages in
`/nix/store`. Nix comes with a `nixpkgs` directory and can build
packages from that tree.

```console
nix-env -iA nixpkgs.hello
```

Mostly nix downloads the binary package from a cache since `nixpkgs`
is automatically tested by a continuous integration server (building
every package definition and ensuring an error free tree) and your
build is gonna produce exactly the same binary for the same `nixpkgs`
tree, hence nix comes with a default enabled binary cache
`https://cache.nixos.org` which provides binaries built by Hydra CI.

## The Problem Definition

Your goal is to implement a nix binary cache in Go Language for
`x86-64-linux` platform. There is no official documentation but you
can find a few starters in Nix Manual, hence you need to find your way
by reading nix source code, discussions and blogs.

It should get `binary-cache-path` to serve and port number to bind:

```console
nix-binary-cache ~/mynixcache -p 8080
```

Binary cache can be populated by build products like:

```console
$ nix build nixpkgs.hello
[1 copied (0.2 MiB), 0.0 MiB DL]

$ nix copy --to file:///home/johndoe/mynixcache nixpkgs.hello
[2 copied (24.0 MiB)]
```

Resulting the following structure:

```console
$ ls -al ~/mynixcache/
total 24
drwxrwxr-x  3 johndoe users 4096 Aug  6 16:21 .
drwxr-xr-x 22 johndoe users 4096 Aug  6 16:21 ..
-rw-r--r--  1 johndoe users  591 Aug  6 16:21 188avy0j39h7iiw3y7fazgh7wk43diz1.narinfo
-rw-r--r--  1 johndoe users  551 Aug  6 16:21 83lrbvbmxrgv7iz49mgd42yvhi473xp6.narinfo
drwxr-xr-x  2 johndoe users 4096 Aug  6 16:21 nar
-rw-r--r--  1 johndoe users   21 Aug  6 16:21 nix-cache-info
```

Pease use [Gin web framework](https://github.com/gin-gonic/gin) to
speedup your development and consider creating a solution that is composable
with another Gin application in the future.
