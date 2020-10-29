---
title: CL_PASS_DATA yapısı
description: C++ derleme öngörüleri SDK CL_PASS_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 24e524b802a124f38043f3b69afed7f1aa9cd156
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923648"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA yapısı

::: moniker range="<=msvc-140"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=msvc-150"

`CL_PASS_DATA`Yapı, bir derleme geçişini açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct CL_PASS_DATA_TAG
{
    int                         TranslationUnitPassCode;
    const wchar_t*              InputSourcePath;
    const wchar_t*              OutputObjectPath;

} CL_PASS_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `TranslationUnitPassCode` | Yürütülen derleme geçişini tanımlayan bir kod. Daha fazla bilgi için bkz. [TRANSLATION_UNIT_PASS_CODE](translation-unit-pass-code-enum.md). |
| `InputSourcePath` | Bu derleme geçişinin yürütüldüğü C veya C++ kaynak dosyası. |
| `OutputObjectPath` | Derleyici tarafından üretilen nesne dosyası. |

::: moniker-end
