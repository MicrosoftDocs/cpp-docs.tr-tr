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
ms.openlocfilehash: 922e5cdf0e52cee694c4ce4e54e90e1fcf10be88
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [CSession sınıfı](../../data/oledb/csession-class.md)