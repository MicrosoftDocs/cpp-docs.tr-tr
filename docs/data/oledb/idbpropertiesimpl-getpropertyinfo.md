---
title: "Idbpropertiesımpl::GetPropertyInfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
dev_langs: C++
helpviewer_keywords: GetPropertyInfo method
ms.assetid: 170e9640-5010-4e0d-8a54-f50b23af08ad
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6b1eb8bc9a859c29a28291dd77e5664df2f185cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="idbpropertiesimplgetpropertyinfo"></a>IDBPropertiesImpl::GetPropertyInfo
Veri kaynağı tarafından desteklenen özellik bilgilerini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD(GetPropertyInfo)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer    
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IDBProperties::GetPropertyInfo](https://msdn.microsoft.com/en-us/library/ms718175.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin **IDBProperties::GetPropertyInfo**:  
  
|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanan [Idbınitializeımpl::m_pcutlpropınfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) bu işlevselliği uygulamak için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Idbpropertiesımpl sınıfı](../../data/oledb/idbpropertiesimpl-class.md)   
 [Idbpropertiesımpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)