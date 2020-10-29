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
ms.openlocfilehash: ebed659ade4610b50ae06f2a32851522073a58d8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923560"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

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
