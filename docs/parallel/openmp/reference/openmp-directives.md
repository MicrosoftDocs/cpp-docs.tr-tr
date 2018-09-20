---
title: OpenMP yönergeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: reference
dev_langs:
- C++
ms.assetid: 0562c263-344c-466d-843e-de830d918940
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 983a71920e9e7ce390ab8c64e81886db0d459450
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389455"
---
# <a name="openmp-directives"></a>OpenMP Yönergeleri

OpenMP API çağrısında kullanılan yönergelere bağlantılar sağlar.

Visual C++ aşağıdaki OpenMP yönergeleri destekler:

|Yönergesi|Açıklama|
|---------------|-----------------|
|[atomic](../../../parallel/openmp/reference/atomic.md)|Belirten bir bellek konumuna atomik olarak güncelleştirilecek.|
|[barrier](../../../parallel/openmp/reference/barrier.md)|Takım tüm iş parçacıklarının eşitler; tüm iş parçacıklarının engeli yürütene kadar tüm iş parçacıklarının engeli duraklatın.|
|[critical](../../../parallel/openmp/reference/critical.md)|Bir kerede tek bir iş parçacığı üzerinde kod yalnızca yürütülür belirtir.|
|[Temizleme](../../../parallel/openmp/reference/flush-openmp.md)|Tüm iş parçacıkları aynı görünümde tüm paylaşılan nesneler için bellek olduğunu belirtir.|
|[for](../../../parallel/openmp/reference/for-openmp.md)|Çalışmanın neden olan bir for döngüsü iş parçacıkları arasında bölünmesi için bir paralel bölgenin içinde.|
|[master](../../../parallel/openmp/reference/master.md)|Yalnızca ana threadshould program bir bölümünü yürütmek belirtir.|
|[Sıralı](../../../parallel/openmp/reference/ordered-openmp-directives.md)|Bu kod bir paralel döngü gibi sıralı döngü yürütülmesi gereken belirtir.|
|[parallel](../../../parallel/openmp/reference/parallel.md)|Birden çok iş parçacığı paralel olarak yürütülen kodu bir paralel bölgenin tanımlar.|
|[Bölümleri](../../../parallel/openmp/reference/sections-openmp.md)|Tüm iş parçacıkları arasında bölünmesi için kod bölümleri tanımlar.|
|[single](../../../parallel/openmp/reference/single.md)|Kodun bir bölümünü tek bir iş parçacığı üzerinde mutlaka ana iş parçacığının yürütülmesi gereken belirtmenize olanak sağlar.|
|[threadprivate](../../../parallel/openmp/reference/threadprivate.md)|Bir değişken için bir iş parçacığı özel olduğunu belirtir.|

## <a name="see-also"></a>Ayrıca Bkz.

[OpenMP](../../../parallel/openmp/openmp-in-visual-cpp.md)<br/>
[Yan Tümceler](../../../parallel/openmp/reference/openmp-clauses.md)