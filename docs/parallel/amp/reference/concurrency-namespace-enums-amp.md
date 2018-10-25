---
title: Eşzamanlılık ad alanı sabit listeleri (AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
dev_langs:
- C++
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58d70b995642eaca3dbefd75383e6d6bf06f2c62
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50082443"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
