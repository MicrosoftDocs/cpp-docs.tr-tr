---
title: steady_clock yapısı
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: d21d5c2ed7ed667333007f3bd12d13f47b868380
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217408"
---
# <a name="steady_clock-struct"></a>steady_clock yapısı

*Sabit* bir saati temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Açıklamalar

Windows üzerinde `steady_clock` işlevi sarmalanmış `QueryPerformanceCounter` .

Bir saat, *monotonic* bir ilk çağrı tarafından döndürülen değer `now` her zaman bir sonraki çağrısıyla döndürülen değerden küçük veya ona eşit ise monoton 'dir `now` . Bir saat *monoton* ise ve saat işaretleri arasındaki süre *sabittir ise sabit olur.*

`high_resolution_clock`için bir typedef `steady_clock` .

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::duration`|İçin bir eş anlamlı `nanoseconds` , içinde tanımlanır \<chrono> .|
|`steady_clock::period`|İçin bir eş anlamlı `nano` , içinde tanımlanır \<ratio> .|
|`steady_clock::rep`|İçin bir eş anlamlı **`long long`** , öğesinin içerilen örneklemede saat işaretleri sayısını temsil etmek için kullanılan tür `duration` .|
|`steady_clock::time_point`|İçin bir eş anlamlı `chrono::time_point<steady_clock>` .|

## <a name="public-functions"></a>Ortak işlevler

|İşlev|Açıklama|
|--------------|-----------------|
|`now`|Geçerli saati bir değer olarak döndürür `time_point` .|

## <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|`steady_clock::is_steady`|Tutar **`true`** . Bir `steady_clock` *sabit*değer.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std:: hatası

## <a name="see-also"></a>Ayrıca bkz.

- [Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock Yapısı](../standard-library/system-clock-structure.md)
