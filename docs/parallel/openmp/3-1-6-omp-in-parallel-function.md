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
ms.openlocfilehash: 22b491695d2ae49336d7d8998af64e724f344d87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686288"
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel İşlevi
**Omp_in_parallel** işlevi paralel bölge yürütmenin paralel olarak dinamik kapsam içinde çağrıldıysa sıfır olmayan bir değer döndürür; Aksi halde 0 döndürür. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Bu işlev, bölge sıralanır iç içe geçmiş bölgeler dahil olmak üzere paralel olarak yürütülen içinde çağrılır, sıfır olmayan bir değer döndürür.