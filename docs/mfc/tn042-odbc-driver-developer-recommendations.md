---
title: 'TN042: ODBC sürücü Geliştirici önerileri'
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 462f8229d995add79f48f34b7f81257710b4a8b8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305417"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC sürücü Geliştirici önerileri

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, ODBC sürücüsü yazarların yönergeleri açıklar. Bu, genel gereksinimler ve varsayımlar MFC veritabanı sınıfları oluşturan ODBC işlevselliği ve çeşitli beklenen anlamsal Ayrıntılar açıklanmaktadır. Gereken üç desteklemek için sürücü işlevleri `CRecordset` açma modları (**forwardOnly**, **anlık görüntü** ve **dynaset**) açıklanmıştır.

## <a name="odbcs-cursor-library"></a>ODBC imleç kitaplığı

MFC veritabanı sınıfları, çoğu düzey 1 ODBC sürücüleri tarafından sağlanan işlevselliği karşıladığından, çoğu durumda kullanıcıya işlevselliği sunar. Neyse ki, ODBC imleç kitaplığı, kendisine bir sürücü ve veritabanı sınıfları arasında katman ve bu ek işlevselliğinin otomatik olarak sağlar.

Örneğin, çoğu 1.0 sürücüleri geriye dönük kaydırma desteklemez. İmleç Kitaplığı, algılayabilir ve önbelleğe sürücüsünden satırları ve FETCH_PREV çağrılarında üzerinde istenen şekilde sunmak `SQLExtendedFetch`.

Başka bir önemli imleç kitaplığı bağımlılığı konumlandırılmış güncelleştirmeler örneğidir. Çoğu 1.0 sürücüleri konumlandırılmış güncelleştirmeler de yoktur ancak imleç kitaplığı, bir hedef satırı geçerli önbelleğe alınmış veri değerlerini, veya bir önbelleğe alınan zaman damgası değeri göre veri kaynağında tanımlamak ve update ifadeleriyle oluşturur.

Sınıf kitaplığı hiçbir zaman birden çok satır kümelerini kullanır. Bu nedenle, birkaç `SQLSetPos` deyimleri 1 satır satır için her zaman uygulanır.

## <a name="cdatabases"></a>CDatabases

