---
title: CFileTime Sınıfı
ms.date: 10/18/2018
f1_keywords:
- CFileTime
- ATLTIME/ATL::CFileTime
- ATLTIME/ATL::CFileTime::CFileTime
- ATLTIME/ATL::CFileTime::GetCurrentTime
- ATLTIME/ATL::CFileTime::GetTime
- ATLTIME/ATL::CFileTime::LocalToUTC
- ATLTIME/ATL::CFileTime::SetTime
- ATLTIME/ATL::CFileTime::UTCToLocal
- ATLTIME/ATL::CFileTime::Day
- ATLTIME/ATL::CFileTime::Hour
- ATLTIME/ATL::CFileTime::Millisecond
- ATLTIME/ATL::CFileTime::Minute
- ATLTIME/ATL::CFileTime::Second
- ATLTIME/ATL::CFileTime::Week
helpviewer_keywords:
- CFileTime class
- shared classes, CFileTime
ms.assetid: 1a358a65-1383-4124-b0d4-59b026e6860f
ms.openlocfilehash: fd19d941365c7772363417ce3e9225bd9b0300b2
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748847"
---
# <a name="cfiletime-class"></a>CFileTime Sınıfı

Bu sınıf, bir dosyayla ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Geçerli sistem tarih ve `CFileTime` saatini temsil eden bir nesneyi almak için bu statik işlevi çağırın.|
|[CFileTime::GetTime](#gettime)|Nesneyden zamanı almak için `CFileTime` bu yöntemi çağırın.|
|[CfileTime::LocalToUTC](#localtoutc)|Yerel bir dosya saatini Eşgüdümlü Evrensel Zaman'ı (UTC) temel alan bir dosya zamanına dönüştürmek için bu yöntemi çağırın.|
|[CFileTime::SetTime](#settime)|`CFileTime` Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi arayın.|
|[CfileTime::UTCToLocal](#utctolocal)|Eşgüdümlü Evrensel Saate (UTC) dayalı zamanı yerel dosya saatine dönüştürmek için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CFileTime::operatör -](#operator_-)|Bu işleç bir `CFileTime` veya `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek için kullanılır.|
|[CFileTime::operatör !=](#operator_neq)|Bu işleç `CFileTime` eşitsizlik için iki nesneyi karşılaştırır.|
|[CFileTime::operatör +](#operator_add)|Bu işleç bir `CFileTimeSpan` nesneye ekleme gerçekleştirmek için kullanılır.|
|[CFileTime::operatör +=](#operator_add_eq)|Bu işleç bir `CFileTimeSpan` nesneye ekleme gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime::operatör&lt;](#operator_lt)|Bu işleç `CFileTime` daha az belirlemek için iki nesne karşılaştırır.|
|[CFileTime::operatör&lt;=](#operator_lt_eq)|Bu işleç `CFileTime` eşitliği veya daha az ını belirlemek için iki nesneyi karşılaştırır.|
|[CFileTime::operator =](#operator_eq)|Atama işleci.|
|[CFileTime::operatör -=](#operator_-_eq)|Bu işleç bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime::operatör ==](#operator_eq_eq)|Bu işleç `CFileTime` eşitlik için iki nesneyi karşılaştırır.|
|[CFileTime::operatör&gt;](#operator_gt)|Bu işleç `CFileTime` büyük belirlemek için iki nesne karşılaştırır.|
|[CFileTime::operatör&gt;=](#operator_gt_eq)|Bu işleç `CFileTime` eşitliği veya daha büyük belirlemek için iki nesneyi karşılaştırır.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[CFileTime::Day](#day)|Bir günü oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|
|[CFileTime::Saat](#hour)|Bir saati oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|
|[CFileTime::Milisaniye](#millisecond)|Bir milisaniyeyi oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|
|[CFileTime::Dakika](#minute)|Bir dakikayı oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|
|[CFileTime::İkinci](#second)|Bir saniyeyi oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|
|[CFileTime::Hafta](#week)|Bir haftayı oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dosyaların oluşturulması, erişimi ve değiştirilmesiyle ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar. Bu sınıfın yöntemleri ve verileri sık sık `CFileTimeSpan` göreli zaman değerleri ile anlaşma nesneleri ile birlikte kullanılır.

Tarih ve saat değeri, 1 Ocak 1601'den bu yana 100 nanosaniyelik aralıksayısını temsil eden 64 bitlik bir değer olarak depolanır. Bu, Eşgüdümlü Evrensel Zaman (UTC) biçimidir.

Hesaplamaları basitleştirmek için aşağıdaki statik const üye değişkenler sağlanır:

|Üye değişkeni|100 nanosaniyelik aralıksayısı|
|---------------------|-----------------------------------------|
|Milisaniye|10,000|
|Saniye|Milisaniye \* 1.000|
|Dakika|İkinci \* 60|
|Saat|Dakika \* 60|
|Gün|Saat \* 24|
|Hafta|7. Gün \*|

**Not** Tüm dosya sistemleri oluşturma ve son erişim süresini kaydedemez ve tüm dosya sistemleri bunları aynı şekilde kaydedemez. Örneğin, Windows NT FAT dosya sisteminde, zaman oluşturmak 10 milisaniye çözünürlüğe sahiptir, yazma süresi 2 saniye çözünürlüğe sahiptir ve erişim süresi 1 günlük bir çözünürlüğe sahiptir (erişim tarihi). NTFS'de erişim süresi 1 saatlik bir çözünürlüğe sahiptir. Ayrıca, FAT yerel saatle diskte süreleri kaydeder, ancak NTFS süreleri UTC'deki diskte kaydeder. Daha fazla bilgi için [Dosya Zamanları'na](/windows/win32/SysInfo/file-times)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime.h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a>CFileTime::CFileTime

Oluşturucu.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Bir [FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı.

*nZaman*<br/>
64 bit değer olarak ifade edilen tarih ve saat.

### <a name="remarks"></a>Açıklamalar

Nesne, `CFileTime` bir `FILETIME` yapıdan varolan bir tarih ve saat kullanılarak oluşturulabilir veya 64 bit lik bir değer olarak ifade edilebilir (yerel veya Eşgüdümlü Evrensel Saat (UTC) zaman biçimlerinde). Varsayılan oluşturucu zamanı 0 olarak ayarlar.

## <a name="cfiletimeday"></a><a name="day"></a>CFileTime::Day

Bir günü oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](#millisecond).

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a>CFileTime::GetCurrentTime

Geçerli sistem tarih ve `CFileTime` saatini temsil eden bir nesneyi almak için bu statik işlevi çağırın.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli sistem tarih ve saatini Eşgüdümlü Evrensel Saat (UTC) biçiminde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a>CFileTime::GetTime

Nesneyden zamanı almak için `CFileTime` bu yöntemi çağırın.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde olabilecek 64 bitlik bir sayı olarak tarih ve saati döndürür.

## <a name="cfiletimehour"></a><a name="hour"></a>CFileTime::Saat

Bir saati oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](#millisecond).

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a>CfileTime::LocalToUTC

Yerel bir dosya saatini Eşgüdümlü Evrensel Zaman'ı (UTC) temel alan bir dosya zamanına dönüştürmek için bu yöntemi çağırın.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

UTC `CFileTime` formatında zamanı içeren bir nesne döndürür.

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:UTCToLocal.](#utctolocal)

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a>CFileTime::Milisaniye

Bir milisaniyeyi oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a>CFileTime::Dakika

Bir dakikayı oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](#millisecond).

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a>CFileTime::operatör -

Bu işleç bir `CFileTime` veya `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek için kullanılır.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
Bir `CFileTimeSpan` nesnesi.

*Ft*<br/>
Bir `CFileTime` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İki `CFileTime` nesne arasındaki `CFileTimeSpan` saat farkının sonucunu temsil eden bir nesne veya nesne döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a>CFileTime::operatör !=

Bu işleç `CFileTime` eşitsizlik için iki nesneyi karşılaştırır.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CFileTime` nesneye eşit değilse TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a>CFileTime::operatör +

Bu işleç bir `CFileTimeSpan` nesneye ekleme gerçekleştirmek için kullanılır.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Özgün `CFileTime` zamanın sonucunu ve göreceli zamanı temsil eden bir nesne döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a>CFileTime::operatör +=

Bu işleç bir `CFileTimeSpan` nesneye ekleme gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Özgün zaman `CFileTime` ve göreceli bir zaman sonucunu temsil eden güncelleştirilmiş nesneyi döndürür.

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a>CFileTime::operatör&lt;

Bu işleç `CFileTime` daha az belirlemek için iki nesne karşılaştırır.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden daha azsa (zaman içinde daha erken) ise TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a>CFileTime::operatör&lt;=

Bu işleç `CFileTime` eşitliği veya daha az ını belirlemek için iki nesneyi karşılaştırır.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (daha erken) veya ikinciye eşitse TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a>CFileTime::operator =

Atama işleci.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Yeni `CFileTime` saat ve tarih içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTime` nesneyi döndürür.

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a>CFileTime::operatör -=

Bu işleç bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*<br/>
Çıkarma `CFileTimeSpan` için göreli zaman içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTime` nesneyi döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a>CFileTime::operatör ==

Bu işleç `CFileTime` eşitlik için iki nesneyi karşılaştırır.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a>CFileTime::operatör&gt;

Bu işleç `CFileTime` büyük belirlemek için iki nesne karşılaştırır.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden (daha sonra) ikinciden daha büyükse TRUE'yu döndürür, aksi takdirde FALSE.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a>CFileTime::operatör&gt;=

Bu işleç `CFileTime` eşitliği veya daha büyük belirlemek için iki nesneyi karşılaştırır.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*Ft*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (daha sonra zaman içinde) veya ikinci, aksi takdirde FALSE eşit ise TRUE döndürür.

## <a name="cfiletimesecond"></a><a name="second"></a>CFileTime::İkinci

Bir günü oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](#millisecond).

## <a name="cfiletimesettime"></a><a name="settime"></a>CFileTime::SetTime

`CFileTime` Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi arayın.

```cpp
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
Yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde tarih ve saati temsil eden 64 bitlik değer.

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a>CfileTime::UTCToLocal

Eşgüdümlü Evrensel Saate (UTC) dayalı zamanı yerel dosya saatine dönüştürmek için bu yöntemi arayın.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel `CFileTime` dosya saati biçiminde saati içeren bir nesneyi döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a>CFileTime::Hafta

Bir haftayı oluşturan 100 nanosaniyelik aralıkların sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](#millisecond).

## <a name="see-also"></a>Ayrıca bkz.

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan Sınıfı](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
