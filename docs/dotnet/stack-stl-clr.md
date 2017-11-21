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
ms.openlocfilehash: dad00eecc05b8b3020dcf024b297b4b090317ee4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[Stack::const_reference (STL/CLR)](../dotnet/stack-const-reference-stl-clr.md)|Bir öğe için sabit bir başvuru türü.|  
|[Stack::container_type (STL/CLR)](../dotnet/stack-container-type-stl-clr.md)|Temel alınan kapsayıcı türü.|  
|[Stack::difference_type (STL/CLR)](../dotnet/stack-difference-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[Stack::generic_container (STL/CLR)](../dotnet/stack-generic-container-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirim türü.|  
|[Stack::generic_value (STL/CLR)](../dotnet/stack-generic-value-stl-clr.md)|Kapsayıcı bağdaştırıcısı için genel arabirimini öğenin türü.|  
|[Stack::Reference (STL/CLR)](../dotnet/stack-reference-stl-clr.md)|Bir öğe için bir başvuru türü.|  
|[Stack::size_type (STL/CLR)](../dotnet/stack-size-type-stl-clr.md)|İki öğe arasındaki işaretli mesafenin türü.|  
|[Stack::value_type (STL/CLR)](../dotnet/stack-value-type-stl-clr.md)|Öğenin türü.|  
  
|Üye İşlevi|Açıklama|  
|---------------------|-----------------|  
|[Stack::Assign (STL/CLR)](../dotnet/stack-assign-stl-clr.md)|Tüm öğeleri değiştirir.|  
|[Stack::Empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)|Bir öğe olup olmadığını sınar.|  
|[Stack::get_container (STL/CLR)](../dotnet/stack-get-container-stl-clr.md)|Temel alınan kapsayıcı erişir.|  
|[Stack::POP (STL/CLR)](../dotnet/stack-pop-stl-clr.md)|Son öğeyi kaldırır.|  
|[Stack::push (STL/CLR)](../dotnet/stack-push-stl-clr.md)|Yeni bir son öğesi ekler.|  
|[Stack::size (STL/CLR)](../dotnet/stack-size-stl-clr.md)|Öğe sayısını sayar.|  
|[Stack::Stack (STL/CLR)](../dotnet/stack-stack-stl-clr.md)|Bir kapsayıcı nesnesi oluşturur.|  
|[Stack::Top (STL/CLR)](../dotnet/stack-top-stl-clr.md)|Son öğe erişir.|  
|[Stack::to_array (STL/CLR)](../dotnet/stack-to-array-stl-clr.md)|Denetimli sırası yeni bir diziye kopyalar.|  
  
|Özellik|Açıklama|  
|--------------|-----------------|  
|[Stack::top_item (STL/CLR)](../dotnet/stack-top-item-stl-clr.md)|Son öğe erişir.|  
  
|İşleç|Açıklama|  
|--------------|-----------------|  
|[Stack::operator (STL/CLR) =](../dotnet/stack-operator-assign-stl-clr.md)|Denetimli dizisi yerini alır.|  
|[operator! = (yığın) (STL/CLR)](../dotnet/operator-inequality-stack-stl-clr.md)|Belirler bir `stack` nesne diğerine eşit değil `stack` nesnesi.|  
|[operator < (yığın) (STL/CLR)](../dotnet/operator-less-than-stack-stl-clr.md)|Belirler bir `stack` nesnesi, başka değerinden `stack` nesnesi.|  
|[operator < = (yığın) (STL/CLR)](../dotnet/operator-less-or-equal-stack-stl-clr.md)|Belirler bir `stack` nesnesidir değerinden küçük veya eşit başka `stack` nesnesi.|  
|[operator == (yığın) (STL/CLR)](../dotnet/operator-equality-stack-stl-clr.md)|Belirler bir `stack` nesnesidir diğerine eşit `stack` nesnesi.|  
|[operator > (yığın) (STL/CLR)](../dotnet/operator-greater-than-stack-stl-clr.md)|Belirler bir `stack` nesnesidir diğerinden daha büyük `stack` nesnesi.|  
|[operator > = (yığın) (STL/CLR)](../dotnet/operator-greater-or-equal-stack-stl-clr.md)|Belirler bir `stack` nesnesidir büyük veya ona eşit diğerine `stack` nesnesi.|  
  
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