Her `CDatabase` tek bir ayırır **HDBC**. (Varsa `CDatabase`'s `ExecuteSQL` işlevi kullanılan bir **HSTMT** geçici olarak ayrılır.) Bunu birden çok `CDatabase`'s, birden çok gerekli **HDBC**s başına **HENV** desteklenmesi gerekir.

Veritabanı sınıfları imleç kitaplığı gerektirir. Bu yansıtılan bir `SQLSetConnections` çağrı **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** tarafından kullanılan `CDatabase::Open` veri kaynağına bağlantı kurmak için.

Sürücü desteklemelidir `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**, `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**.

İçin desteklenen işlemler için sırayla `CDatabase` ve onun bağımlı kayıt kümelerini `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` ve **SQL_CURSOR_ROLLBACK_BEHAVIOR** olmalıdır **SQL_CR_PRESERVE**. Aksi takdirde, işlem denetiminin gerçekleştirmeyi dener göz ardı edilir.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` desteklenmesi gerekir. "Y" döndürürse, veri kaynağı üzerinde hiçbir güncelleştirme işlemleri gerçekleştirilir.

Varsa `CDatabase` açıldığında salt okunur, okunur veri kaynağı ayarlama girişimi yalnızca oluşturulacak ile `SQLSetConnectOption SQL_ACCESS_MODE`, **SQL_MODE_READ_ONLY**.

Tanımlayıcıları Alıntısı gerektiriyorsa, bu bilgileri ile sürücüsünden döndürülmesi gereken bir `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` çağırın.

Hata ayıklama amacıyla, `SQLGetInfo SQL_DBMS_VER` ve **SQL_DBMS_NAME** sürücüsünden alınır.

`SQLSetStmtOption SQL_QUERY_TIMEOUT` ve **SQL_ASYNC_ENABLE** üzerinde çağrılabilir bir `CDatabase`'s **HDBC**.

`SQLError` tüm değişkenleri NULL ile çağrılabilir.

Elbette, `SQLAllocEnv`, `SQLAllocConnect`, `SQLDisconnect` ve `SQLFreeConnect` desteklenmesi gerekir.

## <a name="executesql"></a>ExecuteSQL

Ayırma ve serbest bırakma geçici yanı sıra **HSTMT**, `ExecuteSQL` çağrıları `SQLExecDirect`, `SQLFetch`, `SQLNumResultCol` ve `SQLMoreResults`. `SQLCancel` üzerinde çağrılabilir **HSTMT**.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` olarak adlandırılır.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, geri alma

`SQLSetConnectOption SQL_AUTOCOMMIT` ve `SQLTransact SQL_COMMIT`, **SQL_ROLLBACK** ve **SQL_AUTOCOMMIT** işlem talepleri yapılırsa çağrılır.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare`, `SQLExecute` (İçin `Open` ve `Requery`), `SQLExecDirect` (için güncelleştirme işlemleri) `SQLFreeStmt` desteklenmesi gerekir. `SQLNumResultCols` ve `SQLDescribeCol` çeşitli zamanlarda ayarlamak sonuçlarına çağırılacak olan.

`SQLSetParam` parametre verisi bağlama için yaygın olarak kullanılır ve **DATA_AT_EXEC** işlevselliği.

`SQLBindCol` kaydetmek için yaygın olarak kullanılan sütun veri depolama konumları ODBC ile çıktı.

İki `SQLGetData` çağrıları almak için kullanılan **SQL_LONG_VARCHAR** ve **SQL_LONG_VARBINARY** veri. İlk çağrı çağırarak toplam uzunluğu sütun değerinin bulmayı dener `SQLGetData` cbMaxValue 0, ancak geçerli pcbValue. PcbValue tutuyorsa **SQL_NO_TOTAL**, bir özel durum oluşturulur. Aksi takdirde, bir **HGLOBAL** tahsis edilir ve başka bir `SQLGetData` tüm sonuç almak için yapılan çağrı.

## <a name="updating"></a>Güncelleştirme

Kötümser kilitleme istenip istenmediğini `SQLGetInfo SQL_LOCK_TYPES` sorgulanır. Varsa **SQL_LCK_EXCLUSIVE** olduğundan desteklenmiyor, bir özel durum oluşturulur.

Güncelleştirmeye çalışırken bir `CRecordset` (**anlık görüntü** veya **dynaset**) ikinci bir neden olacak **HSTMT** ayrılacak. Desteklemeyen sürücüleri için ikinci **HSTMT**, imleç kitaplığı bu işlevselliği benzetimini yapacaksınız. Ne yazık ki bu bazen ilk geçerli sorgu zorlama gelebilir **HSTMT** ikinci işlenmeden önce tamamlanması için **HSTMT**kullanıcının isteği.

`SQLFreeStmt SQL_CLOSE` ve **SQL_RESET_PARAMS** ve `SQLGetCursorName` güncelleştirme işlemleri sırasında çağrılır.

Varsa **CLongBinarys** içinde **outputColumns**, ODBC **DATA_AT_EXEC** işlevselliği desteklenmelidir. Bu döndüren içerir **SQL_NEED_DATA** gelen `SQLExecDirect`, `SQLParamData` ve `SQLPutData`.

`SQLRowCount` Yalnızca 1 kaydı tarafından güncelleştirildiğini doğrulamak için yürütüldükten sonra çağrılır `SQLExecDirect`.

## <a name="forwardonly-cursors"></a>ForwardOnly imleçler

Yalnızca `SQLFetch` gereklidir `Move` operations. Unutmayın **forwardOnly** imleçler güncelleştirmeleri desteklemez.

## <a name="snapshot-cursors"></a>Anlık görüntü imleçler

Anlık görüntüsü işlevinin gerektirir `SQLExtendedFetch` destekler. Yukarıda belirtildiği gibi bir sürücü desteklemediği zaman ODBC imleç kitaplığı algılar `SQLExtendedFetch`ve gerekli destek sağlar.

`SQLGetInfo`, **Çağırın** desteklemelidir **SQL_SO_STATIC**.

## <a name="dynaset-cursors"></a>Dynaset imleçler

Bir dinamik açmak için gereken en düşük destek aşağıdadır:

`SQLGetInfo`, **SQL_ODBC_VER** döndürmelidir > "01".

`SQLGetInfo`, **Çağırın** desteklemelidir **SQL_SO_KEYSET_DRIVEN**.

`SQLGetInfo`, **SQL_ROW_UPDATES** "Y" döndürmelidir.

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** desteklemelidir **SQL_PS_POSITIONED_DELETE** ve **SQL_PS_POSITIONED_UPDATE**.

Kötümser kilitleme istenip istenmediğini Ayrıca, bir çağrı `SQLSetPos` IRow 1, FALSE fRefresh ve fLock **SQL_LCK_EXCLUSIVE** hale getirilir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
