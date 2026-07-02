1. `lsblk`
   - **Explanation:** This lists all block devices to give an overview of the system's physical storage structure. It showed an 80.1G primary disk (`sda`) with a single main partition (`sda1`).
2. `df -h`
   - **Explanation:** This displays disk space usage in human-readable sizes. I observed that the root partition (`/dev/sda1`) had a total size of 79G, with 58G still available and only 23% used.
3. `df -i`
   - **Explanation:** This displays the inode utilization for mounted filesystems, which tracks the number of files rather than physical byte size. It showed the root partition is extremely healthy, using only 10% of its available inodes.
4. `vi Storage_Assessment_Report.txt`
   - **Explanation:** I opened the `vi` text editor to draft and save the final storage assessment based on the metrics I gathered in the previous steps.