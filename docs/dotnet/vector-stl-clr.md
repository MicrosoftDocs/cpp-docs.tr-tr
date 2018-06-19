---
title: vektör (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- cliext::vector
dev_langs:
- C++
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: de5d09d569933dc06666ed2008081703d59c1564
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172644"
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
|[vector::const_iterator (STL/CLR)](../dotnet/vector-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[vector::const_reference (STL/CLR)](../dotnet/vector-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[vector::const_reverse_iterator (STL/CLR)](../dotnet/vector-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[vector::difference_type (STL/CLR)](../dotnet/vector-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[vector::generic_container (STL/CLR)](../dotnet/vector-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[vector::generic_iterator (STL/CLR)](../dotnet/vector-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[vector::generic_reverse_iterator (STL/CLR)](../dotnet/vector-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[vector::generic_value (STL/CLR)](../dotnet/vector-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[vector::iterator (STL/CLR)](../dotnet/vector-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[vector::reference (STL/CLR)](../dotnet/vector-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[vector::reverse_iterator (STL/CLR)](../dotnet/vector-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[vector::size_type (STL/CLR)](../dotnet/vector-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[vector::value_type (STL/CLR)](../dotnet/vector-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[vector::assign (STL/CLR)](../dotnet/vector-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[vector::at (STL/CLR)](../dotnet/vector-at-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[vector::back (STL/CLR)](../dotnet/vector-back-stl-clr.md)|Son öğe erişir.|  
|[vector::begin (STL/CLR)](../dotnet/vector-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[vector::capacity (STL/CLR)](../dotnet/vector-capacity-stl-clr.md)|Kapsayıcı için ayrılan depolama alanı boyutunu raporlar.|  
|[vector::clear (STL/CLR)](../dotnet/vector-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[vector::empty (STL/CLR)](../dotnet/vector-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[vector::end (STL/CLR)](../dotnet/vector-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[vector::erase (STL/CLR)](../dotnet/vector-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[vector::front (STL/CLR)](../dotnet/vector-front-stl-clr.md)|İlk öğe erişir.|  
|[vector::insert (STL/CLR)](../dotnet/vector-insert-stl-clr.md)|Öğeleri belirtilen bir konumda ekler.|  
|[vector::pop_back (STL/CLR)](../dotnet/vector-pop-back-stl-clr.md)|Son öğeyi kaldırır.|  
|[vector::push_back (STL/CLR)](../dotnet/vector-push-back-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[vector::rbegin (STL/CLR)](../dotnet/vector-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[vector::rend (STL/CLR)](../dotnet/vector-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[vector::reserve (STL/CLR)](../dotnet/vector-reserve-stl-clr.md)|Kapsayıcı için en düşük büyüme kapasitesi sağlar.|  
|[vector::resize (STL/CLR)](../dotnet/vector-resize-stl-clr.md)|Öğe sayısını değiştirir.|  
|[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)|Öğe sayısını sayar.|  
|[vector::swap (STL/CLR)](../dotnet/vector-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[vector::to_array (STL/CLR)](../dotnet/vector-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[vector::vector (STL/CLR)](../dotnet/vector-vector-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[vector::back_item (STL/CLR)](../dotnet/vector-back-item-stl-clr.md)|Son öğe erişir.|  
|[vector::front_item (STL/CLR)](../dotnet/vector-front-item-stl-clr.md)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[vector::operator= (STL/CLR)](../dotnet/vector-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[vector::operator(STL/CLR)](../dotnet/vector-operator-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[operator!= (vector) (STL/CLR)](../dotnet/operator-inequality-vector-stl-clr.md)|Belirler bir `vector` nesne diğerine eşit değil `vector` nesnesi.|  
|[operator< (vector) (STL/CLR)](../dotnet/operator-less-than-vector-stl-clr.md)|Belirler bir `vector` nesnesi, başka değerinden `vector` nesnesi.|  
|[operator<= (vector) (STL/CLR)](../dotnet/operator-less-or-equal-vector-stl-clr.md)|Belirler bir `vector` nesnesidir değerinden küçük veya eşit başka `vector` nesnesi.|  
|[operator== (vector) (STL/CLR)](../dotnet/operator-equality-vector-stl-clr.md)|Belirler bir `vector` nesnesidir diğerine eşit `vector` nesnesi.|  
|[operator> (vector) (STL/CLR)](../dotnet/operator-greater-than-vector-stl-clr.md)|Belirler bir `vector` nesnesidir diğerinden daha büyük `vector` nesnesi.|  
|[operator>= (vector) (STL/CLR)](../dotnet/operator-greater-or-equal-vector-stl-clr.md)|Belirler bir `vector` nesnesidir büyük veya ona eşit diğerine `vector` nesnesi.|  
  
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
 [vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)  
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)