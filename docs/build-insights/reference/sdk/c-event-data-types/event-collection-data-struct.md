---
title: EVENT_COLLECTION_DATA yapısı
description: C++ derleme öngörüleri SDK EVENT_COLLECTION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EVENT_COLLECTION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 17daaa6feb784c501d180a982cd4ad2b405ccf67
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921093"
---
# <a name="event_collection_data-structure"></a>EVENT_COLLECTION_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`EVENT_COLLECTION_DATA`Yapı, bir dizi [EVENT_DATA](event-data-struct.md) öğesi tanımlar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct EVENT_COLLECTION_DATA_TAG
{
    unsigned int            Count;
    const EVENT_DATA*       Elements;

} EVENT_COLLECTION_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Count` | `EVENT_DATA`Dizideki öğelerin sayısı. |
| `Elements` | Dizideki ilk öğeye yönelik işaretçi `EVENT_DATA` . |

::: moniker-end
