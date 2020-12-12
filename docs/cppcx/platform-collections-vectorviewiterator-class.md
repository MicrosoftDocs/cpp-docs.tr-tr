---
description: ': Platform:: Collections:: Vectorviewwiterator sınıfı hakkında daha fazla bilgi edinin'
title: 'Platform:: Collections:: Vectorviewwiterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: f10d6c31e60c4f8deac2ba924ec5f9de6faec30c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176138"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform:: Collections:: Vectorviewwiterator sınıfı

Windows Çalışma Zamanı arabiriminden türetilmiş nesneler için standart bir şablon kitaplığı Yineleyici sağlar `IVectorView` .

`ViewVectorIterator` , türündeki öğeleri depolayan bir proxy Yineleyici `VectorProxy<T>` . Ancak, proxy nesnesi neredeyse hiçbir şekilde Kullanıcı koduna görünmez. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
VectorViewIterator şablon sınıfının TypeName 'i.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|Bir işaretçi farkı (ptrdiff_t).|
|`iterator_category`|Rastgele erişim Yineleyici kategorisi (:: std:: random_access_iterator_tag).|
|`pointer`|Vektörtorviewiterator uygulamasının uygulanması için gerekli olan bir iç tür işaretçisi.|
|`reference`|VectorViewIterator 'in uygulanması için gerekli olan bir iç türe başvuru.|
|`value_type`|`T`TypeName.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[VectorViewIterator:: Vectorviewwiterator](#ctor)|Vectorviewwiterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[VectorViewIterator:: operator-Işleci](#operator-minus)|Geçerli yineleyiciden belirtilen sayıda öğeyi, yeni bir yineleyici oluşturan ya da geçerli yineleyiciden belirtilen bir yineleyiciyi, yineleyiciler arasındaki öğe sayısını çıkaran şekilde çıkartır.|
|[VectorViewIterator:: operator--Işleci](#operator-decrement)|Geçerli Vektörtorviewiterator 'ı azaltır.|
|[VectorViewIterator:: operator! = Işleci](#operator-inequality)|Geçerli VectorViewIterator 'ın belirtilen bir VectorViewIterator değerine eşit olup olmadığını gösterir.|
|[VectorViewIterator:: operator * Işleci](#operator-dereference)|Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorViewIterator:: işleci\[\]](#operator-at)|Geçerli VectorViewIterator öğesinden belirtilen bir öteleme olan öğeye bir başvuru alır.|
|[VectorViewIterator:: operator + Işleci](#operator-plus)|Belirtilen Vectorviewwiterator öğesinden belirtilen yer alan öğeye başvuran bir Vectorviewwiterator döndürür.|
|[VectorViewIterator:: operator + + Işleci](#operator-increment)|Geçerli Vektörtorviewiterator değerini artırır.|
|[VectorViewIterator:: operator + = Işleci](#operator-plus-equals)|Belirtilen öteleme ile geçerli Vektörtorviewiterator öğesini arttırır.|
|[VectorViewIterator:: operator< Işleci](#operator-less-than)|Geçerli VectorViewIterator 'ın belirtilen bir Vectorviewwiterator değerinden küçük olup olmadığını gösterir.|
|[VectorViewIterator:: operator \< = işleci](#operator-less-than-or-equals)|Geçerli VectorViewIterator 'ın belirtilen bir VectorViewIterator değerinden küçük veya bu değere eşit olup olmadığını gösterir.|
|[VectorViewIterator:: operator-= Işleci](#operator-minus-assign)|Belirtilen öteleme ile geçerli Vektörtorviewiterator 'ı azaltır.|
|[VectorViewIterator:: operator = = Işleci](#operator-equality)|Geçerli VectorViewIterator 'ın belirtilen bir VectorViewIterator değerine eşit olup olmadığını gösterir.|
|[VectorViewIterator:: operator> Işleci](#operator-greater-than)|Geçerli VectorViewIterator 'ın belirtilen bir Vectorviewwiterator değerinden büyük olup olmadığını gösterir.|
|[VectorViewIterator:: operator-> Işleci](#operator-arrow)|Geçerli VectorViewIterator tarafından başvurulan öğenin adresini alır.|
|[VectorViewIterator:: operator>= Işleci](#operator-greater-than-or-equals)|Geçerli VectorViewIterator 'ın belirtilen bir Vectorviewwiterator değerinden büyük veya bu değere eşit olup olmadığını gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorViewIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="vectorviewiteratoroperator-gt-operator"></a><a name="operator-arrow"></a> VectorViewIterator:: operator- &gt; işleci

Geçerli VectorViewIterator tarafından başvurulan öğenin adresini alır.

### <a name="syntax"></a>Syntax

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından başvurulan öğenin değeri.

Dönüş değerinin türü, bu işlecin uygulanması için gerekli olan belirtilmemiş bir iç türdür.

## <a name="vectorviewiteratoroperator---operator"></a><a name="operator-decrement"></a> VectorViewIterator:: operator--Işleci

Geçerli Vektörtorviewiterator 'ı azaltır.

### <a name="syntax"></a>Syntax

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi, ve ardından geçerli Vektörtorviewiterator değerini azaltır. İkinci sözdizimi, geçerli VectorViewIterator 'in bir kopyasını döndürür ve ardından geçerli Vektörtorviewiterator değerini azaltır.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator sözdizimi, geçerli Vektörtorviewiterator ' i önceden azaltır.

İkinci sözdizimi sonrası, geçerli Vektörtorviewiterator ' i azaltır. **`int`** İkinci söz diziminde tür, gerçek bir tamsayı işleneni değil, azaltma sonrası bir işlemi gösterir.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-dereference"></a> VectorViewIterator:: operator \* işleci

Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Syntax

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından belirtilen öğe.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-equality"></a> VectorViewIterator:: operator = = Işleci

Geçerli VectorViewIterator 'ın belirtilen bir VectorViewIterator değerine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli varsa `VectorViewIterator` , tersi durumda  **`false`** .

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than"></a> VectorViewIterator:: operator &gt; işleci

Geçerli VectorViewIterator 'ın belirtilen bir Vectorviewwiterator değerinden büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorViewIterator *bundan büyükse;* Aksi takdirde, **`false`** .

## <a name="vectorviewiteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a> VectorViewIterator:: operator &gt; = işleci

Geçerli, `VectorViewIterator` belirtilen değere eşit veya ondan büyük olup olmadığını gösterir `VectorViewIterator` .

### <a name="syntax"></a>Sözdizimi

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli bir değerden `VectorViewIterator` büyükse veya buna eşitse, aksi takdirde **`false`** .

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-increment"></a> VectorViewIterator:: operator + + Işleci

Geçerli Vektörtorviewiterator değerini artırır.

### <a name="syntax"></a>Syntax

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artar ve ardından geçerli Vektörtorviewiterator öğesini döndürür. İkinci sözdizimi, geçerli VectorViewIterator öğesinin bir kopyasını döndürür ve ardından geçerli VectorViewIterator öğesini arttırır.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator sözdizimi, geçerli Vektörtorviewiterator öğesini önceden arttırır.

İkinci sözdizimi, geçerli Vektörtorviewiterator öğesini arttırır. **`int`** İkinci sözdiziminde tür, gerçek bir tamsayı işleneni değil, artırma sonrası bir işlemi gösterir.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-inequality"></a> VectorViewIterator:: operator! = Işleci

Geçerli VectorViewIterator 'ın belirtilen bir VectorViewIterator değerine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli, `VectorViewIterator` *diğer* bir değere eşit değilse, tersi durumda **`false`** .

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than"></a> VectorViewIterator:: operator &lt; işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden küçük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir `VectorIterator` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli `VectorIterator` *diğer* değerinden küçükse, aksi durumda, **`false`** .

## <a name="vectorviewiteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a> VectorViewIterator:: operator &lt; = işleci

Geçerli `VectorIterator` bir belirtilen değere eşit veya ondan küçük olup olmadığını gösterir `VectorIterator` .

### <a name="syntax"></a>Sözdizimi

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir `VectorIterator` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli, `VectorIterator` *diğer* bir değerden küçükse veya eşitse, aksi durumda **`false`** .

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus"></a> VectorViewIterator:: operator-Işleci

Geçerli yineleyiciden belirtilen sayıda öğeyi, yeni bir yineleyici oluşturan ya da geçerli yineleyiciden belirtilen bir yineleyiciyi, yineleyiciler arasındaki öğe sayısını çıkaran şekilde çıkartır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir dizi öğe.

*farklı*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sözdizimi, `n` geçerli vectorviewiterator öğesinden daha az öğe olan bir vectorviewiterator nesnesi döndürür. İkinci işleç sözdizimi, geçerli ve `other` vektörtorviewiterator arasındaki öğe sayısını döndürür.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus-equals"></a> VectorViewIterator:: operator + = Işleci

Belirtilen öteleme ile geçerli Vektörtorviewiterator öğesini arttırır.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorViewIterator.

## <a name="vectorviewiteratoroperator-operator"></a><a name="operator-plus"></a> VectorViewIterator:: operator + Işleci

Belirtilen Vectorviewwiterator öğesinden belirtilen yer alan öğeye başvuran bir Vectorviewwiterator döndürür.

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
İkinci sözdiziminde, VectorViewIterator typeName.

*n*<br/>
Bir tamsayı değiştirme.

*i*<br/>
İkinci sözdiziminde, bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdiziminde, geçerli VectorViewIterator öğesinden belirtilen yer alan öğeye başvuran bir VectorViewIterator.

İkinci sözdiziminde, parametrenin başlangıcından belirtilen ötede öğeye başvuran bir VectorViewIterator `i` .

## <a name="vectorviewiteratoroperator--operator"></a><a name="operator-minus-assign"></a> VectorViewIterator:: operator-= Işleci

Belirtilen öteleme ile geçerli Vektörtorterator 'ı azaltır.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectorviewiteratoroperator"></a><a name="operator-at"></a> VectorViewIterator:: işleci\[\]

Geçerli VectorViewIterator öğesinden belirtilen bir öteleme olan öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

`n`Geçerli VectorViewIterator öğesinden öğeler tarafından yer alan öğe.

## <a name="vectorviewiteratorvectorviewiterator-constructor"></a><a name="ctor"></a> VectorViewIterator:: Vectorviewwiterator Oluşturucusu

Vectorviewwiterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>Parametreler

*Yönetim*<br/>
Bir ıvectorview \<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği varsayılan oluşturucudur. İkinci sözdizimi örneği bir ıvectorview nesnesinden bir VectorViewIterator oluşturmak için kullanılan açık bir oluşturucudur \<T> .

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
