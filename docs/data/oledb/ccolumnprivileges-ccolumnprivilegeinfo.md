---
title: "CColumnPrivileges, Ccolumnprivilegeınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szTableSchema
- CColumnPrivileges
- m_bIsGrantable
- m_nColumnPropID
- m_szPrivilegeType
- COLUMN_GUID
- IS_GRANTABLE
- m_szColumnName
- m_szTableCatalog
- m_szGrantor
- GRANTOR
- GRANTEE
- COLUMN_PROPID
- m_guidColumn
- COLUMN_PRIVILEGES
- m_szTableName
- CColumnPrivilegeInfo
- m_szGrantee
dev_langs: C++
helpviewer_keywords:
- COLUMN_PROPID
- GRANTOR
- m_szPrivilegeType
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- COLUMN_PRIVILEGES
- IS_GRANTABLE
- m_nColumnPropID
- TABLE_SCHEMA
- m_szColumnName
- COLUMN_NAME
- m_szTableCatalog
- m_szGrantee
- m_szGrantor
- m_szTableName
- CColumnPrivileges typedef class
- COLUMN_GUID
- GRANTEE
- m_guidColumn
- CColumnPrivilegeInfo parameter class
- m_bIsGrantable
ms.assetid: 245df365-421f-43c6-9fcd-fb2197c871c6
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ae6f0d10b3c7dca22ded5a65ac5930258c89ca2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccolumnprivileges-ccolumnprivilegeinfo"></a>CColumnPrivileges, CColumnPrivilegeInfo
Çağrı typedef sınıfı **CColumnPrivileges** parametre sınıfı uygulamak için **Ccolumnprivilegeınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf için kullanılabilir veya belirli bir kullanıcı tarafından verilen Kataloğu'nda tanımlanan tablolar, sütunlar üzerinde ayrıcalıkları tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [COLUMN_PRIVILEGES satır kümesi](https://msdn.microsoft.com/en-us/library/ms715800.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szGrantor|GRANTOR|  
|m_szGrantee|GRANTEE|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szColumnName|COLUMN_NAME|  
|m_guidColumn|COLUMN_GUID|  
|m_nColumnPropID|COLUMN_PROPID|  
|m_szPrivilegeType|PRIVILEGE_TYPE|  
|m_bIsGrantable|IS_GRANTABLE|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)