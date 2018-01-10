---
title: "Irowsetımpl::restartposition | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
dev_langs: C++
helpviewer_keywords: RestartPosition method
ms.assetid: 14de66ef-8d2c-4404-adb6-3f6c74ac6cf1
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d8ed3217a635f8a0b9af5e2c94fff325e07bff61
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplrestartposition"></a>IRowsetImpl::RestartPosition
Sonraki getirme konumunu ilk konumuna yeniden konumlandırır; diğer bir deyişle, satır ilk kez yüklendiğinde konumuna oluşturulur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD( RestartPosition )(  
   HCHAPTER /* hReserved */   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowset::RestartPosition](https://msdn.microsoft.com/en-us/library/ms712877.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Satır kümesi konumdur kadar tanımsız **GetNextRow** olarak adlandırılır. Geriye dönük çağırarak bir rowet taşıyabilirsiniz `RestartPosition` ve getirme veya geriye doğru kaydırma.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)