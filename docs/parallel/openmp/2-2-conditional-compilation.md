---
title: 2.2 koşullu derleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b3d8c7073548c015d9982b721387176a0ca658c2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="22-conditional-compilation"></a>2.2 Koşullu Derleme
_**OPENMP** makrosu adı OpenMP uyumlu uygulamaları tarafından ondalık sabit olarak tanımlanmış *yyyymm*, yıl ve ay onaylanan belirtimi olacak. Bu makrosu konusunun olmamalıdır bir **#define** veya **#undef** önişlem yönergesi.  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 Satıcılar için OpenMP uzantıları tanımlarsanız, ek önceden tanımlı makrolar belirtmiş olabilir.