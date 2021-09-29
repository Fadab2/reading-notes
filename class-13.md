## Local Storage

Local storage allows JavaScript apps data on browers and subfolder in the user's computer.

What we need is a lot of storage space on the client side that is not affected by refreshing the page and not transmitted to a server.
  
### Cookies are include with every http request and:
- Slow down web applications
- Sent over http in clear text
- Limited to 4 Kb

### HTML5 Storage
- Enables web pages to store key/value pairs locally in the client's browser.
- Data exists even when the client exit the browser
- Never transimitted to a server automatically.
- Implemented natively in browsers
- Almost supported by all browsers.
  
Code to check for HTML5 Storage
```
function supports_html5_storage() {
  try {
    return 'localStorage' in window && window['localStorage'] !== null;
  } catch (e) {
    return false;
  }
}
```
If we are storing data other than strings then we need to use functions to parse it.

To set locat storage values
```
var foo = localStorage.getItem("bar");
// ...
localStorage.setItem("bar", foo);
```

To delete storage values:
```
interface Storage {
  deleter void removeItem(in DOMString key);
  void clear();
};
```
### Limmition on browsers
- 5 megabyes of storage space
- QUOTA_EXCEEDED_ERR if max storage exceeded.
- You can't ask for more storage
- 

#### Reference
[THE PAST, PRESENT & FUTURE OF LOCAL STORAGE FOR WEB APPLICATIONS](http://diveinto.html5doctor.com/storage.html)

[go to home](README.md)