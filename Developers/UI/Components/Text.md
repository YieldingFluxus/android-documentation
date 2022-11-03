# Text
## Constructor
```ts
export function(text: string): TextComponent;
```
Creates a new Text [Component](/Developers/UI/UI%20Library#components) with the contents of `text`. This supports [Rich Text](https://create.roblox.com/docs/building-and-visuals/ui/rich-text)[\*](#setrichtextenabled) & newlines.
### Example
```lua
local text = tab:Create('Text', '<i>Hello</i> World');
```
---
## Methods
### SetRichTextEnabled
```ts
export function SetRichTextEnabled(state: boolean): TextComponent;
```
Determines whether Rich Text is enabled or not (enabled by default).
> **Why does this exist?**
> Sometimes, Roblox's Rich Text Implementation can be *very* buggy, so it might be easier to disable rich text on some elements.
> Additionally, if you're rendering user input, you may not need rich text & you may want the text to display as-is with no weirdness.
##### Example
```lua
text:SetRichTextEnabled(false); --> Disables Rich Text on the element text
```
---
### UpdateText
```ts
export function UpdateText(text: string): TextComponent;
```
Updates the text of said component to `text`.
##### Example
```lua
text:UpdateText('<i>Goodbye</i> World');
```
