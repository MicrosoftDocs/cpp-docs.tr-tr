---
title: "Idbpropertiesımpl::GetProperties | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs: C++
helpviewer_keywords: GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e066e525def0a983d6912774f2e27e2af045a01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
Şu anda veri kaynağı nesnesi veya üzerinde şu anda ayarlanmış başlatma özellik grubundaki özelliklerinin değerlerini ayarlamak veri kaynağı, veri kaynağı bilgileri ve başlatma özellik grupları özelliklerinin değerlerini döndürür Numaralandırıcı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin **IDBProperties::GetProperties**:  
  
|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlayıcı başlatılırsa, bu yöntem özelliklerinde değerlerini döndürür **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** şu anda veri kaynağı nesnesinde ayarlanmış özellik grupları. Sağlayıcı, başlatılmadı, döndürür **DBPROPSET_DBINIT** Grup yalnızca özellikleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idbpropertiesımpl sınıfı](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesımpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [Idbpropertiesımpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)