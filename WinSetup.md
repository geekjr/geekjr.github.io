## Windows setup
Note: It you already have Rust installed, it is a good idea to update it with `$ rustup update stable` before skipping to step 6. If you have any of the other things alredy installed, you can skip them as needed. Also, run all the commands from an **elevated(administrator)** Command Promt
The only prerequisite to install Taruri on Windows is Node.js
1. First, you will need to install Visual studio build tools. You can download the installer from [here](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16). Once the file is done downloading, run the file as administratior. Once you accept the license agreement, there will be a menu that comes up that allows you to select which build tools you need. From the workloads section, select C++ build tools and click install. This will take some time depending on your internet speed and computer speed. Once it is done installing, close the installer. 
2. Next, install Yarn:
```batchfile
> npm i yarn
```
3. Then, download and install Rust with its Cargo package manager. [64-bit](https://win.rustup.rs/x86_64) [32-bit](https://win.rustup.rs/i686)
4. And verify the installtaion:
```batchfile
> rustc --version
```
5. Enable loopback(this is required for the dev server:
```batchfile
> CheckNetIsolation.exe LoopbackExempt -a -n="Microsoft.Win32WebViewHost_cw5n1h2txyewy"
```
6. Finally, install Tauri Bundler via Cargo:
```batchfile
> cargo install tauri-bundler --force
```
Thats it! The setup is complete. You can now jump to the building app section. 
