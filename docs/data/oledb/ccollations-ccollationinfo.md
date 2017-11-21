---
title: "CCollations, Ccollationınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COLLATION_CATALOG
- m_szCatalog
- CCollationInfo
- CCollations
- CHARACTER_SET_NAME
- CHARACTER_SET_SCHEMA
- m_szCharSetName
- m_szSchema
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- m_szCharSetCatalog
- m_szPadAttribute
- COLLATION_NAME
- COLLATION_SCHEMA
- m_szName
- COLLATIONS
dev_langs: C++
helpviewer_keywords:
- m_szSchema
- COLLATION_SCHEMA
- m_szCharSetCatalog
- m_szCatalog
- COLLATIONS recordset
- COLLATION_CATALOG
- CCollationInfo parameter class
- m_szName
- COLLATION_NAME
- m_szPadAttribute
- CHARACTER_SET_NAME
- m_szCharSetName
- CHARACTER_SET_SCHEMA
- CHARACTER_SET_CATALOG
- m_szCharSetSchema
- CCollations typedef class
ms.assetid: d8b43c4d-9dd5-4043-b4c8-38c03bfa0c72
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 99bf8120d048298ca570ea4b318c7ae9c04da811
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccollations-ccollationinfo"></a>CCollations, CCollationInfo
Çağrı typedef sınıfı **CCollations** parametre sınıfı uygulamak için **Ccollationınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf belirli bir kullanıcıya erişilebilen Kataloğu'nda tanımlanan karakter harmanlamaları, tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [HARMANLAMALARI satır kümesi](https://msdn.microsoft.com/en-us/library/ms715783.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szCatalog|COLLATION_CATALOG|  
|m_szSchema|COLLATION_SCHEMA|  
|m_szName|COLLATION_NAME|  
|m_szCharSetCatalog|CHARACTER_SET_CATALOG|  
|m_szCharSetSchema|CHARACTER_SET_SCHEMA|  
|m_szCharSetName|CHARACTER_SET_NAME|  
|m_szPadAttribute|PAD_ATTRIBUTE|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions sınıfı](../../data/oledb/crestrictions-class.md)