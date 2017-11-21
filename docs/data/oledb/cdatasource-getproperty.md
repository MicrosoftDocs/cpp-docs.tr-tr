---
title: CDataSource::GetProperty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
dev_langs: C++
helpviewer_keywords: GetProperty method
ms.assetid: 6531147c-b164-4ab5-a4a7-509634b85b4d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 96b7437bd96592044b4eab33df3e4912bd677591
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourcegetproperty"></a>CDataSource::GetProperty
Bağlı veri kaynağı nesnesi için belirtilen bir özelliğin değerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT GetProperty(   
   const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant    
) const throw( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `guid`  
 [in] Kendisi için özelliği geri dönmek ayarlanan özelliği tanımlayan bir GUID.  
  
 `propid`  
 [in] Döndürülecek bir özellik için özellik kimliği.  
  
 *pVariant*  
 [out] Değişken için bir işaretçi nerede **GetProperty** özelliğinin değerini döndürür.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Birden çok özellikleri almak için [GetProperties](../../data/oledb/cdatasource-getproperties.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDataSource sınıfı](../../data/oledb/cdatasource-class.md)