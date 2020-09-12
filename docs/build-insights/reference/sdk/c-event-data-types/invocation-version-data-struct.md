---
title: INVOCATION_VERSION_DATA yapısı
description: C++ derleme öngörüleri SDK INVOCATION_VERSION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ec54c560dd408dc3beecbc20eaac69d389c7ec37
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041571"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, bir `INVOCATION_VERSION_DATA` sürüm numarasını bir integral değerleri grubu olarak tanımlar.

## <a name="syntax"></a>Syntax

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

| Ad | Açıklama |
|--|--|
| `VersionMajor` | Sürümün ana numarası. |
| `VersionMinor` | Sürümün küçük sayısı. |
| `BuildNumberMajor` | Yapılandırmanın ana numarası. |
| `BuildNumberMinor` | Derleme küçük numarası. |

::: moniker-end
