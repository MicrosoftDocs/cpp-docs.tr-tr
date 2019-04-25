---
title: 'Platform::Collections:: Map sınıfı'
ms.date: 03/27/2019
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
ms.openlocfilehash: ce50290217c7c06e26f26fc50564d3e37c873157
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161764"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections:: Map sınıfı

Temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar-değer çifti anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değer türü.

*C*<br/>
İki öğenin değerlerini haritadaki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Varsayılan olarak, [std::less\<K >](../standard-library/less-struct.md).

*__is_valid_winrt_type()* türünü doğrular derleyici tarafından oluşturulan bir işlev *K* ve *V* ve kolay hata iletisi türü haritada depolanırsa sağlar.

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arabirim sınıfı ^

- Genel başvuru sınıfı ^

- değer yapısı

- Genel sabit listesi sınıfı

Haritası, temelde için sarmalayıcı [std::map](../standard-library/map-class.md). Bir C++ somut uygulaması olan [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) ve [Iobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Windows çalışma zamanı arasında ortak geçirilen türleri arabirimi. Kullanmayı denerseniz bir `Platform::Collections::Map` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Hata, parametre veya dönüş değerinin türünü değiştirerek düzeltebilirsiniz [Windows::Foundation::Collections::IMap\<K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_).

Daha fazla bilgi için [koleksiyonları](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Map::Map](#ctor)|Eşleme sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Map::Clear](#clear)|Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.|
|[Map::First](#first)|Haritada ilk öğeyi belirleyen bir yineleyici döndürür.|
|[Map::GetView](#getview)|Geçerli eşlemesi salt okunur bir görünümünü verir. diğer bir deyişle, bir [Platform::Collections:: mapview sınıfı](../cppcx/platform-collections-mapview-class.md).|
|[Map::HasKey](#haskey)|Geçerli eşleme belirtilen anahtarı içerip içermediğini belirler.|
|[Map::INSERT](#insert)|Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.|
|[Map::Lookup](#lookup)|Öğe geçerli harita nesnedeki belirtilen anahtarı alır.|
|[Map::Remove](#remove)|Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.|
|[Map::size](#size)|Geçerli eşleme nesnesinde öğelerin sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Ad|Açıklama|
|[Map::MapChanged](#mapchanged) olay|Harita değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Map`

### <a name="requirements"></a>Gereksinimler

**Başlık:** collection.h

**Namespace:** Platform::Collections

## <a name="clear"></a>  Map::Clear yöntemi

Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="first"></a>  Map::First yöntemi

Haritada ilk öğeyi belirleyen bir yineleyici döndürür veya `nullptr` eşlem boşsa.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Haritada ilk öğeyi belirleyen bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin: `auto x = myMap->First();`

## <a name="getview"></a>  Map::GetView yöntemi

Geçerli eşlemesi salt okunur bir görünümünü verir. diğer bir deyişle, bir [Platform::Collections:: mapview sınıfı](../cppcx/platform-collections-mapview-class.md), uygulayan [Windows::Foundation::Collections::IMapView\<K, V >] / uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirimi.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

A `MapView` nesne.

## <a name="haskey"></a>  Map::HasKey yöntemi

Geçerli eşleme belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Harita öğesini bulmak için kullanılan anahtar. Türünü *anahtarı* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**doğru** anahtar bulunduysa, **false**.

## <a name="insert"></a>  Map::INSERT yöntemi

Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

*value*<br/>
Anahtar-değer çiftinin değer bölümünü. Türünü *değer* TypeName *V*.

### <a name="return-value"></a>Dönüş Değeri

**true** geçerli Haritası'nda var olan bir öğenin anahtarı eşleşip eşleşmediğini *anahtarı* ve bu öğenin değeri kısmı kümesine *değer*. **false** geçerli Haritası'nda var olan bir öğe yok eşleşiyorsa *anahtar* ve *anahtar* ve *değer* parametreleri bir anahtar-değer çifti yapılan ve ardından eklenir Geçerli eşleme.

## <a name="lookup"></a>  Map::Lookup yöntemi

V türündeki anahtar varsa, türü K, belirtilen anahtarla ilişkili değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Haritada bir öğeyi bulmak için kullanılan anahtar. Türünü *anahtarı* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

İle eşleştirilmiş değeri *anahtar*. Dönüş değeri typename türüdür *V*.

### <a name="remarks"></a>Açıklamalar

Anahtar mevcut değilse bir [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) oluşturulur.

## <a name="ctor"></a>  Map::Map Oluşturucusu

Eşleme sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit Map(const C& comp = C());
explicit Map(const StdMap& m);
explicit Map(StdMap&& m ;
template <typename InIt>
Map(
   InItfirst,
   InItlast,
   const C& comp = C());
```

### <a name="parameters"></a>Parametreler

*InIt*<br/>
Geçerli eşlemesi tür adı.

*Comp*<br/>
İki öğenin değerlerini haritadaki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür.

*m*<br/>
Bir başvuru veya [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir `map Class` geçerli eşlemesi başlatmak için kullanılır.

*ilk*<br/>
Geçerli eşlemesi başlatmak için kullanılan öğelerin bir aralıktaki ilk öğenin bir giriş yineleyici.

*Son*<br/>
Geçerli eşlemesi başlatmak için kullanılan öğelerin bir aralığını sonra ilk öğenin bir giriş yineleyici.

## <a name="mapchanged"></a>  Map::MapChanged olayı

Bir öğe eklenen veya eşleme kaldırılmış olduğunda oluşturulur.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) olay ve gerçekleşen değişiklik türünü oluşturan nesneye hakkında bilgiler içerir. Ayrıca bkz: [IMapChangedEventArgs\<K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) ve [CollectionChange numaralandırma](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

C# veya Visual Basic kullanan Windows çalışma zamanı uygulamaları proje IMAP\<K, V > IDictionary olarak\<K, V >.

## <a name="remove"></a>  Map::Remove yöntemi

Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

## <a name="size"></a>  Map::size yöntemi

Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) eşlemedeki öğeler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Platform Namespace](platform-namespace-c-cx.md)<br/>
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
