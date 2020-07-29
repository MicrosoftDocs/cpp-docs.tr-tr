---
title: 'Platform:: Collections:: MapView Sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: 6c50825cb3003c2b1b63a25419ca67742c92b52f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215003"
---
# <a name="platformcollectionsmapview-class"></a>Platform:: Collections:: MapView Sınıfı

Anahtar-değer çiftleri koleksiyonu olan bir *haritada*salt okunurdur görünümü temsil eder.

## <a name="syntax"></a>Söz dizimi

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar-değer çiftindeki anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değerin türü.

*,*<br/>
İki öğe değerini eşleme anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: less \<K> ](../standard-library/less-struct.md).

### <a name="remarks"></a>Açıklamalar

MapView, uygulama ikili arabirimi (ABı) arasında geçirilen [Windows:: Foundation:: Collections:: \<K,V> ımapview](/uwp/api/windows.foundation.collections.imapview-2) arabiriminin somut bir C++ uygulamasıdır. Daha fazla bilgi için bkz. [Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[MapView:: MapView](#ctor)|MapView sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[MapView:: First](#first)|Harita görünümündeki ilk öğeye başlatılan bir yineleyici döndürür.|
|[MapView:: HasKey](#haskey)|Geçerli MapView 'ın belirtilen anahtarı içerip içermediğini belirler.|
|[MapView:: Lookup](#lookup)|Geçerli MapView nesnesinde belirtilen anahtardaki öğeyi alır.|
|[MapView:: size](#size)|Geçerli MapView nesnesindeki öğe sayısını döndürür.|
|[MapView:: Split](#split)|Orijinal bir MapView nesnesini iki MapView nesnesine böler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MapView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="mapviewfirst-method"></a><a name="first"></a>MapView:: First yöntemi

Harita görünümündeki ilk öğeyi belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Harita görünümündeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **`auto`** tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myMapView->First();`.

## <a name="mapviewhaskey-method"></a><a name="haskey"></a>MapView:: HasKey yöntemi

Geçerli MapView 'ın belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Söz dizimi

```

bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
MapView öğesini bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**`true`** anahtar bulunursa; Aksi takdirde, **`false`** .

## <a name="mapviewlookup-method"></a><a name="lookup"></a>MapView:: Lookup yöntemi

K türünde belirtilen anahtarla ilişkilendirilen V türü değerini alır.

### <a name="syntax"></a>Söz dizimi

```
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
MapView içindeki bir öğeyi bulmak için kullanılan anahtar. Türü `key` TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değer `key` . Dönüş değerinin türü, TypeName *V*.

## <a name="mapviewmapview-constructor"></a><a name="ctor"></a>MapView:: MapView Oluşturucusu

MapView sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>Parametreler

*Dengeleyici*<br/>
Geçerli MapView typeName.

*inin*<br/>
Eşleme anahtarları olarak iki öğe değerini karşılaştıran bir işlev nesnesi, MapView içinde göreli sıralarını tespit edebilir.

*m*<br/>
Geçerli MapView 'u başlatmak için kullanılan bir başvuru veya [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) `map Class` .

*adı*<br/>
Geçerli MapView 'ı başlatmak için kullanılan öğe aralığındaki ilk öğenin giriş yineleyicisi.

*soyadına*<br/>
Geçerli MapView 'ı başlatmak için kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

*Demiryolu*<br/>
Bir [std:: initializer_list \<K,V> ><std:](../standard-library/initializer-list-class.md) öğeleri MapView içine eklenecek olan:p AIR.

## <a name="mapviewsize-method"></a><a name="size"></a>MapView:: size yöntemi

Geçerli MapView nesnesindeki öğe sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli MapView içindeki öğe sayısı.

## <a name="mapviewsplit-method"></a><a name="split"></a>MapView:: Split yöntemi

Geçerli MapView nesnesini iki MapView nesnesine böler. Bu yöntem işlemsel değil.

### <a name="syntax"></a>Söz dizimi

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>Parametreler

*Ilkbölüm*<br/>
Özgün MapView nesnesinin ilk bölümü.

*secondPartition*<br/>
Özgün MapView nesnesinin ikinci bölümü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem işlemsel değil; hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)
