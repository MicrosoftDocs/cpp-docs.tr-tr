---
title: __dllonexit
ms.date: 11/04/2016
api_name:
- __dllonexit
api_location:
- msvcrt.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr120.dll
- msvcr90.dll
- msvcr120_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __dllonexit
helpviewer_keywords:
- __dllonexit
ms.assetid: 708f2ceb-f95c-46b0-a58d-d68b3fa36f12
ms.openlocfilehash: 61d63c751dd755bf8a7680c674681e114945814b
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940442"
---
# <a name="__dllonexit"></a>__dllonexit

Çıkış zamanında çağrılması için bir yordam kaydeder.

## <a name="syntax"></a>Sözdizimi

```
_onexit_t __dllonexit(   _onexit_t func,
   _PVFV **  pbegin,
   _PVFV **  pend
   )
```

#### <a name="parameters"></a>Parametreler

*func*<br/>
Çıkış sonrasında yürütülecek bir işlev işaretçisi.

*pbegın*<br/>
Ayrılmaya yürütülecek işlevlerin listesinin başlangıcını işaret eden bir değişkene yönelik işaretçi.

*bekleyen*<br/>
Ayrılmaya yürütülecek işlevlerin listesinin sonuna işaret eden değişken işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, kullanıcının işlevine yönelik bir işaretçi. Aksi takdirde, bir **null** işaretçi.

## <a name="remarks"></a>Açıklamalar

İşlev, bu işlev tarafından kullanılan genel değişkenlerin bu yordama görünür olmaması dışında, [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) işlevine benzer. `__dllonexit` Genel değişkenler yerine, bu işlev `pbegin` ve `pend` parametrelerini kullanır.

Msvcrt ile `atexit` bağlantılı bir dll içindeki veişlevleri.`_onexit` LıB kendi atexit/_onexit listesini korumalıdır. Bu yordam, bu tür dll 'Ler tarafından çağrılan çalışandır.

`_PVFV` Türü olarak`typedef void (__cdecl *_PVFV)(void)`tanımlanır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli dosya|
|-------------|-------------------|
|__dllonexit|OnExit. c|

## <a name="see-also"></a>Ayrıca bkz.

[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
