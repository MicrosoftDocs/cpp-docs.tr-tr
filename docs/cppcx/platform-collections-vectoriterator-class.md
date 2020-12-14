---
description: ': Platform:: Collections:: Vectorterator sınıfı hakkında daha fazla bilgi edinin'
title: 'Platform:: Collections:: Vectorterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
ms.openlocfilehash: ad572a8b426092fb0ddb39db44f387598674c988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253916"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform:: Collections:: Vectorterator sınıfı

Windows Çalışma Zamanı IVector arabiriminden türetilmiş nesneler için standart bir şablon kitaplığı Yineleyici sağlar.

VectorIterator, VectorProxy türünde öğeleri depolayan bir proxy Yineleyici \<T> . Ancak, proxy nesnesi neredeyse hiçbir şekilde Kullanıcı koduna görünmez. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
VectorIterator şablon sınıfının TypeName 'i.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|Bir işaretçi farkı (ptrdiff_t).|
|`iterator_category`|Rastgele erişim Yineleyici kategorisi (:: std:: random_access_iterator_tag).|
|`pointer`|\<T>Vektörtorterator 'in uygulanması için gerekli olan, bir iç türe yönelik bir işaretçi olan platform:: Collections::D euçlar:: VectorProxy.|
|`reference`|\<T>Vektörtorterator uygulamasının uygulanması için gerekli olan, bir iç türe yönelik bir başvuru olan platform:: Collections::D euçlar:: VectorProxy.|
|`value_type`|`T`TypeName.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[VectorIterator:: Vectorterator](#ctor)|VectorIterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[VectorIterator:: operator-Işleci](#operator-minus)|Geçerli yineleyiciden belirtilen sayıda öğeyi, yeni bir yineleyici oluşturan ya da geçerli yineleyiciden belirtilen bir yineleyiciyi, yineleyiciler arasındaki öğe sayısını çıkaran şekilde çıkartır.|
|[VectorIterator:: operator--Işleci](#operator-decrement)|Geçerli Vektörtorterator 'ı azaltır.|
|[VectorIterator:: operator! = Işleci](#operator-inequality)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator öğesine eşit olup olmadığını gösterir.|
|[VectorIterator:: operator * Işleci](#operator-dereference)|Geçerli VectorIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorIterator:: işleci\[\]](#operator-at)|Geçerli VectorIterator öğesinden belirtilen bir öteleme olan öğeye bir başvuru alır.|
|[VectorIterator:: operator + Işleci](#operator-plus)|Belirtilen VectorIterator öğesinden belirtilen yer alan öğeye başvuran bir VectorIterator döndürür.|
|[VectorIterator:: operator + + Işleci](#operator-increment)|Geçerli Vektörtorterator 'ı arttırır.|
|[VectorIterator:: operator + = Işleci](#operator-plus-assign)|Belirtilen öteleme ile geçerli Vektörtorterator 'ı arttırır.|
|[VectorIterator:: operator< Işleci](#operator-less-than)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden küçük olup olmadığını gösterir.|
|[VectorIterator:: operator \< = işleci](#operator-less-than-or-equals)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden küçük veya bu değere eşit olup olmadığını gösterir.|
|[VectorIterator:: operator-= Işleci](#operator-minus-equals)|Belirtilen öteleme ile geçerli Vektörtorterator 'ı azaltır.|
|[VectorIterator:: operator = = Işleci](#operator-equality)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerine eşit olup olmadığını gösterir.|
|[VectorIterator:: operator> Işleci](#operator-greater-than)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden büyük olup olmadığını gösterir.|
|[VectorIterator:: operator-> Işleci](#operator-arrow)|Geçerli VectorIterator tarafından başvurulan öğenin adresini alır.|
|[VectorIterator:: operator>= Işleci](#operator-greater-than-or-equals)|Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden büyük veya bu değere eşit olup olmadığını gösterir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorIterator`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="vectoriteratoroperator-gt-operator"></a><a name="operator-arrow"></a> VectorIterator:: operator- &gt; işleci

Geçerli VectorIterator tarafından başvurulan öğenin adresini alır.

### <a name="syntax"></a>Syntax

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından başvurulan öğenin değeri.

Dönüş değerinin türü, bu işlecin uygulanması için gerekli olan belirtilmemiş bir iç türdür.

## <a name="vectoriteratoroperator---operator"></a><a name="operator-decrement"></a> VectorIterator:: operator--Işleci

Geçerli Vektörtorterator 'ı azaltır.

### <a name="syntax"></a>Syntax

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi, ' i azaltır ve ardından geçerli Vektörtorterator ' i döndürür. İkinci sözdizimi, geçerli VectorIterator öğesinin bir kopyasını döndürür ve ardından geçerli VectorIterator 'ı azaltır.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator sözdizimi, geçerli Vektörtorterator öğesini önceden azaltır.

İkinci sözdizimi sonrası, geçerli Vektörtorterator ' i azaltır. **`int`** İkinci söz diziminde tür, gerçek bir tamsayı işleneni değil, azaltma sonrası bir işlemi gösterir.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-dereference"></a> VectorIterator:: operator \* işleci

Geçerli VectorIterator tarafından belirtilen öğenin adresini alır.

### <a name="syntax"></a>Syntax

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından belirtilen öğe.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-equality"></a> VectorIterator:: operator = = Işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator *diğer* bir değere eşitse; Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than"></a> VectorIterator:: operator &gt; işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator *bundan büyükse;* Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperatorgt-operator"></a><a name="operator-greater-than-or-equals"></a> VectorIterator:: operator &gt; = işleci

Geçerli VectorIterator 'ın belirtilen VectorIterator değerinden büyük veya bu değere eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator öğesinden büyükse veya buna *eşitse;* Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperator-operator"></a><a name="operator-increment"></a> VectorIterator:: operator + + Işleci

Geçerli Vektörtorterator 'ı arttırır.

### <a name="syntax"></a>Syntax

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi artar ve ardından geçerli Vektörtorterator öğesini döndürür. İkinci sözdizimi, geçerli VectorIterator öğesinin bir kopyasını döndürür ve ardından geçerli Vektörtorterator 'ı arttırır.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator sözdizimi, geçerli Vektörtorterator öğesini önceden arttırır.

İkinci sözdizimi, son vektör terator ' i arttırır. **`int`** İkinci sözdiziminde tür, gerçek bir tamsayı işleneni değil, artırma sonrası bir işlemi gösterir.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-inequality"></a> VectorIterator:: operator! = Işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator öğesine eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator *diğer* değere eşit değilse; Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than"></a> VectorIterator:: operator &lt; işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden küçük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator *varsayılandan* küçükse; Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperatorlt-operator"></a><a name="operator-less-than-or-equals"></a> VectorIterator:: operator &lt; = işleci

Geçerli VectorIterator 'ın belirtilen bir VectorIterator değerinden küçük veya bu değere eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli VectorIterator *diğer* değerden küçükse veya buna eşitse; Aksi takdirde, **`false`** .

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus"></a> VectorIterator:: operator-Işleci

Geçerli yineleyiciden belirtilen sayıda öğeyi, yeni bir yineleyici oluşturan ya da geçerli yineleyiciden belirtilen bir yineleyiciyi, yineleyiciler arasındaki öğe sayısını çıkaran şekilde çıkartır.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir dizi öğe.

*farklı*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sözdizimi, `n` geçerli vectoriterator öğesinden daha az öğe olan bir VectorIterator nesnesi döndürüyor. İkinci işleç sözdizimi, geçerli ve vektörtorterator arasındaki öğe sayısını döndürür `other` .

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus-assign"></a> VectorIterator:: operator + = Işleci

Belirtilen öteleme ile geçerli Vektörtorterator 'ı arttırır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectoriteratoroperator-operator"></a><a name="operator-plus"></a> VectorIterator:: operator + Işleci

Belirtilen VectorIterator öğesinden belirtilen yer alan öğeye başvuran bir VectorIterator döndürür.

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
İkinci sözdiziminde, VectorIterator typeName.

*n*<br/>
Bir tamsayı değiştirme.

*i*<br/>
İkinci sözdiziminde, bir Vectorterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdiziminde, geçerli VectorIterator öğesinden belirtilen yer alan öğeye başvuran bir Vectorterator.

İkinci sözdiziminde, parametrenin başlangıcından belirtilen ötede öğeye başvuran bir Vectorterator `i` .

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği

## <a name="vectoriteratoroperator--operator"></a><a name="operator-minus-equals"></a> VectorIterator:: operator-= Işleci

Belirtilen öteleme ile geçerli Vektörtorterator 'ı azaltır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="vectoriteratoroperator"></a><a name="operator-at"></a> VectorIterator:: işleci\[\]

Geçerli VectorIterator öğesinden belirtilen bir öteleme olan öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı değiştirme.

### <a name="return-value"></a>Dönüş Değeri

`n`Geçerli VectorIterator öğesinden öğeler tarafından yer alan öğe.

## <a name="vectoriteratorvectoriterator-constructor"></a><a name="ctor"></a> VectorIterator:: Vectorterator Oluşturucusu

VectorIterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>Parametreler

*Yönetim*<br/>
Bir IVector \<T> nesnesi.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği varsayılan oluşturucudur. İkinci sözdizimi örneği bir IVector nesnesinden VectorIterator oluşturmak için kullanılan açık bir oluşturucudur \<T> .

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
