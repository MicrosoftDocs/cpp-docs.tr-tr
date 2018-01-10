---
title: "3.2 kilit işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 151c809a7bd28a2e4384371f5cec3bd192eed9d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="32-lock-functions"></a>3.2 Kilit İşlevleri
Bu bölümde açıklanan işlevleri eşitleme için kullanılan kilitleri yönetme.  
  
 Aşağıdaki işlevleri için kilit değişken türü olmalıdır **omp_lock_t**. Bu değişken yalnızca bu işlevler erişilmesi gerekir. Tüm kilit işlevleri için bir işaretçi sahip bağımsız değişken gerektirir **omp_lock_t** türü.  
  
-   `omp_init_lock` İşlevi basit bir kilit başlatır.  
  
-   `omp_destroy_lock` İşlevi basit bir kilidi kaldırır.  
  
-   `omp_set_lock` İşlevi, basit bir kilit kullanılabilir oluncaya kadar bekler.  
  
-   `omp_unset_lock` İşlevi basit bir kilidi serbest bırakır.  
  
-   `omp_test_lock` İşlevi basit bir kilit sınar.  
  
 Aşağıdaki işlevleri için kilit değişken türü olmalıdır **omp_nest_lock_t**.  Bu değişken yalnızca bu işlevler erişilmesi gerekir. Tüm nestable kilit işlevleri için bir işaretçi sahip bağımsız değişken gerektirir **omp_nest_lock_t** türü.  
  
-   `omp_init_nest_lock` İşlevi nestable kilit başlatır.  
  
-   `omp_destroy_nest_lock` İşlevi nestable kilit kaldırır.  
  
-   `omp_set_nest_lock` İşlevi nestable kilit kullanılabilir oluncaya kadar bekler.  
  
-   `omp_unset_nest_lock` İşlevi nestable kilidi serbest bırakır.  
  
-   `omp_test_nest_lock` İşlevi nestable kilit sınar.  
  
 OpenMP kilit işlevleri bunlar her zaman okuma ve en güncel değişkenin değeri olarak kilit güncelleştirme olduğunu şekilde kilit değişkeninde erişin. Bu nedenle, bir OpenMP program açık dahil etmek gerekli değildir **flush** yönergeleri kilit değişkenin değeri farklı iş parçacıkları arasında tutarlı olduğundan emin olun. (Bir gereksinimini olabilir **flush** diğer değişkenlerin değerleri tutarlı hale getirmek için yönergeleri.)