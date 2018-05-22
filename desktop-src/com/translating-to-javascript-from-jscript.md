---
title: Translating to JavaScript from JScript
description: Translating to JavaScript from JScript
ms.assetid: '11d31c8c-868d-4220-9298-6d24a209dc47'
---

# Translating to JavaScript from JScript

JScript is largely compatible with JavaScript. However, JScript includes some objects not currently supported by JavaScript, such as ActiveXObject, Enumerator, Error, Global, and VBArray.

JScript version 5.0 supports exception handling through **try**...**catch** statements. JavaScript does not currently provide an error-handing mechanism.

When working with either JScript or JavaScript, there are some subtle differences between the object model implementations supported by various Web browsers. To write script that runs on both Internet Explorer and Netscape Navigator, limit the features used by your scripts to those specified in the World Wide Web Consortium (W3C) [standard for HTML version 3.2](http://go.microsoft.com/fwlink/p/?linkid=103684).

## Related topics

<dl> <dt>

[Translating to JavaScript](translating-to-javascript.md)
</dt> </dl>

 

 



