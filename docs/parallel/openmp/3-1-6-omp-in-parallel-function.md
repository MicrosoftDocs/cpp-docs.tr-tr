---
title: 3.1.6 omp_in_parallel işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9ba6c35d42f8497869894bd5ec95b83f0c8793f1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404624"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel İşlevi

**Omp_in_parallel** işlevi dinamik kapsam, paralel olarak yürütülen bir paralel bölgenin içinde çağrılırsa sıfır olmayan bir değer döndürür; Aksi takdirde 0 değerini döndürür. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_in_parallel(void);
```

Bu işlev bir bölge serileştirilme şeklini iç içe geçmiş bölge dahil paralel olarak yürütülen'içinde çağrılır, sıfır olmayan bir değer döndürür.