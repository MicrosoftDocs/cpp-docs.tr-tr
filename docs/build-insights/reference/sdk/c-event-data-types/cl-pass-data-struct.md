---
title: CL_PASS_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK CL_PASS_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3df5b5bc1cddbadc4a4d432ae021dd8b338c532e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333827"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`CL_PASS_DATA` yapısı, bir derleme geçişini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `TranslationUnitPassCode` | Yürütülen derleme geçişini tanımlayan bir kod. Daha fazla bilgi için bkz. [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md). |
| `InputSourcePath` | Bu derleme geçişinin C++ yürütüldüğü C veya kaynak dosyası. |
| `OutputObjectPath` | Derleyici tarafından üretilen nesne dosyası. |

::: moniker-end
