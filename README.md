# RX-Modulator

BEFORE

<a href="http://imgur.com/HVHSfoR"><img src="http://i.imgur.com/HVHSfoR.png" title="Before" /></a>

AFTER

<a href="http://imgur.com/Whq44wj"><img src="http://i.imgur.com/Whq44wj.png" title="After" /></a>


A bash script in the theme of Kung Fury, utilizing git --date to commit 
in the past. Effectivly hacking you back in time.

Git commits are done on a once per-day psuedo-random coin flip basis from the
chosen start date. Simply run this again if your commit density is
less than desired.

<img src="https://i.ytimg.com/vi/KEkrWRHCDQU/maxresdefault.jpg" alt="Hackerman" height="350px"> 

Conduct a mainframe cell direct and hack the uplink to the download
It means that with the right computer algorithms, I can hack you back in time. Just like a time machine.

<a href="http://imgur.com/y86T2gc"><img src="http://i.imgur.com/y86T2gc.gif" /></a>

## Features

- GUI with references to the hit kickstarter movie [KUNG FURY](https://youtu.be/bS5P_LAqiVg?t=9m53s)
- Written in uncomplicated bash
- Create a personal repo, copy source, paste and [run](https://github.com/BillSkiCO/RX-Modulator#how-to-run).
- Stupidly [easy to use](https://github.com/BillSkiCO/RX-Modulator#basic-usage)
- Works on Mac and Linux (maybe on new windows 10?)

## How to run
#### Step 1
- Create new repo
```
Commits will only show up if:
The commits were made in a standalone repository, not a fork.
```
Thanks @michaeltangelo

#### Step 2
- Copy script into a new file in that repository
- Name it timehack for consistancy

#### Step 3
Make sure you have cURL, dialog, and git installed on your system

```bash
$ sudo apt-get update
$ sudo apt-get install curl
$ sudo apt-get install dialog
$ sudo apt-get install git
```

#### Step 4
Clone your new repository to your computer if new repo was created on github

```bash
$ git clone https://github.com/Your-Username/Repo-Name.git
$ cd ~/your-repo-name/
$ sudo bash timehack
```

#### Note
On *nix systems other than Linux it's fairly common for the GNU flavor of utilities to be installed prefixed with a ```g```
You may have to change ```date``` to ```gdate``` in the source code to get it working

TO TEST THIS:
See if you get any errors typing in 
```bash
$ date
```
If date errors arise, FEAR NOT! Just install gdate with homebrew using 

```bash
$ brew install coreutils
```
You will still have to change ```date``` to ```gdate``` after this

### Basic usage

```bash
$ sudo bash timehack    # must run sudo to make sure your git is configured correctly
```
- To move around the GUI simply use the arrow keys or click with the mouse.
- Press enter to submit forms.
- The prompt at the end for your username and password comes from git push. Not me!
```bash
$ # You are about to hack time are you sure?
$ dialog --backtitle "GitHub Time Hacker" \
$	--title "WARNING" \
$	--yesno "\nYOU'RE ABOUT\nTO HACK TIME,\nARE YOU SURE?" 10 30
$       
$ yn_response=$?
$ case $yn_response in
$ 	0) git push;;           # <--- Here's where the prompt is coming from
$	1) echo "Aborted";;
$	255) echo "Aborted";;
$ esac
```
## Contributing

#### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/BillSkiCO/RX-Modulator/issues) to report any bugs or file feature requests.

#### Developing

PRs are welcome. To begin developing, do this:

```bash
$ git clone git@github.com:BillSkiCO/RX-Modulator.git
$ cd RX-Modulator/
```
## Privacy
- There is a simple POST to google analytics at the beginning of the script for a "Hit Counter".
- [Here is a reference](https://developers.google.com/analytics/devguides/collection/protocol/v1/reference) for what each value means in the POST to analytics.

```bash
export analytics_id="UA-89577187-1"
export category="AppCounter"
export action="CountAction"
export label="CountLabel"
export value="1"

curl -s -X POST \
        -d 'v=1&tid='"$analytics_id"'&cid=555&t=event&ec='"$category"\
        '&ea='"$action"'&el='"$label"'&ev='"$value"'' \
        -H "User-Agent: AppSpecific" \
        https://www.google-analytics.com/collect > /dev/null &
```

- To remove, simply commment it out, or delete it.
