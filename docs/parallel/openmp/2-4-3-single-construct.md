---
title: 2.4.3 single Yapı
ms.date: 11/04/2016
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
ms.openlocfilehash: 7dda98ee83ee08adc29830a9c4ada71a208705fe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466371"
---
# <a name="243-single-construct"></a>2.4.3 single Yapı

**Tek** yönergesi ilişkili yapısal bloğunun (mutlaka ana iş parçacığı) takım yalnızca bir iş parçacığı tarafından yürütülür belirten bir yapı tanımlar. Söz dizimi **tek** yönerge aşağıdaki gibidir:

```
#pragma omp single [clause[[,] clause] ...] new-linestructured-block
```

Yan tümcesi aşağıdakilerden biridir:

**Özel (** *değişken listesi* **)**

**firstprivate (** *değişken listesi* **)**

**copyprivate (** *değişken listesi* **)**

**nowait**

Sonra örtük bir engel var. **tek** sürece oluşturmak bir **nowait** yan tümcesi belirtildi.

Kısıtlamaları **tek** yönerge aşağıdaki gibidir:

- Yalnızca tek bir **nowait** yan tümcesi görüntülenebilir bir **tek** yönergesi.

- **Copyprivate** yan tümcesi olmayan kullanılmalıdır **nowait** yan tümcesi.

## <a name="cross-references"></a>Başvuruları çapraz:

- **özel**, **firstprivate**, ve **copyprivate** yan tümcesi bkz [bölümü 2.7.2](../../parallel/openmp/2-7-2-data-sharing-attribute-clauses.md) sayfasında 25.