---
title: "Ierrorrecordsımpl::getcustomerrorobject | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IErrorRecordsImpl::GetCustomErrorObject
- IErrorRecordsImpl::GetCustomErrorObject
- ATL.IErrorRecordsImpl.GetCustomErrorObject
- IErrorRecordsImpl.GetCustomErrorObject
- GetCustomErrorObject
dev_langs: C++
helpviewer_keywords: GetCustomErrorObject method
ms.assetid: 96d3549b-a49c-4552-94b2-71babaf1bf20
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 918c5800d645575f99450b1fbc3b9f2bfb303e20
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgetcustomerrorobject"></a>IErrorRecordsImpl::GetCustomErrorObject
Bir işaretçi bir arabirim için bir özel hata nesnesi döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD( GetCustomErrorObject )(  
   ULONG ulRecordNum,  
   REFIID riid,  
   IUnknown **ppObject   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IErrorRecords::GetCustomErrorObject](https://msdn.microsoft.com/en-us/library/ms725417.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IErrorRecordsImpl Sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)