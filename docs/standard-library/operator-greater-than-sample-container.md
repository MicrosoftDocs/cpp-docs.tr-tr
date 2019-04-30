---
title: İşleç&gt; (&lt;örnek kapsayıcı&gt;)
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
ms.openlocfilehash: 7d6c1135632d57707812a6702d7226eafa49c0c2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371400"
---
# <a name="operatorgt-ltsample-containergt"></a>İşleç&gt; (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konuda C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsiz bir örnek olarak Visual C++ belgelerinin bulunduğu. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Aşırı **işleci >** şablon sınıfının iki nesneleri karşılaştırmak için [kapsayıcı](../standard-library/sample-container-class.md).

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

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
