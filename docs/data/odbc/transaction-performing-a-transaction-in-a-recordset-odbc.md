---
title: "İşlem: (ODBC) kayıt kümesinde işlem gerçekleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: transactions, updating recordsets
ms.assetid: cf1d6b48-7fb8-4903-84f7-a1822054534d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1451775374b94bbefb6396e7afeda2396df84ba4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="transaction-performing-a-transaction-in-a-recordset-odbc"></a>İşlem: Kayıt Kümesinde İşlem Gerçekleştirme (ODBC)
Bu konu kayıt kümesinde işlem gerçekleştirme açıklar.  
  
> [!NOTE]
>  Yalnızca bir düzey işlemler desteklenir; işlemleri iç içe yerleştirilemez.  
  
#### <a name="to-perform-a-transaction-in-a-recordset"></a>Bir kayıt kümesindeki bir işlem gerçekleştirmek için  
  
1.  Çağrı `CDatabase` nesnenin **BeginTrans** üye işlevi.  
  
2.  Toplu satır getirme değil uyguladıysanız, çağrı **AddNew/Update**, **Düzenle/güncelleştirme**, ve **silme** bir veya daha fazla kayıt aynı kümesi nesnesinin üye işlevleri Veritabanı gerektiği pek çok. Daha fazla bilgi için bkz: [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md). Toplu satır getirme uyguladıysanız, veri kaynağını güncelleştirmek için kendi işlevlerinizi yazmanız gerekir.  
  
3.  Son olarak, arama `CDatabase` nesnenin **CommitTrans** üye işlevi. Güncelleştirmeleri birinde bir hata oluşursa veya değişiklikleri iptal etmeye karar verirseniz, çağırın kendi **geri alma** üye işlevi.  
  
 Aşağıdaki örnekte iki kayıt kümeleri öğrencinin kayıt Öğrenci Öğrenci kayıtlı tüm sınıflardan kaldırarak bir okul kayıt veritabanından silmek için kullanır. Çünkü **silmek** her iki kayıt kümeleri çağrılarında başarılı olması gerekir, bir işlem gereklidir. Örnek varlığını varsayar `m_dbStudentReg`, üye değişkeni türü `CDatabase` zaten bağlı veri kaynağı ve kayıt kümesi sınıfları `CEnrollmentSet` ve `CStudentSet`. `strStudentID` Değişkeni kullanıcıdan alınan bir değer içeriyor.  
  
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
>  Çağırma **BeginTrans** yeniden çağırmadan **CommitTrans** veya **geri alma** bir hatadır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşlem (ODBC)](../../data/odbc/transaction-odbc.md)   
 [İşlem: İşlemlerin güncelleştirmeleri (ODBC) etkilemesi](../../data/odbc/transaction-how-transactions-affect-updates-odbc.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)