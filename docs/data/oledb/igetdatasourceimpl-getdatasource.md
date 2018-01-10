---
title: "Igetdatasourceımpl::getdatasource | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetDataSource
- IGetDataSourceImpl.GetDataSource
- IGetDataSourceImpl::GetDataSource
dev_langs: C++
helpviewer_keywords: GetDataSource method
ms.assetid: b70995d2-b951-452e-a2d4-fb3eb085886e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 850cdd40124566fad0bc71d70e0fc2e4f1317de9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="igetdatasourceimplgetdatasource"></a>IGetDataSourceImpl::GetDataSource
Arabirim işaretçisi oturum oluşturduğunuz veri kaynağı nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD(GetDataSource)(   
   REFIID riid,   
   IUnknown ** ppDataSource    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IGetDataSource::GetDataSource](https://msdn.microsoft.com/en-us/library/ms725443.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Veri kaynağı nesnesi özelliklerinde erişmeniz gerekiyorsa yararlıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IGetDataSourceImpl Sınıfı](../../data/oledb/igetdatasourceimpl-class.md)