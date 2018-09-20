---
title: 2.6.1 master yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c092064b-ea57-4d4e-9c99-a004d65656fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8d82ae673e428c635172f35f9b0f682aa65dc2b8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46445639"
---
# <a name="261-master-construct"></a>2.6.1 master Yapı

**Ana** yönergesi takım ana iş parçacığı tarafından yürütülen bir yapısal bloğunun belirten bir yapı tanımlar. Söz dizimi **ana** yönerge aşağıdaki gibidir:

```
#pragma omp master new-linestructured-block
```

Takımın diğer iş parçacıkları ilişkili yapısal bloğunun yürütülmez. Giriş veya çıkış master yapı'zımni hiçbir engel yok.