---
description: 'Daha fazla bilgi edinin: CompareStringOrdinal yöntemi'
title: CompareStringOrdinal Yöntemi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: 1994d0f3ec4104e27094de10255194a911ae2945
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282854"
---
# <a name="comparestringordinal-method"></a>CompareStringOrdinal Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline INT32 CompareStringOrdinal(
   HSTRING lhs,
   HSTRING rhs)
```

### <a name="parameters"></a>Parametreler

*Point*<br/>
Karşılaştırılacak ilk HSTRıNG.

*sağ taraftan*<br/>
Karşılaştırılacak ikinci HSTRING.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Koşul|
|-----------|---------------|
|-1|*LHS* , *RHS*'den küçük.|
|0|*LHS* eşittir *RHS*.|
|1|*LHS* , *RHS*'den büyük.|

## <a name="remarks"></a>Açıklamalar

Belirtilen iki HSTRıNG nesnesini karşılaştırır ve göreli konumunu bir sıralama düzeninde gösteren bir tamsayı döndürür.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** corewrapper. h

**Ad alanı:** Microsoft:: WRL:: sarmalayıcılar::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL:: sarmalayıcılar::D euçlar ad alanı](microsoft-wrl-wrappers-details-namespace.md)
