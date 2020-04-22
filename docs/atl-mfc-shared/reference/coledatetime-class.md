---
title: COleDateTime Sınıfı
ms.date: 03/27/2019
f1_keywords:
- COleDateTime
- ATLCOMTIME/ATL::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::COleDateTime
- ATLCOMTIME/ATL::COleDateTime::Format
- ATLCOMTIME/ATL::COleDateTime::GetAsDBTIMESTAMP
- ATLCOMTIME/ATL::COleDateTime::GetAsSystemTime
- ATLCOMTIME/ATL::COleDateTime::GetAsUDATE
- ATLCOMTIME/ATL::COleDateTime::GetCurrentTime
- ATLCOMTIME/ATL::COleDateTime::GetDay
- ATLCOMTIME/ATL::COleDateTime::GetDayOfWeek
- ATLCOMTIME/ATL::COleDateTime::GetDayOfYear
- ATLCOMTIME/ATL::COleDateTime::GetHour
- ATLCOMTIME/ATL::COleDateTime::GetMinute
- ATLCOMTIME/ATL::COleDateTime::GetMonth
- ATLCOMTIME/ATL::COleDateTime::GetSecond
- ATLCOMTIME/ATL::COleDateTime::GetStatus
- ATLCOMTIME/ATL::COleDateTime::GetYear
- ATLCOMTIME/ATL::COleDateTime::ParseDateTime
- ATLCOMTIME/ATL::COleDateTime::SetDate
- ATLCOMTIME/ATL::COleDateTime::SetDateTime
- ATLCOMTIME/ATL::COleDateTime::SetStatus
- ATLCOMTIME/ATL::COleDateTime::SetTime
- ATLCOMTIME/ATL::COleDateTime::m_dt
- ATLCOMTIME/ATL::COleDateTime::m_status
helpviewer_keywords:
- shared classes, COleDateTime
- time-only values
- Date data type, MFC encapsulation of
- COleDateTime class
- dates, handling in MFC
- time, handling in MFC
ms.assetid: e718f294-16ec-4649-88b6-a4dbae5178fb
ms.openlocfilehash: 8ba09430427b6ece8ae5956912cbcc40fb33fcf2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81747165"
---
# <a name="coledatetime-class"></a>COleDateTime Sınıfı

OLE otomasyonunda `DATE` kullanılan veri türünü kapsüller.

## <a name="syntax"></a>Sözdizimi

```
class COleDateTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTime::COleDateTime](#coledatetime)|Bir `COleDateTime` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTime::Biçim](#format)|Nesnenin biçimlendirilmiş dize `COleDateTime` temsilini oluşturur.|
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|`COleDateTime` Nesnedeki zamanı veri yapısı olarak elde etmek için bu yöntemi çağırın. `DBTIMESTAMP`|
|[COleDateTime::GetAsSystemTime](#getassystemtime)|`COleDateTime` [SystemTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) veri yapısı olarak nesnedeki zamanı elde etmek için bu yöntemi arayın.|
|[COleDateTime::GetAsUDATE](#getasudate)|Bir veri yapısı `COleDateTime` olarak zaman elde etmek için bu yöntemi arayın. `UDATE`|
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Geçerli zamanı `COleDateTime` (statik üye işlev) temsil eden bir nesne oluşturur.|
|[COleDateTime::GetDay](#getday)|Bu `COleDateTime` nesnenin temsil olduğu günü döndürür (1 - 31).|
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Bu `COleDateTime` nesnenin temsil olduğu haftanın gününü verir (Pazar = 1).|
|[COleDateTime::GetDayOfYear](#getdayofyear)|Bu `COleDateTime` nesnenin temsil olduğu yılın gününü döndürür (1 Ocak = 1).|
|[COleDateTime::GetHour](#gethour)|Bu `COleDateTime` nesnenin temsil ettiği saati döndürür (0 - 23).|
|[COleDateTime::GetMinute](#getminute)|Bu `COleDateTime` nesnenin temsil içarırım ışığını (0 - 59) döndürür.|
|[COleDateTime::GetMonth](#getmonth)|Bu `COleDateTime` nesnenin temsil olduğu ayı döndürür (1 - 12).|
|[COleDateTime::GetSecond](#getsecond)|Bu `COleDateTime` nesnenin temsil oluşturduğu ikinci nesneyi döndürür (0 - 59).|
|[COleDateTime::GetStatus](#getstatus)|Bu `COleDateTime` nesnenin durumunu (geçerliliğini) alır.|
|[COleDateTime::GetYear](#getyear)|Bu `COleDateTime` nesnenin temsil olduğu yılı döndürür.|
|[COleDateTime::ParseDateTime](#parsedatetime)|Bir dizeden tarih/saat değerini okur ve `COleDateTime`değerini ayarlar.|
|[COleDateTime::SetDate](#setdate)|Bu `COleDateTime` nesnenin değerini belirtilen yalnızca tarih değerine ayarlar.|
|[COleDateTime::SetDateTime](#setdatetime)|Bu `COleDateTime` nesnenin değerini belirtilen tarih/saat değerine ayarlar.|
|[COleDateTime::SetStatus](#setstatus)|Bu `COleDateTime` nesnenin durumunu (geçerliliğini) ayarlar.|
|[COleDateTime::SetTime](#settime)|Bu `COleDateTime` nesnenin değerini belirtilen yalnızca zaman değerine ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTime::operator ==, COleDateTime::operator <, vb.](#coledatetime_relational_operators)|İki `COleDateTime` değeri karşılaştırın.|
|[COleDateTime::operatör +, COleDateTime::operator -](#operator_add_-)|`COleDateTime` Değer ekleme ve çıkarma.|
|[COleDateTime::operatör +=, COleDateTime::operator -=](#operator_add_eq_-_eq)|Bu `COleDateTime` nesneden `COleDateTime` bir değer ekleyin ve çıkarın.|
|[COleDateTime::operator =](#operator_eq)|Bir `COleDateTime` değeri kopyalar.|
|[COleDateTime::operatör Tarİhİ, COleDateTime::operatör Tarihi*](#operator_date)|Bir `COleDateTime` değeri bir `DATE` veya `DATE*`bir değere dönüştürür.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[COleDateTime::m_dt](#m_dt)|Bu `DATE` `COleDateTime` nesnenin altında yatan altkını içerir.|
|[COleDateTime::m_status](#m_status)|Bu `COleDateTime` nesnenin durumunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleDateTime`taban sınıfa sahip değildir.

