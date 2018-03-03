---
title: "2.6.2 critical yapı | Microsoft Docs"
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
ms.assetid: c46ecd00-b4a2-4a5e-ba92-288c329e773a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c658b32536404dde1a693582e78bfbedc2823b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="262-critical-construct"></a>2.6.2 critical Yapı
**Kritik** yönergesi ilişkili yapılandırılmış blok yürütülmesi için tek bir iş parçacığı aynı anda kısıtlayan bir yapı tanımlar. Söz dizimi **kritik** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp critical [(name)]  new-linestructured-block  
```  
  
 İsteğe bağlı bir *adı* kritik bölge tanımlamak için kullanılabilir. Kritik bir bölge tanımlamak için kullanılan tanımlayıcıları dış bağlantı varsa ve etiketleri, etiketler, üyeleri ve sıradan tanımlayıcıları tarafından kullanılan ad alanları ayrı olan bir ad alanında.  
  
 Bir iş parçacığı bir kritik bölgede (herhangi bir yere programı) aynı ada sahip başka bir iş parçacığı yürütüyor kritik bir bölge başında bekler. Adlandırılmamış tüm **kritik** yönergeleri aynı belirtilmeyen adına eşleyin.