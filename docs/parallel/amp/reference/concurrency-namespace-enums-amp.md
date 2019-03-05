---
title: Eşzamanlılık ad alanı sabit listeleri (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: adfc1743d887f2a670111eff31cf4653d2df1bee
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326081"
---
# <a name="concurrency-namespace-enums-amp"></a>Eşzamanlılık ad alanı sabit listeleri (AMP)

|||
|-|-|
|[access_type numaralandırması](#access_type)|[queuing_mode numaralandırması](#queuing_mode)|

##  <a name="access_type"></a>  access_type numaralandırması

Çeşitli veri erişimi belirtmek için kullanılan numaralandırma türü.

```
enum access_type;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`access_type_auto`|Otomatik olarak en iyi seçin `access_type` Hızlandırıcı için.|
|`access_type_none`|Ayrılmış. Ayırma, yalnızca Hızlandırıcı ve CPU üzerinde erişilebilir.|
|`access_type_read`|Paylaşılan. Tahsisat, hızlandırıcıda erişilebilirdir ve CPU üzerinde okunabilir.|
|`access_type_read_write`|Paylaşılan. Tahsisat, hızlandırıcıda erişilebilirdir ve CPU üzerinde yazılabilir.|
|`access_type_write`|Paylaşılan. Tahsisat, hızlandırıcıda erişilebilirdir ve hem okunabilir, hem de CPU üzerinde yazılabilir.|

##  <a name="queuing_mode"></a>  queuing_mode numaralandırması

Hızlandırıcı üzerinde desteklenen sıralama modlarını belirtir.

```
enum queuing_mode;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`queuing_mode_immediate`|Örneğin, herhangi bir belirten bir sıralama modu komutları [parallel_for_each işlevi (C++ AMP)](concurrency-namespace-functions-amp.md#parallel_for_each), bunlar çağırana dönmez ilgili Hızlandırıcı cihaza gönderilir.|
|`queuing_mode_automatic`|Komutları için karşılık gelen bir komut sırası üzerinde sırada olduğunu belirten bir sıralama modu [accelerator_view](accelerator-view-class.md) nesne. Komutları cihaza gönderilen zaman [accelerator_view::flush](accelerator-view-class.md#flush) çağrılır.|

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
