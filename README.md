# wp-cli-DA

Step 1: Install WP-CLI
/usr/local/directadmin/custombuild/build wp

OR

curl -O https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
chmod +x wp-cli.phar
sudo mv wp-cli.phar /usr/local/bin/wp
Check: wp --info

Step 2: Adjust PHP Functions
cd /usr/local/directadmin/custombuild
mkdir custom
touch custom/php_disable_functions
echo "exec,system,passthru,shell_exec,dl,popen,show_source,posix_kill,posix_mkfifo,posix_getpwuid,posix_setpgid,posix_setsid,posix_setuid,posix_setgid,posix_seteuid,posix_setegid,posix_uname" > custom/php_disable_functions
./build set secure_php yes
./build secure_php
Check: grep disable_functions /usr/local/php*/lib/php.ini

Step 3: 1-Click Install
bash <(wget -qO- https://raw.githubusercontent.com/hvmediavn/wp-cli-DA/main/DA_WP/install.sh)
