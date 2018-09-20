---
title: 2.4.3 tek yapı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 15c180cd-e462-4b41-bf8c-cb8b1afb1a9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 81abf5324c215b9011ecbd774626a213c2eda653
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376506"
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