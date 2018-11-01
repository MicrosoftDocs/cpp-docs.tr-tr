---
title: 2.6.1 master Yapı
ms.date: 11/04/2016
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
ms.openlocfilehash: 0501b1fdfbd36829cee2793fc0f7bb03daeda900
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475536"
---
# <a name="261-master-construct"></a>2.6.1 master Yapı

**Ana** yönergesi takım ana iş parçacığı tarafından yürütülen bir yapısal bloğunun belirten bir yapı tanımlar. Söz dizimi **ana** yönerge aşağıdaki gibidir:

```
#pragma omp master new-linestructured-block
```

Takımın diğer iş parçacıkları ilişkili yapısal bloğunun yürütülmez. Giriş veya çıkış master yapı'zımni hiçbir engel yok.