OLE otomasyonunun [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) veri türü için olası türlerden biridir. Değer `COleDateTime` mutlak bir tarih ve saat değerini temsil eder.

Tür `DATE` kayan nokta değeri olarak uygulanır. Günler 30 Aralık 1899 gece yarısı ölçülür. Aşağıdaki tabloda bazı tarihler ve ilişkili değerleri gösterilmektedir:

|Tarih|Değer|
|----------|-----------|
|29 Aralık 1899, gece yarısı|-1.0|
|29 Aralık 1899, 06:00|-1.25|
|30 Aralık 1899, gece yarısı|0,0|
|31 Aralık 1899, gece yarısı|1.0|
|1 Ocak 1900, sabah 6.00.|2.25|

> [!CAUTION]
> Yukarıdaki tabloda, gün değerleri 30 Aralık 1899 gece yarısından önce negatif olmasına rağmen, gün değerleri yok. Örneğin, 06:00 her zaman günü temsil eden tamsayının pozitif mi yoksa negatif mi (30 Aralık 1899'dan önce) olduğuna bakılmaksızın 0,25 kesirli bir değerle temsil edilir. Bu, basit bir kayan nokta karşılaştırmasının, `COleDateTime` 29/1899'da 06:00'da, aynı gün 07:00'yi temsil eden bir kişiden daha **geç** bir şekilde hatalı bir şekilde sıraladığı anlamına gelir.

Sınıf `COleDateTime` 1 Ocak 100 ile 31 Aralık 9999 tarihleri işler. Sınıf `COleDateTime` Gregoryen takvimini kullanır; Julian tarihlerini desteklemiyor. `COleDateTime`Gün ışığından yararlanma saatini yok sayar. (Bkz. [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> `%y` Biçimi, yalnızca 1900'den başlayan tarihler için iki basamaklı bir yıl almak için kullanabilirsiniz. `%y` Biçimi 1900'den önceki bir tarihte kullanırsanız, kod bir ASSERT hatası oluşturur.

Bu tür, yalnızca tarih veya yalnızca zaman değerlerini temsil etmek için de kullanılır. Sözleşmeye göre, 0 tarihi (30 Aralık 1899) yalnızca zaman değerleri için kullanılır ve saat 00:00 (gece yarısı) yalnızca tarih değerleri için kullanılır.

`COleDateTime` Bir nesneyi 100'den az bir tarih kullanarak oluşturursanız, tarih `GetYear`kabul `GetMonth` `GetDay`edilir, ancak sonraki aramalar , `GetHour`, `GetMinute`, , ve `GetSecond` başarısız ve return -1. Önceden, iki basamaklı tarihler kullanabilirsiniz, ancak tarihler MFC 4.2 ve sonraki 100 veya daha büyük olmalıdır.

Sorunları önlemek için dört basamaklı bir tarih belirtin. Örneğin:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

`COleDateTime` Değerler için temel aritmetik işlemler eşlik eden sınıf [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md)kullanın. `COleDateTimeSpan`değerler bir zaman aralığı tanımlar. Bu sınıflar arasındaki ilişki CTime ve [CTimeSpan](../../atl-mfc-shared/reference/ctime-class.md) arasındakine benzer. [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)

Sınıflar `COleDateTime` ve sınıflar `COleDateTimeSpan` hakkında daha fazla bilgi için Tarih ve [Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ATLComTime.h

## <a name="coledatetime-relational-operators"></a><a name="coledatetime_relational_operators"></a>COleDateTime İlişkisel Operatörler

Karşılaştırma işleçleri.

```
bool operator==(const COleDateTime& date) const throw();
bool operator!=(const COleDateTime& date) const throw();
bool operator<(const COleDateTime& date) const throw();
bool operator>(const COleDateTime& date) const throw();
bool operator<=(const COleDateTime& date) const throw();
bool operator>=(const COleDateTime& date) const throw();
```

### <a name="parameters"></a>Parametreler

*Tarih*<br/>
Karşılaştırılacak `COleDateTime` nesne.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> İki operanddan biri geçersizse bir ATLASSERT oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Örnek

**>=** İşleçler **>**, **<** ** \< **, ve `COleDateTime` , nesne null ayarlanırsa iddia edecektir.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

## <a name="coledatetimecoledatetime"></a><a name="coledatetime"></a>COleDateTime::COleDateTime

Bir `COleDateTime` nesne inşa eder.

```
COleDateTime() throw();
COleDateTime(const VARIANT& varSrc) throw();
COleDateTime(DATE dtSrc) throw();
COleDateTime(time_t timeSrc) throw();
COleDateTime(__time64_t timeSrc) throw();
COleDateTime(const SYSTEMTIME& systimeSrc) throw();
COleDateTime(const FILETIME& filetimeSrc) throw();

COleDateTime(int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();

COleDateTime(WORD wDosDate,
    WORD wDosTime) throw();
COleDateTime(const DBTIMESTAMP& timeStamp) throw();
```

### <a name="parameters"></a>Parametreler

*tarihSrc*<br/>
Varolan `COleDateTime` bir nesne yeni `COleDateTime` nesneye kopyalanacak.

*varSrc*<br/>
Tarih/saat değerine `COleVariant` (VT_DATE) dönüştürülecek ve yeni `COleDateTime` nesneye kopyalanacak varolan `VARIANT` bir veri yapısı (büyük olasılıkla bir nesne).

*dtSrc*<br/>
Yeni `COleDateTime` nesneye`DATE`kopyalanacak tarih/saat ( ) değeri.

*zamanSrc*<br/>
Tarih/saat değerine dönüştürülecek ve yeni `time_t` `__time64_t` `COleDateTime` nesneye kopyalanacak a veya değer.

*systimeSrc*<br/>
Tarih/saat değerine dönüştürülecek ve yeni `SYSTEMTIME` `COleDateTime` nesneye kopyalanacak bir yapı.

*filetimeSrc*<br/>
Tarih/saat değerine dönüştürülecek ve yeni `FILETIME` `COleDateTime` nesneye kopyalanacak bir yapı. A, `FILETIME` Evrensel Eşgüdümlü Süre 'yi (UTC) kullanır, bu nedenle yapıda yerel bir saati geçerseniz, sonuçlarınız yanlış olur. Daha fazla bilgi için Windows SDK'daki [Dosya Süreleri'ne](/windows/win32/SysInfo/file-times) bakın.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Yeni `COleDateTime` nesneye kopyalanacak tarih ve saat değerlerini belirtin.

*wDosTarih*, *wDosTime*<br/>
MS-DOS tarih ve saat değerleri tarih/saat değerine dönüştürülür ve `COleDateTime` yeni nesneye kopyalanır.

*Zaman damgası*<br/>
Geçerli yerel saati içeren bir [DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular, belirtilen değere başlalanan yeni `COleDateTime` nesneler oluştururlar. Aşağıdaki tablo, her tarih ve saat bileşeni için geçerli aralıkları gösterir:

|Tarih/saat bileşeni|Geçerli aralık|
|--------------------------|-----------------|
|yıl|100 - 9999|
|ay|0 - 12|
|gün|0 - 31|
|saat|0 - 23|
|dakika|0 - 59|
|saniye|0 - 59|

Gün bileşeni için gerçek üst sınır ay ve yıl bileşenlerine bağlı olarak değişir unutmayın. Ayrıntılar için, `SetDate` bkz. `SetDateTime`

Aşağıda her yapıcının kısa bir açıklaması vereme

- `COleDateTime(`**)** 0'a başlatılanmış bir `COleDateTime` nesne inşa eder (gece yarısı, 30 Aralık 1899).

- `COleDateTime(``dateSrc` **)** Varolan `COleDateTime` bir nesneden bir nesne yi yitir. `COleDateTime`

- `COleDateTime(`*varSrc* **)** Bir `COleDateTime` nesne yi kurar. Bir `VARIANT` yapıyı veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesini bir `VT_DATE`tarih/saat () değerine dönüştürmeye çalışır. Bu dönüşüm başarılı olursa, dönüştürülen değer yeni `COleDateTime` nesneye kopyalanır. Değilse, nesnenin `COleDateTime` değeri 0 (gece yarısı, 30 Aralık 1899) ve durumu geçersiz olarak ayarlanır.

- `COleDateTime(``dtSrc` **)** Bir `COleDateTime` `DATE` değerden bir nesne inşa eder.

- `COleDateTime(``timeSrc` **)** Bir `COleDateTime` `time_t` değerden bir nesne inşa eder.

- `COleDateTime(`*systimeSrc* **)** Bir `COleDateTime` `SYSTEMTIME` değerden bir nesne yi kurar.

