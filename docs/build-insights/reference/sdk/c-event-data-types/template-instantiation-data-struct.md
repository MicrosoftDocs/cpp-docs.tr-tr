---
title: TEMPLATE_INSTANTIATION_DATA yapısı
description: C++ Build Insights SDK TEMPLATE_INSTANTIATION_DATA yapı referansı.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a38d19368e7c0a9912907f1da6e7a2e31ffe8d90
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325325"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

Yapı, `TEMPLATE_INSTANTIATION_DATA` şablon anlık açıklamalarını açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>Üyeler

|  |  |
|--|--|
| `SpecializationSymbolKey` | Şablon uzmanlık türü için anahtar. Bu değer, analiz edilen izleme içinde benzersizdir. |
| `PrimaryTemplateSymbolKey` | Özelleştirilmiş birincil şablon türü için anahtar. Bu değer, analiz edilen izleme içinde benzersizdir. |
| `KindCode` | Şablon anlık türü. Daha fazla bilgi için [TEMPLATE_INSTANTIATION_KIND_CODE.](template-instantiation-kind-code-enum.md) |

## <a name="remarks"></a>Açıklamalar

Yapıdaki `TEMPLATE_INSTANTIATION_DATA` anahtarlar analiz edilen iz içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen iki farklı anahtar, iki aynı türe işaret edebilir. Birden çok `TEMPLATE_INSTANTIATION_DATA` derleyici ön uç geçişinden bilgi tüketirken, iki tür aynı olup olmadığını belirlemek için [SYMBOL_NAME](../event-table.md#symbol-name) olayları kullanın. `SymbolName`olaylar, tüm şablon anlık gerçekleşmeleri gerçekleştikten sonra, derleyici ön uç geçişinin sonunda yayılır.

::: moniker-end
