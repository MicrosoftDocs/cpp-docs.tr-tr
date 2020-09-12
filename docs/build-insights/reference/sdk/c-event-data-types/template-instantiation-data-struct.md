---
title: TEMPLATE_INSTANTIATION_DATA yapısı
description: C++ derleme öngörüleri SDK TEMPLATE_INSTANTIATION_DATA yapısı başvurusu.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TEMPLATE_INSTANTIATION_DATA
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 15bbb25c3abac339201179e763bffd916dba0480
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040879"
---
# <a name="template_instantiation_data-structure"></a>TEMPLATE_INSTANTIATION_DATA yapısı

::: moniker range="<=vs-2015"

C++ Build Insights SDK 'Sı, Visual Studio 2017 ve üzeri ile uyumludur. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end
::: moniker range=">=vs-2017"

`TEMPLATE_INSTANTIATION_DATA`Yapı, bir şablon örneğini açıklar.

## <a name="syntax"></a>Syntax

```cpp
typedef struct TEMPLATE_INSTANTIATION_DATA_TAG
{
    unsigned long long  SpecializationSymbolKey;
    unsigned long long  PrimaryTemplateSymbolKey;
    int                 KindCode;

} TEMPLATE_INSTANTIATION_DATA;
```

## <a name="members"></a>Üyeler

| Ad | Açıklama |
|--|--|
| `SpecializationSymbolKey` | Şablon özelleşmenin türü için anahtar. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `PrimaryTemplateSymbolKey` | Özelleştirilmiş birincil şablon türü için anahtar. Bu değer, çözümlenmekte olan izleme içinde benzersizdir. |
| `KindCode` | Şablon örneği oluşturma türü. Daha fazla bilgi için bkz. [TEMPLATE_INSTANTIATION_KIND_CODE](template-instantiation-kind-code-enum.md). |

## <a name="remarks"></a>Açıklamalar

`TEMPLATE_INSTANTIATION_DATA`Yapıdaki anahtarlar çözümlenmekte olan izleme içinde benzersizdir. Ancak, farklı derleyici ön uç geçişlerinden gelen iki farklı anahtar iki özdeş türe işaret edebilir. `TEMPLATE_INSTANTIATION_DATA`Birden çok derleyici ön uç geçişlerinden bilgi tükettiği zaman, iki türün aynı olup olmadığını anlamak için [SYMBOL_NAME](../event-table.md#symbol-name) olaylarını kullanın. `SymbolName` olaylar, tüm şablon örneklemeleri gerçekleştirildikten sonra bir derleyici ön ucu geçişinin sonuna yayılır.

::: moniker-end
