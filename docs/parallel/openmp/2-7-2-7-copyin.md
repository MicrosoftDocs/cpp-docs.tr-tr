---
title: 2.7.2.7 copyin
ms.date: 11/04/2016
ms.assetid: 76cfb9f8-bf65-4585-adbf-fd933f5606b4
ms.openlocfilehash: 20db32530ee60967245497cdfb12a0fce103f7b7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519535"
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