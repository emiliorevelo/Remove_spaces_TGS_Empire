# Remove_spaces_TGS_Empire
Removing blank spaces on the TGSs obtained when executing Invoke_Kerberoast using the framework Empire.


cat file.txt | tr -d "[:blank:]" | tr -d " \t\n\r"
a=$(echo -e '$krb...'|tr -d "[:blank:]" | tr -d " \t\n\r")
echo -e $a >> file

Once done, in order to crack them you can use hashcat as follows:

hashcat -m 13100 -a 0 file /usr/share/wordlists/sqlmap.txt --force
