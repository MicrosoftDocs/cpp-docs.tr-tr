---
description: 'Daha fazla bilgi edinin: nesne durumu makroları'
title: Nesne durumu makroları
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
ms.openlocfilehash: 7aac547ac0b63a7db9ceea3b58befdea3e076f3f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157912"
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
