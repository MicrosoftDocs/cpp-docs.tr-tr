---
title: CSession::Commit | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
dev_langs: C++
helpviewer_keywords: Commit method
ms.assetid: 1d5f56b9-000c-4bae-a975-89d3452f499f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d7cec85c3f667b5ea0423ad6caf998c53bad6307
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csessioncommit"></a>CSession::Commit
İşlem kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Commit(   
   BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSession Sınıfı](../../data/oledb/csession-class.md)