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
ms.openlocfilehash: 78d49f82f39bc0e96f88ffdcad2cde8a20b0f123
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221375"
---
# <a name="operatorlt-ltsample-containergt"></a>İşleç&lt;= (&lt;örnek kapsayıcı&gt;)

> [!NOTE]
> Bu konu Microsoft olan C++ kullanılan kapsayıcıları işlevsiz bir örnek olarak belgeleri C++ standart kitaplığı. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

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
