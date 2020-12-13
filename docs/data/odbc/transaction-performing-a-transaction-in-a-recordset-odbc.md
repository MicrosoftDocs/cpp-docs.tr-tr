---
description: 'Daha fazla bilgi edinin: Işlem: bir kayıt kümesinde Işlem gerçekleştirme (ODBC)'
title: 'İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: bb041d35e7ab0bfc7e19f2658a8cdadae4bd8c7e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333884"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)

Bu konu, bir kayıt kümesinde bir işlemin nasıl gerçekleştirileceğini açıklamaktadır.

> [!NOTE]
> Yalnızca bir düzey işlem desteklenir; işlem iç içe geçirilemez.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Bir kayıt kümesinde işlem gerçekleştirmek için

1. `CDatabase`Nesnenin `BeginTrans` üye işlevini çağırın.

1. Toplu satır getirmeyi gerçekleştirdiyseniz, `AddNew/Update` `Edit/Update` `Delete` aynı veritabanının bir veya daha fazla kayıt kümesi nesnesinin,, ve üye işlevlerini gereken sayıda çağırın. Daha fazla bilgi için bkz. [kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Toplu satır getirmeyi uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.

1. Son olarak, `CDatabase` nesnenin `CommitTrans` üye işlevini çağırın. Güncelleştirmelerden birinde bir hata oluşursa veya değişiklikleri iptal etmeyi seçerseniz, `Rollback` üye işlevini çağırın.

Aşağıdaki örnek iki kayıt kümesi kullanarak bir okulın kayıt veritabanından bir öğrencinin kaydını siler ve öğrencinin kayıtlı olduğu tüm sınıflardan bir öğrenci 'yi kaldırır. `Delete`Her iki kayıt kümesinde yapılan çağrılar başarılı olması gerektiğinden, bir işlem gereklidir. Örnek, öğesinin varlığını `m_dbStudentReg` , `CDatabase` veri kaynağına zaten bağlanmış bir üye değişkenini ve kayıt kümesi sınıflarını ve ' nin olduğunu varsayar `CEnrollmentSet` `CStudentSet` . `strStudentID`Değişken, kullanıcıdan alınan bir değer içeriyor.

```
BOOL CEnrollDoc::RemoveStudent( CString strStudentID )
{
    // remove student from all the classes
    // the student is enrolled in

    if ( !m_dbStudentReg.BeginTrans( ) )
        return FALSE;

    CEnrollmentSet rsEnrollmentSet(&m_dbStudentReg);
    rsEnrollmentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsEnrollmentSet.Open(CRecordset::dynaset) )
        return FALSE;

    CStudentSet rsStudentSet(&m_dbStudentReg);
    rsStudentSet.m_strFilter = "StudentID = " + strStudentID;

    if ( !rsStudentSet.Open(CRecordset::dynaset) )
        return FALSE;

    TRY
    {
        while ( !rsEnrollmentSet.IsEOF( ) )
        {
            rsEnrollmentSet.Delete( );
            rsEnrollmentSet.MoveNext( );
        }

        // delete the student record
        rsStudentSet.Delete( );

        m_dbStudentReg.CommitTrans( );
    }

    CATCH_ALL(e)
    {
        m_dbStudentReg.Rollback( );
        return FALSE;
    }
    END_CATCH_ALL

    rsEnrollmentSet.Close( );
    rsStudentSet.Close( );

    return TRUE;

}
```

> [!NOTE]
> `BeginTrans`Çağırmadan `CommitTrans` veya bir hata olmadan yeniden çağırma `Rollback` .

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: Işlemlerin güncelleştirmeleri etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
