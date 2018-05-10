---
title: 2.4.3 tek yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: db3f9ca834fb3f35c95732698fd02e16f31b4225
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="243-single-construct"></a>2.4.3 single Yapı
**Tek** yönergesi ilişkili yapılandırılmış blok (mutlaka ana iş parçacığı) ekibin yalnızca bir iş parçacığı tarafından yürütülür belirleyen bir yapısı tanımlar. Söz dizimi **tek** yönergesi aşağıdaki gibidir:  
  
```  
#pragma omp single [clause[[,] clause] ...] new-linestructured-block  
```  
  
 Yan tümcesi aşağıdakilerden biridir:  
  
 **Özel (** *değişken listesi* **)**  
  
 **firstprivate (** *değişken listesi* **)**  
  
 **copyprivate (** *değişken listesi* **)**  
  
 **nowait**  
  
 Sonra örtük bir engel yok **tek** sürece oluşturmak bir **nowait** yan tümcesi belirtilir.  
  
 Kısıtlamaları **tek** yönergesi aşağıdaki gibidir:  
  
-   Yalnızca tek bir **nowait** yan tümcesi görünebilir bir **tek** yönergesi.  
  
-   **Copyprivate** yan tümcesi değil kullanılmalıdır **nowait** yan tümcesi.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   **özel**, **firstprivate**, ve **copyprivate** yan tümceleri, bkz: [bölüm 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.