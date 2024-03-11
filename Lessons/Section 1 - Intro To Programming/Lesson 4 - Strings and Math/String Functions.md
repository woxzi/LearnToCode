Words, phrases, or sentences often need to be constructed programmatically. To do this, built-in functions are used to manipulate strings in ways that would normally need extensive looping logic. 

### String Interpolation
When inserting a variable in the middle of a string, the string needs to be constructed from parts. To solve this issue, C# includes *Interpolated Strings*. Interpolated strings allow the user to write variables directly into their strings without needing to construct a new string. There are also [special formatting options](https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/tokens/interpolated) that can be used for things like only printing a specific number of digits, or aligning text.

```csharp
// previously, this would need to be used
"beginning of the string " + yourVariable + " end of the string"

// with interpolated strings, this results in the same value
$"beginning of the string {yourVariable} end of the string"
```

### Common String Functions
| Function | Description | Example Usage | Example Result |
| ---- | ---- | ---- | ---- |
| `.ToUpper()` | Converts all alphabetic characters to their uppercase versions | `"pOtAto".ToUpper()` | `POTATO` |
| `.ToLower()` | Converts all alphabetic characters to their lowercase versions | `"pOtAto".ToLower()` | `potato` |
| `.Length` | Returns the length of a string | `"potato".Length` | `6` |
| `.ToCharArray()` | Returns an array containing each character in the string | `"cat".ToCharArray()` | `[ 'c', 'a', 't' ]` |
| `.Substring(start, length)` | Returns the first *n* characters in the string starting from the position specified in `start`, where n is the specified `length`. | `"potato".Substring(2,3)` | `tat` |
| `.Split(string)` | Returns an array of strings, containing each substring split by the provided value | `"potato".Split("t")` | `["po", "a", "o"]` |
| `string.Join(string, string[])` | Returns a string that combines each | `string[] in = { "a", "b", "c" };`<br>`string.Join("+", in)` | `a+b+c` |
