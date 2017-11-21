---
title: "2.2 koşullu derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ddfb754e3aa4142b6d070f2b5fe20ac7a63512e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="22-conditional-compilation"></a>2.2 Koşullu Derleme
_**OPENMP** makrosu adı OpenMP uyumlu uygulamaları tarafından ondalık sabit olarak tanımlanmış *yyyymm*, yıl ve ay onaylanan belirtimi olacak. Bu makrosu konusunun olmamalıdır bir **#define** veya **#undef** önişlem yönergesi.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Satıcılar için OpenMP uzantıları tanımlarsanız, ek önceden tanımlı makrolar belirtmiş olabilir.