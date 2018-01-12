---
title: IRowsetUpdateImpl::Update | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
dev_langs: C++
helpviewer_keywords: Update method
ms.assetid: 9ec6884d-aa9c-4871-a803-c048f162403c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2cf0b2989fabda9217abd64aef485f94b2c5ccc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetupdateimplupdate"></a>IRowsetUpdateImpl::Update
Satırın son getirme veya güncelleştirme yapılan değişiklikler iletir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD ( Update )(  
   HCHAPTER /* hReserved */,  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBCOUNTITEM* pcRows,  
   HROW** prgRows,  
   DBROWSTATUS** prgRowStatus   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hReserved`  
 [in] Karşılık gelen `hChapter` parametresinde [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx).  
  
 Diğer parametreler için bkz: [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Değişiklikleri aktarılan çağırarak [IRowsetChangeImpl::flushdata](../../data/oledb/irowsetchangeimpl-flushdata.md). Tüketici çağırmalısınız [CRowset::Update](../../data/oledb/crowset-update.md) değişikliklerin etkili olması. Ayarlama *prgRowstatus* açıklandığı gibi uygun bir değere [satır durumları](https://msdn.microsoft.com/en-us/library/ms722752.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetUpdateImpl Sınıfı](../../data/oledb/irowsetupdateimpl-class.md)