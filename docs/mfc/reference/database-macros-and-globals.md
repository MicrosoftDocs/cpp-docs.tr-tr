---
title: "Veritabanı makroları ve genel öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs: C++
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5f43135678c54ed2f837934c19a8543c86a65fdb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="database-macros-and-globals"></a>Veritabanı Makroları ve Genel Öğeleri
Makrolar ve genel öğeleri aşağıda listelenen ODBC tabanlı veritabanı uygulamaları için geçerlidir. DAO tabanlı uygulamalarla kullanılmaz.  
  
 MFC 4.2, makroları önce `AFX_SQL_ASYNC` ve `AFX_SQL_SYNC` zaman uyumsuz işlemleri diğer işlemlere zamanı elde etmek için bir fırsat vermiş oldunuz. MFC 4.2, yalnızca zaman uyumlu işlemler MFC ODBC sınıfları kullanılan değiştirildiğinden bu makroları uyarlamasını başlayarak. Makro `AFX_ODBC_CALL` MFC 4.2 yeni oluştu.  
  
### <a name="database-macros"></a>Veritabanı makroları  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|Döndüren bir ODBC API işlev çağrılarını `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL`Art arda işlevi kadar artık döndürür çağıracak `SQL_STILL_EXECUTING`.|  
|[AFX_SQL_ASYNC](#afx_sql_async)|Çağrıları `AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|Döndürmez bir ODBC API işlev çağrılarını `SQL_STILL_EXECUTING`.|  
  
### <a name="database-globals"></a>Veritabanı genel öğeleri  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|Dinamik olarak MFC'ye bağlı normal bir MFC DLL için veritabanı desteği ekler.| 
|[AfxGetHENV](#afxgethenv)|MFC tarafından kullanılmakta ODBC ortam için bir tanıtıcı alır. Doğrudan ODBC çağrılarında bu tanıtıcıyı kullanabilirsiniz.|  


## <a name="afxdbinitmodule"></a>AfxDbInitModule
MFC veritabanı (veya DAO) dinamik olarak MFC'ye bağlı normal bir MFC DLL gelen desteklemek için bu işlevi çağrısı, Normal MFC DLL içinde eklemek **CWinApp::InitInstance** MFC başlatılamadı işlevi DLL veritabanı.  
   
### <a name="syntax"></a>Sözdizimi    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı önce herhangi bir temel sınıf çağrısına oluşur veya MFC veritabanı DLL erişen kodu eklenen tüm emin olun. MFC DLL MFC uzantı DLL'si veritabanıdır; MFC uzantı DLL'si sipariş içine kablolu için de bir **CDynLinkLibrary** zinciri, onu oluşturmanız gerekir bir **CDynLinkLibrary** kullanarak her bir modüle bağlamda nesnesi. `AfxDbInitModule`oluşturur **CDynLinkLibrary** içine kablolu böylece Normal MFC DLL bağlamda nesne **CDynLinkLibrary** nesne Normal MFC DLL zinciri.  
   
### <a name="requirements"></a>Gereksinimler  
 **Başlık:** < afxdll_.h >  
   
### <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>AFX_ODBC_CALL  
 Bu makrosu döndürebilir herhangi bir ODBC API işlev çağrısı kullanmasını `SQL_STILL_EXECUTING`.  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>Parametreler  
 `SQLFunc`  
 Bir ODBC API işlev. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_ODBC_CALL`Art arda işlevi kadar artık döndürür çağırır `SQL_STILL_EXECUTING`.  
  
 Çağırmadan önce `AFX_ODBC_CALL`, bir değişkeni bildirilmelidir `nRetCode`, türü **RETCODE**.  
  
 MFC ODBC şimdi kullanımı yalnızca zaman uyumlu işleme sınıfları unutmayın. Zaman uyumsuz bir işlem gerçekleştirmek için ODBC API işlev çağrısı **SQLSetConnectOption**. Daha fazla bilgi için "Yürütme işlevleri zaman uyumsuz olarak" Windows SDK konusuna bakın.  

  
### <a name="example"></a>Örnek  
 Bu örnekte `AFX_ODBC_CALL` çağırmak için **sütunu** tarafından adlandırılmış tabloda sütun listesini döndürür ODBC API işlevi `strTableName`. Bildirimi Not `nRetCode` ve işlev için parametreleri geçirmek için kayıt kümesi veri üyeleri kullanımı. Örnek ile çağrısının sonuçlarını denetimi de gösterir **denetleyin**, sınıfının üye işlevini `CRecordset`. Değişkeni `prs` gösteren bir işaretçidir bir `CRecordset` nesnesi, başka bir yerde bildirilmedi.  
  
 [!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  

##  <a name="afx_sql_async"></a>AFX_SQL_ASYNC  
 MFC 4.2 değiştirilen bu makrosu uygulanması.  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>Parametreler  
 `prs`  
 Bir işaretçi bir `CRecordset` nesnesi veya bir `CDatabase` nesnesi. MFC 4.2 ile başlayarak, bu parametre değeri yoksayılır.  
  
 `SQLFunc`  
 Bir ODBC API işlev. ODBC API işlevleri hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 `AFX_SQL_ASYNC`yalnızca makrosu çağırır [AFX_ODBC_CALL](#afx_odbc_call) ve yoksayar `prs` parametresi. MFC sürümlerinde 4.2 önce `AFX_SQL_ASYNC` döndürebilir ODBC API işlevleri çağırmak için kullanılan `SQL_STILL_EXECUTING`. ODBC API işlevini geri döndürmedi, `SQL_STILL_EXECUTING`, ardından `AFX_SQL_ASYNC` çağırırdı `prs->OnWaitForDataSource`.  
  
> [!NOTE]
>  MFC ODBC sınıfları artık yalnızca zaman uyumlu işleme kullanın. Zaman uyumsuz bir işlem gerçekleştirmek için ODBC API işlev çağrısı **SQLSetConnectOption**. Daha fazla bilgi için "Yürütme işlevleri zaman uyumsuz olarak" Windows SDK konusuna bakın.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdb.h  
  
##  <a name="afx_sql_sync"></a>AFX_SQL_SYNC  
 `AFX_SQL_SYNC` Makrosu yalnızca işlevi çağırır `SQLFunc`.  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>Parametreler  
 `SQLFunc`  
 Bir ODBC API işlev. Bu işlevler hakkında daha fazla bilgi için Windows SDK'sı bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu makro değil döndürülecek ODBC API işlevleri çağırmak için kullanmak `SQL_STILL_EXECUTING`.  
  
 Çağırmadan önce `AFX_SQL_SYNC`, bir değişkeni bildirilmelidir `nRetCode`, türü **RETCODE**. Değerini kontrol edebilirsiniz `nRetCode` makrosu çağrısından sonra.  
  
 Unutmayın uygulanması `AFX_SQL_SYNC` MFC 4.2 değiştirildi. Sunucu durumu denetleniyor artık gerekli olmadığından `AFX_SQL_SYNC` yalnızca bir değere atar `nRetCode`. Örneğin, çağrıyı yapan yerine  
  
 [!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 Basit atama yapabilir  
  
 [!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdb.h  
  
##  <a name="afxgethenv"></a>AfxGetHENV  
 Doğrudan ODBC çağrılarında döndürülen tanıtıcı kullanabilirsiniz, ancak siz değil tanıtıcı kapatın veya tanıtıcı var olan sonra hala geçerli ve kullanılabilir olduğunu varsayın `CDatabase`- veya `CRecordset`-türetilen nesneler yok.  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 MFC tarafından kullanılmakta ODBC ortamına işleci. Olabilir `SQL_HENV_NULL` varsa hiçbir [CDatabase](../../mfc/reference/cdatabase-class.md) nesneleri ve Hayır [CRecordset](../../mfc/reference/crecordset-class.md) nesneleri.  
  
### <a name="requirements"></a>Gereksinimler  
  **Üstbilgi** afxdb.h  
    
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları ve genel öğeleri](../../mfc/reference/mfc-macros-and-globals.md)
