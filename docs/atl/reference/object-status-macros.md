---
title: Nesne durumu makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: d9e2223739dc3d0636337e2e2f713c80dff50131
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835239"
---
# <a name="object-status-macros"></a>Nesne durumu makroları

Bu makro, ActiveX denetimlerine ait olan bayrakları ayarlar.

|Ad|Açıklama|
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|OLEMISC bayraklarını ayarlamak için ATL ActiveX denetimlerinde kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a> DECLARE_OLEMISC_STATUS

OLEMISC bayraklarını ayarlamak için ATL ActiveX denetimlerinde kullanılır.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Parametreler

*Hatalı CStatus*<br/>
Tüm geçerli OLEMISC bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir ActiveX denetimi için OLEMISC bayraklarını ayarlamak üzere kullanılır. Daha fazla ayrıntı için [IOleObject:: GetMiscStatus](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) öğesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
