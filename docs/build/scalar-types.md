---
title: Ölçekli Türler
ms.date: 11/04/2016
ms.assetid: 07c9195e-b6c7-4083-8ef0-8a93032e4d1e
ms.openlocfilehash: 0c2fa18022763564a29b6a96f8ce719039dcd216
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492074"
---
# <a name="scalar-types"></a>Ölçekli Türler

Veri erişimi her hizalamadan donanımından kaynaklanabilir olsa da, veri performans kaybı (veya birden çok yapanın) önlemek için doğal sınırında hizalı önerilir. Sabit listelerinde sabit tamsayı olan ve 32 bit tamsayılar olarak kabul edilir. Aşağıdaki hizalama değerleri kullanarak hizalama ilgili olarak aşağıdaki tabloda tür tanımını ve önerilen depolama için açıklanmaktadır:

- Byte - 8 bit

- Word - 16 bit

- Çift sözcük - 32 bit

- Dörtlü Word - 64 bit

- Octa Word - 128 bit

|||||
|-|-|-|-|
|Skalar türü|C veri türü|Depolama boyutu (bayt cinsinden)|Önerilen hizalama|
|**INT8**|**char**|1.|Bayt|
|**UINT8**|**İmzasız char**|1.|Bayt|
|**INT16**|**short**|2|Word|
|**UINT16**|**İmzasız short**|2|Word|
|**INT32**|**int**, **uzun**|4|Doubleword|
|**UINT32**|**işaretsiz int, işaretsiz uzun**|4|Doubleword|
|**INT64**|**__int64**|8|Quadword|
|**UINT64**|**imzalanmamış __int64**|8|Quadword|
|**FP32 (tek duyarlık)**|**float**|4|Doubleword|
|**FP64 (çift duyarlık)**|**double**|8|Quadword|
|**İŞARETÇİ**|<strong>\*</strong>|8|Quadword|
|**__m64**|**Yapı __m64**|8|Quadword|
|**__m128**|**Yapı __m128**|16|Octaword|

## <a name="see-also"></a>Ayrıca Bkz.

[Türler ve Depolama](../build/types-and-storage.md)