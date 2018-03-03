---
title: "Tarih ve saat: Otomasyon desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- adding dates
- calculating dates and times
- formatting [Visual Studio], dates
- dates, Automation support
- elapsed time, calculating in Automation
- COleDateTime class, Automation date/time support
- COleDateTimeSpan class, Automation date/time support
- Automation, date and time support
- formatting [Visual Studio], time
- calculations, date and time
- time [Visual Studio], Automation support
ms.assetid: 6eee94c4-943d-4ffc-bf7c-bdda89337ab0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a40a8fe49d9564714c328b657bc0d85d52ad84b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="date-and-time-automation-support"></a>Tarih ve saat: Otomasyon desteği
Bu makalede, tarih ve saat yönetimiyle ilgili sınıf kitaplığı Hizmetleri yararlanmak açıklar. Açıklanan yordamları içerir:  
  
-   [Geçerli saati alma](../atl-mfc-shared/current-time-automation-classes.md)  
  
-   [Geçen süre hesaplama](../atl-mfc-shared/elapsed-time-automation-classes.md)  
  
-   [Bir dize gösterimini bir tarih/saat biçimlendirme](../atl-mfc-shared/formatting-time-automation-classes.md)  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı tarih ve saat bilgilerini göstermek için bir yol sağlar. Hassas ayrıntı düzeyi ve daha büyük bir aralık sağlar [CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfı. [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfı temsil eder, ikisi arasındaki farkı gibi belirli bir süre `COleDateTime` nesneleri.  
  
 `COleDateTime` Ve `COleDateTimeSpan` sınıfları ile kullanılmak üzere tasarlanmıştır `COleVariant` Otomasyon kullanılan bir sınıftır. `COleDateTime`ve `COleDateTimeSpan` MFC veritabanı programlama kullanışlıdır ancak tarih ve saat değerlerini değiştirmek istediğiniz zaman kullanılabilirler. Rağmen `COleDateTime` sınıfına sahip değerleri ve daha hassas ayrıntı düzeyi daha geniş bir yelpazede `CTime` sınıfı, bir nesne başına daha fazla depolama alanı gerektiren `CTime`. Ayrıca vardır bazı özel durumlar arka plandaki ile çalışırken **tarih** türü. Bkz: [DATE türünde](../atl-mfc-shared/date-type.md) uygulaması hakkında daha fazla ayrıntı için **tarih**.  
  
 `COleDateTime`Nesne, tarih arasındaki 1 Ocak 100 ve 31 Aralık 9999 temsil etmek için kullanılabilir. `COleDateTime`bir yaklaşık 1 milisaniyelik çözümlenmesi ile nokta değerleri kayan nesneyi. `COleDateTime`dayanır **tarih** veri türü, MFC belgelerinde altında tanımlı [COleDateTime::operator tarih](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Gerçek uygulanması **tarih** bu sınırları genişletir. `COleDateTime` Uygulama sınıfı ile çalışmayı kolaylaştırmak için bu sınırlar uygular.  
  
 `COleDateTime`Jülyen tarihleri desteklemez. Gregoryen takvim, 1 Ocak 100'e geçmişe genişletmek için varsayılır.  
  
 `COleDateTime`gün ışığından yararlanma saati (DST) yok sayar. Aşağıdaki kod örneğinde DST geçiş tarih kestiği bir zaman aralığı hesaplamak için iki yöntem karşılaştırır: CRT kullanarak bir tane ve diğer kullanarak `COleDateTime`. DST üzerinden, çoğu yerlerde Nisan'ın ikinci hafta ve Ekim üçüncü geçer.  
  
 İlk yöntem iki ayarlar `CTime` nesneleri *saat1* ve *time2*Nisan 5 ve 6 Nisan sırasıyla standart C türü yapıları kullanarak **tm** ve `time_t`. Kod görüntüler *saat1* ve *time2* ve bunların arasındaki zaman aralığı.  
  
 İkinci yöntem iki oluşturur `COleDateTime` nesneleri `oletime1` ve `oletime2`ve aynı tarih olarak ayarlar *saat1* ve *time2*. Görüntülediği `oletime1` ve `oletime2` ve bunların arasındaki zaman aralığı.  
  
 CRT 23 saat farkını doğru olarak hesaplar. `COleDateTimeSpan`24 saatlik bir fark hesaplar.  
  
 Geçici bir çözüm örnek sonuna yakın kullanılarak uygun şekilde tarihini görüntülemek için kullanılır `COleDateTime::Format`. Bilgi Bankası makalesi "hata: Format("%D") başarısız `COleDateTime` ve `COleDateTimeSpan`" (Q167338).  
  
 [!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Tarih ve Saat](../atl-mfc-shared/date-and-time.md)

