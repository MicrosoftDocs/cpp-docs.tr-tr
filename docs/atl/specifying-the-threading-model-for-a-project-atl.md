---
title: "Proje (ATL) için iş parçacığı modeline belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4c115b326d2cdfe82a0466461bd378fd1b4be80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Proje İçin İş Parçacıklı Model Belirtme (ATL)
ATL projesinde iş parçacığı modeli belirtmek aşağıdaki makroları kullanılabilir:  
  
|Makrosu|Kullanma için yönergeler|  
|-----------|--------------------------|  
|_ATL_SINGLE_THREADED|Tüm nesnelerinin tek iş parçacığı modelini kullandıysanız tanımlayın.|  
|_ATL_APARTMENT_THREADED|Bir veya daha fazla nesnelerinizi Apartman iş parçacığı oluşturma kullanırsanız tanımlayın.|  
|_ATL_FREE_THREADED|Bir veya daha fazla nesnelerinizi boş veya nötr iş parçacığı oluşturma kullanırsanız tanımlayın. Var olan kodu eşdeğer makrosu başvurular içerebilir [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|  
  
 Projeniz için bu makroları hiçbirini tanımlamıyorsa _ATL_FREE_THREADED uygulanmaz.  
  
 Makrolar gibi çalışma zamanı performansı etkiler:  
  
-   Projenizdeki nesnelere karşılık gelen makrosu belirterek çalışma zamanı performansını iyileştirebilir.  
  
-   Tümü nesnelerinizi akıtılan, tek olduğunda _ATL_APARTMENT_THREADED belirtirseniz, örneğin makrosu daha yüksek düzeyde belirtme biraz çalışma zamanı performansının düşmesine neden.  
  
-   _Atl_sıngle_threaded biri belirlerseniz veya nesnelerinin daha fazla Grup iş parçacığı oluşturma ya da boş iş parçacığı oluşturma, kullanırsanız, makrosu, örneğin, alt düzey belirtme, uygulamanızın çalışma zamanında başarısız olmasına neden olabilir.  
  
 Bkz: [seçenekleri, ATL Basit Nesne Sihirbazı](../atl/reference/options-atl-simple-object-wizard.md) iş parçacığı için bir açıklama modeller ATL nesne için kullanılabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../atl/active-template-library-atl-concepts.md)

