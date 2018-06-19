---
title: IRowsetChangeImpl::flushdata | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs:
- C++
helpviewer_keywords:
- FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 00ad40d6d795ce7f3e9307e7034df875380be839
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099228"
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
Verileri, depolama alanına kaydetmeye sağlayıcısı tarafından Overidden.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT FlushData(HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush);  ```  
  
#### Parameters  
 *hRowToFlush*  
 [in] Handle to the rows for the data. The type of this row is determined from the *RowClass* template argument of the `IRowsetImpl` class (`CSimpleRow` by default).  
  
 *hAccessorToFlush*  
 [in] Handle to the accessor, which contains binding information and type information in its **PROVIDER_MAP** (see [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
## Return Value  
 A standard `HRESULT`.  
  
## Requirements  
 **Header:** atldb.h  
  
## See Also  
 [IRowsetChangeImpl Class](../../data/oledb/irowsetchangeimpl-class.md)