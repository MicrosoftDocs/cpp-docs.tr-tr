---
title: 4.3 OMP_DYNAMIC
ms.date: 11/04/2016
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
ms.openlocfilehash: 0ea6784159a11fc194d0c1cd16d2316a80b9cd37
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488575"
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC

**Omp_dynamıc** ortam değişkeni etkinleştirir veya yerleştirmenin dinamik ayarına açıkça etkin veya devre dışı çağıraraksüreceparalelbölgeleriyürütülmesiiçinkullanılabilirişparçacığısayısınıyerleştirmenindinamikayarınadevredışıbırakır.**omp_set_dynamic** yordamı. Değeri olmalıdır **TRUE** veya **FALSE**.

Varsa kümesine **TRUE**, paralel bölgeleri yürütmek için kullanılan iş parçacıklarının sayısını sistem kaynakları en iyi şekilde yararlanmak için çalışma zamanı ortamı tarafından ayarlanmış.  Varsa kümesine **FALSE**, yerleştirmenin dinamik ayarına devre dışı bırakıldı. Uygulama tanımlı varsayılan durumdur.

Örnek:

```
setenv OMP_DYNAMIC TRUE
```

## <a name="cross-references"></a>Başvuruları çapraz:

- Paralel bölgeleri hakkında daha fazla bilgi için bkz. [bölümü 2.3](../../parallel/openmp/2-3-parallel-construct.md) 8 sayfasında.

- **omp_set_dynamic** çalışması için bkz: [bölümü 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.