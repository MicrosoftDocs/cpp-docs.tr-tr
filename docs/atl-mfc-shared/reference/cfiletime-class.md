---
title: CFileTime sınıfı
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
ms.openlocfilehash: 07b888b031a38dc2f09404a14e729e26b3eaa019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235139"
---
# <a name="cfiletime-class"></a>CFileTime sınıfı

Bu sınıf, bir dosya ile ilişkilendirilmiş tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime::CFileTime](#cfiletime)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime::GetCurrentTime](#getcurrenttime)|Alınacak statik bu işlevi çağırın bir `CFileTime` geçerli sistem tarihi ve saati temsil eden nesne.|
|[CFileTime::GetTime](#gettime)|Zamandan almak için bu yöntemi çağırın `CFileTime` nesne.|
|[CFileTime::LocalToUTC](#localtoutc)|Bir dosyanın dosya saati Eşgüdümlü Evrensel Saat (UTC) temel bir yerel dosya zamanı dönüştürmek için bu yöntemi çağırın.|
|[CFileTime::SetTime](#settime)|Tarih ve saat tarafından depolanan ayarlamak için bu yöntemi çağırın `CFileTime` nesne.|
|[CFileTime::UTCToLocal](#utctolocal)|Üzerinde Eşgüdümlü Evrensel Saat (UTC) yerel dosya zamana bağlı olarak zaman dönüştürmek için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime::operator-](#operator_-)|Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CFileTime` veya `CFileTimeSpan` nesne.|
|[CFileTime::operator! =](#operator_neq)|Bu işleç iki karşılaştırır `CFileTime` nesneleri için eşitsizlik.|
|[CFileTime::operator +](#operator_add)|Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne.|
|[CFileTime::operator +=](#operator_add_eq)|Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.|
|[CFileTime::operator &lt;](#operator_lt)|Bu işleç iki karşılaştırır `CFileTime` küçük olanı belirlemek için nesneleri.|
|[CFileTime::operator &lt;=](#operator_lt_eq)|Bu işleç iki karşılaştırır `CFileTime` eşitlik ya da küçük olanı belirlemek için nesneleri.|
|[CFileTime::operator =](#operator_eq)|Atama işleci.|
|[CFileTime::operator-=](#operator_-_eq)|Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.|
|[CFileTime::operator ==](#operator_eq_eq)|Bu işleç iki karşılaştırır `CFileTime` eşitlik için nesneleri.|
|[CFileTime::operator &gt;](#operator_gt)|Bu işleç iki karşılaştırır `CFileTime` büyük belirlemek için nesneleri.|
|[CFileTime::operator &gt;=](#operator_gt_eq)|Bu işleç iki karşılaştırır `CFileTime` eşitlik ya da daha büyük belirlemek için nesneleri.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime::Day](#day)|100 nanosaniyelik aralık sayısını depolama statik veri üyesine bir günlük olun.|
|[CFileTime::Hour](#hour)|Statik veri üyesine bir saat yapmak 100 nanosaniyelik aralık sayısını depolama.|
|[CFileTime::Millisecond](#millisecond)|Statik veri üyesine bir milisaniye yapmak 100 nanosaniyelik aralık sayısını depolama.|
|[CFileTime::Minute](#minute)|Statik veri üyesine bir dakika yapmak 100 nanosaniyelik aralık sayısını depolama.|
|[CFileTime::Second](#second)|Statik veri üyesine bir saniye yapmak 100 nanosaniyelik aralık sayısını depolama.|
|[CFileTime::Week](#week)|100 nanosaniyelik aralık sayısını depolama statik veri üyesine bir haftanın olun.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf oluşturma, erişim ve dosyaların değiştirilmesini ile ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar. Bu sınıfın veri ve yöntemler sık ile birlikte kullanılan `CFileTimeSpan` göreli zaman değerleri ile ilgili nesneler.

Tarih ve saat değerini, 1 Ocak 1601 bu yana 100 nano saniyelik aralıkların sayısını temsil eden 64-bit bir değer olarak depolanır. Eşgüdümlü Evrensel Saat (UTC) biçiminde budur.

Aşağıdaki statik const üye değişkenleri hesaplamaları basitleştirmek için sağlanır:

|Üye değişkeni|100 nanosaniyelik aralık sayısı|
|---------------------|-----------------------------------------|
|Milisaniye|10,000|
|Saniye|Milisaniye \* 1.000|
|Dakika|İkinci \* 60|
|Saat|Dakika \* 60|
|Gün|Saat \* 24|
|Hafta|Gün \* 7|

**Not** tüm dosya sistemleri oluşturma kaydedebilir ve son erişim zamanı ve tüm dosya sistemleri kayıt bunları aynı şekilde. Örneğin, Windows NT FAT dosya sistemi oluşturmak için süresi 10 milisaniyeden çözünürlüğü var, yazma süresi 2 saniyelik bir çözüm olan ve erişim süresi 1 gün (erişim tarihi), bir çözüm olan. 1 saatlik bir çözüm, NTFS erişim zamanı var. Ayrıca, FAT defa diskte yerel saatle kaydeder, ancak NTFS disk saatleri UTC biçiminde kaydeder. Daha fazla bilgi için [dosya zamanlarını](/windows/desktop/SysInfo/file-times).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltime.h

##  <a name="cfiletime"></a>  CFileTime::CFileTime

Oluşturucu.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
A [FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime) yapısı.

*nZaman*<br/>
Tarih ve saat 64-bit bir değer ifade edilir.

### <a name="remarks"></a>Açıklamalar

`CFileTime` Nesnesi, bir var olan bir tarih ve saat kullanarak oluşturulabilir bir `FILETIME` yapılandırdığınızı ya da bir 64-bit değeri (yerel veya Eşgüdümlü Evrensel Saat (UTC) saat biçimleri) olarak ifade edilir. Varsayılan Oluşturucu, zaman 0 olarak ayarlar.

##  <a name="day"></a>  CFileTime::Day

100 nanosaniyelik aralık sayısını depolama statik veri üyesine bir günlük olun.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](#millisecond).

##  <a name="getcurrenttime"></a>  CFileTime::GetCurrentTime

Alınacak statik bu işlevi çağırın bir `CFileTime` geçerli sistem tarihi ve saati temsil eden nesne.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

##  <a name="gettime"></a>  CFileTime::GetTime

Zamandan almak için bu yöntemi çağırın `CFileTime` nesne.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde veya yerel olabilir 64 bit bir sayı olarak döndürür.

##  <a name="hour"></a>  CFileTime::Hour

Statik veri üyesine bir saat yapmak 100 nanosaniyelik aralık sayısını depolama.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](#millisecond).

##  <a name="localtoutc"></a>  CFileTime::LocalToUTC

Bir dosyanın dosya saati Eşgüdümlü Evrensel Saat (UTC) temel bir yerel dosya zamanı dönüştürmek için bu yöntemi çağırın.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTime` saati UTC biçiminde içeren nesne.

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::UTCToLocal](#utctolocal).

##  <a name="millisecond"></a>  CFileTime::Millisecond

Statik veri üyesine bir milisaniye yapmak 100 nanosaniyelik aralık sayısını depolama.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

##  <a name="minute"></a>  CFileTime::Minute

Statik veri üyesine bir dakika yapmak 100 nanosaniyelik aralık sayısını depolama.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](#millisecond).

##  <a name="operator_-"></a>  CFileTime::operator-

Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CFileTime` veya `CFileTimeSpan` nesne.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*span*<br/>
A `CFileTimeSpan` nesne.

*ft*<br/>
A `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTime` nesnesi veya bir `CFileTimeSpan` iki nesne arasındaki zaman farkı sonucunu temsil eden nesne.

##  <a name="operator_neq"></a>  CFileTime::operator! =

Bu işleç iki karşılaştırır `CFileTime` nesneleri için eşitsizlik.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğesi eşit değilse TRUE döndürür `CFileTime` nesnesi, aksi takdirde FALSE.

##  <a name="operator_add"></a>  CFileTime::operator +

Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*span*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTime` özgün saati artı göreli zaman sonucunu temsil eden nesne.

##  <a name="operator_add_eq"></a>  CFileTime::operator +=

Bu işleç ayrıca gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*span*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTime` özgün saati artı göreli zaman sonucunu temsil eden nesne.

##  <a name="operator_lt"></a>  CFileTime::operator &lt;

Bu işleç iki karşılaştırır `CFileTime` küçük olanı belirlemek için nesneleri.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin ikinci değerinden küçük (daha önce zaman içinde) değilse FALSE değerini TRUE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

##  <a name="operator_lt_eq"></a>  CFileTime::operator &lt;=

Bu işleç iki karşılaştırır `CFileTime` eşitlik ya da küçük olanı belirlemek için nesneleri.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin (zaman içinde önceki) daha az veya ona eşit, ikincisi ise TRUE döndürür Aksi durumda FALSE.

##  <a name="operator_eq"></a>  CFileTime::operator =

Atama işleci.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
A `CFileTime` yeni saat ve tarihi içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTime` nesne.

##  <a name="operator_-_eq"></a>  CFileTime::operator-=

Bu işleç çıkarma gerçekleştirmek için kullanılan bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*span*<br/>
A `CFileTimeSpan` çıkarılacak göreli zaman içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTime` nesne.

##  <a name="operator_eq_eq"></a>  CFileTime::operator ==

Bu işleç iki karşılaştırır `CFileTime` eşitlik için nesneleri.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşit, aksi durumda FALSE ise true değeri döndürür.

##  <a name="operator_gt"></a>  CFileTime::operator &gt;

Bu işleç iki karşılaştırır `CFileTime` büyük belirlemek için nesneleri.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin (daha sonra zaman içinde) büyükse TRUE döndürür ikinciden, aksi takdirde FALSE.

##  <a name="operator_gt_eq"></a>  CFileTime::operator &gt;=

Bu işleç iki karşılaştırır `CFileTime` eşitlik ya da daha büyük belirlemek için nesneleri.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*ft*<br/>
`CFileTime` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin (daha sonra zaman içinde) büyüktür veya eşittir, ikinci ise TRUE döndürür Aksi durumda FALSE.

##  <a name="second"></a>  CFileTime::Second

100 nanosaniyelik aralık sayısını depolama statik veri üyesine bir günlük olun.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](#millisecond).

##  <a name="settime"></a>  CFileTime::SetTime

Tarih ve saat tarafından depolanan ayarlamak için bu yöntemi çağırın `CFileTime` nesne.

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
Tarih ve saat, yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde temsil eden 64-bit değeri.

##  <a name="utctolocal"></a>  CFileTime::UTCToLocal

Üzerinde Eşgüdümlü Evrensel Saat (UTC) yerel dosya zamana bağlı olarak zaman dönüştürmek için bu yöntemi çağırın.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTime` yerel dosya saat biçiminde saati içeren bir nesne.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

##  <a name="week"></a>  CFileTime::Week

100 nanosaniyelik aralık sayısını depolama statik veri üyesine bir haftanın olun.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](#millisecond).

## <a name="see-also"></a>Ayrıca bkz.

[FILETIME](/windows/desktop/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan Sınıfı](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
