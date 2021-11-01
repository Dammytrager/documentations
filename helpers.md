##### Check process ID running on a particular port

```bash
netstat -vanp tcp | grep <PORT>
```



##### Kill a process with process ID

```bash
kill -9 <PID>
```



##### Decode base64 from file

```bash
cat <path_to_base_64_file> | base64 -d > <path_to_output_file>
```



##### Bye bug doc

[https://github.com/deivid-rodriguez/byebug](https://github.com/deivid-rodriguez/byebug)



##### Rails `link_to` helper

[https://www.rubyguides.com/2019/05/rails-link_to-method/](https://www.rubyguides.com/2019/05/rails-link_to-method/)



##### Configure Rails Db

[https://guides.rubyonrails.org/configuring.html#configuring-a-database](https://guides.rubyonrails.org/configuring.html#configuring-a-database)



##### Create a WireFrame 

[https://balsamiq.com/](https://balsamiq.com/)



#### Installing wkhtmltopdf

```bas
yum install -y xorg-x11-fonts-75dpi xorg-x11-fonts-Type1
```



```bas
yum install -y  xorg-x11-fonts-100dpi.noarch xorg-x11-fonts-75dpi.noarch xorg-x11-fonts-ISO8859-1-100dpi.noarch xorg-x11-fonts-ISO8859-1-75dpi.noarch xorg-x11-fonts-ISO8859-14-100dpi.noarch xorg-x11-fonts-ISO8859-14-75dpi.noarch xorg-x11-fonts-ISO8859-15-100dpi.noarch xorg-x11-fonts-ISO8859-15-75dpi.noarch xorg-x11-fonts-ISO8859-2-100dpi.noarch xorg-x11-fonts-ISO8859-2-75dpi.noarch xorg-x11-fonts-ISO8859-9-100dpi.noarch xorg-x11-fonts-ISO8859-9-75dpi.noarch xorg-x11-fonts-Type1.noarch xorg-x11-fonts-cyrillic.noarch xorg-x11-fonts-ethiopic.noarch xorg-x11-fonts-misc.noarch
```



##### Show Git Branch in Terminal

```bash
function parse_git_branch() {
    git branch 2> /dev/null | sed -n -e 's/^\* \(.*\)/[\1]/p'
}

COLOR_DEF=$'\e[0m'
COLOR_USR=$'\e[38;5;243m'
COLOR_DIR=$'\e[38;5;197m'
COLOR_GIT=$'\e[38;5;39m'
setopt PROMPT_SUBST
export PROMPT=%B'${COLOR_DEF}%~${COLOR_GIT}$(parse_git_branch)${COLOR_DEF}$ '%b

```



