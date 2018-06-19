---
title: 2.8 yönerge bağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02492b228b4bb47a800955f078a59ce680312a87
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33689460"
---
# <a name="28-directive-binding"></a>2.8 Yönerge Bağlama
Dinamik bağlama yönergeleri aşağıdaki kurallara uymalıdır:  
  
-   **İçin**, **bölümleri**, **tek**, **ana**, ve **engel** yönergeleri bağlamak için dinamik olarak kapsayan **paralel**, bir bağımsız olarak herhangi bir değeri varsa, **varsa** üzerinde bu yönergesi bulunabilecek yan tümcesi. Paralel bölge şu anda yürütülmekte olan, yönergeleri yalnızca ana iş parçacığı oluşan bir ekibin yürütülür.  
  
-   **Sıralı** yönergesi bağlar dinamik olarak kapsayan **için**.  
  
-   **Atomik** yönergesi zorlar ilişkilendirilebilmesi için özel erişim **atomik** yalnızca geçerli takım tüm iş parçacıklarının yönergeleri.  
  
-   **Kritik** yönergesi zorlar ilişkilendirilebilmesi için özel erişim **kritik** yalnızca geçerli takım tüm iş parçacıklarının yönergeleri.  
  
-   Bir yönerge asla en yakın dışında tüm yönergesi dinamik olarak bağlayabilirsiniz kapsayan **paralel**.