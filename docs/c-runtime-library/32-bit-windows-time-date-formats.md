---
description: 'Hakkında daha fazla bilgi edinin: 32-bit Windows saat/tarih biçimleri'
title: 32 bit Windows Time-Date biçimleri
ms.date: 11/04/2016
f1_keywords:
- vc.time
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
ms.openlocfilehash: 3893a2abc5d00cfba7ec83209470e907f87d3e94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135791"
---
# <a name="32-bit-windows-timedate-formats"></a>32 Bit Windows Saat/Tarih Biçimleri

Dosya saati ve Tarih, işaretsiz tamsayılar bit alanları olarak kullanılarak tek tek depolanır. Dosya saati ve tarihi şu şekilde paketlenmiştir:

### <a name="time"></a>Zaman

|Bit konumu:|0 1 2 3 4|5 6 7 8 9 A|B C D E F|
|-------------------|-----------------------|---------------------------|-----------------------|
|Uzunluklu|5|6|5|
|İçerik:|saat|minutes|2 saniyelik artışlarla|
|Değer aralığı:|0-23|0-59|2 saniyelik aralıklarda 0-29|

### <a name="date"></a>Tarih

|Bit konumu:|0 1 2 3 4 5 6|7 8 9 A|B C D E F|
|-------------------|-------------------------------|-------------------|-----------------------|
|Uzunluklu|7|4|5|
|İçerik:|yıl|ay|gün|
|Değer aralığı:|0-119|1-12|1-31|
||(1980 'e göre)|||

## <a name="see-also"></a>Ayrıca bkz.

[Global sabitler](../c-runtime-library/global-constants.md)
