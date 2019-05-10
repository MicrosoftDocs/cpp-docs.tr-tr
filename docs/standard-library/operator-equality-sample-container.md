---
title: işleç == (&lt;örnek kapsayıcı&gt;)
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
ms.openlocfilehash: 9313df5d75efa043f2fb9df6090c125de75a2636
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220264"
---
# <a name="operator-ltsample-containergt"></a>işleç == (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu Microsoft olan C++ kullanılan kapsayıcıları işlevsiz bir örnek olarak belgeleri C++ standart kitaplığı. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Aşırı `operator==` şablon sınıfının iki nesneleri karşılaştırmak için [kapsayıcı](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `left.` [boyutu](../standard-library/container-class-size.md) ` == right.size && equal(left.` [başlamak](../standard-library/container-class-begin.md)`, left.`[son](../standard-library/container-class-end.md)`, right.begin)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
