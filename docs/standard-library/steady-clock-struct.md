---
title: steady_clock yapısı | Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5445379597c4fefcd657303a05c33b6509d54d2e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569904"
---
# <a name="steadyclock-struct"></a>steady_clock yapısı

Temsil eden bir *sürekli* saat.

## <a name="syntax"></a>Sözdizimi

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Açıklamalar

Windows, `steady_clock` sarmalar `QueryPerformanceCounter` işlevi.

Bir saattir *monoton* durumunda ilk çağrı tarafından döndürülen değer `now` her zaman bir sonraki çağrı tarafından döndürülen değer küçük veya buna eşit olan `now`. Bir saattir *sürekli* , *monoton* ve saat saat dilimleri arasında sabit ise.

`high_resolution_clock` typedef için olan `steady_clock`.

### <a name="public-typedefs"></a>Genel tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::duration`|Eşanlamlısı `nanoseconds`, içinde tanımlı \<chrono >.|
|`steady_clock::period`|Eşanlamlısı `nano`, içinde tanımlı \<oranı >.|
|`steady_clock::rep`|Eşanlamlısı **uzun** **uzun**, kaç saat tık kapsanan örneği oluşturulmasını içinde temsil etmek için kullanılan türü `duration`.|
|`steady_clock::time_point`|Eşanlamlısı `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Genel işlevler

|İşlev|Açıklama|
|--------------|-----------------|
|`now`|Geçerli saat olarak döndürür bir `time_point` değeri.|

## <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::is_steady`|Tutan `true`. A `steady_clock` olan *sürekli*.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="see-also"></a>Ayrıca bkz.

- [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono >](../standard-library/chrono.md)
- [system_clock Yapısı](../standard-library/system-clock-structure.md)
