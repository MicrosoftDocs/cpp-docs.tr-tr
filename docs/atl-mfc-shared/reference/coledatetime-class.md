---
title: COleDateTime sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: a49b886bcf9c25642b1f7b8e843be11baf2d2d00
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894113"
---
# <a name="coledatetime-class"></a>COleDateTime sınıfı

Kapsülleyen `DATE` OLE Otomasyonu nesnesi etkin kullanılan veri türü.

## <a name="syntax"></a>Sözdizimi

```
class COleDateTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTime::COleDateTime](#coledatetime)|Oluşturur bir `COleDateTime` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTime::Format](#format)|Bir biçimlendirilmiş dize gösterimini oluşturur bir `COleDateTime` nesne.|
|[COleDateTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Sürede elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir `DBTIMESTAMP` veri yapısı.|
|[COleDateTime::GetAsSystemTime](#getassystemtime)|Sürede elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) veri yapısı.|
|[COleDateTime::GetAsUDATE](#getasudate)|Sürede elde etmek için bu yöntemi çağırın `COleDateTime` olarak bir `UDATE` veri yapısı.|
|[COleDateTime::GetCurrentTime](#getcurrenttime)|Oluşturur bir `COleDateTime` (statik üye işlevini) geçerli zamanı temsil eden nesne.|
|[COleDateTime::GetDay](#getday)|Bu günlük döndürür `COleDateTime` nesnesi (1-31) temsil eder.|
|[COleDateTime::GetDayOfWeek](#getdayofweek)|Bu haftanın gününü döndürür `COleDateTime` nesnesi (Pazar = 1) temsil eder.|
|[COleDateTime::GetDayOfYear](#getdayofyear)|Bu yılın gününü döndürür `COleDateTime` nesnesi (Ocak 1 = 1) temsil eder.|
|[COleDateTime::GetHour](#gethour)|Bu saati döndürür `COleDateTime` nesnesini temsil eder (0 - 23).|
|[COleDateTime::GetMinute](#getminute)|Bu dakika döndürür `COleDateTime` nesnesini temsil eder (0 - 59).|
|[COleDateTime::GetMonth](#getmonth)|Bu ay döndürür `COleDateTime` nesnesi (1-12) temsil eder.|
|[COleDateTime::GetSecond](#getsecond)|Bu ikinci döndürür `COleDateTime` nesnesini temsil eder (0 - 59).|
|[COleDateTime::GetStatus](#getstatus)|Bu durum (geçerlilik) alır `COleDateTime` nesne.|
|[COleDateTime::GetYear](#getyear)|Bu yıl döndürür `COleDateTime` nesnesini temsil eder.|
|[COleDateTime::ParseDateTime](#parsedatetime)|Bir dizeden bir tarih/saat değerini okur ve değerini ayarlar `COleDateTime`.|
|[COleDateTime::SetDate](#setdate)|Bu ayarlar `COleDateTime` nesne belirtilen salt değer.|
|[COleDateTime::SetDateTime](#setdatetime)|Bu ayarlar `COleDateTime` nesne belirtilen tarih/saat değeri.|
|[COleDateTime::SetStatus](#setstatus)|' % S'durumunu (geçerlilik) Bu ayarlar `COleDateTime` nesne.|
|[COleDateTime::SetTime](#settime)|Bu ayarlar `COleDateTime` nesne belirtilen yalnızca saat değeri.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTime::operator ==, COleDateTime::operator < vb.](#coledatetime_relational_operators)|Karşılaştırabilirsiniz `COleDateTime` değerleri.|
|[COleDateTime::operator +, COleDateTime::operator-](#operator_add_-)|Ekleme ve çıkarmayı `COleDateTime` değerleri.|
|[COleDateTime::operator +=, COleDateTime::operator-=](#operator_add_eq_-_eq)|Ekleme ve çıkarmayı bir `COleDateTime` bu değerden `COleDateTime` nesne.|
|[COleDateTime::operator =](#operator_eq)|Kopya bir `COleDateTime` değeri.|
|[Tarih, COleDateTime::operator COleDateTime::operator tarih *](#operator_date)|Dönüştürür bir `COleDateTime` içine değeri bir `DATE` veya `DATE*`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTime::m_dt](#m_dt)|Arka plandaki içeren `DATE` bu `COleDateTime` nesne.|
|[COleDateTime::m_status](#m_status)|Bu durumu içeren `COleDateTime` nesne.|

## <a name="remarks"></a>Açıklamalar

`COleDateTime` bir temel sınıfa sahip değil.

Olası türlerinde biridir [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) OLE Otomasyonu nesnesi etkin veri türü. A `COleDateTime` değeri bir mutlak tarih ve saat değerini temsil eder.

`DATE` Türü, bir kayan nokta değeri gerçekleştirilir. Gün 30 Aralık 1899 ' gece yarısı olarak ölçülür. Aşağıdaki tablo bazı tarihleri ve ilişkili değerleri gösterir:

|Tarih|Değer|
|----------|-----------|
|29 Aralık 1899 gece yarısı|-1.0|
|29 Aralık 1899'den itibaren 6 saatlerinde|-1.25|
|30 Aralık 1899 gece yarısı|0.0|
|31 Aralık 1899 gece yarısı|1.0|
|1 Ocak 1900'den itibaren 6 AM|2.25|

> [!CAUTION]
> Yukarıdaki tabloda gün değerleri, 30 Aralık 1899 gece yarısından önce negatif olabilir ancak günün saati değerleri edilmediğini unutmayın. Örneğin, 6: 00'da her zaman gününü temsil eden tamsayı (sonra 30 Aralık 1899) pozitif veya negatif (önce 30 Aralık 1899) olmasına bakılmaksızın bir kesir değerini 0,25 temsil edilir. Basit bir kayan nokta karşılaştırma deneyebileceğinizi sıralamanız gerekir yani bir `COleDateTime` 6: 00'da 29/12/1899 temsil eden **daha sonra** 7: 00'da aynı günde birden temsil eden.

`COleDateTime` Sınıfı tarihler 1 Ocak 100-31 Aralık 9999 işler. `COleDateTime` Sınıfı Miladi takvimini kullanır; Jülyen tarihleri desteklemez. `COleDateTime` gün ışığından yararlanma yok sayar. (Bkz [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> Kullanabileceğiniz `%y` iki basamaklı bir yıl 1900 başlangıç tarihler için alınacak biçimi. Kullanırsanız `%y` kod 1900, önceki bir tarih biçimi, bir onay hatası oluşturur.

Bu tür, yalnızca tarih veya yalnızca saat değerlerini temsil etmek için de kullanılır. Kural olarak, yalnızca saat değerleri için kullanılan 0 (30 Aralık 1899) tarih ve saat 00:00 (gece yarısı) yalnızca tarih değerleri için kullanılır.

Oluşturursanız, bir `COleDateTime` nesnesi kullanarak bir tarih değerinden 100 tarihi kabul edilen, ancak sonraki çağrılar, `GetYear`, `GetMonth`, `GetDay`, `GetHour`, `GetMinute`, ve `GetSecond` başarısız ve -1 döndürür. Daha önce iki basamaklı tarihleri kullanabilirsiniz, ancak tarihler, 100 veya daha büyüktür, MFC 4.2 ve üzeri olması gerekir.

Sorunları önlemek için dört basamaklı bir tarih belirtin. Örneğin:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

Temel aritmetik işlemleri için `COleDateTime` değerlerinde Yardımcısı sınıfı [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md). `COleDateTimeSpan` bir zaman aralığı değerleri tanımlayın. Bu sınıflar arasındaki ilişkiyi arasında bir benzer [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md).

Hakkında daha fazla bilgi için `COleDateTime` ve `COleDateTimeSpan` sınıfları, başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** ATLComTime.h

##  <a name="coledatetime_relational_operators"></a>  COleDateTime ilişkisel işleçleri

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
`COleDateTime` Karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  İki işlenenden geçersiz ise bir ATLASSERT meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Örnek

İşleçler **>=**, **\< =**, **>**, ve **<**, varsa onay `COleDateTime` kümesi nesnesi null.

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

##  <a name="coledatetime"></a>  COleDateTime::COleDateTime

Oluşturur bir `COleDateTime` nesne.

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
COleDateTime(const DBTIMESTAMP& dbts) throw();
```

