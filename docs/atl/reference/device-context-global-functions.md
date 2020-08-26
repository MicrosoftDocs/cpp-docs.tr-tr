---
title: Cihaz bağlamı genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: d2d25660083f074683a3f42f878497ce14a008b8
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88833471"
---
# <a name="device-context-global-functions"></a>Cihaz bağlamı genel Işlevleri

Bu işlev, belirli bir cihaz için bir cihaz bağlamı oluşturur.

|Ad|Açıklama|
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Bir cihaz bağlamı oluşturur.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a> AtlCreateTargetDC

[Dvtargetdevice](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısında belirtilen cihaz için bir cihaz bağlamı oluşturur.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Parametreler

*HDC*<br/>
'ndaki Bir cihaz bağlamının var olan tanıtıcısı veya NULL.

*PTD*<br/>
'ndaki `DVTARGETDEVICE` Hedef cihazla ilgili bilgileri içeren yapıya yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İçinde belirtilen cihazın bir cihaz bağlamına tanıtıcıyı döndürür `DVTARGETDEVICE` . Hiçbir cihaz belirtilmemişse, varsayılan görüntüleme cihazına olan tanıtıcıyı döndürür.

### <a name="remarks"></a>Açıklamalar

Yapı NULL ise ve *HDC* null ise, varsayılan görüntü cihazı için bir cihaz bağlamı oluşturur.

*HDC* null değilse ve *PTD* null ise, işlev var olan *HDC*'yi döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin. h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
