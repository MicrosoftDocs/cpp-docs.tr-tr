---
title: "Platform::Collections:: Vector sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Vector::Vector
- COLLECTION/Platform::Collections::Vector::Append
- COLLECTION/Platform::Collections::Vector::Clear
- COLLECTION/Platform::Collections::Vector::First
- COLLECTION/Platform::Collections::Vector::GetAt
- COLLECTION/Platform::Collections::Vector::GetMany
- COLLECTION/Platform::Collections::Vector::GetView
- COLLECTION/Platform::Collections::Vector::IndexOf
- COLLECTION/Platform::Collections::Vector::InsertAt
- COLLECTION/Platform::Collections::Vector::ReplaceAll
- COLLECTION/Platform::Collections::Vector::RemoveAt
- COLLECTION/Platform::Collections::Vector::RemoveAtEnd
- COLLECTION/Platform::Collections::Vector::SetAt
- COLLECTION/Platform::Collections::Vector::Size
- COLLECTION/Platform::Collections::Vector::VectorChanged
dev_langs: C++
helpviewer_keywords: Vector Class (C++/Cx)
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 35299f80b85432286859ed76afdd7a599809f67f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="platformcollectionsvector-class"></a>Platform::Collections:: Vector sınıfı
Dizini tarafından erişilebilecek nesnelerin sıralı bir koleksiyonu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Vektör nesnesinde bulunan öğelerin türü.  
  
 `E`  
 Eşitlik türü değerleri ile test için ikili bir koşul belirtir `T`. Varsayılan değer `std::equal_to<T>` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 İzin verilen türleri şunlardır:  
  
1.  tamsayılar  
  
2.  arabirim sınıfı ^  
  
3.  Ortak ref sınıfı ^  
  
4.  değer yapısı  
  
