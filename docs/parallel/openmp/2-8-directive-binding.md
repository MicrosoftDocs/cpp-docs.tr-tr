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
ms.openlocfilehash: dc5b702b17e01bb8d4625a837abdb71086113e68
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415908"
---
# <a name="28-directive-binding"></a>2.8 Yönerge Bağlama

Dinamik bağlama yönergeleri şu kurallara uymalıdır:

- **İçin**, **bölümleri**, **tek**, **ana**, ve **engel** yönergeleri bağlamak için dinamik olarak kapsayan **paralel**, bir bağımsız olarak herhangi bir değeri varsa, **varsa** bu yönergesinde bulunabilecek yan tümcesi. Herhangi bir paralel bölgenin şu anda yürütülmekte olan, yönergeleri ana iş parçacığı yalnızca oluşan bir ekip tarafından yürütülür.

- **Sıralı** yönergesi bağlar dinamik olarak kapsayan **için**.

- **Atomik** yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar **atomik** tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- **Kritik** yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar **kritik** tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- Bir yönerge hiçbir zaman en yakın dışında herhangi bir yönerge dinamik olarak adlarınıza bağlayabileceğiniz kapsayan **paralel**.