1. `whoami`
   - Explanation: I ran this to display my current effective user ID. It confirmed that I am logged in as the user `sarthak`.
2. `groups`
   - Explanation: This command prints the groups a user is in. The output verified that my user belongs to the `sarthak` and `users` groups.
3. `echo $SHELL`
   - Explanation: By echoing the SHELL environment variable, I verified the command-line interpreter in use. The output showed `/bin/bash` as my current shell.
4. `pwd`
   - Explanation: This prints the absolute path of the current working directory. It confirmed I was operating within my home directory, `/home/sarthak`.
5. `ls -ls`
   - Explanation: This lists the directory contents alongside their sizes and permissions. I observed the standard default Kali Linux folders (Desktop, Documents, Downloads, etc.) owned by my user.
6. `ping -c 4 google.com`
   - Explanation: This sent 4 ICMP echo requests to Google to test external network connectivity. It returned 4 successful replies with 0% packet loss, confirming the environment is connected to the internet.