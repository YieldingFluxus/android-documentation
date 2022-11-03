A [Button](https://en.wikipedia.org/wiki/Button_(computing)) is the simplest type of input, triggered by a user tapping/clicking the button.
### Active vs Passive Buttons
Activie buttons are meant as a more "primary" type of button, where passive ones are more "secondary".
Below, there's an image comparing the two:
![[ActiveVsPassive.png]]
## Constructor
```ts
export function(state: 'active'|'passive', buttonText: string, sidebarText: string, callback?: ()=>any): ButtonComponent;
export function(state: 'active'|'passive', buttonText: string, callback?: ()=>any): ButtonComponent;
```
Creates a Button & binds `callback` to it's clicks.
If `sidebarText` is specified, the button will be smaller and on the right of the component, next to `sidebarText`.
#### Example
```lua
local button = tab:Create('Button', 'active', 'Hello there! Click/Tap me!', function()
  print('Clicked');
end);
```
---
## Methods
### SetText
```ts
export function SetText(text: string): ButtonComponent;
```
Sets the button's text. Note that this only affects the text on the button, not the sidebarText - the only way to change that is by using [Update()](#update).
#### Example
```lua
local button = tab:Create('Button', 'active', 'Hello there!');
button:SetText('Oh hello there.')
```
---
### Update
```ts
export function Update(...args: ButtonComponentConstructorArgs): ButtonComponent;
```
See [Constructor](#constructor). This effectively replaces a button with one equivalent to if it was created using `...args` as the input.
#### Example
```lua
local button = tab:Create('Button', 'active', 'Some button');
button:Update('passive','Click me','This is now a button with sidebarText')
```
---
### \_SetScaleY
```ts
export function _SetScaleY(scaleY: number): ButtonComponent;
```
Sets the component's Y size to `scaleY` times the original.
> **⚠ THIS IS VERY BROKEN ⚠**
> This is a very unstable method that I will likely never fix. If this causes funky UI behaviour, don't say I didn't warn you.
> **⚠ UNSTABLE NAME ⚠**
> If I ever fix this, the name will change from `_SetScaleY` to `SetScaleY` or `SetYScale`. Your code __will__ break if this ever happens.
#### Example
```lua
local button = tab:Create('Button', 'active', 'Some button');
button:_SetScaleY(5) -- makes the button 5x bigger than default, don't do this plz
```
---
## Events
### Clicked
```ts
export type Changed = Event<null>;
```
Fired when the user clicks the button.
#### Example
```lua
button.Clicked:Connect(function()print('user clicked btn');end);
```