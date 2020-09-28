## Mac setup
Note: It you already have Rust installed, it is a good idea to update it with `$ rustup update stable` before skipping to step 6. If you have any of the other things alredy installed, you can skip them as needed. 
The only prerequisite to install Taruri on Mac(besides Node.js) is [homebrew](https://brew.sh/). If you don't have it installed alredy, you can install it by running: 
```shell 
$ /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```
1. Once you have homebrew installed, you need to install the Xcode command line tools. That can be done with the following command:
```shell 
$ xcode-select --install
```
2. Next, you will need to install gcc:
```shell
$ brew install gcc
```
3. Then, install Yarn:
```shell
$ npm i yarn
```
4. Now, lets install Rust with it's Cargo Manager:
```shell
$ curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
5. And verify the installtaion:
```shell
$ rustc --version
```
6. Finally, lets install the Tauri Bundler via Cargo:
```shell
$ cargo install tauri-bundler --force
```
Thats it! The setup is complete. You can now jump to the building app section. 
