---
title: "3.1.6 omp_in_parallel işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e5d05af81eb112894ca27a7599c271138893ee1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel İşlevi
**Omp_in_parallel** işlevi paralel bölge yürütmenin paralel olarak dinamik kapsam içinde çağrıldıysa sıfır olmayan bir değer döndürür; Aksi halde 0 döndürür. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Bu işlev, bölge sıralanır iç içe geçmiş bölgeler dahil olmak üzere paralel olarak yürütülen içinde çağrılır, sıfır olmayan bir değer döndürür.