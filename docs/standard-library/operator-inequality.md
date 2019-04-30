---
title: operator!=
ms.date: 11/04/2016
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
ms.openlocfilehash: a3a750565f16a0a01770cea16bf91918887095f4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371431"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> Bu konuda C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsiz bir örnek olarak Visual C++ belgelerinin bulunduğu. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Aşırı `operator!=` şablon sınıfının iki nesneleri karşılaştırmak için [kapsayıcı](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

Döndürür `!(left == right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Örnek kapsayıcı >](../standard-library/sample-container.md)<br/>
