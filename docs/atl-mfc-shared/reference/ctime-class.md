---
title: CTime Sınıfı
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
ms.openlocfilehash: e6e471fe648c5fa370cce750e8569e158eb1ffe4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317565"
---
# <a name="ctime-class"></a>CTime Sınıfı

Mutlak bir saati ve tarihi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CTime::CTime](#ctime)|Nesneleri `CTime` çeşitli şekillerde inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTime::Biçim](#format)|Nesneyi `CTime` yerel saat dilimini temel alan biçimlendirilmiş bir dizedönüştürür.|
|[CTime::FormatGmt](#formatgmt)|Bir `CTime` nesneyi UTC'ye dayalı biçimlendirilmiş bir dize dönüştürür.|
|[CTime::GetasDBTIMESTAMP](#getasdbtimestamp)|`CTime` Nesnede depolanan saat bilgilerini Win32 uyumlu DBTIMESTAMP yapısına dönüştürür.|
|[CTime::GetasSystemTime](#getassystemtime)|`CTime` Nesnede depolanan saat bilgilerini Win32 uyumlu [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürür.|
|[CTime::GetCurrentTime](#getcurrenttime)|Geçerli zamanı `CTime` (statik üye işlev) temsil eden bir nesne oluşturur.|
|[CTime::GetDay](#getday)|`CTime` Nesneye göre temsil edilen günü döndürür.|
|[CTime::GetDayofWeek](#getdayofweek)|`CTime` Nesne tarafından temsil edilen haftanın gününü döndürür.|
|[CTime::GetGmtTm](#getgmttm)|UTC'ye dayalı olarak bir `CTime` nesneyi bileşenlere ayırır.|
|[CTime::GetHour](#gethour)|`CTime` Nesne tarafından temsil edilen saati döndürür.|
|[CTime::GetLocalTm](#getlocaltm)|Yerel saat `CTime` dilimini temel alan bir nesneyi bileşenlere ayırır.|
|[CTime::GetMinute](#getminute)|Nesne tarafından temsil edilen `CTime` dakikayı döndürür.|
|[CTime::GetMonth](#getmonth)|`CTime` Nesne tarafından temsil edilen ayı döndürür.|
|[CTime::GetSecond](#getsecond)|`CTime` Nesne tarafından temsil edilen ikinci yi döndürür.|
|[CTime::GetTime](#gettime)|Verilen `CTime` nesne için **__time64_t** bir değer verir.|
|[CTime::GetYear](#getyear)|`CTime` Nesne tarafından temsil edilen yılı döndürür.|
|[Ç::Serialize64](#serialize64)|Arşive veya arşivden gelen verileri seri hale getirmek.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operatör + -](#operator_add_-)|Bu işleçler `CTimeSpan` ekleyin `CTime` ve çıkarmak ve nesneleri.|
|[işleç +=, -=](#operator_add_eq_-_eq)|Bu işleçler bir `CTimeSpan` nesne ekler `CTime` ve bu nesneye ve bu nesneye çıkarır.|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç ==, <, vb.](#ctime_comparison_operators)|Karşılaştırma işleçleri.|

## <a name="remarks"></a>Açıklamalar

`CTime`taban sınıfa sahip değildir.

`CTime`değerler, Eşgüdümlü Evrensel zamana (Greenwich Ortalama Saati, GMT) eşdeğer olan eşgüdümlü evrensel zamana (UTC) dayanır. Saat diliminin nasıl belirlendiği hakkında bilgi için [Zaman Yönetimi'ne](../../c-runtime-library/time-management.md) bakın.

Bir `CTime` nesne oluşturduğunuzda, `nDST` parametreyi standart saatin geçerli olduğunu belirtmek için 0'a veya gün ışığından yararlanma süresinin geçerli olduğunu belirtmek için 0'dan büyük bir değere veya standart saat veya gün ışığından yararlanma saati olup olmadığını C çalışma zamanı kitaplık kodunu hesaplamak için sıfırdan daha küçük bir değere ayarlayın. `tm_isdst`gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve [mktime'ın](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) geri dönüş değeri öngörülemez. bir `timeptr` tm yapısına işaret eden bir tm [yapısı, asctime_s,](../../c-runtime-library/reference/asctime-s-wasctime-s.md) [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)için önceki bir çağrı yla döndürülürse, `tm_isdst` alan doğru değeri içerir.

Bir eşlik sınıf, [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığı temsil eder.

`CTime` Ve `CTimeSpan` sınıflar türetme için tasarlanmaz. Sanal işlev ler olmadığından, boyutu `CTime` `CTimeSpan` ve nesneleri tam olarak 8 bayt. Üye işlevlerin çoğu satır lıdır.

> [!NOTE]
> Üst tarih sınırı 12/31/3000'dir. Alt sınır 1/1/1970 12:00:00 GMT'dir.

Kullanma `CTime`hakkında daha fazla bilgi için, Run-Time Kitaplığı Başvurusu'ndaki [Tarih ve Saat](../../atl-mfc-shared/date-and-time.md)ve Zaman [Yönetimi](../../c-runtime-library/time-management.md) makalelerini görün.

> [!NOTE]
> Yapı `CTime` MFC 7.1'den MFC 8.0'a değiştirildi. Bir `CTime` yapıyı, MFC 8.0 veya sonraki bir sürüm altında ** <<işleci** <<kullanarak seri hale ederseniz, ortaya çıkan dosya MFC'nin eski sürümlerinde okunamaz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime.h

## <a name="ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a>CTime Karşılaştırma Operatörleri

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

*time*<br/>
Karşılaştırılacak `CTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki mutlak kez karşılaştırın ve koşul doğruysa TRUE döndürülme; aksi takdirde YANLIŞ.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

## <a name="ctimectime"></a><a name="ctime"></a>CTime::CTime

Belirtilen süre `CTime` yle baş harfe getirilmiş yeni bir nesne oluşturur.

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

*zamanSrc*<br/>
Zaten `CTime` var olan bir nesneyi gösterir.

*time*<br/>
1 `__time64_t` Ocak 1970 UTC'den sonraki saniye sayısı olan bir zaman değeri. Bunun yerel saate göre ayarlanacağını unutmayın. Örneğin, New York'taysanız ve `CTime` 0 parametresi geçerek bir nesne oluşturuyorsanız, [CTime::GetMonth](#getmonth) 12 döndürür.

*nYear*, *nMonth*, *nDay*, *nHour*, *nMin*, *nSec*<br/>
Yeni `CTime` nesneye kopyalanacak tarih ve saat değerlerini gösterir.

*nDST*<br/>
Gün ışığından yararlanma zamanının geçerli olup olmadığını gösterir. Üç değerden biri olabilir:

- *nDST* 0Standart zaman adabı yürürlüktedir.

- *nDST* 0Daylight'dan daha büyük bir değere ayarlanmıştır.

- *nDST* 0The varsayılanından daha az bir değere ayarlanır. Standart saatin veya gün ışığından yararlanma saatinin geçerli olup olmadığını otomatik olarak hesaplar.

*wDosTarih*, *wDosTime*<br/>
MS-DOS tarih ve saat değerleri tarih/saat değerine dönüştürülür ve `CTime` yeni nesneye kopyalanır.

*St*<br/>
Tarih/saat değerine dönüştürülecek ve yeni `CTime` nesneye kopyalanacak [systemtime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı.

*Ft*<br/>
Bir DATE/time değerine dönüştürülecek ve yeni `CTime` nesneye kopyalanacak bir [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı.

*dbts*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Her yapıcı aşağıda açıklanmıştır:

- `CTime();`Başledilmemiş `CTime` bir nesne oluşturuyor. Bu oluşturucu nesne `CTime` dizileri tanımlamak için izin verir. Kullanmadan önce bu tür dizileri geçerli sürelerle başlatmanız gerekir.

- `CTime( const CTime& );`Bir nesneyi başka `CTime` bir `CTime` değerden inşa eder.

- `CTime( __time64_t );``CTime` **__time64_t** türünden bir nesne oluşturuyor. Bu oluşturucu utc zamanı bekler ve sonucu depolamadan önce sonucu yerel bir saate dönüştürür.

- `CTime( int, int, ...);`Her bileşen `CTime` aşağıdaki aralıklarla sınırlandırılmış yerel saat bileşenlerinden bir nesne oluşur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*nYıl*|1970-3000|
   |*nAy*|1-12|
   |*nGün*|1-31|
   |*nSaat*|0-23|
   |*nMin*|0-59|
   |*Nsec*|0-59|

   Bu oluşturucu UTC'ye uygun dönüştürme yapar. Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü, zaman bileşenlerinden birinin veya daha fazlasının kapsama alanı dışında olduğunu ileri sürmektedir. Aramadan önce bağımsız değişkenleri doğrulamanız gerekir. Bu oluşturucu yerel bir saat bekliyor.

- `CTime( WORD, WORD );`Belirtilen MS-DOS tarih ve saat değerlerinden bir `CTime` nesne yapar. Bu oluşturucu yerel bir saat bekliyor.

- `CTime( const SYSTEMTIME& );`Bir `CTime` `SYSTEMTIME` yapıdan bir nesne inşa eder. Bu oluşturucu yerel bir saat bekliyor.

- `CTime( const FILETIME& );`Bir `CTime` `FILETIME` yapıdan bir nesne inşa eder. Büyük olasılıkla doğrudan `CTime FILETIME` başlatma kullanmazsınız. Bir dosyayı `CFile` işlemek için bir `CFile::GetStatus` nesne kullanıyorsanız, `FILETIME` bir yapıyla `CTime` birlikte başharfe bvuran bir nesne aracılığıyla dosya zaman damgasını sizin için alır. Bu oluşturucu UTC'ye dayalı bir süre varsayar ve sonucu depolamadan önce değeri otomatik olarak yerel saate dönüştürür.

   > [!NOTE]
   > Parametre kullanan `DBTIMESTAMP` yapıcı yalnızca OLEDB.h dahil edildiğinde kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına bakın. Ayrıca Windows SDK'daki [MS-DOS Tarih ve Saat](/windows/win32/SysInfo/ms-dos-date-and-time) girişine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

## <a name="ctimeformat"></a><a name="format"></a>CTime::Biçim

Tarih-saat değerinin biçimlendirilmiş bir temsilini oluşturmak için bu üye işlevi arayın.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçimlendirme dizesine `printf` benzer bir biçimlendirme dizesi. Bir yüzde ( )`%`işaretinden önce biçimlendirme kodları ilgili `CTime` bileşen tarafından değiştirilir. Biçimlendirme dizesindeki diğer karakterler döndürülen dize değişmeden kopyalanır. Biçimlendirme kodları listesi için çalışma zamanı işlevinin [süresine](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) bakın.

*nFormatID*<br/>
Bu biçimi tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş zamanı içeren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Bu `CTime` nesnenin durumu null ise, döndürme değeri boş bir dize.

Bu yöntem, biçime tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000 Evrensel Eşgüdümlü Zaman (UTC) arasında değişmiyorsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

## <a name="ctimeformatgmt"></a><a name="formatgmt"></a>CTime::FormatGmt

Bu `CTime` nesneye karşılık gelen biçimlendirilmiş bir dize oluşturur.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
`printf` Biçimlendirme dizesine benzer bir biçimlendirme dizesini belirtir. Ayrıntılar için çalışma [zamanı](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) işlevini niçin inceleyene bakın.

*nFormatID*<br/>
Bu biçimi tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilmiş zamanı içeren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Zaman değeri dönüştürülmez ve bu nedenle UTC'yi yansıtır.

Bu yöntem, biçime tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000 Evrensel Eşgüdümlü Zaman (UTC) arasında değişmiyorsa bir özel durum oluşturur.

### <a name="example"></a>Örnek

CTime örneğine [bakın:Biçim.](#format)

## <a name="ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a>CTime::GetasDBTIMESTAMP

`CTime` Nesnede depolanan zaman bilgilerini Win32 uyumlu DBTIMESTAMP yapısına dönüştürmek için bu üye işlevi arayın.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ortaya çıkan zamanı başvurulan *dbts* yapısında saklar. Bu `DBTIMESTAMP` işlev tarafından ortaya alınan veri `fraction` yapısı, üyesini sıfıra ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

## <a name="ctimegetassystemtime"></a><a name="getassystemtime"></a>CTime::GetasSystemTime

`CTime` Nesnede depolanan zaman bilgilerini Win32 uyumlu [SYSTEMTIME](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürmek için bu üye işlevi arayın.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
Nesnenin dönüştürülen tarih/saat değerini tutacak [systemtime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına `CTime` yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Doğru eğer başarılı; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime`ortaya çıkan zamanı başvurulan *zamanDest* yapısında depolar. Bu `SYSTEMTIME` işlev tarafından ortaya alınan veri `wMilliseconds` yapısı, üyesini sıfıra ayarlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

## <a name="ctimegetcurrenttime"></a><a name="getcurrenttime"></a>CTime::GetCurrentTime

Geçerli `CTime` zamanı temsil eden bir nesne döndürür.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Açıklamalar

Eşgüdümlü Evrensel Saat 'te (UTC) geçerli sistem tarih ve saatini verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

## <a name="ctimegetday"></a><a name="getday"></a>CTime::GetDay

`CTime` Nesneye göre temsil edilen günü döndürür.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate bağlı olarak ayın gününü 1 ile 31 aralığında döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili, statik olarak ayrılmış bir arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

## <a name="ctimegetdayofweek"></a><a name="getdayofweek"></a>CTime::GetDayofWeek

`CTime` Nesne tarafından temsil edilen haftanın gününü döndürür.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre haftanın gününü döndürür; 1 = Pazar, 2 = Pazartesi, 7 = Cumartesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

## <a name="ctimegetgmttm"></a><a name="getgmttm"></a>CTime::GetGmtTm

Bu `CTime` nesnede bulunan zamanın ayrıştırma içeren bir **yapı tm** alır.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ptm*<br/>
Zaman verilerini alacak bir arabelleğe işaret edin. Bu işaretçi NULL ise, bir özel durum atılır.

### <a name="return-value"></a>Dönüş Değeri

Dahil dosya TIME tanımlandığı gibi doldurulmuş **bir yapı tm** için bir işaretçi. H. Yapı düzeni için [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) bakın.

### <a name="remarks"></a>Açıklamalar

`GetGmtTm`UTC'yi döndürür.

*ptm* NULL olamaz. Ptm'nin iç, statik olarak ayrılmış *ptm* bir arabelleğe kullanılması gerektiğini belirtmek için NULL olabileceği eski davranışa dönmek istiyorsanız, _SECURE_ATL tanımlanama.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

## <a name="ctimegethour"></a><a name="gethour"></a>CTime::GetHour

`CTime` Nesne tarafından temsil edilen saati döndürür.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saati, yerel saate göre 0 ile 23 aralığında döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

## <a name="ctimegetlocaltm"></a><a name="getlocaltm"></a>CTime::GetLocalTm

Bu `CTime` nesnede bulunan zamanın ayrışmasını içeren bir **yapı tm** alır.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ptm*<br/>
Zaman verilerini alacak bir arabelleğe işaret edin. Bu işaretçi NULL ise, bir özel durum atılır.

### <a name="return-value"></a>Dönüş Değeri

Dahil dosya TIME tanımlandığı gibi doldurulmuş **bir yapı tm** için bir işaretçi. H. Yapı düzeni için [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) bakın.

### <a name="remarks"></a>Açıklamalar

`GetLocalTm`yerel saati döndürür.

*ptm* NULL olamaz. Ptm'nin iç, statik olarak ayrılmış *ptm* bir arabelleğe kullanılması gerektiğini belirtmek için NULL olabileceği eski davranışa dönmek istiyorsanız, _SECURE_ATL tanımlanama.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

## <a name="ctimegetminute"></a><a name="getminute"></a>CTime::GetMinute

Nesne tarafından temsil edilen `CTime` dakikayı döndürür.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dakikayı, yerel saate göre 0 ile 59 aralığında döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="ctimegetmonth"></a><a name="getmonth"></a>CTime::GetMonth

`CTime` Nesne tarafından temsil edilen ayı döndürür.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 12 (1 = Ocak) aralığında yerel saate göre ayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)için örneğe bakın.

## <a name="ctimegetsecond"></a><a name="getsecond"></a>CTime::GetSecond

`CTime` Nesne tarafından temsil edilen ikinci yi döndürür.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre ikincisini 0 ile 59 aralığında döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="ctimegettime"></a><a name="gettime"></a>CTime::GetTime

Verilen `CTime` nesne için **__time64_t** bir değer verir.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`GetTime`geçerli `CTime` nesne ile 1 Ocak 1970 arasındaki saniye sayısını döndürecektir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

## <a name="ctimegetyear"></a><a name="getyear"></a>CTime::GetYear

`CTime` Nesne tarafından temsil edilen yılı döndürür.

```
int GetYear();
```

### <a name="return-value"></a>Dönüş Değeri

1 Ocak 1,1970 aralığında yerel saate göre yılı 18 Ocak 2038 'e (dahil) döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev, dahili statik olarak ayrılmış arabellek kullanan çağrıları çağırır. `GetLocalTm` Bu arabellekteki veriler, diğer `CTime` üye işlevlere yapılan çağrılar nedeniyle üzerine yazılır.

### <a name="example"></a>Örnek

[GetDay](#getday)için örneğe bakın.

## <a name="ctimeoperator-"></a><a name="operator_eq"></a>CTime::operator =

Atama işleci.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parametreler

*time*<br/>
Yeni tarih/saat değeri.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenen atama işleci, `CTime` kaynak zamanı bu nesneye kopyalar. Bir `CTime` nesnedeki iç zaman depolama sı saat diliminden bağımsızdır. Atama sırasında saat dilimi dönüştürmegerekli değildir.

## <a name="ctimeoperator---"></a><a name="operator_add_-"></a>CTime::operatör +, -

Bu işleçler `CTimeSpan` ekleyin `CTime` ve çıkarmak ve nesneleri.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*Timespan*<br/>
Eklenecek `CTimeSpan` veya çıkarılacak nesne.

*time*<br/>
Çıkarılacak `CTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İşlemin sonucunu temsil eden bir `CTime` veya `CTimeSpan` nesne.

### <a name="remarks"></a>Açıklamalar

`CTime`nesneler mutlak zamanı, `CTimeSpan` nesneler göreceli zamanı temsil eder. İlk iki işleç, `CTimeSpan` nesnelere ve nesnelerden `CTime` nesneler eklemenize ve çıkarmanıza olanak sağlar. Üçüncü işleç, bir `CTime` `CTimeSpan` nesneyi verim vermek için bir nesneyi diğerinden çıkarmanızı sağlar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

## <a name="ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a>CTime::işleç +=, -=

Bu işleçler bir `CTimeSpan` nesne ekler `CTime` ve bu nesneye ve bu nesneye çıkarır.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
Eklenecek `CTimeSpan` veya çıkarılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bir `CTimeSpan` nesne eklemenize ve `CTime` bu nesneye ve bu nesneye çıkarmanıza izin verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

## <a name="ctimeserialize64"></a><a name="serialize64"></a>Ç::Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFC projelerinde kullanılabilir.

Bir arşive veya arşivden üye değişkenle ilişkili verileri seri hale getirmek.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
Güncelleştirmek istediğiniz `CArchive` nesne.

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
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
