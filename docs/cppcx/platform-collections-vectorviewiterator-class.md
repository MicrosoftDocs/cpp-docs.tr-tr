---
title: 'Platform::Collections:: vectorviewıterator sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorViewIterator::VectorViewIterator
helpviewer_keywords:
- VectorViewIterator Class
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
ms.openlocfilehash: 0de4ffb8e72c21490f07ae164aa23ffcd524c2b8
ms.sourcegitcommit: 309dc532f13242854b47759cef846de59bb807f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2019
ms.locfileid: "58565668"
---
# <a name="platformcollectionsvectorviewiterator-class"></a>Platform::Collections:: vectorviewıterator sınıfı

Windows çalışma zamanını şuradan türetilmiş nesneler için bir standart Şablon kitaplığı yineleyiciler sağlayan`IVectorView` arabirimi.

`ViewVectorIterator` türünde öğeler depolayan bir ara sunucu yineleyici `VectorProxy<T>`. Ancak, proxy neredeyse hiç kullanıcı kodu tarafından nesnedir. Daha fazla bilgi için [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorViewIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Typename VectorViewIterator Şablon sınıfı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Bir rastgele erişim yineleyici kategorisi (:: std::random_access_iterator_tag).|
|`pointer`|VectorViewIterator uygulanması için gerekli olan iç tür için bir işaretçi.|
|`reference`|VectorViewIterator uygulanması için gerekli olan iç tür referansı.|
|`value_type`|`T` Typename.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[VectorViewIterator::VectorViewIterator](#ctor)|VectorViewIterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[VectorViewIterator::operator- Operator](#operator-minus)|Yineleyici arasındaki öğelerin sayısını sonuçlanmıyor geçerli yineleyici öğesinden yeni bir yineleyici veya belirtilen bir yineleyici sağlayan geçerli yineleyici öğelerden birini ya da bir belirtilen sayıyı çıkartır.|
|[VectorViewIterator::operator-- Operator](#operator-decrement)|Geçerli VectorViewIterator azaltır.|
|[VectorViewIterator::operator!= Operator](#operator-inequality)|Geçerli VectorViewIterator için belirtilen bir VectorViewIterator eşit olup olmadığını gösterir.|
|[VectorViewIterator::operator * işleci](#operator-dereference)|Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorViewIterator::operator\[\]](#operator-at)|Geçerli VectorViewIterator öğesinden belirtilen bir yer olan öğeye bir başvuru alır.|
|[VectorViewIterator::operator+ Operator](#operator-plus)|Belirtilen VectorViewIterator belirtilen öteleme öğeye başvuran bir VectorViewIterator döndürür.|
|[VectorViewIterator::operator++ Operator](#operator-increment)|Geçerli VectorViewIterator artırır.|
|[VectorViewIterator::operator+= Operator](#operator-plus-equals)|Geçerli VectorViewIterator tarafından belirtilen öteleme artırır.|
|[VectorViewIterator::operator < işleci](#operator-less-than)|Geçerli VectorViewIterator belirtilen VectorViewIterator küçük olup olmadığını belirtir.|
|[VectorViewIterator::operator\<= Operator](#operator-less-than-or-equals)|Geçerli VectorViewIterator ya da belirtilen VectorViewIterator eşit olup olmadığını belirtir.|
|[VectorViewIterator::operator-= Operator](#operator-minus-assign)|Belirtilen öteleme tarafından geçerli VectorViewIterator azaltır.|
|[VectorViewIterator::operator== Operator](#operator-equality)|Geçerli VectorViewIterator için belirtilen bir VectorViewIterator eşit olup olmadığını gösterir.|
|[VectorViewIterator::operator > işleci](#operator-greater-than)|Geçerli VectorViewIterator belirtilen bir VectorViewIterator büyük olup olmadığını gösterir.|
|[VectorViewIterator::operator -> işleci](#operator-arrow)|Geçerli VectorViewIterator tarafından başvurulan bir öğenin adresi alır.|
|[VectorViewIterator::operator>= Operator](#operator-greater-than-or-equals)|Geçerli VectorViewIterator büyüktür veya belirtilen VectorViewIterator eşit olup olmadığını belirtir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorViewIterator`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="operator-arrow"></a>  VectorViewIterator::operator -&gt; işleci

Geçerli VectorViewIterator tarafından başvurulan bir öğenin adresi alır.

### <a name="syntax"></a>Sözdizimi

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından başvurulan öğenin değeri.

Dönüş değerinin türü bu işleci uygulanması için gerekli olan belirtilmemiş bir iç türüdür.

## <a name="operator-decrement"></a>  VectorViewIterator::operator--işleci

Geçerli VectorViewIterator azaltır.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator--();
VectorViewIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk söz dizimi azaltır ve ardından geçerli VectorViewIterator döndürür. İkinci sözdizimi geçerli VectorViewIterator geçerli VectorViewIterator ve ardından azaltır bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator söz dizimi geçerli VectorViewIterator önceden decrements.

İkinci sözdizimi geçerli VectorViewIterator sonrası decrements. `int` İkinci söz diziminde türü, gerçek tamsayı işlenen bir sonrası azaltma işlemi gösterir.

## <a name="operator-dereference"></a>  VectorViewIterator::operator\* işleci

Geçerli VectorViewIterator tarafından belirtilen öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorViewIterator tarafından belirtilen öğe.

## <a name="operator-equality"></a>  VectorViewIterator::operator== Operator

Geçerli VectorViewIterator için belirtilen bir VectorViewIterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `VectorViewIterator` eşittir *diğer*; Aksi takdirde **false**.

## <a name="operator-greater-than"></a>  VectorViewIterator::operator&gt; işleci

Geçerli VectorViewIterator belirtilen bir VectorViewIterator büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```

bool operator>(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorViewIterator büyükse *diğer*; Aksi takdirde **false**.

## <a name="operator-greater-than-or-equals"></a>  VectorViewIterator::operator&gt;= işleci

Belirtir olup olmadığını geçerli `VectorViewIterator` büyüktür veya eşittir belirtilen `VectorViewIterator`.

### <a name="syntax"></a>Sözdizimi

```

bool operator>=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `VectorViewIterator` büyüktür veya eşittir *diğer*; Aksi takdirde **false**.

## <a name="operator-increment"></a>  VectorViewIterator::operator ++ işleci

Geçerli VectorViewIterator artırır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator& operator++();
VectorViewIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk söz dizimi artırır ve geçerli VectorViewIterator döndürür. İkinci sözdizimi geçerli VectorViewIterator bir kopyasını döndürür ve ardından geçerli VectorViewIterator artırır.

### <a name="remarks"></a>Açıklamalar

İlk VectorViewIterator söz dizimi geçerli VectorViewIterator önceden artırır.

İkinci sözdizimi geçerli VectorViewIterator sonrası artırır. `int` İkinci söz diziminde türü sonrası artırma işlemi, gerçek tamsayı işlenen gösterir.

## <a name="operator-inequality"></a>  VectorViewIterator::operator! = işleci

Geçerli VectorViewIterator için belirtilen bir VectorViewIterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `VectorViewIterator` eşit değildir *diğer*; Aksi takdirde **false**.

## <a name="operator-less-than"></a>  VectorViewIterator::operator&lt; işleci

Geçerli VectorIterator belirtilen VectorIterator küçük olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```
bool operator<(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir `VectorIterator`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `VectorIterator` olduğu küçüktür *diğer*; Aksi takdirde **false**.

## <a name="operator-less-than-or-equals"></a>  VectorViewIterator::operator&lt;= işleci

Belirtir olup olmadığını geçerli `VectorIterator` değerinden küçük veya eşit belirtilen bir `VectorIterator`.

### <a name="syntax"></a>Sözdizimi

```

bool operator<=(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir `VectorIterator`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa geçerli `VectorIterator` küçüktür veya eşittir *diğer*; Aksi takdirde **false**.

## <a name="operator-minus"></a>  VectorViewIterator::operator-işleci

Yineleyici arasındaki öğelerin sayısını sonuçlanmıyor geçerli yineleyici öğesinden yeni bir yineleyici veya belirtilen bir yineleyici sağlayan geçerli yineleyici öğelerden birini ya da bir belirtilen sayıyı çıkartır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator operator-(difference_type n) const;

difference_type operator-(const VectorViewIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Öğe sayısı.

*Diğer*<br/>
Başka bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sözdizimi bir VectorViewIterator nesnesini döndürür `n` öğeleri geçerli VectorViewIterator küçüktür. İkinci işleç sözdizimi arasında geçerli öğe sayısını döndürür ve `other` VectorViewIterator.

## <a name="operator-plus-equals"></a>  VectorViewIterator::operator += işleci

Geçerli VectorViewIterator tarafından belirtilen öteleme artırır.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorViewIterator.

## <a name="operator-plus"></a>  VectorViewIterator::operator + işleci

Belirtilen VectorViewIterator belirtilen öteleme öğeye başvuran bir VectorViewIterator döndürür.

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
İkinci sözdizimi, VectorViewIterator tür adı.

*n*<br/>
Bir tamsayı yer değiştirme.

*i*<br/>
İkinci sözdizimi, bir VectorViewIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi, geçerli VectorViewIterator belirtilen öteleme öğeye başvuran bir VectorViewIterator.

İkinci sözdiziminde, parametre başlangıcından itibaren belirtilen öteleme öğeye başvuran bir VectorViewIterator `i`.

## <a name="operator-minus-assign"></a>  VectorViewIterator::operator-= Operator

Belirtilen öteleme tarafından geçerli VectorIterator azaltır.

### <a name="syntax"></a>Sözdizimi

```
VectorViewIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="operator-at"></a>  VectorViewIterator::operator\[\]

Geçerli VectorViewIterator öğesinden belirtilen bir yer olan öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Tarafından değişmiş olan zamanda öğesi `n` geçerli VectorViewIterator öğeleri.

## <a name="ctor"></a>  VectorViewIterator::VectorViewIterator Oluşturucusu

VectorViewIterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```

VectorViewIterator();

explicit VectorViewIterator(
   Windows::Foundation::Collections::IVectorView<T>^ v
);
```

### <a name="parameters"></a>Parametreler

*v*<br/>
Bir IVectorView\<T > nesne.

### <a name="remarks"></a>Açıklamalar

İlk söz dizimi varsayılan oluşturucu örnektir. İkinci sözdizimi bir IVectorView gelen bir VectorViewIterator oluşturmak için kullanılan açık bir oluşturucu örnektir\<T > nesne.

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)
