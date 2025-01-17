---
UID: NE:rilapitypes.RILSMSFORMAT
title: RILSMSFORMAT (rilapitypes.h)
description: "Microsoft reserves the RILSMSFORMAT enumeration for internal use only. Don't use this enumeration in your code."
old-location: netvista\rilsmsformat_2.htm
tech.root: netvista
ms.date: 02/26/2018
keywords: ["RILSMSFORMAT enumeration"]
ms.keywords: RILSMSFORMAT, RILSMSFORMAT enumeration [Network Drivers Starting with Windows Vista], RIL_SMSFORMAT_3GPP, RIL_SMSFORMAT_3GPP2, RIL_SMSFORMAT_MAX, netvista.rilsmsformat_2, rilapitypes/RILSMSFORMAT, rilapitypes/RIL_SMSFORMAT_3GPP, rilapitypes/RIL_SMSFORMAT_3GPP2, rilapitypes/RIL_SMSFORMAT_MAX
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
targetos: Windows
req.typenames: RILSMSFORMAT
req.product: Windows 10 or later.
f1_keywords:
 - RILSMSFORMAT
 - rilapitypes/RILSMSFORMAT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILSMSFORMAT
---

# RILSMSFORMAT enumeration (rilapitypes.h)


## -description

This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## -enum-fields

### -field RIL_SMSFORMAT_NONE

### -field RIL_SMSFORMAT_3GPP

### -field RIL_SMSFORMAT_3GPP2

### -field RIL_SMSFORMAT_MAX

## -syntax

```cpp
typedef enum _RILSMSFORMAT {
  RIL_SMSFORMAT_3GPP,
  RIL_SMSFORMAT_3GPP2,
  RIL_SMSFORMAT_MAX
} RILSMSFORMAT;
```

