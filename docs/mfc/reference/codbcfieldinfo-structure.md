---
title: "Codbcfieldınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CODBCFieldInfo
dev_langs: C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db9eaca0857d2caedb525dc56ad3d99aaf1d4559
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo Yapısı
`CODBCFieldInfo` Yapısı ODBC veri kaynağını alanları hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CODBCFieldInfo  
{  
    CString m_strName;  
    SWORD m_nSQLType;  
    UDWORD m_nPrecision;  
    SWORD m_nScale;  
    SWORD m_nNullability;  
};  
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Alanın adı.  
  
 *m_nSQLType*  
 Alan SQL veri türü. Bu, bir ODBC SQL veri türü veya bir sürücüye özgü SQL veri türü olabilir. Geçerli ODBC SQL veri türleri listesi için Windows SDK'sı "SQL veri türleri" konusuna bakın. Sürücü özgü SQL veri türleri hakkında daha fazla bilgi için sürücünün belgelerine bakın.  
  
 *m_nPrecision*  
 Alan en fazla hassasiyet. Ayrıntılar için Windows SDK'ın "Duyarlık, Ölçek, uzunluğu ve görüntüleme boyutu" bakın.  
  
 *m_nScale*  
 Alan ölçeği. Ayrıntılar için Windows SDK'ın "Duyarlık, Ölçek, uzunluğu ve görüntüleme boyutu" bakın.  
  
 *m_nNullability*  
 Olup alan bir Null değer kabul eder. Bu iki değerden biri olabilir: **SQL_NULLABLE** Null değerler, alanın kabul ederse veya **SQL_NO_NULLS** alanı Null değerleri kabul etmiyorsa.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bilgileri almak için arama [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


