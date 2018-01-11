---
title: "Ierrorrecordsımpl::geterrorınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorInfo
- IErrorRecordsImpl.GetErrorInfo
- IErrorRecordsImpl::GetErrorInfo
dev_langs: C++
helpviewer_keywords: GetErrorInfo method
ms.assetid: 44d0872f-f25f-4102-8f7f-a2cfb3eeb1a0
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: db1a997235a763aa306188d612bb359cce537ba0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgeterrorinfo"></a>IErrorRecordsImpl::GetErrorInfo
Döndürür bir [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) belirtilen kayıt arabirimi işaretçisi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD( GetErrorInfo )(  
   ULONG ulRecordNum,  
   LCID lcid,  
   IErrorInfo **ppErrorInfo   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IErrorRecordsImpl Sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)