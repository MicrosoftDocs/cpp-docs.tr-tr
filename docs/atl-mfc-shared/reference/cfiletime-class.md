---
description: 'Daha fazla bilgi edinin: CFileTime sınıfı'
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
ms.openlocfilehash: 95b46c188be60da787612a30ebff161a4ecf5966
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166856"
---
# <a name="cfiletime-class"></a>CFileTime sınıfı

Bu sınıf, bir dosyayla ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Syntax

```
class CFileTime :  public FILETIME
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime:: CFileTime](#cfiletime)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime:: GetCurrentTime](#getcurrenttime)|`CFileTime`Geçerli sistem tarihini ve saatini temsil eden bir nesne almak için bu statik işlevi çağırın.|
|[CFileTime:: GetTime](#gettime)|Nesneden saati almak için bu yöntemi çağırın `CFileTime` .|
|[CFileTime:: LocalToUTC](#localtoutc)|Yerel bir dosya saatini Eşgüdümlü Evrensel Saat (UTC) temelinde bir dosya saatine dönüştürmek için bu yöntemi çağırın.|
|[CFileTime:: SetTime](#settime)|Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi çağırın `CFileTime` .|
|[CFileTime:: UTCToLocal](#utctolocal)|Eşgüdümlü Evrensel Saat (UTC) temelinde yerel dosya zamanına göre saati dönüştürmek için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime:: operator-](#operator_-)|Bu işleç, bir veya nesnesi üzerinde çıkarma gerçekleştirmek için kullanılır `CFileTime` `CFileTimeSpan` .|
|[CFileTime:: operator! =](#operator_neq)|Bu işleç, `CFileTime` eşitsizlik için iki nesneyi karşılaştırır.|
|[CFileTime:: operator +](#operator_add)|Bu işleç, bir nesnesine ekleme yapmak için kullanılır `CFileTimeSpan` .|
|[CFileTime:: operator + =](#operator_add_eq)|Bu işleç, bir nesnesine ekleme yapmak `CFileTimeSpan` ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime:: işleci &lt;](#operator_lt)|Bu işleç, daha `CFileTime` az anlamak için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci &lt;=](#operator_lt_eq)|Bu işleç `CFileTime` , eşitlik veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|
|[CFileTime:: operator =](#operator_eq)|Atama işleci.|
|[CFileTime:: operator-=](#operator_-_eq)|Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek `CFileTimeSpan` ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime:: operator = =](#operator_eq_eq)|Bu işleç, `CFileTime` eşitlik için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci &gt;](#operator_gt)|Bu işleç `CFileTime` , daha büyük olduğunu anlamak için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci &gt;=](#operator_gt_eq)|Bu işleç `CFileTime` , eşitlik veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime::D ay](#day)|Bir gün oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|
|[CFileTime:: Saat](#hour)|Bir saat oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|
|[CFileTime:: milisaniyelik](#millisecond)|Bir milisaniyelik oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|
|[CFileTime:: dakika](#minute)|Bir dakika oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|
|[CFileTime:: Second](#second)|Bir saniye oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|
|[CFileTime:: Week](#week)|Bir hafta oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, dosya oluşturma, erişim ve değiştirme ile ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar. Bu sınıfın yöntemleri ve verileri, genellikle `CFileTimeSpan` göreli zaman değerleriyle ilgilenen nesneler ile birlikte kullanılır.

Tarih ve saat değeri, 1 Ocak 1601 ' den bu yana 100-nanosaniyelik aralıklarının sayısını temsil eden 64 bitlik bir değer olarak depolanır. Bu Eşgüdümlü Evrensel Saat (UTC) biçimidir.

Hesaplamaları basitleştirmek için aşağıdaki statik const üye değişkenleri verilmiştir:

|Üye değişkeni|100-nanosaniyelik aralıklarının sayısı|
|---------------------|-----------------------------------------|
|Milisaniy|10,000|
|Second|Milisaniyelik \* 1.000|
|Dakika|İkinci \* 60|
|Saat|Dakika \* 60|
|Gün|Saat \* 24|
|Hafta|Gün \* 7|

**Göz önünde** Tüm dosya sistemleri, oluşturma ve son erişim süresini kaydedebilir ve tüm dosya sistemleri aynı şekilde kayıt yapabilir. Örneğin, Windows NT FAT dosya sisteminde, oluşturma süresi 10 milisaniyelik bir çözünürlüğe sahiptir, yazma zamanı 2 saniye çözünürlüğe sahiptir ve erişim süresi 1 günlük çözünürlüğe sahiptir (erişim tarihi). NTFS 'de, erişim süresinin 1 saat çözünürlüğü vardır. Ayrıca, FAT yerel saate göre diskler halinde kayıt kaydeder, ancak NTFS ise diskte UTC olarak saat kaydeder. Daha fazla bilgi için bkz. [Dosya süreleri](/windows/win32/SysInfo/file-times).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FILETIME`

`CFileTime`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

## <a name="cfiletimecfiletime"></a><a name="cfiletime"></a> CFileTime:: CFileTime

Oluşturucu.

