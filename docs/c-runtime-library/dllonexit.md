---
description: 'Hakkında daha fazla bilgi edinin: __dllonexit'
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
ms.openlocfilehash: ef9dc444ecb1b36062a4dc9ea98ec9a15804f930
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151833"
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

`__dllonexit`İşlev, bu işlev tarafından kullanılan genel değişkenlerin bu yordama görünür olmaması dışında [_onexit](../c-runtime-library/reference/onexit-onexit-m.md) işleve benzer. Genel değişkenler yerine, bu işlev `pbegin` ve `pend` parametrelerini kullanır.

`_onexit` `atexit` Msvcrt ile bağlantılı bir dll içindeki ve işlevleri. LıB kendi atexit/_onexit listesini korumalıdır. Bu yordam, bu tür dll 'Ler tarafından çağrılan çalışandır.

`_PVFV`Türü olarak tanımlanır `typedef void (__cdecl *_PVFV)(void)` .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli dosya|
|-------------|-------------------|
|__dllonexit|OnExit. c|

## <a name="see-also"></a>Ayrıca bkz.

[_onexit, _onexit_m](../c-runtime-library/reference/onexit-onexit-m.md)
