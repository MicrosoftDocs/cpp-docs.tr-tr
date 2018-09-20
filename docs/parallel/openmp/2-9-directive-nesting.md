---
title: 2.9 yönerge iç içe | Microsoft Docs
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
ms.openlocfilehash: b9558180a2f063171be563219f89ec3858e37a5d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396995"
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