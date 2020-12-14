---
description: ': Platform:: Collections:: UnorderedMapView sınıfı hakkında daha fazla bilgi'
title: Platform::Collections::UnorderedMapView Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: 39f33fd75db92e81fa5321d8983b1b5ea9fce79a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252382"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView Sınıfı

Anahtar-değer çiftleri koleksiyonu olan bir *haritada* salt okunurdur görünümü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar-değer çiftindeki anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değerin türü.

*,*<br/>
İki anahtar değerini eşitlik için karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: equal_to \<K> ](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>Açıklamalar

UnorderedMapView, uygulama ikili arabirimi (ABı) arasında geçirilen [Windows:: Foundation:: Collections:: \<K,V> ımapview](/uwp/api/windows.foundation.collections.imapview-2) arabiriminin somut bir C++ uygulamasıdır. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMapView:: UnorderedMapView](#ctor)|UnorderedMapView sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMapView:: First](#first)|Harita görünümündeki ilk öğeye başlatılan bir yineleyici döndürür.|
|[UnorderedMapView:: HasKey](#haskey)|Geçerli UnorderedMapView 'ın belirtilen anahtarı içerip içermediğini belirler.|
|[UnorderedMapView:: Lookup](#lookup)|Geçerli UnorderedMapView nesnesinde belirtilen anahtardaki öğeyi alır.|
|[UnorderedMapView:: size](#size)|Geçerli UnorderedMapView nesnesindeki öğe sayısını döndürür.|
|[UnorderedMapView:: Split](#split)|Orijinal UnorderedMapView nesnesini iki UnorderedMapView nesnelerine böler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMapView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a> UnorderedMapView:: First yöntemi

Sıralanmamış eşlemede ilk [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğesini belirten bir yineleyici döndürür.

### <a name="syntax"></a>Syntax

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Dönüş Değeri

Harita görünümündeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **`auto`** tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myMapView->First();`.

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a> UnorderedMapView:: HasKey yöntemi

Geçerli UnorderedMap 'in belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Öğesini bulmak için kullanılan anahtar. Türü `key` TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**`true`** anahtar bulunursa; Aksi takdirde, **`false`** .

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a> UnorderedMapView:: Lookup yöntemi

K türünde belirtilen anahtarla ilişkilendirilen V türü değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
UnorderedMapView içindeki bir öğeyi bulmak için kullanılan anahtar. Türü `key` TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değer `key` . Dönüş değerinin türü, TypeName *V*.

## <a name="unorderedmapviewsize-method"></a><a name="size"></a> UnorderedMapView:: size yöntemi

UnorderedMapView içindeki [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğelerinin sayısını döndürür.

### <a name="syntax"></a>Syntax

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız MapView içindeki öğe sayısı.

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a> UnorderedMapView:: Split yöntemi

Geçerli UnorderedMapView nesnesini iki UnorderedMapView nesnelerine böler. Bu yöntem işlemsel değil.

### <a name="syntax"></a>Sözdizimi

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>Parametreler

*Ilkbölüm*<br/>
Orijinal UnorderedMapView nesnesinin ilk bölümü.

*secondPartition*<br/>
Orijinal UnorderedMapView nesnesinin ikinci bölümü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem işlemsel değil; hiçbir şey yapmaz.

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a> UnorderedMapView:: UnorderedMapView Oluşturucusu

UnorderedMapView sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
UnorderedMapView();
explicit UnorderedMapView(size_t n);
UnorderedMapView(size_t n, const H& h);
UnorderedMapView(size_t n, const H& h, const P& p);

explicit UnorderedMapView(
    const std::unordered_map<K, V, H, P>& m);
explicit UnorderedMapView(
    std::unordered_map<K, V, H, P>&& m);

template <typename InIt> UnorderedMapView(InIt first, InIt last );
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h );

template <typename InIt> UnorderedMapView(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p );

UnorderedMapView(std::initializer_list<std::pair<const K, V>);

UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h);

UnorderedMapView(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p );
```

### <a name="parameters"></a>Parametreler

*n*<br/>
İçin alan önceden ayrılacak öğe sayısı.

*Dengeleyici*<br/>
UnorderedMapView typeName.

*Olsun*<br/>
Bir anahtar için karma değer sağlayan bir işlev nesnesi. Tarafından desteklenen türler için [std: \<K> : Hash](../standard-library/hash-class.md) varsayılandır `std::hash` .

*P*<br/>
Eşitliklerini belirleyebilmek için iki anahtarı karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: equal_to \<K> ](../standard-library/equal-to-struct.md).

*m*<br/>
UnorderedMapView 'u başlatmak için kullanılan bir [std:: unordered_map](../standard-library/unordered-map-class.md) için bir başvuru veya [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) .

*adı*<br/>
UnorderedMapView 'ı başlatmak için kullanılan öğe aralığındaki ilk öğenin giriş yineleyicisi.

*soyadına*<br/>
UnorderedMapView 'ı başlatmak için kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform:: Collections ad alanı](../cppcx/platform-collections-namespace.md)<br/>
[Windows:: Foundation:: ımapview](/uwp/api/windows.foundation.collections.imapview-2)
