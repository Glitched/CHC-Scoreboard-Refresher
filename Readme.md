# Scoreboard Refresher

This page refreshes itself at a hardcoded interval. It loads a page in an iframe and scrolls down by a set amount. It is designed to be run on a Raspberry Pi that is configured to automatically load the page fullscreen on boot without any human interaction. The URL of the page and offset will be changed as CHC participates in different CTF's.

## Making it work

The page has three values to be customized:

1. The frame source

2. The refresh delay

3. The scroll offset

Change them according to the needs of a particular CTF

### Setup

Some pages disallow embedding them in iframes, such as the one currently embedded in the page.

```
ERROR: Refused to display 'example.com/scoreboard' in a frame because it set 'X-Frame-Options' to 'DENY'.
```

Some browsers have add-ons that disable this functionality, like [Firefox](https://addons.mozilla.org/en-us/firefox/addon/ignore-x-frame-options/) or [Chrome](https://chrome.google.com/webstore/detail/ignore-x-frame-headers/gleekbfjekiniecknbkamfmkohkpodhe). Using these add-ons on a machine you use for general web browsing is a very bad idea. Do not do it.

-------------------------------------------------

Also, scrolling in an iframe is also disabled as a security feature. 

```
ERROR: Blocked a frame with origin "null" from accessing a cross-origin frame.
```

You can disable this security feature by launching Chrome with the flag `--disable-web-security`. Again, this is a very bad idea if you use this browser for anything other than this. Do not do it. [This Firefox add-on](https://addons.mozilla.org/en-Us/firefox/addon/cors-everywhere/) should accomplish the same task.

### Firefox users:

This uses Javascript that has not been implemented until Firefox 52 beta, but in my testing it has been having trouble with iframes, so use at your own peril.