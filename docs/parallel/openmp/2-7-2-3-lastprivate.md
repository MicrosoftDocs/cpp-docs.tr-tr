---
title: 2.7.2.3 lastprivate
ms.date: 11/04/2016
ms.assetid: 77f6a5c9-704f-4a88-8476-29db852ed800
ms.openlocfilehash: 15f9af23c4f4e1c0ce2914a979f7a41e7b4a6bc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428469"
---
# <a name="2723-lastprivate"></a>2.7.2.3 lastprivate

`lastprivate` Yan tümcesi tarafından sağlanan bir işlevselliğin sağlar `private` yan tümcesi. Söz dizimi `lastprivate` yan tümcesi şu şekildedir:

```
lastprivate(variable-list)
```

Belirtilen değişkenler *değişken listesi* sahip `private` yan tümcesi semantiği. Olduğunda bir `lastprivate` yan tümcesi görünür değeri her bir iş paylaşımı yapısı tanımlayan yönergesinde `lastprivate` ilişkili döngü ya da sözcüksel olarak son bölüm yönergesi, sıralı olarak son yinelenmesinden değişkeninden atanır değişkenin özgün nesne. Olmayan değişkenleri atanmış bir değer tarafından son yinelemeyi **için** veya **için paralel**, veya sözcüksel olarak son Kısım **bölümleri** veya  **Paralel bölümleri** yönergesi, sonra yapısı belirsiz değerlere sahip olur. Atanmamış alt nesnelerinin, ayrıca sonra yapısı belirsiz bir değere sahip.

Kısıtlamaları `lastprivate` yan tümcesi aşağıdaki gibidir:

- İçin tüm kısıtlamalar `private` uygulayın.

- Bir değişken olarak belirtilen sınıf türüyle `lastprivate` bir erişilebilir, açık kopya atama işleci olması gerekir.

- Bir paralel bölgenin içinde özel olmayan veya, görünen değişkenleri `reduction` yan tümcesi bir **paralel** yönergesi belirtilemez bir `lastprivate` iş paylaşım için paralel yapı bağlayan bir yönerge yan tümcesi.