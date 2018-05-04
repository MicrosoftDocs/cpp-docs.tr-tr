---
title: CInterfaceList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CInterfaceList
- ATLCOLL/ATL::CInterfaceList
- ATLCOLL/ATL::CInterfaceList::CInterfaceList
dev_langs:
- C++
helpviewer_keywords:
- CInterfaceList class
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1fc523b1eccc88678cda48a0c7e429ea0fc09f9b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="cinterfacelist-class"></a>CInterfaceList sınıfı
Bu sınıf, COM arabirim işaretçileri listesi oluşturulurken, kullanışlı yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Parametreler  
 `I`  
 Depolanacak işaretçi türünü belirleyen bir COM arabirimi.  
  
 `piid`  
 Bir işaretçi IID `I`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Arabirim listesi Oluşturucusu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir oluşturucu ve COM arabirim işaretçileri listesini oluşturmak için türetilen yöntemler sağlar. Kullanım [CInterfaceArray](../../atl/reference/cinterfacearray-class.md) bir dizi zaman gereklidir.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList  
 Arabirim listesi Oluşturucusu.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Varsayılan değer 10 blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok boyutu, yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlList sınıfı](../../atl/reference/catllist-class.md)   
 [CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
