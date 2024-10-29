### Single Command Line 
# In computer science Computer Science refers to a sequence of commands grouped together using symbols such as &, &&, and | |, allowing the command interpreter to process them either sequentially or based on certain conditions.
```
php -v >/dev/null 2>&1 && echo -e "\e[32mPhp version: $( php -v | head -n 1 | awk '{print $2}') is already installed \e[0m" || echo -e "\e[31mPhp is not installed \e[0m"
```
#The above command checks if php is already installed, it suppresses the output by >/dev/null. > is used to write the output to a file or some location.
#head -n 1 gets the first line of the out put. Echo -e is used to get color formats. 32m is green and 31m is black.
```
php_enabled=$(sudo yum module list php | awk '$3 ~ /\[e\]/ {print $2}' | grep -E '^[0-9]+\.[0-9]+' | sort -u) ; [[ "$php_enabled" == "8.2" ]] && echo -e "\e[32mTarget php version matches the enabled php version in the server (${php_enabled})\e[0m" ||  echo -e "\e[31mTarget php version mismatches the enabled version (${php_enabled})\e[0m"	
```
#The command on line 9 checks, if php is available as modular stream.It finds the enabled modular stream of php. 8.2 is target php version. 

echo -n Q | openssl s_client -servername example.production.com -connect example.production.com:443 | openssl x509 -noout -dates	

#The command on line 13 checks the ssl cert validity. 

systemctl is-active -q httpd && echo -e "\e[32mApache is active\e[0m"; [[ -f "/etc/httpd/conf.d/example.conf" ]] && echo -e "\e[32mApache configuration eample.conf found\e[0m" || echo -e "\e[31mApache configuration example.conf missing,copy it from backup\e[0m"	file name:amecms.conf,contains document root,rewrite rules,ssl configuration. 

source /etc/os-release; [ "x${ID}x" = "xolx" ] && echo -e "\e[32mLinux distribution complies (${ID})\e[0m" ||  echo -e "\e[31mWrong Linux distribution (${ID})\e[0m"; [[ $(echo $VERSION | cut -d'.' -f 1) -eq 9 ]] && echo -e "\e[32mOracle  Linux version complies (${VERSION})\e[0m" || echo -e "\e[31mBad Oracle Linux version (${VERSION})\e[0m"; VERSION=$(/usr/bin/mysql --version | awk  ' NR==1 { print $3 } ' | cut -d'.' -f 1) && [[ $VERSION -eq 8 ]] && echo -e "\e[32mMySQL version complies (${VERSION})\e[0m" || echo -e "\e[31mBad MySQL version (${VERSION})\e[0m"; VERSION=$(/usr/bin/php --version | awk  ' NR==1 { print $2 } ' | cut -d'.' -f 1) && [[ $VERSION -eq 8 ]] && echo -e "\e[32mPHP version complies (${VERSION})\e[0m" || echo -e "\e[31mBad PHP  version (${VERSION})\e[0m"	
#the above one line checks if OS is oracle linux 9, php version and mysql version. 
