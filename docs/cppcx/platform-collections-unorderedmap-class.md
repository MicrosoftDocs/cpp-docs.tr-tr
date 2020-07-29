---
title: Platform::Collections::UnorderedMap Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMap
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
ms.openlocfilehash: 3c95f4a982e23d757b330ecadcae5cfbfd6fd531
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213079"
---
# <a name="platformcollectionsunorderedmap-class"></a>Platform::Collections::UnorderedMap Sınıfı

Anahtar-değer çiftleri koleksiyonu olan sıralanmamış bir *eşlemeyi*temsil eder.

## <a name="syntax"></a>Söz dizimi

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
Anahtar-değer çiftindeki anahtar türü.

*V*<br/>
Anahtar-değer çiftindeki değerin türü.

*,*<br/>
Haritada göreli sıralarını belirleyebilmek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak [std:: equal_to \<K> ](../standard-library/equal-to-struct.md).

### <a name="remarks"></a>Açıklamalar

İzin verilen türler şunlardır:

- integers

- arabirim sınıfı ^

- ortak başvuru sınıfı ^

- value yapısı

- ortak enum sınıfı

**Unorderedmap** , temel olarak Windows çalışma zamanı türlerinin depolanmasını destekleyen [std:: unordered_map](../standard-library/unordered-map-class.md) için bir sarmalayıcıdır. Bu, genel Windows Çalışma Zamanı arabirimleri arasında geçirilen [Windows:: Foundation:: Collections:: Map](/uwp/api/windows.foundation.collections.imap-2) ve [ıobservablemap](/uwp/api/windows.foundation.collections.iobservablemap-2) türlerinin somut bir uygulamasıdır. `Platform::Collections::UnorderedMap`Ortak dönüş değeri veya parametresinde bir tür kullanmaya çalışırsanız, derleyici hatası C3986 tetiklenir. Bu hatayı, parametre türünü veya döndürülen değeri [Windows:: Foundation:: Collections:: Map](/uwp/api/windows.foundation.collections.imap-2)olarak değiştirerek giderebilirsiniz.

