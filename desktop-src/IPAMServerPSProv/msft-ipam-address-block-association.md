---
Description: 'Defines an association between a IPAM block and an IPAM address.'
audience: developer
author: 'REDMOND\\markl'
manager: 'REDMOND\\markl'
ms.assetid: '0352085a-1f7d-4886-bc5b-e7bf7bd04c3c'
ms.prod: 'windows-server-dev'
ms.technology:
- 'internet-protocol-address-management'
- 'windows-management-instrumentation'
ms.tgt_platform: multiple
title: 'MSFT\_IPAM\_Address\_Block\_Association class'
---

# MSFT\_IPAM\_Address\_Block\_Association class

Defines an association between a IPAM block and an IPAM address.

The following syntax is simplified from Managed Object Format (MOF) code and includes all of the inherited properties.

## Syntax

``` syntax
[Association, Aggregation, UMLPackagePath("CIM::Core::CoreElements"), ClassVersion("1.0.0"), dynamic, provider("IPAMServerPSProvider"), AMENDMENT]
class MSFT_IPAM_Address_Block_Association : CIM_Component
{
  MSFT_IPAM_Address REF PartComponent;
  MSFT_IPAM_Block�� REF GroupComponent;
};
```

## Members

The **MSFT\_IPAM\_Address\_Block\_Association** class has these types of members:

-   [Properties](#properties)

### Properties

The **MSFT\_IPAM\_Address\_Block\_Association** class has these properties.

<dl> <dt>

**GroupComponent**
</dt> <dd> <dl> <dt>

Data type: **MSFT\_IPAM\_Block**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Aggregate**](https://msdn.microsoft.com/library/aa393650), [**Override**](https://msdn.microsoft.com/library/aa393650) ("GroupComponent")
</dt> </dl>

Reference to the Block object.

</dd> <dt>

**PartComponent**
</dt> <dd> <dl> <dt>

Data type: **MSFT\_IPAM\_Address**
</dt> <dt>

Access type: Read-only
</dt> <dt>

Qualifiers: [**key**](https://msdn.microsoft.com/library/aa392157), [**Override**](https://msdn.microsoft.com/library/aa393650) ("PartComponent")
</dt> </dl>

Reference to the Address object.

</dd> </dl>

## Requirements



|                                     |                                                                                                     |
|-------------------------------------|-----------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                           |
| Minimum supported server<br/> | Windows Server�2012�R2<br/>                                                                   |
| Namespace<br/>                | Root\\Microsoft\\IPAM<br/>                                                                    |
| MOF<br/>                      | <dl> <dt>IPAMServerPSProvider.mof</dt> </dl> |
| DLL<br/>                      | <dl> <dt>IPAMServerPSProvider.dll</dt> </dl> |



## See also

<dl> <dt>

[**CIM\_Component**](cim-component.md)
</dt> <dt>

[IPAM Server WMI Provider Reference](ipam-server-wmi-provider-reference.md)
</dt> </dl>

�

�



