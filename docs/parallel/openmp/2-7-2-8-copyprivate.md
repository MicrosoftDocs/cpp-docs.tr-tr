---
title: 2.7.2.8 copyprivate
ms.date: 11/04/2016
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
ms.openlocfilehash: d4df1b4216014d3cd15be1480d2f83334fddb72d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622917"
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