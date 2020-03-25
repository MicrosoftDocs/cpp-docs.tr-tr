---
title: DerefHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 43453d3162de697fa1cfcf0581953c91bbe3934f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214051"
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

*Şı*<br/>
Şablon parametresi.

## <a name="remarks"></a>Açıklamalar

`T*` Template parametresine başvuru yapılan bir işaretçiyi temsil eder.

**DerefHelper** , şöyle bir ifade içinde kullanılır: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`DerefType`|Başvurusu kaldırılmış şablon parametresi için tanımlayıcı `T*`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DerefHelper`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
