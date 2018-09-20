---
title: 2.6.2 critical yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e51bd425999081c7a06a7d5692dbea16c887fa0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417858"
---
# <a name="262-critical-construct"></a>2.6.2 critical Yapı

**Kritik** yönergesi ilişkili yapısal bloğunun yürütülmesi için tek bir iş parçacığı aynı anda kısıtlayan bir yapı tanımlar. Söz dizimi **kritik** yönerge aşağıdaki gibidir:

```
#pragma omp critical [(name)]  new-linestructured-block
```

İsteğe bağlı *adı* kritik bölge tanımlamak için kullanılabilir. Kritik bir bölge tanımlamak için kullanılan tanımlayıcıları dış bağlantısı vardır ve etiketler, etiketler, üyeleri ve sıradan tanımlayıcıları tarafından kullanılan ad alanları'ndan ayrı bir ad alanı bulunan.

Bir iş parçacığı bir kritik bölgede (herhangi bir yere program) aynı ada sahip başka bir iş parçacığı yürütülmekte olan kritik bir bölge başında bekler. Adlandırılmamış tüm **kritik** yönergeleri aynı belirtilmeyen adına eşleyin.