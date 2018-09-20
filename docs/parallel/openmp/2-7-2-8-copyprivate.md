---
title: 2.7.2.8 copyprivate | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6815afe12344f94ed33d6b9260472f3e29eb72a0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406366"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

**Copyprivate** yan tümcesi bir değer diğer üyeleri, takımın bir üyesi yayınlamak için özel bir değişken kullanmak için bir mekanizma sağlar. Paylaşılan bir değişken sağlayan (örneğin, farklı bir değişken her düzeyde gerektiren özyineleme) zor olduğunda için paylaşılan bir değişken değeri kullanarak bir alternatiftir. **Copyprivate** yan tümcesi üzerinde yalnızca görüntülenebilir **tek** yönergesi.

Söz dizimi **copyprivate** yan tümcesi şu şekildedir:

```

copyprivate(
variable-list
)

```

Etkisini **copyprivate** yan tümcesi değişkeni-listesinde değişkenlerde gerçekleşir ilişkili yapısal bloğunun yürütülmesi sonrasında **tek** oluşturun ve herhangi bir iş parçacığı önce takım yapısı sonunda engel kalmadı. Ardından, her bir değişken için takım diğer iş parçacıklarını *değişken listesi*, bu değişken (atama gibi) karşılık gelen değer ile tanımlanan olur yapısı yürütülen iş parçacığının değişkene yapılandırılmış Blok.

Kısıtlamaları **copyprivate** yan tümcesi aşağıdaki gibidir:

- Belirtilen değişken **copyprivate** yan tümcesi içinde değil görünmelidir bir **özel** veya **firstprivate** aynı yan tümcesinde **tek**yönergesi.

- Varsa bir **tek** yönergesi ile bir **copyprivate** yan tümcesi bir paralel bölgenin içinde dinamik kapsamı ile karşılaşıldı, tüm değişkenleri belirtilen **copyprivate** yan tümcesi olmalıdır. kapsayan bağlamda özel.

- Belirtilen değişken **copyprivate** yan tümcesi bir erişilebilir belirsiz kopya atama işleci olması gerekir.