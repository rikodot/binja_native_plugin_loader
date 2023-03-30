### How it works
On the start of Binary Ninja, this script checks if the related native plugin is present and either downloads it or verifies its version using native plugin's github repository. Native plugin requires its own repository which is also used for updating. Each native plugin requires its own loader. Unless there is a bug within this python script or an update is required or highly beneficial, this script is not supposed to be updated as it servers just as a loader. Exact behaviour is described within the script itself.

### Example
[binja_native_sigscan_loader](https://github.com/rikodot/binja_native_sigscan_loader) which is being used for loading [binja_native_sigscan](https://github.com/rikodot/binja_native_sigscan)

### Usage
1. create your native plugin for Binary Ninja
2. configure the script, there are 7 variables to be filled on the beginning of the file
3. follow official Binary Ninja's tutorial on how to write plugins
4. create one github repository for the native plugin itself (use github releases to push updates, each release needs to contain binaries for all supported operating systems - if you want to support let's say only linux, leave windows and macos variables in the script blank - read comments within the script or check out the example above for more context)
5. create second github repository for the loader (this is the one you are going to submit to the Binary Ninja's [community repository](https://github.com/Vector35/community-plugins))
6. for updating the native plugin, push a new release on **its** github repository, this loader will prompt all users to update on the next start of Binary Ninja

### Known issues
- in order to update or delete native plugins, Binary Ninja must be closed (at least on Windows), therefore updating must be done manually (for now)
