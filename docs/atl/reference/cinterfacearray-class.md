---
title: "CInterfaceArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray
- ATLCOLL/ATL::CInterfaceArray::CInterfaceArray
dev_langs: C++
helpviewer_keywords: CInterfaceArray class
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a06fe0f7fab05b6b73856fa3f326f1c54d4f55c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cinterfacearray-class"></a>CInterfaceArray sınıfı
Bu sınıf, bir dizi COM arabirim işaretçileri oluşturulurken yararlı yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class I, const IID* piid=& __uuidof(I)>  
class CInterfaceArray : 
   public CAtlArray<ATL::CComQIPtr<I, piid>,
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
|[CInterfaceArray::CInterfaceArray](#cinterfacearray)|Arabirim dizi Oluşturucusu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf, bir oluşturucu ve COM arabirim işaretçileri dizisi oluşturmak için türetilen yöntemler sağlar. Kullanım [CInterfaceList](../../atl/reference/cinterfacelist-class.md) listesini zaman gereklidir.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="cinterfacearray"></a>CInterfaceArray::CInterfaceArray  
 Oluşturucu.  
  
```
CInterfaceArray() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Akıllı işaretçi dizi başlatır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlArray sınıfı](../../atl/reference/catlarray-class.md)   
 [CComQIPtr sınıfı](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits sınıfı](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
