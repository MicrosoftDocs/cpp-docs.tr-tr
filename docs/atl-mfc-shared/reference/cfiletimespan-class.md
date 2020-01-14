---
title: CFileTimeSpan sınıfı
description: Etkin Şablon kitaplığı (ATL) ve Microsoft Foundation Sınıfları (MFC) CFileTimeSpan sınıfı, FILETIME birimlerindeki zaman aralıklarını yönetir.
ms.date: 01/10/2020
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
ms.openlocfilehash: 89d95759b11ff7e52c2a8fa75cf94f7b7b81fa36
ms.sourcegitcommit: c3283062ce4e382aec7f11626d358a37caf8cdbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75914389"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan sınıfı

Bu sınıf, bir dosyayla ilişkili göreli tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CFileTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: CFileTimeSpan](#cfiletimespan)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: GetTimeSpan](#gettimespan)|`CFileTimeSpan` nesnesinden zaman aralığını almak için bu yöntemi çağırın.|
|[CFileTimeSpan:: SetTimeSpan](#settimespan)|`CFileTimeSpan` nesnesinin zaman aralığını ayarlamak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak işleçler

|Name|Açıklama|
|----------|-----------------|
|[CFileTimeSpan:: operator-](#operator_-)|`CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirir.|
|[CFileTimeSpan:: operator! =](#operator_neq)|Eşitsizlik için iki `CFileTimeSpan` nesnesini karşılaştırır.|
|[CFileTimeSpan:: operator +](#operator_add)|`CFileTimeSpan` nesnesine ekleme gerçekleştirir.|
|[CFileTimeSpan:: operator + =](#operator_add_eq)|`CFileTimeSpan` nesnesine ekleme gerçekleştirir ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan:: operator &lt;](#operator_lt)|, Daha az anlamak için iki `CFileTimeSpan` nesnesini karşılaştırır.|
|[CFileTimeSpan:: operator &lt;=](#operator_lt_eq)|, Eşitlik veya daha küçük bir şekilde belirlenmesi için iki `CFileTimeSpan` nesnesini karşılaştırır.|
|[CFileTimeSpan:: operator =](#operator_eq)|Atama işleci.|
|[CFileTimeSpan:: operator-=](#operator_-_eq)|`CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirir ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan:: operator = =](#operator_eq_eq)|, Eşitlik için iki `CFileTimeSpan` nesnesini karşılaştırır.|
|[CFileTimeSpan:: operator &gt;](#operator_gt)|Daha büyük olduğunu anlamak için iki `CFileTimeSpan` nesnesini karşılaştırır.|
|[CFileTimeSpan:: operator &gt;=](#operator_gt_eq)|, Eşitlik veya daha büyük olan iki `CFileTimeSpan` nesnesini karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

`CFileTimeSpan` sınıfı, dosya sisteminin kullandığı birimlerde ilgili zaman aralıklarını işlemek için yöntemler sağlar. Bu birimler genellikle dosya işlemlerinde, örneğin bir dosyanın oluşturulduğu, son erişildiği veya son değiştirilme tarihi gibi kullanılır. Bu sınıfın yöntemleri, genellikle [CFileTime sınıf](../../atl-mfc-shared/reference/cfiletime-class.md) nesneleriyle birlikte kullanılır.

## <a name="example"></a>Örnek

[CFileTime:: milisaniyelik](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond)örneğine bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime. h

## <a name="cfiletimespan"></a>CFileTimeSpan:: CFileTimeSpan

Oluşturucu.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Varolan bir `CFileTimeSpan` nesnesi.

*Nspan*\
FILETIME birimlerindeki bir süre.

### <a name="remarks"></a>Açıklamalar

`CFileTimeSpan` nesnesi, var olan bir `CFileTimeSpan` nesnesi kullanılarak oluşturulabilir veya 100-nanosaniyelik FILETIME birimlerinde 64 bitlik bir değer olarak ifade edilebilir. Daha fazla bilgi için bkz. [CFileTime](cfiletime-class.md). Varsayılan Oluşturucu, zaman aralığını 0 olarak ayarlar.

## <a name="gettimespan"></a>CFileTimeSpan:: GetTimeSpan

`CFileTimeSpan` nesnesinden zaman aralığını almak için bu yöntemi çağırın.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Dönüş değeri

100-nanosaniyelik FILETIME birimlerindeki zaman aralığını döndürür. Daha fazla bilgi için bkz. [CFileTime](cfiletime-class.md).

## <a name="operator_-"></a>CFileTimeSpan:: operator-

`CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirir.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş değeri

İki zaman yayılmaları arasındaki farkın sonucunu temsil eden bir `CFileTimeSpan` nesnesi döndürür.

## <a name="operator_neq"></a>CFileTimeSpan:: operator! =

Eşitsizlik için iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

Karşılaştırılan öğe `CFileTimeSpan` nesnesine eşitse TRUE değerini döndürür; Aksi halde yanlış.

## <a name="operator_add"></a>CFileTimeSpan:: operator +

`CFileTimeSpan` nesnesine ekleme gerçekleştirir.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş değeri

İki zaman yayıldığı toplamı içeren `CFileTimeSpan` nesnesini döndürür.

## <a name="operator_add_eq"></a>CFileTimeSpan:: operator + =

`CFileTimeSpan` nesnesine ekleme gerçekleştirir ve sonucu geçerli nesneye atar.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş değeri

İki zaman yayılma alanının toplamını içeren güncelleştirilmiş `CFileTimeSpan` nesnesini döndürür.

## <a name="operator_lt"></a>CFileTimeSpan:: operator &lt;

, Daha az anlamak için iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

İlk nesne daha az (yani, daha kısa bir zaman aralığı temsil ediyorsa) ikinciden küçükse TRUE, aksi takdirde FALSE döndürür.

## <a name="operator_lt_eq"></a>CFileTimeSpan:: operator &lt;=

, Eşitlik veya daha küçük bir şekilde belirlenmesi için iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

İlk nesne küçüktür (yani, daha kısa bir zaman aralığını temsil eder) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

## <a name="operator_eq"></a>CFileTimeSpan:: operator =

Atama işleci.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş değeri

Güncelleştirilmiş `CFileTimeSpan` nesnesini döndürür.

## <a name="operator_-_eq"></a>CFileTimeSpan:: operator-=

`CFileTimeSpan` nesnesi üzerinde çıkarma gerçekleştirir ve sonucu geçerli nesneye atar.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
A `CFileTimeSpan` nesne.

### <a name="return-value"></a>Dönüş değeri

Güncelleştirilmiş `CFileTimeSpan` nesnesini döndürür.

## <a name="operator_eq_eq"></a>CFileTimeSpan:: operator = =

, Eşitlik için iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

Nesneler eşitse TRUE, değilse FALSE döndürür.

## <a name="operator_gt"></a>CFileTimeSpan:: operator &gt;

Daha büyük olduğunu anlamak için iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

İlk nesne, ikinciden büyükse TRUE, aksi durumda FALSE değerini döndürür.

## <a name="operator_gt_eq"></a>CFileTimeSpan:: operator &gt;=

, Eşitlik veya daha büyük olan iki `CFileTimeSpan` nesnesini karşılaştırır.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*yayılma*\
Karşılaştırılacak `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Dönüş değeri

İlk nesne büyüktür (yani, daha uzun bir zaman aralığını temsil eder) veya ikinciye eşitse TRUE, değilse FALSE döndürür.

## <a name="settimespan"></a>CFileTimeSpan:: SetTimeSpan

`CFileTimeSpan` nesnesinin zaman aralığını ayarlamak için bu yöntemi çağırın.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*Nspan*\
100-nanosaniyelik FILETIME birimlerindeki zaman aralığı için yeni değer. Daha fazla bilgi için bkz. [CFileTime](cfiletime-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)\
[CFileTime sınıfı](cfiletime-class.md)\
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)\
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
