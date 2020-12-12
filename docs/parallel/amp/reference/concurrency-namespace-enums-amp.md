---
description: 'Daha fazla bilgi edinin: eşzamanlılık ad alanı numaralandırmaları (AMP)'
title: Eşzamanlılık ad alanı sabit listeleri (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 60f4b325de47a600ee5a28f30ecc4a06fc2082a2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284908"
---
# <a name="concurrency-namespace-enums-amp"></a>Eşzamanlılık ad alanı sabit listeleri (AMP)

[access_type numaralandırması](#access_type)\
[queuing_mode numaralandırması](#queuing_mode)

## <a name="access_type-enumeration"></a><a name="access_type"></a> access_type numaralandırması

Verilerin çeşitli erişim türlerini belirtmek için kullanılan numaralandırma türü.

```cpp
enum access_type;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`access_type_auto`|Hızlandırıcı için en iyi seçeneği otomatik olarak seçin `access_type` .|
|`access_type_none`|Ayrılan. Ayırmaya yalnızca hızlandırıcıda erişilebilirdir ve CPU üzerinde değil.|
|`access_type_read`|Paylaşılan. Ayırmaya hızlandırıcıda erişilebilirdir ve CPU üzerinde okunabilir.|
|`access_type_read_write`|Paylaşılan. Ayırmaya hızlandırıcıda erişilebilirdir ve CPU üzerinde yazılabilir.|
|`access_type_write`|Paylaşılan. Ayırmaya hızlandırıcıda erişilebilirdir ve CPU üzerinde hem okunabilir hem de yazılabilir.|

## <a name="queuing_mode-enumeration"></a><a name="queuing_mode"></a> queuing_mode numaralandırması

Hızlandırıcıda desteklenen sıraya alma modlarını belirtir.

```cpp
enum queuing_mode;
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`queuing_mode_immediate`|[Parallel_for_each işlevi (C++ amp)](concurrency-namespace-functions-amp.md#parallel_for_each)gibi herhangi bir komutun, çağırana geri dönerken ilgili Hızlandırıcı cihazına gönderileceğini belirten bir sıraya alma modu.|
|`queuing_mode_automatic`|Bu komutların [accelerator_view](accelerator-view-class.md) nesnesine karşılık gelen bir komut kuyruğu üzerinde sıralanmış olduğunu belirten bir sıraya alma modu. [Accelerator_view:: Flush](accelerator-view-class.md#flush) çağrıldığında, komutlar cihaza gönderilir.|

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
