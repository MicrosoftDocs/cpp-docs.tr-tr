---
title: OpenMP kitaplıkları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: f89abf97-67e3-4327-bc30-43f85b9533a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 46bd287ff8a020a4d5d7775afdb12f5571d43294
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="openmp-libraries"></a>OpenMP Kitaplıkları
Visual C++'ta OpenMP çalışma zamanı kitaplıkları oluşturan .lib dosyaları açıklanır.  
  
 Aşağıdaki kitaplıkları Visual C++ OpenMP çalışma zamanı kitaplığı işlevleri içerir.  
  
|OpenMP çalışma zamanı kitaplığı|Özellikler|  
|------------------------------|---------------------|  
|VCOMP. LIB|Birden çok iş parçacıklı, dinamik bağlantı (VCOMP için içeri aktarma kitaplığı. LIB).|  
|VCOMPD. LIB|Birden çok iş parçacıklı, dinamik bağlantı (VCOMPD için içeri aktarma kitaplığı. Kapak) (hata ayıklama)|  
  
 _DEBUG bir derlemede tanımlanan bulunuyorsa ve `#include omp.h` VCOMPD, kaynak kodu verilmiştir. LIB varsayılan lib olacaktır. Aksi takdirde VCOMP. LIB kullanılır.  
  
 Kullanabileceğiniz [/NODEFAULTLIB (kitaplıkları yoksay)](../../../build/reference/nodefaultlib-ignore-libraries.md) varsayılan lib kaldırmak ve tercih ettiğiniz lib ile açıkça bağlanmak için.  
  
 OpenMP DLL'leri Visual C++ yeniden dağıtılabilir dizinde bulunan ve OpenMP kullanan uygulamaları ile dağıtılması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kitaplık Başvurusu](../../../parallel/openmp/reference/openmp-library-reference.md)