### <a name="parameters"></a>Parametreler

*dateSrc*<br/>
Mevcut bir `COleDateTime` yeni içine kopyalanacak nesne `COleDateTime` nesne.

*varSrc*<br/>
Mevcut bir `VARIANT` veri yapısı (büyük olasılıkla bir `COleVariant` nesnesi) bir tarih/saat değeri (VT_DATE) dönüştürülür ve yeni kopyalanan `COleDateTime` nesne.

*dtSrc*<br/>
Bir tarih/saat (`DATE`) yeni içine kopyalanacak değeri `COleDateTime` nesne.

*timeSrc*<br/>
A `time_t` veya `__time64_t` değerini bir tarih/saat değerine dönüştürülür ve yeni kopyalanan `COleDateTime` nesne.

*systimeSrc*<br/>
A `SYSTEMTIME` yapısı bir tarih/saat değerine dönüştürülür ve yeni kopyalanan `COleDateTime` nesne.

*filetimeSrc*<br/>
A `FILETIME` yapısı bir tarih/saat değerine dönüştürülür ve yeni kopyalanan `COleDateTime` nesne. Unutmayın `FILETIME` Eşgüdümlü Evrensel Saat (UTC) kullanan yerel saati yapısında geçirirseniz, sonuçlarınızı yanlış olur. Bkz: [dosya zamanlarını](/windows/desktop/SysInfo/file-times) daha fazla bilgi için Windows SDK.

*nYear*, *nMonth*, *nhatalı günü*, *nHour*, *nMin*, *nSec*<br/>
Yeni içine kopyalanacak tarih ve saat değerleri gösterir `COleDateTime` nesne.

*wDosDate*, *wDosTime*<br/>
Bir tarih/saat değerine dönüştürülür ve yeni kopyalanan için tarih ve saat değerlerini MS-DOS `COleDateTime` nesne.

*dbts*<br/>
Bir başvuru bir [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) geçerli yerel saat içeren yapısı.

