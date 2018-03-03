---
title: priority_queue (STL/CLR) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- cliext::priority_queue
dev_langs:
- C++
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: b7d1459da07f7e392a2da1fbf5d6e9d72c8f4653
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="priorityqueue-stlclr"></a>priority_queue (STL/CLR)
Şablon sınıfı bir değişen Sınırlı erişime öğe dizisi sıralı uzunlukta denetleyen bir nesne tanımlar. Kapsayıcı bağdaştırıcısı kullandığınız `priority_queue` temel alınan bir kapsayıcı bir öncelik sırası olarak yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`. Benzer şekilde, `GContainer` aynı `Container` ikinci ref türü olmadıkça olmasından; bu durumda `Container^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value,  
    typename Container>  
    ref class priority_queue  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>  
    { ..... };  
```  
  
#### <a name="parameters"></a>Parametreler  
 Değer  
 Denetlenen sıradaki öğenin türü.  
  
 Kapsayıcı  
 Temel alınan kapsayıcı türü.  
  
## <a name="members"></a>Üyeler  
  
|Tür Tanımlaması|Açıklama|  
|---------------------|-----------------|  
|[priority_queue::const_reference (STL/CLR)](../dotnet/priority-queue-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[priority_queue::container_type (STL/CLR)](../dotnet/priority-queue-container-type-stl-clr.md)|Temel alınan kapsayıcı türü.|  
|[priority_queue::difference_type (STL/CLR)](../dotnet/priority-queue-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[priority_queue::generic_container (STL/CLR)](../dotnet/priority-queue-generic-container-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|  
|[priority_queue::generic_value (STL/CLR)](../dotnet/priority-queue-generic-value-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirimini öğenin türü.|  
|[priority_queue::reference (STL/CLR)](../dotnet/priority-queue-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[priority_queue::size_type (STL/CLR)](../dotnet/priority-queue-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)|İki öğe için sıralama temsilcisi.|  
|[priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[priority_queue::assign (STL/CLR)](../dotnet/priority-queue-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[priority_queue::empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[priority_queue::get_container (STL/CLR)](../dotnet/priority-queue-get-container-stl-clr.md)|Temel alınan kapsayıcı erişir.|  
|[priority_queue::pop (STL/CLR)](../dotnet/priority-queue-pop-stl-clr.md)|Hghest öncelikli öğeyi kaldırır.|  
|[priority_queue::priority_queue (STL/CLR)](../dotnet/priority-queue-priority-queue-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[priority_queue::push (STL/CLR)](../dotnet/priority-queue-push-stl-clr.md)|Yeni bir öğe ekler.|  
|[priority_queue::size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)|Öğe sayısını sayar.|  
|[priority_queue::top (STL/CLR)](../dotnet/priority-queue-top-stl-clr.md)|En yüksek öncelikli öğenin erişir.|  
|[priority_queue::to_array (STL/CLR)](../dotnet/priority-queue-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
|[priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)|İki öğe için sıralama temsilci kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[priority_queue::top_item (STL/CLR)](../dotnet/priority-queue-top-item-stl-clr.md)|En yüksek öncelikli öğenin erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[priority_queue::operator= (STL/CLR)](../dotnet/priority-queue-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|IPriorityQueue\<değeri, kapsayıcı >|Genel kapsayıcı bağdaştırıcısı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve türündeki temel alınan bir kapsayıcı denetlediği dizisi için depolama boşaltır `Container`, depolar `Value` öğeleri ve isteğe bağlı olarak artar. En yüksek öncelikli öğesiyle (üst öğe) kolayca erişilebilir ve taşınabilir bir yığın olarak sıralı dizisi tutar. Nesne, yeni öğeler dağıtmaya ve yalnızca en yüksek öncelikli öğesi, bir öncelik sırası uygulama pencerelerinin erişimi sınırlandırır.  
  
 Nesne denetleyen bir saklı temsilci nesne türü çağırarak dizisi siparişleri [priority_queue::value_compare (STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md). Priority_queue yapısı oluştururken saklı temsilci nesnesini belirtebilirsiniz; hiçbir temsilci nesnesi belirtirseniz, karşılaştırma varsayılandır `operator<(value_type, value_type)`. Üye işlevini çağırarak saklı bu nesneye erişim [priority_queue::value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)`()`.  
  
 Böyle bir temsilci nesnenin katı bir zayıf türü değerlerine sıralama zorunlu tuttukları gerekir [priority_queue::value_type (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md). Yani, herhangi iki tuşları `X` ve `Y`:  
  
 `value_comp()(X, Y)`Her çağrıda aynı Boolean sonucu döndürür.  
  
 Varsa `value_comp()(X, Y)` true ise `value_comp()(Y, X)` false olmalıdır.  
  
 Varsa `value_comp()(X, Y)` true ise `X` önce sıralanmalıdır söylenir `Y`.  
  
 Varsa `!value_comp()(X, Y) && !value_comp()(Y, X)` true ise `X` ve `Y` eşdeğer sıralama sahip söylenir.  
  
 Herhangi bir öğe için `X` , önündeki `Y` denetlenen sıradaki `key_comp()(Y, X)` false olur. (Varsayılan temsilci nesnesi için anahtarları hiçbir zaman değerini azaltın.)  
  
 En yüksek öncelik bu nedenle, önce başka bir öğenin sıralı olmayan öğelerden birini öğedir.  
  
 Temel alınan kapsayıcı bir yığın sıralı öğeleri tutar bu yana:  
  
 Kapsayıcı rasgele erişim yineleyiciler desteklemesi gerekir.  
  
 Gönderilen daha eşdeğer sıralama ile öğeleri farklı bir sırada Sil'i. (Sıralama tutarlı değil.)  
  
 Bu nedenle, temel alınan kapsayıcısı için aday dahil [deque (STL/CLR)](../dotnet/deque-stl-clr.md) ve [vektör (STL/CLR)](../dotnet/vector-stl-clr.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)