---
title: İşleç&lt;= (&lt;örnek kapsayıcı&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
ms.openlocfilehash: 4b7461246b7dd610dc0043a242bd8010e9077fad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371405"
---
# <a name="operatorlt-ltsample-containergt"></a>İşleç&lt;= (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konuda C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsiz bir örnek olarak Visual C++ belgelerinin bulunduğu. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Aşırı **operator < =** şablon sınıfının iki nesneleri karşılaştırmak için [kapsayıcı](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `!(right < left)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
