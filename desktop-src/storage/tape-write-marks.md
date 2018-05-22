---
title: TAPE\_WRITE\_MARKS structure
description: The TAPE\_WRITE\_MARKS structure is used in conjunction with an IOCTL\_TAPE\_WRITE\_MARKS request to write a setmark, a filemark, a short filemark, or a long filemark to tape.
ms.assetid: 'cc4dabe3-4e14-4495-89b4-37f1a31ea62d'
keywords: ["TAPE_WRITE_MARKS structure Storage Devices", "PTAPE_WRITE_MARKS structure pointer Storage Devices"]
topic_type:
- apiref
api_name:
- TAPE_WRITE_MARKS
api_location:
- ntddtape.h
api_type:
- HeaderDef
---

# TAPE\_WRITE\_MARKS structure

The TAPE\_WRITE\_MARKS structure is used in conjunction with an [**IOCTL\_TAPE\_WRITE\_MARKS**](ioctl-tape-write-marks.md) request to write a setmark, a filemark, a short filemark, or a long filemark to tape.

## Syntax


```C++
typedef struct _TAPE_WRITE_MARKS {
  ULONG ��Type;
  ULONG ��Count;
  BOOLEAN Immediate;
} TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS;
```



## Members

<dl> <dt>

**Type**
</dt> <dd>

Indicates the type of mark to write. This member can have one of the following values:



| Type                              | Meaning                                                                         |
|-----------------------------------|---------------------------------------------------------------------------------|
| TAPE\_SETMARKS<br/>         | Writes the number of setmarks specified by **Count**.<br/>                |
| TAPE\_FILEMARKS<br/>        | Writes the number of filemarks specified by the **Count** parameter.<br/> |
| TAPE\_SHORT\_FILEMARKS<br/> | Writes the number of short filemarks specified by **Count**.<br/>         |
| TAPE\_LONG\_FILEMARKS <br/> | Writes the number of long filemarks specified by **Count**.<br/>          |



�

</dd> <dt>

**Count**
</dt> <dd>

Indicates the number of marks to write.

</dd> <dt>

**Immediate**
</dt> <dd>

When set to **TRUE**, indicates that the target device should return status immediately. When set to **FALSE**, indicates that the device should return status after the operation is complete.

</dd> </dl>

## Requirements



|                   |                                                                                                                          |
|-------------------|--------------------------------------------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>Ntddtape.h (include Ntddtape.h or Minitape.h)</dt> </dl> |



## See also

<dl> <dt>

[**IOCTL\_TAPE\_WRITE\_MARKS**](ioctl-tape-write-marks.md)
</dt> <dt>

[**TapeMiniWriteMarks**](https://msdn.microsoft.com/library/windows/hardware/ff567958)
</dt> </dl>

�

�

[Send comments about this topic to Microsoft](mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback%20%5Bstorage\storage%5D:%20TAPE_WRITE_MARKS%20structure%20%20RELEASE:%20%283/29/2018%29&body=%0A%0APRIVACY%20STATEMENT%0A%0AWe%20use%20your%20feedback%20to%20improve%20the%20documentation.%20We%20don't%20use%20your%20email%20address%20for%20any%20other%20purpose,%20and%20we'll%20remove%20your%20email%20address%20from%20our%20system%20after%20the%20issue%20that%20you're%20reporting%20is%20fixed.%20While%20we're%20working%20to%20fix%20this%20issue,%20we%20might%20send%20you%20an%20email%20message%20to%20ask%20for%20more%20info.%20Later,%20we%20might%20also%20send%20you%20an%20email%20message%20to%20let%20you%20know%20that%20we've%20addressed%20your%20feedback.%0A%0AFor%20more%20info%20about%20Microsoft's%20privacy%20policy,%20see%20http://privacy.microsoft.com/default.aspx. "Send comments about this topic to Microsoft")





