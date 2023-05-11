# Execution Sequence
---

![[Pasted image 20230511114629.png]]

## Javascript

> [!note] Global Variable - `req`
> - is assigned either `new XMLHttpRequest()` or `new ActiveXObject()`
> 	- the latter is used to provide support for older browsers *(primarily Internet Explorer)*
> - is used to send the request to the server (servlet?)

> [!note] Global Variable - `isIE`
> - boolean
> - is used to check if browser being used is Internet Explorer

> [!note] Global Variable - `completeField`
> - HTML element
> - represents an inputbox (for text) inside of a form

> [!note] Global Variable - `completeTable`
> - HTML element
> - represents the nested table used for the autocomplete feature
> - will contain all composers that match the input in `completeField`

1. **JavaScript** | `init()`
	- sets `complete-field` (inputbox for text), `complete-table` (nested table), and `auto-row` (table row which contains previously mentioned elements) to javascript variables.
	- function is called when the `body` HTML element has been loaded
2. **Javascript** | `showCompletion()` 
	- initializes block-scoped variable `url`, which is a request containing the `id` to be searched and needed `action` taken by the server (servlet?)
	- the function `initRequest()` is also called in order for the XMLHttpRequest to be sent
3. **Javascript** | `initRequest()`
	- returns an object(???), which is to be assigned to the variable `req` in the `showCompletion()` function.
	- also does checks if the browser being used is Internet Explorer
		- sets the variable `isIE` to true and will return `ActiveXObject` instead of `XMLHttpRequest`
4. **Javascript** | `showCompletion()`
	- calls the function `callback()`
5. **Javascript** | `callback()`
	- calls the function `clearTable()`
6. **Javascript** | `clearTable()`
7. **Javascript** | `callback()`
8. **Javascript** | `parseMessage()`
9. **Javascript** | `appendComposer()`