5.  Ortak enum sınıfı  
  
 Vector sınıfı C++ somut uygulamasıdır [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410) arabirimi.  
  
 Vector türü bir public kullanmayı denerseniz, değeri veya parametre, C3986 gerçekleştirilecektir derleyici hatası döndürür. Parametre değiştirerek hatayı düzeltin ya da dönüş değeri türü [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410). Daha fazla bilgi için bkz: [koleksiyonlar (C + +/ CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Vector::Vector](#ctor)|Vector sınıfı yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Vector::Append](#append)|Geçerli vektör son öğeden sonra belirtilen öğeyi ekler.|  
|[Vector::Clear](#clear)|Geçerli vektör tüm öğeler siler.|  
|[Vector::First](#first)|İlk öğe vektörü belirtir yineleyici döndürür.|  
|[Vector::GetAt](#getat)|Belirtilen dizin tarafından identifed olan geçerli vektör öğesi alır.|  
|[Vector::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli vektör öğelerinin bir dizisini alır.|  
|[Vector::GetView](#getview)|Vektör salt okunur bir görünümünü verir; diğer bir deyişle, bir [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector::IndexOf](#indexof)|Geçerli vektör belirtilen öğeyi arar ve bulundu, döndürür öğenin dizini.|  
|[Vector::InsertAt](#insertat)|Belirtilen öğe belirtilen dizin tarafından tanımlanan öğesinden sonra geçerli vektör ekler.|  
|[Vector::ReplaceAll](#replaceall)|Geçerli vektör öğelerinde siler ve sonra belirtilen dizisinden öğeleri ekler.|  
|[Vector::RemoveAt](#removeat)|Geçerli vektör belirtilen dizinden tarafından tanımlanan öğesini siler.|  
|[Vector::RemoveAtEnd](#removeatend)|Geçerli vektör ucundaki öğe siler.|  
|[Vector::SetAt](#setat)|Belirtilen dizini tarafından tanımlanan geçerli vektör öğesinde belirtilen değeri atar.|  
|[Vector::size](#size)|Geçerli vektör nesnesinde öğe sayısını döndürür.|  
  
### <a name="events"></a>Olaylar  
  
|||  
|-|-|  
|Ad|Açıklama|  
|olay [Windows::Foundation::Collection::VectorChangedEventHandler\<T > ^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Vektör değiştiğinde gerçekleşir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Vector`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="append"></a>Vector::Append yöntemi
Geçerli vektör son öğeden sonra belirtilen öğeyi ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void Append(T item);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Vektör eklenecek öğe. Türü `item` tarafından tanımlanan *T* typename.  
  


## <a name="clear"></a>Vector::Clear yöntemi
Geçerli vektör tüm öğeler siler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void Clear();  
```   


## <a name="first"></a>Vector::First yöntemi
Yineleyici işaret vektör ilk öğe döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^ First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Vektör ilk öğe işaret yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myVector->First();`. Bu yineleyici koleksiyonun uzunluğundan bilir.  
  
 Bir STL işleve yineleyiciler çifti gerektiğinde boş işlevleri kullanın [Windows::Foundation::Collections:: başlamak](../cppcx/begin-function.md) ve [Windows::Foundation::Collections::end](../cppcx/end-function.md)  
  


## <a name="getat"></a>Vector::GetAt yöntemi
Belirtilen dizin tarafından identifed olan geçerli vektör öğesi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual T GetAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğeyle vektör nesnesinde belirtir sıfır tabanlı, imzalanmamış bir tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen öğenin `index` parametresi. Öğe türü tarafından tanımlanan *T* typename.  
  


## <a name="getmany"></a>Vector::GetMany yöntemi
Belirtilen dizinden başlayarak geçerli vektör öğelerinin bir dizisini alır ve bunları arayana ayrılan diziye kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual unsigned int GetMany(
    unsigned int startIndex, 
    Platform::WriteOnlyArray<T>^ dest);  
```  
  
### <a name="parameters"></a>Parametreler  
 `startIndex`  
 Alınacak öğeleri başlangıcı sıfır tabanlı dizini.  
  
 `dest`  
 Belirtilen öğede başlayan öğeleri çağıran tarafından ayrılmış bir dizi `startIndex` ve vektör son öğesi sonunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısı aldı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, doğrudan istemci kodu tarafından kullanılmak üzere tasarlanmamıştır. Dahili olarak kullanılan [to_vector işlevi](../cppcx/to-vector-function.md) std::vector örnekleri Platform::Vector intances verimli dönüşümünü etkinleştirmek için.  
  


## <a name="getview"></a>Vector::GetView yöntemi
Vektör salt okunur bir görünümünü verir; diğer bir deyişle, bir IVectorView.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
Windows::Foundation::Collections::IVectorView<T>^ GetView();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 IVectorView nesne.  
  


## <a name="indexof"></a>Vector::IndexOf yöntemi
Geçerli vektör belirtilen öğeyi arar ve bulundu, döndürür öğenin dizini.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual bool IndexOf(T value, unsigned int* index);  
```  
  
### <a name="parameters"></a>Parametreler  
 `value`  
 Bulunacak öğe.  
  
 `index`  
 Öğenin sıfır tabanlı dizini varsa parametre `value` bulundu; Aksi takdirde, 0.  
  
 `index` Parametresi ise 0 öğe vektör ilk öğedir veya öğe bulunamadı. Dönüş değeri ise `true`, öğe bulundu ve ilk öğedir; Aksi halde, öğe bulunamadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Belirtilen öğe bulunursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 IndexOf std::find_if öğesini bulmak için kullanır. Özel öğe türü == bu nedenle tekrar ve! = işleci eşitlik etkinleştirmek için bu find_if karşılaştırmaları gerektirir.  
  


##  <a name="insertat"></a>Vector::InsertAt yöntemi
Belirtilen öğe belirtilen dizin tarafından tanımlanan öğesinden sonra geçerli vektör ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void InsertAt(unsigned int index, T item)  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğeyle vektör nesnesinde belirtir sıfır tabanlı, imzalanmamış bir tamsayı.  
  
 `item`  
 Tarafından belirtilen öğesinden sonra vektör eklemek için bir öğe `index`. Türü `item` tarafından tanımlanan *T* typename.  
  


## <a name="removeat"></a>Vector::RemoveAt yöntemi
Geçerli vektör belirtilen dizinden tarafından tanımlanan öğesini siler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void RemoveAt(unsigned int index);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğeyle vektör nesnesinde belirtir sıfır tabanlı, imzalanmamış bir tamsayı.  
  


## <a name="removeatend"></a>Vector::RemoveAtEnd yöntemi
Geçerli vektör ucundaki öğe siler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void RemoveAtEnd();  
```  
  


## <a name="replaceall"></a>Vector::ReplaceAll yöntemi
Geçerli vektör öğelerinde siler ve sonra belirtilen dizisinden öğeleri ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void ReplaceAll(const ::Platform::Array<T>^ arr);  
```  
  
### <a name="parameters"></a>Parametreler  
 `arr`  
 Türü tarafından tanımlanan nesneleri içeren bir dizi *T* typename.  
  


## <a name="setat"></a>Vector::SetAt yöntemi
Belirtilen dizini tarafından tanımlanan geçerli vektör öğesinde belirtilen değeri atar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual void SetAt(unsigned int index, T item);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğeyle vektör nesnesinde belirtir sıfır tabanlı, imzalanmamış bir tamsayı.  
  
 `item`  
 Belirtilen öğe atanacak değer. Türü `item` tarafından tanımlanan *T* typename.  
  


## <a name="size"></a>Vector::size yöntemi
Geçerli vektör nesnesinde öğe sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli vektör öğe sayısı.  
  


## <a name="ctor"></a>Vector::Vector Oluşturucusu
Vector sınıfı yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
Vector();  
  
explicit Vector(unsigned int size);  
Vector( unsigned int size, T value);    
template <typename U> explicit Vector( const ::std::vector<U>& v);    
template <typename U> explicit Vector( std::vector<U>&& v);    

Vector( const T * ptr, unsigned int size);    
template <size_t N> explicit Vector(const T(&arr)[N]);    
template <size_t N> explicit Vector(const std::array<T, N>& a);   
explicit Vector(const Array<T>^ arr);  
  
template <typename InIt> Vector(InIt first, InIt last);   
Vector(std::initializer_list<T> il);  
```  
  
### <a name="parameters"></a>Parametreler  
 bir  
 A [std::array](../standard-library/array-class-stl.md) vektör başlatmak için kullanılır.  
  
 bir  
 A [Platform::Array](../cppcx/platform-array-class.md) vektör başlatmak için kullanılır.  
  
 `InIt`  
 Geçerli vektör başlatmak için kullanılan nesneleri koleksiyonu türü.  
  
 IL  
 A [std::initializer_list](../standard-library/initializer-list-class.md) nesne türü `T` vektör başlatmak için kullanılır.  
  
 `N`  
 Geçerli vektör başlatmak için kullanılan nesneleri koleksiyonu öğe sayısı.  
  
 `size`  
 Vektör öğe sayısı.  
  
 `value`  
 Her bir öğesinde geçerli vektör başlatmak için kullanılan bir değer.  
  
 `v`  
 Bir [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::vector](../standard-library/vector-class.md) geçerli vektör başlatmak için kullanılır.  
  
 `ptr`  
 İşaretçi bir `std::vector` geçerli vektör başlatmak için kullanılır.  
  
 `arr`  
 A [Platform::Array](../cppcx/platform-array-class.md) geçerli vektör başlatmak için kullanılan nesne.  
  
 `a`  
 A [std::array](../standard-library/array-class-stl.md) geçerli vektör başlatmak için kullanılan nesne.  
  
 `first`  
 Geçerli vektör başlatmak için kullanılan nesnelerinin bir dizisi ilk öğe. Türü `first` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Geçerli vektör başlatmak için kullanılan nesnelerinin bir dizisi son öğesi. Türü `last` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)