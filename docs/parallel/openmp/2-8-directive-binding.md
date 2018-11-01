---
title: 2.8 Yönerge Bağlama
ms.date: 11/04/2016
ms.assetid: 7bdac45e-ab55-42f0-bd47-a2e3d5bbab3e
ms.openlocfilehash: fb22d1b503303842ff73550c1c6544cae7e5f2f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528628"
---
# <a name="28-directive-binding"></a>2.8 Yönerge Bağlama

Dinamik bağlama yönergeleri şu kurallara uymalıdır:

- **İçin**, **bölümleri**, **tek**, **ana**, ve **engel** yönergeleri bağlamak için dinamik olarak kapsayan **paralel**, bir bağımsız olarak herhangi bir değeri varsa, **varsa** bu yönergesinde bulunabilecek yan tümcesi. Herhangi bir paralel bölgenin şu anda yürütülmekte olan, yönergeleri ana iş parçacığı yalnızca oluşan bir ekip tarafından yürütülür.

- **Sıralı** yönergesi bağlar dinamik olarak kapsayan **için**.

- **Atomik** yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar **atomik** tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- **Kritik** yönergesi ile ilişkilendirilebilmesi için özel erişim zorlar **kritik** tüm iş parçacıkları, yalnızca geçerli takım yönergeleri.

- Bir yönerge hiçbir zaman en yakın dışında herhangi bir yönerge dinamik olarak adlarınıza bağlayabileceğiniz kapsayan **paralel**.