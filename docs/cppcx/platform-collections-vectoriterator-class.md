---
title: 'Platform::Collections:: vectorıterator sınıfı | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorIterator::VectorIterator
dev_langs:
- C++
helpviewer_keywords:
- VectorIterator Class
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 668365cf69fc3457efc615a5fa0da2c24b3cb02e
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162392"
---
# <a name="platformcollectionsvectoriterator-class"></a>Platform::Collections:: vectorıterator sınıfı

Windows çalışma zamanı Ivector arabirimden türetilmiş nesneler için bir standart Şablon kitaplığı yineleyici sağlar.

VectorIterator VectorProxy türünde öğeler depolayan bir ara sunucu yineleyici olduğunu\<T >. Ancak, proxy neredeyse hiç kullanıcı kodu tarafından nesnedir. Daha fazla bilgi için [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).

## <a name="syntax"></a>Sözdizimi

```
template <typename T>
class VectorIterator;
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Typename VectorIterator Şablon sınıfı.

### <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|`difference_type`|İşaretçi farkı (ptrdiff_t).|
|`iterator_category`|Bir rastgele erişim yineleyici kategorisi (:: std::random_access_iterator_tag).|
|`pointer`|İç tür, Platform::Collections::Details::VectorProxy işaretçisi\<T >, yani VectorIterator uygulanması için gereklidir.|
|`reference`|İç tür, Platform::Collections::Details::VectorProxy başvuru\<T >,, diğer bir deyişle VectorIterator uygulanması için gereklidir.|
|`value_type`|`T` Typename.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[VectorIterator::VectorIterator](#ctor)|VectorIterator sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[VectorIterator::operator- Operator](#operator-minus)|Yineleyici arasındaki öğelerin sayısını sonuçlanmıyor geçerli yineleyici öğesinden yeni bir yineleyici veya belirtilen bir yineleyici sağlayan geçerli yineleyici öğelerden birini ya da bir belirtilen sayıyı çıkartır.|
|[VectorIterator::operator-- Operator](#operator-decrement)|Geçerli VectorIterator azaltır.|
|[VectorIterator::operator!= Operator](#operator-inequality)|Geçerli VectorIterator için belirtilen bir VectorIterator eşit olup olmadığını gösterir.|
|[VectorIterator::operator * işleci](#operator-dereference)|Geçerli VectorIterator tarafından belirtilen öğeye bir başvuru alır.|
|[VectorIterator::operator\[\]](#operator-at)|Geçerli VectorIterator öğesinden belirtilen bir yer olan öğeye bir başvuru alır.|
|[VectorIterator::operator + işleci](#operator-plus)|Belirtilen VectorIterator belirtilen öteleme öğeye başvuran bir VectorIterator döndürür.|
|[VectorIterator::operator++ Operator](#operator-increment)|Geçerli VectorIterator artırır.|
|[VectorIterator::operator += işleci](#operator-plus-assign)|Geçerli VectorIterator tarafından belirtilen öteleme artırır.|
|[VectorIterator::operator < işleci](#operator-less-than)|Geçerli VectorIterator belirtilen VectorIterator küçük olup olmadığını belirtir.|
|[VectorIterator::operator\<= işleci](#operator-less-than-or-equals)|Geçerli VectorIterator ya da belirtilen VectorIterator eşit olup olmadığını belirtir.|
|[VectorIterator::operator-= işleci](#operator-subtract-assign)|Belirtilen öteleme tarafından geçerli VectorIterator azaltır.|
|[VectorIterator::operator == işleci](#operator-equality)|Geçerli VectorIterator için belirtilen bir VectorIterator eşit olup olmadığını gösterir.|
|[VectorIterator::operator > işleci](#operator-greater-than)|Geçerli VectorIterator belirtilen bir VectorIterator büyük olup olmadığını gösterir.|
|[VectorIterator::operator -> işleci](#operator-arrow)|Geçerli VectorIterator tarafından başvurulan bir öğenin adresi alır.|
|[VectorIterator::operator > = işleci](#operator-greater-than-or-equal)|Geçerli VectorIterator büyüktür veya belirtilen VectorIterator eşit olup olmadığını belirtir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`VectorIterator`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="operator-arrow"></a>  VectorIterator::operator -&gt; işleci

Geçerli VectorIterator tarafından başvurulan bir öğenin adresi alır.

### <a name="syntax"></a>Sözdizimi

```
Detail::ArrowProxy<T> operator->() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından başvurulan öğenin değeri.

Dönüş değerinin türü bu işleci uygulanması için gerekli olan belirtilmemiş bir iç türüdür.

## <a name="operator-decrement"></a>  VectorIterator::operator--işleci

