# Image
## Constructor
```ts
export function(assetid?: string): ImageComponent;
```
A component describing an image
#### Example
```lua
local Image = tab:Create('Image', 'rbxassetid://11441046007');
```
---
## Methods
### SetImage
```ts
export function SetImage(assetid?: string): ImageComponent;
```
Sets the Image to `assetid`
##### Example
```lua
Image:SetImage('rbxassetid://11441046007');
```
---
### SetHeight
```ts
export function SetHeight(height: number): ImageComponent;
```
Sets the height of the image to `height` pixels.
> Note: You will need to change the aspect ratio using [SetAspectRatio](#SetAspectRatio)
##### Example
```lua
Image:SetHeight(512);
```
---
### SetAspectRatio
```ts
export function SetAspectRatio(aspectratio: number): ImageComponent;
```
Sets the image's [AspectRatioConstraint.AspectRatio](https://developer.roblox.com/en-us/api-reference/property/UIAspectRatioConstraint/AspectRatio)
##### Example
```lua
Image:SetAspectRatio(1); --> Sets the image to a square
```
---
## Events
None
## Attributes
None
