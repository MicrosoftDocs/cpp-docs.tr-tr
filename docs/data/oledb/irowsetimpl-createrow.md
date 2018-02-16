---
title: "Irowsetımpl::createrow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs:
- C++
helpviewer_keywords:
- CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4403388146b79eec4435374793b2517dd46ff188
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Bir yardımcı yöntemi tarafından çağrılır [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) yeni ayırmak için **HROW**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT CreateRow(DBROWOFFSET lRowsOffset,  
  DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *lRowsOffset*  
 Oluşturulan satır imleç konumu.  
  
 *cRowsObtained*  
 Bir başvuru oluşturulan satır sayısını gösteren kullanıcıya geri geçirildi.  
  
 *rgRows*  
 Bir dizi **HROW**s döndürülen yeni oluşturulan satır işleyicilerini ile çağırana.  
  
## <a name="remarks"></a>Açıklamalar  
 Satır varsa, bu yöntemi çağırır [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve döndürür. Aksi takdirde RowClass Şablon değişkeni yeni bir örneğini ayırır ve ona ekler [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)