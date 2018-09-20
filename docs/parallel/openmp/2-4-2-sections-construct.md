---
title: 2.4.2 sections yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e9e6e3ea-7fc9-4925-8f68-92b8a5bb1e76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35ae940e37b40cbb9c883c4d7d6bca7b0fa65520
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410554"
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