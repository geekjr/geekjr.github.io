## Building and Bundling the app
1. First, create the app:
```shell
$ npx create-react-app tauri-tutorial
```
2. Next, `cd` into tauri-tutorial and install Tauri to that app:
```shell
$ yarn add tauri
```
3. Add the following to the `scripts` section of `package.json`
```json
"tauri": "tauri",
"dev": "npm run tauri dev",
"bundle": "tauri build",
```
4. Now we have to initalize the Tauri app. That can be done with the following:
```shell
$ npm run tauri init
```
5. Then, we have to tell npm to build our app:
```shell
npm run build
```
6. Finallly, we have to build the binary of our Tauri app:
```shell
npm run bundle
```
 The bundle command will take some time to run the first time it is being run. This is becuase it has to download all the Tauri crates. It will be faster on future runs. 
Once it is done running, you will find the binaries in the format of the specific os in the folder `tauri-tutorial/src-tauri/target/release/bundle`.
