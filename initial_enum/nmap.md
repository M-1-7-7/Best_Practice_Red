# How to initiate an attack with nmap enumeration
### set a single target
1. start with intialisting the [initialNMAP.sh](https://github.com/M-1-7-7/OSCP_SCRIPTS/blob/main/initialNMAP.sh)
2. make sure you have the [HTTP,HTTPS_web_enum.sh](https://github.com/M-1-7-7/OSCP_SCRIPTS/blob/main/HTTP%2CHTTPS_web_enum.sh) in the same directory
3. this will do a full tcp udp service scan on the target IP address,

### add a target range
1. create a list of numbers that represent the last octet and name it somthing like `ip_last_octet.txt` and add this below the `base_ip=...` line:
```
   # List of last octets
    touch ip_list.txt
    cat ip_last_octet.txt | while read line;
    do
      echo "$base_ip$line" >> ip_list.txt
    done;
```
2. add a funtion to the outside of everything like:
   ```
    cat ip_list.txt | while read line;
    do
      echo -e "===== Scanning $line =====\n"
    	ip=$line
      insert line 23 to 51
    done;
   ```
   
