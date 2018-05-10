---
title: 2.6.2 critical yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae7070fcc590307e71b0c34259bcbe1c12200550
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="262-critical-construct"></a>2.6.2 critical Yapı
**Kritik** yönergesi ilişkili yapılandırılmış blok yürütülmesi için tek bir iş parçacığı aynı anda kısıtlayan bir yapı tanımlar. Söz dizimi **kritik** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 İsteğe bağlı bir *adı* kritik bölge tanımlamak için kullanılabilir. Kritik bir bölge tanımlamak için kullanılan tanımlayıcıları dış bağlantı varsa ve etiketleri, etiketler, üyeleri ve sıradan tanımlayıcıları tarafından kullanılan ad alanları ayrı olan bir ad alanında.  
  
 Bir iş parçacığı bir kritik bölgede (herhangi bir yere programı) aynı ada sahip başka bir iş parçacığı yürütüyor kritik bir bölge başında bekler. Adlandırılmamış tüm **kritik** yönergeleri aynı belirtilmeyen adına eşleyin.