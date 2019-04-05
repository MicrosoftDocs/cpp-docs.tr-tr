---
title: CompareStringOrdinal Yöntemi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: a1ac0576bdd374daa5cbd445af480e7652b61e45
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59027709"
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

*lhs*<br/>
Karşılaştırılacak ilk HSTRING.

*Sol*<br/>
Karşılaştırılacak ikinci HSTRING.

## <a name="return-value"></a>Dönüş Değeri

|Değer|Koşul|
|-----------|---------------|
|-1|*lhs* olduğu küçüktür *sol*.|
|0|*lhs* eşittir *sol*.|
|1.|*lhs* büyüktür *sol*.|

## <a name="remarks"></a>Açıklamalar

İki belirtilen HSTRING nesneyi karşılaştırır ve bir sıralama düzeni kendi göreli konumunu belirten bir tamsayı döndürür.

## <a name="requirements"></a>Gereksinimler

**Başlık:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::details

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)