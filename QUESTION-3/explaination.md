# Command Explanations

1. `touch original_file.txt`
   - **Explanation:** Created an empty file named `original_file.txt`. This serves as the base file for demonstrating linking concepts.
2. `echo "Hello Linux" > original_file.txt`
   - **Explanation:** Redirected the string "Hello Linux" into the original file. This populates it with data so we can verify if the links properly access the content.
3. `ln original_file.txt hard_link.txt`
   - **Explanation:** Created a hard link named `hard_link.txt`. This creates a direct reference to the exact same physical inode on the disk as the original file.
4. `ln -s original_file.txt sym_link.txt`
   - **Explanation:** Created a symbolic (soft) link named `sym_link.txt`. This acts merely as a shortcut pointing to the filename `original_file.txt`, not its physical data blocks.
5. `ls -li original_file.txt hard_link.txt sym_link.txt`
   - **Explanation:** Listed the files alongside their inode numbers. I observed that `original_file.txt` and `hard_link.txt` shared identical inode numbers (`3932608`), while `sym_link.txt` had a unique inode (`3932609`).
6. `rm original_file.txt`
   - **Explanation:** Deleted the source file. I did this to test and demonstrate how the two different types of links behave when their parent file is removed.
7. `cat hard_link.txt`
   - **Explanation:** I read the contents of the hard link and it successfully printed "Hello Linux". This proves that the data remains on the disk as long as at least one hard link points to the inode.
8. `cat sym_link.txt`
   - **Explanation:** I attempted to read the symbolic link but received a "No such file or directory" error. This proves that soft links break (become dangling) when the path they point to is deleted.