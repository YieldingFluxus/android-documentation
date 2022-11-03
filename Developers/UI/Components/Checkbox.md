## Constructor
```ts
export function(text: string, checked?: boolean = false): TextComponent;
```
Creates a checkbox labelled with `text`.
##### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example On', true);
local checkbox2 = tab:Create('Checkbox', 'Example Off', true);
checkbox.Changed:Connect(function(status)print('Checkbox set to:',status);end);
checkbox2.Changed:Connect(function(status)print('Checkbox2 set to:',status);end);
```
---
## Methods
### Set
```ts
export function Set(checked: boolean): TextComponent;
```
Sets the Checkbox's Status to `checked`. Fires [`Changed`](#changed) if the state doesn't match the previous one.
#### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example');
checkbox:Set(true);
print(checkbox.Status); --> true
checkbox:Set(false);
print(checkbox.Status); --> false
```
---
### Toggle
```ts
export function Toggle(): TextComponent;
```
Sets the Checkbox's Status to the inverse of `checkbox.Status`. Fires [`Changed`](#changed).
#### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example');
checkbox:Set(true);
print(checkbox.Status); --> true
checkbox:Toggle();
print(checkbox.Status); --> false
```
---
### Get
```ts
export function Get(): boolean;
```
Returns `checkbox.Status`.
#### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example');
checkbox:Set(true);
print(checkbox:Get()); --> true
```
---
### SetText
```ts
export function SetText(text: string): TextComponent;
```
Sets the checkbox's label to `text`.
#### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example');
checkbox:SetText('Another Example');
```
---
## Events
### Changed
```ts
export type Changed = Event<boolean>;
```
Fired on Status Change
##### Example
```lua
local checkbox = tab:Create('Checkbox', 'Example On', true);
checkbox.Changed:Connect(function(status)print('Checkbox set to:',status);end);
checkbox:Set(false); --> 'Checkbox set to: false'
```
---
