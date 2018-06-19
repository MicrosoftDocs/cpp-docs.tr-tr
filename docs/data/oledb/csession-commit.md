---
title: CSession::Commit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
dev_langs:
- C++
helpviewer_keywords:
- Commit method
ms.assetid: 1d5f56b9-000c-4bae-a975-89d3452f499f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 44fdeef9462bf30a30226ea292024a4cdb1bf8ca
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33096853"
---
# <a name="csessioncommit"></a>CSession::Commit
İşlem kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Commit(BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0) const throw();  
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