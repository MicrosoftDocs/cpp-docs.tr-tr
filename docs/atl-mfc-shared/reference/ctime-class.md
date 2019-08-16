---
title: CTime sınıfı
ms.date: 10/18/2018
f1_keywords:
- CTime
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
ms.openlocfilehash: daf2a0d884a6b7a74b5edde2ed7db3b6aeea368d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491570"
---
# <a name="ctime-class"></a>CTime sınıfı

Mutlak bir saat ve tarihi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTime:: CTime](#ctime)|Nesneleri `CTime` çeşitli şekillerde oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTime:: biçim](#format)|Bir `CTime` nesneyi yerel saat dilimine göre biçimli bir dizeye dönüştürür.|
|[CTime:: FormatGmt](#formatgmt)|Bir `CTime` nesneyi UTC 'ye göre biçimli bir dizeye dönüştürür.|
|[CTime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|`CTime` Nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir DBTimeStamp yapısına dönüştürür.|
|[CTime:: GetAsSystemTime](#getassystemtime)|`CTime` Nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürür.|
|[CTime:: GetCurrentTime](#getcurrenttime)|Geçerli saati `CTime` (statik üye işlevi) temsil eden bir nesne oluşturur.|
|[CTime:: GetDay](#getday)|`CTime` Nesnenin gösterdiği günü döndürür.|
|[CTime:: GetDayOfWeek](#getdayofweek)|`CTime` Nesnenin gösterdiği haftanın gününü döndürür.|
|[CTime:: Getgmttd](#getgmttm)|UTC 'ye göre `CTime` bir nesneyi bileşenlere ayırır.|
|[CTime:: GetHour](#gethour)|`CTime` Nesnenin gösterdiği saati döndürür.|
|[CTime:: GetLocalTm](#getlocaltm)|Yerel saat dilimine `CTime` bağlı olarak bir nesneyi bileşenlere ayırır.|
|[CTime:: GetMinute](#getminute)|`CTime` Nesnenin temsil ettiği dakikayı döndürür.|
|[CTime:: GetMonth](#getmonth)|`CTime` Nesnenin temsil ettiği ayı döndürür.|
|[CTime:: GetSecond](#getsecond)|`CTime` Nesne tarafından temsil edilen saniyeyi döndürür.|
|[CTime:: GetTime](#gettime)|Verilen`CTime` nesne için bir **__time64_t** değeri döndürür.|
|[CTime:: GetYear](#getyear)|`CTime` Nesnenin temsil ettiği yılı döndürür.|
|[CTime:: Serialize64](#serialize64)|Verileri bir arşivye veya bir arşive seri hale getirir.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç +-](#operator_add_-)|Bu işleçler ve `CTime` nesneler ekler `CTimeSpan` ve çıkarır.|
|[işleç + =,-=](#operator_add_eq_-_eq)|Bu işleçler, nesnesine ve `CTimeSpan` `CTime` nesnesinden bir nesne ekler ve çıkarır.|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç = =, <, vb.](#ctime_comparison_operators)|Karşılaştırma işleçleri.|

## <a name="remarks"></a>Açıklamalar

`CTime`taban sınıfına sahip değildir.

`CTime`değerler Eşgüdümlü Evrensel saate (UTC) göre belirlenir (Greenwich saati, GMT). Saat diliminin nasıl belirlendiği hakkında bilgi için bkz. [saat yönetimi](../../c-runtime-library/time-management.md) .

Bir `CTime` nesne oluşturduğunuzda, standart saatin geçerli olduğunu `nDST` veya 0 ' dan büyük bir değere sahip olması gerektiğini göstermek için parametreyi 0 olarak ayarlayın ve C çalışma zamanı kitaplık kodu bilgi 'in bir değeri sıfırdan küçük bir değere Standart saat veya yaz saati kaydetme saatinin etkin olup olmadığı. `tm_isdst`gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 'den dönüş değeri tahmin edilemez. Önceki `timeptr` bir [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)çağrısıyla döndürülen bir TM yapısına işaret ediyorsa, `tm_isdst` alan doğru değeri içerir.

Eşlik eden bir sınıf olan [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığını temsil eder.

`CTime` Ve`CTimeSpan` sınıfları türetme için tasarlanmamıştır. Sanal işlev olmadığından, `CTime` ve `CTimeSpan` nesnelerinin boyutu tam olarak 8 bayttır. Çoğu üye işlevleri satır içidir.

> [!NOTE]
>  Üst tarih sınırı 12/31/3000 ' dir. Alt sınır 1/1/1970 12:00:00 GMT 'dir.

Kullanma `CTime`hakkında daha fazla bilgi için bkz. çalışma zamanı kitaplık başvurusunda makalelerin [Tarih ve saat](../../atl-mfc-shared/date-and-time.md)ve [saat yönetimi](../../c-runtime-library/time-management.md) .

> [!NOTE]
>  `CTime` Yapı MFC 7,1 ' den MFC 8,0 ' ye değişti. MFC 8,0 veya sonraki `CTime` bir sürümü altındaki **işleci < <** kullanarak bir yapıyı seri hale getirmek istiyorsanız, sonuçta elde edilen dosya daha eski MFC sürümlerinde okunabilir olmayacaktır.

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

*saat*<br/>
Karşılaştırılacak `CTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki mutlak kez karşılaştırıp koşulun true olması durumunda TRUE değerini döndürür; Aksi halde yanlış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>CTime:: CTime

Belirtilen saat ile `CTime` başlatılan yeni bir nesne oluşturur.

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
Zaten var `CTime` olan bir nesneyi gösterir.

*saat*<br/>
1 Ocak 1970 utc 'den sonraki saniye sayısı olan saatdeğeri.`__time64_t` Bu, yerel zaman olarak ayarlanacağını unutmayın. Örneğin, New York 'taysa ve 0 parametresini geçirerek bir `CTime` nesne oluşturuyorsanız, [CTime:: GetMonth](#getmonth) , 12 döndürür.

*nYear*, *nmonth*, *nday*, *nhour*, *nMin*, *NSEC*<br/>
Yeni `CTime` nesneye kopyalanacak tarih ve saat değerlerini gösterir.

*nDST*<br/>
Gün ışığından yararlanma saatinin etkin olup olmadığını gösterir. Üç değerden birine sahip olabilir:

- *nDST* , 0Standart zaman olarak ayarlanmıştır.

- *nDST* , 0 ' dan büyük bir değere ayarlandığında gün ışığından yararlanma süresinden fazla olur.

- *nDST* , 0 ' dan küçük bir değere ayarlanır. Standart saat veya yaz tasarrufu süresinin etkin olup olmadığını otomatik olarak hesaplar.

*Wdosdate*, *wdostime*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesneye kopyalandığı MS-DOS tarih ve saat değerleri.

*oluşan*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesneye kopyaladığınız bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı.

*meniz*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni `CTime` nesneye kopyaladığınız bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı.

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Her Oluşturucu aşağıda açıklanmıştır:

- `CTime();`Başlatılmamış `CTime` bir nesne oluşturur. Bu Oluşturucu, nesne dizilerini tanımlamanızı `CTime` sağlar. Kullanmadan önce bu tür dizileri geçerli saatlere başlatmalısınız.

- `CTime( const CTime& );``CTime` Başka`CTime` bir değerden bir nesne oluşturur.

- `CTime( __time64_t );`Bir `CTime` **__time64_t** türünden bir nesne oluşturur. Bu Oluşturucu bir UTC saati bekler ve sonucu depolamadan önce sonucu yerel saate dönüştürür.

- `CTime( int, int, ...);`Her bileşeni `CTime` aşağıdaki aralıklar için kısıtlanmış yerel saat bileşenlerinden bir nesne oluşturur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*Nyıl*|1970-3000|
   |*Nay*|1-12|
   |*nHatalı*|1-31|
   |*Ngünün saati*|0-23|
   |*Ngünde en az*|0-59|
   |*nSec*|0-59|

   Bu Oluşturucu UTC 'ye uygun dönüştürme yapar. Microsoft Foundation Class Kitaplığı hata ayıklama sürümü, bir veya daha fazla zaman bileşeni Aralık dışında olduğunda onay onaylar. Çağrılmadan önce bağımsız değişkenleri doğrulamanız gerekir. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( WORD, WORD );`Belirtilen MS-DOS `CTime` tarih ve saat değerlerinden bir nesne oluşturur. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const SYSTEMTIME& );``SYSTEMTIME` Yapıdan bir `CTime` nesne oluşturur. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const FILETIME& );``FILETIME` Yapıdan bir `CTime` nesne oluşturur. En büyük olasılıkla başlatmayı doğrudan kullanamayacaksınız `CTime FILETIME` . Bir dosyayı işlemek için `CFile` bir nesnesi kullanırsanız, `CFile::GetStatus` bir `FILETIME` yapıyla başlatılan bir `CTime` nesne aracılığıyla sizin için dosya zaman damgasını alır. Bu Oluşturucu UTC 'yi temel alan bir zaman varsayar ve sonucu depolamadan önce değeri otomatik olarak yerel saate dönüştürür.

   > [!NOTE]
   > Parametresi kullanılarak `DBTIMESTAMP` Oluşturucu yalnızca OLEDB. h dahil edildiğinde kullanılabilir.

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
Biçimlendirme dizesine benzer `printf` bir biçimlendirme dizesi. Bir yüzde (`%`) işaretinden önce gelen biçimlendirme kodları ilgili `CTime` bileşenle değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. Biçimlendirme kodlarının listesi için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilen saati içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Bu `CTime` nesnenin durumu null ise, dönüş değeri boş bir dizedir.

Bu yöntem, biçimlendirme tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000, Evrensel Eşgüdümlü saat (UTC) arasında değilse bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>CTime:: FormatGmt

Bu `CTime` nesneye karşılık gelen biçimli bir dize oluşturur.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
`printf` Biçimlendirme dizesine benzer bir biçimlendirme dizesi belirtir. Ayrıntılar için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

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

`CTime` Nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir DBTimeStamp yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Elde edilen süreyi başvurulan *dbts* yapısına depolar. Bu işlev tarafından başlatılan `fraction` veriyapısınınüyesisıfıraayarlanmışolacak.`DBTIMESTAMP`

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>CTime:: GetAsSystemTime

`CTime` Nesnesinde depolanan zaman bilgilerini Win32 ile uyumlu bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
`CTime` Nesnenin dönüştürülmüş tarih/saat değerini tutan bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime`elde edilen süreyi başvurulan *timeDest* yapısına depolar. Bu işlev tarafından başlatılan `wMilliseconds` veriyapısınınüyesisıfıraayarlanmışolacak.`SYSTEMTIME`

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>CTime:: GetCurrentTime

Geçerli saati `CTime` temsil eden bir nesne döndürür.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Açıklamalar

Geçerli sistem tarihini ve saati Eşgüdümlü Evrensel Saat (UTC) olarak döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>CTime:: GetDay

`CTime` Nesnenin gösterdiği günü döndürür.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 31 aralığında yerel saate göre ayın gününü döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili ve statik olarak ayrılmış bir arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>CTime:: GetDayOfWeek

`CTime` Nesnenin gösterdiği haftanın gününü döndürür.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Haftanın gününü yerel saate göre döndürür; 1 = Pazar, 2 = Pazartesi, 7 = Cumartesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>CTime:: Getgmttd

Bu`CTime` nesnede bulunan sürenin ayrışanı içeren bir **struct tm** alır.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İçerme dosyası SıRASıNDA tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Olsun. Yapı düzeni için bkz. [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetGmtTm`UTC döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL öğesini tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>CTime:: GetHour

`CTime` Nesnenin gösterdiği saati döndürür.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 0 ile 23 aralığındaki saati döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>CTime:: GetLocalTm

Bu`CTime` nesnede bulunan sürenin ayrışanı içeren bir **struct tm** alır.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

İçerme dosyası SıRASıNDA tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Olsun. Yapı düzeni için bkz. [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetLocalTm`yerel saati döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL öğesini tanımlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>CTime:: GetMinute

`CTime` Nesnenin temsil ettiği dakikayı döndürür.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre dakikayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="getmonth"></a>CTime:: GetMonth

`CTime` Nesnenin temsil ettiği ayı döndürür.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 1 ile 12 arasında (1 = Ocak) ayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="getsecond"></a>CTime:: GetSecond

`CTime` Nesne tarafından temsil edilen saniyeyi döndürür.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre saniyeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

##  <a name="gettime"></a>CTime:: GetTime

Verilen`CTime` nesne için bir **__time64_t** değeri döndürür.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`GetTime`geçerli `CTime` nesne ve 1 Ocak 1970 arasındaki saniye sayısını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>CTime:: GetYear

`CTime` Nesnenin temsil ettiği yılı döndürür.

```
int GetYear();
```

### <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970 aralığında, 18 Ocak 2038 (dahil) aralığında yerel saate göre yılı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `GetLocalTm`dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer `CTime` üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

##  <a name="operator_eq"></a>CTime:: operator =

Atama işleci.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parametreler

*saat*<br/>
Yeni tarih/saat değeri.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleci, kaynak saatini bu `CTime` nesneye kopyalar. Bir `CTime` nesnedeki iç zaman depolama alanı saat diliminden bağımsızdır. Atama sırasında saat dilimi dönüştürmesi gerekli değildir.

##  <a name="operator_add_-"></a>CTime:: operator +,-

Bu işleçler ve `CTime` nesneler ekler `CTimeSpan` ve çıkarır.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*timeSpan*<br/>
Eklenecek veya çıkarılacak nesne. `CTimeSpan`

*saat*<br/>
Çıkarılacak `CTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlemin `CTime` sonucunu `CTimeSpan` temsil eden bir veya nesnesi.

### <a name="remarks"></a>Açıklamalar

`CTime`nesneler mutlak süreyi temsil eder `CTimeSpan` , nesneler göreli süreyi temsil eder. İlk iki operatör `CTime` nesneleri nesnelerine ve nesnelerden nesneleri eklemenize ve `CTimeSpan` bunlara çıkareklemenize olanak tanır. Üçüncü işleç bir nesneyi başka `CTime` `CTimeSpan` bir nesneden çıkartabilir olanak sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>CTime:: operator + =,-=

Bu işleçler, nesnesine ve `CTimeSpan` `CTime` nesnesinden bir nesne ekler ve çıkarır.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Eklenecek veya çıkarılacak nesne. `CTimeSpan`

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu `CTimeSpan` `CTime` nesneye ve nesnesinden bir nesne eklemenize ve çıkartabilir.

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
Güncelleştirmek `CArchive` istediğiniz nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

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
