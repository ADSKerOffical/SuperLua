Hello developer. I want to show you my new creation – SuperLua. In this module, I created a lot of functions that will make your work easier in the Lua environment. There are enough sections in this module to cover most of your problems:  

1. **string**
2. **string.bit**
3. *"string.crypt**
4. **math**
5. **table**
6. **file_manager**
7. **kernel**  

# Installation  
The installation mainly depends on your environment  
## Termux  
If you have the curl command available, you can easily download the file from the URL:  
```bash
curl -s https://raw.githubusercontent.com/ADSKerOffical/SuperLua/refs/heads/main/super_lua.lua > super_lua.lua
```
But if you still don't have curl command, then download super_lua.lua from this repository and run this command:
```bash
# Let's say that your External Storage is /sdcard
echo "$(cat /sdcard/Download/super_lua.lua)" > super_lua.lua
# Usually files downloaded from GitHub appear in this folder
```
## From File Storage
If your environment is not a terminal (like Termux), then it's a little more complicated. Your path must be specified using package.path
```lua
package.path = package.path .. ";/sdcard/?.lua;/storage/emulated/0/?.lua;/sdcard/Download/?.lua" -- searches for such a module in these folders when used require
local super_lua = require("super_lua") -- Now you can use the module
```
## Luau (Roblox)
It also depends on the environment. If you are using this in roblox studio, then you need to do the following:  

1. **Create ModuleScript (for example game.ReplicatedStorage.SuperLua)**  
2. **Paste the SuperLua source code into this ModuleScript**  
3. **Use this:**  
```luau
local super_lua = require(game.ReplicatedStorage.SuperLua)
```
**And that's all**
