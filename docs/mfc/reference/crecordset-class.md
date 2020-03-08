---
title: CRecordset sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
ms.openlocfilehash: 1ebdb18254171d28b5d5e02367596b79142df284
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854032"
---
# <a name="crecordset-class"></a>CRecordset sınıfı

Bir veri kaynağından seçilen bir kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset:: CRecordset](#crecordset)|`CRecordset` nesnesi oluşturur. Türetilmiş sınıfınız bunu çağıran bir Oluşturucu sağlamalıdır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset:: AddNew](#addnew)|Yeni bir kayıt eklemeye hazırlar. Ekleme işleminin tamamlanabilmesi için `Update` çağırın.|
|[CRecordset:: CanAppend](#canappend)|`AddNew` üye işlevi aracılığıyla kayıt kümesine yeni kayıtlar eklenebileceği sıfır dışında bir değer döndürür.|
|[CRecordset:: CanBookmark](#canbookmark)|Kayıt kümesi yer imlerini destekliyorsa sıfır dışında bir değer döndürür.|
|[CRecordset:: Cancel](#cancel)|Zaman uyumsuz bir işlemi veya ikinci bir iş parçacığından bir işlemi iptal eder.|
|[CRecordset:: CancelUpdate](#cancelupdate)|`AddNew` veya `Edit` işlemi nedeniyle bekleyen tüm güncelleştirmeleri iptal eder.|
|[CRecordset:: CanRestart](#canrestart)|Kayıt kümesinin sorgusunu yeniden çalıştırmak için `Requery` çağrılırsa sıfır dışı döndürür.|
|[CRecordset:: CanScroll](#canscroll)|Kayıtlar arasında gezinebilirsiniz, sıfır dışında bir değer döndürür.|
|[CRecordset:: CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CRecordset:: CanUpdate](#canupdate)|Kayıt kümesi güncelleştiribir şekilde (kayıt ekleyebilir, güncelleştirebilir veya silebilirsiniz) sıfır dışında bir değer döndürür.|
|[CRecordset:: CheckRowsetError](#checkrowseterror)|Kayıt getirilirken oluşturulan hataları işlemek için çağırılır.|
|[CRecordset:: Close](#close)|Kayıt kümesini ve onunla ilişkili ODBC HSTMT 'yi kapatır.|
|[CRecordset::D Sil](#delete)|Kayıt kümesinden geçerli kaydı siler. Silme işleminden sonra açıkça başka bir kayda kaydırma yapmanız gerekir.|
|[CRecordset::D oBulkFieldExchange](#dobulkfieldexchange)|Veri kaynağından kayıt kümesine toplu veri verileri alışverişi için çağırılır. Toplu kayıt alanı değişimi (toplu RFX) uygular.|
|[CRecordset::D oFieldExchange](#dofieldexchange)|Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki karşılık gelen kayıt arasındaki verileri (her iki yönde) değiş tokuş etmek için çağırılır. Kayıt alanı değişimi (RFX) uygular.|
|[CRecordset:: Edit](#edit)|Geçerli kayıttaki değişikliklere hazırlar. Düzenleme işleminin tamamlanabilmesi için `Update` çağırın.|
|[CRecordset:: FlushResultSet](#flushresultset)|Önceden tanımlanmış bir sorgu kullanılırken, alınacak başka bir sonuç kümesi varsa sıfır dışında bir değer döndürür.|
|[CRecordset:: GetBookmark](#getbookmark)|Bir kaydın yer işareti değerini parametre nesnesine atar.|
|[CRecordset:: GetDefaultConnect](#getdefaultconnect)|Varsayılan bağlantı dizesini almak için çağırılır.|
|[CRecordset:: GetDefaultSQL](#getdefaultsql)|Yürütülecek varsayılan SQL dizesini almak için çağırılır.|
|[CRecordset:: GetFieldValue](#getfieldvalue)|Bir kayıt kümesindeki bir alanın değerini döndürür.|
|[CRecordset:: GetODBCFieldCount](#getodbcfieldcount)|Kayıt kümesindeki alan sayısını döndürür.|
|[CRecordset:: GetODBCFieldInfo](#getodbcfieldinfo)|Bir kayıt kümesindeki alanlarla ilgili belirli tür bilgileri döndürür.|
|[CRecordset:: GetRecordCount](#getrecordcount)|Kayıt kümesindeki kayıt sayısını döndürür.|
|[CRecordset:: GetRowsetSize](#getrowsetsize)|Tek bir getirme sırasında almak istediğiniz kayıt sayısını döndürür.|
|[CRecordset:: Getrowsgetirilen](#getrowsfetched)|Bir getirme sırasında alınan satırların gerçek sayısını döndürür.|
|[CRecordset:: GetRowStatus](#getrowstatus)|Bir getirme işleminden sonra satırın durumunu döndürür.|
|[CRecordset:: GetSQL](#getsql)|Kayıt kümesi için kayıt seçmek üzere kullanılan SQL dizesini alır.|
|[CRecordset:: GetStatus](#getstatus)|Kayıt kümesinin durumunu alır: geçerli kaydın dizini ve kayıtların son sayımının alınıp alınmayacağı.|
|[CRecordset:: GetTableName](#gettablename)|Kayıt kümesinin temel aldığı tablonun adını alır.|
|[CRecordset:: IsBOF](#isbof)|Kayıt kümesi ilk kayıttan önce konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.|
|[CRecordset:: IsDeleted](#isdeleted)|Kayıt kümesi silinen bir kayıt üzerinde konumlandırılmışsa sıfır dışında bir değer döndürür.|
|[CRecordset:: IsEOF](#iseof)|Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.|
|[CRecordset:: IsFieldDirty](#isfielddirty)|Geçerli kayıttaki belirtilen alan değiştirilmişse sıfır dışında bir değer döndürür.|
|[CRecordset:: IsFieldNull](#isfieldnull)|Geçerli kayıttaki belirtilen alan null ise (değer yoksa) sıfır dışında bir değer döndürür.|
|[CRecordset:: Isfieldnullenebilir](#isfieldnullable)|Geçerli kayıttaki belirtilen alan null (değer olmadan) olarak ayarlandıysa sıfır dışında bir değer döndürür.|
|[CRecordset:: IsOpen](#isopen)|Daha önce çağrılırsa `Open` sıfır dışı döndürür.|
|[CRecordset:: Move](#move)|Kayıt kümesini geçerli kayıttaki belirtilen sayıda kayda her iki yönde konumlandırır.|
|[CRecordset:: MoveFirst](#movefirst)|Kayıt kümesindeki ilk kayıttaki geçerli kaydı konumlandırır. Önce `IsBOF` için test edin.|
|[CRecordset:: MoveLast](#movelast)|Son kayıttaki veya son satır kümesindeki geçerli kaydı konumlandırır. Önce `IsEOF` için test edin.|
|[CRecordset:: MoveNext](#movenext)|Sonraki kayıttaki veya bir sonraki satır kümesindeki geçerli kaydı konumlandırır. Önce `IsEOF` için test edin.|
|[CRecordset:: Moveöncekini](#moveprev)|Önceki kayıttaki veya önceki satır kümesindeki geçerli kaydı konumlandırır. Önce `IsBOF` için test edin.|
|[CRecordset:: OnSetOptions](#onsetoptions)|Belirtilen ODBC ifadesinin seçeneklerini (seçimde kullanılan) ayarlamak için çağırılır.|
|[CRecordset:: OnSetUpdateOptions](#onsetupdateoptions)|Belirtilen ODBC ifadesinin seçeneklerini (güncelleştirmede kullanılır) ayarlamak için çağırılır.|
|[CRecordset:: Open](#open)|Tabloyu alarak veya kayıt kümesinin temsil ettiği sorguyu gerçekleştirerek kayıt kümesini açar.|
|[CRecordset:: RefreshRowset](#refreshrowset)|Belirtilen satırların verilerini ve durumunu yeniler.|
|[CRecordset:: Requery](#requery)|Seçilen kayıtları yenilemek için kayıt kümesinin sorgusunu yeniden çalıştırır.|
|[CRecordset:: SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesini belirtilen kayıt numarasına karşılık gelen kayıtta konumlandırır.|
|[CRecordset:: SetBookmark](#setbookmark)|Yer işareti tarafından belirtilen kayıttaki kayıt kümesini konumlandırır.|
|[CRecordset:: SetFieldDirty](#setfielddirty)|Geçerli kayıttaki belirtilen alanı değiştirildi olarak işaretler.|
|[CRecordset:: SetFieldNull](#setfieldnull)|Geçerli kayıttaki belirtilen alanın değerini null olarak ayarlar (hiçbir değer olmadan).|
|[CRecordset:: SetLockingMode](#setlockingmode)|Kilitleme modunu "iyimser" kilitleme (varsayılan) veya "kötümser" kilitleme olarak ayarlar. Kayıtların güncelleştirmeler için nasıl kilitlendiğini belirler.|
|[CRecordset:: SetParamNull](#setparamnull)|Belirtilen parametreyi null (değer olmadan) olarak ayarlar.|
|[CRecordset:: SetRowsetCursorPosition](#setrowsetcursorposition)|İmleci satır kümesi içindeki belirtilen satıra konumlandırır.|
|[CRecordset:: SetRowsetSize](#setrowsetsize)|Bir getirme sırasında almak istediğiniz kayıt sayısını belirtir.|
|[CRecordset:: Update](#update)|Yeni veya düzenlenmiş verileri veri kaynağına kaydederek bir `AddNew` veya `Edit` işlemi tamamlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset:: m_hstmt](#m_hstmt)|Kayıt kümesi için ODBC ifade tanıtıcısını içerir. `HSTMT` yazın.|
|[CRecordset:: m_nFields](#m_nfields)|Kayıt kümesindeki alan veri üyelerinin sayısını içerir. `UINT` yazın.|
|[CRecordset:: m_nParams](#m_nparams)|Kayıt kümesindeki parametre veri üyelerinin sayısını içerir. `UINT` yazın.|
|[CRecordset:: m_pDatabase](#m_pdatabase)|Kayıt kümesinin bir veri kaynağına bağlı olduğu `CDatabase` nesnesine yönelik bir işaretçi içerir.|
|[CRecordset:: m_strFilter](#m_strfilter)|Bir Yapılandırılmış Sorgu Dili (SQL) `WHERE` yan tümcesini belirten bir `CString` içerir. Yalnızca belirli ölçütlere uyan kayıtları seçmek için filtre olarak kullanılır.|
|[CRecordset:: m_strSort](#m_strsort)|Bir SQL `ORDER BY` yan tümcesini belirten bir `CString` içerir. Kayıtların nasıl sıralanacağını denetlemek için kullanılır.|

## <a name="remarks"></a>Açıklamalarının

"Kayıt kümeleri" olarak bilinen `CRecordset` nesneleri genellikle iki biçimde kullanılır: Dinamik kümeler ve anlık görüntüler. DYNASET, diğer kullanıcılar tarafından yapılan veri güncelleştirmeleriyle eşitlenmiş olarak kalır. Anlık görüntü, verilerin statik bir görünümüdür. Her form, kayıt kümesinin açıldığı sırada düzeltilen bir kayıt kümesini temsil eder, ancak bir Dynaset içindeki bir kayda kaydırdığınızda, diğer kullanıcılar veya uygulamanızdaki diğer kayıt kümeleri tarafından daha sonra yapılan değişiklikleri yansıtır.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine Class [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Her iki tür kayıt kümesiyle çalışmak için, genellikle `CRecordset`' den uygulamaya özgü bir kayıt kümesi sınıfı türetirsiniz. Kayıt kümeleri bir veri kaynağından kayıtları seçer ve ardından şunları yapabilirsiniz:

- Kayıtlarda ilerleyin.

- Kayıtları güncelleştirin ve kilitleme modunu belirtin.

- Veri kaynağında kullanılabilir olanlardan seçim yaptığı kayıtları kısıtlamak için kayıt kümesini filtreleyin.

- Kayıt kümesini sıralayın.

- Çalışma zamanına kadar bilinmeyen bilgilerle seçimini özelleştirmek için kayıt kümesini parametreleştirin.

Sınıfınızı kullanmak için bir veritabanı açın ve bir kayıt kümesi nesnesi oluşturun ve oluşturucuyu `CDatabase` nesnesine bir işaretçi geçirerek. Ardından, nesnenin Dynaset veya anlık görüntü olduğunu belirtebileceğiniz kayıt kümesinin `Open` üye işlevini çağırın. Çağırma `Open` veri kaynağından veri seçer. Kayıt kümesi nesnesi açıldıktan sonra, kayıtlarda gezinmek ve üzerinde işlem yapmak için üye işlevlerini ve veri üyelerini kullanın. Kullanılabilir işlemler, nesnenin bir değişken kümesi mi yoksa anlık görüntü mi olduğunu, güncelleştirilebilir mi yoksa salt okunurdur mi olduğunu (Bu, açık veritabanı bağlantısı (ODBC) veri kaynağının özelliğine bağlıdır) ve toplu satır getirme uyguladığınıza göre değişir. `Open` çağrısından bu yana değiştirilmiş veya eklenmiş olabilecek kayıtları yenilemek için, nesnenin `Requery` üye işlevini çağırın. Nesnenin `Close` üye işlevini çağırın ve ile bitirdiğinizde nesneyi yok edin.

Türetilmiş bir `CRecordset` sınıfında kayıt alanlarını okumayı ve güncelleştirmeyi desteklemek için kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (toplu RFX) kullanılır.

Kayıt kümeleri ve kayıt alanı değişimi hakkında daha fazla bilgi için bkz. makalelere [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md), [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md). Dinamik [kümeler ve anlık](../../data/odbc/dynaset.md) görüntülere odaklanmak için bkz [..](../../data/odbc/snapshot.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

##  <a name="addnew"></a>CRecordset:: AddNew

Tabloya yeni bir kayıt eklemeye hazırlar.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Yeni eklenen kaydı görmek için [YenidenSorgula](#requery) üye işlevini çağırmanız gerekir. Kaydın alanları başlangıçta null. (Veritabanı terimlerinde null "değer yok" anlamına gelir ve içinde C++null ile aynı değildir.) İşlemi gerçekleştirmek için, [Update](#update) member işlevini çağırmanız gerekir. `Update`, veri kaynağına yaptığınız değişiklikleri kaydeder.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `AddNew`çağıramaz. Bu, başarısız bir onaylama işlemi oluşmasına neden olur. `CRecordset` sınıfı, toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, `SQLSetPos`ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew`, kayıt kümesinin alan veri üyelerini kullanarak yeni, boş bir kayıt hazırlar. `AddNew`çağırdıktan sonra, kayıt kümesinin alan veri üyelerinde istediğiniz değerleri ayarlayın. (Bu amaçla üye [Düzenle](#edit) işlevini çağırmanız gerekmez; yalnızca mevcut kayıtlar için `Edit` kullanın.) Daha sonra `Update`çağırdığınızda, alan veri üyelerinde değiştirilen değerler veri kaynağına kaydedilir.

> [!CAUTION]
>  `Update`çağırmadan önce yeni bir kayda kayırsanız, yeni kayıt kaybolur ve hiçbir uyarı verilmez.

Veri kaynağı işlemleri destekliyorsa `AddNew` bir işlemin parçası olarak çağrı yapabilirsiniz. İşlemler hakkında daha fazla bilgi için bkz. sınıf [CDatabase](../../mfc/reference/cdatabase-class.md). `AddNew`çağrılmadan önce [CDatabase:: BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağrısı yapmanız gerektiğini unutmayın.

> [!NOTE]
>  Dinamik kümeler için son kayıt olarak kayıt kümesine yeni kayıtlar eklenir. Eklenen kayıtlar anlık görüntülere eklenmez; kayıt kümesini yenilemek için `Requery` çağırmanız gerekir.

`Open` üye işlevi çağrılmayan bir kayıt kümesi için `AddNew` çağrısı geçersizdir. Öğesine eklenemedikleri bir kayıt kümesi için `AddNew` çağırırsanız bir `CDBException` oluşturulur. Kayıt kümesinin [CanAppend](#canappend)çağırarak güncelleştirilebilir olup olmadığını belirleyebilirsiniz.

Daha fazla bilgi için şu makalelere bakın: [kayıt kümesi: kayıt kümelerinin kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)(ODBC) ve [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

##  <a name="canappend"></a>CRecordset:: CanAppend

Daha önce açılan kayıt kümesinin yeni kayıtlar eklemenize izin verip sağlamadığını belirler.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yeni kayıtlar eklemeye izin veriyorsa sıfır dışı; Aksi takdirde 0. kayıt kümesini salt okunurdur olarak açtıysanız `CanAppend` 0 döndürür.

##  <a name="canbookmark"></a>CRecordset:: CanBookmark

Kayıt kümesinin, kayıt imlerini kullanarak kayıtları işaretlemenize izin verip sağlamadığını belirler.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümeleri, yer işaretlerini destekliyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, [Open](#open) member Işlevinin *dwoptions* parametresindeki `CRecordset::useBookmarks` seçeneğinden bağımsızdır. `CanBookmark`, verilen ODBC sürücüsünün ve imleç türünün yer imlerini destekleyip desteklemediğini gösterir. `CRecordset::useBookmarks`, desteklenseler de yer işaretlerinin kullanılabilir olup olmadığını gösterir.

> [!NOTE]
>  Yer işaretleri salt iletme kayıt kümelerinde desteklenmez.

Yer işaretleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cancel"></a>CRecordset:: Cancel

Veri kaynağının devam eden bir zaman uyumsuz işlemi ya da ikinci bir iş parçacığından bir işlemi iptal ettiğini ister.

```
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıflarının artık zaman uyumsuz işleme kullanmadığını unutmayın; bir asychronous işlemi gerçekleştirmek için `SQLSetConnectOption`ODBC API işlevini doğrudan çağırmanız gerekir. Daha fazla bilgi için, *ODBC SDK Programcı Kılavuzu*'Ndaki "Işlevleri zaman uyumsuz olarak yürütme" konusuna bakın.

##  <a name="cancelupdate"></a>CRecordset:: CancelUpdate

[Güncelleştirme](#update) çağrılmadan önce, bir [düzenleme](#edit) veya [AddNew](#addnew) işlemi nedeniyle bekleyen tüm güncelleştirmeleri iptal eder.

```
void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu üye işlevi, toplu satır getirme kullanan kayıt kümelerinde uygulanabilir değildir, çünkü bu kayıt kümeleri `Edit`, `AddNew`veya `Update`çağıramaz. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Otomatik kirli alan denetimi etkinse `CancelUpdate`, üye değişkenlerini `Edit` veya `AddNew` çağrılmadan önce sahip oldukları değerlere geri yükler; Aksi takdirde, tüm değer değişiklikleri kalır. Varsayılan olarak, kayıt kümesi açıldığında otomatik alan denetimi etkinleştirilir. Devre dışı bırakmak için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::noDirtyFieldCheck` belirtmeniz gerekir.

Verileri güncelleştirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).

##  <a name="canrestart"></a>CRecordset:: CanRestart

Kayıt kümesinin, `Requery` üye işlevini çağırarak sorgunun (kayıtlarını yenilemek için) yeniden başlatılmasına izin verip sağlamadığını belirler.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

YenidenSorgula izin veriliyorsa sıfır dışı; Aksi takdirde 0.

##  <a name="canscroll"></a>CRecordset:: CanScroll

Kayıt kümesinin kaydırmaya izin verip etmeyeceğini belirler.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kaydırmaya izin veriyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma hakkında daha fazla bilgi için bkz. [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cantransact"></a>CRecordset:: CanTransact

Kayıt kümesinin işlemlere izin verip etmeyeceğini belirler.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi işlemlere izin veriyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>CRecordset:: CanUpdate

Kayıt kümesinin güncelleştirilip güncelleştirimeyeceğini belirler.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirişiyorsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi, temel alınan veri kaynağı salt okunurdur veya kayıt kümesini açtığınızda *dwOptions* parametresinde `CRecordset::readOnly` belirlediyseniz salt okunurdur.

##  <a name="checkrowseterror"></a>CRecordset:: CheckRowsetError

Kayıt getirilirken oluşturulan hataları işlemek için çağırılır.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Parametreler

*Nekcode*<br/>
ODBC API işlevi dönüş kodu. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlevi, kayıtlar getirilirken oluşan hataları işler ve toplu satır getirme sırasında yararlı olur. Kendi hata işleme uygulamak için `CheckRowsetError` geçersiz kılmayı düşünmek isteyebilirsiniz.

`CheckRowsetError`, `Open`, `Requery`veya herhangi bir `Move` işlemi gibi imleç gezinme işleminde otomatik olarak çağrılır. ODBC API işlevinin dönüş değeri `SQLExtendedFetch`geçirilir. Aşağıdaki tabloda, *Nekcode* parametresi için olası değerler listelenmektedir.

|Nekcode|Açıklama|
|--------------|-----------------|
|SQL_SUCCESS|İşlev başarıyla tamamlandı; ek bilgi yok.|
|SQL_SUCCESS_WITH_INFO|İşlev, büyük olasılıkla önemli olmayan bir hatayla başarıyla tamamlandı. Ek bilgiler `SQLError`çağırarak elde edilebilir.|
|SQL_NO_DATA_FOUND|Sonuç kümesindeki tüm satırlar getirildi.|
|SQL_ERROR|İşlev başarısız oldu. Ek bilgiler `SQLError`çağırarak elde edilebilir.|
|SQL_INVALID_HANDLE|Geçersiz ortam tanıtıcısı, bağlantı tanıtıcısı veya ekstre tanıtıcısı nedeniyle işlev başarısız oldu. Bu bir programlama hatası gösterir. `SQLError`ek bilgi yok.|
|SQL_STILL_EXECUTING|Zaman uyumsuz olarak başlatılan bir işlev hala yürütülüyor. Varsayılan olarak, MFC 'nin bu değeri hiçbir şekilde `CheckRowsetError`geçirdiğine unutmayın; MFC artık SQL_STILL_EXECUTING döndürünceye kadar `SQLExtendedFetch` çağırmaya devam eder.|

`SQLError`hakkında daha fazla bilgi için bkz. Windows SDK. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="close"></a>CRecordset:: Close

Kayıt kümesini kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

ODBC HSTMT ve kayıt kümesi için ayrılan çerçeve serbest bırakılır. Genellikle `Close`çağrıldıktan sonra, C++ **Yeni**ile ayrıldıysa kayıt kümesi nesnesini silersiniz.

`Close`çağrıldıktan sonra `Open` yeniden çağırabilirsiniz. Bu, kayıt kümesi nesnesini yeniden kullanmanıza olanak sağlar. Alternatif, `Requery`çağırdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

##  <a name="crecordset"></a>CRecordset:: CRecordset

`CRecordset` nesnesi oluşturur.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
`CDatabase` nesnesine veya NULL değerine yönelik bir işaretçi içerir. NULL değilse ve `CDatabase` nesnenin `Open` üye işlevi onu veri kaynağına bağlamak için çağrılmışsa, kayıt kümesi kendi `Open` çağrısı sırasında sizin için açmaya çalışır. NULL geçirirseniz, ClassWizard ile kayıt kümesi sınıfınızı türettiğiniz zaman belirttiğiniz veri kaynağı bilgileri kullanılarak sizin için bir `CDatabase` nesnesi oluşturulur ve bağlanır.

### <a name="remarks"></a>Açıklamalar

`CRecordset` doğrudan kullanabilir ya da uygulamaya özgü bir sınıfı `CRecordset`türetebilirsiniz. Kayıt kümesi sınıflarınızı türetmek için ClassWizard ' i kullanabilirsiniz.

> [!NOTE]
>  Türetilmiş bir sınıfın kendi oluşturucusunu sağlaması *gerekir* . Türetilmiş sınıfınızın oluşturucusunda, ile ilgili parametreleri geçirerek Oluşturucu `CRecordset::CRecordset`çağırın.

Sizin için otomatik olarak bir `CDatabase` nesnesinin oluşturulmasını ve bağlanmasını sağlamak için kayıt kümesi yapıcısına NULL geçirin. Bu, kayıt kümenizin oluşturmadan önce bir `CDatabase` nesnesi oluşturup bağlamanıza gerek olmayan yararlı bir toplu özelliktir.

### <a name="example"></a>Örnek

Daha fazla bilgi için bkz. [kayıt kümesi: tablo Için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

##  <a name="delete"></a>CRecordset::D Sil

Geçerli kaydı siler.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı bir silme işleminden sonra, kayıt kümesinin alan verisi üyeleri bir boş değere ayarlanır ve silinen kaydın dışına geçmek için `Move` işlevlerinden birini açıkça çağırmanız gerekir. Silinen kaydı kapattıktan sonra buna dönmek mümkün değildir. Veri kaynağı işlemleri destekliyorsa, `Delete` çağrısı bir işlemin parçası yapabilirsiniz. Daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `Delete`çağıramaz. Bu, başarısız bir onaylama işlemi oluşmasına neden olur. `CRecordset` sınıfı, toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, `SQLSetPos`ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir olmalıdır ve `Delete`çağırdığınızda kayıt kümesinde geçerli olan geçerli bir kayıt olmalıdır; Aksi takdirde bir hata oluşur. Örneğin, bir kaydı siler ancak `Delete` yeniden çağırmadan önce yeni bir kayda kaymayın, `Delete` bir [CDBException](../../mfc/reference/cdbexception-class.md)oluşturur.

[AddNew](#addnew) ve [Edit](#edit)'in aksine, bir `Delete` çağrısının ardından [güncelleştirme](#update)çağrısı yoktur. `Delete` çağrısı başarısız olursa, alan veri üyeleri değişmeden bırakılır.

### <a name="example"></a>Örnek

Bu örnek, bir işlevin çerçevesinde oluşturulan bir kayıt kümesini gösterir. Örnek, `m_dbCust`varlığını, `CDatabase` türünde bir üye değişkeninin zaten veri kaynağına bağlı olduğunu varsayar.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

##  <a name="dobulkfieldexchange"></a>CRecordset::D oBulkFieldExchange

Veri kaynağından kayıt kümesine toplu veri verileri alışverişi için çağırılır. Toplu kayıt alanı değişimi (toplu RFX) uygular.

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Çerçeve, alan değişim işlemi için bir bağlam belirtmek üzere bu nesneyi zaten ayarlamış.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulandığında, çerçeve veri kaynağındaki verileri kayıt kümesi nesneniz için otomatik olarak aktarmak üzere bu üye işlevini çağırır. `DoBulkFieldExchange` Ayrıca parametre veri üyelerinize, varsa kayıt kümesinin seçimine ait SQL deyimindeki parametre yer tutucularına bağlar.

Toplu satır getirme uygulanmadığından, Framework, [DoFieldExchange](#dofieldexchange)' i çağırır. Toplu satır getirmeyi uygulamak için, [Açık](#open) üye Işlevindeki *dwoptions* parametresinin `CRecordset::useMultiRowFetch` seçeneğini belirtmeniz gerekir.

> [!NOTE]
> `DoBulkFieldExchange`, yalnızca `CRecordset`türetilmiş bir sınıf kullanıyorsanız kullanılabilir. Doğrudan `CRecordset`bir kayıt kümesi nesnesi oluşturduysanız, verileri almak için [GetFieldValue](#getfieldvalue) üye işlevini çağırmanız gerekir.

Toplu kayıt alanı değişimi (toplu RFX), kayıt alanı değişimi (RFX) ile benzerdir. Veriler veri kaynağından kayıt kümesi nesnesine otomatik olarak aktarılır. Ancak, değişiklikleri veri kaynağına geri aktarmak için `AddNew`, `Edit`, `Delete`veya `Update` çağıramıyorsunuz. Sınıf `CRecordset` Şu anda toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamıyor; Ancak, `SQLSetPos`ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz.

ClassWizard 'ın toplu kayıt alanı değişimini desteklemediğini unutmayın; Bu nedenle, toplu RFX işlevlerine çağrılar yazarak `DoBulkFieldExchange` el ile geçersiz kılmanız gerekir. Bu işlevler hakkında daha fazla bilgi için bkz. [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).

Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). İlgili bilgiler için bkz. [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="dofieldexchange"></a>CRecordset::D oFieldExchange

Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki karşılık gelen kayıt arasındaki verileri (her iki yönde) değiş tokuş etmek için çağırılır. Kayıt alanı değişimi (RFX) uygular.

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine yönelik bir işaretçi. Çerçeve, alan değişim işlemi için bir bağlam belirtmek üzere bu nesneyi zaten ayarlamış.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulanmadığı zaman, çerçeve, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasında otomatik olarak veri alışverişi yapmak için bu üye işlevini çağırır. `DoFieldExchange` Ayrıca parametre veri üyelerinize, varsa kayıt kümesinin seçimine ait SQL deyimindeki parametre yer tutucularına bağlar.

Toplu satır getirme uygulanmışsa, Framework [DoBulkFieldExchange](#dobulkfieldexchange)çağırır. Toplu satır getirmeyi uygulamak için, [Açık](#open) üye Işlevindeki *dwoptions* parametresinin `CRecordset::useMultiRowFetch` seçeneğini belirtmeniz gerekir.

> [!NOTE]
> `DoFieldExchange`, yalnızca `CRecordset`türetilmiş bir sınıf kullanıyorsanız kullanılabilir. Doğrudan `CRecordset`bir kayıt kümesi nesnesi oluşturduysanız, verileri almak için [GetFieldValue](#getfieldvalue) üye işlevini çağırmanız gerekir.

Kayıt alanı değişimi (RFX) olarak adlandırılan alan verileri alışverişi her iki yönde de geçerlidir: kayıt kümesi nesnesinin alan verileri üyelerinden veri kaynağındaki kaydın alanları ve veri kaynağındaki kayıttan kayıt kümesi nesnesi.

Yalnızca türetilmiş kayıt kümesi sınıfınız için `DoFieldExchange` uygulamak için gerçekleştirmeniz gereken tek eylem, sınıfı ClassWizard ile oluşturmak ve alan veri üyelerinin adlarını ve veri türlerini belirtmek içindir. Ayrıca, parametre veri üyelerini belirtmek veya dinamik olarak bağlanan tüm sütunlarla uğraşmak için ClassWizard 'ın yazdığı kodu da ekleyebilirsiniz. Daha fazla bilgi için bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Türetilmiş kayıt kümesi sınıfınızı ClassWizard ile bildirdiğinizde, sihirbaz sizin için `DoFieldExchange` bir geçersiz kılma yazar ve bu örnek aşağıdaki örneğe benzer:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).

`DoFieldExchange`hakkında daha fazla örnek ve Ayrıntılar için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md). RFX hakkında genel bilgi için bkz. [kayıt alanı değişimi](../../data/odbc/record-field-exchange-rfx.md)makalesi.

##  <a name="edit"></a>CRecordset:: Edit

Geçerli kayıtta değişikliklere izin verir.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

`Edit`çağırdıktan sonra, değerlerini doğrudan sıfırlayarak alan veri üyelerini değiştirebilirsiniz. Değişiklikleri veri kaynağına kaydetmek için daha sonra [Update](#update) member işlevini çağırdığınızda işlem tamamlanır.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `Edit`çağıramaz. Bu, başarısız bir onaylama işlemi oluşmasına neden olur. `CRecordset` sınıfı, toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, `SQLSetPos`ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit`, kayıt kümesinin veri üyelerinin değerlerini kaydeder. `Edit`çağırır, değişiklikler yaparsanız ve `Edit` yeniden çağırırsanız, kaydın değerleri ilk `Edit` çağrısından önceki duruma geri yüklenir.

Bazı durumlarda, null (veri içermeyen) yaparak bir sütunu güncelleştirmek isteyebilirsiniz. Bunu yapmak için, null parametresiyle [SetFieldNull](#setfieldnull) çağrısı yapın, alanı null olarak işaretleyin; Bu, sütunun güncelleştirilmesine de neden olur. Değer değişmemiş olmasına rağmen bir alanın veri kaynağına yazılmasını istiyorsanız, TRUE parametresiyle [SetFieldDirty](#setfielddirty) çağırın. Bu, alanda null değeri olsa bile işe yarar.

Veri kaynağı işlemleri destekliyorsa, `Edit` çağrısı bir işlemin parçası yapabilirsiniz. `Edit` çağrılmadan önce ve kayıt kümesi açıldıktan sonra [CDatabase:: BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağrısı yapmanız gerektiğini unutmayın. Ayrıca, `Edit` işleminin tamamlanabilmesi için [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) çağırmanın `Update` çağrısı için bir yedek olmadığına de unutmayın. İşlemler hakkında daha fazla bilgi için bkz. sınıf [CDatabase](../../mfc/reference/cdatabase-class.md).

Geçerli kilitleme moduna bağlı olarak, `Update` çağırana veya başka bir kayda kaydırma yapana kadar, güncelleştirilmekte olan kayıt `Edit` tarafından kilitlenebilir veya yalnızca `Edit` çağrısı sırasında kilitlenmiş olabilir. Kilit modunu [SetLockingMode](#setlockingmode)ile değiştirebilirsiniz.

`Update`çağrılmadan önce yeni bir kayda kaydırırsanız geçerli kaydın önceki değeri geri yüklenir. Güncelleştirilemeyen bir kayıt kümesi için `Edit` çağırdıysanız veya geçerli kayıt yoksa `CDBException` atılır.

Daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md) ve [kayıt kümesi: KAYıTLARı kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

##  <a name="flushresultset"></a>CRecordset:: FlushResultSet

Birden çok sonuç kümesi varsa, önceden tanımlanmış bir sorgunun (saklı yordam) bir sonraki sonuç kümesini alır.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Dönüş Değeri

Alınacak daha fazla sonuç kümesi varsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca geçerli sonuç kümesinde imleç ile tamamen işiniz bittiğinde `FlushResultSet` çağırmalısınız. `FlushResultSet`çağırarak bir sonraki sonuç kümesini aldığınızda, imlecinizin bu sonuç kümesinde geçerli olmadığı unutulmamalıdır; `FlushResultSet`çağrıldıktan sonra [MoveNext](#movenext) üye işlevini çağırmanız gerekir.

Önceden tanımlanmış bir sorgu çıkış parametresi veya giriş/çıkış parametreleri kullanıyorsa, bu parametre değerlerini almak için `FALSE` (0 değeri) görünene kadar `FlushResultSet` çağırmanız gerekir.

`FlushResultSet` ODBC API işlevini `SQLMoreResults`çağırır. `SQLMoreResults` SQL_ERROR veya SQL_INVALID_HANDLE döndürürse `FlushResultSet` bir özel durum oluşturulur. `SQLMoreResults`hakkında daha fazla bilgi için bkz. Windows SDK.

`FlushResultSet`çağırmak istiyorsanız, saklı yordamınız bağlantılı alanlara sahip olmalıdır.

### <a name="example"></a>Örnek

Aşağıdaki kod, `COutParamRecordset` bir giriş parametresi ve bir çıkış parametresi ve birden çok sonuç kümesine sahip önceden tanımlanmış bir sorgu temel alınarak `CRecordset`türetilmiş bir nesne olduğunu varsayar. [DoFieldExchange](#dofieldexchange) geçersiz kılma yapısına göz önünde edin.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

##  <a name="getbookmark"></a>CRecordset:: GetBookmark

Geçerli kayıt için yer işareti değerini alır.

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Geçerli kayıttaki yer işaretini temsil eden bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinde yer işaretlerinin desteklenip desteklenmediğini anlamak için [CanBookmark](#canbookmark)çağırın. Eğer desteklendiklerinde yer imlerini kullanılabilir hale getirmek için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::useBookmarks` seçeneğini ayarlamanız gerekir.

> [!NOTE]
>  Yer işaretleri desteklenmiyorsa veya kullanılamıyorsa, `GetBookmark` çağırmak bir özel durum oluşmasına neden olur. Yer işaretleri salt iletme kayıt kümelerinde desteklenmez.

`GetBookmark` geçerli kayıt için yer işaretinin değerini bir `CDBVariant` nesnesine atar. Farklı bir kayda geçtikten sonra istediğiniz zaman bu kayda dönmek için, karşılık gelen `CDBVariant` nesnesiyle birlikte [SetBookmark](#setbookmark) çağırın.

> [!NOTE]
>  Belirli kayıt kümesi işlemlerinden sonra, yer işaretleri artık geçerli olmayabilir. Örneğin, `Requery`tarafından izlenen `GetBookmark` çağırırsanız `SetBookmark`ile kayda geri dönemeyebilirsiniz. `SetBookmark`güvenli bir şekilde çağırıp çağıramayacağını denetlemek için [CDatabase:: Getbookmarkkalıcılığı](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) çağırın.

Yer işaretleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="getdefaultconnect"></a>CRecordset:: GetDefaultConnect

Varsayılan bağlantı dizesini almak için çağırılır.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan bağlantı dizesini içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Framework, kayıt kümesinin temel aldığı veri kaynağı için varsayılan bağlantı dizesini almak üzere bu üye işlevini çağırır. ClassWizard, tablolar ve sütunlar hakkında bilgi almak için classıntertıon sihirbazında kullandığınız veri kaynağını tanımlayarak sizin için bu işlevi uygular. Büyük olasılıkla uygulamanızı geliştirirken bu varsayılan bağlantıyı kullanmak için uygun olduğunu fark edersiniz. Ancak varsayılan bağlantı, uygulamanızın kullanıcıları için uygun olmayabilir. Bu durumda, ClassWizard 'ın sürümünü atarak bu işlevi yeniden uygulamalısınız. Bağlantı dizeleri hakkında daha fazla bilgi için bkz. [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).

##  <a name="getdefaultsql"></a>CRecordset:: GetDefaultSQL

Yürütülecek varsayılan SQL dizesini almak için çağırılır.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan SQL ifadesini içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Çerçeve, üzerinde kayıt kümesinin temel aldığı varsayılan SQL ifadesini almak için bu üye işlevini çağırır. Bu bir tablo adı veya bir SQL **Select** bildirisi olabilir.

Sınıf Sihirbazı ile kayıt kümesi sınıfınızı bildirerek varsayılan SQL ifadesini dolaylı olarak tanımlarsınız ve ClassWizard bu görevi sizin için gerçekleştirir.

Kendi kullanmanız için SQL deyimin dizesine ihtiyacınız varsa, bu kayıt kümesi açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL ifadesini döndüren `GetSQL`çağırın. Sınıfınızın `GetDefaultSQL`geçersiz kılındığı varsayılan SQL dizesini düzenleyebilirsiniz. Örneğin, **Call** ifadesini kullanarak önceden tanımlanmış bir sorgu için bir çağrı belirtebilirsiniz. (Ancak `GetDefaultSQL`düzenlediğinizde, veri kaynağındaki sütun sayısıyla eşleşmesi için `m_nFields` de değiştirmeniz gerektiğini unutmayın.)

Daha fazla bilgi için bkz. [kayıt kümesi: tablo Için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
>  Çerçeve bir tablo adı tanımlayamadı, birden fazla tablo adı sağlanırsa veya bir **çağrı** açıklaması yorumlanamadığından tablo adı boş olur. Bir **çağrı** açıklaması kullanırken, küme ayracı ile **Call** anahtar sözcüğü arasında boşluk eklememelisiniz, ya da küme ayracından önce ya da **Select** deyimindeki **Select** anahtar sözcüğünden önce boşluk eklemeniz gerektiğini unutmayın.

##  <a name="getfieldvalue"></a>CRecordset:: GetFieldValue

Geçerli kayıttaki alan verilerini alır.

```
void GetFieldValue(
    LPCTSTR lpszName,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CStringA& strValue);

void GetFieldValue(
    short nIndex,
    CStringW& strValue);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir alanın adı.

alan değerini depolayacak bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine başvuru.

*N,*<br/>
Alanın ODBC C veri türü. DEFAULT_FIELD_TYPE varsayılan değerini kullanarak, aşağıdaki tabloya bağlı olarak, SQL veri türü ' nden C veri türünü belirleme `GetFieldValue` zorlar. Aksi takdirde, veri türünü doğrudan belirtebilir veya uyumlu bir veri türü seçebilirsiniz; Örneğin, SQL_C_CHAR herhangi bir veri türünü saklayabilirsiniz.

|C veri türü|SQL veri türü|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

ODBC veri türleri hakkında daha fazla bilgi için Windows SDK ek D 'de "SQL veri türleri" ve "C veri türleri" konularına bakın.

*nDizin*<br/>
Alanın sıfır tabanlı dizini.

*strValue*<br/>
Alanın veri türünden bağımsız olarak, alana Dönüştürülecek alanın değerini depolayan bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Bir alanı ada veya dizine göre arayabilirsiniz. Alan değerini bir `CDBVariant` nesne veya bir `CString` nesnesi içinde saklayabilirsiniz.

Toplu satır getirme uyguladıysanız geçerli kayıt, her zaman bir satır kümesindeki ilk kayıtta konumlandırılır. Belirli bir satır kümesi içindeki bir kayıt üzerinde `GetFieldValue` kullanmak için, önce imleci bu satır kümesi içindeki istenen satıra taşımak için [SetRowsetCursorPosition](#setrowsetcursorposition) üye işlevini çağırmanız gerekir. Sonra bu satır için `GetFieldValue` çağırın. Toplu satır getirmeyi uygulamak için, [Açık](#open) üye Işlevindeki *dwoptions* parametresinin `CRecordset::useMultiRowFetch` seçeneğini belirtmeniz gerekir.

Çalışma zamanında alanları, tasarım zamanında statik olarak bağlamak yerine dinamik olarak getirmek için `GetFieldValue` kullanabilirsiniz. Örneğin, doğrudan `CRecordset`bir kayıt kümesi nesnesi bildirdiyseniz, alan verilerini almak için `GetFieldValue` kullanmanız gerekir; kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (toplu RFX) uygulanmadı.

> [!NOTE]
>  `CRecordset`türetmeden bir kayıt kümesi nesnesi bildirirseniz ODBC Imleç kitaplığı yüklü değildir. İmleç kitaplığı, kayıt kümesinin en az bir tane bağlantılı sütunu olmasını gerektirir; Ancak `CRecordset` doğrudan kullandığınızda, sütunlardan hiçbiri bağlanmadı. İmleç kitaplığının yüklenip yüklenmeyeceğini, [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) ve [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) işlevlerini üye olarak denetleyin.

`GetFieldValue` ODBC API işlevini `SQLGetData`çağırır. Sürücünüz alan değerinin gerçek uzunluğu için SQL_NO_TOTAL değerini çıktıysa, `GetFieldValue` bir özel durum oluşturur. `SQLGetData`hakkında daha fazla bilgi için bkz. Windows SDK.

### <a name="example"></a>Örnek

Aşağıdaki örnek kod, `CRecordset`doğrudan tanımlanmış bir kayıt kümesi nesnesi için `GetFieldValue` çağrılarını gösterir.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
>  `CDaoRecordset`DAO sınıfının aksine, `CRecordset` `SetFieldValue` üye işlevine sahip değildir. Doğrudan `CRecordset`bir nesne oluşturursanız, bu, etkin bir şekilde salt okunurdur.

Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getodbcfieldcount"></a>CRecordset:: GetODBCFieldCount

Kayıt kümesi nesnenizin Toplam alan sayısını alır.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki alan sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz: [kayıt kümeleri oluşturma ve kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getodbcfieldinfo"></a>CRecordset:: GetODBCFieldInfo

Kayıt kümesindeki alanlarla ilgili bilgileri alır.

```
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir alanın adı.

*sağlanırken*<br/>
`CODBCFieldInfo` yapısına yönelik bir başvuru.

*nDizin*<br/>
Alanın sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü bir alanı adına göre arama yapmanızı sağlar. Diğer sürüm, bir alanı dizine göre arama yapmanızı sağlar.

Döndürülen bilgiler hakkında bir açıklama için bkz. [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) yapısı.

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz: [kayıt kümeleri oluşturma ve kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getrecordcount"></a>CRecordset:: GetRecordCount

Kayıt kümesinin boyutunu belirler.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısı; kayıt kümesi kayıt içermiyorsa 0; ya da kayıt sayısı belirlenemiyorsa-1.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Kayıt sayısı bir "yüksek su işareti" olarak korunur, ancak Kullanıcı kayıtlarda ilerleyecek şekilde görülen en yüksek numaralı kayıt. Toplam kayıt sayısı yalnızca Kullanıcı son kaydın ötesine taşındıktan sonra bilinirdi. Performans nedenleriyle, `MoveLast`çağırdığınızda sayı güncellenmez. Kayıtları kendiniz saymak için, `IsEOF` sıfır dışında bir değer döndürene kadar `MoveNext` tekrar tekrar çağırın. `CRecordset:AddNew` ve `Update` aracılığıyla bir kayıt eklemek sayıyı artırır; `CRecordset::Delete` aracılığıyla bir kaydı silmek sayıyı azaltır.

##  <a name="getrowsetsize"></a>CRecordset:: GetRowsetSize

Belirli bir getirme sırasında almak istediğiniz satır sayısı için geçerli ayarı edinir.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirli bir getirme sırasında alınacak satır sayısı.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme kullanıyorsanız, kayıt kümesi açıldığında varsayılan satır kümesi boyutu 25 ' tir; Aksi takdirde, 1 ' dir.

Toplu satır getirmeyi uygulamak için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::useMultiRowFetch` seçeneğini belirtmeniz gerekir. Satır kümesi boyutu ayarını değiştirmek için [SetRowsetSize](#setrowsetsize)çağırın.

Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getrowsfetched"></a>CRecordset:: Getrowsgetirilen

Bir getirme işleminden sonra gerçekten kaç kayıt alındığını belirler.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirli bir getirme işleminden sonra veri kaynağından alınan satır sayısı.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uyguladığınızda bu faydalıdır. Satır kümesi boyutu normalde, bir getirmeye göre kaç satır alınacağını belirtir; Ancak, kayıt kümesindeki toplam satır sayısı, bir satır kümesinde kaç satır alınacağını da etkiler. Örneğin, kayıt kümeniz, satır kümesi boyutu ayarı 4 olan 10 kayda sahipse, `MoveNext` çağırarak kayıt kümesinden döngü, son satır kümesinin yalnızca 2 kayıt olmasına neden olur.

Toplu satır getirmeyi uygulamak için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::useMultiRowFetch` seçeneğini belirtmeniz gerekir. Satır kümesi boyutunu belirtmek için [SetRowsetSize](#setrowsetsize)çağırın.

Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

##  <a name="getrowstatus"></a>CRecordset:: GetRowStatus

Geçerli satır kümesindeki bir satırın durumunu alır.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer, 1 ' den satır kümesinin boyutuyla değişebilir.

### <a name="return-value"></a>Dönüş Değeri

Satır için bir durum değeri. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

`GetRowStatus`, veri kaynağından en son alındığı veya *wRow* 'a karşılık gelen bir satırın getirilmediği tarihten itibaren satıra yapılan herhangi bir değişikliği belirten bir değer döndürür. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Durum değeri|Açıklama|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Satır değiştirilmez.|
|SQL_ROW_UPDATED|Satır güncelleştirildi.|
|SQL_ROW_DELETED|Satır silindi.|
|SQL_ROW_ADDED|Satır eklendi.|
|SQL_ROW_ERROR|Satır bir hata nedeniyle geri alınamıyor.|
|SQL_ROW_NOROW|*WRow*'a karşılık gelen satır yok.|

Daha fazla bilgi için Windows SDK `SQLExtendedFetch` ODBC API işlevine bakın.

##  <a name="getstatus"></a>CRecordset:: GetStatus

Kayıt kümesindeki geçerli kaydın dizinini ve son kaydın görülip görülmediğini belirler.

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Parametreler

*rStatus*<br/>
`CRecordsetStatus` nesnesine bir başvuru. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`CRecordset` dizini izlemeye çalışır, ancak bazı durumlarda bu mümkün olmayabilir. Bir açıklama için bkz. [GetRecordCount](#getrecordcount) .

`CRecordsetStatus` yapısı aşağıdaki biçimdedir:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

`CRecordsetStatus` iki üyesi aşağıdaki anlamlara sahiptir:

- `m_lCurrentRecord`, bilinen kayıt kümesindeki geçerli kaydın sıfır tabanlı dizinini Içerir. Dizin saptanamıyor, bu üye AFX_CURRENT_RECORD_UNDEFINED (-2) içerir. `IsBOF` TRUE ise (boş kayıt kümesi veya ilk kayıttan önce kaydırmaya çalışırsanız), `m_lCurrentRecord` AFX_CURRENT_RECORD_BOF (-1) olarak ayarlanır. İlk kayıtta, 0, ikinci kayıt 1, vb. olarak ayarlanır.

- kayıt kümesindeki toplam kayıt sayısı belirleniyorsa sıfır dışında `m_bRecordCountFinal`. Genellikle bu, kayıt kümesinin başlangıcında başlayıp `IsEOF` sıfır dışında bir değer döndürülünceye kadar `MoveNext` yapılmalıdır. Bu üye sıfırsa, `GetRecordCount`tarafından döndürülen kayıt sayısı, yalnızca bir "yüksek su işareti" sayısı olarak ayarlanır.

##  <a name="getsql"></a>CRecordset:: GetSQL

Açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL ifadesini almak için bu üye işlevi çağırın.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

SQL ifadesini içeren `CString` bir **const** başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle bir SQL **Select** deyimidir. `GetSQL` tarafından döndürülen dize salt okunurdur.

`GetSQL` tarafından döndürülen dize, genel olarak, *lpszSQL* parametresindeki kayıt kümesine `Open` üye işlevine geçirilebileceğiniz herhangi bir dizeden farklıdır. Bunun nedeni, kayıt kümesinin `Open`ne geçirdiklerinizi, ClassWizard ile belirtdiklerinizi, `m_strFilter` ve `m_strSort` veri üyelerini ve belirttiğiniz tüm parametreleri temel alan tam bir SQL ifadesini oluşturduğundan. Kayıt kümesinin bu SQL ifadesini oluşturma hakkında ayrıntılı bilgi için kayıt [kümesi: kayıt kümeleri kayıtları seçme (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

> [!NOTE]
>  Bu üye işlevini yalnızca [Open](#open)çağrıldıktan sonra çağırın.

##  <a name="gettablename"></a>CRecordset:: GetTableName

Kayıt kümesi sorgusunun temel aldığı SQL tablosunun adını alır.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi bir tabloyu temel alıyorsa tablo adını içeren `CString` bir **const** başvurusu; Aksi takdirde, boş bir dize.

### <a name="remarks"></a>Açıklamalar

`GetTableName` yalnızca kayıt kümesi, birden fazla tablonun veya önceden tanımlanmış bir sorgunun (saklı yordam) JOIN değil bir tabloyu temel alıyorsa geçerlidir. Ad salt okunurdur.

> [!NOTE]
>  Bu üye işlevini yalnızca [Open](#open)çağrıldıktan sonra çağırın.

##  <a name="isbof"></a>CRecordset:: IsBOF

Kayıt kümesi ilk kayıttan önce konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermiyorsa veya ilk kayıttan önce geriye doğru kaydırdıysanız sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin ilk kaydından önce ilerlemeyeceğinizi öğrenmek için kayıttan kayda geçmeden önce Bu üye işlevini çağırın. Kayıt kümesinin herhangi bir kayıt içerip içermediğini veya boş olduğunu anlamak için `IsEOF` ile birlikte `IsBOF` de kullanabilirsiniz. `Open`çağırdıktan hemen sonra, kayıt kümesi hiçbir kayıt içermiyorsa, `IsBOF` sıfır dışında bir değer döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, ilk kayıt geçerli kayıttır ve `IsBOF` 0 döndürür.

İlk kayıt geçerli kayıttır ve `MovePrev`çağırırsanız, `IsBOF` daha sonra sıfır dışında bir değer döndürür. `IsBOF` sıfır dışında bir değer döndürürse ve `MovePrev`çağırırsanız bir hata oluşur. `IsBOF` sıfır dışında bir değer döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem hataya neden olur.

### <a name="example"></a>Örnek

Bu örnek, kod kayıt kümesini her iki yönde de kaydığından, bir kayıt kümesinin sınırlarını algılamak için `IsBOF` ve `IsEOF` kullanır.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

##  <a name="isdeleted"></a>CRecordset:: IsDeleted

Geçerli kaydın silinip silinmediğini belirler.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayıtta konumlandırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kayırsanız ve `IsDeleted` TRUE (sıfır dışında) döndürürse, başka bir kayıt kümesi işlemini gerçekleştirebilmek için önce başka bir kayda kaydırmanız gerekir.

`IsDeleted` sonucu, kayıt kümeniz, kayıt kümenizin güncelleştirilebilir olup olmadığı, kayıt kümesini açarken `CRecordset::skipDeletedRecords` seçeneğini belirtdiğinize bakılmaksızın, Sürücü paketlerinizin kayıtları sildiği ve birden çok kullanıcı olup olmadığı gibi birçok etkene bağlıdır.

`CRecordset::skipDeletedRecords` ve sürücü paketleme hakkında daha fazla bilgi için, [Açık](#open) üye işlevine bakın.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `IsDeleted`çağırmamalıdır. Bunun yerine [GetRowStatus](#getrowstatus) member işlevini çağırın. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="iseof"></a>CRecordset:: IsEOF

Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi hiçbir kayıt içermiyorsa veya son kaydın ötesine kaydırdıysanız sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin son kaydını aşıp geçmeyeceğinizi öğrenmek için kayıttan kayda gittiğinden bu üye işlevi çağırın. Kayıt kümesinin herhangi bir kayıt içerip içermediğini veya boş olduğunu anlamak için `IsEOF` de kullanabilirsiniz. `Open`çağırdıktan hemen sonra, kayıt kümesi hiçbir kayıt içermiyorsa, `IsEOF` sıfır dışında bir değer döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, ilk kayıt geçerli kayıttır ve `IsEOF` 0 döndürür.

`MoveNext`çağırdığınızda son kayıt geçerli kayıt ise, `IsEOF` daha sonra sıfır dışında bir değer döndürür. `IsEOF` sıfır dışında bir değer döndürürse ve `MoveNext`çağırırsanız bir hata oluşur. `IsEOF` sıfır dışında bir değer döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem hataya neden olur.

### <a name="example"></a>Örnek

[IsBOF](#isbof)örneğine bakın.

##  <a name="isfielddirty"></a>CRecordset:: IsFieldDirty

[Düzenleme](#edit) veya [AddNew](#addnew) çağrıldıktan sonra belirtilen alan veri üyesinin değiştirilip değiştirilmediğini belirler.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin kirli olup olmadığını belirleme NULL.

### <a name="return-value"></a>Dönüş Değeri

`AddNew` veya `Edit`çağrıldıktan sonra belirtilen alan veri üyesi değiştiyse sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli kayıt, `CRecordset` [Update](#update) üye işlevine yapılan bir çağrı (`Edit` veya `AddNew`çağrısı sonrasında) ile güncelleştirildiği zaman, tüm kirli alan verileri üyelerinde veri kaynağındaki kayda aktarılır.

> [!NOTE]
>  Bu üye işlevi, toplu satır getirme kullanan kayıt kümelerinde uygulanabilir değildir. Toplu satır getirmeyi uyguladıysanız `IsFieldDirty` her zaman FALSE döndürür ve başarısız bir onaylama işlemine neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldDirty` çağrısı, alanın kirli durumu yeniden değerlendirildiğinden, önceki çağrıların etkilerini [SetFieldDirty](#setfielddirty) olarak sıfırlayacaktır. `AddNew` durumda, geçerli alan değeri sözde null değerinden farklıysa, alan durumu kirli olarak ayarlanır. `Edit` durumda, alan değeri önbelleğe alınan değerden farklıysa, alan durumu kirli olarak ayarlanır.

`IsFieldDirty`, [DoFieldExchange](#dofieldexchange)aracılığıyla uygulanır.

Kirli bayrağı hakkında daha fazla bilgi için [kayıt kümesi: kayıt kümeleri kayıtları seçme (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

##  <a name="isfieldnull"></a>CRecordset:: IsFieldNull

Geçerli kayıttaki belirtilen alan null ise (değer yoksa) sıfır dışında bir değer döndürür.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin null olup olmadığını belirleme NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan verisi üyesi null olarak işaretlense sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesinin belirtilen alan verisi üyesinin null olarak işaretlenip işaretlenmediğini öğrenmek için bu üye işlevini çağırın. (Veritabanı terimlerinde null "değer yok" anlamına gelir ve içinde C++null ile aynı değildir.) Bir alan veri üyesine null olarak bayrak eklenmiş ise, geçerli kaydın değeri olmayan bir sütun olarak yorumlanır.

> [!NOTE]
>  Bu üye işlevi, toplu satır getirme kullanan kayıt kümelerinde uygulanabilir değildir. Toplu satır getirmeyi uyguladıysanız `IsFieldNull` her zaman FALSE döndürür ve başarısız bir onaylama işlemine neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull`, [DoFieldExchange](#dofieldexchange)aracılığıyla uygulanır.

##  <a name="isfieldnullable"></a>CRecordset:: Isfieldnullenebilir

Geçerli kayıttaki belirtilen alan null (değer olmadan) olarak ayarlandıysa sıfır dışında bir değer döndürür.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin null değere ayarlanmadığını belirleme NULL.

### <a name="remarks"></a>Açıklamalar

Belirtilen alan verisi üyesinin "Nullable" olup olmadığını ve null değere ayarlanamayacağını öğrenmek için bu üye işlevi çağırın; C++ Null, Veritabanı terminolojisinde "hiçbir değer yok" anlamına gelen null ile aynı değildir.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `IsFieldNullable`çağıramaz. Bunun yerine, bir alanın null değere ayarlanamayacağını öğrenmek için [GetODBCFieldInfo](#getodbcfieldinfo) üye işlevini çağırın. Toplu satır getirme uygulanıp uygulanmadığı bağımsız olarak `GetODBCFieldInfo`her zaman çağırabileceğinizi unutmayın. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Null olmayan bir alan bir değere sahip olmalıdır. Bir kaydı eklerken veya güncelleştirirken bu tür bir alanı null olarak ayarlamaya çalışırsanız, veri kaynağı ekleme veya güncelleştirmeyi reddeder ve [güncelleştirme](#update) bir özel durum oluşturur. Özel durum, [SetFieldNull](#setfieldnull)' ı çağırdığınızda değil `Update`çağırdığınızda oluşur.

İşlevin ilk bağımsız değişkeni için NULL kullanmak, işlevi `param` alanlara değil yalnızca `outputColumn` alanlara uygular. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanlarını NULL olarak ayarlar; `param` alanlar etkilenmeyecektir.

`param` alanlarla çalışmak için, üzerinde çalışmak istediğiniz bireysel `param` gerçek adresini sağlamanız gerekir, örneğin:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, `outputColumn` alanları ile yaptığınız gibi tüm `param` alanlarını NULL olarak ayarlayamayacağı anlamına gelir.

`IsFieldNullable`, [DoFieldExchange](#dofieldexchange)aracılığıyla uygulanır.

##  <a name="isopen"></a>CRecordset:: IsOpen

Kayıt kümesinin zaten açık olup olmadığını belirler.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi nesnesinin [Open](#open) veya [Requery](#requery) üye işlevi daha önce çağrılırsa ve kayıt kümesi kapanmamış ise sıfır dışı. Aksi takdirde 0.

##  <a name="m_hstmt"></a>CRecordset:: m_hstmt

Kayıt kümesiyle ilişkili olan HSTMT türündeki ODBC deyim veri yapısına yönelik bir tanıtıcı içerir.

### <a name="remarks"></a>Açıklamalar

ODBC veri kaynağına yapılan her sorgu, HSTMT ile ilişkilendirilir.

> [!CAUTION]
>  [Open](#open) çağrılmadan önce `m_hstmt` kullanmayın.

Normalde HSTMT 'ye doğrudan erişmeniz gerekmez, ancak SQL deyimlerinin doğrudan yürütülmesi için buna ihtiyacınız olabilir. `CDatabase` sınıfının `ExecuteSQL` üye işlevi `m_hstmt`kullanma örneği sağlar.

##  <a name="m_nfields"></a>CRecordset:: m_nFields

Kayıt kümesi sınıfındaki alan veri üyelerinin sayısını içerir; diğer bir deyişle, veri kaynağından kayıt kümesi tarafından seçilen sütun sayısıdır.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfının Oluşturucusu doğru sayıda `m_nFields` başlatmalıdır. Toplu satır getirmeyi uygulamadıysanız, ClassWizard, kayıt kümesi sınıfınızı bildirmek için kullandığınızda bu başlatmayı sizin için yazar. Ayrıca, el ile de yazabilirsiniz.

Framework, alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasındaki etkileşimi yönetmek için bu numarayı kullanır.

> [!CAUTION]
>  Bu sayı, `DoFieldExchange` kayıtlı olan "çıkış sütunları" sayısına veya `CFieldExchange::outputColumn`parametresiyle [SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısından sonra `DoBulkFieldExchange` karşılık gelmelidir.

"Kayıt kümesi: dinamik olarak veri sütunlarını bağlama" makalesinde açıklandığı gibi sütunları dinamik olarak bağlayabilirsiniz. Bunu yaparsanız, dinamik olarak bağlı sütunlar için `DoFieldExchange` veya `DoBulkFieldExchange` üye işlevinizdeki RFX veya toplu RFX işlev çağrılarının sayısını yansıtmak üzere `m_nFields` sayısını artırmanız gerekir.

Daha fazla bilgi için bkz. Makaleler [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) ve [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

[Kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md)makalesine bakın.

##  <a name="m_nparams"></a>CRecordset:: m_nParams

Kayıt kümesi sınıfındaki parametre veri üyelerinin sayısını içerir; diğer bir deyişle, kayıt kümesinin sorgusuyla geçilen parametre sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızın herhangi bir parametre veri üyesi varsa, sınıfın oluşturucusunun doğru sayıyla `m_nParams` başlatması gerekir. `m_nParams` değeri varsayılan olarak 0 ' dır. Parametre veri üyelerini (el ile yapmanız gereken) eklerseniz, parametre sayısını yansıtmak için sınıf oluşturucusunda bir başlatma da eklemeniz gerekir (en azından, `m_strFilter` veya `m_strSort` dizesindeki ' ' yer tutucuları sayısı kadar büyük olması gerekir).

Çerçeve, kayıt kümesinin sorgusunu parametrelendirtiğinde bu numarayı kullanır.

> [!CAUTION]
>  Bu sayı, `DoFieldExchange` kayıtlı olan "params" sayısına veya `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`veya `CFieldExchange::inoutParam`parametre değeriyle [SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısından sonra `DoBulkFieldExchange` karşılık gelmelidir.

### <a name="example"></a>Örnek

  Bkz. Makaleler [kayıt kümesi: bir kayıt kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) ve [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_pdatabase"></a>CRecordset:: m_pDatabase

Kayıt kümesinin bir veri kaynağına bağlı olduğu `CDatabase` nesnesine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu değişken iki şekilde ayarlanır. Genellikle, kayıt kümesi nesnesini oluştururken zaten bağlı olan `CDatabase` nesnesine bir işaretçi geçirirsiniz. Bunun yerine NULL geçirirseniz `CRecordset`, sizin için bir `CDatabase` nesnesi oluşturur ve bunu bağlar. Her iki durumda da, `CRecordset` işaretçiyi Bu değişkende depolar.

Normalde, `m_pDatabase`' de depolanan işaretçiyi doğrudan kullanmanız gerekmez. `CRecordset`için kendi uzantılarınızı yazarsanız, işaretçiyi kullanmanız gerekebilir. Örneğin, kendi `CDBException`s oluşturduysanız işaretçiye ihtiyacınız vardır. Ya da işlem çalıştırma, zaman aşımlarını ayarlama ya da SQL deyimlerini doğrudan yürütmek için `CDatabase` sınıfının `ExecuteSQL` member işlevini çağırma gibi aynı `CDatabase` nesnesini kullanarak bir şey yapmanız gerekiyorsa, buna ihtiyacınız olabilir.

##  <a name="m_strfilter"></a>CRecordset:: m_strFilter

Kayıt kümesi nesnesini oluşturduktan sonra, ancak `Open` üye işlevini çağırmadan önce, bir SQL **WHERE** yan tümcesi içeren bir `CString` depolamak için bu veri üyesini kullanın.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi, `Open` veya `Requery` çağrısı sırasında seçtiği kayıtları kısıtlamak (veya filtrelemek) için bu dizeyi kullanır. Bu, bir kayıt alt kümesini seçmek için yararlıdır, örneğin "California 'yı temel alarak tüm saleskişileriniz" ("State = CA"). **WHERE** yan TÜMCESI IÇIN ODBC SQL söz dizimi

`WHERE search-condition`

Dizeniz **WHERE** anahtar sözcüğünü eklemeyin. Framework bunu sağlar.

Ayrıca, içinde ' ' yer tutucuları yerleştirerek, her yer tutucu için sınıfınıza bir parametre veri üyesi bildirerek ve çalışma zamanında parametreleri kayıt kümesine geçirerek filtre dizenizi parametreleştirebilirsiniz. Bu, çalışma zamanında filtreyi oluşturmanıza olanak sağlar. Daha fazla bilgi için bkz. kayıt kümesi [: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

SQL **WHERE** yan tümceleri hakkında daha fazla bilgi için [SQL](../../data/odbc/sql.md)makalesine bakın. Kayıtları seçme ve filtreleme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

##  <a name="m_strsort"></a>CRecordset:: m_strSort

Kayıt kümesi nesnesini oluşturduktan sonra, ancak `Open` üye işlevini çağırmadan önce, SQL **order by** yan tümcesini içeren bir `CString` depolamak için bu veri üyesini kullanın.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi bu dizeyi, `Open` veya `Requery` çağrısı sırasında seçtiği kayıtları sıralamak için kullanır. Bu özelliği, bir veya daha fazla sütunda bir kayıt kümesini sıralamak için kullanabilirsiniz. **Order by** yan TÜMCESININ ODBC SQL söz dizimi

`ORDER BY sort-specification [, sort-specification]...`

sıralama belirtiminin tamsayı veya sütun adı olduğu yerdir. Ayrıca sıralama dizesindeki sütun listesine "ASC" veya "DESC" ekleyerek artan veya azalan sıra (varsayılan olarak sıralama) belirtebilirsiniz. Seçilen kayıtlar önce listelenen ilk sütundan, sonra ikincisine göre sıralanır ve bu şekilde devam eder. Örneğin, bir "Customers" kayıt kümesini soyadı, sonra adı olarak sipariş edebilirsiniz. Listeleyebilir sütun sayısı veri kaynağına bağlıdır. Daha fazla bilgi için Windows SDK bakın.

Dizeniz **Için order by** anahtar sözcüğünü dahil mayacağınızı unutmayın. Framework bunu sağlar.

SQL yan tümceleri hakkında daha fazla bilgi için [SQL](../../data/odbc/sql.md)makalesine bakın. Kayıtları sıralama hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

##  <a name="move"></a>CRecordset:: Move

Kayıt kümesi içindeki geçerli kayıt işaretçisini ileri veya geri kaydırır.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Parametreler

*nsatırlar*<br/>
İleri veya geri taşınacak satır sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru ileri doğru taşınır. Negatif değerler geriye doğru, başlangıca taşınır.

*wFetchType*<br/>
`Move` getirecek satır kümesini belirler. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

*Nrows*için 0 değerini geçirirseniz, `Move` geçerli kaydı yeniler; `Move` geçerli `AddNew` veya `Edit` modundan sona acaktır ve `AddNew` veya `Edit` çağrılmadan önce geçerli kaydın değerini geri yükler.

> [!NOTE]
>  Bir kayıt kümesi içinde geçiş yaptığınızda, silinen kayıtları atlayamazsınız. Daha fazla bilgi için bkz. [CRecordset:: IsDeleted](#isdeleted) . `skipDeletedRecords` seçenek kümesi ile bir `CRecordset` açtığınızda, *nrows* parametresinin 0 olması durumunda `Move` onaylar. Bu davranış, aynı verileri kullanan diğer istemci uygulamaları tarafından silinen satırların yenilenmesini önler. `skipDeletedRecords`açıklaması için bkz. *dwOption* parametresi [Açık](#open) .

`Move` kayıt kümelerini satır kümelerine göre konumlandırır. *Nrows* ve *wFetchType*değerlerini temel alarak, `Move` uygun satır kümesini getirir ve sonra o satır kümesindeki ilk kaydı geçerli kayıt yapar. Toplu satır getirmeyi gerçekleştirdiyseniz, satır kümesi boyutu her zaman 1 ' dir. Bir satır kümesi getirilirken, `Move` doğrudan [CheckRowsetError](#checkrowseterror) üye işlevini çağırarak, getirme işleminden kaynaklanan hataları işler.

Geçirdiğiniz değerlere bağlı olarak, `Move` diğer `CRecordset` üye işlevlerine eşdeğerdir. Özellikle, *wFetchType* değeri, geçerli kaydın taşınması için daha sezgisel ve genellikle tercih edilen yöntem olan bir üye işlevi gösterebilir.

Aşağıdaki *tabloda wFetchType için olası*değerler, `Move` *wFetchType* ve *nrows*temel alınarak getirileceği satır kümesi ve *wFetchType*öğesine karşılık gelen eşdeğer üye işlevleri listelenmektedir.

|wFetchType|Getirilen satır kümesi|Denk üye işlevi|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (varsayılan değer)|Geçerli satır kümesindeki ilk satırdan *nrows* satırlarını Başlatan satır kümesi.||
|SQL_FETCH_NEXT|Sonraki satır kümesi; *nsatırlar* yoksayıldı.|[Iken](#movenext)|
|SQL_FETCH_PRIOR|Önceki satır kümesi; *nsatırlar* yoksayıldı.|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|Kayıt kümesindeki ilk satır kümesi; *nsatırlar* yoksayıldı.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Kayıt kümesindeki son tamamlanma satır kümesi; *nsatırlar* yoksayıldı.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|*Nrows* > 0 ise, satır kümesi, kayıt kümesinin başından *nrows* satırlarını Başlatan satır kümesidir. *Nrows* < 0 ise satır kümesi, kayıt kümesinin sonundan *nrows* satırlarını başlatıyor. Eğer *nrows* = 0 ise, bir dosya BAŞLANGıCı (BOF) koşulu döndürülür.|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Yer işareti değeri *nrows*'a karşılık gelen satırda başlayan satır kümesi.|[SetBookmark](#setbookmark)|

> [!NOTE]
>  Yalnızca ileri kayıt kümeleri için `Move` yalnızca *wFetchType*için SQL_FETCH_NEXT değeriyle geçerlidir.

> [!CAUTION]
>  `Move` çağrısı, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinde herhangi bir kayıt olup olmadığını belirleme, [IsBOF](#isbof) ve [IOF](#iseof)'yi çağırın.

> [!NOTE]
>  Kayıt kümesinin başlangıcını veya sonunu (`IsBOF` veya `IsEOF` sıfır dışında bir değer döndürür) daha önce kaydırdıysanız, bir `Move` işlevi çağırmak muhtemelen bir `CDBException`oluşturur. Örneğin, `IsEOF` sıfır dışında bir değer döndürürse ve `IsBOF`, `MoveNext` bir özel durum oluşturur, ancak `MovePrev` olmaz.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` çağırırsanız güncelleştirmeler uyarı vermeden kaybedilir.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). İlgili bilgiler için Windows SDK `SQLExtendedFetch` ODBC API işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

##  <a name="movefirst"></a>CRecordset:: MoveFirst

İlk satır kümesindeki ilk kaydı geçerli kayıt yapar.

```
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır yakalamanın uygulanıp uygulanmadığı bağımsız olarak, bu her zaman kayıt kümesindeki ilk kayıt olacaktır.

Kayıt kümesini açtıktan hemen sonra `MoveFirst` çağırmanız gerekmez. Bu sırada, ilk kayıt (varsa) otomatik olarak geçerli kayıt olur.

> [!NOTE]
>  Bu üye işlevi yalnızca iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi içinde geçiş yaptığınızda, silinen kayıtları atlayamazsınız. Ayrıntılar için [IsDeleted](#isdeleted) üye işlevine bakın.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinin herhangi bir kayıt içerip içermediğini anlamak için, `IsBOF` ve `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

##  <a name="movelast"></a>CRecordset:: MoveLast

Son tamamlanan ilk kayıt satır kümesinden geçerli kaydı yapar.

```
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirmeyi gerçekleştirdiyseniz, kayıt kümeniz 1 satır kümesi boyutuna sahiptir, bu nedenle `MoveLast` yalnızca kayıt kümesindeki son kayda gider.

> [!NOTE]
>  Bu üye işlevi yalnızca iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi içinde geçiş yaptığınızda, silinen kayıtları atlayamazsınız. Ayrıntılar için [IsDeleted](#isdeleted) üye işlevine bakın.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinin herhangi bir kayıt içerip içermediğini anlamak için, `IsBOF` ve `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

##  <a name="movenext"></a>CRecordset:: MoveNext

Sonraki satır kümesindeki ilk kaydı geçerli kayıt yapar.

```
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirmeyi gerçekleştirdiyseniz, kayıt kümeniz 1 satır kümesi boyutuna sahiptir, bu nedenle `MoveNext` yalnızca bir sonraki kayda gider.

> [!NOTE]
>  Bir kayıt kümesi içinde geçiş yaptığınızda, silinen kayıtları atlayamazsınız. Ayrıntılar için [IsDeleted](#isdeleted) üye işlevine bakın.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinin herhangi bir kayıt içerip içermediğini anlamak için, `IsBOF` ve `IsEOF`çağırın.

> [!NOTE]
>  Ayrıca, `MoveNext`çağrılmadan önce `IsEOF` çağırmanız önerilir. Örneğin, kayıt kümesinin sonunu daha önce kaydırdıysanız `IsEOF` sıfır dışında döndürür; `MoveNext` sonraki bir çağrı özel durum oluşturur.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

##  <a name="moveprev"></a>CRecordset:: Moveöncekini

Önceki satır kümesindeki ilk kaydı geçerli kayıt yapar.

```
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirmeyi gerçekleştirdiyseniz, kayıt kümeniz 1 satır kümesi boyutuna sahiptir, bu nedenle `MovePrev` yalnızca önceki kayda gider.

> [!NOTE]
>  Bu üye işlevi yalnızca iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi içinde geçiş yaptığınızda, silinen kayıtları atlayamazsınız. Ayrıntılar için [IsDeleted](#isdeleted) üye işlevine bakın.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Kayıt kümesinin herhangi bir kayıt içerip içermediğini anlamak için, `IsBOF` ve `IsEOF`çağırın.

> [!NOTE]
>  Ayrıca, `MovePrev`çağrılmadan önce `IsBOF` çağırmanız önerilir. Örneğin, kayıt kümesinin başından önce kaydırdıysanız `IsBOF` sıfır dışında döndürür; `MovePrev` sonraki bir çağrı özel durum oluşturur.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

##  <a name="onsetoptions"></a>CRecordset:: OnSetOptions

Belirtilen ODBC ifadesinin seçeneklerini (seçimde kullanılan) ayarlamak için çağırılır.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Seçenekleri ayarlanacak ODBC ifadesinin HSTMT 'ı.

### <a name="remarks"></a>Açıklamalar

Belirtilen ODBC ifadesinin seçeneklerini (seçimde kullanılan) ayarlamak için `OnSetOptions` çağırın. Çerçeve, kayıt kümesine yönelik başlangıç seçeneklerini ayarlamak için bu üye işlevini çağırır. `OnSetOptions`, veri kaynağının kaydırılabilir imleçler ve imleç Eşzamanlılık için desteğini belirler ve kayıt kümesinin seçeneklerini uygun şekilde ayarlar. (`OnSetOptions` seçim işlemleri için `OnSetUpdateOptions`, güncelleştirme işlemleri için kullanılır.)

Sürücüye veya veri kaynağına özgü seçenekleri ayarlamak için `OnSetOptions` geçersiz kılın. Örneğin, veri kaynağınız özel erişim için açmayı destekliyorsa, bu özelliklerden yararlanmak için `OnSetOptions` geçersiz kılabilirsiniz.

İmleçler hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="onsetupdateoptions"></a>CRecordset:: OnSetUpdateOptions

Belirtilen ODBC ifadesinin seçeneklerini (güncelleştirmede kullanılır) ayarlamak için çağırılır.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*bağlayıcıları*<br/>
Seçenekleri ayarlanacak ODBC ifadesinin HSTMT 'ı.

### <a name="remarks"></a>Açıklamalar

Belirtilen ODBC ifadesinin seçeneklerini (güncelleştirmede kullanılan) ayarlamak için `OnSetUpdateOptions` çağırın. Framework bir kayıt kümesindeki kayıtları güncelleştirmek için bir HSTMT oluşturduktan sonra bu üye işlevini çağırır. (`OnSetOptions` seçim işlemleri için `OnSetUpdateOptions`, güncelleştirme işlemleri için kullanılır.) `OnSetUpdateOptions`, veri kaynağının kaydırılabilir imleçler ve imleç Eşzamanlılık için desteğini belirler ve kayıt kümesinin seçeneklerini uygun şekilde ayarlar.

Bir veritabanına erişmek için bu deyimin kullanılmadan önce ODBC bildiriminin seçeneklerini ayarlamak için `OnSetUpdateOptions` geçersiz kılın.

İmleçler hakkında daha fazla bilgi için bkz. [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="open"></a>CRecordset:: Open

Tabloyu alarak veya kayıt kümesinin temsil ettiği sorguyu gerçekleştirerek kayıt kümesini açar.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Parametreler

*nOpenType*<br/>
Varsayılan değeri kabul edin, AFX_DB_USE_DEFAULT_TYPE veya `enum OpenType`aşağıdaki değerlerden birini kullanın:

- iki yönlü kaydırma içeren bir kayıt kümesi `CRecordset::dynaset`. Kayıtların üyeliği ve sıralaması, kayıt kümesi açıldığında belirlenir, ancak diğer kullanıcılar tarafından veri değerlerine yapılan değişiklikler bir getirme işleminden sonra görünür olur. Dinamik kümeler, anahtar kümesi temelli kayıt kümeleri olarak da bilinir.

- iki yönlü kaydırma ile statik bir kayıt kümesi `CRecordset::snapshot`. Kayıtların üyeliği ve sıralaması, kayıt kümesi açıldığında belirlenir; veri değerleri, kayıtlar getirilirken belirlenir. Diğer kullanıcılar tarafından yapılan değişiklikler, kayıt kümesi kapatılana ve sonra yeniden açılıncaya kadar görünmez.

- iki yönlü kaydırma içeren bir kayıt kümesi `CRecordset::dynamic`. Diğer kullanıcılar tarafından üyelik, sıralama ve veri değerlerine yapılan değişiklikler, getirme işleminden sonra görülebilir. Birçok ODBC sürücüsünün bu tür bir kayıt kümesini desteklemediğini unutmayın.

- yalnızca ileri kaydırma içeren salt okunurdur bir kayıt kümesi `CRecordset::forwardOnly`.

   `CRecordset`için varsayılan değer `CRecordset::snapshot`. Varsayılan değer mekanizması, Visual C++ sihirbazları 'nın, farklı varsayılan değerlere sahıp hem ODBC `CRecordset` hem de DAO `CDaoRecordset`etkileşime geçmesini sağlar.

Bu kayıt kümesi türleri hakkında daha fazla bilgi için bkz. [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). İlgili bilgiler için, Windows SDK "blok ve kaydırılabilir Imleçler kullanma" makalesine bakın.

> [!CAUTION]
>  İstenen tür desteklenmiyorsa Framework bir özel durum oluşturur.

*lpszSQL*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- NULL işaretçi.

- Bir tablonun adı.

- Bir SQL **Select** deyimi (isteğe bağlı olarak bir SQL **WHERE** veya **order by** yan tümcesi ile).

- Önceden tanımlanmış bir sorgunun (saklı yordam) adını belirten bir **çağrı** bildirisi. Küme ayracı ve **Call** anahtar sözcüğü arasına boşluk eklememeye dikkat edin.

Bu dize hakkında daha fazla bilgi için, [açıklamalar](#remarks) bölümü altındaki ClassWizard 'ın rolünün tablosuna ve başlığına bakın.

> [!NOTE]
>  Sonuç kümesindeki sütunların sırası, [DoFieldExchange](#dofieldexchange) veya [DoBulkFieldExchange](#dobulkfieldexchange) IşLEVI geçersiz kılmanızda RFX veya toplu RFX işlev çağrılarının sırasıyla eşleşmelidir.

*dwOptions*<br/>
Aşağıda listelenen değerlerin birleşimini belirtebileceğiniz bir bit maskesi. Bunlardan bazıları birbirini dışlıyor. Varsayılan değer **none**' dır.

- `CRecordset::none` seçenek ayarlanmadı. Bu parametre değeri, diğer tüm değerlerle birbirini dışlıyor. Varsayılan olarak, kayıt kümesi [düzenleme](#edit) veya [silme](#delete) ile güncelleştirilebilen ve [AddNew](#addnew)ile yeni kayıtlar eklemeye izin verebilir. Updatability, veri kaynağına ve belirttiğiniz *nOpenType* seçeneğine bağlıdır. Toplu eklemeler için iyileştirme kullanılamıyor. Toplu satır getirme uygulanmayacak. Silinen kayıtlar, kayıt kümesi gezintisi sırasında atlanmaz. Yer işaretleri kullanılamıyor. Otomatik kirli alan denetimi uygulandı.

- `CRecordset::appendOnly`, kayıt kümesinde `Edit` veya `Delete` izin vermez. Yalnızca `AddNew` izin ver. Bu seçenek `CRecordset::readOnly`birlikte birbirini dışlar.

- `CRecordset::readOnly` kayıt kümesini salt okuma olarak açın. Bu seçenek `CRecordset::appendOnly`birlikte birbirini dışlar.

- tek seferde çok sayıda kayıt eklemeyi iyileştirmek için hazırlanmış bir SQL ifadesini kullanmak `CRecordset::optimizeBulkAdd`. Kayıt kümesini güncelleştirmek için `SQLSetPos` ODBC API işlevini kullanmıyorsanız geçerlidir. İlk güncelleştirme hangi alanların kirli olarak işaretlendiğini belirler. Bu seçenek `CRecordset::useMultiRowFetch`birlikte birbirini dışlar.

- tek bir getirme işleminde birden çok satırın alınmasına izin vermek için toplu satır getirmeyi uygulayın `CRecordset::useMultiRowFetch`. Bu, performansı artırmak için tasarlanan gelişmiş bir özelliktir; ancak toplu kayıt alanı değişimi, ClassWizard tarafından desteklenmez. Bu seçenek `CRecordset::optimizeBulkAdd`birlikte birbirini dışlar. `CRecordset::useMultiRowFetch`belirtirseniz `CRecordset::noDirtyFieldCheck` seçeneğinin otomatik olarak açılıp açılmadığını unutmayın (çift arabelleğe alma kullanılamaz); yalnızca iletme kayıt kümelerinde `CRecordset::useExtendedFetch` seçeneği otomatik olarak açılır. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords`, kayıt kümesinden gezinirken silinen tüm kayıtları atlayın. Bu, belirli göreli getirmeler için performansı yavaşlatır. Bu seçenek yalnızca iletme kayıt kümelerinde geçerli değildir. [Move](#move) for *nrows* parametresi 0 olarak ayarlandıysa ve `CRecordset::skipDeletedRecords` seçenek ayarlandıysa, `Move` onay olur. `CRecordset::skipDeletedRecords`, *sürücü paketleme*ile benzerdir, yani silinen satırlar kayıt kümesinden kaldırılır. Ancak, Sürücü paketlerinizin kaydı varsa, yalnızca sildiğiniz kayıtları atlar; kayıt kümesi açıkken, diğer kullanıcılar tarafından silinen kayıtları atlamaz. `CRecordset::skipDeletedRecords`, diğer kullanıcılar tarafından silinen satırları atlar.

- `CRecordset::useBookmarks`, destekleniyorsa, kayıt kümesinde yer işaretlerini kullanabilir. Yer işaretleri yavaş veri alımı, ancak veri gezinmesi performansını geliştirir. Yalnızca iletme kayıt kümelerinde geçerli değildir. Daha fazla bilgi için bkz. [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- Otomatik kirli alan denetimini devre dışı bırakmak `CRecordset::noDirtyFieldCheck` (çift arabelleğe alma). Bu, performansı iyileştirir; Ancak, `SetFieldDirty` ve `SetFieldNull` üye işlevlerini çağırarak alanları kirli olarak el ile işaretlemeniz gerekir. `CRecordset` sınıfında çift arabelleğe alma, `CDaoRecordset`sınıfında çift arabelleğe alma ile benzerdir. Ancak, `CRecordset`' de tek tek alanlarda çift arabelleğe almayı etkinleştiremezsiniz; Tüm alanlar için etkinleştirin ya da tüm alanlar için devre dışı bırakın. `CRecordset::useMultiRowFetch`seçeneğini belirtirseniz `CRecordset::noDirtyFieldCheck` otomatik olarak açılır. Ancak, `SetFieldDirty` ve `SetFieldNull` toplu satır getirmeyi uygulayan kayıt kümelerinde kullanılamaz.

- `CRecordset::executeDirect` hazırlanan bir SQL ifadesini kullanmayın. Daha iyi performans için, `Requery` member işlevinin hiçbir şekilde çağrılmayacağı bu seçeneği belirtin.

- `CRecordset::useExtendedFetch` `SQLFetch`yerine `SQLExtendedFetch` uygulayın. Bu, yalnızca ileri kayıt kümelerinde toplu satır getirmeyi uygulamak için tasarlanmıştır. Yalnızca bir salt iletme kayıt kümesinde `CRecordset::useMultiRowFetch` seçeneğini belirtirseniz, `CRecordset::useExtendedFetch` otomatik olarak açılır.

- `CRecordset::userAllocMultiRowBuffers` kullanıcının veri için depolama arabellekleri ayıracaktır. Kendi depolama alanınızı ayırmak istiyorsanız bu seçeneği `CRecordset::useMultiRowFetch` birlikte kullanın; Aksi takdirde, çerçeve gerekli depolamayı otomatik olarak ayırır. Daha fazla bilgi için [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)başlıklı makaleye bakın. `CRecordset::useMultiRowFetch` belirtmeksizin `CRecordset::userAllocMultiRowBuffers` belirtmenin, başarısız bir onaylama işlemi ile sonuçlanabileceğini unutmayın.

### <a name="return-value"></a>Dönüş Değeri

`CRecordset` nesnesi başarıyla açıldıysa sıfır dışı; Aksi takdirde 0 varsa, [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (çağrılırsa) 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevini çağırmanız gerekir. `Open`çağrılmadan önce, kayıt kümesi nesnesi oluşturmanız gerekir.

Bu kayıt kümesinin veri kaynağıyla bağlantısı, `Open`çağrılmadan önce kayıt kümesini nasıl oluşturduğunuza bağlıdır. Veri kaynağına bağlı olmayan kayıt kümesi oluşturucusuna bir [CDatabase](../../mfc/reference/cdatabase-class.md) nesnesi geçirirseniz, bu üye işlev veritabanı nesnesini açmayı denemek Için [GetDefaultConnect](#getdefaultconnect) kullanır. Kayıt kümesi oluşturucusuna NULL geçirirseniz, Oluşturucu sizin için bir `CDatabase` nesnesi oluşturur ve `Open` veritabanı nesnesini bağlamaya çalışır. Kayıt kümesini ve bağlantıyı bu farklı koşullarda kapatma hakkında ayrıntılar için bkz. [Close](#close).

> [!NOTE]
>  `CRecordset` nesne aracılığıyla bir veri kaynağına erişim her zaman paylaşılır. `CDaoRecordset` sınıfından farklı olarak, bir veri kaynağını özel erişim ile açmak için bir `CRecordset` nesnesi kullanamazsınız.

`Open`çağırdığınızda bir sorgu, genellikle bir SQL **Select** deyimidir, aşağıdaki tabloda gösterilen ölçütlere göre kayıtları seçer.

|LpszSQL parametresinin değeri|Seçilen kayıtlar şunları belirler|Örnek|
|------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL`tarafından döndürülen dize.||
|SQL tablo adı|`DoFieldExchange` veya `DoBulkFieldExchange`içindeki Tablo listesinin tüm sütunları.|`"Customer"`|
|Önceden tanımlanmış sorgu (saklı yordam) adı|Sorgunun geri dönmesi için tanımladığı sütunlar.|`"{call OverDueAccts}"`|
|**Tablo listesinden** sütun listesi **seçin**|Belirtilen tablo (ler) den belirtilen sütunlar.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
>  SQL dizeniz üzerinde fazladan boşluk eklememeye dikkat edin. Örneğin, küme ayracı ve **Call** anahtar sözcüğü arasında boşluk eklersenız, MFC SQL dizesini tablo adı olarak yorumlayıp bir **Select** ifadesiyle birleştirir, bu da bir özel durum oluşmasına neden olur. Benzer şekilde, önceden tanımlanmış sorgunuz bir çıkış parametresi kullanıyorsa, küme ayracı ve ' ' sembolü arasına boşluk eklemeyin. Son olarak, bir **çağrı** deyimindeki küme ayracından önce veya **Select** deyimindeki **Select** anahtar sözcüğünden önce boşluk eklememelidir.

Her zamanki yordam `Open`NULL değer geçirmektir; Bu durumda, `Open` [GetDefaultSQL](#getdefaultsql)çağırır. Türetilmiş bir `CRecordset` sınıfı kullanıyorsanız, `GetDefaultSQL` ClassWizard 'da belirttiğiniz tablo adlarını verir. Bunun yerine `lpszSQL` parametresinde diğer bilgileri belirtebilirsiniz.

Her ne kadar başarılı olursa olsun, sorgu için son bir SQL dizesi `Open` (dize, geçirdiğiniz `lpszSQL` dizesinin sonuna SQL **WHERE** ve **order by** yan tümceleri olabilir) ve sonra sorguyu yürütür. `Open`çağrıldıktan sonra [GetSQL](#getsql) 'i çağırarak oluşturulmuş dizeyi inceleyebilirsiniz. Kayıt kümesinin bir SQL ifadesini nasıl oluşturup kayıt seçtiğinden ilgili ek ayrıntılar için kayıt [kümesi: kayıt kümeleri kayıtları seçme (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

Kayıt kümesi sınıfınızın alan veri üyeleri, seçilen verilerin sütunlarına bağlanır. Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesi için filtre veya sıralama gibi seçenekler ayarlamak istiyorsanız, kayıt kümesi nesnesini oluşturduktan sonra, ancak `Open`çağırmadan önce bu ayarları belirtin. Kayıt kümesi zaten açık olduktan sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız, yeniden [sorgula](#requery)' yı çağırın.

Ek örnekler dahil daha fazla bilgi için bkz. Makaleler [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: kayıt kümeleri KAYıTLARı seçme (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)ve [kayıt kümesi: kayıt KÜMELERI oluşturma ve kapatma (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Örnek

Aşağıdaki kod örnekleri `Open` çağrısının farklı biçimlerini gösterir.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

##  <a name="refreshrowset"></a>CRecordset:: RefreshRowset

Geçerli satır kümesindeki bir satırın verilerini ve durumunu güncelleştirir.

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer sıfırdan satır kümesinin boyutuna kadar değişebilir.

*wLockType*<br/>
Yenilenme sonrasında satırın nasıl kilitleneceği belirten bir değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

*WRow*için sıfır değerini geçirirseniz, satır kümesindeki her satır yenilenir.

`RefreshRowset`kullanmak için, [Open](#open) member işlevinde `CRecordset::useMulitRowFetch` seçeneğini belirterek toplu satır getirmeyi uygulamış olmanız gerekir.

`RefreshRowset` ODBC API işlevini `SQLSetPos`çağırır. *WLockType* parametresi, `SQLSetPos` yürütüldükten sonra satırın kilit durumunu belirtir. Aşağıdaki tabloda *wLockType*için olası değerler açıklanmaktadır.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı, `RefreshRowset` çağrılmadan önce, sıranın aynı kilitli veya kilitlenmemiş durumda olmasını sağlar.|
|SQL_LOCK_EXCLUSIVE|Sürücü veya veri kaynağı satırı özel olarak kilitler. Tüm veri kaynakları bu tür kilidi desteklemez.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı satırın kilidini açar. Tüm veri kaynakları bu tür kilidi desteklemez.|

`SQLSetPos`hakkında daha fazla bilgi için bkz. Windows SDK. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="requery"></a>CRecordset:: Requery

Bir kayıt kümesini yeniden oluşturur (yeniler).

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi başarıyla yeniden oluşturulmuşsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesinin, sizin veya diğer kullanıcıların veri kaynağına yaptığı eklemeleri ve silmeleri yansıtması için, `Requery`çağırarak kayıt kümesini yeniden oluşturmanız gerekir. Kayıt kümesi bir Dynaset ise, sizin veya diğer kullanıcıların mevcut kayıtları (eklemeler) üzerinde yaptığı güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntüdür, diğer kullanıcıların yanı sıra eklemeleri ve silmeleri yansıtmak için `Requery` çağırmanız gerekir.

Bir Dynaset veya anlık görüntü için, yeni bir filtre veya sıralama ya da yeni parametre değerleri kullanarak kayıt kümesini yeniden derlemek istediğiniz zaman `Requery` çağırın. `Requery`çağrılmadan önce `m_strFilter` ve `m_strSort` yeni değerler atayarak yeni filtre veya sıralama özelliğini ayarlayın. `Requery`çağrılmadan önce parametre veri üyelerine yeni değerler atayarak yeni parametreler ayarlayın. Filtre ve sıralama dizeleri değişmezse, sorguyu yeniden kullanabilirsiniz ve bu da performansı geliştirir.

Kayıt kümesini yeniden derleme girişimi başarısız olursa, kayıt kümesi kapalıdır. `Requery`çağırmadan önce, `CanRestart` üye işlevini çağırarak kayıt kümesinin yeniden sorgulama yapıp kullanamayacağını belirleyebilirsiniz. `CanRestart`, `Requery` başarılı olacağını garanti etmez.

> [!CAUTION]
>  Yalnızca [Open](#open)'ı çağırdıktan sonra `Requery` çağırın.

### <a name="example"></a>Örnek

Bu örnek, farklı bir sıralama düzeni uygulamak için bir kayıt kümesi yeniden oluşturur.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

##  <a name="setabsoluteposition"></a>CRecordset:: SetAbsolutePosition

Kayıt kümesini belirtilen kayıt numarasına karşılık gelen kayıtta konumlandırır.

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Parametreler

*nsatırlar*<br/>
Kayıt kümesindeki geçerli kayıt için tek tabanlı sıra konumu.

### <a name="remarks"></a>Açıklamalar

`SetAbsolutePosition` geçerli kayıt işaretçisini bu sıra konumuna göre taşımaktır.

> [!NOTE]
>  Bu üye işlevi yalnızca iletme kayıt kümelerinde geçerli değildir.

ODBC kayıt kümeleri için, mutlak konum ayarı, kayıt kümesindeki ilk kayda başvurur; 0 ayarı dosya başı (BOF) konumunu ifade eder.

Ayrıca, `SetAbsolutePosition`negatif değerler geçirebilirsiniz. Bu durumda, kayıt kümesinin konumu kayıt kümesinin sonundan değerlendirilir. Örneğin, `SetAbsolutePosition( -1 )` geçerli kayıt işaretçisini kayıt kümesindeki son kayda taşıır.

> [!NOTE]
>  Mutlak konum, vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Önceki kayıtlar silindiğinde bir kaydın konumu değiştiği için, yer işaretleri hâlâ belirli bir konuma geri dönmek ve döndürmek için önerilen yoldur. Ayrıca, bir kayıt kümesi içindeki bireysel kayıtların sırası, **order by** yan tümcesi KULLANıLARAK bir SQL ifadesiyle oluşturulmadığı müddetçe, belirli bir kaydın aynı mutlak konuma sahip olduğundan emin olamaz.

Kayıt kümesi gezintisi ve yer işaretleri hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer Işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="setbookmark"></a>CRecordset:: SetBookmark

Kayıt kümesini belirtilen yer işaretini içeren kayıt üzerinde konumlandırır.

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Belirli bir kayıt için yer işareti değerini içeren bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinde yer işaretlerinin desteklenip desteklenmediğini anlamak için [CanBookmark](#canbookmark)çağırın. Eğer desteklendiklerinde yer imlerini kullanılabilir hale getirmek için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::useBookmarks` seçeneğini ayarlamanız gerekir.

> [!NOTE]
>  Yer işaretleri desteklenmiyorsa veya kullanılamıyorsa, `SetBookmark` çağırmak bir özel durum oluşmasına neden olur. Yer işaretleri salt iletme kayıt kümelerinde desteklenmez.

İlk olarak geçerli kayıt için yer işaretini almak üzere, bir `CDBVariant` nesnesine yer işareti değerini kaydeden [GetBookmark](#getbookmark)öğesini çağırın. Daha sonra, kaydedilen yer işareti değerini kullanarak `SetBookmark` çağırarak bu kayda geri dönebilirsiniz.

> [!NOTE]
>  Belirli kayıt kümesi işlemlerinden sonra, `SetBookmark`çağrılmadan önce yer işareti kalıcılığını denetlemeniz gerekir. Örneğin, `GetBookmark` içeren bir yer işareti alırsanız ve sonra `Requery`çağırırsanız, yer işareti artık geçerli olmayabilir. `SetBookmark`güvenli bir şekilde çağırıp çağıramayacağını denetlemek için [CDatabase:: Getbookmarkkalıcılığı](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) çağırın.

Yer işaretleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için bkz. makalelere [kayıt kümesi: yer işaretleri ve mutlak konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="setfielddirty"></a>CRecordset:: SetFieldDirty

Kayıt kümesinin alan veri üyesini değiştirilmiş veya değiştirilmemiş olarak işaretler.

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Kayıt kümesindeki bir alan veri üyesinin adresini veya NULL değerini içerir. NULL ise, kayıt kümesindeki tüm alan verisi üyeleri işaretlenir. (C++ Null, Veritabanı terminolojisinde null ile aynı değildir, yani "hiçbir değer yok" anlamına gelir.)

*bDirty*<br/>
Alan veri üyesi "kirli" (değiştirilmiş) olarak işaretlenmek için TRUE. Aksi takdirde, alan veri üyesi "temiz" (değiştirilmemiş) olarak işaretlenmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değiştirilmemiş olarak işaretlemek, alanın güncelleştirilmediğini ve daha az SQL trafiği elde edilmesini sağlar.

> [!NOTE]
>  Bu üye işlevi, toplu satır getirme kullanan kayıt kümelerinde uygulanabilir değildir. Toplu satır getirmeyi uyguladıysanız `SetFieldDirty`, başarısız bir onaylama işlemine neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Çerçeve, veri kaynağındaki kayda kayıt alanı değişimi (RFX) mekanizması tarafından yazıldıklarından emin olmak için alan veri üyelerini işaretler. Bir alanın değerini değiştirmek genellikle alanı kirli olarak ayarlar. bu nedenle, nadiren `SetFieldDirty` çağırmanız gerekir, ancak bazen, alan veri üyesinde hangi değerin olduğuna bakılmaksızın sütunların açıkça güncelleştirilmesini veya eklenmesini sağlamak isteyebilirsiniz.

> [!CAUTION]
>  Yalnızca [Edit](#edit) veya [AddNew](#addnew)çağrıldıktan sonra bu üye işlevini çağırın.

İşlevin ilk bağımsız değişkeni için NULL kullanmak, işlevi `param` alanlara değil yalnızca `outputColumn` alanlara uygular. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanlarını NULL olarak ayarlar; `param` alanlar etkilenmeyecektir.

`param` alanlarla çalışmak için, üzerinde çalışmak istediğiniz bireysel `param` gerçek adresini sağlamanız gerekir, örneğin:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, `outputColumn` alanları ile yaptığınız gibi tüm `param` alanlarını NULL olarak ayarlayamayacağı anlamına gelir.

##  <a name="setfieldnull"></a>CRecordset:: SetFieldNull

Kayıt kümesinin bir alan veri üyesini null (özellikle bir değer olmadan) veya null olmayan olarak işaretler.

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Kayıt kümesindeki bir alan veri üyesinin adresini veya NULL değerini içerir. NULL ise, kayıt kümesindeki tüm alan verisi üyeleri işaretlenir. (C++ Null, Veritabanı terminolojisinde null ile aynı değildir, yani "hiçbir değer yok" anlamına gelir.)

*bNull*<br/>
Alan verisi üyesinin değer yok (null) olarak işaretlenmek için sıfır dışında. Aksi takdirde 0 alan verisi üyesi null olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta null değere ayarlanır ve "kirli" (değiştirildi) olarak işaretlenir. Bir veri kaynağından bir kayıt aldığınızda, sütunlarının değerleri zaten var ya da null.

> [!NOTE]
>  Toplu satır getirme kullanan kayıt kümelerinde Bu üye işlevini çağırmayın. Toplu satır getirme uyguladıysanız, `SetFieldNull` çağrısı başarısız bir onaylama sırasında sonuçları çağırır. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Geçerli kaydın bir alanını bir değer olmadan belirlemek isterseniz, null olarak işaretlemek için *bNull* değeri true olarak ayarlanmış `SetFieldNull` çağırın. Bir alan önceden null olarak işaretlenmişse ve bundan böyle bir değer vermek istiyorsanız, yeni değerini ayarlamanız yeterlidir. Null bayrağını `SetFieldNull`kaldırmak zorunda değilsiniz. Alanın null olmasına izin verilip verilmeyeceğini anlamak için `IsFieldNullable`çağırın.

> [!CAUTION]
>  Yalnızca [Edit](#edit) veya [AddNew](#addnew)çağrıldıktan sonra bu üye işlevini çağırın.

İşlevin ilk bağımsız değişkeni için NULL kullanmak, işlevi `param` alanlara değil yalnızca `outputColumn` alanlara uygular. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanlarını NULL olarak ayarlar; `param` alanlar etkilenmeyecektir.

`param` alanlarla çalışmak için, üzerinde çalışmak istediğiniz bireysel `param` gerçek adresini sağlamanız gerekir, örneğin:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, `outputColumn` alanları ile yaptığınız gibi tüm `param` alanlarını NULL olarak ayarlayamayacağı anlamına gelir.

> [!NOTE]
>  Parametreleri null olarak ayarlarken, kayıt kümesi açılmadan önce `SetFieldNull` çağrısı bir onaylama işlemine neden olur. Bu durumda [SetParamNull](#setparamnull)çağrısı yapın.

`SetFieldNull`, [DoFieldExchange](#dofieldexchange)aracılığıyla uygulanır.

##  <a name="setlockingmode"></a>CRecordset:: SetLockingMode

Kilitleme modunu "iyimser" kilitleme (varsayılan) veya "kötümser" kilitleme olarak ayarlar. Kayıtların güncelleştirmeler için nasıl kilitlendiğini belirler.

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Parametreler

*nMode*<br/>
`enum LockMode`aşağıdaki değerlerden birini içerir:

- `optimistic` Iyimser kilitleme, yalnızca `Update`çağrısı sırasında güncelleştirilmekte olan kaydı kilitler.

- `pessimistic` Kötümser kilitleme, `Edit` çağrıldıktan hemen sonra kaydı kilitler ve `Update` çağrısı tamamlanana kadar veya yeni bir kayda geçene kadar kilitli kalır.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin güncelleştirmeler için hangi iki kayıt kilitleme stratejisinden hangisini kullandığını belirtmeniz gerekiyorsa bu üye işlevini çağırın. Varsayılan olarak, bir kayıt kümesinin kilitleme modu `optimistic`. Bunu, kilitleme stratejisi `pessimistic` daha dikkatli bir şekilde değiştirebilirsiniz. Kayıt kümesi nesnesini oluşturup açtıktan sonra, ancak `Edit`çağırmadan önce `SetLockingMode` çağırın.

##  <a name="setparamnull"></a>CRecordset:: SetParamNull

Bir parametreyi null (özellikle bir değer olmadan) veya null olmayan şekilde işaretler.

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Parametrenin sıfır tabanlı dizini.

*bNull*<br/>
TRUE ise (varsayılan değer), parametre null olarak işaretlenir. Aksi takdirde, parametresi null olmayan olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

[SetFieldNull](#setfieldnull)'ın aksine, kayıt kümesini açmadan önce `SetParamNull` çağırabilirsiniz.

`SetParamNull` genellikle önceden tanımlanmış sorgular (saklı yordamlar) ile kullanılır.

##  <a name="setrowsetcursorposition"></a>CRecordset:: SetRowsetCursorPosition

İmleci geçerli satır kümesi içindeki bir satıra kaydırır.

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer, 1 ' den satır kümesinin boyutuyla değişebilir.

*wLockType*<br/>
Yenilenme sonrasında satırın nasıl kilitleneceği belirten değer. Ayrıntılar için bkz. açıklamalar.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygularken, kayıtlar satır kümesi tarafından alınır; burada getirilen satır kümesindeki ilk kayıt geçerli kayıttır. Geçerli kaydın satır kümesi içinde başka bir kayıt yapmak için `SetRowsetCursorPosition`çağırın. Örneğin, verileri kayıt kümenizin herhangi bir kaydından dinamik olarak almak için `SetRowsetCursorPosition` [GetFieldValue](#getfieldvalue) üye işleviyle birleştirebilirsiniz.

`SetRowsetCursorPosition`kullanmak için, [Open](#open) member Işlevindeki *dwoptions* parametresinin `CRecordset::useMultiRowFetch` seçeneğini belirterek toplu satır getirmeyi uygulamış olmanız gerekir.

`SetRowsetCursorPosition` ODBC API işlevini `SQLSetPos`çağırır. *WLockType* parametresi, `SQLSetPos` yürütüldükten sonra satırın kilit durumunu belirtir. Aşağıdaki tabloda *wLockType*için olası değerler açıklanmaktadır.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı, `SetRowsetCursorPosition` çağrılmadan önce, sıranın aynı kilitli veya kilitlenmemiş durumda olmasını sağlar.|
|SQL_LOCK_EXCLUSIVE|Sürücü veya veri kaynağı satırı özel olarak kilitler. Tüm veri kaynakları bu tür kilidi desteklemez.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı satırın kilidini açar. Tüm veri kaynakları bu tür kilidi desteklemez.|

`SQLSetPos`hakkında daha fazla bilgi için bkz. Windows SDK. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="setrowsetsize"></a>CRecordset:: SetRowsetSize

Bir getirme sırasında almak istediğiniz kayıt sayısını belirtir.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Parametreler

*dwNewRowsetSize*<br/>
Belirli bir getirme sırasında alınacak satır sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlevi, toplu satır getirme kullanılırken tek bir getirme sırasında kaç satır getirmek istediğinizi belirtir. Toplu satır getirmeyi uygulamak için, [Open](#open) member Işlevinin *dwoptions* parametresinde `CRecordset::useMultiRowFetch` seçeneğini ayarlamanız gerekir.

> [!NOTE]
>  Toplu satır getirmeyi uygulamadan `SetRowsetSize` çağırmak, başarısız bir onaylama işlemine neden olur.

Kayıt kümesinin satır kümesi boyutunu başlangıçta ayarlamak için `Open` çağrılmadan önce `SetRowsetSize` çağırın. Toplu satır getirmeyi uygularken varsayılan satır kümesi boyutu 25 ' tir.

> [!NOTE]
>  `SetRowsetSize`çağrılırken dikkatli olun. Veriler için el ile depolama alanı ayırdıysanız (`Open`dwOptions parametresinin `CRecordset::userAllocMultiRowBuffers` seçeneği tarafından belirtildiği gibi), `SetRowsetSize`çağırdıktan sonra, imleç gezinme işlemini gerçekleştirmeden önce bu depolama arabelleklerini yeniden ayırmanız gerekip gerekmediğini denetlemeniz gerekir.

Satır kümesi boyutu için geçerli ayarı almak üzere [GetRowsetSize](#getrowsetsize)çağırın.

Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="update"></a>CRecordset:: Update

Yeni veya düzenlenmiş verileri veri kaynağına kaydederek bir `AddNew` veya `Edit` işlemi tamamlar.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt başarıyla güncelleştirilirse sıfır dışı; Aksi takdirde 0 sütunu değiştirilmeyecektir. Hiçbir kayıt güncellenmemişse veya birden fazla kayıt güncellendiyse, bir özel durum oluşturulur. Veri kaynağındaki diğer hatalar için de bir özel durum oluşturulur.

### <a name="remarks"></a>Açıklamalar

[AddNew](#addnew) veya [Edit](#edit) member işlevine yapılan çağrıdan sonra bu üye işlevini çağırın. `AddNew` veya `Edit` işleminin tamamlanabilmesi için bu çağrı gereklidir.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız `Update`çağıramaz. Bu, başarısız bir onaylama işlemi oluşmasına neden olur. `CRecordset` sınıfı, toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, `SQLSetPos`ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Hem `AddNew` hem de `Edit` veri kaynağına kaydetmek için eklenen veya düzenlenen verilerin yerleştirildiği bir düzenleme arabelleği hazırlayın. `Update` verileri kaydeder. Yalnızca değiştirilen veya değiştirilmiş olarak algılanan alanlar güncelleştirilir.

Veri kaynağı işlemleri destekliyorsa, `Update` çağrısını (ve buna karşılık gelen `AddNew` veya `Edit` çağrısını) bir işlemin parçası yapabilirsiniz. İşlemler hakkında daha fazla bilgi için bkz. Makale [işleme (ODBC)](../../data/odbc/transaction-odbc.md).

> [!CAUTION]
>  Önce `AddNew` veya `Edit`çağırılmadan `Update` çağırırsanız `Update` bir `CDBException`oluşturur. `AddNew` veya `Edit`çağırırsanız, `Move` bir işlemi çağırmadan önce veya kayıt kümesini ya da veri kaynağı bağlantısını kapatmadan önce `Update` çağırmanız gerekir. Aksi takdirde, değişiklikleriniz bildirim olmadan kaybedilir.

`Update` başarısızlıklarını işleme hakkında daha fazla bilgi için [kayıt kümesi: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

İşlem [: kayıt kümesinde Işlem gerçekleştirme (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView Sınıfı](../../mfc/reference/crecordview-class.md)
