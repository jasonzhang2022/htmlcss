[reference web site](http://excess-xss.com)

#xss
what is xss: cross-site scripting. Web site executes script injected from other web site. How can attacher inject the scripting? Attacher can injects script where user input is used to generate part of web site

##user inputs
* form input
* query parameter in link
* link fragment in url

#three types of xss
* **persistent xss** :Attachers post some content which is saved to database. Victim loads legitimate site containing the contents. Anyone could be victim.
* **Reflected xss**: Victim accesses the site through a URL. Some information(query parameter, fragment, extra path) in the url is treated as input in server and is used to generated part of html. **Only the user who clicks the link **can be victim. Attacher publishes the link somewhere and expects user to click the link.
* **DOM-based xss**:  Javascript at client side use user input to generate part of html page. **The generation is done at client side**.
 
#classic prevention

##encoding
Encoding escapes unsafe character. Encoding depends on context. For example, text content has different set of special characters from that of attribute. double quote is special as attribute value , but is perfect legal as text content. Some DOM method automatically encodes special characters.
> element.textContent="text". Text is encoded properly.
> element.setAttribute("x", v) or element["x"]=v, special character in v is encoded
> element.style.width="5px"
> a.href=url
> window.encodeURLComponent(url) encode query value

#validation/filtering
Some input is perfect valid, and no special character, but it is undesired in some case and could cause potential xss. For example, you may not expect **javascript:** when a url is expected. In this case, you may need to filter the encoded result and only allow those expected pass.

#CSP
Content Security Policy provides an additional layer of defense for when secure input handling fails.