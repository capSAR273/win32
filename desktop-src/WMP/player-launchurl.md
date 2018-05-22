---
title: Player.launchURL method
description: The launchURL method sends a URL to the user's default browser to be rendered.
ms.assetid: '3e8dfdbb-b5ad-44ea-97a6-e860386b7fb4'
keywords: ["launchURL method Windows Media Player", "launchURL method Windows Media Player , Player class", "Player class Windows Media Player , launchURL method"]
topic_type:
- apiref
api_name:
- Player.launchURL
api_location:
- wmp.dll
api_type:
- COM
---

# Player.launchURL method

The **launchURL** method sends a URL to the user's default browser to be rendered.

## Syntax


```JScript
Player.launchURL(
  URL
)
```



## Parameters

<dl> <dt>

*URL* \[in\]
</dt> <dd>

**String** value representing the URL to launch.

</dd> </dl>

## Return value

This method does not return a value.

## Remarks

This method only opens webpages using the HTTP or HTTPS protocols.

**Windows Media Player 10 Mobile:** This method is not supported.

## Examples

The following example creates an HTML BUTTON element that, when clicked, displays the Microsoft website in a new browser window. The **Player** element was created with ID = "Player".


```JScript
<INPUT  TYPE = "BUTTON"  ID = "GOTOMS"  VALUE = "Microsoft.com"  onClick = "

    /* Open the Microsoft website. */
    Player.launchURL('http://www.microsoft.com');
">

```



## Requirements



|                    |                                                                                    |
|--------------------|------------------------------------------------------------------------------------|
| Version<br/> | Windows Media Player version 7.0 or later.<br/>                              |
| DLL<br/>     | <dl> <dt>Wmp.dll</dt> </dl> |



## See also

<dl> <dt>

[**Player Object**](player-object.md)
</dt> </dl>

�

�




