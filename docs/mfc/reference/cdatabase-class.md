---
title: CDatabase Sınıfı
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
ms.openlocfilehash: bc920307e09179dc214710a3b6b19ff27a82749d
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754634"
---
# <a name="cdatabase-class"></a>CDatabase Sınıfı

Veri kaynağı üzerinde çalışabileceğiniz bir veri kaynağına olan bağlantıyı temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase::CDatabase](#cdatabase)|Bir `CDatabase` nesne inşa eder. Nesneyi arayarak `OpenEx` veya `Open`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase::BeginTrans](#begintrans)|Bağlı veri kaynağında `AddNew`sınıfın `Edit` `Delete` `Update` `CRecordset` , ve üye işlevlerine geri döndürülebilir bir dizi çağrı olan bir "işlem" başlatır. Veri kaynağının herhangi `BeginTrans` bir etkisi olması için hareketleri desteklemesi gerekir.|
|[CDatabase::BindParametreleri](#bindparameters)|Aramadan önce parametreleri `CDatabase::ExecuteSQL`bağlamanızı sağlar.|
|[CDatabase::İptal et](#cancel)|Bir eşzamanlı işlemi veya işlemi ikinci bir iş parçacığından iptal eder.|
|[CDatabase::CanTransact](#cantransact)|Veri kaynağı hareketleri destekliyorsa sıfırsız döndürür.|
|[CDatabase::CanUpdate](#canupdate)|`CDatabase` Nesne güncel değilse sıfırsız döndürür (salt okunur değil).|
|[CDatabase::Kapat](#close)|Veri kaynağı bağlantısını kapatır.|
|[CDatabase::CommitTrans](#committrans)|`BeginTrans`Tarafından başlatılan bir işlemi tamamlar. İşlemde veri kaynağını değiştiren komutlar gerçekleştirilir.|
|[CDatabase::ExecuteSQL](#executesql)|Bir SQL deyimi yürütür. Hiçbir veri kaydı döndürülür.|
|[CDatabase::GetBookmarkPersistence](#getbookmarkpersistence)|Yer imlerinin kayıt kümesi nesnelerinde devam ettiği işlemleri tanımlar.|
|[CDatabase::GetConnect](#getconnect)|Nesneyi bir veri kaynağına bağlamak `CDatabase` için kullanılan ODBC bağlantı dizesini döndürür.|
|[CDatabase::GetCursorCommitBehavior](#getcursorcommitbehavior)|Açık kayıt kümesi nesnesi üzerinde bir hareket gerçekleştirmenin etkisini tanımlar.|
|[CDatabase::GetCursorRollbackBehavior](#getcursorrollbackbehavior)|Bir hareketi açık kayıt kümesi nesnesi üzerinde geri alma nın etkisini tanımlar.|
|[CDatabase::GetDatabaseName](#getdatabasename)|Şu anda kullanılmakta olan veritabanının adını döndürür.|
|[CDatabase::IsOpen](#isopen)|Nesne şu anda bir veri kaynağına `CDatabase` bağlıysa sıfırsız döndürür.|
|[CDatabase::OnsetOptions](#onsetoptions)|Standart bağlantı seçenekleri ayarlamak için çerçeve tarafından çağrılır. Varsayılan uygulama sorgu zaman dışarı değerini ayarlar. Bu seçenekleri önceden arayarak `SetQueryTimeout`kurabilirsiniz.|
|[CDatabase::Aç](#open)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase::OpenEx](#openex)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase::Geri alma](#rollback)|Geçerli hareket sırasında yapılan değişiklikleri tersine çevirir. Veri kaynağı, `BeginTrans` çağrıda tanımlandığı gibi önceki durumuna değiştirilmeden döner.|
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Veri kaynağı bağlantı denemesinin zaman dolana yapacağı saniye sayısını ayarlar.|
|[CDatabase::SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin zaman dolana yapacağı saniye sayısını ayarlar. Sonraki tüm kayıt `Open` `AddNew`kümesini `Delete` ve `Edit`aramaları etkiler.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDatabase::m_hdbc](#m_hdbc)|Veritabanı Bağlantısı (ODBC) bağlantı tanıtıcısını bir veri kaynağına açın. *HDBC*yazın.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı, bazı veritabanı yönetim sistemi (DBMS) tarafından barındırılan belirli bir veri örneğidir. Örnekler arasında Microsoft SQL Server, Microsoft Access, Borland dBASE ve xBASE sayılabilir. Uygulamanızda aynı anda bir veya daha fazla `CDatabase` nesne etkin olabilir.

> [!NOTE]
> Açık Veritabanı Bağlantısı (ODBC) sınıfları yerine Veri Erişim Nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) sınıfını kullanın. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

Kullanmak `CDatabase`için, `CDatabase` bir nesne `OpenEx` oluşturmak ve üye işlevi arayın. Bu bir bağlantı açar. Daha sonra `CRecordset` bağlı veri kaynağı üzerinde çalışmak için nesneler inşa ettiğinizde, kaydedici `CDatabase` oluşturucuyu nesnenize geçirin. Bağlantıyı kullanmayı bitirdiğinizde, `Close` üye işlevi arayın `CDatabase` ve nesneyi yok edin. `Close`daha önce kapatmadığınız kayıt kümelerini kapatır.

Hakkında `CDatabase`daha fazla bilgi için, [makaleler Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) ve Genel Bakış [bakınız: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="cdatabasebegintrans"></a><a name="begintrans"></a>CDatabase::BeginTrans

Bağlı veri kaynağıyla bir işlem başlatmak için bu üye işlevi arayın.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Arama başarılı olduysa ve değişiklikler yalnızca el ile işlenirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir hareket, `AddNew`bir `Edit` `Delete` `Update` `CRecordset` nesnenin , , ve üye işlevlerine yapılan bir veya daha fazla çağrıdan oluşur. Bir işleme başlamadan `CDatabase` önce, nesnenin veri kaynağına kendi `OpenEx` veya `Open` üye işlevini çağırarak zaten bağlanmış olması gerekir. İşlemi sona erdirmek için [CommitTrans'ı](#committrans) arayarak veri kaynağındaki tüm değişiklikleri kabul edin (ve bunları gerçekleştirin) veya tüm hareketi iptal etmesi için [Rollback'i](#rollback) arayın. İşlemle ilgili kayıt kümelerini `BeginTrans` açtıktan sonra ve gerçek güncelleştirme işlemlerine mümkün olduğunca yakın arayın.

> [!CAUTION]
> ODBC sürücünüze bağlı olarak, aramadan `BeginTrans` önce bir `Rollback`kayıt kümesini açmak arama yaparken sorunlara neden olabilir. Kullandığınız belirli sürücüyü kontrol etmelisiniz. Örneğin, Microsoft ODBC Masaüstü Sürücü Paketi 3.0'da yer alan Microsoft Access sürücüsünü kullanırken, Açık imleci olan herhangi bir veritabanında işlem başlatmamanız gerektiğini Jet veritabanı altyapısı nın gereksinimini hesaba katmalısınız. MFC veritabanı sınıflarında, açık imleç açık `CRecordset` bir nesne anlamına gelir. Daha fazla bilgi için [Teknik Not 68'e](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md)bakın.

`BeginTrans`ayrıca, istenen eşzamanlılık ve veri kaynağının yeteneklerine bağlı olarak, sunucudaki veri kayıtlarını kilitleyebilir. Verileri kilitleme hakkında daha fazla bilgi için [Recordset: Locking Records (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)makalesine bakın.

Kullanıcı tanımlı hareketler Işlem [(ODBC)](../../data/odbc/transaction-odbc.md)makalesinde açıklanmıştır.

`BeginTrans`hareket sırasının geri alınabileceği (tersine çevrilebileceği durumu) belirler. Geri almalar için yeni bir durum oluşturmak için `BeginTrans` geçerli bir işlem gerçekleştirin ve ardından yeniden arayın.

> [!CAUTION]
> Aramadan `BeginTrans` veya `CommitTrans` `Rollback` bir hata olmadan yeniden arama.

Sürücünüzün belirli bir veritabanı için hareketleri destekleyip desteklemediğini belirlemek için [CanTransact](#cantransact) üye işlevini arayın. İmleç koruma desteğini belirlemek için [GetCursorCommitBehavior](#getcursorcommitbehavior) ve [GetCursorRollbackBehavior'i](#getcursorrollbackbehavior) de aramalısınız.

İşlemler hakkında daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  Makaleye Bakın [Hareket: Kayıt Kümesinde (ODBC) İşlem Gerçekleştirme.](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

## <a name="cdatabasebindparameters"></a><a name="bindparameters"></a>CDatabase::BindParametreleri

`BindParameters` [CDatabase::ExecuteSQL'i](#executesql)aramadan önce parametreleri bağlamanız gerektiğinde geçersiz kılın.

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*Hstmt*<br/>
Parametreleri bağlamak istediğiniz ODBC deyimi tutamacı.

### <a name="remarks"></a>Açıklamalar

Bu yaklaşım, depolanan bir yordamdan belirlenen sonuca ihtiyacınız olmadığında yararlıdır.

Geçersiz kılmanızda, `SQLBindParameters` parametreleri bağlamak için çağrı ve ilgili ODBC işlevleri. MFC, aramadan önce geçersiz `ExecuteSQL`kılmanızı çağırır. Aramanız `SQLPrepare`gerekmez; `ExecuteSQL` aramaları `SQLExecDirect` ve sadece bir kez kullanılan *hstmt*yok eder.

## <a name="cdatabasecancel"></a><a name="cancel"></a>CDatabase::İptal et

Veri kaynağının devam eden bir eşzamanlı işlemi veya ikinci bir iş parçacığından bir işlemi iptal etmesini istemek için bu üye işlevi arayın.

```cpp
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıfları artık eşzamanlı işleme kullanmaz; bir eşzamanlı işlem gerçekleştirmek için doğrudan ODBC API fonksiyonu [SQLSetConnectOption](/sql/odbc/reference/syntax/sqlsetconnectoption-function)aramanız gerekir. Daha fazla bilgi için [Bkz.](/sql/odbc/reference/develop-app/asynchronous-execution)

## <a name="cdatabasecantransact"></a><a name="cantransact"></a>CDatabase::CanTransact

Veritabanının hareketlere izin verip vermeyemeyeceğini belirlemek için bu üye işlevini arayın.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CDatabase` nesneyi kullanan kayıt kümeleri hareketlere izin verirse sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlemler hakkında bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

## <a name="cdatabasecanupdate"></a><a name="canupdate"></a>CDatabase::CanUpdate

Nesnenin `CDatabase` güncelleştirmelere izin verip vermeyemeyeceğini belirlemek için bu üye işlevi arayın.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne güncelleştirmeleri `CDatabase` izin veriyorsa sıfır olmayan; aksi takdirde 0, `CDatabase` nesneyi açtığınızda sadece *TRUE* geçti ya da veri kaynağı kendisi okunur olduğunu belirten. Veri kaynağı yalnızca SQL_DATASOURCE_READ_ONLY için ODBC API işlevine `SQLGetInfo` yapılan bir çağrı "y" döndürürse okunur.

### <a name="remarks"></a>Açıklamalar

Tüm sürücüler güncelleştirmeleri desteklemez.

## <a name="cdatabasecdatabase"></a><a name="cdatabase"></a>CDatabase::CDatabase

Bir `CDatabase` nesne inşa eder.

```
CDatabase();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi oluşturduktan sonra, belirli `OpenEx` `Open` bir veri kaynağına bağlantı kurmak için onun veya üye işlevini aramanız gerekir.

Nesneyi belge sınıfınıza gömmeyi `CDatabase` uygun bulabilirsiniz.

### <a name="example"></a>Örnek

Bu örnek, `CDatabase` türemiş bir `CDocument`sınıfta kullanımı göstermektedir.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

## <a name="cdatabaseclose"></a><a name="close"></a>CDatabase::Kapat

Bir veri kaynağından bağlantınızı kesmek istiyorsanız bu üye işlevini arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağırmadan `CDatabase` önce nesneyle ilişkili tüm kayıt kümelerini kapatmanız gerekir. Nesneyi yok `Close` `CDatabase` etmediğinden, aynı veri kaynağına veya farklı bir veri kaynağına yeni bir bağlantı açarak nesneyi yeniden kullanabilirsiniz.

Veritabanını `AddNew` `Edit` kullanan kayıt kümelerinin tüm bekleyen veya ekstreleri iptal edilir ve bekleyen tüm hareketler geri alınır. Nesneye `CDatabase` bağlı tüm kayıt kümeleri tanımlanmamış bir durumda bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

## <a name="cdatabasecommittrans"></a><a name="committrans"></a>CDatabase::CommitTrans

İşlemleri tamamladıktan sonra bu üye işlevini arayın.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirmeler başarıyla işlenmişse sıfırolmayan; aksi takdirde 0. Başarısız `CommitTrans` olursa, veri kaynağının durumu tanımsız. Durumunu belirlemek için verileri denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

`AddNew`Bir işlem, [BeginTrans](#begintrans) üye işlevine `Delete`yapılan `Update` bir çağrıyla başlayan bir `CRecordset` nesnenin , , `Edit`ve üye işlevlerine yapılan bir dizi çağrıdan oluşur. `CommitTrans`işlemi yapar. Varsayılan olarak, güncelleştirmeler hemen işlenir; çağrılması, `BeginTrans` güncelleştirmelerin çağrılına kadar `CommitTrans` geciktirilmesine neden olur.

Bir hareketi `CommitTrans` sona erdirmek için arayana kadar, işlemi iptal etmek ve veri kaynağını özgün durumunda bırakmak için [Geri Alma](#rollback) üye işlevini arayabilirsiniz. Yeni bir işlem başlatmak `BeginTrans` için yeniden arayın.

İşlemler hakkında daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  Makaleye Bakın [Hareket: Kayıt Kümesinde (ODBC) İşlem Gerçekleştirme.](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

## <a name="cdatabaseexecutesql"></a><a name="executesql"></a>CDatabase::ExecuteSQL

Doğrudan bir SQL komutu yürütmeniz gerektiğinde bu üye işlevi arayın.

```cpp
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*Lpszsql*<br/>
Yürütmek için geçerli bir SQL komutu içeren null-sonlandırılan dize işaretçisi. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)geçirebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Komutu null-sonlandırılan dize olarak oluşturun. `ExecuteSQL`veri kayıtlarını döndürmez. Kayıtları çalıştırmak istiyorsanız, bunun yerine bir kayıt kümesi nesnesi kullanın.

Bir veri kaynağı için komutlarınızın çoğu, veri seçme, yeni kayıtlar ekleme, kayıtları silme ve kayıtları düzenleme komutlarını destekleyen kayıt kümesi nesneleri aracılığıyla verilir. Ancak, tüm ODBC işlevselliği doğrudan veritabanı sınıfları tarafından desteklenmez, bu nedenle `ExecuteSQL`zaman zaman doğrudan bir SQL araması yapmanız gerekebilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

## <a name="cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>CDatabase::GetBookmarkPersistence

Belirli işlemlerden sonra kayıt kümesi nesnesi üzerindeki yer imlerinin kalıcılığını belirlemek için bu üye işlevi arayın.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yer imleri kayıt kümesi nesnesi üzerinde devam ettiği işlemleri tanımlayan bir bitmaskesi. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Örneğin, arar ve `CRecordset::GetBookmark` sonra `CRecordset::Requery`ararsanız, elde `GetBookmark` edilen yer imi artık geçerli olmayabilir. Aramadan `GetBookmarkPersistence` önce `CRecordset::SetBookmark`aramalısın.

Aşağıdaki tabloda, `GetBookmarkPersistence`'nin geri dönüş değeri için birlenebilen bitmask değerleri listelenir.

|Bitmask değeri|Yer imi kalıcılığı|
|-------------------|--------------------------|
|SQL_BP_CLOSE|Yer imleri bir `Requery` işlemden sonra geçerlidir.|
|SQL_BP_DELETE|Satır için yer imi, `Delete` bu satırdaki bir işlemden sonra geçerlidir.|
|SQL_BP_DROP|Yer imleri bir `Close` işlemden sonra geçerlidir.|
|SQL_BP_SCROLL|Yer imleri herhangi `Move` bir işlemden sonra geçerlidir. Bu, yer imlerinin kayıt kümesinde desteklenip `CRecordset::CanBookmark`desteklenmediğini tanımlar ve '.|
|SQL_BP_TRANSACTION|Yer imleri, bir işlem işlendikten veya geri alındıktan sonra geçerlidir.|
|SQL_BP_UPDATE|Satır için yer imi, `Update` bu satırdaki bir işlemden sonra geçerlidir.|
|SQL_BP_OTHER_HSTMT|Bir kayıt kümesi nesnesi ile ilişkili yer imleri ikinci bir kayıt kümesinde geçerlidir.|

Bu iade değeri hakkında daha fazla bilgi için `SQLGetInfo` Windows SDK'daki ODBC API işlevine bakın. Yer imleri hakkında daha fazla bilgi için [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalesine bakın.

## <a name="cdatabasegetconnect"></a><a name="getconnect"></a>CDatabase::GetConnect

Arama sırasında kullanılan veya `OpenEx` `Open` `CDatabase` nesneyi bir veri kaynağına bağlayan bağlantı dizesini almak için bu üye işlevi arayın.

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çağrıldıysa `OpenEx` veya `Open` çağrıldıysa bağlantı dizesini içeren bir **const**[CString;](../../atl-mfc-shared/reference/cstringt-class.md) aksi takdirde, boş bir dize.

### <a name="remarks"></a>Açıklamalar

[Bkz. CDatabase::Bağlantı](#open) dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için aç.

## <a name="cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>CDatabase::GetCursorCommitBehavior

[CommitTrans](#committrans) işleminin açık kayıt kümesi nesnelerindeki imleçleri nasıl etkilediğini belirlemek için bu üye işlevi arayın.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hareketlerin açık kayıt kümesi nesneleri üzerindeki etkisini gösteren bir değer. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo, olası iade `GetCursorCommitBehavior` değerlerini ve açık kayıt kümesi üzerindeki karşılık gelen etkiyi listeler.

|Döndürülen değer|CRecordset nesneleri üzerindeki etkisi|
|------------------|----------------------------------|
|SQL_CB_CLOSE|İşlem `CRecordset::Requery` i¶rlemi hemen ardından arayın.|
|SQL_CB_DELETE|İşlem `CRecordset::Close` i¶rlemi hemen ardından arayın.|
|SQL_CB_PRESERVE|İşlemlerle normal `CRecordset` bir şekilde ilerleyin.|

Bu iade değeri hakkında daha fazla bilgi için `SQLGetInfo` Windows SDK'daki ODBC API işlevine bakın. İşlemler hakkında daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

## <a name="cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>CDatabase::GetCursorRollbackBehavior

[Bir Rollback](#rollback) işleminin açık kayıt kümesi nesnelerinde imleçleri nasıl etkilediğini belirlemek için bu üye işlevi arayın.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Hareketlerin açık kayıt kümesi nesneleri üzerindeki etkisini gösteren bir değer. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tablo, olası iade `GetCursorRollbackBehavior` değerlerini ve açık kayıt kümesi üzerindeki karşılık gelen etkiyi listeler.

|Döndürülen değer|CRecordset nesneleri üzerindeki etkisi|
|------------------|----------------------------------|
|SQL_CB_CLOSE|Hareket `CRecordset::Requery` geri alındırından hemen sonra arayın.|
|SQL_CB_DELETE|Hareket `CRecordset::Close` geri alındırından hemen sonra arayın.|
|SQL_CB_PRESERVE|İşlemlerle normal `CRecordset` bir şekilde ilerleyin.|

Bu iade değeri hakkında daha fazla bilgi için `SQLGetInfo` Windows SDK'daki ODBC API işlevine bakın. İşlemler hakkında daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

## <a name="cdatabasegetdatabasename"></a><a name="getdatabasename"></a>CDatabase::GetDatabaseName

Şu anda bağlı olan veritabanının adını almak için bu üye işlevi arayın (veri kaynağının "veritabanı" adlı bir adı geçen bir nesne tanımlaması koşuluyla).

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanı adını içeren bir [CString;](../../atl-mfc-shared/reference/cstringt-class.md) aksi takdirde, `CString`boş bir .

### <a name="remarks"></a>Açıklamalar

Bu, aramada `OpenEx` `Open` belirtilen veri kaynağı adı (DSN) ile aynı değildir. Ne `GetDatabaseName` döner ODBC bağlıdır. Genel olarak, veritabanı tablolar topluluğudur. Bu varlığın bir `GetDatabaseName` adı varsa, döndürür.

Örneğin, bu adı bir başlıkta görüntülemek isteyebilirsiniz. ODBC'den adı alırken bir hata oluşursa, `GetDatabaseName` boş `CString`bir .

## <a name="cdatabaseisopen"></a><a name="isopen"></a>CDatabase::IsOpen

Nesnenin şu anda `CDatabase` bir veri kaynağına bağlı olup olmadığını belirlemek için bu üye işlevi arayın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Nesne şu `CDatabase` anda bağlıysa sıfıra doğru; aksi takdirde 0.

## <a name="cdatabasem_hdbc"></a><a name="m_hdbc"></a>CDatabase::m_hdbc

ODBC veri kaynağı bağlantısıiçin ortak iştanıtıcı içerir - bir "bağlantı tanıtıcısı."

### <a name="remarks"></a>Açıklamalar

Normalde, bu üye değişkene doğrudan erişmenize gerek yoktur. Bunun yerine, çerçeve, istediğinizde `OpenEx` tutamacı ayırır veya `Open`. Çerçeve anlaşması, nesneüzerindeki **silme** işlecini çağırdığınızda tutamacı yeralır. `CDatabase` Üye işlevin `Close` tutamacı nı işlemediğini unutmayın.

Ancak, bazı durumlarda tutamacı doğrudan kullanmanız gerekebilir. Örneğin, sınıf `CDatabase`yerine doğrudan ODBC API işlevlerini aramanız gerekiyorsa, parametre olarak geçmek için bir bağlantı tanıtıcınız gerekebilir. Aşağıdaki kod örneğine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

## <a name="cdatabaseonsetoptions"></a><a name="onsetoptions"></a>CDatabase::OnsetOptions

Framework, `ExecuteSQL` üye işlevle doğrudan bir SQL deyimi yürürken bu üye işlevi çağırır.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*Hstmt*<br/>
Hangi seçeneklerin ayarlandığı için ODBC deyimi işletti.

### <a name="remarks"></a>Açıklamalar

`CRecordset::OnSetOptions`ayrıca bu üye işlevi çağırır.

`OnSetOptions`giriş zaman ödeme değerini ayarlar. Üye işlev için `SetQueryTimeout` daha önce çağrılar `OnSetOptions` yapılmışsa, geçerli değerleri yansıtır; aksi takdirde, varsayılan değerleri ayarlar.

> [!NOTE]
> MFC 4.2'den `OnSetOptions` önce, işlem modunu snychronous veya asynchronous olarak da ayarlayın. MFC 4.2 ile başlayarak tüm işlemler eşzamanlıdır. Eşzamanlı bir işlem gerçekleştirmek için ODBC API işlevini `SQLSetPos`doğrudan aramanız gerekir.

Zaman aşan değeri `OnSetOptions` değiştirmek için geçersiz kılmanız gerekmez. Bunun yerine, sorgu zaman aşım `SetQueryTimeout` değerini özelleştirmek için, bir kayıt kümesi oluşturmadan önce arayın; `OnSetOptions` yeni değeri kullanır. Ayarlanan değerler, tüm kayıt kümelerinde veya doğrudan SQL çağrılarındaki sonraki işlemler için geçerlidir.

Ek `OnSetOptions` seçenekler ayarlamak istiyorsanız geçersiz kılın. Geçersiz kılmanız, ODBC API işlevini `OnSetOptions` `SQLSetStmtOption`aramadan önce veya sonra taban sınıfı aramalıdır. Çerçevenin varsayılan uygulamasında gösterilen yöntemi `OnSetOptions`izleyin.

## <a name="cdatabaseopen"></a><a name="open"></a>CDatabase::Aç

Yeni oluşturulan `CDatabase` bir nesneyi başlatmak için bu üye işlevi arayın.

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
ODBC Administrator programı aracılığıyla ODBC'ye kayıtlı bir ad olan bir veri kaynağı adı belirtir. *LpszConnect'te* bir DSN değeri belirtilirse ("DSN=\<veri kaynağı>" şeklinde), *lpszDSN'de*tekrar belirtilmemelidir. Bu durumda, *lpszDSN* NULL olmalıdır. Aksi takdirde, kullanıcıya bir veri kaynağı seçebileceği bir Veri Kaynağı iletişim kutusu sunmak istiyorsanız NULL'u geçirebilirsiniz. Daha fazla bilgi için Açıklamalar'a bakın.

*bExclusive*<br/>
Sınıf kitaplığın bu sürümünde desteklenmez. Şu anda, bu parametre TRUE ise bir iddia başarısız olur. Veri kaynağı her zaman paylaşılan (münhasır değil) olarak açılır.

*bReadOnly*<br/>
Bağlantının salt okunur olmasını ve veri kaynağında güncelleştirmeleri yasaklamasını istiyorsanız DOĞRU. Tüm bağımlı kayıt kümeleri bu özniteliği devralır. Varsayılan değer FALSE'dur.

*lpszConnect*<br/>
Bağlantı dizesi belirtir. Bağlantı dizesi, büyük olasılıkla bir veri kaynağı adı, veri kaynağında geçerli bir kullanıcı kimliği, kullanıcı kimlik doğrulama dizesi (veri kaynağı gerektiriyorsa parola) ve diğer bilgileri içeren bilgileri birleştirir. Tüm bağlantı dizesi "ODBC; " dizesi tarafından önceden belirlenmiş olmalıdır. (büyük veya küçük harf). "ODBC;" dizesi, bağlantının bir ODBC veri kaynağına olduğunu belirtmek için kullanılır; bu, sınıf kitaplığı gelecekteki sürümleri odbc olmayan veri kaynaklarını destekleyebilir yukarı uyumluluk içindir.

*bUseCursorLib*<br/>
ODBC İmleç Kitaplığı DLL'nin yüklenmesini istiyorsanız DOĞRU. İmleç kitaplığı, altta yatan ODBC sürücüsünün bazı işlevlerini maskeleyerek dinamatörkullanımını etkin bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklenmişse desteklenen tek imleç statik anlık görüntüler ve yalnızca ileriimleçlerdir. Varsayılan değer TRUE'dur. Bir kayıt kümesi nesnesi `CRecordset` oluşturmayı planlıyorsanız, imleç kitaplığını yüklememelisiniz.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapılırsa sıfıra inme; aksi takdirde kullanıcı daha fazla bağlantı bilgisi isteyen bir iletişim kutusu sunulduğunda İptal'i seçerse 0. Diğer tüm durumlarda, çerçeve bir özel durum atar.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmek için önce veritabanı nesnenizin başlatılması gerekir.

> [!NOTE]
> [OpenEx](#openex) üye işlevini çağırmak, bir veri kaynağına bağlanmak ve veritabanı nesnenizi başlatmanın tercih edilen yoludur.

Aramanızdaki `Open` parametreler bağlantıyı yapmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. Bağlantı dizeniz `Open` *lpszConnect'i*aradığınızda `CDatabase` nesnede özel olarak saklanır ve [GetConnect](#getconnect) üye işlevini arayarak kullanılabilir.

İsterseniz, parola gibi kullanıcıdan bilgi almak `Open` için aramadan önce kendi iletişim kutunuzu açabilir, ardından bu bilgileri `Open`geçtiğiniz bağlantı dizesine ekleyebilirsiniz. Veya, uygulamanız bir `Open` `CDatabase` nesneyi bir sonraki aramada yeniden kullanabilmek için geçtiğiniz bağlantı dizesini kaydetmek isteyebilirsiniz.

Bağlantı dizesini birden çok oturum açma yetkilendirme düzeyi (her biri farklı `CDatabase` bir nesne için) veya diğer veri kaynağına özgü bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için Windows SDK'daki Bölüm 5'e bakın.

Örneğin, DBMS ana bilgisayarı kullanılamıyorsa, bir bağlantı denemesinin zaman dışarı çıkması mümkündür. Bağlantı girişimi başarısız `Open` olursa, `CDBException`bir .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

## <a name="cdatabaseopenex"></a><a name="openex"></a>CDatabase::OpenEx

Yeni oluşturulan `CDatabase` bir nesneyi başlatmak için bu üye işlevi arayın.

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszConnectString*<br/>
ODBC bağlantı dizesi belirtir. Bu, veri kaynağı adının yanı sıra kullanıcı kimliği ve parola gibi diğer isteğe bağlı bilgileri de içerir. Örneğin, "DSN=SQLServer_Source; UID=SA; PWD=abc123" olası bir bağlantı dizesidir. *LPSZConnectString*için NULL'u geçerseniz, bir Veri Kaynağı iletişim kutusu kullanıcıdan bir veri kaynağı seçmesini ister.

*Dwoptions*<br/>
Aşağıdaki değerlerin bir birleşimini belirten bir bitmaskesi. Varsayılan değer 0'dır, bu da veritabanının yazma erişimiyle paylaşıldığı, ODBC Imleç Kitaplığı DLL'nin yüklenmeyeceğini ve ODBC bağlantı iletişim kutusunun yalnızca bağlantıyı yapmak için yeterli bilgi yoksa görüntülenecektir anlamına gelir.

- `CDatabase::openExclusive`Sınıf kitaplığın bu sürümünde desteklenmez. Bir veri kaynağı her zaman paylaşılan (münhasır değil) olarak açılır. Şu anda, bu seçeneği belirtirseniz bir iddia başarısız olur.

- `CDatabase::openReadOnly`Veri kaynağını salt okunur olarak açın.

- `CDatabase::useCursorLib`ODBC İmleç Kitaplığını Yükleyin DLL. İmleç kitaplığı, altta yatan ODBC sürücüsünün bazı işlevlerini maskeleyerek dinamatörkullanımını etkin bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklenmişse desteklenen tek imleç statik anlık görüntüler ve yalnızca ileriimleçlerdir. Bir kayıt kümesi nesnesi `CRecordset` oluşturmayı planlıyorsanız, imleç kitaplığını yüklememelisiniz.

- `CDatabase::noOdbcDialog`Yeterli bağlantı bilgisi sağlanıp sağlanmadığına bakılmaksızın ODBC bağlantı iletişim kutusunu görüntülemeyin.

- `CDatabase::forceOdbcDialog`ODBC bağlantı iletişim kutusunu her zaman görüntüleyin.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapılırsa sıfıra inme; aksi takdirde kullanıcı daha fazla bağlantı bilgisi isteyen bir iletişim kutusu sunulduğunda İptal'i seçerse 0. Diğer tüm durumlarda, çerçeve bir özel durum atar.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmek için önce veritabanı nesnenizin başlatılması gerekir.

Aramanızdaki `OpenEx` *lpszConnectString* parametresi bağlantıyı kurmak için yeterli bilgi içermiyorsa, DwOptions parametresini ayarlamamış `CDatabase::noOdbcDialog` `CDatabase::forceOdbcDialog` veya *dwOptions* parametresinde bulunmamışsanız, Kullanıcıdan gerekli bilgileri almak için ODBC sürücüsü bir iletişim kutusu açar. Bağlantı dizeniz *lpszConnectString'* i aradığınızda `CDatabase` `OpenEx`nesnede özel olarak saklanır ve [GetConnect](#getconnect) üye işlevini arayarak kullanılabilir.

İsterseniz, parola gibi kullanıcıdan bilgi almak `OpenEx` için aramadan önce kendi iletişim kutunuzu açabilir ve bu bilgileri geçtiğiniz `OpenEx`bağlantı dizesine ekleyebilirsiniz. Veya, uygulamanız bir `OpenEx` `CDatabase` nesneyi bir sonraki aramada yeniden kullanabilmek için geçtiğiniz bağlantı dizesini kaydetmek isteyebilirsiniz.

Bağlantı dizesini birden çok oturum açma yetkilendirme düzeyi (her biri farklı `CDatabase` bir nesne için) veya diğer veri kaynağına özgü bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için, *ODBC ProgramcısıNın Başvurusu'ndaki Bölüm 6'ya*bakın.

Örneğin, DBMS ana bilgisayarı kullanılamıyorsa, bir bağlantı denemesinin zaman dışarı çıkması mümkündür. Bağlantı girişimi başarısız `OpenEx` olursa, `CDBException`bir .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

## <a name="cdatabaserollback"></a><a name="rollback"></a>CDatabase::Geri alma

Bir işlem sırasında yapılan değişiklikleri tersine çevirmek için bu üye işlevi arayın.

```
BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarıyla tersine çevrildiyse sıfırsız; aksi takdirde 0. Bir `Rollback` çağrı başarısız olursa, veri kaynağı ve işlem durumları tanımsız. 0 `Rollback` döndürürse, durumunu belirlemek için veri kaynağını denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Son `CRecordset` `AddNew` `Edit` [BeginTrans'dan](#begintrans) bu yana yürütülen tüm , , `Delete`ve `Update` çağrılar bu çağrı sırasında var olan duruma geri alınır.

Bir aramadan `Rollback`sonra, işlem sona erdi `BeginTrans` ve başka bir işlem için yeniden aramanız gerekir. Aramadan `BeginTrans` önce geçerli olan kayıt, ''den sonra `Rollback`yeniden geçerli kayıt olur.

Geri alma dan sonra, geri alma önce geçerli olan kayıt geçerli kalır. Kayıt kümesinin durumu ve geri alma sonrası veri kaynağı hakkında ayrıntılar için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  Makaleye Bakın [Hareket: Kayıt Kümesinde (ODBC) İşlem Gerçekleştirme.](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

## <a name="cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>CDatabase::SetLoginTimeout

Bir veri kaynağı bağlantısı `OpenEx` denemesi `Open` nden önce izin verilen varsayılan saniye sayısını geçersiz kılmak için aramadan önce veya bu üye işlevini arayın.

```cpp
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Bağlantı denemesinden önce izin verilebilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Örneğin, DBMS kullanılamıyorsa, bir bağlantı denemesi zaman kaybedebilir. Başlatmayan `SetLoginTimeout` `CDatabase` nesneyi yaptıktan sonra, `OpenEx` aramadan önce veya `Open`.

Giriş zaman ları için varsayılan değer 15 saniyedir. Tüm veri kaynakları oturum açma zaman ödeme değerini belirtme yeteneğini desteklemez. Veri kaynağı zaman desteklemiyorsa, izleme çıktısı alırsınız, ancak bir özel durum elde e-posta sı alırsınız. 0 değeri "sonsuz" anlamına gelir.

## <a name="cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDatabase::SetQueryTimeout

Bağlı veri kaynağı zaman aşması üzerinde sonraki işlemlerden önce izin vermek için varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi arayın.

```cpp
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Sorgu denemesi nden önce izin verilebilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişim sorunları, aşırı sorgu işlem süresi ve benzeri nedenler nedeniyle bir işlem zaman alabilir. Sorgu `SetQueryTimeout` zaman önceliğini değiştirmek istiyorsanız, kayıt setinizi `AddNew` `Update` açmadan veya kayıt setinin veya `Delete` üye işlevlerini çağırmadan önce arayın. Ayar, `Open`sonraki tüm `AddNew` `Update`, `Delete` , ve bu `CDatabase` nesne ile ilişkili herhangi bir kayıt kümeleri çağrıları etkiler. Açıldıktan sonra bir kayıt kümesinin sorgu zaman anına değerini değiştirmek, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki `Move` işlemler yeni değeri kullanmayın.

Sorgu zaman ları için varsayılan değer 15 saniyedir. Tüm veri kaynakları sorgu zaman anına değer ayarlama yeteneğini desteklemez. 0 sorgu zaman ödeme değeri ayarlarsanız, zaman ası oluşmaz; veri kaynağı ile iletişim yanıt durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Veri kaynağı zaman desteklemiyorsa, izleme çıktısı alırsınız, ancak bir özel durum elde e-posta sı alırsınız.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
