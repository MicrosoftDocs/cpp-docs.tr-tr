---
title: "IRowsetChangeImpl::ınsertrow | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
dev_langs: C++
helpviewer_keywords: InsertRow method
ms.assetid: 93027be3-921e-438e-a19a-6e5aadb813eb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f434468580d37fd9a05b659b59d320199f366c84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetchangeimplinsertrow"></a>IRowsetChangeImpl::InsertRow
Oluşturur ve yeni bir satır kümesinde başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD ( InsertRow )(  
   HCHAPTER /* hReserved */,  
   HACCESSOR hAccessor,  
   void* pData,  
   HROW* phRow   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetChange::InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetChangeImpl Sınıfı](../../data/oledb/irowsetchangeimpl-class.md)