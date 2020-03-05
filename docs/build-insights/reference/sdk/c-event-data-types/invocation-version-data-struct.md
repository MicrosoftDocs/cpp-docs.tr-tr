---
title: INVOCATION_VERSION_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK INVOCATION_VERSION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_VERSION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 040b0f90b14133ec2b25f7a12d35b88d382c4f7a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333680"
---
# <a name="invocation_version_data-structure"></a>INVOCATION_VERSION_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_VERSION_DATA` yapısı, bir sürüm numarasını bir integral değerleri grubu olarak tanımlar.

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
| `VersionMinor` | Sürümün küçük sayısı. |
| `BuildNumberMajor` | Yapılandırmanın ana numarası. |
| `BuildNumberMinor` | Derleme küçük numarası. |

::: moniker-end
