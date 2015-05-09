# Raspberry-Pi-Send-Ip-Address
The code in this repository can be used to make your Raspberry Pi computer
send its ip address(es) to you in email whenever it changes.
This is very useful if your Pi is used on multiple networks uitilizing DHCP.
The code is based on work done by **Todd Lawall**.

##Installation
* Make sure that if you are using a wireless network that it is already present in `/etc/wpa_supplicant/wpa_supplicant.conf`. An example of this file
  is included in this repo.
* Copy the Python script `send_ip_address.py` to your favorite execution directory. I use `/usr/local/bin`
* Edit your `/etc/networks/interfaces` to look like the `interfaces` file that in this repository. If your binary is in `/usr/local/bin` you
  can use the file in this repo.

##Configuration
If you are lucky and have your own domain with a SMPT server and the ISP hosting the networks of your Raspberry Pi's does not block outbound
traffic on port 25 (like many of them do) you can edit the variables in `send_ip_address.py` to point to your email server and set your
username and password to what that account is set up for.
If on the other hand you do not have your own domain or your ISP is evil there is the option of using a regular gmail account.
You can either use an existing account you have or create a new one.

###Gmail credentials
You can use an existing gmail address and password, but if you are security concious you should use two factor authentication on your
Google account. If you use two factor authentication you can set up application specific password for your account that does not
require the second factor, and has limited privileges. To set this up simply go to [Google MyAccount](https://myaccount.google.com)
and select **Account Permissions** in the Connected apps and services section. On that page select **Manage app passwords** at the
bottom of that page. On the App passwords page select **Mail** and **Other** device as you generate the password. The generated password
is the one you specify together with the gmail.com account in `send_ip_address.py`.
