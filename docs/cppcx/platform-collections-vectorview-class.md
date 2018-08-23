---
title: 'Platform::Collections:: vectorview sınıfı | Microsoft Docs'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs:
- C++
helpviewer_keywords:
- VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0020937bae5f6392c7d9e5e8daf22f3cc4e6a31
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42584112"
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections:: vectorview sınıfı
Sıralı bir koleksiyonu tek tek dizin tarafından erişilebilen bir nesne salt okunur bir görünümünü temsil eder. Koleksiyondaki her bir nesnenin türü şablon parametresi tarafından belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İçindeki öğe türünü `VectorView` nesne.  
  
 `E`  
 Türündeki değerlerle eşitlik testi için bir ikili koşula belirtir `T`. Varsayılan değer `std::equal_to<T>` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 `VectorView` Sınıfının Implements [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) arabirimi ve standart Şablon kitaplığı yineleyicilerine desteği.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|VectorView sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorView::First](#first)|VectorView ilk öğeyi belirleyen bir yineleyici döndürür.|  
|[VectorView::GetAt](#getat)|Belirtilen dizin tarafından belirtilen geçerli VectorView öğesi alır.|  
|[VectorView::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli VectorView öğelerinin bir dizisini alır.|  
|[VectorView::IndexOf](#indexof)|Geçerli VectorView belirtilen öğeyi arar ve bulundu, döndürür öğenin dizini.|  
|[VectorView::Size](#size)|Geçerli VectorView nesnesinde öğelerin sayısını döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VectorView`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="first"></a>  VectorView::First yöntemi
VectorView ilk öğeyi belirleyen bir yineleyici döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 VectorView ilk öğeyi belirleyen bir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak First() tarafından döndürülen yineleyici tutmak için kullanışlı bir yol olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin, `auto x = myVectorView->First();`.  
  


## <a name="getat"></a>  VectorView::GetAt yöntemi
Belirtilen dizin tarafından belirtilen geçerli VectorView öğesi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğenin VectorView nesnesinde belirten sıfır tabanlı, işaretsiz bir tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen öğenin `index` parametresi. Öğe türü VectorView şablon parametresi tarafından belirtilen *T*.  
  


## <a name="getmany"></a>  VectorView::GetMany yöntemi
Belirtilen dizinden başlayarak geçerli VectorView öğelerinin bir dizisini alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual unsigned int GetMany(  
   unsigned int startIndex,   
   ::Platform::WriteOnlyArray<T>^ dest  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `startIndex`  
 Alınacak öğelerin başladığı sıfır tabanlı dizini.  
  
 `dest`  
 Bu işlem tamamlandığında, bir dizi tarafından belirtilen öğede başlayan öğeleri `startIndex` ve sonunda VectorView içerisindeki son öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısını alınır.  
  


## <a name="indexof"></a>  VectorView::IndexOf yöntemi
Geçerli VectorView belirtilen öğeyi arar ve bulundu, döndürür öğenin dizini.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual bool IndexOf(  
   T value,  
   unsigned int* index  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `value`  
 Bulunacak öğe.  
  
 `index`  
 Öğenin sıfır tabanlı dizini, parametre `value` bulundu; Aksi takdirde, 0.  
  
 `index` Parametresi ise 0 öğe VectorView ilk öğesidir ya da öğe bulunamadı. Dönüş değeri ise `true`, öğe bulundu ve ilk öğedir; Aksi takdirde, öğe bulunamadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Belirtilen öğe bulunursa; Aksi takdirde, `false`.  
  


## <a name="size"></a>  VectorView::Size yöntemi
Geçerli VectorView nesnesinde öğelerin sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorView içindeki öğe sayısı.  
  


## <a name="ctor"></a>  VectorView::VectorView Oluşturucusu
VectorView sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `InIt`  
 Geçerli VectorView başlatmak için kullanılan bir koleksiyon nesnelerin türü.  
  
 IL  
 A [std::initializer_list](../standard-library/initializer-list-class.md) öğeleri VectorView başlatmak için kullanılır.  
  
 `N`  
 Bir koleksiyondaki öğeleri geçerli VectorView başlatmak için kullanılan nesnelerin sayısı.  
  
 `size`  
 VectorView içindeki öğe sayısı.  
  
 `value`  
 Her bir öğesinde geçerli VectorView başlatmak için kullanılan bir değer.  
  
 `v`  
 Bir [Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) için bir [std::vector](../standard-library/vector-class.md) geçerli VectorView başlatmak için kullanılır.  
  
 `ptr`  
 İşaretçi bir `std::vector` geçerli VectorView başlatmak için kullanılır.  
  
 `arr`  
 A [Platform::Array](../cppcx/platform-array-class.md) geçerli VectorView başlatmak için kullanılan nesne.  
  
 `a`  
 A [std::array](../standard-library/array-class-stl.md) geçerli VectorView başlatmak için kullanılan nesne.  
  
 `first`  
 Geçerli VectorView başlatmak için kullanılan nesnelerin bir dizideki ilk öğe. Türünü `first` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Son öğeden bir dizideki nesnelerin geçerli VectorView başlatmak için kullanılır. Türünü `last` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)