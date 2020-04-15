---
title: Platform::Collections::Map Sınıfı
ms.date: 10/01/2019
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
ms.openlocfilehash: 7f41a924811be95160b06a2097db6103cde8fc11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354442"
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map Sınıfı

Anahtar değeri çiftleri topluluğu olan bir *haritayı*temsil eder. Windows [uygular::Foundation::Collections::IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap_k_v_) XAML [veri bağlama](/windows/uwp/data-binding/data-binding-in-depth)ile yardımcı olmak için .

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar değeri çiftindeki anahtarın türü.

*V*<br/>
Anahtar değeri çiftindeki değerin türü.

*C*<br/>
Haritadaki göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak, [std::daha\<az K>](../standard-library/less-struct.md).

*__is_valid_winrt_type()* *K* ve *V* türünü doğrulayan ve tür Harita'da depolanamıyorsa kolay bir hata iletisi sağlayan derleyici tarafından oluşturulan bir işlev.

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arayüz sınıfı^

- kamu ref sınıfı^

- değer struct

- public enum sınıfı

Harita temelde std için bir [sarmalayıcı::harita](../standard-library/map-class.md). [Windows::Foundation::Collections::IMap<Windows::Foundation::Collections::IKeyValuePair\<K,V>>](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) ve [IObservableMap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) türlerinin genel Windows Runtime arabirimleri arasında geçirilen bir C++ somut uygulamasıdır. Ortak iade değeri `Platform::Collections::Map` veya parametrebir tür kullanmaya çalışırsanız, derleyici hatası C3986 yükseltilir. Parametre nin türünü veya döndürme değerini Windows olarak değiştirerek hatayı [düzeltebilirsiniz::Temel::Koleksiyonlar::IMap\<K,V>. ](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)

Daha fazla bilgi için [Koleksiyonlar'a](../cppcx/collections-c-cx.md)bakın.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Harita::Harita](#ctor)|Harita sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Harita::Temizle](#clear)|Geçerli Harita nesnesinden tüm anahtar değeri çiftlerini kaldırır.|
|[Harita::İlk](#first)|Haritadaki ilk öğeyi belirten bir yineleyici döndürür.|
|[Harita::GetView](#getview)|Geçerli Haritanın salt okunur görünümünü döndürür; yani, bir [Platform::Koleksiyonlar::MapView Sınıfı](../cppcx/platform-collections-mapview-class.md).|
|[Harita::HasKey](#haskey)|Geçerli Haritanın belirtilen anahtarı bulunup içermediğini belirler.|
|[Harita::Ekle](#insert)|Geçerli Eşleşme nesnesine belirtilen anahtar-dekis çiftini ekler.|
|[Harita::Arama](#lookup)|Geçerli Harita nesnesinde belirtilen anahtardaki öğeyi alır.|
|[Harita::Kaldır](#remove)|Geçerli Eşalan nesnesinden belirtilen anahtar değeri çiftini siler.|
|[Harita::Boyut](#size)|Geçerli Eşleman nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Adı|Açıklama|
|[Harita::MapChanged](#mapchanged) olay|Harita değiştiğinde oluşur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Map`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="mapclear-method"></a><a name="clear"></a>Harita::Yöntemi Temizle

Geçerli Harita nesnesinden tüm anahtar değeri çiftlerini kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a>Harita::İlk Yöntem

Haritadaki ilk öğeyi belirten veya `nullptr` harita boşsa yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myMap->First();`.

## <a name="mapgetview-method"></a><a name="getview"></a>Harita::GetView Yöntemi

Geçerli Haritanın salt okunur görünümünü döndürür; yani, bir [Platform::Koleksiyonlar::MapView Sınıfı,](../cppcx/platform-collections-mapview-class.md)[Windows::Foundation::Collections::IMapView\<K,V>]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirimini uygular.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `MapView` nesnesi.

## <a name="maphaskey-method"></a><a name="haskey"></a>Harita::HasKey Yöntemi

Geçerli Haritanın belirtilen anahtarı bulunup içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Harita öğesini bulmak için kullanılan anahtar. *Anahtar* türü *k*türüdür.

### <a name="return-value"></a>Dönüş Değeri

anahtar bulunursa **doğru;** aksi takdirde, **yanlış**.

## <a name="mapinsert-method"></a><a name="insert"></a>Harita::Ekle Yöntemi

Geçerli Eşleşme nesnesine belirtilen anahtar-dekis çiftini ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar değeri çiftinin anahtar kısmı. *Anahtar* türü *k*türüdür.

*Değer*<br/>
Anahtar değeri çiftinin değer kısmı. *Değer* *türü, V*türüdür.

### <a name="return-value"></a>Dönüş Değeri

geçerli Harita'daki varolan bir öğenin anahtarı *anahtarla* eşleşirse ve bu öğenin değer bölümü *değerlenecek*şekilde ayarlanmışsa **doğru.** **false** geçerli Harita'da varolan hiçbir öğe *anahtarla* eşleşmezse ve *anahtar* ve *değer* parametreleri anahtar değeri çiftine dönüştürülürve ardından geçerli Harita'ya eklenir.

## <a name="maplookup-method"></a><a name="lookup"></a>Harita::Arama Yöntemi

Anahtar varsa, Belirtilen K türünün anahtarıyla ilişkili V türünün değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Haritadaki bir öğeyi bulmak için kullanılan anahtar. *Anahtar* türü *k*türüdür.

### <a name="return-value"></a>Dönüş Değeri

*Anahtarla*eşleştirilmiş değer. İade değerinin türü *V*türüdür.

### <a name="remarks"></a>Açıklamalar

Anahtar yoksa, bir [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) atılır.

## <a name="mapmap-constructor"></a><a name="ctor"></a>Harita::Harita Oluşturucusu

Harita sınıfının yeni bir örneğini başolarak karşılar.

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

*ınit*<br/>
Geçerli Haritanın yazı adı.

*Comp*<br/>
Haritadaki göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

*M*<br/>
Geçerli Harita'yı başlatmak için kullanılan bir `map Class` başvuru veya [rvalue.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ilk*<br/>
Geçerli Haritayı başlatmada kullanılan bir dizi öğedeki ilk öğenin giriş yineleyicisi.

*Son*<br/>
Geçerli Haritayı başlatmada kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a>Harita::MapChanged Olay

Bir öğe eşliğe eklendiğinde veya haritadan kaldırıldığında yükseltilir.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

[Bir MapChangedEventHandler\<K,V>](/uwp/api/windows.foundation.collections.mapchangedeventhandler) olayı yükselten nesne ve meydana gelen değişiklik türü hakkında bilgi içerir. Ayrıca bakınız [IMapChangedEventArgs\<K>](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) ve [CollectionChange Numaralandırma](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

C# veya Visual Basic projesini kullanan Windows\<Runtime uygulamaları IMap K,V> IDictionary\<K,V> olarak.

## <a name="mapremove-method"></a><a name="remove"></a>Harita::Kaldırma Yöntemi

Geçerli Eşalan nesnesinden belirtilen anahtar değeri çiftini siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar değeri çiftinin anahtar kısmı. *Anahtar* türü *k*türüdür.

## <a name="mapsize-method"></a><a name="size"></a>Harita::Boyut Yöntemi

Windows sayısını [döndürür::Foundation::Collections::IKeyValuePair\<K,V>](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) öğelerini Haritada gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğe sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar (C++/CX)](collections-c-cx.md)<br/>
[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[C++'da Windows Runtime Bileşenleri Oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
