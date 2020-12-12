---
description: 'Daha fazla bilgi edinin: CTime sınıfı'
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
ms.openlocfilehash: 3768423a4d3bf873e9161b846e21fda4beffdc9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166609"
---
# <a name="ctime-class"></a>CTime sınıfı

Mutlak bir saat ve tarihi temsil eder.

## <a name="syntax"></a>Syntax

```
class CTime
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CTime:: CTime](#ctime)|`CTime`Nesneleri çeşitli şekillerde oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTime:: biçim](#format)|Bir `CTime` nesneyi yerel saat dilimine göre biçimli bir dizeye dönüştürür.|
|[CTime:: FormatGmt](#formatgmt)|Bir `CTime` NESNEYI UTC 'ye göre biçimli bir dizeye dönüştürür.|
|[CTime:: GetAsDBTIMESTAMP](#getasdbtimestamp)|Nesnesinde depolanan zaman bilgilerini `CTime` Win32 ile uyumlu bır DBTIMESTAMP yapısına dönüştürür.|
|[CTime:: GetAsSystemTime](#getassystemtime)|Nesnesinde depolanan zaman bilgilerini `CTime` Win32 ile uyumlu bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürür.|
|[CTime:: GetCurrentTime](#getcurrenttime)|`CTime`Geçerli saati (statik üye işlevi) temsil eden bir nesne oluşturur.|
|[CTime:: GetDay](#getday)|Nesnenin gösterdiği günü döndürür `CTime` .|
|[CTime:: GetDayOfWeek](#getdayofweek)|Nesnenin gösterdiği haftanın gününü döndürür `CTime` .|
|[CTime:: Getgmttd](#getgmttm)|`CTime`UTC 'ye göre bir nesneyi bileşenlere ayırır.|
|[CTime:: GetHour](#gethour)|Nesnenin gösterdiği saati döndürür `CTime` .|
|[CTime:: GetLocalTm](#getlocaltm)|`CTime`Yerel saat dilimine bağlı olarak bir nesneyi bileşenlere ayırır.|
|[CTime:: GetMinute](#getminute)|Nesnenin temsil ettiği dakikayı döndürür `CTime` .|
|[CTime:: GetMonth](#getmonth)|Nesnenin temsil ettiği ayı döndürür `CTime` .|
|[CTime:: GetSecond](#getsecond)|Nesne tarafından temsil edilen saniyeyi döndürür `CTime` .|
|[CTime:: GetTime](#gettime)|Verilen nesne için bir **__time64_t** değeri döndürür `CTime` .|
|[CTime:: GetYear](#getyear)|Nesnenin temsil ettiği yılı döndürür `CTime` .|
|[CTime:: Serialize64](#serialize64)|Verileri bir arşivye veya bir arşive seri hale getirir.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç +-](#operator_add_-)|Bu işleçler ve nesneler ekler ve çıkarır `CTimeSpan` `CTime` .|
|[işleç + =,-=](#operator_add_eq_-_eq)|Bu işleçler, nesnesine ve nesnesinden bir nesne ekler ve çıkarır `CTimeSpan` `CTime` .|
|[işleç =](#operator_eq)|Atama işleci.|
|[işleç = =, <, vb.](#ctime_comparison_operators)|Karşılaştırma işleçleri.|

## <a name="remarks"></a>Açıklamalar

`CTime` taban sınıfına sahip değildir.

`CTime` değerler Eşgüdümlü Evrensel saate (UTC) göre belirlenir (Greenwich saati, GMT). Saat diliminin nasıl belirlendiği hakkında bilgi için bkz. [saat yönetimi](../../c-runtime-library/time-management.md) .

Bir `CTime` nesne oluşturduğunuzda, `nDST` Standart saatin geçerli olduğunu belirtmek için parametresini 0 olarak, gün ışığından yararlanma saatinin etkin olduğunu veya 0 ' dan büyük bir değere göre, standart saat veya yaz saatinin etkin olup olmadığını belirten C çalışma zamanı kitaplık kodu hesaplama için sıfırdan küçük bir değere ayarlayın. `tm_isdst` gerekli bir alandır. Ayarlanmamışsa, değeri tanımsızdır ve [mktime](../../c-runtime-library/reference/mktime-mktime32-mktime64.md) 'den dönüş değeri tahmin edilemez. `timeptr`Önceki bir [asctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md), [_gmtime_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)veya [localtime_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)çağrısıyla döndürülen bir TM yapısına işaret ediyorsa, `tm_isdst` alan doğru değeri içerir.

Eşlik eden bir sınıf olan [CTimeSpan](../../atl-mfc-shared/reference/ctimespan-class.md), bir zaman aralığını temsil eder.

`CTime`Ve `CTimeSpan` sınıfları türetme için tasarlanmamıştır. Sanal işlev olmadığından, `CTime` ve `CTimeSpan` nesnelerinin boyutu tam olarak 8 bayttır. Çoğu üye işlevleri satır içidir.

> [!NOTE]
> Üst tarih sınırı 12/31/3000 ' dir. Alt sınır 1/1/1970 12:00:00 GMT 'dir.

Kullanma hakkında daha fazla bilgi için `CTime` , Run-Time kitaplığı başvurusunda makaleleri [Tarih ve saat](../../atl-mfc-shared/date-and-time.md)ve [zaman yönetimi](../../c-runtime-library/time-management.md) bölümüne bakın.

> [!NOTE]
> `CTime`Yapı mfc 7,1 ' den mfc 8,0 ' ye değişti. `CTime`Mfc 8,0 veya sonraki bir sürümde **işleç <<** kullanarak bir yapıyı seri hale getirmek istiyorsanız, sonuçta elde edilen dosya daha eski MFC sürümlerinde okunabilir olmayacaktır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

## <a name="ctime-comparison-operators"></a><a name="ctime_comparison_operators"></a> CTime karşılaştırma Işleçleri

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
`CTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu işleçler iki mutlak kez karşılaştırıp koşulun true olması durumunda TRUE değerini döndürür; Aksi halde yanlış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#161](../../atl-mfc-shared/codesnippet/cpp/ctime-class_1.cpp)]

