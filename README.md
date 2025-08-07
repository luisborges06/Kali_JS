# Kali_JS
Run Kali linux (x86) on your Browser using V86 emulator! 

Just a Side-project created for testing & experimentation, hence open-sourced for sharing the experience .

If you are willing to try, you may follow these simple steps :

# Install & run :

1) Download Source Code from `release` section & extract the `.zip`
2) Run it locally on your device by python or npx <br>
    ```
    python -m http.server
    ```
     or
   ```
   npx http-server
     ```
3) Finally select the `kali.iso` and Boot it into FailSafe mode (HIGHLY RECOMMENDED!)
  <br> `Note: Other modes won't work , it will result into Kernel panic `
4) Optionally, you can use it to run other x86 images too.
   
<br />Credits:
<br /> For Base JS & Booting Structure [V86](https://github.com/copy/v86/blob/master/docs/how-it-works.md)
