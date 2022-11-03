# Textbox
## Constructor
```ts
export function(): TextboxComponent;
```
Creates a Textbox. Use `'TextBoxMultiLine'` as the component name (identical API) for a multi-line one
#### Example
```lua
local Textbox = tab:Create('Textbox');
```
---
## Methods
### SetPlaceholder
```ts
export function SetPlaceholder(placeholder: string): TextboxComponent;
```
Sets the textfield's placeholder
##### Example
```lua
Textbox:SetPlaceholder('Some Placeholder');
```
---
### GetValue
```ts
export function GetValue(): string;
```
Gets & Returns the currently inputted value of the textbox; `''` if empty
##### Example
```lua
print(Textbox:GetValue());
```
---
### SetValue
```ts
export function SetValue(value: string): TextboxComponent;
```
Sets the value of the textbox, useful for ensuring valid input
##### Example
```lua
Textbox:SetValue('example value');
```
---
## Events
### Changed
```ts
export type Changed = Event<unknown>;
```
Describes when the textbox's content is changed
##### Example
```lua
Textbox.Changed:Connect(function()
  print(Textbox:GetValue());
end);
```
---
## Attributes
None
