---
title: Veritabanı Makroları ve Genel Öğeleri
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79420843"
---
# <a name="database-macros-and-globals"></a>Veritabanı Makroları ve Genel Öğeleri

Aşağıda listelenen makrolar ve genel ayarlar ODBC tabanlı veritabanı uygulamaları için geçerlidir. Bunlar, DAO tabanlı uygulamalarla kullanılmaz.

MFC 4,2 ' den önce, `AFX_SQL_ASYNC` ve `AFX_SQL_SYNC` zaman uyumsuz olarak, diğer işlemlere zaman elde eden bir fırsat sağlar. MFC 4,2 ile başlayarak, MFC ODBC sınıfları yalnızca zaman uyumlu işlemleri kullandığı için bu makroların uygulanması değişti. Makro `AFX_ODBC_CALL` MFC 4,2 ' de yenidir.

### <a name="database-macros"></a>Veritabanı makroları

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|`SQL_STILL_EXECUTING`döndüren bir ODBC API işlevini çağırır. `AFX_ODBC_CALL`, artık `SQL_STILL_EXECUTING`döndürünceye kadar işlevi tekrar tekrar çağıracaktır.|
|[AFX_SQL_ASYNC](#afx_sql_async)|`AFX_ODBC_CALL`çağırır.|
|[AFX_SQL_SYNC](#afx_sql_sync)|`SQL_STILL_EXECUTING`döndürmeyen bir ODBC API işlevini çağırır.|

### <a name="database-globals"></a>Veritabanı genel

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC 'ye dinamik olarak bağlanan normal bir MFC DLL için veritabanı desteği ekler.|
|[AfxGetHENV](#afxgethenv)|MFC tarafından kullanılmakta olan ODBC ortamına yönelik bir tanıtıcı alır. Bu tanıtıcıyı doğrudan ODBC çağrılarında kullanabilirsiniz.|

## <a name="afxdbinitmodule"></a>AfxDbInitModule

MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'den MFC veritabanı (veya DAO) desteği için, MFC veritabanı DLL 'sini başlatmak üzere normal MFC DLL 'inin `CWinApp::InitInstance` işlevinde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Açıklamalar

Bu çağrının herhangi bir temel sınıf çağrısından veya MFC veritabanı DLL 'sine erişen eklenen bir koddan önce olduğundan emin olun. MFC veritabanı DLL 'si bir MFC uzantısı DLL dosyası; bir MFC uzantısı DLL 'sinin `CDynLinkLibrary` zincirine kablolu olması için, onu kullanacak her modülün bağlamında bir `CDynLinkLibrary` nesnesi oluşturması gerekir. `AfxDbInitModule`, normal MFC DLL 'inin `CDynLinkLibrary` nesne zincirine kablolu olması için normal MFC DLL bağlamındaki `CDynLinkLibrary` nesnesini oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<afxdll_. h >

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL

`SQL_STILL_EXECUTING`döndüreolabilecek herhangi bir ODBC API işlevini çağırmak için bu makroyu kullanın.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
Bir ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_ODBC_CALL`, artık `SQL_STILL_EXECUTING`döndürünceye kadar işlevi tekrar çağırır.

`AFX_ODBC_CALL`çağırmadan önce, EKCODE türünde bir `nRetCode`değişkeni bildirmeniz gerekir.

MFC ODBC sınıflarının artık yalnızca zaman uyumlu işleme kullandığına göz önünde kalmaz. Zaman uyumsuz bir işlem gerçekleştirmek için `SQLSetConnectOption`ODBC API işlevini çağırmanız gerekir. Daha fazla bilgi için, Windows SDK "Işlevleri zaman uyumsuz olarak yürütme" konusuna bakın.

### <a name="example"></a>Örnek

Bu örnek, `strTableName`tarafından adlandırılan tablodaki sütunların bir listesini döndüren `SQLColumns` ODBC API işlevini çağırmak için `AFX_ODBC_CALL` kullanır. `nRetCode` bildirimine ve parametreleri işleve geçirmek için kayıt kümesi veri üyelerinin kullanımına göz önünde. Örnek ayrıca, `CRecordset`sınıfının bir üye işlevi olan `Check`çağrısının sonuçlarını denetlemeyi gösterir. `prs` değişkeni, başka bir yerde bildirildiği `CRecordset` nesnesinin bir işaretçisidir.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC

Bu makronun uygulanması MFC 4,2 ' de değiştirilmiştir.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Parametreler

*PR 'ler*<br/>
`CRecordset` nesnesine veya `CDatabase` nesnesine yönelik bir işaretçi. MFC 4,2 ile başlayarak, bu parametre değeri yok sayılır.

*SQLFunc*<br/>
Bir ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_SQL_ASYNC` yalnızca makro [AFX_ODBC_CALL](#afx_odbc_call) çağırır ve *PR 'ler* parametresini yoksayar. 4,2 ' dan önceki MFC sürümlerinde, `SQL_STILL_EXECUTING`döndürebilen ODBC API işlevlerini çağırmak için `AFX_SQL_ASYNC` kullanılmıştır. Bir ODBC API işlevi `SQL_STILL_EXECUTING`döndürmediyseniz `AFX_SQL_ASYNC` `prs->OnWaitForDataSource`çağırır.

> [!NOTE]
>  MFC ODBC sınıfları artık yalnızca zaman uyumlu işlemeyi kullanır. Zaman uyumsuz bir işlem gerçekleştirmek için `SQLSetConnectOption`ODBC API işlevini çağırmanız gerekir. Daha fazla bilgi için, Windows SDK "Işlevleri zaman uyumsuz olarak yürütme" konusuna bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC

`AFX_SQL_SYNC` makro yalnızca `SQLFunc`işlevini çağırır.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
Bir ODBC API işlevi. Bu işlevler hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

`SQL_STILL_EXECUTING`döndürmeyecek ODBC API işlevlerini çağırmak için bu makroyu kullanın.

`AFX_SQL_SYNC`çağrılmadan önce, EKCODE türünde bir `nRetCode`değişkeni bildirmeniz gerekir. Makro çağrısından sonra `nRetCode` değerini kontrol edebilirsiniz.

`AFX_SQL_SYNC` uygulamasının MFC 4,2 ' de değiştiğini unutmayın. Sunucu durumunun denetlenmesi artık gerekli olmadığından, `AFX_SQL_SYNC` `nRetCode`bir değer atar. Örneğin, çağrı yapmak yerine

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

yalnızca atamayı yapabilirsiniz

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

##  <a name="afxgethenv"></a>AfxGetHENV

Döndürülen tanıtıcıyı doğrudan ODBC çağrılarında kullanabilirsiniz, ancak tanıtıcıyı kapatmamalıdır ya da tanıtıcının hala geçerli olduğunu ve var olan `CDatabase`ya da `CRecordset`türetilmiş nesnelerden sonra kullanılabilir olduğunu varsaymalısınız.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Dönüş Değeri

MFC tarafından şu anda kullanılmakta olan ODBC ortamının tanıtıcısı. Bir [CDatabase](../../mfc/reference/cdatabase-class.md) nesnesi yoksa ve kullanılan [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi yoksa `SQL_HENV_NULL` olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
