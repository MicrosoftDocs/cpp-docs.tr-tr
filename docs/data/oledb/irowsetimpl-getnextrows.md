---
title: "Irowsetımpl::GetNextRows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
dev_langs: C++
helpviewer_keywords: GetNextRows method
ms.assetid: 1c0975d6-d770-4884-830b-6986c6fa8e65
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6876cd59a36177ce89a196d6fe0ae403d16bfa68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplgetnextrows"></a>IRowsetImpl::GetNextRows
Satırları ardışık olarak önceki konumdan hatırlamak getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD( GetNextRows )(  
   HCHAPTER hReserved,  
   DBROWOFFSET lRowsOffset,  
   DBROWCOUNT cRows,  
   DBCOUNTITEM* pcRowsObtained,  
   HROW** prghRows   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowset::GetNextRows](https://msdn.microsoft.com/en-us/library/ms709827.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Irowsetımpl sınıfı](../../data/oledb/irowsetimpl-class.md)   
 [Irowsetımpl::addrefrows](../../data/oledb/irowsetimpl-addrefrows.md)   
 [Irowsetımpl::releaserows](../../data/oledb/irowsetimpl-releaserows.md)