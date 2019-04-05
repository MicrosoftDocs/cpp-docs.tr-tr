---
title: DerefHelper Yapısı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 96b7e83a854765fb872b87d062928311731cfd26
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032017"
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

Başvurusu kaldırılmış bir işaretçi temsil `T*` şablon parametresi.

**DerefHelper** bir ifadede gibi kullanılır: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`DerefType`|Başvurusu kaldırılmış bir şablon parametresi için tanımlayıcı `T*`.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`DerefHelper`

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)