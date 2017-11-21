---
title: "Idbınitializeımpl::m_dwstatus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl.m_dwStatus
- ATL.IDBInitializeImpl.m_dwStatus
- IDBInitializeImpl::m_dwStatus
- IDBInitializeImpl<T>::m_dwStatus
- ATL.IDBInitializeImpl<T>.m_dwStatus
- ATL::IDBInitializeImpl<T>::m_dwStatus
- m_dwStatus
dev_langs: C++
helpviewer_keywords: m_dwStatus
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c54cc1d91916e23e432faf8e407400b0985e3285
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idbinitializeimplmdwstatus"></a>IDBInitializeImpl::m_dwStatus
Veri kaynağı bayraklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
DWORD m_dwStatus;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bayrakların belirtin veya veri kaynağı nesnesi için çeşitli öznitelikler durumunu gösterir. Bir veya daha fazlasını içeriyor `enum` değerler:  
  
```  
enum DATASOURCE_FLAGS {  
    DSF_MASK_INIT     = 0xFFFFF00F,  
    DSF_PERSIST_DIRTY = 0x00000001,  
    DSF_INITIALIZED   = 0x00000010,  
};  
```  
  
|||  
|-|-|  
|**DSF_MASK_INIT**|Başlatılmamış duruma geri etkinleştirmek için bir maske.|  
|**DSF_PERSIST_DIRTY**|Veri kaynağı nesnesi Kalıcılık gerektiriyorsa (diğer bir deyişle, olduysa değişiklikleri) ayarlayın.|  
|**DSF_INITIALIZED**|Veri kaynağı başlatılmışsa ayarlayın.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idbınitializeımpl sınıfı](../../data/oledb/idbinitializeimpl-class.md)   
 [Idbınitializeımpl::ıdbınitializeımpl](../../data/oledb/idbinitializeimpl-idbinitializeimpl.md)   
 [Idbınitializeımpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)