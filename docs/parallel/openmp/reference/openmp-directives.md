---
title: "OpenMP yönergeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21cb751c4ee4c261db1d6a4d5efda49a1445ade7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri
OpenMP API çağrısında kullanılan yönergeleri bağlantılar sağlar.  
  
 Visual C++ aşağıdaki OpenMP yönergeleri destekler:  
  
|Yönergesi|Açıklama|  
|---------------|-----------------|  
|[Atomik](../../../parallel/openmp/reference/atomic.md)|Belirleyen bir bellek konumundan otomatik olarak güncelleştirilir.|  
|[engelle](../../../parallel/openmp/reference/barrier.md)|Bir takım tüm iş parçacıkları eşitler; tüm iş parçacıklarının engel yürütme kadar tüm iş parçacıklarının engel duraklatın.|  
|[Kritik](../../../parallel/openmp/reference/critical.md)|Aynı anda bir iş parçacığında, kod yalnızca yürütülür belirtir.|  
|[Temizleme](../../../parallel/openmp/reference/flush-openmp.md)|Tüm iş parçacıklarının tüm paylaşılan nesneler için bellek aynı görünümünü olduğunu belirtir.|  
|[için](../../../parallel/openmp/reference/for-openmp.md)|Çalışmanın neden olan bir iş parçacıkları arasında bölünür için paralel bir bölge içinde döngü için.|  
|[Ana](../../../parallel/openmp/reference/master.md)|Yalnızca ana threadshould bir bölümünü program yürütme belirtir.|  
|[sıralı](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Döngü gibi sıralı bir döngü yürütülmesi için bu kodu bir parallelized altında belirtir.|  
|[Paralel](../../../parallel/openmp/reference/parallel.md)|Paralel olarak birden çok iş parçacığı tarafından yürütülen kod bir paralel bölge tanımlar.|  
|[bölümler](../../../parallel/openmp/reference/sections-openmp.md)|Tüm iş parçacıkları arasında bölünür için kod bölümleri tanımlar.|  
|[tek](../../../parallel/openmp/reference/single.md)|Kodun bir bölümü, mutlaka ana iş parçacığı gibi tek bir iş üzerinde yürütülmesi gereken belirtmenize olanak sağlar.|  
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Bir değişken için bir iş parçacığı özel olduğunu belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Yan tümceleri](../../../parallel/openmp/reference/openmp-clauses.md)