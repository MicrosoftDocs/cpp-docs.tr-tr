---
title: EVENT_COLLECTION_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK EVENT_COLLECTION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a622a8459b6aa6d9dcbe0faaf90ae545b449466
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333813"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`EVENT_COLLECTION_DATA` yapısı, bir dizi [EVENT_DATA](event-data-struct.md) öğesi tanımlar.

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
| `Count` | Dizideki `EVENT_DATA` öğe sayısı. |
| `Elements` | Dizideki ilk `EVENT_DATA` öğeye yönelik işaretçi. |

::: moniker-end
