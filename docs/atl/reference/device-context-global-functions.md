---
title: Cihaz Bağlamı Genel İşlevleri
ms.date: 11/04/2016
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
ms.openlocfilehash: e640f310a1976c29a39f0ab7c2575dfd1073c889
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330148"
---
# <a name="device-context-global-functions"></a>Cihaz Bağlamı Genel İşlevleri

Bu işlev, belirli bir aygıt için bir aygıt bağlamı oluşturur.

|||
|-|-|
|[AtlCreateTargetDC](#atlcreatetargetdc)|Aygıt bağlamı oluşturur.|

## <a name="atlcreatetargetdc"></a><a name="atlcreatetargetdc"></a>AtlCreateTargetDC

[DVTARGETDEVICE](/windows/win32/api/objidl/ns-objidl-dvtargetdevice) yapısında belirtilen aygıt için bir aygıt bağlamı oluşturur.

```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```

### <a name="parameters"></a>Parametreler

*Hdc*<br/>
[içinde] Aygıt bağlamının varolan tutamacı veya NULL.

*ptd*<br/>
[içinde] Hedef aygıt `DVTARGETDEVICE` hakkında bilgi içeren yapının işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Tanıtıcıyı, 'de belirtilen aygıt için `DVTARGETDEVICE`aygıt bağlamına döndürür. Aygıt belirtilmemişse, tutamacı varsayılan görüntü aygıtına döndürür.

### <a name="remarks"></a>Açıklamalar

Yapı NULL ve *HDC* NULL ise, varsayılan görüntü aygıtı için bir aygıt bağlamı oluşturur.

*HDC* NULL değilse ve *ptd* NULL ise, işlev varolan *hdc*döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlwin.h

## <a name="see-also"></a>Ayrıca bkz.

[İşlevler](../../atl/reference/atl-functions.md)
