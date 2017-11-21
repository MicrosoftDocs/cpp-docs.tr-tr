---
title: "Irowsetınfoımpl::getspecification | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetInfoImpl::GetSpecification
- ATL.IRowsetInfoImpl.GetSpecification
- IRowsetInfoImpl.GetSpecification
- GetSpecification
- ATL::IRowsetInfoImpl::GetSpecification
dev_langs: C++
helpviewer_keywords: GetSpecification method
ms.assetid: 8e14289d-9cca-4df7-a9e0-f4ef03c61e30
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 012f845cd47bca6008cdc493651cf17bb1745466
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetinfoimplgetspecification"></a>IRowsetInfoImpl::GetSpecification
Arabirim işaretçisi bu satır kümesini oluşturan nesnede (komut veya oturum) döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD ( GetSpecification )(  
   REFIID riid,  
   IUnknown** ppSpecification   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetInfo::GetSpecification](https://msdn.microsoft.com/en-us/library/ms716746.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntemle kullanmak [Igetdatasourceımpl](../../data/oledb/igetdatasourceimpl-class.md) veri kaynağı nesnesinden alınamıyor.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Irowsetınfoımpl sınıfı](../../data/oledb/irowsetinfoimpl-class.md)   
 [Irowsetınfoımpl::getreferencedrowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [Irowsetınfoımpl::GetProperties](../../data/oledb/irowsetinfoimpl-getproperties.md)