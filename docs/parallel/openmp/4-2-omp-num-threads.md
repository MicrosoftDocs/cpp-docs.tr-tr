---
title: 4.2 OMP_NUM_THREADS | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b4208d7fe7d453dd1f701d820a85fce5cd68ba
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS
**OMP_NUM_THREADS** ortam değişkeni, bu sayı, açıkça çağırarak değiştirilmediği sürece yürütme sırasında kullanılacak iş parçacıklarının varsayılan sayısını ayarlar **omp_set_num_threads** kitaplığı yordamı veya açık bir tarafından **num_threads** yan tümcesi bir **paralel** yönergesi.  
  
 Değeri **OMP_NUM_THREADS** ortam değişkeni, pozitif bir tamsayı olmalıdır. İş parçacığı sayısını dinamik olarak ayarlamayı etkinleştirilip etkinleştirilmediği bağlı etkisini bağlıdır. Kuralları arasındaki etkileşimi hakkında kapsamlı bir kümesini için **OMP_NUM_THREADS** ortam değişken ve dinamik düzeltmesi iş parçacığı, 8 sayfasında bölüm 2.3 bakın.  
  
 İçin herhangi bir değer belirtilmişse **OMP_NUM_THREADS** ortam değişkeni veya belirtilen değer pozitif bir tamsayı değil veya değer en fazla iş parçacığı sayısından büyükse, sistem için destek, kullanılacak iş parçacığı sayısı uygulama tanımlı değil.  
  
 Örnek:  
  
```  
setenv OMP_NUM_THREADS 16  
```  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **num_threads** yan tümcesi, bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **omp_set_num_threads** işlev, bkz: [bölüm 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) sayfasında 36.  
  
-   **omp_set_dynamic** işlev, bkz: [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.