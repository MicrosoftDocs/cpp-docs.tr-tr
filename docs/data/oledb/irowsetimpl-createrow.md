---
title: "Irowsetımpl::createrow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
dev_langs: C++
helpviewer_keywords: CreateRow method
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2f455935a1736eae2c70d95f4528d216a80e782a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplcreaterow"></a>IRowsetImpl::CreateRow
Bir yardımcı yöntemi tarafından çağrılır [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) yeni ayırmak için **HROW**.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
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
 [Irowsetımpl sınıfı](../../data/oledb/irowsetimpl-class.md)