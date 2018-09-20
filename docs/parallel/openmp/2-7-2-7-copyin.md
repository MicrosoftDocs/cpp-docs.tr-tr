---
title: 2.7.2.7 copyin | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 94b4c529b7ad6fd717be1e1dee0edd3ff9ac3ff5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426893"
---
# <a name="2727-copyin"></a>2.7.2.7 copyin

**Copyin** yan tümcesi için aynı değer atamak için bir mekanizma sağlar **threadprivate** paralel bölgenin yürütme takım içindeki her iş parçacığı için değişkenleri. Belirtilen her bir değişken için bir **copyin** yan tümcesi, takımın ana iş parçacığında bir değişkenin değerini kopyalanır, atama gibi paralel bölge başına iş parçacığı özel kopya tarafından. Söz dizimi **copyin** yan tümcesi şu şekildedir:

```

copyin(
variable-list
)

```

Kısıtlamaları **copyin** yan tümcesi aşağıdaki gibidir:

- Belirtilen değişken **copyin** yan tümcesi bir erişilebilir, açık kopya atama işleci olması gerekir.

- Belirtilen değişken **copyin** yan tümcesi olmalıdır bir **threadprivate** değişkeni.