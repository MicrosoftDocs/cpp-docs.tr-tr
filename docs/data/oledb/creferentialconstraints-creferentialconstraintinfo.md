---
title: "CReferentialConstraints, Creferentialconstraintınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_szUniqueName
- m_szCatalog
- DELETE_RULE
- m_szUniqueCatalog
- CONSTRAINT_NAME
- CReferentialConstraintInfo
- MATCH_OPTION
- m_szSchema
- m_szDeleteRule
- m_szUpdateRule
- m_szUniqueSchema
- CReferentialConstraints
- m_szName
- CONSTRAINT_CATALOG
- m_szMatchOption
- CONSTRAINT_SCHEMA
dev_langs: C++
helpviewer_keywords:
- m_szUniqueSchema
- DESCRIPTION class data member
- m_szSchema
- CONSTRAINT_CATALOG
- CReferentialConstraints typedef class
- m_szUniqueName
- m_szCatalog
- CONSTRAINT_NAME
- m_szDeleteRule
- DELETE_RULE
- MATCH_OPTION
- CONSTRAINT_SCHEMA
- m_szName
- m_szDescription
- m_szMatchOption
- m_szUniqueCatalog
- m_szUpdateRule
- CReferentialConstraintInfo parameter class
ms.assetid: 5d485358-be29-41c2-b0ce-19e023598e73
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: efc7df7f5d8dfd2cd0106297ac8748a4d1b0531e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creferentialconstraints-creferentialconstraintinfo"></a>CReferentialConstraints, CReferentialConstraintInfo
Çağrı typedef sınıfı **CReferentialConstraints** parametre sınıfı uygulamak için **Creferentialconstraintınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf belirli bir kullanıcı tarafından sahip olunan Kataloğu'nda tanımlanan başvuru kısıtlamalarını, tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [REFERENTIAL_CONSTRAINTS satır kümesi](https://msdn.microsoft.com/en-us/library/ms719737.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szUniqueCatalog|UNIQUE_CONSTRAINT_CATALOG|  
|m_szUniqueSchema|UNIQUE_CONSTRAINT_SCHEMA|  
|m_szUniqueName|UNIQUE_CONSTRAINT_NAME|  
|m_szMatchOption|MATCH_OPTION|  
|m_szUpdateRule|UPDATE_RULE|  
|m_szDeleteRule|DELETE_RULE|  
|m_szDescription|AÇIKLAMA|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions sınıfı](../../data/oledb/crestrictions-class.md)