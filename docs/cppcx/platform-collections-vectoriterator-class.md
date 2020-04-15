---
title: Platform::Collections::VectorIterator Sınıfı
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: e649027c2ba3f637c42765af691f4d321913fb28
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354363"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections::VectorIterator Sınıfı

Windows Runtime IVector arabiriminden türetilen nesneler için Standart Şablon Kitaplığı yineleyicisi sağlar.

VectorIterator, VectorProxy\<T> türü öğeleri depolayan bir proxy yineleyicidir. Ancak, proxy nesnesi kullanıcı kodu için hemen hemen hiç görünür değildir. Daha fazla bilgi için [Bkz. Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
VectorIterator şablon sınıfının dis adı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Rasgele erişim yineleme kategorisi (::std::random_access_iterator_tag).|
|`pointer`|Bir iç türü için bir işaretçi, Platform::Koleksiyonlar::Details::VectorProxy\<T>, VectorIterator uygulanması için gereklidir.|
|`reference`|Bir iç tür, Platform::Collections::Details::VectorProxy\<T>, bu VectorIterator uygulanması için gereklidir bir başvuru.|
|`value_type`|Yazı `T` adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[VectorIterator::VectorIterator](#ctor)|VectorIterator sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[VectorIterator::operator- Operatör](#operator-minus)|Yeni bir yineleyici veren geçerli yineleyiciden belirli sayıda öğe veya yinelenenler arasındaki öğe sayısını veren geçerli yineleyiciden belirtilen bir yineleyici çıkarılır.|
|[VectorIterator::operator- Operatör](#operator-decrement)|Geçerli VectorIterator'u atar.|
|[VectorIterator::operator!= Operatör](#operator-inequality)|Geçerli VectorIterator'un belirli bir VectorIterator'a eşit olup olmadığını gösterir.|
|[VectorIterator::operator* Operatör](#operator-dereference)|Geçerli VectorIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorIterator::operatör\[\]](#operator-at)|Geçerli VectorIterator'dan belirtilen bir yer değiştirme öğesine bir başvuru alır.|
|[VectorIterator::operator+ Operatör](#operator-plus)|Belirtilen VectorIterator'dan belirtilen deplasmantaki elemana başvuran bir VectorIterator döndürür.|
|[VectorIterator::operator++ Operatör](#operator-increment)|Geçerli VectorIterator'u da martılar.|
|[VectorIterator::operator+= Operatör](#operator-plus-assign)|Geçerli VectorIterator'u belirtilen yer değiştirmeyle karşılar.|
|[VectorIterator::operatör< Operatörü](#operator-less-than)|Geçerli VectorIterator'un belirli bir VectorIterator'dan daha az olup olmadığını gösterir.|
|[VectorIterator::operator\<= Operatör](#operator-less-than-or-equals)|Geçerli VectorIterator'un belirtilen VectorIterator'dan daha az mı yoksa eşit mi olduğunu gösterir.|
|[VectorIterator::operator-= Operatör](#operator-minus-equals)|Geçerli VectorIterator'u belirtilen yer değiştirmeyle erteler.|
|[VectorIterator::operator== Operatör](#operator-equality)|Geçerli VectorIterator'un belirli bir VectorIterator'a eşit olup olmadığını gösterir.|
|[VectorIterator::operatör> Operatörü](#operator-greater-than)|Geçerli VectorIterator'un belirli bir VectorIterator'dan büyük olup olmadığını gösterir.|
|[VectorIterator::operatör-> Operatörü](#operator-arrow)|Geçerli VectorIterator tarafından başvurulan öğenin adresini alır.|
|[VectorIterator::operator>= Operatör](#operator-greater-than-or-equals)|Geçerli VectorIterator'un belirtilen VectorIterator'dan büyük mü yoksa eşit mi olduğunu gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a>VectorIterator::operator-&gt; Operatör

Geçerli VectorIterator tarafından başvurulan öğenin adresini alır.

### <a name="syntax"></a>Sözdizimi

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından başvurulan öğenin değeri.

İade değerinin türü, bu işlecinin uygulanması için gerekli olan belirtilmemiş bir iç türüdür.

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a>VectorIterator::operator- Operatör

Geçerli VectorIterator'u atar.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi kararları ve ardından geçerli VectorIterator döndürür. İkinci sözdizimi, geçerli VectorIterator'un bir kopyasını döndürür ve ardından geçerli VectorIterator'u verir.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator sözdizimi geçerli VectorIterator'u önceden atar.

İkinci sözdizimi, geçerli VectorIterator'u atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, bir post-crement işlemi gösterir.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a>VectorIterator::operatör\* Operatörü

Geçerli VectorIterator tarafından belirtilen öğenin adresini alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından belirtilen öğe.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a>VectorIterator::operator== Operatör

Geçerli VectorIterator'un belirli bir VectorIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator *diğer*eşit ise **doğru** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>VectorIterator::operatör&gt; Operatörü

Geçerli VectorIterator'un belirli bir VectorIterator'dan büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator *diğerinden*daha büyük ise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>VectorIterator::operator&gt;= Operatör

Geçerli VectorIterator'un belirtilen VectorIterator'dan büyük mü yoksa eşit mi olduğunu gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator *diğer*büyük veya eşit ise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a>VectorIterator::operator++ Operatör

Geçerli VectorIterator'u da martılar.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artışlarını ve ardından geçerli VectorIterator'u döndürür. İkinci sözdizimi, geçerli VectorIterator'un bir kopyasını döndürür ve ardından geçerli VectorIterator'u çıkarır.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator sözdizimi geçerli VectorIterator'u önceden atar.

İkinci sözdizimi, geçerli VectorIterator'u aşamalı olarak atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, artış sonrası işlemi gösterir.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a>VectorIterator::operator!= Operatör

Geçerli VectorIterator'un belirli bir VectorIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator *diğer*eşit değilse **doğru** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a>VectorIterator::operatör&lt; Operatörü

Geçerli VectorIterator'un belirli bir VectorIterator'dan daha az olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator *diğerinden*daha az ise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>VectorIterator::operator&lt;= Operatör

Geçerli VectorIterator'un belirtilen VectorIterator'dan daha az mı yoksa eşit mi olduğunu gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorIterator daha az veya *diğer*eşit ise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a>VectorIterator::operator- Operatör

Yeni bir yineleyici veren geçerli yineleyiciden belirli sayıda öğe veya yinelenenler arasındaki öğe sayısını veren geçerli yineleyiciden belirtilen bir yineleyici çıkarılır.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir dizi öğe.

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleci sözdizimi, geçerli VectorIterator'dan daha az `n` eleman olan bir VectorIterator nesnesini döndürür. İkinci işleç sözdizimi, akım ve `other` VectorIterator arasındaki eleman sayısını döndürür.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a>VectorIterator::operator+= Operatör

Geçerli VectorIterator'u belirtilen yer değiştirmeyle karşılar.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Tamsayı deplasmanı.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a>VectorIterator::operator+ Operatör

Belirtilen VectorIterator'dan belirtilen deplasmantaki elemana başvuran bir VectorIterator döndürür.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator operator+(difference_type n);

template <typename T>
inline VectorIterator<T> operator+(
  ptrdiff_t n,
  const VectorIterator<T>& i);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
İkinci sözdiziminde, VectorIterator'un tür adı.

*n*<br/>
Bir sonda değişimi.

*Ⅰ*<br/>
İkinci sözdiziminde, bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdiziminde, geçerli VectorIterator'dan belirtilen yer değiştirmeöğesine başvuran bir VectorIterator.

İkinci sözdiziminde, parametrenin `i`başlangıcından itibaren belirtilen yer değiştirme öğesine başvuran bir VectorIterator .

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a>VectorIterator::operator-= Operatör

Geçerli VectorIterator'u belirtilen yer değiştirmeyle erteler.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir sonda değişimi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a>VectorIterator::operatör\[\]

Geçerli VectorIterator'dan belirtilen bir yer değiştirme öğesine bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir sonda değişimi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator'daki öğeler tarafından `n` yer değiştiren öğe.

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a>VectorIterator::VectorIterator Constructor

VectorIterator sınıfının yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>Parametreler

*v*<br/>
Bir IVector\<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği varsayılan oluşturucudur. İkinci sözdizimi örneği, Bir IVector\<T> nesnesinden VectorIterator oluşturmak için kullanılan açık bir oluşturucudur.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
