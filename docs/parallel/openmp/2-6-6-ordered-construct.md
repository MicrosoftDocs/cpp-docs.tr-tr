---
title: 2.6.6 ordered yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 5b3c1ba5-cfb8-4b05-865b-f446ae1c9f7c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b83c3dfc13b231a1314343a1dff496acf7a99b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412203"
---
# <a name="266-ordered-construct"></a>2.6.6 ordered Yapı

Yapısal bloğunun aşağıdaki bir **sıralı** yönergesi, yinelemeler yürütülebilir bir sıralı döngüde sırayla yürütülür. Söz dizimi **sıralı** yönerge aşağıdaki gibidir:

```
#pragma omp ordered new-linestructured-block
```

Bir **sıralı** yönergesi içinde dinamik kapsamı olmalıdır bir **için** veya **için paralel** oluşturun. **İçin** veya **için paralel** hangi yönerge **sıralı** yapısı bağlamalar olmalıdır bir **sıralı** açıklandığı belirtilen yan tümcesi [Bölümü 2.4.1](../../parallel/openmp/2-4-1-for-construct.md) sayfasında 11. Yürütülmesi bir **için** veya **için paralel** ile oluşturmak bir **sıralı** yan tümcesi **sıralı** yapıları kesinlikle içinde çalıştırılır sıra, bunlar döngünün bir sıralı yürütme yürütüldüğü.

Kısıtlamaları **sıralı** yönerge aşağıdaki gibidir:

- Yineleme döngüsü ile bir **için** yapısı gerekir değil yürütün aynı ordered yönergesi birden çok kez ve onu birden fazla yürütmeli değil **sıralı** yönergesi.