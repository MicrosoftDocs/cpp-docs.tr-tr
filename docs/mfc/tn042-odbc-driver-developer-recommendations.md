---
title: 'TN042: ODBC Sürücü Geliştirici Önerileri'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 67f7a86a247b60be66dabb0a89f04d39ce76222b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372133"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC Sürücü Geliştirici Önerileri

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, ODBC sürücü yazarları için yönergeleri açıklar. MFC Veritabanı sınıflarının yaptığı ODBC işlevinin genel gereksinimlerini ve varsayımlarını ve beklenen çeşitli anlamsal ayrıntıları özetler. Üç `CRecordset` Açık modunu desteklemek için gerekli sürücü işlevi **(forwardOnly**, **anlık görüntü** ve **dynaset)** tanımlanır.

## <a name="odbcs-cursor-library"></a>ODBC'nin İmleç Kütüphanesi

MFC Veritabanı sınıfları, çoğu durumda çoğu düzey 1 ODBC sürücüsü tarafından sağlanan işlevselliği aşan işlevselliği kullanıcıya sunar. Neyse ki, ODBC'nin İmleç Kitaplığı veritabanı sınıfları ve sürücü arasında kendini katman ve otomatik olarak bu ek işlevselliğin çok sağlayacaktır.

Örneğin, çoğu 1.0 sürücüsü geriye kaydırmayı desteklemez. İmleç Kitaplığı bunu algılayabilir ve sürücüden satırları önbelleğe alabilir ve FETCH_PREV `SQLExtendedFetch`aramalarda istendiği gibi sunar.

İmleç kitaplığı bağımlılığının bir diğer önemli örneği de konumlandırılmış güncelleştirmelerdir. Çoğu 1.0 sürücüsünün de konumlandırılmış güncelleştirmeleri yoktur, ancak imleç kitaplığı, geçerli önbelleğe alınmış veri değerlerini veya önbelleğe alınmış zaman damgası değerini temel alan veri kaynağında bir hedef satırı tanımlayan güncelleştirme deyimleri oluşturur.

Sınıf kitaplığı hiçbir zaman birden çok satır kümesini kullanmaz. Bu nedenle, `SQLSetPos` birkaç ifadeler her zaman satır kümesinin satır 1 uygulanır.

## <a name="cdatabases"></a>CVeritabanları

