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
ms.openlocfilehash: 89d41d099d151f77d91cd94b22047824779dcf54
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687343"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Sınıf şablonu [kapsayıcısının](../standard-library/sample-container-class.md)iki nesnesini karşılaştırmak için `operator!=` aşırı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Dönüş Değeri

@No__t_0 döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[kapsayıcı > \<sample](../standard-library/sample-container.md)
