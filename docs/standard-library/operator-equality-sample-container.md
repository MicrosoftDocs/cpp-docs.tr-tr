---
title: operator = = (&lt;sample kapsayıcı &gt;)
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
ms.openlocfilehash: 3f84e8e5f7d0c09a865fe47d7493daecf68cf60c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689199"
---
# <a name="operator-ltsample-containergt"></a>operator = = (&lt;sample kapsayıcı &gt;)

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için `operator==` aşırı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

@No__t_0[boyutunu](../standard-library/container-class-size.md) döndürür ` == right.size && equal(left.`[End](../standard-library/container-class-end.md) `, right.begin)` `, left.`[başlar](../standard-library/container-class-begin.md) .

## <a name="see-also"></a>Ayrıca bkz.

[kapsayıcı > \<sample](../standard-library/sample-container.md)
