# Base
This is the "base" component. It cannot be directly created, however it's bethods can be called on any component.

## Methods
### SetVisible
```lua
export function SetVisible(visible: boolean): Component;
```
Sets the component as visible/hidden
#### Example
```lua
local text = tab:Create('Text', '<i>Hello</i> World'):SetVisible(false); --> Creates a hidden component
task.wait(2);
text:SetVisible(true); --> Shows it after 2 seconds
```
