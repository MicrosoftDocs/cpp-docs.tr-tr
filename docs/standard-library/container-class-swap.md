---
title: Kapsayıcı Sınıfı::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: b344747c42e9b8b751b97747aacec0b39d10d6a1
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221523"
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap

> [!NOTE]
> Bu konu Microsoft olan C++ kullanılan kapsayıcıları işlevsiz bir örnek olarak belgeleri C++ standart kitaplığı. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Denetlenen diziyi değiştirir  **\*bu** ve bağımsız değişkeni.

## <a name="syntax"></a>Sözdizimi

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Açıklamalar

Varsa  **\*this.get\_ayırıcı ==** _doğru_**.get_allocator**, bunu bir takas Sabit sürede gerçekleştirir. Aksi takdirde, bir dizi öğesi atamalar ve oluşturucu çağrıları öğelerin sayısını orantılı iki denetimli sıralarında gerçekleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)<br/>
