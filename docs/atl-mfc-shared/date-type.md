---
title: TARİH Türü
ms.date: 11/04/2016
f1_keywords:
- DATE
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
ms.openlocfilehash: 6fd9fde83474ff4f439c0dd3989d4dc35fe1241a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317916"
---
# <a name="date-type"></a>TARİH Türü

DATE türü 8 bayt kayan nokta numarası kullanılarak uygulanır. Günler, 30 Aralık 1899'dan itibaren gece yarısı sıfır saatiyle başlayan tam sayı artışlarıyla gösterilir. Saat değerleri, sayının kesirli kısmının mutlak değeri olarak ifade edilir. Aşağıdaki tabloda, DATE türü sayısal eşdeğeri ile birlikte birkaç tarih gösterilebilir:

|Tarih ve saat|Gösterimi|
|-------------------|--------------------|
|30 Aralık 1899, gece yarısı|0,00|
|1 Ocak 1900, gece yarısı|2,00|
|4 Ocak 1900, gece yarısı|5,00|
|4 Ocak 1900, 06:00|5.25|
|4 Ocak 1900, öğlen|5.50|
|4 Ocak 1900, 21:00.|5.875|

DATE tarih türü ve `COleDateTime` sınıf, tarihleri ve saatleri klasik bir sayı satırı olarak temsil eder. Sınıf, `COleDateTime` date değerlerini işlemek için, diğer ortak tarih biçimlerine ve diğer ortak tarih biçimlerine dönüştürme de dahil olmak üzere çeşitli yöntemler içerir.

Otomasyon'da bu tarih ve saat biçimleriyle çalışırken aşağıdaki noktalara dikkat edilmelidir:

- Tarihler yerel saatle belirtilir; eşitleme, farklı saat dilimlerindeki tarihlerle çalışırken el ile yapılmalıdır.

- Tarih türleri Gün ışığından yararlanma saatini hesaba katmaz.

- Tarih zaman çizelgesi 0'dan küçük tarih değerleri için (30 Aralık 1899'dan önce) kesintili olur. Bunun nedeni, tarih değerinin tam sayı bölümünün imzalanmış olarak kabul edilirken, kesirli kısmı imzasız olarak kabul edilir. Başka bir deyişle, tarih değerinin tam sayı kısmı pozitif veya negatif olabilir, tarih değerinin kesirli kısmı ise her zaman genel mantıksal tarihe eklenir. Aşağıdaki tabloda birkaç örnek gösterilmektedir:

|Tarih ve saat|Gösterimi|
|-------------------|--------------------|
|27 Aralık 1899, gece yarısı|-3.00|
|28 Aralık 1899, öğlen|-2.50|
|28 Aralık 1899, gece yarısı|-2.00|
|29 Aralık 1899, gece yarısı|-1.00|
|30 Aralık 1899, 18:00.|-0.75|
|30 Aralık 1899, öğlen|-0.50|
|30 Aralık 1899, 06:00|-0.25|
|30 Aralık 1899, gece yarısı|0,00|
|30 Aralık 1899, 06:00|0,25|
|30 Aralık 1899, öğlen|0,50|
|30 Aralık 1899, 18:00.|0,75|
|31 Aralık 1899, gece yarısı|1,00|
|1 Ocak 1900, gece yarısı|2,00|
|1 Ocak 1900, öğlen|2.50|
|2 Ocak 1900, gece yarısı|3,00|

> [!CAUTION]
> 06:00 her zaman bir kesirli değeri 0,25 ile temsil edilir, ne olursa olsun gün temsil eden tamsayı pozitif olup olmadığını (30 Aralık sonra, 1899) veya negatif (30 Aralık 1899'dan önce), basit bir kayan nokta karşılaştırması, aynı gün 07:00'yi temsil eden bir TARİhten daha *geç* olarak, 12/30/1899'dan bir gün önce 06:00'yı temsil eden herhangi bir DATE'i hatalı bir şekilde sıralar.

TARİh ve `COleDateTime` türleri ile ilgili konular hakkında daha fazla bilgi [COleDateTime Sınıf](../atl-mfc-shared/reference/coledatetime-class.md) ve Tarih ve Saat altında [bulunabilir: Otomasyon Desteği](../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="see-also"></a>Ayrıca bkz.

[Tarih ve Saat](../atl-mfc-shared/date-and-time.md)<br/>
[COleDateTime Sınıfı](../atl-mfc-shared/reference/coledatetime-class.md)
