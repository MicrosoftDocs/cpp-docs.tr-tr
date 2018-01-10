---
title: "CHeapPtrList sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs: C++
helpviewer_keywords: CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bda8c44142425e93792648cbbf07f5dd5e0bdb47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cheapptrlist-class"></a>CHeapPtrList sınıfı
Bu sınıf, yığın işaretçileri listesi oluşturulurken, kullanışlı yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `E`  
 Koleksiyona sınıfında depolanması için nesne türü.  
  
 `Allocator`  
 Bellek ayırma kullanacak şekilde sınıfı. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf bir oluşturucu sağlar ve yöntemleri türetilen [CAtlList](../../atl/reference/catllist-class.md) ve [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) yığın işaretçileri depolayan bir koleksiyon sınıfı nesnesinin oluşturulmasını yardımcı olmak için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CHeapPtrList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cheapptrlist"></a>CHeapPtrList::CHeapPtrList  
 Oluşturucu.  
  
```
CHeapPtrList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok boyutu, yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlList sınıfı](../../atl/reference/catllist-class.md)   
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits sınıfı](../../atl/reference/cheapptrelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
