---
title: 'TN068: Microsoft Access 7 ODBC sürücüsü ile işlem yapma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.data.odbc
dev_langs:
- C++
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 63cce7532d93b1bd44b6a44c526310bd894d5e07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384823"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Microsoft Access 7 ODBC Sürücüsü ile İşlem Yapma
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not Microsoft ODBC Masaüstü Sürücü paketi sürüm 3.0 dahil Microsoft Access 7.0 ODBC sürücüsü MFC ODBC veritabanı sınıflarını kullanırken işlemleri gerçekleştirmeyi açıklar.  
  
## <a name="overview"></a>Genel Bakış  
 Veritabanı uygulamanızı işlemleri gerçekleştirirse, çağırmak dikkatli olmalısınız `CDatabase::BeginTrans` ve `CRecordset::Open` uygulamanızda doğru sırada. Microsoft Access 7.0 sürücü Microsoft Jet veritabanı altyapısı kullanır ve uygulamanızın açık bir imleç sahip herhangi bir veritabanı üzerinde bir işlemi başlamaz Jet gerektirir. MFC ODBC veritabanı sınıfları için açık bir imleç açık karşılık gelir `CRecordset` nesnesi.  
  
 Kayıt kümesi çağırmadan önce açarsanız **BeginTrans**, herhangi bir hata iletisi görüntülenebilir. Ancak, herhangi bir kayıt çağrıldıktan sonra kalıcı olur, uygulama yapar güncelleştirmeleri `CRecordset::Update`, ve güncelleştirmeleri geri çağırarak alınacak değil **geri alma**. Bu sorunu önlemek için çağırmalısınız **BeginTrans** ilk ve kayıt kümesi'ni açın.  
  
 MFC sürücü işlevselliği için imleç kaydetme ve geri alma davranışını denetler. Sınıf `CDatabase` iki üye işlevleri sağlar `GetCursorCommitBehavior` ve `GetCursorRollbackBehavior`, açık herhangi bir işlem etkisini belirlemek için `CRecordset` nesnesi. Microsoft Access 7.0 ODBC sürücüsü için bu üye işlevleri dönmek `SQL_CB_CLOSE` erişim sürücü imleç korunması desteklemediğinden. Bu nedenle, çağırmalısınız `CRecordset::Requery` aşağıdaki bir **CommitTrans** veya **geri alma** işlemi.  
  
 Birden çok işlem birbiri ardından gerçekleştirmeniz gerektiğinde çağıramazsınız **Requery** ilk işlem ve bir sonraki başlatın. Kayıt kümesi sonraki çağırmadan önce kapatmalısınız **BeginTrans** Jet'ın gereksinimi karşılamak için. Bu teknik Not Bu durum işleme için iki yöntem açıklanmaktadır:  
  
-   Kayıt kümesi her komuttan sonra kapatma **CommitTrans** veya **geri alma** işlemi.  
  
-   ODBC API işlevini kullanarak **SQLFreeStmt**.  
  
## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Kayıt kümesi her CommitTrans veya geri alma işlemi sonra kapatma  
 Bir işlem başlatmadan önce kayıt kümesi nesnesi kapalı olduğundan emin olun. Çağırdıktan sonra **BeginTrans**, kayıt kümesinin çağrısı **açık** üye işlevi. Kayıt kümesi hemen çağrıldıktan sonra kapatın **CommitTrans** veya **geri alma**. Art arda açma ve kayıt kapatma uygulamanın performansını yavaşlatabilir unutmayın.  
  
## <a name="using-sqlfreestmt"></a>SQLFreeStmt kullanma  
 ODBC API işlevini de kullanabilirsiniz **SQLFreeStmt** açıkça imleci bir işlem bitiş sonra kapatın. Başka bir işlem başlatmaya çağrısı **BeginTrans** arkasından `CRecordset::Requery`. Çağrılırken **SQLFreeStmt**, kayıt kümesinin HSTMT ilk parametre olarak belirtmeniz gerekir ve **SQL_CLOSE** ikinci parametre olarak. Bu yöntem kapatmak ve her işlem başlangıcında kayıt kümesi açmak daha hızlıdır. Aşağıdaki kod, bu teknik uygulamak gösterilmiştir:  
  
```  
CMyDatabase db;  
db.Open("MYDATASOURCE");

CMyRecordset rs(&db);

 
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor  
::SQLFreeStmt(rs.m_hstmt, SQL_CLOSE);

 
// start transaction 2  
db.BeginTrans();

 
// now get the result set  
rs.Requery();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();

 
rs.Close();

db.Close();
```  
  
 Bu teknik uygulamak için başka bir yolu, yeni bir işlev yazmaktır **RequeryWithBeginTrans**, daha sonraki işlem yürüttükten sonra başlatmak için çağırabilir veya geri alma ilk. Bu tür bir işlevi yazmak için aşağıdaki adımları uygulayın:  
  
1.  Kodu Kopyala **CRecordset::Requery ()** yeni işlev.  
  
2.  Çağırdıktan hemen sonra aşağıdaki satırı ekleyin **SQLFreeStmt**:  
  
 `m_pDatabase->BeginTrans( );`  
  
 Şimdi bu işlevi işlemleri çiftleri arasındaki çağırabilirsiniz:  
  
```  
// start transaction 1 and   
// open the recordset  
db.BeginTrans();

rs.Open();

 
// manipulate data  
 
// end transaction 1  
db.CommitTrans();
*// or Rollback()  
 
// close the cursor,
    start new transaction,  
// and get the result set  
rs.RequeryWithBeginTrans();

 
// manipulate data  
 
// end transaction 2  
db.CommitTrans();
*// or Rollback()  
```  
  
> [!NOTE]
>  Kayıt kümesi üye değişkenleri değiştirmeniz gerekirse, bu teknik kullanmayın **m_strFilter** veya `m_strSort` işlemleri arasında. Bu durumda, kayıt kümesinin her komuttan sonra kapatmalısınız **CommitTrans** veya **geri alma** işlemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

