---
title: 'İşlem: (ODBC) kayıt kümesinde işlem gerçekleştirme'
ms.date: 11/04/2016
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
ms.openlocfilehash: 9e06d61d3d86233e136b0b3fe78f149a6778649b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329835"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: (ODBC) kayıt kümesinde işlem gerçekleştirme

Bu konuda, bir kayıt kümesinde işlem gerçekleştirme açıklanmaktadır.

> [!NOTE]
>  Tek düzey işlemleri desteklenmez. işlemleri iç içe olamaz.

#### <a name="to-perform-a-transaction-in-a-recordset"></a>Bir kayıt kümesinde işlem gerçekleştirme

1. Çağrı `CDatabase` nesnenin `BeginTrans` üye işlevi.

1. Toplu satır getirme değil uyguladıysanız, çağrı `AddNew/Update`, `Edit/Update`, ve `Delete` nesnelerin bir veya daha fazla kayıt aynı veritabanında gerektiği birçok üye işlevleri. Daha fazla bilgi için [kayıt kümesi: Ekleme, güncelleştirme ve silme (ODBC) kayıtları](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Toplu satır getirme uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.

1. Son olarak, çağrı `CDatabase` nesnenin `CommitTrans` üye işlevi. Güncelleştirmelerden biri bir hata oluşursa ya değişiklikleri iptal etmek karar verirseniz, arama, `Rollback` üye işlevi.

Aşağıdaki örnek, bir öğrencinin kayıt Öğrenci, Öğrenci kayıtlı tüm sınıflardan kaldırarak bir okul kayıt veritabanından silmek için iki kayıt kümelerini kullanır. Çünkü `Delete` her iki kayıt kümelerinde çağrıları başarılı olmalıdır, bir işlem gereklidir. Örnek varsayar `m_dbStudentReg`, bir üye değişkeni türü `CDatabase` zaten bağlı veri kaynağı ve kayıt kümesi sınıfları `CEnrollmentSet` ve `CStudentSet`. `strStudentID` Değişken kullanıcıdan alınan bir değer içeriyor.

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
>  Çağırma `BeginTrans` yeniden çağırmadan `CommitTrans` veya `Rollback` bir hatadır.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem (ODBC)](../../data/odbc/transaction-odbc.md)<br/>
[İşlem: İşlemlerin Güncelleştirmeleri Etkileme Biçimi (ODBC)](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)