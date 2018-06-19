---
title: CHeapPtrElementTraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits
- ATLCOLL/ATL::CHeapPtrElementTraits::INARGTYPE
- ATLCOLL/ATL::CHeapPtrElementTraits::OUTARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrElementTraits class
ms.assetid: 910e0e06-3c8b-4242-bf00-b57eb74fbc77
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa4b29f5893a0b1536a087b0c516e6340eca8449
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360083"
---
# <a name="cheapptrelementtraits-class"></a>CHeapPtrElementTraits sınıfı
Bu sınıf, yığın işaretçileri koleksiyonları oluştururken yöntemleri, statik işlevler ve tür tanımları yararlı sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrElementTraits : 
   public CDefaultElementTraits<ATL::CHeapPtr<T, Allocator>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Koleksiyona sınıfında depolanması için nesne türü.  
  
 `Allocator`  
 Bellek ayırma kullanacak şekilde sınıfı. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CHeapPtrElementTraits::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, kuruluşlara yardımcı olmaktayız yığın işaretçileri içeren koleksiyon sınıfı nesneleri oluşturma yöntemleri, statik işlevler ve tür tanımları sağlar. Sınıf `CHeapPtrList` türetilen `CHeapPtrElementTraits`.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CHeapPtrElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="inargtype"></a>  CHeapPtrElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef CHeapPtr<T, Allocator>& INARGTYPE;
```  
  
##  <a name="outargtype"></a>  CHeapPtrElementTraits::OUTARGTYPE  
 Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.  
  
```
typedef T *& OUTARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [CComHeapPtr sınıfı](../../atl/reference/ccomheapptr-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
