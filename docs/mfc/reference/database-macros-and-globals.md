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
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268726"
---
# <a name="database-macros-and-globals"></a>Veritabanı Makroları ve Genel Öğeleri

Makrolar ve genel öğeleri aşağıda listelenen ODBC tabanlı veritabanı uygulamaları için geçerlidir. DAO tabanlı uygulamalarınızı kullanılmazlar.

MFC 4.2 makroları önce `AFX_SQL_ASYNC` ve `AFX_SQL_SYNC` zaman uyumsuz işlemleri zaman diğer işlemler için yield fırsatı verdiği. MFC ODBC sınıfları yalnızca zaman uyumlu işlemler kullanılır çünkü değiştirilmesi bu makrolar uygulamasını MFC 4.2 ve sonraki sürümlerinde. Makro `AFX_ODBC_CALL` MFC 4.2 için yeni olan.

### <a name="database-macros"></a>Veritabanı makroları

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Döndürür bir ODBC API işlevini çağırır `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL` sürekli olarak işlev kadar artık döndürür çağırır `SQL_STILL_EXECUTING`.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Çağrıları `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Sonuç döndürmez bir ODBC API işlevini çağırır `SQL_STILL_EXECUTING`.|

### <a name="database-globals"></a>Veritabanı genel öğeleri

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN veritabanı desteği ekler.|
|[AfxGetHENV](#afxgethenv)|MFC tarafından kullanılmakta ODBC ortam için bir tanıtıcı alır. Bu işleyici, doğrudan ODBC çağrılarında kullanabilirsiniz.|

## <a name="afxdbinitmodule"></a> AfxDbInitModule

Dinamik olarak MFC'ye bağlı normal MFC DLL'SİNİN gelen MFC veritabanı (veya DAO) desteği sağlamak için bu işlev çağrısı, Normal MFC DLL içinde ekleyin `CWinApp::InitInstance` işlevi MFC DLL veritabanı.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Açıklamalar

Bu çağrı herhangi bir temel sınıf çağrısından önce oluşur veya MFC veritabanı DLL erişir kod eklenen tüm emin olun. MFC DLL bir MFC uzantılı DLL veritabanıdır; bir MFC uzantılı DLL içine kablolu için sırada bir `CDynLinkLibrary` zinciri gerekir oluşturma bir `CDynLinkLibrary` onu kullanan her bir modüle bağlamında nesne. `AfxDbInitModule` oluşturur `CDynLinkLibrary` içine kablolu, böylece Normal MFC DLL bağlamda nesne `CDynLinkLibrary` nesnesi Normal MFC DLL'SİNİN zinciri.

### <a name="requirements"></a>Gereksinimler

**Başlık:** \<afxdll_.h >

##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL

Döndürebilir herhangi bir ODBC API işlevini çağırmak için bu makroyu kullanın `SQL_STILL_EXECUTING`.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_ODBC_CALL` Art arda kadar artık döndürür sürüklerken `SQL_STILL_EXECUTING`.

Çağırmadan önce `AFX_ODBC_CALL`, bir değişken bildirmeniz gerekir `nRetCode`, RETCODE türü.

MFC ODBC şimdi kullanımı yalnızca zaman uyumlu işleme sınıfları unutmayın. Zaman uyumsuz bir işlemi gerçekleştirmek için ODBC API işlevini çağırmanız gerekir `SQLSetConnectOption`. Daha fazla bilgi için "Yürütülen işlevler zaman uyumsuz olarak" Windows SDK konusuna bakın.

### <a name="example"></a>Örnek

Bu örnekte `AFX_ODBC_CALL` çağrılacak `SQLColumns` tarafından adlı tablo sütun listesini döndüren ODBC API işlevini `strTableName`. Bildirimi Not `nRetCode` ve işlevin parametreleri geçirmek için kayıt kümesi veri üyelerinin kullanın. Örnek ayrıca denetimi ile arama sonuçlarını gösterir `Check`, sınıfının üye işlevinde `CRecordset`. Değişken `prs` işaretçisidir bir `CRecordset` nesnenin, başka bir yerde bildirilmiş.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC

MFC 4.2 içinde değiştirilen Bu makroyu uygulanması.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Parametreler

*çekme istekleri*<br/>
Bir işaretçi bir `CRecordset` nesnesi veya bir `CDatabase` nesne. MFC 4.2 ile başlayarak, bu parametre yoksayılır.

*SQLFunc*<br/>
ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_SQL_ASYNC` yalnızca makronun çağırır [AFX_ODBC_CALL](#afx_odbc_call) ve yoksayar *pr'ler* parametresi. 4.2 önce MFC sürümlerinde `AFX_SQL_ASYNC` döndürebilir ODBC API işlevleri çağırmak için kullanılan `SQL_STILL_EXECUTING`. ODBC API işlevi döndürmedi, `SQL_STILL_EXECUTING`, ardından `AFX_SQL_ASYNC` çağıracak `prs->OnWaitForDataSource`.

> [!NOTE]
>  MFC ODBC sınıfları artık yalnızca zaman uyumlu işleme kullanır. Zaman uyumsuz bir işlemi gerçekleştirmek için ODBC API işlevini çağırmanız gerekir `SQLSetConnectOption`. Daha fazla bilgi için "Yürütülen işlevler zaman uyumsuz olarak" Windows SDK konusuna bakın.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdb.h

##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC

`AFX_SQL_SYNC` Makrosu yalnızca işlev çağrıları `SQLFunc`.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
ODBC API işlevi. Bu işlevler hakkında daha fazla bilgi için Windows SDK'sı bakın.

### <a name="remarks"></a>Açıklamalar

Değil döndüreceği ODBC API işlevlerini çağırmak için bu makroyu kullanın `SQL_STILL_EXECUTING`.

Çağırmadan önce `AFX_SQL_SYNC`, bir değişken bildirmeniz gerekir `nRetCode`, RETCODE türü. Değerini kontrol edebilirsiniz `nRetCode` makrosu çağrısından sonra.

Unutmayın, uygulama `AFX_SQL_SYNC` MFC 4.2 içinde değiştirildi. Sunucu durumu denetimi artık gerekli olduğundan `AFX_SQL_SYNC` yalnızca bir değer atar `nRetCode`. Örneğin, çağrıyı yapan yerine

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

Basit atama yapabilir

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdb.h

##  <a name="afxgethenv"></a>  AfxGetHENV

Döndürülen tanıtıcının doğrudan ODBC çağrılarında kullanabilirsiniz, ancak size değil tanıtıcı kapatın veya tanıtıcı herhangi bir mevcut sonra hala geçerli ve kullanılabilir olduğunu varsayın `CDatabase`- veya `CRecordset`-türetilmiş nesneler yok.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Dönüş Değeri

MFC tarafından kullanılmakta ODBC ortam tanıtıcısı. Olabilir `SQL_HENV_NULL` varsa hiçbir [CDatabase](../../mfc/reference/cdatabase-class.md) nesneleri ve Hayır [CRecordset](../../mfc/reference/crecordset-class.md) nesneleri.

### <a name="requirements"></a>Gereksinimler

  **Üst bilgi** afxdb.h

## <a name="see-also"></a>Ayrıca bkz.

[Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
