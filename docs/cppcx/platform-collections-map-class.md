---
title: 'Platform:: Collections:: Map sınıfı'
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
ms.openlocfilehash: 81721d719a424250beed89f4a5656b3f2fc27922
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816309"
---
# <a name="platformcollectionsmap-class"></a>Platform:: Collections:: Map sınıfı

Anahtar-değer çiftleri koleksiyonu olan bir *eşlemeyi*temsil eder. XAML [veri bağlamaya](/windows/uwp/data-binding/data-binding-in-depth)yardımcı olmak için [Windows:: Foundation:: Collections:: ıobservablemap](/uwp/api/windows.foundation.collections.iobservablemap_k_v_) uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Parametreler

*Ek*<br/>
Anahtar-değer çiftindeki anahtar türü.

*Yönetim*<br/>
Anahtar-değer çiftindeki değerin türü.

*C*<br/>
Haritada göreli sıralarını belirleyebilmek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: less @ no__t-1K >](../standard-library/less-struct.md).

*__is_valid_wınrt_type ()* *K* ve *V* türünü doğrulayan ve tür haritada depolanmıyorsa kolay bir hata iletisi sağlayan derleyicinin ürettiği bir işlev.

### <a name="remarks"></a>Açıklamalar

İzin verilen türler şunlardır:

- Kesirli

- arabirim sınıfı ^

- ortak başvuru sınıfı ^

- value yapısı

- ortak enum sınıfı

Eşleme temel olarak [std:: Map](../standard-library/map-class.md)için bir sarmalayıcı olur. Windows:: C++ [Foundation:: Collections:: Map < Windows:: Foundation:: Collections:: IKeyValuePair @ no__t-2k, V > >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_) ve [ıobservablemap](/uwp/api/Windows.Foundation.Collections.IObservableMap_K_V_) Types 'ın ortak pencereler arasında geçirildiği somut bir uygulamasıdır Çalışma zamanı arabirimleri. Ortak dönüş değeri veya parametresinde `Platform::Collections::Map` türü kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Bu hatayı, parametre türünü veya döndürülen değeri [Windows:: Foundation:: Collections:: Map @ no__t-1K, V >](/uwp/api/Windows.Foundation.Collections.IMap_K_V_)olarak değiştirerek çözebilirsiniz.

Daha fazla bilgi için bkz. [koleksiyonlar](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeleri

### <a name="public-constructors"></a>Ortak oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[Map:: Map](#ctor)|Map sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[Map:: Clear](#clear)|Geçerli harita nesnesinden tüm anahtar-değer çiftlerini kaldırır.|
|[Map:: First](#first)|Eşlemedeki ilk öğeyi belirten bir yineleyici döndürür.|
|[Map:: GetView](#getview)|Geçerli haritanın salt okunurdur görünümünü döndürür; diğer bir deyişle, bir [Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md).|
|[Map:: HasKey](#haskey)|Geçerli haritanın belirtilen anahtarı içerip içermediğini belirler.|
|[Map:: INSERT](#insert)|Belirtilen anahtar-değer çiftini geçerli harita nesnesine ekler.|
|[Map:: Lookup](#lookup)|Geçerli harita nesnesindeki belirtilen anahtardaki öğeyi alır.|
|[Map:: Remove](#remove)|Belirtilen anahtar-değer çiftini geçerli harita nesnesinden siler.|
|[Map:: size](#size)|Geçerli harita nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Etkinlikler

|||
|-|-|
|Adı|Açıklama|
|[Map:: MapChanged](#mapchanged) olayı|Eşleme değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma hiyerarşisi

`Map`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="clear"></a>Map:: Clear yöntemi

Geçerli harita nesnesinden tüm anahtar-değer çiftlerini kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="first"></a>Map:: First yöntemi

Eşlemedeki ilk öğeyi belirten bir yineleyici veya eşleme boşsa `nullptr` döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş değeri

Eşlemedeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **Auto** Type kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myMap->First();`.

## <a name="getview"></a>Map:: GetView yöntemi

Geçerli haritanın salt okunurdur görünümünü döndürür; diğer bir deyişle, [Windows:: Foundation:: Collections:: ımapview @ no__t-1K, V >]/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirimini uygulayan [Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md).

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş değeri

@No__t-0 nesnesi.

## <a name="haskey"></a>Map:: HasKey yöntemi

Geçerli haritanın belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Map öğesini bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş değeri

anahtar bulunursa **true** ; Aksi takdirde, **false**.

## <a name="insert"></a>Map:: Insert yöntemi

Belirtilen anahtar-değer çiftini geçerli harita nesnesine ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

*value*<br/>
Anahtar-değer çiftinin değer kısmı. *Değer* türü, TypeName *V*' dir.

### <a name="return-value"></a>Dönüş değeri

geçerli haritadaki var olan bir *öğenin anahtarı ile eşleşiyorsa* **true** , bu öğenin değer kısmı ise *değer*olarak ayarlanır. geçerli Haritadaki mevcut hiçbir öğe *anahtarla* eşleşmez ve anahtar ve *değer* parametreleri *anahtar-* değer çiftinde yapılırsa ve sonra geçerli haritaya eklendiyse **false** .

## <a name="lookup"></a>Map:: Lookup yöntemi

Anahtar varsa, o türü K olan belirtilen anahtarla ilişkili V türü değerini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Haritada bir öğe bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş değeri

*Anahtarla*eşleştirilmiş değer. Dönüş değerinin türü, TypeName *V*.

### <a name="remarks"></a>Açıklamalar

Anahtar yoksa, [Platform:: OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) oluşturulur.

## <a name="ctor"></a>Map:: Map Oluşturucusu

Map sınıfının yeni bir örneğini başlatır.

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

*Dengeleyici*<br/>
Geçerli haritanın TypeName 'i.

*inin*<br/>
Haritada göreli sıralarını belirleyebilmek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür.

*m*<br/>
Geçerli eşlemeyi başlatmak için kullanılan `map Class` öğesine bir başvuru veya [rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) .

*adı*<br/>
Geçerli eşlemeyi başlatmak için kullanılan öğe aralığındaki ilk öğenin giriş yineleyicisi.

*soyadına*<br/>
Geçerli eşlemeyi başlatmak için kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="mapchanged"></a>Map:: MapChanged olayı

Haritaya bir öğe eklendiğinde veya haritada kaldırıldığında oluşturulur.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik değeri/dönüş değeri

Olayı oluşturan nesne ve gerçekleşen değişiklik türü hakkında bilgi içeren bir [MapChangedEventHandler @ no__t-1K, V >](/uwp/api/windows.foundation.collections.mapchangedeventhandler) . Ayrıca bkz. [ımapchangedeventargs @ no__t-1K >](/uwp/api/Windows.Foundation.Collections.IMapChangedEventArgs_K_) ve [collectionchange numaralandırması](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework eşdeğeri

IMAP @ no__t- C# 1k, v > ' ı IDictionary @ No__t-2k, v > olarak kullanan veya Visual Basic Windows çalışma zamanı uygulamalar.

## <a name="remove"></a>Map:: Remove yöntemi

Belirtilen anahtar-değer çiftini geçerli harita nesnesinden siler.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

## <a name="size"></a>Map:: size yöntemi

Eşlemedeki [Windows:: Foundation:: Collections:: IKeyValuePair @ no__t-1K, V >](/uwp/api/Windows.Foundation.Collections.IKeyValuePair_K_V_) öğelerinin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş değeri

Haritadaki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar (C++/CX)](collections-c-cx.md)<br/>
[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[İçinde Windows Çalışma Zamanı bileşenleri oluşturmaC++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
