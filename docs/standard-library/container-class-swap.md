---
title: Kapsayıcı Sınıfı::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: 2c2b87e8cc51248fd3d29df7f361fff92da72957
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62210850"
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap

> [!NOTE]
> Bu konuda C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsiz bir örnek olarak Visual C++ belgelerinin bulunduğu. Daha fazla bilgi için [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Denetlenen diziyi değiştirir  **\*bu** ve bağımsız değişkeni.

## <a name="syntax"></a>Sözdizimi

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Açıklamalar

Varsa  **\*this.get\_ayırıcı ==** _doğru_**.get_allocator**, bunu bir takas Sabit sürede gerçekleştirir. Aksi takdirde, bir dizi öğesi atamalar ve oluşturucu çağrıları öğelerin sayısını orantılı iki denetimli sıralarında gerçekleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)<br/>
