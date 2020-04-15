---
title: FUNCTION_FORCE_INLINEE_DATA yapısı
description: C++ Build Insights SDK yapı referansı FUNCTION_FORCE_INLINEE_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FUNCTION_FORCE_INLINEE_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a4781c9157130cb46e92906017af98710f5637b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325501"
---
# <a name="function_force_inlinee_data-structure"></a>FUNCTION_FORCE_INLINEE_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `FUNCTION_FORCE_INLINEE_DATA` kuvvet ekicikli bir işlevi tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct FUNCTION_FORCE_INLINEE_DATA_TAG
{
    const char*         Name;
    unsigned short      Size;

} FUNCTION_FORCE_INLINEE_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Name` | Fonksiyonun adı, UTF-8 kodlanmış. |
| `Size` | Ara yönergeler bir dizi olarak işlevin boyutu. |

::: moniker-end
