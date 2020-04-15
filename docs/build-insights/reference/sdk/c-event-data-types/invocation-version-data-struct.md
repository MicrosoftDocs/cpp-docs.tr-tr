---
title: INVOCATION_VERSION_DATA yapısı
description: C++ Yapı Öngörüleri SDK yapı referansı INVOCATION_VERSION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1211b4eb999fd63767af71c6884d7d20d6920df0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325466"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `INVOCATION_VERSION_DATA` bir sürüm numarasını integral değerler grubu olarak tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct INVOCATION_VERSION_DATA_TAG
{
    unsigned short VersionMajor;
    unsigned short VersionMinor;
    unsigned short BuildNumberMajor;
    unsigned short BuildNumberMinor;

} INVOCATION_VERSION_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `VersionMajor` | Sürümün ana numarası. |
| `VersionMinor` | Sürümün küçük numarası. |
| `BuildNumberMajor` | Yapının en büyük numarası. |
| `BuildNumberMinor` | Yapının küçük numarası. |

::: moniker-end
