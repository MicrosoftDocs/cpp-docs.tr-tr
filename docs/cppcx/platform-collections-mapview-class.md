---
title: Platform::Collections::MapView sınıfı | Microsoft Docs
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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b5000ad06e542aa4616a29150601b8d628fc097
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33091537"
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView sınıfı
Salt okunur bir görünüme temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.  
  
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
 Anahtar-değer çiftinin değer türü.  
  
 `C`  
 İşlev nesnesi sağlayan bir tür MapView içindeki göreli sıralarına belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırabilirsiniz. Varsayılan olarak, [std::less\<K >](../standard-library/less-struct.md).  
  
### <a name="remarks"></a>Açıklamalar  
 MapView olan somut bir C++ uygulaması [Windows::Foundation::Collections::IMapView \<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) uygulama ikili arabirimi (ABI) geçirilir arabirimi. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MapView::MapView](#ctor)|MapView sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[MapView::First](#first)|Başlatılmış bir yineleyici harita görünümünü ilk öğe döndürür.|  
|[MapView::HasKey](#haskey)|Geçerli MapView belirtilen anahtarı içerip içermediğini belirler.|  
|[MapView::Lookup](#lookup)|Belirtilen anahtar geçerli MapView nesnesindeki öğede alır.|  
|[MapView::Size](#size)|Geçerli MapView nesnesinde öğe sayısını döndürür.|  
|[MapView::Split](#split)|Özgün MapView nesneyi iki MapView nesnelerine ayırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `MapView`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  


## <a name="first"></a> MapView::First yöntemi
Harita görünümünü ilk öğe belirten yineleyici döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita görünümünü ilk öğe belirtir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  MapView::HasKey yöntemi
Geçerli MapView belirtilen anahtarı içerip içermediğini belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 MapView öğesi bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` anahtar bulunursa; Aksi takdirde `false`.  
  


##  <a name="lookup"></a> MapView::Lookup yöntemi
V türü türü K. belirtilen anahtarla ilişkili değeri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir öğenin MapView bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
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
 Geçerli MapView typename.  
  
 `comp`  
 İki öğenin değerleri MapView içindeki göreli sıralarına belirlemek için sıralama anahtarları olarak karşılaştırabilirsiniz işlev nesnesi.  
  
 `m`  
 Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir `map Class` geçerli MapView başlatmak için kullanılır.  
  
 `first`  
 Geçerli MapView başlatmak için kullanılan öğelerin bir aralıktaki ilk öğe giriş yineleyici.  
  
 `last`  
 İlk öğeden sonra öğeleri geçerli MapView başlatmak için kullanılan bir dizi giriş yineleyici.  
  
 IL  
 A [std::initializer_list < std::pair\<K, V >>](../standard-library/initializer-list-class.md) öğeleri MapView eklenecek.  



##  <a name="size"></a> MapView::Size yöntemi
Geçerli MapView nesnesinde öğe sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli MapView öğe sayısı.  
  


##  <a name="split"></a> MapView::Split yöntemi
Geçerli MapView nesne iki MapView nesnelerine böler. Bu yöntem çalışmaz.  
  
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
 Özgün MapView nesne ilk kısmı.  
  
 `secondPartition`  
 Özgün MapView nesne ikinci bölümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem işlemsel değil; hiçbir şey yapmaz.  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)