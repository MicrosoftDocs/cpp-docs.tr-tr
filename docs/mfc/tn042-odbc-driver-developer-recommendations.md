---
description: 'Hakkında daha fazla bilgi edinin: TN042: ODBC sürücü geliştirici önerileri'
title: 'TN042: ODBC Sürücü Geliştirici Önerileri'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 896c99ffeba98f1ea38771676475c85abf13d983
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215306"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC Sürücü Geliştirici Önerileri

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta ODBC sürücü yazarları için yönergeler açıklanmaktadır. MFC veritabanı sınıflarının yaptığı ODBC işlevselliğinin genel gereksinimlerini ve varsayımlarını ve beklenen çeşitli anlam ayrıntılarını özetler. Üç `CRecordset` Açık modu (**ForwardOnly**, **anlık görüntü** ve **Dynaset**) desteklemeye yönelik gerekli sürücü işlevselliği açıklanır.

## <a name="odbcs-cursor-library"></a>ODBC Imleç kitaplığı

MFC veritabanı sınıfları, kullanıcının birçok durumda en fazla düzey 1 ODBC sürücüsü tarafından sunulan işlevselliği geçtiği işlevselliği sunar. Neyse ki, ODBC 'nin Imleç kitaplığı kendisini veritabanı sınıfları ve sürücü arasında katman oluşturacak ve bu ek işlevlerin çoğunu otomatik olarak sağlayacaktır.

Örneğin, 1,0 sürücü, geriye doğru kaydırmayı desteklemez. Imleç kitaplığı bunu algılayabilir ve içindeki satırları önbellekte önbelleğe alır ve içindeki FETCH_PREV çağrılarında istenen şekilde sunabilir `SQLExtendedFetch` .

İmleç kitaplığı bağımlılığını diğer önemli bir örneği de güncelleştirmeler konumlandırılır. Çoğu 1,0 sürücü aynı zamanda konumlandırılmış güncelleştirmeler içermez, ancak imleç kitaplığı, geçerli önbelleğe alınmış veri değerlerine veya önbelleğe alınmış bir zaman damgası değerine göre veri kaynağındaki bir hedef satırı tanımlayan Update deyimlerini oluşturur.

Sınıf kitaplığı hiçbir şekilde birden çok satır kümesi kullanmaz. Bu nedenle, birkaç `SQLSetPos` deyim her zaman satır kümesinin satır 1 ' e uygulanır.

## <a name="cdatabases"></a>CDatabases

Her biri `CDatabase` tek bir **HDBC** ayırır. ( `CDatabase` `ExecuteSQL` İşlevi kullanılıyorsa, bir **hstmt** geçici olarak ayrılır.) Bu nedenle, birden çok `CDatabase` gerekliyse, **HENV** başına birden fazla **HDBC** desteklenmelidir.

Veritabanı sınıfları imleç kitaplığı gerektirir. Bu `SQLSetConnections` , **SQL_CUR_USE_ODBC** bir çağrı **SQL_ODBC_CURSORS** yansıtılır.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** tarafından `CDatabase::Open` veri kaynağıyla bağlantı kurmak için kullanılır.

Sürücü `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  , SQL_OSC_MINIMUM **SQL_OAC_LEVEL1** desteklemelidir `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  .

İşlemlerin `CDatabase` ve bağımlı kayıt kümelerinde desteklenecek `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` ve **SQL_CURSOR_ROLLBACK_BEHAVIOR** **sql_cr_preserve** sahip olmalıdır. Aksi takdirde, işlem denetimi gerçekleştirmeye yönelik girişimler göz ardı edilir.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` desteklenmelidir. "Y" döndürürse, veri kaynağında hiçbir güncelleştirme işlemi gerçekleştirilmez.

Salt okunur `CDatabase` açılırsa, veri kaynağını salt okunur olarak ayarlama girişimi `SQLSetConnectOption SQL_ACCESS_MODE` , **SQL_MODE_READ_ONLY** ile yapılır.

Tanımlayıcılar tırnak içine alma gerektiriyorsa, bu bilgiler sürücüden bir çağrı ile döndürülmelidir `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` .

Hata ayıklama amacıyla `SQLGetInfo SQL_DBMS_VER` ve **SQL_DBMS_NAME** sürücüden alınır.

`SQLSetStmtOption SQL_QUERY_TIMEOUT`**SQL_ASYNC_ENABLE** , bir `CDatabase` **HDBC** üzerinde çağrılabilir.

`SQLError` herhangi bir veya tüm bağımsız değişkenlerle çağrılabilir.

Kuşkusuz,, `SQLAllocEnv` ve ' nin `SQLAllocConnect` `SQLDisconnect` `SQLFreeConnect` desteklenmesi gerekir.

## <a name="executesql"></a>ExecuteSql 'den

Geçici bir **hstmt**,, ve çağrısı,, ve boşaltma özelliklerine ek olarak `ExecuteSQL` `SQLExecDirect` `SQLFetch` `SQLNumResultCol` `SQLMoreResults` . `SQLCancel`**hstmt** üzerinde çağrılabilir.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` çağrılacaktır.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, geri alma