### <a name="remarks"></a>Açıklamalar

Bu oluşturucular Yeni Oluştur `COleDateTime` nesneleri belirtilen değerle başlatılır. Aşağıdaki tabloda her bir tarih ve saat bileşeni için geçerli aralıklar gösterilmektedir:

|Tarih/Saat bileşeni|Geçerli aralık|
|--------------------------|-----------------|
|yıl|100 - 9999|
|ay|0 - 12|
|gün|0 - 31|
|Saat|0 - 23|
|Dakika|0 - 59|
|Saniye|0 - 59|

Gün bileşenini gerçek üst sınırını değişir Not, ay ve yıl bileşenlerine göre. Ayrıntılar için bkz `SetDate` veya `SetDateTime` üye işlevleri.

Her Oluşturucu kısa bir açıklaması verilmiştir:

- `COleDateTime(` **)** Oluşturan bir `COleDateTime` nesne (gece yarısı, 30 Aralık 1899) 0 olarak başlatılır.

- `COleDateTime(` `dateSrc` **)** Oluşturan bir `COleDateTime` mevcut bir nesne `COleDateTime` nesne.

- `COleDateTime(` *varSrc* **)** oluşturan bir `COleDateTime` nesne. Dönüştürmeye çalışır bir `VARIANT` yapısı veya [COleVariant](../../mfc/reference/colevariant-class.md) nesneye bir tarih/saat ( `VT_DATE`) değeri. Bu dönüştürmenin başarılı olursa, dönüştürülen değer yeni kopyalanan `COleDateTime` nesne. Değerini, değilse `COleDateTime` nesnesi, 0 (gece yarısı, 30 Aralık 1899)'geçersiz durumu ayarlanır.

- `COleDateTime(` `dtSrc` **)** Oluşturan bir `COleDateTime` nesnesinden bir `DATE` değeri.

- `COleDateTime(` `timeSrc` **)** Oluşturan bir `COleDateTime` nesnesinden bir `time_t` değeri.

- `COleDateTime(` *systimeSrc* **)** oluşturan bir `COleDateTime` nesnesinden bir `SYSTEMTIME` değeri.

- `COleDateTime(` `filetimeSrc` **)** Oluşturan bir `COleDateTime` nesnesinden bir `FILETIME` değeri. biçimindeki telefon numarasıdır. Unutmayın `FILETIME` Eşgüdümlü Evrensel Saat (UTC) kullanan yerel saati yapısında geçirirseniz, sonuçlarınızı yanlış olur. Bkz: [dosya zamanlarını](/windows/desktop/SysInfo/file-times) daha fazla bilgi için Windows SDK.

- `COleDateTime(` `nYear``nMonth`, `nDay`, `nHour`, `nMin`, `nSec` **)** Oluşturan bir `COleDateTime` nesnesinden belirtilen sayısal değerler.

- `COleDateTime(` `wDosDate``wDosTime` **)** Oluşturan bir `COleDateTime` nesnesinden belirtilen MS-DOS tarih ve saat değerleri.

