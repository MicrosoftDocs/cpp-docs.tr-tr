---
title: Kapsayıcı sınıfı::Swap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6691b8ee8471ebf0e8edc8f1513d0229193a4a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="container-classswap"></a>Kapsayıcı Sınıfı::swap

> [!NOTE]
> Bu konu, Visual C++ belge C++ Standart Kitaplığı'nda kullanılan kapsayıcıları işlevsel bir örnek olarak kullanılıyor. Daha fazla bilgi için bkz: [C++ Standart Kitaplığı kapsayıcıları](../standard-library/stl-containers.md).

Denetimli sıraları arasında değiştirir  **\*bu** ve bağımsız değişkeni.

## <a name="syntax"></a>Sözdizimi

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Açıklamalar

Varsa  **\*this.get\_ayırıcısı ==** _sağ_**.get_allocator**, bunu bir takas Sabit sürede yapar. Aksi durumda, iki denetimli sıralarında öğesi atamaları ve oluşturucu çağrıları öğe sayısını orantılı çeşitli gerçekleştirir.

## <a name="see-also"></a>Ayrıca bkz.

[Örnek Kapsayıcı Sınıfı](../standard-library/sample-container-class.md)<br/>
