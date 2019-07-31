---
title: Kapsayıcı Sınıfı::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: ccf4ae6ebc3ca13a42ca950310a60e30dbb27034
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450766"
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap

> [!NOTE]
> Bu konu, C++ standart kitaplıkta kullanılan C++ kapsayıcıların Işlevsel bir örneği olarak Microsoft belgelerimde yer almaktadır. Daha fazla bilgi için bkz [ C++ . standart kitaplık kapsayıcıları](../standard-library/stl-containers.md).

**\*Bu** ve bağımsız değişkeni arasındaki denetlenen dizileri değiştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Açıklamalar

Bu. **\*Get\_ayırıcısı = =** _Right_ **. get_allocator**, sabit bir zamanda takas yapar. Aksi takdirde, bir dizi öğe ataması ve Oluşturucu çağrısı, iki denetimli dizi içindeki öğe sayısıyla orantılı olarak gerçekleştirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)
