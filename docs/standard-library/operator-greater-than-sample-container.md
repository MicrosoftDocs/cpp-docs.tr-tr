---
title: işleç&gt; (&lt;örnek kapsayıcı&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: e7da0250dc647d2d519b9c3d105fb942717c7a4c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449736"
---
# <a name="operatorgt-ltsample-containergt"></a>işleç&gt; (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Şablon sınıfı [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **işleç >** aşırı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `right < left`.

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)
