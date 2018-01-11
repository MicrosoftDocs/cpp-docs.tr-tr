---
title: "CConstraintTableUsage, Cconstrainttableusageınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CConstraintTableUsageInfo
- CONSTRAINT_TABLE_USAGE
- m_szTableSchema
- m_szConstraintCatalog
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szConstraintSchema
- m_szTableName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- CConstraintTableUsage
- m_szConstraintName
dev_langs: C++
helpviewer_keywords:
- CConstraintTableUsage typedef class
- m_szConstraintCatalog
- CONSTRAINT_CATALOG
- m_szTableSchema
- CConstraintTableUsageInfo parameter class
- TABLE_CATALOG
- CONSTRAINT_TABLE_USAGE
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szTableCatalog
- m_szConstraintName
- m_szTableName
- m_szConstraintSchema
ms.assetid: 666b44de-3922-4c5e-ad17-d5ea27120174
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bf806ac79d74a3ce0ba265722a1633854d925778
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cconstrainttableusage-cconstrainttableusageinfo"></a>CConstraintTableUsage, CConstraintTableUsageInfo
Çağrı typedef sınıfı **CConstraintTableUsage** parametre sınıfı uygulamak için **Cconstrainttableusageınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf, Kataloğu'nda tanımlanan ve belirli bir kullanıcıya ait başvuru kısıtlamalarını, benzersiz kısıtlamalar, denetim kısıtlamaları ve onaylar tarafından kullanılır tabloları tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [CONSTRAINT_TABLE_USAGE satır kümesi](https://msdn.microsoft.com/en-us/library/ms724522.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szConstraintCatalog|CONSTRAINT_CATALOG|  
|m_szConstraintSchema|CONSTRAINT_SCHEMA|  
|m_szConstraintName|CONSTRAINT_NAME|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)