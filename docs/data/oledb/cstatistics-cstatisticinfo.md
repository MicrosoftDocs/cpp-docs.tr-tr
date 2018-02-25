---
title: "CStatistics, Cstatisticınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStatistics
- m_szTableSchema
- CStatisticInfo
- m_szTableCatalog
- m_nCardinality
- m_szTableName
dev_langs:
- C++
helpviewer_keywords:
- m_nCardinality
- m_szTableSchema
- TABLE_CATALOG
- TABLE_NAME
- TABLE_SCHEMA
- CStatistics typedef class
- m_szTableCatalog
- m_szTableName
- CStatisticInfo parameter class
ms.assetid: 5822231c-6963-44a6-ae2f-29aca76e1600
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d267bbedf1663f7dfc5f31cd102a45c121c77af8
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="cstatistics-cstatisticinfo"></a>CStatistics, CStatisticInfo
Çağrı typedef sınıfı **CStatistics** parametre sınıfı uygulamak için **Cstatisticınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf Kataloğu'nda tanımlanan ve belirli bir kullanıcıya ait istatistikleri, tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [İSTATİSTİKLERİ satır kümesi](https://msdn.microsoft.com/en-us/library/ms715957.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szTableCatalog|TABLE_CATALOG|  
|m_szTableSchema|TABLE_SCHEMA|  
|m_szTableName|TABLE_NAME|  
|m_nCardinality|ÖNEM DÜZEYİ|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)