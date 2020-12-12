---
description: 'Hakkında daha fazla bilgi edinin: TN068: Microsoft Access 7 ODBC sürücüsü ile Işlem gerçekleştirme'
title: 'TN068: Microsoft Access 7 ODBC Sürücüsü ile İşlem Yapma'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: ebc98a0fd2bea78c0159daa9a53a11a292482257
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214552"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Microsoft Access 7 ODBC Sürücüsü ile İşlem Yapma

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, Microsoft ODBC Masaüstü sürücü paketi sürüm 3,0 ' ye eklenen MFC ODBC veritabanı sınıfları ve Microsoft Access 7,0 ODBC sürücüsü kullanılırken nasıl işlem gerçekleştirileceği açıklanmaktadır.

## <a name="overview"></a>Genel Bakış

Veritabanı uygulamanız işlem gerçekleştiriyorsa, `CDatabase::BeginTrans` uygulamanızda doğru sırada ve çağrısı yapmanız gerekir `CRecordset::Open` . Microsoft Access 7,0 sürücüsü Microsoft Jet veritabanı altyapısını kullanır ve Jet, uygulamanızın açık imleç içeren herhangi bir veritabanında bir işlem başlatmaya gerek duyuyor. MFC ODBC veritabanı sınıfları için açık bir imleç açık bir nesneye karşılık gelir `CRecordset` .

Çağrılmadan önce bir kayıt kümesi açarsanız `BeginTrans` , herhangi bir hata iletisi göremeyebilirsiniz. Bununla birlikte, uygulamanız çağrıldıktan sonra uygulamanızın yaptığı tüm kayıt kümeleri kalıcı hale gelir `CRecordset::Update` ve bu güncelleştirmeler çağırarak geri alınmaz `Rollback` . Bu sorundan kaçınmak için, önce öğesini çağırmanız `BeginTrans` ve sonra kayıt kümesini açmanız gerekir.

MFC, imleç yürütmesi ve geri alma davranışı için sürücü işlevselliğini denetler. Sınıfı `CDatabase` iki üye işlevi sağlar `GetCursorCommitBehavior` ve `GetCursorRollbackBehavior` Açık nesnenizin herhangi bir işlemin etkisini tespit etmek için `CRecordset` . Microsoft Access 7,0 ODBC sürücüsü için, `SQL_CB_CLOSE` erişim sürücüsü imleç korumasını desteklemediğinden bu üye işlevleri döndürülür. Bu nedenle, `CRecordset::Requery` aşağıdaki bir `CommitTrans` veya işlemini çağırmanız gerekir `Rollback` .

Bir kez daha sonra birden çok işlem gerçekleştirmeniz gerektiğinde, `Requery` ilk işlemden sonra çağrı gerçekleştiremez ve sonra bir sonraki işlemi başlatamazsınız. Jet 'in gereksinimini karşılamak için bir sonraki çağrıdan önce kayıt kümesini kapatmanız gerekir `BeginTrans` . Bu teknik notta, bu durumu işlemenin iki yöntemi açıklanmaktadır:

- Her veya işlemden sonra kayıt kümesi kapatılıyor `CommitTrans` `Rollback` .

- ODBC API işlevini kullanma `SQLFreeStmt` .

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Kayıt kümesini her bir CommitTrans veya geri alma işleminden sonra kapatma

Bir işlem başlatmadan önce, kayıt kümesi nesnesinin kapalı olduğundan emin olun. Çağrıldıktan sonra `BeginTrans` , kayıt kümesinin `Open` üye işlevini çağırın. Veya çağrıldıktan sonra kayıt kümesini hemen `CommitTrans` kapatın `Rollback` . Kayıt kümesini tekrar tekrar açan ve kapatan bir uygulamanın performansının yavaşlamasına neden olabileceğini unutmayın.

## <a name="using-sqlfreestmt"></a>SQLFreeStmt kullanma

`SQLFreeStmt`Bir işlemi sonlandırdıktan sonra imleci açıkça kapatmak IÇIN ODBC API işlevini de kullanabilirsiniz. Başka bir işlem başlatmak için, `BeginTrans` bunu çağırın `CRecordset::Requery` . Çağrılırken `SQLFreeStmt` , kayıt KÜMESININ hstmt öğesini ilk parametre olarak belirtmeniz ve ikinci parametre olarak *SQL_CLOSE* gerekir. Bu yöntem, her işlemin başlangıcında kayıt kümesini kapatıp açmaktan daha hızlıdır. Aşağıdaki kod, bu tekniğin nasıl uygulanacağını göstermektedir:

```cpp
CMyDatabase db;
db.Open("MYDATASOURCE");
CMyRecordset rs(&db);

// start transaction 1 and
// open the recordset
db.BeginTrans();
rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans(); // or Rollback()

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

Bu tekniği uygulamak için başka bir yöntem ise, `RequeryWithBeginTrans` ilk birini gerçekleştirdikten veya geri aldıktan sonra bir sonraki işlemi başlatmak üzere çağrılabilmeniz için yeni bir işlev yazmaktır. Böyle bir işlevi yazmak için aşağıdaki adımları uygulayın:

1. Kodunu `CRecordset::Requery( )` Yeni işleve kopyalayın.

2. Çağrısından hemen sonra aşağıdaki satırı ekleyin `SQLFreeStmt` :

   `m_pDatabase->BeginTrans( );`

Artık bu işlevi, her işlem çifti arasında çağırabilirsiniz:

```cpp
// start transaction 1 and
// open the recordset
db.BeginTrans();

rs.Open();

// manipulate data

// end transaction 1
db.CommitTrans();   // or Rollback()

// close the cursor, start new transaction,
// and get the result set
rs.RequeryWithBeginTrans();

// manipulate data

// end transaction 2
db.CommitTrans();   // or Rollback()
```

> [!NOTE]
> Kayıt kümesi üye değişkenlerini *m_strFilter* veya işlemler arasında *m_strSort* değiştirmeniz gerekiyorsa bu tekniği kullanmayın. Bu durumda, her bir veya işlemden sonra kayıt kümesini kapatmanız `CommitTrans` gerekir `Rollback` .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
