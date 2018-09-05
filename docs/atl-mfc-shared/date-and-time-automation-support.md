---
title: 'Tarih ve saat: Otomasyon desteği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38933847065544f97d60dfc109436f059a025f7a
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763860"
---
# <a name="date-and-time-automation-support"></a>Tarih ve saat: Otomasyon desteği

Bu makalede, tarih ve saat yönetimiyle ilgili sınıf kitaplığı hizmetlerinden yararlanan açıklar. Açıklanan yordamları içerir:

- [Geçerli saati alma](../atl-mfc-shared/current-time-automation-classes.md)

- [Geçen süreyi hesaplama](../atl-mfc-shared/elapsed-time-automation-classes.md)

- [Bir tarih dize gösterimini biçimlendirme](../atl-mfc-shared/formatting-time-automation-classes.md)

[COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı tarih ve saat bilgilerini temsil etmek için bir yol sağlar. Daha iyi tanecikli ve daha büyük bir aralık sağladığı [CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfı. [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfı temsil eder, ikisi arasındaki farkı gibi belirli bir süre `COleDateTime` nesneleri.

`COleDateTime` Ve `COleDateTimeSpan` sınıfları ile kullanılmak üzere tasarlanmıştır `COleVariant` Automation'da kullanılan sınıf. `COleDateTime` ve `COleDateTimeSpan` MFC veritabanı programlama, kullanışlıdır ancak tarih ve saat değerlerini değiştirmek istediğiniz zaman kullanılabilirler. Ancak `COleDateTime` sınıfında değerleri ve hassas taneciklikten daha geniş bir yelpazede `CTime` sınıfı, bir nesne başına daha fazla depolama gerektiren `CTime`. Aynı zamanda temel alınan tarih türü ile çalışırken de bazı özel durumlar vardır. Bkz: [tarih türü](../atl-mfc-shared/date-type.md) tarih uygulanması hakkında daha fazla bilgi.

`COleDateTime` nesneleri tarihleri arasında 1 Ocak 100 ve 31 Aralık 9999 temsil etmek için kullanılabilir. `COleDateTime` 1 milisaniyelik, yaklaşık bir çözümleme nokta değerleri kayan nesneler. `COleDateTime` MFC belgelerinde altında tanımlanan tarih veri türüne dayalı [COleDateTime::operator tarih](../atl-mfc-shared/reference/coledatetime-class.md#operator_date). Gerçek tarih uygulanması bu sınırlarının ötesine genişletir. `COleDateTime` Uygulama sınıfı ile çalışmayı kolaylaştırmak için bu sınır uygular.

`COleDateTime` Jülyen tarihleri desteklemez. Gregoryen takvim geçmişe 1 Ocak 100'e genişletmek için kabul edilir.

`COleDateTime` Yaz Saati (DST) yok sayar. Aşağıdaki kod örneği DST geçiş tarihi aştığında bir zaman aralığını hesaplamak için iki yöntem karşılaştırır: bir CRT ve diğer kullanarak `COleDateTime`. Hedef üzerinde çoğu yerel ayarlarda ikinci hafta Nisan ve Ekim Ayının Üçüncü geçer.

İlk yöntem iki ayarlar `CTime` nesneleri *saat1* ve *time2*Nisan 5 ve 6 Nisan sırasıyla, standart C tür yapıları kullanarak `tm` ve `time_t`. Kod görüntüler *saat1* ve *time2* ve bunlar arasındaki zaman aralığı.

İkinci yöntem iki oluşturur `COleDateTime` nesneleri `oletime1` ve `oletime2`ve bunları aynı tarih olarak ayarlar *saat1* ve *time2*. Bu görüntüler `oletime1` ve `oletime2` ve bunlar arasındaki zaman aralığı.

CRT doğru bir 23 saat farkı hesaplar. `COleDateTimeSpan` 24 saatlik bir farkı hesaplar.

Geçici bir çözüm örneği sonuna yakın düzgün bir şekilde kullanma tarihini görüntülemek için kullanıldığını unutmayın `COleDateTime::Format`. Bilgi Bankası makalesine bakın "hata: Format("%D") başarısız için `COleDateTime` ve `COleDateTimeSpan`" (Q167338).

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[Tarih ve Saat](../atl-mfc-shared/date-and-time.md)

