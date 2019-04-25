---
title: Platform::Collections::UnorderedMapView Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
ms.openlocfilehash: ebda6f179c365aaa009eb45425a36058105def10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161642"
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView Sınıfı

Bir salt okunur görünüme temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.

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
Anahtar-değer çifti anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değer türü.

*C*<br/>
Eşitlik için iki anahtar değeri karşılaştıran bir işlev nesnesi sağlayan tür. Varsayılan olarak, [std::equal_to\<K >](../standard-library/equal-to-struct.md)

### <a name="remarks"></a>Açıklamalar

UnorderedMapView olan somut bir C++ uygulaması [Windows::Foundation::Collections::IMapView\<K, V >](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) uygulama ikili arabiriminde (ABI) geçirilen arabirimi. Daha fazla bilgi için [koleksiyonları (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMapView::UnorderedMapView](#ctor)|UnorderedMapView sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMapView::First](#first)|Harita görünümünü içindeki ilk öğeyi başlatılan bir yineleyiciyi döndürür.|
|[UnorderedMapView::HasKey](#haskey)|Geçerli UnorderedMapView belirtilen anahtarı içerip içermediğini belirler.|
|[UnorderedMapView::Lookup](#lookup)|Öğe geçerli UnorderedMapView nesnedeki belirtilen anahtarı alır.|
|[UnorderedMapView::Size](#size)|Geçerli UnorderedMapView nesnesinde öğelerin sayısını döndürür.|
|[UnorderedMapView::Split](#split)|Özgün UnorderedMapView nesneyi iki UnorderedMapView nesnelerini böler.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMapView`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="first"></a>  UnorderedMapView::First yöntemi

İlk belirten bir yineleyici döndüren [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) sıralanmamış eşleme öğesi.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
    First();
```

### <a name="return-value"></a>Dönüş Değeri

Harita Görünümü'nde ilk öğeyi belirleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin: `auto x = myMapView->First();`

## <a name="haskey"></a>  UnorderedMapView::HasKey yöntemi

Geçerli UnorderedMap belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Öğeyi bulmak için kullanılan anahtar. Türünü `key` TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** anahtar bulunduysa, **false**.

## <a name="lookup"></a>  UnorderedMapView::Lookup yöntemi

V türünün türü K. belirtilen anahtarla ilişkili değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bir öğe içinde UnorderedMapView bulmak için kullanılan anahtar. Türünü `key` TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değeri `key`. Dönüş değeri typename türüdür *V*.

## <a name="size"></a>  UnorderedMapView::Size yöntemi

Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) UnorderedMapView öğeleri.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız MapView içindeki öğe sayısı.

## <a name="split"></a>  UnorderedMapView::Split yöntemi

Geçerli UnorderedMapView nesne iki UnorderedMapView nesnelerini böler. Bu yöntem çalışmaz.

### <a name="syntax"></a>Sözdizimi

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K,V>^ * secondPartition);
```

### <a name="parameters"></a>Parametreler

*firstPartition*<br/>
Özgün UnorderedMapView nesnenin ilk bölümü.

*secondPartition*<br/>
Özgün UnorderedMapView nesnenin ikinci bölümü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, işlemsel değildir; hiçbir şey yapmaz.

## <a name="ctor"></a>  UnorderedMapView::UnorderedMapView Oluşturucusu

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
Alan erişinceye öğe sayısı.

*InIt*<br/>
UnorderedMapView tür adı.

*H*<br/>
Bir anahtar için bir karma değer için bir işlev nesnesi. Varsayılan olarak [std::hash\<K >](../standard-library/hash-class.md) türleri için `std::hash` destekler.

*P*<br/>
Kendi eşitlik belirlemek için iki anahtarı karşılaştıran işlev nesnesi sağlayan tür. Varsayılan olarak [std::equal_to\<K >](../standard-library/equal-to-struct.md).

*m*<br/>
Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::unordered_map](../standard-library/unordered-map-class.md) UnorderedMapView başlatmak için kullanılır.

*ilk*<br/>
UnorderedMapView başlatmak için kullanılan öğelerin bir aralıktaki ilk öğenin bir giriş yineleyici.

*Son*<br/>
İlk öğenin UnorderedMapView başlatmak için kullanılan öğelerin bir aralığını sonra bir giriş yineleyici.

## <a name="see-also"></a>Ayrıca bkz.

[Platform::Collections Ad Alanı](../cppcx/platform-collections-namespace.md)<br/>
[Windows::Foundation::IMapView](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_)
