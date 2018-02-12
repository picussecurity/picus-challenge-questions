# MailDelivr

You are supposed to write a web service for sending email campaigns to contacts. You are free to choose whatever technology you will use to implement it.

## Requirements

* The user can upload a text file containing a list of names and email addresses in the following format:

```
Edward Kmett <ekmett@example.com>
Simon Peyton Jones <spj@example.com>
Michael Snoyman <snoyberg@example.com>
```

* After a successful upload, the user can see the list of contacts and select the ones to include in a campaign.

* The user can type the body of the email and send it to selected contacts.

* The contacts who receive the email will see the message and see a custom link. Clicking the link will show a success page.

* The contacts list will show which contacts were sent an email, which ones clicked the link, and how long it took between the time to receive the email and click the link.

* The server should survive a reboot.

## Bonus points

These are not necessary and only valuable if you meet all of the requirements with time to spare

* Ability to add/edit/delete/clear contacts

* Ability to create groups and manage them

* Ability to create/list/cancel campaigns

It's very important to deliver us the source code of the project and clear instructions to build and test it. You can assume we will run on Linux with no extra packages installed.
