---
title: Cınterfacelist sınıfı | Microsoft Docs
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
ms.openlocfilehash: 33cfcc072e000bc903cceb4ac5551071e35610d9
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884382"
---
# <a name="cinterfacelist-class"></a>Cınterfacelist sınıfı
Bu sınıf, COM arabirim işaretçilerini listesini oluştururken kullanışlı yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class I, const IID* piid =& __uuidof(I)>  
class CInterfaceList 
   : public CAtlList<ATL::CComQIPtr<I, piid>,
                     CComQIPtrElementTraits<I, piid>>
```  
  
#### <a name="parameters"></a>Parametreler  
 *I*  
 Depolanacak işaretçi türü belirten bir COM arabirimi.  
  
 *piid*  
 Laboratuvardaki işaretçisi *miyim*.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](#cinterfacelist)|Arabirim listesi için oluşturucu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir oluşturucu ve COM arabirim işaretçilerini listesini oluşturmak için türetilmiş yöntemleri sağlar. Kullanım [Cınterfacearray](../../atl/reference/cinterfacearray-class.md) bir dizi olduğunda gereklidir.  
  
 Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cinterfacelist"></a>  CInterfaceList::CInterfaceList  
 Arabirim listesi için oluşturucu.  
  
```
CInterfaceList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *nBlockSize*  
 Varsayılan değer 10 blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlList sınıfı](../../atl/reference/catllist-class.md)   
 [CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)   
 [Ccomqıptrelementtraits sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
