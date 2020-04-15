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
ms.openlocfilehash: 4e9700311bbc20ea017675357a91a56813cc4bde
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376957"
---
# <a name="database-macros-and-globals"></a>Veritabanı Makroları ve Genel Öğeleri

Aşağıda listelenen makrolar ve globaller ODBC tabanlı veritabanı uygulamaları için geçerlidir. DAO tabanlı uygulamalarda kullanılmaz.

MFC 4.2'den önce `AFX_SQL_ASYNC` `AFX_SQL_SYNC` makrolar ve eşzamanlı işlemler, diğer işlemlere zaman kazandırma fırsatı verir. MFC 4.2 ile başlayarak, MFC ODBC sınıfları yalnızca senkron işlemler kullandığından, bu makroların uygulanması değişti. Makro `AFX_ODBC_CALL` MFC 4.2 için yeniydi.

### <a name="database-macros"></a>Veritabanı Makroları

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Döndüren `SQL_STILL_EXECUTING`bir ODBC API işlevini çağırır. `AFX_ODBC_CALL`artık geri dönene `SQL_STILL_EXECUTING`kadar işlevi tekrar tekrar arayacaktır.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Aramalar `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Geri dönmeyen `SQL_STILL_EXECUTING`bir ODBC API işlevini çağırır.|

### <a name="database-globals"></a>Veritabanı Globals

|||
|-|-|
|[AfxDbInitModülü](#afxdbinitmodule)|Dinamik olarak MFC'ye bağlı normal bir MFC DLL için veritabanı desteği ekler.|
|[AfxGetHENV](#afxgethenv)|Şu anda MFC tarafından kullanılmakta olan ODBC ortamına bir tanıtıcı alır. Bu tutamacı doğrudan ODBC aramalarında kullanabilirsiniz.|

## <a name="afxdbinitmodule"></a><a name="afxdbinitmodule"></a>AfxDbInitModülü

MFC veritabanı (veya DAO) dinamik olarak MFC'ye bağlı normal bir MFC DLL desteği için, MFC `CWinApp::InitInstance` veritabanı DLL'yi başlatmayı sağlamak için normal MFC DLL işlevinizde bu işleve bir çağrı ekleyin.

### <a name="syntax"></a>Sözdizimi

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Açıklamalar

Bu çağrının herhangi bir taban sınıf çağrısından veya MFC veritabanı DLL'ye erişen herhangi bir ek koddan önce oluştuğundan emin olun. MFC veritabanı DLL bir MFC uzantısı DLL olduğunu; Bir MFC uzantısı DLL'nin bir `CDynLinkLibrary` zincire bağlanabilmesi `CDynLinkLibrary` için, onu kullanacak her modül bağlamında bir nesne oluşturması gerekir. `AfxDbInitModule`normal MFC DLL'nizin `CDynLinkLibrary` `CDynLinkLibrary` nesne zincirine bağlanıyor diye normal MFC DLL bağlamında nesne oluşturur.

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<afxdll_.h>

## <a name="afx_odbc_call"></a><a name="afx_odbc_call"></a>AFX_ODBC_CALL

Geri dönebilecek `SQL_STILL_EXECUTING`herhangi bir ODBC API işlevini çağırmak için bu makroyu kullanın.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_ODBC_CALL`artık geri dönene `SQL_STILL_EXECUTING`kadar işlevi tekrar tekrar çağırır.

Aramadan `AFX_ODBC_CALL`önce, RETCODE türünde bir değişken `nRetCode`bildirmeniz gerekir.

MFC ODBC sınıflarında artık yalnızca eşzamanlı işleme kullanıldığını unutmayın. Eşzamanlı bir işlem gerçekleştirmek için ODBC API işlevini `SQLSetConnectOption`aramanız gerekir. Daha fazla bilgi için Windows SDK'daki "İşlevleri Eşit leme" konusuna bakın.

### <a name="example"></a>Örnek

