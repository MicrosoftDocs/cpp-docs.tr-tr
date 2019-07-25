---
title: işleç&lt; (&lt;örnek kapsayıcı&gt;)
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
ms.openlocfilehash: a286833d96e913a66240d25798e1cc230adf58b0
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458719"
---
# <a name="operatorlt-ltsample-containergt"></a>işleç&lt; (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Şablon sınıfı [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **işleç <** aşırı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `lexicographical_compare(left.begin, left.end, right.begin, right.end)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)\
[başladı](../standard-library/container-class-begin.md)\
[erer](../standard-library/container-class-end.md)