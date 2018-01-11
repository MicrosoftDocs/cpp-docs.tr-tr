---
title: "Idbpropertiesımpl::SetProperties | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs: C++
helpviewer_keywords: SetProperties method
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d835810a2ca14c8e0631ed7dda8fcaddeb859d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idbpropertiesimplsetproperties"></a>IDBPropertiesImpl::SetProperties
Özellikleri veri kaynağı ve başlatma özellik grupları için veri kaynağı nesneleri veya başlatma özellik grubu sıralayıcısını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD(SetProperties)(   
   ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IDBProperties::SetProperties](https://msdn.microsoft.com/en-us/library/ms723049.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlayıcı başlatılırsa, bu yöntem özellik değerlerini ayarlar **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** özelliği veri kaynağı nesnesi için grupları. Sağlayıcı başlatılmadı, ayarlar **DBPROPSET_DBINIT** Grup yalnızca özellikleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idbpropertiesımpl sınıfı](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesımpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)