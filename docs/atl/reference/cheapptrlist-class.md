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
ms.openlocfilehash: cd3342e7c64a13761830073cd3ed82b627b8c407
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879302"
---
# <a name="cheapptrlist-class"></a>CHeapPtrList sınıfı
Bu sınıf, yığın işaretçileri listesini oluştururken kullanışlı yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename E, class Allocator = ATL::CCRTAllocator>  
class CHeapPtrList 
   : public CAtlList<ATL::CHeapPtr<E, Allocator>,
                     CHeapPtrElementTraits<E, Allocator>>
```  
  
#### <a name="parameters"></a>Parametreler  
 *E*  
 Koleksiyon sınıfı içinde depolanan nesne türü.  
  
 *Ayırıcı*  
 Bellek ayırma kullanmak için sınıf. Varsayılan değer [CCRTAllocator](../../atl/reference/ccrtallocator-class.md).  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CHeapPtrList::CHeapPtrList](#cheapptrlist)|Oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir oluşturucu sağlar ve türeyen yöntemlerinden [CAtlList](../../atl/reference/catllist-class.md) ve [CHeapPtrElementTraits](../../atl/reference/cheapptrelementtraits-class.md) yığın işaretçileri depolama koleksiyon sınıf nesnesi oluşturmaya yardımcı olmak için.  
  
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
 *nBlockSize*  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlList sınıfı](../../atl/reference/catllist-class.md)   
 [CHeapPtr sınıfı](../../atl/reference/cheapptr-class.md)   
 [CHeapPtrElementTraits sınıfı](../../atl/reference/cheapptrelementtraits-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
