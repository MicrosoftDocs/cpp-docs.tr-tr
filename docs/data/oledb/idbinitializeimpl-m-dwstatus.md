---
title: IDBInitializeImpl::m_dwStatus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
dev_langs:
- C++
helpviewer_keywords:
- m_dwStatus
ms.assetid: 7621ccff-ca60-4b75-9c6a-c104bd0e2038
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2ca6b9b072b28225883ff1972475521f0cab76c2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbinitializeimplmdwstatus"></a>IDBInitializeImpl::m_dwStatus
Veri kaynağı bayraklar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
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
 [IDBInitializeImpl::Uninitialize](../../data/oledb/idbinitializeimpl-uninitialize.md)