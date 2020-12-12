---
description: 'Hakkında daha fazla bilgi edinin: Tarih ve saat'
title: Tarih ve Saat
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 4a8f2d5c9537f07c5d410361e79bf14a12778bc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167038"
---
# <a name="date-and-time"></a>Tarih ve Saat

MFC, tarihler ve saatler ile çalışmanın birkaç farklı yolunu destekler:

- Otomasyon [tarihi veri türü](../atl-mfc-shared/date-type.md)için destek. Tarih, saat ve tarih/saat değerlerini destekler. [Copadatetime](../atl-mfc-shared/reference/coledatetime-class.md) ve [Cotadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfları bu işlevi kapsülle. Otomasyon desteğini kullanarak [Cotavaryant](../mfc/reference/colevariant-class.md) sınıfıyla çalışır.

- Genel amaçlı zaman sınıfları. [CTime](../atl-mfc-shared/reference/ctime-class.md) ve [CTIMESPAN](../atl-mfc-shared/reference/ctimespan-class.md) sınıfları, Time. H içinde belirtilen ANSI standardı zaman kitaplığıyla ilişkili işlevselliğin çoğunu kapsüller.

- Sistem saati desteği. MFC sürüm 3,0 ile, ' ye `CTime` Win32 `SYSTEMTIME` ve veri türleri için destek eklenmiştir `FILETIME` .

## <a name="date-and-time-automation-support"></a>Tarih ve Saat: Otomasyon Desteği

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı, tarih ve saat bilgilerini temsil etmek için bir yol sağlar. [CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfından daha fazla ayrıntı düzeyi ve daha büyük bir Aralık sağlar. [Cotadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfı, iki nesne arasındaki fark gibi geçen süreyi temsil eder `COleDateTime` .

`COleDateTime`Ve `COleDateTimeSpan` sınıfları sınıfıyla kullanılmak üzere tasarlanmıştır `COleVariant` . `COleDateTime``COleDateTimeSpan`Ayrıca MFC veritabanı programlamasında de yararlıdır, ancak tarih ve saat değerlerini her işlemek istediğinizde kullanılabilirler. Sınıfında daha `COleDateTime` büyük bir değer aralığı ve sınıftan daha ayrıntılı bir değer bulunmasına rağmen `CTime` , nesne başına daha fazla depolama alanı gerektirir `CTime` . Temel alınan TARIH türüyle çalışırken bazı özel önemli noktalar da vardır. TARIH uygulama hakkında daha fazla bilgi için bkz. [Tarih türü](../atl-mfc-shared/date-type.md).

`COleDateTime` nesneler, 1 Ocak 100 ve 31 Aralık 9999 tarihleri arasında bir tarih temsil etmek için kullanılabilir. `COleDateTime` nesneler, 1 milisaniyenin yaklaşık çözünürlüğü ile kayan nokta değerleridir. `COleDateTime` , [COleDateTime:: operator Date](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)altındaki MFC BELGELERINDE tanımlanan tarih veri türüne dayalıdır. TARIHIN gerçek uygulanma değeri bu sınırların ötesinde genişletilir. `COleDateTime`Uygulama, sınıfla çalışmayı kolaylaştırmak için bu sınırları uygular.

`COleDateTime` Jülyen tarihlerini desteklemez. Gregoryen takvim, zaman 1 Ocak 100 ' e kadar geri genişletileceği varsayılır.

`COleDateTime` Gün ışığından yararlanma saatini (DST) yoksayar. Aşağıdaki kod örneği, DST geçiş tarihi: biri CRT ve diğeri kullanılarak kullanılan bir zaman aralığını hesaplamaya yönelik iki yöntemi karşılaştırır `COleDateTime` .

İlk yöntem `CTime` , *Time1* ve *time2* gibi iki nesneyi, standart C türü yapılarını ve ' ı sırasıyla 5 Nisan ve 6 Nisan 'a ayarlar `tm` `time_t` . Kod, *Time1* ve *time2* ve aralarındaki zaman aralığını görüntüler.

İkinci yöntem, ve ile iki `COleDateTime` nesne `oletime1` oluşturur `oletime2` ve bunları *Time1* ve *time2* ile aynı tarihlere ayarlar. `oletime1`Ve `oletime2` arasındaki zaman aralığını görüntüler.

CRT, 23 saatin farkını doğru şekilde hesaplar. `COleDateTimeSpan` 24 saatin farkını hesaplar.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>Geçerli saati al

Aşağıdaki yordamda bir nesnesinin nasıl oluşturulduğu `COleDateTime` ve geçerli zamandan nasıl başlatıldığı gösterilmektedir.

#### <a name="to-get-the-current-time"></a>Geçerli zamanı almak için

1. Bir `COleDateTime` nesne oluşturun.

1. Çağrısı yapın `GetCurrentTime` .

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>Geçen süreyi hesapla

Bu yordam, iki nesne arasındaki farkın nasıl hesaplanacağını gösterir `COleDateTime` ve bir sonuç elde edin `COleDateTimeSpan` .

#### <a name="to-calculate-elapsed-time"></a>Geçen süreyi hesaplamak için

1. İki `COleDateTime` nesne oluşturun.

1. `COleDateTime`Nesnelerden birini geçerli saate ayarlayın.

1. Zaman alan bir görev gerçekleştirin.

1. Diğer `COleDateTime` nesneyi geçerli saate ayarlayın.

1. İki kat arasındaki farkı uygulayın.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>Saati biçimlendirme

#### <a name="to-format-a-time"></a>Bir saati biçimlendirmek için

`Format`Zaman veya geçen süreyi temsil eden bir karakter dizesi oluşturmak Için [Colandatetime](../atl-mfc-shared/reference/coledatetime-class.md) veya [copadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) öğesinin üye işlevini kullanın.

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

Daha fazla bilgi için bkz. sınıf [Cotavariant](../mfc/reference/colevariant-class.md).

## <a name="date-and-time-database-support"></a>Tarih ve Saat: Veritabanı Desteği

Sürüm 4,0 ' den başlayarak, MFC veritabanı programlama, tarih ve saat verilerini temsil etmek için [Copadatetime](../atl-mfc-shared/reference/coledatetime-class.md) ve [Copadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıflarını kullanır. Otomasyon 'da da kullanılan bu sınıflar, sınıf [Cotavariant](../mfc/reference/colevariant-class.md)sınıfından türetilir. Bunlar, tarih ve saat verilerini, [CTime](../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)yerine yönetmek için daha iyi destek sağlar.

## <a name="date-and-time-systemtime-support"></a>Tarih ve Saat: SYSTEMTIME Desteği

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı, Win32 'den sistem ve dosya sürelerini kabul eden oluşturuculara sahiptir.

Win32 `FILETIME` yapısı saati 64 bitlik bir değer olarak temsil eder. Bir yapıyla iç depolama için daha kolay bir biçimdir `SYSTEMTIME` ve dosya oluşturma zamanını temsil etmek Için Win32 tarafından kullanılan biçim. SYSTEMTIME yapısı hakkında daha fazla bilgi için bkz. [SystemTime](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). FILETIME yapısı hakkında daha fazla bilgi için bkz. [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../mfc/mfc-concepts.md)\
[Genel MFC konuları](../mfc/general-mfc-topics.md)