Her `CDatabase` biri tek bir **HDBC**ayırır. `CDatabase`('ın `ExecuteSQL` işlevi kullanılırsa, geçici olarak bir **HSTMT** ayrılır.) Bu nedenle, birden fazla `CDatabase`'s gerekiyorsa, **HENV** başına birden fazla **HDBC**s desteklenmelidir.

Veritabanı sınıfları imleç kitaplığını gerektirir. Bu bir `SQLSetConnections` çağrı **SQL_ODBC_CURSORS**yansıtılır , **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** veri `CDatabase::Open` kaynağına bağlantı kurmak için kullanılır.

Sürücü **SQL_OAC_LEVEL1** `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >= destek `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >= gerekir , **SQL_OSC_MINIMUM**.

Hareketlerin `CDatabase` ve bağımlı kayıt kümeleri için desteklenebilmesi için `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` **ve SQL_CURSOR_ROLLBACK_BEHAVIOR** **SQL_CR_PRESERVE.** Aksi takdirde, işlem denetimi gerçekleştirme girişimleri yoksayılır.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY`desteklenmelidir. "Y" döndürürse, veri kaynağında güncelleştirme işlemi yapılmaz.

ReadOnly `CDatabase` açılırsa, yalnızca okunan veri kaynağını ayarlama girişimi `SQLSetConnectOption SQL_ACCESS_MODE`, **SQL_MODE_READ_ONLY**.

Tanımlayıcılar teklif alınmasını gerektiriyorsa, bu bilgiler sürücüden bir `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` çağrıyla birlikte döndürülmelidir.

Hata ayıklama amacıyla `SQLGetInfo SQL_DBMS_VER` ve **SQL_DBMS_NAME** sürücüden alınır.

`SQLSetStmtOption SQL_QUERY_TIMEOUT`ve **SQL_ASYNC_ENABLE** bir `CDatabase`'s **HDBC**çağrılabilir.

`SQLError`null bağımsız değişkenleri veya tümü ile çağrılabilir.

Tabii `SQLAllocEnv`ki, `SQLAllocConnect` `SQLDisconnect` , `SQLFreeConnect` , ve desteklenmelidir.

## <a name="executesql"></a>Executesql

Geçici bir **HSTMT**ayırma ve serbest `ExecuteSQL` ek `SQLExecDirect` `SQLFetch`olarak, aramalar , `SQLNumResultCol` , ve `SQLMoreResults`. `SQLCancel`**HSTMT'de**çağrılabilir.

## <a name="getdatabasename"></a>Veritabanı Adı Alma

`SQLGetInfo SQL_DATABASE_NAME`çağrılacaktır.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, Geri Alma

`SQLSetConnectOption SQL_AUTOCOMMIT`ve `SQLTransact SQL_COMMIT`, **SQL_ROLLBACK** ve **SQL_AUTOCOMMIT** hareket istekleri yapılırsa çağrılacaktır.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare` `SQLExecute` (For `Open` `Requery`and `SQLExecDirect` ), (güncelleştirme `SQLFreeStmt` işlemleri için), desteklenmelidir. `SQLNumResultCols`ve `SQLDescribeCol` çeşitli zamanlarda belirlenen sonuçlar aranacaktır.

`SQLSetParam`parametre verilerini bağlamak ve işlevselliği **DATA_AT_EXEC** için yaygın olarak kullanılır.

`SQLBindCol`çıktı Sütun veri depolama konumlarını ODBC ile kaydetmek için yaygın olarak kullanılır.

SQL_LONG_VARCHAR `SQLGetData` almak ve **SQL_LONG_VARCHAR** verileri **SQL_LONG_VARBINARY** için iki arama kullanılır. İlk arama, 0 cbMaxValue ile arayarak `SQLGetData` sütun değerinin toplam uzunluğunu bulmaya çalışır, ancak geçerli bir pcbValue ile. pcbValue **SQL_NO_TOTAL**tutarsa, bir özel durum atılır. Aksi takdirde, bir **HGLOBAL** ayrılır `SQLGetData` ve tüm sonucu almak için başka bir arama yapılır.

## <a name="updating"></a>Güncelleştirme

Kötümser kilitleme istenirse, `SQLGetInfo SQL_LOCK_TYPES` sorgulanır. **SQL_LCK_EXCLUSIVE** desteklenmezse, bir özel durum atılır.

Bir `CRecordset` **(anlık görüntü** veya **dynaset)** güncelleştirme girişimleri ikinci bir **HSTMT** tahsis edilmesine neden olur. İkinci **HSTMT'yi**desteklemeyen sürücüler için imleç kitaplığı bu işlevselliği simüle eder. Ne yazık ki, bu bazen ikinci **HSTMT**'in isteği işlemeden önce tamamlanması için ilk **HSTMT** geçerli sorgu zorlamak anlamına gelebilir.

`SQLFreeStmt SQL_CLOSE`ve **SQL_RESET_PARAMS** SQL_RESET_PARAMS `SQLGetCursorName` ve güncelleştirme işlemleri sırasında çağrılacaktır.

Çıktılarda **CLongBinarys** varsa **Sütunlar,** ODBC'nin **DATA_AT_EXEC** işlevselliği desteklenmelidir. Bu, **geri** dönen `SQLExecDirect` `SQLParamData` SQL_NEED_DATA `SQLPutData`ve .

`SQLRowCount`yalnızca 1 kaydın . `SQLExecDirect`

## <a name="forwardonly-cursors"></a>ForwardOnly Imleçler

Yalnızca `SQLFetch` `Move` işlemler için gereklidir. **İleriyalnızca** imleçlerin güncelleştirmeleri desteklemediğini unutmayın.

## <a name="snapshot-cursors"></a>Anlık Görüntü İmleçleri

Anlık görüntü `SQLExtendedFetch` işlevi destek gerektirir. Yukarıda belirtildiği gibi, ODBC imleç kitaplığı, bir `SQLExtendedFetch`sürücünün desteklemediği ve gerekli desteği kendisinin sağladığı nı algılar.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** **SQL_SO_STATIC**desteklemelidir.

## <a name="dynaset-cursors"></a>Dynaset İmlerler

Aşağıda bir dinamit açmak için gereken minimum destek:

`SQLGetInfo`, **SQL_ODBC_VER** "01" > dönmelidir.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** **SQL_SO_KEYSET_DRIVEN**desteklemelidir.

`SQLGetInfo`, **SQL_ROW_UPDATES** "Y"yi iade etmelidir.

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** **SQL_PS_POSITIONED_DELETE** ve **SQL_PS_POSITIONED_UPDATE**desteklemelidir.

Buna ek olarak, kötümser kilitleme istenirse, irow 1, fRefresh FALSE ve fLock `SQLSetPos` **SQL_LCK_EXCLUSIVE** ile bir çağrı yapılacaktır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
