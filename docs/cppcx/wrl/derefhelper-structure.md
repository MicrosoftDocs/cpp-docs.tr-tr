---
description: 'Daha fazla bilgi edinin: DerefHelper yapısı'
title: DerefHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 8605e3923d8d3099a080be22f9d8e70ee9187ef9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272922"
---
# <a name="derefhelper-structure"></a>DerefHelper Yapısı

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Şablon parametresi.

## <a name="remarks"></a>Açıklamalar

Şablon parametresine başvuru yapılan bir işaretçiyi temsil eder `T*` .

**DerefHelper** , şöyle bir ifadede kullanılır: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;` .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`DerefType`|Başvurusu kaldırılmış şablon parametresi için tanımlayıcı `T*` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DerefHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
