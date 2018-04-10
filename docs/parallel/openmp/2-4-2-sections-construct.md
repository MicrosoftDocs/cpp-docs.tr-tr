---
title: 2.4.2 sections yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6e5b755e95e9bbbb78d6ab13cd09732f9c9aee3d
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/10/2018
---
# <a name="242-sections-construct"></a>2.4.2 sections Yapı
**Bölümleri** yönergesi takım iş parçacıkları arasında bölünür üzeresiniz yapıları kümesini belirten bir noniterative iş paylaşım yapısını tanımlar. Her bölümü takım bir iş parçacığı tarafından bir kez çalıştırılır. Söz dizimi **bölümleri** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp sections [clause[[,] clause] ...] new-line  
   {  
   [#pragma omp section new-line]  
      structured-block  
   [#pragma omp section new-linestructured-block ]  
...  
}  
```  
  
 Yan tümcesi aşağıdakilerden biridir:  
  
 **Özel (** *değişken listesi* **)**  
  
 **firstprivate (** *değişken listesi* **)**  
  
 **lastprivate (** *değişken listesi* **)**  
  
 **azaltma (** *işleci* **:***değişken listesi* **)**   
  
 **nowait**  
  
 Her bölüm öncesinde bir **bölüm** yönergesi, ancak **bölüm** yönergesi ilk bölümü için isteğe bağlı. **Bölüm** yönergeleri içinde sözcük kapsamını görünmelidir **bölümleri** yönergesi. Sonunda örtük bir engel olan bir **bölümleri** sürece oluşturmak bir **nowait** belirtilir.  
  
 Kısıtlamaları **bölümleri** yönergesi aşağıdaki gibidir:  
  
-   A **bölüm** yönergesi gerekir görünmüyor sözcük kapsamını dışında **bölümleri** yönergesi.  
  
-   Yalnızca tek bir **nowait** yan tümcesi görünebilir bir **bölümleri** yönergesi.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **özel**, **firstprivate**, **lastprivate**, ve **azaltma** yan tümceleri, bkz: [bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.