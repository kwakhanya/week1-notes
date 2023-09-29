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

