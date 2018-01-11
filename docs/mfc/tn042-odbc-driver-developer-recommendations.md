---
title: "TN042: ODBC sürücü Geliştirici önerileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.odbc
dev_langs: C++
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad6361266ebf2f09b8f34d150de835b25c55720b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042: ODBC Sürücü Geliştirici Önerileri
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not ODBC sürücüsü yazarların yönergelerini açıklar. Genel gereksinimler ve MFC veritabanı sınıfları olun ODBC işlevselliği ve çeşitli beklenen anlamsal ayrıntıları özelliklerinin özetlenmektedir. Gereken üç desteklemek için sürücü işlevleri `CRecordset` açmak modları (**forwardOnly**, **anlık görüntü** ve **dynaset**) açıklanmaktadır.  
  
## <a name="odbcs-cursor-library"></a>ODBC imleç kitaplığı  
 MFC veritabanı sınıfları, çoğu durumda çoğu düzey 1 ODBC sürücüleri tarafından sağlanan işlevleri karşıladığından kullanıcı işlevselliği sunar. Neyse ki, ODBC imleç kitaplığı kendisini veritabanı sınıfları ve sürücü arasında katman ve otomatik olarak bu ek işlev çoğunu sağlar.  
  
 Örneğin, çoğu 1.0 sürücüleri geri kaydırma desteklemez. İmleç kitaplığı bunu algılayabilir ve önbellek sürücüsü satırları ve FETCH_PREV çağrılarında istendiği gibi sunmak **SQLExtendedFetch**.  
  
 Başka bir önemli imleç kitaplığı bağımlılığı konumlandırılmış güncelleştirmeler örnektir. Çoğu 1.0 sürücüleri de konumlandırılmış güncelleştirmeler yok ancak imleç kitaplığı geçerli önbelleğe alınmış veri değerlerini veya önbelleğe alınmış zaman damgası değeri göre veri kaynağında bir hedef satır tanımlamak güncelleştirme deyimleri oluşturur.  
  
 Sınıf kitaplığı hiçbir zaman birden çok satır kümeleri kullanır. Bu nedenle, birkaç **SQLSetPos** deyimleri satır kümesinin 1 satır için her zaman uygulanır.  
  
