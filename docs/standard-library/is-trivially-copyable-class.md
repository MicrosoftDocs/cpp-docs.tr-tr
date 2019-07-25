---
title: is_trivially_copyable sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_trivially_copyable
helpviewer_keywords:
- is_trivially_copyable
ms.assetid: 89a53bf8-036c-4108-91e1-fe34adbde8b3
ms.openlocfilehash: d3062ae311b63be76ba07185f4f8173afa4229cc
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459758"
---
# <a name="istriviallycopyable-class"></a>is_trivially_copyable sınıfı

Türün bir üçlü kopyalanabilir türü olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_trivially_copyable;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Tür *T* bir örnek bir kopyalanabilir türü ise true, aksi takdirde false değerini tutar. Üçlü kopyalanabilir türlerinin önemsiz olmayan kopyalama işlemleri, taşıma işlemleri veya yok ediciler yoktur. Genellikle, bir kopyalama işlemi bit düzeyinde bir kopya olarak uygulanmıyorsa önemsiz olarak değerlendirilir. Hem yerleşik türler hem de kopyalanabilir türler dizileri, önemli kopyalanabilir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<type_traits >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)
