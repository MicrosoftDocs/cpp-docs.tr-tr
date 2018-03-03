---
title: "3.1.9 omp_set_nested işlevi | Microsoft Docs"
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
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0910e7df0ebd423b9967fd0eb7931b7434ba94fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="319-ompsetnested-function"></a>3.1.9 omp_set_nested İşlevi
**Omp_set_nested** işlevini etkinleştirir veya iç içe geçmiş paralellik devre dışı bırakır. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
void omp_set_nested(int nested);  
```  
  
 Varsa *iç içe geçmiş* iç içe geçmiş 0 olarak değerlendirir paralellik devre dışıysa, varsayılan olan ve iç içe geçmiş paralel bölgeler serileştirilmiş ve geçerli iş parçacığı tarafından yürütülen. Varsa *iç içe geçmiş* değerlendirir sıfır olmayan bir değere iç içe geçmiş paralellik etkin ve iç içe paralel bölgeler iç içe geçmiş takımlar oluşturmak için ek iş parçacığı dağıtmak.  
  
 Bu işlev bir program bölümünden çağrıldığında yukarıda açıklanan etkilere sahiptir nerede **omp_in_parallel** işlevi sıfır döndürür. Program bir kısmına çağrılıp çağrılmayacağını nerede **omp_in_parallel** işlevi sıfır olmayan bir değer döndürür, bu işlevin davranışı tanımlı değil.  
  
 Bu çağrı üzerinden önceliğe sahip **OMP_NESTED** ortam değişkeni.  
  
 İç içe geçmiş paralellik etkinleştirildiğinde, uygulama tanımlı paralel iç içe geçmiş bölgeler yürütmek için kullanılan iş parçacıklarının sayısı. Sonuç olarak, OpenMP uyumlu uygulamaları, iç içe geçmiş paralellik etkin olsa bile paralel iç içe geçmiş bölgeler serileştirmek için izin verilir.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **OMP_NESTED** ortam değişkeni, bkz: [bölüm 4.4](../../parallel/openmp/4-4-omp-nested.md) sayfasında 49.  
  
-   **omp_in_parallel** işlev, bkz: [bölüm 3.1.6](../../parallel/openmp/3-1-6-omp-in-parallel-function.md) sayfasında 38.