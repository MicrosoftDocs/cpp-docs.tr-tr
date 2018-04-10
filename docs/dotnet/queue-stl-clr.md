---
title: sıra (STL/CLR) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- cliext::queue
dev_langs:
- C++
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d5b91a2556a93f3cd74a24ea57306d70f2cbdb41
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="queue-stlclr"></a>sıraya al (STL/CLR)
Şablon sınıfı ilk giren ilk çıkar özelliğine sahip erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı bağdaştırıcısı kullandığınız `queue` temel alınan bir kapsayıcı bir sıra olarak yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`. Benzer şekilde, `GContainer` aynı `Container` ikinci ref türü olmadıkça olmasından; bu durumda `Container^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value,  
    typename Container>  
    ref class queue  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>  
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
|[queue::const_reference (STL/CLR)](../dotnet/queue-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[queue::container_type (STL/CLR)](../dotnet/queue-container-type-stl-clr.md)|Temel alınan kapsayıcı türü.|  
|[queue::difference_type (STL/CLR)](../dotnet/queue-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[queue::generic_container (STL/CLR)](../dotnet/queue-generic-container-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|  
|[queue::generic_value (STL/CLR)](../dotnet/queue-generic-value-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirimini öğenin türü.|  
|[queue::reference (STL/CLR)](../dotnet/queue-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[queue::size_type (STL/CLR)](../dotnet/queue-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[queue::value_type (STL/CLR)](../dotnet/queue-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[queue::assign (STL/CLR)](../dotnet/queue-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[queue::back (STL/CLR)](../dotnet/queue-back-stl-clr.md)|Son öğe erişir.|  
|[queue::empty (STL/CLR)](../dotnet/queue-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[queue::front (STL/CLR)](../dotnet/queue-front-stl-clr.md)|İlk öğe erişir.|  
|[queue::get_container (STL/CLR)](../dotnet/queue-get-container-stl-clr.md)|Temel alınan kapsayıcı erişir.|  
|[queue::pop (STL/CLR)](../dotnet/queue-pop-stl-clr.md)|İlk öğeyi kaldırır.|  
|[queue::push (STL/CLR)](../dotnet/queue-push-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[queue::queue (STL/CLR)](../dotnet/queue-queue-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[queue::size (STL/CLR)](../dotnet/queue-size-stl-clr.md)|Öğe sayısını sayar.|  
|[queue::to_array (STL/CLR)](../dotnet/queue-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[queue::back_item (STL/CLR)](../dotnet/queue-back-item-stl-clr.md)|Son öğe erişir.|  
|[queue::front_item (STL/CLR)](../dotnet/queue-front-item-stl-clr.md)|İlk öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[queue::operator= (STL/CLR)](../dotnet/queue-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator!= (queue) (STL/CLR)](../dotnet/operator-inequality-queue-stl-clr.md)|Belirler bir `queue` nesne diğerine eşit değil `queue` nesnesi.|  
|[operator< (queue) (STL/CLR)](../dotnet/operator-less-than-queue-stl-clr.md)|Belirler bir `queue` nesnesi, başka değerinden `queue` nesnesi.|  
|[operator<= (queue) (STL/CLR)](../dotnet/operator-less-or-equal-queue-stl-clr.md)|Belirler bir `queue` nesnesidir değerinden küçük veya eşit başka `queue` nesnesi.|  
|[operator== (queue) (STL/CLR)](../dotnet/operator-equality-queue-stl-clr.md)|Belirler bir `queue` nesnesidir diğerine eşit `queue` nesnesi.|  
|[operator> (queue) (STL/CLR)](../dotnet/operator-greater-than-queue-stl-clr.md)|Belirler bir `queue` nesnesidir diğerinden daha büyük `queue` nesnesi.|  
|[operator>= (queue) (STL/CLR)](../dotnet/operator-greater-or-equal-queue-stl-clr.md)|Belirler bir `queue` nesnesidir büyük veya ona eşit diğerine `queue` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|IQueue\<değeri, kapsayıcı >|Genel kapsayıcı bağdaştırıcısı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve türündeki temel alınan bir kapsayıcı denetlediği dizisi için depolama boşaltır `Container`, depolar `Value` öğeleri ve isteğe bağlı olarak artar. Yalnızca ilk öğe gönderilmesi için nesne erişimi kısıtlayan ve son öğe pencerelerinin, ilk giren ilk çıkar uygulama sıraya (FIFO sıra veya yalnızca bir sıra olarak da bilinir).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/kuyruk >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [Yığın (STL/CLR)](../dotnet/stack-stl-clr.md)   
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)