---
title: "2.9 yönerge iç içe geçme | Microsoft Docs"
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
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd3c4f790681b1b044f435c03d185585b565eb62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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