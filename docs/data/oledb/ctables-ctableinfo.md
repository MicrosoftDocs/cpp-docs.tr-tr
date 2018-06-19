---
title: CTables, Ctableınfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- m_szCatalog
- TABLE_SCHEMA
- CTables
- TABLE_NAME
- TABLE_CATALOG
- CTableInfo
- m_guidTable
- m_szType
- m_szSchema
- m_szName
- TABLE_GUID
dev_langs:
- C++
helpviewer_keywords:
- DESCRIPTION class data member
- m_szSchema
- TABLE_CATALOG
- m_szType
- m_szCatalog
- TABLE_NAME
- TABLE_SCHEMA
- TABLE_GUID
- m_szName
- m_szDescription
- CTables typedef class
- m_guidTable
- CTableInfo parameter class
ms.assetid: 57670f1b-ba99-43b0-b406-4c75b44f14f6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 63c190fb32718ce87b611a7c7f5f5e8e1a2c343a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100284"
---
# <a name="ctables-ctableinfo"></a>CTables, CTableInfo
Çağrı typedef sınıfı **CTables** parametre sınıfı uygulamak için **Ctableınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf için kullanılabilir veya belirli bir kullanıcı tarafından verilen Kataloğu'nda tanımlanan tablolarda ayrıcalıkları tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [tablolar satır kümesi](https://msdn.microsoft.com/en-us/library/ms716980.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szCatalog|TABLE_CATALOG|  
|m_szSchema|TABLE_SCHEMA|  
|m_szName|TABLE_NAME|  
|m_szType|TABLE_TYPE|  
|m_guidTable|TABLE_GUID|  
|m_szDescription|AÇIKLAMA|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)