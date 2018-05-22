﻿---
Description: 'Indicates whether a network address conforms to a specified type and format.'
title: 'NCM\_GETADDRESS message'
---

# NCM\_GETADDRESS message

Indicates whether a network address conforms to a specified type and format.


```C++
NCM_GETADDRESS

    wParam = (WPARAM) (PNC_ADDRESS) pv;

    lParam = 0;            

            
```



## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>Must be zero.</dd> <dt>

*pv* \[in, out\]
</dt> <dd>A pointer to an [**NC\_ADDRESS**](nc-address.md) structure to receive network address information in parsed form, if the address format and type in the control specified by *hwnd* are validated. The calling application is responsible for allocating the memory for this structure.</dd> </dl>

## Return value

Returns one of the following values of type **HRESULT**.



| Return code                                                                                                | Description                                                                                          |
|------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------|
| <dl> <dt>**E\_INVALIDARG**</dt> </dl>               | The calling application failed to allocate a [**NC\_ADDRESS**](nc-address.md) structure.<br/> |
| <dl> <dt>**ERROR\_INSUFFICIENT\_BUFFER**</dt> </dl> | The out buffer is too small to hold the parsed network address.<br/>                           |
| <dl> <dt>**ERROR\_INVALID\_PARAMETER**</dt> </dl>   | The network address string is not of any type specified.<br/>                                  |
| <dl> <dt>**ERROR\_SUCCESS**</dt> </dl>              | The operation was successful.<br/>                                                             |
| <dl> <dt>**S\_FALSE**</dt> </dl>                    | There is no address in the network address control to validate.<br/>                           |



 

## Remarks

Use the **NCM\_GETADDRESS** message to validate a network address in a network address control against a preset network address type mask. To instantiate, use the class **msctls\_netaddress** defined in Shellapi.h. Call [**InitNetworkAddressControl**](initnetworkaddresscontrol.md) at run time before sending this message. This initializes the common controls library that contains the network address control.

This message gets the network address string from a network address control, parses the string, and checks whether the string matches a network address type mask. If the string matches the mask, the message returns S\_OK and returns the string in parsed form to the calling application (including the port number, prefix length, and other address information), using the [**NC\_ADDRESS**](nc-address.md) structure pointed to by *pv*. This message returns E\_INVALIDARG if the calling application fails to allocate the structure pointed to by *pv*.

Representations of Internet Protocol (IP) address versions 4 and 6 (v4/v6) for services and networks, as well as named Internet addresses and services using Domain Name System (DNS) format are parsed. If the network address string represents a named host name (DNS) or service, the value returned in the **PrefixLength** member of [**NC\_ADDRESS**](nc-address.md) is zero.

Set the network address type mask using the [**NCM\_SETALLOWTYPE**](ncm-setallowtype.md) message before you send the **NCM\_GETADDRESS** macro.

## Requirements



|                                     |                                                                                       |
|-------------------------------------|---------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                        |
| Minimum supported server<br/> | Windows Server 2008 \[desktop apps only\]<br/>                                  |
| Header<br/>                   | <dl> <dt>Shellapi.h</dt> </dl> |



## See also

<dl> <dt>

[**NCM\_GETALLOWTYPE**](ncm-getallowtype.md)
</dt> <dt>

[**NetAddr\_GetAddress**](netaddr-getaddress.md)
</dt> </dl>

 

 



