---
title: Nesne durumu makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: cb5ff6d7570b03b32852fc450f58043446f721f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198180"
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

*MiscStatus*<br/>
Tüm uygun OLEMISC bayrakları.

### <a name="remarks"></a>Açıklamalar

Bu makro, bir ActiveX denetimi için OLEMISC bayrakları ayarlamak için kullanılır. Başvurmak [IOleObject::GetMiscStatus](/windows/desktop/api/oleidl/nf-oleidl-ioleobject-getmiscstatus) daha fazla ayrıntı için.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]

## <a name="see-also"></a>Ayrıca bkz.

[Makroları](../../atl/reference/atl-macros.md)
