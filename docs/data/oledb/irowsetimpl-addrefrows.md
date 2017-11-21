---
title: "Irowsetımpl::addrefrows | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl::AddRefRows
- AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
dev_langs: C++
helpviewer_keywords: AddRefRows method
ms.assetid: adc0989b-7592-432e-82d9-df4445431531
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b890d549b6173982d4b63885f0a4ea5bf16e0007
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimpladdrefrows"></a>IRowsetImpl::AddRefRows
Bir başvuru sayısı varolan bir satır tanıtıcı ekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD( AddRefRows )(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[]   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Irowsetımpl sınıfı](../../data/oledb/irowsetimpl-class.md)   
 [Irowsetımpl::refrows](../../data/oledb/irowsetimpl-refrows.md)   
 [Irowsetımpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)   
 [Irowsetımpl::releaserows](../../data/oledb/irowsetimpl-releaserows.md)