---
title: 32 bit Windows saat / tarih biçimleri
ms.date: 11/04/2016
f1_keywords:
- vc.time
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
ms.openlocfilehash: 4827f82df08273dfa369d6242b9fe2be84875128
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746363"
---
# <a name="32-bit-windows-timedate-formats"></a>32 Bit Windows Saat/Tarih Biçimleri

Bit alanları olarak işaretsiz tamsayılar kullanarak dosyanın dosya saati ve tarihi ayrı ayrı depolanır. Dosyanın dosya saati ve tarihi gibi paketlenir:

### <a name="time"></a>Zaman

|Bit konumu:|0   1   2   3   4|5 6 7 8 9 A|B C D E F|
|-------------------|-----------------------|---------------------------|-----------------------|
|Uzunluk:|5|6|5|
|İçerik:|saat|dakika|2 saniyelik artışlarla|
|Değer aralığı:|0-23|0-59|0-29 2-ikinci aralıkları|

### <a name="date"></a>Tarih

|Bit konumu:|0   1   2   3   4   5   6|7 8 9 A|B C D E F|
|-------------------|-------------------------------|-------------------|-----------------------|
|Uzunluk:|7|4|5|
|İçerik:|yıl|ay|gün|
|Değer aralığı:|0-119|1-12|1-31|
||(1980 için göreli)|||

## <a name="see-also"></a>Ayrıca bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)
