# fortudon

**Fortudon v3-dev (20200126)**

Fortudon is a Fediverse bot designed for posting random BSD-style fortunes
directly to Mastodon and Pleroma instances. It incorporates a fork of 
fortune.py and includes its own Fediverse bot features.

**REQUIREMENTS:**

* Python 3.5 or higher
* Mastodon.py and its dependencies
* curl
* Fortune files, such as those provided with fortune-mod or BSD fortune

**DIFFERENCES BETWEEN FORTUDON AND FORTUNE.PY:**

The original fortune.py was created by Michael Goerz in 2008. It was only
compatible with Python 2. cPickle was used to create data files, with 
protocol version 2 and extension `.pdat`. The program worked inconsistently
depending on the terminal's character encoding. Offensive fortune files
ending in `-o` were supported, but unlike traditional BSD fortune, these files
are not ROT13-rotated.

http://www.physik.fu-berlin.de/~goerz

fortune.py was forked by Volker Kettenbach in 2018 and was designed to work
with Python 3.7.1 and UTF-8 fortune files. cPickle was replaced with Pickle,
and protocol was left compatible at legacy version 2.

https://gitlab.com/volkerkettenbach/fortune-api/tree/master

Fortudon was forked from Kettenbach's fortune.py in 2020 by redneonglow.
Changes were made with regard to use of legacy code. The pickle protocol
was changed to version 4 and the file extension is now `.p4dat`. As with the
traditional fortune package, offensive fortune files must be ROT13-rotated in
addition to ending in `-o`. Posting and searching offensive fortunes will
automatically apply ROT13 as needed.

Fortudon is designed as a Fediverse bot with built in support for posting
fortunes to Pleroma and Mastodon instances. Code from Dark Web Mystery Bot
(another Fediverse bot by redneonglow) was incorporated into Fortudon.

https://github.com/redblade7/darkwebmysterybot

Fortudon, like fortune.py, is licensed under the GPLv3.

The official Web site for Fortudon is:

https://github.com/redblade7/fortudon

**SET UP THE TOKEN FILE:**

1. Create a Fediverse account for your Fortudon bot.
2. Set up a token here: https://tinysubversions.com/notes/mastodon-bot/
3. Create a token file by running this command:
   `curl <command you are given> > tokenfile.json`

**EXAMPLE COMMANDS:**

Show help: `./fortudon.py -h`

Show version: `./fortudon.py -v`

Generate required `.p4dat` data files for fortunes in folder `fortune-folder`: `./fortudon.py -u fortune-folder`

Display random fortune chosen from non-offensive files in `fortune-folder`: `./fortudon.py fortune-folder`

Display random long fortune chosen from either `fortune-folder/myfortunes1` or `fortune-folder/myfortunes2`: `./fortudon.py -l fortune-folder/myfortunes1 fortune-folder/myfortunes2`

Post random short fortune, choosing from both offensive and non-offensive files in `fortune-folder`, to Pleroma instance Neckbeard, using token file `tokenfile.json` and public visibility: `./fortudon.py -sap https://neckbeard.xyz tokenfile.json public fortune-folder`

Post random short fortune, chosen from non-offensive files in `fortune-folder`, to Mastodon instance `mastodon.social`, using token file `wokenfile.json` and unlisted visibility: `./fortudon.py -sp https://mastodon.social wokenfile.json unlisted fortune-folder`

**VISIBILITY:**

The visibility option may be any of the following:

* `direct` (only visible to the bot account)
* `private` (only visible to the bot account's followers)
* `public` (visible to everyone)
* `unlisted` (visible to everyone, but hidden from the public timeline)

In most cases you would want to use either `public` or `unlisted` for the visibility option.

Enjoy!

-redblade7 aka redneonglow

**FEDIVERSE CONTACT INFO:**

* `@redneonglow@neckbeard.xyz` / https://neckbeard.xyz/redneonglow (main)
* `@redneonglow@anime.website` / https://anime.website/redneonglow (backup)
* `@redneonglow@weeaboo.space` / https://weeaboo.space/redneonglow (backup)

**FORTUNE BOTS RUNNING FORTUDON:**

* `@YKYWTMSMW@neckbeard.xyz` / https://neckbeard.xyz/ykywtmsmw
