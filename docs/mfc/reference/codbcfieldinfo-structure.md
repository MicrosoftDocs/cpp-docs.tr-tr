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
ms.openlocfilehash: c1723e93320129fae232bb850caa123d1638a37b
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853088"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo Yapısı
`CODBCFieldInfo` Yapısı bir ODBC veri kaynağı alanları hakkında bilgileri içerir.  
  
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
 *m_strName*  
 Alanın adı.  
  
 *m_nSQLType*  
 Alan SQL veri türü. Bu, bir ODBC SQL veri türü veya bir sürücüye özel SQL veri türü olabilir. Geçerli ODBC SQL veri türleri listesi için Windows SDK'sı "SQL veri türleri" konusuna bakın. Sürücü özgü SQL veri türleri hakkında daha fazla bilgi için sürücünün belgelerine bakın.  
  
 *m_nPrecision*  
 Verilen duyarlık alan. Ayrıntılar için Windows SDK'yı "Duyarlığı, Ölçek, uzunluğu ve görüntüleme boyutu" konularına bakın.  
  
 *m_nScale*  
 Ölçeğin alan. Ayrıntılar için Windows SDK'yı "Duyarlığı, Ölçek, uzunluğu ve görüntüleme boyutu" konularına bakın.  
  
 *m_nNullability*  
 Olup alan, bir Null değer kabul eder. Bu iki değerden biri olabilir: alan Null değerleri kabul eder ya da alan kabul edilmez, SQL_NO_NULLS Null değerleri SQL_NULLABLE.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu bilgileri almak için arama [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri çağırmaları ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRecordset::GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)   
 [CRecordset::GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)