## <a name="cdatabases"></a>CDatabases  
 Her `CDatabase` tek bir ayırır **HDBC**. (Varsa `CDatabase`'s `ExecuteSQL` işlevi kullanılır, bir **HSTMT** geçici olarak ayrılır.) Birden çok bunu `CDatabase`ait birden çok gerekli, **HDBC**s başına **HENV** desteklenmesi gerekir.  
  
 Veritabanı sınıfları imleç kitaplığı gerektirir. Bu yansıtılmıştır bir **SQLSetConnections** çağrısı **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.  
  
 **SQLDriverConnect**, **SQL_DRIVER_COMPLETE** tarafından kullanılan `CDatabase::Open` veri kaynağına bağlantı kurmak için.  
  
 Sürücü desteklemelidir **SQLGetInfo SQL_ODBC_API_CONFORMANCE** >= **SQL_OAC_LEVEL1**, **SQLGetInfo SQL_ODBC_SQL_CONFORMANCE**  >=  **SQL_OSC_MINIMUM**.  
  
 İçin desteklenen işlemler için sırayla `CDatabase` ve onun bağımlı kayıt kümelerini **SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR** ve **SQL_CURSOR_ROLLBACK_BEHAVIOR** olmalıdır**SQL_CR_PRESERVE**. Aksi takdirde işlem denetimi gerçekleştirmek için girişimleri yoksayılacak.  
  
 **SQLGetInfo SQL_DATA_SOURCE_READ_ONLY** desteklenmesi gerekir. "Y" döndürürse, hiç güncelleştirme işlemlerini veri kaynağı üzerinde gerçekleştirilir.  
  
 Varsa `CDatabase` açıldığında salt okunur, okuma veri kaynağını ayarlama girişimi yalnızca oluşturulacak ile **SQLSetConnectOption SQL_ACCESS_MODE**, **SQL_MODE_READ_ONLY**.  
  
 Tanımlayıcıları tırnak içine almak gerektiriyorsa, bu bilgileri ile sürücüsünden döndürülmesi gereken bir **SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR** çağırın.  
  
 Hata ayıklama amacıyla, **SQLGetInfo SQL_DBMS_VER** ve **SQL_DBMS_NAME** sürücüsünden alınır.  
  
 **SQLSetStmtOption SQL_QUERY_TIMEOUT** ve **SQL_ASYNC_ENABLE** üzerinde çağrılabilir bir `CDatabase`'s **HDBC**.  
  
 **SQLError** tüm bağımsız değişkenler NULL çağrılabilir.  
  
 Elbette, **SQLAllocEnv**, **SQLAllocConnect**, **SQLDisconnect** ve **SQLFreeConnect** desteklenmesi gerekir.  
  
## <a name="executesql"></a>ExecuteSQL  
 Ayırma ve geçici bir boşaltma yanı sıra **HSTMT**, `ExecuteSQL` çağrıları **SQLExecDirect**, **SQLFetch**, **SQLNumResultCol**ve `SQLMoreResults`. **SQLCancel** üzerinde çağrılabilir **HSTMT**.  
  
## <a name="getdatabasename"></a>GetDatabaseName  
 **SQLGetInfo SQL_DATABASE_NAME** çağrılır.  
  
## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, geri alma  
 **SQLSetConnectOption SQL_AUTOCOMMIT** ve **SQLTransact SQL_COMMIT**, **SQL_ROLLBACK** ve **SQL_AUTOCOMMIT** olursa çağrılacak işlem yapılan istekleri.  
  
## <a name="crecordsets"></a>CRecordsets  
 **SQLAllocStmt**, **SQLPrepare**, **SQLExecute** (için **açık** ve **Requery**), **SQLExecDirect**  (için güncelleştirme işlemleri için) **SQLFreeStmt** desteklenmesi gerekir. **SQLNumResultCols** ve **SQLDescribeCol** çeşitli zamanlarda ayarlamak sonuçlarını çağrılır.  
  
 **SQLSetParam** parametre veri bağlama için yaygın olarak kullanılır ve **DATA_AT_EXEC** işlevselliği.  
  
 **SQLBindCol** kaydetmek için yaygın olarak kullanılan sütun veri depolama konumları ODBC ile çıkış.  
  
 İki **SQLGetData** çağrılarını almak için kullanılan **SQL_LONG_VARCHAR** ve **SQL_LONG_VARBINARY** veri. İlk çağrıda çağırarak sütun değeri toplam uzunluğu bulmayı dener **SQLGetData** cbMaxValue 0 ile ancak geçerli pcbValue. PcbValue tutuyorsa **SQL_NO_TOTAL**, bir özel durum. Aksi halde, bir `HGLOBAL` tahsis edilir ve başka bir **SQLGetData** tüm sonuç almak için yapılan çağrı.  
  
## <a name="updating"></a>Güncelleştirme  
 Kötümser kilitleme istenip istenmediğini **SQLGetInfo SQL_LOCK_TYPES** Sorgulanacak. Varsa **SQL_LCK_EXCLUSIVE** olan desteklenmiyor, bir özel durum oluşturulur.  
  
 Güncelleştirmeye çalışırken bir `CRecordset` (**anlık görüntü** veya **dynaset**) saniyenin neden olacak **HSTMT** ayrılacak. Desteklemediği için sürücüleri ikinci **HSTMT**, imleç kitaplığı bu işlevselliği benzetimini yapacaksınız. Ne yazık ki, bu bazen geçerli sorgu ilk zorlama olduğu anlamına gelebilir **HSTMT** ikinci işlenmeden önce tamamlanma **HSTMT**kullanıcının isteği.  
  
 **SQLFreeStmt SQL_CLOSE** ve **SQL_RESET_PARAMS** ve **SQLGetCursorName** güncelleştirme işlemleri sırasında çağrılır.  
  
 Varsa **CLongBinarys** içinde **outputColumns**, ODBC **DATA_AT_EXEC** işlevselliği desteklenen. Bu döndürme içerir **SQL_NEED_DATA** gelen **SQLExecDirect**, **SQLParamData** ve **SQLPutData**.  
  
 **SQLRowCount** yalnızca 1 kaydı tarafından güncelleştirildiğini doğrulamak için yürüttükten sonra adlı **SQLExecDirect**.  
  
## <a name="forwardonly-cursors"></a>ForwardOnly imleçler  
 Yalnızca **SQLFetch** için gerekli **taşıma** işlemleri. Unutmayın **forwardOnly** imleçler güncelleştirmeleri desteklemez.  
  
## <a name="snapshot-cursors"></a>Anlık görüntü imleçler  
 Anlık görüntü işlevselliği gerektiren **SQLExtendedFetch** destekler. Yukarıda belirtildiği gibi bir sürücü desteklemediği zaman ODBC imleç kitaplığı algılar **SQLExtendedFetch**ve gerekli destek sağlar.  
  
 **SQLGetInfo**, **çağırın** desteklemelidir **SQL_SO_STATIC**.  
  
## <a name="dynaset-cursors"></a>Dinamik imleçler  
 Bir dinamik açmak için gereken en düşük destek aşağıdadır:  
  
 **SQLGetInfo**, **SQL_ODBC_VER** döndürmelidir > "01".  
  
 **SQLGetInfo**, **çağırın** desteklemelidir **SQL_SO_KEYSET_DRIVEN**.  
  
 **SQLGetInfo**, **SQL_ROW_UPDATES** "Y" döndürmesi gerekir.  
  
 **SQLGetInfo**, **SQL_POSITIONED_UPDATES** desteklemelidir **SQL_PS_POSITIONED_DELETE** ve **SQL_PS_POSITIONED_UPDATE**.  
  
 Ayrıca, kötümser kilitleme istenip istenmediğini yapılan bir çağrı **SQLSetPos** IRow 1, fRefresh FALSE ve fLock **SQL_LCK_EXCLUSIVE** yapılmayacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

