---
title: FRONT_END_FILE_DATA yapısı
description: C++ Build Insights SDK FRONT_END_FILE_DATA yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FRONT_END_FILE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7fb6b6fff4f309a3539a290f279d1e31cb1ed76b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325546"
---
# <a name="front_end_file_data-structure"></a>FRONT_END_FILE_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `FRONT_END_FILE_DATA` derleyici ön uç tarafından bir dosyanın işlenmesi açıklanır.

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
| `Path` | Dosyanın mutlak yolu UTF-8'de kodlanmış. |

::: moniker-end
