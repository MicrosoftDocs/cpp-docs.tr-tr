---
title: 3.1.9 omp_set_nested işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e4afc3aa-bb96-4314-9849-fd5df5f437d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df08d6eb1a93ff5852c239757d5f917e9777919b
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687289"
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