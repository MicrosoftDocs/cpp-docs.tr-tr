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
ms.openlocfilehash: 0ddb15507c97c0dfff48575e476b57fe91359239
ms.sourcegitcommit: 65fead53d56d531d71be42216056aca5f44def11
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88610913"
---
# <a name="platformcollectionsmap-class"></a>Platform:: Collections:: Map sınıfı

Anahtar-değer çiftleri koleksiyonu olan bir *eşlemeyi*temsil eder. XAML [veri bağlamaya](/windows/uwp/data-binding/data-binding-in-depth)yardımcı olmak için [Windows:: Foundation:: Collections:: ıobservablemap](/uwp/api/windows.foundation.collections.iobservablemap-2) uygular.

## <a name="syntax"></a>Söz dizimi

```cpp
template <
   typename K,
   typename V,
   typename C = std::less<K>>
ref class Map sealed;
```

### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar-değer çiftindeki anahtar türü.

*Yönetim*<br/>
Anahtar-değer çiftindeki değerin türü.

*,*<br/>
Haritada göreli sıralarını belirleyebilmek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: less \<K> ](../standard-library/less-struct.md).

*__is_valid_winrt_type ()* *K* ve *V* türünü doğrulayan ve tür haritada depolanmıyorsa kolay bir hata iletisi sağlayan derleyicinin ürettiği bir işlev.

### <a name="remarks"></a>Açıklamalar

İzin verilen türler şunlardır:

- integers

- arabirim sınıfı ^

- ortak başvuru sınıfı ^

- value yapısı

- ortak enum sınıfı

Eşleme temel olarak [std:: Map](../standard-library/map-class.md)için bir sarmalayıcı olur. Bu, genel Windows çalışma zamanı arabirimleri arasında geçirilen [Windows:: Foundation:: Collections:: Map \<Windows::Foundation::Collections::IKeyValuePair\<K,V> > ](/uwp/api/windows.foundation.collections.imap-2) ve [ıobservablemap](/uwp/api/windows.foundation.collections.iobservablemap-2) türlerinin C++ somut bir uygulamasıdır. `Platform::Collections::Map`Ortak dönüş değeri veya parametresinde bir tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Bu hatayı, parametre türünü veya döndürülen değeri [Windows:: Foundation:: Collections:: Map \<K,V> ](/uwp/api/windows.foundation.collections.imap-2)olarak değiştirerek giderebilirsiniz.

