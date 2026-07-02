1. `lsof -u $(whoami) | head -n 15`
   - **Explanation:** This listed the first 15 open files and processes for my user `sarthak`. I observed that various background processes, specifically `systemd`, had multiple file descriptors actively open.
2. `ls -la /proc/$$/fd`
   - **Explanation:** This listed the file descriptors for my current shell session. It revealed how standard input (0), output (1), and error (2) are mapped to my terminal interface (`/dev/pts/0`).
3. `ls /fake_directory > standard_out.txt 2> error_out.txt`
   - **Explanation:** I attempted to list a non-existent directory while redirecting stdout to `standard_out.txt` and stderr to `error_out.txt`. This separates successful outputs from error logs.
4. `cat error_out.txt`
   - **Explanation:** I read the contents of the error log file. It confirmed that the standard error stream successfully caught the "cannot access '/fake_directory': No such file or directory" message.
5. `ulimit -a`
   - **Explanation:** This displayed all user-level resource limits for my active session. I observed limits such as the maximum number of open file descriptors, which is capped at 1024.