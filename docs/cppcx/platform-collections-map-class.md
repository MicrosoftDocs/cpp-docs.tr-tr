---
title: "Platform::Collections sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
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
dev_langs: C++
helpviewer_keywords: Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3893f7213bc2b154851a5d2481070d0d43724bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections sınıfı
Temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>>  
ref class Map sealed;  
```  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar-değer çifti anahtar türü.  
  
 `V`  
 Anahtar-değer çiftinin değer türü.  
  
 `C`  
 İşlev nesnesi sağlayan bir türü göreli sıralarına eşlemesindeki belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırabilirsiniz. Varsayılan olarak, [std::less\<K >](../standard-library/less-struct.md).  
  
 __is_valid_winrt_type()  
 Derleyici türünü K ve V doğrular ve bir kolay hata iletisi türü eşlemesinde depoladıysanız sağlayan işlevi oluşturulur.  
  
### <a name="remarks"></a>Açıklamalar  
 İzin verilen türleri şunlardır:  
  
-   tamsayılar  
  
-   arabirim sınıfı ^  
  
-   Ortak ref sınıfı ^  
  
-   değer yapısı  
  
-   Ortak enum sınıfı  
  
 Harita, aslında için sarmalayıcı [std::map](../standard-library/map-class.md). C++ somut uyarlamasını olan [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408) ve [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) Windows çalışma zamanı arasında ortak geçirilen türleri arabirimi. Kullanmaya çalışırsa, bir `Platform::Collections::Map` türü ortak dönüş değeri veya parametre, derleyici hatası C3986 oluşturulur. Parametresi veya dönüş değerinin türünü değiştirerek hatayı düzeltmek [Windows::Foundation::Collections::IMap\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Daha fazla bilgi için bkz: [koleksiyonları](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Map::Map](#ctor)|Harita sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Map::Clear](#clear)|Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.|  
|[Map::First](#first)|İlk öğe eşlemesinde belirtir yineleyici döndürür.|  
|[Map::GetView](#getview)|Geçerli eşlemesi salt okunur bir görünümünü verir; diğer bir deyişle, bir [Platform::Collections::MapView sınıfı](../cppcx/platform-collections-mapview-class.md).|  
|[Map::HasKey](#haskey)|Geçerli eşlemesi belirtilen anahtarı içerip içermediğini belirler.|  
|[Map::INSERT](#insert)|Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.|  
|[Map::Lookup](#lookup)|Geçerli harita nesnesi belirtilen anahtar öğede alır.|  
|[Map::Remove](#remove)|Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.|  
|[Map::size](#size)|Geçerli harita nesnesinde öğe sayısını döndürür.|  
  
### <a name="events"></a>Olaylar  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[Map::MapChanged](#mapchanged-event.md)`event`|Harita değiştiğinde gerçekleşir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Map`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="clear"></a>Map::Clear yöntemi
Tüm anahtar-değer çiftleri geçerli harita nesnesinden kaldırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void Clear();   
```  
  


## <a name="first"></a>Map::First yöntemi
İlk öğe eşlemesinde belirtir yineleyici döndürür veya `nullptr` harita boşsa.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe eşlemesinde belirtir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myMap->First();`.  
  


## <a name="getview"></a>Map::GetView yöntemi
Geçerli eşlemesi salt okunur bir görünümünü verir; diğer bir deyişle, bir [Platform::Collections::MapView sınıfı](../cppcx/platform-collections-mapview-class.md), hangi uygulayan [Windows::Foundation::Collections::IMapView\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) arabirimi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
Windows::Foundation::Collections::IMapView<K, V>^ GetView();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `MapView` nesnesi.  
  


## <a name="haskey"></a>Map::HasKey yöntemi
Geçerli eşlemesi belirtilen anahtarı içerip içermediğini belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Map öğesi bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`anahtar bulunursa; Aksi takdirde `false`.  
  


## <a name="insert"></a>Map::INSERT yöntemi
Geçerli harita nesnesi belirtilen anahtar-değer çifti ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual bool Insert(K key, V value);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar-değer çifti anahtar bölümünü. Türü `key` TypeName *K*.  
  
 `value`  
 Anahtar-değer çiftinin değer bölümünü. Türü `value` TypeName *V*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Geçerli eşlemesindeki var olan bir öğe anahtarı eşleşip eşleşmediğini `key` ve o öğenin değeri kısmı kümesine `value`. `false`Geçerli eşlemesindeki var olan bir öğe eşleşmiyorsa `key` ve `key` ve `value` parametreleri bir anahtar-değer çifti yapılan ve geçerli eşlemesi eklendi.  
  


## <a name="lookup"></a>Map::Lookup yöntemi
Anahtar varsa türü K, belirtilen anahtarla ilişkilendirilen değeri türü V alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir öğenin eşlemesinde bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İle eşleştirilmiş değeri `key`. Dönüş değeri typename türüdür *V*.  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtar mevcut değilse, sonra bir [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) atılır.  
  


## <a name="ctor"></a>Map::Map Oluşturucusu
Harita sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
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
 `InIt`  
 Geçerli eşlemesi typename.  
  
 `comp`  
 İşlev nesnesi sağlayan bir türü göreli sıralarına eşlemesindeki belirlemek için sıralama anahtarları olarak iki öğenin değerleri karşılaştırabilirsiniz.  
  
 `m`  
 Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir `map Class` geçerli eşlemesi başlatmak için kullanılır.  
  
 `first`  
 Geçerli eşlemesi başlatmak için kullanılan öğelerin bir aralıktaki ilk öğe giriş yineleyici.  
  
 `last`  
 İlk öğeden sonra öğeleri geçerli eşlemesi başlatmak için kullanılan bir dizi giriş yineleyici.  
  


## <a name="mapchanged"></a>Map::MapChanged olayı
Bir öğe eklenen veya eşleme kaldırılmış tetiklenir.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) olay ve tür oluştu değişiklik yükseltilmiş nesne hakkında bilgiler içerir. Ayrıca bkz. [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) ve [CollectionChange numaralandırma](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## <a name="net-framework-equivalent"></a>.NET Framework Eşdeğeri  
 C# veya Visual Basic kullanan Windows mağazası uygulamaları proje IMAP\<K, V > IDictionary olarak\<K, V >.  
  


## <a name="remove"></a>Map::Remove yöntemi
Belirtilen anahtar-değer çifti geçerli harita nesneyi siler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void Remove(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar-değer çifti anahtar bölümünü. Türü `key` TypeName *K*.  
  


## <a name="size"></a>Map::size yöntemi
Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) harita öğeler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita öğe sayısı.  
  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)