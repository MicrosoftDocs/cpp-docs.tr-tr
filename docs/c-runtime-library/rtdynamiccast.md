---
description: 'Hakkında daha fazla bilgi edinin: __RTDynamicCast'
title: __RTDynamicCast
ms.date: 1/14/2021
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __RTDynamicCast
helpviewer_keywords:
- __RTDynamicCast
ms.assetid: 56aa2d7a-aa47-46ef-830d-e37175611239
ms.openlocfilehash: cefd5248e0409b72f97c959d08aa30b1c0167e26
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243118"
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
Parametresi tarafından işaret edilen statik nesne türü `inptr` .

*Öğesi*<br/>
İstenen dönüştürme sonucu.

*IsReference*<br/>
**`true`** Giriş bir başvuru ise, **`false`** Giriş bir işaretçisiyse.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa uygun alt nesneye yönelik işaretçi. Aksi takdirde, **null**.

## <a name="exceptions"></a>Özel durumlar

`bad_cast()` girişi `dynamic_cast<>` bir başvuru ise ve atama başarısız olursa.

## <a name="remarks"></a>Açıklamalar

`inptr`Türündeki bir nesneye dönüştürür `TargetType` . Türü bir işaretçisiyse `inptr` `TargetType` veya bir başvuru ise l değeri bir işaretçi olmalıdır `TargetType` . `TargetType` bir işaretçi veya önceden tanımlanmış bir sınıf türüne başvuru ya da void işaretçisi olmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__RTDynamicCast|rtti. h|
