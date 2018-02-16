---
title: CDynamicParameterAccessor::SetParamStatus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
dev_langs:
- C++
helpviewer_keywords:
- SetParamStatus method
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d958514a0e9b784fa969695bbb75e530d0ae6db
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="cdynamicparameteraccessorsetparamstatus"></a>CDynamicParameterAccessor::SetParamStatus
Arabellekte depolanan belirtilen parametre durumunu ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
bool SetParamStatus(DBORDINAL nParam,  
   DBSTATUS status);  ```  
  
#### Parameters  
 `nParam`  
 [in] The parameter number (offset from 1). Parameter 0 is reserved for return values. The parameter number is the index of the parameter based on its order in the SQL or stored procedure call. See [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) for an example.  
  
 *status*  
 [in] The `DBSTATUS` status of the specified parameter. For information on `DBSTATUS` values, see [Status](https://msdn.microsoft.com/en-us/library/ms722617.aspx) in the *OLE DB Programmer's Reference*, or search for `DBSTATUS` in oledb.h.  
  
## Remarks  
 Returns **true** on success or **false** on failure.  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [CDynamicParameterAccessor Class](../../data/oledb/cdynamicparameteraccessor-class.md)