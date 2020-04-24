---
title: Platform::Koleksiyonlar::MapView Sınıfı
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
ms.openlocfilehash: a770b318d893b9e81bdf11a75c2b0b05c0a9979f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750605"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Koleksiyonlar::MapView Sınıfı

Anahtar değeri çiftleri topluluğu olan *bir haritaya*salt okunur görünümü temsil eder.

## <a name="syntax"></a>Sözdizimi

```
template <
   typename K,
   typename V,
   typename C = ::std::less<K>>
ref class MapView sealed;
```

#### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar değeri çiftindeki anahtarın türü.

*V*<br/>
Anahtar değeri çiftindeki değerin türü.

*C*<br/>
MapView'daki göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan bir tür. Varsayılan olarak, [std::daha\<az K>](../standard-library/less-struct.md).

### <a name="remarks"></a>Açıklamalar

MapView, Windows'un somut bir C++ [uygulamasıdır::Hazırlık::Koleksiyonlar::IMapView \<K,V>](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) arabirimi, uygulama ikili arabirimi (ABI) üzerinden geçirilir. Daha fazla bilgi için [Bkz. Koleksiyonlar (C++/CX)](../cppcx/collections-c-cx.md).

### <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[MapView::MapView](#ctor)|MapView sınıfının yeni bir örneğini başolarak karşılar.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[MapView::İlk](#first)|Harita görünümündeki ilk öğeye başharflendirilen bir yineleyici döndürür.|
|[MapView::HasKey](#haskey)|Geçerli MapView'in belirtilen anahtarı bulunup içermediğini belirler.|
|[MapView::Arama](#lookup)|Geçerli MapView nesnesinde belirtilen anahtardaki öğeyi alır.|
|[MapView::Boyut](#size)|Geçerli MapView nesnesindeki öğe sayısını verir.|
|[MapView::Bölme](#split)|Özgün bir MapView nesnesine iki MapView nesnesi bölünür.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`MapView`

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** collection.h

**Ad alanı:** Platform::Koleksiyonlar

## <a name="mapviewfirst-method"></a><a name="first"></a>MapView::İlk Yöntem

Harita görünümünde ilk öğeyi belirten bir yineleyici döndürür.

### <a name="syntax"></a>Sözdizimi

```
virtual Windows::Foundation::Collections::IIterator<
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();
```

### <a name="return-value"></a>Dönüş Değeri

Harita görünümündeki ilk öğeyi belirten bir yineleyici.

### <a name="remarks"></a>Açıklamalar

First() tarafından döndürülen yineleyiciyi tutmanın kullanışlı bir yolu, otomatik **tür** kesintisi anahtar sözcüğüyle birlikte bildirilen bir değişkene iade değerini atamaktır. Örneğin, `auto x = myMapView->First();`.

## <a name="mapviewhaskey-method"></a><a name="haskey"></a>MapView::HasKey Yöntemi

Geçerli MapView'in belirtilen anahtarı bulunup içermediğini belirler.

### <a name="syntax"></a>Sözdizimi

```

bool HasKey(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
MapView öğesini bulmak için kullanılan anahtar. *Anahtar* türü *k*türüdür.

### <a name="return-value"></a>Dönüş Değeri

anahtar bulunursa **doğru;** aksi takdirde, **yanlış**.

## <a name="mapviewlookup-method"></a><a name="lookup"></a>MapView::Arama Yöntemi

Belirtilen K türünün anahtarıyla ilişkili V türünün değerini alır.

### <a name="syntax"></a>Sözdizimi

```
V Lookup(K key);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
MapView'daki bir öğeyi bulmak için kullanılan anahtar. Türü `key` k *türüdür.*

### <a name="return-value"></a>Dönüş Değeri

`key`' ile eşleştirilmiş olan değer. İade değerinin türü *V*türüdür.

## <a name="mapviewmapview-constructor"></a><a name="ctor"></a>MapView::MapView Oluşturucu

MapView sınıfının yeni bir örneğini başolarak karşılar.

### <a name="syntax"></a>Sözdizimi

```cpp
explicit MapView(const C& comp = C());

explicit MapView(const ::std::map<K, V, C>& m);

explicit MapView(std::map<K, V, C>&& m);

template <typename InIt> MapView(
    InIt first,
    InIt last,
    const C& comp = C());

MapView(
    ::std::initializer_list<std::pair<const K, V>> il,
    const C& comp = C());
```

### <a name="parameters"></a>Parametreler

*ınit*<br/>
Geçerli MapView'in yazı adı.

*Comp*<br/>
MapView'daki göreli sıralarını belirlemek için iki öğe değerini sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi.

*M*<br/>
Geçerli MapView'ı başlatmak `map Class` için kullanılan bir başvuru veya [Lvalues ve Rvalues.](../cpp/lvalues-and-rvalues-visual-cpp.md)

*Ilk*<br/>
Geçerli MapView'i başlatmada kullanılan bir dizi öğedeki ilk öğenin giriş yineleyicisi.

*Son*<br/>
Geçerli MapView'i başlatmada kullanılan bir dizi öğeden sonra ilk öğenin giriş yineleyicisi.

*ıl*<br/>
Bir [std::initializer_list<std::pair\<K,V>>](../standard-library/initializer-list-class.md) olan elemanları MapView eklenecektir.

## <a name="mapviewsize-method"></a><a name="size"></a>MapView::Boyut Yöntemi

Geçerli MapView nesnesindeki öğe sayısını verir.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual property unsigned int Size;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli MapView'daki öğelerin sayısı.

## <a name="mapviewsplit-method"></a><a name="split"></a>MapView::Bölme Yöntemi

Geçerli MapView nesnesini iki MapView nesnesine böler. Bu yöntem çalışmıyor.

### <a name="syntax"></a>Sözdizimi

```cpp
void Split(
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * firstPartition,
   Windows::Foundation::Collections::IMapView<
                         K, V>^ * secondPartition);
```

### <a name="parameters"></a>Parametreler

*ilkBölüm*<br/>
Orijinal MapView nesnesinin ilk bölümü.

*secondPartition*<br/>
Orijinal MapView nesnesinin ikinci bölümü.

### <a name="remarks"></a>Açıklamalar

Bu yöntem işlevsel değildir; Hiçbir şey yapmaz.

## <a name="see-also"></a>Ayrıca bkz.

[Platform İsim Alanı](platform-namespace-c-cx.md)
