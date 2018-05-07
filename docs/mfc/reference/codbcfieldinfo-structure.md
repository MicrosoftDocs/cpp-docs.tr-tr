---
title: Codbcfieldınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CODBCFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88bcac3c7ce4658ec7dafeaa1cac45b5f2450298
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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


