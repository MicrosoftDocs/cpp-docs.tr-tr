---
description: 'Daha fazla bilgi edinin: CODBCFieldInfo Yapısı'
title: CODBCFieldInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 7cd7072719bec46cfbfaeb02c5c86d714c4de13c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331422"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo Yapısı

`CODBCFieldInfo`Yapı, BIR ODBC veri kaynağındaki alanlarla ilgili bilgiler içerir.

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

*m_strName*<br/>
Alanın adı.

*m_nSQLType*<br/>
Alanın SQL veri türü. Bu bir ODBC SQL veri türü veya sürücüye özgü bir SQL veri türü olabilir. Geçerli ODBC SQL veri türlerinin bir listesi için, Windows SDK "SQL veri türleri" başlığına bakın. Sürücüye özgü SQL veri türleri hakkında daha fazla bilgi için sürücünün belgelerine bakın.

*m_nPrecision*<br/>
Alanın en büyük duyarlığı. Ayrıntılar için Windows SDK "duyarlık, ölçek, uzunluk ve görüntüleme boyutu" başlığına bakın.

*m_nScale*<br/>
Alanın ölçeği. Ayrıntılar için Windows SDK "duyarlık, ölçek, uzunluk ve görüntüleme boyutu" başlığına bakın.

*m_nNullability*<br/>
Alanın null bir değer kabul edip etmeyeceğini belirtir. Bu iki değerden biri olabilir: alan null değerleri kabul ederse SQL_NULLABLE veya alan null değerleri kabul etmezse SQL_NO_NULLS.

## <a name="remarks"></a>Açıklamalar

Bu bilgileri almak için [CRecordset:: GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)çağırın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset:: GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset:: GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)
