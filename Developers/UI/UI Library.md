# UI Library
Fluxus' UI Library is pretty straightforward; it's structured into [Tabs](#createtab), each tab has it's own icon (what's shown on the left) & it's own components.

> Note: You cannot directly manipulate the UI's Instance Structure on Fluxus Android.
> This might be possible with [the Desktop Polyfill](#polyfill) in the future

## Accessing the API
Internally, the UI Library is exposed using 3 variables;
```lua
getgenv().fluxusandroidui = API -- branded ui variable w/ platform
getgenv().androidui = API -- unbranded ui variable w/ platform
getgenv().execui = API -- unbranded ui variable w/o platform
```

Although you can use any of those 3, we'd strongly suggest using `execui`.

## Root Level API
Root-Level APIs can be accessed directly on the `execui` object.

---
### CreateTab
```ts
export function CreateTab(assetid: string): Tab;
```
Creates a [Tab](#tab), accessible with the specified icon.

> Note: Tabs cannot, as of writing, be destroyed, and are always created right above the settings tab.

#### Example
```lua
local tab = execui:CreateTab('rbxassetid://<your icon>');
```
---
### SetSmallUIEnabled
```ts
export function SetSmallUIEnabled(UseSmallUI: boolean): null;
```
Toggles whether we use the [Small UI](/Getting%20Started/Settings#SmallUI) or not. This does not save, unlike if you use the option in the settings menu.

#### Example
```lua
execui:SetSmallUIEnabled(true); --> enables the small ui
```
---
### Minimize
```ts
export function Minimize(): null;
```
Minimizes the UI.

#### Example
```lua
execui:Minimize();
```
---
### Unminimize
```ts
export function Unminimize(): null;
```
Unminimizes the UI.

#### Example
```lua
execui:Unminimize();
```
---
## Tab
### Create
```ts
export function Create(componentType: string, ...componentArgs: any[]): Component;
```
Returns a [Component](#components) as specified by `componentType`, passes `...componentArgs` to the component

#### Example
```lua
tab:Create('Text', 'Hello World');
```
---
### Focus
```ts
export function Focus(): null;
```
Focuses the tab

#### Example
```lua
tab:Focus();
```
---
## Components
- [Base](/Developers/UI/Components/Base)
- [Text](/Developers/UI/Components/Text)
- [Button](/Developers/UI/Components/Button)
- [Checkbox](/Developers/UI/Components/Checkbox)
- [Textbox + TextBoxMultiLine](/Developers/UI/Components/Textbox)
- [Image](/Developers/UI/Components/Image)
- [Spacer](/Developers/UI/Components/Spacer)
- [Search](/Developers/UI/Components/Search)
- [ExecBox](/Developers/UI/Components/ExecBox) _Internal, you likely don't have a use for this._
---
## Polyfill
> Currently not implemented. This "polyfill" will let you use the exact same code you're using to integrate with the Android UI, as a standalone UI Library for Desktop.