- `COleDateTime(``filetimeSrc` **)** Bir `COleDateTime` `FILETIME` değerden bir nesne inşa eder. . A, `FILETIME` Evrensel Eşgüdümlü Süre 'yi (UTC) kullanır, bu nedenle yapıda yerel bir saati geçerseniz, sonuçlarınız yanlış olur. Daha fazla bilgi için Windows SDK'daki [Dosya Süreleri'ne](/windows/win32/SysInfo/file-times) bakın.

- `COleDateTime(``nYear`, `nMonth` `nDay`, `nHour` `nMin`, `nSec` , , `COleDateTime` **)** Bir nesneyi belirtilen sayısal değerlerden yapıları.

- `COleDateTime(``wDosDate`, `wDosTime` **)** Belirtilen `COleDateTime` MS-DOS tarih ve saat değerlerinden bir nesne yapar.

`time_t` Veri türü hakkında daha fazla bilgi *için, Çalışma Zamanı Kitaplığı Başvurusu'ndaki* [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevine bakın.

Daha fazla bilgi için Windows SDK'daki [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapılarına bakın.

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

> [!NOTE]
> Parametre kullanan `DBTIMESTAMP` yapıcı yalnızca OLEDB.h dahil edildiğinde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

## <a name="coledatetimeformat"></a><a name="format"></a>COleDateTime::Biçim

