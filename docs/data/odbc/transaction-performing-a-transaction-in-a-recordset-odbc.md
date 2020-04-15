---
title: 'İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 45ae414c318376b2c4d787498e9a288a0037af83
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358091"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)

Bu konu, kayıt kümesinde bir işlemin nasıl gerçekleştirildirilebildiğini açıklar.

> [!NOTE]
> Yalnızca bir işlem düzeyi desteklenir; hareketleri iç içe geçemezsiniz.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Kayıt kümesinde bir hareket gerçekleştirmek için

1. Nesnenin `CDatabase` `BeginTrans` üye işlevini arayın.

1. Toplu satır alma uygulamadıysanız, aynı `AddNew/Update`veritabanının `Edit/Update` `Delete` bir veya daha fazla kayıt kümesi nesnesinin , ve üye işlevlerini gerektiği kadar çağırın. Daha fazla bilgi için kayıt [kümesi: Kayıt Ekleme, Güncelleme ve Silme Kayıtları (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)bölümüne bakın. Toplu satır alma uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.

1. Son olarak, `CDatabase` nesnenin `CommitTrans` üye işlevini arayın. Güncelleştirmelerden birinde bir hata oluşursa veya değişiklikleri iptal etmeye `Rollback` karar verirseniz, üye işlevini arayın.

Aşağıdaki örnekte, öğrencinin kaydını okul kayıt veritabanından silmek için iki kayıt kümesi kullanır ve öğrencinin kayıtlı olduğu tüm derslerden uzaklaştırılır. Her `Delete` iki kayıt kümesindeki çağrıların başarılı olması gerektiğinden, bir hareket gereklidir. Örnek, veri kaynağına `m_dbStudentReg`zaten bağlı olan `CDatabase` bir üye değişkenin ve kayıt `CEnrollmentSet` kümesi `CStudentSet`sınıflarının ve . `strStudentID` Değişken, kullanıcıdan elde edilen bir değer içerir.

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
> Aramadan `BeginTrans` veya `CommitTrans` `Rollback` bir hata olmadan yeniden arama.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: İşlemlerin Güncelleştirmeleri Etkilemesi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
