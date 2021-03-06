---
description: 'Daha fazla bilgi edinin: cihaz bağlamı genel Işlevleri'
title: Cihaz bağlamı genel Işlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: f5e87271170e29a2f0cc4d42b4e7739a5fd869ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139919"
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
