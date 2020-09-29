---
title: TARIH türü
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
ms.openlocfilehash: 5a6c1e1cca5b2cb978d6af4208377db1a2926357
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502177"
---
# <a name="date-type"></a>TARIH türü

TARIH türü, 8 baytlık kayan noktalı sayı kullanılarak uygulanır. Günler, 30 Aralık 1899 ile başlayarak, sıfır zaman kadar gece yarısı kadar tüm sayı artışlarıyla temsil edilir. Saat değerleri, sayının kesir bölümünün mutlak değeri olarak ifade edilir. Aşağıdaki tabloda, TARIH türü sayısal eşdeğeri ile birlikte birkaç tarih gösterilmektedir:

|Tarih ve saat|İmle|
|-------------------|--------------------|
|30 Aralık 1899, gece yarısı|0.00|
|1 Ocak 1900, gece yarısı|2.00|
|4 Ocak 1900, gece yarısı|5.00|
|4 Ocak 1900, 11:00|5,25|
|4 Ocak 1900, Öğle|5,50|
|4 Ocak 1900, 13:00|5,875|

TARIH tarih türü `COleDateTime` ve sınıfının yanı sıra, tarihleri ve saatleri klasik bir sayı çizgisi olarak temsil eder. `COleDateTime`Sınıfı, diğer ortak tarih biçimlerinden ve bunlardan dönüştürme dahil olmak üzere tarih değerlerini işlemek için birkaç yöntem içerir.

Otomasyon 'da bu tarih ve saat biçimleriyle çalışırken aşağıdaki noktaların not edilmelidir:

- Tarihler yerel saat içinde belirtilir; farklı saat dilimlerindeki tarihlerle çalışırken eşitlemenin el ile gerçekleştirilmesi gerekir.

- Tarih türleri gün ışığından yararlanma saatine göre hesaba uygulanmaz.

- Tarih zaman çizelgesi 0 ' dan küçük tarih değerleri için sürekli süreklidir (30 Aralık 1899 ' dan önce). Bunun nedeni, tarih değerinin tam sayı kısmının imzalı olarak değerlendirilmesidir, ancak kesirli bölüm işaretsiz olarak kabul edilir. Diğer bir deyişle, tarih değerinin tam sayı kısmı pozitif veya negatif olabilir, ancak tarih değerinin kesirli bölümü her zaman genel mantıksal Tarih 'e eklenir. Aşağıdaki tabloda birkaç örnek gösterilmektedir:

|Tarih ve saat|İmle|
|-------------------|--------------------|
|27 Aralık 1899, gece yarısı|-3,00|
|28 Aralık 1899, Öğle|-2,50|
|28 Aralık 1899, gece yarısı|-2,00|
|29 Aralık 1899, gece yarısı|-1,00|
|30 Aralık 1899, 6 P.M.|-0,75|
|30 Aralık 1899, Öğle|-0,50|
|30 Aralık 1899, 6 saat|-0,25|
|30 Aralık 1899, gece yarısı|0.00|
|30 Aralık 1899, 6 saat|0,25|
|30 Aralık 1899, Öğle|0.50|
|30 Aralık 1899, 6 P.M.|0,75|
|31 Aralık 1899, gece yarısı|1,00|
|1 Ocak 1900, gece yarısı|2.00|
|1 Ocak 1900, Öğle|2,50|
|2 Ocak 1900, gece yarısı|3,00|

> [!CAUTION]
> 6:00 ile, günü temsil eden tamsayının pozitif mi (30 Aralık 30 1899 ' dan sonra) veya negatif (30 Aralık 1899 ' ten önce) arasında her zaman bir kesirli 0,25 değer olarak temsil edildiği için, basit bir kayan nokta karşılaştırması, aynı günde 6:00 ' ı temsil eden bir TARIHTEN *sonraki* bir tarihte, 12/30/1899 'yi temsil eden BIR günün tarihini yanlışlıkla sıralar.

TARIH ve türlerle ilgili sorunlar hakkında daha fazla bilgiyi `COleDateTime` [COleDateTime sınıfı](../atl-mfc-shared/reference/coledatetime-class.md) ve [Tarih ve saat altında bulabilirsiniz: Otomasyon desteği](./date-and-time.md).

## <a name="see-also"></a>Ayrıca bkz.

[Tarih ve Saat](../atl-mfc-shared/date-and-time.md)<br/>
[Cotadatetime sınıfı](../atl-mfc-shared/reference/coledatetime-class.md)
