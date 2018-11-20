# JavaScript Snippets and notes


## Requests

Requests objects can't be read more than one time, so if you need to read its data and reuse the request you need to clone it:

```js
const handleFetch = (req, res) => {
  const temp_req = req.clone()
  // ... do something
  return res // preserving the request
}
```