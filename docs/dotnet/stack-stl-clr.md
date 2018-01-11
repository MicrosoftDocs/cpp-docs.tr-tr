---
title: "Yığın (STL/CLR) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: cliext::stack
dev_langs: C++
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c7f6d9eac97fa1907a0901c725645f29dcdd5d9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stack-stlclr"></a>yığın (STL/CLR)
Şablon sınıfı son giren ilk çıkar özelliğine sahip erişimi olan öğeleri değişen uzunluk dizisi denetleyen bir nesne tanımlar. Kapsayıcı bağdaştırıcısı kullandığınız `stack` temel alınan bir kapsayıcı itme aşağı yığın olarak yönetmek için.  
  
 Aşağıda, açıklamada `GValue` aynı `Value` ikinci ref türü olmadıkça olmasından; bu durumda `Value^`. Benzer şekilde, `GContainer` aynı `Container` ikinci ref türü olmadıkça olmasından; bu durumda `Container^`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<typename Value,  
    typename Container>  
    ref class stack  
        :   public  
        System::ICloneable,  
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>  
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
|[stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|Temel alınan kapsayıcı türü.|  
|[stack::difference_type (STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|  
|[stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirimini öğenin türü.|  
|[stack::reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[stack::size_type (STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[stack::assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[stack::empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[stack::get_container (STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|Temel alınan kapsayıcı erişir.|  
|[stack::pop (STL/CLR)](../dotnet/stack-pop-stl-clr.md)|Son öğeyi kaldırır.|  
|[stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)|Öğe sayısını sayar.|  
|[stack::stack (STL/CLR)](../dotnet/stack-stack-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[stack::top (STL/CLR)](../dotnet/stack-top-stl-clr.md)|Son öğe erişir.|  
|[stack::to_array (STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[stack::top_item (STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|Son öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[stack::operator= (STL/CLR)](../dotnet/stack-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator!= (stack) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|Belirler bir `stack` nesne diğerine eşit değil `stack` nesnesi.|  
|[operator< (stack) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|Belirler bir `stack` nesnesi, başka değerinden `stack` nesnesi.|  
|[operator<= (stack) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Belirler bir `stack` nesnesidir değerinden küçük veya eşit başka `stack` nesnesi.|  
|[operator== (stack) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|Belirler bir `stack` nesnesidir diğerine eşit `stack` nesnesi.|  
|[operator> (stack) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|Belirler bir `stack` nesnesidir diğerinden daha büyük `stack` nesnesi.|  
|[operator>= (stack) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Belirler bir `stack` nesnesidir büyük veya ona eşit diğerine `stack` nesnesi.|  
  
## <a name="interfaces"></a>Arabirimler  
  
|Arabirim|Açıklama|  
|---------------|-----------------|  
|<xref:System.ICloneable>|Yinelenen bir nesne.|  
|IStack\<değeri, kapsayıcı >|Genel kapsayıcı bağdaştırıcısı korur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Nesne ayırır ve türündeki temel alınan bir kapsayıcı denetlediği dizisi için depolama boşaltır `Container`, depolar `Value` öğeleri ve isteğe bağlı olarak artar. Nesne, iletme ve son giren ilk çıkar özelliğine sahip sıra (olarak da bilinen bir LIFO sıra veya yığın) uygulama yalnızca son öğe pencerelerinin erişimi sınırlandırır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<cliext/stack >  
  
 **Namespace:** cliext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [deque (STL/CLR)](../dotnet/deque-stl-clr.md)   
 [Liste (STL/CLR)](../dotnet/list-stl-clr.md)   
 [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)   
 [sıra (STL/CLR)](../dotnet/queue-stl-clr.md)   
 [vektör (STL/CLR)](../dotnet/vector-stl-clr.md)   
 [STL/CLR Kitaplık Başvurusu](../dotnet/stl-clr-library-reference.md)