---
title: deque (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::deque
dev_langs:
- C++
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9bd847b2641e6670a91d2edf1eb926aca423ad2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="deque-stlclr"></a>sıradan ayır (STL/CLR)
Şablon sınıfı rastgele erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı kullandığınız `deque` bitişik bir blok depolama gibi görünüyor, ancak hangi büyütür veya kalan öğeler kopyalamak için gerek kalmadan her iki uçta küçültür bir dizi öğelerini yönetmek için. Bunu verimli bir şekilde böylece uygulayabileceğiniz bir `double-ended queue`. (Bu nedenle ad.)  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value>  
    ref class deque  
        :   public  
        System::ICloneable,  
        System::Collections::IEnumerable,  
        System::Collections::ICollection,  
        System::Collections::Generic::IEnumerable<GValue>,  
        System::Collections::Generic::ICollection<GValue>,  
        System::Collections::Generic::IList<GValue>,  
        Microsoft::VisualC::StlClr::IDeque<GValue>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 GValue  
 Denetlenen sıradaki öğenin genel türü.  
  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[deque::const_iterator (STL/CLR)](../dotnet/deque-const-iterator-stl-clr.md)|Denetlenen dizi için bir sabit yineleyici türü.|  
|[deque::const_reference (STL/CLR)](../dotnet/deque-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[deque::const_reverse_iterator (STL/CLR)](../dotnet/deque-const-reverse-iterator-stl-clr.md)|Denetimli sırası için sabit bir ters yineleyici türü.|  
|[deque::difference_type (STL/CLR)](../dotnet/deque-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[deque::generic_container (STL/CLR)](../dotnet/deque-generic-container-stl-clr.md)|Genel arabirim kapsayıcının türü.|  
|[deque::generic_iterator (STL/CLR)](../dotnet/deque-generic-iterator-stl-clr.md)|Yineleyici kapsayıcısı için genel arabirimi türü.|  
|[deque::generic_reverse_iterator (STL/CLR)](../dotnet/deque-generic-reverse-iterator-stl-clr.md)|Kapsayıcı için genel arabirimini ters yineleyici türü.|  
|[deque::generic_value (STL/CLR)](../dotnet/deque-generic-value-stl-clr.md)|Kapsayıcı için genel arabirimini öğenin türü.|  
|[deque::iterator (STL/CLR)](../dotnet/deque-iterator-stl-clr.md)|Denetlenen dizi için bir yineleyici türü.|  
|[deque::reference (STL/CLR)](../dotnet/deque-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[deque::reverse_iterator (STL/CLR)](../dotnet/deque-reverse-iterator-stl-clr.md)|Denetimli sırası için ters yineleyici türü.|  
|[deque::size_type (STL/CLR)](../dotnet/deque-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[deque::value_type (STL/CLR)](../dotnet/deque-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[deque::assign (STL/CLR)](../dotnet/deque-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[deque::at (STL/CLR)](../dotnet/deque-at-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[deque::back (STL/CLR)](../dotnet/deque-back-stl-clr.md)|Son öğe erişir.|  
|[deque::begin (STL/CLR)](../dotnet/deque-begin-stl-clr.md)|Denetlenen dizinin başlangıcını belirtir.|  
|[deque::clear (STL/CLR)](../dotnet/deque-clear-stl-clr.md)|Tüm öğeleri kaldırır.|  
|[deque::deque (STL/CLR)](../dotnet/deque-deque-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[deque::empty (STL/CLR)](../dotnet/deque-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[deque::end (STL/CLR)](../dotnet/deque-end-stl-clr.md)|Denetlenen dizinin bitişini belirtir.|  
|[deque::erase (STL/CLR)](../dotnet/deque-erase-stl-clr.md)|Belirtilen konumlardaki öğeleri kaldırır.|  
|[deque::front (STL/CLR)](../dotnet/deque-front-stl-clr.md)|İlk öğe erişir.|  
|[deque::insert (STL/CLR)](../dotnet/deque-insert-stl-clr.md)|Öğeleri belirtilen bir konumda ekler.|  
|[deque::pop_back (STL/CLR)](../dotnet/deque-pop-back-stl-clr.md)|Son öğeyi kaldırır.|  
|[deque::pop_front (STL/CLR)](../dotnet/deque-pop-front-stl-clr.md)|İlk öğeyi kaldırır.|  
|[deque::push_back (STL/CLR)](../dotnet/deque-push-back-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[deque::push_front (STL/CLR)](../dotnet/deque-push-front-stl-clr.md)|Yeni bir ilk öğesi ekler.|  
|[deque::rbegin (STL/CLR)](../dotnet/deque-rbegin-stl-clr.md)|Ters denetimli dizisi başlangıcını belirtir.|  
|[deque::rend (STL/CLR)](../dotnet/deque-rend-stl-clr.md)|Ters denetimli dizinin sonuna belirler.|  
|[deque::resize (STL/CLR)](../dotnet/deque-resize-stl-clr.md)|Öğe sayısını değiştirir.|  
|[deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md)|Öğe sayısını sayar.|  
|[deque::swap (STL/CLR)](../dotnet/deque-swap-stl-clr.md)|İki kapsayıcının içeriğinin yerini değiştirir.|  
|[deque::to_array (STL/CLR)](../dotnet/deque-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[deque::back_item (STL/CLR)](../dotnet/deque-back-item-stl-clr.md)|Son öğe erişir.|  
|[deque::front_item (STL/CLR)](../dotnet/deque-front-item-stl-clr.md)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[deque::operator!= (STL/CLR)](../dotnet/deque-operator-inequality-stl-clr.md)|İki belirler `deque` nesneler eşit değildir.|  
|[deque::operator(STL/CLR)](../dotnet/deque-operator-stl-clr.md)|Belirtilen konumda bir öğe erişir.|  
|[operator< (deque) (STL/CLR)](../dotnet/operator-less-than-deque-stl-clr.md)|Belirler bir `deque` nesnesi, başka değerinden `deque` nesnesi.|  
|[operator<= (deque) (STL/CLR)](../dotnet/operator-less-or-equal-deque-stl-clr.md)|Belirler bir `deque` nesnesidir değerinden küçük veya eşit başka `deque` nesnesi.|  
|[operator= (deque) (STL/CLR)](../dotnet/operator-assign-deque-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator== (deque) (STL/CLR)](../dotnet/operator-equality-deque-stl-clr.md)|Belirler bir `deque` nesnesidir diğerine eşit `deque` nesnesi.|  
|[operator> (deque) (STL/CLR)](../dotnet/operator-greater-than-deque-stl-clr.md)|Belirler bir `deque` nesnesidir diğerinden daha büyük `deque` nesnesi.|  
|[operator>= (deque) (STL/CLR)](../dotnet/operator-greater-or-equal-deque-stl-clr.md)|Belirler bir `deque` nesnesidir büyük veya ona eşit diğerine `deque` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|<xref:System.Collections.IEnumerable>|Öğeleri dizisi.|  
|<xref:System.Collections.ICollection>|Öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IEnumerable%601>|Yazılan öğeleri dizisi.|  
|<xref:System.Collections.Generic.ICollection%601>|Yazılı öğeleri grubunu koruyun.|  
|<xref:System.Collections.Generic.IList%601>|Yazılı öğeleri sıralı grubunu koruyun.|  
|IDeque < değeri\>|Genel kapsayıcı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve saklı dizisi bloklarını tanımladığınız tanıtıcıları denetlediği dizisi için depolama boşaltır `Value` öğeleri. Dizi isteğe bağlı olarak artar. Büyüme eklenmesini ya da yeni bir öğe ekleme maliyetini sabit zamanıdır ve kalan öğe dağıtılmış bir şekilde gerçekleşir. Her iki ucunda bir öğe Ayrıca, sabit zaman ve rahatsız edici kalan öğeleri olmadan da kaldırabilirsiniz. Bu nedenle, bir deque Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğunu [sıra (STL/CLR)](../dotnet/queue-stl-clr.md) veya Şablon sınıfı [yığın (STL/CLR)](../dotnet/stack-stl-clr.md).  
  
 A `deque` nesnesi ilk (ön) öğesi için sıfırdan sayım doğrudan sayısal konumuna verilen bir öğesine başvurabilir başka bir deyişle, rastgele erişim yineleyiciler destekler [deque::size (STL/CLR)](../dotnet/deque-size-stl-clr.md) `() - 1` için son (arka) öğesi. Ayrıca bir deque Şablon sınıfı için temel alınan kapsayıcısı için iyi bir aday olduğu anlamına gelir [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md).  
  
 Deque yineleyici onu atayan öğesi sapması yanı sıra, ilişkili deque nesnesi için bir tanıtıcı depolar. Yalnızca ilişkili kapsayıcı nesneleri ile yineleyiciler kullanabilirsiniz. Deque öğesinin sapması ise `not` mutlaka aynı konumu. Eklenen ilk öğe sapması sıfır, sapması 1 sonraki eklenmiş öğeye sahip, ancak sonraki prepended öğesi sapması -1 içeriyor.  
  
 Ekleme veya her iki uçta öğeleri silme `not` geçerli tüm sapması depolanan bir öğenin değerini alter. Ekleme veya bir iç öğesi, ancak silmeyi `can` yineleyici tarafından atanan değer de değiştirebilmeniz için belirli bir sapması depolanan öğesi değeri değiştirin. (Kapsayıcı delik INSERT önce oluşturmak veya bir silme sonra delik doldurmak için aşağı veya yukarı öğeleri kopyalamak gerekebilir.) Bununla birlikte, geçerli bir öğesi kendi sapmaya atayan sürece deque yineleyici geçerli kalır. Ayrıca, geçerli bir yineleyici dereferencable kalır--erişmek veya kendi sapmaya tarafından döndürülen yineleyici sapması eşit değil sürece bunu atayan--öğe değerini değiştirmek için kullanmak `end()`.  
  
 Silme veya bir öğe kaldırıldığında yıkıcı depolanan değeri için çağırır. Kapsayıcı yok etme tüm öğeleri siler. Bu nedenle, hiçbir öğe kapsayıcı outlive ref sınıfı öğe türü olan bir kapsayıcı sağlar. Ancak, bir kapsayıcı, tanıtıcısı algılamadığı unutmayın `not` öğeleri yok.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/deque >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)