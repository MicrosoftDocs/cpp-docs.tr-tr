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
ms.openlocfilehash: a5384966ff96c4e4831ba06f7c67467156a9ecd2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170078"
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
`inptr` parametresi tarafından işaret edilen statik nesne türü.

*Öğesi*<br/>
İstenen dönüştürme sonucu.

*IsReference*<br/>
Giriş bir başvuru ise **doğru** ; Giriş bir işaretçisiyse **false** .

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa uygun alt nesneye yönelik işaretçi. Aksi takdirde, **null**.

## <a name="exceptions"></a>Özel Durumlar

`dynamic_cast<>` giriş bir başvuru ise ve dönüştürme başarısız olursa `bad_cast()`.

## <a name="remarks"></a>Açıklamalar

`inptr` `TargetType`türündeki bir nesneye dönüştürür. `inptr` türü, `TargetType` bir işaretçisiyse veya `TargetType` bir başvuru ise bir l değeri olduğunda bir işaretçi olmalıdır. `TargetType`, önceden tanımlanmış bir sınıf türüne veya void işaretçisine bir işaretçi veya başvuru olmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__RTDynamicCast|rtti. h|
