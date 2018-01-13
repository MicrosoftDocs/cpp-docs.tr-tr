---
title: "pointer_traits yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- memory/std::pointer_traits::element_type
- memory/std::pointer_traits::pointer
- memory/std::pointer_traits
- memory/std::pointer_traits::difference_type
- memory/std::pointer_traits::rebind
- xmemory0/std::pointer_traits::element_type
- xmemory0/std::pointer_traits::pointer
- xmemory0/std::pointer_traits
- xmemory0/std::pointer_traits::difference_type
- xmemory0/std::pointer_traits::rebind
- memory/std::pointer_traits::pointer_to
dev_langs: C++
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b82970336c11e8060b01b9c78b48b21accdc67db
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="pointertraits-struct"></a>pointer_traits Yapısı
Şablon sınıfın bir nesnesi tarafından gereken tek bilgi sağlayan `allocator_traits` işaretçi türü ile bir ayırıcı açıklamak için `Ptr`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <class Ptr>
struct pointer_traits;
```  
  
## <a name="remarks"></a>Açıklamalar  
 PTR türündeki ham bir işaretçi olabilir `Ty *` veya aşağıdaki özelliklerle bir sınıf.  
```  
struct Ptr
   { // describes a pointer type usable by allocators
   typedef Ptr pointer;
   typedef T1 element_type; // optional
   typedef T2 difference_type; // optional
   template <class Other>
   using rebind = typename Ptr<Other, Rest...>; // optional
   static pointer pointer_to(element_type& obj);
   // optional
   };  
```
### <a name="typedefs"></a>Tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`typedef T2 difference_type`|Türü `T2` olan `Ptr::difference_type` türü varsa, aksi takdirde, `ptrdiff_t`. Varsa `Ptr` ham işaretçi türü `ptrdiff_t`.|  
|`typedef T1 element_type`|Türü `T1` olan `Ptr::element_type` türü varsa, aksi takdirde, `Ty`. Varsa `Ptr` ham işaretçi türü `Ty`.|  
|`typedef Ptr pointer`|Tür `Ptr`.|  
  
### <a name="structs"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`pointer_traits::rebind`|Temel alınan işaretçi Dönüştür girişimleri için belirtilen bir türün yazın.|  
  
### <a name="methods"></a>Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[pointer_to](#pointer_to)|Sınıfın bir nesnesi için rasgele bir başvuru dönüştürür `Ptr`.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<bellek >  
  
 **Namespace:** std  
  
##  <a name="pointer_to"></a>pointer_to  
 Döndüren statik yöntem `Ptr::pointer_to(obj)`, bu işlevin varsa. Aksi takdirde, sınıfın bir nesnesi için rasgele bir başvuru dönüştürülmesi mümkün değil `Ptr`. Varsa `Ptr` bir ham, bu yöntem işaretçidir `addressof(obj)`.  
  
```cpp  
static pointer pointer_to(element_type& obj);
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<bellek >](../standard-library/memory.md)   
 [allocator_traits Sınıfı](../standard-library/allocator-traits-class.md)