Daha fazla bilgi için bkz. [koleksiyonlar](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Map:: Map](#ctor)|Map sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Map:: Clear](#clear)|Geçerli harita nesnesinden tüm anahtar-değer çiftlerini kaldırır.|
|[Map:: First](#first)|Eşlemedeki ilk öğeyi belirten bir yineleyici döndürür.|
|[Map:: GetView](#getview)|Geçerli haritanın salt okunurdur görünümünü döndürür; diğer bir deyişle, bir [Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md).|
|[Map:: HasKey](#haskey)|Geçerli haritanın belirtilen anahtarı içerip içermediğini belirler.|
|[Map:: INSERT](#insert)|Belirtilen anahtar-değer çiftini geçerli harita nesnesine ekler.|
|[Map:: Lookup](#lookup)|Geçerli harita nesnesindeki belirtilen anahtardaki öğeyi alır.|
|[Map:: Remove](#remove)|Belirtilen anahtar-değer çiftini geçerli harita nesnesinden siler.|
|[Map:: size](#size)|Geçerli harita nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Ekinlikler

|||
|-|-|
|Ad|Açıklama|
|[Map:: MapChanged](#mapchanged) olayı|Eşleme değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`Map`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="mapclear-method"></a><a name="clear"></a> Map:: Clear yöntemi

Geçerli harita nesnesinden tüm anahtar-değer çiftlerini kaldırır.

### <a name="syntax"></a>Syntax

```cpp
virtual void Clear();
```

## <a name="mapfirst-method"></a><a name="first"></a> Map:: First yöntemi

Eşlemedeki ilk öğeyi belirten bir yineleyici döndürür veya **`nullptr`** eşleme boştur.

### <a name="syntax"></a>Syntax

```cpp
virtual Windows::Foundation::Collections::IIterator<
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Eşlemedeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **`auto`** tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myMap->First();`.

## <a name="mapgetview-method"></a><a name="getview"></a> Map:: GetView yöntemi

Geçerli haritanın salt okunurdur görünümünü döndürür; diğer bir deyişle, [Windows:: Foundation:: Collections:: \<K,V> ımapview](/uwp/api/windows.foundation.collections.imapview-2) arabirimini uygulayan bir [Platform:: Collections:: MapView Sınıfı](../cppcx/platform-collections-mapview-class.md).

### <a name="syntax"></a>Syntax

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `MapView` nesnesi.

## <a name="maphaskey-method"></a><a name="haskey"></a> Map:: HasKey yöntemi

Geçerli haritanın belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Söz dizimi

```cpp
bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Map öğesini bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**`true`** anahtar bulunursa; Aksi takdirde, **`false`** .

## <a name="mapinsert-method"></a><a name="insert"></a> Map:: Insert yöntemi

Belirtilen anahtar-değer çiftini geçerli harita nesnesine ekler.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual bool Insert(K key, V value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

*deeri*<br/>
Anahtar-değer çiftinin değer kısmı. *Değer* türü, TypeName *V*' dir.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli haritadaki var olan bir *öğenin anahtarı ile eşleşiyorsa ve* bu öğenin değer kısmı *değer*olarak ayarlanmışsa. **`false`** geçerli Haritadaki mevcut bir öğe *anahtarla* eşleşmez ve anahtar ve *değer* *parametreleri anahtar-* değer çiftinde oluşturulur ve ardından geçerli haritaya eklenir.

## <a name="maplookup-method"></a><a name="lookup"></a> Map:: Lookup yöntemi

Anahtar varsa, o türü K olan belirtilen anahtarla ilişkili V türü değerini alır.

### <a name="syntax"></a>Söz dizimi

```cpp
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Haritada bir öğe bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

*Anahtarla*eşleştirilmiş değer. Dönüş değerinin türü, TypeName *V*.

### <a name="remarks"></a>Açıklamalar

Anahtar yoksa, [Platform:: OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) oluşturulur.

## <a name="mapmap-constructor"></a><a name="ctor"></a> Map:: Map Oluşturucusu

Map sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

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
[rvalue](../cpp/lvalues-and-rvalues-visual-cpp.md) `map Class` Geçerli eşlemeyi başlatmak için kullanılan bir başvurusu veya rvalue.

*adı*<br/>
Geçerli eşlemeyi başlatmak için kullanılan öğe aralığındaki ilk öğenin giriş yineleyicisi.

*soyadına*<br/>
Geçerli eşlemeyi başlatmak için kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="mapmapchanged-event"></a><a name="mapchanged"></a> Map:: MapChanged olayı

Haritaya bir öğe eklendiğinde veya haritada kaldırıldığında oluşturulur.

### <a name="syntax"></a>Syntax

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Olayı tetikleyen nesne ve gerçekleşen değişiklik türü hakkında bilgi içeren bir [MapChangedEventHandler \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) . Ayrıca bkz. [ımapchangedeventargs \<K> ](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) ve [collectionchange numaralandırması](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

C# veya Visual Basic projesi IMAP 'yi \<K,V> IDictionary olarak kullanan uygulamalar Windows çalışma zamanı \<K,V> .

## <a name="mapremove-method"></a><a name="remove"></a> Map:: Remove yöntemi

Belirtilen anahtar-değer çiftini geçerli harita nesnesinden siler.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual void Remove(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

## <a name="mapsize-method"></a><a name="size"></a> Map:: size yöntemi

Eşlemedeki [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğelerinin sayısını döndürür.

### <a name="syntax"></a>Syntax

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Haritadaki öğelerin sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Koleksiyonlar (C++/CX)](collections-c-cx.md)<br/>
[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[C++ ' ta Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
