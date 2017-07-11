+++
date = "2017-06-27T20:18:05-04:00"
title = "Getting Started With KeePassXC"
subtitle = ""
tags = []
comments = true
draft = false
+++

## What is KeePassXC

[KeePassXC](https://keepassxc.org) is a cross-platform, modern open-source password manager. It is a community fork of [KeePassX](https://www.keepassx.org/), a native cross-platform port of [KeePass Password Safe](http://keepass.info/), with the goal to extend and improve it with new features and bug fixes.

This is a basic guide of how to get started with KeePassXC. This guide is **for OS X / macOS users** (hereto referred to as "macOS"), though note that KeePassXC is built to work with Linux and Windows as well, and this guide may be helpful for those users too. Note that I'm not a security expert or professional, so buyer beware from this point on. If you spot any errors or have any suggestions for this post, feel free to contact me via [Twitter](https://twitter.com/sts10) or [elsewhere](https://gist.github.com/sts10/4a4e01021b3a5ad42e9b73e0abd7b7e3).

(I'd like to note that I drew some inspiration and methodology from [Martin Shelton's "KeePass for Beginners" post](https://medium.com/@mshelton/keypass-for-beginners-dc8adfcdad54).)

## Level 0: Starting Out

### Downloading KeePassXC

First, let's head over to the KeePassXC's [Download page](https://keepassxc.org/download).

![KeePassXC Download page, with macOS selected](/img/keepassxc-download-page-screenshot.png)

Select your desired operating system (the current options are Linux, macOS, and Windows), or to compile KeePassXC from source code. If we're using macOS, we'll go to the "macOS" tab and click the link labeled "Binary bundle for macOS 10.7 and later" to download the latest macOS release of KeePassXC to our computer.

### Verifying our Download

Before you install KeePassXC from this downloaded file, it is recommended that you verify the signature of your download. By verifying the signatures of KeePassXC releases, you can prove the authenticity and integrity of the downloaded file. This guarantees that the file you just downloaded was originally created by the KeePassXC Team and that its contents haven't been tampered with on the way. 

You can learn how to verify your download on [the Verifying Signatures page](https://keepassxc.org/verifying-signatures) of the KeePassXC website.

### Installing KeePassXC on macOS

Now that we're downloaded and verified our .dmg file, simply double click it to mount the disk image.  Next drag the KeePassXC icon into you Applications folder. 

![Installation](/img/keepassxc-install.gif)

KeePassXC should now be installed on your computer.

## A general overview of how KeePassXC works as a password manager

Before we go any further, lets talk a bit about how KeePassXC works. As we have learned, KeePassXC is a password manager-- it saves your passwords (and associated usernames) securely for you. 

We're going to use KeePassXC, an application, to create and edit KeePass password databases. It may be helpful to think of it like Microsoft Excel: You use Excel to create and edit files on our computer that are spreadsheets. Similarly, KeePassXC enables us create and edit files on our computer that are databases of usernames and passwords.

Of course one significant difference here is that these database files are always encrypted when not in use. To access them, you first open the database using KeePassXC (just as you would open a spreadsheet with Excel), then you must enter the "master key", which is usually a long master password, in order to access the database.

So let's create a KeePass database and see how we use it to save and manage passwords securely.

## Level 1: Getting Setup

Now that KeePassXC is installed on our machine, let's create a password database.

### Creating a Password Database

![KeePassXC 2.2.0 start screen](https://keepassxc.org/images/screenshots/macos/screen_001.png)

When we launch KeePassXC for the first time, we're greeted with the screen above. Since we don't have any databases yet, let's click the "Create new database" button. 

![Save Database](/img/keepassxc-save-database-as.png)

First, we're asked to choose a name and a location to save this database file we're creating. I created a new folder called "passwords" in my Documents folder, then I named my new database "my-passwords" (the full file name will be `my-passwords.kdbx`), but you can name it whatever you want. 

![Setting master key](/img/keepassxc-entering-master-password.gif)

Next, we're asked to set up a master key. For now, let's focus on the section under the "Password" section and ignore the "Key file" and "Challenge Response" sections. 

Here, we're going to enter a long password or _passphrase_ that we'll need to use every time we want to open this database. There are multiple methods for creating nice long, random passphrases that are difficult for attackers to guess-- we'll discuss how to use KeePassXC to generate a random passphrase for us below. (Another method involves [using physical dice](https://theintercept.com/2015/03/26/passphrases-can-memorize-attackers-cant-guess/).)

Enter your master password twice and then hit "OK". 

### Creating your first entry

Let's add our first entry. As an example, let's say we want to store our Reddit username and password. 

First, find the button with the key and the green downward arrow. 

![Add new entry button](/img/keepassxc-blank-add-new-entry.png)

We'll be presented with an interface to create our new entry. Let's fill in a title (Reddit), Username (our Reddit username), our Reddit password (Password) twice, and then the URL of the site (https://www.reddit.com), which you can of course paste in.

![Our first entry](/img/keepassxc-entry-creation.gif)

If you want to view your password, you can click the button with the eye icon on the right. 

Note that KeePassXC has the ability to generate random passwords for us, which we can do by clicking the black die icon. We'll go over that below, but for now let's pretend we're simply storing your existing password.

Once we've filled in this basic information, we'll click the OK button to save these changes to our database. We'll now see our new entry in our database. 

![one little entry](/img/keepassxc-one-entry.png)

Make sure to save your database at this point, either by clicking the button with floppy disk icon or going to Database > Save database.

### Logging in to Reddit

OK now let's actually use KeePassXC to log in to Reddit. KeePassXC has a few ways to do this-- we'll start with the simplest. 

Let's open [https://reddit.com/login](https://reddit.com/login) in a browser. With KeePassXC open to the side and our lone entry highlighted (single clicking it), click the person + paper icon to copy your Reddit username to the clipboard. Go paste that into the Reddit login page. Then return to KeePassXC to click the lock + paper icon to copy your Reddit password to your clipboard. Paste that into the Reddit login page, and click the "LOG IN" button (or press enter).

![log in gif 1](/img/keepassxc-reddit-login.gif)

#### Auto-Type: A more convenient login workflow

KeePassXC has a feature called Auto-Type that, as the name implies, automatically types your username and password into a form. 

To invoke Auto-Type, move focus from your browser to KeePassXC, then right-click the entry you want to Auto-Type and click "Perform Auto-Type". KeePassXC will type your username, hit tab, type your password, and then hit enter. 

![autotype gif](/img/keepassxc-auto-type.gif)

(Note: `{USERNAME}{TAB}{PASSWORD}{ENTER}` is the default Auto-Type sequence. However you can edit this sequence on a per-entry level. Just edit the entry by clicking the button with the key and blue pen icon, navigate to the Auto-Type section of the menu, and write a custom Auto-Type sequence. [More info on writing these custom sequences](http://keepass.info/help/base/autotype.html#autoseq).)

![Custom auto-type sequence](/img/keepassxc-custom-auto-type-sequence.png)

### Locking your database

If you're stepping away from your computer, it's wise to lock your KeePass database. To do this, go to Tools > Lock database (or hit command + l). Once locked, you'll have to enter your master password to unlock your database. 

![Lock it down](/img/keepassxc-lock-database.gif)

Note that you can set KeePassXC to lock your databases after a specific number of seconds of inactivity by going to KeePassXC Preference > Security.

![auto lock setting](/img/keepassxc-set-lock-time.png)

## Level 2: More Security Tips

We'll now look at some further setting and practices that can make your usage of KeePassXC even more secure. I've tried to put the required basics in the sections above-- this is the sort-of optional-but-good-to-do things.

### Generating random passwords for your accounts

One of the best benefits of using a password manager like KeePassXC is that, since you only have to remember one master password and can forget your individual account passwords, you can use long unique, random passwords for each service you use. [Martin Shelton](https://twitter.com/mshelton), a user and security researcher, explained the benefits of random, unique passwords succinctly in [a Medium post about password managers](https://medium.com/@mshelton/password-managers-for-beginners-d1f49866f80f):

> If you use the same password everywhere, a hacker only needs to get your password once in order to break into many of your online accounts... For example, Yahoo recently announced that [passwords for 500 million Yahoo users were breached in 2014](http://www.pbs.org/newshour/rundown/500-million-yahoo-accounts-hit-hackers-company-confirms/). Imagine if an attacker used your single, easy-to-remember password to access your health care records, your home address, credit card numbers, or your social security number... To minimize the damage from a breach, you should use unique passwords on each account. But it can be a challenge to remember each password.

KeePassXC has a built-in random password generator just for creating passwords you'll likely never have to memorize.

Let's say we're creating a new GitHub account and want to store our username and password in our KeePass database. First, we'll create an entry for GitHub and create a random password for our yet-to-be-created GitHub account.

![Creating a new entry with a randomly generated passphrase](/img/keepassxc-new-random-entry.gif)

First, we'll hit the key + green arrow button to create a new entry. Then fill out the title and username as we did above. However now, instead of just making up a password, we're going to use KeePassXC's password generator to create a random password for our yet-to-be-created GitHub account. 

The password generator has a few options. First, we can chose between a "Password" (a series of random characters) and a "Passphrase" (a series of random words). Passphrases have to be longer in length to be as secures as passwords, but they are easier to remember. 

If we were **creating a random password**, we have a number of options. We can increase or decrease the length, choose to include or exclude uppercase letters, lowercase letters, numbers, or special characters. And we can even choose to "exclude look-alike characters" and whether to "Pick characters from every group". Most of these options exist to help you, the user, get around password requirements like "must contain at least one number and one uppercase letter" or "cannot include any special characters", etc.

If we're **creating a random passphrase**, we can only select length and the word separator. For length, 6 or 7 is usually fine (watch the password strength meter). For the word separator, I personally prefer a hyphen, but that can be your call (you likely won't ever have to type this passphrase in by hand anyway). 

Once you've got a password or phrase you like and that meets the service's requirements (in our case, GitHub), hit the Apply button to set your new password or passphrase. Then hit OK to store your entry. Click the floppy disk icon to save your database. 

Now go to [GitHub's sign-up page](https://github.com/join?source=header-home) and create a new account with the username and password we just saved in your database.

### Generating a long, random passphrase for your master password

We can also use KeePassXC's built-in password generator to generate random passphrases to be used as our master password. Since you actually have to type in this password, we're going to generate as passphrase rather than a password.

To change the master password of an existing KeePass database, go to the "Database" menu and select "Change master key". Next click the black die icon to generate a new random passphrase.

Switch the random generator mode from "Password" to "Passphrase", then set the Length to six words. You then may want to change the "Word Separator" from the default of a space to a hyphen, or even to no character (nothing).

![randomly generating a master passphrase](/img/keepassxc-random-master-passphrase.gif)

Once you've got a 6-word passphrase with your desired word separator, write your new passphrase on a piece of paper and keep it somewhere safe. 

It's very important to note that you're going to need to remember this passphrase (as it's not going to be stored in your KeePass database). Basically, **don't change your master password to the generated passphrase unless you have it written down somewhere or memorized.**

Now click the Copy button to copy your new passphrase to the clipboard. Then click the Close button to close the password generator. 

At this point we're ready to change your master password to your new passphrase by pasting it into the "Enter password" field and the "Repeat password" field. Clicking the OK button will change your database's master password to your new passphrase. Again, don't do this unless you've written the new passphrase down somewhere safe and/or memorized it.

![XKCD long passprhases](https://imgs.xkcd.com/comics/password_strength.png)

One way to remember these long passphrases is to [create a little story about them](https://www.xkcd.com/936/) in your head.

### Setting number of transform rounds by benchmark

Another way we'll want to make our KeePass database a bit more secure is to increase the number of "transform rounds" needed to be performed for every master password guess. 

The basic idea is that we want to create a time delay for every master password guess. If we can slow down the process such that it takes roughly one second per guess, we'll be able to hamper a brute force dictionary attack, in which an attacker would systematically guess every possible password. 

The way KeePassXC allows for us to create this time delay is to change the way your database in encrypted such that any computer attempting to unlock it will be forced to run your master key through a high number of rounds of encryption before actually trying the password they want to try. You can read more about it in [this blog post](http://www.laurencegellert.com/2015/02/a-keepass-setting-that-might-save-your-online-identity/).

How many rounds should you set? Conveniently, KeePassXC has a "Benchmark" button that tests your current machine to see how many transform rounds it can do in 1 second. It then enters that number in the "Transform rounds" field. 

To set the number of transform rounds, with your database unlocked go to the Database menu and select "Database settings". Then click the "Benchmark" button, wait one second for the higher number to appear in the form, and hit OK.

![Benchmarking transform round](/img/keepassxc-benchmarking.gif)

Now your database should take about one second to try a master password guess (whether it's correct or incorrect). Assuming you, knowing the passphrase, can get it in one or maybe a handful of guesses, this is not much of a delay. But to a program systematically guessing millions of passwords, it can be a road block.

## Level 3: Getting Organized

### Syncing options

If you want keep you KeePass database synchronized across multiple devices, you'll need to share your database between those devices. The easiest way to do that is to use a cloud storage service like [Google Drive](https://www.google.com/drive/download/) or [Dropbox](https://www.dropbox.com/). You simply move your KeePass database (which, remember, is well-encrypted) into a folder on your Google Drive or Dropbox. 

To access your password from a smartphone, you'll need to use an app that can open KeePass databases. There are a handful for both iOS and Android, but I haven't used any of them so I won't comment further.

### Using Groups

As you've likely noticed, on the left-hand side of KeePassXC there's a folder tree. Using these folders, you can keep your accounts organized in groups like "work", "finance" and whatever other categories you like. 

![groups](/img/keepassxc-groups.png)

You can later drag entries in and out of groups. You can even create groups within groups.

### Downloading Favicons

To beautify your KeePass database even further, you can automatically download the favicon (usually the service's logo) from the website of the service. 

To do this, edit an entry, then click the "icon" button on the left. While you can select from any of the given options, you can also click the "Download favicon" button in the bottom right. Be sure to have the full URL of the service in your entry (in this case `https://github.com/`), so KeePassXC knows where to download the favicon from.

![custom icon](/img/keepassxc-custom-icon.png)

Once the favicon downloads (it might take a second), be sure to select it and then hit "OK" to save the changes to the entry.

### Search

KeePassXC, as you may have already observed by this point, has search functionality via a text field in the top right of the program. As of KeePassXC v 2.2.0 it searches all of your folders, regardless of which folder you're currently in, which is nice.

<!--
## Level 4: Using multiple factors
  - Key file
  - Challenge / Response
-->

_Again, if you spot any errors or have any suggestions for this post, feel free to contact me via [Twitter](https://twitter.com/sts10) or [elsewhere](https://gist.github.com/sts10/4a4e01021b3a5ad42e9b73e0abd7b7e3)._
