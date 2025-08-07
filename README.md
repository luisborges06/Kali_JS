# Kali_JS
Run Kali linux (x86) on your Browser as an emulator! 

⚠️ **it is just for experimentation & it is slower for 32-bit Operating systems. so have patience while booting.**
<br>

### If you are willing to try online, you may  [click here](https://kali-js.netlify.app) & make sure to downlaod `.iso` i provided in `release` section.

# Install & run Locally :

1) Download `.iso` & `.zip` from `release` section & extract the `.zip`
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

5) Optionally, you can use it to run other x86 images too.

## Recommendations: 
- After selection of `.iso` go to URL bar & paste this after profile=custom --> `&mute=1&m=2048&vram=256&boot_order=312&acpi=1`

