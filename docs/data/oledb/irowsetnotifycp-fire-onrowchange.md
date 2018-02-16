---
title: IRowsetNotifyCP::Fire_OnRowChange | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetNotifyCP.Fire_OnRowChange
- ATL.IRowsetNotifyCP.Fire_OnRowChange
- Fire_OnRowChange
- ATL::IRowsetNotifyCP::Fire_OnRowChange
- IRowsetNotifyCP::Fire_OnRowChange
dev_langs:
- C++
helpviewer_keywords:
- Fire_OnRowChange method
ms.assetid: 6f9beed6-7a69-4c92-936f-422e98f3de5c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a1b957ebf13dce0b276955bd9f089b461677b556
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetnotifycpfireonrowchange"></a>IRowsetNotifyCP::Fire_OnRowChange
Yayınlar bir [OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) bağlantı noktasındaki tüm dinleyicileri olaya **IID_IRowsetNotify** tüketicilere satırları etkileyen bir değişiklik.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Fire_OnRowChange(IRowset* pRowset,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetNotify::OnRowChange](https://msdn.microsoft.com/en-us/library/ms722694.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetNotifyCP Sınıfı](../../data/oledb/irowsetnotifycp-class.md)