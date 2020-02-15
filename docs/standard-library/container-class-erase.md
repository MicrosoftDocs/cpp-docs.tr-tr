---
title: Kapsayıcı Sınıfı::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 1fa3fe7dee10f3033b84a671fdc35c193cd6ec3c
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257903"
---
# <a name="container-classerase"></a>Kapsayıcı Sınıfı::erase

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

Bir öğeyi siler.

## <a name="syntax"></a>Sözdizimi

```cpp
iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>Açıklamalar

İlk üye işlevi, *_Where*tarafından işaret edilen denetimli sıranın öğesini kaldırır. İkinci üye işlevi [`first`, `last`) aralığındaki denetlenen sıranın öğelerini kaldırır. Her ikisi de kaldırılan öğelerin ötesinde kalan ilk öğeyi atayan bir yineleyici döndürür ya da böyle bir öğe yoksa [End](../standard-library/container-class-end.md) .

Üye işlevleri yalnızca bir kopyalama işlemi özel durum oluşturursa bir özel durum oluşturur.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)
