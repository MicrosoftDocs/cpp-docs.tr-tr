---
title: NAME_VALUE_PAIR_DATA yapısı
description: C++ derleme öngörüleri SDK NAME_VALUE_PAIR_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- NAME_VALUE_PAIR_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 384ed0340cd8de09101e2fe3e62e1a75f25e2bc1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041698"
---
# <a name="name_value_pair_data-structure"></a>NAME_VALUE_PAIR_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`NAME_VALUE_PAIR_DATA`Yapı bir ad ve değer çiftini tanımlar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct NAME_VALUE_PAIR_DATA_TAG
{
    const wchar_t*      Name;
    const wchar_t*      Value;
} NAME_VALUE_PAIR_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Name` | Ad. |
| `Value` | Değer. |

::: moniker-end
