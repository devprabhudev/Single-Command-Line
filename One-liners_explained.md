### Single Command Line 
In computer science One liners or single line command refers to a sequence of commands grouped together using symbols such as &, &&, and | |, allowing the command interpreter to process them either sequentially or based on certain conditions.
The service desk or support agents can copy paste a single command that performs multiple actions.This approach reduces human error, speeds up resolution times and even allows less experienced members to run sophiscated fixes or configurations.
```
php -v >/dev/null 2>&1 && echo -e "\e[32mPhp version: $( php -v | head -n 1 | awk '{print $2}') is already installed \e[0m" || echo -e "\e[31mPhp is not installed \e[0m"
```
#The above one line checks if php is installed, if yes it prints the version installed in green output color and if not it gives an output in red indicating an error

```
php_enabled=$(sudo yum module list php | awk '$3 ~ /\[e\]/ {print $2}' | grep -E '^[0-9]+\.[0-9]+' | sort -u) ; [[ "$php_enabled" == "8.2" ]] && echo -e "\e[32mTarget php version matches the enabled php version in the server (${php_enabled})\e[0m" ||  echo -e "\e[31mTarget php version mismatches the enabled version (${php_enabled})\e[0m"	
```
#The command checks if php is available as modular streams, in oracle linux 8 and above php is available in modular streams, it checks and compares it with the required target version which is 8.2 in this example.

```
echo -n Q | openssl s_client -servername example.production.com -connect example.production.com:443 | openssl x509 -noout -dates	
```
The command checks the ssl validity on 443
```
systemctl is-active -q httpd && echo -e "\e[32mApache is active\e[0m"; [[ -f "/etc/httpd/conf.d/example.conf" ]] && echo -e "\e[32mApache configuration example.conf found\e[0m" || echo -e "\e[31mApache configuration example.conf missing,copy it from
backup\e[0m"	file name:example.conf,contains document root,rewrite rules,ssl configuration.
```
 
```
source /etc/os-release; [ "x${ID}x" = "xolx" ] && echo -e "\e[32mLinux distribution complies (${ID})\e[0m" ||  echo -e "\e[31mWrong Linux distribution (${ID})\e[0m"; [[ $(echo $VERSION | cut -d'.' -f 1) -eq 9 ]] && echo -e "\e[32mOracle  Linux version complies (${VERSION})\e[0m" || echo -e "\e[31mBad Oracle Linux version (${VERSION})\e[0m"; VERSION=$(/usr/bin/mysql --version | awk  ' NR==1 { print $3 } ' | cut -d'.' -f 1) && [[ $VERSION -eq 8 ]] && echo -e "\e[32mMySQL version complies (${VERSION})\e[0m" || echo -e "\e[31mBad MySQL version (${VERSION})\e[0m"; VERSION=$(/usr/bin/php --version | awk  ' NR==1 { print $2 } ' | cut -d'.' -f 1) && [[ $VERSION -eq 8 ]] && echo -e "\e[32mPHP version complies (${VERSION})\e[0m" || echo -e "\e[31mBad PHP  version (${VERSION})\e[0m"
```	
#the above one line checks if OS is oracle linux 9, php version and mysql version. 
