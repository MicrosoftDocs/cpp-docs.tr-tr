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
ms.openlocfilehash: 53f4deb0bfe9439011f75cd22d0d52b74dae9c1f
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38959731"
---
# <a name="steadyclock-struct"></a>steady_clock yapısı

Temsil eden bir *sürekli* saati.

## <a name="syntax"></a>Sözdizimi

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Açıklamalar

Windows, şirket `steady_clock` sarmalar `QueryPerformanceCounter` işlevi.

Bir saat *monoton* varsa bir ilk çağrı tarafından döndürülen değer `now` her zaman sonraki çağrı tarafından döndürülen değer küçük veya ona eşit olduğundan `now`. Bir saat *sürekli* ise *monoton* ve saatin tik takları arasındaki zaman sabittir.

`high_resolution_clock` için bir TypeDef `steady_clock`.

### <a name="public-typedefs"></a>Genel typedefler

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::duration`|İçin bir eşanlamlı `nanoseconds`içinde tanımlanmış \<chrono >.|
|`steady_clock::period`|İçin bir eşanlamlı `nano`içinde tanımlanmış \<oranı >.|
|`steady_clock::rep`|İçin bir eşanlamlı **uzun** **uzun**, içinde içerilen saat tik taklarının sayısını belirtmek için kullanılan tür `duration`.|
|`steady_clock::time_point`|İçin bir eşanlamlı `chrono::time_point<steady_clock>`.|

## <a name="public-functions"></a>Genel işlevleri

|İşlev|Açıklama|
|--------------|-----------------|
|`now`|Olarak geçerli saati döndürür bir `time_point` değeri.|

## <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::is_steady`|Tutan **true**. A `steady_clock` olduğu *sürekli*.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="see-also"></a>Ayrıca bkz.

- [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono >](../standard-library/chrono.md)
- [system_clock Yapısı](../standard-library/system-clock-structure.md)
