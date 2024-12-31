![bash_unit CI](https://github.com/pforret/gh_localdeploy/workflows/bash_unit%20CI/badge.svg)
![Shellcheck CI](https://github.com/pforret/gh_localdeploy/workflows/Shellcheck%20CI/badge.svg)
![GH Language](https://img.shields.io/github/languages/top/pforret/gh_localdeploy)
![GH stars](https://img.shields.io/github/stars/pforret/gh_localdeploy)
![GH tag](https://img.shields.io/github/v/tag/pforret/gh_localdeploy)
![GH License](https://img.shields.io/github/license/pforret/gh_localdeploy)
[![basher install](https://img.shields.io/badge/basher-install-white?logo=gnu-bash&style=flat)](https://www.basher.it/package/)

# gh_localdeploy

automatic deploy on LAN/localhost upon `github push`, using ngrok and webhook

## 🔥 Usage

```
Program : gh_localdeploy  by peter@forret.com
Version : v0.0.2 (2024-12-30 16:49)
Purpose : automatic deploy on LAN/localhost upon 'github push'
Usage   : gh_localdeploy [-h] [-Q] [-V] [-f] [-L <LOG_DIR>] [-T <TMP_DIR>] [-P <PORT>] [-H <HOOKS>] <action> <input?>
Flags, options and parameters:
    -h|--help        : [flag] show usage [default: off]
    -Q|--QUIET       : [flag] no output [default: off]
    -V|--VERBOSE     : [flag] also show debug messages [default: off]
    -f|--FORCE       : [flag] do not ask for confirmation (always yes) [default: off]
    -L|--LOG_DIR <?> : [option] folder for log files   [default: /home/pforret/log/gh_localdeploy]
    -T|--TMP_DIR <?> : [option] folder for temp files  [default: /tmp/gh_localdeploy]
    -P|--PORT <?>    : [option] deployment server will run on local port  [default: 8008]
    -H|--HOOKS <?>   : [option] webhook config file  [default: ./gh_localdeploy.yaml]
    <action>         : [choice] action to perform  [options: init,serve,check,env,update]
    <input>          : [parameter] input file/text (optional)
                                                                                                                                                                                                                                                                                                                                                                 
### TIPS & EXAMPLES
* use gh_localdeploy init to help and check the installation dependent tools
  gh_localdeploy init
* use gh_localdeploy serve to ...
  gh_localdeploy serve
* use gh_localdeploy action3 to ...
  gh_localdeploy action3
* use gh_localdeploy check to check if this script is ready to execute and what values the options/flags are
  gh_localdeploy check
* use gh_localdeploy env to generate an example .env file
  gh_localdeploy env > .env
* use gh_localdeploy update to update to the latest version
  gh_localdeploy update
* >>> bash script created with pforret/bashew
* >>> for bash development, also check out pforret/setver and pforret/progressbar
```

## ⚡️ Examples

```bash
> gh_localdeploy -h 
# get extended usage info
> gh_localdeploy env > .env
# create a .env file with default values
```

## 🚀 Installation

with [basher](https://github.com/basherpm/basher)

	$ basher install pforret/gh_localdeploy

or with `git`

	$ git clone https://github.com/pforret/gh_localdeploy.git
	$ cd gh_localdeploy

The following programs are also required:

### [ngrok](https://ngrok.com/) (free):

* create a free account on [dashboard.ngrok.com](https://dashboard.ngrok.com/) - this includes 2 free endpoints (e.g. 1 for development/testing and 1 for production)
* install Linux client: [Setup & Installation](https://dashboard.ngrok.com/get-started/setup/linux)
```bash
curl -sSL https://ngrok-agent.s3.amazonaws.com/ngrok.asc | sudo tee /etc/apt/trusted.gpg.d/ngrok.asc >/dev/null \
&& echo "deb https://ngrok-agent.s3.amazonaws.com buster main" | sudo tee /etc/apt/sources.list.d/ngrok.list \
&& sudo apt update && sudo apt install ngrok
```

### [adnanh/webhook](https://github.com/adnanh/webhook) (Golang - open-source)

```bash
sudo apt-get install webhook
```

## 📝 Acknowledgements

* script created with [bashew](https://github.com/pforret/bashew)
* [ngrok: GitHub Repository Webhooks](https://ngrok.com/docs/integrations/github/webhooks/)

&copy; 2024 Peter Forret
