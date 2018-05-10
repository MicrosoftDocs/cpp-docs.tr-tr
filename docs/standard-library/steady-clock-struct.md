---
title: steady_clock yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e1dbfac1eb8c67c5306bded6e6fd9ee8dacf54b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="steadyclock-struct"></a>steady_clock yapısı

Temsil eden bir `steady` saat.

## <a name="syntax"></a>Sözdizimi

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Açıklamalar

Windows üzerinde steady_clock QueryPerformanceCounter işlevi sarmalar.

Bir saattir *monoton* durumunda ilk çağrı tarafından döndürülen değer `now()` her zaman bir sonraki çağrı tarafından döndürülen değer küçük veya buna eşit olan `now()`.

Bir saattir *sürekli* , *monoton* ve saat saat dilimleri arasında sabit ise.

High_resolution_clock typdef steady_clock için ' dir.

## <a name="public-functions"></a>Genel işlevler

|İşlev|Açıklama|
|--------------|-----------------|
|Şimdi|Time_point değeri olarak geçerli saati döndürür.|

## <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|`system_clock::is_steady`|Tutan `true`. A `steady_clock` olan *sürekli*.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
[system_clock Yapısı](../standard-library/system-clock-structure.md)<br/>
