---
title: "Platform::Collections:: unorderedmapview sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- collection/Platform::Collections::UnorderedMapView
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1bb555cc804069aed3c778acf1ac71e795a11ff
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="platformcollectionsunorderedmapview-class"></a>Platform::Collections::UnorderedMapView Sınıfı
Salt okunur bir görünüme temsil eden bir *harita*, anahtar-değer çiftleri koleksiyonu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>>  
ref class UnorderedMapView sealed;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar-değer çifti anahtar türü.  
  
 `V`  
 Anahtar-değer çiftinin değer türü.  
  
 `C`  
 İşlev nesnesi sağlayan bir türü eşitlik için iki anahtar değeri karşılaştırabilirsiniz. Varsayılan olarak, [std::equal_to\<K >](../standard-library/equal-to-struct.md)  
  
### <a name="remarks"></a>Açıklamalar  
 UnorderedMapView olan somut bir C++ uygulaması [Windows::Foundation::Collections::IMapView\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) uygulama ikili arabirimi (ABI) geçirilir arabirimi. Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[UnorderedMapView::UnorderedMapView](#ctor)|UnorderedMapView sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[UnorderedMapView::First](#first)|Başlatılmış bir yineleyici harita görünümünü ilk öğe döndürür.|  
|[UnorderedMapView::HasKey](#haskey)|Geçerli UnorderedMapView belirtilen anahtarı içerip içermediğini belirler.|  
|[UnorderedMapView::Lookup](#lookup)|Belirtilen anahtar geçerli UnorderedMapView nesnesindeki öğede alır.|  
|[UnorderedMapView::Size](#size)|Geçerli UnorderedMapView nesnesinde öğe sayısını döndürür.|  
|[UnorderedMapView::Split](#split)|Özgün UnorderedMapView nesneyi iki UnorderedMapView nesnelerine ayırır.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `UnorderedMapView`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="first"></a>  UnorderedMapView::First yöntemi
İlk belirtir yineleyici döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) sırasız eşlemesindeki öğesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp   
virtual Windows::Foundation::Collections::IIterator<  
    Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
    First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita görünümünü ilk öğe belirtir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  UnorderedMapView::HasKey yöntemi
Geçerli UnorderedMap belirtilen anahtarı içerip içermediğini belirler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Öğeyi bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` anahtar bulunursa; Aksi takdirde `false`.  
  


## <a name="lookup"></a>  UnorderedMapView::Lookup yöntemi
V türü türü K. belirtilen anahtarla ilişkili değeri alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bir öğenin UnorderedMapView bulmak için kullanılan anahtar. Türü `key` TypeName *K*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İle eşleştirilmiş değeri `key`. Dönüş değeri typename türüdür *V*.  
  


## <a name="size"></a>  UnorderedMapView::Size yöntemi
Sayısını döndürür [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) UnorderedMapView öğeler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sırasız MapView öğe sayısı.  
  


## <a name="split"></a>  UnorderedMapView::Split yöntemi
Geçerli UnorderedMapView nesne iki UnorderedMapView nesnelerine böler. Bu yöntem çalışmaz.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K,V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>Parametreler  
 `firstPartition`  
 Özgün UnorderedMapView nesne ilk kısmı.  
  
 `secondPartition`  
 Özgün UnorderedMapView nesne ikinci bölümü.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem işlemsel değil; hiçbir şey yapmaz.  
  


## <a name="ctor"></a>  UnorderedMapView::UnorderedMapView Oluşturucusu
UnorderedMapView sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
UnorderedMapView();    
explicit UnorderedMapView(size_t n);   
UnorderedMapView(size_t n, const H& h);   
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m);  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m);  
  
template <typename InIt> UnorderedMapView(InIt first, InIt last );  
template <typename InIt> UnorderedMapView(InIt first, InIt last, size_t n );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p );  
  
UnorderedMapView(std::initializer_list<std::pair<const K, V>);  
  
UnorderedMapView(std::initializer_list< std::pair<const K, V>> il, size_t n   
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h);  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p );  
```  
  
### <a name="parameters"></a>Parametreler  
 n  
 Alan erişinceye öğe sayısı.  
  
 `InIt`  
 UnorderedMapView typename.  
  
 `H`  
 Bir anahtar için bir karma değer için bir işlev nesnesi. Varsayılan olarak [std::hash\<K >](http://msdn.microsoft.com/en-us/54f67435-af9d-4217-a29d-fa4d2491a104) türleri için `std::hash` destekler.  
  
 `P`  
 İşlev nesnesi sağlayan bir türü kendi eşitlik belirlemek için iki anahtar karşılaştırabilirsiniz. Varsayılan olarak [std::equal_to\<K >](../standard-library/equal-to-struct.md).  
  
 `m`  
 Bir başvuru veya [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::unordered_map](../standard-library/unordered-map-class.md) UnorderedMapView başlatmak için kullanılır.  
  
 `first`  
 UnorderedMapView başlatmak için kullanılan öğelerin bir aralıktaki ilk öğe giriş yineleyici.  
  
 `last`  
 İlk öğeden sonra öğeleri UnorderedMapView başlatmak için kullanılan bir dizi giriş yineleyici.  
   
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform::Collections Namespace](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)