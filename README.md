# Week1-notes
Pop-ups
Popup is more like an alert message, they are used to display a message or a notification to the user.
A popup is a separate window with its own independent JavaScript environment. Popup window is one of the oldest methods to show the additional documents to the user.
Pop-up Blocking
Popup blocking is a feature in web browsers that prevents websites from opening new browser windows or tabs without the user's explicit permission. This feature was introduced to improve user experience and security by preventing annoying and potentially harmful pop-up windows from appearing unexpectedly.
Window.open
window.open() is a JavaScript method that is used to open a new browser window or tab. It is commonly used for various purposes, such as opening a new page, displaying a popup window, or showing a dynamically generated HTML content in a new browser window.
Accessing pop-up
Accessing a popup window from the parent window in JavaScript involves a few steps. You need to open the popup window using window.open() and then interact with it from the parent window.
Accessing a window from a popup typically involves interacting with the parent window or the window that opened the popup. The window.opener property allows you to access the parent window from a popup window. You can use it to manipulate the parent window's DOM or perform actions in the parent window.
To close a window we use win.close().

To check if a window is closed we use win.closed.
Technically, the close() method is available for any window, but window.close() is ignored by most browsers if window is not created with window.open(). So it’ll only work on a popup.
Scrolling and resizing
There are methods to move/resize a window:

win.moveBy(x,y)

Move the window relative to current position x pixels to the right and y pixels down. Negative values are allowed (to move left/up).

win.moveTo(x,y)

Move the window to coordinates (x,y) on the screen.

win.resizeBy(width,height)

Resize the window by given width/height relative to the current size. Negative values are allowed.

win.resizeTo(width,height)

Resize the window to the given size.

There’s also window.onresize event.
Scrolling a window
win.scrollBy(x,y)

Scroll the window x pixels right and y down relative the current scroll. Negative values are allowed.

win.scrollTo(x,y)

Scroll the window to the given coordinates (x,y).

elem.scrollIntoView(top = true)
Focus/Blur a window
In web development, you can use the focus and blur events to control the focus and blur states of a window or element. However, it's important to note that these events are typically associated with HTML elements like input fields, buttons, and links, and not with the entire browser window. You can't directly focus or blur the entire browser window using these events. Instead, you can work with elements within the window.

Focus Event:

The focus event is triggered when an element gains focus, typically through user interaction like clicking or tabbing into the element.
The blur event is triggered when an element loses focus, usually when the user clicks outside the element or tabs away from it.

Day 2
Same Origin
In web development, the concept of the "same origin policy" is crucial for web security, and it defines that two URLs are considered to have the "same origin" if they share the same protocol (e.g., HTTP or HTTPS), domain (e.g., example.com), and port (e.g., :80 for HTTP, :443 for HTTPS).

Here's a breakdown of what each component of the "same origin" means

Protocol: The protocol is the part of the URL that specifies how the browser should communicate with the server. Common protocols include HTTP and HTTPS. URLs with different protocols, such as HTTP and HTTPS, are not considered to have the same origin due to security restrictions.

Domain: The domain is the human-readable name of the web server that hosts the website. For example, in the URL "https://www.example.com/page", "www.example.com" is the domain. URLs with different domains (e.g., example.com and anotherexample.com) are not considered to have the same origin.

Port: The port is a numerical identifier that specifies a specific communication endpoint on the web server. URLs can include a port number to access different services on the same server. If a URL doesn't specify a port, the default port for the protocol is used (e.g., :80 for HTTP, :443 for HTTPS). If the ports are different in two URLs, they are not considered to have the same origin.

The same origin policy is a security measure implemented by web browsers to prevent web pages from making unauthorized requests to a different origin, which could potentially lead to security vulnerabilities like cross-site request forgery (CSRF) and cross-site scripting (XSS) attacks. By enforcing this policy, browsers help protect users' data and ensure that web applications remain secure.

It's worth noting that there are ways to relax the same-origin policy for specific use cases, such as using Cross-Origin Resource Sharing (CORS) headers to enable cross-origin requests when needed while maintaining security control.
In Action Iframe
An <iframe> tag hosts a separate embedded window, with its own separate document and window objects.

We can access them using properties:

iframe.contentWindow to get the window inside the <iframe>.
iframe.contentDocument to get the document inside the <iframe>, iframe.contentWindow.document.

iframe.onload vs iframe.contentWindow.onload

The iframe.onload event (on the <iframe>tag) is essentially the same as iframe.contentWindow.onload (on the embedded window object). It triggers when the embedded window fully loads with all resources.
Window on subdomain
The document.domain property is a JavaScript feature that can be used to relax the same-origin policy for web pages served from subdomains of the same parent domain. It allows web pages served from different subdomains to communicate with each other using JavaScript, which would normally be restricted by the same-origin policy.
Wrong Document pitfall
The "wrong document" pitfall when working with iframes is a common issue that arises when developers try to access or manipulate elements within an iframe without properly considering the same-origin policy and the structure of the document hierarchy. This can lead to JavaScript errors and unexpected behavior.
Window Frame
In JavaScript, the window.frames collection is an array-like object that represents all the <iframe> elements within the current window or frameset. Each <iframe> element is accessible as an item in the window.frames collection.

An alternative way to get a window object for <iframe>– is to get it from the named collectionwindow.frames:

By number: window.frames[0] – the window object for the first frame in the document.
By name: window.frames.iframeName – the window object for the frame withname="iframeName".

Navigation links are:

window.frames – the collection of “children” windows (for nested frames).
window.parent – the reference to the “parent” (outer) window.
window.top – the reference to the topmost parent window.
Sandbox iframe attribute
The sandbox attribute allows for the exclusion of certain actions inside an <iframe> in order to prevent it from executing untrusted code. 
allow-same-origin
By default "sandbox" forces the “different origin” policy for the iframe. In other words, it makes the browser to treat the iframe as coming from another origin, even if its src points to the same site. With all implied restrictions for scripts. This option removes that feature.
Cross-window
Cross-window messaging, also known as cross-document messaging or postMessage API, is a method for securely communicating between different windows or iframes within a web application, even when they have different origins (e.g., different domains, protocols, or ports). This communication allows data to be exchanged and actions to be triggered across documents while maintaining strict security controls.

