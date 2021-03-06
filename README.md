# Discord-python-Example
A barebones example Discord bot, written in Python 3.6 using the [discord.py](https://github.com/Rapptz/discord.py) library.

See also [CSSBot](https://github.com/Chris-Johnston/CSSBot), same idea just in C#.

# Installation / Setup / Usage

This project is meant for Python 3.5 and up. Please insure that you have that
Python 3.5 or higher installed. You can check this using `python --version`
or `python3 --version`.

Python 3.5 is shipped by default in the latest versions of Ubuntu.

## Prerequisites
You'll need to install some packages first. These are included in the
`requirements.txt` file for you.

Linux:
```bash
python3 -m pip install -r requirements.txt
# only required for doing voice on Linux environments
sudo apt-get install libffi-dev python3-dev
```

See the [discord.py documentation](http://discordpy.readthedocs.io/en/rewrite/intro.html#installing)
for why the additional tools are necessary.

Windows:
```
py -3 -m pip install -r requirements.txt
```

Mac:
```
python3 -m pip install -r requirements.txt
```

## Setup

- Register your own Discord bot for testing with.
  - Navigate to the Discord API docs and log in: https://discordapp.com/developers/applications/me (If you log in for the first time, it'll probably take you to the app, so go back to this link again).
  - Click on the "New App" button.
  - Name your app. Click "Create App".
  - Click "Create a Bot User". (Discord API supports a few types of apps/bots, but we are building a bot)
  - Locate your bot's user token. **Your user token must not be shared with anyone. If it is posted publicly, change it ASAP.**
    - Please refer to the best practices for storing and managing connection tokens. `todo`
- Fork this repo.
- Clone your copy of this repo using `git clone https://github.com/USERNAME/CSSBot_Py.git`
- Create a new file in your CSSBot_Py directory: `config.ini`
  - Populate the file with the following contents:
  ```ini
  [Configuration]
  connection_token=XXXXXXXXXYOURTOKENGOESHEREXXXXXXX
  ```

## Usage

Run the following command:
```bash
python3 main.py
```

The first lines should read something like:
```
using discordpy version 1.0.0a
Logged in SomeUser - 1234567890
Version 1.0.0a
```

## FAQ - Common Issues

### AioHTTP

#### Problem

When I run `python3 main.py` I get this error.

`TypeError: Inheritance a class <class 'aiohttp.http_writer.URL'> from URL is forbidden`

#### Solution

Update your requirements.txt with the latest version from this repo with the latest contents. The file should contain:

```
yarl<1.2
git+https://github.com/Rapptz/discord.py@rewrite#egg=discord.py[voice]
```

Run your `python3 -m pip install -r requirements.txt` (or equivalent) command again, then `python3 main.py`.

### Mac SSL Cannot Connect

#### Problem

On Mac, with Python 3.6, I cannot get my bot to connect online, and the error log complains about some SSL issue.

#### Solution

You need to install certificates. Navigate to `Applications/Python 3.6`, and double click the `Install Certificates.command` file. Give it a few seconds. Once the terminal window stops doing stuff, you can close it. Retry running the bot with `python3 main.py`.

### Pip Install Doesn't Work

#### Problem

When I run `py -3 -m pip install -r requirements.txt`, the installation fails for some reason.

#### Solution

Ensure that you have git installed, since the requirements installation process makes use of git.


### `python3` is not recognized as an internal or external command... (Windows)

On windows, you need to use `py` isntead of `python3`. Ensure that you have Python installed, and re-open your command window 
to ensure that your `%PATH%` has been updated.

# Contributing

This bot is intended to serve as an example. Either use this code as a reference or a base to make your own bot!

## Reference Material

Here are some resources to get you started:

https://github.com/Rapptz/discord.py

https://discordapp.com/developers/docs/intro

http://discordpy.readthedocs.io/en/rewrite/

http://discordpy.readthedocs.io/en/rewrite/ext/commands/api.html

https://gist.github.com/MysterialPy/d78c061a4798ae81be9825468fe146be
