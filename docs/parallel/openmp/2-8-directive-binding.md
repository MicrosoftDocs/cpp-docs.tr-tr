---
title: "2.8 yönerge bağlama | Microsoft Docs"
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
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 731c509c0c2f300d7a9d4e39261ffedd1c22a094
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="28-directive-binding"></a>2.8 Yönerge Bağlama
Dinamik bağlama yönergeleri aşağıdaki kurallara uymalıdır:  
  
-   **İçin**, **bölümleri**, **tek**, **ana**, ve **engel** yönergeleri bağlamak için dinamik olarak kapsayan **paralel**, bir bağımsız olarak herhangi bir değeri varsa, **varsa** üzerinde bu yönergesi bulunabilecek yan tümcesi. Paralel bölge şu anda yürütülmekte olan, yönergeleri yalnızca ana iş parçacığı oluşan bir ekibin yürütülür.  
  
-   **Sıralı** yönergesi bağlar dinamik olarak kapsayan **için**.  
  
-   **Atomik** yönergesi zorlar ilişkilendirilebilmesi için özel erişim **atomik** yalnızca geçerli takım tüm iş parçacıklarının yönergeleri.  
  
-   **Kritik** yönergesi zorlar ilişkilendirilebilmesi için özel erişim **kritik** yalnızca geçerli takım tüm iş parçacıklarının yönergeleri.  
  
-   Bir yönerge asla en yakın dışında tüm yönergesi dinamik olarak bağlayabilirsiniz kapsayan **paralel**.