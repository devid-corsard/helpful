In macOS, you cannot assign two owners to the same directory or file. Each file or directory has a single owner. When you use the `chown` command with the `-R` flag to recursively change ownership, it replaces the existing owner with the new owner you specify. In your case, the ownership of the `/usr/local/Homebrew` directory will be changed to `user2`, and any subdirectories and files under it will also be changed to have `user2` as the owner.

If you need multiple users to have access to the same files or directories, you can use group ownership and permissions to control access.

Here's how you can do it:

1. Create a group: You can create a group and add both `user1` and `user2` to that group. Use the `dseditgroup` or `sudo dscl . create /Groups/groupname` command to create a group.

2. Add users to the group:
   ```
   sudo dseditgroup -o edit -a user1 -t user groupname
   sudo dseditgroup -o edit -a user2 -t user groupname
   ```

3. Change ownership to the group:
   ```
   sudo chown -R :groupname /usr/local/Homebrew
   ```

4. Set permissions:
   ```
   sudo chmod -R 775 /usr/local/Homebrew
   ```

This will give both `user1` and `user2` access to the `/usr/local/Homebrew` directory and its contents, with `user2` as the owner and `groupname` as the group. `775` permissions allow the owner and group to read, write, and execute, and others to read and execute.

Keep in mind that this approach allows multiple users to access the files and directories but doesn't provide a true multi-owner setup, as macOS, like most Unix-based systems, doesn't support multiple owners for the same file or directory. Instead, it uses ownership and group membership to manage access and permissions.