## <a name="ctimectime"></a><a name="ctime"></a> CTime:: CTime

`CTime`Belirtilen saat ile başlatılan yeni bir nesne oluşturur.

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
`CTime`Zaten var olan bir nesneyi gösterir.

*ışınızda*<br/>
`__time64_t`1 ocak 1970 utc 'den sonraki saniye sayısı olan saat değeri. Bu, yerel zaman olarak ayarlanacağını unutmayın. Örneğin, New York 'taysa ve `CTime` 0 parametresini geçirerek bir nesne oluşturuyorsanız, [CTime:: GetMonth](#getmonth) , 12 döndürür.

*nYear*, *nmonth*, *nday*, *nhour*, *nMin*, *NSEC*<br/>
Yeni nesneye kopyalanacak tarih ve saat değerlerini gösterir `CTime` .

*nDST*<br/>
Gün ışığından yararlanma saatinin etkin olup olmadığını gösterir. Üç değerden birine sahip olabilir:

- *nDST* , 0Standart zaman olarak ayarlanmıştır.

- *nDST* , 0 ' dan büyük bir değere ayarlandığında gün ışığından yararlanma süresinden fazla olur.

- *nDST* , 0 ' dan küçük bir değere ayarlanır. Standart saat veya yaz tasarrufu süresinin etkin olup olmadığını otomatik olarak hesaplar.

*Wdosdate*, *wdostime*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni nesneye kopyalandığı MS-DOS tarih ve saat değerleri `CTime` .

*oluşan*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni nesneye kopyaladığınız bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısı `CTime` .

*meniz*<br/>
Bir tarih/saat değerine dönüştürülecek ve yeni nesneye kopyaladığınız bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı `CTime` .

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="remarks"></a>Açıklamalar

Her Oluşturucu aşağıda açıklanmıştır:

- `CTime();` Başlatılmamış bir `CTime` nesne oluşturur. Bu Oluşturucu, `CTime` nesne dizilerini tanımlamanızı sağlar. Kullanmadan önce bu tür dizileri geçerli saatlere başlatmalısınız.

- `CTime( const CTime& );` Başka bir `CTime` değerden bir nesne oluşturur `CTime` .

- `CTime( __time64_t );``CTime` **__Time64_t** türünden bir nesne oluşturur. Bu Oluşturucu bir UTC saati bekler ve sonucu depolamadan önce sonucu yerel saate dönüştürür.

- `CTime( int, int, ...);``CTime`Her bileşeni aşağıdaki aralıklar için kısıtlanmış yerel saat bileşenlerinden bir nesne oluşturur:

   |Bileşen|Aralık|
   |---------------|-----------|
   |*Nyıl*|1970-3000|
   |*Nay*|1-12|
   |*nHatalı*|1-31|
   |*Ngünün saati*|0-23|
   |*Ngünde en az*|0-59|
   |*nSec*|0-59|

   Bu Oluşturucu UTC 'ye uygun dönüştürme yapar. Microsoft Foundation Class Kitaplığı hata ayıklama sürümü, bir veya daha fazla zaman bileşeni Aralık dışında olduğunda onay onaylar. Çağrılmadan önce bağımsız değişkenleri doğrulamanız gerekir. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( WORD, WORD );``CTime`Belirtilen MS-DOS tarih ve saat değerlerinden bir nesne oluşturur. Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const SYSTEMTIME& );` Yapıdan bir `CTime` nesne oluşturur `SYSTEMTIME` . Bu Oluşturucu yerel bir saat bekliyor.

- `CTime( const FILETIME& );` Yapıdan bir `CTime` nesne oluşturur `FILETIME` . En büyük olasılıkla başlatmayı doğrudan kullanamayacaksınız `CTime FILETIME` . Bir `CFile` dosyayı işlemek için bir nesnesi kullanırsanız, bir `CFile::GetStatus` yapıyla başlatılan bir nesne aracılığıyla sizin için dosya zaman damgasını alır `CTime` `FILETIME` . Bu Oluşturucu UTC 'yi temel alan bir zaman varsayar ve sonucu depolamadan önce değeri otomatik olarak yerel saate dönüştürür.

   > [!NOTE]
   > Parametresi kullanılarak Oluşturucu `DBTIMESTAMP` yalnızca OLEDB. h dahil edildiğinde kullanılabilir.

Daha fazla bilgi için Windows SDK [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) ve [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısına bakın. Ayrıca Windows SDK [MS-DOS tarih ve saat](/windows/win32/SysInfo/ms-dos-date-and-time) girdisine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#148](../../atl-mfc-shared/codesnippet/cpp/ctime-class_2.cpp)]

## <a name="ctimeformat"></a><a name="format"></a> CTime:: biçim

Tarih-saat değerinin biçimli bir gösterimini oluşturmak için bu üye işlevini çağırın.

```
CString Format(LPCTSTR pszFormat) const;
CString Format(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçimlendirme dizesine benzer bir biçimlendirme dizesi `printf` . Bir yüzde ( `%` ) işaretinden önce gelen biçimlendirme kodları ilgili `CTime` bileşenle değiştirilmiştir. Biçimlendirme dizesindeki diğer karakterler, döndürülen dizeye değiştirilmeden kopyalanır. Biçimlendirme kodlarının listesi için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilen saati içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Bu `CTime` nesnenin durumu null ise, dönüş değeri boş bir dizedir.

Bu yöntem, biçimlendirme tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000, Evrensel Eşgüdümlü saat (UTC) arasında değilse bir özel durum oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#149](../../atl-mfc-shared/codesnippet/cpp/ctime-class_3.cpp)]

## <a name="ctimeformatgmt"></a><a name="formatgmt"></a> CTime:: FormatGmt

Bu nesneye karşılık gelen biçimli bir dize oluşturur `CTime` .

```
CString FormatGmt(LPCTSTR pszFormat) const;
CString FormatGmt(UINT nFormatID) const;
```

### <a name="parameters"></a>Parametreler

*pszFormat*<br/>
Biçimlendirme dizesine benzer bir biçimlendirme dizesi belirtir `printf` . Ayrıntılar için bkz. çalışma zamanı işlevi [strftime](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md) .

*nFormatID*<br/>
Bu biçimi tanımlayan dizenin KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirilen saati içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Zaman değeri dönüştürülmez ve bu nedenle UTC 'yi yansıtır.

Bu yöntem, biçimlendirme tarih-saat değeri gece yarısı, 1 Ocak 1970 ile 31 Aralık 3000, Evrensel Eşgüdümlü saat (UTC) arasında değilse bir özel durum oluşturur.

### <a name="example"></a>Örnek

[CTime:: Format](#format)örneğine bakın.

## <a name="ctimegetasdbtimestamp"></a><a name="getasdbtimestamp"></a> CTime:: GetAsDBTIMESTAMP

Nesnesinde depolanan zaman bilgilerini `CTime` Win32 ile uyumlu bır DBTIMESTAMP yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsDBTIMESTAMP(DBTIMESTAMP& dbts) const throw();
```

### <a name="parameters"></a>Parametreler

*dbts 'ler*<br/>
Geçerli yerel saati içeren bir DBTIMESTAMP yapısına başvuru.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Elde edilen süreyi başvurulan *dbts* yapısına depolar. `DBTIMESTAMP`Bu işlev tarafından başlatılan veri yapısının `fraction` üyesi sıfıra ayarlanmış olacak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#150](../../atl-mfc-shared/codesnippet/cpp/ctime-class_4.cpp)]

## <a name="ctimegetassystemtime"></a><a name="getassystemtime"></a> CTime:: GetAsSystemTime

Nesnesinde depolanan zaman bilgilerini `CTime` Win32 ile uyumlu bir [sistem zaman](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına dönüştürmek için bu üye işlevi çağırın.

```
bool GetAsSystemTime(SYSTEMTIME& st) const throw();
```

### <a name="parameters"></a>Parametreler

*timeDest*<br/>
Nesnenin dönüştürülmüş tarih/saat değerini tutan bir [SystemTime](/windows/win32/api/minwinbase/ns-minwinbase-systemtime) yapısına başvuru `CTime` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

`GetAsSystemTime` elde edilen süreyi başvurulan *timeDest* yapısına depolar. `SYSTEMTIME`Bu işlev tarafından başlatılan veri yapısının `wMilliseconds` üyesi sıfıra ayarlanmış olacak.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#151](../../atl-mfc-shared/codesnippet/cpp/ctime-class_5.cpp)]

## <a name="ctimegetcurrenttime"></a><a name="getcurrenttime"></a> CTime:: GetCurrentTime

`CTime`Geçerli saati temsil eden bir nesne döndürür.

```
static CTime WINAPI GetCurrentTime() throw();
```

### <a name="remarks"></a>Açıklamalar

Geçerli sistem tarihini ve saati Eşgüdümlü Evrensel Saat (UTC) olarak döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#152](../../atl-mfc-shared/codesnippet/cpp/ctime-class_6.cpp)]

## <a name="ctimegetday"></a><a name="getday"></a> CTime:: GetDay

Nesnenin gösterdiği günü döndürür `CTime` .

```
int GetDay() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ile 31 aralığında yerel saate göre ayın gününü döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili ve statik olarak ayrılmış bir arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#153](../../atl-mfc-shared/codesnippet/cpp/ctime-class_7.cpp)]

## <a name="ctimegetdayofweek"></a><a name="getdayofweek"></a> CTime:: GetDayOfWeek

Nesnenin gösterdiği haftanın gününü döndürür `CTime` .

```
int GetDayOfWeek() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Haftanın gününü yerel saate göre döndürür; 1 = Pazar, 2 = Pazartesi, 7 = Cumartesi.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#154](../../atl-mfc-shared/codesnippet/cpp/ctime-class_8.cpp)]

## <a name="ctimegetgmttm"></a><a name="getgmttm"></a> CTime:: Getgmttd

Bu nesnede bulunan sürenin ayrışanı içeren bir **struct tm** alır `CTime` .

```
struct tm* GetGmtTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

Dosya ekleme saatı. H içinde tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Yapı düzeni için bkz. [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetGmtTm` UTC döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL tanımlamayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#155](../../atl-mfc-shared/codesnippet/cpp/ctime-class_9.cpp)]

## <a name="ctimegethour"></a><a name="gethour"></a> CTime:: GetHour

Nesnenin gösterdiği saati döndürür `CTime` .

```
int GetHour() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 0 ile 23 aralığındaki saati döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#156](../../atl-mfc-shared/codesnippet/cpp/ctime-class_10.cpp)]

## <a name="ctimegetlocaltm"></a><a name="getlocaltm"></a> CTime:: GetLocalTm

Bu nesnede bulunan sürenin ayrışanı içeren bir **struct tm** alır `CTime` .

```
struct tm* GetLocalTm(struct tm* ptm) const;
```

### <a name="parameters"></a>Parametreler

*PTM*<br/>
Zaman verisini alacak bir arabelleğe işaret eder. Bu işaretçi NULL ise bir özel durum oluşturulur.

### <a name="return-value"></a>Dönüş Değeri

Dosya ekleme saatı. H içinde tanımlanan bir doldurulmuş **Yapı TM** işaretçisi. Yapı düzeni için bkz. [gmtime, _gmtime32 _gmtime64](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md) .

### <a name="remarks"></a>Açıklamalar

`GetLocalTm` yerel saati döndürür.

*PTM* null olamaz. *PTM* 'nin dahili ve statik olarak ayrılan bir arabelleğin kullanılması gerektiğini BELIRTMEK için null olabilecek eski davranışa geri dönmek istiyorsanız, _SECURE_ATL tanımlamayın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#157](../../atl-mfc-shared/codesnippet/cpp/ctime-class_11.cpp)]

## <a name="ctimegetminute"></a><a name="getminute"></a> CTime:: GetMinute

Nesnenin temsil ettiği dakikayı döndürür `CTime` .

```
int GetMinute() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre dakikayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="ctimegetmonth"></a><a name="getmonth"></a> CTime:: GetMonth

Nesnenin temsil ettiği ayı döndürür `CTime` .

```
int GetMonth() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel saate göre, 1 ile 12 arasında (1 = Ocak) ayı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

## <a name="ctimegetsecond"></a><a name="getsecond"></a> CTime:: GetSecond

Nesne tarafından temsil edilen saniyeyi döndürür `CTime` .

```
int GetSecond() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

0 ile 59 aralığında yerel saate göre saniyeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[GetHour](#gethour)örneğine bakın.

## <a name="ctimegettime"></a><a name="gettime"></a> CTime:: GetTime

Verilen nesne için bir **__time64_t** değeri döndürür `CTime` .

```
__time64_t GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`GetTime` geçerli `CTime` nesne ve 1 ocak 1970 arasındaki saniye sayısını döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#158](../../atl-mfc-shared/codesnippet/cpp/ctime-class_12.cpp)]

## <a name="ctimegetyear"></a><a name="getyear"></a> CTime:: GetYear

Nesnenin temsil ettiği yılı döndürür `CTime` .

```
int GetYear();
```

### <a name="return-value"></a>Dönüş Değeri

1 Ocak 1970 aralığında, 18 Ocak 2038 (dahil) aralığında yerel saate göre yılı döndürür.

### <a name="remarks"></a>Açıklamalar

Bu işlev `GetLocalTm` , dahili bir statik olarak ayrılan arabellek kullanan çağırır. Diğer üye işlevlerine yapılan çağrılar nedeniyle bu arabellekteki verilerin üzerine yazılır `CTime` .

### <a name="example"></a>Örnek

[GetDay](#getday)örneğine bakın.

## <a name="ctimeoperator-"></a><a name="operator_eq"></a> CTime:: operator =

Atama işleci.

```
CTime& operator=(__time64_t time) throw();
```

### <a name="parameters"></a>Parametreler

*ışınızda*<br/>
Yeni tarih/saat değeri.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu aşırı yüklenmiş atama işleci, kaynak saatini bu `CTime` nesneye kopyalar. Bir nesnedeki iç zaman depolama alanı `CTime` saat diliminden bağımsızdır. Atama sırasında saat dilimi dönüştürmesi gerekli değildir.

## <a name="ctimeoperator---"></a><a name="operator_add_-"></a> CTime:: operator +,-

Bu işleçler ve nesneler ekler ve çıkarır `CTimeSpan` `CTime` .

```
CTime operator+(CTimeSpan timeSpan) const throw();
CTime operator-(CTimeSpan timeSpan) const throw();
CTimeSpan operator-(CTime time) const throw();
```

### <a name="parameters"></a>Parametreler

*timeSpan*<br/>
`CTimeSpan`Eklenecek veya çıkarılacak nesne.

*ışınızda*<br/>
`CTime`Çıkarılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

`CTime` `CTimeSpan` İşlemin sonucunu temsil eden bir veya nesnesi.

### <a name="remarks"></a>Açıklamalar

`CTime` nesneler mutlak süreyi temsil eder, `CTimeSpan` nesneler göreli süreyi temsil eder. İlk iki operatör `CTimeSpan` nesneleri nesnelerine ve nesnelerden nesneleri eklemenize ve bunlara çıkareklemenize olanak tanır `CTime` . Üçüncü işleç bir nesneyi başka bir nesneden çıkartabilir olanak sağlar `CTime` `CTimeSpan` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#159](../../atl-mfc-shared/codesnippet/cpp/ctime-class_13.cpp)]

## <a name="ctimeoperator---"></a><a name="operator_add_eq_-_eq"></a> CTime:: operator + =,-=

Bu işleçler, nesnesine ve nesnesinden bir nesne ekler ve çıkarır `CTimeSpan` `CTime` .

```
CTime& operator+=(CTimeSpan span) throw();
CTime& operator-=(CTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
`CTimeSpan`Eklenecek veya çıkarılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CTime` nesne.

### <a name="remarks"></a>Açıklamalar

Bu işleçler, bu nesneye ve nesnesinden bir nesne eklemenize ve çıkartabilir `CTimeSpan` `CTime` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATLMFC_Utilities#160](../../atl-mfc-shared/codesnippet/cpp/ctime-class_14.cpp)]

## <a name="ctimeserialize64"></a><a name="serialize64"></a> CTime:: Serialize64

> [!NOTE]
> Bu yöntem yalnızca MFC projelerinde kullanılabilir.

Üye değişkeniyle ilişkili verileri bir arşivden veya bir arşive serileştirir.

```
CArchive& Serialize64(CArchive& ar);
```

### <a name="parameters"></a>Parametreler

*Ar*<br/>
`CArchive`Güncelleştirmek istediğiniz nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CArchive` nesne.

## <a name="see-also"></a>Ayrıca bkz.

[asctime_s, _wasctime_s](../../c-runtime-library/reference/asctime-s-wasctime-s.md)<br/>
[_ftime_s, _ftime32_s, _ftime64_s](../../c-runtime-library/reference/ftime-s-ftime32-s-ftime64-s.md)<br/>
[gmtime_s, _gmtime32_s, _gmtime64_s](../../c-runtime-library/reference/gmtime-s-gmtime32-s-gmtime64-s.md)<br/>
[localtime_s, _localtime32_s, _localtime64_s](../../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](../../c-runtime-library/reference/strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)<br/>
[CTimeSpan sınıfı](../../atl-mfc-shared/reference/ctimespan-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
