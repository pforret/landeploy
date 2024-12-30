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
Version : v0.0.1 (Apr 22 16:07:13 2023)
Purpose : automatic deploy on LAN/localhost upon 'github push'
Usage   : gh_localdeploy [-h] [-q] [-v] [-f] [-l <log_dir>] [-t <tmp_dir>] <action>
Flags, options and parameters:
    -h|--help        : [flag] show usage [default: off]
    -q|--quiet       : [flag] no output [default: off]
    -v|--verbose     : [flag] also show debug messages [default: off]
    -f|--force       : [flag] do not ask for confirmation (always yes) [default: off]
    -l|--log_dir <?> : [option] folder for log files   [default: /Users/pforret/log/script]
    -t|--tmp_dir <?> : [option] folder for temp files  [default: /tmp/script]
    <action>         : [choice] action to perform  [options: action1,action2,check,env,update]
                                  
### TIPS & EXAMPLES
* use gh_localdeploy action1 to ...
  gh_localdeploy action1
* use gh_localdeploy action2 to ...
  gh_localdeploy action2
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
