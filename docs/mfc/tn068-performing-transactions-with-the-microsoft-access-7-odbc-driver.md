---
title: 'TN068: Microsoft Access 7 ODBC sürücüsü ile işlem yapma'
ms.date: 06/28/2018
f1_keywords:
- vc.data.odbc
helpviewer_keywords:
- TN068 [MFC]
- transactions [MFC], calling BeginTrans
- transactions [MFC], Microsoft Access
ms.assetid: d3f8f5d9-b118-4194-be36-a1aefb630c45
ms.openlocfilehash: 3121587f85c4ea19cc92e39569008b597d24ea58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62363797"
---
# <a name="tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver"></a>TN068: Microsoft Access 7 ODBC sürücüsü ile işlem yapma

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, MFC ODBC veritabanı sınıfları ve Microsoft ODBC Masaüstü Sürücü paketi sürüm 3.0 Microsoft Access 7.0 ODBC sürücüsü kullanılırken işlemleri gerçekleştirmeyi açıklar.

## <a name="overview"></a>Genel Bakış

Veritabanı uygulamanızı işlemler gerçekleştirirse çağırmak dikkatli olmanız gerekir `CDatabase::BeginTrans` ve `CRecordset::Open` uygulamanızdaki doğru sırada. Microsoft Access 7.0 sürücü Microsoft Jet veritabanı motorunu kullanır ve uygulamanızı bir işlem açık bir imleç sahip herhangi bir veritabanı üzerinde başlamaz Jet gerektirir. MFC ODBC veritabanı sınıfları için açık bir imleç açık karşılık gelmektedir `CRecordset` nesne.

Bir kayıt kümesi çağırmadan önce açarsanız `BeginTrans`, herhangi bir hata iletisi görüntülenebilir. Ancak, herhangi bir kayıt çağırdıktan sonra kalıcı olur, uygulama yapar güncelleştirmeleri `CRecordset::Update`, ve güncelleştirmeleri geri çağırarak alınmaz `Rollback`. Bu sorunu önlemek için çağırmalıdır `BeginTrans` ilk kayıt kümesini açın.

MFC sürücü işlevleri için imleç kaydetme ve geri alma davranışını denetler. Sınıf `CDatabase` iki üye işlevini sağlar `GetCursorCommitBehavior` ve `GetCursorRollbackBehavior`, açık herhangi bir işlem etkisini belirlemek için `CRecordset` nesne. Microsoft Access 7.0 ODBC sürücüsü, bu üye işlevleri dönüş `SQL_CB_CLOSE` erişim sürücü imleç korunması desteklemediği için. Bu nedenle, çağırmalıdır `CRecordset::Requery` aşağıdaki bir `CommitTrans` veya `Rollback` işlemi.

Birden çok işlem birbiri ardına gerçekleştirmeniz gerektiğinde, çağıramazsınız `Requery` ilk işlem ve bir sonraki başlatın. Sonraki çağırmadan önce kayıt kapatmalısınız `BeginTrans` Jet'ın gereksinimi karşılamak için. Bu teknik Not, bu durum işleme için iki yöntem açıklar:

- Kayıt kümesi her birinden sonra kapanış `CommitTrans` veya `Rollback` işlemi.

- ODBC API işlevini kullanarak `SQLFreeStmt`.

## <a name="closing-the-recordset-after-each-committrans-or-rollback-operation"></a>Kayıt kümesi her CommitTrans ya da geri alma işlemi kapatma

Bir işlem başlatmadan önce kayıt kümesi nesnesi kapalı olduğundan emin olun. Arama sonra `BeginTrans`, kayıt kümesinin çağrı `Open` üye işlevi. Kayıt kümesi çağırdıktan hemen sonra kapatmak `CommitTrans` veya `Rollback`. Tekrar tekrar açma ve kapatma kayıt uygulamanın performansını yavaşlatabilir unutmayın.

## <a name="using-sqlfreestmt"></a>SQLFreeStmt kullanma

ODBC API işlevini de kullanabilirsiniz `SQLFreeStmt` açıkça İmleç bir işlem bitiş sonra kapatın. Başka bir işlem başlatmak için çağrı `BeginTrans` ardından `CRecordset::Requery`. Çağrılırken `SQLFreeStmt`, kayıt kümesinin HSTMT ilk parametre olarak belirtmeniz gerekir ve *SQL_CLOSE* ikinci parametre olarak. Bu yöntem kapatıp açarak her işlem başlangıcında kayıt daha hızlıdır. Aşağıdaki kod, bu teknik uygulama gösterilmektedir:

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

Bu teknik uygulamak için başka bir yolu, yeni bir işlev yazmaktır `RequeryWithBeginTrans`, hangi kaydetmeyi tamamladıktan sonraki işlemi başlatmak için çağırabileceğiniz ya da geri alma ilk öğe. Böyle bir işlevi yazmak için aşağıdaki adımları uygulayın:

1. Kodu Kopyala `CRecordset::Requery( )` yeni işlev.

2. Çağırdıktan hemen sonra aşağıdaki satırı ekleyin `SQLFreeStmt`:

   `m_pDatabase->BeginTrans( );`

Artık işlemlerin arasındaki bu işlevi çağırabilirsiniz:

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
> Kayıt kümesi üye değişkenleri değiştirmeniz gerekirse, bu tekniği kullanmayın *m_strFilter* veya *m_strSort* işlemleri arasında. Bu durumda, kayıt kümesinin her birinden sonra kapatmalısınız `CommitTrans` veya `Rollback` işlemi.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