Daha fazla bilgi için bkz. [koleksiyonlar](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap:: UnorderedMap](#ctor)|Map sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[UnorderedMap:: Clear](#clear)|Geçerli harita nesnesinden tüm anahtar-değer çiftlerini kaldırır.|
|[UnorderedMap:: First](#first)|Eşlemedeki ilk öğeyi belirten bir yineleyici döndürür.|
|[UnorderedMap:: GetView](#getview)|Geçerli haritanın salt okunurdur görünümünü döndürür; diğer bir deyişle, bir platform:: Collections:: UnorderedMapView sınıfı.|
|[UnorderedMap:: HasKey](#haskey)|Geçerli haritanın belirtilen anahtarı içerip içermediğini belirler.|
|[UnorderedMap:: INSERT](#insert)|Belirtilen anahtar-değer çiftini geçerli harita nesnesine ekler.|
|[UnorderedMap:: Lookup](#lookup)|Geçerli harita nesnesindeki belirtilen anahtardaki öğeyi alır.|
|[UnorderedMap:: Remove](#remove)|Belirtilen anahtar-değer çiftini geçerli harita nesnesinden siler.|
|[UnorderedMap:: size](#size)|Geçerli harita nesnesindeki öğe sayısını döndürür.|

### <a name="events"></a>Olaylar

|||
|-|-|
|Ad|Açıklama|
|[Map:: MapChanged](#mapchanged) olayı|Eşleme değiştiğinde gerçekleşir.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`UnorderedMap`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Collection. h

**Ad alanı:** Platform:: Collections

## <a name="unorderedmapclear-method"></a><a name="clear"></a>UnorderedMap:: Clear yöntemi

Geçerli UnorderedMap nesnesinden tüm anahtar-değer çiftlerini kaldırır.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual void Clear();
```

## <a name="unorderedmapfirst-method"></a><a name="first"></a>UnorderedMap:: First yöntemi

Sıralanmamış eşlemede ilk [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğesini belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^
   First();
```

### <a name="return-value"></a>Dönüş Değeri

Eşlemedeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

Ilk () tarafından döndürülen yineleyiciyi tutmanın uygun bir yolu, dönüş değerini **`auto`** tür kesintisi anahtar sözcüğüyle belirtilen bir değişkene atamaktır. Örneğin, `auto x = myUnorderedMap->First();`.

## <a name="unorderedmapgetview-method"></a><a name="getview"></a>UnorderedMap:: GetView yöntemi

Geçerli UnorderedMap 'in salt okunurdur görünümünü döndürür; diğer bir deyişle, [Windows:: Foundation:: Collections:: ımapview:: ımapview](/uwp/api/windows.foundation.collections.imapview-2) arabirimini uygulayan bir [Platform:: Collections:: Unorderedmapview sınıfı](../cppcx/platform-collections-unorderedmapview-class.md) .

### <a name="syntax"></a>Sözdizimi

```cpp
Windows::Foundation::Collections::IMapView<K, V>^ GetView();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `UnorderedMapView` nesnesi.

## <a name="unorderedmaphaskey-method"></a><a name="haskey"></a>UnorderedMap:: HasKey yöntemi

Geçerli UnorderedMap 'in belirtilen anahtarı içerip içermediğini belirler.

### <a name="syntax"></a>Söz dizimi

```cpp
bool HasKey(
   K key
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
UnorderedMap öğesini bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

**`true`** anahtar bulunursa; Aksi takdirde, **`false`** .

## <a name="unorderedmapinsert-method"></a><a name="insert"></a>UnorderedMap:: Insert yöntemi

Belirtilen anahtar-değer çiftini geçerli UnorderedMap nesnesine ekler.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual bool Insert(
   K key,
   V value
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

*deeri*<br/>
Anahtar-değer çiftinin değer kısmı. *Değer* türü, TypeName *V*' dir.

### <a name="return-value"></a>Dönüş Değeri

**`true`** geçerli haritadaki var olan bir *öğenin anahtarı ile eşleşiyorsa ve* bu öğenin değer kısmı *değer*olarak ayarlanmışsa. **`false`** geçerli Haritadaki mevcut bir öğe *anahtarla* eşleşmez ve anahtar ve *değer* *parametreleri anahtar-* değer çiftinde yapılır ve sonra geçerli unorderedmap 'e eklenir.

## <a name="unorderedmaplookup-method"></a><a name="lookup"></a>UnorderedMap:: Lookup yöntemi

K türünde belirtilen anahtarla ilişkilendirilen V türü değerini alır.

### <a name="syntax"></a>Söz dizimi

```cpp
V Lookup(
   K key
);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
UnorderedMap içindeki bir öğeyi bulmak için kullanılan anahtar. *Anahtar* türü TypeName *K*.

### <a name="return-value"></a>Dönüş Değeri

*Anahtarla*eşleştirilmiş değer. Dönüş değerinin türü, TypeName *V*.

## <a name="unorderedmapmapchanged"></a><a name="mapchanged"></a>UnorderedMap:: MapChanged

Haritaya bir öğe eklendiğinde veya haritada kaldırıldığında oluşturulur.

### <a name="syntax"></a>Sözdizimi

```cpp
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;
```

### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri

Olayı tetikleyen nesne ve gerçekleşen değişiklik türü hakkında bilgi içeren bir [MapChangedEventHandler \<K,V> ](/uwp/api/windows.foundation.collections.mapchangedeventhandler-2) . Ayrıca bkz. [ımapchangedeventargs \<K> ](/uwp/api/windows.foundation.collections.imapchangedeventargs-1) ve [collectionchange numaralandırması](/uwp/api/windows.foundation.collections.collectionchange).

## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri

C# ABD veya proje IMAP 'yi \<K,V> IDictionary olarak Visual Basic Windows çalışma zamanı uygulamalar \<K,V> .

## <a name="unorderedmapremove-method"></a><a name="remove"></a>UnorderedMap:: Remove yöntemi

Belirtilen anahtar-değer çiftini UnorderedMap nesnesinden siler.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual void Remove(
   K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar-değer çiftinin anahtar bölümü. *Anahtar* türü TypeName *K*.

## <a name="unorderedmapsize-method"></a><a name="size"></a>UnorderedMap:: size yöntemi

UnorderedMap içindeki [Windows:: Foundation:: Collections:: IKeyValuePair \<K,V> ](/uwp/api/windows.foundation.collections.ikeyvaluepair-2) öğelerinin sayısını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Sıralanmamış haritadaki öğelerin sayısı.

## <a name="unorderedmapunorderedmap-constructor"></a><a name="ctor"></a>UnorderedMap:: UnorderedMap Oluşturucusu

UnorderedMap sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Söz dizimi

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

*Dengeleyici*<br/>
Geçerli UnorderedMap TypeName öğesi.

*P*<br/>
Eşit olup olmadıklarını belirleyebilmek için iki anahtarı karşılaştırabilen bir işlev nesnesi. Bu parametre varsayılan olarak [std:: equal_to \<K> ](../standard-library/equal-to-struct.md)olur.

*H*<br/>
Anahtarlar için karma değer üreten bir işlev nesnesi. Bu parametre, sınıfının desteklediği anahtar türleri için [karma Sınıf 1 ' i](../standard-library/hash-class.md) varsayılan olarak belirler.

*m*<br/>
Geçerli UnorderedMap 'i başlatmak için kullanılan bir [std:: unordered_map](../standard-library/unordered-map-class.md) için bir başvuru veya [lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) .

*Demiryolu*<br/>
Bir [std:: initializer_list](../standard-library/initializer-list-class.md) [std::p AIR](../standard-library/pair-structure.md) nesnelerinden eşlemeyi başlatmak için kullanılır.

*adı*<br/>
Geçerli UnorderedMap 'i başlatmak için kullanılan öğe aralığındaki ilk öğenin giriş yineleyicisi.

*soyadına*<br/>
Geçerli UnorderedMap 'i başlatmak için kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](platform-namespace-c-cx.md)<br/>
[Platform:: Collections ad alanı](../cppcx/platform-collections-namespace.md)<br/>
[Platform:: Collections:: Map sınıfı](../cppcx/platform-collections-map-class.md)<br/>
[Platform:: Collections:: UnorderedMapView sınıfı](../cppcx/platform-collections-unorderedmapview-class.md)<br/>
[Koleksiyonlar](../cppcx/collections-c-cx.md)<br/>
[C++ ' ta Windows Çalışma Zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
