---
description: 'Daha fazla bilgi edinin: veritabanı makroları ve genel'
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
ms.openlocfilehash: 1dd6501c8ea37478a7b75341467e1c77819aa3f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220324"
---
# <a name="database-macros-and-globals"></a>Veritabanı Makroları ve Genel Öğeleri

Aşağıda listelenen makrolar ve genel ayarlar ODBC tabanlı veritabanı uygulamaları için geçerlidir. Bunlar, DAO tabanlı uygulamalarla kullanılmaz.

MFC 4,2 ' den önce makrolar `AFX_SQL_ASYNC` ve `AFX_SQL_SYNC` izin verdiği zaman uyumsuz, diğer işlemlere zaman elde etmek için bir fırsat sağlar. MFC 4,2 ile başlayarak, MFC ODBC sınıfları yalnızca zaman uyumlu işlemleri kullandığı için bu makroların uygulanması değişti. Makro `AFX_ODBC_CALL` MFC 4,2 'e yenidir.

### <a name="database-macros"></a>Veritabanı makroları

|Ad|Açıklama|
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Döndüren bir ODBC API işlevini çağırır `SQL_STILL_EXECUTING` . `AFX_ODBC_CALL` , artık dönene kadar işlevi tekrar tekrar çağırır `SQL_STILL_EXECUTING` .|
|[AFX_SQL_ASYNC](#afx_sql_async)|Çağırır `AFX_ODBC_CALL` .|
|[AFX_SQL_SYNC](#afx_sql_sync)|Döndürmeyen bir ODBC API işlevini çağırır `SQL_STILL_EXECUTING` .|

### <a name="database-globals"></a>Veritabanı genel

|Ad|Açıklama|
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|MFC 'ye dinamik olarak bağlanan normal bir MFC DLL için veritabanı desteği ekler.|
|[AfxGetHENV](#afxgethenv)|MFC tarafından kullanılmakta olan ODBC ortamına yönelik bir tanıtıcı alır. Bu tanıtıcıyı doğrudan ODBC çağrılarında kullanabilirsiniz.|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a> AfxDbInitModule

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'den MFC veritabanı (veya DAO) desteği için, `CWinApp::InitInstance` MFC VERITABANı dll 'sini başlatmak üzere normal MFC DLL işlevinizdeki bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Syntax

```cpp
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Açıklamalar

Bu çağrının herhangi bir temel sınıf çağrısından veya MFC veritabanı DLL 'sine erişen eklenen bir koddan önce olduğundan emin olun. MFC veritabanı DLL 'si bir MFC uzantısı DLL dosyası; bir MFC uzantısı DLL 'inin bir zincirine kablolu olması için, onu `CDynLinkLibrary` `CDynLinkLibrary` kullanacak her modülün bağlamında bir nesne oluşturması gerekir. `AfxDbInitModule` normal mfc dll `CDynLinkLibrary` `CDynLinkLibrary` 'inin nesne zincirine kablolu olması için NESNEYI normal MFC DLL içeriğinde oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a> AFX_ODBC_CALL

Döndüreetkileyebilecek herhangi bir ODBC API işlevini çağırmak için bu makroyu kullanın `SQL_STILL_EXECUTING` .

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
Bir ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_ODBC_CALL` işlevi, artık döndürülünceye kadar tekrar tekrar çağırır `SQL_STILL_EXECUTING` .

' İ çağırmadan önce, `AFX_ODBC_CALL` EKCODE türünde bir değişken bildirmeniz gerekir `nRetCode` .

MFC ODBC sınıflarının artık yalnızca zaman uyumlu işleme kullandığına göz önünde kalmaz. Zaman uyumsuz bir işlem gerçekleştirmek için ODBC API işlevini çağırmanız gerekir `SQLSetConnectOption` . Daha fazla bilgi için, Windows SDK "Işlevleri zaman uyumsuz olarak yürütme" konusuna bakın.

### <a name="example"></a>Örnek

Bu örnek `AFX_ODBC_CALL` `SQLColumns` , tarafından adlandırılan tablodaki sütunların bir listesini döndüren ODBC API işlevini çağırmak için kullanır `strTableName` . ' In bildirimini `nRetCode` ve parametreleri işleve geçirmek için kayıt kümesi veri üyelerinin kullanımını göz önünde. Örnek ayrıca `Check` , sınıfının bir üye işlevi olan çağrının sonuçlarının denetlenmesi gösterilmektedir `CRecordset` . Değişken, `prs` `CRecordset` başka bir yerde belirtilen bir nesne işaretçisidir.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a> AFX_SQL_ASYNC

Bu makronun uygulanması MFC 4,2 ' de değiştirilmiştir.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Parametreler

*PR 'ler*<br/>
Bir `CRecordset` nesne veya `CDatabase` nesne işaretçisi. MFC 4,2 ile başlayarak, bu parametre değeri yok sayılır.

*SQLFunc*<br/>
Bir ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_SQL_ASYNC` yalnızca [AFX_ODBC_CALL](#afx_odbc_call) makro çağırır ve *PR 'ler* parametresini yoksayar. 4,2 ' den önceki MFC sürümlerinde, `AFX_SQL_ASYNC` DÖNDÜREBILECEK ODBC API işlevlerini çağırmak için kullanılmıştır `SQL_STILL_EXECUTING` . Bir ODBC API işlevi döndürüyordu `SQL_STILL_EXECUTING` , sonra `AFX_SQL_ASYNC` çağıracaktı `prs->OnWaitForDataSource` .

> [!NOTE]
> MFC ODBC sınıfları artık yalnızca zaman uyumlu işlemeyi kullanır. Zaman uyumsuz bir işlem gerçekleştirmek için ODBC API işlevini çağırmanız gerekir `SQLSetConnectOption` . Daha fazla bilgi için, Windows SDK "Işlevleri zaman uyumsuz olarak yürütme" konusuna bakın.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a> AFX_SQL_SYNC

`AFX_SQL_SYNC`Makro yalnızca işlevini çağırır `SQLFunc` .

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
Bir ODBC API işlevi. Bu işlevler hakkında daha fazla bilgi için Windows SDK bakın.

### <a name="remarks"></a>Açıklamalar

Bu makroyu, döndürmeyen ODBC API işlevlerini çağırmak için kullanın `SQL_STILL_EXECUTING` .

Çağrılmadan önce, `AFX_SQL_SYNC` EKCODE türünde bir değişken bildirmeniz gerekir `nRetCode` . Makro çağrısından sonra değerini kontrol edebilirsiniz `nRetCode` .

`AFX_SQL_SYNC`MFC 4,2 ' de değiştirilen uygulamanın değiştiğini unutmayın. Sunucu durumunun denetlenmesi artık gerekli olmadığı `AFX_SQL_SYNC` için, yalnızca bir değer atar `nRetCode` . Örneğin, çağrı yapmak yerine

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

yalnızca atamayı yapabilirsiniz

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

## <a name="afxgethenv"></a><a name="afxgethenv"></a> AfxGetHENV

Döndürülen tanıtıcıyı doğrudan ODBC çağrılarında kullanabilirsiniz, ancak tanıtıcıyı kapatmamalıdır veya var olan ya da türetilmiş herhangi bir `CDatabase` nesne yok edildiğinde tanıtıcının hala geçerli ve kullanılabilir olduğunu varsayın `CRecordset` .

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Dönüş Değeri

MFC tarafından şu anda kullanılmakta olan ODBC ortamının tanıtıcısı. `SQL_HENV_NULL`Hiçbir [CDatabase](../../mfc/reference/cdatabase-class.md) nesnesi ve kullanımda bir [CRecordset](../../mfc/reference/crecordset-class.md) nesnesi yoksa, bu olabilir.

### <a name="requirements"></a>Gereksinimler

  **Başlık** Afxdb. h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve genel öğeler](../../mfc/reference/mfc-macros-and-globals.md)
