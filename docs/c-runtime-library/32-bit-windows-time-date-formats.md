---
title: 32 bit Windows Saat ve tarih biçimleri | Microsoft Docs
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
ms.openlocfilehash: 41a415b2601db1e7fc755903145d6dd2b6293ed9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="32-bit-windows-timedate-formats"></a>32 Bit Windows Saat/Tarih Biçimleri
Dosyanın dosya saati ve tarihi ayrı ayrı işaretsiz tamsayı bit alanları kullanılarak depolanır. Dosyanın dosya saati ve tarihi gibi paketlenmiş:  
  
### <a name="time"></a>Zaman  
  
|Bit konumu:|0   1   2   3   4|5 6 7 8 9 A|B C D E F|  
|-------------------|-----------------------|---------------------------|-----------------------|  
|Uzunluk:|5|6|5|  
|İçeriği:|saat|dakika|2-ikinci artırır|  
|Değer aralığı:|0-23|0-59|0-29 2-ikinci aralıkları|  
  
### <a name="date"></a>Tarih  
  
|Bit konumu:|0   1   2   3   4   5   6|7 8 9 A|B C D E F|  
|-------------------|-------------------------------|-------------------|-----------------------|  
|Uzunluk:|7|4|5|  
|İçeriği:|Yıl|Ay|günü|  
|Değer aralığı:|0-119|1-12|1-31|  
||(göreli 1980.)|||  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Global Sabitler](../c-runtime-library/global-constants.md)