1. `umask`
   - **Explanation:** This displays the current user file-creation mask. The output showed `0002`, meaning by default, write permissions are removed for "others" when new files/directories are created.
2. `mkdir -p project_workspace/docs project_workspace/code`
   - **Explanation:** I used the `-p` flag to create a parent directory (`project_workspace`) and two nested subdirectories (`docs` and `code`) simultaneously. This sets up the structural foundation for the secure workspace.
3. `touch project_workspace/docs/design.txt`
   - **Explanation:** This created a new, empty text file named `design.txt` inside the `docs` folder. It serves as a placeholder for project documentation.
4. `ls -l project_workspace/docs/design.txt`
   - **Explanation:** This displayed the detailed permissions of the newly created file. I observed the default permissions (`-rw-rw-r--`) applied based on my 0002 umask.
5. `chmod 700 project_workspace/code`
   - **Explanation:** I modified the permissions of the `code` directory to `rwx------`. This strictly locks down the folder so only the owner can read, write, or execute files inside it, enhancing security.
6. `chown $USER:$USER project_workspace/docs/design.txt`
   - **Explanation:** This explicitly sets the owner and group owner of `design.txt` to the current user (`BAPAIAH`). It ensures proper ownership boundaries are established for the project data.
