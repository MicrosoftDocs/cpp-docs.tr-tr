---
description: 'Daha fazla bilgi edinin: CDatabase sınıfı'
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
ms.openlocfilehash: 82859ebcffeb833ca5afe885b0ae35916da4cf28
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247988"
---
# <a name="cdatabase-class"></a>CDatabase sınıfı

Veri kaynağında çalışabileceğiniz bir veri kaynağıyla bağlantısını temsil eder.

## <a name="syntax"></a>Syntax

```
class CDatabase : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase:: CDatabase](#cdatabase)|Bir `CDatabase` nesnesi oluşturur. Ya da çağırarak nesneyi başlatmalısınız `OpenEx` `Open` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase:: BeginTrans](#begintrans)|`AddNew` `Edit` `Delete` `Update` Bağlı veri kaynağında, sınıfının,, ve üye işlevlerine `CRecordset` yönelik bir dizi geri alınamaz çağrı dizisi olan bir "işlem" başlatır. Veri kaynağının `BeginTrans` herhangi bir etkiye sahip olması için işlemleri desteklemesi gerekir.|
|[CDatabase:: BindParameters](#bindparameters)|Çağrılmadan önce parametreleri bağlamanıza olanak tanır `CDatabase::ExecuteSQL` .|
|[CDatabase:: Cancel](#cancel)|Zaman uyumsuz bir işlemi veya ikinci bir iş parçacığından bir işlemi iptal eder.|
|[CDatabase:: CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CDatabase:: CanUpdate](#canupdate)|`CDatabase`Nesne güncelleştirilebilir ise (salt okunurdur) sıfır dışında bir değer döndürür.|
|[CDatabase:: Close](#close)|Veri kaynağı bağlantısını kapatır.|
|[CDatabase:: CommitTrans](#committrans)|Tarafından başlatılan bir işlemi tamamlar `BeginTrans` . İşlemin veri kaynağını değiştirecek komutları yürütülür.|
|[CDatabase:: ExecuteSQL](#executesql)|Bir SQL ifadesini yürütür. Hiçbir veri kaydı döndürülmedi.|
|[CDatabase:: Getbookmarkkalıcılığı](#getbookmarkpersistence)|Kayıt işaretlerinin kayıt kümesi nesnelerinde kalıcı olduğu işlemleri tanımlar.|
|[CDatabase:: GetConnect](#getconnect)|Nesneyi bir veri kaynağına bağlamak için kullanılan ODBC bağlantı dizesini döndürür `CDatabase` .|
|[CDatabase:: GetCursorCommitBehavior](#getcursorcommitbehavior)|Açık bir kayıt kümesi nesnesinde işlem yürütme etkisini tanımlar.|
|[CDatabase:: GetCursorRollbackBehavior](#getcursorrollbackbehavior)|Açık bir kayıt kümesi nesnesi üzerinde bir işlemin geri alınması etkisini tanımlar.|
|[CDatabase:: GetDatabaseName](#getdatabasename)|Kullanılmakta olan veritabanının adını döndürür.|
|[CDatabase:: IsOpen](#isopen)|`CDatabase`Nesne şu anda bir veri kaynağına bağlıysa sıfır olmayan bir değer döndürür.|
|[CDatabase:: OnSetOptions](#onsetoptions)|Standart bağlantı seçeneklerini ayarlamak için Framework tarafından çağırılır. Varsayılan uygulama, sorgu zaman aşımı değerini ayarlar. ' İ çağırarak bu seçenekleri daha önce kurabilirsiniz `SetQueryTimeout` .|
|[CDatabase:: Open](#open)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase:: OpenEx](#openex)|Bir veri kaynağına (ODBC sürücüsü aracılığıyla) bağlantı kurar.|
|[CDatabase:: Rollback](#rollback)|Geçerli işlem sırasında yapılan değişiklikleri tersine çevirir. Veri kaynağı, çağrı sırasında, değiştirilmemiş olarak tanımlandığı şekilde önceki durumuna geri döner `BeginTrans` .|
|[CDatabase:: SetLoginTimeout](#setlogintimeout)|Bir veri kaynağı bağlantı denemesinin zaman aşımına uğrar saniye sayısını ayarlar.|
|[CDatabase:: SetQueryTimeout](#setquerytimeout)|Veritabanı sorgusu işlemlerinin zaman aşımına geçmesi için geçmesi gereken saniye sayısını ayarlar. Sonraki tüm recordset `Open` , `AddNew` , `Edit` ve çağrılarını etkiler `Delete` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDatabase:: m_hdbc](#m_hdbc)|Veritabanı bağlantısı (ODBC) bağlantı tanıtıcısını bir veri kaynağına açın. *HDBC* yazın.|

## <a name="remarks"></a>Açıklamalar

Veri kaynağı, bazı veritabanı yönetim sistemi (DBMS) tarafından barındırılan belirli bir veri örneğidir. Örnek olarak Microsoft SQL Server, Microsoft Access, Borland dBASE ve xBASE sayılabilir. Uygulamanızda bir seferde bir veya daha fazla `CDatabase` nesneniz etkin olabilir.

> [!NOTE]
> Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine Class [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Kullanmak için `CDatabase` bir nesnesi oluşturun `CDatabase` ve `OpenEx` üye işlevini çağırın. Bu, bir bağlantı açar. Daha sonra `CRecordset` bağlı veri kaynağında çalıştırmak için nesneleri yapılandırdığınızda, kayıt kümesi oluşturucusunu nesneniz için bir işaretçi geçirin `CDatabase` . Bağlantıyı kullanmayı bitirdiğinizde `Close` üye işlevini çağırın ve nesneyi yok edin `CDatabase` . `Close` daha önce kapatılmayan tüm kayıt kümelerini kapatır.

Hakkında daha fazla bilgi için `CDatabase` bkz. Makaleler [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md) ve [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDatabase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="cdatabasebegintrans"></a><a name="begintrans"></a> CDatabase:: BeginTrans

Bağlı veri kaynağıyla bir işlem başlatmak için bu üye işlevi çağırın.

```
BOOL BeginTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Çağrı başarılı olduysa ve değişiklikler yalnızca el ile uygulandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir işlem, `AddNew` `Edit` bir nesnenin,, `Delete` ve `Update` üye işlevlerine yapılan bir veya daha fazla çağrının oluşur `CRecordset` . Bir işleme başlamadan önce, `CDatabase` `OpenEx` veya üye işlevi çağırarak nesnenin zaten veri kaynağına bağlanmış olması gerekir `Open` . İşlemi sonlandırmak için, veri kaynağındaki tüm değişiklikleri kabul etmek (ve bunları taşımak) veya tüm işlemi iptal etmek için [geri alma](#rollback) çağrısı yapmak üzere [CommitTrans](#committrans) 'yi çağırın. `BeginTrans`İşlemle ilgili kayıt kümelerini açtıktan sonra ve gerçek güncelleştirme işlemlerine olabildiğince yakın şekilde çağrı yapın.

> [!CAUTION]
> ODBC sürücünüze bağlı olarak, çağrılmadan önce bir kayıt kümesi açmak, `BeginTrans` çağırma sırasında sorunlara neden olabilir `Rollback` . Kullanmakta olduğunuz belirli sürücüyü denetlemeniz gerekir. Örneğin, Microsoft ODBC Masaüstü sürücü paketi 3,0 ' ye dahil olan Microsoft Access sürücüsünü kullanırken, Jet veritabanı altyapısının, açık imleç içeren herhangi bir veritabanında bir işlem başlatmaya gerek olmaması için hesabınızın olması gerekir. MFC veritabanı sınıflarında açık bir imleç açık bir nesne anlamına gelir `CRecordset` . Daha fazla bilgi için bkz. [teknik notta 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).

`BeginTrans` , istenen eşzamanlılık ve veri kaynağının özelliklerine bağlı olarak sunucudaki veri kayıtlarını da kilitleyebilir. Verileri kilitleme hakkında daha fazla bilgi için bkz. [kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

Kullanıcı tanımlı işlemler, makale [hareketinde (ODBC)](../../data/odbc/transaction-odbc.md)açıklanmaktadır.

`BeginTrans` işlem dizisinin geri alınacağı durumu (ters çevrilen) belirler. Geri alma işlemleri için yeni bir durum oluşturmak için, geçerli tüm işlemleri işleyin ve sonra `BeginTrans` yeniden çağırın.

> [!CAUTION]
> `BeginTrans`Çağırmadan `CommitTrans` veya bir hata olmadan yeniden çağırma `Rollback` .

Sürücünüzün belirli bir veritabanı için işlemleri destekleyip desteklemediğini öğrenmek için [CanTransact](#cantransact) üye işlevini çağırın. Ayrıca, imleç saklama desteğini belirleyebilmek için [GetCursorCommitBehavior](#getcursorcommitbehavior) ve [GetCursorRollbackBehavior](#getcursorrollbackbehavior) öğesini çağırmanız gerekir.

İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

## <a name="cdatabasebindparameters"></a><a name="bindparameters"></a> CDatabase:: BindParameters

`BindParameters` [CDatabase:: ExecuteSQL](#executesql)çağrılmadan önce parametreleri bağlamanız gerektiğinde geçersiz kılın.

```
virtual void BindParameters(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Parametreleri bağlamak istediğiniz ODBC bildiri tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bu yaklaşım, bir saklı yordamdan elde edilen sonuç kümesine ihtiyacınız olmadığında faydalıdır.

Geçersiz kılmada, `SQLBindParameters` parametreleri bağlamak için ve ılgılı ODBC işlevlerini çağırın. MFC, çağrısından önce geçersiz kılmanızı çağırır `ExecuteSQL` . `SQLPrepare` `ExecuteSQL` `SQLExecDirect` Yalnızca bir kez kullanılan *hstmt* öğesini çağırmanız ve yok etmek zorunda değilsiniz.

## <a name="cdatabasecancel"></a><a name="cancel"></a> CDatabase:: Cancel

Veri kaynağının devam eden bir zaman uyumsuz işlemi ya da ikinci bir iş parçacığından bir işlemi iptal ettiğini istemek için bu üye işlevini çağırın.

```cpp
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıflarının artık zaman uyumsuz işleme kullanmadığını unutmayın; zaman uyumsuz bir işlem gerçekleştirmek için, [SQLSetConnectOption](/sql/odbc/reference/syntax/sqlsetconnectoption-function)ODBC API işlevini doğrudan çağırmanız gerekir. Daha fazla bilgi için bkz. [zaman uyumsuz yürütme](/sql/odbc/reference/develop-app/asynchronous-execution).

## <a name="cdatabasecantransact"></a><a name="cantransact"></a> CDatabase:: CanTransact

Veritabanının işlemlere izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesneyi kullanan kayıt kümeleri `CDatabase` işlemlere izin verir; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İşlemler hakkında daha fazla bilgi için, bkz. [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="cdatabasecanupdate"></a><a name="canupdate"></a> CDatabase:: CanUpdate

Nesnenin güncelleştirmelere izin verip içermediğini öğrenmek için bu üye işlevi çağırın `CDatabase` .

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDatabase`Nesne güncelleştirmelere izin veriyorsa sıfır olmayan BIR değer; Aksi takdirde 0, nesneyi açtığınızda *bReadOnly* içinde doğru geçtiğini `CDatabase` ya da veri kaynağının kendisini salt okunur olduğunu belirtir. SQL_DATASOURCE_READ_ONLY için ODBC API işlevine yapılan bir çağrı `SQLGetInfo` "y" döndürürse veri kaynağı salt okunurdur.

### <a name="remarks"></a>Açıklamalar

Tüm sürücüler güncelleştirmeleri desteklemez.

## <a name="cdatabasecdatabase"></a><a name="cdatabase"></a> CDatabase:: CDatabase

Bir `CDatabase` nesnesi oluşturur.

```
CDatabase();
```

### <a name="remarks"></a>Açıklamalar

Nesnesi oluşturulduktan sonra, `OpenEx` `Open` belirtilen veri kaynağına bir bağlantı kurmak için veya üye işlevini çağırmanız gerekir.

Nesneyi belge sınıfınıza katıştırmayı kullanışlı bulabilirsiniz `CDatabase` .

### <a name="example"></a>Örnek

Bu örnek, ile `CDatabase` türetilmiş bir `CDocument` sınıfta kullanmayı göstermektedir.

[!code-cpp[NVC_MFCDatabase#9](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]

[!code-cpp[NVC_MFCDatabase#10](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]

## <a name="cdatabaseclose"></a><a name="close"></a> CDatabase:: Close

Bir veri kaynağıyla bağlantısını kesmek istiyorsanız bu üye işlevi çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bu üye işlevini çağırabilmeniz için, nesneyle ilişkili tüm kayıt kümelerini kapatmanız gerekir `CDatabase` . `Close`Nesneyi yok etmez `CDatabase` , aynı veri kaynağına veya farklı bir veri kaynağına yeni bir bağlantı açarak nesneyi yeniden kullanabilirsiniz.

`AddNew` `Edit` Veritabanını kullanan kayıt kümelerinin tüm bekliyor veya deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Nesneye bağımlı tüm kayıt kümeleri `CDatabase` tanımsız bir durumda bırakılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#12](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]

## <a name="cdatabasecommittrans"></a><a name="committrans"></a> CDatabase:: CommitTrans

İşlemleri tamamladıktan sonra bu üye işlevini çağırın.

```
BOOL CommitTrans();
```

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirmeler başarıyla taahhütse sıfır dışı; Aksi takdirde 0. `CommitTrans`Başarısız olursa, veri kaynağının durumu tanımsız olur. Durumunu öğrenmek için verileri denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

Bir işlem, `AddNew` `Edit` `Delete` `Update` `CRecordset` [BeginTrans](#begintrans) üye işlevine çağrısıyla başlayan bir nesnenin,,, ve üye işlevlerine yapılan bir dizi çağrıdan oluşur. `CommitTrans` işlemi kaydeder. Güncelleştirmeler varsayılan olarak hemen kaydedilir; çağırma `BeginTrans` , çağrılana kadar güncelleştirmelerin gecikmesine neden olur `CommitTrans` .

`CommitTrans`Bir işlemi sona erdirmek için çağrı yapana kadar, işlemi iptal etmek ve veri kaynağını özgün durumunda bırakmak Için [Rollback](#rollback) üye işlevini çağırabilirsiniz. Yeni bir işlem başlatmak için yeniden çağırın `BeginTrans` .

İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

## <a name="cdatabaseexecutesql"></a><a name="executesql"></a> CDatabase:: ExecuteSQL

Doğrudan bir SQL komutu yürütmeniz gerektiğinde bu üye işlevini çağırın.

```cpp
void ExecuteSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Parametreler

*lpszSQL*<br/>
Yürütülecek geçerli bir SQL komutu içeren null ile sonlandırılmış bir dize işaretçisi. Bir [CString](../../atl-mfc-shared/reference/cstringt-class.md)geçirebilirsiniz.

### <a name="remarks"></a>Açıklamalar

Komutu null ile sonlandırılmış bir dize olarak oluşturun. `ExecuteSQL` veri kayıtlarını döndürmez. Kayıtlar üzerinde işlem yapmak istiyorsanız, bunun yerine bir kayıt kümesi nesnesi kullanın.

Bir veri kaynağına yönelik komutlarınızın çoğu, veri seçme, yeni kayıtlar ekleme, kayıtları silme ve kayıtları düzenlemeyle ilgili komutları destekleyen kayıt kümesi nesneleri aracılığıyla verilir. Ancak, tüm ODBC işlevleri veritabanı sınıfları tarafından doğrudan desteklenmediğinden, ile doğrudan bir SQL çağrısı yapmanız gerekebilir `ExecuteSQL` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#13](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]

## <a name="cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a> CDatabase:: Getbookmarkkalıcılığı

Belirli işlemlerden sonra bir kayıt kümesi nesnesinde yer işaretlerinin kalıcılığını öğrenmek için bu üye işlevi çağırın.

```
DWORD GetBookmarkPersistence() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt işaretlerinin bir kayıt kümesi nesnesinde kalıcı olduğu işlemleri tanımlayan bir bit maskesi. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Örneğin, öğesini çağırıp `CRecordset::GetBookmark` çağırın `CRecordset::Requery` , öğesinden elde edilen yer işareti `GetBookmark` artık geçerli olmayabilir. `GetBookmarkPersistence`Çağrılmadan önce öğesini çağırmanız gerekir `CRecordset::SetBookmark` .

Aşağıdaki tabloda, dönüş değeri için birleştirilebilecek bit maskesi değerleri listelenmektedir `GetBookmarkPersistence` .

|Bit maskesi değeri|Yer işareti kalıcılığı|
|-------------------|--------------------------|
|SQL_BP_CLOSE|Yer işaretleri bir işlemden sonra geçerlidir `Requery` .|
|SQL_BP_DELETE|Bir satır için yer işareti, `Delete` Bu satırdaki bir işlemden sonra geçerlidir.|
|SQL_BP_DROP|Yer işaretleri bir işlemden sonra geçerlidir `Close` .|
|SQL_BP_SCROLL|Yer işaretleri herhangi bir işlemden sonra geçerlidir `Move` . Bu basitçe, tarafından döndürülen kayıt kümeleri için bir kayıt kümesi desteklenip desteklenmediğini tanımlar `CRecordset::CanBookmark` .|
|SQL_BP_TRANSACTION|Yer işaretleri bir işlem tamamlandıktan veya geri alındıktan sonra geçerlidir.|
|SQL_BP_UPDATE|Bir satır için yer işareti, `Update` Bu satırdaki bir işlemden sonra geçerlidir.|
|SQL_BP_OTHER_HSTMT|Bir kayıt kümesi nesnesiyle ilişkili yer işaretleri ikinci bir kayıt kümesinde geçerlidir.|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK ODBC API işlevine bakın `SQLGetInfo` . Yer işaretleri hakkında daha fazla bilgi için bkz. [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

## <a name="cdatabasegetconnect"></a><a name="getconnect"></a> CDatabase:: GetConnect

' A yapılan çağrı sırasında kullanılan bağlantı dizesini `OpenEx` veya `Open` bir veri kaynağına bağlı olan bağlantı dizesini almak için bu üye işlevini çağırın `CDatabase` .

```
const CString GetConnect() const;
```

### <a name="return-value"></a>Dönüş Değeri

**`const`** [](../../atl-mfc-shared/reference/cstringt-class.md) Veya çağrılırsa bağlantı dizesini içeren bir CString `OpenEx` `Open` ; Aksi takdirde boş bir dize.

### <a name="remarks"></a>Açıklamalar

Bağlantı dizesinin nasıl oluşturulduğuna ilişkin bir açıklama için bkz. [CDatabase:: Open](#open) .

## <a name="cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a> CDatabase:: GetCursorCommitBehavior

Bir [CommitTrans](#committrans) işleminin açık kayıt kümesi nesnelerinde imleçleri nasıl etkilediğini öğrenmek için bu üye işlevi çağırın.

```
int GetCursorCommitBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt kümesi nesnelerindeki işlemlerin etkisini gösteren bir değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, için olası dönüş değerleri `GetCursorCommitBehavior` ve açık kayıt kümesine karşılık gelen efekt listelenmektedir.

|Döndürülen değer|CRecordset nesneleri üzerindeki etki|
|------------------|----------------------------------|
|SQL_CB_CLOSE|`CRecordset::Requery`İşlem işlemesini hemen takip eden çağrı.|
|SQL_CB_DELETE|`CRecordset::Close`İşlem işlemesini hemen takip eden çağrı.|
|SQL_CB_PRESERVE|İşlemler ile normal olarak devam edin `CRecordset` .|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK ODBC API işlevine bakın `SQLGetInfo` . İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a> CDatabase:: GetCursorRollbackBehavior

Bir [geri alma](#rollback) işleminin açık kayıt kümesi nesnelerinde imleçleri nasıl etkilediğini öğrenmek için bu üye işlevi çağırın.

```
int GetCursorRollbackBehavior() const;
```

### <a name="return-value"></a>Dönüş Değeri

Açık kayıt kümesi nesnelerindeki işlemlerin etkisini gösteren bir değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda, için olası dönüş değerleri `GetCursorRollbackBehavior` ve açık kayıt kümesine karşılık gelen efekt listelenmektedir.

|Döndürülen değer|CRecordset nesneleri üzerindeki etki|
|------------------|----------------------------------|
|SQL_CB_CLOSE|`CRecordset::Requery`İşlem geri alma işleminden hemen sonra çağrı yapın.|
|SQL_CB_DELETE|`CRecordset::Close`İşlem geri alma işleminden hemen sonra çağrı yapın.|
|SQL_CB_PRESERVE|İşlemler ile normal olarak devam edin `CRecordset` .|

Bu dönüş değeri hakkında daha fazla bilgi için Windows SDK ODBC API işlevine bakın `SQLGetInfo` . İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="cdatabasegetdatabasename"></a><a name="getdatabasename"></a> CDatabase:: GetDatabaseName

Şu anda bağlı olan veritabanının adını almak için bu üye işlevi çağırın (veri kaynağı "veritabanı" adlı adlandırılmış bir nesneyi tanımladığından).

```
CString GetDatabaseName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa veritabanı adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) ; Aksi takdirde, boş `CString` .

### <a name="remarks"></a>Açıklamalar

Bu, veya çağrısında belirtilen veri kaynağı adı (DSN) ile aynı değildir `OpenEx` `Open` . `GetDatabaseName`Dönüşler ODBC 'ye bağlıdır. Genel olarak, bir veritabanı bir tablo koleksiyonudur. Bu varlık bir ada sahipse, `GetDatabaseName` döndürür.

Örneğin, bu adı bir başlıkta göstermek isteyebilirsiniz. ODBC 'den adı alırken bir hata oluşursa `GetDatabaseName` boş bir değer döndürür `CString` .

## <a name="cdatabaseisopen"></a><a name="isopen"></a> CDatabase:: IsOpen

`CDatabase`Nesnenin şu anda bir veri kaynağına bağlı olup olmadığını anlamak için bu üye işlevi çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CDatabase`Nesne şu anda bağlı ise sıfır dışı; Aksi takdirde 0.

## <a name="cdatabasem_hdbc"></a><a name="m_hdbc"></a> CDatabase:: m_hdbc

Bir ODBC veri kaynağı bağlantısına ("bağlantı tanıtıcısı") genel bir tanıtıcı içerir.

### <a name="remarks"></a>Açıklamalar

Normalde, bu üye değişkenine doğrudan erişmeniz gerekmez. Bunun yerine, veya öğesini çağırdığınızda Framework tanıtıcıyı ayırır `OpenEx` `Open` . Nesne üzerinde işleci çağırdığınızda çerçeve tanıtıcıyı kaldırır **`delete`** `CDatabase` . `Close`Üye işlevinin tanıtıcıyı serbest desteklemediğini unutmayın.

Ancak bazı durumlarda tanıtıcıyı doğrudan kullanmanız gerekebilir. Örneğin, ODBC API işlevlerini doğrudan sınıf yerine doğrudan çağırmanız gerekiyorsa `CDatabase` , parametre olarak geçirmek için bir bağlantı işleyicisine ihtiyacınız olabilir. Aşağıdaki kod örneğine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#15](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]

## <a name="cdatabaseonsetoptions"></a><a name="onsetoptions"></a> CDatabase:: OnSetOptions

Çerçeve, üye işlevi ile bir SQL ifadesini doğrudan yürütürken bu üye işlevini çağırır `ExecuteSQL` .

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Hangi seçeneklerin ayarlandığı ODBC bildiri tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

`CRecordset::OnSetOptions` Ayrıca, bu üye işlevini çağırır.

`OnSetOptions` oturum açma zaman aşımı değerini ayarlar. `SetQueryTimeout`Ve üye işlevine önceki çağrılar varsa, `OnSetOptions` geçerli değerleri yansıtır; Aksi takdirde, varsayılan değerleri ayarlar.

> [!NOTE]
> MFC 4,2 ' den önce, `OnSetOptions` işlem modunu hiç zaman uyumlu veya zaman uyumsuz olarak ayarlayın. MFC 4,2 ' den başlayarak tüm işlemler zaman uyumludur. Zaman uyumsuz bir işlem gerçekleştirmek için ODBC API işlevine doğrudan çağrı yapmanız gerekir `SQLSetPos` .

`OnSetOptions`Zaman aşımı değerini değiştirmek için geçersiz kılmanız gerekmez. Bunun yerine, sorgu zaman aşımı değerini özelleştirmek için, `SetQueryTimeout` bir kayıt kümesi oluşturmadan önce çağırın; `OnSetOptions` yeni değeri kullanacaktır. Değerler kümesi, tüm kayıt kümelerinde veya doğrudan SQL çağrılarında sonraki işlemlere uygulanır.

`OnSetOptions`Ek seçenekleri ayarlamak istiyorsanız geçersiz kılın. Geçersiz kılma işlemi, `OnSetOptions` ODBC API işlevini çağırmadan önce veya sonra temel sınıfı çağırmalıdır `SQLSetStmtOption` . Çerçevesinin varsayılan uygulamasında gösterilen yöntemi izleyin `OnSetOptions` .

## <a name="cdatabaseopen"></a><a name="open"></a> CDatabase:: Open

Yeni oluşturulan bir nesneyi başlatmak için bu üye işlevini çağırın `CDatabase` .

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
ODBC yönetici programı aracılığıyla ODBC ile kaydedilen bir ad olan bir veri kaynağı adı belirtir. *LpszConnect* IÇINDE bir DSN değeri belirtilmişse ("DSN = \<data-source> " biçiminde), *lpszDSN* içinde yeniden belirtilmemelidir. Bu durumda, *LPSZDSN* null olmalıdır. Aksi takdirde, kullanıcının bir veri kaynağı seçmesini sağlayan bir veri kaynağı iletişim kutusuyla sunmak istiyorsanız NULL değerini geçirebilirsiniz. Daha fazla bilgi için bkz. açıklamalar.

*bExclusive*<br/>
Sınıf kitaplığının bu sürümünde desteklenmiyor. Şu anda, bu parametre TRUE olduğunda bir onaylama başarısız olur. Veri kaynağı her zaman paylaşılan (özel değil) olarak açılır.

*bReadOnly*<br/>
Bağlantıyı Salt okunabilir olacak şekilde düşünüyorsanız ve veri kaynağı için güncelleştirmeleri yasakladıysanız TRUE. Tüm bağımlı kayıt kümeleri bu özniteliği devralınır. Varsayılan değer FALSE 'dur.

*lpszConnect*<br/>
Bir bağlantı dizesi belirtir. Bağlantı dizesi, büyük olasılıkla bir veri kaynağı adı, veri kaynağı üzerinde geçerli bir kullanıcı KIMLIĞI, bir kullanıcı kimlik doğrulama dizesi (veri kaynağı bir tane gerektiriyorsa) ve diğer bilgiler dahil olmak üzere bilgileri birleştirir. Tüm bağlantı dizesi "ODBC;" dizesinin önüne alınmalıdır (büyük veya küçük harf). "ODBC;" dizesi, bağlantının bir ODBC veri kaynağına ait olduğunu göstermek için kullanılır; Bu, sınıf kitaplığının gelecekteki sürümleri ODBC olmayan veri kaynaklarını destekliyorsa, daha yüksek uyumluluk içindir.

*bUseCursorLib*<br/>
ODBC Imleç kitaplığı DLL dosyasının yüklenmesini istiyorsanız TRUE. İmleç kitaplığı, temel alınan ODBC sürücüsünün bazı işlevlerini maskeler ve dinamik kümeler kullanımını etkili bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklendiğinde desteklenen imleçler yalnızca statik anlık görüntüler ve salt ileri imleçler olur. Varsayılan değer TRUE 'dur. İçinden türetmeden doğrudan bir kayıt kümesi nesnesi oluşturmayı planlıyorsanız `CRecordset` , imleç kitaplığı 'nı yüklenmemelisiniz.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapıldıysa sıfır dışı; Aksi takdirde, Kullanıcı daha fazla bağlantı bilgileri soran bir iletişim kutusu sunulursa Iptal ' i seçerse 0. Diğer tüm durumlarda Framework bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmeniz için veritabanı nesnenizin başlatılması gerekir.

> [!NOTE]
> [OpenEx](#openex) üye işlevini çağırmak, bir veri kaynağına bağlanmak ve veritabanı nesneniz başlatmak için tercih edilen yoldur.

`Open`Çağrınızdan parametreler bağlantıyı oluşturmak için yeterli bilgi içermiyorsa, ODBC sürücüsü kullanıcıdan gerekli bilgileri almak için bir iletişim kutusu açar. ' İ çağırdığınızda, `Open` bağlantı dizeniz *lpszConnect*, nesneye özel olarak depolanır `CDatabase` ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgi almak için çağrı yapmadan önce kendi iletişim kutusunu açabilir `Open` ve sonra bu bilgileri geçirdiğiniz bağlantı dizesine ekleyebilirsiniz `Open` . Ya da geçirdiğiniz bağlantı dizesini kaydederek uygulamanızın bir nesne üzerinde çağrı yaptığı bir dahaki sefer onu yeniden kullanabilirsiniz `Open` `CDatabase` .

Bağlantı dizesini, birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDatabase` nesne için) veya veri kaynağına özgü diğer bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için, Windows SDK bölüm 5 ' i inceleyin.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `Open` bir oluşturur `CDBException` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#14](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]

## <a name="cdatabaseopenex"></a><a name="openex"></a> CDatabase:: OpenEx

Yeni oluşturulan bir nesneyi başlatmak için bu üye işlevini çağırın `CDatabase` .

```
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,
    DWORD dwOptions = 0);
```

### <a name="parameters"></a>Parametreler

*lpszConnectString*<br/>
Bir ODBC bağlantı dizesi belirtir. Bu, veri kaynağı adının yanı sıra Kullanıcı KIMLIĞI ve parola gibi diğer isteğe bağlı bilgileri de içerir. Örneğin, "DSN = SQLServer_Source; UID = SA; PWD = abc123 "olası bir bağlantı dizesidir. *LpszConnectString* için null geçirirseniz, bir veri kaynağı iletişim kutusu kullanıcıdan bir veri kaynağı seçmesini ister.

*dwOptions*<br/>
Aşağıdaki değerlerin birleşimini belirten bir bit maskesi. Varsayılan değer 0 ' dır, yani veritabanının yazma erişimiyle paylaşılan olarak açılabileceği anlamına gelir, ODBC Imleç kitaplığı DLL 'SI yüklenmez ve ODBC bağlantısı iletişim kutusu yalnızca bağlantıyı kurmak için yeterli bilgi yoksa görüntülenir.

- `CDatabase::openExclusive` Sınıf kitaplığının bu sürümünde desteklenmiyor. Bir veri kaynağı her zaman paylaşılan (özel değil) olarak açılır. Şu anda, bu seçeneği belirtirseniz bir onaylama başarısız olur.

- `CDatabase::openReadOnly` Veri kaynağını salt okuma olarak açın.

- `CDatabase::useCursorLib` ODBC Imleç kitaplığı DLL 'ini yükleyin. İmleç kitaplığı, temel alınan ODBC sürücüsünün bazı işlevlerini maskeler ve dinamik kümeler kullanımını etkili bir şekilde önler (sürücü destekliyorsa). İmleç kitaplığı yüklendiğinde desteklenen imleçler yalnızca statik anlık görüntüler ve salt ileri imleçler olur. İçinden türetmeden doğrudan bir kayıt kümesi nesnesi oluşturmayı planlıyorsanız `CRecordset` , imleç kitaplığı 'nı yüklenmemelisiniz.

- `CDatabase::noOdbcDialog` Yeterli bağlantı bilgilerinin sağlanmadığına bakılmaksızın ODBC bağlantısı iletişim kutusunu görüntülememe.

- `CDatabase::forceOdbcDialog` Her zaman ODBC bağlantısı iletişim kutusunu görüntüleyin.

### <a name="return-value"></a>Dönüş Değeri

Bağlantı başarıyla yapıldıysa sıfır dışı; Aksi takdirde, Kullanıcı daha fazla bağlantı bilgileri soran bir iletişim kutusu sunulursa Iptal ' i seçerse 0. Diğer tüm durumlarda Framework bir özel durum oluşturur.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturmak için kullanabilmeniz için veritabanı nesnenizin başlatılması gerekir.

Çağrınızdan *lpszConnectString* parametresi `OpenEx` Bağlantıyı yapmak için yeterli BILGI içermiyorsa, ODBC sürücüsü bir iletişim kutusu açar, bu, ayarlamış olmanız `CDatabase::noOdbcDialog` veya `CDatabase::forceOdbcDialog` *dwOptions* parametresinde, kullanıcının gerekli bilgilerini elde eder. ' İ çağırdığınızda, `OpenEx` bağlantı dizeniz *lpszConnectString*, nesneye özel olarak depolanır `CDatabase` ve [GetConnect](#getconnect) üye işlevi çağırarak kullanılabilir.

İsterseniz, kullanıcıdan bir parola gibi bilgi almak için çağrı yapmadan önce kendi iletişim kutusunu açabilir `OpenEx` ve sonra bu bilgileri geçirdiğiniz bağlantı dizesine ekleyebilirsiniz `OpenEx` . Ya da geçirdiğiniz bağlantı dizesini kaydederek uygulamanızın bir nesne üzerinde çağrı yaptığı bir dahaki sefer onu yeniden kullanabilirsiniz `OpenEx` `CDatabase` .

Bağlantı dizesini, birden fazla oturum açma yetkilendirmesi (her biri farklı bir `CDatabase` nesne için) veya veri kaynağına özgü diğer bilgileri iletmek için de kullanabilirsiniz. Bağlantı dizeleri hakkında daha fazla bilgi için, bkz. Bölüm 6, *ODBC Programcı başvurusu*.

Örneğin, DBMS ana bilgisayarı kullanılamadığında bir bağlantı girişimi zaman aşımına uğrar. Bağlantı girişimi başarısız olursa, `OpenEx` bir oluşturur `CDBException` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#11](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]

## <a name="cdatabaserollback"></a><a name="rollback"></a> CDatabase:: Rollback

İşlem sırasında yapılan değişiklikleri tersine çevirmek için bu üye işlevini çağırın.

```
BOOL Rollback();
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başarıyla geri çevrilirse sıfır dışı; Aksi takdirde 0. Bir `Rollback` çağrı başarısız olursa, veri kaynağı ve işlem durumları tanımsızdır. `Rollback`0 döndürürse, durumunu öğrenmek için veri kaynağını denetlemeniz gerekir.

### <a name="remarks"></a>Açıklamalar

`CRecordset` `AddNew` `Edit` `Delete` `Update` Son [BeginTrans](#begintrans) bu çağrı sırasında var olan duruma geri alındığından,, ve tüm çağrılar yürütülür.

Bir çağrısından sonra, `Rollback` işlem bittikten sonra, `BeginTrans` başka bir işlem için yeniden çağırmanız gerekir. Çağrılmadan önce geçerli olan kayıt, `BeginTrans` sonra geçerli kayıt haline gelir `Rollback` .

Geri alma işleminden sonra, geri alma işleminden önce geçerli olan kayıt geçerli olmaya devam eder. Bir geri alma işleminden sonra kayıt kümesinin ve veri kaynağının durumu hakkında ayrıntılar için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

  İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

## <a name="cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a> CDatabase:: SetLoginTimeout

`OpenEx` `Open` Denenen bir veri kaynağı bağlantısı zaman aşımına uğramadan önce izin verilen varsayılan saniye sayısını geçersiz kılmak için, veya ' i çağırmadan önce Bu üye işlevini çağırın.

```cpp
void SetLoginTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Bağlantı girişimi zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Örneğin, DBMS kullanılamıyorsa bir bağlantı girişimi zaman aşımına uğrar. `SetLoginTimeout`Başlatılmamış nesneyi oluşturduktan sonra, `CDatabase` veya öğesini çağırmadan önce çağırın `OpenEx` `Open` .

Oturum açma zaman aşımları için varsayılan değer 15 saniyedir. Tüm veri kaynakları, bir oturum açma zaman aşımı değeri belirtme yeteneğini desteklemez. Veri kaynağı zaman aşımını desteklemiyorsa, izleme çıkışı alırsınız ancak özel durum oluşturmaz. 0 değeri "sonsuz" anlamına gelir.

## <a name="cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a> CDatabase:: SetQueryTimeout

Bağlı veri kaynağındaki sonraki işlemlerin zaman aşımına geçmeden önce izin verilecek varsayılan saniye sayısını geçersiz kılmak için bu üye işlevi çağırın.

```cpp
void SetQueryTimeout(DWORD dwSeconds);
```

### <a name="parameters"></a>Parametreler

*dwSeconds*<br/>
Sorgu girişiminden zaman aşımına uğramadan önce izin verilen saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Ağ erişimi sorunları, aşırı sorgu işleme süresi vb. nedeniyle bir işlem zaman aşımına uğrar. `SetQueryTimeout`Kayıt kümenize açmadan önce veya `AddNew` `Update` `Delete` sorgu zaman aşımı değerini değiştirmek istiyorsanız kayıt kümesini veya üye işlevlerini çağırmadan önce çağırın. `Open`Bu ayar, sonraki,, `AddNew` , `Update` ve `Delete` Bu nesneyle ilişkili tüm kayıt kümelerine yapılan çağrıları etkiler `CDatabase` . Açıldıktan sonra bir kayıt kümesi için sorgu zaman aşımı değerini değiştirme, kayıt kümesinin değerini değiştirmez. Örneğin, sonraki `Move` işlemler yeni değeri kullanmaz.

Sorgu zaman aşımları için varsayılan değer 15 saniyedir. Tüm veri kaynakları bir sorgu zaman aşımı değeri ayarlama yeteneğini desteklemez. 0 ' ın bir sorgu zaman aşımı değeri ayarlarsanız zaman aşımı oluşmaz; veri kaynağıyla iletişim yanıt vermeyi durdurabilir. Bu davranış geliştirme sırasında yararlı olabilir. Veri kaynağı zaman aşımını desteklemiyorsa, izleme çıkışı alırsınız ancak özel durum oluşturmaz.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
