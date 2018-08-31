---
title: 'Platform::Collections:: Map sınıfı | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2018
ms.technology: cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a2192786a9ebb14061e31655fd63e0f7c67b5100
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218429"
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

*K*  
 Anahtar-değer çifti anahtar türü.

*V*  
Anahtar-değer çiftindeki değer türü.

*C*  
İki öğenin değerlerini haritadaki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Varsayılan olarak, [std::less\<K >](../standard-library/less-struct.md).

*__is_valid_winrt_type()*  
Derleyicinin ürettiği funkci türünü doğrular *K* ve *V* ve kolay hata iletisi türü haritada depolanırsa sağlar.

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arabirim sınıfı ^

- Genel başvuru sınıfı ^

- değer yapısı

- Genel sabit listesi sınıfı

Haritası, temelde için sarmalayıcı [std::map](../standard-library/map-class.md). Bir C++ somut uygulaması olan [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408) ve [Iobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Windows çalışma zamanı arasında ortak geçirilen türleri arabirimi. Kullanmayı denerseniz bir `Platform::Collections::Map` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Hata, parametre veya dönüş değerinin türünü değiştirerek düzeltebilirsiniz [Windows::Foundation::Collections::IMap\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408).

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
|[Map::MapChanged](#mapchanged-event.md) `event`|Harita değiştiğinde gerçekleşir.|

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

Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin, `auto x = myMap->First();`.

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

*Anahtarı*  
Harita öğesini bulmak için kullanılan anahtar. Türünü *anahtarı* TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

`true` anahtar bulunursa; Aksi takdirde, `false`.

## <a name="insert"></a>  Map::INSERT yöntemi

Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*  
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

*value*  
Anahtar-değer çiftinin değer bölümünü. Türünü *değer* TypeName *V*.

### <a name="return-value"></a>Dönüş Değeri

`true` Geçerli Haritası'nda var olan bir öğenin anahtarı eşleşip eşleşmediğini *anahtarı* ve bu öğenin değeri kısmı kümesine *değer*. `false` Geçerli bir eşlem içindeki herhangi bir mevcut öğe eşleşiyorsa *anahtarı* ve *anahtarı* ve *değer* parametreleri bir anahtar-değer çifti yapılan ve ardından geçerli haritaya eklenen.

## <a name="lookup"></a>  Map::Lookup yöntemi

V türündeki anahtar varsa, türü K, belirtilen anahtarla ilişkili değeri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*  
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

*InIt*  
Geçerli eşlemesi tür adı.

*Comp*  
İki öğenin değerlerini haritadaki kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür.

*m*  
Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir `map Class` geçerli eşlemesi başlatmak için kullanılır.

*ilk*  
Geçerli eşlemesi başlatmak için kullanılan öğelerin bir aralıktaki ilk öğenin bir giriş yineleyici.

*Son*  
Geçerli eşlemesi başlatmak için kullanılan öğelerin bir aralığını sonra ilk öğenin bir giriş yineleyici.

## <a name="mapchanged"></a>  Map::MapChanged olayı

Bir öğe eklenen veya eşleme kaldırılmış olduğunda oluşturulur.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

A [MapChangedEventHandler\<K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) olay ve gerçekleşen değişiklik türünü oluşturan nesneye hakkında bilgiler içerir. Ayrıca bkz: [IMapChangedEventArgs\<K >](https://msdn.microsoft.com/library/windows/apps/br226034.aspx) ve [CollectionChange numaralandırma](https://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

C# veya Visual Basic kullanan Windows çalışma zamanı uygulamaları proje IMAP\<K, V > IDictionary olarak\<K, V >.

## <a name="remove"></a>  Map::Remove yöntemi

Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Parametreler

*Anahtarı*  
Anahtar-değer çifti anahtar bölümü. Türünü *anahtarı* TypeName *K*.

## <a name="size"></a>  Map::size yöntemi

Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](https://msdn.microsoft.com/library/windows/apps/br226031.aspx) eşlemedeki öğeler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Eşlem içindeki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca Bkz.

[Platform Namespace](platform-namespace-c-cx.md)  
[C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)  
