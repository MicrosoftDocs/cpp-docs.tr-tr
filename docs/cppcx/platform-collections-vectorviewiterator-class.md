---
title: Platform::Koleksiyonlar::VectorViewIterator Sınıfı
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: 01ae4286e996db9819cb697360f6de9c344edd21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81363703"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform::Koleksiyonlar::VectorViewIterator Sınıfı

Windows Runtime`IVectorView` arabiriminden türetilen nesneler için Standart Şablon Kitaplığı yineleyicisi sağlar.

`ViewVectorIterator`türündeki `VectorProxy<T>`öğeleri depolayan bir proxy yineleyicidir. Ancak, proxy nesnesi kullanıcı kodu için hemen hemen hiç görünür değildir. Daha fazla bilgi için [Bkz. Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
VectorViewIterator şablon sınıfının dis adı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Rasgele erişim yineleme kategorisi (::std::random_access_iterator_tag).|
|`pointer`|VectorViewIterator'un uygulanması için gerekli olan dahili türe işaretçi.|
|`reference`|VectorViewIterator'un uygulanması için gerekli olan dahili türe başvuru.|
|`value_type`|Yazı `T` adı.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[VectorViewIterator::VectorViewIterator](#ctor)|VectorViewIterator sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[VectorViewIterator::operatör- Operatör](#operator-minus)|Yeni bir yineleyici veren geçerli yineleyiciden belirli sayıda öğe veya yinelenenler arasındaki öğe sayısını veren geçerli yineleyiciden belirtilen bir yineleyici çıkarılır.|
|[VectorViewIterator::operator-- Operatör](#operator-decrement)|Geçerli VectorViewIterator'u atar.|
|[VectorViewIterator::operator!= Operatör](#operator-inequality)|Geçerli VectorViewIterator'un belirli bir VectorViewIterator'a eşit olup olmadığını gösterir.|
|[VectorViewIterator::operator* Operatör](#operator-dereference)|Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorViewIterator::operatör\[\]](#operator-at)|Geçerli VectorViewIterator'dan belirtilen bir yer değiştirme öğesine bir başvuru alır.|
|[VectorViewIterator::operator+ Operatör](#operator-plus)|Belirtilen VectorViewIterator'dan belirtilen deplasmantaki elemana başvuran bir VectorViewIterator döndürür.|
|[VectorViewIterator::operator++ Operatör](#operator-increment)|Geçerli VectorViewIterator'u atar.|
|[VectorViewIterator::operator+= Operatör](#operator-plus-equals)|Geçerli VectorViewIterator'u belirtilen yer değiştirmeyle karşılar.|
|[VectorViewIterator::operatör< Operatörü](#operator-less-than)|Geçerli VectorViewIterator'un belirli bir VectorViewIterator'dan daha az olup olmadığını gösterir.|
|[VectorViewIterator::operator\<= Operatör](#operator-less-than-or-equals)|Geçerli VectorViewIterator'un belirtilen VectorViewIterator'dan daha az mı yoksa eşit mi olduğunu gösterir.|
|[VectorViewIterator::operator-= Operatör](#operator-minus-assign)|Geçerli VectorViewIterator'u belirtilen yer değiştirmeyle eriter.|
|[VectorViewIterator::operator== Operatör](#operator-equality)|Geçerli VectorViewIterator'un belirli bir VectorViewIterator'a eşit olup olmadığını gösterir.|
|[VectorViewIterator::operatör> Operatörü](#operator-greater-than)|Geçerli VectorViewIterator'un belirli bir VectorViewIterator'dan büyük olup olmadığını gösterir.|
|[VectorViewIterator::operatör-> Operatörü](#operator-arrow)|Geçerli VectorViewIterator tarafından başvurulan öğenin adresini alır.|
|[VectorViewIterator::operatör>= Operatör](#operator-greater-than-or-equals)|Geçerli VectorViewIterator'un belirtilen VectorViewIterator'dan büyük mü yoksa eşit mi olduğunu gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorViewIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="vectorviewiteratoroperator-gt-operator"></a><a name="operator-arrow"></a>VectorViewIterator::operatör-&gt; Operatör

Geçerli VectorViewIterator tarafından başvurulan öğenin adresini alır.

### <a name="syntax"></a>Sözdizimi

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından başvurulan öğenin değeri.

İade değerinin türü, bu işlecinin uygulanması için gerekli olan belirtilmemiş bir iç türüdür.

## <a name="vectorviewiteratoroperator---operator"></a><a name="operator-decrement"></a>VectorViewIterator::operator-- Operatör

Geçerli VectorViewIterator'u atar.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi kararları ve ardından geçerli VectorViewIterator döndürür. İkinci sözdizimi, geçerli VectorViewIterator'un bir kopyasını döndürür ve ardından geçerli VectorViewIterator'u verir.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator sözdizimi geçerli VectorViewIterator ön-kararnameler.

İkinci sözdizimi, geçerli VectorViewIterator'u atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, bir post-crement işlemi gösterir.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-dereference"></a>VectorViewIterator::operatör\* Operatörü

Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından belirtilen öğe.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-equality"></a>VectorViewIterator::operator== Operatör

Geçerli VectorViewIterator'un belirli bir VectorViewIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

akım `VectorViewIterator` *diğer*ine eşitse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than"></a>VectorViewIterator::operatör&gt; Operatörü

Geçerli VectorViewIterator'un belirli bir VectorViewIterator'dan büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

geçerli VectorViewIterator *diğerinden*daha büyükise **doğrudur** ; aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a>VectorViewIterator::operator&gt;= Operatör

Akımın `VectorViewIterator` belirtilenden `VectorViewIterator`büyük mü yoksa eşit mi olduğunu gösterir.

### <a name="syntax"></a>Sözdizimi

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

akım `VectorViewIterator` *diğerinden*büyük veya eşitse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-increment"></a>VectorViewIterator::operator++ Operatör

Geçerli VectorViewIterator'u atar.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artışlarını ve ardından geçerli VectorViewIterator'u döndürür. İkinci sözdizimi, geçerli VectorViewIterator'un bir kopyasını döndürür ve ardından geçerli VectorViewIterator'u da atar.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator sözdizimi geçerli VectorViewIterator ön-artışlar.

İkinci sözdizimi, geçerli VectorViewIterator'u aşamalı olarak atar. İkinci `int` sözdiziminde tür, gerçek bir tamsayı operand değil, artış sonrası işlemi gösterir.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-inequality"></a>VectorViewIterator::operator!= Operatör

Geçerli VectorViewIterator'un belirli bir VectorViewIterator'a eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

akım `VectorViewIterator` *diğer*eşit değilse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than"></a>VectorViewIterator::operatör&lt; Operatörü

Geçerli VectorIterator'un belirli bir VectorIterator'dan daha az olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka `VectorIterator`bir .

### <a name="return-value"></a>Dönüş Değeri

akım `VectorIterator` *diğerinden*daha az ise **doğrudur;** aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a>VectorViewIterator::operator&lt;= Operatör

Akımın `VectorIterator` belirtilenden `VectorIterator`küçük mü yoksa eşit mi olduğunu gösterir.

### <a name="syntax"></a>Sözdizimi

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka `VectorIterator`bir .

### <a name="return-value"></a>Dönüş Değeri

akım `VectorIterator` *diğerinden*daha az veya eşitse **doğrudur;** aksi takdirde, **yanlış**.

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus"></a>VectorViewIterator::operatör- Operatör

Yeni bir yineleyici veren geçerli yineleyiciden belirli sayıda öğe veya yinelenenler arasındaki öğe sayısını veren geçerli yineleyiciden belirtilen bir yineleyici çıkarılır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir dizi öğe.

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleci sözdizimi, geçerli VectorViewIterator'dan daha az eleman olan `n` bir VectorViewIterator nesnesini döndürür. İkinci işleç sözdizimi, akım ve `other` VectorViewIterator arasındaki eleman sayısını döndürür.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus-equals"></a>VectorViewIterator::operator+= Operatör

Geçerli VectorViewIterator'u belirtilen yer değiştirmeyle karşılar.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Tamsayı deplasmanı.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorViewIterator.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus"></a>VectorViewIterator::operator+ Operatör

Belirtilen VectorViewIterator'dan belirtilen deplasmantaki elemana başvuran bir VectorViewIterator döndürür.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator operator+(difference_type n) const;

template <typename T>
inline VectorViewIterator<T> operator+
   (ptrdiff_t n,
   const VectorViewIterator<T>& i);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
İkinci sözdiziminde, VectorViewIterator'un tür adı.

*n*<br/>
Bir sonda değişimi.

*Ⅰ*<br/>
İkinci sözdiziminde, bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdiziminde, geçerli VectorViewIterator'dan belirtilen yer değiştirme öğesine başvuran bir VectorViewIterator.

İkinci sözdiziminde, parametrenin `i`başlangıcından itibaren belirtilen yer değiştirme öğesine başvuran bir VectorViewIterator.

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus-assign"></a>VectorViewIterator::operator-= Operatör

Geçerli VectorIterator'u belirtilen yer değiştirmeyle erteler.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir sonda değişimi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectorviewiteratoroperator"></a><a name="operator-at"></a>VectorViewIterator::operatör\[\]

Geçerli VectorViewIterator'dan belirtilen bir yer değiştirme öğesine bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir sonda değişimi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator'daki öğeler tarafından `n` yer değiştiren öğe.

## <a name="vectorviewiteratorvectorviewiterator-constructor"></a><a name="ctor"></a>VectorViewIterator::VectorViewIterator Constructor

VectorViewIterator sınıfının yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>Parametreler

*v*<br/>
Bir IVectorView\<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği varsayılan oluşturucudur. İkinci sözdizimi örneği, IVectorView\<T> nesnesinden bir VectorViewIterator oluşturmak için kullanılan açık bir oluşturucudur.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
