---
title: 'İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 94177a27a1f99a8c9c37b7fce3f697fd0088b7c6
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80212595"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)

Bu konu, bir kayıt kümesinde bir işlemin nasıl gerçekleştirileceğini açıklamaktadır.

> [!NOTE]
>  Yalnızca bir düzey işlem desteklenir; işlem iç içe geçirilemez.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Bir kayıt kümesinde işlem gerçekleştirmek için

1. `CDatabase` nesnesinin `BeginTrans` üye işlevini çağırın.

1. Toplu satır getirmeyi uygulamadıysanız, aynı veritabanının bir veya daha fazla kayıt kümesi nesnesinin `AddNew/Update`, `Edit/Update`ve `Delete` üye işlevlerini gerektiği kadar çağırın. Daha fazla bilgi için bkz. [kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Toplu satır getirmeyi uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.

1. Son olarak, `CDatabase` nesnesinin `CommitTrans` üye işlevini çağırın. Güncelleştirmelerden birinde bir hata oluşursa veya değişiklikleri iptal etmeyi seçerseniz, `Rollback` üye işlevini çağırın.

Aşağıdaki örnek iki kayıt kümesi kullanarak bir okulın kayıt veritabanından bir öğrencinin kaydını siler ve öğrencinin kayıtlı olduğu tüm sınıflardan bir öğrenci 'yi kaldırır. Her iki kayıt kümesinde `Delete` çağrısı başarılı olması gerektiğinden, bir işlem gereklidir. Örnek, `m_dbStudentReg`varlığını, `CDatabase` türünde bir üye değişkenini zaten veri kaynağına bağlandığını ve kayıt kümesi sınıflarını `CEnrollmentSet` ve `CStudentSet`olduğunu varsayar. `strStudentID` değişkeni kullanıcıdan alınan bir değer içeriyor.

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
>  `CommitTrans` veya `Rollback` çağrılmadan `BeginTrans` yeniden çağrılması bir hatadır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
