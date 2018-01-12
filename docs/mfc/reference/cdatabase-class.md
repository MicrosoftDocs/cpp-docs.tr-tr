---
title: "CDatabase sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDatabase
- AFXDB/CDatabase
- AFXDB/CDatabase::CDatabase
- AFXDB/CDatabase::BeginTrans
- AFXDB/CDatabase::BindParameters
- AFXDB/CDatabase::Cancel
- AFXDB/CDatabase::CanTransact
- AFXDB/CDatabase::CanUpdate
- AFXDB/CDatabase::Close
- AFXDB/CDatabase::CommitTrans
- AFXDB/CDatabase::ExecuteSQL
- AFXDB/CDatabase::GetBookmarkPersistence
- AFXDB/CDatabase::GetConnect
- AFXDB/CDatabase::GetCursorCommitBehavior
- AFXDB/CDatabase::GetCursorRollbackBehavior
- AFXDB/CDatabase::GetDatabaseName
- AFXDB/CDatabase::IsOpen
- AFXDB/CDatabase::OnSetOptions
- AFXDB/CDatabase::Open
- AFXDB/CDatabase::OpenEx
- AFXDB/CDatabase::Rollback
- AFXDB/CDatabase::SetLoginTimeout
- AFXDB/CDatabase::SetQueryTimeout
- AFXDB/CDatabase::m_hdbc
dev_langs: C++
helpviewer_keywords:
- CDatabase [MFC], CDatabase
- CDatabase [MFC], BeginTrans
- CDatabase [MFC], BindParameters
- CDatabase [MFC], Cancel
- CDatabase [MFC], CanTransact
- CDatabase [MFC], CanUpdate
- CDatabase [MFC], Close
- CDatabase [MFC], CommitTrans
- CDatabase [MFC], ExecuteSQL
- CDatabase [MFC], GetBookmarkPersistence
- CDatabase [MFC], GetConnect
- CDatabase [MFC], GetCursorCommitBehavior
- CDatabase [MFC], GetCursorRollbackBehavior
- CDatabase [MFC], GetDatabaseName
- CDatabase [MFC], IsOpen
- CDatabase [MFC], OnSetOptions
- CDatabase [MFC], Open
- CDatabase [MFC], OpenEx
- CDatabase [MFC], Rollback
- CDatabase [MFC], SetLoginTimeout
- CDatabase [MFC], SetQueryTimeout
- CDatabase [MFC], m_hdbc
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c6aeaa64b0b665449ee9216070cdebbc2632948b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdatabase-class"></a>CDatabase sınıfı
Veri kaynağı üzerinde çalışabilir, bir veri kaynağına bağlantıyı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDatabase : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDatabase::CDatabase](#cdatabase)|Oluşturan bir `CDatabase` nesnesi. Çağırarak nesne başlatmalıdır `OpenEx` veya **açık**.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|"İşlem" başlatır — bir dizi ters çevrilebilir çağrısı `AddNew`, **Düzenle**, **silmek**, ve **güncelleştirme** sınıfının üye işlevleri `CRecordset` — üzerinde bağlı veri kaynağı. Veri kaynağı için hareketleri desteklemesi gerekir **BeginTrans** herhangi bir etkisi olması.|  
|[CDatabase::BindParameters](#bindparameters)|Çağırmadan önce parametreleri bağlamak sağlar `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](#cancel)|Zaman uyumsuz bir işlem veya ikinci bir iş parçacığı işleminden iptal eder.|  
|[CDatabase::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır olmayan döndürür.|  
|[CDatabase::CanUpdate](#canupdate)|Döndürür sıfır olmayan IF `CDatabase` nesne güncelleştirilebilir değil (salt okunur değil).|  
|[CDatabase::Close](#close)|Veri kaynağı bağlantısı kapatır.|  
|[CDatabase::CommitTrans](#committrans)|Bir işlem tarafından başlamış tamamlandıktan **BeginTrans**. Veri kaynağı alter komutları işlemde gerçekleştirilir.|  
|[CDatabase::ExecuteSQL](#executesql)|Bir SQL deyimini yürütür. Hiçbir veri kaydı döndürülür.|  
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|Üzerinden yer işaretleri kayıt kümesi nesnelerde kalıcı işlemler belirtilmektedir.|  
|[CDatabase::GetConnect](#getconnect)|Bağlanmak için kullanılan ODBC bağlantı dizesi döndürür `CDatabase` bir veri kaynağına nesnesi.|  
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|Bir açık kayıt nesne üzerinde bir işlemi sonlandırdı etkisini tanımlar.|  
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|Açık kayıt nesne üzerinde bir işlemi geri alınıyor etkisini tanımlar.|  
|[CDatabase::GetDatabaseName](#getdatabasename)|Veritabanının adını şu anda kullanımda döndürür.|  
|[CDatabase::IsOpen](#isopen)|Döndürür sıfır olmayan IF `CDatabase` nesne bir veri kaynağı için şu anda bağlı.|  
|[CDatabase::OnSetOptions](#onsetoptions)|Standart bağlantı seçeneklerini ayarlamak için çerçevesi tarafından çağrılır. Varsayılan uygulama sorgu zaman aşımı değerini ayarlar. Çağırarak bu seçenekler önceden kurup `SetQueryTimeout`.|  
|[CDatabase::Open](#open)|Bir veri kaynağı (aracılığıyla ODBC sürücüsü) bir bağlantı kurar.|  
|[CDatabase::OpenEx](#openex)|Bir veri kaynağı (aracılığıyla ODBC sürücüsü) bir bağlantı kurar.|  
|[CDatabase::Rollback](#rollback)|Geçerli işlem sırasında yapılan değişiklikleri geri alır. Veri kaynağı için tanımlanan şekilde önceki durumuna döndürür **BeginTrans** değiştirilmemiş çağrısı.|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Bir veri kaynağı bağlantı denemesi sonra zaman aşımına olacak saniye sayısını ayarlar.|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|Operations sorgusu hangi veritabanı saniye sayısını ayarlar zaman aşımına uğrar. Sonraki tüm kayıt kümesi etkiler **açık**, `AddNew`, **Düzenle**, ve **silmek** çağrıları.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDatabase::m_hdbc](#m_hdbc)|Bir veri kaynağı açık veritabanı bağlantısı (ODBC) bağlantı tanıtıcısı. Tür **HDBC**.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir veri kaynağı, bazı veritabanı yönetim sistemi (DBMS) tarafından barındırılan veri, belirli bir örneğidir. Microsoft SQL Server, Microsoft Access, Borland dBASE ve xBASE örnek verilebilir. Bir veya daha fazla olabilir `CDatabase` nesneleri, uygulamanızdaki bir anda etkin.  
  
> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, bir sınıf kullanma [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) yerine. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 Kullanılacak `CDatabase`, oluşturmak bir `CDatabase` nesne ve çağrı kendi `OpenEx` üye işlevi. Bir bağlantı açar. Ardından oluşturmak zaman `CRecordset` nesnelerini bağlı veri kaynağı üzerinde çalışmak için bir işaretçi kayıt kümesi Oluşturucusu geçirmek, `CDatabase` nesnesi. Bağlantı kullanmayı bitirdiğinizde, çağrı **Kapat** üye işlev ve destroy `CDatabase` nesnesi. **Kapat** olmayan kapattığınız önceden kümeleri kapatır.  
  
 Hakkında daha fazla bilgi için `CDatabase`, makalelerine bakın [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) ve [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="begintrans"></a>CDatabase::BeginTrans  
 Bağlı veri kaynağı ile bir işlemi başlatmak için bu üye işlevini çağırın.  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çağrı başarılı oldu ve değişiklikler yalnızca el ile uygulanır sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla çağrıları için bir işlem oluşan `AddNew`, **Düzenle**, **silmek**, ve **güncelleştirme** üye işlevlerinin bir `CRecordset` nesne. Bir işlem başlamadan önce `CDatabase` nesne gerekir zaten veri kaynağına bağlı çağırarak kendi `OpenEx` veya **açık** üye işlevi. İşlem sona erdirmek için arama [CommitTrans](#committrans) veri kaynağı için tüm değişiklikleri kabul etmek için (ve bunları yürütmek için) veya arama [geri alma](#rollback) tüm işlemi durdurulacak. Çağrı **BeginTrans** işlemde herhangi kayıt kümeleri'ni açın ve olarak gerçek yakın güncelleştirme işlemlerini mümkün olduğunca sonra.  
  
> [!CAUTION]
>  ODBC sürücüsü bağlı olarak, bir kayıt çağırmadan önce açma **BeginTrans** çağrılırken sorunlara neden olabilirsiniz **geri alma**. Kullanmakta olduğunuz belirli sürücü denetlemeniz gerekir. Örneğin, Microsoft ODBC Masaüstü Sürücü Paketi 3.0 dahil Microsoft Access sürücüsü kullanırken, açık bir imleç sahip herhangi bir veritabanı üzerinde bir işlemi başlamamalıdır Jet veritabanı altyapısı gereksinimi dikkate alması gerekir. MFC veritabanı sınıfları açık bir imleç açık anlamına gelir. `CRecordset` nesnesi. Daha fazla bilgi için bkz: [Teknik Not 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).  
  
 **BeginTrans** sunucuda istenen eşzamanlılık ve veri kaynağı özelliklerini bağlı olarak veri kayıtlarını da kilitleme. Kilitleme veriler hakkında daha fazla bilgi için bkz: [kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
 Kullanıcı tanımlı işlemleri makalesinde açıklanmıştır [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
 **BeginTrans** olduğu hareketler dizisi geri durum oluşturur (tersine). Geri alma için yeni bir durum oluşturmak için herhangi bir geçerli işlem Yürüt'ı çağırın **BeginTrans** yeniden.  
  
> [!CAUTION]
>  Çağırma **BeginTrans** yeniden çağırmadan **CommitTrans** veya **geri alma** bir hatadır.  
  
 Çağrı [CanTransact](#cantransact) sürücünüzü için verilen bir veritabanı işlemleri destekleyip desteklemediğini belirlemek için üye işlevi. Ayrıca çağırmalıdır [GetCursorCommitBehavior](#getcursorcommitbehavior) ve [GetCursorRollbackBehavior](#getcursorrollbackbehavior) imleç koruma desteğini belirlemek için.  
  
 İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Örnek  
  Makalesine bakın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="bindparameters"></a>CDatabase::BindParameters  
 Geçersiz kılma `BindParameters` çağırmadan önce parametreleri bağlamak gerektiğinde [CDatabase::ExecuteSQL](#executesql).  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parametreler  
 `hstmt`  
 Parametreleri bağlamak istediğiniz ODBC deyim tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yaklaşım sonucu gerekmediğinde yararlıdır bir saklı yordam ayarlayın.  
  
 Geçersiz kılmada çağrısı **SQLBindParameters** ve ilgili parametreleri bağlamak için ODBC işlevleri. MFC çağırır aramanız için önce geçersiz kılma `ExecuteSQL`. Çağrı gerekmez **SQLPrepare**; `ExecuteSQL` çağrıları **SQLExecDirect** ve bozar **hstmt**, kullanılan yalnızca bir kez.  
  
##  <a name="cancel"></a>CDatabase::Cancel  
 Veri kaynağı zaman uyumsuz bir işlem devam ediyor veya ikinci bir iş parçacığı işleminden iptal istemek için bu üye işlevini çağırın.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Açıklamalar  
 MFC ODBC sınıfları artık zaman uyumsuz işleme kullandığını unutmayın; bir asychronous işlemi gerçekleştirmek için doğrudan ODBC API işlevini çağırmanız gerekir [SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx). Daha fazla bilgi için bkz: [zaman uyumsuz yürütme](https://msdn.microsoft.com/library/ms713563.aspx) Windows SDK'sındaki.  
  
##  <a name="cantransact"></a>CDatabase::CanTransact  
 Veritabanı işlemleri izin verip vermediğini belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF bunu kullanarak kayıt kümeleri `CDatabase` nesne izin işlemleri; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>CDatabase::CanUpdate  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDatabase` nesne güncelleştirmeler sağlar.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDatabase` nesne güncelleştirmeler sağlar; Aksi halde 0 ya da bu gösteren geçirilen **TRUE** içinde `bReadOnly` açıldığında, `CDatabase` nesne veya veri kendisini kaynağı salt okunur. Veri kaynağı salt okunur bir çağrı varsa ODBC API işlevi **SQLGetInfo** için **SQL_DATASOURCE_READ_ONLY** "y" döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm sürücüleri güncelleştirmeleri destekler.  
  
##  <a name="cdatabase"></a>CDatabase::CDatabase  
 Oluşturan bir `CDatabase` nesnesi.  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturma sonra çağırmalısınız kendi `OpenEx` veya **açık** belirtilen veri kaynağı bağlantı kurmak için üye işlevi.  
  
 Katıştırmak kullanışlı bulabilirsiniz `CDatabase` belge sınıfınızda nesnesi.  
  
### <a name="example"></a>Örnek  
 Bu örnekte kullanarak gösterilmektedir `CDatabase` içinde bir `CDocument`-türetilmiş sınıf.  
  
 [!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="close"></a>CDatabase::Close  
 Bir veri kaynağından bağlantıyı kesmek isterseniz, bu üye işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İle ilişkili tüm kayıt kümeleri kapatmalısınız `CDatabase` bu üye işlevini çağırmadan önce nesne. Çünkü **Kapat** yok `CDatabase` nesne yeniden nesne aynı veri kaynağı veya farklı bir veri kaynağı için yeni bir bağlantı açarak.  
  
 Tüm bekleyen `AddNew` veya **Düzenle** veritabanını kullanma kümelerinin deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Bağımlı hiçbir kayıt kümeleri `CDatabase` Nesne tanımlanmamış bir durumda bırakılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="committrans"></a>CDatabase::CommitTrans  
 İşlemleri tamamladıktan sonra bu üye işlevini çağırın.  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirmeleri başarıyla yürütüldü, sıfır olmayan; Aksi takdirde 0. Varsa **CommitTrans** başarısız olursa, veri kaynağı durumunu tanımlanmadı. Durumunu belirlemek için verileri denetlemeniz gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir dizi çağrısı için bir işlem oluşan `AddNew`, **Düzenle**, **silmek**, ve **güncelleştirme** üye işlevlerinin bir `CRecordset` ile başlayan nesne bir çağrısı [BeginTrans](#begintrans) üye işlevi. **CommitTrans** hareketi tamamlar. Varsayılan olarak, güncelleştirmeler hemen uygulanır; Çağırma **BeginTrans** kadar Gecikmeli taahhüt güncelleştirmelerin neden **CommitTrans** olarak adlandırılır.  
  
 Çağırmanız kadar **CommitTrans** bir işlemi sonlandırmak için çağırabilirsiniz [geri alma](#rollback) işlem iptal etmek ve veri kaynağı orijinal durumuna bırakmak için üye işlevi. Yeni bir işlemi başlatmak için arama **BeginTrans** yeniden.  
  
 İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Örnek  
  Makalesine bakın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="executesql"></a>CDatabase::ExecuteSQL  
 Bir SQL komutu doğrudan yürütülmesi gerektiğinde bu üye işlevini çağırın.  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSQL`  
 İşaretçi yürütmek için geçerli bir SQL komut içeren null ile sonlandırılmış bir dize. Geçirebilirsiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Komut null ile sonlandırılmış bir dize olarak oluşturun. `ExecuteSQL`veri kayıtları döndürmez. Kayıtlarda çalıştırmak istiyorsanız, bunun yerine bir kayıt kümesi nesnesi kullanın.  
  
 Bir veri kaynağı için komutların çoğu komutları verileri seçme, yeni kayıtlar ekleme, kayıt silme ve kayıtlarının düzenlenmesi için desteği kayıt kümesi nesneleri üzerinden verilir. Bazen doğrudan SQL çağrı yapmanız gerekebilir şekilde ancak, tüm ODBC işlevselliği doğrudan veritabanı sınıfları tarafından desteklenen `ExecuteSQL`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="getbookmarkpersistence"></a>CDatabase::GetBookmarkPersistence  
 Yer işaretleri kayıt kümesi nesnesi üzerinde Kalıcılık belirli işlemlerinden sonra belirlemek için bu üye işlevini çağırın.  
  
```  
DWORD GetBookmarkPersistence() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üzerinden bir kayıt kümesi nesnesinde yer işaretleri kalıcı işlemleri tanımlayan bir bit maskesi. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, çağırırsanız `CRecordset::GetBookmark` ve ardından arama `CRecordset::Requery`, yer işareti alınan `GetBookmark` artık geçerli olmayabilir. Çağırmalısınız `GetBookmarkPersistence` çağırmadan önce `CRecordset::SetBookmark`.  
  
 Dönüş değeri için birleştirilebilir bit maskesi değerleri aşağıdaki tabloda listelenmektedir `GetBookmarkPersistence`.  
  
|Bit maskesi değeri|Yer işareti kalıcılığı|  
|-------------------|--------------------------|  
|`SQL_BP_CLOSE`|Yer işaretleri sonra geçerli bir **Requery** işlemi.|  
|`SQL_BP_DELETE`|Bir satır için yer işareti sonra geçerli bir **silmek** satır işlemi.|  
|`SQL_BP_DROP`|Yer işaretleri sonra geçerli bir **Kapat** işlemi.|  
|`SQL_BP_SCROLL`|Yer işaretleri geçerli herhangi sonra **taşıma** işlemi. Yer işaretleri kayıt kümesinde destekleniyorsa, bu yalnızca tarafından döndürülen tanımlar `CRecordset::CanBookmark`.|  
|`SQL_BP_TRANSACTION`|Yer işaretleri, bir işlem yürütülmeli veya geri sonra geçerlidir.|  
|`SQL_BP_UPDATE`|Bir satır için yer işareti sonra geçerli bir **güncelleştirme** satır işlemi.|  
|`SQL_BP_OTHER_HSTMT`|Bir kayıt kümesi nesnesiyle ilişkili yer işaretleri ikinci bir kayıt kümesinde geçerli değil.|  
  
 Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevi **SQLGetInfo** Windows SDK'sındaki. Yer işaretleri hakkında daha fazla bilgi için bkz: [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="getconnect"></a>CDatabase::GetConnect  
 Çağrı sırasında kullanılan bağlantı dizesini almak için bu üye işlevini çağırın `OpenEx` veya `Open` bağlı `CDatabase` bir veri kaynağına nesnesi.  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md) bağlantı dizesini içeren `OpenEx` veya `Open` boyunca; tersi durumda, boş bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CDatabase::Open](#open) bağlantı dizesini nasıl oluşturulduğunu, açıklaması.  
  
##  <a name="getcursorcommitbehavior"></a>CDatabase::GetCursorCommitBehavior  
 Belirlemek için bu üye işlevini çağırın nasıl bir [CommitTrans](#committrans) işlemi açık kayıt nesneler üzerinde imleçler etkiler.  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açık kayıt nesneler üzerinde işlemler etkisini belirten bir değer. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda olası dönüş değerleri listelenmektedir `GetCursorCommitBehavior` ve buna karşılık gelen etkisi kayıt kümesi açar.  
  
|Dönüş değeri|CRecordset nesneleri etkisi|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Çağrı `CRecordset::Requery` işlem yürütme hemen ardından.|  
|`SQL_CB_DELETE`|Çağrı `CRecordset::Close` işlem yürütme hemen ardından.|  
|`SQL_CB_PRESERVE`|Normal şekilde devam `CRecordset` işlemleri.|  
  
 Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevi **SQLGetInfo** Windows SDK'sındaki. İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="getcursorrollbackbehavior"></a>CDatabase::GetCursorRollbackBehavior  
 Belirlemek için bu üye işlevini çağırın nasıl bir [geri alma](#rollback) işlemi açık kayıt nesneler üzerinde imleçler etkiler.  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açık kayıt nesneler üzerinde işlemler etkisini belirten bir değer. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda olası dönüş değerleri listelenmektedir `GetCursorRollbackBehavior` ve buna karşılık gelen etkisi kayıt kümesi açar.  
  
|Dönüş değeri|CRecordset nesneleri etkisi|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Çağrı `CRecordset::Requery` işlemi geri alma hemen ardından.|  
|`SQL_CB_DELETE`|Çağrı `CRecordset::Close` işlemi geri alma hemen ardından.|  
|`SQL_CB_PRESERVE`|Normal şekilde devam `CRecordset` işlemleri.|  
  
 Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevi **SQLGetInfo** Windows SDK'sındaki. İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="getdatabasename"></a>CDatabase::GetDatabaseName  
 (Veri kaynağı "veritabanı" adlı bir adlandırılmış nesneyi tanımlar olması koşuluyla) şu anda bağlı veritabanı adını almak için bu üye işlevini çağırın.  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) veritabanı adını içeren başarılı; Aksi takdirde, boş bir `CString`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu belirtilen veri kaynağı adı (DSN) ile aynı değil `OpenEx` veya **açık** çağırın. Ne `GetDatabaseName` döndürür ODBC bağlıdır. Genel olarak, bir veritabanı tabloları koleksiyonudur. Bu varlık bir ada sahipse `GetDatabaseName` değerini döndürür.  
  
 Örneğin, bu ad, bir başlık görüntülemek isteyebilirsiniz. ODBC'den, adı alınırken bir hata oluşursa, `GetDatabaseName` boş döndürür **Cstring**.  
  
##  <a name="isopen"></a>CDatabase::IsOpen  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDatabase` nesne bir veri kaynağı için şu anda bağlı.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDatabase` nesne şu anda bağlı; Aksi halde 0.  
  
##  <a name="m_hdbc"></a>CDatabase::m_hdbc  
 Bir ODBC veri kaynağı bağlantısı için ortak bir tanıtıcı içerir — bir "bağlantı tanıtıcı."  
  
### <a name="remarks"></a>Açıklamalar  
 Normalde, bu üye değişkeni doğrudan erişmek için gerekli olacaktır. Bunun yerine, çağırdığınızda framework tanıtıcı ayırır `OpenEx` veya **açık**. Çağırdığınızda framework tanıtıcı kaldırır **silmek** işlecinin `CDatabase` nesnesi. Unutmayın **Kapat** üye işlevi tanıtıcı ayırması değil.  
  
 Ancak, bazı durumlarda, tanıtıcı doğrudan kullanmanız gerekebilir. Örneğin, yerine doğrudan sınıfı aracılığıyla ODBC API işlevlerini çağırmanız gerekiyorsa `CDatabase`, parametre olarak geçirmek için bir bağlantı tanıtıcı gerekebilir. Aşağıdaki kod örneğine bakın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="onsetoptions"></a>CDatabase::OnSetOptions  
 Doğrudan bir SQL deyimi ile yürütürken framework bu üye işlevini çağırması `ExecuteSQL` üye işlevi.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parametreler  
 `hstmt`  
 Seçenekler ayarlanan ODBC deyim tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `CRecordset::OnSetOptions`Ayrıca bu üye işlevi çağırır.  
  
 `OnSetOptions`oturum açma zaman aşımı değerini ayarlar. Önceki çağrıları olduysa `SetQueryTimeout` ve üye işlevi `OnSetOptions` yansıtır geçerli değerleri; Aksi takdirde, varsayılan değerleri ayarlar.  
  
> [!NOTE]
>  MFC 4.2 önce `OnSetOptions` da işleme modunu ya da snychronous veya zaman uyumsuz olarak ayarlayın. MFC 4.2 ile başlayarak, tüm işlemleri zaman uyumlu. Zaman uyumsuz bir işlem gerçekleştirmek için doğrudan ODBC API işlevi çağrısı yapmak **SQLSetPos**.  
  
 Geçersiz kılma gerekmez `OnSetOptions` zaman aşımı değerini değiştirmek için. Sorgu zaman aşımı değerini özelleştirmek için bunun yerine, çağrı `SetQueryTimeout` ; kayıt oluşturmadan önce `OnSetOptions` yeni değeri kullanır. Değerleri kümesi tüm kayıt kümeleri veya doğrudan SQL çağrıları sonraki işlemleri için geçerlidir.  
  
 Geçersiz kılma `OnSetOptions` ek seçenekleri ayarlamak istiyorsanız. Geçersiz kılma temel sınıfı çağırmalıdır `OnSetOptions` önce veya ODBC API işlevini çağırdıktan sonra **SQLSetStmtOption**. Framework'ün varsayılan uygulamasında gösterilen yöntemi izleyin `OnSetOptions`.  
  
##  <a name="open"></a>CDatabase::Open  
 Yeni oluşturulan başlatmak için bu üye işlevini çağırın `CDatabase` nesnesi.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszDSN`  
 Bir veri kaynağı adı belirtir — bir adı ODBC Yöneticisi program aracılığıyla ODBC ile kaydedilmiş. DSN değeri belirtilmişse `lpszConnect` (biçiminde "DSN =\<veri kaynağı >"), yeniden belirtilmemelidir `lpszDSN`. Bu durumda, `lpszDSN` olmalıdır **NULL**. Aksi takdirde geçirebilirsiniz **NULL** , kullanıcı bir veri kaynağı seçebilirsiniz bir veri kaynağı iletişim kutusu ile kullanıcıya sunmak istiyorsanız. Daha fazla bilgi için açıklamalar bakın.  
  
 `bExclusive`  
 Sınıf Kitaplığı'nın bu sürümünde desteklenmiyor. Bu parametre bir onaylama işlemi şu anda başarısız **doğru**. Veri kaynağı (özel olmayan) paylaşılan olarak her zaman açıktır.  
  
 `bReadOnly`  
 **DOĞRU** salt okunur ve veri kaynağı güncelleştirmelerini önlemek için bağlantı istiyorsanız. Tüm bağımlı kayıt kümeleri, bu öznitelik devralır. Varsayılan değer **FALSE**.  
  
 `lpszConnect`  
 Bir bağlantı dizesi belirtir. Bağlantı dizesi bilgi büyük olasılıkla bir veri kaynağı adı, bir kullanıcı kimliği geçerli veri kaynağı, bir kullanıcı kimlik doğrulaması dizesi (parola, veri kaynağı bir gerektiriyorsa) ve diğer bilgileri de dahil olmak üzere, art arda ekler. Tüm bağlantı dizesi "ODBC;" dizesiyle eklenmelidir (büyük veya küçük harf). "ODBC;" dize bağlantının bir ODBC veri kaynağı için; olduğunu belirtmek için kullanılır Sınıf Kitaplığı'nın gelecek sürümlerini olmayan ODBC veri kaynaklarını desteklemiyor olabilir, bu yukarı doğru uyumluluk için olur.  
  
 `bUseCursorLib`  
 **DOĞRU** yüklenecek ODBC imleç kitaplığı DLL istiyorsanız. İmleç Kitaplığı (sürücü bunları destekliyorsa) dinamik kümeler kullanımını etkili bir şekilde engelleyen temel ODBC sürücüsü bazı işlevselliğini maskeleri. İmleç Kitaplığı yüklerse desteklenen tek imleçler statik anlık görüntüler ve yalnızca ileri İmleçler ' dir. Varsayılan değer **doğru**. Doğrudan kayıt kümesi nesnesi oluşturmak Planlama `CRecordset` buradan türetme olmadan, imleç kitaplığı yüklenmemelidir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantı başarıyla yapılırsa, sıfır olmayan; Aksi durumda kullanıcı seçerse, 0, daha fazla bağlantı bilgilerini soran bir iletişim kutusu sunulduğunda iptal edin. Diğer durumlarda, framework bir özel durum oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi nesnesi oluşturmak için kullanmadan önce veritabanı nesnesi başlatılmalıdır.  
  
> [!NOTE]
>  Çağırma [OpenEx](#openex) üye işlevi olan bir veri kaynağına bağlanmak ve veritabanı nesneyi başlatmak için tercih edilen yöntem.  
  
 Varsa parametrelerinde, **açık** çağrısı bağlantı oluşturmak için yeterli bilgi içermiyor, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır. Çağırdığınızda **açık**, bağlantı dizenizi `lpszConnect`, özel olarak içinde depolanan `CDatabase` nesne ve çağırarak kullanılabilir [GetConnect](#getconnect) üye işlevi.  
  
 İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz **açmak** kullanıcıdan bir parola gibi bilgileri almak için daha sonra bu bilgileri geçirmek için bağlantı dizesi ekleyin **açmak**. Veya sonraki yeniden şekilde geçirdiğiniz bağlantı dizesini uygulama çağrılarınızı zaman isteyebilirsiniz **açık** üzerinde bir `CDatabase` nesnesi.  
  
 Oturum açma yetkilendirme birden çok düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDatabase` nesnesi) veya diğer veri kaynağı özgü bilgileri iletmek için. Bağlantı dizeleri hakkında daha fazla bilgi için bkz: Windows SDK'da bölüm 5.  
  
 Örneğin, DBMS konak kullanılamıyorsa, bağlantı girişimi zaman aşımına mümkündür. Bağlantı denemesi başarısız olursa, **açık** oluşturur bir `CDBException`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="openex"></a>CDatabase::OpenEx  
 Yeni oluşturulan başlatmak için bu üye işlevini çağırın `CDatabase` nesnesi.  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszConnectString`  
 Bir ODBC bağlantı dizesi belirtir. Bu veri kaynağı adı ve bunun yanı sıra kullanıcı kimliği ve parola gibi diğer isteğe bağlı bilgiler içerir. Örneğin, "DSN = SQLServer_Source; UID = SA; PWD abc123 = "olası bağlantı dizesi. Geçirdiğiniz gerçekleştiriyorsanız **NULL** için `lpszConnectString`, bir veri kaynağı iletişim kutusu veri kaynağı seçmek için kullanıcıyı uyarır.  
  
 `dwOptions`  
 Aşağıdaki değerleri bileşimini belirten bir bit maskesi. Varsayılan değer 0'dır veritabanı olarak açılacak anlamı yazma erişimi paylaşılan, ODBC imleç kitaplığı DLL yüklenmeyecek ve yalnızca yoksa bağlantı oluşturmak için yeterli bilgi ODBC bağlantı iletişim kutusu görüntülenir.  
  
- **CDatabase::openExclusive** Sınıf Kitaplığı'nın bu sürümünde desteklenmiyor. Bir veri kaynağı (özel olmayan) paylaşılan olarak her zaman açıktır. Şu anda, bu seçeneği belirtirseniz, bir onaylama işlemi başarısız olur.  
  
- **CDatabase::openReadOnly** veri kaynağı salt okunur olarak açın.  
  
- **CDatabase::useCursorLib** ODBC imleç kitaplığı DLL yüklenemiyor. İmleç Kitaplığı (sürücü bunları destekliyorsa) dinamik kümeler kullanımını etkili bir şekilde engelleyen temel ODBC sürücüsü bazı işlevselliğini maskeleri. İmleç Kitaplığı yüklerse desteklenen tek imleçler statik anlık görüntüler ve yalnızca ileri İmleçler ' dir. Doğrudan kayıt kümesi nesnesi oluşturmak Planlama `CRecordset` buradan türetme olmadan, imleç kitaplığı yüklenmemelidir.  
  
- **CDatabase::noOdbcDialog** yeterli bağlantı bilgilerini olup sağlanan bağımsız olarak ODBC bağlantı iletişim kutusu, gösterme.  
  
- **CDatabase::forceOdbcDialog** her zaman ODBC bağlantı iletişim kutusu görüntüler.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlantı başarıyla yapılırsa, sıfır olmayan; Aksi durumda kullanıcı seçerse, 0, daha fazla bağlantı bilgilerini soran bir iletişim kutusu sunulduğunda iptal edin. Diğer durumlarda, framework bir özel durum oluşturur.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi nesnesi oluşturmak için kullanmadan önce veritabanı nesnesi başlatılmalıdır.  
  
 Varsa `lpszConnectString` parametresinde, `OpenEx` çağrısı bağlantı oluşturmak için yeterli bilgi içermiyor, ayarlanmamış koşuluyla ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır **CDatabase:: noOdbcDialog** veya **CDatabase::forceOdbcDialog** içinde `dwOptions` parametresi. Çağırdığınızda `OpenEx`, bağlantı dizenizi `lpszConnectString`, özel olarak içinde depolanan `CDatabase` nesne ve çağırarak kullanılabilir [GetConnect](#getconnect) üye işlevi.  
  
 İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz `OpenEx` kullanıcıdan bir parola gibi bilgi almak ve sonra bu bilgileri geçirmek için bağlantı dizesi eklemek için `OpenEx`. Veya sonraki yeniden şekilde geçirdiğiniz bağlantı dizesini uygulama çağrılarınızı zaman isteyebilirsiniz `OpenEx` üzerinde bir `CDatabase` nesnesi.  
  
 Oturum açma yetkilendirme birden çok düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDatabase` nesnesi) veya diğer veri kaynağı özgü bilgileri iletmek için. Bağlantı dizeleri hakkında daha fazla bilgi için bkz: Bölüm 6 ' *ODBC Programcının Başvurusu*.  
  
 Örneğin, DBMS konak kullanılamıyorsa, bağlantı girişimi zaman aşımına mümkündür. Bağlantı denemesi başarısız olursa, `OpenEx` oluşturur bir `CDBException`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="rollback"></a>CDatabase::Rollback  
 İşlem sırasında yapılan değişiklikleri geri almak için bu üye işlevini çağırın.  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlem başarıyla tersine, sıfır olmayan; Aksi takdirde 0. Varsa bir **geri alma** çağrısı başarısız olursa, veri kaynağı ve işlem durumlarıdır tanımlanmamış. Varsa **geri alma** 0 döndürür durumunu belirlemek için veri kaynağı işaretlemeniz gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm `CRecordset` `AddNew`, **Düzenle**, **silmek**, ve **güncelleştirme** en son yürütülen çağrıları [BeginTrans](#begintrans) alınır Bu çağrı aynı anda var olan durumuna geri.  
  
 Çağrı sonra **geri alma**, işlem sona erdi ve çağırmalısınız **BeginTrans** başka bir işlem için yeniden. Aradığınız önce geçerli kayıt **BeginTrans** geçerli kayıt yeniden sonra olur **geri alma**.  
  
 Bir geri alma sonra geri alma önce geçerli kayıt geçerli olmaya devam eder. Kayıt kümesi ve bir geri alma sonra veri kaynağı durumu hakkında daha fazla ayrıntı için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Örnek  
  Makalesine bakın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="setlogintimeout"></a>CDatabase::SetLoginTimeout  
 Bu üye işlevini çağırın — çağırmadan önce `OpenEx` veya **açık** — bir veri önce izin verilen saniye varsayılan sayısını geçersiz kılmak için kaynak bağlantı zaman aşımına uğruyor.  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwSeconds`  
 Önce bir bağlantı girişimini izin vermek için saniye sayısını zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, DBMS kullanılabilir durumda değilse, bağlantı girişimi zaman aşımı olabilir. Çağrı **SetLoginTimeout** başlatılmamış oluşturduktan sonra `CDatabase` nesne ancak aramadan önce `OpenEx` veya **açık**.  
  
 Oturum açma zaman aşımı için varsayılan değer 15 saniyedir. Tüm veri kaynakları bir oturum açma zaman aşımı değeri belirtmek için özelliğini destekler. Veri kaynağı zaman aşımı desteklemiyorsa, izleme çıktısı, ancak bir özel alın. 0 değeri, "sonsuz." anlamına gelir  
  
##  <a name="setquerytimeout"></a>CDatabase::SetQueryTimeout  
 Bağlı veri kaynağı zaman aşımı sonraki işlemlerde önce izin vermek için saniye varsayılan sayısını geçersiz kılma için bu üye işlevini çağırın.  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwSeconds`  
 Bir sorguyu denemeden önce izin vermek için saniye sayısını zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işlem ağ erişim sorunları, aşırı sorgu işleme süresini ve benzeri nedeniyle zaman. Çağrı `SetQueryTimeout` kümenizin açmadan önce veya kayıt kümesinin çağırmadan önce `AddNew`, **güncelleştirme** veya **silmek** üye işlevlerini sorgu zaman aşımı değeri değiştirmek istiyorsanız. Ayar sonraki tüm etkiler **açık**, `AddNew`, **güncelleştirme**, ve **silmek** bu ile ilişkili tüm kayıt kümeleri çağrıları `CDatabase` nesnesi. Bir kayıt kümesi için sorgu zaman aşımı değeri açıldıktan sonra değiştirme kayıt değeri değiştirmez. Örneğin, sonraki **taşıma** işlemleri, yeni değer kullanmayın.  
  
 Sorgu zaman aşımı için varsayılan değer 15 saniyedir. Tüm veri kaynakları sorgu zaman aşımı değerini ayarlama özelliği destekler. Bir sorgu zaman aşımı değeri 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; veri kaynağı ile iletişimi yanıt vermeyebilir. Bu davranış geliştirme sırasında yararlı olabilir. Veri kaynağı zaman aşımı desteklemiyorsa, izleme çıktısı, ancak bir özel alın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
