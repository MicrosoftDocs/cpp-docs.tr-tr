---
title: Eşzamanlılık ad alanı sabit listeleri (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 2467db27ad36dfcda31dfb5bb45067ada5470d07
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376328"
---
# <a name="concurrency-namespace-enums-amp"></a>Eşzamanlılık ad alanı sabit listeleri (AMP)

|||
|-|-|
|[access_type Numaralandırma](#access_type)|[queuing_mode Numaralandırma](#queuing_mode)|

## <a name="access_type-enumeration"></a><a name="access_type"></a>access_type Numaralandırma

Çeşitli veri türlerini belirtmek için kullanılan numaralandırma türü.

```cpp
enum access_type;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`access_type_auto`|Otomatik olarak hızlandırıcı için en iyi `access_type` seçin.|
|`access_type_none`|Adan -mış. Ayırmaya cpu'da değil, yalnızca hızlandırıcıda erişilebilir.|
|`access_type_read`|Paylaşılan. Ayırma hızlandırıcıda erişilebilir ve CPU'da okunabilir.|
|`access_type_read_write`|Paylaşılan. Ayırma hızlandırıcıda erişilebilir ve CPU'da yazılabilir.|
|`access_type_write`|Paylaşılan. Ayırma hızlandırıcıda erişilebilir ve CPU'da hem okunabilir hem de okunabilir.|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a>queuing_mode Numaralandırma

Hızlandırıcıda desteklenen kuyruk modlarını belirtir.

```cpp
enum queuing_mode;
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`queuing_mode_immediate`|Örneğin, [parallel_for_each Fonksiyonu (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each)gibi komutların arayanın dönüşü nde ilgili hızlandırıcı aygıta gönderilmesini belirten bir kuyruk modu.|
|`queuing_mode_automatic`|[Komutların accelerator_view](accelerator-view-class.md) nesneye karşılık gelen bir komut kuyruğunda sıraya alınmasını belirten bir kuyruk modu. Komutlar [accelerator_view::flush](accelerator-view-class.md#flush) çağrıldığında aygıta gönderilir.|

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
