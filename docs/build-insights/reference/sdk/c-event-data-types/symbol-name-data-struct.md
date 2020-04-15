---
title: SYMBOL_NAME_DATA yapı
description: C++ Build Insights SDK yapı referansı SYMBOL_NAME_DATA.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1217572f20a772fde629533d6ab170c14dc5b5e0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325346"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA yapı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı `SYMBOL_NAME_DATA` derleyici ön uç simgesini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `Key` | Sembolün anahtarı. Bu değer, analiz edilen izleme içinde benzersizdir. |
| `Name` | Sembolün adı. |

## <a name="remarks"></a>Açıklamalar

İki farklı derleyici ön uç geçişinden gelen semboller aynı ada ama farklı bir anahtara sahip olabilir. Bu durumda, iki tür aynı olup olmadığını belirlemek için sembol adlarını kullanın.

::: moniker-end
