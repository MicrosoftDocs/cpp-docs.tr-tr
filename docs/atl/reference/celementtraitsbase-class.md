---
title: "CElementTraitsBase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase
- ATLCOLL/ATL::CElementTraitsBase::INARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::OUTARGTYPE
- ATLCOLL/ATL::CElementTraitsBase::CopyElements
- ATLCOLL/ATL::CElementTraitsBase::RelocateElements
dev_langs: C++
helpviewer_keywords: CElementTraitsBase class
ms.assetid: 75284caf-347e-4355-a7d8-efc708dd514a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0201ecd971b13b69e210b356ba9192bfdc89a54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="celementtraitsbase-class"></a>CElementTraitsBase sınıfı
Bu sınıf, varsayılan copy sağlar ve koleksiyon sınıfı yöntemleri taşıyın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>  
class CElementTraitsBase
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Bir koleksiyonda depolanan verilerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CElementTraitsBase::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
|[CElementTraitsBase::OUTARGTYPE](#outargtype)|Koleksiyon sınıfı nesnesinden öğeleri almak için kullanılacak veri türü.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CElementTraitsBase::CopyElements](#copyelements)|Bir koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.|  
|[CElementTraitsBase::RelocateElements](#relocateelements)|Bir koleksiyon sınıfı nesnesinde depolanan öğeler konumunu değiştirmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 Taban sınıfı kopyalama ve koleksiyon sınıfı öğelerini yeniden konumlandırma için yöntemleri tanımlar. Sınıfları tarafından kullanılan [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md), [CStringRefElementTraits](../../atl/reference/cstringrefelementtraits-class.md), ve [CStringElementTraitsI](../../atl/reference/cstringelementtraitsi-class.md).  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="copyelements"></a>CElementTraitsBase::CopyElements  
 Bir koleksiyon sınıfı nesnesinde depolanan öğeleri kopyalamak için bu yöntemi çağırın.  
  
```
static void CopyElements(
    T* pDest,
    const T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDest`  
 Kopyalanan veriler alacak ilk öğe işaretçi.  
  
 `pSrc`  
 Kopyalamak için ilk öğe işaretçi.  
  
 `nElements`  
 Kopyalanacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak ve hedef öğeleri çakışmaması gerekir.  
  
##  <a name="inargtype"></a>CElementTraitsBase::INARGTYPE  
 Koleksiyona öğe eklemek için kullanılacak veri türü.  
  
```
typedef const T& INARGTYPE;
```  
  
##  <a name="outargtype"></a>CElementTraitsBase::OUTARGTYPE  
 Koleksiyondan öğeleri almak için kullanılacak veri türü.  
  
```
typedef T& OUTARGTYPE;
```  
  
##  <a name="relocateelements"></a>CElementTraitsBase::RelocateElements  
 Bir koleksiyon sınıfı nesnesinde depolanan öğeler konumunu değiştirmek için bu yöntemi çağırın.  
  
```
static void RelocateElements(
    T* pDest,
    T* pSrc,
    size_t nElements);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDest`  
 Yeniden konumlandırılan veri alacak ilk öğe işaretçi.  
  
 `pSrc`  
 İşaretçi ilk öğesine taşıyabilir.  
  
 `nElements`  
 Taşıyabilir öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [memmove](../../c-runtime-library/reference/memmove-wmemmove.md), çoğu veri türleri için yeterli olduğu. Taşınan nesne kendi üye işaretçileri içeriyorsa, bu yöntem geçersiz kılınabilir gerekecektir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
