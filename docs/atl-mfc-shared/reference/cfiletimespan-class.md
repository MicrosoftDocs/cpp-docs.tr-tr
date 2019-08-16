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
ms.openlocfilehash: f9bb42ba4c142f671a83dcfa7e99cff940fff047
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491286"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan sınıfı

Bu sınıf, bir dosyayla ilişkili göreli tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CFileTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: CFileTimeSpan](#cfiletimespan)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: GetTimeSpan](#gettimespan)|`CFileTimeSpan` Nesneden zaman aralığını almak için bu yöntemi çağırın.|
|[CFileTimeSpan:: SetTimeSpan](#settimespan)|`CFileTimeSpan` Nesnenin zaman aralığını ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: operator-](#operator_-)|Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir.|
|[CFileTimeSpan:: operator! =](#operator_neq)|Eşitsizlik için `CFileTimeSpan` iki nesneyi karşılaştırır.|
|[CFileTimeSpan:: operator +](#operator_add)|Bir `CFileTimeSpan` nesnesine ekleme gerçekleştirir.|
|[CFileTimeSpan:: operator + =](#operator_add_eq)|Bir `CFileTimeSpan` nesnesine ekleme gerçekleştirir ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan:: işleci&lt;](#operator_lt)|, Daha `CFileTimeSpan` az anlamak için iki nesneyi karşılaştırır.|
|[CFileTimeSpan:: işleci&lt;=](#operator_lt_eq)|, Eşitlik `CFileTimeSpan` veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|
|[CFileTimeSpan:: operator =](#operator_eq)|Atama işleci.|
|[CFileTimeSpan:: operator-=](#operator_-_eq)|Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan:: operator = =](#operator_eq_eq)|, Eşitlik `CFileTimeSpan` için iki nesneyi karşılaştırır.|
|[CFileTimeSpan:: işleci&gt;](#operator_gt)|Daha büyük `CFileTimeSpan` olduğunu anlamak için iki nesneyi karşılaştırır.|
|[CFileTimeSpan:: işleci&gt;=](#operator_gt_eq)|, Eşitlik `CFileTimeSpan` veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf, bir dosyanın oluşturulduğu, son erişildiği veya en son değiştirildiği zaman ile ilgili işlemler gerçekleştirirken sıklıkla karşılaşılan zaman, göreli süreleri yönetmek için yöntemler sağlar. Bu sınıfın yöntemleri, genellikle [CFileTime sınıf](../../atl-mfc-shared/reference/cfiletime-class.md) nesneleriyle birlikte kullanılır.

## <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

##  <a name="cfiletimespan"></a>CFileTimeSpan:: CFileTimeSpan

Oluşturucu.

```
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Varolan bir `CFileTimeSpan` nesnesi.

*nSpan*<br/>
Milisaniye cinsinden bir süre.

### <a name="remarks"></a>Açıklamalar

Nesnesi, varolan `CFileTimeSpan` bir nesne kullanılarak veya 64 bitlik bir değer olarak ifade edilebilir. `CFileTimeSpan` Varsayılan Oluşturucu, zaman aralığını 0 olarak ayarlar.

##  <a name="gettimespan"></a>CFileTimeSpan:: GetTimeSpan

`CFileTimeSpan` Nesneden zaman aralığını almak için bu yöntemi çağırın.

```
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Milisaniye cinsinden zaman aralığını döndürür.

##  <a name="operator_-"></a>CFileTimeSpan:: operator-

Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir.

```
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İki zaman `CFileTimeSpan` yayılmış arasındaki farkın sonucunu temsil eden bir nesne döndürür.

##  <a name="operator_neq"></a>CFileTimeSpan:: operator! =

Eşitsizlik için `CFileTimeSpan` iki nesneyi karşılaştırır.

```
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Karşılaştırılan öğe `CFileTimeSpan` nesneye eşitse true, değilse false döndürür.

##  <a name="operator_add"></a>CFileTimeSpan:: operator +

Bir `CFileTimeSpan` nesnesine ekleme gerçekleştirir.

```
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İki zaman `CFileTimeSpan` yayıldığı toplamı içeren bir nesne döndürür.

##  <a name="operator_add_eq"></a>CFileTimeSpan:: operator + =

Bir `CFileTimeSpan` nesnesine ekleme gerçekleştirir ve sonucu geçerli nesneye atar.

```
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İki zaman yayılma `CFileTimeSpan` alanının toplamını içeren güncelleştirilmiş nesneyi döndürür.

##  <a name="operator_lt"></a>CFileTimeSpan:: işleci&lt;

, Daha `CFileTimeSpan` az anlamak için iki nesneyi karşılaştırır.

```
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne daha az (yani, daha kısa bir zaman aralığı temsil ediyorsa) ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

##  <a name="operator_lt_eq"></a>CFileTimeSpan:: işleci&lt;=

, Eşitlik `CFileTimeSpan` veya daha küçük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne küçüktür (yani, daha kısa bir zaman aralığını temsil eder) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

##  <a name="operator_eq"></a>CFileTimeSpan:: operator =

Atama işleci.

```
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTimeSpan` nesneyi döndürür.

##  <a name="operator_-_eq"></a>CFileTimeSpan:: operator-=

Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir ve sonucu geçerli nesneye atar.

```
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CFileTimeSpan` nesneyi döndürür.

##  <a name="operator_eq_eq"></a>CFileTimeSpan:: operator = =

, Eşitlik `CFileTimeSpan` için iki nesneyi karşılaştırır.

```
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşitse TRUE, değilse FALSE döndürür.

##  <a name="operator_gt"></a>CFileTimeSpan:: işleci&gt;

Daha büyük `CFileTimeSpan` olduğunu anlamak için iki nesneyi karşılaştırır.

```
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne, ikinciden büyükse TRUE, aksi durumda FALSE değerini döndürür.

##  <a name="operator_gt_eq"></a>CFileTimeSpan:: işleci&gt;=

, Eşitlik `CFileTimeSpan` veya daha büyük bir şekilde belirlenmesi için iki nesneyi karşılaştırır.

```
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*kapsamı*<br/>
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş Değeri

İlk nesne büyüktür (yani, daha uzun bir zaman aralığını temsil eder) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

##  <a name="settimespan"></a>CFileTimeSpan:: SetTimeSpan

`CFileTimeSpan` Nesnenin zaman aralığını ayarlamak için bu yöntemi çağırın.

```
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*nSpan*<br/>
Milisaniye cinsinden zaman aralığı için yeni değer.

## <a name="see-also"></a>Ayrıca bkz.

[FILETIME](/windows/win32/api/minwinbase/ns-minwinbase-filetime)<br/>
[CFileTime Sınıfı](../../atl-mfc-shared/reference/cfiletime-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
