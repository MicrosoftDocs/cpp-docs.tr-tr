---
description: ': İşleci hakkında daha fazla bilgi&gt;='
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
ms.openlocfilehash: 1821647ebb281020cef1798cf056fbf816aa855c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297076"
---
# <a name="operatorgt"></a>işlecinde&gt;=

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **>=** aşırı yüklemeleri işleci.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator>=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

`!(left < right)` döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<sample container>](../standard-library/sample-container.md)
