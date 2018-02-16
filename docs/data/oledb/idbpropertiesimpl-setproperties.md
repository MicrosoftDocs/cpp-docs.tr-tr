---
title: "Idbpropertiesımpl::SetProperties | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl.SetProperties
- SetProperties
- IDBPropertiesImpl::SetProperties
dev_langs:
- C++
helpviewer_keywords:
- SetProperties method
ms.assetid: 2f9fc1de-7f35-4bca-bab3-7b427bf92c26
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9cd0b425a61d3a9dd669f99e4c4471e728e68662
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="idbpropertiesimplsetproperties"></a>IDBPropertiesImpl::SetProperties
Özellikleri veri kaynağı ve başlatma özellik grupları için veri kaynağı nesneleri veya başlatma özellik grubu sıralayıcısını ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD(SetProperties)(ULONG cPropertySets,   
   DBPROPSET rgPropertySets[]);  
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