Bu örnek, tabloda adı geçen sütunların listesini döndüren `AFX_ODBC_CALL` `SQLColumns` ODBC `strTableName`API işlevini çağırmak için kullanılır. Parametreleri işleve aktarmak için kayıt kümesi veri üyelerinin bildirimine `nRetCode` ve kullanımına dikkat edin. Örnek, sınıfın `CRecordset`bir üye işlevi ile `Check`arama sonuçlarını denetlemeyi de göstermektedir. Değişken, `prs` başka bir `CRecordset` yerde bildirilen bir nesneye işaretçidir.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="afx_sql_async"></a><a name="afx_sql_async"></a>AFX_SQL_ASYNC

Bu makronun uygulanması MFC 4.2'de değiştirildi.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Parametreler

*Prs*<br/>
Bir `CRecordset` nesneye veya `CDatabase` nesneye işaretçi. MFC 4.2 ile başlayarak, bu parametre değeri yoksayılır.

*SQLFunc*<br/>
ODBC API işlevi. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="remarks"></a>Açıklamalar

`AFX_SQL_ASYNC`makroyu [AFX_ODBC_CALL](#afx_odbc_call) çağırır ve *prs* parametresini yok sayar. 4.2'den önceki MFC `AFX_SQL_ASYNC` sürümlerinde, dönebilecek `SQL_STILL_EXECUTING`ODBC API işlevlerini aramak için kullanıldı. Bir ODBC API işlevi `SQL_STILL_EXECUTING`döndüyse, o zaman `AFX_SQL_ASYNC` . `prs->OnWaitForDataSource`

> [!NOTE]
> MFC ODBC sınıfları artık yalnızca eşzamanlı işleme kullanır. Eşzamanlı bir işlem gerçekleştirmek için ODBC API işlevini `SQLSetConnectOption`aramanız gerekir. Daha fazla bilgi için Windows SDK'daki "İşlevleri Eşit leme" konusuna bakın.

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdb.h

## <a name="afx_sql_sync"></a><a name="afx_sql_sync"></a>AFX_SQL_SYNC

Makro `AFX_SQL_SYNC` sadece işlevi `SQLFunc`çağırır.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Parametreler

*SQLFunc*<br/>
ODBC API işlevi. Bu işlevler hakkında daha fazla bilgi için Windows SDK'ya bakın.

### <a name="remarks"></a>Açıklamalar

Bu makroyu, geri dönmeyen `SQL_STILL_EXECUTING`ODBC API işlevlerini çağırmak için kullanın.

Aramadan `AFX_SQL_SYNC`önce, RETCODE `nRetCode`türünde bir değişken bildirmelisiniz. Makro çağrısından `nRetCode` sonra değerini kontrol edebilirsiniz.

MFC 4.2'de uygulamanın `AFX_SQL_SYNC` değiştiğini unutmayın. Sunucu durumunu denetlemek artık gerekli `AFX_SQL_SYNC` olmadığından, yalnızca bir `nRetCode`değer atayabilmek için. Örneğin, arama yapmak yerine

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

sadece atama yapabilirsiniz

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdb.h

## <a name="afxgethenv"></a><a name="afxgethenv"></a>AfxGetHENV

Döndürülen tutamacı doğrudan ODBC aramalarında kullanabilirsiniz, ancak tutamacı kapatmamalı veya varolan `CDatabase`veya `CRecordset`türetilen nesneler yok edildikten sonra tutamacın hala geçerli ve kullanılabilir olduğunu varsaymamalısınız.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Dönüş Değeri

Şu anda MFC tarafından kullanılmakta olan ODBC ortamının tutamacı. CDatabase `SQL_HENV_NULL` nesnesi ve kullanılan [CRecordset](../../mfc/reference/crecordset-class.md) nesneleri yoksa olabilir. [CDatabase](../../mfc/reference/cdatabase-class.md)

### <a name="requirements"></a>Gereksinimler

  **Üstbilgi** afxdb.h

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar ve Küreseller](../../mfc/reference/mfc-macros-and-globals.md)
