---
title: ANALYSIS_DESCRIPTOR yapısı
description: C++ Build Insights SDK yapı referansı ANALYSIS_DESCRIPTOR.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ANALYSIS_DESCRIPTOR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1de7f2a5bc3f02a327daaecf8c2cebc44687ba43
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323607"
---
# <a name="analysis_descriptor-structure"></a>ANALYSIS_DESCRIPTOR yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `ANALYSIS_DESCRIPTOR` [AnalyzeA](../functions/analyze-a.md) ve [AnalyzeW](../functions/analyze-w.md) işlevleri ile kullanılır. Windows için Olay İzleme (ETW) izlemenin nasıl çözümlenmesi gerektiğini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct ANALYSIS_DESCRIPTOR_TAG
{
    unsigned                NumberOfPasses;
    ANALYSIS_CALLBACKS      Callbacks;
    void*                   Context;
} ANALYSIS_DESCRIPTOR;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `NumberOfPasses` | ETW izleme üzerinden yapılması gereken analiz geçişlerinin sayısı. |
| `Callbacks` | Çözümleme oturumu sırasında hangi işlevlerin çağrılmasını belirten [ANALYSIS_CALLBACKS](analysis-callbacks-struct.md) bir nesne. |
| `Context` | Belirtilen tüm geri arama işlevlerine bağımsız değişken olarak geçirilen kullanıcı tarafından sağlanan bağlam`Callbacks` |

## <a name="remarks"></a>Açıklamalar

Yapı `Callbacks` yalnızca üye olmayan işlevlere işaretçileri kabul eder. Bir nesne işaretçisine `Context` ayarlayarak bu sınırlamayı atlatabilirsiniz. Bu nesne işaretçisi, üye olmayan tüm geri arama işlevlerinize bağımsız değişken olarak geçirilir. Üye olmayan geri arama işlevleriniz içinden üye işlevleri çağırmak için bu işaretçiyi kullanın.

::: moniker-end
