---
title: __RTDynamicCast
ms.date: 11/04/2016
api_name:
- __RTDynamicCast
api_location:
- msvcr90.dll
- msvcr110.dll
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: 238310791baebc941ad23b798adc1ea2e7fffcbb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218513"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

[Dynamic_cast](../cpp/dynamic-cast-operator.md) işlecinin çalışma zamanı uygulama.

## <a name="syntax"></a>Söz dizimi

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

*ınptr*<br/>
Polimorfik nesne işaretçisi.

*VfDelta*<br/>
Nesne içindeki sanal işlev işaretçisinin boşluğu.

*SrcType*<br/>
Parametresi tarafından işaret edilen statik nesne türü `inptr` .

*Öğesi*<br/>
İstenen dönüştürme sonucu.

*IsReference*<br/>
**`true`** Giriş bir başvuru ise, **`false`** Giriş bir işaretçisiyse.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa uygun alt nesneye yönelik işaretçi. Aksi takdirde, **null**.

## <a name="exceptions"></a>Özel durumlar

`bad_cast()`girişi `dynamic_cast<>` bir başvuru ise ve atama başarısız olursa.

## <a name="remarks"></a>Açıklamalar

`inptr`Türündeki bir nesneye dönüştürür `TargetType` . Türü bir işaretçisiyse `inptr` `TargetType` veya bir başvuru ise l değeri bir işaretçi olmalıdır `TargetType` . `TargetType`bir işaretçi veya önceden tanımlanmış bir sınıf türüne başvuru ya da void işaretçisi olmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__RTDynamicCast|rtti. h|
