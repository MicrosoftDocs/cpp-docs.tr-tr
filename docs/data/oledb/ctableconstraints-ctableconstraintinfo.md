---
title: CTableConstraints, CTableConstraintInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- m_szTableSchema
- CONSTRAINT_TYPE
- m_szCatalog
- CTableConstraints
- m_bInitiallyDeferred
- CONSTRAINT_NAME
- m_szTableCatalog
- m_szType
- m_szSchema
- INITIALLY_DEFERRED
- CTableConstraintInfo
- m_szTableName
- m_bIsDeferrable
- m_szName
- CONSTRAINT_CATALOG
- CONSTRAINT_SCHEMA
- IS_DEFERRABLE
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- CTableConstraints typedef class
- IS_DEFERRABLE
- m_szSchema
- m_bInitiallyDeferred
- CONSTRAINT_CATALOG
- m_szTableSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- CONSTRAINT_NAME
- CONSTRAINT_TYPE
- CONSTRAINT_SCHEMA
- TABLE_SCHEMA
- m_szName
- m_szTableCatalog
- m_szDescription
- CTableConstraintInfo parameter class
- m_szTableName
- INITIALLY_DEFERRED
- m_bIsDeferrable
ms.assetid: aaa07ade-0bfa-41d0-94df-8342152a4ff0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d90307bfea01f203ad61180b87aed418769c3162
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ctableconstraints-ctableconstraintinfo"></a>CTableConstraints, CTableConstraintInfo
Çağrı typedef sınıfı **CTableConstraints** parametre sınıfı uygulamak için **Ctableconstraintınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf belirli bir kullanıcı tarafından sahip olunan Kataloğu'nda tanımlanan tablo kısıtlamaları tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [TABLE_CONSTRAINTS satır kümesi](https://msdn.microsoft.com/en-us/library/ms715921.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szCatalog|CONSTRAINT_CATALOG|  
|m_szSchema|CONSTRAINT_SCHEMA|  
|m_szName|CONSTRAINT_NAME|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_szType|CONSTRAINT_TYPE|  
|m_bIsDeferrable|IS_DEFERRABLE|  
|m_bInitiallyDeferred|INITIALLY_DEFERRED|  
|m_szDescription|AÇIKLAMA|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)