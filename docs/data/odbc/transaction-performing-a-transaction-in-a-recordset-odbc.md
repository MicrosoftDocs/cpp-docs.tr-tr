---
title: 'İşlem: kayıt kümesi (ODBC) bir işlem gerçekleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9fcc5c6aae86aea005aef50f9083aeb718f64b19
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340273"
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)
Bu konuda, bir kayıt kümesinde işlem gerçekleştirme açıklanmaktadır.  
  
> [!NOTE]
>  Tek düzey işlemleri desteklenmez. işlemleri iç içe olamaz.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Bir kayıt kümesinde işlem gerçekleştirme  
  
1.  Çağrı `CDatabase` nesnenin `BeginTrans` üye işlevi.  
  
2.  Toplu satır getirme değil uyguladıysanız, çağrı `AddNew/Update`, `Edit/Update`, ve `Delete` nesnelerin bir veya daha fazla kayıt aynı veritabanında gerektiği birçok üye işlevleri. Daha fazla bilgi için [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Toplu satır getirme uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.  
  
3.  Son olarak, çağrı `CDatabase` nesnenin `CommitTrans` üye işlevi. Güncelleştirmelerden biri bir hata oluşursa ya değişiklikleri iptal etmek karar verirseniz, arama, `Rollback` üye işlevi.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem (ODBC)](../../data/odbc/transaction-odbc.md)   
 [İşlem: İşlemlerin güncelleştirmeleri (ODBC) nasıl etkiler.](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)