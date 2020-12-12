---
description: 'Daha fazla bilgi edinin: kapsayıcı sınıfı:: Erase'
title: Kapsayıcı Sınıfı::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 7e9d7747237a38c42bfb7a39c5d5e66cc8a44608
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324873"
---
# <a name="container-classerase"></a>Kapsayıcı Sınıfı::erase

> [!NOTE]
> Bu konu, C++ standart kitaplığı 'nda kullanılan kapsayıcılardan oluşan işlevsel bir örnek olarak Microsoft C++ belgelerinde yer almaktadır. Daha fazla bilgi için bkz. [C++ standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Bir öğeyi siler.

## <a name="syntax"></a>Syntax

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Açıklamalar

İlk üye işlevi, *_Where* tarafından işaret edilen denetimli sıranın öğesini kaldırır. İkinci üye işlevi, [,) aralığındaki denetlenen sıranın öğelerini kaldırır `first` `last` . Her ikisi de kaldırılan öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür ya da böyle bir öğe yoksa [End](../standard-library/container-class-end.md) .

Üye işlevleri yalnızca bir kopyalama işlemi özel durum oluşturursa bir özel durum oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek kapsayıcı sınıfı](../standard-library/sample-container-class.md)
