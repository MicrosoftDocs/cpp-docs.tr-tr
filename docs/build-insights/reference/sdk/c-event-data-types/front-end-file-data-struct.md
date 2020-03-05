---
title: FRONT_END_FILE_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK FRONT_END_FILE_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 33232a0f83566e58e64964e84961a7ade2de7b7c
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333743"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`FRONT_END_FILE_DATA` yapısı, bir dosyanın derleyicinin ön ucuna göre işlenmesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct FRONT_END_FILE_DATA_TAG
{
    const char*         Path;

} FRONT_END_FILE_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Path` | Dosyanın mutlak yolu UTF-8 olarak kodlanır. |

::: moniker-end
