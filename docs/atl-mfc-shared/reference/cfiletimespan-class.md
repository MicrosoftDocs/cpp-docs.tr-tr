---
title: CFileTimeSpan sınıfı
description: Etkin Şablon Kitaplığı (ATL) ve Microsoft Hazırlık Sınıfları (MFC) CFileTimeSpan sınıfı, FILETIME birimlerindeki zaman aralıklarını yönetir.
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
ms.openlocfilehash: 87737ea1c778660a68510b484bcdfa3a4670e8ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317850"
---
# <a name="cfiletimespan-class"></a>CFileTimeSpan sınıfı

Bu sınıf, bir dosyayla ilişkili göreli tarih ve saat değerlerini yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CFileTimeSpan
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Kamu yapıcılar

|Adı|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::CFileTimeSpan](#cfiletimespan)|Oluşturucu.|

### <a name="public-methods"></a>Genel yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::GetTimeSpan](#gettimespan)|`CFileTimeSpan` Nesneden zaman aralığıalmak için bu yöntemi arayın.|
|[CFileTimeSpan::SetTimeSpan](#settimespan)|Nesnenin zaman aralığını ayarlamak `CFileTimeSpan` için bu yöntemi çağırın.|

### <a name="public-operators"></a>Kamu operatörleri

|Adı|Açıklama|
|----------|-----------------|
|[CFileTimeSpan::operatör -](#operator_-)|Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir.|
|[CFileTimeSpan::operatör !=](#operator_neq)|Eşitsizlik için `CFileTimeSpan` iki nesneyi karşılaştırır.|
|[CFileTimeSpan::operatör +](#operator_add)|Bir `CFileTimeSpan` nesneye ekleme yapar.|
|[CFileTimeSpan::operatör +=](#operator_add_eq)|Bir `CFileTimeSpan` nesneye ekleme yapar ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan::operatör&lt;](#operator_lt)|Daha azını belirlemek için iki `CFileTimeSpan` nesneyi karşılaştırır.|
|[CFileTimeSpan::operatör&lt;=](#operator_lt_eq)|Eşitliği veya `CFileTimeSpan` daha azı belirlemek için iki nesneyi karşılaştırır.|
|[CFileTimeSpan::operator =](#operator_eq)|Atama işleci.|
|[CFileTimeSpan::operatör -=](#operator_-_eq)|Bir `CFileTimeSpan` nesne üzerinde çıkarma yapar ve sonucu geçerli nesneye atar.|
|[CFileTimeSpan::operatör ==](#operator_eq_eq)|Eşitlik için `CFileTimeSpan` iki nesneyi karşılaştırır.|
|[CFileTimeSpan::operatör&gt;](#operator_gt)|Büyük belirlemek `CFileTimeSpan` için iki nesneyi karşılaştırır.|
|[CFileTimeSpan::operatör&gt;=](#operator_gt_eq)|Eşitliği veya `CFileTimeSpan` daha büyük olanın belirlenmesi için iki nesneyi karşılaştırır.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CFileTimeSpan` dosya sisteminin kullandığı birimlerde göreli zaman dönemlerini işlemek için yöntemler sağlar. Bu birimler genellikle dosya nın ne zaman oluşturulduğu, en son erişilmesi veya en son değiştirilmesi gibi dosya işlemlerinde kullanılır. Bu sınıfın yöntemleri sık sık [CFileTime sınıf](../../atl-mfc-shared/reference/cfiletime-class.md) nesneleri ile birlikte kullanılır.

## <a name="example"></a>Örnek

CFileTime örneğine [bakın:Milisaniye](../../atl-mfc-shared/reference/cfiletime-class.md#millisecond).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atltime.h

## <a name="cfiletimespancfiletimespan"></a><a name="cfiletimespan"></a>CFileTimeSpan::CFileTimeSpan

Oluşturucu.

```cpp
CFileTimeSpan() throw();
CFileTimeSpan(const CFileTimeSpan& span) throw();
CFileTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Varolan bir `CFileTimeSpan` nesnesi.

*nSpan*\
FILETIME birimlerinde bir süre.

### <a name="remarks"></a>Açıklamalar

Nesne `CFileTimeSpan` varolan `CFileTimeSpan` bir nesne kullanılarak oluşturulabilir veya 100 nanosaniyelik FILETIME birimlerinde 64 bit lik bir değer olarak ifade edilebilir. Daha fazla bilgi için [CFileTime'a](cfiletime-class.md)bakın. Varsayılan oluşturucu zaman aralığını 0 olarak ayarlar.

## <a name="cfiletimespangettimespan"></a><a name="gettimespan"></a>CFileTimeSpan::GetTimeSpan

`CFileTimeSpan` Nesneden zaman aralığıalmak için bu yöntemi arayın.

```cpp
LONGLONG GetTimeSpan() const throw();
```

### <a name="return-value"></a>Döndürülen değer

Zaman aralığını 100 nanosaniyelik FILETIME birimlerinde döndürür. Daha fazla bilgi için [CFileTime'a](cfiletime-class.md)bakın.

## <a name="cfiletimespanoperator--"></a><a name="operator_-"></a>CFileTimeSpan::operatör -

Bir `CFileTimeSpan` nesne üzerinde çıkarma gerçekleştirir.

```cpp
CFileTimeSpan operator-(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Döndürülen değer

İki `CFileTimeSpan` zaman aralığı arasındaki farkın sonucunu temsil eden bir nesne döndürür.

## <a name="cfiletimespanoperator-"></a><a name="operator_neq"></a>CFileTimeSpan::operatör !=

Eşitsizlik için `CFileTimeSpan` iki nesneyi karşılaştırır.

```cpp
bool operator!=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

Karşılaştırılan öğe `CFileTimeSpan` nesneye eşit değilse TRUE döndürür; aksi takdirde YANLIŞ.

## <a name="cfiletimespanoperator-"></a><a name="operator_add"></a>CFileTimeSpan::operatör +

Bir `CFileTimeSpan` nesneye ekleme yapar.

```cpp
CFileTimeSpan operator+(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Döndürülen değer

İki `CFileTimeSpan` zaman aralığının toplamını içeren bir nesneyi döndürür.

## <a name="cfiletimespanoperator-"></a><a name="operator_add_eq"></a>CFileTimeSpan::operatör +=

Bir `CFileTimeSpan` nesneye ekleme yapar ve sonucu geçerli nesneye atar.

```cpp
CFileTimeSpan& operator+=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Döndürülen değer

İki zaman `CFileTimeSpan` aralığının toplamını içeren güncelleştirilmiş nesneyi döndürür.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt"></a>CFileTimeSpan::operatör&lt;

Daha azını belirlemek için iki `CFileTimeSpan` nesneyi karşılaştırır.

```cpp
bool operator<(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

İlk nesne ikinciden daha azsa (yani daha kısa bir zaman dilimini temsil ediyorsa) TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimespanoperator-lt"></a><a name="operator_lt_eq"></a>CFileTimeSpan::operatör&lt;=

Eşitliği veya `CFileTimeSpan` daha azı belirlemek için iki nesneyi karşılaştırır.

```cpp
bool operator<=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

İlk nesne (yani daha kısa bir zaman dilimini temsil eder) veya ikincisine eşitse, aksi takdirde FALSE'dan daha azsa TRUE döndürür.

## <a name="cfiletimespanoperator-"></a><a name="operator_eq"></a>CFileTimeSpan::operator =

Atama işleci.

```cpp
CFileTimeSpan& operator=(const CFileTimeSpan& span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Döndürülen değer

Güncelleştirilmiş `CFileTimeSpan` nesneyi döndürür.

## <a name="cfiletimespanoperator--"></a><a name="operator_-_eq"></a>CFileTimeSpan::operatör -=

Bir `CFileTimeSpan` nesne üzerinde çıkarma yapar ve sonucu geçerli nesneye atar.

```cpp
CFileTimeSpan& operator-=(CFileTimeSpan span) throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Bir `CFileTimeSpan` nesnesi.

### <a name="return-value"></a>Döndürülen değer

Güncelleştirilmiş `CFileTimeSpan` nesneyi döndürür.

## <a name="cfiletimespanoperator-"></a><a name="operator_eq_eq"></a>CFileTimeSpan::operatör ==

Eşitlik için `CFileTimeSpan` iki nesneyi karşılaştırır.

```cpp
bool operator==(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

Nesneler eşitse TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt"></a>CFileTimeSpan::operatör&gt;

Büyük belirlemek `CFileTimeSpan` için iki nesneyi karşılaştırır.

```cpp
bool operator>(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

İlk nesne ikinciden daha büyükse (diğer bir süre daha uzun bir zamanı temsil ediyorsa) TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimespanoperator-gt"></a><a name="operator_gt_eq"></a>CFileTimeSpan::operatör&gt;=

Eşitliği veya `CFileTimeSpan` daha büyük olanın belirlenmesi için iki nesneyi karşılaştırır.

```cpp
bool operator>=(CFileTimeSpan span) const throw();
```

### <a name="parameters"></a>Parametreler

*Span*\
Karşılaştırılacak `CFileTimeSpan` nesne.

### <a name="return-value"></a>Döndürülen değer

İlk nesne daha büyükse (yani daha uzun bir zamanı temsil ediyorsa) veya ikincisine eşitse TRUE döndürür, aksi takdirde FALSE.

## <a name="cfiletimespansettimespan"></a><a name="settimespan"></a>CFileTimeSpan::SetTimeSpan

Nesnenin zaman aralığını ayarlamak `CFileTimeSpan` için bu yöntemi çağırın.

```cpp
void SetTimeSpan(LONGLONG nSpan) throw();
```

### <a name="parameters"></a>Parametreler

*nSpan*\
100 nanosaniyelik FILETIME birimlerinde zaman aralığı için yeni değer. Daha fazla bilgi için [CFileTime'a](cfiletime-class.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Filetime](/windows/win32/api/minwinbase/ns-minwinbase-filetime)\
[CFileTime sınıfı](cfiletime-class.md)\
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)\
[ATL/MFC paylaşılan sınıflar](../../atl-mfc-shared/atl-mfc-shared-classes.md)
