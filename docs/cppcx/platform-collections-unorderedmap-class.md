---
title: "Platform::Collections:: unorderedmap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 248b25e61af0ce766c81d480d7ebf39618a8dfec
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap Sınıfı

Bir sırasız temsil eden *harita*, anahtar-değer çiftleri koleksiyonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = std::equal_to<K>
>
ref class Map sealed;
```

#### <a name="parameters"></a>Parametreler

*K*  
Anahtar-değer çifti anahtar türü.

*V*  
Anahtar-değer çiftinin değer türü.

*C*  
İşlev nesnesi sağlayan bir türü göreli sıralarına eşlemesindeki belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırabilirsiniz. Varsayılan olarak, [std::equal_to\<K >](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arabirim sınıfı ^

- Ortak ref sınıfı ^

- değer yapısı

- Ortak enum sınıfı

**UnorderedMap** temelde için sarmalayıcı olan [std::unordered_map](../standard-library/unordered-map-class.md) Windows çalışma zamanı türleri depolanmasını destekler. Bu somut bir uyarlamasını [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) ve [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Windows çalışma zamanı arasında ortak geçirilen türleri arabirimi. Kullanmaya çalışırsa, bir `Platform::Collections::UnorderedMap` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Parametresi veya dönüş değerinin türünü değiştirerek hatayı düzeltmek [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Daha fazla bilgi için bkz: [koleksiyonları](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|Harita sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.|
|[UnorderedMap::First](#first)|İlk öğe eşlemesinde belirtir yineleyici döndürür.|
|[UnorderedMap::GetView](#getview)|Geçerli eşlemesi salt okunur bir görünümünü verir; diğer bir deyişle, Platform::Collections:: unorderedmapview sınıfı.|
|[UnorderedMap::HasKey](#haskey)|Geçerli eşlemesi belirtilen anahtarı içerip içermediğini belirler.|
|[Unorderedmap::INSERT](#insert)|Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.|
|[UnorderedMap::Lookup](#lookup)|Geçerli harita nesnesi belirtilen anahtar öğede alır.|
|[UnorderedMap::Remove](#remove)|Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.|
|[UnorderedMap::Size](#size)|Geçerli harita nesnesinde öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Ad|Açıklama|
|[Map::MapChanged](#mapchanged) olayı|Harita değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMap`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="clear"></a>  UnorderedMap::Clear yöntemi

Tüm anahtar-değer çiftleri geçerli UnorderedMap nesnesinden kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="first"></a>  UnorderedMap::First yöntemi

İlk belirtir yineleyici döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) sırasız eşlemesindeki öğesi.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ 
   First();
```

### <a name="return-value"></a>Dönüş Değeri

İlk öğe eşlemesinde belirtir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myUnorderedMap->First();`.

## <a name="getview"></a>  UnorderedMap::GetView yöntemi

Geçerli UnorderedMap salt okunur bir görünümünü verir; diğer bir deyişle, bir [Platform::Collections:: unorderedmapview sınıfı](../cppcx/platform-collections-unorderedmapview-class.md) uygulayan [Windows::Foundation::Collections::IMapView::IMapView](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) arabirimi.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `UnorderedMapView` nesnesi.

## <a name="haskey"></a>  UnorderedMap::HasKey yöntemi

Geçerli UnorderedMap belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Parametreler

*key*  
UnorderedMap öğesi bulmak için kullanılan anahtar. Türü *anahtar* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

`true` anahtar bulunursa; Aksi takdirde `false`.

## <a name="insert"></a>  Unorderedmap::INSERT yöntemi

Belirtilen anahtar-değer çifti geçerli UnorderedMap nesnesine ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Parametreler

*key*  
Anahtar-değer çifti anahtar bölümünü. Türü *anahtar* TypeName *K*.

*value*  
Anahtar-değer çiftinin değer bölümünü. Türü *değeri* TypeName *V*.

### <a name="return-value"></a>Dönüş Değeri

