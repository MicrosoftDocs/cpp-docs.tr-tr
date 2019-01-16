---
title: CompareStringOrdinal Yöntemi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
ms.openlocfilehash: c9dbbe8926036ea18210fb30928fafc40093092e
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335216"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](microsoft-wrl-wrappers-details-namespace.md)