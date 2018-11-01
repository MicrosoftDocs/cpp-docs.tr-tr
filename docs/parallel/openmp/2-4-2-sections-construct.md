---
title: 2.4.2 sections Yapı
ms.date: 11/04/2016
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
ms.openlocfilehash: 2d9fca08eecd382c9d3df60159c13ac188a1ab85
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486820"
---
# <a name="242-sections-construct"></a>2.4.2 sections Yapı

**Bölümleri** yönergesi, bir takım iş parçacıkları arasında bölünmesi gereken yapıları kümesini belirten bir noniterative iş paylaşımı yapısı tanımlar. Her bölüm, takım bir iş parçacığı tarafından bir kez yürütülür. Söz dizimi **bölümleri** yönerge aşağıdaki gibidir:

```
#pragma omp sections [clause[[,] clause] ...] new-line
   {
   [#pragma omp section new-line]
      structured-block
   [#pragma omp section new-linestructured-block ]
...
}
```

Yan tümcesi aşağıdakilerden biridir:

**Özel (** *değişken listesi* **)**

**firstprivate (** *değişken listesi* **)**

**lastprivate (** *değişken listesi* **)**

**azaltma (** *işleci* **:***değişken listesi* **)**

**nowait**

Her bölümde öncesinde bir **bölümü** yönergesi, ancak **bölümü** yönergesiyse ilk bölüm için isteğe bağlı. **Bölümü** yönergeleri sözcük kapsamı içinde görünmelidir **bölümleri** yönergesi. Sonunda örtük bir engel olan bir **bölümleri** sürece oluşturmak bir **nowait** belirtilir.

Kısıtlamaları **bölümleri** yönerge aşağıdaki gibidir:

- A **bölümü** yönergesi değil sözcük kapsamı dışında görünmelidir **bölümleri** yönergesi.

- Yalnızca tek bir **nowait** yan tümcesi görüntülenebilir bir **bölümleri** yönergesi.

## <a name="cross-references"></a>Başvuruları çapraz:

- **özel**, **firstprivate**, **lastprivate**, ve **azaltma** yan tümcesi bkz [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.