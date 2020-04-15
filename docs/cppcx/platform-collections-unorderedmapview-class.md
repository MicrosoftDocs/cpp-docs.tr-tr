---
title: Platform::Collections::UnorderedMapView Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: 8f8bc3490fba28232cdab3ea189dd9cfcc8d0650
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354388"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView Sınıfı

Anahtar değeri çiftleri topluluğu olan *bir haritaya*salt okunur görünümü temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = ::std::equal_to<K>>
ref class UnorderedMapView sealed;
```

#### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar değeri çiftindeki anahtarın türü.

*V*<br/>
Anahtar değeri çiftindeki değerin türü.

*C*<br/>
Eşitlik için iki temel değeri karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak, [\<std::equal_to K>](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>Açıklamalar

UnorderedMapView, [Windows:Foundation::Collections::IMapView\<K,V>](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirimi üzerinden geçirilen ve uygulama ikili arabirimi (ABI) üzerinden geçirilen somut bir C++ uygulamasıdır. Daha fazla bilgi için [Bkz. Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[SırasızMapView::SırasızMapView](#ctor)|SıradışıMapView sınıfının yeni bir örneğini başlattı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[SırasızMapView::İlk](#first)|Harita görünümündeki ilk öğeye başharflendirilen bir yineleyici döndürür.|
|[SırasızMapView::HasKey](#haskey)|Geçerli UnorderedMapView'in belirtilen anahtarı içerip içerip içermediğini belirler.|
|[SırasızMapView::Arama](#lookup)|Geçerli Sıradışı MapView nesnesinde belirtilen anahtardaki öğeyi alır.|
|[SırasızMapView::Boyut](#size)|Geçerli Sıradışı MapView nesnesindeki öğe sayısını verir.|
|[SırasızMapView::Bölme](#split)|Özgün bir UnorderedMapView nesnesi iki UnorderedMapView nesnesine böler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMapView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="unorderedmapviewfirst-method"></a><a name="first"></a>SırasızMapView::İlk Yöntem

İlk [Windows::Foundation::Collections::IKeyValuePair\<K,V>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) öğesini sıralanmamış haritada belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Dönüş Değeri

Harita görünümündeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myMapView->First();`.

## <a name="unorderedmapviewhaskey-method"></a><a name="haskey"></a>SırasızMapView::HasKey Yöntemi

Geçerli UnorderedMap'in belirtilen anahtarı içerip içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Öğeyi bulmak için kullanılan anahtar. Türü `key` k *türüdür.*

### <a name="return-value"></a>Dönüş Değeri

anahtar bulunursa **doğru;** aksi takdirde, **yanlış**.

## <a name="unorderedmapviewlookup-method"></a><a name="lookup"></a>SırasızMapView::Arama Yöntemi

Belirtilen K türünün anahtarıyla ilişkili V türünün değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Sırasız MapView'deki bir öğeyi bulmak için kullanılan anahtar. Türü `key` k *türüdür.*

### <a name="return-value"></a>Dönüş Değeri

`key`' ile eşleştirilmiş olan değer. İade değerinin türü *V*türüdür.

## <a name="unorderedmapviewsize-method"></a><a name="size"></a>SırasızMapView::Boyut Yöntemi

Windows sayısını [döndürür::Foundation::Collections::IKeyValuePair\<K,V>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) öğeleri SırasızMapView.)'de.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız MapView'daki öğelerin sayısı.

## <a name="unorderedmapviewsplit-method"></a><a name="split"></a>SırasızMapView::Bölme Yöntemi

Geçerli UnorderedMapView nesnesini iki SıradışıMapView nesnesine böler. Bu yöntem çalışmıyor.

### <a name="syntax"></a>Sözdizimi

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>Parametreler

*ilkBölüm*<br/>
Özgün UnorderedMapView nesnesinin ilk bölümü.

*secondPartition*<br/>
Özgün UnorderedMapView nesnesinin ikinci bölümü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem işlevsel değildir; Hiçbir şey yapmaz.

## <a name="unorderedmapviewunorderedmapview-constructor"></a><a name="ctor"></a>SırasızMapView::SırasızMapView Oluşturucu

SıradışıMapView sınıfının yeni bir örneğini başlattı.

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
Yer bulmak için öğelerin sayısı.

*ınit*<br/>
SırasızMapView'in daktison adı.

*H*<br/>
Bir anahtar için karma değer edebilen bir işlev nesnesi. Varsayılan [std::hash\<K>](../standard-library/hash-class.md) destekleyen `std::hash` türleri için.

*P*<br/>
Eşitliklerini belirlemek için iki anahtarı karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan [\<std::equal_to K>](../standard-library/equal-to-struct.md).

*M*<br/>
UnorderedMapView'i başlatmada kullanılan [bir std::unordered_map](../standard-library/unordered-map-class.md) için bir başvuru veya [Lvalues ve Rvalues.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ilk*<br/>
SıradışıMapView'i başlatmada kullanılan bir dizi öğedeki ilk öğenin giriş yineleyicisi.

*Son*<br/>
SıradışıMapView'i başlatmada kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform::Koleksiyonlar Namespace](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)
