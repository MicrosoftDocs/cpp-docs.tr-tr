---
title: "Platform::Collections::VectorView sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::VectorView::VectorView
- COLLECTION/Platform::Collections::VectorView::First
- COLLECTION/Platform::Collections::VectorView::GetAt
- COLLECTION/Platform::Collections::VectorView::GetMany
- COLLECTION/Platform::Collections::VectorView::IndexOf
- COLLECTION/Platform::Collections::VectorView::Size
dev_langs: C++
helpviewer_keywords: VectorView Class
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8ef351759814ee03b54160cac2340eafd304d5f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsvectorview-class"></a>Platform::Collections::VectorView sınıfı
Sıralı bir koleksiyonu dizini tarafından erişilebilecek nesnelerin salt okunur bir görünümünü temsil eder. Koleksiyondaki her nesne türü şablon parametresi tarafından belirtilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 İçindeki öğe türü `VectorView` nesnesi.  
  
 `E`  
 Eşitlik türü değerleri ile test için ikili bir koşul belirtir `T`. Varsayılan değer `std::equal_to<T>` şeklindedir.  
  
### <a name="remarks"></a>Açıklamalar  
 `VectorView` Uygulayan sınıf [Windows::Foundation::Collections::IVectorView\<T >](http://go.microsoft.com/fwlink/p/?LinkId=262411) arabirimi ve standart Şablon kitaplığı yineleyiciler desteği.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorView::VectorView](#ctor)|VectorView sınıfının yeni bir örneğini başlatır.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[VectorView::First](#first)|İlk öğe VectorView belirten yineleyici döndürür.|  
|[VectorView::GetAt](#getat)|Belirtilen dizini tarafından belirtilen geçerli VectorView öğesi alır.|  
|[VectorView::GetMany](#getmany)|Belirtilen dizinden başlayarak geçerli VectorView öğelerinin bir dizisini alır.|  
|[VectorView::IndexOf](#indexof)|Geçerli VectorView belirtilen öğeyi arar ve bulundu, döndürür öğenin dizini.|  
|[VectorView::Size](#size)|Geçerli VectorView nesnesinde öğe sayısını döndürür.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VectorView`  
  
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** collection.h  
  
 **Namespace:** Platform::Collections  

## <a name="first"></a>VectorView::First yöntemi
İlk öğe VectorView belirten yineleyici döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk öğe VectorView belirtir yineleyici.  
  
### <a name="remarks"></a>Açıklamalar  
 Dönüş değeri ile bildirilen bir değişken atamak için First() tarafından döndürülen yineleyici tutmak için kolay bir yol olduğu **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myVectorView->First();`.  
  


## <a name="getat"></a>VectorView::GetAt yöntemi
Belirtilen dizini tarafından belirtilen geçerli VectorView öğesi alır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
T GetAt(  
   UInt32 index  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 `index`  
 Belirli bir öğeyle VectorView nesnesinde belirtir sıfır tabanlı, imzalanmamış bir tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen öğenin `index` parametresi. Öğe türü VectorView şablon parametresi tarafından belirtilen *T*.  
  


## <a name="getmany"></a>VectorView::GetMany yöntemi
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
 Alınacak öğeleri başlangıcı sıfır tabanlı dizini.  
  
 `dest`  
 Bu işlem tamamlandığında, bir dizi tarafından belirtilen öğede başlayan öğeleri `startIndex` ve VectorView son öğesi sonunda.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısı aldı.  
  


## <a name="indexof"></a>VectorView::IndexOf yöntemi
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
 Öğenin sıfır tabanlı dizini varsa parametre `value` bulundu; Aksi takdirde, 0.  
  
 `index` Parametresi ise 0 öğe VectorView ilk öğedir veya öğe bulunamadı. Dönüş değeri ise `true`, öğe bulundu ve ilk öğedir; Aksi halde, öğe bulunamadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`Belirtilen öğe bulunursa; Aksi takdirde `false`.  
  


## <a name="size"></a>VectorView::Size yöntemi
Geçerli VectorView nesnesinde öğe sayısını döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli VectorView öğe sayısı.  
  


## <a name="ctor"></a>VectorView::VectorView Oluşturucusu
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
 Geçerli VectorView başlatmak için kullanılan nesneleri koleksiyonu türü.  
  
 IL  
 A [std::initializer_list](../standard-library/initializer-list-class.md) öğeleri VectorView başlatmak için kullanılır.  
  
 `N`  
 Geçerli VectorView başlatmak için kullanılan nesneleri koleksiyonu öğe sayısı.  
  
 `size`  
 VectorView öğe sayısı.  
  
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
 Geçerli VectorView başlatmak için kullanılan nesnelerinin bir dizisi ilk öğe. Türü `first` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Geçerli VectorView başlatmak için kullanılan nesnelerinin bir dizisi son öğesi. Türü `last` yoluyla geçirilen *kusursuz iletme*. Daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)   
 [C++'ta Windows çalışma zamanı bileşenleri oluşturma](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)