```
CFileTime() throw();
CFileTime(const FILETIME& ft) throw();
CFileTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Bir [filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime) yapısı.

*nZaman*<br/>
64 bitlik bir değer olarak ifade edilen tarih ve saat.

### <a name="remarks"></a>Açıklamalar

`CFileTime`Nesne, bir yapıdan mevcut bir tarih ve saat kullanılarak `FILETIME` veya 64 bitlik bir değer (yerel veya Eşgüdümlü Evrensel Saat (UTC) saat biçimlerinde) olarak ifade edilebilir. Varsayılan Oluşturucu saati 0 olarak ayarlar.

## <a name="cfiletimeday"></a><a name="day"></a> CFileTime::D ay

Bir gün oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="cfiletimegetcurrenttime"></a><a name="getcurrenttime"></a> CFileTime:: GetCurrentTime

`CFileTime`Geçerli sistem tarihini ve saatini temsil eden bir nesne almak için bu statik işlevi çağırın.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

## <a name="cfiletimegettime"></a><a name="gettime"></a> CFileTime:: GetTime

Nesneden saati almak için bu yöntemi çağırın `CFileTime` .

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saati 64 bitlik bir sayı olarak döndürür. Bu, yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde olabilir.

## <a name="cfiletimehour"></a><a name="hour"></a> CFileTime:: Saat

Bir saat oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="cfiletimelocaltoutc"></a><a name="localtoutc"></a> CFileTime:: LocalToUTC

Yerel bir dosya saatini Eşgüdümlü Evrensel Saat (UTC) temelinde bir dosya saatine dönüştürmek için bu yöntemi çağırın.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CFileTime`Saatı UTC biçiminde içeren bir nesne döndürür.

### <a name="example"></a>Örnek

[CFileTime:: UTCToLocal](#utctolocal)örneğine bakın.

## <a name="cfiletimemillisecond"></a><a name="millisecond"></a> CFileTime:: milisaniyelik

Bir milisaniyelik oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

## <a name="cfiletimeminute"></a><a name="minute"></a> CFileTime:: dakika

Bir dakika oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="cfiletimeoperator--"></a><a name="operator_-"></a> CFileTime:: operator-

Bu işleç, bir veya nesnesi üzerinde çıkarma gerçekleştirmek için kullanılır `CFileTime` `CFileTimeSpan` .

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Bir `CFileTimeSpan` nesnesi.

*meniz*<br/>
Bir `CFileTime` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İki nesne `CFileTime` `CFileTimeSpan` arasındaki zaman farkının sonucunu temsil eden bir nesne veya nesne döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_neq"></a> CFileTime:: operator! =

Bu işleç, `CFileTime` eşitsizlik için iki nesneyi karşılaştırır.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe nesneye eşitse TRUE `CFileTime` , DEĞILSE false döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_add"></a> CFileTime:: operator +

Bu işleç, bir nesnesine ekleme yapmak için kullanılır `CFileTimeSpan` .

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`CFileTime`Özgün zamanın sonucunu ve göreli bir süreyi temsil eden bir nesne döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_add_eq"></a> CFileTime:: operator + =

Bu işleç, bir nesnesine ekleme yapmak `CFileTimeSpan` ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

`CFileTime`Orijinal saatin sonucunu ve göreli bir süreyi temsil eden güncelleştirilmiş nesneyi döndürür.

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt"></a> CFileTime:: işleci &lt;

Bu işleç, daha `CFileTime` az anlamak için iki nesneyi karşılaştırır.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

## <a name="cfiletimeoperator-lt"></a><a name="operator_lt_eq"></a> CFileTime:: işleci &lt;=

Bu işleç `CFileTime` , eşitlik veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (zaman içinde daha önce) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

## <a name="cfiletimeoperator-"></a><a name="operator_eq"></a> CFileTime:: operator =

Atama işleci.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Yeni saat ve tarihi içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CFileTime` .

## <a name="cfiletimeoperator--"></a><a name="operator_-_eq"></a> CFileTime:: operator-=

Bu işleç, bir nesne üzerinde çıkarma gerçekleştirmek `CFileTimeSpan` ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
`CFileTimeSpan`Çıkarmak için göreli süreyi içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CFileTime` .

## <a name="cfiletimeoperator-"></a><a name="operator_eq_eq"></a> CFileTime:: operator = =

Bu işleç, `CFileTime` eşitlik için iki nesneyi karşılaştırır.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE, değilse FALSE döndürür.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt"></a> CFileTime:: işleci &gt;

Bu işleç `CFileTime` , daha büyük olduğunu anlamak için iki nesneyi karşılaştırır.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyükse TRUE, değilse FALSE döndürür.

## <a name="cfiletimeoperator-gt"></a><a name="operator_gt_eq"></a> CFileTime:: işleci &gt;=

Bu işleç `CFileTime` , eşitlik veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
`CFileTime`Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (daha sonra zaman içinde) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

## <a name="cfiletimesecond"></a><a name="second"></a> CFileTime:: Second

Bir gün oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="cfiletimesettime"></a><a name="settime"></a> CFileTime:: SetTime

Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi çağırın `CFileTime` .

```cpp
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
Yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde tarih ve saati temsil eden 64 bitlik değer.

## <a name="cfiletimeutctolocal"></a><a name="utctolocal"></a> CFileTime:: UTCToLocal

Eşgüdümlü Evrensel Saat (UTC) temelinde yerel dosya zamanına göre saati dönüştürmek için bu yöntemi çağırın.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CFileTime`Yerel dosya saat biçiminde saati içeren bir nesne döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

## <a name="cfiletimeweek"></a><a name="week"></a> CFileTime:: Week

Bir hafta oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[FıLETıME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan sınıfı](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
