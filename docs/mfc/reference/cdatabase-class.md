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
ms.openlocfilehash: ebc36d82af9bfe12ab30a86214e58610b5eaab95
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79418757"
---
# <a name="cdatabase-class"></a>CDatabase sınıfı

Veri kaynağında çalışabileceğiniz bir veri kaynağıyla bağlantısını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Genel Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase:: CDatabase](#cdatabase)|`CDatabase` nesnesi oluşturur. `OpenEx` veya `Open`çağırarak nesneyi başlatmalısınız.|

### <a name="public-methods"></a>Genel Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase:: BeginTrans](#begintrans)|Bağlı veri kaynağında `AddNew`, `Edit`, `Delete``Update` ve `CRecordset` sınıfının üye işlevlerine yönelik bir dizi geri alınamaz çağrı dizisi başlatır. Veri kaynağının herhangi bir etkiye sahip olması için `BeginTrans` işlemleri desteklemesi gerekir.|
|[CDatabase:: BindParameters](#bindparameters)|`CDatabase::ExecuteSQL`çağrılmadan önce parametreleri bağlamanıza olanak tanır.|
|[CDatabase:: Cancel](#cancel)|Zaman uyumsuz bir işlemi veya ikinci bir iş parçacığından bir işlemi iptal eder.|
|[CDatabase:: CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CDatabase:: CanUpdate](#canupdate)|`CDatabase` nesnesi güncelleştirilebilir ise (salt okunurdur) sıfır olmayan bir değer döndürür.|
|[CDatabase:: Close](#close)|Veri kaynağı bağlantısını kapatır.|
|[CDatabase:: CommitTrans](#committrans)|`BeginTrans`tarafından başlatılan bir işlemi tamamlar. İşlemin veri kaynağını değiştirecek komutları yürütülür.|
|[CDatabase:: ExecuteSQL](#executesql)|Bir SQL ifadesini yürütür. Hiçbir veri kaydı döndürülmedi.|
|[CDatabase:: Getbookmarkkalıcılığı](#getbookmarkpersistence)|Kayıt işaretlerinin kayıt kümesi nesnelerinde kalıcı olduğu işlemleri tanımlar.|
|[CDatabase:: GetConnect](#getconnect)|`CDatabase` nesnesini bir veri kaynağına bağlamak için kullanılan ODBC bağlantı dizesini döndürür.|
|[CDatabase:: GetCursorCommitBehavior](#getcursorcommitbehavior)|Açık bir kayıt kümesi nesnesinde işlem yürütme etkisini tanımlar.|
|[CDatabase:: GetCursorRollbackBehavior](#getcursorrollbackbehavior)|Açık bir kayıt kümesi nesnesi üzerinde bir işlemin geri alınması etkisini tanımlar.|
|[CDatabase:: GetDatabaseName](#getdatabasename)|Kullanılmakta olan veritabanının adını döndürür.|
|[CDatabase:: IsOpen](#isopen)|`CDatabase` nesnesi şu anda bir veri kaynağına bağlıysa sıfır olmayan bir değer döndürür.|
|[CDatabase:: OnSetOptions](#onsetoptions)|Standart bağlantı seçeneklerini ayarlamak için Framework tarafından çağırılır. Varsayılan uygulama, sorgu zaman aşımı değerini ayarlar. `SetQueryTimeout`çağırarak bu seçenekleri bir süre önce kurabilirsiniz.|
|[CDatabase:: Open](#open)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase:: OpenEx](#openex)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase:: Rollback](#rollback)|Geçerli işlem sırasında yapılan değişiklikleri tersine çevirir. Veri kaynağı, değiştirilmemiş `BeginTrans` çağrısında tanımlandığı şekilde önceki durumuna geri döner.|
|[CDatabase:: SetLoginTimeout](#setlogintimeout)|Bir veri kaynağı bağlantı denemesinin zaman aşımına uğrar saniye sayısını ayarlar.|
|[CDatabase:: SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin zaman aşımına geçmesi için geçmesi gereken saniye sayısını ayarlar. Sonraki tüm kayıt kümesi `Open`, `AddNew`, `Edit`ve `Delete` çağrılarını etkiler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase:: m_hdbc](#m_hdbc)|Veritabanı bağlantısı (ODBC) bağlantı tanıtıcısını bir veri kaynağına açın. *HDBC*yazın.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı, bazı veritabanı yönetim sistemi (DBMS) tarafından barındırılan belirli bir veri örneğidir. Örnek olarak Microsoft SQL Server, Microsoft Access, Borland dBASE ve xBASE sayılabilir. Uygulamanızda tek seferde etkin bir veya daha fazla `CDatabase` nesnesi olabilir.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine Class [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

`CDatabase`kullanmak için bir `CDatabase` nesnesi oluşturun ve `OpenEx` üye işlevini çağırın. Bu, bir bağlantı açar. Daha sonra bağlı veri kaynağında çalıştırmak için `CRecordset` nesneleri oluşturduğunuzda, kayıt kümesi oluşturucusunu `CDatabase` nesneniz için bir işaretçi geçirin. Bağlantıyı kullanmayı bitirdiğinizde `Close` member işlevini çağırın ve `CDatabase` nesnesini yok edin. `Close`, daha önce kapatılmayan tüm kayıt kümelerini kapatır.

`CDatabase`hakkında daha fazla bilgi için bkz. makalelere [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) ve [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

##  <a name="begintrans"></a>CDatabase:: BeginTrans

Bağlı veri kaynağıyla bir işlem başlatmak için bu üye işlevi çağırın.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrı başarılı olduysa ve değişiklikler yalnızca el ile uygulandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir işlem, bir `CRecordset` nesnesinin `AddNew`, `Edit`, `Delete`ve `Update` üye işlevlerine yapılan bir veya daha fazla çağrının oluşur. Bir işleme başlamadan önce, `OpenEx` veya `Open` üye işlevini çağırarak `CDatabase` nesnenin zaten veri kaynağına bağlanmış olması gerekir. İşlemi sonlandırmak için, veri kaynağındaki tüm değişiklikleri kabul etmek (ve bunları taşımak) veya tüm işlemi iptal etmek için [geri alma](#rollback) çağrısı yapmak üzere [CommitTrans](#committrans) 'yi çağırın. İşlemde yer alan kayıt kümelerini açtıktan ve gerçek güncelleştirme işlemlerine olabildiğince yakın sürede `BeginTrans` çağırın.

> [!CAUTION]
>  ODBC sürücünüze bağlı olarak, `BeginTrans` çağrılmadan önce bir kayıt kümesi açmak, `Rollback`çağrılırken sorun oluşmasına neden olabilir. Kullanmakta olduğunuz belirli sürücüyü denetlemeniz gerekir. Örneğin, Microsoft ODBC Masaüstü sürücü paketi 3,0 ' ye dahil olan Microsoft Access sürücüsünü kullanırken, Jet veritabanı altyapısının, açık imleç içeren herhangi bir veritabanında bir işlem başlatmaya gerek olmaması için hesabınızın olması gerekir. MFC veritabanı sınıflarında açık bir imleç, açık bir `CRecordset` nesnesi anlamına gelir. Daha fazla bilgi için bkz. [teknik notta 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).

`BeginTrans`, veri kaynağının istenen eşzamanlılık ve yeteneklerine bağlı olarak sunucudaki veri kayıtlarını da kilitleyebilir. Verileri kilitleme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

Kullanıcı tanımlı işlemler, makale [hareketinde (ODBC)](../../data/odbc/transaction-odbc.md)açıklanmaktadır.

`BeginTrans`, işlem dizisinin geri alınacağı durumu (ters çevrilen) belirler. Geri alma işlemleri için yeni bir durum oluşturmak için, geçerli işlemi işleyin ve sonra `BeginTrans` yeniden çağırın.

> [!CAUTION]
>  `CommitTrans` veya `Rollback` çağrılmadan `BeginTrans` yeniden çağrılması bir hatadır.

Sürücünüzün belirli bir veritabanı için işlemleri destekleyip desteklemediğini öğrenmek için [CanTransact](#cantransact) üye işlevini çağırın. Ayrıca, imleç saklama desteğini belirleyebilmek için [GetCursorCommitBehavior](#getcursorcommitbehavior) ve [GetCursorRollbackBehavior](#getcursorrollbackbehavior) öğesini çağırmanız gerekir.

İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

##  <a name="bindparameters"></a>CDatabase:: BindParameters

[CDatabase:: ExecuteSQL](#executesql)çağrılmadan önce parametreleri bağlamanız gerektiğinde `BindParameters` geçersiz kılın.

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Parametreleri bağlamak istediğiniz ODBC bildiri tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu yaklaşım, bir saklı yordamdan elde edilen sonuç kümesine ihtiyacınız olmadığında faydalıdır.

Geçersiz kılmada, parametreleri bağlamak için `SQLBindParameters` ve ilgili ODBC işlevlerini çağırın. MFC, `ExecuteSQL`çağrısından önce geçersiz kılmanızı çağırır. `SQLPrepare`çağırmanız gerekmez; `ExecuteSQL` çağırır `SQLExecDirect` ve yalnızca bir kez kullanılan *hstmt*'yi yok eder.

##  <a name="cancel"></a>CDatabase:: Cancel

Veri kaynağının devam eden bir zaman uyumsuz işlemi ya da ikinci bir iş parçacığından bir işlemi iptal ettiğini istemek için bu üye işlevini çağırın.

```
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıflarının artık zaman uyumsuz işleme kullanmadığını unutmayın; zaman uyumsuz bir işlem gerçekleştirmek için, [SQLSetConnectOption](/sql/odbc/reference/syntax/sqlsetconnectoption-function)ODBC API işlevini doğrudan çağırmanız gerekir. Daha fazla bilgi için bkz. [zaman uyumsuz yürütme](/sql/odbc/reference/develop-app/asynchronous-execution).

##  <a name="cantransact"></a>CDatabase:: CanTransact

Veritabanının işlemlere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CDatabase` nesnesini kullanan kayıt kümeleri işlemlere izin verir; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlemler hakkında daha fazla bilgi için, bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>CDatabase:: CanUpdate

`CDatabase` nesnesinin güncelleştirmelere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDatabase` nesnesi güncelleştirmelere izin veriyorsa sıfır dışında; Aksi takdirde 0, `CDatabase` nesnesini açtığınızda *bReadOnly* içinde doğru geçtiğini veya veri kaynağının kendisini salt okunur olduğunu belirtir. SQL_DATASOURCE_READ_ONLY için `SQLGetInfo` ODBC API işlevine yapılan bir çağrı, "y" döndürürse, veri kaynağı salt okunurdur.

### <a name="remarks"></a>Açıklamalar

Tüm sürücüler güncelleştirmeleri desteklemez.

##  <a name="cdatabase"></a>CDatabase:: CDatabase

`CDatabase` nesnesi oluşturur.

```
CDatabase();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, belirtilen veri kaynağına bir bağlantı kurmak için `OpenEx` veya `Open` üye işlevini çağırmanız gerekir.

`CDatabase` nesnesini belge sınıfınıza katıştırmayı kullanışlı bulabilirsiniz.

### <a name="example"></a>Örnek

Bu örnekte, `CDocument`türetilmiş bir sınıfta `CDatabase` kullanımı gösterilmektedir.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

##  <a name="close"></a>CDatabase:: Close

Bir veri kaynağıyla bağlantısını kesmek istiyorsanız bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırmadan önce `CDatabase` nesnesiyle ilişkili kayıt kümelerini kapatmanız gerekir. `Close` `CDatabase` nesnesini yok etmez, aynı veri kaynağına veya farklı bir veri kaynağına yeni bir bağlantı açarak nesneyi yeniden kullanabilirsiniz.

Veritabanını kullanan kayıt kümelerinin tüm bekleyen `AddNew` veya `Edit` deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. `CDatabase` nesnesine bağımlı tüm kayıt kümeleri tanımsız bir durumda bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

##  <a name="committrans"></a>CDatabase:: CommitTrans

İşlemleri tamamladıktan sonra bu üye işlevini çağırın.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirmeler başarıyla taahhütse sıfır dışı; Aksi takdirde 0. `CommitTrans` başarısız olursa, veri kaynağının durumu tanımsız olur. Durumunu öğrenmek için verileri denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Bir işlem, [BeginTrans](#begintrans) üye işlevine yapılan çağrıdan başlayan bir `CRecordset` nesnesinin `AddNew`, `Edit`, `Delete`ve `Update` üye işlevlerine yönelik bir dizi çağrıdan oluşur. `CommitTrans` işlemi kaydeder. Güncelleştirmeler varsayılan olarak hemen kaydedilir; `BeginTrans` çağırmak, `CommitTrans` çağrılana kadar güncelleştirmelerin gecikmesine neden olur.

Bir işlemi sonlandırmak için `CommitTrans` çağırana kadar, işlemi iptal etmek ve veri kaynağını özgün durumunda bırakmak için [Rollback](#rollback) üye işlevini çağırabilirsiniz. Yeni bir işleme başlamak için yeniden `BeginTrans` çağırın.

İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

##  <a name="executesql"></a>CDatabase:: ExecuteSQL

Doğrudan bir SQL komutu yürütmeniz gerektiğinde bu üye işlevini çağırın.

```
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütülecek geçerli bir SQL komutu içeren null ile sonlandırılmış bir dize işaretçisi. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)geçirebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Komutu null ile sonlandırılmış bir dize olarak oluşturun. `ExecuteSQL` veri kayıtlarını döndürmez. Kayıtlar üzerinde işlem yapmak istiyorsanız, bunun yerine bir kayıt kümesi nesnesi kullanın.

Bir veri kaynağına yönelik komutlarınızın çoğu, veri seçme, yeni kayıtlar ekleme, kayıtları silme ve kayıtları düzenlemeyle ilgili komutları destekleyen kayıt kümesi nesneleri aracılığıyla verilir. Ancak, tüm ODBC işlevleri veritabanı sınıfları tarafından doğrudan desteklenmediğinden, `ExecuteSQL`ile doğrudan bir SQL çağrısı yapmanız gerekebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

##  <a name="getbookmarkpersistence"></a>CDatabase:: Getbookmarkkalıcılığı

Belirli işlemlerden sonra bir kayıt kümesi nesnesinde yer işaretlerinin kalıcılığını öğrenmek için bu üye işlevi çağırın.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt işaretlerinin bir kayıt kümesi nesnesinde kalıcı olduğu işlemleri tanımlayan bir bit maskesi. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Örneğin, `CRecordset::GetBookmark` çağırır ve sonra `CRecordset::Requery`çağırırsanız, `GetBookmark` elde edilen yer işareti artık geçerli olmayabilir. `CRecordset::SetBookmark`çağrılmadan önce `GetBookmarkPersistence` çağırmalısınız.

Aşağıdaki tabloda, `GetBookmarkPersistence`dönüş değeri için birleştirilebilecek bit maskesi değerleri listelenmektedir.

|Bit maskesi değeri|Yer işareti kalıcılığı|
|-------------------|--------------------------|
|SQL_BP_CLOSE|`Requery` bir işlemden sonra yer işaretleri geçerlidir.|
|SQL_BP_DELETE|Satır için yer işareti, bu satırdaki `Delete` işleminden sonra geçerlidir.|
|SQL_BP_DROP|`Close` bir işlemden sonra yer işaretleri geçerlidir.|
|SQL_BP_SCROLL|Yer işaretleri, `Move` işleminden sonra geçerlidir. Bu yalnızca, `CRecordset::CanBookmark`tarafından döndürülen kayıt kümeleri üzerinde yer işaretlerinin desteklenip desteklenmediğini tanımlar.|
|SQL_BP_TRANSACTION|Yer işaretleri bir işlem tamamlandıktan veya geri alındıktan sonra geçerlidir.|
|SQL_BP_UPDATE|Satır için yer işareti, bu satırdaki `Update` işleminden sonra geçerlidir.|
|SQL_BP_OTHER_HSTMT|Bir kayıt kümesi nesnesiyle ilişkili yer işaretleri ikinci bir kayıt kümesinde geçerlidir.|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK `SQLGetInfo` ODBC API işlevine bakın. Yer işaretleri hakkında daha fazla bilgi için bkz. [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="getconnect"></a>CDatabase:: GetConnect

`OpenEx` çağrısı sırasında kullanılan bağlantı dizesini veya `CDatabase` nesnesini bir veri kaynağına bağlayan `Open` almak için bu üye işlevi çağırın.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Dönüş Değeri

`OpenEx` veya `Open` çağrılırsa bağlantı dizesini içeren **const**bir[CString](../../atl-mfc-shared/reference/cstringt-class.md) ; Aksi takdirde, boş bir dize.

### <a name="remarks"></a>Açıklamalar

Bağlantı dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için bkz. [CDatabase:: Open](#open) .

##  <a name="getcursorcommitbehavior"></a>CDatabase:: GetCursorCommitBehavior

Bir [CommitTrans](#committrans) işleminin açık kayıt kümesi nesnelerinde imleçleri nasıl etkilediğini öğrenmek için bu üye işlevi çağırın.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt kümesi nesnelerindeki işlemlerin etkisini gösteren bir değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `GetCursorCommitBehavior` için olası dönüş değerleri ve açık kayıt kümesine karşılık gelen efekt listelenmektedir.

|Dönüş değeri|CRecordset nesneleri üzerindeki etki|
|------------------|----------------------------------|
|SQL_CB_CLOSE|İşlem işlemesini hemen izleyerek `CRecordset::Requery` çağırın.|
|SQL_CB_DELETE|İşlem işlemesini hemen izleyerek `CRecordset::Close` çağırın.|
|SQL_CB_PRESERVE|`CRecordset` işlemler ile normal şekilde devam edin.|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK `SQLGetInfo` ODBC API işlevine bakın. İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getcursorrollbackbehavior"></a>CDatabase:: GetCursorRollbackBehavior

Bir [geri alma](#rollback) işleminin açık kayıt kümesi nesnelerinde imleçleri nasıl etkilediğini öğrenmek için bu üye işlevi çağırın.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt kümesi nesnelerindeki işlemlerin etkisini gösteren bir değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda `GetCursorRollbackBehavior` için olası dönüş değerleri ve açık kayıt kümesine karşılık gelen efekt listelenmektedir.

|Dönüş değeri|CRecordset nesneleri üzerindeki etki|
|------------------|----------------------------------|
|SQL_CB_CLOSE|İşlem geri almanın hemen ardından `CRecordset::Requery` çağırın.|
|SQL_CB_DELETE|İşlem geri almanın hemen ardından `CRecordset::Close` çağırın.|
|SQL_CB_PRESERVE|`CRecordset` işlemler ile normal şekilde devam edin.|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK `SQLGetInfo` ODBC API işlevine bakın. İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="getdatabasename"></a>CDatabase:: GetDatabaseName

Şu anda bağlı olan veritabanının adını almak için bu üye işlevi çağırın (veri kaynağı "veritabanı" adlı adlandırılmış bir nesneyi tanımladığından).

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanı adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) ; Aksi takdirde, boş bir `CString`.

### <a name="remarks"></a>Açıklamalar

Bu, `OpenEx` veya `Open` çağrısında belirtilen veri kaynağı adı (DSN) ile aynı değildir. `GetDatabaseName` döndürdüğü değer ODBC 'ye bağlıdır. Genel olarak, bir veritabanı bir tablo koleksiyonudur. Bu varlığın bir adı varsa `GetDatabaseName` döndürür.

Örneğin, bu adı bir başlıkta göstermek isteyebilirsiniz. ODBC 'den adı alırken bir hata oluşursa `GetDatabaseName` boş bir `CString`döndürür.

##  <a name="isopen"></a>CDatabase:: IsOpen

`CDatabase` nesnesinin Şu anda bir veri kaynağına bağlı olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDatabase` nesnesi şu anda bağlıysa sıfır dışı; Aksi takdirde 0.

##  <a name="m_hdbc"></a>CDatabase:: m_hdbc

Bir ODBC veri kaynağı bağlantısına ("bağlantı tanıtıcısı") genel bir tanıtıcı içerir.

### <a name="remarks"></a>Açıklamalar

Normalde, bu üye değişkenine doğrudan erişmeniz gerekmez. Bunun yerine, `OpenEx` veya `Open`çağırdığınızda çerçeve tanıtıcıyı ayırır. `CDatabase` nesnesinde **Delete** işlecini çağırdığınızda çerçeve tanıtıcıyı kaldırır. `Close` member işlevinin tanıtıcıyı serbest desteklemediğini unutmayın.

Ancak bazı durumlarda tanıtıcıyı doğrudan kullanmanız gerekebilir. Örneğin, sınıf `CDatabase`yerine ODBC API işlevlerini doğrudan çağırmanız gerekiyorsa, parametre olarak geçirmek için bir bağlantı işleyicisine ihtiyacınız olabilir. Aşağıdaki kod örneğine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

##  <a name="onsetoptions"></a>CDatabase:: OnSetOptions

Framework, `ExecuteSQL` member işleviyle bir SQL ifadesini doğrudan yürütürken bu üye işlevini çağırır.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Hangi seçeneklerin ayarlandığı ODBC bildiri tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`CRecordset::OnSetOptions` Ayrıca bu üye işlevini çağırır.

`OnSetOptions`, oturum açma zaman aşımı değerini ayarlar. `SetQueryTimeout` ve üye işlevine yapılan önceki çağrılar varsa, `OnSetOptions` geçerli değerleri yansıtır; Aksi takdirde, varsayılan değerleri ayarlar.

> [!NOTE]
>  MFC 4,2 ' den önce, `OnSetOptions` işlem modunu hiç zaman uyumlu veya zaman uyumsuz olarak da ayarlar. MFC 4,2 ' den başlayarak tüm işlemler zaman uyumludur. Zaman uyumsuz bir işlem gerçekleştirmek için `SQLSetPos`ODBC API işlevine doğrudan çağrı yapmalısınız.

Zaman aşımı değerini değiştirmek için `OnSetOptions` geçersiz kılmalısınız. Bunun yerine, sorgu zaman aşımı değerini özelleştirmek için, bir kayıt kümesi oluşturmadan önce `SetQueryTimeout` çağırın; `OnSetOptions` yeni değeri kullanacaktır. Değerler kümesi, tüm kayıt kümelerinde veya doğrudan SQL çağrılarında sonraki işlemlere uygulanır.

Ek seçenekler ayarlamak istiyorsanız `OnSetOptions` geçersiz kılın. Geçersiz kılma işlemi, `SQLSetStmtOption`ODBC API işlevini çağırmadan önce veya sonra `OnSetOptions` temel sınıfı çağırmalıdır. Framework 'ün `OnSetOptions`varsayılan uygulamasında gösterilen yöntemi izleyin.

##  <a name="open"></a>CDatabase:: Open

Yeni oluşturulan bir `CDatabase` nesnesini başlatmak için bu üye işlevini çağırın.

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
ODBC yönetici programı aracılığıyla ODBC ile kaydedilen bir ad olan bir veri kaynağı adı belirtir. *LpszConnect* IÇINDE bir DSN değeri belirtilmişse ("DSN =\<Data-Source >" biçiminde), *lpszDSN*içinde yeniden belirtilmemelidir. Bu durumda, *LPSZDSN* null olmalıdır. Aksi takdirde, kullanıcının bir veri kaynağı seçmesini sağlayan bir veri kaynağı iletişim kutusuyla sunmak istiyorsanız NULL değerini geçirebilirsiniz. Daha fazla bilgi için bkz. açıklamalar.

*bExclusive*<br/>
Sınıf kitaplığının bu sürümünde desteklenmiyor. Şu anda, bu parametre TRUE olduğunda bir onaylama başarısız olur. Veri kaynağı her zaman paylaşılan (özel değil) olarak açılır.

*bReadOnly*<br/>
Bağlantıyı Salt okunabilir olacak şekilde düşünüyorsanız ve veri kaynağı için güncelleştirmeleri yasakladıysanız TRUE. Tüm bağımlı kayıt kümeleri bu özniteliği devralınır. Varsayılan değer FALSE 'dur.

*lpszConnect*<br/>
Bir bağlantı dizesi belirtir. Bağlantı dizesi, büyük olasılıkla bir veri kaynağı adı, veri kaynağı üzerinde geçerli bir kullanıcı KIMLIĞI, bir kullanıcı kimlik doğrulama dizesi (veri kaynağı bir tane gerektiriyorsa) ve diğer bilgiler dahil olmak üzere bilgileri birleştirir. Tüm bağlantı dizesi "ODBC;" dizesinin önüne alınmalıdır (büyük veya küçük harf). "ODBC;" dizesi, bağlantının bir ODBC veri kaynağına ait olduğunu göstermek için kullanılır; Bu, sınıf kitaplığının gelecekteki sürümleri ODBC olmayan veri kaynaklarını destekliyorsa, daha yüksek uyumluluk içindir.

*bUseCursorLib*<br/>
ODBC Imleç kitaplığı DLL dosyasının yüklenmesini istiyorsanız TRUE. İmleç kitaplığı, temel alınan ODBC sürücüsünün bazı işlevlerini maskeler ve dinamik kümeler kullanımını etkili bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklendiğinde desteklenen imleçler yalnızca statik anlık görüntüler ve salt ileri imleçler olur. Varsayılan değer TRUE 'dur. İçinden türetmeden `CRecordset` doğrudan bir kayıt kümesi nesnesi oluşturmayı planlıyorsanız, imleç kitaplığı 'nı yüklenmemelisiniz.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapıldıysa sıfır dışı; Aksi takdirde, Kullanıcı daha fazla bağlantı bilgileri soran bir iletişim kutusu sunulursa Iptal ' i seçerse 0. Diğer tüm durumlarda Framework bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmeniz için veritabanı nesnenizin başlatılması gerekir.

> [!NOTE]
>  [OpenEx](#openex) üye işlevini çağırmak, bir veri kaynağına bağlanmak ve veritabanı nesneniz başlatmak için tercih edilen yoldur.

`Open` çağrındaki parametreler bağlantıyı yapmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. `Open`çağırdığınızda, bağlantı dizeniz, *lpszConnect*nesnesi `CDatabase` içinde özel olarak depolanır ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgileri almak için `Open` çağırmadan önce kendi iletişim kutusunu açabilir, ardından bu bilgileri `Open`geçirdiğiniz bağlantı dizesine ekleyebilirsiniz. Ya da geçirdiğiniz bağlantı dizesini kaydetmek isteyebilirsiniz. böylece, uygulamanız bir `CDatabase` nesnesi üzerinde `Open` bir sonraki sefer çağırıyorsa onu yeniden kullanabilirsiniz.

Bağlantı dizesini Ayrıca, birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDatabase` nesnesi için) veya diğer veri kaynağına özgü bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için, Windows SDK bölüm 5 ' i inceleyin.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `Open` bir `CDBException`oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

##  <a name="openex"></a>CDatabase:: OpenEx

Yeni oluşturulan bir `CDatabase` nesnesini başlatmak için bu üye işlevini çağırın.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszConnectString*<br/>
Bir ODBC bağlantı dizesi belirtir. Bu, veri kaynağı adının yanı sıra Kullanıcı KIMLIĞI ve parola gibi diğer isteğe bağlı bilgileri de içerir. Örneğin, "DSN = SQLServer_Source; UID = SA; PWD = abc123 "olası bir bağlantı dizesidir. *LpszConnectString*için null geçirirseniz, bir veri kaynağı iletişim kutusu kullanıcıdan bir veri kaynağı seçmesini ister.

*dwOptions*<br/>
Aşağıdaki değerlerin birleşimini belirten bir bit maskesi. Varsayılan değer 0 ' dır, yani veritabanının yazma erişimiyle paylaşılan olarak açılabileceği anlamına gelir, ODBC Imleç kitaplığı DLL 'SI yüklenmez ve ODBC bağlantısı iletişim kutusu yalnızca bağlantıyı kurmak için yeterli bilgi yoksa görüntülenir.

- `CDatabase::openExclusive`, sınıf kitaplığının bu sürümünde desteklenmiyor. Bir veri kaynağı her zaman paylaşılan (özel değil) olarak açılır. Şu anda, bu seçeneği belirtirseniz bir onaylama başarısız olur.

- `CDatabase::openReadOnly` veri kaynağını salt okuma olarak açın.

- ODBC Imleç kitaplığı DLL 'sini `CDatabase::useCursorLib` yükleyin. İmleç kitaplığı, temel alınan ODBC sürücüsünün bazı işlevlerini maskeler ve dinamik kümeler kullanımını etkili bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklendiğinde desteklenen imleçler yalnızca statik anlık görüntüler ve salt ileri imleçler olur. İçinden türetmeden `CRecordset` doğrudan bir kayıt kümesi nesnesi oluşturmayı planlıyorsanız, imleç kitaplığı 'nı yüklenmemelisiniz.

- `CDatabase::noOdbcDialog`, yeterli bağlantı bilgilerinin sağlanmadığına bakılmaksızın ODBC bağlantısı iletişim kutusunu görüntülemez.

- `CDatabase::forceOdbcDialog` her zaman ODBC bağlantısı iletişim kutusunu görüntüler.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapıldıysa sıfır dışı; Aksi takdirde, Kullanıcı daha fazla bağlantı bilgileri soran bir iletişim kutusu sunulursa Iptal ' i seçerse 0. Diğer tüm durumlarda Framework bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmeniz için veritabanı nesnenizin başlatılması gerekir.

`OpenEx` çağrınızdan *lpszConnectString* parametresi bağlantıyı yapmak için yeterli bilgi IÇERMIYORSA, ODBC sürücüsü kullanıcının gerekli bilgilerini almak için bir iletişim kutusu açar, `CDatabase::noOdbcDialog` veya *dwoptions* parametresinde `CDatabase::forceOdbcDialog` ayarlayamazsınız. `OpenEx`çağırdığınızda, bağlantı dizeniz, *lpszConnectString*nesnesi `CDatabase` içinde özel olarak depolanır ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgileri almak için `OpenEx` çağırmadan önce kendi iletişim kutusunu açabilir ve sonra bu bilgileri `OpenEx`geçirdiğiniz bağlantı dizesine ekleyebilirsiniz. Ya da geçirdiğiniz bağlantı dizesini kaydetmek isteyebilirsiniz. böylece, uygulamanız bir `CDatabase` nesnesi üzerinde `OpenEx` bir sonraki sefer çağırıyorsa onu yeniden kullanabilirsiniz.

Bağlantı dizesini Ayrıca, birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDatabase` nesnesi için) veya diğer veri kaynağına özgü bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için, bkz. Bölüm 6, *ODBC Programcı başvurusu*.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `OpenEx` bir `CDBException`oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

##  <a name="rollback"></a>CDatabase:: Rollback

İşlem sırasında yapılan değişiklikleri tersine çevirmek için bu üye işlevini çağırın.

```
BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarıyla geri çevrilirse sıfır dışı; Aksi takdirde 0. Bir `Rollback` çağrısı başarısız olursa, veri kaynağı ve işlem durumları tanımsızdır. `Rollback` 0 döndürürse, durumunu öğrenmek için veri kaynağını denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Tüm `CRecordset` `AddNew`, `Edit`, `Delete`ve `Update` son [BeginTrans](#begintrans) bu çağrı sırasında var olan duruma geri alınana kadar yürütülür.

`Rollback`çağrısından sonra, işlem üzerinden yapılır ve başka bir işlem için `BeginTrans` yeniden çağırmanız gerekir. `BeginTrans` çağrılmadan önce geçerli olan kayıt, `Rollback`sonra geçerli kayıt haline gelir.

Geri alma işleminden sonra, geri alma işleminden önce geçerli olan kayıt geçerli olmaya devam eder. Bir geri alma işleminden sonra kayıt kümesinin ve veri kaynağının durumu hakkında ayrıntılar için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

##  <a name="setlogintimeout"></a>CDatabase:: SetLoginTimeout

Denenen bir veri kaynağı bağlantısı zaman aşımına uğramadan önce izin verilen varsayılan saniye sayısını geçersiz kılmak için, bu üye işlevini çağırın — `OpenEx` veya `Open` çağırmadan önce, izin verilen saniye sayısı

```
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Bağlantı girişimi zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Örneğin, DBMS kullanılamıyorsa bir bağlantı girişimi zaman aşımına uğrar. Başlatılmamış `CDatabase` nesnesini oluşturduktan sonra, `OpenEx` veya `Open`çağırmadan önce `SetLoginTimeout` çağırın.

Oturum açma zaman aşımları için varsayılan değer 15 saniyedir. Tüm veri kaynakları, bir oturum açma zaman aşımı değeri belirtme yeteneğini desteklemez. Veri kaynağı zaman aşımını desteklemiyorsa, izleme çıkışı alırsınız ancak özel durum oluşturmaz. 0 değeri "sonsuz" anlamına gelir.

##  <a name="setquerytimeout"></a>CDatabase:: SetQueryTimeout

Bağlı veri kaynağındaki sonraki işlemlerin zaman aşımına geçmeden önce izin verilecek varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi çağırın.

```
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Sorgu girişiminden zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişimi sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. Sorgu zaman aşımı değerini değiştirmek istiyorsanız kayıt kümenizin `AddNew`, `Update` veya `Delete` üye işlevleri çağrılmadan önce `SetQueryTimeout` çağırın. Bu ayar, sonraki tüm `Open`, `AddNew`, `Update`ve bu `CDatabase` nesnesiyle ilişkili tüm kayıt kümelerine `Delete` çağrılarını etkiler. Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki `Move` işlemleri yeni değeri kullanmaz.

Sorgu zaman aşımları için varsayılan değer 15 saniyedir. Tüm veri kaynakları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; veri kaynağıyla iletişim yanıt vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Veri kaynağı zaman aşımını desteklemiyorsa, izleme çıkışı alırsınız ancak özel durum oluşturmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
