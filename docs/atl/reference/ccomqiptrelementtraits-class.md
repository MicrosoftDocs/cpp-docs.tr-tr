---
title: CComQIPtrElementTraits sınıfı | Microsoft Docs
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
ms.openlocfilehash: 9122431d0d71d33406250a624048dbede46fd387
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomqiptrelementtraits-class"></a>CComQIPtrElementTraits sınıfı
Bu sınıf, COM arabirim işaretçileri koleksiyonları oluştururken yöntemleri, statik işlevler ve tür tanımları yararlı sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename I, const IID* piid=& __uuidof(I)>  
class CComQIPtrElementTraits : 
   public CDefaultElementTraits<ATL::CComQIPtr<I, piid>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `I`  
 Depolanacak işaretçi türünü belirleyen bir COM arabirimi.  
  
 `piid`  
 Bir işaretçi IID `I`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComQIPtrElementTraits::INARGTYPE](#inargtype)|Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf yöntemlerini türetilen ve yararlı bir typedef koleksiyonu sınıfının oluştururken sağlar [CComQIPtr](../../atl/reference/ccomqiptr-class.md) COM arabirimi işaretçisi nesneleri. Bu sınıf tarafından her ikisi de kullanılan [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) ve [CInterfaceList](../../atl/reference/cinterfacelist-class.md) sınıfları.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CDefaultCompareTraits](../../atl/reference/cdefaultcomparetraits-class.md)  
  
 [CDefaultHashTraits](../../atl/reference/cdefaulthashtraits-class.md)  
  
 [CElementTraitsBase](../../atl/reference/celementtraitsbase-class.md)  
  
 [CDefaultElementTraits](../../atl/reference/cdefaultelementtraits-class.md)  
  
 `CComQIPtrElementTraits`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="inargtype"></a>  CComQIPtrElementTraits::INARGTYPE  
 Koleksiyon sınıfı nesnesine öğe eklemek için kullanılacak veri türü.  
  
```
typedef I* INARGTYPE;
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDefaultElementTraits sınıfı](../../atl/reference/cdefaultelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
