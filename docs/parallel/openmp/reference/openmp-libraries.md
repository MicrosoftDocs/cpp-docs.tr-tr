---
title: "OpenMP kitaplıkları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 760e7d138ab71244419ff71960948d4d10f125eb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="openmp-libraries"></a>OpenMP Kitaplıkları
Visual C++'ta OpenMP çalışma zamanı kitaplıkları oluşturan .lib dosyaları açıklanır.  
  
 Aşağıdaki kitaplıkları Visual C++ OpenMP çalışma zamanı kitaplığı işlevleri içerir.  
  
|OpenMP çalışma zamanı kitaplığı|Özellikler|  
|------------------------------|---------------------|  
|VCOMP. LIB|Birden çok iş parçacıklı, dinamik bağlantı (VCOMP için içeri aktarma kitaplığı. LIB).|  
|VCOMPD.LIB|Birden çok iş parçacıklı, dinamik bağlantı (VCOMPD için içeri aktarma kitaplığı. Kapak) (hata ayıklama)|  
  
 _DEBUG bir derlemede tanımlanan bulunuyorsa ve `#include omp.h` VCOMPD, kaynak kodu verilmiştir. LIB varsayılan lib olacaktır. Aksi takdirde VCOMP. LIB kullanılır.  
  
 Kullanabileceğiniz [/NODEFAULTLIB (kitaplıkları yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan lib kaldırmak ve tercih ettiğiniz lib ile açıkça bağlanmak için.  
  
 OpenMP DLL'leri Visual C++ yeniden dağıtılabilir dizinde bulunan ve OpenMP kullanan uygulamaları ile dağıtılması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)