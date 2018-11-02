---
title: __RTDynamicCast
ms.date: 11/04/2016
apiname:
- __RTDynamicCast
apilocation:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: f4bf4895af99b2d5c2d61e739c9d49d59cecb020
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485741"
---
# <a name="rtdynamiccast"></a>__RTDynamicCast

Çalışma zamanı uygulaması [dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.

## <a name="syntax"></a>Sözdizimi

```cpp
PVOID __RTDynamicCast (
   PVOID inptr,
   LONG VfDelta,
   PVOID SrcType,
   PVOID TargetType,
   BOOL isReference
   ) throw(...)
```

#### <a name="parameters"></a>Parametreler

*inptr*<br/>
Çok biçimli bir nesne işaretçisi.

*VfDelta*<br/>
Nesnedeki sanal işlev işaretçisi uzaklığı.

*SrcType*<br/>
Statik nesne türü tarafından işaret edilen `inptr` parametresi.

*TargetType*<br/>
Hedeflenen atamanın sonucu.

*IsReference*<br/>
**doğru** Giriş bir başvuruysa; **false** Giriş bir işaretçi ise.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa uygun alt nesneye işaretçi; Aksi takdirde, **NULL**.

## <a name="exceptions"></a>Özel Durumlar

`bad_cast()` Giriş `dynamic_cast<>` bir başvurudur ve dönüştürme başarısız.

## <a name="remarks"></a>Açıklamalar

Dönüştürür `inptr` türünde bir nesne için `TargetType`. Türünü `inptr` bir işaretçi olmalıdır `TargetType` bir işaretçi ya da bir l-değeri ise `TargetType` bir başvurudur. `TargetType` bir işaretçi veya önceden tanımlanmış sınıf türüne yapılan başvuru veya void bir işaretçi olması gerekir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__RTDynamicCast|rtti.h|