---
title: 4.3 OMP_DYNAMIC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c15fa9d8c9d86b736bfc577a3b17e9809ec9baaf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439204"
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