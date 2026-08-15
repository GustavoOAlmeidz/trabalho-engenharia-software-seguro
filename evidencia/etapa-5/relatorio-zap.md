# ZAP Scanning Report

ZAP by [Checkmarx](https://checkmarx.com/).


## Summary of Alerts

| Risk Level | Number of Alerts |
| --- | --- |
| High | 1 |
| Medium | 4 |
| Low | 7 |
| Informational | 4 |




## Insights

| Level | Reason | Site | Description | Statistic |
| --- | --- | --- | --- | --- |
| Low | Warning |  | ZAP warnings logged - see the zap.log file for details | 25    |
| Info | Informational | http://juice-shop:3000 | Percentage of responses with status code 1xx | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of responses with status code 2xx | 88 % |
| Info | Informational | http://juice-shop:3000 | Percentage of responses with status code 3xx | 8 % |
| Info | Informational | http://juice-shop:3000 | Percentage of responses with status code 4xx | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type application/javascript | 5 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type application/json | 9 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type application/octet-stream | 2 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type font/woff2 | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type image/jpeg | 13 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type image/png | 6 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type image/svg+xml | 24 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type image/x-icon | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type text/css | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type text/html | 32 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type text/markdown | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with content type text/plain | 1 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with method GET | 98 % |
| Info | Informational | http://juice-shop:3000 | Percentage of endpoints with method POST | 1 % |
| Info | Informational | http://juice-shop:3000 | Count of total endpoints | 176    |
| Info | Informational | http://juice-shop:3000 | Percentage of slow responses | 24 % |
| Info | Informational | https://api.github.com | Percentage of endpoints with content type text/plain | 100 % |
| Info | Informational | https://api.github.com | Percentage of endpoints with method POST | 100 % |
| Info | Informational | https://api.github.com | Count of total endpoints | 1    |
| Info | Informational | https://avatars.githubusercontent.com | Percentage of endpoints with content type image/png | 100 % |
| Info | Informational | https://avatars.githubusercontent.com | Percentage of endpoints with method GET | 100 % |
| Info | Informational | https://avatars.githubusercontent.com | Count of total endpoints | 1    |
| Info | Informational | https://camo.githubusercontent.com | Percentage of endpoints with content type image/svg+xml | 93 % |
| Info | Informational | https://camo.githubusercontent.com | Percentage of endpoints with content type text/plain | 6 % |
| Info | Informational | https://camo.githubusercontent.com | Percentage of endpoints with method GET | 100 % |
| Info | Informational | https://camo.githubusercontent.com | Count of total endpoints | 29    |
| Info | Informational | https://collector.github.com | Percentage of endpoints with method POST | 100 % |
| Info | Informational | https://collector.github.com | Count of total endpoints | 2    |
| Info | Informational | https://github.com | Percentage of endpoints with content type application/json | 50 % |
| Info | Informational | https://github.com | Percentage of endpoints with content type image/png | 7 % |
| Info | Informational | https://github.com | Percentage of endpoints with content type image/svg+xml | 14 % |
| Info | Informational | https://github.com | Percentage of endpoints with content type text/html | 28 % |
| Info | Informational | https://github.com | Percentage of endpoints with method GET | 100 % |
| Info | Informational | https://github.com | Count of total endpoints | 14    |
| Info | Informational | https://github.githubassets.com | Percentage of endpoints with content type application/javascript | 82 % |
| Info | Informational | https://github.githubassets.com | Percentage of endpoints with content type text/css | 16 % |
| Info | Informational | https://github.githubassets.com | Percentage of endpoints with method GET | 100 % |
| Info | Informational | https://github.githubassets.com | Count of total endpoints | 130    |
| Info | Informational | https://raw.githubusercontent.com | Percentage of endpoints with content type image/gif | 20 % |
| Info | Informational | https://raw.githubusercontent.com | Percentage of endpoints with content type image/jpeg | 40 % |
| Info | Informational | https://raw.githubusercontent.com | Percentage of endpoints with content type image/png | 40 % |
| Info | Informational | https://raw.githubusercontent.com | Percentage of endpoints with method GET | 100 % |
| Info | Informational | https://raw.githubusercontent.com | Count of total endpoints | 5    |







## Alerts

| Name | Risk Level | Number of Instances |
| --- | --- | --- |
| Off-site Redirect | High | 1 |
| Content Security Policy (CSP) Header Not Set | Medium | Systemic |
| Cross-Domain Misconfiguration | Medium | Systemic |
| Missing Anti-clickjacking Header | Medium | 1 |
| Session ID in URL Rewrite | Medium | Systemic |
| Cross-Origin-Embedder-Policy Header Missing or Invalid | Low | 5 |
| Cross-Origin-Opener-Policy Header Missing or Invalid | Low | 5 |
| Dangerous JS Functions | Low | 3 |
| Deprecated Feature Policy Header Set | Low | Systemic |
| Private IP Disclosure | Low | 1 |
| Timestamp Disclosure - Unix | Low | Systemic |
| X-Content-Type-Options Header Missing | Low | 3 |
| Modern Web Application | Informational | Systemic |
| Non-Storable Content | Informational | 4 |
| Storable and Cacheable Content | Informational | 1 |
| Storable but Non-Cacheable Content | Informational | Systemic |




## Alert Detail



### [ Off-site Redirect ](https://www.zaproxy.org/docs/alerts/10028/)



##### High (Medium)

### Description

Open redirects are one of the OWASP 2010 Top Ten vulnerabilities. This check looks at user-supplied input in query string parameters and POST data to identify where open redirects might be possible. Open redirects occur when an application allows user-supplied input (e.g. https://nottrusted.com) to control an off-site destination. This is generally a pretty accurate way to find where 301 or 302 redirects could be exploited by spammers or phishing attacks.

For example an attacker could supply a user with the following link: https://example.com/example.php?url=https://malicious.example.com.

NOTE: For the purposes of the passive check the authority portion of the origin and destination were compared. Manual testing may be required to validate the impact of this finding.

* URL: http://juice-shop:3000/redirect%3Fto=https://github.com/juice-shop/juice-shop
  * Node Name: `http://juice-shop:3000/redirect (to)`
  * Method: `GET`
  * Parameter: `to`
  * Attack: ``
  * Evidence: ``
  * Other Info: `The 301 or 302 response to a request for the following URL appeared to contain user input in the location header:

http://juice-shop:3000/redirect?to=https://github.com/juice-shop/juice-shop

The user input found was:

to=https://github.com/juice-shop/juice-shop

The context was:

https://github.com/juice-shop/juice-shop`


Instances: 1

### Solution

To avoid the open redirect vulnerability, parameters of the application script/program must be validated before sending 302 HTTP code (redirect) to the client browser. Implement safe redirect functionality that only redirects to relative URI's, or a list of trusted domains.

### Reference


* [ https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Unvalidated_Redirects_and_Forwards_Cheat_Sheet.html)
* [ https://cwe.mitre.org/data/definitions/601.html ](https://cwe.mitre.org/data/definitions/601.html)


#### CWE Id: [ 601 ](https://cwe.mitre.org/data/definitions/601.html)


#### WASC Id: 38

#### Source ID: 3

### [ Content Security Policy (CSP) Header Not Set ](https://www.zaproxy.org/docs/alerts/10038/)



##### Medium (High)

### Description

Content Security Policy (CSP) is an added layer of security that helps to detect and mitigate certain types of attacks, including Cross Site Scripting (XSS) and data injection attacks. These attacks are used for everything from data theft to site defacement or distribution of malware. CSP provides a set of standard HTTP headers that allow website owners to declare approved sources of content that browsers should be allowed to load on that page — covered types are JavaScript, CSS, HTML frames, fonts, images and embeddable objects such as Java applets, ActiveX, audio and video files.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/coupons_2013.md.bak
  * Node Name: `http://juice-shop:3000/ftp/coupons_2013.md.bak`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/eastere.gg
  * Node Name: `http://juice-shop:3000/ftp/eastere.gg`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/package-lock.json.bak
  * Node Name: `http://juice-shop:3000/ftp/package-lock.json.bak`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: ``

Instances: Systemic


### Solution

Ensure that your web server, application server, load balancer, etc. is configured to set the Content-Security-Policy header.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CSP)
* [ https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html ](https://cheatsheetseries.owasp.org/cheatsheets/Content_Security_Policy_Cheat_Sheet.html)
* [ https://www.w3.org/TR/CSP/ ](https://www.w3.org/TR/CSP/)
* [ https://w3c.github.io/webappsec-csp/ ](https://w3c.github.io/webappsec-csp/)
* [ https://web.dev/articles/csp ](https://web.dev/articles/csp)
* [ https://caniuse.com/#feat=contentsecuritypolicy ](https://caniuse.com/#feat=contentsecuritypolicy)
* [ https://content-security-policy.com/ ](https://content-security-policy.com/)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Cross-Domain Misconfiguration ](https://www.zaproxy.org/docs/alerts/10098/)



##### Medium (Medium)

### Description

Web browser data loading may be possible, due to a Cross Origin Resource Sharing (CORS) misconfiguration on the web server.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Access-Control-Allow-Origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: http://juice-shop:3000/assets/public/favicon_js.ico
  * Node Name: `http://juice-shop:3000/assets/public/favicon_js.ico`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Access-Control-Allow-Origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: http://juice-shop:3000/robots.txt
  * Node Name: `http://juice-shop:3000/robots.txt`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Access-Control-Allow-Origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: http://juice-shop:3000/scripts.js
  * Node Name: `http://juice-shop:3000/scripts.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Access-Control-Allow-Origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`
* URL: http://juice-shop:3000/styles.css
  * Node Name: `http://juice-shop:3000/styles.css`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Access-Control-Allow-Origin: *`
  * Other Info: `The CORS misconfiguration on the web server permits cross-domain read requests from arbitrary third party domains, using unauthenticated APIs on this domain. Web browser implementations do not permit arbitrary third parties to read the response from authenticated APIs, however. This reduces the risk somewhat. This misconfiguration could be used by an attacker to access data that is available in an unauthenticated manner, but which uses some other form of security, such as IP address white-listing.`

Instances: Systemic


### Solution

Ensure that sensitive data is not available in an unauthenticated manner (using IP address white-listing, for instance).
Configure the "Access-Control-Allow-Origin" HTTP header to a more restrictive set of domains, or remove all CORS headers entirely, to allow the web browser to enforce the Same Origin Policy (SOP) in a more restrictive manner.

### Reference


* [ https://vulncat.fortify.com/en/detail?category=HTML5&subcategory=Overly%20Permissive%20CORS%20Policy ](https://vulncat.fortify.com/en/detail?category=HTML5&subcategory=Overly%20Permissive%20CORS%20Policy)


#### CWE Id: [ 264 ](https://cwe.mitre.org/data/definitions/264.html)


#### WASC Id: 14

#### Source ID: 3

### [ Missing Anti-clickjacking Header ](https://www.zaproxy.org/docs/alerts/10020/)



##### Medium (Medium)

### Description

The response does not protect against 'ClickJacking' attacks. It should include either Content-Security-Policy with 'frame-ancestors' directive or X-Frame-Options.

* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Boa&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)(40)`
  * Method: `POST`
  * Parameter: `x-frame-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 1

### Solution

Modern Web browsers support the Content-Security-Policy and X-Frame-Options HTTP headers. Ensure one of them is set on all web pages returned by your site/app.
If you expect the page to be framed only by pages on your server (e.g. it's part of a FRAMESET) then you'll want to use SAMEORIGIN, otherwise if you never expect the page to be framed, you should use DENY. Alternatively consider implementing Content Security Policy's "frame-ancestors" directive.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/X-Frame-Options)


#### CWE Id: [ 1021 ](https://cwe.mitre.org/data/definitions/1021.html)


#### WASC Id: 15

#### Source ID: 3

### [ Session ID in URL Rewrite ](https://www.zaproxy.org/docs/alerts/3/)



##### Medium (High)

### Description

URL rewrite is used to track user session ID. The session ID may be disclosed via cross-site referer header. In addition, the session ID might be stored in browser history or server logs.

* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Boc&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)`
  * Method: `GET`
  * Parameter: `sid`
  * Attack: ``
  * Evidence: `BvmDb6OPbNSEALlIAAAC`
  * Other Info: ``
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=websocket&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,transport)`
  * Method: `GET`
  * Parameter: `sid`
  * Attack: ``
  * Evidence: `BvmDb6OPbNSEALlIAAAC`
  * Other Info: ``
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=websocket&sid=phO3b_1IoidkFJfcAAAE
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,transport)`
  * Method: `GET`
  * Parameter: `sid`
  * Attack: ``
  * Evidence: `phO3b_1IoidkFJfcAAAE`
  * Other Info: ``
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Boa&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)(40)`
  * Method: `POST`
  * Parameter: `sid`
  * Attack: ``
  * Evidence: `BvmDb6OPbNSEALlIAAAC`
  * Other Info: ``
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Fhw&sid=phO3b_1IoidkFJfcAAAE
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)(40)`
  * Method: `POST`
  * Parameter: `sid`
  * Attack: ``
  * Evidence: `phO3b_1IoidkFJfcAAAE`
  * Other Info: ``

Instances: Systemic


### Solution

For secure content, put session ID in a cookie. To be even more secure consider using a combination of cookie and URL rewrite.

### Reference


* [ https://seclists.org/webappsec/2002/q4/111 ](https://seclists.org/webappsec/2002/q4/111)


#### CWE Id: [ 598 ](https://cwe.mitre.org/data/definitions/598.html)


#### WASC Id: 13

#### Source ID: 3

### [ Cross-Origin-Embedder-Policy Header Missing or Invalid ](https://www.zaproxy.org/docs/alerts/90004/)



##### Low (Medium)

### Description

Cross-Origin-Embedder-Policy header is a response header that prevents a document from loading any cross-origin resources that don't explicitly grant the document permission (using CORP or CORS).

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: `Cross-Origin-Embedder-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/
  * Node Name: `http://juice-shop:3000/`
  * Method: `GET`
  * Parameter: `Cross-Origin-Embedder-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/ftp
  * Node Name: `http://juice-shop:3000/ftp`
  * Method: `GET`
  * Parameter: `Cross-Origin-Embedder-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18
  * Node Name: `http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18`
  * Method: `GET`
  * Parameter: `Cross-Origin-Embedder-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: `Cross-Origin-Embedder-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 5

### Solution

Ensure that the application/web server sets the Cross-Origin-Embedder-Policy header appropriately, and that it sets the Cross-Origin-Embedder-Policy header to 'require-corp' for documents.
If possible, ensure that the end user uses a standards-compliant and modern web browser that supports the Cross-Origin-Embedder-Policy header (https://caniuse.com/mdn-http_headers_cross-origin-embedder-policy).

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Embedder-Policy ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Embedder-Policy)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 14

#### Source ID: 3

### [ Cross-Origin-Opener-Policy Header Missing or Invalid ](https://www.zaproxy.org/docs/alerts/90004/)



##### Low (Medium)

### Description

Cross-Origin-Opener-Policy header is a response header that allows a site to control if others included documents share the same browsing context. Sharing the same browsing context with untrusted documents might lead to data leak.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: `Cross-Origin-Opener-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/
  * Node Name: `http://juice-shop:3000/`
  * Method: `GET`
  * Parameter: `Cross-Origin-Opener-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/ftp
  * Node Name: `http://juice-shop:3000/ftp`
  * Method: `GET`
  * Parameter: `Cross-Origin-Opener-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18
  * Node Name: `http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18`
  * Method: `GET`
  * Parameter: `Cross-Origin-Opener-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: `Cross-Origin-Opener-Policy`
  * Attack: ``
  * Evidence: ``
  * Other Info: ``


Instances: 5

### Solution

Ensure that the application/web server sets the Cross-Origin-Opener-Policy header appropriately, and that it sets the Cross-Origin-Opener-Policy header to 'same-origin' for documents.
'same-origin-allow-popups' is considered as less secured and should be avoided.
If possible, ensure that the end user uses a standards-compliant and modern web browser that supports the Cross-Origin-Opener-Policy header (https://caniuse.com/mdn-http_headers_cross-origin-opener-policy).

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Opener-Policy ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Cross-Origin-Opener-Policy)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 14

#### Source ID: 3

### [ Dangerous JS Functions ](https://www.zaproxy.org/docs/alerts/10110/)



##### Low (Low)

### Description

A dangerous JS function seems to be in use that would leave the site vulnerable.

* URL: http://juice-shop:3000/about.component-CZcG2819.js
  * Node Name: `http://juice-shop:3000/about.component-CZcG2819.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `bypassSecurityTrustHtml(`
  * Other Info: ``
* URL: http://juice-shop:3000/chunk-eYAgyLdn.js
  * Node Name: `http://juice-shop:3000/chunk-eYAgyLdn.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `bypassSecurityTrustHtml(`
  * Other Info: ``
* URL: http://juice-shop:3000/main.js
  * Node Name: `http://juice-shop:3000/main.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `bypassSecurityTrustHtml(`
  * Other Info: ``


Instances: 3

### Solution

See the references for security advice on the use of these functions.

### Reference


* [ https://v17.angular.io/guide/security ](https://v17.angular.io/guide/security)


#### CWE Id: [ 749 ](https://cwe.mitre.org/data/definitions/749.html)


#### Source ID: 3

### [ Deprecated Feature Policy Header Set ](https://www.zaproxy.org/docs/alerts/10063/)



##### Low (Medium)

### Description

The header has now been renamed to Permissions-Policy.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Feature-Policy`
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/package-lock.json.bak
  * Node Name: `http://juice-shop:3000/ftp/package-lock.json.bak`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Feature-Policy`
  * Other Info: ``
* URL: http://juice-shop:3000/polyfills.js
  * Node Name: `http://juice-shop:3000/polyfills.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Feature-Policy`
  * Other Info: ``
* URL: http://juice-shop:3000/scripts.js
  * Node Name: `http://juice-shop:3000/scripts.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Feature-Policy`
  * Other Info: ``
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `Feature-Policy`
  * Other Info: ``

Instances: Systemic


### Solution

Ensure that your web server, application server, load balancer, etc. is configured to set the Permissions-Policy header instead of the Feature-Policy header.

### Reference


* [ https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Permissions-Policy ](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Headers/Permissions-Policy)
* [ https://scotthelme.co.uk/goodbye-feature-policy-and-hello-permissions-policy/ ](https://scotthelme.co.uk/goodbye-feature-policy-and-hello-permissions-policy/)


#### CWE Id: [ 16 ](https://cwe.mitre.org/data/definitions/16.html)


#### WASC Id: 15

#### Source ID: 3

### [ Private IP Disclosure ](https://www.zaproxy.org/docs/alerts/2/)



##### Low (Medium)

### Description

A private IP (such as 10.x.x.x, 172.x.x.x, 192.168.x.x) or an Amazon EC2 private hostname (for example, ip-10-0-56-78) has been found in the HTTP response body. This information might be helpful for further attacks targeting internal systems.

* URL: http://juice-shop:3000/rest/admin/application-configuration
  * Node Name: `http://juice-shop:3000/rest/admin/application-configuration`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `192.168.99.100:3000`
  * Other Info: `192.168.99.100:3000
192.168.99.100:4200
`


Instances: 1

### Solution

Remove the private IP address from the HTTP response body. For comments, use JSP/ASP/PHP comment instead of HTML/JavaScript comment which can be seen by client browsers.

### Reference


* [ https://datatracker.ietf.org/doc/html/rfc1918 ](https://datatracker.ietf.org/doc/html/rfc1918)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ Timestamp Disclosure - Unix ](https://www.zaproxy.org/docs/alerts/10096/)



##### Low (Low)

### Description

A timestamp was disclosed by the application/web server. - Unix

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1666666667`
  * Other Info: `1666666667, which evaluates to: 2022-10-25 02:57:47.`
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1666666667`
  * Other Info: `1666666667, which evaluates to: 2022-10-25 02:57:47.`
* URL: http://juice-shop:3000/styles.css
  * Node Name: `http://juice-shop:3000/styles.css`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1528301887`
  * Other Info: `1528301887, which evaluates to: 2018-06-06 16:18:07.`
* URL: http://juice-shop:3000/styles.css
  * Node Name: `http://juice-shop:3000/styles.css`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1578947368`
  * Other Info: `1578947368, which evaluates to: 2020-01-13 20:29:28.`
* URL: http://juice-shop:3000/styles.css
  * Node Name: `http://juice-shop:3000/styles.css`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `1602209945`
  * Other Info: `1602209945, which evaluates to: 2020-10-09 02:19:05.`

Instances: Systemic


### Solution

Manually confirm that the timestamp data is not sensitive, and that the data cannot be aggregated to disclose exploitable patterns.

### Reference


* [ https://cwe.mitre.org/data/definitions/200.html ](https://cwe.mitre.org/data/definitions/200.html)


#### CWE Id: [ 497 ](https://cwe.mitre.org/data/definitions/497.html)


#### WASC Id: 13

#### Source ID: 3

### [ X-Content-Type-Options Header Missing ](https://www.zaproxy.org/docs/alerts/10021/)



##### Low (Medium)

### Description

The Anti-MIME-Sniffing header X-Content-Type-Options was not set to 'nosniff'. This allows older versions of Internet Explorer and Chrome to perform MIME-sniffing on the response body, potentially causing the response body to be interpreted and displayed as a content type other than the declared content type. Current (early 2014) and legacy versions of Firefox will use the declared content type (if one is set), rather than performing MIME-sniffing.

* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Boc&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)`
  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039BhB
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,t,transport)`
  * Method: `GET`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`
* URL: http://juice-shop:3000/socket.io/%3FEIO=4&transport=polling&t=Q039Boa&sid=BvmDb6OPbNSEALlIAAAC
  * Node Name: `http://juice-shop:3000/socket.io/ (EIO,sid,t,transport)(40)`
  * Method: `POST`
  * Parameter: `x-content-type-options`
  * Attack: ``
  * Evidence: ``
  * Other Info: `This issue still applies to error type pages (401, 403, 500, etc.) as those pages are often still affected by injection issues, in which case there is still concern for browsers sniffing pages away from their actual content type.
At "High" threshold this scan rule will not alert on client or server error responses.`


Instances: 3

### Solution

Ensure that the application/web server sets the Content-Type header appropriately, and that it sets the X-Content-Type-Options header to 'nosniff' for all web pages.
If possible, ensure that the end user uses a standards-compliant and modern web browser that does not perform MIME-sniffing at all, or that can be directed by the web application/web server to not perform MIME-sniffing.

### Reference


* [ https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85) ](https://learn.microsoft.com/en-us/previous-versions/windows/internet-explorer/ie-developer/compatibility/gg622941(v=vs.85))
* [ https://owasp.org/www-community/Security_Headers ](https://owasp.org/www-community/Security_Headers)


#### CWE Id: [ 693 ](https://cwe.mitre.org/data/definitions/693.html)


#### WASC Id: 15

#### Source ID: 3

### [ Modern Web Application ](https://www.zaproxy.org/docs/alerts/10109/)



##### Informational (Medium)

### Description

The application appears to be a modern web application. If you need to explore it automatically then the Client Spider may well be more effective than the standard one.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<script>
    window.addEventListener("load", function(){
      window.cookieconsent.initialise({
        "palette": {
          "popup": { "background": "var(--theme-primary)", "text": "var(--theme-text)" },
          "button": { "background": "var(--theme-accent)", "text": "var(--theme-text)" }
        },
        "theme": "classic",
        "position": "bottom-right",
        "content": { "message": "This website uses fruit cookies to ensure you get the juiciest tracking experience.", "dismiss": "Me want it!", "link": "But me wait!", "href": "https://www.youtube.com/watch?v=9PnbKL3wuH4" }
      })});
  </script>`
  * Other Info: `No links have been found while there are scripts, which is an indication that this is a modern web application.`
* URL: http://juice-shop:3000/
  * Node Name: `http://juice-shop:3000/`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<script>
    window.addEventListener("load", function(){
      window.cookieconsent.initialise({
        "palette": {
          "popup": { "background": "var(--theme-primary)", "text": "var(--theme-text)" },
          "button": { "background": "var(--theme-accent)", "text": "var(--theme-text)" }
        },
        "theme": "classic",
        "position": "bottom-right",
        "content": { "message": "This website uses fruit cookies to ensure you get the juiciest tracking experience.", "dismiss": "Me want it!", "link": "But me wait!", "href": "https://www.youtube.com/watch?v=9PnbKL3wuH4" }
      })});
  </script>`
  * Other Info: `No links have been found while there are scripts, which is an indication that this is a modern web application.`
* URL: http://juice-shop:3000/juice-shop/build/routes/fileServer.js:52:13
  * Node Name: `http://juice-shop:3000/juice-shop/build/routes/fileServer.js:52:13`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<script>
    window.addEventListener("load", function(){
      window.cookieconsent.initialise({
        "palette": {
          "popup": { "background": "var(--theme-primary)", "text": "var(--theme-text)" },
          "button": { "background": "var(--theme-accent)", "text": "var(--theme-text)" }
        },
        "theme": "classic",
        "position": "bottom-right",
        "content": { "message": "This website uses fruit cookies to ensure you get the juiciest tracking experience.", "dismiss": "Me want it!", "link": "But me wait!", "href": "https://www.youtube.com/watch?v=9PnbKL3wuH4" }
      })});
  </script>`
  * Other Info: `No links have been found while there are scripts, which is an indication that this is a modern web application.`
* URL: http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18
  * Node Name: `http://juice-shop:3000/juice-shop/build/routes/fileServer.js:68:18`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<script>
    window.addEventListener("load", function(){
      window.cookieconsent.initialise({
        "palette": {
          "popup": { "background": "var(--theme-primary)", "text": "var(--theme-text)" },
          "button": { "background": "var(--theme-accent)", "text": "var(--theme-text)" }
        },
        "theme": "classic",
        "position": "bottom-right",
        "content": { "message": "This website uses fruit cookies to ensure you get the juiciest tracking experience.", "dismiss": "Me want it!", "link": "But me wait!", "href": "https://www.youtube.com/watch?v=9PnbKL3wuH4" }
      })});
  </script>`
  * Other Info: `No links have been found while there are scripts, which is an indication that this is a modern web application.`
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `<script>
    window.addEventListener("load", function(){
      window.cookieconsent.initialise({
        "palette": {
          "popup": { "background": "var(--theme-primary)", "text": "var(--theme-text)" },
          "button": { "background": "var(--theme-accent)", "text": "var(--theme-text)" }
        },
        "theme": "classic",
        "position": "bottom-right",
        "content": { "message": "This website uses fruit cookies to ensure you get the juiciest tracking experience.", "dismiss": "Me want it!", "link": "But me wait!", "href": "https://www.youtube.com/watch?v=9PnbKL3wuH4" }
      })});
  </script>`
  * Other Info: `No links have been found while there are scripts, which is an indication that this is a modern web application.`

Instances: Systemic


### Solution

This is an informational alert and so no changes are required.

### Reference




#### Source ID: 3

### [ Non-Storable Content ](https://www.zaproxy.org/docs/alerts/10049/)



##### Informational (Medium)

### Description

The response contents are not storable by caching components such as proxy servers. If the response does not contain sensitive, personal or user-specific information, it may benefit from being stored and cached, to improve performance.

* URL: http://juice-shop:3000/ftp/coupons_2013.md.bak
  * Node Name: `http://juice-shop:3000/ftp/coupons_2013.md.bak`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/eastere.gg
  * Node Name: `http://juice-shop:3000/ftp/eastere.gg`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/encrypt.pyc
  * Node Name: `http://juice-shop:3000/ftp/encrypt.pyc`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``
* URL: http://juice-shop:3000/ftp/package-lock.json.bak
  * Node Name: `http://juice-shop:3000/ftp/package-lock.json.bak`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `403`
  * Other Info: ``


Instances: 4

### Solution

The content may be marked as storable by ensuring that the following conditions are satisfied:
The request method must be understood by the cache and defined as being cacheable ("GET", "HEAD", and "POST" are currently defined as cacheable)
The response status code must be understood by the cache (one of the 1XX, 2XX, 3XX, 4XX, or 5XX response classes are generally understood)
The "no-store" cache directive must not appear in the request or response header fields
For caching by "shared" caches such as "proxy" caches, the "private" response directive must not appear in the response
For caching by "shared" caches such as "proxy" caches, the "Authorization" header field must not appear in the request, unless the response explicitly allows it (using one of the "must-revalidate", "public", or "s-maxage" Cache-Control response directives)
In addition to the conditions above, at least one of the following conditions must also be satisfied by the response:
It must contain an "Expires" header field
It must contain a "max-age" response directive
For "shared" caches such as "proxy" caches, it must contain a "s-maxage" response directive
It must contain a "Cache Control Extension" that allows it to be cached
It must have a status code that is defined as cacheable by default (200, 203, 204, 206, 300, 301, 404, 405, 410, 414, 501).

### Reference


* [ https://datatracker.ietf.org/doc/html/rfc7234 ](https://datatracker.ietf.org/doc/html/rfc7234)
* [ https://datatracker.ietf.org/doc/html/rfc7231 ](https://datatracker.ietf.org/doc/html/rfc7231)
* [ https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html)


#### CWE Id: [ 524 ](https://cwe.mitre.org/data/definitions/524.html)


#### WASC Id: 13

#### Source ID: 3

### [ Storable and Cacheable Content ](https://www.zaproxy.org/docs/alerts/10049/)



##### Informational (Medium)

### Description

The response contents are storable by caching components such as proxy servers, and may be retrieved directly from the cache, rather than from the origin server by the caching servers, in response to similar requests from other users. If the response data is sensitive, personal or user-specific, this may result in sensitive information being leaked. In some cases, this may even result in a user gaining complete control of the session of another user, depending on the configuration of the caching components in use in their environment. This is primarily an issue where "shared" caching servers such as "proxy" caches are configured on the local network. This configuration is typically found in corporate or educational environments, for instance.

* URL: http://juice-shop:3000/robots.txt
  * Node Name: `http://juice-shop:3000/robots.txt`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: ``
  * Other Info: `In the absence of an explicitly specified caching lifetime directive in the response, a liberal lifetime heuristic of 1 year was assumed. This is permitted by rfc7234.`


Instances: 1

### Solution

Validate that the response does not contain sensitive, personal or user-specific information. If it does, consider the use of the following HTTP response headers, to limit, or prevent the content being stored and retrieved from the cache by another user:
Cache-Control: no-cache, no-store, must-revalidate, private
Pragma: no-cache
Expires: 0
This configuration directs both HTTP 1.0 and HTTP 1.1 compliant caching servers to not store the response, and to not retrieve the response (without validation) from the cache, in response to a similar request.

### Reference


* [ https://datatracker.ietf.org/doc/html/rfc7234 ](https://datatracker.ietf.org/doc/html/rfc7234)
* [ https://datatracker.ietf.org/doc/html/rfc7231 ](https://datatracker.ietf.org/doc/html/rfc7231)
* [ https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html)


#### CWE Id: [ 524 ](https://cwe.mitre.org/data/definitions/524.html)


#### WASC Id: 13

#### Source ID: 3

### [ Storable but Non-Cacheable Content ](https://www.zaproxy.org/docs/alerts/10049/)



##### Informational (Medium)

### Description

The response contents are storable by caching components such as proxy servers, but will not be retrieved directly from the cache, without validating the request upstream, in response to similar requests from other users.

* URL: http://juice-shop:3000
  * Node Name: `http://juice-shop:3000`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `max-age=0`
  * Other Info: ``
* URL: http://juice-shop:3000/assets/public/favicon_js.ico
  * Node Name: `http://juice-shop:3000/assets/public/favicon_js.ico`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `max-age=0`
  * Other Info: ``
* URL: http://juice-shop:3000/polyfills.js
  * Node Name: `http://juice-shop:3000/polyfills.js`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `max-age=0`
  * Other Info: ``
* URL: http://juice-shop:3000/sitemap.xml
  * Node Name: `http://juice-shop:3000/sitemap.xml`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `max-age=0`
  * Other Info: ``
* URL: http://juice-shop:3000/styles.css
  * Node Name: `http://juice-shop:3000/styles.css`
  * Method: `GET`
  * Parameter: ``
  * Attack: ``
  * Evidence: `max-age=0`
  * Other Info: ``

Instances: Systemic


### Solution



### Reference


* [ https://datatracker.ietf.org/doc/html/rfc7234 ](https://datatracker.ietf.org/doc/html/rfc7234)
* [ https://datatracker.ietf.org/doc/html/rfc7231 ](https://datatracker.ietf.org/doc/html/rfc7231)
* [ https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html ](https://www.w3.org/Protocols/rfc2616/rfc2616-sec13.html)


#### CWE Id: [ 524 ](https://cwe.mitre.org/data/definitions/524.html)


#### WASC Id: 13

#### Source ID: 3


