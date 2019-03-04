---
title: CDatabase sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 0e523b2a145254cd9b7adf2b066605a679349f6c
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57273458"
---
# <a name="cdatabase-class"></a>CDatabase sınıfı

Veri kaynağı üzerinde çalışabileceğiniz bir veri kaynağı bağlantısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase::CDatabase](#cdatabase)|Oluşturur bir `CDatabase` nesne. Nesne çağırarak başlatmalıdır `OpenEx` veya `Open`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase::BeginTrans](#begintrans)|Bir "işlem" başlar — bir dizi ters çevrilebilir çağrıda `AddNew`, `Edit`, `Delete`, ve `Update` sınıfın üye işlevleri `CRecordset` — bağlı veri kaynağı. Veri kaynağı için işlem desteklemelidir `BeginTrans` herhangi bir etkisi olması.|
|[CDatabase::BindParameters](#bindparameters)|Çağırmadan önce parametleri bağlamak tanır `CDatabase::ExecuteSQL`.|
|[CDatabase::Cancel](#cancel)|Zaman uyumsuz bir işlem veya ikinci bir iş parçacığı bir işlem iptal eder.|
|[CDatabase::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa, sıfır döndürür.|
|[CDatabase::CanUpdate](#canupdate)|Döndürür gösterimiyse `CDatabase` nesne güncelleştirilebilir değil (salt okunur).|
|[CDatabase::Close](#close)|Veri kaynağı bağlantısı kapatır.|
|[CDatabase::CommitTrans](#committrans)|Bir işlem tarafından başlamış tamamlandıktan `BeginTrans`. Veri kaynağını etkileyen komutlar işlemde gerçekleştirilir.|
|[CDatabase:: Executesql'den](#executesql)|Bir SQL deyimi yürütür. Hiç veri kaydı döndürülür.|
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|Kayıt kümesi nesnelerde yer işaretleri üzerinden kalıcı işlemler belirtilmektedir.|
|[CDatabase::GetConnect](#getconnect)|Bağlanmak için kullanılan ODBC bağlantı dizesi döndürür `CDatabase` bir veri kaynağı nesnesi.|
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|Bir açık kayıt nesne üzerinde bir işlem Sistemi'ne etkisini tanımlar.|
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|Bir açık kayıt nesne üzerinde bir işlemin geri alınması etkisini tanımlar.|
|[CDatabase::GetDatabaseName](#getdatabasename)|Veritabanının adı, şu anda kullanımda döndürür.|
|[CDatabase::IsOpen](#isopen)|Döndürür gösterimiyse `CDatabase` nesnesi şu anda bir veri kaynağına bağlı.|
|[CDatabase::OnSetOptions](#onsetoptions)|Standart bağlantı seçeneklerini ayarlamak için framework tarafından çağırılır. Varsayılan uygulama, sorgu zaman aşımı değerini ayarlar. Çağırarak bu seçenekler önceden kurup `SetQueryTimeout`.|
|[Sihirbazda](#open)|Bir veri kaynağı (ODBC sürücüsü aracılığıyla bir) bir bağlantı kurar.|
|[CDatabase::OpenEx](#openex)|Bir veri kaynağı (ODBC sürücüsü aracılığıyla bir) bir bağlantı kurar.|
|[CDatabase::Rollback](#rollback)|Geçerli işlem sırasında yapılan değişiklikleri geri alır. Veri kaynağı olarak tanımlanan önceki durumuna döndürür `BeginTrans` değiştirilmeden çağrısı.|
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Bir veri kaynağı bağlantı denemesi sonra zaman aşımına olacak saniye sayısını ayarlar.|
|[CDatabase::SetQueryTimeout](#setquerytimeout)|İşlem Sorgusu saniye sonra hangi veritabanı sayısını ayarlar zaman aşımına uğrar. Tüm sonraki kayıt etkiler `Open`, `AddNew`, `Edit`, ve `Delete` çağırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase::m_hdbc](#m_hdbc)|Bir veri kaynağına açık veritabanı bağlantısı (ODBC) bağlantı tanıtıcısı. Tür *HDBC*.|

## <a name="remarks"></a>Açıklamalar

Bir veri kaynağı, bazı veritabanı yönetim sistemi (DBMS) tarafından barındırılan bir veri, belirli bir örneğidir. Microsoft SQL Server, Microsoft Access, Borland'da dBASE ve xBASE verilebilir. Bir veya daha fazla olabilir `CDatabase` nesneleri, uygulamanız bir anda etkin.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, sınıf kullanmak [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) yerine. Daha fazla bilgi için bkz [genel bakış: Veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Kullanılacak `CDatabase`, oluşturun bir `CDatabase` nesne ve çağrı kendi `OpenEx` üye işlevi. Bu, bir bağlantı açar. Ardından oluşturmak zaman `CRecordset` bağlı veri kaynağı üzerinde çalışmak nesnelerini geçirmek kayıt oluşturucusu için bir işaretçi, `CDatabase` nesne. Bağlantıyı kullanmayı bitirdiğinizde, çağrı `Close` üye işlevi ve yok et `CDatabase` nesne. `Close` önceden kapattıysanız değil tüm kayıt kümelerini kapatır.

Hakkında daha fazla bilgi için `CDatabase`, makalelere göz atın [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) ve [genel bakış: Veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="begintrans"></a>  CDatabase::BeginTrans

Bağlı veri kaynağı ile bir işlem başlatmak için bu üye işlevini çağırın.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrı başarılı olmuş ve yalnızca el ile geçildiğinde değişiklikler yapılır olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazla işlem oluşan `AddNew`, `Edit`, `Delete`, ve `Update` üye işlevlerinin bir `CRecordset` nesne. Bir işlem başlamadan önce `CDatabase` nesnesi gerekir zaten bağlı veri kaynağına çağırarak kendi `OpenEx` veya `Open` üye işlevi. İşlemin sona erdirmek için çağrı [CommitTrans](#committrans) veri kaynağında yapılan tüm değişiklikler kabul (ve bunları yürütmek için) veya çağrı [geri alma](#rollback) tüm işlem durdurulacak. Çağrı `BeginTrans` sonra işlem sırasında katılan tüm kayıt kümelerini açın ve olarak gerçek yakın güncelleştirme işlemlerini mümkün olduğunca.

> [!CAUTION]
>  ODBC sürücüsünün bağlı olarak, bir kayıt kümesi çağırmadan önce açma `BeginTrans` çağırırken sorunlara neden `Rollback`. Kullanmakta olduğunuz belirli sürücü denetlemeniz gerekir. Örneğin, Microsoft ODBC Masaüstü Sürücü Paketi 3.0 dahil Microsoft Access sürücüsü kullanılırken, açık bir imleç sahip herhangi bir veritabanı üzerinde bir işlem başlamamalıdır Jet veritabanı altyapısının gereksinim için dikkate alması gerekir. MFC veritabanı sınıfları açık bir imleç açık anlamına gelir. `CRecordset` nesne. Daha fazla bilgi için [Teknik Not 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).

`BeginTrans` Ayrıca veri kayıtlarının sunucuda istenen eşzamanlılık ve veri kaynağının özelliklerini bağlı olarak, kilit. Kilitleme veriler hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

İşlem kullanıcı tarafından tanımlanan makalesinde açıklanan [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

`BeginTrans` istediğiniz işlem dizisini gerçekleştirilen adımların geri alınması durumunda kurar (tersine). Geri alma işlemleri için yeni bir durum oluşturmak için geçerli bir işlem işleme sonra çağrı `BeginTrans` yeniden.

> [!CAUTION]
>  Çağırma `BeginTrans` yeniden çağırmadan `CommitTrans` veya `Rollback` bir hatadır.

Çağrı [CanTransact](#cantransact) sürücünüz işlemleri için belirli bir veritabanı destekleyip desteklemediğini belirlemek için üye işlevi. Ayrıca çağırmalıdır [GetCursorCommitBehavior](#getcursorcommitbehavior) ve [GetCursorRollbackBehavior](#getcursorrollbackbehavior) imleç korunması desteğini belirlemek için.

İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  Makaleye göz atın [işlem: (ODBC) kayıt kümesinde işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="bindparameters"></a>  CDatabase::BindParameters

Geçersiz kılma `BindParameters` çağırmadan önce parametleri bağlamak gerektiğinde [CDatabase:: Executesql'den](#executesql).

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*hstmt*<br/>
Parametleri bağlamak istediğiniz ODBC deyim tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Bu yaklaşım, sonuç gerekmediğinde yararlıdır bir saklı yordamdan ayarlayın.

Geçersiz kılmada çağrı `SQLBindParameters` ve ilgili parametleri bağlamak için ODBC işlevleri. MFC çağrınız önce geçersiz kılma çağrıları `ExecuteSQL`. Çağrı gerekmez `SQLPrepare`; `ExecuteSQL` çağrıları `SQLExecDirect` ve yok eder *hstmt*, yalnızca bir kez kullanılır.

##  <a name="cancel"></a>  CDatabase::Cancel

Veri kaynağı zaman uyumsuz bir işlem devam ediyor ya da bir işlemin ikinci bir iş parçacığından iptal istemek için bu üye işlevini çağırın.

```
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıfları artık zaman uyumsuz işleme kullandığını unutmayın. bir Aracıdan işlemi gerçekleştirmek için doğrudan ODBC API işlevini çağırmanız gerekir [SQLSetConnectOption](/previous-versions/windows/desktop/ms713564). Daha fazla bilgi için [zaman uyumsuz yürütme](/previous-versions/windows/desktop/ms713563) Windows SDK.

##  <a name="cantransact"></a>  CDatabase::CanTransact

Veritabanı işlemleri izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnız bu kullanarak kayıt kümelerini `CDatabase` nesnenin izin işlemleri; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>  CDatabase::CanUpdate

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDatabase` nesne güncelleştirmeler sağlar.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yalnız `CDatabase` nesne güncelleştirmeleri sağlar; Aksi durumda 0 ya da sizin belirten TRUE geçirilen *bReadOnly* açtığınızda `CDatabase` nesne veya veri kendisini kaynağı salt okunur. Veri kaynağı salt okunur bir çağrı, ODBC API işlevine `SQLGetInfo` SQL_DATASOURCE_READ_ONLY "y" döndürür.

### <a name="remarks"></a>Açıklamalar

Tüm sürücüleri güncelleştirmelerini destekler.

##  <a name="cdatabase"></a>  CDatabase::CDatabase

Oluşturur bir `CDatabase` nesne.

```
CDatabase();
```

### <a name="remarks"></a>Açıklamalar

Nesne oluşturduktan sonra çağırmanız gerekir, `OpenEx` veya `Open` belirtilen veri kaynağı ile bağlantı kurmak için üye işlevi.

Eklemek kullanışlı bulabilirsiniz `CDatabase` belge sınıfınızdaki nesne.

### <a name="example"></a>Örnek

Bu örnekte kullanılması gösterilmektedir `CDatabase` içinde bir `CDocument`-türetilmiş sınıf.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

##  <a name="close"></a>  CDatabase::Close

Bir veri kaynağından bağlantısını kesmek istiyorsanız, bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

İle ilişkili tüm kayıt kümelerini kapatmalısınız `CDatabase` bu üye işlevini çağırmadan önce nesne. Çünkü `Close` yok `CDatabase` yeniden nesne aynı veri kaynağına veya farklı bir veri kaynağı için yeni bir bağlantı açarak nesnesi.

Tüm bekleyen `AddNew` veya `Edit` veritabanını kullanarak kümelerinin deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Bağımlı tüm kayıt kümelerini `CDatabase` Nesne tanımlanmamış bir durumda bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

##  <a name="committrans"></a>  CDatabase::CommitTrans

İşlemleri tamamladıktan sonra bu üye işlevini çağırın.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirmeler başarıyla yürütüldü olursa sıfır dışı; Aksi durumda 0. Varsa `CommitTrans` başarısız olursa, veri kaynağının durumu tanımsızdır. Durumunu belirlemek için verileri denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Bir dizi çağrıda bir işlem oluşan `AddNew`, `Edit`, `Delete`, ve `Update` üye işlevlerinin bir `CRecordset` çağrısı ile başlayan nesne [BeginTrans](#begintrans) üye işlevi. `CommitTrans` hareketi tamamlar. Varsayılan olarak, güncelleştirmeler hemen kaydedilir; Çağırma `BeginTrans` kadar geciktirileceği taahhüt güncelleştirmelerin neden `CommitTrans` çağrılır.

Çağırana kadar `CommitTrans` bir işlemi sonlandırmak için çağırabilirsiniz [geri alma](#rollback) işlem durdurma ve ilk durumu veri kaynağı bırakmak için üye işlevi. Yeni bir işlem başlatmak için çağrı `BeginTrans` yeniden.

İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  Makaleye göz atın [işlem: (ODBC) kayıt kümesinde işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="executesql"></a>  CDatabase:: Executesql'den

Doğrudan SQL komutu yürütmek gerektiğinde bu üye işlevini çağırın.

```
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütmek için geçerli bir SQL komut içeren null ile sonlandırılmış bir dize işaretçisi. Geçirebilirsiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Açıklamalar

Komut null ile sonlandırılmış bir dize olarak oluşturun. `ExecuteSQL` veri kayıtlarının döndürmez. Kayıtlar üzerinde çalışmak istiyorsanız, bir kayıt kümesi nesnesi kullanın.

Bir veri kaynağı için komutların çoğu, verileri seçme, yeni kayıtlar ekleme, kayıtları silme ve kayıtlarının düzenlenmesi için komutları destekleyen kayıt nesneler aracılığıyla verilir. Bazen ile doğrudan SQL çağrı yapmak gerekebilir ancak tüm ODBC işlevselliği doğrudan veritabanı sınıfları tarafından desteklenir. Bu sayede `ExecuteSQL`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

##  <a name="getbookmarkpersistence"></a>  CDatabase::GetBookmarkPersistence

Kayıt kümesi nesnesi yer işaretlerini sürekliliği sonra belirli işlemleri belirlemek için bu üye işlevini çağırın.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesi nesnesi üzerinde yer işaretleri üzerinden kalıcı işlemleri tanımlayan bir bit maskesi. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Örneğin, eğer `CRecordset::GetBookmark` ve sonra çağrı `CRecordset::Requery`, yer işareti alınan `GetBookmark` artık geçerli olmayabilir. Çağırmalısınız `GetBookmarkPersistence` çağırmadan önce `CRecordset::SetBookmark`.

Aşağıdaki tablo, dönüş değeri için birleştirilebilen bit maskesi değerleri listeler `GetBookmarkPersistence`.

|Bit maskesi değeri|Yer işareti kalıcılığı|
|-------------------|--------------------------|
|SQL_BP_CLOSE|Yer işaretleri sonra geçerli bir `Requery` işlemi.|
|SQL_BP_DELETE|Bir satır için yer işareti sonra geçerli bir `Delete` satırının işlemi.|
|SQL_BP_DROP|Yer işaretleri sonra geçerli bir `Close` işlemi.|
|SQL_BP_SCROLL|Yer işaretleri geçerli herhangi sonra `Move` işlemi. Kayıt kümesi üzerinde yer işaretleri destekleniyorsa bu yalnızca tarafından döndürülen tanımlar `CRecordset::CanBookmark`.|
|SQL_BP_TRANSACTION|Bir işlem kaydedilmiş veya geri alınmış sonra yer işaretlerini geçerlidir.|
|SQL_BP_UPDATE|Bir satır için yer işareti sonra geçerli bir `Update` satırının işlemi.|
|SQL_BP_OTHER_HSTMT|Bir kayıt kümesi nesnesi ile ilişkili yer işaretleri, ikinci kayıt üzerinde geçerlidir.|

Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevini `SQLGetInfo` Windows SDK. Yer işaretleri hakkında daha fazla bilgi için bkz [kayıt kümesi: Yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="getconnect"></a>  CDatabase::GetConnect

Çağrı sırasında kullanılan bağlantı dizesini almak için bu üye işlevi çağrısı `OpenEx` veya `Open` bağlı `CDatabase` bir veri kaynağı nesnesi.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const**[CString](../../atl-mfc-shared/reference/cstringt-class.md) bağlantı dizesini içeren `OpenEx` veya `Open` olan; tersi durumda, boş bir dize.

### <a name="remarks"></a>Açıklamalar

Bkz: [CDatabase::Open](#open) için bağlantı dizesini nasıl oluşturulduğunu açıklaması.

##  <a name="getcursorcommitbehavior"></a>  CDatabase::GetCursorCommitBehavior

Belirlemek için bu üye işlevi çağrısı nasıl bir [CommitTrans](#committrans) işlemi açık kayıt nesnelerine işaretçiler etkiler.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt nesneler üzerinde işlem etkisini gösteren bir değer. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda olası dönüş değerleri listelenmektedir `GetCursorCommitBehavior` ve açık bir kayıt kümesi üzerindeki etkisini.

|Dönüş değeri|CRecordset nesneleri etkisi|
|------------------|----------------------------------|
|SQL_CB_CLOSE|Çağrı `CRecordset::Requery` hareket işleme hemen ardından.|
|SQL_CB_DELETE|Çağrı `CRecordset::Close` hareket işleme hemen ardından.|
|SQL_CB_PRESERVE|Normal olarak devam `CRecordset` operations.|

Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevini `SQLGetInfo` Windows SDK. İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getcursorrollbackbehavior"></a>  CDatabase::GetCursorRollbackBehavior

Belirlemek için bu üye işlevi çağrısı nasıl bir [geri alma](#rollback) işlemi açık kayıt nesnelerine işaretçiler etkiler.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt nesneler üzerinde işlem etkisini gösteren bir değer. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda olası dönüş değerleri listelenmektedir `GetCursorRollbackBehavior` ve açık bir kayıt kümesi üzerindeki etkisini.

|Dönüş değeri|CRecordset nesneleri etkisi|
|------------------|----------------------------------|
|SQL_CB_CLOSE|Çağrı `CRecordset::Requery` işlemi geri alma hemen ardından.|
|SQL_CB_DELETE|Çağrı `CRecordset::Close` işlemi geri alma hemen ardından.|
|SQL_CB_PRESERVE|Normal olarak devam `CRecordset` operations.|

Bu dönüş değeri hakkında daha fazla bilgi için bkz: ODBC API işlevini `SQLGetInfo` Windows SDK. İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getdatabasename"></a>  CDatabase::GetDatabaseName

("Veritabanı" olarak adlandırılan bir adlandırılmış bir nesne veri kaynağı tanımlar şartıyla) şu anda bağlı veritabanı adını almak için bu üye işlevini çağırın.

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) boş bir veritabanı adı içeren başarılı; Aksi takdirde, `CString`.

### <a name="remarks"></a>Açıklamalar

Bu belirtilen veri kaynağı adı (DSN) aynı değil `OpenEx` veya `Open` çağırın. Hangi `GetDatabaseName` döndürür ODBC bağlıdır. Genel olarak, bir veritabanı tabloları bir koleksiyonudur. Bu varlık, bir adı varsa `GetDatabaseName` döndürür.

Örneğin, bu ad bir başlığa görüntülemek isteyebilirsiniz. ODBC'den, adı alınırken bir hata oluşursa `GetDatabaseName` boş döndürür `CString`.

##  <a name="isopen"></a>  CDatabase::IsOpen

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDatabase` nesnesi şu anda bir veri kaynağına bağlı.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CDatabase` nesnesi şu anda bağlı; Aksi durumda 0.

##  <a name="m_hdbc"></a>  CDatabase::m_hdbc

Bir ODBC veri kaynağı bağlantısı için ortak bir tanıtıcı içeriyor: "bağlantı tanıtıcı."

### <a name="remarks"></a>Açıklamalar

Normalde, bu üye değişkeni doğrudan bağlanmasına gerek sahip olur. Bunun yerine, framework tanıtıcı ayırır çağırdığınızda `OpenEx` veya `Open`. Çağırdığınızda framework tanıtıcı kaldırır **Sil** işlecinin `CDatabase` nesne. Unutmayın `Close` üye işlevi, tanıtıcıyı serbest değil.

Ancak, bazı durumlarda, doğrudan tanıtıcı kullanmanız gerekebilir. Örneğin, yerine doğrudan sınıfı aracılığıyla ODBC API işlevleri çağırmak gerekiyorsa `CDatabase`, parametre olarak geçirmek için bir bağlantı tanıtıcısı gerekebilir. Aşağıdaki kod örneği bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

##  <a name="onsetoptions"></a>  CDatabase::OnSetOptions

Bu üye işlevi, doğrudan bir SQL deyimi ile yürütürken framework çağırır `ExecuteSQL` üye işlevi.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*hstmt*<br/>
Seçenekleri ayarlanan ODBC deyim tanıtıcı.

### <a name="remarks"></a>Açıklamalar

`CRecordset::OnSetOptions` Ayrıca, bu üye işlevini çağırır.

`OnSetOptions` oturum açma zaman aşımı değerini ayarlar. Önceki çağrıları olduğunda `SetQueryTimeout` ve üye işlevini `OnSetOptions` ; geçerli değerleri yansıtır. Aksi takdirde, varsayılan değerleri ayarlar.

> [!NOTE]
>  MFC 4.2 önce `OnSetOptions` da işleme modunu ya da snychronous veya zaman uyumsuz olarak ayarlayın. MFC 4.2 ile başlayarak, tüm işlemleri eşzamanlıdır. Zaman uyumsuz bir işlemi gerçekleştirmek için ODBC API işlevini doğrudan çağrı yapmak `SQLSetPos`.

Geçersiz kılma gerekmez `OnSetOptions` zaman aşımı değerini değiştirmek için. Sorgu zaman aşımı değerini özelleştirmek için bunun yerine çağrı `SetQueryTimeout` bir kayıt kümesi; oluşturmadan önce `OnSetOptions` yeni değeri kullanır. Değerler ayarlanmış tüm kayıt kümelerini veya doğrudan SQL çağrıları sonraki işlemleri için geçerlidir.

Geçersiz kılma `OnSetOptions` ek seçenekleri ayarlamak istiyorsanız. Geçersiz taban sınıf çağırmalıdır `OnSetOptions` önce veya etkinleştirdikten sonra ODBC API işlevini çağırmak `SQLSetStmtOption`. Framework'ün varsayılan uygulamasında gösterilen yöntemi izleyin `OnSetOptions`.

##  <a name="open"></a>  Sihirbazda

Yeni oluşturulan başlatmak için bu üye işlevi çağrısı `CDatabase` nesne.

```
virtual BOOL Open(
    LPCTSTR lpszDSN,
    BOOL bExclusive = FALSE,
    BOOL bReadOnly = FALSE,
    LPCTSTR lpszConnect = _T("ODBC;"),
    BOOL bUseCursorLib = TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszDSN*<br/>
Bir veri kaynağı adı belirtir; bir adı, ODBC Yöneticisi program aracılığıyla ODBC ile kaydedilmiş. DSN değeri belirtilmişse *lpszConnect* (biçiminde "DSN =\<veri kaynağı >"), yeniden belirtilmemelidir *lpszDSN*. Bu durumda, *lpszDSN* NULL olmalıdır. Aksi takdirde, kullanıcı bir veri kaynağı iletişim kutusu kullanıcı bir veri kaynağı seçebilir sunmak istiyorsanız, NULL geçirebilirsiniz. Daha fazla bilgi için açıklamalara bakın.

*bExclusive*<br/>
Sınıf Kitaplığı'nın bu sürümünde desteklenmiyor. Bu parametre TRUE ise, şu anda bir onaylama işlemi başarısız olur. Veri kaynağı her zaman (özel olmayan) paylaşılan olarak açılır.

*bReadOnly*<br/>
Salt okunur ve güncelleştirmeleri veri kaynağına yasaklamak için bağlantı istiyorsanız TRUE. Bu özniteliğe bağımlı tüm kayıt kümelerini devralır. Varsayılan değer FALSE olur.

*lpszConnect*<br/>
Bir bağlantı dizesi belirtir. Bağlantı dizesi olasılıkla veri kaynağı adı, veri kaynağı, bir kullanıcı kimlik doğrulama dizesi (parola, veri kaynağı gerekli kılmışsa) ve diğer bilgileri geçerli bir kullanıcı kimliği gibi bilgileri art arda ekler. Tüm bağlantı dizesi "ODBC;" dizesiyle önek eklenmelidir (büyük veya küçük harf). "ODBC;" dizesi, bağlantının bir ODBC veri kaynağında olduğunu belirtmek için kullanılır Sınıf Kitaplığı'nın gelecekteki sürümleri olmayan bir ODBC veri kaynaklarını desteklemiyor olabilir, bu yukarı doğru uyumluluk için olur.

*bUseCursorLib*<br/>
ODBC imleç kitaplığı DLL yüklenecek istiyorsanız TRUE. İmleç Kitaplığı, temel alınan ODBC sürücüsünün (sürücü bunları destekliyorsa) etkili bir şekilde dynaset'ler kullanımını engelleyen, bazı işlevler maskeler. İmleç Kitaplığı yüklenirse desteklenen yalnızca işaretçiler statik anlık görüntüler ve yalnızca iletme İmleçler ' dir. Varsayılan değer True'dur. Doğrudan kayıt kümesi nesnesi oluşturmak Planlama `CRecordset` ondan türetilen olmadan, imleç kitaplığı yüklenmemelidir.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarılı olursa sıfır dışı; Aksi takdirde kullanıcı seçerse 0 için daha fazla bağlantı bilgilerini soran bir iletişim kutusu yansıtılırken iptal edin. Diğer durumlarda, framework özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanmadan önce veritabanı nesnesi başlatılmalıdır.

> [!NOTE]
>  Çağırma [OpenEx](#openex) üye işlevi, bir veri kaynağına bağlanmak ve veritabanını nesneyi başlatmak için tercih edilen yoludur.

Parametreleri, `Open` çağrı bağlantı kurmak için yeterli bilgi içermiyor, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır. Çağırdığınızda `Open`, bağlantı dizenizi *lpszConnect*, özel olarak içinde depolanan `CDatabase` nesne ve nolu telefonu arayarak [GetConnect](#getconnect) üye işlevi.

İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz `Open` kullanıcıdan bir parola gibi bilgileri almak için daha sonra bu bilgileri geçirmek için bağlantı dizesi ekleyin `Open`. Veya sonraki yeniden kullanabilmesi geçirdiğiniz bağlantı dizesini, uygulama çağrıları zaman isteyebileceğiniz `Open` üzerinde bir `CDatabase` nesne.

Birden çok oturum açma yetkilendirme düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDatabase` nesne) veya diğer veri kaynağına özgü bilgileri iletmek için. Bölüm 5'te Windows SDK'sı bağlantı dizeleri hakkında daha fazla bilgi için bkz.

Örneğin, DBMS konak kullanılamıyorsa, zaman aşımı bağlanma girişimi için mümkündür. Bağlantı denemesi başarısız olursa `Open` oluşturur bir `CDBException`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

##  <a name="openex"></a>  CDatabase::OpenEx

Yeni oluşturulan başlatmak için bu üye işlevi çağrısı `CDatabase` nesne.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszConnectString*<br/>
Bir ODBC bağlantı dizesini belirtir. Bu veri kaynağı adı ve bunun yanı sıra kullanıcı kimliği ve parola gibi diğer isteğe bağlı bilgiler içerir. Örneğin, "DSN SQLServer_Source; = UID; SA = PWD abc123 = "olası bağlantı dizesi. NULL geçirmek gerçekleştiriyorsanız *lpszConnectString*, bir veri kaynağı iletişim kutusu bir veri kaynağı seçmek için kullanıcıyı uyarır.

*dwOptions*<br/>
Aşağıdaki değerleri birleşimi belirten bir bit maskesi. Varsayılan değer 0 ' dır yazma erişimi ile paylaşılan, ODBC imleç kitaplığı DLL yüklenmeyecek veritabanı olarak açılacak anlamına gelir ve yalnızca yoksa bağlantı kurmak için yeterli bilgi ODBC bağlantı iletişim kutusu görüntülenir.

- `CDatabase::openExclusive` Sınıf Kitaplığı'nın bu sürümünde desteklenmiyor. Bir veri kaynağı her zaman (özel olmayan) paylaşılan olarak açılır. Şu anda, bu seçeneği belirtirseniz, bir onaylama işlemi başarısız olur.

- `CDatabase::openReadOnly` Veri kaynağı salt okunur olarak açın.

- `CDatabase::useCursorLib` ODBC imleç kitaplığı DLL yükleyin. İmleç Kitaplığı, temel alınan ODBC sürücüsünün (sürücü bunları destekliyorsa) etkili bir şekilde dynaset'ler kullanımını engelleyen, bazı işlevler maskeler. İmleç Kitaplığı yüklenirse desteklenen yalnızca işaretçiler statik anlık görüntüler ve yalnızca iletme İmleçler ' dir. Doğrudan kayıt kümesi nesnesi oluşturmak Planlama `CRecordset` ondan türetilen olmadan, imleç kitaplığı yüklenmemelidir.

- `CDatabase::noOdbcDialog` Yeterli bağlantı bilgilerini olup sağlanan bağımsız olarak ODBC bağlantı iletişim kutusunda görüntülenmez.

- `CDatabase::forceOdbcDialog` Her zaman ODBC bağlantı iletişim kutusu görüntüler.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarılı olursa sıfır dışı; Aksi takdirde kullanıcı seçerse 0 için daha fazla bağlantı bilgilerini soran bir iletişim kutusu yansıtılırken iptal edin. Diğer durumlarda, framework özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanmadan önce veritabanı nesnesi başlatılmalıdır.

Varsa *lpszConnectString* parametresinde, `OpenEx` çağrı bağlantı kurmak için yeterli bilgi içermiyor, sahip olduğunuz değil sağlanan ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açılır. ayarlama `CDatabase::noOdbcDialog` veya `CDatabase::forceOdbcDialog` içinde *dwOptions* parametresi. Çağırdığınızda `OpenEx`, bağlantı dizenizi *lpszConnectString*, özel olarak içinde depolanan `CDatabase` nesne ve nolu telefonu arayarak [GetConnect](#getconnect) üye işlevi.

İsterseniz, çağırmadan önce kendi iletişim kutusunu açabilirsiniz `OpenEx` kullanıcıdan bir parola gibi bilgi almak ve sonra bu bilgileri geçirmek için bağlantı dizesi eklemek için `OpenEx`. Veya sonraki yeniden kullanabilmesi geçirdiğiniz bağlantı dizesini, uygulama çağrıları zaman isteyebileceğiniz `OpenEx` üzerinde bir `CDatabase` nesne.

Birden çok oturum açma yetkilendirme düzeyi için bağlantı dizesini de kullanabilirsiniz (her biri için farklı bir `CDatabase` nesne) veya diğer veri kaynağına özgü bilgileri iletmek için. Bağlantı dizeleri hakkında daha fazla bilgi için bkz: Bölüm 6'da *ODBC Programcının Başvurusu*.

Örneğin, DBMS konak kullanılamıyorsa, zaman aşımı bağlanma girişimi için mümkündür. Bağlantı denemesi başarısız olursa `OpenEx` oluşturur bir `CDBException`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

##  <a name="rollback"></a>  CDatabase::Rollback

Bir hareket sırasında yapılan değişiklikleri geri almak için bu üye işlevini çağırın.

```
BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarıyla tersine olursa sıfır dışı; Aksi durumda 0. Varsa bir `Rollback` çağrısı başarısız olursa, işlem ve veri kaynağı durumları tanımlanmamıştır. Varsa `Rollback` 0 döndürür durumunu belirlemek için veri kaynağı işaretlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Tüm `CRecordset` `AddNew`, `Edit`, `Delete`, ve `Update` en son yürütülen çağrıları [BeginTrans](#begintrans) bu çağrı zamandaki duruma geri alınır.

Çağrısı yapıldıktan sonra `Rollback`, işlemin sona erdi ve çağırmalısınız `BeginTrans` başka bir işlem için yeniden. Aradığınız önce geçerli kaydı `BeginTrans` geçerli kayıt yeniden sonra olur `Rollback`.

Bir geri alma sonra geri alma önce geçerli kaydı geçerli olmaya devam eder. Kayıt kümesi ve bir geri alma sonra veri kaynağı durumunu hakkında daha fazla ayrıntı için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  Makaleye göz atın [işlem: (ODBC) kayıt kümesinde işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="setlogintimeout"></a>  CDatabase::SetLoginTimeout

Bu üye işlevi çağrısı — çağırmadan önce `OpenEx` veya `Open` — bir veri önce izin verilen saniye varsayılan sayısı geçersiz kılmak için kaynak bağlantısı zaman aşımına.

```
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Önce bir bağlantı denemesi izin vermek için saniye sayısını zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

Örneğin, DBMS kullanılabilir değilse, bağlantı girişimi zaman aşımına uğrayabilir. Çağrı `SetLoginTimeout` başlatılmamış oluşturduktan sonra `CDatabase` nesnesi ancak aramadan önce `OpenEx` veya `Open`.

Oturum açma zaman aşımı için'varsayılan değer 15 saniyedir. Tüm veri kaynakları bir oturum açma zaman aşımı değeri belirtmek için destekler. Veri kaynağı zaman aşımı desteklemiyorsa, izleme çıktısı, ancak bir özel alın. 0 değeri "sonsuz" anlamına gelir

##  <a name="setquerytimeout"></a>  CDatabase::SetQueryTimeout

Saniye önce sonraki işlemlerde bağlı veri kaynağı zaman aşımına izin vermek için varsayılan sayısını geçersiz kılma için bu üye işlevini çağırın.

```
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Bir sorgu girişiminden önce izin vermek için saniye sayısını zaman aşımına uğradı.

### <a name="remarks"></a>Açıklamalar

Bir işlem nedeniyle ağ erişim sorunları, aşırı miktarda sorgu işleme süresi ve benzeri zaman. Çağrı `SetQueryTimeout` kümenizin açmadan önce veya kümesinin çağırmadan önce `AddNew`, `Update` veya `Delete` üye işlevleri sorgu zaman aşımı değerini değiştirmek istiyorsanız. Bu ayar tüm sonraki etkiler `Open`, `AddNew`, `Update`, ve `Delete` bununla ilişkili tüm kayıt kümelerini çağrıları `CDatabase` nesne. Kayıt kümesi için bir değer açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirmeyi değiştirmez. Örneğin, sonraki `Move` işlemleri, yeni değer kullanmayın.

Sorgu zaman aşımı için'varsayılan değer 15 saniyedir. Tüm veri kaynakları sorgu zaman aşımı değerini ayarlama özelliğini destekler. Sorgu zaman aşımı değerini 0 olarak ayarlarsanız, hiçbir zaman aşımı oluşur; veri kaynağı ile iletişimi yanıt vermemeye başlayabilir. Bu davranış, geliştirme sırasında yararlı olabilir. Veri kaynağı zaman aşımı desteklemiyorsa, izleme çıktısı, ancak bir özel alın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
