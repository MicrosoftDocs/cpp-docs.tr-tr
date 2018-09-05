---
title: 'Platform::Collections:: mapview sınıfı | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
dev_langs:
- C++
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e1dfbcff7e9e470992b0799aac1c87984b52ed50
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755914"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections:: mapview sınıfı
Bir salt okunur görünüme temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>>  
ref class MapView sealed;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar-değer çifti anahtar türü.  
  
 `V`  
 Anahtar-değer çiftindeki değer türü.  
  
 `C`  
 İki öğenin değerlerini MapView kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi sağlayan tür. Varsayılan olarak, [std::less\<K >](../standard-library/less-struct.md).  
  
### <a name="remarks"></a>Açıklamalar  
 MapView olan somut bir C++ uygulaması [Windows::Foundation::Collections::IMapView \<K, V >](/uwp/api/Windows.Foundation.Collections.IMapView_K_V_) uygulama ikili arabiriminde (ABI) geçirilen arabirimi. Daha fazla bilgi için [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MapView::MapView](#ctor)|MapView sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MapView::First](#first)|Harita görünümünü içindeki ilk öğeyi başlatılan bir yineleyiciyi döndürür.|  
|[MapView::HasKey](#haskey)|Geçerli MapView belirtilen anahtarı içerip içermediğini belirler.|  
|[MapView::Lookup](#lookup)|Öğe geçerli MapView nesnedeki belirtilen anahtarı alır.|  
|[MapView::Size](#size)|Geçerli MapView nesnesinde öğelerin sayısını döndürür.|  
|[MapView::Split](#split)|Özgün MapView nesneyi iki MapView nesnelerini böler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `MapView`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  


## <a name="first"></a> MapView::First yöntemi
Harita Görünümü'nde ilk öğeyi belirleyen bir yineleyici döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita Görünümü'nde ilk öğeyi belirleyen bir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin, `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  MapView::HasKey yöntemi
Geçerli MapView belirtilen anahtarı içerip içermediğini belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 MapView öğeyi bulmak için kullanılan anahtar. Türünü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` anahtar bulunursa; Aksi takdirde, `false`.  
  


##  <a name="lookup"></a> MapView::Lookup yöntemi
V türünün türü K. belirtilen anahtarla ilişkili değeri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir öğe içinde MapView bulmak için kullanılan anahtar. Türünü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İle eşleştirilmiş değeri `key`. Dönüş değeri typename türüdür *V*.  
  


##  <a name="ctor"></a> MapView::MapView Oluşturucusu
MapView sınıfının yeni bir örneğini başlatır.  
  
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
 `InIt`  
 Geçerli MapView tür adı.  
  
 `comp`  
 İki öğenin değerlerini MapView kendi göreli sıralarını belirlemek için sıralama anahtarları olarak karşılaştırabilen bir işlev nesnesi.  
  
 `m`  
 Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir `map Class` geçerli MapView başlatmak için kullanılır.  
  
 `first`  
 Geçerli MapView başlatmak için kullanılan öğelerin bir aralıktaki ilk öğenin bir giriş yineleyici.  
  
 `last`  
 Geçerli MapView başlatmak için kullanılan öğelerin bir aralığını sonra ilk öğenin bir giriş yineleyici.  
  
 IL  
 A [std::initializer_list < std::pair\<K, V >>](../standard-library/initializer-list-class.md) öğeleri MapView eklenir.  



##  <a name="size"></a> MapView::Size yöntemi
Geçerli MapView nesnesinde öğelerin sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli MapView içindeki öğe sayısı.  
  


##  <a name="split"></a> MapView::Split yöntemi
Geçerli MapView nesne iki MapView nesnelerini böler. Bu yöntem çalışmaz.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>Parametreler  
 `firstPartition`  
 Özgün MapView nesnenin ilk bölümü.  
  
 `secondPartition`  
 Özgün MapView nesnenin ikinci bölümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, işlemsel değildir; hiçbir şey yapmaz.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)