---
title: 2.9 Yönerge İç İçe Koyma
ms.date: 11/04/2016
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
ms.openlocfilehash: 804cafd65fde19e501b89c47925f471143d74938
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438734"
---
# <a name="29-directive-nesting"></a>2.9 Yönerge İç İçe Koyma

Dinamik iç içe geçmiş yönergeleri şu kurallara uymalıdır:

- A **paralel** dinamik olarak iç yönerge **paralel** yalnızca geçerli iş parçacığı oluşur, yeni bir takım paralellik iç içe geçmiş sürece etkin mantıksal olarak oluşturur.

- **için**, **bölümleri**, ve **tek** aynı bağlama yönergeleri **paralel** diğer içinde iç içe geçmiş izin verilmez.

- **Kritik** yönergeleri aynı ada sahip diğer içinde iç içe geçmiş izin verilmez. Bu kısıtlama kilitlenmeyi önlemek için yeterli olmadığını unutmayın.

- **için**, **bölümleri**, ve **tek** yönergeleri dinamik kapsam verilmez **kritik**, **sıralı**, ve **ana** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.

- **engel** yönergeleri dinamik kapsam verilmez **için**, **sıralı**, **bölümleri**, **tek**, **ana**, ve **kritik** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.

- **Ana** yönergeleri dinamik kapsam verilmez **için**, **bölümleri**, ve **tek** yönergeleri, **ana** yönergeleri bağlamak için aynı **paralel** iş paylaşım yönergelerinin olarak.

- **Sıralı** yönergeleri dinamik kapsam verilmez **kritik** yönergeleri aynı bağlarsanız bölgeleri **paralel** bölgeleri olarak.

- Dinamik olarak bir paralel bölgenin içinde çalıştırıldığında verilen tüm yönergesi, bir paralel bölgenin dışında yürütüldüğünde de izin verilir. Dinamik olarak bir kullanıcı tarafından belirtilen paralel bölgenin dışında yürütüldüğünde yönergesi yalnızca ana iş parçacığı oluşan bir ekip tarafından yürütülür.