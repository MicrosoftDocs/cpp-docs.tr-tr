---
title: 2.6.6 ordered Yapı
ms.date: 11/04/2016
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
ms.openlocfilehash: fe6ad4adf2a4fcccfefe3c3585d9c88c0a118931
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615806"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered Yapı

Yapısal bloğunun aşağıdaki bir **sıralı** yönergesi, yinelemeler yürütülebilir bir sıralı döngüde sırayla yürütülür. Söz dizimi **sıralı** yönerge aşağıdaki gibidir:

```
#pragma omp ordered new-linestructured-block
```

Bir **sıralı** yönergesi içinde dinamik kapsamı olmalıdır bir **için** veya **için paralel** oluşturun. **İçin** veya **için paralel** hangi yönerge **sıralı** yapısı bağlamalar olmalıdır bir **sıralı** açıklandığı belirtilen yan tümcesi [Bölümü 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11. Yürütülmesi bir **için** veya **için paralel** ile oluşturmak bir **sıralı** yan tümcesi **sıralı** yapıları kesinlikle içinde çalıştırılır sıra, bunlar döngünün bir sıralı yürütme yürütüldüğü.

Kısıtlamaları **sıralı** yönerge aşağıdaki gibidir:

- Yineleme döngüsü ile bir **için** yapısı gerekir değil yürütün aynı ordered yönergesi birden çok kez ve onu birden fazla yürütmeli değil **sıralı** yönergesi.