---
title: "Codbcfieldınfo yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5b2b5d707b9915aa0d5e3fd1362746fe30a99a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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


