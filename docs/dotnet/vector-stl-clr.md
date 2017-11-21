---
title: "vektör (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::vector
dev_langs: C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4ee3debcaf651a2a11ef51cac405edf816c5b8ba
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vector-stlclr"></a>vektör (STL/CLR)
Şablon sınıfı rastgele erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `vector` öğeleri dizisi bitişik bir blok depolama olarak yönetmek için. Blok büyür isteğe bağlı olarak bir dizi olarak uygulanır.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    ref class vector  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IVector<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[Vector::const_iterator (STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[Vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[Vector::const_reverse_iterator (STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[Vector::difference_type (STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[Vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[Vector::generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[Vector::generic_reverse_iterator (STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[Vector::generic_value (STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[Vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[Vector::Reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[Vector::reverse_iterator (STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[Vector::size_type (STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[Vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[Vector::Assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[Vector::AT (STL/CLR)](../dotnet/vector-at-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[Vector::Back (STL/CLR)](../dotnet/vector-back-stl-clr.md)|Son öğe erişir.|  
|[Vector::Begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[Vector::Capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|Kapsayıcı için ayrılan depolama alanı boyutunu raporlar.|  
|[Vector::Clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[Vector::Empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[Vector::End (STL/CLR)](../dotnet/vector-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[Vector::ERASE (STL/CLR)](../dotnet/vector-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[Vector::Front (STL/CLR)](../dotnet/vector-front-stl-clr.md)|İlk öğe erişir.|  
|[Vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)|Öğeleri belirtilen bir konumda ekler.|  
|[Vector::pop_back (STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|Son öğeyi kaldırır.|  
|[Vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[Vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[Vector::rend (STL/CLR)](../dotnet/vector-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[Vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|Kapsayıcı için en düşük büyüme kapasitesi sağlar.|  
|[Vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)|Öğe sayısını değiştirir.|  
|[Vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)|Öğe sayısını sayar.|  
|[Vector::Swap (STL/CLR)](../dotnet/vector-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[Vector::to_array (STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[Vector::Vector (STL/CLR)](../dotnet/vector-vector-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[Vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|Son öğe erişir.|  
|[Vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[Vector::operator = (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[Vector::operator(stl/CLR)](../dotnet/vector-operator-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[operator! = (vektör) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|Belirler bir `vector` nesne diğerine eşit değil `vector` nesnesi.|  
|[operator < (vektör) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|Belirler bir `vector` nesnesi, başka değerinden `vector` nesnesi.|  
|[operator < = (vektör) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Belirler bir `vector` nesnesidir değerinden küçük veya eşit başka `vector` nesnesi.|  
|[operator == (vektör) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|Belirler bir `vector` nesnesidir diğerine eşit `vector` nesnesi.|  
|[operator > (vektör) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|Belirler bir `vector` nesnesidir diğerinden daha büyük `vector` nesnesi.|  
|[operator > = (vektör) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Belirler bir `vector` nesnesidir büyük veya ona eşit diğerine `vector` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IList%601>|Yazılı öğeleri sıralı grubunu koruyun.|  
|IVector < değeri\>|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve depolanan bir dizi denetlediği dizisi için depolama boşaltır `Value` isteğe bağlı olarak büyür öğeleri. Büyüme yeni bir öğe ekleme maliyetini amortized sabit zaman olduğunu şekilde gerçekleşir. Diğer bir deyişle, sonunda öğe eklemek maliyeti, ortalama olarak büyük denetimli dizisi alır uzunluğu olarak artırmaz. Bu nedenle, bir vektör Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğunu [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `vector` ilk (ön) öğesinin sıfırdan sayım doğrudan sayısal konumuna verilen bir öğesine başvurabilir anlamına gelir destekler rasgele erişim yineleyiciler `size() - 1` son (arka) öğesi için. Ayrıca bir vektör Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğu anlamına gelir [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Vektör yineleyici onu atayan öğesi sapması yanı sıra, ilişkili vektör nesnesi için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. Vector öğesinin sapması konumuna ile aynıdır.  
  
 Ekleme veya öğeleri silme yineleyici tarafından atanan değer de değiştirebilmeniz için belirli bir konumda depolanan öğe değeri değiştirebilirsiniz. (Kapsayıcı delik INSERT önce oluşturmak veya bir silme sonra delik doldurmak için aşağı veya yukarı öğeleri kopyalamak gerekebilir.) Bununla birlikte, kendi sapmaya aralığında olduğu sürece vektör yineleyici geçerli kaldığı `[0, size()]`. Ayrıca, geçerli bir yineleyici dereferencable kalır--erişmek veya kendi sapmaya eşit değil sürece bunu atayan--öğe değerini değiştirmek için kullanmak `size()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı öğeleri silmiyor unutmayın.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/vektör >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [Vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)