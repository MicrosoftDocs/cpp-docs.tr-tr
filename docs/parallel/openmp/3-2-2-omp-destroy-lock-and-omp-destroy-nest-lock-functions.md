---
title: 3.2.2 omp_destroy_lock ve omp_destroy_nest_lock işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: d334907d-94f7-4bbf-b20e-41d53484cbff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7b762614e406e5fb4497ec901ad8f65dae15a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433882"
---
# <a name="322-ompdestroylock-and-ompdestroynestlock-functions"></a>3.2.2 omp_destroy_lock ve omp_destroy_nest_lock İşlevleri

Bu işlevler işaret kilit değişkenine emin *kilit* başlatılmadı. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
void omp_destroy_lock(omp_lock_t *lock);
void omp_destroy_nest_lock(omp_nest_lock_t *lock);
```

Çağırın ya da bu yordamların başlatılmamış veya kilidinin kilit değişken ile uyumsuzdur.