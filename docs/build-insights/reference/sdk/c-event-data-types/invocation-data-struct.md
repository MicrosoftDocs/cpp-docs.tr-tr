---
title: INVOCATION_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK INVOCATION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b2e8ddcf79201d8bcbbb8eb298b96b5c7680f90e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333694"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_DATA` yapısı bir derleyici veya bağlayıcı çağrısını açıklar.

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
| `MSVCToolCode` | Çağrının türünü tanımlayan bir kod. Daha fazla bilgi için bkz. [MSVC_TOOL_CODE](msvc-tool-code-enum.md). |
| `ToolVersion` | Çağrılan aracın sürümünü bir integral değerleri grubu olarak depolayan bir nesne. |
| `ToolVersionString` | Çağrılan aracın metin biçimindeki sürümünü açıklar. |
| `WorkingDirectory` | Çağrının yapıldığı dizin. |
| `ToolPath` | Çağrılan aracın mutlak yolu. |

::: moniker-end
