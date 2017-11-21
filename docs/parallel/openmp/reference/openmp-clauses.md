---
title: "OpenMP yan tümceleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 806e7d8f-b204-4e4c-a12c-273ab540a7ca
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4de0ac69733bee42d4102edf345f69be2e5fea3f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="openmp-clauses"></a>OpenMP Yan Tümceleri
OpenMP API çağrısında kullanılan yan tümceleri bağlantılar sağlar.  
  
 Visual C++ aşağıdaki OpenMP yan tümceleri destekler:  
  
|Yan Tümce|Açıklama|  
|------------|-----------------|  
|[copyin](../../../parallel/openmp/reference/copyin.md)|Ana iş parçacığının değeri erişmek iş parçacığı sağlayan bir [threadprivate](../../../parallel/openmp/reference/threadprivate.md) değişkeni.|  
|[copyprivate](../../../parallel/openmp/reference/copyprivate.md)|Bir veya daha fazla değişken tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.|  
|[Varsayılan](../../../parallel/openmp/reference/default-openmp.md)|Paralel bir bölgede dizininden kapsam dışı değişkenleri davranışını belirtir.|  
|[firstprivate](../../../parallel/openmp/reference/firstprivate.md)|Paralel yapı önce mevcut olduğundan her iş parçacığı bir değişken örneğini olmalıdır ve değişkeni değişken değeri ile başlatılmış olduğunu belirtir.|  
|[Eğer](../../../parallel/openmp/reference/if-openmp.md)|Döngü paralel veya seri gerçekleştirilip gerçekleştirilmeyeceğini belirtir.|  
|[lastprivate](../../../parallel/openmp/reference/lastprivate.md)|Değişkeni kapsayan bağlamın sürümünü son yineleme (döngü için yapı) ya da son Kısım (#pragma bölümleri) hangi iş parçacığı yürütür özel sürümü için eşit olarak ayarlanır belirtir.|  
|[nowait](../../../parallel/openmp/reference/nowait.md)|Bir yönerge örtük engel geçersiz kılar.|  
|[num_threads](../../../parallel/openmp/reference/num-threads.md)|İş parçacığı sayısı, iş parçacığı ekip olarak ayarlar.|  
|[sıralı](../../../parallel/openmp/reference/ordered-openmp-clauses.md)|Üzerinde bir paralel gerekli [için](../../../parallel/openmp/reference/for-openmp.md) deyimi, bir [sıralı](../../../parallel/openmp/reference/ordered-openmp-directives.md) yönergesi olup döngüde kullanılacak.|  
|[Özel](../../../parallel/openmp/reference/private-openmp.md)|Her iş parçacığı bir değişken örneğini olması gerektiğini belirtir.|  
|[Azaltma](../../../parallel/openmp/reference/reduction.md)|Her iş parçacığı için özel bir veya daha fazla değişken azaltma işlemi paralel bölge sonundaki konu olduğunu belirtir.|  
|[zamanlama](../../../parallel/openmp/reference/schedule.md)|Uygulandığı öğe [için](../../../parallel/openmp/reference/for-openmp.md) yönergesi.|  
|[Paylaşılan](../../../parallel/openmp/reference/shared-openmp.md)|Bir veya daha fazla değişken tüm iş parçacıkları arasında paylaşılan olduğunu belirtir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)   
 [Yönergeleri](../../../parallel/openmp/reference/openmp-directives.md)