`SQLSetConnectOption SQL_AUTOCOMMIT``SQLTransact SQL_COMMIT` **SQL_ROLLBACK** ve **SQL_AUTOCOMMIT** , işlem istekleri yapılırsa çağrılır.

## <a name="crecordsets"></a>Ckayıt kümeleri

`SQLAllocStmt`, `SQLPrepare` , `SQLExecute` ( `Open` Ve için `Requery` ), `SQLExecDirect` (güncelleştirme işlemleri için), `SQLFreeStmt` desteklenmelidir. `SQLNumResultCols` ve `SQLDescribeCol` çeşitli zamanlarda sonuçlar kümesi üzerinde çağrılacaktır.

`SQLSetParam` , parametre verilerini ve **data_at_exec** işlevselliği bağlamak için kapsamlı olarak kullanılır.

`SQLBindCol` , çıkış sütunu veri depolama konumlarını ODBC ile kaydetmek için kapsamlı olarak kullanılır.

`SQLGetData` **SQL_LONG_VARCHAR** ve **SQL_LONG_VARBINARY** verileri almak için iki çağrı kullanılır. İlk çağrı, `SQLGetData` cbMaxValue değeri 0 ve geçerli bir pcbValue ile çağırarak sütun değerinin toplam uzunluğunu bulmaya çalışır. PcbValue **SQL_NO_TOTAL** tutuyorsa, bir özel durum oluşturulur. Aksi takdirde, bir **HGLOBAL** değer ayrılır ve `SQLGetData` sonucun tamamını almak için başka bir çağrı yapılır.

## <a name="updating"></a>Güncelleştirme

Kötümser kilitleme isteniyorsa, `SQLGetInfo SQL_LOCK_TYPES` sorgulanacaktır. **SQL_LCK_EXCLUSIVE** desteklenmiyorsa, bir özel durum oluşturulur.

Bir `CRecordset` (**anlık görüntü** veya **Dynaset**) güncelleştirme denemeleri ikinci bir **hstmt** ayrılmasına neden olur. İkinci **hstmt**'yi desteklemeyen sürücüler için imleç kitaplığı bu işlevin benzetimini yapar. Ne yazık ki, bu durum bazen ikinci **hstmt**'nin isteğini işlemeden önce ilk **hstmt** 'deki geçerli sorguyu tamamlamaya zorlamayabilir.

`SQLFreeStmt SQL_CLOSE` ve **sql_reset_params** ve `SQLGetCursorName` güncelleştirme işlemleri sırasında çağrılacaktır.

**OutputColumns**'Ta **Clongbinarys** varsa, ODBC 'nin **data_at_exec** işlevselliği desteklenmelidir. Bu, ve ' den **sql_need_data** döndürmeyi içerir `SQLExecDirect` `SQLParamData` `SQLPutData` .

`SQLRowCount` , tarafından yalnızca 1 kaydın güncelleştirildiğinden emin olmak için yürütüldükten sonra çağrılır `SQLExecDirect` .

## <a name="forwardonly-cursors"></a>ForwardOnly Imleçleri

Yalnızca `SQLFetch` işlemler için gereklidir `Move` . **ForwardOnly** imleçlerinin güncelleştirmeleri desteklemediğini unutmayın.

## <a name="snapshot-cursors"></a>Anlık görüntü Imleçleri

Anlık görüntü işlevselliği için `SQLExtendedFetch` destek gerekir. Yukarıda belirtildiği gibi, ODBC imleç kitaplığı, bir sürücünün ne zaman desteklemediği tespit eder `SQLExtendedFetch` ve gerekli desteği sağlar.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** **SQL_SO_STATIC** desteklemelidir.

## <a name="dynaset-cursors"></a>Değişken küme Imleçleri

Bir Dynaset açmak için gereken en düşük destek aşağıda verilmiştir:

`SQLGetInfo`**SQL_ODBC_VER** "01" > döndürmelidir.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** **SQL_SO_KEYSET_DRIVEN** desteklemelidir.

`SQLGetInfo`**SQL_ROW_UPDATES** , "Y" döndürmelidir.

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** **SQL_PS_POSITIONED_DELETE** ve **SQL_PS_POSITIONED_UPDATE** desteklemelidir.

Ayrıca, Kötümser kilitleme isteniyorsa, `SQLSetPos` IRow 1, fRefresh false ve fLock **SQL_LCK_EXCLUSIVE** ile yapılan bir çağrı yapılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