`true` Geçerli eşlemesindeki var olan bir öğe anahtarı eşleşip eşleşmediğini *anahtar* ve o öğenin değeri kısmı kümesine *değeri*. `false` Geçerli eşlemesindeki var olan bir öğe eşleşmiyorsa *anahtar* ve *anahtar* ve *değeri* parametreleri bir anahtar-değer çifti yapılan ve geçerli UnorderedMap eklendi.

## <a name="lookup"></a>  UnorderedMap::Lookup yöntemi

V türü türü K. belirtilen anahtarla ilişkili değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Parametreler

*key*  
Bir öğenin UnorderedMap bulmak için kullanılan anahtar. Türü *anahtar* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değeri *anahtar*. Dönüş değeri typename türüdür *V*.

## <a name="mapchanged"></a>  UnorderedMap::MapChanged

Bir öğe eklenen veya eşleme kaldırılmış tetiklenir.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) olay ve tür oluştu değişiklik yükseltilmiş nesne hakkında bilgiler içerir. Ayrıca bkz. [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) ve [CollectionChange numaralandırma](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

Windows çalışma zamanı uygulamaları bize C# veya Visual Basic IMAP proje\<K, V > IDictionary olarak\<K, V >.

## <a name="remove"></a>  UnorderedMap::Remove yöntemi

Belirtilen anahtar-değer çifti UnorderedMap nesneyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Parametreler

*key*  
Anahtar-değer çifti anahtar bölümünü. Türü *anahtar* TypeName *K*.

## <a name="size"></a>  UnorderedMap::Size yöntemi

Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMap öğeler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız eşlemesindeki öğe sayısı.

## <a name="ctor"></a>  UnorderedMap::UnorderedMap Oluşturucusu

UnorderedMap sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
UnorderedMap();

explicit UnorderedMap(
    size_t n
    );

UnorderedMap(
    size_t n,
    const H& h
    );

UnorderedMap(
    size_t n,
    const H& h,
    const P& p
    );

explicit UnorderedMap(
    const std::unordered_map<K, V, H, P>& m
    );

explicit UnorderedMap(
    std::unordered_map<K, V, H, P>&& m
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h
    );

template <typename InIt>
UnorderedMap(
    InIt first,
    InIt last,
    size_t n,
    const H& h,
    const P& p
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h
    );

UnorderedMap(
    std::initializer_list< std::pair<const K, V>> il,
    size_t n,
    const H& h,
    const P& p
    );
```

### <a name="parameters"></a>Parametreler

*InIt*  
Geçerli UnorderedMap typename.

*P*  
Eşit olup olmadıklarını belirlemek için iki anahtar karşılaştırabilirsiniz işlev nesnesi. Bu parametre için varsayılan olarak [std::equal_to\<K >](../standard-library/equal-to-struct.md).

*H*  
Bir anahtarları için bir karma değer üreten bir işlev nesnesi. Bu parametre için varsayılan olarak [sınıfı 1 karma](../standard-library/hash-class.md) destekler sınıfı, anahtar türleri için.

*m*  
Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::unordered_map](../standard-library/unordered-map-class.md) geçerli UnorderedMap başlatmak için kullanılır.

*IL* A [std::initializer_list](../standard-library/initializer-list-class.md) , [std::pair](../standard-library/pair-structure.md) harita başlatmak için kullanılan nesne.

*first*  
Geçerli UnorderedMap başlatmak için kullanılan öğelerin bir aralıktaki ilk öğe giriş yineleyici.

*Son*  
İlk öğeden sonra öğeleri geçerli UnorderedMap başlatmak için kullanılan bir dizi giriş yineleyici.

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)  
[Platform::Collections Ad Alanı](../cppcx/platform-collections-namespace.md)  
[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)  
[Platform::Collections::UnorderedMapView Sınıfı](../cppcx/platform-collections-unorderedmapview-class.md)  
[Koleksiyonlar](../cppcx/collections-c-cx.md)  
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
