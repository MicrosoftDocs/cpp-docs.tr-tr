---
title: CompareStringOrdinal yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Details::CompareStringOrdinal
dev_langs:
- C++
ms.assetid: ffa997fd-8cd7-40a5-b9e7-f55d40b072f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0dc85bad774260f3db589d4f2649e0c39de2a530
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067208"
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

**Namespace:** Microsoft::WRL::Wrappers::Details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Wrappers::Details Ad Alanı](../windows/microsoft-wrl-wrappers-details-namespace.md)