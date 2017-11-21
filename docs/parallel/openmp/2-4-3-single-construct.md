---
title: "2.4.3 tek yapı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3efb6c833227140440d327ea47906f8239769689
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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