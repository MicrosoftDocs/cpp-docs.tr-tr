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
ms.openlocfilehash: c4b0caadf20d6c5494acf47ee5a788b5ee009c47
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957337"
---
# <a name="__rtdynamiccast"></a>__RTDynamicCast

[Dynamic_cast](../cpp/dynamic-cast-operator.md) işlecinin çalışma zamanı uygulama.

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

*ınptr*<br/>
Polimorfik nesne işaretçisi.

*VfDelta*<br/>
Nesne içindeki sanal işlev işaretçisinin boşluğu.

*SrcType*<br/>
`inptr` Parametresi tarafından işaret edilen statik nesne türü.

*Öğesi*<br/>
İstenen dönüştürme sonucu.

*IsReference*<br/>
Giriş bir başvuru ise **doğru** ; Giriş bir işaretçisiyse **false** .

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa uygun alt nesneye yönelik işaretçi. Aksi takdirde, **null**.

## <a name="exceptions"></a>Özel Durumlar

`bad_cast()`girişi bir başvuru `dynamic_cast<>` ise ve atama başarısız olursa.

## <a name="remarks"></a>Açıklamalar

`inptr` Türündeki`TargetType`bir nesneye dönüştürür. Türü `inptr` bir işaretçisiyse veya bir başvuru ise `TargetType` l değeri `TargetType` bir işaretçi olmalıdır. `TargetType`bir işaretçi veya önceden tanımlanmış bir sınıf türüne başvuru ya da void işaretçisi olmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__RTDynamicCast|rtti. h|