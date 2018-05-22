---
Description: 'Notifies applications of a change in the power status of the computer, such as a switch from battery power to A/C.'
ms.assetid: 'dc56fee3-e0df-4f8e-8a41-92460279280a'
title: 'PBT\_APMPOWERSTATUSCHANGE event'
---

# PBT\_APMPOWERSTATUSCHANGE event

Notifies applications of a change in the power status of the computer, such as a switch from battery power to A/C. The system also broadcasts this event when remaining battery power slips below the threshold specified by the user or if the battery power changes by a specified percentage.

A window receives this event through the [**WM\_POWERBROADCAST**](wm-powerbroadcast.md) message. The *wParam* and *lParam* parameters are set as described following.


```C++
LRESULT 
CALLBACK 
WindowProc( HWND hwnd,      // handle to window
            UINT uMsg,      // WM_POWERBROADCAST
            WPARAM wParam,  // PBT_APMPOWERSTATUSCHANGE
            LPARAM lParam); // zero
```



## Parameters

<dl> <dt>

*hwnd* 
</dt> <dd>

A handle to window.

</dd> <dt>*uMsg* </dt> <dd> 

| Value                                                                                                                                                                                                                                                                   | Meaning                        |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------|
| <span id="WM_POWERBROADCAST"></span><span id="wm_powerbroadcast"></span><dl> <dt>**[**WM\_POWERBROADCAST**](wm-powerbroadcast.md)**</dt> <dt>536 (0x218)</dt> </dl> | Message identifier.<br/> |



�

</dd> <dt>*wParam* </dt> <dd> 

| Value                                                                                                                                                                                                                                                        | Meaning                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| <span id="PBT_APMPOWERSTATUSCHANGE"></span><span id="pbt_apmpowerstatuschange"></span><dl> <dt>**PBT\_APMPOWERSTATUSCHANGE**</dt> <dt>10 (0xA)</dt> </dl> | Event identifier.<br/> |



�

</dd> <dt>

*lParam* 
</dt> <dd>

Reserved; must be zero.

</dd> </dl>

## Return value

No return value.

## Remarks

An application should process this event by calling the [**GetSystemPowerStatus**](getsystempowerstatus.md) function to retrieve the current power status of the computer. In particular, the application should check the **ACLineStatus**, **BatteryFlag**, **BatteryLifeTime**, and **BatteryLifePercent** members of the [**SYSTEM\_POWER\_STATUS**](system-power-status-str.md) structure for any changes. This event can occur when battery life drops to less than 5 minutes, or when the percentage of battery life drops below 10 percent, or if the battery life changes by 3 percent.

## Requirements



|                                     |                                                                                                          |
|-------------------------------------|----------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows�XP \[desktop apps only\]<br/>                                                              |
| Minimum supported server<br/> | Windows Server�2003 \[desktop apps only\]<br/>                                                     |
| Header<br/>                   | <dl> <dt>WinUser.h (include Windows.h)</dt> </dl> |



## See also

<dl> <dt>

[System Power Status](system-power-status.md)
</dt> <dt>

[Power Management Events](power-management-events.md)
</dt> <dt>

[**GetSystemPowerStatus**](getsystempowerstatus.md)
</dt> <dt>

[**SYSTEM\_POWER\_STATUS**](system-power-status-str.md)
</dt> <dt>

[**WM\_POWERBROADCAST**](wm-powerbroadcast.md)
</dt> </dl>

�

�



