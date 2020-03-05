---
title: NAME_VALUE_PAIR_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK NAME_VALUE_PAIR_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f6c4f6fef11e6365bdc930d5df1f48f72186ebdb
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333645"
---
# <a name="name_value_pair_data-structure"></a>NAME_VALUE_PAIR_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`NAME_VALUE_PAIR_DATA` yapısı bir ad ve değer çiftini tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Name` | Ad. |
| `Value` | Değer. |

::: moniker-end
