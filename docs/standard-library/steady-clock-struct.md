---
title: steady_clock yapısı
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 19e9f5c4dcfc7306b989605894e9a0787e0920ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412403"
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
