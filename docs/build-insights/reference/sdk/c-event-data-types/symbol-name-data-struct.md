---
title: SYMBOL_NAME_DATA yapısı
description: C++ derleme öngörüleri SDK SYMBOL_NAME_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: d234c6c225eff87a0eecd98fa5ff60bf92db97f5
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041919"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`SYMBOL_NAME_DATA`Yapı bir derleyici ön uç sembolünü açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct SYMBOL_NAME_DATA_TAG
{
    unsigned long long  Key;
    const char*         Name;

} SYMBOL_NAME_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `Key` | Simgenin anahtarı. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `Name` | Simgenin adı. |

## <a name="remarks"></a>Açıklamalar

İki farklı derleyici ön uç geçişlerinden gelen semboller aynı ada ancak farklı bir anahtara sahip olabilir. Bu durumda, iki türün aynı olup olmadığını anlamak için sembol adlarını kullanın.

::: moniker-end
