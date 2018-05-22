﻿---
Description: 'Specifies the monitor refresh rate.'
ms.assetid: 'deeb780c-2dc2-4a9a-926a-23b9ae3bedd5'
title: 'MF\_TOPOLOGY\_PLAYBACK\_FRAMERATE attribute'
---

# MF\_TOPOLOGY\_PLAYBACK\_FRAMERATE attribute

Specifies the monitor refresh rate.

## Data type

**UINT64**

## Get/set

To get this attribute, call [**MFGetAttributeRatio**](mfgetattributeratio.md).

To set this attribute, call [**MFSetAttributeRatio**](mfsetattributeratio.md).

## Applies to

[**IMFTopology**](imftopology.md)

## Remarks

The topology loader uses this attribute to optimize the pipeline before playback starts. If you set this attribute, also set the [MF\_TOPOLOGY\_STATIC\_PLAYBACK\_OPTIMIZATIONS](mf-topology-static-playback-optimizations.md) attribute to **TRUE**.

The frame rate is expressed as a ratio. The upper 32 bits of the attribute value contain the numerator, and the lower 32 bits contain the denominator.

The GUID constant for this attribute is exported from mfuuid.lib.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows 7 \[desktop apps only\]<br/>                                         |
| Minimum supported server<br/> | Windows Server 2008 R2 \[desktop apps only\]<br/>                            |
| Header<br/>                   | <dl> <dt>Mfidl.h</dt> </dl> |



## See also

<dl> <dt>

[Alphabetical List of Media Foundation Attributes](alphabetical-list-of-media-foundation-attributes.md)
</dt> <dt>

[Topology Attributes](topology-attributes.md)
</dt> <dt>

[Video Quality Management](video-quality-management.md)
</dt> </dl>

 

 



