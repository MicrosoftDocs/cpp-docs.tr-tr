---
description: ': İşleci hakkında daha fazla bilgi edinin &lt; ( &lt; örnek kapsayıcı &gt; )'
title: işleç &lt; ( &lt; örnek kapsayıcı &gt; )
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
ms.openlocfilehash: e7bba9be33a2dc4dea6257b159966c867bb33929
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176489"
---
# <a name="operatorlt-ltsample-containergt"></a>işleç &lt; ( &lt; örnek kapsayıcı &gt; )

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **işleç<** aşırı yükler.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator<(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

`lexicographical_compare(left.begin, left.end, right.begin, right.end)` döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<sample container>](../standard-library/sample-container.md)\
[başladı](../standard-library/container-class-begin.md)\
[erer](../standard-library/container-class-end.md)
