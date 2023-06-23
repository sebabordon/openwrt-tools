# openwrt-tools
Openwrt Scripts made by me...
**OpenVPN Server - Client list on status Page**

This simple and raw page + scrip will give you in the status page, the list of active OpenVPN Clients
The script will get the status from the openvpn default status on /var/run/openvpn.<instance>.status and post it to a file in /tmp
The html status page will get that information preformatted from the file and display it on the homepage of openwrt.

![image](https://github.com/sebabordon/openwrt-tools/assets/19667013/6af2838d-4a99-4e04-a9bd-3b86c8d0e1a2)

**Instructions**
copy _client-status.sh_ to a folder of your liking, maybe /etc/openvpn/
copy _openvpn.htm_ to /usr/lib/lua/luci/view/admin_status/index/ (index folder might not exist on your installation)
Add a new scheduled tasks on Openwrt, with the line 

   */1 * * * * /etc/openvpn/client-status.sh

Wait one minute for the client generation script to run and the clients will appear on the home page. 
I could not get the HTML page to run the script so I resorted to the scheduled task. 

This was made possible by some scripts I've found on the Openwrt Forums, so the credit is not fully mine. I will try to address the names as soon as I can find them. 
I'm sure it can be made simpler in a single html page but I lack the knowledge to do it
