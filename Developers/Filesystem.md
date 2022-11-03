The Filesystem API ([see UNC FS](https://github.com/unified-naming-convention/NamingStandard/blob/main/api/filesystem.md)) functions allow you to read & write data to files in a directory (`Workspace`) on the device.

## Location

This directory is located at `/storage/emulated/0/Android/data/com.roblox.client/files/Fluxus/Workspace` on most devices & can be accessed using a more advanced file management tool like [Total Commander](https://play.google.com/store/apps/details?id=com.ghisler.android.TotalCommander&pcampaignid=MKT-Other-global-all-co-prtnr-py-PartBadge-Mar2515-1) or [MT Manager](https://apkcombo.com/mt-manager/bin.mt.plus/).

## APIs
---
### readfile
```ts
declare function readfile(path: string): string;
```
Reads the contents of the file at `Workspace/(path)` & returns said content.

#### Note
In certain edge-cases, attempting to read certain files will cause SecurityExceptions. Use with caution.

#### Example
```lua
local filename = 'test.txt'
if (not isfile(filename)) then writefile(filename, 'default content') end
print(readfile(filename)) --> prints 'default content', unless the file is altered on disk.
```
---
### writefile
```ts
declare function writefile(path: string, data: string): unknown
```
Writes `data` to the file at `Workspace/(path)` - Errors if `path` is a directory or if `data` is not a string.

#### Example
```lua
local filename = 'test.txt'
if (not isfile(filename)) then writefile(filename, 'default content') end
print(readfile(filename)) --> prints 'default content', unless the file is altered on disk.
```
---
### isfile
```ts
declare function isfile(path: string): boolean
```
Returns `true` if `path` exists, otherwise returns `false`

#### Example
```lua
local filename = 'test.txt'
if (not isfile(filename)) then writefile(filename, 'default content') end
print(readfile(filename)) --> prints 'default content', unless the file is altered on disk.
```
---
### delfile
```ts
declare function delfile(path: string): unknown
```
Deletes the file located at `path`. Errors if no file was found.
#### Example
```lua
local file = 'example'
writefile(file)
print(isfile(file)) --> true
delfile(file)
print(isfile(file)) --> false
```
---
### listfiles
```ts
declare function listfiles(path: string): string[]
```
Returns a list of files & directories in the directory located at `path` - The paths are relative to the `Workspace` directory.

#### Note
Certain Internal Fluxus files will be skipped by this function.

#### Example
```lua
if not isfolder('test') then makefolder('test') end
writefile('test/test.txt', 'example')
for idx, file in pairs(listfiles('test/')) do
  print(string.format('File: %s\nContent: %s')) --> File: test/test.txt\nContent: example
end
```
---
### makefolder
```ts
declare function makefolder(path: string): unknown
```
Creates a folder at  `path`, unless it already exists.
#### Example
```lua
if not isfolder('test') then makefolder('test') end
writefile('test/test.txt', 'example') -- without the first line, this would've errored because the directory `test/` does not exist
for idx, file in pairs(listfiles('test/')) do
  print(string.format('File: %s\nContent: %s')) --> File: test/test.txt\nContent: example
end
```
---
### isfolder
```ts
declare function isfolder(path: string): boolean
```
Returns `true` if the directory exists, otherwise returns `false`.
#### Example
```lua
if not isfolder('test') then makefolder('test') end
writefile('test/test.txt', 'example') -- without the first line, this would've errored because the directory `test/` does not exist
for idx, file in pairs(listfiles('test/')) do
  print(string.format('File: %s\nContent: %s')) --> File: test/test.txt\nContent: example
end
```
---
### delfolder
```ts
declare function delfolder(path: string): unknown
```
Deletes the folder located at `path`. Errors if no folder was found.
#### Example
```lua
local folder = 'example'
makefolder(folder)
print(isfolder(folder)) --> true
delfolder(folder)
print(isfolder(folder)) --> false
```
