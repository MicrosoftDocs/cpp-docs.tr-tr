---
title: Irowsetımpl::m_rgrowhandles | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs:
- C++
helpviewer_keywords:
- m_rgRowHandles
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b4eeeb9d048cd33513556d8b0585d1e84a0699a8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101753"
---
# <a name="irowsetimplmrgrowhandles"></a>IRowsetImpl::m_rgRowHandles
Şu anda yanıt olarak sağlayıcısı tarafından bulunan satır işleyicilerini haritasını `GetNextRows`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
MapClass  
 m_rgRowHandles;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Satır işleyicilerini çağırarak kaldırılır `ReleaseRows`. Bkz: [Irowsetımpl genel bakış](../../data/oledb/irowsetimpl-class.md) tanımı için *MapClass*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)