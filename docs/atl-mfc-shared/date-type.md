---
title: Tarih türü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DATE
dev_langs:
- C++
helpviewer_keywords:
- Date data type, implementing
- Date data type
- DATE type
- Date data type, about Date data type
- MFC, date and time
- hour values representation
ms.assetid: 695853ed-b614-4575-b793-b8c287372038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 314b943b171d43f8b1723321ac3a942ed33fd100
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883472"
---
# <a name="date-type"></a>Tarih türü
Tarih türü, 8-bayt kayan noktalı sayı kullanılarak uygulanır. Gün 30 Aralık 1899, sıfır saat olarak gece yarısı ile başlayan tam sayı artışlarla tarafından temsil edilir. Saat değerleri sayının kesirli kısmını mutlak değeri ifade edilir. Aşağıdaki tabloda, çeşitli tarih tarih türü sayısal eşdeğeri ile birlikte gösterilmektedir:  
  
|Tarih ve Saat|Temsili|  
|-------------------|--------------------|  
|30 Aralık 1899, gece yarısı|0.00|  
|Gece yarısı, 1 Ocak 1900|2.00|  
|Gece yarısı 4 Ocak 1900|5.00|  
|4 Ocak 1900 ' 6'da|5.25|  
|4 Ocak 1900 Öğlen|5.50|  
|4 Ocak 1900 ' 9'da|5.875|  
  
 TARİH tarih türü olarak `COleDateTime` temsil tarihler ve saatler Klasik numarası çizgi olarak sınıf. `COleDateTime` Sınıfı için ve diğer yaygın tarih biçimleri dönüştürme de dahil olmak üzere, tarih değerlerini düzenlemek için çeşitli yöntemler içerir.  
  
 Bu tarih ve saat biçimleri otomasyon ile çalışırken aşağıdaki noktaları dikkate alınmalıdır:  
  
-   Tarihleri yerel saatle belirtilir; Eşitleme el ile farklı saat dilimlerinde tarih ile çalışırken gerçekleştirilmesi gerekir.  
  
-   Tarih türleri, gün ışığından yararlanma saatine hesap kullanılamıyor.  
  
-   Tarih zaman çizelgesi (30 Aralık 1899 önce) tarih değerleri 0'dan kesintili haline gelir. Tarih değeri tam sayı bölümü kesirli bölümü kabul ederken, oturum açmış olarak kabul edilir nedeni olarak imzalanmamış. Diğer bir deyişle, tarih değeri kesirli kısmını her zaman genel mantıksal tarihe eklenirken tarih değeri tam sayı bölümü pozitif veya negatif olabilir. Aşağıdaki tablo bazı örnekler gösterilmektedir:  
  
|Tarih ve Saat|Temsili|  
|-------------------|--------------------|  
|27 Aralık 1899, gece yarısı|-3.00|  
|28 Aralık 1899 Öğlen|-2.50|  
|28 Aralık 1899, gece yarısı|-2.00|  
|29 Aralık 1899, gece yarısı|-1.00|  
|30 Aralık 1899, 6'da|-0.75|  
|30 Aralık 1899 Öğlen|-0.50|  
|30 Aralık 1899, 6 AM|-0.25|  
|30 Aralık 1899, gece yarısı|0.00|  
|30 Aralık 1899, 6 AM|0.25|  
|30 Aralık 1899 Öğlen|0.50|  
|30 Aralık 1899, 6'da|0.75|  
|31 Aralık 1899, gece yarısı|1.00|  
|Gece yarısı, 1 Ocak 1900|2.00|  
|1 Ocak 1900 Öğlen|2.50|  
|Gece 2 Ocak 1900|3.00|  
  
> [!CAUTION]
>  6: 00'da her zaman gününü temsil eden tamsayı (30 Aralık 1899 sonra) pozitif olmasına bakılmaksızın bir kesir değerini 0,25 tarafından temsil edilen veya negatif (önce 30 Aralık 1899), basit bir kayan nokta karşılaştırma deneyebileceğinizi sıralamanız gerekir çünkü unutmayın. 6: 00'da 12/30/1899'dan önceki bir günü temsil eden herhangi bir tarih *daha sonra* 7: 00'da, aynı gün temsil eden bir tarihten.  
  
 Sorunları hakkında daha fazla bilgi için tarih ilgili ve `COleDateTime` türleri altında bulunabilir [COleDateTime sınıfı](../atl-mfc-shared/reference/coledatetime-class.md) ve [tarih ve saat: Otomasyon desteği](../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve saat](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime Sınıfı](../atl-mfc-shared/reference/coledatetime-class.md)