Geçerli VectorIterator azaltır.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator& operator--();
VectorIterator operator--(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk söz dizimi azaltır ve ardından geçerli VectorIterator döndürür. İkinci sözdizimi geçerli VectorIterator geçerli VectorIterator ve ardından azaltır bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator söz dizimi geçerli VectorIterator önceden decrements.

İkinci sözdizimi geçerli VectorIterator sonrası decrements. `int` İkinci söz diziminde türü, gerçek tamsayı işlenen bir sonrası azaltma işlemi gösterir.

## <a name="operator-dereference"></a>  VectorIterator::operator\* işleci

Geçerli VectorIterator tarafından belirtilen bir öğenin adresi alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator*() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli VectorIterator tarafından belirtilen öğe.

## <a name="operator-equality"></a>  VectorIterator::operator == işleci

Geçerli VectorIterator için belirtilen bir VectorIterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator==(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator eşitse *diğer*; Aksi takdirde **false**.

## <a name="operator-greater-than"></a>  VectorIterator::operator&gt; işleci

Geçerli VectorIterator belirtilen bir VectorIterator büyük olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator büyükse *diğer*; Aksi takdirde **false**.

## <a name="operator-greater-than-or-equals"></a>  VectorIterator::operator&gt;= işleci

Geçerli VectorIterator büyüktür veya belirtilen VectorIterator eşit olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator>=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator değerinden büyük veya ona eşit olup olmadığını *diğer*; Aksi takdirde **false**.

## <a name="operator-increment"></a>  VectorIterator::operator ++ işleci

Geçerli VectorIterator artırır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator++();
VectorIterator operator++(int);
```

### <a name="return-value"></a>Dönüş Değeri

İlk söz dizimi artırır ve geçerli VectorIterator döndürür. İkinci sözdizimi geçerli VectorIterator bir kopyasını döndürür ve ardından geçerli VectorIterator artırır.

### <a name="remarks"></a>Açıklamalar

İlk VectorIterator söz dizimi geçerli VectorIterator önceden artırır.

İkinci sözdizimi geçerli VectorIterator sonrası artırır. `int` İkinci söz diziminde türü sonrası artırma işlemi, gerçek tamsayı işlenen gösterir.

## <a name="operator-inequality"></a>  VectorIterator::operator! = işleci

Geçerli VectorIterator için belirtilen bir VectorIterator eşit olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```
bool operator!=(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator eşit değilse *diğer*; Aksi takdirde **false**.

## <a name="operator-less-than"></a>  VectorIterator::operator&lt; işleci

Geçerli VectorIterator belirtilen VectorIterator küçük olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator ise kısa *diğer*; Aksi takdirde **false**.

## <a name="operator-less-than-or-equals"></a>  VectorIterator::operator&lt;= işleci

Geçerli VectorIterator ya da belirtilen VectorIterator eşit olup olmadığını belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool operator<=(const VectorIterator& other) const
```

### <a name="parameters"></a>Parametreler

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

**doğru** geçerli VectorIterator küçük veya buna eşit olup olmadığı *diğer*; Aksi takdirde **false**.

## <a name="operator-minus"></a>  VectorIterator::operator-işleci

Yineleyici arasındaki öğelerin sayısını sonuçlanmıyor geçerli yineleyici öğesinden yeni bir yineleyici veya belirtilen bir yineleyici sağlayan geçerli yineleyici öğelerden birini ya da bir belirtilen sayıyı çıkartır.

### <a name="syntax"></a>Sözdizimi

```

VectorIterator operator-(difference_type n) const;

difference_type operator-(const VectorIterator& other) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Öğe sayısı.

*Diğer*<br/>
Başka bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk işleç sözdizimi bir VectorIterator nesnesini döndürür `n` öğeleri geçerli VectorIterator küçüktür. İkinci işleç sözdizimi arasında geçerli öğe sayısını döndürür ve `other` VectorIterator.

## <a name="operator-plus-assign"></a>  VectorIterator::operator += işleci

Geçerli VectorIterator tarafından belirtilen öteleme artırır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator+=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="operator-plus"></a>  ectorIterator::operator + işleci

Belirtilen VectorIterator belirtilen öteleme öğeye başvuran bir VectorIterator döndürür.

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
İkinci sözdizimi, VectorIterator tür adı.

*n*<br/>
Bir tamsayı yer değiştirme.

*i*<br/>
İkinci sözdizimi, bir VectorIterator.

### <a name="return-value"></a>Dönüş Değeri

İlk sözdizimi, geçerli VectorIterator belirtilen öteleme öğeye başvuran bir VectorIterator.

İkinci sözdiziminde, parametre başlangıcından itibaren belirtilen öteleme öğeye başvuran bir VectorIterator `i`.

### <a name="remarks"></a>Açıklamalar

İlk sözdizimi örneği

## <a name="operator-minus-equals"></a>  VectorIterator::operator-= işleci

Belirtilen öteleme tarafından geçerli VectorIterator azaltır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator& operator-=(difference_type n);
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş VectorIterator.

## <a name="operator-at"></a>  VectorIterator::operator\[\]

Geçerli VectorIterator öğesinden belirtilen bir yer olan öğeye bir başvuru alır.

### <a name="syntax"></a>Sözdizimi

```
reference operator[](difference_type n) const;
```

### <a name="parameters"></a>Parametreler

*n*<br/>
Bir tamsayı yer değiştirme.

### <a name="return-value"></a>Dönüş Değeri

Tarafından değişmiş olan zamanda öğesi `n` geçerli VectorIterator öğeleri.

## <a name="ctor"></a>  VectorIterator::VectorIterator Oluşturucusu

VectorIterator sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
VectorIterator();

explicit VectorIterator(
   Windows::Foundation::Collections::IVector<T>^ v);
```

### <a name="parameters"></a>Parametreler

*v*<br/>
Bir Ivector\<T > nesne.

### <a name="remarks"></a>Açıklamalar

İlk söz dizimi varsayılan oluşturucu örnektir. İkinci sözdizimi bir Ivector gelen bir VectorIterator oluşturmak için kullanılan açık bir oluşturucu örnektir\<T > nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)