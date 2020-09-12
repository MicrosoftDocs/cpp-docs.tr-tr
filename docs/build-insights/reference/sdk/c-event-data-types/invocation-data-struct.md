---
title: INVOCATION_DATA yapısı
description: C++ derleme öngörüleri SDK INVOCATION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- INVOCATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 48b4c28d3c01d61a31343894312a54ba2ab17a70
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041646"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`INVOCATION_DATA`Yapı, bir derleyici veya bağlayıcı çağrısını açıklar.

## <a name="syntax"></a>Syntax

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

| Ad | Açıklama |
|--|--|
| `MSVCToolCode` | Çağrının türünü tanımlayan bir kod. Daha fazla bilgi için bkz. [MSVC_TOOL_CODE](msvc-tool-code-enum.md). |
| `ToolVersion` | Çağrılan aracın sürümünü bir integral değerleri grubu olarak depolayan bir nesne. |
| `ToolVersionString` | Çağrılan aracın metin biçimindeki sürümünü açıklar. |
| `WorkingDirectory` | Çağrının yapıldığı dizin. |
| `ToolPath` | Çağrılan aracın mutlak yolu. |

::: moniker-end
