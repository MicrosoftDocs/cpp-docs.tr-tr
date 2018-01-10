---
title: "Irowsetımpl::m_rgrowhandles | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
dev_langs: C++
helpviewer_keywords: m_rgRowHandles
ms.assetid: d3c2578f-58c4-4301-bf59-cf101a523a95
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bdb68e9eac5204da8c293742bcfd6ddcfdba1652
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplmrgrowhandles"></a>IRowsetImpl::m_rgRowHandles
Şu anda yanıt olarak sağlayıcısı tarafından bulunan satır işleyicilerini haritasını `GetNextRows`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
MapClass  
 m_rgRowHandles;  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Satır işleyicilerini çağırarak kaldırılır `ReleaseRows`. Bkz: [Irowsetımpl genel bakış](../../data/oledb/irowsetimpl-class.md) tanımı için *MapClass*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)