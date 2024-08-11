# Connect to EC2 Instance Using Remote-SSH Extension

## Setting Up VS Code for SSH

1. **Install the Remote - SSH Extension**:
   - Open VS Code.
   - Go to the Extensions view by clicking on the Extensions icon in the Activity Bar on the side of the window or by pressing `Ctrl+Shift+X`.
   - Search for `Remote - SSH` and click `Install` on the extension provided by Microsoft.

2. **Configure Your SSH Connection**:
   - **Open the Command Palette**: Press `Ctrl+Shift+P` (or `Cmd+Shift+P` on macOS).
   - **Search for and Select**: `Remote-SSH: Open Configuration File`.
   - **Choose the File**: You may need to select a configuration file (typically `config` located in the `.ssh` directory).

   If you don’t have a config file, you can create one by adding a new file named `config` in the `.ssh` directory (usually located in your user’s home directory). Add the following configuration:

   ```plaintext
   Host my-ec2
     HostName <your-ec2-public-dns>
     User ec2-user
     IdentityFile <path-to-your-pem-file>
   ```

   Replace `<your-ec2-public-dns>` with your EC2 instance’s public DNS and `<path-to-your-pem-file>` with the path to your `.pem` file.

3. **Connect to the EC2 Instance**:
   - **Open the Command Palette** again (`Ctrl+Shift+P` or `Cmd+Shift+P`).
   - **Search for and Select**: `Remote-SSH: Connect to Host...`.
   - **Choose**: `my-ec2` (or whatever name you used in your SSH config file).

4. **Open Your Project**:
   - Once connected, you’ll be able to browse the files on your EC2 instance.
   - Open the folder or workspace where your project is located.

5. **Perform Development Tasks**:
   - You can now edit files, run terminal commands, and use Git directly from within VS Code.

### Troubleshooting

- **Ensure that** your `.pem` file permissions are correct and that it is not publicly accessible. Linux `chmod 400 <path-to-your-pem-file>` for Windows `icacls "C:\path\to\your\file.pem" /grant:r %username%:R` to restrict permissions if necessary.
- **Verify the SSH Configuration**: Ensure that the `config` file in the `.ssh` directory is correctly set up with the proper details for connecting to your EC2 instance.

By following these steps, you should be able to use VS Code effectively to manage and develop your project on your EC2 instance.
