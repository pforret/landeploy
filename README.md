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
Program : landeploy  by peter@forret.com
Version : v0.1.0 (2024-12-31 13:27)
Purpose : automatic deploy on LAN/localhost upon 'github push'
Usage   : landeploy [-h] [-Q] [-V] [-f] [-L <LOG_DIR>] [-T <TMP_DIR>] [-B <BRANCH>] [-D <DOMAIN>] [-E <ENVIRONMENT>] [-H <HOOKS>] [-P <PORT>] [-R <REMOTE>] [-Y <REDEPLOY>] <action>
Flags, options and parameters:
    -h|--help        : [flag] show usage [default: off]
    -Q|--QUIET       : [flag] no output [default: off]
    -V|--VERBOSE     : [flag] also show debug messages [default: off]
    -f|--FORCE       : [flag] do not ask for confirmation (always yes) [default: off]
    -L|--LOG_DIR <?> : [option] folder for log files   [default: log/landeploy]
    -T|--TMP_DIR <?> : [option] folder for temp files  [default: .tmp]
    -B|--BRANCH <?>  : [option] remote repo branch  [default: main]
    -D|--DOMAIN <?>  : [option] ngrok domain to use (from https://dashboard.ngrok.com/domains)
    -E|--ENVIRONMENT <?>: [option] deployment type (only php for now)  [default: php]
    -H|--HOOKS <?>   : [option] webhook config file  [default: landeploy.yaml]
    -P|--PORT <?>    : [option] local port for ngrok service  [default: 8008]
    -R|--REMOTE <?>  : [option] remote repo name  [default: origin]
    -Y|--REDEPLOY <?>: [option] deploy script file  [default: redeploy.sh]
    <action>         : [choice] action to perform  [options: init,serve,check,env,update]
                                                                                                                                                                                                                                                                                                                                                                 
### TIPS & EXAMPLES
* use landeploy init to do/check the installation of ngrok and webhook
  landeploy init
* use landeploy serve to start local webhook server and remote tunnel
  landeploy serve
* use landeploy check to check if this script is ready to execute and what values the options/flags are
  landeploy check
* use landeploy env to generate an example .env file
  landeploy env > .env
* use landeploy update to update to the latest version
  landeploy update
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
