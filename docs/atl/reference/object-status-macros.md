---
title: Nesne Durumu Makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 5617ce7fb972c98775072f72244f91052d41ece3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326174"
---
# <a name="object-status-macros"></a>Nesne Durumu Makroları

Bu makro, ActiveX denetimlerine ait bayrakları ayarlar.

|||
|-|-|
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|OLEMISC bayraklarını ayarlamak için ATL ActiveX denetimlerinde kullanılır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="declare_olemisc_status"></a><a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS

OLEMISC bayraklarını ayarlamak için ATL ActiveX denetimlerinde kullanılır.

```
DECLARE_OLEMISC_STATUS( miscstatus )
```

### <a name="parameters"></a>Parametreler

*yanlış durum*<br/>
Tüm geçerli OLEMISC bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu makro, ActiveX denetimi için OLEMISC bayraklarını ayarlamak için kullanılır. Daha fazla bilgi için [IOleObject::GetMiscStatus'e](/windows/win32/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
