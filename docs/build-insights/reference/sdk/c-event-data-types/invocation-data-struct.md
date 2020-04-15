---
title: INVOCATION_DATA yapısı
description: C++ Yapı Öngörüleri SDK yapı başvurusu INVOCATION_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4e1f428facac413d7a4a5c059452dd8cdb07be4c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325482"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `INVOCATION_DATA` derleyici veya bağlayıcı çağırma açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct INVOCATION_DATA_TAG
{
    int                         MSVCToolCode;

    INVOCATION_VERSION_DATA     ToolVersion;

    const char*                 ToolVersionString;
    const wchar_t*              WorkingDirectory;
    const wchar_t*              ToolPath;

} INVOCATION_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `MSVCToolCode` | Çağırmanın türünü tanımlayan bir kod. Daha fazla bilgi için [MSVC_TOOL_CODE.](msvc-tool-code-enum.md) |
| `ToolVersion` | Çağrılan aracın sürümünü integral değerler grubu olarak depolayan bir nesne. |
| `ToolVersionString` | Çağrılan aracın sürümünü metin biçiminde açıklar. |
| `WorkingDirectory` | Çağırmanın yapıldığı dizin. |
| `ToolPath` | Çağrılan aracın mutlak yolu. |

::: moniker-end
