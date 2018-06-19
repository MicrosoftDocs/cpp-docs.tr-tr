---
title: CHeapPtrList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList
- ATLCOLL/ATL::CHeapPtrList::CHeapPtrList
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrList class
ms.assetid: cc70e585-362a-4007-81db-c705eb181226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dc5b164fda27775a7b3fb272d8718c31815cb1ca
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358821"
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
  
##  <a name="cheapptrlist"></a>  CHeapPtrList::CHeapPtrList  
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
