---
title: PROVIDER_COLUMN_ENTRY_GN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- PROVIDER_COLUMN_ENTRY_GN
dev_langs:
- C++
helpviewer_keywords:
- PROVIDER_COLUMN_ENTRY_GN macro
ms.assetid: be77ba85-634c-4e28-832f-d2fa40413254
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 203f339dc031f4a21f16181043b051c4eaa5ec35
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="providercolumnentrygn"></a>PROVIDER_COLUMN_ENTRY_GN
Sağlayıcı tarafından desteklenen belirli bir sütunu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
PROVIDER_COLUMN_ENTRY_GN (name  
, ordinal, flags, colSize, dbtype, precision, scale, guid )  
```  
  
#### <a name="parameters"></a>Parametreler  
 *Adı*  
 [in] Sütun adı.  
  
 `ordinal`  
 [in] Sütun numarası. Bir yer işareti sütun sütun olmadığı sürece sütun numarası 0 olmalıdır.  
  
 `flags`  
 [in] Verinin nasıl döndürüldüğüne belirtir. Bkz: `dwFlags` açıklamasında [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *colSize*  
 [in] Sütun boyutu.  
  
 `dbtype`  
 [in] Değer veri türünü belirtir. Bkz: **wType** açıklamasında [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 *precision*  
 [in] Veri alınırken kullanılacak duyarlık gösterir *dbType* olan `DBTYPE_NUMERIC` veya **DBTYPE_DECIMAL**. Bkz: **bPrecision** açıklamasında [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `scale`  
 [in] DbType ise veri alınırken kullanılacak ölçek gösterir `DBTYPE_NUMERIC` veya **DBTYPE_DECIMAL**. Bkz: **bScale** açıklamasında [IAccessor::CreateAccessor'ı yapıları](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  
  
 `guid`  
 Bir şema satır kümesi GUID'si. Bkz: [IDBSchemaRowset](https://msdn.microsoft.com/en-us/library/ms713686.aspx) içinde *OLE DB Programcının Başvurusu* şema satır kümeleri ve GUID'ler listesi.  
  
## <a name="remarks"></a>Açıklamalar  
 Sütunun boyutu, veri türü, duyarlık, ölçek ve şema satır kümesi GUID'si belirtmenize olanak tanır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB sağlayıcı şablonları için makrolar](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)   
 [OLE DB Sağlayıcısı Oluşturma](../../data/oledb/creating-an-ole-db-provider.md)