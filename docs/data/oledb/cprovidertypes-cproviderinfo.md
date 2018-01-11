---
title: "CProviderTypes, Cproviderınfo | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- m_bIsLong
- m_szLocalTypeName
- m_guidType
- m_bCaseSensitive
- m_szVersion
- m_szCreateParams
- IS_NULLABLE
- m_bAutoUniqueValue
- LITERAL_SUFFIX
- COLUMN_SIZE
- CProviderTypes
- LOCAL_TYPE_NAME
- MINIMUM_SCALE
- m_nMinScale
- m_nColumnSize
- m_szLiteralSuffix
- m_bFixedPrecScale
- m_szLiteralPrefix
- m_nMaxScale
- m_szTypeLib
- m_nDataType
- m_bUnsignedAttribute
- m_nSearchable
- m_bBestMatch
- m_szTypeName
- DATA_TYPE
- MAXIMUM_SCALE
- CProviderInfo
- FIXED_PREC_SCALE
- m_bIsNullable
- IS_LONG
dev_langs: C++
helpviewer_keywords:
- DATA_TYPE
- MAXIMUM_SCALE
- m_nMinScale
- m_guidType
- LOCAL_TYPE_NAME
- m_bAutoUniqueValue
- m_bBestMatch
- m_bIsLong
- m_bUnsignedAttribute
- CProviderInfo parameter class
- FIXED_PREC_SCALE
- m_nColumnSize
- m_szVersion
- CProviderTypes typedef class
- m_szCreateParams
- IS_NULLABLE
- m_bIsNullable
- m_szTypeLib
- m_szLiteralPrefix
- m_nMaxScale
- m_nDataType
- m_bCaseSensitive
- m_bFixedPrecScale
- m_nSearchable
- MINIMUM_SCALE
- m_szTypeName
- m_szLocalTypeName
- IS_LONG
- LITERAL_SUFFIX
- COLUMN_SIZE
- m_szLiteralSuffix
ms.assetid: 6f1620ff-c2f0-4f5b-931c-27b0cd2a580d
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e0f3b5e505695eca01437bf8d1999ffccca881a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cprovidertypes-cproviderinfo"></a>CProviderTypes, CProviderInfo
Çağrı typedef sınıfı **CProviderTypes** parametre sınıfı uygulamak için **Cproviderınfo**.  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [şema satır kümesi sınıfları ve Typedef sınıfları](../../data/oledb/schema-rowset-classes-and-typedef-classes.md) typedef sınıfları kullanma hakkında daha fazla bilgi için.  
  
 Bu sınıf veri sağlayıcısı tarafından desteklenen (Temel) veri türlerini tanımlar.  
  
 Aşağıdaki tabloda, sınıf veri üyeleri ve bunların karşılık gelen OLE DB sütunlarını listeler. Bkz: [provıder_types satır kümesi](https://msdn.microsoft.com/en-us/library/ms709785.aspx) içinde *OLE DB Programcının Başvurusu* şemayı ve sütunları hakkında daha fazla bilgi.  
  
|Veri üyeleri|OLE DB sütunları|  
|------------------|--------------------|  
|m_szTypeName|TYPE_NAME|  
|m_nDataType|DATA_TYPE|  
|m_nColumnSize|COLUMN_SIZE|  
|m_szLiteralPrefix|LITERAL_PREFIX|  
|m_szLiteralSuffix|LITERAL_SUFFIX|  
|m_szCreateParams|CREATE_PARAMS|  
|m_bIsNullable|IS_NULLABLE|  
|m_bCaseSensitive|CASE_SENSITIVE|  
|m_nSearchable|ARANABİLİR|  
|m_bUnsignedAttribute|UNSIGNED_ATTRIBUTE|  
|m_bFixedPrecScale|FIXED_PREC_SCALE|  
|m_bAutoUniqueValue|AUTO_UNIQUE_VALUE|  
|m_szLocalTypeName|LOCAL_TYPE_NAME|  
|m_nMinScale|MINIMUM_SCALE|  
|m_nMaxScale|MAXIMUM_SCALE|  
|m_guidType|GUID|  
|m_szTypeLib|TÜR KİTAPLIĞI|  
|m_szVersion|VERSION|  
|m_bIsLong|IS_LONG|  
|m_bBestMatch|BEST_MATCH|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbsch.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CRestrictions Sınıfı](../../data/oledb/crestrictions-class.md)