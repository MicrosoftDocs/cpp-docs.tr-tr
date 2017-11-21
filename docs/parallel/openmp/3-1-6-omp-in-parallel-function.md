---
title: "3.1.6 omp_in_parallel işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: db6e3a63-2a0a-4b8e-8cc6-c6b49edca5fb
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b72351095fd56ae6543c2ca742983eef315f2158
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="316-ompinparallel-function"></a>3.1.6 omp_in_parallel İşlevi
**Omp_in_parallel** işlevi paralel bölge yürütmenin paralel olarak dinamik kapsam içinde çağrıldıysa sıfır olmayan bir değer döndürür; Aksi halde 0 döndürür. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_in_parallel(void);  
```  
  
 Bu işlev, bölge sıralanır iç içe geçmiş bölgeler dahil olmak üzere paralel olarak yürütülen içinde çağrılır, sıfır olmayan bir değer döndürür.