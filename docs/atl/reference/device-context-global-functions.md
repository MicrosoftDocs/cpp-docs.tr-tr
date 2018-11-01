---
title: Cihaz bağlamı genel işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: 25ceae897d3cc845ab06fd4d898c87518b15eacb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50551209"
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel işlevleri

Bu işlev, belirli bir cihaz için bir cihaz bağlamı oluşturur.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|

##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC

Belirtilen cihaz için bir cihaz bağlamı oluşturur [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice) yapısı.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Parametreler

*hdc*<br/>
[in] Bir cihaz bağlamı NULL veya var olan işleyici.

*ptd*<br/>
[in] Bir işaretçi `DVTARGETDEVICE` hedef cihaz hakkındaki bilgileri içeren yapısı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen cihaz için bir cihaz bağlamı için bir tanıtıcı döndürür `DVTARGETDEVICE`. Cihaz belirtilmezse, varsayılan görüntüleme cihazında tanıtıcısını döndürür.

### <a name="remarks"></a>Açıklamalar

Yapısı NULL ise ve *hdc* NULL ise, varsayılan görüntüleme cihazı için bir cihaz bağlamı oluşturur.

Varsa *hdc* NULL değil ve *ptd* NULL ise mevcut bir işlevi döndürür *hdc*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlwin.h

## <a name="see-also"></a>Ayrıca Bkz.

[İşlevler](../../atl/reference/atl-functions.md)
