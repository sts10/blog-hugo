+++
date = "2017-06-27T20:18:05-04:00"
title = "Getting Started With KeePassXC"
subtitle = ""
tags = []
draft = false
comments = true
+++

## What is KeePassXC

[KeePassXC](https://keepassxc.org) is a feature-rich, fully cross-platform and modern open-source password manager. It is a community fork of [KeePassX](https://www.keepassx.org/), a native cross-platform port of [KeePass Password Safe](http://keepass.info/), with the goal to extend and improve it with new features and bug fixes.

This is a basic guide of how to get started with KeePassXC. This guide is **for OS X / macOS users**, though note that KeePassXC is built to work with Linux and Windows as well, and this guide may be helpful for those users too.

## Downloading KeePassXC

First, let's head over to the KeePassXC's [Download page](https://keepassxc.org/download).

![KeePassXC Download page, with OS X selected](/img/keepassxc-download-page-screenshot.png)

Select your desired operating system (the current options are Linux, OS X, and Windows), or to compile KeePassXC from source code. If we're using Mac (OS X), we'll go to the "OS X" tab and click the link labeled "Binary bundle for OS X 10.7 and later" to download the latest OS X release of KeePassXC to our computer.

## Verifying our Download

Before you install KeePassXC from this downloaded file, it is recommended that you verify the signature of your download. By verifying the signatures of KeePassXC releases, you can prove the authenticity and integrity of the downloaded file. This guarantees that the file you just downloaded was originally created by the KeePassXC Team and that its contents haven't been tampered with on the way. 

You can learn how to verify your download on [the Verifying Signatures page](https://keepassxc.org/verifying-signatures) of the KeePassXC website.

## Installing KeePassXC on mac OS/OS X

Now that we're downloaded and verified our .dmg file, simply double click it to mount the disk image. 

![Installation](/img/keepassxc-install.gif)

Now drag the KeePassXC icon into you Applications folder. KeePassXC should now be installed on your computer.

## And now, a general overview of how KeePassXC works as a password manager

Before we go any further, let's learn a bit about how KeePassXC works. 

As we have learned, KeePassXC is a password manager. We're going to use KeePassXC, an application, to create an edit KeePass password databases. It may be helpful to think of it like Microsoft Excel: You use Excel to create and edit files on our computer that are spreadsheet. Similarly, KeePassXC let's us create and edit files on our computer that are databases of usernames and passwords.

Of course the difference here is that these database files are always encrypted when not in use. To access them, you first open the database using KeePassXC (just as you would open a spreadsheet with Excel), then you must enter the "master key", which is usually a long master password, for that database.

So let's create a KeePass database and see how we use it to save and manage passwords securely.

## Creating a Password Database

![KeePassXC 2.2.0 start screen](https://keepassxc.org/images/screenshots/macos/screen_001.png)

When we launch KeePassXC for the first time, we're greeted with the screen above. Since we don't have any databases yet, let's click the "Create new database" button. 

![Save Database](/img/keepassxc-save-database-as.png)

First, we're asked to choose a name and a location to save this database file we're creating. I created a new folder called "passwords" in my Documents folder, then I named my new database "my-passwords", but you can name it whatever you want. 

![Setting master key](/img/keepassxc-entering-master-password.gif)

Next, we're asked to set up a master key. For now, let's focus on the section under the "Password" section and ignore the "Key file" and "Challenge Response" sections. 

Here, we're going to enter a long password or _passphrase_ that we'll use to open this database. There are many methods for creating nice long passphrases that are difficult for attackers to guess-- ["diceware"](https://theintercept.com/2015/03/26/passphrases-can-memorize-attackers-cant-guess/) is one such method.

Enter your master password twice and then hit "OK". 

## Creating your first entry

Let's add our first entry. As an example, let's say we want to store our Reddit username and password. 

First, let's find the button with the key and the green downward arrow. 

![Add new entry button](/img/keepassxc-blank-add-new-entry.png)

We'll be presented with an interface to create our new entry. Let's fill in a title (Reddit), Username (our Reddit username), and our Password.

![Our first entry](/img/keepassxc-entry-creation.gif)

If you want to view your password, you can click the button with the eye icon on the right. 

Note that KeePassXC has the ability to generate random passwords for us, which we can do by clicking the black die icon, but for now that outside of the scope of this little guide. 

Once we've filled in this basic information, we'll click the OK button to save these changes to our database. We'll now see our new entry in our database. 

![one little entry](/img/keepassxc-one-entry.png)

Make sure to save your database at this point, either by clicking the button with floppy disk icon or going to Database > Save database.

## Logging in to Reddit

OK now let's actually use KeePassXC to log in to Reddit. KeePassXC has a few ways to do this-- we'll start with the simplest. 

Let's open [https://reddit.com/login](https://reddit.com/login) in a browser. With KeePassXC open to the side and our lone entry highlighted (single clicking it), click the person + paper icon to copy your Reddit username to the clipboard. Go paste that into the Reddit login page. Then return to KeePassXC to click the lock + paper icon to copy your Reddit password to your clipboard. Paste that into the Reddit login page, and click the "LOG IN" button (or press enter).

![log in gif 1](/img/keepassxc-reddit-login.gif)

### Auto-Type: A more convenient login workflow

KeePassXC has a feature called Auto-Type that, as the name implies, automatically types your username and password into a form. 

To invoke Auto-Type, move focus from your browser to KeePassXC, then right-click the entry you want to Auto-Type and click "Perform Auto-Type". KeePassXC will type your username, hit tab, type your password, and then hit enter. 

![autotype gif](/img/keepassxc-auto-type.gif)

(Note: `{USERNAME}{TAB}{PASSWORD}{ENTER}` is the default Auto-Type sequence. However you can edit this sequence on a per-entry level. Just edit the entry by clicking the button with the key and blue pen icon, navigate to the Auto-Type section of the menu, and write a custom Auto-Type sequence. [More info on writing these custom sequences](http://keepass.info/help/base/autotype.html#autoseq).)

![Custom auto-type sequence](/img/keepassxc-custom-auto-type-sequence.png)

## Locking your database

If you're stepping away from your computer, it's wise to lock your KeePass database. Do do this, go to Tools > Lock database (or hit command + l). Once locked, you'll have to enter your master password to unlock your database. 

Note that you can tell KeePassXC to lock databases after a specific number of seconds of inactivity by going to KeePassXC Preference > Security.

