---
title: Nesne durumu makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04bad7c90869eb5a5b87a465b175e4ed3f0b9991
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43751517"
---
# <a name="object-status-macros"></a>Nesne durumu makroları

Bu makro, ActiveX denetimlerine ait bayraklarını ayarlar.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL ActiveX denetimlerinde OLEMISC bayrakları ayarlamak için kullanılır.|  

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS

ATL ActiveX denetimlerinde OLEMISC bayrakları ayarlamak için kullanılır.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Parametreler

*MiscStatus*  
Tüm uygun OLEMISC bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir ActiveX denetimi için OLEMISC bayrakları ayarlamak için kullanılır. Başvurmak [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) daha fazla ayrıntı için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
