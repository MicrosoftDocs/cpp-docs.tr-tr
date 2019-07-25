---
title: operator = = (&lt;örnek kapsayıcı&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: 168785abb09ca198435c301040d7628a6dd12b26
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460149"
---
# <a name="operator-ltsample-containergt"></a>operator = = (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Şablon `operator==` sınıfı [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için aşırı yüklemeler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

`left.` [Boyut](../standard-library/container-class-size.md) [başlangıcı](../standard-library/container-class-begin.md)[sonunu](../standard-library/container-class-end.md)döndürür. ` == right.size && equal(left.``, left.``, right.begin)`

## <a name="see-also"></a>Ayrıca bkz.

[\<örnek kapsayıcı >](../standard-library/sample-container.md)
