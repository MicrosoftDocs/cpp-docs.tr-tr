---
title: işleç&lt; (&lt;örnek kapsayıcısı&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator<
- operator<
- std.<
- <
- std.operator<
- std::<
helpviewer_keywords:
- < operator, comparing specific objects
- operator<, valarrays
- < operator
- operator <, valarrays
ms.assetid: 31027dd6-53be-428b-b950-1dcb25393597
ms.openlocfilehash: 6ef43fb762c4da71062fc846048f21c0112bfafc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80215273"
---
# <a name="operatorlt-ltsample-containergt"></a>işleç&lt; (&lt;örnek kapsayıcısı&gt;)

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **işleç <** aşırı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

`lexicographical_compare(left.begin, left.end, right.begin, right.end)` döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)\
\ [başla](../standard-library/container-class-begin.md)
[erer](../standard-library/container-class-end.md)
