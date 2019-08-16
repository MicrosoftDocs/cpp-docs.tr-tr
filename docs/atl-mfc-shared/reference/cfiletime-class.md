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
ms.openlocfilehash: b24d1e4d3e670a820c41735617b7db6780ff137c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491480"
---
# <a name="cfiletime-class"></a>CFileTime sınıfı

Bu sınıf, bir dosyayla ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

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
|[CFileTime:: GetCurrentTime](#getcurrenttime)|Geçerli sistem tarihini ve saatini temsil eden `CFileTime` bir nesne almak için bu statik işlevi çağırın.|
|[CFileTime:: GetTime](#gettime)|`CFileTime` Nesneden saati almak için bu yöntemi çağırın.|
|[CFileTime:: LocalToUTC](#localtoutc)|Yerel bir dosya saatini Eşgüdümlü Evrensel Saat (UTC) temelinde bir dosya saatine dönüştürmek için bu yöntemi çağırın.|
|[CFileTime:: SetTime](#settime)|`CFileTime` Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi çağırın.|
|[CFileTime:: UTCToLocal](#utctolocal)|Eşgüdümlü Evrensel Saat (UTC) temelinde yerel dosya zamanına göre saati dönüştürmek için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTime:: operator-](#operator_-)|Bu işleç, bir `CFileTime` veya `CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirmek için kullanılır.|
|[CFileTime:: operator! =](#operator_neq)|Bu işleç, eşitsizlik `CFileTime` için iki nesneyi karşılaştırır.|
|[CFileTime:: operator +](#operator_add)|Bu işleç, bir `CFileTimeSpan` nesnesine ekleme yapmak için kullanılır.|
|[CFileTime:: operator + =](#operator_add_eq)|Bu işleç, bir `CFileTimeSpan` nesnesine ekleme yapmak ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime:: işleci&lt;](#operator_lt)|Bu işleç, daha `CFileTime` az anlamak için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci&lt;=](#operator_lt_eq)|Bu işleç, eşitlik `CFileTime` veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|
|[CFileTime:: operator =](#operator_eq)|Atama işleci.|
|[CFileTime:: operator-=](#operator_-_eq)|Bu işleç, bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.|
|[CFileTime:: operator = =](#operator_eq_eq)|Bu işleç, eşitlik `CFileTime` için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci&gt;](#operator_gt)|Bu işleç, daha `CFileTime` büyük olduğunu anlamak için iki nesneyi karşılaştırır.|
|[CFileTime:: işleci&gt;=](#operator_gt_eq)|Bu işleç, eşitlik `CFileTime` veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|

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

Bu sınıf, dosya oluşturma, erişim ve değiştirme ile ilişkili tarih ve saat değerlerini yönetmek için yöntemler sağlar. Bu sınıfın yöntemleri ve verileri, genellikle göreli zaman değerleriyle ilgilenen nesneler ile `CFileTimeSpan` birlikte kullanılır.

Tarih ve saat değeri, 1 Ocak 1601 ' den bu yana 100-nanosaniyelik aralıklarının sayısını temsil eden 64 bitlik bir değer olarak depolanır. Bu Eşgüdümlü Evrensel Saat (UTC) biçimidir.

Hesaplamaları basitleştirmek için aşağıdaki statik const üye değişkenleri verilmiştir:

|Üye değişkeni|100-nanosaniyelik aralıklarının sayısı|
|---------------------|-----------------------------------------|
|Milisaniy|10,000|
|Saniye|Milisaniyelik \* 1.000|
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

##  <a name="cfiletime"></a>CFileTime:: CFileTime

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

Nesne, bir `FILETIME` yapıdan mevcut bir tarih ve saat kullanılarak veya 64 bitlik bir değer (yerel veya Eşgüdümlü Evrensel Saat (UTC) saat biçimlerinde) olarak ifade edilebilir. `CFileTime` Varsayılan Oluşturucu saati 0 olarak ayarlar.

##  <a name="day"></a>CFileTime::D ay

Bir gün oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Day = Hour* 24;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

##  <a name="getcurrenttime"></a>CFileTime:: GetCurrentTime

Geçerli sistem tarihini ve saatini temsil eden `CFileTime` bir nesne almak için bu statik işlevi çağırın.

```
static CFileTime GetCurrentTime() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli sistem tarihi ve saati Eşgüdümlü Evrensel Saat (UTC) biçiminde döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#41](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_1.cpp)]

##  <a name="gettime"></a>CFileTime:: GetTime

`CFileTime` Nesneden saati almak için bu yöntemi çağırın.

```
ULONGLONG GetTime() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tarih ve saati 64 bitlik bir sayı olarak döndürür. Bu, yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde olabilir.

##  <a name="hour"></a>CFileTime:: Saat

Bir saat oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Hour = Minute* 60;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

##  <a name="localtoutc"></a>CFileTime:: LocalToUTC

Yerel bir dosya saatini Eşgüdümlü Evrensel Saat (UTC) temelinde bir dosya saatine dönüştürmek için bu yöntemi çağırın.

```
CFileTime LocalToUTC() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saati UTC `CFileTime` biçiminde içeren bir nesne döndürür.

### <a name="example"></a>Örnek

[CFileTime:: UTCToLocal](#utctolocal)örneğine bakın.

##  <a name="millisecond"></a>CFileTime:: milisaniyelik

Bir milisaniyelik oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Millisecond = 10000;
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#44](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_2.cpp)]

##  <a name="minute"></a>CFileTime:: dakika

Bir dakika oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Minute = Second* 60;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

##  <a name="operator_-"></a>CFileTime:: operator-

Bu işleç, bir `CFileTime` veya `CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirmek için kullanılır.

```
CFileTime operator-(CFileTimeSpan span) const throw();
CFileTimeSpan operator-(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

*meniz*<br/>
A `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İki nesne arasındaki zaman farkının `CFileTimeSpan` sonucunu temsil eden bir nesne veya nesne döndürür. `CFileTime`

##  <a name="operator_neq"></a>CFileTime:: operator! =

Bu işleç, eşitsizlik `CFileTime` için iki nesneyi karşılaştırır.

```
bool operator!=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CFileTime` nesneye eşitse true, değilse false döndürür.

##  <a name="operator_add"></a>CFileTime:: operator +

Bu işleç, bir `CFileTimeSpan` nesnesine ekleme yapmak için kullanılır.

```
CFileTime operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Özgün zamanın `CFileTime` sonucunu ve göreli bir süreyi temsil eden bir nesne döndürür.

##  <a name="operator_add_eq"></a>CFileTime:: operator + =

Bu işleç, bir `CFileTimeSpan` nesnesine ekleme yapmak ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Orijinal saatin sonucunu `CFileTime` ve göreli bir süreyi temsil eden güncelleştirilmiş nesneyi döndürür.

##  <a name="operator_lt"></a>CFileTime:: işleci&lt;

Bu işleç, daha `CFileTime` az anlamak için iki nesneyi karşılaştırır.

```
bool operator<(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#43](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_3.cpp)]

##  <a name="operator_lt_eq"></a>CFileTime:: işleci&lt;=

Bu işleç, eşitlik `CFileTime` veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator<=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (zaman içinde daha önce) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

##  <a name="operator_eq"></a>CFileTime:: operator =

Atama işleci.

```
CFileTime& operator=(const FILETIME& ft) throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Yeni `CFileTime` saat ve tarihi içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTime` nesneyi döndürür.

##  <a name="operator_-_eq"></a>CFileTime:: operator-=

Bu işleç, bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirmek ve sonucu geçerli nesneye atamak için kullanılır.

```
CFileTime& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Çıkarmak `CFileTimeSpan` için göreli süreyi içeren bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTime` nesneyi döndürür.

##  <a name="operator_eq_eq"></a>CFileTime:: operator = =

Bu işleç, eşitlik `CFileTime` için iki nesneyi karşılaştırır.

```
bool operator==(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE, değilse FALSE döndürür.

##  <a name="operator_gt"></a>CFileTime:: işleci&gt;

Bu işleç, daha `CFileTime` büyük olduğunu anlamak için iki nesneyi karşılaştırır.

```
bool operator>(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne ikinciden büyükse TRUE, değilse FALSE döndürür.

##  <a name="operator_gt_eq"></a>CFileTime:: işleci&gt;=

Bu işleç, eşitlik `CFileTime` veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator>=(CFileTime ft) const throw();
```

### <a name="parameters"></a>Parametreler

*meniz*<br/>
Karşılaştırılacak `CFileTime` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne (daha sonra zaman içinde) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

##  <a name="second"></a>CFileTime:: Second

Bir gün oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Second = Millisecond* 1000;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

##  <a name="settime"></a>CFileTime:: SetTime

`CFileTime` Nesne tarafından depolanan tarih ve saati ayarlamak için bu yöntemi çağırın.

```
void SetTime(ULONGLONG nTime) throw();
```

### <a name="parameters"></a>Parametreler

*nZaman*<br/>
Yerel veya Eşgüdümlü Evrensel Saat (UTC) biçiminde tarih ve saati temsil eden 64 bitlik değer.

##  <a name="utctolocal"></a>CFileTime:: UTCToLocal

Eşgüdümlü Evrensel Saat (UTC) temelinde yerel dosya zamanına göre saati dönüştürmek için bu yöntemi çağırın.

```
CFileTime UTCToLocal() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Yerel dosya `CFileTime` saat biçiminde saati içeren bir nesne döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCFiles#42](../../atl-mfc-shared/reference/codesnippet/cpp/cfiletime-class_4.cpp)]

##  <a name="week"></a>CFileTime:: Week

Bir hafta oluşturan 100-nanosaniyelik aralıklarının sayısını depolayan statik bir veri üyesi.

```
static const ULONGLONG Week = Day* 7;
```

### <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](#millisecond)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTimeSpan Sınıfı](../../atl-mfc-shared/reference/cfiletimespan-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
