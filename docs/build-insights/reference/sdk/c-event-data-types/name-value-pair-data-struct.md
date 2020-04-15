---
title: NAME_VALUE_PAIR_DATA yapısı
description: C++ Build Insights SDK yapı referansı NAME_VALUE_PAIR_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4a0bf8e8ba32d94d30a56d0ef26ca4ed0c9b0711
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325351"
---
# <a name="name_value_pair_data-structure"></a>NAME_VALUE_PAIR_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `NAME_VALUE_PAIR_DATA` bir ad ve değer çiftini açıklar.

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
