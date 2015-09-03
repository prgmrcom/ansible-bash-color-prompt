Bash Color Prompt
=========

This role globally overrides the bash shell prompt and makes it easy to set a custom color scheme per host or per group. 

Credits to https://wiki.archlinux.org/index.php/Color_Bash_Prompt for the list of colors.

Role Variables
--------------

color_prompt_base: The prompt, not including the strings which set the prompt color. Defaults to '\u@\h \W\$ \e[0m' 

color_prompt_target_file: file to write script to. By default the role writes a new prompt to the file /etc/profile.d/colorprompt.sh. The user must source a file that sources this from their .bashrc and not override PS1 in their local .bashrc for this script to take effect.

color_prompt_fg: The foreground color. Defaults to 'Color_Off'. Possible values are as follows:

Regular
* Black
* Red
* Green
* Yellow
* Blue
* Purple
* Cyan
* White

Bold
* BBlack
* BRed
* BGreen
* BYellow
* BBlue
* BPurple
* BCyan
* BWhite

Underlined
* UBlack
* URed
* UGreen
* UYellow
* UBlue
* UPurple
* UCyan
* UWhite

High Intensity
* IBlack
* IRed
* IGreen
* IYellow
* IBlue
* IPurple
* ICyan
* IWhite

Bold High Intensity
* BIBlack
* BIRed
* BIGreen
* BIYellow
* BIBlue
* BIPurple
* BICyan
* BIWhite

Color_Off will clear the color.

color_prompt_bg: The background color. Defaults to 'Color_Off'. Possible values are as follows:

Regular:
* Black
* Red
* Green
* Yellow
* Blue
* Purple
* Cyan
* White

High Intensity
* IBlack
* IRed
* IGreen
* IYellow
* IBlue
* IPurple
* ICyan
* IWhite

Color_Off will clear the color.

color_prompt_state: present or absent. If this variable is not defined, no action will be taken. Defaults to 'present'.

Example Playbook
----------------

    - hosts: database
      gather_facts: False
      roles:
         - { role: color-prompt, color_prompt_bg: Black, color_prompt_fg: Red }

    - hosts: webserver
      gather_facts: False
      roles:
         - { role: color-prompt, color_prompt_bg: Black, color_prompt_fg: Blue }

License
-------

GPLv3

Author Information
------------------

Please contact Sarah Newman - srn at prgmr.com - with any feedback.