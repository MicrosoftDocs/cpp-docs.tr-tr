---
title: "Tarih türü | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f1ed7eb2b467fd52545f65f98b87e8e34ad71f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="date-type"></a>Tarih türü
**Tarih** türü, 8-bayt kayan noktalı sayı kullanılarak gerçekleştirilir. Gün, 30 Aralık 1899, gece saat sıfır olarak başlayarak tamsayı artışlarla temsil edilir. Saat değerleri sayının kesirli kısmını mutlak değeri olarak ifade edilir. Aşağıdaki tabloda çeşitli tarihleri ile birlikte gösterilmektedir kendi **tarih** türü sayısal eşdeğer:  
  
|Tarih ve Saat|Gösterimi|  
|-------------------|--------------------|  
|30 Aralık 1899, gece yarısı|0.00|  
|1 Ocak 1900, gece yarısı|2.00|  
|4 Ocak 1900, gece yarısı|5.00|  
|4 Ocak 1900 ' 6'da|5.25|  
|4 Ocak 1900 ' Öğlen|5.50|  
|4 Ocak 1900 ' 9'da|5.875|  
  
 **Tarih** tarih türü yanı sıra `COleDateTime` temsil tarihler ve saatler Klasik numarası çizgi olarak sınıf. `COleDateTime` Sınıfı tarih değerlerini dönüştürme için ve diğer ortak tarih biçimleri dahil olmak üzere, işleme için birkaç yöntem içerir.  
  
 Bu tarih ve saat biçimleri otomasyon ile çalışırken, aşağıdaki noktaları bulundurulmalıdır:  
  
-   Tarihleri yerel saat belirtilir; Eşitleme el ile farklı saat diliminde tarihleri ile birlikte çalışırken gerçekleştirilmesi gerekir.  
  
-   Tarih türleri günışığından yararlanma saatine hesabı değil.  
  
-   Tarih zaman çizelgesi (30 Aralık 1899 önce) tarih değerlerini 0'dan kesintili olur. Tarih değeri tamsayılı kısmı imzalanmış kesirli bölümü kabul ederken olarak değerlendirildiğinden budur olarak imzalanmamış. Diğer bir deyişle, tarih değerinin kesirli kısmını her zaman genel mantıksal tarihe eklenirken tam sayı tarih değerinin bir parçası pozitif veya negatif olabilir. Aşağıdaki tabloda bazı örnekler gösterilmektedir:  
  
|Tarih ve Saat|Gösterimi|  
|-------------------|--------------------|  
|27 Aralık 1899, gece yarısı|-3.00|  
|28 Aralık 1899 Öğlen|-2.50|  
|28 Aralık 1899, gece yarısı|-2.00|  
|29 Aralık 1899, gece yarısı|-1.00|  
|30 Aralık 1899, 18: 00|-0.75|  
|30 Aralık 1899 Öğlen|-0.50|  
|30 Aralık 1899, 6'da|-0.25|  
|30 Aralık 1899, gece yarısı|0.00|  
|30 Aralık 1899, 6'da|0.25|  
|30 Aralık 1899 Öğlen|0.50|  
|30 Aralık 1899, 18: 00|0.75|  
|31 Aralık 1899, gece yarısı|1.00|  
|1 Ocak 1900, gece yarısı|2.00|  
|1 Ocak 1900 ' Öğlen|2.50|  
|2 Ocak 1900, gece yarısı|3.00|  
  
> [!CAUTION]
>  6: 00'da her zaman gününü temsil eden tamsayıyı (30 Aralık 1899 sonra) pozitif olmasına bakılmaksızın bir kesir değerini 0,25 tarafından temsil edilen veya negatif (önce 30 Aralık 1899), basit bir kayan nokta karşılaştırma yanlışlıkla sıralamanız gerekir çünkü unutmayın tüm **tarih** 6: 00'da 30/12/1899 ' den önceki bir tarihte temsil eden *daha sonra* değerinden bir **tarih** 7: 00'da o aynı gün temsil eden.  
  
 İle ilgili sorunlar hakkında daha fazla bilgi **tarih** ve `COleDateTime` türleri, altında bulunabilir [COleDateTime sınıfı](../atl-mfc-shared/reference/coledatetime-class.md) ve [tarih ve saat: Otomasyon desteği](../atl-mfc-shared/date-and-time-automation-support.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve saat](../atl-mfc-shared/date-and-time.md)   
 [COleDateTime Sınıfı](../atl-mfc-shared/reference/coledatetime-class.md)