Tarih/saat değerinin biçimlendirilmiş bir temsilini oluşturur.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*Dwflags*<br/>
Aşağıdaki yerel bayraklardan birini gösterir:

- LOCALE_NOUSEROVERRIDE Özel kullanıcı ayarları yerine sistemin varsayılan yerel ayarları kullanın.

- VAR_TIMEVALUEONLY Ayrışdırma sırasında tarih kısmını yoksayın.

- VAR_DATEVALUEONLY Ayrışdırma sırasında zaman kısmını yoksay.

*lcid*<br/>
Dönüşüm için kullanılacak yerel kimliği gösterir. Dil tanımlayıcıları hakkında daha fazla bilgi için [Dil Tanımlayıcıları'na](/windows/win32/Intl/language-identifiers)bakın.

*lpszFormat*<br/>
Biçimlendirme dizesine `printf` benzer bir biçimlendirme dizesi. Yüzde () `%`işaretinden önce gelen her biçimlendirme kodu, `COleDateTime` ilgili bileşentarafından değiştirilir. Biçimlendirme dizesindeki diğer karakterler döndürülen dize değişmeden kopyalanır. Daha fazla bilgi için çalışma zamanı işlevini [niçin](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)bkz. Biçimlendirme kodlarının değeri ve `Format` anlamı şunlardır:

- `%H`Geçerli gündeki saatler

- `%M`Geçerli saatteki dakikalar

- `%S`Geçerli dakikadaki saniyeler

- `%%`Yüzde işareti

*nFormatID*<br/>
Biçim denetimi dizesi için kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş tarih/saat değerini içeren a. `CString`

### <a name="remarks"></a>Açıklamalar

Bu `COleDateTime` nesnenin durumu null ise, döndürme değeri boş bir dize. Durum geçersizse, geri dönüş dizesi dize kaynak ATL_IDS_DATETIME_INVALID tarafından belirtilir.

Bu işlev için üç formun kısa bir açıklaması aşağıdaki gibidir:

`Format`( *dwFlags*, *lcid*)<br/>
Bu form, tarih ve saat için dil belirtimlerini (yerel işlmeler) kullanarak değeri biçimlendiriyor. Varsayılan parametreleri kullanarak, bu form, saat kısmı 0 (gece yarısı) olmadığı sürece, tarih ve saati yazdırır, bu durumda yalnızca tarihi yazdırır veya tarih kısmı 0 (30 Aralık 1899) olur ve bu durumda yalnızca zamanı yazdırır. Tarih/saat değeri 0 ise (30 Aralık 1899, gece yarısı), varsayılan parametreleri olan bu form gece yarısı yazdırılır.

`Format`( *lpszFormat*)<br/>
Bu form, yüzde işaretinden önce gelen özel biçimlendirme kodlarını içeren biçim dizesini `printf`kullanarak değeri biçimlendirmektedir.) Biçimlendirme dizesi işleve parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için, Run-Time Kitaplığı Başvurusu'nda [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) adresine bakın.

`Format`( *nFormatID*)<br/>
Bu form, yüzde işaretinden önce gelen özel biçimlendirme kodlarını içeren biçim dizesini `printf`kullanarak değeri biçimlendirmektedir.) Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağının kimliği parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi *için, Run-Time Kitaplığı Başvurusu'nda* [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) adresine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

## <a name="coledatetimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>COleDateTime::GetAsDBTIMESTAMP

`COleDateTime` Nesnedeki zamanı veri yapısı olarak elde etmek için bu yöntemi çağırın. `DBTIMESTAMP`

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Parametreler

