---
title: Cotadatetime sınıfı
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
ms.openlocfilehash: a254019d1efe916365799affa3d2c5271883bafb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491266"
---
# <a name="coledatetime-class"></a>Cotadatetime sınıfı

OLE Otomasyonu 'nda kullanılan veritürünükapsüller.`DATE`

## <a name="syntax"></a>Sözdizimi

```
class COleDateTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Copadatetime:: Cotadatetime](#coledatetime)|Bir `COleDateTime` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatetime:: Format](#format)|Bir `COleDateTime` nesnenin biçimli dize temsilini oluşturur.|
|[Cotadatetime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|`COleDateTime` Nesne içindeki saati bir `DBTIMESTAMP` veri yapısı olarak almak için bu yöntemi çağırın.|
|[Cotadatetime:: GetAsSystemTime](#getassystemtime)|`COleDateTime` Nesne içindeki saati bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) veri yapısı olarak almak için bu yöntemi çağırın.|
|[Cotadatetime:: GetAsUDATE](#getasudate)|Saati `COleDateTime` `UDATE` veri yapısı olarak almak için bu yöntemi çağırın.|
|[Cotadatetime:: GetCurrentTime](#getcurrenttime)|Geçerli saati `COleDateTime` (statik üye işlevi) temsil eden bir nesne oluşturur.|
|[Cotadatetime:: GetDay](#getday)|Bu `COleDateTime` nesnenin gösterdiği günü döndürür (1-31).|
|[Cotadatetime:: GetDayOfWeek](#getdayofweek)|Bu `COleDateTime` nesnenin temsil ettiği haftanın gününü döndürür (Pazar = 1).|
|[Cotadatetime:: GetDayOfYear](#getdayofyear)|Bu `COleDateTime` nesnenin temsil ettiği yılın gününü döndürür (Ocak 1 = 1).|
|[Cotadatetime:: GetHour](#gethour)|Bu `COleDateTime` nesnenin temsil ettiği saati döndürür (0-23).|
|[Cotadatetime:: GetMinute](#getminute)|Bu `COleDateTime` nesnenin temsil ettiği dakikayı döndürür (0-59).|
|[Cotadatetime:: GetMonth](#getmonth)|Bu `COleDateTime` nesnenin temsil ettiği ayı döndürür (1-12).|
|[Cotadatetime:: GetSecond](#getsecond)|Bu `COleDateTime` nesnenin temsil ettiği saniyeyi döndürür (0-59).|
|[Cotadatetime:: GetStatus](#getstatus)|Bu `COleDateTime` nesnenin durumunu (geçerlilik) alır.|
|[Cotadatetime:: GetYear](#getyear)|Bu `COleDateTime` nesnenin temsil ettiği yılı döndürür.|
|[Cotadatetime::P arseDateTime](#parsedatetime)|Bir dizeden tarih/saat değerini okur ve değerini `COleDateTime`ayarlar.|
|[Cotadatetime:: SetDate](#setdate)|Bu `COleDateTime` nesnenin değerini yalnızca belirtilen tarih-değer değerine ayarlar.|
|[Cotadatetime:: SetDateTime](#setdatetime)|Bu `COleDateTime` nesnenin değerini belirtilen tarih/saat değerine ayarlar.|
|[Cotadatetime:: SetStatus](#setstatus)|Bu `COleDateTime` nesnenin durumunu (geçerlilik) ayarlar.|
|[Cotadatetime:: SetTime](#settime)|Bu `COleDateTime` nesnenin değerini belirtilen yalnızca saat değerine ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[COleDateTime:: operator = =, COleDateTime:: operator <, vb.](#coledatetime_relational_operators)|İki `COleDateTime` değeri karşılaştırın.|
|[COleDateTime:: operator +, COleDateTime:: operator-](#operator_add_-)|Değer ekleme ve `COleDateTime` çıkarma.|
|[COleDateTime:: operator + =, COleDateTime:: operator-=](#operator_add_eq_-_eq)|`COleDateTime` Bu`COleDateTime` nesneden bir değer ekleyin ve çıkarın.|
|[COleDateTime:: operator =](#operator_eq)|Bir `COleDateTime` değeri kopyalar.|
|[COleDateTime:: operator DATE, COleDateTime:: operator Date *](#operator_date)|Bir değeri bir `DATE` veya`DATE*`öğesine dönüştürür. `COleDateTime`|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cotadatetime:: m_dt](#m_dt)|`DATE` Bu`COleDateTime` nesne için temeldeki öğesini içerir.|
|[Cotadatetime:: m_status](#m_status)|Bu `COleDateTime` nesnenin durumunu içerir.|

## <a name="remarks"></a>Açıklamalar

`COleDateTime`taban sınıfına sahip değildir.

OLE otomasyonunun [değişken](/windows/win32/api/oaidl/ns-oaidl-variant) veri türü için olası türlerden biridir. `COleDateTime` Değer, mutlak bir tarih ve saat değerini temsil eder.

Tür `DATE` , kayan noktalı bir değer olarak uygulanır. Gün sayısı 30 Aralık 1899, gece yarısı ölçülür. Aşağıdaki tabloda bazı tarihler ve bunlarla ilişkili değerler gösterilmektedir:

|Tarih|Değer|
|----------|-----------|
|29 Aralık 1899, gece yarısı|-1.0|
|29 Aralık 1899, 6 A. d|-1.25|
|30 Aralık 1899, gece yarısı|0.0|
|31 Aralık 1899, gece yarısı|1.0|
|1 Ocak 1900, 11:00|2.25|

> [!CAUTION]
> Yukarıdaki tabloda, gün değerleri 30 Aralık 1899 ' de gece yarısından önce negatif hale gelir, ancak gün saati değerleri değildir. Örneğin, günü temsil eden tamsayının pozitif mi (30 Aralık 6:00 1899 ' den önce) yoksa negatif mi (30 Aralık 1899 tarihinden önce) olsun, olarak her zaman bir kesirli değer 0,25 olarak temsil edilir. Bu, basit bir kayan nokta karşılaştırmasının yanlışlıkla 12/29/1899 ' de bir `COleDateTime` temsil eden 6:00 ' i, aynı günde bir ' ı temsil 7:00 eden farklı bir şekilde sıralaması gerektiği anlamına gelir.

`COleDateTime` Sınıfı, 1 Ocak 100 ' den 31 Aralık 9999 ' ye kadar olan tarihleri işler. `COleDateTime` Sınıf, Gregoryen takvimini kullanır; bu, Jülyen tarihleri desteklemez. `COleDateTime`Gündüz kaydetme süresini yoksayar. (Bkz [. Tarih ve Saat: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).)

> [!NOTE]
> Yalnızca 1900 ' den `%y` başlayan tarihler için iki basamaklı bir yıl almak üzere biçimini kullanabilirsiniz. `%y` Biçimi 1900 ' den önceki bir tarih üzerinde kullanırsanız, kod bir onaylama hatası oluşturur.

Bu tür, yalnızca tarih veya yalnızca saat değerlerini temsil etmek için de kullanılır. Kurala göre, 0 (Aralık 30, 1899) tarihi yalnızca saat değerleri için kullanılır ve 00:00 (gece yarısı) zamanı yalnızca tarih değerleri için kullanılır.

100 'den küçük bir `COleDateTime` Tarih kullanarak bir nesne oluşturursanız, tarih kabul edilir, ancak sonraki `GetYear`, `GetMinute` `GetHour` `GetMonth` `GetDay`,,,, ve `GetSecond` başarısız olur ve-1 döndürür. Daha önce, iki basamaklı tarihleri kullanabilirsiniz, ancak tarihler MFC 4,2 ve sonrasında 100 veya daha büyük olmalıdır.

Sorunlardan kaçınmak için dört basamaklı bir tarih belirtin. Örneğin:

[!code-cpp[NVC_ATLMFC_Utilities#1](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_1.cpp)]

`COleDateTime` Değerler için temel aritmetik işlemler [cotadatetimespan](../../atl-mfc-shared/reference/coledatetimespan-class.md)yardımcı sınıfını kullanır. `COleDateTimeSpan`değerler bir zaman aralığı tanımlar. Bu sınıflar arasındaki ilişki, [CTime](../../atl-mfc-shared/reference/ctime-class.md) ve [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md)arasında bir örneğe benzerdir.

`COleDateTime` [Ve sınıflarıhakkındadahafazlabilgiiçinbkz.Tarihvesaatmakalesi:`COleDateTimeSpan` Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

## <a name="requirements"></a>Gereksinimler

**Üst bilgi** ATLComTime. h

##  <a name="coledatetime_relational_operators"></a>Cotadatetime Ilişkisel Işleçleri

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

*güncel*<br/>
Karşılaştırılacak `COleDateTime` nesne.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  İki işlenenden biri geçersiz olursa ATLASSERT meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#13](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_2.cpp)]

### <a name="example"></a>Örnek

,, **>=** Ve **\<işleçleri ,=nesnenullolarak** ayarlandıysaonayalacak`COleDateTime` . **>** **<**

[!code-cpp[NVC_ATLMFC_Utilities#170](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_3.cpp)]

##  <a name="coledatetime"></a>Copadatetime:: Cotadatetime

Bir `COleDateTime` nesnesi oluşturur.

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

*Tarih Kaynak*<br/>
`COleDateTime` Yeni`COleDateTime` nesneye Kopyalanacak varolan bir nesne.

*varSrc*<br/>
Bir tarih `VARIANT` /saat değerine (VT_DATE `COleVariant` ) dönüştürülecek ve yeni `COleDateTime` nesneye kopyalanabilecek mevcut bir veri yapısı (muhtemelen bir nesne).

*dtSrc*<br/>
`DATE` Yeni`COleDateTime` nesneye kopyalanacak bir tarih/saat () değeri.

*zaman dilimlerini*<br/>
Bir `time_t` Tarih `__time64_t` /saat değerine dönüştürülecek ve yeni `COleDateTime` nesneye kopyalandığı bir veya değeri.

*systimeSrc*<br/>
Bir `SYSTEMTIME` tarih/saat değerine dönüştürülecek ve yeni `COleDateTime` nesneye kopyaladığınız bir yapı.

*filetimeSrc*<br/>
Bir `FILETIME` tarih/saat değerine dönüştürülecek ve yeni `COleDateTime` nesneye kopyaladığınız bir yapı. , Evrensel Eşgüdümlü saat (UTC) kullanır,bunedenleyapıdayerelbirsaatgeçirirseniz,sonuçlarınızyanlışolur.`FILETIME` Daha fazla bilgi için Windows SDK [Dosya sürelerine](/windows/win32/SysInfo/file-times) bakın.

*nYear*, *nmonth*, *nday*, *nhour*, *nMin*, *NSEC*<br/>
Yeni `COleDateTime` nesneye kopyalanacak tarih ve saat değerlerini belirtin.

*Wdosdate*, *wdostime*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `COleDateTime` nesneye kopyalandığı MS-DOS tarih ve saat değerleri.

*Ilişkin*<br/>
Geçerli yerel saati içeren bir [DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Tüm bu oluşturucular, belirtilen `COleDateTime` değere başlatılan yeni nesneler oluşturur. Aşağıdaki tabloda her bir tarih ve saat bileşeni için geçerli aralıklar gösterilmektedir:

|Tarih/saat bileşeni|Geçerli Aralık|
|--------------------------|-----------------|
|yıl|100 - 9999|
|ay|0 - 12|
|gün|0 - 31|
|saate|0 - 23|
|dakikaya|0 - 59|
|İkincisi|0 - 59|

Gün bileşeni için gerçek üst sınır, ay ve yıl bileşenlerine göre farklılık gösterir. Ayrıntılar için bkz `SetDate` . veya `SetDateTime` üye işlevleri.

Her oluşturucunun kısa bir açıklaması aşağıda verilmiştir:

- `COleDateTime(` **)** 0 olarak `COleDateTime` başlatılan bir nesne oluşturur (gece yarısı, 30 Aralık 1899).

- `COleDateTime(`) Var olan `COleDateTime` bir`COleDateTime` nesneden bir nesne oluşturur. `dateSrc`

- `COleDateTime(`*varSrc* **)** Bir `COleDateTime` nesnesi oluşturur. Bir `VARIANT` yapıyı veya [cotavariant](../../mfc/reference/colevariant-class.md) nesnesini bir tarih/saat ( `VT_DATE`) değerine dönüştürmeye çalışır. Bu dönüştürme başarılı olursa, dönüştürülmüş değer yeni `COleDateTime` nesneye kopyalanır. Değilse, `COleDateTime` nesnenin değeri 0 (gece yarısı, 30 Aralık 1899) ve durumu geçersiz olarak ayarlanır.

- `COleDateTime(`) Bir değerden`DATE` bir `COleDateTime` nesne oluşturur. `dtSrc`

- `COleDateTime(`) Bir değerden`time_t` bir `COleDateTime` nesne oluşturur. `timeSrc`

- `COleDateTime(`*Systimesrc* **)** Bir `SYSTEMTIME` değerden `COleDateTime` bir nesne oluşturur.

- `COleDateTime(`) Bir değerden`FILETIME` bir `COleDateTime` nesne oluşturur. `filetimeSrc` biçimindeki telefon numarasıdır. , Evrensel Eşgüdümlü saat (UTC) kullanır,bunedenleyapıdayerelbirsaatgeçirirseniz,sonuçlarınızyanlışolur.`FILETIME` Daha fazla bilgi için Windows SDK [Dosya zamanları](/windows/win32/SysInfo/file-times) bölümüne bakın.

- `COleDateTime(``nYear`, ,`nMonth` ,,`nMin`,)Belirtilensayısal değerlerden bir nesne`COleDateTime` oluşturur. `nSec` `nHour` `nDay`

- `COleDateTime(``wDosDate`, )`wDosTime` Belirtilen MS-DOS `COleDateTime` tarih ve saat değerlerinden bir nesne oluşturur.

`time_t` Veri türü hakkında daha fazla bilgi için *çalışma zamanı kitaplık başvurusundaki* [Time](../../c-runtime-library/reference/time-time32-time64.md) işlevine bakın.

Daha fazla bilgi için Windows SDK [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapılarına bakın.

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

> [!NOTE]
> Parametresi kullanılarak `DBTIMESTAMP` Oluşturucu yalnızca OLEDB. h dahil edildiğinde kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#2](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_4.cpp)]

##  <a name="format"></a>Cotadatetime:: Format

Tarih/saat değerinin biçimli bir temsilini oluşturur.

```
CString Format(DWORD dwFlags = 0,  LCID lcid = LANG_USER_DEFAULT) const;
CString Format(LPCTSTR lpszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*dwFlags*<br/>
Aşağıdaki yerel ayar bayraklarından birini belirtir:

- LOCALE_NOUSEROVERRIDE özel Kullanıcı ayarları yerine sistem varsayılan yerel ayar ayarlarını kullanın.

- VAR_TIMEVALUEONLY, ayrıştırma sırasında tarih bölümünü yoksayar.

- VAR_DATEVALUEONLY, ayrıştırma sırasında zaman bölümünü yoksayar.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar KIMLIĞINI gösterir. Dil tanımlayıcıları hakkında daha fazla bilgi için bkz. [Dil tanımlayıcıları](/windows/win32/Intl/language-identifiers).

*lpszFormat*<br/>
Biçimlendirme dizesine benzer `printf` bir biçimlendirme dizesi. Bir yüzde ( `%`) işaretinden önce gelen her biçimlendirme kodu, ilgili `COleDateTime` bileşen ile değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. Daha fazla bilgi için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md). İçin `Format` biçimlendirme kodlarının değeri ve anlamı şunlardır:

- `%H`Geçerli gündeki saat

- `%M`Geçerli saat içindeki dakika sayısı

- `%S`Geçerli dakikadaki Saniyeler

- `%%`Yüzde işareti

*nFormatID*<br/>
Biçim denetimi dizesinin kaynak KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimli `CString` tarih/saat değerini içeren bir.

### <a name="remarks"></a>Açıklamalar

Bu `COleDateTime` nesnenin durumu null ise, dönüş değeri boş bir dizedir. Durum geçersizse, döndürülen dize ATL_IDS_DATETIME_INVALID dize kaynağı tarafından belirtilir.

Bu işlev için üç formun kısa bir açıklaması aşağıdadır:

`Format`( *dwFlags*, *LCID*)<br/>
Bu form, tarih ve saat için dil belirtimlerini (yerel ayar kimlikleri) kullanarak değeri biçimlendirir. Bu form, varsayılan parametreleri kullanarak tarihi ve saati, zaman kısmı 0 (gece yarısı) değilse, bu durumda yalnızca tarihi yazdıracaktır veya tarih kısmı 0 (30 Aralık 1899) ise, bu durumda yalnızca saati yazdıracaktır. Tarih/saat değeri 0 (30 Aralık 1899, gece yarısı) ise, Varsayılan parametrelere sahip bu form gece yarısı yazdırılır.

`Format`( *lpszFormat*)<br/>
Bu form, içinde `printf`olduğu gibi yüzde işareti (%) olan özel biçimlendirme kodları içeren biçim dizesini kullanarak değeri biçimlendirir. Biçimlendirme dizesi, işleve parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz. çalışma zamanı kitaplık başvurusunda [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

`Format`( *nFormatID*)<br/>
Bu form, içinde `printf`olduğu gibi yüzde işareti (%) olan özel biçimlendirme kodları içeren biçim dizesini kullanarak değeri biçimlendirir. Biçimlendirme dizesi bir kaynaktır. Bu dize kaynağının KIMLIĞI parametre olarak geçirilir. Biçimlendirme kodları hakkında daha fazla bilgi için bkz. *çalışma zamanı kitaplık başvurusunda* [strftime, wcsftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#3](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_5.cpp)]

##  <a name="getasdbtimestamp"></a>Cotadatetime:: GetAsDBTIMESTAMP

`COleDateTime` Nesne içindeki saati bir `DBTIMESTAMP` veri yapısı olarak almak için bu yöntemi çağırın.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& timeStamp) const throw();
```

### <a name="parameters"></a>Parametreler

*Ilişkin*<br/>
[DBTimeStamp](/dotnet/api/system.data.oledb.oledbtype) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Elde edilen süreyi başvurulan *zaman damgası* yapısına depolar. Bu işlev tarafından başlatılan `fraction` veriyapısınınüyesisıfıraayarlanmışolacak.`DBTIMESTAMP`

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#4](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_6.cpp)]

##  <a name="getassystemtime"></a>Cotadatetime:: GetAsSystemTime

`COleDateTime` Nesne içindeki saati bir `SYSTEMTIME` veri yapısı olarak almak için bu yöntemi çağırın.

```
bool GetAsSystemTime(SYSTEMTIME& sysTime) const throw();
```

### <a name="parameters"></a>Parametreler

*sysTime*<br/>
`COleDateTime` Nesnesinden dönüştürülmüş tarih/saat değerini almak için bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Dönüştürme başarısız olursa veya `COleDateTime` nesne null ya da geçersiz ise false.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime`elde edilen süreyi başvurulan *SysTime* nesnesinde depolar. Bu işlev tarafından başlatılan `wMilliseconds` veriyapısınınüyesisıfıraayarlanmışolacak.`SYSTEMTIME`

Bir `COleDateTime` nesnede tutulan durum bilgileri hakkında daha fazla bilgi için bkz. [GetStatus](#getstatus).

##  <a name="getasudate"></a>Cotadatetime:: GetAsUDATE

`COleDateTime` Nesne içindeki saati bir `UDATE` veri yapısı olarak almak için bu yöntemi çağırın.

```
bool GetAsUDATE(UDATE& uDate) const throw();
```

### <a name="parameters"></a>Parametreler

*Uıdate*<br/>
Nesnesinden dönüştürülmüş Tarih/ `UDATE` saat değerini almak için bir yapıya başvuru. `COleDateTime`

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE döndürür; Dönüştürme başarısız olursa veya `COleDateTime` nesne null ya da geçersiz ise false.

### <a name="remarks"></a>Açıklamalar

Bir `UDATE` yapı "paketten çıkarılan" bir tarihi temsil eder.

##  <a name="getcurrenttime"></a>Cotadatetime:: GetCurrentTime

Geçerli tarih/saat değerini döndürmek için bu statik üye işlevini çağırın.

```
static COleDateTime WINAPI GetCurrentTime() throw();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#5](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_7.cpp)]

##  <a name="getday"></a>Cotadatetime:: GetDay

Bu tarih/saat değeri ile temsil edilen ayın gününü alır.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen ayın günü veya `COleDateTime::error` gün elde edilememe.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 1 ile 31 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#6](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_8.cpp)]

##  <a name="getdayofweek"></a>Cotadatetime:: GetDayOfWeek

Bu tarih/saat değeri ile temsil edilen ayın gününü alır.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen veya `COleDateTime::error` haftanın günü alınamadığından haftanın günü.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 1 ile 7 arasında, 1 = Pazar, 2 = Pazartesi vb. arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#7](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_9.cpp)]

##  <a name="getdayofyear"></a>Cotadatetime:: GetDayOfYear

Bu tarih/saat değeri ile temsil edilen yılın gününü alır.

```
int GetDayOfYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen yılın günü veya `COleDateTime::error` yılın günü edinilemedi.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 1 ile 366 arasında (1 = 1) arasındadır.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#8](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_10.cpp)]

##  <a name="gethour"></a>Cotadatetime:: GetHour

Bu tarih/saat değeri ile temsil edilen saati alır.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen saat veya `COleDateTime::error` saat elde edilememelidir.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 0 ile 23 arasında.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#9](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_11.cpp)]

##  <a name="getminute"></a>Cotadatetime:: GetMinute

Bu tarih/saat değeri ile temsil edilen dakikayı alır.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen dakika veya `COleDateTime::error` dakika elde edilememe.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 0 ile 59 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="getmonth"></a>Cotadatetime:: GetMonth

Bu tarih/saat değeri ile temsil edilen ayı alır.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri veya `COleDateTime::error` ay elde edibir değere göre temsil edilen ay.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 1 ile 12 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="getsecond"></a>Cotadatetime:: GetSecond

Bu tarih/saat değeri ile temsil edilen saniyeyi alır.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri veya `COleDateTime::error` ikincisi alınamadığından temsil edilen ikinci değer.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri 0 ile 59 arasında değişir.

> [!NOTE]
>  Sınıf `COleDateTime` , artık saniyeler desteklemez.

Uygulamasına yönelik `COleDateTime`uygulama hakkında daha fazla bilgi için bkz. Tarih [ve saat makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="getstatus"></a>Cotadatetime:: GetStatus

Belirli `COleDateTime` bir nesnenin durumunu (geçerlilik) alır.

```
DateTimeStatus GetStatus() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` değerin durumunu döndürür. Varsayılan değer ile `GetStatus` oluşturulmuş bir `COleDateTime` nesne üzerinde çağrı yaparsanız, geçerli döndürülür. Oluşturucu null olarak `GetStatus` ayarlanmış şekilde `COleDateTime` başlatılan bir nesneyi çağırırsanız, `GetStatus` null döndürür.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri, `COleDateTime` sınıfı içinde tanımlanan, `DateTimeStatus` numaralandırılmış tür tarafından tanımlanır.

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

- `COleDateTime::error`Tarih/saat değerinin bir bölümünü almaya çalışırken bir hata oluştuğunu belirtir.

- `COleDateTime::valid`Bu `COleDateTime` nesnenin geçerli olduğunu gösterir.

- `COleDateTime::invalid`Bu `COleDateTime` nesnenin geçersiz olduğunu gösterir; diğer bir deyişle, değeri yanlış olabilir.

- `COleDateTime::null`Bu `COleDateTime` nesnenin null olduğunu, yani bu nesne için hiçbir değer sağlanmadığını gösterir. (Bu, "değer olmadan", C++ null değerinin aksine, veritabanı "null" değeridir.)

Bir `COleDateTime` nesnenin durumu aşağıdaki durumlarda geçersizdir:

- Değeri bir tarih/saat değerine dönüştürülemeyen `VARIANT` bir `COleVariant` veya değerinden ayarlandıysa.

- Değeri, geçerli bir tarih/saat `time_t`değerine `SYSTEMTIME`dönüştürülemeyen bir `FILETIME` , veya değerinden ayarlandıysa.

- Değeri geçersiz parametre değerleriyle ayarlanmış `SetDateTime` ise.

- Bu nesne bir aritmetik atama işlemi `+=` `-=`sırasında bir taşma veya yetersiz

- Bu nesneye geçersiz bir değer atanmışsa.

- Bu nesnenin durumu, kullanılarak `SetStatus`açıkça geçersiz olarak ayarlandıysa.

Durumu geçersiz olarak ayarlayaetkileyebilecek işlemler hakkında daha fazla bilgi için aşağıdaki üye işlevlere bakın:

- [Cotadatetime](#coledatetime)

- [SetDateTime](#setdatetime)

- [işleç +,-](#operator_add_-)

- [işleç + =,-=](#operator_add_eq_-_eq)

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#10](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_12.cpp)]

##  <a name="getyear"></a>Cotadatetime:: GetYear

Bu tarih/saat değeri ile temsil edilen yılı alır.

```
int GetYear() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri ile temsil edilen yıl veya `COleDateTime::error` yıl elde edilememe.

### <a name="remarks"></a>Açıklamalar

Geçerli dönüş değerleri, yüzyıl 'yi içeren 100 ve 9999 arasında değişir.

Bu `COleDateTime` nesnenin değerini sorgulayan diğer üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="m_dt"></a>Cotadatetime:: m_dt

`DATE` Bu`COleDateTime` nesnenin temel yapısı.

```
DATE m_dt;
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Bu işlevin döndürdüğü işaretçinin eriştiği `DATE` nesnedeki değeri değiştirmek, bu `COleDateTime` nesnenin değerini değiştirecek. Bu `COleDateTime` nesnenin durumunu değiştirmez.

`DATE` Nesnesinin uygulanması hakkında daha fazla bilgi için bkz. Tarih ve saat makalesi [: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="m_status"></a>Cotadatetime:: m_status

Bu `COleDateTime` nesnenin durumunu içerir.

```
DateTimeStatus m_status;
```

### <a name="remarks"></a>Açıklamalar

Bu veri üyesinin türü, `DateTimeStatus` `COleDateTime` sınıfı içinde tanımlanan, numaralandırılmış türüdür. Daha fazla bilgi için bkz. [Copadatetime:: GetStatus](#getstatus).

> [!CAUTION]
>  Bu veri üyesi gelişmiş programlama durumlarına yöneliktir. [GetStatus](#getstatus) ve [SetStatus](#setstatus)satır içi üye işlevlerini kullanmanız gerekir. Bu `SetStatus` veri üyesini açıkça ayarlamayla ilgili daha fazla uyarı için bkz.

##  <a name="operator_eq"></a>COleDateTime:: operator =

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

Bu aşırı yüklenmiş atama işleçleri, kaynak tarih/saat değerini bu `COleDateTime` nesneye kopyalar. Bu aşırı yüklenmiş tüm atama işleçleri için kısa bir açıklama aşağıda verilmiştir:

- **operator = (** `dateSrc` **)** işlenenin değeri ve durumu bu `COleDateTime` nesneye kopyalanır.

- **operator = (** *varSrc* **)** [Değişken](/windows/win32/api/oaidl/ns-oaidl-variant) değer (veya [colevaryant](../../mfc/reference/colevariant-class.md) nesnesi) bir tarih/saat (VT_DATE) olarak dönüştürülürse, dönüştürülen değer bu `COleDateTime` nesneye kopyalanır ve durumu geçerli olarak ayarlanır. Dönüştürme başarılı olmazsa, bu nesnenin değeri sıfır (30 Aralık 1899, gece yarısı) ve durumu geçersiz olarak ayarlanır.

- **operator = (** `dtSrc` **)** `DATE` değer Bu`COleDateTime` nesneye kopyalanır ve durumu geçerli olarak ayarlanır.

- **operator = (** `timeSrc` `COleDateTime` **)** `time_t` veya`__time64_t` değeri dönüştürülür ve bu nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır.

- **operator = (** *systimesrc* **)** [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) değeri dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır.

- **operator = (** `uDate` `COleDateTime` )`UDATE` değer dönüştürülür ve bu nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; başarısız olursa, geçersiz olarak ayarlanır. Bir `UDATE` yapı "paketten çıkarılan" bir tarihi temsil eder. Daha fazla bilgi için bkz. [VarDateFromUdate](/windows/win32/api/oleauto/nf-oleauto-vardatefromudate)işlevi.

- **operator = (** `filetimeSrc` **)** [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) değeri dönüştürülür ve bu `COleDateTime` nesneye kopyalanır. Dönüştürme başarılı olursa, bu nesnenin durumu geçerli olarak ayarlanır; Aksi halde, geçersiz olarak ayarlanır. `FILETIME`Evrensel Eşgüdümlü saat (UTC) kullanır. bu nedenle, yapıya bir UTC saati geçirirseniz, sonuçlarınız UTC saatinden yerel saate dönüştürülür ve değişken zaman olarak depolanır. Bu davranış, Visual C++ 6,0 ve visual C++.NET 2003 SP2 ile aynıdır. Daha fazla bilgi için Windows SDK [Dosya zamanları](/windows/win32/SysInfo/file-times) bölümüne bakın.

Daha fazla bilgi için Windows SDK [Varyant](/windows/win32/api/oaidl/ns-oaidl-variant) girişine bakın.

`time_t` Veri türü hakkında daha fazla bilgi için *çalışma zamanı kitaplık başvurusundaki* [Time](../../c-runtime-library/reference/time-time32-time64.md) işlevine bakın.

Daha fazla bilgi için Windows SDK [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapılarına bakın.

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_add_-"></a>COleDateTime:: operator +,-

Değer ekleme ve `ColeDateTime` çıkarma.

```
COleDateTime operator+(COleDateTimeSpan dateSpan) const throw();
COleDateTime operator-(COleDateTimeSpan dateSpan) const throw();
COleDateTimeSpan operator-(const COleDateTime& date) const throw();
```

### <a name="remarks"></a>Açıklamalar

`COleDateTime`nesneler mutlak zamanları temsil eder. [Cotadatetimespan](../../atl-mfc-shared/reference/coledatetimespan-class.md) nesneleri göreli zamanları temsil eder. İlk iki operatör bir `COleDateTimeSpan` `COleDateTime` değerden değer eklemenize ve çıkartabilir olanak sağlar. Üçüncü işleç bir değeri başka bir değerden çıkarmak `COleDateTime` için `COleDateTimeSpan` bir değer elde etmenizi sağlar.

İşlenenden biri null ise, sonuçta elde edilen `COleDateTime` değerin durumu null olur.

Elde edilen `COleDateTime` değer kabul edilebilir değerler sınırlarının dışında kalırsa, bu `COleDateTime` değerin durumu geçersiz olur.

İşlenenden biri geçersiz ve diğeri null değilse, sonuçta elde edilen `COleDateTime` değerin durumu geçersizdir.

Ve **+** **işleçleri-,nesnenullolarak** ayarlandıysaonayalacak.`COleDateTime` Bir örnek için bkz. [Copadatetime Ilişkisel işleçleri](#coledatetime_relational_operators) .

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#12](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>COleDateTime:: operator + =,-=

`ColeDateTime` Bu`COleDateTime` nesneden bir değer ekleyin ve çıkarın.

```
COleDateTime& operator+=(COleDateTimeSpan dateSpan) throw();
COleDateTime& operator-=(COleDateTimeSpan dateSpan) throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu `COleDateTimeSpan` `COleDateTime`değerden ve öğesinden bir değer eklemenizi ve çıkartabilir. İşlenenden biri null ise, sonuçta elde edilen `COleDateTime` değerin durumu null olur.

Elde edilen `COleDateTime` değer kabul edilebilir değerler sınırlarının dışında kalırsa, bu `COleDateTime` değerin durumu geçersiz olarak ayarlanır.

İşlenenden biri geçersiz ve diğeri null değilse, sonuçta elde edilen `COleDateTime` değerin durumu geçersizdir.

Geçerli, geçersiz ve null durum değerleri hakkında daha fazla bilgi için bkz. [m_status](#m_status) üye değişkeni.

Ve **+=** **işleçleri-=,nesnenullolarak** ayarlandıysaonayalacak.`COleDateTime` Bir örnek için bkz. [Copadatetime Ilişkisel işleçleri](#coledatetime_relational_operators) .

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="operator_date"></a>COleDateTime:: operator TARIHI

`ColeDateTime` Bir değeri öğesine dönüştürür `DATE`.

```
operator DATE() const throw();
```

### <a name="remarks"></a>Açıklamalar

Bu işleç, değeri `DATE` bu `COleDateTime` nesneden kopyalanmış olan bir nesne döndürür. `DATE` Nesnesinin uygulanması hakkında daha fazla bilgi için bkz. Tarih ve saat makalesi [: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

İşleci, `COleDateTime` nesne null olarak ayarlandıysa onay alacak. `DATE` Bir örnek için bkz. [Copadatetime Ilişkisel işleçleri](#coledatetime_relational_operators) .

##  <a name="parsedatetime"></a>Cotadatetime::P arseDateTime

Bir tarih/saat değerini okumak için bir dize ayrıştırır.

```
bool ParseDateTime(
    LPCTSTR lpszDate,
    DWORD dwFlags = 0,
    LCID lcid = LANG_USER_DEFAULT) throw();
```

### <a name="parameters"></a>Parametreler

*lpszDate*<br/>
Ayrıştırılacak null ile sonlandırılmış dizeye yönelik bir işaretçi. Ayrıntılar için bkz. açıklamalar.

*dwFlags*<br/>
Yerel ayar ayarları ve ayrıştırma için bayrakları gösterir. Aşağıdaki bayraklardan biri veya daha fazlası:

- LOCALE_NOUSEROVERRIDE özel Kullanıcı ayarları yerine sistem varsayılan yerel ayar ayarlarını kullanın.

- VAR_TIMEVALUEONLY, ayrıştırma sırasında tarih bölümünü yoksayar.

- VAR_DATEVALUEONLY, ayrıştırma sırasında zaman bölümünü yoksayar.

*lcid*<br/>
Dönüştürme için kullanılacak yerel ayar KIMLIĞINI gösterir.

### <a name="return-value"></a>Dönüş Değeri

Dize bir tarih/saat değerine başarıyla dönüştürülürse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Dize bir tarih/saat değerine başarıyla dönüştürülürse, bu nesnenin değeri bu `COleDateTime` değere ve durumu geçerli olarak ayarlanır.

> [!NOTE]
>  Yıl değerlerinin ikisi de dahil 100 ile 9999 arasında olmalıdır.

*LpszDate* parametresi çeşitli biçimlerde olabilir. Örneğin, aşağıdaki dizeler kabul edilebilir tarih/saat biçimlerini içerir:

`"25 January 1996"`

`"8:30:00"`

`"20:30:00"`

`"January 25, 1996 8:30:00"`

`"8:30:00 Jan. 25, 1996"`

`"1/25/1996 8:30:00"  // always specify the full year, even in a 'short date' format`

Yerel ayar KIMLIĞI, dize biçiminin bir tarih/saat değerine dönüştürme için kabul edilebilir olup olmadığını da etkiler.

VAR_DATEVALUEONLY durumunda, zaman değeri saat 0 veya gece yarısı olarak ayarlanır. VAR_TIMEVALUEONLY durumunda Date değeri 0 tarihi, yani 30 Aralık 1899 olarak ayarlanır.

Dize bir tarih/saat değerine dönüştürülemiyorsa veya sayısal bir taşma varsa, bu `COleDateTime` nesnenin durumu geçersiz olur.

Değerler için `COleDateTime` sınır ve uygulama hakkında daha fazla bilgi için bkz. Tarih ve [saat makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

##  <a name="setdate"></a>Cotadatetime:: SetDate

Bu `COleDateTime` nesnenin tarihini ayarlar.

```
int SetDate(
    int nYear,
    int nMonth,
    int nDay) throw();
```

### <a name="parameters"></a>Parametreler

*nYear*, *nmonth*, *nday*<br/>
Bu `COleDateTime` nesneye kopyalanacak Tarih bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlandıysa sıfır; Aksi takdirde, 1. Bu dönüş değeri, `DateTimeStatus` numaralandırılmış türü temel alır. Daha fazla bilgi için bkz. [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Tarih, belirtilen değerlere ayarlanır. Saat 0, gece yarısı olarak ayarlanır.

Parametre değerlerinin sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*Nyıl*|100 - 9999|
|*Nay*|1 - 12|
|*nHatalı*|0 - 31|

Ayın günü taşarsa, sonraki ayın doğru gününe dönüştürülür ve ay ve/veya yıl uygun şekilde artırılır. Sıfır gün değeri, önceki ayın son gününü gösterir. Davranış, ile `SystemTimeToVariantTime`aynıdır.

Parametreler tarafından belirtilen tarih değeri geçerli değilse, bu nesnenin durumu olarak `COleDateTime::invalid`ayarlanır. `DATE` Değerin geçerliliğini denetlemek için [GetStatus](#getstatus) kullanmanız gerekir ve [m_dt](#m_dt) değerinin değiştirilmemiş olarak kalacağını varsaymamalıdır.

Tarih değerlerine ilişkin bazı örnekler aşağıda verilmiştir:

|*Nyıl*|*Nay*|*nHatalı*|Değer|
|-------------|--------------|------------|-----------|
|2000|2|29|29 Şubat 2000|
|1776|7|4|4 Temmuz 1776|
|1925|4|35|1925 Nisan 35 (Geçersiz tarih)|
|10000|1\.|1\.|1 Ocak 10000 (Geçersiz tarih)|

Hem tarih hem de saati ayarlamak için bkz. [copadatetime:: SetDateTime](#setdatetime).

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#11](../../atl-mfc-shared/codesnippet/cpp/coledatetime-class_14.cpp)]

##  <a name="setdatetime"></a>Cotadatetime:: SetDateTime

Bu `COleDateTime` nesnenin tarihini ve saatini ayarlar.

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

*nYear*, *nmonth*, *nday*, *nhour*, *nMin*, *NSEC*<br/>
Bu `COleDateTime` nesneye kopyalanacak tarih ve saat bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlandıysa sıfır; Aksi takdirde, 1. Bu dönüş değeri, `DateTimeStatus` numaralandırılmış türü temel alır. Daha fazla bilgi için bkz. [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Parametre değerlerinin sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*Nyıl*|100 - 9999|
|*Nay*|1 - 12|
|*nHatalı*|0 - 31|
|*Ngünün saati*|0 - 23|
|*Ngünde en az*|0 - 59|
|*nSec*|0 - 59|

Ayın günü taşarsa, sonraki ayın doğru gününe dönüştürülür ve ay ve/veya yıl uygun şekilde artırılır. Sıfır gün değeri, önceki ayın son gününü gösterir. Davranış, [SystemTimeToVariantTime](/windows/win32/api/oleauto/nf-oleauto-systemtimetovarianttime)ile aynıdır.

Parametreler tarafından belirtilen tarih veya saat değeri geçerli değilse, bu nesnenin durumu geçersiz olarak ayarlanır ve bu nesnenin değeri değiştirilmez.

Zaman değerlerinin bazı örnekleri aşağıda verilmiştir:

|*Ngünün saati*|*Ngünde en az*|*nSec*|Değer|
|-------------|------------|------------|-----------|
|1\.|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Tarih değerlerine ilişkin bazı örnekler aşağıda verilmiştir:

|*Nyıl*|*Nay*|*nHatalı*|Değer|
|-------------|--------------|------------|-----------|
|1995|4|15|15 Nisan 1995|
|1789|7|14|17 Temmuz 1789|
|1925|2|30|Geçersiz|
|10000|1\.|1\.|Geçersiz|

Yalnızca tarihi ayarlamak için bkz. [Copadatetime:: SetDate](#setdate). Yalnızca saati ayarlamak için bkz. [Copadatetime:: SetTime](#settime).

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

[GetStatus](#getstatus)örneğine bakın.

##  <a name="setstatus"></a>Cotadatetime:: SetStatus

Bu `COleDateTime` nesnenin durumunu ayarlar.

```
void SetStatus(DateTimeStatus status) throw();
```

### <a name="parameters"></a>Parametreler

*status*<br/>
Bu `COleDateTime` nesnenin yeni durum değeri.

### <a name="remarks"></a>Açıklamalar

*Durum* parametresi değeri, `DateTimeStatus` `COleDateTime` sınıfı içinde tanımlanan, numaralandırılmış tür tarafından tanımlanır. Ayrıntılar için bkz. [Copadatetime:: GetStatus](#getstatus) .

> [!CAUTION]
>  Bu işlev, gelişmiş programlama durumları içindir. Bu işlev, bu nesnedeki verileri değiştirmez. En sık, durumu **null** veya **geçersiz**olarak ayarlamak için kullanılır. Atama işleci ([operator =](#operator_eq)) ve [SetDateTime](#setdatetime) , kaynak değer (ler) i temel alarak nesnenin durumunu ayarlar.

### <a name="example"></a>Örnek

[GetStatus](#getstatus)örneğine bakın.

##  <a name="settime"></a>Cotadatetime:: SetTime

Bu `COleDateTime` nesnenin saatini ayarlar.

```
int SetTime(
    int nHour,
    int nMin,
    int nSec) throw();
```

### <a name="parameters"></a>Parametreler

*Nhour*, *nMin*, *NSEC*<br/>
Bu `COleDateTime` nesneye kopyalanacak saat bileşenlerini belirtin.

### <a name="return-value"></a>Dönüş Değeri

Bu `COleDateTime` nesnenin değeri başarıyla ayarlandıysa sıfır; Aksi takdirde, 1. Bu dönüş değeri, `DateTimeStatus` numaralandırılmış türü temel alır. Daha fazla bilgi için bkz. [SetStatus](#setstatus) üye işlevi.

### <a name="remarks"></a>Açıklamalar

Zaman, belirtilen değerlere ayarlanır. Tarih 0 ' a, yani 30 Aralık 1899 ' e ayarlanır.

Parametre değerlerinin sınırları için aşağıdaki tabloya bakın:

|Parametre|Sınırları|
|---------------|------------|
|*Ngünün saati*|0 - 23|
|*Ngünde en az*|0 - 59|
|*nSec*|0 - 59|

Parametreler tarafından belirtilen zaman değeri geçerli değilse, bu nesnenin durumu geçersiz olarak ayarlanır ve bu nesnenin değeri değiştirilmez.

Zaman değerlerinin bazı örnekleri aşağıda verilmiştir:

|*Ngünün saati*|*Ngünde en az*|*nSec*|Değer|
|-------------|------------|------------|-----------|
|1\.|3|3|01:03:03|
|23|45|0|23:45:00|
|25|30|0|Geçersiz|
|9|60|0|Geçersiz|

Hem tarih hem de saati ayarlamak için bkz. [copadatetime:: SetDateTime](#setdatetime).

Bu `COleDateTime` nesnenin değerini sorgulayan üye işlevleri hakkında daha fazla bilgi için, aşağıdaki üye işlevlere bakın:

- [GetDay](#getday)

- [GetMonth](#getmonth)

- [GetYear](#getyear)

- [GetHour](#gethour)

- [GetMinute](#getminute)

- [GetSecond](#getsecond)

- [GetDayOfWeek](#getdayofweek)

- [GetDayOfYear](#getdayofyear)

`COleDateTime` Değerlerin sınırları hakkında daha fazla bilgi için bkz. Tarih ve saat [makalesi: Otomasyon desteği](../../atl-mfc-shared/date-and-time-automation-support.md).

### <a name="example"></a>Örnek

Bkz. [setDate](#setdate)örneği.

## <a name="see-also"></a>Ayrıca bkz.

[COleVariant Sınıfı](../../mfc/reference/colevariant-class.md)<br/>
[CTime Sınıfı](../../atl-mfc-shared/reference/ctime-class.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
