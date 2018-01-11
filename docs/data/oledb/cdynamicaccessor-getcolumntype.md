---
title: CDynamicAccessor::GetColumnType | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDynamicAccessor.GetColumnType
- CDynamicAccessor::GetColumnType
- GetColumnType
- CDynamicAccessor.GetColumnType
- ATL::CDynamicAccessor::GetColumnType
dev_langs: C++
helpviewer_keywords: GetColumnType method
ms.assetid: ac96a2e9-6049-4eb5-9718-9f5f5446b74e
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: dedacd68de5a254d138326a4030511685ab0da2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdynamicaccessorgetcolumntype"></a>CDynamicAccessor::GetColumnType
Belirtilen sütunun veri türünü alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool GetColumnType(   
   DBORDINAL nColumn,   
   DBTYPE* pType    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nColumn`  
 [in] Sütun numarası. Sütun numaraları 1 ile başlar. 0 değeri, varsa yer işareti sütuna başvuruyor.  
  
 `pType`  
 [out] Belirtilen sütunun veri türünü gösteren bir işaretçi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarı veya **false** hatasında.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicAccessor sınıfı](../../data/oledb/cdynamicaccessor-class.md)   
 [DBTYPE](https://msdn.microsoft.com/en-us/library/ms711251.aspx)