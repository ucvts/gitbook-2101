# Our Development Environment

## Installing Node.js and NPM

Node.js is a cross-platform JavaScript runtime environment. We'll be writing all of our code in JavaScript, and Node.js will help us execute it. NPM is a package manager \(short for Node Package Manager\) that allows us to quickly download external packages we may need for our own applications.

To get started, navigate to the [Node.js page](https://nodejs.org/en/). It's smart enough to figure out the operating system you're using, and offer the appropriate download. NPM is bundled with the Node.js download, so we're going to get both.

{% tabs %}
{% tab title="Windows" %}
This video is a little dated, so it may not match your system exactly. Don't worry, the steps don't change. Some things might just be worded a little differently.

{% embed url="https://youtu.be/X-FPCwZFU\_8" %}

To verify the success of your installation, open the Command Prompt and enter the `node` command, followed by the `-v` flag \(which stands for version\).

```text
C:\> node -v

TODO

C:\>
```

Check the NPM version, too, using the `npm` command. Don't worry if your version numbers don't match mine. As long as both commands return a version number \(and not an error message\), then your installation was successful.

```text
C:\> npm -v

TODO

C:\>
```
{% endtab %}

{% tab title="macOS" %}
This video is a little dated, so it may not match your system exactly. Don't worry, the steps don't change. Some things might just be worded a little differently.

{% embed url="https://www.youtube.com/watch?v=rF1ZHmqvm8I" %}

To verify the success of your installation, open the Terminal and enter the `node` command, followed by the `-v` flag \(which stands for version\).

![](../.gitbook/assets/node-v.png)

Check the NPM version, too, using the `npm` command. Don't worry if your version numbers don't match mine. As long as both commands return a version number \(and not an error message\), then your installation was successful.

![](../.gitbook/assets/npm-v.png)
{% endtab %}
{% endtabs %}

## Version Control with Git

Version control, more generally, is the process by which developers track changes to project files over time. You can think of this like the version history feature in Google Docs. It affords you the opportunity to revert to a prior working state in the event you mess something up. When working on a team, you can keep track of who made what changes. It may not seem like it, but something like this is very useful.

Git is one of several powerful version control systems. It handles the job of tracking newly created files, changes to existing files, and deleted files. Like anything worth knowing or doing, there's a bit of a learning curve. At first, you'll want to pull your hair out. Trust me, though. There's a reason every software developer in the world uses some variation of this to manage their codebases. It's well worth learning.

{% tabs %}
{% tab title="Windows" %}
Git, the version control system software, was originally written for the Linux operating system. Git for Windows ports the Git functionality over to the Windows operating system.

{% embed url="https://youtu.be/nbFwejIsHlY" %}

After the installation is complete, open up the Git Bash window through the Start menu. It looks a lot like a Command Prompt, and it's where you'll enter all of your Linux and Git commands needed to interact with and manipulate your files, folders, and applications. Like it or not, you're going to get very comfortable working from the command line.

![](../.gitbook/assets/git-bash.png)
{% endtab %}

{% tab title="macOS" %}
If you're running Mavericks \(10.9\) or later, it's incredibly simple to install Git. To do so, you just need to install the Xcode Command Line Tools. Open the Terminal and run the following command. If you receive a response reporting your Git version, then you already have the Xcode Command Line Tools installed.

![](../.gitbook/assets/git-v.png)

Otherwise, you'll be prompted to install them. Click Install, accept the license agreement, and hang tight. It's a fairly quick installation.

![](../.gitbook/assets/git-install.png)

When it's finished, click Done and re-run the `git --version` command. It doesn't matter if your version doesn't match mine. It very well may be more recent!
{% endtab %}
{% endtabs %}

## Hosting with GitHub

GitHub is Google Drive for programmers—it provides repositories where you can store your projects remotely. This is a great way to backup your code in case something happens to your local copy. More importantly, though, it lets you keep your local copies in sync when working across different devices.

Navigate to [Github](https://github.com/). If you have an existing account, you're welcome to use it. Otherwise, choose a username, email, and password, and sign up. A word to the wise—the district spam filters love to hold GitHub confirmation emails hostage. A personal email is a better choice, at least in the beginning.

![](../.gitbook/assets/github-signup.png)

If privacy is a concern, you can always hide your email address from the public. I'll go over this in the Personal Settings section.

### Personal Settings

When you first login, you'll see a square, pixelated icon in the top-right corner of the page. Click it, and then select Settings. Yours will look a little different than mine, but you should see something to this effect. This is your Public profile.

![](../.gitbook/assets/github-profile.png)

In the Personal settings menu on the left, you can explore different configurations for your account. It's unlikely you'll need to worry about most of these sections, but here are the highlights of each.

* Profile - general biographical information.
* Account - username and password changes; account deletion.
* Emails - add and remove email address\(es\); make an email private.
* Notifications - configure email notifications.
* Billing - upgrade to paid plans; manage payment methods.
* SSH and GPG keys - add authentication key\(s\) for your computer\(s\).
* Security - manage two-factor authentication.
* Sessions - view a list of active sessions.
* Blocked users - block specific users from interacting with you on GitHub.
* Repositories - view a list of your repositories.
* Organizations - view a list of your member organizations.
* Saved replies - create reusable snippets for GitHub comments.
* Applications - view applications with permission to access your account.

If you're still panicking about your personal email being visible to the world, here's where we're going to fix that. Click Emails. You can add or remove emails, and configure your preferences however you'd like. Check this box to hide your emails from the prying eyes of the cyber world.

![](../.gitbook/assets/private-email.png)

Most sections have some sort of save button at the bottom, so make sure you click this to persist your changes.

### Setting up an SSH Key

Before you can meaningfully use GitHub, you'll need to establish a connection between your computer and your account. To do that, you have to create and add an SSH key to your account.

An SSH key is a means by which your computer can identify itself to the GitHub servers. SSH keys come in pairs—a public key and private key. The public key is shared with GitHub, while the private key is stored locally on your computer. When you try to access GitHub, a "handshake" takes place between your computer and GitHub's servers. During this handshake, you are only granted access if the public/private key pair matches.

To start this process, enter the following command. Make sure you replace `rwilson@ucvts.org` with your actual email address, which should match the one you used to create your GitHub account.

![](../.gitbook/assets/ssh-key-1.png)

It'll run you through a series of prompts, first asking you to enter the file in which you want to save your public/private key pair. Unless you have a really good reason for doing so, accept the default location by pressing `Enter` without typing any other text.

![](../.gitbook/assets/ssh-key-2.png)

Next, you'll be asked to enter a password. You can leave this blank, too. Press `Enter`.

![](../.gitbook/assets/ssh-key-3.png)

Like most systems, you'll be asked to confirm the password you entered. If you left it blank the first time, leave it blank this time, too. If you chose to enter a password, confirm it.

![](../.gitbook/assets/ssh-key-4.png)

The strange little graphic you're seeing is called a randomart image, and it means your public/private key pair was successfully generated. You'll have two files: one with a `.pub` extension, and one without. The one with the `.pub` is your public key. You should never share your private key.

![](../.gitbook/assets/ssh-key-5.png)

Use the following command to copy the contents of your public key. This assumes you accepted the default location for your public/private key pair earlier. If you chose a custom location, you'll need to modify this command accordingly.

![](../.gitbook/assets/ssh-key-6.png)

Since I'm on a Mac and most of you are using Windows, there are a few differences in some of the commands. This is one of those uncommon occasions. Windows users should use this copy command.

```text
$ clip < ~/.ssh/id_rsa.pub
```

#### Copying the Key to GitHub

That wasn't too hard, right? Now, you just have to paste it into the appropriate section of your GitHub account settings. Click SSH and GPG keys in the Personal settings menu, then click New SSH key. Choose a suitable title that describes the computer you're using \(especially if you plan on generating multiple keys from multiple devices\) and enter this in the title field. Then, paste the contents of your public key in the key field.

![](../.gitbook/assets/github-settings-2.png)

Click Add SSH key, and you're all set.

## Setting up Visual Studio Code

Visual Studio Code, or VSCode, is a cross-platform editor from Microsoft. It provides a smooth programming environment, and offers a ton of cool plug-ins to aid in our development. All of the samples, demonstrations, and tutorials will be based on VSCode. You're free to use another editor if you'd like, but you'll be on your own in terms of installation, configuration, and usage.

The installation and setup is more-or-less the same for Windows or macOS. It's a point-and-click installation, so it's difficult to screw it up. Follow along with this video, which briefly covers installation, but focuses more on showing you how to use the editor.

You can ignore the typo in the beginning of the video. Or, you can laugh at his failure to proofread. Either way, the content thereafter is what we care about anyway.

{% embed url="https://www.youtube.com/watch?v=4NfFFsQC77M" %}

You don't need to setup your editor the way the video does, but it shows you how to configure a lot of things in VSCode. Feel free to customize your installation as you see fit.

