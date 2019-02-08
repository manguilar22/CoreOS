# <img src="https://github.com/manguilar22/icons/blob/master/coreOS.png" width="50" height="50"/> CoreOS

Configurations and Services

* Virtual Box
	- __Configuration File to setup CoreOS within Virtualbox__
	- ``` sudo coreos-install -d /dev/sda -C stable -c cloud-config.yaml ```
	
* Generate Hashed Passwords

```
# On Debian/Ubuntu (via the package "whois")
mkpasswd --method=SHA-512 --rounds=4096

# OpenSSL (note: this will only make md5crypt.  While better than plantext it should not be considered fully secure)
openssl passwd -1

# Python
python -c "import crypt,random,string; print(crypt.crypt(input('clear-text password: '), '\$6\$' + ''.join([random.choice(string.ascii_letters + string.digits) for _ in range(16)])))"

# Perl (change password and salt values)
perl -e 'print crypt("password","\$6\$SALT\$") . "\n"'
```
	
