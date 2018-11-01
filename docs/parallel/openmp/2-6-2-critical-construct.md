---
title: 2.6.2 critical Yapı
ms.date: 11/04/2016
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
ms.openlocfilehash: dcc0e6144be5daee2a225cda621db818e5a38e2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539080"
---
# <a name="262-critical-construct"></a>2.6.2 critical Yapı

**Kritik** yönergesi ilişkili yapısal bloğunun yürütülmesi için tek bir iş parçacığı aynı anda kısıtlayan bir yapı tanımlar. Söz dizimi **kritik** yönerge aşağıdaki gibidir:

```
#pragma omp critical [(name)]  new-linestructured-block
```

İsteğe bağlı *adı* kritik bölge tanımlamak için kullanılabilir. Kritik bir bölge tanımlamak için kullanılan tanımlayıcıları dış bağlantısı vardır ve etiketler, etiketler, üyeleri ve sıradan tanımlayıcıları tarafından kullanılan ad alanları'ndan ayrı bir ad alanı bulunan.

Bir iş parçacığı bir kritik bölgede (herhangi bir yere program) aynı ada sahip başka bir iş parçacığı yürütülmekte olan kritik bir bölge başında bekler. Adlandırılmamış tüm **kritik** yönergeleri aynı belirtilmeyen adına eşleyin.