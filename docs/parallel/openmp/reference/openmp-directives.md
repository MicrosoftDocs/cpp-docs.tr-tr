---
title: OpenMP yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7421f397b39c6d26c2e60042b25f37277afa5fd
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33692200"
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri
OpenMP API çağrısında kullanılan yönergeleri bağlantılar sağlar.  
  
 Visual C++ aşağıdaki OpenMP yönergeleri destekler:  
  
|Yönergesi|Açıklama|  
|---------------|-----------------|  
|[atomic](../../../parallel/openmp/reference/atomic.md)|Belirleyen bir bellek konumundan otomatik olarak güncelleştirilir.|  
|[barrier](../../../parallel/openmp/reference/barrier.md)|Bir takım tüm iş parçacıkları eşitler; tüm iş parçacıklarının engel yürütme kadar tüm iş parçacıklarının engel duraklatın.|  
|[critical](../../../parallel/openmp/reference/critical.md)|Aynı anda bir iş parçacığında, kod yalnızca yürütülür belirtir.|  
|[Temizleme](../../../parallel/openmp/reference/flush-openmp.md)|Tüm iş parçacıklarının tüm paylaşılan nesneler için bellek aynı görünümünü olduğunu belirtir.|  
|[for](../../../parallel/openmp/reference/for-openmp.md)|Çalışmanın neden olan bir iş parçacıkları arasında bölünür için paralel bir bölge içinde döngü için.|  
|[master](../../../parallel/openmp/reference/master.md)|Yalnızca ana threadshould bir bölümünü program yürütme belirtir.|  
|[sıralı](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Döngü gibi sıralı bir döngü yürütülmesi için bu kodu bir parallelized altında belirtir.|  
|[parallel](../../../parallel/openmp/reference/parallel.md)|Paralel olarak birden çok iş parçacığı tarafından yürütülen kod bir paralel bölge tanımlar.|  
|[Bölümler](../../../parallel/openmp/reference/sections-openmp.md)|Tüm iş parçacıkları arasında bölünür için kod bölümleri tanımlar.|  
|[single](../../../parallel/openmp/reference/single.md)|Kodun bir bölümü, mutlaka ana iş parçacığı gibi tek bir iş üzerinde yürütülmesi gereken belirtmenize olanak sağlar.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Bir değişken için bir iş parçacığı özel olduğunu belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)