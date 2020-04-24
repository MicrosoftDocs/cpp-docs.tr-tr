---
title: Platform::Collections::UnorderedMap Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 80b46cb95f2fdb83922ca22e8aa06a89aca4bfde
ms.sourcegitcommit: 89d9e1cb08fa872483d1cde98bc2a7c870e505e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82031504"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap Sınıfı

Anahtar değer çiftleri topluluğu olan sıralanmamış bir *haritayı*temsil eder.

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

*Kahraman*<br/>
Anahtar değeri çiftindeki anahtarın türü.

*V*<br/>
Anahtar değeri çiftindeki değerin türü.

*C*<br/>
Haritadaki göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak, [\<std::equal_to K>](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Açıklamalar

İzin verilen türleri şunlardır:

- tamsayılar

- arayüz sınıfı^

- kamu ref sınıfı^

- değer struct

- public enum sınıfı

**UnorderedMap** temelde std için bir [sarmalayıcı::Windows](../standard-library/unordered-map-class.md) Runtime türlerinin depolama destekleyen unordered_map. Windows'un somut bir [uygulamasıdır::Foundation::Collections::IMap](/uwp/api/windows.foundation.collections.imap-2) ve [IObservableMap](/uwp/api/windows.foundation.collections.iobservablemap-2) türleri genel Windows Runtime arabirimleri arasında geçirilir. Ortak iade değeri `Platform::Collections::UnorderedMap` veya parametrebir tür kullanmaya çalışırsanız, derleyici hatası C3986 yükseltilir. Parametrenin türünü veya döndürme değerini Windows'a değiştirerek hatayı [düzeltebilirsiniz::Temel::Koleksiyonlar::IMap](/uwp/api/windows.foundation.collections.imap-2).

Daha fazla bilgi için [Koleksiyonlar'a](../cppcx/collections-c-cx.md)bakın.

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[SırasızMap::SıradışıMap](#ctor)|Harita sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[SırasızMap::Temizleyin](#clear)|Geçerli Harita nesnesinden tüm anahtar değeri çiftlerini kaldırır.|
|[SırasızMap::İlk](#first)|Haritadaki ilk öğeyi belirten bir yineleyici döndürür.|
|[SırasızMap::GetView](#getview)|Geçerli Haritanın salt okunur görünümünü döndürür; diğer bir, bir Platform::Koleksiyonlar::SırasızMapView Sınıfı.|
|[SırasızMap::HasKey](#haskey)|Geçerli Haritanın belirtilen anahtarı bulunup içermediğini belirler.|
|[SırasızMap::Ekle](#insert)|Geçerli Eşleşme nesnesine belirtilen anahtar-dekis çiftini ekler.|
|[SırasızMap::Arama](#lookup)|Geçerli Harita nesnesinde belirtilen anahtardaki öğeyi alır.|
|[SırasızMap::Kaldır](#remove)|Geçerli Eşalan nesnesinden belirtilen anahtar değeri çiftini siler.|
|[SırasızMap::Boyut](#size)|Geçerli Eşleman nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Adı|Açıklama|
|[Harita::MapChanged](#mapchanged) olay|Harita değiştiğinde oluşur.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMap`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="unorderedmapclear-method"></a><a name="clear"></a>SırasızMap::Açık Yöntem

Geçerli UnorderedMap nesnesinden tüm anahtar değeri çiftlerini kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a>SırasızMap::İlk Yöntem

İlk [Windows::Foundation::Collections::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğesini sıralanmamış haritada belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myUnorderedMap->First();`.

## <a name="unorderedmapgetview-method"></a><a name="getview"></a>SırasızMap::GetView Yöntemi

Geçerli Sıradışı Haritanın salt okunur görünümünü döndürür; yani, bir [Platform::Koleksiyonlar::Windows'u uygulayan SıradışıMapView](../cppcx/platform-collections-unorderedmapview-class.md) [Sınıfı::Hazırlık::Koleksiyonlar::IMapView::IMapView](/uwp/api/windows.foundation.collections.imapview-2) arayüzü.

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `UnorderedMapView` nesnesi.

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a>SırasızMap::HasKey Yöntemi

Geçerli UnorderedMap'in belirtilen anahtarı içerip içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Sıradışı Harita öğesini bulmak için kullanılan anahtar. *Anahtar* türü *k*türüdür.

### <a name="return-value"></a>Dönüş Değeri

anahtar bulunursa **doğru;** aksi takdirde, **yanlış**.

## <a name="unorderedmapinsert-method"></a><a name="insert"></a>SırasızMap::Ekle Yöntemi

Geçerli Sıradışı Harita nesnesine belirtilen anahtar değeri çiftini ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar değeri çiftinin anahtar kısmı. *Anahtar* türü *k*türüdür.

*value*<br/>
Anahtar değeri çiftinin değer kısmı. *Değer* *türü, V*türüdür.

### <a name="return-value"></a>Dönüş Değeri

geçerli Harita'daki varolan bir öğenin anahtarı *anahtarla* eşleşirse ve bu öğenin değer bölümü *değerlenecek*şekilde ayarlanmışsa **doğru.** **false** geçerli Harita'da varolan hiçbir öğe *anahtarla* eşleşmezse ve *anahtar* ve *değer* parametreleri anahtar değeri çiftine dönüştürülürve ardından geçerli Sırasız Harita'ya eklenir.

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a>SırasızMap::Arama Yöntemi

Belirtilen K türünün anahtarıyla ilişkili V türünün değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Sırasız Harita'da bir öğeyi bulmak için kullanılan anahtar. *Anahtar* türü *k*türüdür.

### <a name="return-value"></a>Dönüş Değeri

*Anahtarla*eşleştirilmiş değer. İade değerinin türü *V*türüdür.

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a>SırasızMap::MapChanged

Bir öğe eşliğe eklendiğinde veya haritadan kaldırıldığında yükseltilir.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

[Bir MapChangedEventHandler\<K,V>](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) olayı yükselten nesne ve meydana gelen değişiklik türü hakkında bilgi içerir. Ayrıca bakınız [IMapChangedEventArgs\<K>](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) ve [CollectionChange Numaralandırma](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

Windows Runtime uygulamaları bize C# veya\<Visual Basic proje IMap K,V> olarak IDictionary\<K,V>.

## <a name="unorderedmapremove-method"></a><a name="remove"></a>SırasızMap::Kaldırma Yöntemi

Sıradışı Harita nesnesinden belirtilen anahtar değeri çiftini siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar değeri çiftinin anahtar kısmı. *Anahtar* türü *k*türüdür.

## <a name="unorderedmapsize-method"></a><a name="size"></a>SırasızMap::Boyut Yöntemi

Sıradışı Haritadaki [Windows::Foundation::Collections::IKeyValuePair\<K,V>](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğelerini verir.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sırasız Haritadaki öğe sayısı.

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a>SırasızMap::Sırasız Map Constructor

Sıradışı Harita sınıfının yeni bir örneğini başlattı.

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

*ınit*<br/>
Geçerli UnorderedMap'in türü.

*P*<br/>
Eşit olup olmadıklarını belirlemek için iki anahtarı karşılaştırabilen bir işlev nesnesi. Bu parametre [varsayılan\<std::equal_to K>](../standard-library/equal-to-struct.md).

*H*<br/>
Anahtarlar için karma değer üreten bir işlev nesnesi. Bu parametre, sınıfın desteklediği anahtar türleri için [karma Sınıf 1'e](../standard-library/hash-class.md) varsayılan olarak gelir.

*M*<br/>
Geçerli UnorderedMap'i başlatmada kullanılan [bir std::unordered_map](../standard-library/unordered-map-class.md) için bir başvuru veya [Lvalues ve Rvalues.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*ıl*<br/>
Bir [std::initializer_list](../standard-library/initializer-list-class.md) [std::pharitayı](../standard-library/pair-structure.md) başlatmak için kullanılan hava nesneleri.

*Ilk*<br/>
Geçerli Sıradışı Haritayı başlatmada kullanılan bir dizi öğedeki ilk öğenin giriş yineleyicisi.

*Son*<br/>
Geçerli Sıra dışı Haritayı başlatmada kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)<br/>
[Platform::Koleksiyonlar Namespace](../cppcx/platform-collections-namespace.md)<br/>
[Platform::Collections::Map Sınıfı](../cppcx/platform-collections-map-class.md)<br/>
[Platform::Koleksiyonlar::SırasızMapView Sınıfı](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[Koleksiyonlar](../cppcx/collections-c-cx.md)<br/>
[C++'da Windows Runtime Bileşenleri Oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
