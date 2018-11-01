---
title: CFileTimeSpan sınıfı
ms.date: 10/18/2018
f1_keywords:
- CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::CFileTimeSpan
- ATLTIME/ATL::CFileTimeSpan::GetTimeSpan
- ATLTIME/ATL::CFileTimeSpan::SetTimeSpan
helpviewer_keywords:
- shared classes, CFileTimeSpan
- CFileTimeSpan class
ms.assetid: 5856fb39-9c82-4027-8ccf-8760890491ec
ms.openlocfilehash: dc59a300fc48f180fb593500ed85ee1a4c34c07e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468932"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan sınıfı

Bu sınıf, göreli tarih ve saat değerleri bir dosyayla ilgili yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFileTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|Zaman aralığını almak için bu yöntemi çağırın `CFileTimeSpan` nesne.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Zaman aralığını ayarlamak için bu yöntemi çağırın `CFileTimeSpan` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::operator-](#operator_-)|Çıkarma gerçekleştirir bir `CFileTimeSpan` nesne.|
|[CFileTimeSpan::operator! =](#operator_neq)|İki karşılaştırır `CFileTimeSpan` nesneleri için eşitsizlik.|
|[CFileTimeSpan::operator +](#operator_add)|Ayrıca gerçekleştiren bir `CFileTimeSpan` nesne.|
|[CFileTimeSpan::operator +=](#operator_add_eq)|Ayrıca gerçekleştiren bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.|
|[CFileTimeSpan::operator &lt;](#operator_lt)|İki karşılaştırır `CFileTimeSpan` küçük olanı belirlemek için nesneleri.|
|[CFileTimeSpan::operator &lt;=](#operator_lt_eq)|İki karşılaştırır `CFileTimeSpan` eşitlik ya da küçük olanı belirlemek için nesneleri.|
|[CFileTimeSpan::operator =](#operator_eq)|Atama işleci.|
|[CFileTimeSpan::operator-=](#operator_-_eq)|Çıkarma gerçekleştirir bir `CFileTimeSpan` nesne ve sonuç geçerli nesneye atayın.|
|[CFileTimeSpan::operator ==](#operator_eq_eq)|İki karşılaştırır `CFileTimeSpan` eşitlik için nesneleri.|
|[CFileTimeSpan::operator &gt;](#operator_gt)|İki karşılaştırır `CFileTimeSpan` büyük belirlemek için nesneleri.|
|[CFileTimeSpan::operator &gt;=](#operator_gt_eq)|İki karşılaştırır `CFileTimeSpan` eşitlik ya da daha büyük belirlemek için nesneleri.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın sağladığı yöntemlerle göreli nokta yönetmek için süresi ne zaman ilgili işlemleri gerçekleştirirken sık karşılaşılan bir dosya oluşturulduğu, en son erişilen veya en son değiştirildiği. Bu sınıftaki yöntemleri ile birlikte sık kullanılan [CFileTime sınıfı](../../atl-mfc-shared/reference/cfiletime-class.md) nesneleri.

## <a name="example"></a>Örnek

Örneğin bakın [CFileTime::Millisecond](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atltime.h

##  <a name="cfiletimespan"></a>  CFileTimeSpan::CFileTimeSpan

Oluşturucu.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
Varolan bir `CFileTimeSpan` nesnesi.

*nSpan*<br/>
Sürenin milisaniye cinsinden süre.

### <a name="remarks"></a>Açıklamalar

`CFileTimeSpan` Var olan bir nesne oluşturulabilir `CFileTimeSpan` nesne veya 64-bit bir değer ifade edilir. Varsayılan Oluşturucu, zaman aralığı 0 olarak ayarlar.

##  <a name="gettimespan"></a>  CFileTimeSpan::GetTimeSpan

Zaman aralığını almak için bu yöntemi çağırın `CFileTimeSpan` nesne.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Zaman aralığını milisaniye cinsinden döndürür.

##  <a name="operator_-"></a>  CFileTimeSpan::operator-

Çıkarma gerçekleştirir bir `CFileTimeSpan` nesne.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTimeSpan` iki zaman aralıkları arasındaki farkı sonucunu temsil eden nesne.

##  <a name="operator_neq"></a>  CFileTimeSpan::operator! =

İki karşılaştırır `CFileTimeSpan` nesneleri için eşitsizlik.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğesi eşit değilse TRUE döndürür `CFileTimeSpan` nesne; Aksi takdirde FALSE.

##  <a name="operator_add"></a>  CFileTimeSpan::operator +

Ayrıca gerçekleştiren bir `CFileTimeSpan` nesne.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CFileTimeSpan` kapsayan iki saat toplamını içeren nesne.

##  <a name="operator_add_eq"></a>  CFileTimeSpan::operator +=

Ayrıca gerçekleştiren bir `CFileTimeSpan` nesne ve sonuç geçerli nesnesine atar.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTimeSpan` kapsayan iki saat toplamını içeren nesne.

##  <a name="operator_lt"></a>  CFileTimeSpan::operator &lt;

İki karşılaştırır `CFileTimeSpan` küçük olanı belirlemek için nesneleri.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin küçükse TRUE döndürür (diğer bir deyişle, daha kısa bir süre temsil eder) ikinciden, aksi takdirde FALSE.

##  <a name="operator_lt_eq"></a>  CFileTimeSpan::operator &lt;=

İki karşılaştırır `CFileTimeSpan` eşitlik ya da küçük olanı belirlemek için nesneleri.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Döndürür, ikinci eşit veya ilk nesnenin küçükse (diğer bir deyişle, daha kısa bir süre temsil eder) TRUE tersi durumda FALSE.

##  <a name="operator_eq"></a>  CFileTimeSpan::operator =

Atama işleci.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTimeSpan` nesne.

##  <a name="operator_-_eq"></a>  CFileTimeSpan::operator-=

Çıkarma gerçekleştirir bir `CFileTimeSpan` nesne ve sonuç geçerli nesnesine atar.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CFileTimeSpan` nesne.

##  <a name="operator_eq_eq"></a>  CFileTimeSpan::operator ==

İki karşılaştırır `CFileTimeSpan` eşitlik için nesneleri.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşit, aksi durumda FALSE ise true değeri döndürür.

##  <a name="operator_gt"></a>  CFileTimeSpan::operator &gt;

İki karşılaştırır `CFileTimeSpan` büyük belirlemek için nesneleri.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin büyükse TRUE döndürür (diğer bir deyişle, daha uzun bir süre temsil eder) ikinciden, aksi takdirde FALSE.

##  <a name="operator_gt_eq"></a>  CFileTimeSpan::operator &gt;=

İki karşılaştırır `CFileTimeSpan` eşitlik ya da daha büyük belirlemek için nesneleri.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*<br/>
`CFileTimeSpan` Karşılaştırılacak nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesnenin büyükse TRUE döndürür (diğer bir deyişle, daha uzun bir süre temsil eder) veya ikinciye, aksi takdirde FALSE.

##  <a name="settimespan"></a>  CFileTimeSpan::SetTimeSpan

Zaman aralığını ayarlamak için bu yöntemi çağırın `CFileTimeSpan` nesne.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*nSpan*<br/>
Milisaniye cinsinden zaman aralığı için yeni değer.

## <a name="see-also"></a>Ayrıca Bkz.

[FILETIME](https://msdn.microsoft.com/library/windows/desktop/ms724284)<br/>
[CFileTime Sınıfı](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