*Zaman damgası*<br/>
[DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan zamanı başvurulan *zamanDamga* yapısında saklar. Bu `DBTIMESTAMP` işlev tarafından ortaya alınan veri `fraction` yapısı, üyesini sıfıra ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

## <a name="coledatetimegetassystemtime"></a><a name="getassystemtime"></a>COleDateTime::GetAsSystemTime

`COleDateTime` Nesnedeki zamanı veri yapısı olarak elde etmek için bu yöntemi çağırın. `SYSTEMTIME`

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Parametreler

*sysTime*<br/>
Nesneden dönüştürülen tarih/saat değerini almak için [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına `COleDateTime` yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Dönüştürme başarısız olursa veya nesne `COleDateTime` NULL veya geçersizse FALSE.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime`ortaya çıkan zamanı başvurulan *sysTime* nesnesinde depolar. Bu `SYSTEMTIME` işlev tarafından ortaya alınan veri `wMilliseconds` yapısı, üyesini sıfıra ayarlar.

Bir `COleDateTime` nesnede tutulan durum bilgileri hakkında daha fazla bilgi için [GetStatus'a](#getstatus)bakın.

## <a name="coledatetimegetasudate"></a><a name="getasudate"></a>COleDateTime::GetAsUDATE

`COleDateTime` Nesnedeki zamanı veri yapısı olarak elde etmek için bu yöntemi çağırın. `UDATE`

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Parametreler

*Udate*<br/>
Nesneden dönüştürülen tarih/saat değerini almak için `UDATE` `COleDateTime` bir yapıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Dönüştürme başarısız olursa veya nesne `COleDateTime` NULL veya geçersizse FALSE.

### <a name="remarks"></a>Açıklamalar

Bir `UDATE` yapı "paketlenmemiş" tarihi temsil eder.

## <a name="coledatetimegetcurrenttime"></a><a name="getcurrenttime"></a>COleDateTime::GetCurrentTime

Geçerli tarih/saat değerini döndürmek için bu statik üye işlevini çağırın.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

## <a name="coledatetimegetday"></a><a name="getday"></a>COleDateTime::GetDay

Bu tarih/saat değeriyle temsil edilen ayın gününü alır.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen ayın `COleDateTime::error` günü veya gün elde edilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 1 ile 31 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

## <a name="coledatetimegetdayofweek"></a><a name="getdayofweek"></a>COleDateTime::GetDayOfWeek

Bu tarih/saat değeriyle temsil edilen ayın gününü alır.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen haftanın `COleDateTime::error` günü veya haftanın günü elde edilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 1 ile 7 arasında değişir, burada 1=Pazar, 2=Pazartesi, ve saire.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

## <a name="coledatetimegetdayofyear"></a><a name="getdayofyear"></a>COleDateTime::GetDayOfYear

Bu tarih/saat değeriyle temsil edilen yılın gününü alır.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen yılın `COleDateTime::error` günü veya yılın günü elde edilenemese.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 1 ile 366 arasında değişir ve 1 Ocak = 1.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

## <a name="coledatetimegethour"></a><a name="gethour"></a>COleDateTime::GetHour

Bu tarih/saat değeriyle temsil edilen saati alır.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen `COleDateTime::error` saat veya saat elde edilemediyse.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 0 ile 23 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

## <a name="coledatetimegetminute"></a><a name="getminute"></a>COleDateTime::GetMinute

Bu tarih/saat değeriyle temsil edilen dakikayı alır.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen `COleDateTime::error` dakika veya dakika elde edilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 0 ile 59 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="coledatetimegetmonth"></a><a name="getmonth"></a>COleDateTime::GetMonth

Bu tarih/saat değeriyle temsil edilen ayı alır.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen `COleDateTime::error` ay veya ay elde edilemediyse.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 1 ile 12 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[GetDay](#getday)için örneğe bakın.

## <a name="coledatetimegetsecond"></a><a name="getsecond"></a>COleDateTime::GetSecond

Bu tarih/saat değeriyle temsil edilen ikinci sini alır.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İkinci bu `COleDateTime` nesnenin değeri ile `COleDateTime::error` temsil veya ikinci elde edilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri 0 ile 59 arasında değişir.

> [!NOTE]
> Sınıf `COleDateTime` artık saniyeleri desteklemez.

Uygulama hakkında daha fazla `COleDateTime`bilgi için , makale tarih [ve saat bakın: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="coledatetimegetstatus"></a><a name="getstatus"></a>COleDateTime::GetStatus

Belirli `COleDateTime` bir nesnenin durumunu (geçerliliğini) alır.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` değerin durumunu döndürür. Varsayılan olarak `GetStatus` oluşturulmuş `COleDateTime` bir nesneyi çağırırsanız, geçerli olarak döndürecektir. Null olarak `GetStatus` ayarlanmış `COleDateTime` kurucu ile başharfe bünyesine sahip bir nesneyi çağırırsanız, `GetStatus` null döndürülecektir.

### <a name="remarks"></a>Açıklamalar

İade değeri, `DateTimeStatus` `COleDateTime` sınıf içinde tanımlanan numaralandırılmış türtarafından tanımlanır.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Bu durum değerlerinin kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTime::error`Tarih/saat değerinin bir parçasını almaya çalışırken bir hata oluştuğunu gösterir.

- `COleDateTime::valid`Bu `COleDateTime` nesnenin geçerli olduğunu gösterir.

- `COleDateTime::invalid`Bu `COleDateTime` nesnenin geçersiz olduğunu gösterir; diğer bir gerçek, değeri yanlış olabilir.

- `COleDateTime::null`Bu `COleDateTime` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlandığını gösterir. (Bu, C++ NULL'un aksine veritabanında "değer sahibi olma" anlamında "null"dur.)

Bir `COleDateTime` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri, tarih/saat `VARIANT` değerine dönüştürülmeyen bir veya `COleVariant` değerden ayarlanırsa.

- Değeri , `time_t`bir , `SYSTEMTIME`veya `FILETIME` geçerli bir tarih/saat değerine dönüştürülemeyecek değerden ayarlanırsa.

- Değeri geçersiz parametre `SetDateTime` değerleri ile ayarlanırsa.

- Bu nesne bir aritmetik atama işlemi sırasında bir taşma `+=` veya `-=`taşma yaşadıysa, yani .

- Bu nesneye geçersiz bir değer atandıysa.

- Bu nesnenin durumu açıkça kullanılarak `SetStatus`geçersiz olarak ayarlanmışsa.

Durumu geçersiz duruma göre ayarlayabilen işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Coledatetime](#coledatetime)

- [Setdatetime](#setdatetime)

- [işleç +, -](#operator_add_-)

- [işleç +=, -=](#operator_add_eq_-_eq)

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

## <a name="coledatetimegetyear"></a><a name="getyear"></a>COleDateTime::GetYear

Bu tarih/saat değeriyle temsil edilen yılı alır.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeriyle temsil edilen `COleDateTime::error` yıl veya yıl elde edilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli iade değerleri yüzyılı içeren 100 ile 9999 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[GetDay](#getday)için örneğe bakın.

## <a name="coledatetimem_dt"></a><a name="m_dt"></a>COleDateTime::m_dt

Bu `COleDateTime` `DATE` nesnenin alt yapısı.

```
DATE m_dt;
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bu işlev tarafından `DATE` döndürülen işaretçi tarafından erişilen nesnedeki `COleDateTime` değeri değiştirmek bu nesnenin değerini değiştirir. Bu `COleDateTime` nesnenin durumunu değiştirmez.

Nesnenin uygulanması hakkında daha `DATE` fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimem_status"></a><a name="m_status"></a>COleDateTime::m_status

Bu `COleDateTime` nesnenin durumunu içerir.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesinin türü, `DateTimeStatus` `COleDateTime` sınıf içinde tanımlanan numaralandırılmış türüdür. Daha fazla bilgi için [COleDateTime::GetStatus](#getstatus)' a bakın.

> [!CAUTION]
> Bu veri üyesi gelişmiş programlama durumları içindir. Sıralı üye işlevleri kullanmalısınız [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bu `SetStatus` veri üyesinin açıkça ayarlanmasıyla ilgili daha fazla uyarı için bkz.

## <a name="coledatetimeoperator-"></a><a name="operator_eq"></a>COleDateTime::operator =

Bir `COleDateTime` değeri kopyalar.

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& uDate) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklü atama işleçleri kaynak `COleDateTime` tarih/saat değerini bu nesneye kopyalar. Her aşırı yüklü atama işleçleri kısa bir açıklama aşağıdaki gibidir:

- **işleç =(** `dateSrc` **)** Operand değeri ve durumu bu `COleDateTime` nesneye kopyalanır.

- **operatör =(** *varSrc* **)** [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) değerinin (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesnesinin) bir tarih/saate (VT_DATE) dönüştürülmesi başarılı olursa, dönüştürülen değer bu `COleDateTime` nesneye kopyalanır ve durumu geçerli olarak ayarlanır. Dönüştürme başarılı olmazsa, bu nesnenin değeri sıfıra (30 Aralık 1899, gece yarısı) ve durumu geçersiz olarak ayarlanır.

- **işleç =(** `dtSrc` **)** Değer `DATE` bu `COleDateTime` nesneye kopyalanır ve durumu geçerli olarak ayarlanır.

- **işleç =(** `timeSrc` **)** Veya `time_t` `__time64_t` değer dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır.

- **operatör =(** *systimeSrc* **)** [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) değeri dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır.

- **işleç =(** `uDate` **)** Değer `UDATE` dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır. Bir `UDATE` yapı "paketlenmemiş" tarihi temsil eder. Daha fazla bilgi için [VarDateFromUdate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)işlevine bakın.

- **işleç =(** `filetimeSrc` **)** [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) değeri dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; aksi takdirde geçersiz olarak ayarlanır. `FILETIME`Evrensel Eşgüdümlü Zaman (UTC) kullanır, bu nedenle yapıda bir UTC süresini geçerseniz, sonuçlarınız UTC saatinden yerel saate dönüştürülür ve varyant süresi olarak depolanır. Bu davranış Visual C++ 6.0 ve Visual C++.NET 2003 SP2 ile aynıdır. Daha fazla bilgi için Windows SDK'daki [Dosya Süreleri'ne](/windows/win32/SysInfo/file-times) bakın.

Daha fazla bilgi için Windows SDK'daki [VARIANT](/windows/win32/api/oaidl/ns-oaidl-variant) girişine bakın.

`time_t` Veri türü hakkında daha fazla bilgi *için, Çalışma Zamanı Kitaplığı Başvurusu'ndaki* [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevine bakın.

Daha fazla bilgi için Windows SDK'daki [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapılarına bakın.

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimeoperator---"></a><a name="operator_add_-"></a>COleDateTime::operatör +, -

`ColeDateTime` Değer ekleme ve çıkarma.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Açıklamalar

`COleDateTime`nesneler mutlak kez temsil eder. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) nesneleri göreli süreleri temsil eder. İlk iki işleç, bir değer `COleDateTimeSpan` eklemenize `COleDateTime` ve bir değerden çıkarmanıza olanak sağlar. Üçüncü işleç, bir `COleDateTime` `COleDateTimeSpan` değer elde etmek için bir değeri diğerinden çıkarmanızı sağlar.

Operandlardan biri null ise, elde edilen `COleDateTime` değerin durumu null'dur.

Elde edilen `COleDateTime` değer kabul edilebilir değerlerin sınırlarıdışında kalırsa, `COleDateTime` bu değerin durumu geçersizdir.

Operand'lardan biri geçersizse ve diğeri null değilse, elde edilen `COleDateTime` değerin durumu geçersizdir.

Ve **+** **-** işleçler nesne `COleDateTime` null ayarlanırsa iddia edecektir. Bir örnek için [COleDateTime İlişkisel Operatörler'e](#coledatetime_relational_operators) bakın.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

## <a name="coledatetimeoperator---"></a><a name="operator_add_eq_-_eq"></a>COleDateTime::operatör +=, -=

Bu `COleDateTime` nesneden `ColeDateTime` bir değer ekleyin ve çıkarın.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu `COleDateTimeSpan` `COleDateTime`değere bir değer eklemenize ve çıkarmanıza izin verir. Operandlardan biri null ise, elde edilen `COleDateTime` değerin durumu null'dur.

Elde edilen `COleDateTime` değer kabul edilebilir değerlerin sınırlarıdışında kalırsa, `COleDateTime` bu değerin durumu geçersiz olarak ayarlanır.

Operands biri geçersiz ve diğer null değilse, ortaya çıkan `COleDateTime` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için [m_status](#m_status) üye değişkenine bakın.

Ve **+=** **-=** işleçler nesne `COleDateTime` null ayarlanırsa iddia edecektir. Bir örnek için [COleDateTime İlişkisel Operatörler'e](#coledatetime_relational_operators) bakın.

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimeoperator-date"></a><a name="operator_date"></a>COleDateTime::operatör Tarİhİ

Bir `ColeDateTime` değeri bir `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, değeri bu `DATE` `COleDateTime` nesneden kopyalanan bir nesneyi döndürür. Nesnenin uygulanması hakkında daha `DATE` fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

Nesne `DATE` null ayarlanırsa `COleDateTime` işleç iddia edecektir. Bir örnek için [COleDateTime İlişkisel Operatörler'e](#coledatetime_relational_operators) bakın.

## <a name="coledatetimeparsedatetime"></a><a name="parsedatetime"></a>COleDateTime::ParseDateTime

Tarih/saat değerini okumak için bir dizeyi parses.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*lpszTarih*<br/>
Ayrıştırılması gereken null-sonlandırılan dize için bir işaretçi. Ayrıntılar için Açıklamalar'a bakın.

*Dwflags*<br/>
Yerel ayarlar ve ayrışma için bayrakları gösterir. Aşağıdaki bayraklardan biri veya birkaçı:

- LOCALE_NOUSEROVERRIDE Özel kullanıcı ayarları yerine sistemin varsayılan yerel ayarları kullanın.

- VAR_TIMEVALUEONLY Ayrışdırma sırasında tarih kısmını yoksayın.

- VAR_DATEVALUEONLY Ayrışdırma sırasında zaman kısmını yoksay.

*lcid*<br/>
Dönüşüm için kullanılacak yerel kimliği gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dize başarıyla bir tarih/saat değerine dönüştürüldüyse TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Dize başarıyla bir tarih/saat değerine dönüştürüldüyse, `COleDateTime` bu nesnenin değeri bu değere ve durumu geçerli olarak ayarlanır.

> [!NOTE]
> Yıl değerleri 100 ile 9999 arasında olmalıdır.

*LPSZDate* parametresi çeşitli biçimler alabilir. Örneğin, aşağıdaki dizeleri kabul edilebilir tarih/saat biçimleri içerir:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Yerel kimlik, dize biçiminin bir tarih/saat değerine dönüştürme için kabul edilebilir olup olmadığını da etkiler.

VAR_DATEVALUEONLY durumunda, saat değeri saat 0 veya gece yarısı olarak ayarlanır. VAR_TIMEVALUEONLY durumunda, tarih değeri 30 Aralık 1899 anlamına gelen 0 tarihine ayarlanır.

Dize bir tarih/saat değerine dönüştürülemediyse veya sayısal bir taşma varsa, `COleDateTime` bu nesnenin durumu geçersizdir.

Değerlerin sınırları ve uygulanması `COleDateTime` hakkında daha fazla bilgi için Tarih ve [Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

## <a name="coledatetimesetdate"></a><a name="setdate"></a>COleDateTime::SetDate

Bu `COleDateTime` nesnenin tarihini ayarlar.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Parametreler

*nYear*, *nMonth*, *nDay*<br/>
Bu `COleDateTime` nesneye kopyalanacak tarih bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlanmışsa sıfır; aksi takdirde, 1. Bu iade değeri numaralandırılmış türü temel alınr. `DateTimeStatus` Daha fazla bilgi için [SetStatus](#setstatus) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Tarih belirtilen değerlere ayarlanır. Saat 0,gece yarısına ayarlandı.

Parametre değerleri için sınırlar için aşağıdaki tabloya bakın:

|Parametre|Sınır -ları|
|---------------|------------|
|*nYıl*|100 - 9999|
|*nAy*|1 - 12|
|*nGün*|0 - 31|

Ayın günü taşarsa, bir sonraki ayın doğru gününe dönüştürülür ve ay ve/veya yıl buna göre artımlanır. Sıfır günlük değeri, bir önceki ayın son gününü gösterir. Davranış `SystemTimeToVariantTime`aynıdır.

Parametreler tarafından belirtilen tarih değeri geçerli değilse, bu nesnenin `COleDateTime::invalid`durumu . Değerin geçerliliğini denetlemek için [GetStatus'u](#getstatus) kullanmalı ve m_dt değerinin değiştirilmediğini varsaymamalısınız. [m_dt](#m_dt) `DATE`

Tarih değerlerine bazı örnekler aşağıda verilmiştir:

|*nYıl*|*nAy*|*nGün*|Değer|
|-------------|--------------|------------|-----------|
|2000|2|29|29 Şubat 2000|
|1776|7|4|4 Temmuz 1776|
|1925|4|35|35 Nisan 1925 (geçersiz tarih)|
|10000|1|1|1 Ocak 10000 (geçersiz tarih)|

Hem tarih hem de saat ayarlamak için [COleDateTime::SetDateTime'a](#setdatetime)bakın.

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

## <a name="coledatetimesetdatetime"></a><a name="setdatetime"></a>COleDateTime::SetDateTime

Bu `COleDateTime` nesnenin tarih ve saatini ayarlar.

```
int SetDateTime(
    int nYear,
    int nMonth,
    int nDay,
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parametreler

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Bu `COleDateTime` nesneye kopyalanacak tarih ve saat bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlanmışsa sıfır; aksi takdirde, 1. Bu iade değeri numaralandırılmış türü temel alınr. `DateTimeStatus` Daha fazla bilgi için [SetStatus](#setstatus) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Parametre değerleri için sınırlar için aşağıdaki tabloya bakın:

|Parametre|Sınır -ları|
|---------------|------------|
|*nYıl*|100 - 9999|
|*nAy*|1 - 12|
|*nGün*|0 - 31|
|*nSaat*|0 - 23|
|*nMin*|0 - 59|
|*Nsec*|0 - 59|

Ayın günü taşarsa, bir sonraki ayın doğru gününe dönüştürülür ve ay ve/veya yıl buna göre artımlanır. Sıfır günlük değeri, bir önceki ayın son gününü gösterir. Davranış [SystemTimeToVariantTime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime)aynıdır.

Parametreler tarafından belirtilen tarih veya saat değeri geçerli değilse, bu nesnenin durumu geçersiz olarak ayarlanır ve bu nesnenin değeri değiştirilmez.

Zaman değerlerine bazı örnekler aşağıda verilmiştir:

|*nSaat*|*nMin*|*Nsec*|Değer|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Tarih değerlerine bazı örnekler aşağıda verilmiştir:

|*nYıl*|*nAy*|*nGün*|Değer|
|-------------|--------------|------------|-----------|
|1995|4|15|15 Nisan 1995|
|1789|7|14|17 Temmuz 1789|
|1925|2|30|Geçersiz|
|10000|1|1|Geçersiz|

Yalnızca tarihi ayarlamak için [COleDateTime::SetDate'e](#setdate)bakın. Yalnızca zamanı ayarlamak için [Bkz. COleDateTime::SetTime](#settime).

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[GetStatus](#getstatus)için örneğe bakın.

## <a name="coledatetimesetstatus"></a><a name="setstatus"></a>COleDateTime::SetStatus

Bu `COleDateTime` nesnenin durumunu ayarlar.

```cpp
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Bu `COleDateTime` nesne için yeni durum değeri.

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `DateTimeStatus` `COleDateTime` sınıf içinde tanımlanan numaralandırılmış türtarafından tanımlanır. Bkz. [COleDateTime::Ayrıntılar](#getstatus) için Durum Bilgisi.

> [!CAUTION]
> Bu işlev gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. Genellikle durumu **geçersiz** veya **geçersiz**olarak ayarlamak için kullanılır. Atama işleci ([işleç =](#operator_eq)) ve [SetDateTime](#setdatetime) nesnenin durumunu kaynak değeri(ler) temel alınca ayarlar.

### <a name="example"></a>Örnek

[GetStatus](#getstatus)için örneğe bakın.

## <a name="coledatetimesettime"></a><a name="settime"></a>COleDateTime::SetTime

Bu `COleDateTime` nesnenin zamanını ayarlar.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parametreler

*nHour*, *nMin*, *nSec*<br/>
Bu `COleDateTime` nesneye kopyalanacak zaman bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlanmışsa sıfır; aksi takdirde, 1. Bu iade değeri numaralandırılmış türü temel alınr. `DateTimeStatus` Daha fazla bilgi için [SetStatus](#setstatus) üye işlevine bakın.

### <a name="remarks"></a>Açıklamalar

Saat belirtilen değerlere ayarlanır. Tarih 0 olarak ayarlanır, yani 30 Aralık 1899.

Parametre değerleri için sınırlar için aşağıdaki tabloya bakın:

|Parametre|Sınır -ları|
|---------------|------------|
|*nSaat*|0 - 23|
|*nMin*|0 - 59|
|*Nsec*|0 - 59|

Parametreler tarafından belirtilen zaman değeri geçerli değilse, bu nesnenin durumu geçersiz olarak ayarlanır ve bu nesnenin değeri değiştirilmez.

Zaman değerlerine bazı örnekler aşağıda verilmiştir:

|*nSaat*|*nMin*|*Nsec*|Değer|
|-------------|------------|------------|-----------|
|1|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Hem tarih hem de saat ayarlamak için [COleDateTime::SetDateTime'a](#setdatetime)bakın.

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevler hakkında bilgi için aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayofWeek](#getdayofweek)

- [Getdayofyear](#getdayofyear)

Değerler için sınırlar hakkında `COleDateTime` daha fazla bilgi için [Tarih ve Saat: Otomasyon Desteği](../../atl-mfc-shared/date-and-time-automation-support.md)makalesine bakın.

### <a name="example"></a>Örnek

[SetDate](#setdate)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CTime Sınıfı](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
