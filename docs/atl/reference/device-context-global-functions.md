---
title: Cihaz bağlamı genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: d225bd0cd996fd908479b5a93aad81ea0428900b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496096"
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel Işlevleri

Bu işlev, belirli bir cihaz için bir cihaz bağlamı oluşturur.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|

##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC

[Dvtargetdevice](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısında belirtilen cihaz için bir cihaz bağlamı oluşturur.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Parametreler

*HDC*<br/>
'ndaki Bir cihaz bağlamının var olan tanıtıcısı veya NULL.

*ptd*<br/>
'ndaki Hedef cihazla ilgili bilgileri `DVTARGETDEVICE` içeren yapıya yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İçinde belirtilen cihazın bir cihaz bağlamına tanıtıcıyı döndürür `DVTARGETDEVICE`. Hiçbir cihaz belirtilmemişse, varsayılan görüntüleme cihazına olan tanıtıcıyı döndürür.

### <a name="remarks"></a>Açıklamalar

Yapı NULL ise ve *HDC* null ise, varsayılan görüntü cihazı için bir cihaz bağlamı oluşturur.

*HDC* null değilse ve *PTD* null ise, işlev var olan *HDC*'yi döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
