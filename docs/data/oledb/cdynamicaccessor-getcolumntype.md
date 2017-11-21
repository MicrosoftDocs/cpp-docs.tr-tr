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
ms.openlocfilehash: c205d11cd71d717bd2ad67d2d271aa421534505a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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