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
ms.openlocfilehash: 98ac234b702ef2c73a5c8d90ee6bf4dc59349ed6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920976"
---
# <a name="invocation_data-structure"></a>INVOCATION_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

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
