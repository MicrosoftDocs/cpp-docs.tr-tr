---
title: 32 bit Windows saat / tarih biçimleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- vc.time
dev_langs:
- C++
helpviewer_keywords:
- 32-bit Windows
ms.assetid: ef1589db-84d7-4b24-8799-7c7a22cfe2bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55eca447de7818f749628505a4c4f2fa6eb0dcd2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061122"
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
|İçerik:|Yıl|Ay|gün|
|Değer aralığı:|0-119|1-12|1-31|
||(1980 için göreli)|||

## <a name="see-also"></a>Ayrıca Bkz.

[Global Sabitler](../c-runtime-library/global-constants.md)