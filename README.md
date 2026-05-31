Hello developer. I want to show you my new creation – SuperLua. In this module, I created a lot of functions that will make your work easier in the Lua environment. There are enough sections in this module to cover most of your problems:  

1. **string**
2. **string.bit**
3. **string.crypt**
4. **string.stego**
5. **math**
6. **table**
7. **file_manager**
8. **palette**
9. **luau**
10. **kernel**  

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
But if you use it in an exploit environment, then it's enough to do this:
```luau
local super_lua = loadstring(game:HttpGet("https://raw.githubusercontent.com/ADSKerOffical/SuperLua/refs/heads/main/super_lua.lua"))()
```
# Using
It was previously shown how to load the module (using require), but the terminal uses a slightly different method:
```bash
lua -e 'local super_lua = require("super_lua")' # from string
```
# Examples
I've counted 280+ functions in my module, so I'll show you examples of some of them
```lua
package.path = package.path .. ";/sdcard/?.lua;/storage/emulated/0/?.lua;/sdcard/Download/?.lua"
local sl = require("super_lua")

print(sl.string.crypt.from_decimal("\72\101\108\108\111\44\32\87\111\114\108\100\33")) -- Hello, World!
print(sl.math.to_fraction(25.07)) -- 2507/100
print(sl.math.round(math.pi, 2)) -- 3.14

for _, num in next, {1, 10.5, math.sqrt(2), math.pi} do
  print(num, sl.math.is_irrational(num)) -- sqrt(2) and pi is irrational
end

local roots = {}
for number = 1, 1000 do
  if sl.math.isroot(number) then
    table.insert(roots, number)
  end
end
print(table.concat(roots, " "))

local array = {1, 2, 3, 4, 5}
local dict = {a = 1, b = 2, c = 3}
local hybrid = {a = 1, [1] = 2, c = 3}

sl._EXPORT(sl.table, _G) -- loading all functions from super_lua.table in global env
print(isarray(array), isdict(array), ishybrid(array)) -- true false false
print(isarray(dict), isdict(dict), ishybrid(dict)) -- false true false
print(isarray(hybrid), isdict(hybrid), ishybrid(hybrid)) -- false false true
```
