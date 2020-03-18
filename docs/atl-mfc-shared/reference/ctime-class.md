---
title: CTime sınıfı
ms.date: 10/18/2018
f1_keywords:
- ATLTIME/ATL::CTime
- ATLTIME/ATL::CTime::CTime
- ATLTIME/ATL::CTime::Format
- ATLTIME/ATL::CTime::FormatGmt
- ATLTIME/ATL::CTime::GetAsDBTIMESTAMP
- ATLTIME/ATL::CTime::GetAsSystemTime
- ATLTIME/ATL::CTime::GetCurrentTime
- ATLTIME/ATL::CTime::GetDay
- ATLTIME/ATL::CTime::GetDayOfWeek
- ATLTIME/ATL::CTime::GetGmtTm
- ATLTIME/ATL::CTime::GetHour
- ATLTIME/ATL::CTime::GetLocalTm
- ATLTIME/ATL::CTime::GetMinute
- ATLTIME/ATL::CTime::GetMonth
- ATLTIME/ATL::CTime::GetSecond
- ATLTIME/ATL::CTime::GetTime
- ATLTIME/ATL::CTime::GetYear
- ATLTIME/ATL::CTime::Serialize64
helpviewer_keywords:
- CTime class
- shared classes, CTime
ms.assetid: 0a299544-485b-48dc-9d3c-fdc30f57d612
ms.openlocfilehash: a1d62cca42e3110974b07dae143bafcf807fed7e
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79440491"
---
# <a name="ctime-class"></a>CTime sınıfı

