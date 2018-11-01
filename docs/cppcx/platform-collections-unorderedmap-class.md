---
title: Platform::Collections::UnorderedMap Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: d3e6069f4bf7b0c23d5db5844821524ee80589da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648337"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap Sınıfı

Sırasız bir temsil *harita*, anahtar-değer çiftleri koleksiyonu.

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

*K*<br/>
Anahtar-değer çifti anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değer türü.

*C*<br/>
İki öğenin değerlerini haritadaki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Varsayılan olarak, [std::equal_to\<K >](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arabirim sınıfı ^

- Genel başvuru sınıfı ^

- değer yapısı

- Genel sabit listesi sınıfı

**UnorderedMap** temelde için bir sarmalayıcı olan [std::unordered_map](../standard-library/unordered-map-class.md) , Windows çalışma zamanı türleri depolama destekler. Bu, somut bir uygulama [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) ve [Iobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Windows çalışma zamanı arasında ortak geçirilen türleri arabirimi. Kullanmayı denerseniz bir `Platform::Collections::UnorderedMap` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Hata, parametre veya dönüş değerinin türünü değiştirerek düzeltebilirsiniz [Windows::Foundation::Collections::IMap](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Daha fazla bilgi için [koleksiyonları](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap::UnorderedMap](#ctor)|Eşleme sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap::Clear](#clear)|Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.|
|[UnorderedMap::First](#first)|Haritada ilk öğeyi belirleyen bir yineleyici döndürür.|
|[UnorderedMap::GetView](#getview)|Geçerli eşlemesi salt okunur bir görünümünü verir. diğer bir deyişle, Platform::Collections:: unorderedmapview sınıfı.|
|[UnorderedMap::HasKey](#haskey)|Geçerli eşleme belirtilen anahtarı içerip içermediğini belirler.|
|[Unorderedmap::INSERT](#insert)|Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.|
|[UnorderedMap::Lookup](#lookup)|Öğe geçerli harita nesnedeki belirtilen anahtarı alır.|
|[UnorderedMap::Remove](#remove)|Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.|
|[UnorderedMap::Size](#size)|Geçerli eşleme nesnesinde öğelerin sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Ad|Açıklama|
|[Map::MapChanged](#mapchanged) olay|Harita değiştiğinde gerçekleşir.|

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

İlk belirten bir yineleyici döndüren [Windows::Foundation::Collections::IKeyValuePair\<K, V >](https://msdn.microsoft.com/library/windows/apps/br226031.aspx) sıralanmamış eşleme öğesi.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Dönüş Değeri

Haritada ilk öğeyi belirleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin: `auto x = myUnorderedMap->First();`

## <a name="getview"></a>  UnorderedMap::GetView metodu

Geçerli UnorderedMap salt okunur bir görünümünü verir. diğer bir deyişle, bir [Platform::Collections:: unorderedmapview sınıfı](../cppcx/platform-collections-unorderedmapview-class.md) uygulayan [Windows::Foundation::Collections::IMapView::IMapView]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirim.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `UnorderedMapView` nesne.

## <a name="haskey"></a>  UnorderedMap::HasKey yöntemi

Geçerli UnorderedMap belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
UnorderedMap öğeyi bulmak için kullanılan anahtar. Türünü *anahtarı* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** anahtar bulunduysa, **false**.

## <a name="insert"></a>  Unorderedmap::INSERT yöntemi

Belirtilen anahtar-değer çifti geçerli UnorderedMap nesneye ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

*value*<br/>
Anahtar-değer çiftinin değer bölümünü. Türünü *değer* TypeName *V*.

### <a name="return-value"></a>Dönüş Değeri

**true** geçerli Haritası'nda var olan bir öğenin anahtarı eşleşip eşleşmediğini *anahtarı* ve bu öğenin değeri kısmı kümesine *değer*. **false** geçerli Haritası'nda var olan bir öğe yok eşleşiyorsa *anahtar* ve *anahtar* ve *değer* parametreleri bir anahtar-değer çifti yapılan ve ardından eklenir Geçerli UnorderedMap.

## <a name="lookup"></a>  UnorderedMap::Lookup yöntemi

V türünün türü K. belirtilen anahtarla ilişkili değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Bir öğe içinde UnorderedMap bulmak için kullanılan anahtar. Türünü *anahtarı* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değeri *anahtar*. Dönüş değeri typename türüdür *V*.

## <a name="mapchanged"></a>  UnorderedMap::MapChanged

Bir öğe eklenen veya eşleme kaldırılmış olduğunda oluşturulur.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) olay ve gerçekleşen değişiklik türünü oluşturan nesneye hakkında bilgiler içerir. Ayrıca bkz: [IMapChangedEventArgs\<K >](https://msdn.microsoft.com/library/windows/apps/br226034.aspx) ve [CollectionChange numaralandırma](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

Windows çalışma zamanı uygulamaları IMAP bize C# veya Visual Basic proje\<K, V > IDictionary olarak\<K, V >.

## <a name="remove"></a>  UnorderedMap::Remove yöntemi

Belirtilen anahtar-değer çifti UnorderedMap nesneyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*<br/>
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

## <a name="size"></a>  UnorderedMap::Size yöntemi

Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](https://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMap öğeleri.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız eşlem içindeki öğelerin sayısı.

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

*InIt*<br/>
Geçerli UnorderedMap tür adı.

*P*<br/>
Eşit olup olmadığını belirlemek için iki anahtarı karşılaştıran bir işlev nesnesi. Bu parametre için varsayılan olarak [std::equal_to\<K >](../standard-library/equal-to-struct.md).

*H*<br/>
Bir anahtar için bir karma değer üreten bir işlev nesnesi. Bu parametre için varsayılan olarak [sınıf 1 karma](../standard-library/hash-class.md) sınıfı, anahtar türleri için destekler.

*m*<br/>
Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::unordered_map](../standard-library/unordered-map-class.md) geçerli UnorderedMap başlatmak için kullanılır.

*IL*<br/>
A [std::initializer_list](../standard-library/initializer-list-class.md) , [std::pair](../standard-library/pair-structure.md) harita başlatmak için kullanılan nesne.

*ilk*<br/>
Geçerli UnorderedMap başlatmak için kullanılan öğelerin bir aralıktaki ilk öğenin bir giriş yineleyici.

*Son*<br/>
Geçerli UnorderedMap başlatmak için kullanılan öğelerin bir aralığını sonra ilk öğenin bir giriş yineleyici.

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)<br/>
[Platform::Collections Ad Alanı](../cppcx/platform-collections-namespace.md)<br/>
[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
[Platform::Collections::UnorderedMapView Sınıfı](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[Koleksiyonlar](../cppcx/collections-c-cx.md)<br/>
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
