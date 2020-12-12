---
description: ': İşleci hakkında daha fazla bilgi edinin &gt; ( &lt; örnek kapsayıcı &gt; )'
title: işleç &gt; ( &lt; örnek kapsayıcı &gt; )
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
ms.openlocfilehash: 4a8282b3cac493bbf0c2bcb24b8db44df45168f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97114968"
---
# <a name="operatorgt-ltsample-containergt"></a>işleç &gt; ( &lt; örnek kapsayıcı &gt; )

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için **işleç>** aşırı yükler.

## <a name="syntax"></a>Syntax

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

`right < left` döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<sample container>](../standard-library/sample-container.md)
