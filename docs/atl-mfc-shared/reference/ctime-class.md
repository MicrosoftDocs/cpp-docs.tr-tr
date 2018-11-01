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
ms.openlocfilehash: bed403e4bc1cca1d31a394be7157de9e65abff95
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519450"
---
# <a name="ctime-class"></a>CTime sınıfı

Bir mutlak saatini ve tarihini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTime::CTime](#ctime)|Yapıları `CTime` çeşitli yollarla nesneleri.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTime::Format](#format)|Dönüştürür bir `CTime` bir biçimlendirilmiş dize nesnesine — yerel saat dilimi temel alınarak.|
|[CTime::FormatGmt](#formatgmt)|Dönüştürür bir `CTime` bir biçimlendirilmiş dize nesnesine — UTC temel.|
|[CTime::GetAsDBTIMESTAMP](#getasdbtimestamp)|Depolanan saat bilgisi dönüştürür `CTime` Win32 uyumlu DBTIMESTAMP yapısı için nesne.|
|[CTime::GetAsSystemTime](#getassystemtime)|Depolanan saat bilgisi dönüştürür `CTime` Win32 uyumlu nesnesine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.|
|[CTime::GetCurrentTime](#getcurrenttime)|Oluşturur bir `CTime` (statik üye işlevini) geçerli zamanı temsil eden nesne.|
|[CTime::GetDay](#getday)|Günü temsil tarafından döndürür `CTime` nesne.|
|[CTime::GetDayOfWeek](#getdayofweek)|Tarafından temsil edilen haftanın gününü döndürür `CTime` nesne.|
|[CTime::GetGmtTm](#getgmttm)|Böler bir `CTime` bileşenleri nesnesine — UTC temel.|
|[CTime::GetHour](#gethour)|Tarafından temsil edilen saati döndürür `CTime` nesne.|
|[CTime::GetLocalTm](#getlocaltm)|Böler bir `CTime` bileşenleri nesnesine — yerel saat dilimi temel alınarak.|
|[CTime::GetMinute](#getminute)|Tarafından temsil edilen dakikayı döndürür `CTime` nesne.|
|[CTime::GetMonth](#getmonth)|Tarafından temsil edilen ayı döndürür `CTime` nesne.|
|[CTime::GetSecond](#getsecond)|Tarafından temsil edilen ikinci döndürür `CTime` nesne.|
|[CTime::GetTime](#gettime)|Döndürür bir **__time64_t** değerini verilen `CTime` nesne.|
|[CTime::GetYear](#getyear)|Tarafından temsil edilen yılı döndürür `CTime` nesne.|
|[CTime::Serialize64](#serialize64)|Bir arşiv veri serileştirir.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator + -](#operator_add_-)|Bu işleçler ekleme ve çıkarmayı `CTimeSpan` ve `CTime` nesneleri.|
|[operator +=-=](#operator_add_eq_-_eq)|Bu işleçler ekleme ve çıkarmayı bir `CTimeSpan` nesne için ve bu `CTime` nesne.|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç ==, <, vb..](#ctime_comparison_operators)|Karşılaştırma işleçleri.|

## <a name="remarks"></a>Açıklamalar

`CTime` bir temel sınıfa sahip değil.

`CTime` değerler Eşgüdümlü Evrensel Saat (UTC) Eşgüdümlü Evrensel Saat (Greenwich saati, GMT) eşdeğer olan temel alır. Bkz: [zaman Yönetimi](../../c-runtime-library/time-management.md) saat dilimini belirleme hakkında bilgi.

Oluştururken bir `CTime` nesne, ayarlama `nDST` parametresi Standart Saati etkindir veya göstermek için 0'dan büyük bir değere bu Yaz Saati etkin olduğunu belirtmek için 0 ya da bir değer sıfırdan küçük C çalışma zamanı kitaplığı kod sayar sağlamak için e Standart Saati gün ışığından yararlanma etkin olup. `tm_isdst` gerekli bir alandır. Değeri tanımlanmamış ayarlanmazsa ve dönüş değeri [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) tahmin edilemez. Varsa `timeptr` önceki bir çağrı tarafından döndürülen tm yapısına işaret [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md), veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md), `tm_isdst` alan içerir doğru değeri.

Bir yardımcı sınıfı [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığını temsil eder.

`CTime` Ve `CTimeSpan` sınıflar türetmeyi için tasarlanmamıştır. Hiçbir sanal işlevi, boyutu olduğundan `CTime` ve `CTimeSpan` nesneleri, tam olarak 8 bayt. Çoğu üye satır içi işlevlerdir.

> [!NOTE]
>  Tarih üst sınırı 12/31/3000'dir. Alt sınır 1/1/1970 12:00:00 GMT.

Kullanma hakkında daha fazla bilgi için `CTime`, makalelere göz atın [tarih ve saat](../../atl-mfc-shared/date-and-time.md), ve [zaman Yönetimi](../../c-runtime-library/time-management.md) çalışma zamanı kitaplığı başvurusu.

> [!NOTE]
>  `CTime` Yapısı için MFC 8.0 MFC 7.1 değiştirildi. Sıralarsanız, bir `CTime` kullanarak yapısı **işleci <<** MFC 8.0 veya sonraki bir sürümünü elde edilen dosyanın eski sürümlerine ilişkin MFC okunabilir olmayacaktır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltime.h

##  <a name="ctime_comparison_operators"></a>  CTime Karşılaştırma işleçleri

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
`CTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Koşul true ise bu işleçler iki kez mutlak ve dönüş doğru karşılaştırma; Aksi durumda FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

##  <a name="ctime"></a>  CTime::CTime

Yeni bir oluşturur `CTime` nesnesi ile belirtilen saat başlatıldı.

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

*timeSrc*<br/>
Belirten bir `CTime` zaten var. nesne.

*saat*<br/>
A `__time64_t` zaman değeri, 1 Ocak 1970 UTC saniye sayısıdır. Bu, yerel saat olarak ayarlanacağını unutmayın. Örneğin, New York'ta ve oluşturursanız bir `CTime` 0, bir parametre geçirerek nesne [CTime::GetMonth](#getmonth) 12 döndürür.

*nYear*, *nMonth*, *nhatalı günü*, *nHour*, *nMin*, *nSec*<br/>
Yeni içine kopyalanacak tarih ve saat değerlerini gösteren `CTime` nesne.

*nDST*<br/>
Günışığından yararlanmanın etkin olup olmadığını gösterir. Üç değerlerden biri olabilir:

- *nDST* 0Standard zaman kümesine etkindir.

- *nDST* saati etkindir 0Daylight büyük bir değere ayarlayın.

- *nDST* 0The varsayılan değerinden düşük bir değere ayarlayın. Standart Saati veya günışığından yararlanmanın etkin olup olmadığını otomatik olarak hesaplar.

*wDosDate*, *wDosTime*<br/>
Bir tarih/saat değerine dönüştürülür ve yeni kopyalanan için tarih ve saat değerlerini MS-DOS `CTime` nesne.

*St*<br/>
A [SYSTEMTIME](../../mfc/reference/systemtime-structure.md) yapısı bir tarih/saat değerine dönüştürülür ve yeni kopyalanan `CTime` nesne.

*ft*<br/>
A [FILETIME](../../mfc/reference/filetime-structure.md) yapısı bir tarih/saat değerine dönüştürülür ve yeni kopyalanan `CTime` nesne.

*dbts*<br/>
Geçerli yerel saat içeren bir DBTIMESTAMP yapısı bir başvuru.

### <a name="remarks"></a>Açıklamalar

Her Oluşturucu, aşağıda açıklanmıştır:

- `CTime();` Başlatılmamış bir yapıları `CTime` nesne. Bu oluşturucu tanımlamanıza olanak tanıyan `CTime` nesne dizileri. Bu tür diziler kullanmadan önce geçerli süreler başlatması gerekir.

- `CTime( const CTime& );` Oluşturur bir `CTime` başka bir nesne `CTime` değeri.

- `CTime( __time64_t );` Oluşturur bir `CTime` nesnesinden bir **__time64_t** türü. Bu oluşturucu, UTC saati bekler ve sonucu depolamadan önce sonucu bir yerel saate dönüştürür.

- `CTime( int, int, ...);` Oluşturur bir `CTime` her bileşeni ile yerel saat bileşenlerini bir nesneden kısıtlı aşağıdaki aralıklara:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*nYear*|1970-3000|
   |*nMonth*|1-12|
   |*nhatalı günü*|1-31|
   |*nHour*|0-23|
   |*nMin*|0-59|
   |*nSec*|0-59|

   Bu oluşturucu, UTC uygun dönüştürme yapar. Bir Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar veya daha fazla zaman bileşenleri aralık dışında. Bağımsız değişkenler çağırmadan önce doğrulamanız gerekir. Bu oluşturucu, yerel saati bekler.

- `CTime( WORD, WORD );` Oluşturur bir `CTime` nesnesinden belirtilen MS-DOS tarih ve saat değerleri. Bu oluşturucu, yerel saati bekler.

- `CTime( const SYSTEMTIME& );` Oluşturur bir `CTime` nesnesinden bir `SYSTEMTIME` yapısı. Bu oluşturucu, yerel saati bekler.

- `CTime( const FILETIME& );` Oluşturur bir `CTime` nesnesinden bir `FILETIME` yapısı. Büyük olasılıkla kullanmaz `CTime FILETIME` doğrudan başlatma. Kullanıyorsanız bir `CFile` bir dosya işlemek için nesne `CFile::GetStatus` dosya zaman damgası için size alır bir `CTime` nesne başlatılmış olan bir `FILETIME` yapısı. Bu oluşturucu, bir süre UTC temel varsayar ve sonucu depolamadan önce değer yerel saat olarak otomatik olarak dönüştürür.

   > [!NOTE]
   > Oluşturucu kullanılarak `DBTIMESTAMP` parametresi, yalnızca kullanılabilir biçim dahil edildiğinde.

Daha fazla bilgi için [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) ve [FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284) Windows SDK'sındaki yapısı. Ayrıca bkz: [MS-DOS tarih ve saat](/windows/desktop/SysInfo/ms-dos-date-and-time) Windows SDK'sı girişi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

##  <a name="format"></a>  CTime::Format

Biçimlendirilmiş bir tarih-saat değeri gösterimini oluşturmak için bu üye işlevini çağırın.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Bir biçimlendirme dizesi benzer `printf` biçimlendirme dizesi. Biçimlendirme kodları, öncesinde bir yüzde (`%`) oturum açın, ilgili değiştirilir `CTime` bileşeni. Biçimlendirme dizesi diğer karakterler döndürülen dizeye değiştirilmeden kopyalanır. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) biçimlendirme kodları listesi için.

*nFormatID*<br/>
Bu biçim tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) , biçimlendirilmiş saati içerir.

### <a name="remarks"></a>Açıklamalar

Varsa bu durum `CTime` nesnesi null ise, dönüş değeri boş bir dizedir.

Biçimlendirilecek tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık, 3000 aralığında değil, bu yöntem bir özel durum oluşturur. Eşgüdümlü Evrensel Saat (UTC).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

##  <a name="formatgmt"></a>  CTime::FormatGmt

Bunun için karşılık gelen bir biçimlendirilmiş dize üretir `CTime` nesne.

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Benzer şekilde bir biçimlendirme dizesi belirtir `printf` biçimlendirme dizesi. Çalışma zamanı işlevi görmek [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) Ayrıntılar için.

*nFormatID*<br/>
Bu biçim tanımlayan dize kimliği.

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) , biçimlendirilmiş saati içerir.

### <a name="remarks"></a>Açıklamalar

Zaman değeri değil dönüştürülür ve bu nedenle UTC yansıtır.

Biçimlendirilecek tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık, 3000 aralığında değil, bu yöntem bir özel durum oluşturur. Eşgüdümlü Evrensel Saat (UTC).

### <a name="example"></a>Örnek

Örneğin bakın [CTime::Format](#format).

##  <a name="getasdbtimestamp"></a>  CTime::GetAsDBTIMESTAMP

Depolanan saat bilgisi dönüştürmek için bu üye işlevi çağrısı `CTime` Win32 uyumlu DBTIMESTAMP yapısı için nesne.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts*<br/>
Geçerli yerel saat içeren bir DBTIMESTAMP yapısı bir başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sonuçta elde edilen zaman başvurulan depolar *dbts* yapısı. `DBTIMESTAMP` Bu işlev tarafından başlatılan veri yapısı olacaktır, `fraction` üye sıfır olarak ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

##  <a name="getassystemtime"></a>  CTime::GetAsSystemTime

Depolanan saat bilgisi dönüştürmek için bu üye işlevi çağrısı `CTime` Win32 uyumlu nesnesine [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) yapısı.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
Bir başvuru bir [SYSTEMTIME](https://msdn.microsoft.com/library/windows/desktop/ms724950) dönüştürülen bir tarih/saat değerini tutacak yapısı `CTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime` Sonuçta elde edilen zaman başvurulan depolar *timeDest* yapısı. `SYSTEMTIME` Bu işlev tarafından başlatılan veri yapısı olacaktır, `wMilliseconds` üye sıfır olarak ayarlayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

##  <a name="getcurrenttime"></a>  CTime::GetCurrentTime

Döndürür bir `CTime` geçerli zamanı temsil eden nesne.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Açıklamalar

Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

##  <a name="getday"></a>  CTime::GetDay

Günü temsil tarafından döndürür `CTime` nesne.

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 31 Aralık içinde yerel saate göre ayın günü döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, iç, statik olarak ayrılan bir arabellek kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

##  <a name="getdayofweek"></a>  CTime::GetDayOfWeek

Tarafından temsil edilen haftanın gününü döndürür `CTime` nesne.

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saatini temel alan haftanın gününü döndürür; 1 Pazar, 2 = Pazartesi =, Cumartesi = 7 için.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

##  <a name="getgmttm"></a>  CTime::GetGmtTm

Alır bir **yapı tm** zaman bu konuda yer alan bir ayrıştırma içeren `CTime` nesne.

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ptm*<br/>
Saat verilerini alacak arabellek işaret eder. Bu işaretçinin NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir doldurulmuş içinde **yapı tm** zaman içerme dosyasında tanımlanan. H Bkz: [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) yapısı düzeni için.

### <a name="remarks"></a>Açıklamalar

`GetGmtTm` UTC döndürür.

*ptm* NULL olamaz. Eski davranışa dönmek istiyorsanız *ptm* belirtmek için boş bir iç olabilir, statik olarak ayrılan arabelleğin kullanılmalıdır, ardından _SECURE_ATL Kaldır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

##  <a name="gethour"></a>  CTime::GetHour

Tarafından temsil edilen saati döndürür `CTime` nesne.

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 23 aralığında yerel saate göre saati döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

##  <a name="getlocaltm"></a>  CTime::GetLocalTm

Alır bir **yapı tm** zaman bu konuda yer alan bir ayrıştırma içeren `CTime` nesne.

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*ptm*<br/>
Saat verilerini alacak arabellek işaret eder. Bu işaretçinin NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir doldurulmuş içinde **yapı tm** zaman içerme dosyasında tanımlanan. H Bkz: [gmtime, _gmtime32, _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) yapısı düzeni için.

### <a name="remarks"></a>Açıklamalar

`GetLocalTm` yerel saati döndürür.

*ptm* NULL olamaz. Eski davranışa dönmek istiyorsanız *ptm* belirtmek için boş bir iç olabilir, statik olarak ayrılan arabelleğin kullanılmalıdır, ardından _SECURE_ATL Kaldır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

##  <a name="getminute"></a>  CTime::GetMinute

Tarafından temsil edilen dakikayı döndürür `CTime` nesne.

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dakika, 0 ile 59 aralığında yerel saate göre döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

Örneğin bakın [GetHour](#gethour).

##  <a name="getmonth"></a>  CTime::GetMonth

Tarafından temsil edilen ayı döndürür `CTime` nesne.

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 12 aralığında yerel saate göre ayı döndürür (1 Ocak =).

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

Örneğin bakın [GetDay](#getday).

##  <a name="getsecond"></a>  CTime::GetSecond

Tarafından temsil edilen ikinci döndürür `CTime` nesne.

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

İkinci döndürür 0 ile 59 aralığında yerel saate göre.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

Örneğin bakın [GetHour](#gethour).

##  <a name="gettime"></a>  CTime::GetTime

Döndürür bir **__time64_t** değerini verilen `CTime` nesne.

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`GetTime` Geçerli saniye sayısını döndürür `CTime` nesne ve 1 Ocak 1970.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

##  <a name="getyear"></a>  CTime::GetYear

Tarafından temsil edilen yılı döndürür `CTime` nesne.

```
int GetYear();
```

### <a name="return-value"></a>Dönüş Değeri

Ocak Aralık içinde yerel saate göre bu yılın döndürür 1,1970, 18 Ocak 2038 (sınırlar dahil) için.

### <a name="remarks"></a>Açıklamalar

Bu işlev çağrıları `GetLocalTm`, arabellek ayrılan bir iç statik olarak kullanır. Diğer çağrılar nedeniyle bu arabelleğinde veri üzerine `CTime` üye işlevleri.

### <a name="example"></a>Örnek

Örneğin bakın [GetDay](#getday).

##  <a name="operator_eq"></a>  CTime::operator =

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

Bu aşırı yüklenmiş atama işleci kaynak zaman içinde bu kopyalar `CTime` nesne. İç saati depolamada bir `CTime` nesnedir saat dilimini bağımsız. Saat dilimi dönüştürmesi ataması sırasında gerekli değildir.

##  <a name="operator_add_-"></a>  CTime::operator +, -

Bu işleçler ekleme ve çıkarmayı `CTimeSpan` ve `CTime` nesneleri.

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*Zaman aralığı*<br/>
`CTimeSpan` Eklenirken veya çıkarılırken için nesne.

*saat*<br/>
`CTime` Çıkarılsın için nesne.

### <a name="return-value"></a>Dönüş Değeri

A `CTime` veya `CTimeSpan` işleminin sonucunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

`CTime` mutlak zaman nesneleri temsil `CTimeSpan` nesneleri göreli zaman temsil eder. İlk iki işleç ekleme ve çıkarmayı izin `CTimeSpan` ve ondan nesneleri `CTime` nesneleri. Üçüncü işleci bir çıkarma sağlar `CTime` elde etmek üzere başka bir nesneden bir `CTimeSpan` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

##  <a name="operator_add_eq_-_eq"></a>  CTime::operator +=-=

Bu işleçler ekleme ve çıkarmayı bir `CTimeSpan` nesne için ve bu `CTime` nesne.

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CTimeSpan` Eklenirken veya çıkarılırken için nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, ekleme ve çıkarmayı sağlar bir `CTimeSpan` nesne için ve bu `CTime` nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

##  <a name="serialize64"></a>  CTime::Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFS projelerinde kullanılabilir.

Bir arşiv bilgisayardan veya bir üye değişkeni ile ilişkili verileri serileştirir.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*ar*<br/>
`CArchive` Güncelleştirmek istediğiniz bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan Sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
