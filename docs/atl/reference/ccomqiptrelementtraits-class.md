---
title: Ccomqıptrelementtraits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits
- ATLCOLL/ATL::CComQIPtrElementTraits::INARGTYPE
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtrElementTraits class
ms.assetid: 9df9250a-5413-4362-b133-332932a597c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e99299d1232fda75d6b0552b5236a060903a08e5
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879658"
---
# <a name="ccomqiptrelementtraits-class"></a>Ccomqıptrelementtraits sınıfı
Bu sınıf, yöntem, statik işlevler ve tür tanımları yararlı COM arabirim işaretçilerini koleksiyonları oluştururken sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>Parametreler  
 *I*  
 Depolanacak işaretçi türü belirten bir COM arabirimi.  
  
 *piid*  
 Laboratuvardaki işaretçisi *miyim*.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel Typedefler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf yöntemleri türetilir ve bir koleksiyon sınıfının oluştururken kullanışlı bir typedef sağlar [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirimi işaretçisini nesneleri. Bu sınıf tarafından kullanılan [Cınterfacearray](../../atl/reference/cinterfacearray-class.md) ve [Cınterfacelist](../../atl/reference/cinterfacelist-class.md) sınıfları.  
  
 Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğeler eklemek için kullanılacak veri türü.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
