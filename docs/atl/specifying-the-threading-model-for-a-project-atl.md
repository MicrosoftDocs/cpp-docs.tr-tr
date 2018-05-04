---
title: Proje (ATL) için iş parçacığı modeline belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6f807aa82a62fb703430ace5bc6be516e08ca9dc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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

