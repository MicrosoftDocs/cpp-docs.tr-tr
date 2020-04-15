---
title: EVENT_COLLECTION_DATA yapısı
description: C++ Build Insights SDK yapı referansı EVENT_COLLECTION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88ba39ede8c86f47c2e6458332ae005eddc06fda
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325688"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `EVENT_COLLECTION_DATA` bir dizi [EVENT_DATA](event-data-struct.md) öğeyi açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Count` | Dizideki `EVENT_DATA` öğelerin sayısı. |
| `Elements` | Dizideki ilk `EVENT_DATA` öğeyi işaretle. |

::: moniker-end
