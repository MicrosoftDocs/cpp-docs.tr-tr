---
title: SYMBOL_NAME_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK SYMBOL_NAME_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SYMBOL_NAME_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 618e84f198c20aa089dc7e06e1e6c09b96b6d273
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333638"
---
# <a name="symbol_name_data-structure"></a>SYMBOL_NAME_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`SYMBOL_NAME_DATA` yapısı bir derleyici ön uç sembolünü açıklar.

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
| `Key` | Simgenin anahtarı. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `Name` | Simgenin adı. |

## <a name="remarks"></a>Açıklamalar

İki farklı derleyici ön uç geçişlerinden gelen semboller aynı ada ancak farklı bir anahtara sahip olabilir. Bu durumda, iki türün aynı olup olmadığını anlamak için sembol adlarını kullanın.

::: moniker-end
