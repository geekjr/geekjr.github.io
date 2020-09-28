## Ubuntu/Debian setup
Note: It you already have Rust installed, it is a good idea to update it with `$ rustup update stable` before skipping to step 6. If you have any of the other things alredy installed, you can skip them as needed. 
The only prerequisite to install Taruri on Ubuntu/Debian is Node.js with npm.
1. First, install the required dependencies. This can be done with the following command:
```shell 
$ sudo apt update && sudo apt install libwebkit2gtk-4.0-dev \
    build-essential \
    curl \
    libssl-dev \
    appmenu-gtk3-module \
    libgtk-3-dev
```
2. Next, install Yarn:
```shell
$ npm i yarn
```
3. Then, install Rust with it's Cargo Manager:
```shell
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
4. And verify the installtaion:
```shell
$ rustc --version
```
5. Finally, lets install the Tauri Bundler via Cargo:
```shell
$ cargo install tauri-bundler --force
```
Thats it! The setup is complete. You can now jump to the building app section. 
