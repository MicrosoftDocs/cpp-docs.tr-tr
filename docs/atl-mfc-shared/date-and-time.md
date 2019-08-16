---
title: Tarih ve Saat
ms.date: 08/13/2019
helpviewer_keywords:
- time, MFC programming
- time
- MFC, date and time
- dates, MFC
ms.assetid: ecf56dc5-d418-4603-ad3e-af7e205a6403
ms.openlocfilehash: 2a5e6977acfca51b8074399f6f9b3166c8a358bc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491305"
---
# <a name="date-and-time"></a>Tarih ve Saat

MFC, tarihler ve saatler ile çalışmanın birkaç farklı yolunu destekler:

- Otomasyon [tarihi veri türü](../atl-mfc-shared/date-type.md)için destek. Tarih, saat ve tarih/saat değerlerini destekler. [Copadatetime](../atl-mfc-shared/reference/coledatetime-class.md) ve [Cotadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfları bu işlevi kapsülle. Otomasyon desteğini kullanarak [Cotavaryant](../mfc/reference/colevariant-class.md) sınıfıyla çalışır.

- Genel amaçlı zaman sınıfları. [CTime](../atl-mfc-shared/reference/ctime-class.md) ve [CTIMESPAN](../atl-mfc-shared/reference/ctimespan-class.md) sınıfları, zaman içinde belirtilen ANSI standardı zaman kitaplığıyla ilişkili işlevselliğin çoğunu kapsüller. Olsun.

- Sistem saati desteği. MFC sürüm 3,0 ile, ' ye `CTime` Win32 `SYSTEMTIME` ve `FILETIME` veri türleri için destek eklenmiştir.

## <a name="date-and-time-automation-support"></a>Tarih ve Saat: Otomasyon desteği

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı, tarih ve saat bilgilerini temsil etmek için bir yol sağlar. [CTime](../atl-mfc-shared/reference/ctime-class.md) sınıfından daha fazla ayrıntı düzeyi ve daha büyük bir Aralık sağlar. [Cotadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıfı, iki `COleDateTime` nesne arasındaki fark gibi geçen süreyi temsil eder.

`COleDateTime` Ve `COleVariant` sınıfları sınıfıyla `COleDateTimeSpan` kullanılmak üzere tasarlanmıştır. `COleDateTime``COleDateTimeSpan` Ayrıca MFC veritabanı programlamasında de yararlıdır, ancak tarih ve saat değerlerini her işlemek istediğinizde kullanılabilirler. Sınıfında daha büyük bir değer aralığı ve `CTime` sınıftan daha ayrıntılı bir değer bulunmasına rağmen, nesne başına `CTime`daha fazla depolama alanı gerektirir. `COleDateTime` Temel alınan TARIH türüyle çalışırken bazı özel önemli noktalar da vardır. TARIH uygulama hakkında daha fazla bilgi için bkz. [Tarih türü](../atl-mfc-shared/date-type.md).

`COleDateTime`nesneler, 1 Ocak 100 ve 31 Aralık 9999 tarihleri arasında bir tarih temsil etmek için kullanılabilir. `COleDateTime`nesneler, 1 milisaniyenin yaklaşık çözünürlüğü ile kayan nokta değerleridir. `COleDateTime`, [COleDateTime:: operator Date](../atl-mfc-shared/reference/coledatetime-class.md#operator_date)altındaki MFC BELGELERINDE tanımlanan tarih veri türüne dayalıdır. TARIHIN gerçek uygulanma değeri bu sınırların ötesinde genişletilir. `COleDateTime` Uygulama, sınıfla çalışmayı kolaylaştırmak için bu sınırları uygular.

`COleDateTime`Jülyen tarihlerini desteklemez. Gregoryen takvim, zaman 1 Ocak 100 ' e kadar geri genişletileceği varsayılır.

`COleDateTime`Gün ışığından yararlanma saatini (DST) yoksayar. Aşağıdaki kod örneği, DST geçiş tarihi: biri CRT ve diğeri kullanılarak `COleDateTime`kullanılan bir zaman aralığını hesaplamaya yönelik iki yöntemi karşılaştırır.

İlk yöntem, *Time1* ve `CTime` *time2*gibi iki nesneyi, standart C türü yapılarını `tm` ve `time_t`' ı sırasıyla 5 Nisan ve 6 Nisan 'a ayarlar. Kod, *Time1* ve *time2* ve aralarındaki zaman aralığını görüntüler.

İkinci yöntem, `COleDateTime` `oletime1` ve `oletime2`ile iki nesne oluşturur ve bunları *Time1* ve *time2*ile aynı tarihlere ayarlar. `oletime1` Ve`oletime2` arasındaki zaman aralığını görüntüler.

CRT, 23 saatin farkını doğru şekilde hesaplar. `COleDateTimeSpan`24 saatin farkını hesaplar.

[!code-cpp[NVC_ATLMFC_Utilities#176](../atl-mfc-shared/codesnippet/cpp/date-and-time-automation-support_1.cpp)]

### <a name="get-the-current-time"></a>Geçerli saati al

Aşağıdaki yordamda bir `COleDateTime` nesnesinin nasıl oluşturulduğu ve geçerli zamandan nasıl başlatıldığı gösterilmektedir.

#### <a name="to-get-the-current-time"></a>Geçerli zamanı almak için

1. Bir `COleDateTime` nesne oluşturun.

1. Çağrısı `GetCurrentTime`yapın.

   [!code-cpp[NVC_ATLMFC_Utilities#177](../atl-mfc-shared/codesnippet/cpp/current-time-automation-classes_1.cpp)]

### <a name="calculate-elapsed-time"></a>Geçen süreyi hesapla

Bu yordam, iki `COleDateTime` nesne arasındaki farkın nasıl hesaplanacağını gösterir ve bir `COleDateTimeSpan` sonuç elde edin.

#### <a name="to-calculate-elapsed-time"></a>Geçen süreyi hesaplamak için

1. İki `COleDateTime` nesne oluşturun.

1. `COleDateTime` Nesnelerden birini geçerli saate ayarlayın.

1. Zaman alan bir görev gerçekleştirin.

1. Diğer `COleDateTime` nesneyi geçerli saate ayarlayın.

1. İki kat arasındaki farkı uygulayın.

   [!code-cpp[NVC_ATLMFC_Utilities#178](../atl-mfc-shared/codesnippet/cpp/elapsed-time-automation-classes_1.cpp)]

### <a name="format-a-time"></a>Saati biçimlendirme

#### <a name="to-format-a-time"></a>Bir saati biçimlendirmek için

Zaman veya geçen süreyi temsil eden bir karakter dizesi oluşturmak için [colandatetime](../atl-mfc-shared/reference/coledatetime-class.md) veya [copadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) öğesinin üyeişlevinikullanın.`Format`

   [!code-cpp[NVC_ATLMFC_Utilities#179](../atl-mfc-shared/codesnippet/cpp/formatting-time-automation-classes_1.cpp)]

Daha fazla bilgi için bkz. sınıf [Cotavariant](../mfc/reference/colevariant-class.md).

## <a name="date-and-time-database-support"></a>Tarih ve Saat: Veritabanı desteği

Sürüm 4,0 ' den başlayarak, MFC veritabanı programlama, tarih ve saat verilerini temsil etmek için [Copadatetime](../atl-mfc-shared/reference/coledatetime-class.md) ve [Copadatetimespan](../atl-mfc-shared/reference/coledatetimespan-class.md) sınıflarını kullanır. Otomasyon 'da da kullanılan bu sınıflar, sınıf [Cotavariant](../mfc/reference/colevariant-class.md)sınıfından türetilir. Bunlar, tarih ve saat verilerini, [CTime](../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)yerine yönetmek için daha iyi destek sağlar.

## <a name="date-and-time-systemtime-support"></a>Tarih ve Saat: SYSTEMTIME desteği

[Cotadatetime](../atl-mfc-shared/reference/coledatetime-class.md) sınıfı, Win32 'den sistem ve dosya sürelerini kabul eden oluşturuculara sahiptir.

Win32 `FILETIME` yapısı saati 64 bitlik bir değer olarak temsil eder. Bir `SYSTEMTIME` yapıyla iç depolama için daha kolay bir biçimdir ve dosya oluşturma zamanını temsil etmek için Win32 tarafından kullanılan biçim. SYSTEMTIME yapısı hakkında daha fazla bilgi için bkz. [SystemTime](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime). FILETIME yapısı hakkında daha fazla bilgi için bkz. [filetime](/windows/desktop/api/minwinbase/ns-minwinbase-filetime).

## <a name="see-also"></a>Ayrıca bkz.

[Tiren](../mfc/mfc-concepts.md)\
[Genel MFC Konuları](../mfc/general-mfc-topics.md)
