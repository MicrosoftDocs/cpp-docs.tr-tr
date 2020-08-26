---
title: Eşzamanlılık ad alanı sabit listeleri (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::access_type
- amp/Concurrency::queuing_mode
ms.assetid: 4c87457e-184f-4992-81ab-ca75e7d524ab
ms.openlocfilehash: 3dbb8f265706f7a4c369c80d3050cd1bfd2f5acb
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845100"
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
