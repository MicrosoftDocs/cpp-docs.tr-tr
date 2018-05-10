---
title: 2.9 yönerge iç içe geçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 28e690ba531b4b37973bc2555d904317181ff918
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="29-directive-nesting"></a>2.9 Yönerge İç İçe Koyma
Dinamik iç içe geçmiş yönergeleri aşağıdaki kurallara uymalıdır:  
  
-   A **paralel** dinamik olarak iç yönerge **paralel** mantıksal olarak yalnızca geçerli iş parçacığının oluşur, yeni bir ekip paralellik iç içe geçmiş sürece etkin oluşturur.  
  
-   **için**, **bölümleri**, ve **tek** aynı bağlama yönergeleri **paralel** diğer içinde iç içe geçmiş izin verilmiyor.  
  
-   **Kritik** yönergeleri aynı ada sahip başka içinde iç içe geçmiş izin verilmez. Bu kısıtlama kilitlenmeyi önlemek için yeterli olmadığını unutmayın.  
  
-   **için**, **bölümleri**, ve **tek** yönergeleri dinamik kapsamını içinde izin verilmez **kritik**, **sıralı**, ve **ana** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.  
  
-   **engel** yönergeleri dinamik kapsamını içinde izin verilmez **için**, **sıralı**, **bölümleri**, **tek**, **ana**, ve **kritik** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.  
  
-   **Ana** yönergeleri dinamik kapsamını içinde izin verilmez **için**, **bölümleri**, ve **tek** yönergeleri, **ana** yönergeleri bağlamak için aynı **paralel** iş paylaşım yönergeleri olarak.  
  
-   **Sıralı** yönergeleri dinamik kapsamını içinde izin verilmez **kritik** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.  
  
-   Dinamik olarak paralel bir bölge içinde çalıştırıldığında izin yönergesi de paralel bölgesinin dışındaki çalıştırıldığında izin verilir. Bir kullanıcı tarafından belirtilen paralel bölgesinin dışındaki dinamik olarak çalıştırıldığında, yönergesi yalnızca ana iş parçacığı oluşan bir ekibin yürütülür.