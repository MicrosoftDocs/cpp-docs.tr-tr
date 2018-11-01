---
title: 4.2 OMP_NUM_THREADS
ms.date: 11/04/2016
ms.assetid: 49dd55dd-25d5-4a5a-a998-cc7f47b2dae2
ms.openlocfilehash: 88ddfc226b8ae905e026e2f0979e07581d1ae83b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668215"
---
# <a name="42-ompnumthreads"></a>4.2 OMP_NUM_THREADS

**OMP_NUM_THREADS** ortam değişkenini bu sayıyı çağrılarak açıkça değiştirmediğiniz sürece varsayılan yürütme sırasında kullanılacak iş parçacığı sayısını ayarlar **omp_set_num_threads** yordamı veya açık bir tarafından **num_threads** yan tümcesi bir **paralel** yönergesi.

Değerini **OMP_NUM_THREADS** ortam değişkeni, pozitif bir tamsayı olmalıdır. İş parçacığı sayısını yerleştirmenin dinamik ayarına etkin bağlı etkisini bağlıdır. Kurallar arasındaki etkileşimi hakkında kapsamlı bir dizi için **OMP_NUM_THREADS** ortam değişken ve dinamik düzeltmesi iş parçacığı, bölüm 2.3 8 sayfasında bakın.

İçin hiçbir değer belirtilmemişse **OMP_NUM_THREADS** ortam değişkeni veya belirtilen değer bir pozitif tamsayı değil veya değer en fazla iş parçacığı sayısından büyükse, sistem için destek, kullanılacak iş parçacığı sayısı uygulama tarafından tanımlanır.

Örnek:

```
setenv OMP_NUM_THREADS 16
```

## <a name="cross-references"></a>Başvuruları çapraz:

- **num_threads** yan tümcesi bkz [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **omp_set_num_threads** çalışması için bkz: [bölümü 3.1.1](../../parallel/openmp/3-1-1-omp-set-num-threads-function.md) 36 sayfasında.

- **omp_set_dynamic** çalışması için bkz: [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.