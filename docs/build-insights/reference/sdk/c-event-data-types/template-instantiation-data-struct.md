---
title: TEMPLATE_INSTANTIATION_DATA yapısı
description: C++ Derleme ÖNGÖRÜLERI SDK TEMPLATE_INSTANTIATION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9aa669d715dbe56ce7e889330f46f307f520710f
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2020
ms.locfileid: "78333624"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA yapısı

::: moniker range="<=vs-2015"

Build C++ Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio sürüm Seçicisi denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın.

::: moniker-end
::: moniker range=">=vs-2017"

`TEMPLATE_INSTANTIATION_DATA` yapısı bir şablon örneğini açıklar.

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
| `SpecializationSymbolKey` | Şablon özelleşmenin türü için anahtar. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `PrimaryTemplateSymbolKey` | Özelleştirilmiş birincil şablon türü için anahtar. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `KindCode` | Şablon örneği oluşturma türü. Daha fazla bilgi için bkz. [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md). |

## <a name="remarks"></a>Açıklamalar

`TEMPLATE_INSTANTIATION_DATA` yapısındaki anahtarlar çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen iki farklı anahtar iki özdeş türe işaret edebilir. Birden çok derleyici ön uç geçişlerinden `TEMPLATE_INSTANTIATION_DATA` bilgilerini tüketerek, iki türün aynı olup olmadığını anlamak için [SYMBOL_NAME](../event-table.md#symbol-name) olaylarını kullanın. `SymbolName` olaylar, tüm şablon örneklemeleri gerçekleştirildikten sonra bir derleyici ön ucu geçişinin sonuna yayılır.

::: moniker-end
