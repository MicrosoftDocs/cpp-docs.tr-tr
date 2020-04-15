---
title: CL_PASS_DATA yapısı
description: C++ Yapı Öngörüleri SDK CL_PASS_DATA yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CL_PASS_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b0a41e59068ade285f1ffa1a9ce13734ef5f1f32
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325704"
---
# <a name="cl_pass_data-structure"></a>CL_PASS_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `CL_PASS_DATA` bir derleme geçiş açıklar.

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
| `TranslationUnitPassCode` | Yürütülmekte olan derleme geçişini tanımlayan bir kod. Daha fazla bilgi için [TRANSLATION_UNIT_PASS_CODE.](translation-unit-pass-code-enum.md) |
| `InputSourcePath` | Bu derleme nin geçtiği C veya C++ kaynak dosyası yürütülür. |
| `OutputObjectPath` | Derleyici tarafından üretilen nesne dosyası. |

::: moniker-end