Daha fazla bilgi için `time_t` veri türünü görmek [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevi *çalışma zamanı kitaplığı başvurusu*.

Daha fazla bilgi için [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) ve [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapıları, Windows SDK'sı.

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

> [!NOTE]
> Oluşturucu kullanılarak `DBTIMESTAMP` parametresi, yalnızca kullanılabilir biçim dahil edildiğinde.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

##  <a name="format"></a>  COleDateTime::Format

Biçimlendirilmiş bir tarih/saat değeri temsilini oluşturur.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*CertOpenStore*<br/>
Aşağıdaki yerel ayar bayraklarından birini gösterir:

- LOCALE_NOUSEROVERRIDE sistem varsayılan yerel ayarları yerine özel kullanıcı ayarları kullanın.

- VAR_TIMEVALUEONLY tarih bölümü ayrıştırılırken yoksayın.

- VAR_DATEVALUEONLY Ayrıştırma sırasında saat kısmının yoksayın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar Kimliğini belirtir. Dil tanımlayıcıları hakkında daha fazla bilgi için bkz. [Dil tanımlayıcıları](/windows/desktop/Intl/language-identifiers).

*lpszFormat*<br/>
Bir biçimlendirme dizesi benzer `printf` biçimlendirme dizesi. Her bir yüzde öncesinde, kod biçimlendirme ( `%`) oturum açın, ilgili değiştirilir `COleDateTime` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dizeye değiştirilmeden kopyalanır. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) daha fazla bilgi için. Değer ve biçimlendirme kodları anlamını `Format` şunlardır:

- `%H` Geçerli günün saat

- `%M` Geçerli bir saatteki dakika

- `%S` Geçerli dakika, saniye

- `%%` Yüzde işareti

*nFormatID*<br/>
Biçim Denetimi dizesi kaynak kimliği.

### <a name="return-value"></a>Dönüş Değeri

A `CString` biçimlendirilmiş tarih/saat değeri içeren.

### <a name="remarks"></a>Açıklamalar

Varsa bu durum `COleDateTime` nesnesi null ise, dönüş değeri boş bir dizedir. Geçersiz durum ise, dize kaynağı ATL_IDS_DATETIME_INVALID dizesini belirtilir.

Bu işlev için üç formları kısa bir açıklaması aşağıdaki gibidir:

`Format`( *CertOpenStore*, *LCID*)<br/>
Bu form değeri (yerel ayar kimlikleri) dil özellikleri kullanarak tarih ve saat için biçimlendirir. Varsayılan parametreleri kullanarak, bu formu tarih ve saat saat kısmının 0 (gece yarısı), durumda yalnızca tarihi yazdırır veya tarih bölümü 0 (30 Aralık 1899), bu durumda tam zamanında yazdırılacağı içinde yazdırır. Tarih/saat değeri 0 (30 Aralık 1899, gece yarısıdır) ise, bu formu varsayılan parametreleri olan gece yarısı yazdırır.

`Format`( *lpszFormat*)<br/>
Bu form değeri (%) yüzde işareti tarafından öncelenen özel biçimlendirme kodları içeren bir biçim dizesi kullanarak olarak biçimlendirir `printf`. Biçimlendirme dizesi, parametre olarak işleve geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz. [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) çalışma zamanı kitaplığı başvurusu.

`Format`( *nFormatID*)<br/>
Bu form değeri (%) yüzde işareti tarafından öncelenen özel biçimlendirme kodları içeren bir biçim dizesi kullanarak olarak biçimlendirir `printf`. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynak kimliği, parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz. [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) içinde *çalışma zamanı kitaplığı başvurusu*.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

##  <a name="getasdbtimestamp"></a>  COleDateTime::GetAsDBTIMESTAMP

Sürede elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir `DBTIMESTAMP` veri yapısı.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts*<br/>
Bir başvuru bir [DBTimeStamp](https://msdn.microsoft.com/library/system.data.oledb.oledbtype) yapısı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sonuçta elde edilen zaman başvurulan depolar *dbts* yapısı. `DBTIMESTAMP` Bu işlev tarafından başlatılan veri yapısı olacaktır, `fraction` üye sıfır olarak ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

##  <a name="getassystemtime"></a>  COleDateTime::GetAsSystemTime

Sürede elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir `SYSTEMTIME` veri yapısı.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Parametreler

*sysTime*<br/>
Bir başvuru bir [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) dönüştürülen bir tarih/saat değerinden almaya yapısı `COleDateTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sahipse TRUE değerini döndürür; FALSE dönüştürme başarısız olursa veya `COleDateTime` nesnedir NULL veya geçersiz.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime` Sonuçta elde edilen zaman başvurulan depolar *sysTime* nesne. `SYSTEMTIME` Bu işlev tarafından başlatılan veri yapısı olacaktır, `wMilliseconds` üye sıfır olarak ayarlayın.

Bkz: [GetStatus](#getstatus) tutulan durum bilgileri hakkında daha fazla bilgi için bir `COleDateTime` nesne.

##  <a name="getasudate"></a>  COleDateTime::GetAsUDATE

Sürede elde etmek için bu yöntemi çağırın `COleDateTime` nesnesinin bir `UDATE` veri yapısı.

```
bool GetAsUDATE(UDATE& udate) const throw();
```

### <a name="parameters"></a>Parametreler

*udate*<br/>
Bir başvuru bir `UDATE` dönüştürülen bir tarih/saat değerinden almaya yapısı `COleDateTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sahipse TRUE değerini döndürür; FALSE dönüştürme başarısız olursa veya `COleDateTime` nesnedir NULL veya geçersiz.

### <a name="remarks"></a>Açıklamalar

A `UDATE` yapısı "paketten çıkarılan" bir tarihi temsil eder.

##  <a name="getcurrenttime"></a>  COleDateTime::GetCurrentTime

Geçerli tarih/saat değerini döndürmek için bu statik üye işlevini çağırın.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

##  <a name="getday"></a>  COleDateTime::GetDay

Bu tarih/saat değeri ile temsil edilen ayın gününü alır.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen ayın gününü `COleDateTime` nesne veya `COleDateTime::error` gün alınamadığından.

### <a name="remarks"></a>Açıklamalar

1 ile 31 arasında geçerli bir dönüş değerleri aralığı.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

##  <a name="getdayofweek"></a>  COleDateTime::GetDayOfWeek

Bu tarih/saat değeri ile temsil edilen ayın gününü alır.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen haftanın gününü `COleDateTime` nesne veya `COleDateTime::error` , haftanın günü sağlanamadı.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri aralığı 7, 1 ila 1 Pazar, 2 = Pazartesi vb.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

##  <a name="getdayofyear"></a>  COleDateTime::GetDayOfYear

Bu tarih/saat değeri ile temsil edilen yılın gününü alır.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen yılın gününü `COleDateTime` nesne veya `COleDateTime::error` , yılın gününü sağlanamadı.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri aralığı 1 ile 366 arasında nerede 1 Ocak = 1.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

##  <a name="gethour"></a>  COleDateTime::GetHour

Bu tarih/saat değeri ile temsil edilen saat alır.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen saat `COleDateTime` nesne veya `COleDateTime::error` saat alınamadığından.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri aralığı 0 ile 23 arasında.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

##  <a name="getminute"></a>  COleDateTime::GetMinute

Bu tarih/saat değeri ile temsil edilen dakika alır.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen dakika `COleDateTime` nesne veya `COleDateTime::error` dakika alınamadığından.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri aralığı 0 ile 59 arasında.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

Örneğin bakın [GetHour](#gethour).

##  <a name="getmonth"></a>  COleDateTime::GetMonth

Bu tarih/saat değeri ile temsil edilen aylık alır.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen aylık `COleDateTime` nesne veya `COleDateTime::error` ay alınamadığından.

### <a name="remarks"></a>Açıklamalar

1 ile 12 arasında geçerli bir dönüş değerleri aralığı.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

Örneğin bakın [GetDay](#getday).

##  <a name="getsecond"></a>  COleDateTime::GetSecond

Bu tarih/saat değeri ile temsil edilen saniye alır.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen ikinci `COleDateTime` nesne veya `COleDateTime::error` , ikinci sağlanamadı.

### <a name="remarks"></a>Açıklamalar

Dönüş değerleri aralığı 0 ile 59 arasında.

> [!NOTE]
>  `COleDateTime` Sınıfı artık saniye desteklemez.

Uygulama hakkında daha fazla bilgi için `COleDateTime`, makaleye göz atın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

Örneğin bakın [GetHour](#gethour).

##  <a name="getstatus"></a>  COleDateTime::GetStatus

(Geçerlilik) durumunu alır bir verilen `COleDateTime` nesne.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu durumunu döndüren `COleDateTime` değeri. Eğer `GetStatus` üzerinde bir `COleDateTime` yapılandırılmış varsayılan nesne, geçerli döndürür. Eğer `GetStatus` üzerinde bir `COleDateTime` Oluşturucusu ayarlanan null ile başlatılan nesne `GetStatus` null döndürür. Bkz: **açıklamalar** daha fazla bilgi için.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri tarafından tanımlanan `DateTimeStatus` listelenmiş içinde tanımlanan bir türü `COleDateTime` sınıfı.

```
enum DateTimeStatus
{
   error = -1,
   valid = 0,
   invalid = 1,    // Invalid date (out of range, etc.)
   null = 2,       // Literally has no value
};
```

Bu durum değerleri kısa bir açıklaması için aşağıdaki listeye bakın:

- `COleDateTime::error` Tarih/saat değerinin bölümünü alınmaya çalışılırken bir hata oluştuğunu gösterir.

- `COleDateTime::valid` Belirten bu `COleDateTime` nesne geçerlidir.

- `COleDateTime::invalid` Belirten bu `COleDateTime` Nesne geçersiz; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTime::null` Belirten bu `COleDateTime` nesnesi, null, diğer bir deyişle, bu nesne için hiçbir değer belirtilmiş. ("Null" bir "herhangi bir değer NULL C++ aksine kullanılmasının" veritabanı anlamında budur.)

Durumunu bir `COleDateTime` aşağıdaki durumlarda nesne geçersiz:

- Gelen değerini ayarlarsanız bir `VARIANT` veya `COleVariant` değerini bir tarih/saat değerine dönüştürülemedi.

- Gelen değerini ayarlarsanız bir `time_t`, `SYSTEMTIME`, veya `FILETIME` geçerli tarih/saat değerine dönüştürülemiyor değer.

- Değeri ayarlanmışsa `SetDateTime` geçersiz parametre değerleri ile.

- Bu nesne bir taşma veya yetersiz gelme aritmetik atama işlemi sırasında yani karşılaştı, `+=` veya `-=`.

- Bu nesne için geçersiz bir değere atanırsa.

- Bu nesne durumunu kullanarak geçersiz açıkça ayarlandığını `SetStatus`.

İşlemleri hakkında daha fazla bilgi için geçersiz, aşağıdaki üye işlevleri için durumunu ayarlayabilir:

- [COleDateTime](#coledatetime)

- [SetDateTime](#setdatetime)

- [operator +, -](#operator_add_-)

- [operator +=-=](#operator_add_eq_-_eq)

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

##  <a name="getyear"></a>  COleDateTime::GetYear

Bu tarih/saat değeri ile temsil edilen yıl alır.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu değeri tarafından temsil edilen yıl `COleDateTime` nesne veya `COleDateTime::error` yıl alınamadığından.

### <a name="remarks"></a>Açıklamalar

Yüzyıl içeren geçerli dönüş değerleri aralığı 100 ile 9999 arasında.

Bu değeri sorgu diğer üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

Örneğin bakın [GetDay](#getday).

##  <a name="m_dt"></a>  COleDateTime::m_dt

Arka plandaki `DATE` yapısı bu `COleDateTime` nesne.

```
DATE m_dt;
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Değer değiştirme `DATE` bu işlev tarafından döndürülen işaretçi tarafından erişilen nesne bu değeri değişecek `COleDateTime` nesne. Bu durumu değiştirmez `COleDateTime` nesne.

Uygulaması hakkında daha fazla bilgi için `DATE` nesne, makaleye göz atın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="m_status"></a>  COleDateTime::m_status

Bu durumu içeren `COleDateTime` nesne.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesi listeden seçimli türü türüdür `DateTimeStatus`, içinde tanımlanan `COleDateTime` sınıfı. Bkz: [COleDateTime::GetStatus](#getstatus) Ayrıntılar için.

> [!CAUTION]
>  Gelişmiş programlama durumlar için bu verileri üyesidir. Satır içi üye işlevleri kullanmalıdır [GetStatus](#getstatus) ve [SetStatus](#setstatus). Bkz: `SetStatus` açıkça bu veri üyesi ayarlama ile ilgili daha fazla uyarılar için.

##  <a name="operator_eq"></a>  COleDateTime::operator =

Kopya bir `COleDateTime` değeri.

```
COleDateTime& operator=(const VARIANT& varSrc) throw();
COleDateTime& operator=(DATE dtSrc) throw();
COleDateTime& operator=(const time_t& timeSrc) throw();
COleDateTime& operator=(const __time64_t& timeSrc) throw();
COleDateTime& operator=(const SYSTEMTIME& systimeSrc) throw();
COleDateTime& operator=(const FILETIME& filetimeSrc) throw();
COleDateTime& operator=(const UDATE& udate) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleçleri bu kaynak tarih değeri kopyalayın `COleDateTime` nesne. Bunlar her kısa bir açıklamasını aşırı yüklenmiş atama işleçleri aşağıdaki:

- **operator = (** `dateSrc` **)** işlenen durumunu ve değer bu kopyalanır `COleDateTime` nesne.

- **işleç = (** *varSrc* **)** varsa dönüştürülmesi [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) değeri (veya [COleVariant](../../mfc/reference/colevariant-class.md) nesne) için bir tarih/saat (VT_ TARİHİ) başarılı olur, dönüştürülen değer bu kopyalanır `COleDateTime` nesne ve durumuna ayarlanır için geçerli. Dönüştürme başarılı olmazsa, bu nesnenin değeri sıfır (30 Aralık 1899 için gece yarısıdır) ayarlanır ve durumu geçersiz.

- **operator = (** `dtSrc` **)** `DATE` değeri bu kopyalanır `COleDateTime` nesne ve durumuna ayarlanır için geçerli.

- **operator = (** `timeSrc` **)** `time_t` veya `__time64_t` değere dönüştürülür ve bu kopyalanan `COleDateTime` nesne. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız ayarlanmış olup olmadığını geçersiz.

- **operator = (** *systimeSrc* **)** [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) değere dönüştürülür ve bu kopyalanan `COleDateTime` nesne. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız ayarlanmış olup olmadığını geçersiz.

- **operator = (** `udate` **)** `UDATE` değere dönüştürülür ve bu kopyalanan `COleDateTime` nesne. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; başarısız ayarlanmış olup olmadığını geçersiz. A `UDATE` yapısı "paketten çıkarılan" bir tarihi temsil eder. İşlevi görmek [VarDateFromUdate](/windows/desktop/api/oleauto/nf-oleauto-vardatefromudate) daha fazla ayrıntı için.

- **operator = (** `filetimeSrc` **)** [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) değere dönüştürülür ve bu kopyalanan `COleDateTime` nesne. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli ayarlanır; Aksi takdirde ayarlamak için geçersiz. `FILETIME` UTC saati yapısında geçirirseniz, sonuçlarınızı UTC zamanından yerel saate dönüştürülür ve değişken zaman olarak depolanacak şekilde Eşgüdümlü Evrensel Saat (UTC) kullanır. Bu davranış Visual C++ 6.0 ve Visual C++ .NET 2003 SP2 için de aynıdır. Bkz: [dosya zamanlarını](/windows/desktop/SysInfo/file-times) daha fazla bilgi için Windows SDK.

Daha fazla bilgi için [değişken](/windows/desktop/api/oaidl/ns-oaidl-tagvariant) Windows SDK'sı girişi.

Daha fazla bilgi için `time_t` veri türünü görmek [zaman](../../c-runtime-library/reference/time-time32-time64.md) işlevi *çalışma zamanı kitaplığı başvurusu*.

Daha fazla bilgi için [SYSTEMTIME](/windows/desktop/api/minwinbase/ns-minwinbase-systemtime) ve [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapıları, Windows SDK'sı.

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_add_-"></a>  COleDateTime::operator +, -

Ekleme ve çıkarmayı `ColeDateTime` değerleri.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Açıklamalar

`COleDateTime` nesneleri, mutlak bir kez temsil eder. [COleDateTimeSpan](../../atl-mfc-shared/reference/coledatetimespan-class.md) nesneleri için göreli bir kez temsil eder. İlk iki işleç ekleme ve çıkarmayı sağlar bir `COleDateTimeSpan` değerini bir `COleDateTime` değeri. Üçüncü işleci bir çıkarma sağlar `COleDateTime` elde etmek üzere başka bir değerden bir `COleDateTimeSpan` değeri.

İşlenenler biri geçerli olduğunda null, ortaya çıkan durumunu `COleDateTime` değeri NULL'dur.

Durumunda ortaya çıkan `COleDateTime` değer kabul edilebilir değerler, bu durum sınırları dışında kalan `COleDateTime` değeri geçersiz.

İşlenenden ya da geçersiz ve diğerini null değilse ortaya çıkan durumu `COleDateTime` değeri geçersiz.

**+** Ve **-** işleçleri assert, `COleDateTime` kümesi nesnesi null. Bkz: [COleDateTime ilişkisel işleçler](#coledatetime_relational_operators) örneği.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  COleDateTime::operator +=-=

Ekleme ve çıkarmayı bir `ColeDateTime` bu değerden `COleDateTime` nesne.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, ekleme ve çıkarmayı sağlar bir `COleDateTimeSpan` için ve bu değer `COleDateTime`. İşlenenler biri geçerli olduğunda null, ortaya çıkan durumunu `COleDateTime` değeri NULL'dur.

Durumunda ortaya çıkan `COleDateTime` değer kabul edilebilir değerler, bu durumu sınırları dışında kalan `COleDateTime` değeri ayarı geçersiz.

İşlenenden ya da geçersiz ve diğer null değilse ortaya çıkan durumu `COleDateTime` değeri geçersiz.

Geçerli, geçersiz ve boş durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

**+=** Ve **-=** işleçleri assert, `COleDateTime` kümesi nesnesi null. Bkz: [COleDateTime ilişkisel işleçler](#coledatetime_relational_operators) örneği.

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_date"></a>  COleDateTime::operator tarihi

Dönüştürür bir `ColeDateTime` içine değeri bir `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç döndürür bir `DATE` nesne değeri bu kopyalanır `COleDateTime` nesne. Uygulaması hakkında daha fazla bilgi için `DATE` nesne, makaleye göz atın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

`DATE` İşleci assert, `COleDateTime` kümesi nesnesi null. Bkz: [COleDateTime ilişkisel işleçler](#coledatetime_relational_operators) örneği.

##  <a name="parsedatetime"></a>  COleDateTime::ParseDateTime

Bir tarih/saat değerini okumak için bir dizeyi ayrıştırır.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*lpszDate*<br/>
Ayrıştırılacak olan boş sonlandırılmış dizeye bir işaretçi. Ayrıntılar için açıklamalara bakın.

*CertOpenStore*<br/>
Yerel ayarlar ve ayrıştırmaktan bayrakları belirtir. Bir veya daha fazla aşağıdaki bayraklar:

- LOCALE_NOUSEROVERRIDE sistem varsayılan yerel ayarları yerine özel kullanıcı ayarları kullanın.

- VAR_TIMEVALUEONLY tarih bölümü ayrıştırılırken yoksayın.

- VAR_DATEVALUEONLY Ayrıştırma sırasında saat kısmının yoksayın.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar Kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Dizeyi tarih/saat değerine, aksi takdirde FALSE başarıyla dönüştürüldü varsa TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Dize bir tarih/saat başarılı bir şekilde dönüştürülmüş değeri, bu değeri `COleDateTime` nesne ayarlandığından bu değeri ve durumu için geçerli.

> [!NOTE]
>  Yıl değerlerini aralığında 100 ve 9999 arasında olmalıdır.

*LpszDate* parametresi, çeşitli biçimlerde alabilir. Örneğin, aşağıdaki dizeleri kabul edilebilir bir tarih/saat biçimleri içerir:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Yerel ayar kimliği dize biçiminde bir tarih/saat değerine dönüştürme için kabul edilebilir olup olmadığını da etkileneceğini unutmayın.

VAR_DATEVALUEONLY söz konusu olduğunda, 0 veya gece saat saat değerine ayarlanır. VAR_TIMEVALUEONLY söz konusu olduğunda, tarih değeri 30 Aralık 1899 anlamına gelen tarih için 0, ayarlanır.

Dizeyi tarih/saat değerine dönüştürülemedi veya sayısal bir taşma, bu durum ise `COleDateTime` nesnesi geçersiz.

Logrequest olayını ve sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="setdate"></a>  COleDateTime::SetDate

Bu tarihin ayarlar `COleDateTime` nesne.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Parametreler

*nYear*, *nMonth*, *nhatalı günü*<br/>
Bu kopyalanacak tarih bileşenleri gösteren `COleDateTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Sıfır ise bu değeri `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Bu dönüş değeri dayanır `DateTimeStatus` listelenmiş türü. Daha fazla bilgi için [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Tarih için belirtilen değerlere ayarlanır. Süresi, süresi 0, gece yarısı olarak ayarlanır.

Parametre değerleri için sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nhatalı günü*|0 - 31|

Ayın gününü taşarsa doğru sonraki ayın ve ayın günü için dönüştürülür ve/veya yıl buna göre artırılır. Sıfır gün değerini, önceki ayın son gününü belirtir. Aynı durum geçerlidir `SystemTimeToVariantTime`.

Parametrelerle belirtilen bir tarih değeri geçerli değil, bu nesnenin durumu kümesine `COleDateTime::invalid`. Kullanmanız gereken [GetStatus](#getstatus) geçerliliğini denetlemek için `DATE` değeri ve bu varsayımında bulunmamalıdır değerini [m_dt](#m_dt) değiştirilmemiş olarak kalır.

Tarih değerlerine ilişkin bazı örnekler şunlardır:

|*nYear*|*nMonth*|*nhatalı günü*|Değer|
|-------------|--------------|------------|-----------|
|2000|2|29|29 Şubat 2000|
|1776|7|4|4 Temmuz 1776|
|1925|4|35|35 Nisan 1925 (geçersiz tarih)|
|10000|1.|1.|1 Ocak 10000 (geçersiz tarih)|

Tarih ve saat hem ayarlamak için bkz: [COleDateTime::SetDateTime](#setdatetime).

Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

##  <a name="setdatetime"></a>  COleDateTime::SetDateTime

Tarih ve saat bu ayarlar `COleDateTime` nesne.

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

*nYear*, *nMonth*, *nhatalı günü*, *nHour*, *nMin*, *nSec*<br/>
Bu kopyalanacak tarih ve saat bileşenlerini belirtmek `COleDateTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Sıfır ise bu değeri `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Bu dönüş değeri dayanır `DateTimeStatus` listelenmiş türü. Daha fazla bilgi için [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Parametre değerleri için sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*nYear*|100 - 9999|
|*nMonth*|1 - 12|
|*nhatalı günü*|0 - 31|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Ayın gününü taşarsa doğru sonraki ayın ve ayın günü için dönüştürülür ve/veya yıl buna göre artırılır. Sıfır gün değerini, önceki ayın son gününü belirtir. Aynı durum geçerlidir [SystemTimeToVariantTime](/windows/desktop/api/oleauto/nf-oleauto-systemtimetovarianttime).

Parametreler ile belirtilen tarih veya saat değeri, bu nesnenin durumu geçersiz ve bu nesnenin değeri olarak ayarlanır, geçerli değilse değiştirilmez.

Zaman değerlerine ilişkin bazı örnekler şunlardır:

|*nHour*|*nMin*|*nSec*|Değer|
|-------------|------------|------------|-----------|
|1.|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Tarih değerlerine ilişkin bazı örnekler şunlardır:

|*nYear*|*nMonth*|*nhatalı günü*|Değer|
|-------------|--------------|------------|-----------|
|1995|4|15|15 Nisan 1995|
|1789|7|14|17 Temmuz 1789|
|1925|2|30|Geçersiz|
|10000|1.|1.|Geçersiz|

Yalnızca tarihi ayarlamak için bkz [COleDateTime::SetDate](#setdate). Yalnızca bir kez ayarlamak için bkz [COleDateTime::SetTime](#settime).

Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

Örneğin bakın [GetStatus](#getstatus).

##  <a name="setstatus"></a>  COleDateTime::SetStatus

Bu durumu ayarlar `COleDateTime` nesne.

```
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Bu yeni durum değeri `COleDateTime` nesne.

### <a name="remarks"></a>Açıklamalar

*Durumu* parametre değeri tarafından tanımlanan `DateTimeStatus` listelenmiş içinde tanımlanan bir türü `COleDateTime` sınıfı. Bkz: [COleDateTime::GetStatus](#getstatus) Ayrıntılar için.

> [!CAUTION]
>  Bu işlev, Gelişmiş programlama durumlar için kullanılır. Bu işlev, bu nesne verileri değiştirmez. Durumu ayarlamak için en sık kullanılacak **null** veya **geçersiz**. Unutmayın atama işleci ( [işleç =](#eq)) ve [SetDateTime](#setdatetime) kaynak değerleri üzerinde temel bir nesnenin durumu ayarlayın.

### <a name="example"></a>Örnek

Örneğin bakın [GetStatus](#getstatus).

##  <a name="settime"></a>  COleDateTime::SetTime

Bu süreyi ayarlar `COleDateTime` nesne.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parametreler

*nHour*, *nMin*, *nSec*<br/>
Bu kopyalanacak zaman bileşenleri gösteren `COleDateTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Sıfır ise bu değeri `COleDateTime` nesne 1 ayarlandığı başarıyla; Aksi takdirde. Bu dönüş değeri dayanır `DateTimeStatus` listelenmiş türü. Daha fazla bilgi için [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Saat için belirtilen değerlere ayarlanır. 30 Aralık 1899 anlamına gelen tarih için 0, tarihi ayarlanır.

Parametre değerleri için sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*nHour*|0 - 23|
|*nMin*|0 - 59|
|*nSec*|0 - 59|

Parametreler ile belirtilen değer geçerli değil. zaman bu nesnenin durumu geçersiz ve bu nesnenin değerini ayarlanırsa değiştirilmez.

Zaman değerlerine ilişkin bazı örnekler şunlardır:

|*nHour*|*nMin*|*nSec*|Değer|
|-------------|------------|------------|-----------|
|1.|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Tarih ve saat hem ayarlamak için bkz: [COleDateTime::SetDateTime](#setdatetime).

Bu değeri sorgu üye işlevleri hakkında bilgi için `COleDateTime` nesne, aşağıdaki üye işlevleri bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

Sınırları hakkında daha fazla bilgi için `COleDateTime` değerleri başlıklı makaleye bakın [tarih ve saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

Örneğin bakın [SetDate](#setdate).

## <a name="see-also"></a>Ayrıca Bkz.

[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CTime Sınıfı](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)

