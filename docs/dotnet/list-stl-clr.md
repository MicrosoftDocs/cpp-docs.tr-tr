---
title: Liste (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::list
dev_langs: C++
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 991b72b312c8ad1b36a9a401a6452ec36ea25d6e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="list-stlclr"></a>liste (STL/CLR)
Şablon sınıfı çift yönlü erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `list` her bir öğe depolamak sırada düğüm, çift yönlü bağlantılı listesi öğelerini yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    ref class list  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        Microsoft::VisualC::StlClr::IList<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[List::const_iterator (STL/CLR)](../dotnet/list-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[List::const_reference (STL/CLR)](../dotnet/list-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[List::const_reverse_iterator (STL/CLR)](../dotnet/list-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[List::difference_type (STL/CLR)](../dotnet/list-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[List::generic_container (STL/CLR)](../dotnet/list-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[List::generic_iterator (STL/CLR)](../dotnet/list-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[List::generic_reverse_iterator (STL/CLR)](../dotnet/list-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[List::generic_value (STL/CLR)](../dotnet/list-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[List::iterator (STL/CLR)](../dotnet/list-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[List::Reference (STL/CLR)](../dotnet/list-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[List::reverse_iterator (STL/CLR)](../dotnet/list-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[List::size_type (STL/CLR)](../dotnet/list-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[List::value_type (STL/CLR)](../dotnet/list-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[List::Assign (STL/CLR)](../dotnet/list-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[List::Back (STL/CLR)](../dotnet/list-back-stl-clr.md)|Son öğe erişir.|  
|[List::Begin (STL/CLR)](../dotnet/list-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[List::Clear (STL/CLR)](../dotnet/list-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[List::Empty (STL/CLR)](../dotnet/list-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[List::End (STL/CLR)](../dotnet/list-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[List::ERASE (STL/CLR)](../dotnet/list-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[List::Front (STL/CLR)](../dotnet/list-front-stl-clr.md)|İlk öğe erişir.|  
|[List::insert (STL/CLR)](../dotnet/list-insert-stl-clr.md)|Öğeleri belirtilen bir konumda ekler.|  
|[List::List (STL/CLR)](../dotnet/list-list-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[List::Merge (STL/CLR)](../dotnet/list-merge-stl-clr.md)|İki denetimli sıraları sıralı birleştirir.|  
|[List::pop_back (STL/CLR)](../dotnet/list-pop-back-stl-clr.md)|Son öğeyi kaldırır.|  
|[List::pop_front (STL/CLR)](../dotnet/list-pop-front-stl-clr.md)|İlk öğeyi kaldırır.|  
|[List::push_back (STL/CLR)](../dotnet/list-push-back-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[List::push_front (STL/CLR)](../dotnet/list-push-front-stl-clr.md)|Yeni bir ilk öğesi ekler.|  
|[List::rbegin (STL/CLR)](../dotnet/list-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[List::Remove (STL/CLR)](../dotnet/list-remove-stl-clr.md)|Belirli bir değerle bir öğeyi kaldırır.|  
|[List::remove_if (STL/CLR)](../dotnet/list-remove-if-stl-clr.md)|Belirtilen bir sınamadan öğeleri kaldırır.|  
|[List::rend (STL/CLR)](../dotnet/list-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[List::resize (STL/CLR)](../dotnet/list-resize-stl-clr.md)|Öğe sayısını değiştirir.|  
|[List::reverse (STL/CLR)](../dotnet/list-reverse-stl-clr.md)|Denetimli sırasını tersine çevirir.|  
|[List::size (STL/CLR)](../dotnet/list-size-stl-clr.md)|Öğe sayısını sayar.|  
|[List::sort (STL/CLR)](../dotnet/list-sort-stl-clr.md)|Denetimli dizisi sıralar.|  
|[List::splice (STL/CLR)](../dotnet/list-splice-stl-clr.md)|Düğümler arasındaki bağlantıları restitches.|  
|[List::Swap (STL/CLR)](../dotnet/list-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[List::to_array (STL/CLR)](../dotnet/list-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[List::Unique (STL/CLR)](../dotnet/list-unique-stl-clr.md)|Belirtilen bir sınamadan bitişik öğeleri kaldırır.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[List::back_item (STL/CLR)](../dotnet/list-back-item-stl-clr.md)|Son öğe erişir.|  
|[List::front_item (STL/CLR)](../dotnet/list-front-item-stl-clr.md)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[List::operator (STL/CLR) =](../dotnet/list-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator! = (listesi) (STL/CLR)](../dotnet/operator-inequality-list-stl-clr.md)|Belirler bir `list` nesne diğerine eşit değil `list` nesnesi.|  
|[operator < (liste) (STL/CLR)](../dotnet/operator-less-than-list-stl-clr.md)|Belirler bir `list` nesnesi, başka değerinden `list` nesnesi.|  
|[operator < = (listesi) (STL/CLR)](../dotnet/operator-less-or-equal-list-stl-clr.md)|Belirler bir `list` nesnesidir değerinden küçük veya eşit başka `list` nesnesi.|  
|[operator == (liste) (STL/CLR)](../dotnet/operator-equality-list-stl-clr.md)|Belirler bir `list` nesnesidir diğerine eşit `list` nesnesi.|  
|[operator > (liste) (STL/CLR)](../dotnet/operator-greater-than-list-stl-clr.md)|Belirler bir `list` nesnesidir diğerinden daha büyük `list` nesnesi.|  
|[operator > = (listesi) (STL/CLR)](../dotnet/operator-greater-or-equal-list-stl-clr.md)|Belirler bir `list` nesnesidir büyük veya ona eşit diğerine `list` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|IList\<değer >|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve çift yönlü bağlantı listesinden tek düğümler olarak denetlediği dizisi için depolama boşaltır. Bu, öğeleri hiçbir zaman kopyalayarak bir düğümün içeriğini başka düğümler arasındaki bağlantılar değiştirerek yeniden düzenler. INSERT ve rahatsız edici kalan öğeleri olmadan serbestçe öğeleri Kaldır anlamına gelir. Bu nedenle, bir şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday listesidir [sıra (STL/CLR)](../dotnet/queue-stl-clr.md) veya Şablon sınıfı [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `list` nesnesi, denetlenen sıradaki öğenin atayan yineleyici verilen bitişik öğelerine adım başka bir deyişle, çift yönlü yineleyiciler destekler. Özel bir baş düğüm tarafından döndürülen yineleyici karşılık gelen [list::end (STL/CLR)](../dotnet/list-end-stl-clr.md)`()`. Denetlenen sıradaki son öğe ulaşmak için bu yineleyici varsa azaltma. Baş düğüm ulaşmak için bir liste yineleyici artırabilirsiniz ve bu ardından eşit karşılaştırır `end()`. Ancak tarafından döndürülen yineleyici başvuramaz `end()`.  
  
 Rasgele erişim yineleyici gerektiren sayısal konumunu--doğrudan verilen bir liste öğesinin başvuramaz unutmayın. Bir liste olacak şekilde `not` Şablon sınıfı için temel alınan kapsayıcı olarak kullanılabilir [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Bir liste yineleyici sırayla ilişkilendirilmiş kapsayıcısı için bir tanıtıcı depolar onun ilişkili liste düğümü için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. İlişkili liste düğümü bazı listesiyle ilişkili olduğu sürece bir liste yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable--erişmek veya eşit değil sürece bunu atayan--öğe değeri değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/listesi >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)