Mutlak bir saat ve tarihi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTime:: CTime](#ctime)|Çeşitli yollarla `CTime` nesneleri oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTime:: biçim](#format)|Bir `CTime` nesnesini, yerel saat dilimine bağlı olarak, biçimli bir dizeye dönüştürür.|
|[CTime:: FormatGmt](#formatgmt)|Bir `CTime` nesnesini UTC 'ye göre biçimli bir dizeye dönüştürür.|
|[CTime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|`CTime` nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir DBTIMESTAMP yapısına dönüştürür.|
|[CTime:: GetAsSystemTime](#getassystemtime)|`CTime` nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürür.|
|[CTime:: GetCurrentTime](#getcurrenttime)|Geçerli saati (statik üye işlevi) temsil eden bir `CTime` nesnesi oluşturur.|
|[CTime:: GetDay](#getday)|`CTime` nesnesi tarafından temsil eden günü döndürür.|
|[CTime:: GetDayOfWeek](#getdayofweek)|`CTime` nesnesi tarafından temsil edilen haftanın gününü döndürür.|
|[CTime:: Getgmttd](#getgmttm)|`CTime` nesnesini, UTC 'ye göre bileşenlere ayırır.|
|[CTime:: GetHour](#gethour)|`CTime` nesnesi tarafından temsil edilen saati döndürür.|
|[CTime:: GetLocalTm](#getlocaltm)|Bir `CTime` nesnesini, yerel saat dilimine bağlı olarak bileşenlere ayırır.|
|[CTime:: GetMinute](#getminute)|`CTime` nesnesinin temsil ettiği dakikayı döndürür.|
|[CTime:: GetMonth](#getmonth)|`CTime` nesnesi tarafından temsil edilen ayı döndürür.|
|[CTime:: GetSecond](#getsecond)|`CTime` nesnesi tarafından temsil edilen saniyeyi döndürür.|
|[CTime:: GetTime](#gettime)|Verilen `CTime` nesnesi için **__time64_t** bir değer döndürür.|
|[CTime:: GetYear](#getyear)|`CTime` nesnesinin temsil ettiği yılı döndürür.|
|[CTime:: Serialize64](#serialize64)|Verileri bir arşivye veya bir arşive seri hale getirir.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç +-](#operator_add_-)|Bu işleçler `CTimeSpan` ve `CTime` nesneleri ekler ve çıkarır.|
|[işleç + =,-=](#operator_add_eq_-_eq)|Bu işleçler, bu `CTime` nesnesine ve öğesinden bir `CTimeSpan` nesnesi ekler ve çıkarır.|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç = =, <, vb.](#ctime_comparison_operators)|Karşılaştırma işleçleri.|

## <a name="remarks"></a>Açıklamalar

`CTime` temel bir sınıfa sahip değil.

`CTime` değerler Eşgüdümlü Evrensel saate (UTC) göre belirlenir (Greenwich saati, GMT). Saat diliminin nasıl belirlendiği hakkında bilgi için bkz. [saat yönetimi](../../c-runtime-library/time-management.md) .

Bir `CTime` nesnesi oluşturduğunuzda, standart saatin geçerli olduğunu belirtmek için, `nDST` parametresini 0 olarak ayarlayın veya gün ışığından yararlanma saatinin etkin olduğunu belirtmek için 0 ' dan büyük bir değere veya standart saat veya yaz saati oluşturma süresinin etkin olup olmadığına göre C çalışma zamanı kitaplık kodu hesaplama için sıfırdan küçük bir değere ayarlayın. `tm_isdst` gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 'den dönüş değeri tahmin edilemez. `timeptr`, önceki bir [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)çağrısıyla döndürülen bir TM yapısına işaret ediyorsa, `tm_isdst` alanı doğru değeri içerir.

Eşlik eden bir sınıf olan [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığını temsil eder.

`CTime` ve `CTimeSpan` sınıfları türetme için tasarlanmamıştır. Sanal işlev olmadığından `CTime` ve `CTimeSpan` nesnelerinin boyutu tam olarak 8 bayttır. Çoğu üye işlevleri satır içidir.

> [!NOTE]
>  Üst tarih sınırı 12/31/3000 ' dir. Alt sınır 1/1/1970 12:00:00 GMT 'dir.

`CTime`kullanma hakkında daha fazla bilgi için bkz. çalışma zamanı kitaplık başvurusunda makalelerin [Tarih ve saat](../../atl-mfc-shared/date-and-time.md)ve [saat yönetimi](../../c-runtime-library/time-management.md) .

> [!NOTE]
>  `CTime` yapısı MFC 7,1 ' den MFC 8,0 ' ye değişti. MFC 8,0 veya sonraki bir sürümü altında **< < işlecini** kullanarak bir `CTime` yapısını seri hale getirmek istiyorsanız, sonuçta elde edilen dosya daha eski MFC sürümlerinde okunabilir olmayacaktır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

##  <a name="ctime_comparison_operators"></a>CTime karşılaştırma Işleçleri

Karşılaştırma işleçleri.

```
bool operator==(CTime time) const throw();
bool operator!=(CTime time) const throw();
bool operator<(CTime time) const throw();
bool operator>(CTime time) const throw();
bool operator<=(CTime time) const throw();
bool operator>=(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*ışınızda*<br/>
Karşılaştırılacak `CTime` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki mutlak kez karşılaştırıp koşulun true olması durumunda TRUE değerini döndürür; Aksi halde yanlış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>CTime:: CTime

Belirtilen zaman ile başlatılan yeni bir `CTime` nesnesi oluşturur.

```
CTime() throw();
CTime(__time64_t time) throw();
CTime(int nYear, int nMonth, int nDay,
      int nHour, int nMin, int nSec, int nDST = -1);
CTime(WORD wDosDate, WORD wDosTime, int nDST = -1);
CTime(const SYSTEMTIME& st, int nDST = - 1) throw();
CTime(const FILETIME& ft, int nDST = - 1);
CTime(const DBTIMESTAMP& dbts, int nDST = -1) throw();
```

### <a name="parameters"></a>Parametreler

*zaman dilimlerini*<br/>
Zaten var olan bir `CTime` nesnesini gösterir.

*ışınızda*<br/>
1 Ocak 1970 UTC 'den sonraki saniye sayısı olan `__time64_t` saat değeri. Bu, yerel zaman olarak ayarlanacağını unutmayın. Örneğin, New York 'taysa ve 0 parametresini geçirerek bir `CTime` nesnesi oluşturuyorsanız, [CTime:: GetMonth](#getmonth) , 12 döndürür.

*nYear*, *nmonth*, *nday*, *nhour*, *nMin*, *NSEC*<br/>
Yeni `CTime` nesnesine kopyalanacak tarih ve saat değerlerini gösterir.

*nDST*<br/>
Gün ışığından yararlanma saatinin etkin olup olmadığını gösterir. Üç değerden birine sahip olabilir:

- *nDST* , 0Standart zaman olarak ayarlanmıştır.

- *nDST* , 0 ' dan büyük bir değere ayarlandığında gün ışığından yararlanma süresinden fazla olur.

- *nDST* , 0 ' dan küçük bir değere ayarlanır. Standart saat veya yaz tasarrufu süresinin etkin olup olmadığını otomatik olarak hesaplar.

*Wdosdate*, *wdostime*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesnesine kopyaladığınız MS-DOS tarih ve saat değerleri.

*oluşan*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesnesine kopyaladığınız bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı.

*meniz*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesnesine kopyaladığınız bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı.

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Her Oluşturucu aşağıda açıklanmıştır:

- `CTime();` başlatılmamış bir `CTime` nesnesi oluşturur. Bu Oluşturucu, `CTime` nesne dizilerini tanımlamanızı sağlar. Kullanmadan önce bu tür dizileri geçerli saatlere başlatmalısınız.

- `CTime( const CTime& );` başka bir `CTime` değerden bir `CTime` nesnesi oluşturur.

- `CTime( __time64_t );` bir **__time64_t** türünden `CTime` nesnesi oluşturur. Bu Oluşturucu bir UTC saati bekler ve sonucu depolamadan önce sonucu yerel saate dönüştürür.

- `CTime( int, int, ...);`, yerel saat bileşenlerinden her bileşeni aşağıdaki aralıklar için kısıtlanmış bir `CTime` nesnesi oluşturur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*Nyıl*|1970-3000|
   |*Nay*|1-12|
   |*nHatalı*|1-31|
   |*Ngünün saati*|0-23|
   |*Ngünde en az*|0-59|
   |*nSec*|0-59|

   Bu Oluşturucu UTC 'ye uygun dönüştürme yapar. Microsoft Foundation Class Kitaplığı hata ayıklama sürümü, bir veya daha fazla zaman bileşeni Aralık dışında olduğunda onay onaylar. Çağrılmadan önce bağımsız değişkenleri doğrulamanız gerekir. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( WORD, WORD );`, belirtilen MS-DOS tarih ve saat değerlerinden bir `CTime` nesnesi oluşturur. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const SYSTEMTIME& );` `SYSTEMTIME` yapısından bir `CTime` nesnesi oluşturur. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const FILETIME& );` `FILETIME` yapısından bir `CTime` nesnesi oluşturur. Büyük olasılıkla `CTime FILETIME` başlatmayı doğrudan kullanamayacaksınız. Bir dosyayı işlemek için `CFile` nesnesi kullanıyorsanız, `CFile::GetStatus`, `FILETIME` yapısıyla başlatılan `CTime` nesnesi aracılığıyla sizin için dosya zaman damgasını alır. Bu Oluşturucu UTC 'yi temel alan bir zaman varsayar ve sonucu depolamadan önce değeri otomatik olarak yerel saate dönüştürür.

   > [!NOTE]
   > `DBTIMESTAMP` parametresi kullanan Oluşturucu yalnızca OLEDB. h dahil edildiğinde kullanılabilir.

Daha fazla bilgi için Windows SDK [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına bakın. Ayrıca Windows SDK [MS-DOS tarih ve saat](/windows/win32/SysInfo/ms-dos-date-and-time) girdisine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>CTime:: biçim

Tarih-saat değerinin biçimli bir gösterimini oluşturmak için bu üye işlevini çağırın.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
`printf` biçimlendirme dizesine benzer bir biçimlendirme dizesi. Bir yüzde (`%`) işaretinden önce gelen biçimlendirme kodları ilgili `CTime` bileşeniyle değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. Biçimlendirme kodlarının listesi için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilen saati içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Bu `CTime` nesnesinin durumu null ise, dönüş değeri boş bir dizedir.

Bu yöntem, biçimlendirme tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000, Evrensel Eşgüdümlü saat (UTC) arasında değilse bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>CTime:: FormatGmt

Bu `CTime` nesnesine karşılık gelen bir biçimli dize oluşturur.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
`printf` biçimlendirme dizesine benzer bir biçimlendirme dizesi belirtir. Ayrıntılar için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilen saati içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Zaman değeri dönüştürülmez ve bu nedenle UTC 'yi yansıtır.

Bu yöntem, biçimlendirme tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000, Evrensel Eşgüdümlü saat (UTC) arasında değilse bir özel durum oluşturur.

### <a name="example"></a>Örnek

[CTime:: Format](#format)örneğine bakın.

##  <a name="getasdbtimestamp"></a>CTime:: GetAsDBTIMESTAMP

`CTime` nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir DBTIMESTAMP yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Elde edilen süreyi başvurulan *dbts* yapısına depolar. Bu işlev tarafından başlatılan `DBTIMESTAMP` veri yapısının, `fraction` üyesi sıfır olarak ayarlanmış olacak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>CTime:: GetAsSystemTime

`CTime` nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
`CTime` nesnesinin dönüştürülmüş tarih/saat değerini tutan bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime`, elde edilen süreyi başvurulan *timeDest* yapısına depolar. Bu işlev tarafından başlatılan `SYSTEMTIME` veri yapısının, `wMilliseconds` üyesi sıfır olarak ayarlanmış olacak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>CTime:: GetCurrentTime

Geçerli saati temsil eden bir `CTime` nesnesi döndürür.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Açıklamalar

Geçerli sistem tarihini ve saati Eşgüdümlü Evrensel Saat (UTC) olarak döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>CTime:: GetDay

`CTime` nesnesi tarafından temsil eden günü döndürür.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 31 aralığında yerel saate göre ayın gününü döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili ve statik olarak ayrılmış bir arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>CTime:: GetDayOfWeek

`CTime` nesnesi tarafından temsil edilen haftanın gününü döndürür.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Haftanın gününü yerel saate göre döndürür; 1 = Pazar, 2 = Pazartesi, 7 = Cumartesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>CTime:: Getgmttd

Bu `CTime` nesnesinde bulunan süreyi ayrışanı içeren bir **struct tm** alır.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İçerme dosyası SıRASıNDA tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Olsun. Yapı düzeni için bkz. [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetGmtTm` UTC döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL tanımlamayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>CTime:: GetHour

`CTime` nesnesi tarafından temsil edilen saati döndürür.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 0 ile 23 aralığındaki saati döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>CTime:: GetLocalTm

Bu `CTime` nesnesinde bulunan süreyi ayrışanı içeren bir **struct tm** alır.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İçerme dosyası SıRASıNDA tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Olsun. Yapı düzeni için bkz. [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetLocalTm` yerel saati döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL tanımlamayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>CTime:: GetMinute

`CTime` nesnesinin temsil ettiği dakikayı döndürür.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre dakikayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="getmonth"></a>CTime:: GetMonth

`CTime` nesnesi tarafından temsil edilen ayı döndürür.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 1 ile 12 arasında (1 = Ocak) ayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="getsecond"></a>CTime:: GetSecond

`CTime` nesnesi tarafından temsil edilen saniyeyi döndürür.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre saniyeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="gettime"></a>CTime:: GetTime

Verilen `CTime` nesnesi için **__time64_t** bir değer döndürür.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`GetTime` geçerli `CTime` nesnesi ve 1 Ocak 1970 arasındaki saniye sayısını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>CTime:: GetYear

`CTime` nesnesinin temsil ettiği yılı döndürür.

```
int GetYear();
```

### <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970 aralığında, 18 Ocak 2038 (dahil) aralığında yerel saate göre yılı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili bir statik olarak ayrılan arabellek kullanan `GetLocalTm`çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="operator_eq"></a>CTime:: operator =

Atama işleci.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parametreler

*ışınızda*<br/>
Yeni tarih/saat değeri.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleci, kaynak saatini bu `CTime` nesnesine kopyalar. `CTime` nesnesindeki iç zaman depolama alanı saat diliminden bağımsızdır. Atama sırasında saat dilimi dönüştürmesi gerekli değildir.

##  <a name="operator_add_-"></a>CTime:: operator +,-

Bu işleçler `CTimeSpan` ve `CTime` nesneleri ekler ve çıkarır.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*timeSpan*<br/>
Eklenecek veya çıkarılacak nesne `CTimeSpan`.

*ışınızda*<br/>
Çıkarılacak `CTime` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İşlemin sonucunu temsil eden bir `CTime` veya `CTimeSpan` nesnesi.

### <a name="remarks"></a>Açıklamalar

`CTime` nesneler mutlak süreyi temsil eder, `CTimeSpan` nesneler göreli süreyi temsil eder. İlk iki operatör, `CTime` nesneleri `CTimeSpan` nesneleri eklemenize ve bunlara çıkareklemenize olanak tanır. Üçüncü işleç, bir `CTime` nesnesini diğerinden çıkarırın bir `CTimeSpan` nesnesi elde etmenizi sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>CTime:: operator + =,-=

Bu işleçler, bu `CTime` nesnesine ve öğesinden bir `CTimeSpan` nesnesi ekler ve çıkarır.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Eklenecek veya çıkarılacak nesne `CTimeSpan`.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesnesi.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu `CTime` nesnesine ve öğesinden bir `CTimeSpan` nesnesi eklemenize ve çıkareklemenize olanak tanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>CTime:: Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFC projelerinde kullanılabilir.

Üye değişkeniyle ilişkili verileri bir arşivden veya bir arşive serileştirir.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Güncelleştirmek istediğiniz `CArchive` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesnesi.

## <a name="see-also"></a>Ayrıca bkz.

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
