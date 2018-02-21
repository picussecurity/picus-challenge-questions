# Connectivity indicator component

We want you to write a component with any technology you are comfortable with (preferably Javascript/React) which will show internet connectivity status of a client-side web app.

## Specifications

- The component should receive a function `checkConnectivity` which will return `true` or `false` depending on online state of the application.
- The component must be in one of following three states: Online, Offline, Reconnecting.
- While in Online state, it should periodically (once per second) call `checkConnectivity` function. Depending on the return value, it should stay in Online state (`true`) or switch to Offline state (`false`). In Online state, nothing should be displayed.
- When it transitions to Offline from Online state, it should start a countdown timer of `5` seconds. At the end of the timer, it should switch to Reconnecting state. When it transitions to Offline from Reconnecting state, it should start timer at the double of the previous timer duration. In Offline state, 'Retrying in X...' text should be displayed where X is the remaining seconds.
- When it transitions to Reconnecting state, it should call `checkConnectivity` function. Depending on the return value, it should switch to Online state (`true`) or switch back to Offline state (`false`). In Reconnecting state, 'Retrying...' text should be displayed.

### Bonus points (these are not required but nice to have)

- There should be a fourth state, Soft Offline, which will be transitioned to when `checkConnectivity` returns `false` in Online state, will try `checkConnectivity` once more and depending on the result it should switch back to Online (`true`) or go to Offline (`false`).
- There should be a 'Retry Now' button in Offline state, which will switch to Reconnecting state immediately.
- There should be a 'Cancel' button in Reconnecting state, which will switch to Offline state immediately. When switched Offline state this way, it won't have a timer and 'Retry Now' button will say just 'Retry'. (This should happen if initial timer value gets over `1000` seconds too.)
- When transitioning to Online from Reconnecting state, it should show 'Connected!' for `2` seconds.

## Goals

- The component should never enter an invalid state.
- The code should be tidy, readable and concise.
- It should look presentable and user-friendly.
- It should be easily adaptable to receive an asynchronous (Promise returning) function instead of a synchronous one.
- It should be able to receive components to display for each state provided by the consumer. (This is called FACC or Render Props pattern.)

## Tip: Sample Type Signature

```
type Props = {
  checkConnectivity: () => boolean | Promise<boolean>,
  renderOffline?: ({ remainingSeconds: number }) => React.Node,
  renderReconnecting?: () => React.Node,
}

type PropsBonus = {
  checkConnectivity: () => boolean | Promise<boolean>,
  renderOnline?: ({ isRecentlyConnected: boolean }) => React.Node,
  renderOffline?: ({remainingSeconds: number | "canceled", retryNow: Function }) => React.Node,
  renderReconnecting?: ({ cancel: Function }) => React.Node,
}
```
