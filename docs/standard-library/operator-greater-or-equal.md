---
title: işlecinde&gt;=
ms.date: 11/04/2016
f1_keywords:
- operator>=
- std::>=
- std.operator>=
- '>='
- std.>=
- std::operator>=
helpviewer_keywords:
- '>= operator, comparing specific objects'
- operator >=
- operator>=
ms.assetid: 14fbebf5-8b75-4afa-a51b-3112d31c07cf
ms.openlocfilehash: 6eb8db25f5f30a978de197d699acf28bf8bea116
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447958"
---
# <a name="operatorgt"></a>işlecinde&gt;=

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Şablon sınıfı [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **> =** aşırı yüklemeleri işleci.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator>=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `!(left < right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)
