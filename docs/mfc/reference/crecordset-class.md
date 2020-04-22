---
title: CRecordset Sınıfı
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
ms.openlocfilehash: ab6cde9f478dc6f2e3cb0ba5bb338a3852f083fd
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81750510"
---
# <a name="crecordset-class"></a>CRecordset Sınıfı

Veri kaynağından seçilen bir kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset::CRecordset](#crecordset)|Bir `CRecordset` nesne inşa eder. Türemiş sınıfınız, buna çağrı yapan bir oluşturucu sağlamalıdır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|Yeni bir kayıt eklemeye hazırlanıyor. Eklemeyi tamamlamak için arayın. `Update`|
|[CRecordset::CanAppend](#canappend)|`AddNew` Üye işlev aracılığıyla kayıt kümesine yeni kayıtlar eklenebiliyorsa sıfırsız döndürür.|
|[CRecordset::CanBookmark](#canbookmark)|Kayıt kümesi yer imlerini destekliyorsa sıfırsız döndürür.|
|[CRecordset::İptal et](#cancel)|Bir eşzamanlı işlemi veya işlemi ikinci bir iş parçacığından iptal eder.|
|[CRecordset::CancelUpdate](#cancelupdate)|Bir `AddNew` veya `Edit` işlem nedeniyle bekleyen güncelleştirmeleri iptal eder.|
|[CRecordset::CanRestart](#canrestart)|Kayıt kümesinin `Requery` sorgusunu yeniden çalıştırmak için çağrılabiliyorsa sıfırsız döndürür.|
|[CRecordset::CanScroll](#canscroll)|Kayıtlar arasında gezinebilirseniz sıfırsız döndürür.|
|[CRecordset::CanTransact](#cantransact)|Veri kaynağı hareketleri destekliyorsa sıfırsız döndürür.|
|[CRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilebiliyorsa sıfırsız döndürür (kayıtları ekleyebilir, güncelleyebilir veya silebilirsiniz).|
|[CRecordset::CheckRowsetHatası](#checkrowseterror)|Kayıt alma sırasında oluşturulan hataları işlemek için çağrıldı.|
|[CRecordset::Kapat](#close)|Kayıt kümesini ve onunla ilişkili ODBC HSTMT'yi kapatır.|
|[CRecordset::Delete](#delete)|Geçerli kaydı kayıt kümesinden siler. Silme işleminden sonra açıkça başka bir kayda kaydırmanız gerekir.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Veri kaynağından kayıt kümesine toplu veri satırları değişimi için çağrılır. Toplu kayıt alanı değişimi (Toplu RFX) uygular.|
|[CRecordset::DoFieldExchange](#dofieldexchange)|Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki ilgili kayıt arasında veri alışverişi (her iki yönde de) çağrılır. Kayıt alanı değişimini (RFX) uygular.|
|[CRecordset::Edit](#edit)|Geçerli kayıtta yapılan değişiklikler için hazırlandığız. Yapılan `Update` mayı tamamlamak için arayın.|
|[CRecordset::FlushResultSet](#flushresultset)|Önceden tanımlanmış bir sorgu kullanırken, alınacak başka bir sonuç kümesi varsa sıfırsız döndürür.|
|[CRecordset::GetBookmark](#getbookmark)|Bir kaydın yer işareti değerini parametre nesnesine atar.|
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Varsayılan bağlantı dizesini almak için çağrıldı.|
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Varsayılan SQL dizesini çalıştırmak için çağrıldı.|
|[CRecordset::GetFieldValue](#getfieldvalue)|Bir kayıt kümesindeki alanın değerini verir.|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Kayıt kümesindeki alan sayısını verir.|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Kayıt kümesindeki alanlar hakkında belirli türde bilgiler verir.|
|[CRecordset::GetRecordCount](#getrecordcount)|Kayıt kümesindeki kayıt sayısını verir.|
|[CRecordset::GetRowsetSize](#getrowsetsize)|Tek bir getirme sırasında almak istediğiniz kayıt sayısını verir.|
|[CRecordset::GetRowsFetched](#getrowsfetched)|Bir getirme sırasında alınan gerçek satır sayısını verir.|
|[CRecordset::GetRowStatus](#getrowstatus)|Bir getirmeden sonra satırın durumunu döndürür.|
|[CRecordset::GetSQL](#getsql)|Kayıt kümesi nin kayıtlarını seçmek için kullanılan SQL dizesini alır.|
|[CRecordset::GetStatus](#getstatus)|Kayıt kümesinin durumunu alır: geçerli kaydın dizini ve kayıtların son sayısının alınıp alınmadığı.|
|[CRecordset::GetTableName](#gettablename)|Kayıt kümesinin dayandığı tablonun adını alır.|
|[CRecordset::IsBOF](#isbof)|Kayıt kümesi ilk kayıtöncesinde konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.|
|[CRecordset::Silinmiş](#isdeleted)|Kayıt kümesi silinmiş bir kayıt ta konumlandırılmışsa sıfırsız döndürür.|
|[CRecordset::IsEOF](#iseof)|Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.|
|[CRecordset::IsFieldDirty](#isfielddirty)|Geçerli kayıtta belirtilen alan değiştirildiyse sıfırsız döndürür.|
|[CRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıtta belirtilen alan null (hiçbir değeri yoktur) ise sıfırsız döndürür.|
|[CRecordset::IsFieldNullable](#isfieldnullable)|Geçerli kayıtta belirtilen alan null (değeri olmayan) olarak ayarlanabilirse sıfırsız döndürür.|
|[CRecordset::Açık](#isopen)|Daha önce `Open` çağrıldıysa sıfırsız döndürür.|
|[CRecordset::Taşı](#move)|Kayıtları her iki yönde de geçerli kayıttan belirli bir sayıda ki kayıt sayısına konumlandırın.|
|[CRecordset::MoveFirst](#movefirst)|Geçerli kaydı kayıt kümesindeki ilk kayıtta konumlandırın. Önce `IsBOF` test edin.|
|[CRecordset::MoveLast](#movelast)|Geçerli kaydı son kayıtta veya son satır kümesinde konumlandırın. Önce `IsEOF` test edin.|
|[CRecordset::MoveNext](#movenext)|Geçerli kaydı bir sonraki kayda veya bir sonraki satır kümesine konumlandırın. Önce `IsEOF` test edin.|
|[CRecordset::MovePrev](#moveprev)|Geçerli kaydı önceki kayıtta veya önceki satır kümesinde konumlandırın. Önce `IsBOF` test edin.|
|[CRecordset::OnSetOptions](#onsetoptions)|Belirtilen ODBC deyimi için seçenekleri ayarlamak (seçimde kullanılır) için çağrılır.|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Belirtilen ODBC deyimi için seçenekleri ayarlamak için çağrılır (güncelleştirmede kullanılır).|
|[CRecordset::Aç](#open)|Tabloyu alarak veya kayıt kümesinin temsil ettiği sorguyu gerçekleştirerek kayıt kümesini açar.|
|[CRecordset::RefreshRowset](#refreshrowset)|Belirtilen satır(lar) verilerini ve durumunu yeniler.|
|[CRecordset::Yeniden sorgu](#requery)|Seçili kayıtları yenilemek için kayıt kümesinin sorgusunu yeniden çalıştırın.|
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesini belirtilen kayıt numarasına karşılık gelen kayıt kümesine konumlandırın.|
|[CRecordset::SetBookmark](#setbookmark)|Kayıt kümesini yer imi tarafından belirtilen kayıtta konumlandırın.|
|[CRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıtta belirtilen alanı değiştirilmiş olarak işaretler.|
|[CRecordset::SetFieldNull](#setfieldnull)|Geçerli kayıtta belirtilen alanın değerini null (değeri olmayan) olarak ayarlar.|
|[CRecordset::SetLockingMode](#setlockingmode)|Kilitleme modunu "iyimser" kilitleme (varsayılan) veya "kötümser" kilitleme olarak ayarlar. Güncelleştirmeler için kayıtların nasıl kilitlendirilebildiğini belirler.|
|[CRecordset::SetParamNull](#setparamnull)|Belirtilen parametreyi null (değeri olmayan) olarak ayarlar.|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|İmleci satır kümesi içinde belirtilen satıra konumlandırın.|
|[CRecordset::SetRowsetSize](#setrowsetsize)|Bir getirme sırasında almak istediğiniz kayıt sayısını belirtir.|
|[CRecordset::Güncelleme](#update)|Yeni veya `AddNew` `Edit` düzenlenen verileri veri kaynağına kaydederek bir işlemi veya işlemi tamamlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CRecordset::m_hstmt](#m_hstmt)|Kayıt kümesi için ODBC deyimi tutamacını içerir. `HSTMT` yazın.|
|[CRecordset::m_nFields](#m_nfields)|Kayıt kümesindeki alan veri üye sayısını içerir. `UINT` yazın.|
|[CRecordset::m_nParams](#m_nparams)|Kayıt kümesindeki parametre veri üye sayısını içerir. `UINT` yazın.|
|[CRecordset::m_pDatabase](#m_pdatabase)|Kayıt kümesinin `CDatabase` bir veri kaynağına bağlı olduğu nesneye bir işaretçi içerir.|
|[CRecordset::m_strFilter](#m_strfilter)|`CString` Yapılandırılmış Sorgu Dili (SQL) `WHERE` yan tümcesini belirten bir sözcük içerir. Yalnızca belirli ölçütleri karşılayan kayıtları seçmek için filtre olarak kullanılır.|
|[CRecordset::m_strSort](#m_strsort)|`CString` Bir SQL `ORDER BY` yan tümcesi belirten bir içerir. Kayıtların nasıl sıralandığını denetlemek için kullanılır.|

## <a name="remarks"></a><a name="remarks"></a>Açıklamalar

"Kayıt kümeleri" `CRecordset` olarak bilinen nesneler genellikle iki şekilde kullanılır: dinaset ve anlık görüntüler. Dynaset, diğer kullanıcılar tarafından yapılan veri güncelleştirmeleriyle senkronize kalır. Anlık görüntü, verilerin statik görünümüdür. Her form, kayıt kümesinin açıldığı anda sabitlenmiş bir kayıt kümesini temsil eder, ancak bir dinamitte bir kayda kaydırdığınızda, diğer kullanıcılar veya uygulamanızdaki diğer kayıt kümeleri tarafından daha sonra kayda yapılan değişiklikleri yansıtır.

> [!NOTE]
> Açık Veritabanı Bağlantısı (ODBC) sınıfları yerine Veri Erişim Nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) sınıfını kullanın. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

Her iki tür de kayıt kümesiyle çalışmak için genellikle `CRecordset`uygulamaya özgü bir kayıt kümesi sınıfı. Kayıt kümeleri bir veri kaynağından kayıtları seçer ve daha sonra şunları yapabilirsiniz:

- Kayıtlar arasında ilerleyin.

- Kayıtları güncelleştirin ve kilitleme modu belirtin.

- Kayıt kümesini, veri kaynağında bulunanlardan hangi kayıtları seçerek sınırlandıracak şekilde filtreleyin.

- Kayıt kümesini sıralayın.

- Seçimin çalışma süresine kadar bilinmeyen bilgilerle özelleştirilmesi için kayıt kümesini parametreleştirin.

Sınıfınızı kullanmak için bir veritabanı açın ve bir kayıt kümesi nesnesi oluşturarak oluşturucuyu nesnenize `CDatabase` bir işaretçi geçirin. Ardından, nesnenin bir `Open` dinamit mi yoksa anlık görüntü mü olduğunu belirtebileceğiniz kayıt kümesinin üye işlevini arayın. Arama, `Open` veri kaynağından veri seçer. Kayıt kümesi nesnesi açıldıktan sonra, kayıtları kaydırmak ve bunları çalıştırmak için üye işlevlerini ve veri üyelerini kullanın. Kullanılabilir işlemler, nesnenin bir dinamit mi yoksa anlık görüntü mü olduğuna, güncelmiyete veya salt okunur olmasına (bu, Açık Veritabanı Bağlantısı (ODBC) veri kaynağının yeteneğine bağlıdır) ve toplu satır alma işlemi uygulayıp uygulamadığınıza bağlıdır. `Open` Çağrıdan sonra değiştirilmiş veya eklenmiş olabilecek kayıtları yenilemek `Requery` için nesnenin üye işlevini arayın. Nesnenin `Close` üye işlevini çağırın ve onunla bitirdiğinizde nesneyi yok edin.

Türetilmiş `CRecordset` bir sınıfta, kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Toplu RFX) kayıt alanlarının okunmasını ve güncellenmesini desteklemek için kullanılır.

Kayıt kümeleri ve kayıt alanı değişimi hakkında daha fazla bilgi için [makalelere Genel Bakış: Veritabanı Programlama,](../../data/data-access-programming-mfc-atl.md) [Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md), Kayıt Kümesi: Toplu Olarak [Kayıt Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)ve [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)bölümüne bakın. Dynasets ve anlık görüntülere odaklanmak için [Dynaset](../../data/odbc/dynaset.md) ve [Snapshot](../../data/odbc/snapshot.md)makalelerine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>CRecordset::AddNew

Tabloya yeni bir kayıt eklemeye hazırlanır.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Yeni eklenen kaydı görmek için [Requery](#requery) üye işlevini aramalısınız. Kaydın alanları başlangıçta Null'tur. (Veritabanı terminolojisinde Null "değeri yoktur" anlamına gelir ve C++'daki NULL ile aynı değildir.) İşlemi tamamlamak [için, Update](#update) üye işlevini aramanız gerekir. `Update`değişikliklerinizi veri kaynağına kaydeder.

> [!NOTE]
> Toplu satır alma uyguladıysanız, 'yi `AddNew`arayamazsınız. Bu başarısız bir iddia neden olur. Sınıf, `CRecordset` toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC API işlevini `SQLSetPos`kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

`AddNew`kayıt kümesinin alan veri üyelerini kullanarak yeni, boş bir kayıt hazırlar. Aradıktan `AddNew`sonra, kayıt kümesinin alan veri üyeleriistediğiniz değerleri ayarlayın. (Bu amaçla [Edit](#edit) üye işlevini çağırmak zorunda değilsin; yalnızca varolan kayıtlar için kullanın.) `Edit` Daha sonra , `Update`alan veri üyeleri değiştirilen değerleri çağırdığınızda veri kaynağına kaydedilir.

> [!CAUTION]
> Aramadan `Update`önce yeni bir kayda kaydırırsanız, yeni kayıt kaybolur ve hiçbir uyarı verilmez.

Veri kaynağı hareketleri destekliyorsa, `AddNew` aramanızı bir hareketin parçası yapabilirsiniz. İşlemler hakkında daha fazla bilgi için [CDatabase](../../mfc/reference/cdatabase-class.md)sınıfına bakın. [CDatabase::BeginTrans'ı](../../mfc/reference/cdatabase-class.md#begintrans) aramadan `AddNew`önce aramanız gerektiğini unutmayın.

> [!NOTE]
> Dynaset'ler için, son kayıt olarak kayıt kümesine yeni kayıtlar eklenir. Eklenen kayıtlar anlık görüntülere eklenmez; kayıt kümesini yenilemek için aramalısınız. `Requery`

Üye işlevi çağrılmayan bir kayıt kümesi ni çağırmak `AddNew` yasa dışıdır. `Open` Eklenen `CDBException` olmayan bir `AddNew` kayıt kümesi ni çağırırsanız A atılır. Kayıt kümesinin güncellenebilir olup olmadığını [CanAppend'i](#canappend)arayarak belirleyebilirsiniz.

Daha fazla bilgi için aşağıdaki makalelere bakın: [Recordset: Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Recordset: Ekleme, Güncelleme ve Kayıtları Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)ve [İşlem (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

Makaleye Bakın [Hareket: Kayıt Kümesinde (ODBC) İşlem Gerçekleştirme.](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

## <a name="crecordsetcanappend"></a><a name="canappend"></a>CRecordset::CanAppend

Daha önce açılmış kayıt kümesinin yeni kayıtlar eklemenize izin verip vermeyini belirler.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yeni kayıtlar eklenmesine izin veriyorsa sıfıra inme; aksi takdirde 0. `CanAppend`yalnızca okunur olarak kayıt kümesini açtıysanız 0 döndürecektir.

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>CRecordset::CanBookmark

Kayıt kümesinin yer imlerini kullanarak kayıtları işaretlemenize izin verip vermeyini belirler.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yer imlerini destekliyorsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, `CRecordset::useBookmarks` [Açık](#open) üye işlevinin *dwOptions* parametresindeki seçenekten bağımsızdır. `CanBookmark`verilen ODBC sürücüsü nün ve imleç türünün yer imlerini destekleyip desteklemediğini gösterir. `CRecordset::useBookmarks`desteklenmeleri koşuluyla yer imlerinin kullanılabilir olup olmayacağını gösterir.

> [!NOTE]
> Yer imleri yalnızca ileri kayıt kümelerinde desteklenmez.

Yer imleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Bookmarks and Absolute Positions (ODBC) ve](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)makalelerine bakın.

## <a name="crecordsetcancel"></a><a name="cancel"></a>CRecordset::İptal et

Veri kaynağının devam eden bir eşzamanlı işlemi veya ikinci bir iş parçacığından bir işlemi iptal etme isteği.

```cpp
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıfları artık eşzamanlı işleme kullanmaz; bir asychronous işlemi gerçekleştirmek için doğrudan ODBC API işlevini `SQLSetConnectOption`aramanız gerekir. Daha fazla bilgi için, *ODBC SDK Programcı Kılavuzu'nda*"İşlevleri Eşit bir şekilde yürütme" konusuna bakın.

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>CRecordset::CancelUpdate

[Güncelleştirme](#update) çağrılmadan önce bir [Düzenleme](#edit) veya [AddNew](#addnew) işleminin neden olduğu bekleyen güncelleştirmeleri iptal eder.

```cpp
void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu tür kayıt kümeleri `Edit`, `AddNew`" veya `Update`. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Otomatik kirli alan denetimi `CancelUpdate` etkinse, üye değişkenleri daha `Edit` önce `AddNew` sahip oldukları veya çağrıldıkları değerlere geri yüklenir; aksi takdirde, herhangi bir değer değişiklikleri kalır. Varsayılan olarak, kayıt kümesi açıldığında otomatik alan denetimi etkinleştirilir. Devre dışı bırakabilmek `CRecordset::noDirtyFieldCheck` [için, Open](#open) üye işlevinin *dwOptions* parametresini belirtmeniz gerekir.

Verileri güncelleştirme hakkında daha fazla bilgi için [Recordset: Records(ODBC) ekleme, güncelleme ve silme makalesine](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)bakın.

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>CRecordset::CanRestart

Kayıt kümesinin `Requery` üye işlevi arayarak sorgusunu yeniden başlatmaya (kayıtlarını yenilemeye) izin verip vermeyeceğini belirler.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

Requery izin verilirse Nonzero; aksi takdirde 0.

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>CRecordset::CanScroll

Kayıt kümesinin kaydırmaya izin verip vermeyeceğini belirler.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kaydırmaya izin veriyorsa sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)makalesine bakın.

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>CRecordset::CanTransact

Kayıt kümesinin hareketlere izin verip vermeyeceğini belirler.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi işlemlere izin veriyorsa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>CRecordset::CanUpdate

Kayıt kümesinin güncelleştirilip güncelleştirilemeyeceğini belirler.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirilebiliyorsa sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Altta yatan veri kaynağı salt okunursa veya kayıt kümesini `CRecordset::readOnly` açtığınızda *dwOptions* parametresinde belirtilmişseniz, yalnızca bir kayıt kümesi okunabilir.

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>CRecordset::CheckRowsetHatası

Kayıt alma sırasında oluşturulan hataları işlemek için çağrıldı.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
ODBC API işlev döndürme kodu. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlev, kayıtlar geldiğinde oluşan hataları işler ve toplu satır alma sırasında yararlıdır. Kendi hata işleme uygulamak `CheckRowsetError` için geçersiz kılma yı düşünebilirsiniz.

`CheckRowsetError`imleç gezinti işleminde `Open`(, yani `Requery`herhangi `Move` bir işlem) otomatik olarak çağrılır. ODBC API işlevinin `SQLExtendedFetch`geri dönüş değeri geçirilir. Aşağıdaki tabloda *nRetCode* parametresi için olası değerler listeleilmektedir.

|nRetCode|Açıklama|
|--------------|-----------------|
|SQL_SUCCESS|İşlev başarıyla tamamlandı; ek bilgi yok.|
|Sql_success_wıth_ınfo|İşlev, büyük olasılıkla ölümcül olmayan bir hata ile başarıyla tamamlandı. Ek bilgi arayarak `SQLError`elde edilebilir.|
|SQL_NO_DATA_FOUND|Sonuç kümesinden tüm satırlar getirilmiştir.|
|Sql_error|İşlev başarısız oldu. Ek bilgi arayarak `SQLError`elde edilebilir.|
|Sql_ınvalıd_handle|İşlev geçersiz bir ortam tutamacı, bağlantı tutamacı veya deyim tutamacı nedeniyle başarısız oldu. Bu bir programlama hatası gösterir. 'den `SQLError`ek bilgi yok.|
|Sql_stıll_executıng|Eşsenkronize olarak başlatılan bir işlev hala yürütülmeye devam ediyor. Varsayılan olarak, MFC'nin bu değeri `CheckRowsetError`asla geçmeyeceğini unutmayın; MFC, SQL_STILL_EXECUTING `SQLExtendedFetch` dönene kadar aramaya devam edecektir.|

Hakkında daha `SQLError`fazla bilgi için Windows SDK'ya bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetclose"></a><a name="close"></a>CRecordset::Kapat

Kayıt kümesini kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

ODBC HSTMT ve kayıt kümesi için ayrılan tüm bellek ayrılır. Genellikle aradıktan `Close`sonra, **yeni**.

Aradıktan `Open` sonra tekrar `Close`arayabilirsiniz. Bu, kayıt kümesi nesnesini yeniden kullanmanıza olanak tanır. Diğer seçenek aramak. `Requery`

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>CRecordset::CRecordset

Bir `CRecordset` nesne inşa eder.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir `CDatabase` nesneye veya NULL değerine işaretçi içerir. NULL değilse ve `CDatabase` nesnenin `Open` üye işlevi veri kaynağına bağlamak için çağrılmazsa, kayıt kümesi kendi `Open` araması sırasında onu sizin için açmaya çalışır. NULL'u geçerseniz, ClassWizard ile kayıt kümesi sınıfınızı türetdiğinizde belirttiğiniz veri kaynağı bilgilerini kullanarak sizin için bir `CDatabase` nesne oluşturulur ve bağlanır.

### <a name="remarks"></a>Açıklamalar

Doğrudan kullanabilir `CRecordset` veya `CRecordset`uygulamaya özgü bir sınıf türetebilirsiniz. Kayıt kümesi sınıflarınızı türetmek için ClassWizard'ı kullanabilirsiniz.

> [!NOTE]
> Türemiş bir sınıf kendi oluşturucusu *sağlamalıdır.* Türemiş sınıfınızın oluşturucusunda, `CRecordset::CRecordset`uygun parametreleri ona ileterek oluşturucuyu arayın.

Bir `CDatabase` nesnenin sizin için otomatik olarak oluşturulması ve bağlanması için NULL'u kayıt ayarlı oluşturucunuza geçirin. Bu, kayıt setinizi oluşturmadan önce bir nesne `CDatabase` oluşturmanızı ve bağlamanızı gerektirmeyen kullanışlı bir kısaltmadır.

### <a name="example"></a>Örnek

Daha fazla bilgi [için, makaleye bakın Recordset: Tablo için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

## <a name="crecordsetdelete"></a><a name="delete"></a>CRecordset::Delete

Geçerli kaydı siler.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı bir silme işleminden sonra, kayıt kümesinin alan veri üyeleri Null değerine ayarlanır ve `Move` silinen kayıttan çıkmak için işlevlerden birini açıkça aramanız gerekir. Silinen kayıttan çıktıktan sonra, kaydına geri dönmek mümkün değildir. Veri kaynağı hareketleri destekliyorsa, `Delete` aramayı bir hareketin parçası yapabilirsiniz. Daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

> [!NOTE]
> Toplu satır alma uyguladıysanız, 'yi `Delete`arayamazsınız. Bu başarısız bir iddia neden olur. Sınıf, `CRecordset` toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC API işlevini `SQLSetPos`kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

> [!CAUTION]
> Kayıt kümesi güncellenebilir olmalı ve çağrı `Delete`yaptığınızda kayıt setinde geçerli bir kayıt akımı olmalıdır; aksi takdirde, bir hata oluşur. Örneğin, bir kaydı siler, ancak yeniden aramadan `Delete` önce `Delete` yeni bir kayda kaydırmazsanız, bir [CDBException](../../mfc/reference/cdbexception-class.md)atar.

[AddNew](#addnew) ve [Edit'in](#edit) `Delete` aksine, bir [çağrıyı Güncelleştirme](#update)çağrısı takip etmez. Bir `Delete` çağrı başarısız olursa, alan veri üyeleri değişmeden bırakılır.

### <a name="example"></a>Örnek

Bu örnek, bir işlevin çerçevesi üzerinde oluşturulan bir kayıt kümesini gösterir. Örnek, veri kaynağına `m_dbCust`zaten bağlı olan `CDatabase` bir üye değişkenin varlığını varsayar.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange

Veri kaynağından kayıt kümesine toplu veri satırları değişimi için çağrılır. Toplu kayıt alanı değişimi (Toplu RFX) uygular.

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine işaretçi. Çerçeve, alan değişimi işlemi için bir bağlam belirtmek için bu nesneyi zaten ayarlamış olacaktır.

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uygulandığında, çerçeve veri kaynağından kayıt kümesi nesnenize verileri otomatik olarak aktarmak için bu üye işlevi çağırır. `DoBulkFieldExchange`ayrıca, parametre veri üyelerinizi, varsa, kayıt kümesinin seçimi için SQL deyimi dizesinde parametre yer tutucularına bağlar.

Toplu satır alma uygulanmazsa, çerçeve [DoFieldExchange](#dofieldexchange)çağırır. Toplu satır getirme uygulamak [için,](#open) `CRecordset::useMultiRowFetch` Açık üye işlevinde *dwOptions* parametre seçeneğini belirtmeniz gerekir.

> [!NOTE]
> `DoBulkFieldExchange`yalnızca `CRecordset`türetilmiş bir sınıf kullanıyorsanız kullanılabilir. Doğrudan bir kayıt kümesi nesnesi `CRecordset`oluşturduysanız, veri almak için [GetFieldValue](#getfieldvalue) üye işlevini aramanız gerekir.

Toplu kayıt alanı değişimi (Bulk RFX) kayıt alanı değişimine (RFX) benzer. Veriler otomatik olarak veri kaynağından kayıt kümesi nesnesine aktarılır. Ancak, değişiklikleri `AddNew`veri `Edit` `Delete`kaynağına `Update` geri aktaramaz veya geri alamazsınız. Sınıf `CRecordset` şu anda toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamaz; ancak, ODBC API işlevini `SQLSetPos`kullanarak kendi işlevlerinizi yazabilirsiniz.

ClassWizard'ın toplu kayıt alanı değişimini desteklemediğini unutmayın; bu nedenle, Toplu `DoBulkFieldExchange` RFX işlevlerine çağrı yazarak el ile geçersiz kılmanız gerekir. Bu işlevler hakkında daha fazla bilgi için, kayıt [alanı değişim fonksiyonları](../../mfc/reference/record-field-exchange-functions.md)konusuna bakın.

Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın. İlgili bilgiler için [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)makalesine bakın.

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CRecordset::DoFieldExchange

Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki ilgili kayıt arasında veri alışverişi (her iki yönde de) çağrılır. Kayıt alanı değişimini (RFX) uygular.

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
[CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine işaretçi. Çerçeve, alan değişimi işlemi için bir bağlam belirtmek için bu nesneyi zaten ayarlamış olacaktır.

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uygulanmadığında, çerçeve bu üye işlevi, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasında otomatik olarak veri alışverişi yapmak için çağırır. `DoFieldExchange`ayrıca, parametre veri üyelerinizi, varsa, kayıt kümesinin seçimi için SQL deyimi dizesinde parametre yer tutucularına bağlar.

Toplu satır alma uygulanıyorsa, çerçeve [DoBulkFieldExchange](#dobulkfieldexchange)çağırır. Toplu satır getirme uygulamak [için,](#open) `CRecordset::useMultiRowFetch` Açık üye işlevinde *dwOptions* parametre seçeneğini belirtmeniz gerekir.

> [!NOTE]
> `DoFieldExchange`yalnızca `CRecordset`türetilmiş bir sınıf kullanıyorsanız kullanılabilir. Doğrudan bir kayıt kümesi nesnesi `CRecordset`oluşturduysanız, veri almak için [GetFieldValue](#getfieldvalue) üye işlevini aramanız gerekir.

Kayıt alanı değişimi (RFX) adı verilen alan veri alışverişi her iki yönde de çalışır: kayıt kümesi nesnesinin alan veri üyelerinden veri kaynağındaki kayıt alanlarına ve veri kaynağındaki kayıttan kayıt kümesi nesnesine kadar.

Türemiş kayıt kümesi sınıfınız `DoFieldExchange` için normalde uygulamanız gereken tek eylem ClassWizard ile sınıfı oluşturmak ve alan veri üyelerinin adlarını ve veri türlerini belirtmektir. Ayrıca, parametre veri üyelerini belirtmek veya dinamik olarak bağladığınız sütunlarla başa çıkmak için ClassWizard'ın yazdıklarına kod ekleyebilirsiniz. Daha fazla bilgi için [Recordset: DynamicAlly Binding Data Columns (ODBC) makalesine](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)bakın.

Türemiş kayıt kümesi sınıfınızı ClassWizard ile beyan ettiğinizde, sihirbaz sizin `DoFieldExchange` için aşağıdaki örneğe benzeyen bir geçersiz kılma yazar:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX işlevleri hakkında daha fazla bilgi için, kayıt [alanı değişim fonksiyonları](../../mfc/reference/record-field-exchange-functions.md)konusuna bakın.

Hakkında daha fazla `DoFieldExchange`bilgi ve ayrıntılar için, [makalekayıt alanı değişimi bakın: Nasıl RFX Çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md). RFX hakkında genel bilgi için [Kayıt Alanı Değişimi](../../data/odbc/record-field-exchange-rfx.md)makalesine bakın.

## <a name="crecordsetedit"></a><a name="edit"></a>CRecordset::Edit

Geçerli kayıtta değişiklik yapılmasına izin verir.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

Aradıktan `Edit`sonra, alan veri üyelerini değerlerini doğrudan sıfırlayarak değiştirebilirsiniz. Değişikliklerinizi veri kaynağına kaydetmek için Daha sonra [Üye Güncelleştirme](#update) işlevini çağırdığınızda işlem tamamlanır.

> [!NOTE]
> Toplu satır alma uyguladıysanız, 'yi `Edit`arayamazsınız. Bu başarısız bir iddia neden olur. Sınıf, `CRecordset` toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC API işlevini `SQLSetPos`kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

`Edit`kaydedici nin veri üyelerinin değerlerini kaydeder. Ararsanız, `Edit`değişiklik yaparsanız, `Edit` sonra yeniden arayın, kaydın değerleri ilk `Edit` çağrıdan önce oldukları şekilde geri yüklenir.

Bazı durumlarda, bir sütunu Null (veri içermeden) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için, Alan Null işaretlemek için TRUE bir parametre ile [SetFieldNull](#setfieldnull) arayın; bu da sütunun güncelleştirilmesine neden olur. Değeri değişmemiş olsa bile bir alanın veri kaynağına yazılmasını istiyorsanız, TRUE parametresi ile [SetFieldDirty'i](#setfielddirty) arayın. Alan Null değerine sahip olsa bile bu işe yarar.

Veri kaynağı hareketleri destekliyorsa, `Edit` aramayı bir hareketin parçası yapabilirsiniz. [CDatabase::BeginTrans'ı](../../mfc/reference/cdatabase-class.md#begintrans) aramadan `Edit` önce ve kayıt kümesi açıldıktan sonra aramanız gerektiğini unutmayın. Ayrıca [CDatabase::CommitTrans'ı](../../mfc/reference/cdatabase-class.md#committrans) aramanın `Edit` işlemi `Update` tamamlamak için aramanın yerini tutamadığını da unutmayın. İşlemler hakkında daha fazla bilgi için [CDatabase](../../mfc/reference/cdatabase-class.md)sınıfına bakın.

Geçerli kilitleme moduna bağlı olarak, güncelleştirilen kayıt `Edit` siz arayana `Update` veya başka bir kayda kaydırAna `Edit` kadar kilitlenebilir veya yalnızca arama sırasında kilitlenebilir. [Kilitleme Modunu](#setlockingmode)ile kilitleme modunu değiştirebilirsiniz.

Aramadan `Update`önce yeni bir kayda kaydırırsanız geçerli kaydın önceki değeri geri yüklenir. Güncelleştirilemeyen bir `Edit` kayıt kümesi ni ararsanız veya geçerli bir kayıt yoksa A `CDBException` atılır.

Daha fazla bilgi için, işlem [(ODBC)](../../data/odbc/transaction-odbc.md) ve [Recordset: Kilitleme Kayıtları (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)makalelerini görün.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>CRecordset::FlushResultSet

Birden çok sonuç kümesi varsa, önceden tanımlanmış bir sorgunun (depolanan yordam) bir sonraki sonuç kümesini alır.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Dönüş Değeri

Alınacak daha fazla sonuç kümesi varsa sıfıra yakın; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca geçerli `FlushResultSet` sonuç kümesindeki imleç tamamen bittiğinde aramalısınız. Arayarak `FlushResultSet`ayarlanan bir sonraki sonucu aldığınızda imlecin bu sonuç kümesinde geçerli olmadığını unutmayın; aradıktan sonra [MoveNext](#movenext) üye `FlushResultSet`işlevini aramalısınız.

Önceden tanımlanmış bir sorgu bir çıktı parametresi veya giriş/çıkış parametreleri kullanıyorsa, bu parametre değerlerini elde etmek için döndürene `FlushResultSet` `FALSE` kadar (değer 0) aramanız gerekir.

`FlushResultSet`ODBC API işlevini `SQLMoreResults`çağırır. SQL_ERROR `SQLMoreResults` veya SQL_INVALID_HANDLE dönerse, bir özel durum `FlushResultSet` oluşturur. Hakkında daha `SQLMoreResults`fazla bilgi için Windows SDK'ya bakın.

Aramak istiyorsanız, depolanan yordamınızın bağlı alanları `FlushResultSet`olması gerekir.

### <a name="example"></a>Örnek

Aşağıdaki kod, giriş `COutParamRecordset` parametresi ve çıktı parametresi olan ve birden çok sonuç kümesiolan önceden tanımlanmış bir sorguya dayalı türetilmiş bir nesne olduğunu `CRecordset`varsayar. [DoFieldExchange](#dofieldexchange) geçersiz kılma yapısına dikkat edin.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>CRecordset::GetBookmark

Geçerli kaydın yer işareti değerini alır.

```cpp
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Geçerli kayıttaki yer işaretini temsil eden [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Kayıt setinde yer imlerinin desteklenip desteklenmedigerekden belirlemek için [CanBookmark'ı](#canbookmark)arayın. Yer imlerini desteklenirse kullanılabilir hale getirmek `CRecordset::useBookmarks` için, seçeneği [Açık](#open) üye işlevinin *dwOptions* parametresinde ayarlamanız gerekir.

> [!NOTE]
> Yer imleri desteklenmezse veya kullanılamıyorsa, arama `GetBookmark` bir özel durum atılmasına neden olur. Yer imleri yalnızca ileri kayıt kümelerinde desteklenmez.

`GetBookmark`geçerli kayıt için yer işaretinin değerini bir `CDBVariant` nesneye atar. Farklı bir kayda geçtikten sonra herhangi bir zamanda bu kayda `CDBVariant` dönmek için, ilgili nesneyle [Birlikte SetBookmark'ı](#setbookmark) arayın.

> [!NOTE]
> Belirli kayıt kümesi işlemden sonra yer imleri artık geçerli olmayabilir. Örneğin, ardından `GetBookmark` `Requery`ararsanız, '' ile `SetBookmark`kayda geri dönemeyebilirsiniz. CDatabase'i arayın::Güvenli bir şekilde arayıp arayamayacağınızı kontrol etmek için [GetBookmarkPersistence'](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) ı arayın. `SetBookmark`

Yer imleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Bookmarks and Absolute Positions (ODBC) ve](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)makalelerine bakın.

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>CRecordset::GetDefaultConnect

Varsayılan bağlantı dizesini almak için çağrıldı.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `CString` bağlantı dizesi içeren bir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, kayıt kümesinin dayandığı veri kaynağı için varsayılan bağlantı dizesini almak için bu üye işlevi çağırır. ClassWizard tablolar ve sütunlar hakkında bilgi almak için ClassWizard kullandığınız aynı veri kaynağını tanımlayarak sizin için bu işlevi uygular. Uygulamanızı geliştirirken bu varsayılan bağlantıya güvenmeyi büyük olasılıkla uygun bulacaksınız. Ancak varsayılan bağlantı uygulamanızın kullanıcıları için uygun olmayabilir. Bu durumda, ClassWizard sürümünü atarak bu işlevi yeniden uygulamanız gerekir. Bağlantı dizeleri hakkında daha fazla bilgi için [Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)makalesine bakın.

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CRecordset::GetDefaultSQL

Varsayılan SQL dizesini çalıştırmak için çağrıldı.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `CString` SQL deyimini içeren bir.

### <a name="remarks"></a>Açıklamalar

Çerçeve, kayıt kümesinin dayandığı varsayılan SQL deyimini almak için bu üye işlevi çağırır. Bu bir tablo adı veya SQL **SELECT** deyimi olabilir.

ClassWizard ile kayıt kümesi sınıfınızı beyan ederek dolaylı olarak varsayılan SQL deyimini tanımlarsınız ve ClassWizard bu görevi sizin yerinize gerçekleştirir.

Kendi kullanımınız için SQL deyimi dizesi gerekiyorsa, açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL deyimini döndüren " i gerektirin. `GetSQL` Varsayılan SQL dizesini sınıfınızın geçersiz kılındırında `GetDefaultSQL`atlayabilirsiniz. Örneğin, **CALL** deyimini kullanarak önceden tanımlanmış bir sorguya çağrı belirtebilirsiniz. (Ancak, bunu değiştirirseniz, `GetDefaultSQL`veri kaynağındaki sütun `m_nFields` sayısını eşleşecek şekilde değiştirmeniz gerektiğini unutmayın.)

Daha fazla bilgi [için, makaleye bakın Recordset: Tablo için Bir Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
> Çerçeve bir tablo adını tanımlayamazsa, birden çok tablo adı sağlanmışsa veya **CALL** deyimi yorumlanamazsa tablo adı boş olacaktır. **CALL** deyimini kullanırken kıvırcık ayracı ile **CALL** anahtar kelimesi arasına beyaz boşluk eklememeniz gerektiğini ve kıvırcık ayracın önüne veya **SELECT** deyimindeki **SELECT** anahtar sözcüğünden önce beyaz boşluk eklememeniz gerektiğini unutmayın.

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CRecordset::GetFieldValue

Geçerli kayıttaki alan verilerini alır.

```cpp
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

*Lpszname*<br/>
Bir alanın adı.

*varValu*e Alanın değerini depolayacak bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine başvuru.

*nFieldType*<br/>
Alanın ODBC C veri türü. Varsayılan değeri kullanarak, DEFAULT_FIELD_TYPE, aşağıdaki tabloya dayalı olarak SQL veri türünden C veri türünü belirlemeye zorlar. `GetFieldValue` Aksi takdirde, veri türünü doğrudan belirtebilir veya uyumlu bir veri türü seçebilirsiniz; örneğin, herhangi bir veri türünü SQL_C_CHAR olarak depolayabilirsiniz.

|C veri türü|SQL veri türü|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|Sql_c_char|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|Sql_c_bınary|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

ODBC veri türleri hakkında daha fazla bilgi için Windows SDK'nın Ek D'sinde yer alan "SQL Veri Türleri" ve "C Veri Türleri" konularına bakın.

*Nındex*<br/>
Alanın sıfır tabanlı dizin.

*strValue*<br/>
Alanın veri türüne bakılmaksızın, alanın metne dönüştürülen değerini depolayacak bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesine yapılan başvuru.

### <a name="remarks"></a>Açıklamalar

Bir alanı ada veya dizin olarak ada göre alabilirsiniz. Alan değerini bir `CDBVariant` nesnede veya `CString` nesnede depolayabilirsiniz.

Toplu satır alma uyguladıysanız, geçerli kayıt her zaman bir satır kümesindeki ilk kayıtta konumlandırılır. Belirli `GetFieldValue` bir satır kümesi içinde bir kayıt kullanmak için, imleci bu satır kümesi içinde istenen satıra taşımak için önce [SetRowsetCursorPosition](#setrowsetcursorposition) üye işlevini aramanız gerekir. O `GetFieldValue` zaman o sırayı ara. Toplu satır getirme uygulamak [için,](#open) `CRecordset::useMultiRowFetch` Açık üye işlevinde *dwOptions* parametre seçeneğini belirtmeniz gerekir.

Alanları tasarım `GetFieldValue` zamanında statik olarak bağlamak yerine çalışma zamanında dinamik olarak getirmek için kullanabilirsiniz. Örneğin, doğrudan bir kayıt kümesi nesnesi beyan `CRecordset` `GetFieldValue` ettiyseniz, alan verilerini almak için kullanmanız gerekir; kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Bulk RFX), uygulanmaz.

> [!NOTE]
> Bir kayıt kümesi nesnesini kaynaktan `CRecordset`bildirirseniz, ODBC İmleç Kitaplığı yüklü değildir. İmleç kitaplığı, kayıt kümesinin en az bir bağlı sütunu olması gerekir; ancak, doğrudan `CRecordset` kullandığınızda, sütunların hiçbiri bağlı değildir. Üye [işlevler CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) ve [CDatabase::İmleç](../../mfc/reference/cdatabase-class.md#open) kitaplığın yüklenip yüklenmeyeceğini kontrol edin.

`GetFieldValue`ODBC API işlevini `SQLGetData`çağırır. Sürücünüz alan değerinin gerçek uzunluğu için SQL_NO_TOTAL değer `GetFieldValue` çıkarsa, bir özel durum atar. Hakkında daha `SQLGetData`fazla bilgi için Windows SDK'ya bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek kod, doğrudan `GetFieldValue` 'den `CRecordset`beyan edilen bir kayıt kümesi nesnesi için yapılan çağrıları göstermektedir.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> DAO sınıfının `CDaoRecordset` `CRecordset` aksine, üye `SetFieldValue` işlevi yoktur. Bir nesneyi doğrudan `CRecordset`bir nesne oluşturursanız, etkili bir şekilde salt okunur.

Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount

Kayıt kümesi nesnenizdeki toplam alan sayısını alır.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki alan sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için [Recordset: Creating and Closing Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)makalesine bakın.

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>CRecordset::GetODBCFieldInfo

Kayıt kümesindeki alanlar hakkında bilgi alır.

```cpp
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Bir alanın adı.

*Fieldınfo*<br/>
Bir `CODBCFieldInfo` yapıya gönderme.

*Nındex*<br/>
Alanın sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir alanı ada göre aramanızı sağlar. Diğer sürüm, bir alanı dizin bazında aramanızı sağlar.

Döndürülen bilgilerle ilgili bir açıklama için [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) yapısına bakın.

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için [Recordset: Creating and Closing Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)makalesine bakın.

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>CRecordset::GetRecordCount

Kayıt kümesinin boyutunu belirler.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısı; Kayıt kümesi kayıt yoksa 0; veya -1 kayıt sayısı belirlenemiyorsa.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Kayıt sayısı bir "yüksek su işareti" olarak korunur, kullanıcı kayıtları arasında hareket ettikçe henüz görülen en yüksek numaralı kayıt. Toplam kayıt sayısı yalnızca kullanıcı son kaydın ötesine geçtikten sonra bilinir. Performans nedenleriyle, 'yi aradiğinizde `MoveLast`sayım güncelleştirilmez. Kayıtları kendiniz saymak `MoveNext` için, `IsEOF` sıfır olmayan döndürünceye kadar art arda arayın. Üzerinden `CRecordset:AddNew` bir kayıt `Update` ekleme ve sayısı artırır; üzerinden `CRecordset::Delete` bir kaydı silerek sayı azalır.

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>CRecordset::GetRowsetSize

Belirli bir getirme sırasında almak istediğiniz satır sayısı için geçerli ayarı alır.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirli bir getirme sırasında alınacak satır sayısı.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme kullanıyorsanız, kayıt kümesi açıldığında varsayılan rowset boyutu 25'tir; aksi takdirde, 1'dir.

Toplu satır alma uygulamak için, `CRecordset::useMultiRowFetch` [Açık](#open) üye işlevinin *dwOptions* parametresinde seçeneği belirtmeniz gerekir. Rowset boyutunun ayarını değiştirmek için [SetRowsetSize'ı](#setrowsetsize)arayın.

Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>CRecordset::GetRowsFetched

Bir getirmeden sonra gerçekte kaç kaydın alındığını belirler.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirli bir getirmeden sonra veri kaynağından alınan satır sayısı.

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uyguladığınız zaman bu yararlıdır. Satır kümesi boyutu normalde bir getir'den kaç satır alınacağını gösterir; ancak, kayıt kümesindeki toplam satır sayısı, bir satır kümesinde kaç satır Alınacağını da etkiler. Örneğin, kayıt setinizin rowset boyutu ayarı 4 olan 10 kaydı varsa, `MoveNext` son satır kümesinin yalnızca 2 kaydı olması yla sonuçlanır.

Toplu satır alma uygulamak için, `CRecordset::useMultiRowFetch` [Açık](#open) üye işlevinin *dwOptions* parametresinde seçeneği belirtmeniz gerekir. Rowset boyutunu belirtmek için [SetRowsetSize'ı](#setrowsetsize)arayın.

Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>CRecordset::GetRowStatus

Geçerli satır kümesindeki bir satırın durumunu alır.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer, satır kümesinin boyutu 1 arasında değişebilir.

### <a name="return-value"></a>Dönüş Değeri

Satır için durum değeri. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

`GetRowStatus`Veri kaynağından son alındığı için satırdaki herhangi bir değişikliği veya *wRow'a* karşılık gelen hiçbir satırın getirilmediğini gösteren bir değer döndürür. Aşağıdaki tabloda olası iade değerleri listelenilmektedir.

|Durum değeri|Açıklama|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Satır değişmedi.|
|SQL_ROW_UPDATED|Satır güncelleştirildi.|
|SQL_ROW_DELETED|Satır silindi.|
|SQL_ROW_ADDED|Satır eklendi.|
|SQL_ROW_ERROR|Satır bir hata nedeniyle geri alınamaz.|
|SQL_ROW_NOROW|*WRow*karşılık gelen hiçbir satır yoktur.|

Daha fazla bilgi için Windows SDK'daki ODBC API işlevine `SQLExtendedFetch` bakın.

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>CRecordset::GetStatus

Kayıt kümesindeki geçerli kaydın dizini ve son kaydın görülüp görülmediğini belirler.

```cpp
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Parametreler

*rDurum*<br/>
Bir `CRecordsetStatus` nesneye başvuru. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`CRecordset`dizini izleme girişiminde bulunabilir, ancak bazı durumlarda bu mümkün olmayabilir. Açıklama için [GetRecordCount'a](#getrecordcount) bakın.

Yapı `CRecordsetStatus` aşağıdaki forma sahiptir:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

İki üyenin `CRecordsetStatus` şu anlamları vardır:

- `m_lCurrentRecord`Biliniyorsa, kayıt kümesindeki geçerli kaydın sıfır tabanlı dizinini içerir. Dizin belirlenemiyorsa, bu üye AFX_CURRENT_RECORD_UNDEFINED (-2) içerir. TRUE `IsBOF` ise (boş kayıt kümesi veya ilk kayıt `m_lCurrentRecord` önce kaydırma girişimi), sonra AFX_CURRENT_RECORD_BOF (-1) ayarlanır. İlk kayıtta ise, 0, ikinci kayıt 1 ve benzeri olarak ayarlanır.

- `m_bRecordCountFinal`Kayıt kümesindeki toplam kayıt sayısı belirlendiyse sıfırsız. Genellikle bu, kayıt kümesinin başında başlayıp sıfır olmayan `MoveNext` `IsEOF` dönene kadar arayarak gerçekleştirilmelidir. Bu üye sıfır ise, -1 `GetRecordCount`değilse, döndürülen kayıt sayısı, kayıtların yalnızca "yüksek su işareti" sayısıdır.

## <a name="crecordsetgetsql"></a><a name="getsql"></a>CRecordset::GetSQL

Açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL deyimini almak için bu üye işlevini arayın.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

SQL deyimini içeren `CString` bir **const** başvurusu.

### <a name="remarks"></a>Açıklamalar

Bu genellikle bir SQL **SELECT** deyimi olacaktır. Döndürülen `GetSQL` dize salt okunur.

Döndürülen `GetSQL` dize genellikle `Open` *lpszSQL* parametresinde üye işleviçin kayıt kümesine geçmiş olabileceğiniz herhangi bir dizeden farklıdır. Bunun nedeni, kayıt kümesinin, geçtiğiniz şeye, ClassWizard'da belirttiğiniz şeye, `Open` `m_strFilter` `m_strSort` veri üyelerinde ve veri üyelerinde belirttiğiniz parametrelere ve belirttiğiniz parametrelere göre tam bir SQL deyimi oluşturmasıdır. Kayıt kümesinin bu SQL deyimini nasıl yaptığı hakkında ayrıntılı bilgi için [Recordset: Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

> [!NOTE]
> Bu üye işlevini yalnızca [Aç'ı](#open)aradıktan sonra arayın.

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>CRecordset::GetTableName

Kayıt kümesinin sorgusunun temel aldığı SQL tablosunun adını alır.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi bir `CString` tabloya dayanıyorsa, tablo adını içeren bir **const** başvurusu; aksi takdirde, boş bir dize.

### <a name="remarks"></a>Açıklamalar

`GetTableName`yalnızca kayıt kümesi birden çok tablonun veya önceden tanımlanmış bir sorgunun (depolanan yordam) birleşimi değil, bir tabloyu temel alıyorsa geçerlidir. Ad salt okunur.

> [!NOTE]
> Bu üye işlevini yalnızca [Aç'ı](#open)aradıktan sonra arayın.

## <a name="crecordsetisbof"></a><a name="isbof"></a>CRecordset::IsBOF

Kayıt kümesi ilk kayıtöncesinde konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermisse veya ilk kayıtdan önce geriye kaydırDsanız sıfır aci; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin ilk kaydından önce olup olmadığınızı öğrenmek için kayıttan kayda kaydırmadan önce bu üye işlevini arayın. Kayıt kümesinin `IsBOF` herhangi `IsEOF` bir kayıt içermediğini veya boş olup olmadığını belirlemek için de kullanabilirsiniz. Aramadan `Open`hemen sonra, kayıt kümesi kayıt `IsBOF` yoksa sıfırsız döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, `IsBOF` ilk kayıt geçerli kayıttır ve 0 döndürür.

İlk kayıt geçerli kayıtsa ve `MovePrev` `IsBOF` ararsanız, daha sonra sıfırsız döndürülecektir. Sıfırsız `IsBOF` döndürür `MovePrev`ve ararsanız, bir hata oluşur. Sıfırsız `IsBOF` döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem hataya neden olur.

### <a name="example"></a>Örnek

Bu örnek, `IsEOF` kod kayıt kümesinde her iki yönde de gezinirken kayıt kümesinin sınırlarını kullanır. `IsBOF`

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>CRecordset::Silinmiş

Geçerli kaydın silinip silinmediğini belirler.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayıt ta konumlandırılırsa sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kaydırır `IsDeleted` ve TRUE (sıfır olmayan) döndürür, başka bir kayıt kümesi işlemi gerçekleştirebilmek için önce başka bir kayda kaydırmanız gerekir.

Bunun sonucu, kayıt kümesi türünüz, kayıt setinizin güncelolup olmadığı, kayıt `IsDeleted` kümesini `CRecordset::skipDeletedRecords` açtığınızda seçeneği belirtip belirtmediğiniz, sürücünüzün silinmiş kayıtları paketleyip paketlemediği ve birden çok kullanıcı olup olmadığı gibi birçok etkene bağlıdır.

Sürücü paketleme `CRecordset::skipDeletedRecords` ve hakkında daha fazla bilgi için [Açık](#open) üye işlevine bakın.

> [!NOTE]
> Toplu satır alma uyguladıysanız, aramamalısınız. `IsDeleted` Bunun yerine, [GetRowStatus](#getrowstatus) üye işlevini arayın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetiseof"></a><a name="iseof"></a>CRecordset::IsEOF

Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermadıysa veya son kaydın ötesine geçtiyseniz sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin son kaydının ötesine geçip geçmediğinizi öğrenmek için kayıttan kayda geçerken bu üye işlevini arayın. Kayıt kümesinin `IsEOF` herhangi bir kayıt içerip içermediğini veya boş olup olmadığını belirlemek için de kullanabilirsiniz. Aramadan `Open`hemen sonra, kayıt kümesi kayıt `IsEOF` yoksa sıfırsız döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, `IsEOF` ilk kayıt geçerli kayıttır ve 0 döndürür.

Son kayıt, aradığınız `MoveNext`geçerli kayıtsa, `IsEOF` daha sonra sıfırsız döndürecektir. Sıfırsız `IsEOF` döndürür `MoveNext`ve ararsanız, bir hata oluşur. Sıfırsız `IsEOF` döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem hataya neden olur.

### <a name="example"></a>Örnek

[IsBOF](#isbof)örneğine bakın.

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>CRecordset::IsFieldDirty

[Edit](#edit) veya [AddNew](#addnew) çağrıldığından beri belirtilen alan veri üyesinin değiştirilip değiştirilmediğini belirler.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin kirli olup olmadığını belirlemek için NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi çağrıdan `AddNew` sonra `Edit`değişmişse sıfırsız veya; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tüm kirli alan veri üyelerindeki veriler, geçerli kayıt Güncelleştirme [üye](#update) işlevine yapılan bir çağrı yla `CRecordset` güncelleştirildiğinde (bir `AddNew`çağrıyı takip ederek veya ardından) veri kaynağındaki kayda `Edit` aktarılır.

> [!NOTE]
> Bu üye işlev, toplu satır alma kullanan kayıt kümelerinde geçerli değildir. Toplu satır alma uyguladıysanız, o `IsFieldDirty` zaman her zaman FALSE döndürecek ve başarısız bir iddia neden olur. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Alanın `IsFieldDirty` kirli durumu yeniden değerlendirildiğinden, arama [setfielddirty](#setfielddirty) önceki çağrıların etkilerini sıfırlar. `AddNew` Durumda, geçerli alan değeri sözde null değerinden farklıysa, alan durumu kirli olarak ayarlanır. `Edit` Durumda, alan değeri önbelleğe alınan değerden farklıysa, alan durumu kirli olarak ayarlanır.

`IsFieldDirty`[DoFieldExchange](#dofieldexchange)üzerinden uygulanmaktadır.

Kirli bayrak hakkında daha fazla bilgi için [Recordset: How Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>CRecordset::IsFieldNull

Geçerli kayıtta belirtilen alan Null ise sıfırsız döndürür (değeri yoktur).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin Null olup olmadığını belirlemek için NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null olarak işaretlenirse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesinin belirtilen alan veri üyesinin Null olarak işaretlenip işaretlenmediğini belirlemek için bu üye işlevini arayın. (Veritabanı terminolojisinde Null "değeri yoktur" anlamına gelir ve C++'daki NULL ile aynı değildir.) Bir alan veri üyesi Null olarak işaretlenirse, geçerli kaydın değeri olmayan bir sütunu olarak yorumlanır.

> [!NOTE]
> Bu üye işlev, toplu satır alma kullanan kayıt kümelerinde geçerli değildir. Toplu satır alma uyguladıysanız, o `IsFieldNull` zaman her zaman FALSE döndürecek ve başarısız bir iddia neden olur. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

`IsFieldNull`[DoFieldExchange](#dofieldexchange)üzerinden uygulanmaktadır.

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CRecordset::IsFieldNullable

Geçerli kayıtta belirtilen alan Null olarak ayarlanabiliyorsa (değeri olmayan) sıfırsız döndürür.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin Null değerine ayarlanıp ayarlanamayacağına karar vermek için NULL.

### <a name="remarks"></a>Açıklamalar

Belirtilen alan veri üyesinin "nullable" olup olmadığını belirlemek için bu üye işlevini arayın (Null değerine ayarlanabilir; C++ NULL, veritabanı terminolojisinde "değeri olmayan" anlamına gelen Null ile aynı değildir.

> [!NOTE]
> Toplu satır alma uyguladıysanız, 'yi `IsFieldNullable`arayamazsınız. Bunun yerine, bir alanın Null değerine ayarlanıp ayarlanamayacağını belirlemek için [GetODBCFieldInfo](#getodbcfieldinfo) üye işlevini arayın. Toplu satır alma `GetODBCFieldInfo`uygulamanız olup olmadığına bakılmaksızın her zaman arayabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Null olmayan bir alanın bir değeri olmalıdır. Bir kaydı eklerken veya güncellerken böyle bir alanı Null'a ayarlamaya çalışırsanız, veri kaynağı eklemeyi veya güncelleştirmeyi reddeder ve [Güncelleştirme](#update) bir özel durum oluşturur. Özel durum, `Update` [SetFieldNull'u](#setfieldnull)aradığınızda değil, aradiğinizde oluşur.

İşlevin ilk bağımsız değişkeni için NULL'un kullanılması `param` işlevi alanlara değil, yalnızca alanlara `outputColumn` uygular. Örneğin, arama

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanları NULL olarak ayarlar; `param` alanlar etkilenmez.

`param` Alanlarda çalışmak için, üzerinde çalışmak istediğiniz kişinin `param` gerçek adresini sağlamanız gerekir:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, tüm `param` alanları, alanlar ile `outputColumn` yapabildiğiniz gibi NULL olarak ayarlayamayacağınız anlamına gelir.

`IsFieldNullable`[DoFieldExchange](#dofieldexchange)üzerinden uygulanmaktadır.

## <a name="crecordsetisopen"></a><a name="isopen"></a>CRecordset::Açık

Kayıt kümesinin zaten açık olup olmadığını belirler.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi nesnesinin [Açık](#open) veya [Requery](#requery) üye işlevi daha önce çağrıldıysa ve kayıt kümesi kapatılmadıysa sıfırsız; aksi takdirde 0.

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>CRecordset::m_hstmt

ODBC deyimi veri yapısına, hstmt türünde, kayıt kümesiyle ilişkili bir tanıtıcı içerir.

### <a name="remarks"></a>Açıklamalar

ODBC veri kaynağına her sorgu bir HSTMT ile ilişkilidir.

> [!CAUTION]
> `m_hstmt` [Açık](#open) çağrılmadan önce kullanmayın.

Normalde Doğrudan HSTMT erişmek gerekmez, ancak SQL deyimleri doğrudan yürütülmesi için gerekebilir. Sınıfın `ExecuteSQL` `CDatabase` üye işlevi kullanarak `m_hstmt`bir örnek sağlar.

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>CRecordset::m_nFields

Kayıt kümesi sınıfındaki alan veri üye sayısını içerir; diğer bir şekilde, veri kaynağından kayıt kümesi tarafından seçilen sütun sayısıdır.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfının oluşturucusu `m_nFields` doğru sayıyla birlikte başlatılması gerekir. Toplu satır alma uygulamadıysanız, ClassWizard kayıt kümesi sınıfını bildirmek için kullandığınızda bu başlatmayı sizin için yazar. Ayrıca el ile de yazabilirsiniz.

Çerçeve, alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasındaki etkileşimi yönetmek için bu sayıyı kullanır.

> [!CAUTION]
> Bu numara, parametreile `DoFieldExchange` `CFieldExchange::outputColumn` [SetFieldType'a](../../mfc/reference/cfieldexchange-class.md#setfieldtype) `DoBulkFieldExchange` yapılan bir çağrıda veya sonrasında kayıtlı "çıkış sütunları" sayısına karşılık olmalıdır.

"Recordset: DynamicAlly Binding Data Columns" makalesinde açıklandığı gibi sütunları dinamik olarak bağlayabilirsiniz. Bunu yaparsanız, dinamik olarak bağlanan sütunlar için sizin veya `m_nFields` `DoFieldExchange` `DoBulkFieldExchange` üye işlevinizdeki RFX veya Toplu RFX işlev çağrılarının sayısını yansıtacak şekilde sayımını artırmanız gerekir.

Daha fazla bilgi [için, kayıt kümesi: Dinamik Bağlama Veri Sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) ve [Kayıt Kümesi: Toplu Olarak Kayıt Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalelerini görün.

### <a name="example"></a>Örnek

Makaleye bakın [Kayıt Alanı Değişimi: RFX kullanma.](../../data/odbc/record-field-exchange-using-rfx.md)

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>CRecordset::m_nParams

Recordset sınıfındaki parametre veri üye sayısını içerir; diğer bir şekilde, kayıt kümesinin sorgusuyla geçirilen parametrelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızda herhangi bir parametre veri üyesi varsa, `m_nParams` sınıfın oluşturucusu doğru sayıyla baş harfe yönelik olmalıdır. `m_nParams` Varsayılan değer 0'a kadar. Parametre veri üyeleri eklerseniz (el ile yapmanız gereken) parametre sayısını yansıtmak için sınıf oluşturucuya el ile bir başlatma eklemeniz gerekir (en azından `m_strFilter` `m_strSort` sizin veya dizenizdeki 'yer tutucuların sayısı kadar olması gerekir).

Çerçeve, kayıt kümesinin sorgusunu parametreleştirdiğinde bu sayıyı kullanır.

> [!CAUTION]
> Bu numara, [SetFieldType'a](../../mfc/reference/cfieldexchange-class.md#setfieldtype) yapılan bir `DoFieldExchange` `DoBulkFieldExchange` aramadan ve parametre değeri `CFieldExchange::inputParam` `CFieldExchange::param` `CFieldExchange::outputParam`, , , veya `CFieldExchange::inoutParam`.

### <a name="example"></a>Örnek

  [Makale kayıt seti bakınız: Bir Recordset parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) ve Kayıt Alanı [Değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CRecordset::m_pDatabase

Kayıt kümesinin `CDatabase` bir veri kaynağına bağlı olduğu nesneye bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu değişken iki şekilde ayarlanır. Genellikle, kayıt kümesi nesnesini oluştursanız, önceden bağlanmış `CDatabase` bir nesneye işaretçi geçirirsiniz. Bunun yerine NULL'u geçerseniz, `CRecordset` sizin için bir `CDatabase` nesne oluşturur ve onu bağlar. Her iki `CRecordset` durumda da işaretçiyi bu değişkende saklar.

Normalde doğrudan depolanan işaretçi kullanmanız `m_pDatabase`gerekmez. `CRecordset`Ancak, kendi uzantılarınızı yazarsanız, işaretçiyi kullanmanız gerekebilir. Örneğin, kendi `CDBException`s atarsanız işaretçi gerekebilir. Veya işlemleri çalıştırma, zaman ayırışlarını `CDatabase` ayarlama veya doğrudan SQL deyimlerini yürütmek için `ExecuteSQL` sınıfın `CDatabase` üye işlevini çağırmak gibi aynı nesneyi kullanarak bir şey yapmanız gerekiyorsa buna ihtiyacınız olabilir.

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>CRecordset::m_strFilter

Kayıt kümesi nesnesini oluşturduktan sonra, `Open` ancak üye işlevini aramadan `CString` önce, bu veri üyesini kullanarak bir SQL **WHERE** yan tümcesi içeren bir yan tümceyi depolayın.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi, arama sırasında seçtiği kayıtları kısıtlamak (veya `Open` `Requery` filtrelemek) için bu dizeyi kullanır. Bu, "Kaliforniya'da bulunan tüm satış temsilcileri" ("eyalet = CA") gibi bir kayıt alt kümesini seçmek için yararlıdır. **WHERE** yan tümcesi için ODBC SQL sözdizimi

`WHERE search-condition`

Dizenize **WHERE** anahtar sözcüklerini eklemediğinizi unutmayın. Çerçeve bunu sağlıyor.

Ayrıca, filtre dizenizi içine '' yer tutucuları yerleştirerek, her yer tutucuiçin sınıfınızda bir parametre veri üyesi beyan ederek ve parametreleri çalışma zamanında kayıt kümesine geçirerek parametrenize aktarabilirsiniz. Bu, filtreyi çalışma zamanında oluşturmanıza olanak tanır. Daha fazla bilgi için [Recordset: Parameterizing a Recordset (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)makalesine bakın.

SQL **WHERE** yan tümceleri hakkında daha fazla bilgi için [SQL](../../data/odbc/sql.md)makalesine bakın. Kayıtları seçme ve filtreleme hakkında daha fazla bilgi için [Recordset: Filtering Records (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>CRecordset::m_strSort

Kayıt kümesi nesnesini oluşturduktan sonra, `Open` ancak üye işlevini aramadan `CString` önce, sql **order by** yan tümcesi içeren bir depolamak için bu veri üyesini kullanın.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi, arama sırasında `Open` `Requery` seçtiği kayıtları sıralamak için bu dizeyi kullanır. Bir veya daha fazla sütunda bir kayıt kümesini sıralamak için bu özelliği kullanabilirsiniz. **Order BY** yan tümcesi için ODBC SQL sözdizimi

`ORDER BY sort-specification [, sort-specification]...`

sıralama belirtimi nin bir tamsayı veya sütun adı olduğu durumlarda. Ayrıca, sıralama dizesinde sütun listesine "ASC" veya "DESC" ekleyerek artan veya azalan sırayı (sipariş varsayılan olarak yükseliyor) belirtebilirsiniz. Seçili kayıtlar önce listelenen ilk sütuna, sonra ikinci sütuna göre sıralanır. Örneğin, önce soyadına, sonra da adla bir "Müşteriler" kayıt kümesi sipariş edebilirsiniz. Listelediğiniz sütun sayısı veri kaynağına bağlıdır. Daha fazla bilgi için Windows SDK'ya bakın.

String'inize ORDER **BY** anahtar sözcüklerini eklemediğinizi unutmayın. Çerçeve bunu sağlıyor.

SQL yan tümceleri hakkında daha fazla bilgi için [SQL](../../data/odbc/sql.md)makalesine bakın. Kayıtları sıralama hakkında daha fazla bilgi için [Recordset: Sorting Records (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>CRecordset::Taşı

Geçerli kayıt işaretçisini kayıt kümesi içinde ileri veya geri taşır.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Parametreler

*Nrows*<br/>
İleri veya geri hareket etmek için satır sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru ilerler. Negatif değerler başa doğru geriye doğru hareket ettirin.

*wFetchType*<br/>
Getirecek satır kümesini `Move` belirler. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

*NRows*için 0 değerini geçerseniz, `Move` geçerli kaydı yeniler; `Move` herhangi bir `AddNew` akımı `Edit` veya modu sona erdirecek ve `AddNew` `Edit` geçerli kaydın değerini önce veya çağrıldı geri yüklenir.

> [!NOTE]
> Bir kayıt kümesinde hareket ettiğinizde, silinen kayıtları atlayamazsınız. Bkz. [CRecordset::Daha](#isdeleted) fazla bilgi için Silindi. Opsiyon kümesiyle `CRecordset` `skipDeletedRecords` a'yı `Move` açtığınızda, *nRows* parametresi 0 olup olmadığını ileri sürer. Bu davranış, aynı verileri kullanarak diğer istemci uygulamaları tarafından silinen satırların yenilenmesini engeller. Bir açıklama için [Açık'taki](#open) `skipDeletedRecords` *dwOption* parametresini görün.

`Move`kayıt kümesini satır kümelerine göre yeniden konumlandırın. *nRows* ve *wFetchType*için değerlere bağlı olarak, `Move` uygun rowset getirir ve sonra geçerli kayıt bu rowset ilk kayıt yapar. Toplu satır alma uygulamadıysanız, satır kümesi boyutu her zaman 1'dir. Bir rowset alırken, `Move` doğrudan alma kaynaklanan hataları işlemek için [CheckRowsetError](#checkrowseterror) üye işlevini çağırır.

Geçtiğiniz değerlere bağlı `Move` olarak, diğer `CRecordset` üye işlevlere eşdeğerdir. Özellikle, *wFetchType* değeri daha sezgisel ve genellikle geçerli kaydı taşımak için tercih edilen yöntem bir üye işlev gösterebilir.

Aşağıdaki tabloda *wFetchType*için olası değerleri listeler `Move` , *wFetchType* ve *nRows*dayalı getirecek rowset, ve *wFetchType*karşılık gelen herhangi bir eşdeğer üye işlevi .

|wFetchType|Getirilen satır kümesi|Eşdeğer üye işlevi|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (varsayılan değer)|Geçerli rowset'teki ilk satırdan *nRows row(lar)ı* başlatan satır kümesi.||
|SQL_FETCH_NEXT|Bir sonraki satır kümesi; *nRows* yoksayılır.|[Movenext](#movenext)|
|SQL_FETCH_PRIOR|Önceki satır kümesi; *nRows* yoksayılır.|[Moveprev](#moveprev)|
|SQL_FETCH_FIRST|Kayıt kümesindeki ilk satır kümesi; *nRows* yoksayılır.|[Movefirst](#movefirst)|
|SQL_FETCH_LAST|Kayıt kümesindeki son tam satır kümesi; *nRows* yoksayılır.|[Movelast](#movelast)|
|SQL_FETCH_ABSOLUTE|*nRows* > 0, rowset başlangıç *nRows* row(lar) kayıt kümesinin başından itibaren. *nRows* < 0, rowset başlangıç *nRows* row(lar) kayıt kümesinin sonundan. *nRows* = 0 ise, dosyabaşlangıcı (BOF) koşulu döndürülür.|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Yer imi değeri *nRows*karşılık gelen satır kümesi başlayan.|[Setbookmark](#setbookmark)|

> [!NOTE]
> Yalnızca ileri kayıt kümeleri için, `Move` yalnızca *wFetchType*için SQL_FETCH_NEXT değeri ile geçerlidir.

> [!CAUTION]
> Kayıt `Move` kümesinde kayıt yoksa arama bir özel durum oluşturur. Kayıt kümesinde herhangi bir kayıt olup olmadığını belirlemek için [IsBOF](#isbof) ve [IsEOF'u](#iseof)arayın.

> [!NOTE]
> Kayıt kümesinin başlangıcını veya sonunu geçtiyseniz`IsBOF` (veya `IsEOF` sıfırsız döndü) bir `Move` işlevi `CDBException`çağırmak büyük olasılıkla bir . Örneğin, `IsEOF` sıfırsız döndürür ve `IsBOF` `MoveNext` dönmezse, bir `MovePrev` özel durum atar, ancak atmaz.

> [!NOTE]
> Geçerli kayıt `Move` güncelleştirilirken veya eklenirken ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın. İlgili bilgiler için Windows SDK'daki `SQLExtendedFetch` ODBC API işlevine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>CRecordset::MoveFirst

İlk satırdaki ilk kaydı geçerli kaydı yapar.

```cpp
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır alma nın uygulanıp uygulanmadığına bakılmaksızın, bu her zaman kayıt kümesindeki ilk kayıt olacaktır.

Kayıt kümesini açtıktan hemen sonra aramanız `MoveFirst` gerekmez. O zaman, ilk kayıt (varsa) otomatik olarak geçerli kayıttır.

> [!NOTE]
> Bu üye işlev yalnızca ileri kayıt kümeleri için geçerli değildir.

> [!NOTE]
> Bir kayıt kümesinde hareket ettiğinizde, silinen kayıtları atlayamazsınız. Ayrıntılar için [Silinmiş](#isdeleted) üye işlevine bakın.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Kayıt kümesinde herhangi bir kayıt `IsBOF` olup `IsEOF`olmadığını belirlemek için, arama ve .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

## <a name="crecordsetmovelast"></a><a name="movelast"></a>CRecordset::MoveLast

Son tam satır daki ilk kaydı geçerli kaydı yapar.

```cpp
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulamadıysanız, kayıt setinizin satır kümesi boyutu `MoveLast` 1'dir, bu nedenle kayıt kümesindeki son kayda geçer.

> [!NOTE]
> Bu üye işlev yalnızca ileri kayıt kümeleri için geçerli değildir.

> [!NOTE]
> Bir kayıt kümesinde hareket ettiğinizde, silinen kayıtları atlayamazsınız. Ayrıntılar için [Silinmiş](#isdeleted) üye işlevine bakın.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Kayıt kümesinde herhangi bir kayıt `IsBOF` olup `IsEOF`olmadığını belirlemek için, arama ve .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

## <a name="crecordsetmovenext"></a><a name="movenext"></a>CRecordset::MoveNext

Bir sonraki satırdaki ilk kaydı geçerli kaydı ayarlar.

```cpp
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uygulamadıysanız, kayıt setinizin satır kümesi boyutu `MoveNext` 1'dir, bu nedenle bir sonraki kayda geçer.

> [!NOTE]
> Bir kayıt kümesinde hareket ettiğinizde, silinen kayıtları atlayamazsınız. Ayrıntılar için [Silinmiş](#isdeleted) üye işlevine bakın.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Kayıt kümesinde herhangi bir kayıt `IsBOF` olup `IsEOF`olmadığını belirlemek için, arama ve .

> [!NOTE]
> Ayrıca aramadan `MoveNext`önce `IsEOF` aramanız önerilir. Örneğin, kayıt kümesinin sonundan geçtiyseniz, `IsEOF` sıfırsız döndürecektir; sonraki bir `MoveNext` çağrı bir özel durum atmak istiyorsunuz.

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>CRecordset::MovePrev

Önceki satır kümesindeki ilk kaydı geçerli kaydı yapar.

```cpp
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uygulamadıysanız, kayıt setinizin satır kümesi boyutu `MovePrev` 1'dir, bu nedenle önceki kayda geçer.

> [!NOTE]
> Bu üye işlev yalnızca ileri kayıt kümeleri için geçerli değildir.

> [!NOTE]
> Bir kayıt kümesinde hareket ettiğinizde, silinen kayıtları atlayamazsınız. Ayrıntılar için [Silinmiş](#isdeleted) üye işlevine bakın.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Kayıt kümesinde herhangi bir kayıt `IsBOF` olup `IsEOF`olmadığını belirlemek için, arama ve .

> [!NOTE]
> Ayrıca aramadan `MovePrev`önce `IsBOF` aramanız önerilir. Örneğin, kayıt kümesinin başlangıcından önce kaydırıldıysanız, `IsBOF` sıfırsız döndürecektir; sonraki bir `MovePrev` çağrı bir özel durum atmak istiyorsunuz.

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

  [IsBOF](#isbof)örneğine bakın.

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>CRecordset::OnSetOptions

Belirtilen ODBC deyimi için seçenekleri ayarlamak (seçimde kullanılır) için çağrılır.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*Hstmt*<br/>
Seçenekleri ayarlanacak Olan ODBC deyiminin HSTMT.

### <a name="remarks"></a>Açıklamalar

Belirtilen `OnSetOptions` ODBC deyimi için seçenekleri ayarlamak için çağrı (seçimde kullanılır). Çerçeve, kayıt kümesi için ilk seçenekleri ayarlamak için bu üye işlevi çağırır. `OnSetOptions`değiştirilebilir imleçler ve imleç eşzamanlılığı için veri kaynağının desteğini belirler ve kayıt kümesinin seçeneklerini buna göre ayarlar. (Oysa `OnSetOptions` seçim işlemleri için `OnSetUpdateOptions` kullanılır, güncelleştirme işlemleri için kullanılır.)

Sürücüye `OnSetOptions` veya veri kaynağına özgü seçenekleri ayarlamak için geçersiz kılın. Örneğin, veri kaynağınız özel erişim için açılmayı `OnSetOptions` destekliyorsa, bu yeteneklerden yararlanmak için geçersiz kılabilirsiniz.

İmleçler hakkında daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md)makalesine bakın.

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions

Belirtilen ODBC deyimi için seçenekleri ayarlamak için çağrılır (güncelleştirmede kullanılır).

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*Hstmt*<br/>
Seçenekleri ayarlanacak Olan ODBC deyiminin HSTMT.

### <a name="remarks"></a>Açıklamalar

Belirtilen `OnSetUpdateOptions` ODBC deyimi için seçenekleri ayarlamak için çağrı (güncelleştirmede kullanılır). Çerçeve, kayıtları bir kayıt kümesinde güncelleştirmek için bir HSTMT oluşturduktan sonra bu üye işlevi çağırır. (Oysa `OnSetOptions` seçim işlemleri için `OnSetUpdateOptions` kullanılır, güncelleştirme işlemleri için kullanılır.) `OnSetUpdateOptions` değiştirilebilir imleçler ve imleç eşzamanlılığı için veri kaynağının desteğini belirler ve kayıt kümesinin seçeneklerini buna göre ayarlar.

Bu `OnSetUpdateOptions` bildirim veritabanına erişmek için kullanılmadan önce bir ODBC deyiminin seçeneklerini ayarlamak için geçersiz kılma.

İmleçler hakkında daha fazla bilgi için [ODBC](../../data/odbc/odbc-basics.md)makalesine bakın.

## <a name="crecordsetopen"></a><a name="open"></a>CRecordset::Aç

Tabloyu alarak veya kayıt kümesinin temsil ettiği sorguyu gerçekleştirerek kayıt kümesini açar.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Parametreler

*nOpenType*<br/>
Varsayılan değeri kabul edin, AFX_DB_USE_DEFAULT_TYPE veya aşağıdaki `enum OpenType`değerlerden birini kullanın:

- `CRecordset::dynaset`Çift yönlü kaydırma ile bir kayıt kümesi. Kayıt kümesi açıldığında kayıtların üyeliği ve sırası belirlenir, ancak diğer kullanıcılar tarafından veri değerlerinde yapılan değişiklikler bir getirme işleminden sonra görülebilir. Dynasets, tuş kümesine dayalı kayıt kümeleri olarak da bilinir.

- `CRecordset::snapshot`Çift yönlü kaydırma ile statik bir kayıt kümesi. Kayıt kümesi açıldığında kayıtların üyelik ve siparişi belirlenir; kayıtlar getirildiğinde veri değerleri belirlenir. Kayıt kümesi kapatıp yeniden açılana kadar diğer kullanıcılar tarafından yapılan değişiklikler görünmez.

- `CRecordset::dynamic`Çift yönlü kaydırma ile bir kayıt kümesi. Diğer kullanıcılar tarafından üyelik, sipariş ve veri değerlerinde yapılan değişiklikler, bir getirme işleminden sonra görülebilir. Birçok ODBC sürücüsünün bu tür kayıt kümesini desteklemediğini unutmayın.

- `CRecordset::forwardOnly`Yalnızca ileri kaydırma ile salt okunur kayıt kümesi.

   Çünkü, `CRecordset`varsayılan değer `CRecordset::snapshot`. Varsayılan değer mekanizması, Visual C++ sihirbazlarının farklı varsayılan `CRecordset` değerlere `CDaoRecordset`sahip olan ODBC ve DAO ile etkileşim kurmasını sağlar.

Bu kayıt kümesi türleri hakkında daha fazla bilgi için [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)makalesine bakın. İlgili bilgiler için Windows SDK'daki "Engellenebilir ve Kaydırılabilir İmlercileri Kullanma" makalesine bakın.

> [!CAUTION]
> İstenen tür desteklenmezse, çerçeve bir özel durum oluşturur.

*Lpszsql*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- Null işaretçisi.

- Bir masanın adı.

- Bir SQL **SELECT** deyimi (isteğe bağlı olarak bir SQL **WHERE** veya **ORDER BY** yan tümcesi ile).

- Önceden tanımlanmış bir sorgunun (depolanan yordam) adını belirten bir **CALL** deyimi. Kıvırcık ayraç ve **CALL** anahtar kelimesi arasına boşluk eklememeye dikkat edin.

Bu dize hakkında daha fazla bilgi için, [Açıklamalar](#remarks) bölümünde sınıf sihirbazının rolünün tartışılması tablosuna ve tartışmasına bakın.

> [!NOTE]
> Sonuç setinizdeki sütunların sırası, [DoFieldExchange veya DoBulkFieldExchange](#dofieldexchange) işlev geçersiz kılmanızdaki [DoBulkFieldExchange](#dobulkfieldexchange) RFX veya Toplu RFX işlev çağrılarının sırasına uygun olmalıdır.

*Dwoptions*<br/>
Aşağıda listelenen değerlerin bir birleşimini belirtebilen bir bitmaskesi. Bunlardan bazıları birbirini dışlayan bir şey. Varsayılan değer **yok.**

- `CRecordset::none`Seçenek ayarlı değil. Bu parametre değeri, diğer tüm değerlerle birbirini dışlar. Varsayılan olarak, kayıt kümesi [Düzenle](#edit) veya [Sil](#delete) ile güncellenebilir ve [AddNew](#addnew)ile yeni kayıtlar eklemeye olanak tanır. Güncellenebilirlik, veri kaynağına ve belirttiğiniz *nOpenType* seçeneğine bağlıdır. Toplu eklemeler için optimizasyon kullanılamaz. Toplu satır alma uygulanmaz. Silinen kayıtlar kayıt kaydı gezintisi sırasında atlanmaz. Yer imleri kullanılamıyor. Otomatik kirli alan denetimi uygulanır.

- `CRecordset::appendOnly`İzin `Edit` verme `Delete` veya kayıt setinde. Sadece `AddNew` izin ver. Bu seçenek, `CRecordset::readOnly`'.

- `CRecordset::readOnly`Kayıt kümesini salt okunur olarak açın. Bu seçenek, `CRecordset::appendOnly`'.

- `CRecordset::optimizeBulkAdd`Aynı anda çok sayıda kayıt eklemeyi en iyi duruma getirmek için hazırlanmış bir SQL deyimi kullanın. Yalnızca kayıt kümesini güncelleştirmek için ODBC `SQLSetPos` API işlevini kullanmıyorsanız geçerlidir. İlk güncelleştirme, hangi alanların kirli olarak işaretlendiğini belirler. Bu seçenek, `CRecordset::useMultiRowFetch`'.

- `CRecordset::useMultiRowFetch`Tek bir getirme işleminde birden çok satırın alınmasına izin vermek için toplu satır alma uygulamasını uygulayın. Bu, performansı artırmak için tasarlanmış gelişmiş bir özelliktir; ancak, toplu kayıt alanı değişimi ClassWizard tarafından desteklenmez. Bu seçenek, `CRecordset::optimizeBulkAdd`'. Belirtirseniz, `CRecordset::useMultiRowFetch`seçeneğin `CRecordset::noDirtyFieldCheck` otomatik olarak açık olacağını unutmayın (çift arabelleğe alma kullanılamaz); yalnızca ileri kayıt kümelerinde `CRecordset::useExtendedFetch` seçenek otomatik olarak açılacaktır. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

- `CRecordset::skipDeletedRecords`Kayıt setinde gezinirken silinen tüm kayıtları atlayın. Bu, belirli göreli getirmelerde performansı yavaşlatır. Bu seçenek yalnızca ileri kayıt kümelerinde geçerli değildir. *NRows* parametresi 0 olarak ayarlanmış ve `CRecordset::skipDeletedRecords` seçenek kümesi `Move` ile [Taşı'yı](#move) çağırırsanız, bu tür bir karar ortaya atacaktır. Sürücü `CRecordset::skipDeletedRecords` *paketlemesine*benzer olduğunu unutmayın, bu da silinen satırların kayıt kümesinden kaldırıldığı anlamına gelir. Ancak, sürücünüz kayıtları paketlerse, yalnızca silersiniz bu kayıtları atlar; kayıt kümesi açıkken diğer kullanıcılar tarafından silinen kayıtları atlamaz. `CRecordset::skipDeletedRecords`diğer kullanıcılar tarafından silinen satırları atlar.

- `CRecordset::useBookmarks`Desteklenirse kayıt kümesinde yer imleri kullanabilir. Yer imleri veri alımLarını yavaşlatamaz, ancak veri gezintisi için performansı artırır. Yalnızca ileri kayıt kümelerinde geçerli değildir. Daha fazla bilgi için [Recordset: Bookmarks and Absolute Positions (ODBC) makalesine](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)bakın.

- `CRecordset::noDirtyFieldCheck`Otomatik kirli alan denetimini (çift arabelleğe alma) kapatın. Bu performansı artıracaktır; ancak, alanları `SetFieldDirty` ve `SetFieldNull` üye işlevleri arayarak alanları el ile kirli olarak işaretlemeniz gerekir. Sınıfta `CRecordset` çift arabelleğe alma nın sınıftaki `CDaoRecordset`çift arabelleğe alma gibi olduğunu unutmayın. Ancak, `CRecordset`' içinde, tek tek alanlarda çift arabelleğe alma etkinleştiremezsiniz; tüm alanlar için etkinleştirin veya tüm alanlar için devre dışı. Seçeneği `CRecordset::useMultiRowFetch`belirtirseniz, otomatik olarak `CRecordset::noDirtyFieldCheck` açık olacağını unutmayın; ancak `SetFieldDirty` toplu `SetFieldNull` satır alma uygulayan kayıt kümelerinde kullanılamaz.

- `CRecordset::executeDirect`Hazırlanmış bir SQL deyimi kullanmayın. Geliştirilmiş performans için, üye `Requery` işlev asla çağrılmayacaksa bu seçeneği belirtin.

- `CRecordset::useExtendedFetch`Yerine `SQLExtendedFetch` `SQLFetch`uygulayın. Bu, yalnızca ileri kayıt kümelerinde toplu satır getirme uygulamak için tasarlanmıştır. Seçeneği `CRecordset::useMultiRowFetch` yalnızca ileri kayıt setinde belirtirseniz, `CRecordset::useExtendedFetch` otomatik olarak açılacaktır.

- `CRecordset::userAllocMultiRowBuffers`Kullanıcı, veriler için depolama arabellekleri tahsis edecektir. Kendi depolama alanınızı `CRecordset::useMultiRowFetch` ayırmak istiyorsanız bu seçeneği birlikte kullanın; aksi takdirde, çerçeve otomatik olarak gerekli depolama tahsis edecektir. Daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC) makalesine](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)bakın. `CRecordset::userAllocMultiRowBuffers` Belirtmeden belirtmenin başarısız `CRecordset::useMultiRowFetch` bir iddiayla sonuçlanacaktır.

### <a name="return-value"></a>Dönüş Değeri

Nesne başarıyla `CRecordset` açılmışsa sıfırsız; aksi takdirde 0 [cdatabase::Open](../../mfc/reference/cdatabase-class.md#open) (çağrıldıysa) 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevi çağırmanız gerekir. Aramadan `Open`önce, kayıt kümesi nesnesini oluşturmanız gerekir.

Bu kayıt kümesinin veri kaynağına bağlantısı, 'yi aramadan `Open`önce kayıt kümesini nasıl oluşturabileceğinize bağlıdır. Bir [CDatabase](../../mfc/reference/cdatabase-class.md) nesnesini veri kaynağına bağlı olmayan kaydedici yapıcıya geçirirseniz, bu üye işlev veritabanı nesnesini açmaya çalışmak için [GetDefaultConnect'i](#getdefaultconnect) kullanır. NULL'u kaydedici oluşturucuya geçirirseniz, oluşturucu `CDatabase` sizin için bir `Open` nesne inşa eder ve veritabanı nesnesini bağlamaya çalışır. Kayıt kümesini ve bu farklı koşullar altındaki bağlantıyı kapatma yla ilgili ayrıntılar için [Bkz.](#close)

> [!NOTE]
> Bir `CRecordset` nesne üzerinden bir veri kaynağına erişim her zaman paylaşılır. `CDaoRecordset` Sınıfın aksine, özel erişime sahip bir veri kaynağı açmak için bir `CRecordset` nesne kullanamazsınız.

Genellikle SQL `Open` **SELECT** deyimi olan bir sorguyu aradiğinizde, aşağıdaki tabloda gösterilen ölçütlere göre kayıtları seçer.

|lpszSQL parametresinin değeri|Seçilen kayıtlar tarafından belirlenir|Örnek|
|------------------------------------|----------------------------------------|-------------|
|NULL|Dize tarafından `GetDefaultSQL`döndürülen.||
|SQL tablo adı|Tablo listesinin tüm sütunları içinde `DoFieldExchange` veya `DoBulkFieldExchange`.|`"Customer"`|
|Önceden tanımlanmış sorgu (depolanmış yordam) adı|Sorgunun döndürülmek üzere tanımladığı sütunlar.|`"{call OverDueAccts}"`|
|**SELECT** sütun listesi **FROM** tablo listesi|Belirtilen tablo(lar)'dan belirtilen sütunlar.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> SQL dizenize fazladan boşluk eklememeye dikkat edin. Örneğin, kıvırcık ayraç ve **CALL** anahtar kelimesi arasına beyaz boşluk eklerseniz, MFC SQL dizesini tablo adı olarak yanlış yorumlar ve bir ÖZEL DURUM ATILANDIRILACAK **SELECT** deyimine dahil edecektir. Benzer şekilde, önceden tanımlanmış sorgunuz bir çıktı parametresi kullanıyorsa, kıvırcık ayraç ve '' simgesi arasına boşluk eklemeyin. Son olarak, **call** deyiminde kıvırcık ayraç önce veya **SELECT** deyiminde **SELECT** anahtar kelime önce beyaz boşluk eklememelisiniz.

Her zamanki prosedür NULL `Open`geçmektir; Bu durumda, `Open` [GetDefaultSQL](#getdefaultsql)çağırır. Türetilmiş `CRecordset` bir sınıf `GetDefaultSQL` kullanıyorsanız, ClassWizard'da belirttiğiniz tablo adını(lar) verir. Bunun yerine `lpszSQL` parametredeki diğer bilgileri belirtebilirsiniz.

Ne geçerseniz `Open` geçerseniz geçirin, sorgu için son bir SQL dizesi (string'te SQL **WHERE** ve **ORDER BY** yan tümceleri geçmiş `lpszSQL` dizeye eklenebilir) ve sonra sorguyu yürütür. GetSQL'i aradıktan `Open`sonra [getSQL'i](#getsql) arayarak yapılandırılan dizeyi inceleyebilirsiniz. Kayıt kümesinin bir SQL deyimini nasıl oluşturup kayıtları seçtiği hakkında ek ayrıntılar için [Recordset: Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)makalesine bakın.

Kayıt kümesi sınıfınızın alan veri üyeleri, seçilen verilerin sütunlarına bağlıdır. Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Filtre veya sıralama gibi kayıt kümesi için seçenekler ayarlamak istiyorsanız, kayıt kümesi nesnesini oluşturmadan `Open`sonra ancak aramadan önce bunları belirtin. Kayıt kümesi zaten açıldıktan sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız, [Requery'yi](#requery)arayın.

Ek örnekler de dahil olmak üzere daha fazla bilgi için [Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)ve [Recordset: Oluşturma ve Kapanış Kayıt Kümeleri (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)makalelerini görün.

### <a name="example"></a>Örnek

Aşağıdaki kod örnekleri, çağrının `Open` farklı biçimlerini gösterir.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>CRecordset::RefreshRowset

Geçerli satır kümesindeki bir satırın verilerini ve durumunu güncelleştirir.

```cpp
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer, sıfırdan satır kümesinin boyutuna kadar değişebilir.

*wLockType*<br/>
Yenilendikten sonra satırın nasıl kilitlenilen inanıldığını gösteren bir değer. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

*WRow*için sıfır değerini geçerseniz, satır kümesindeki her satır yenilenir.

Kullanmak `RefreshRowset`için, `CRecordset::useMulitRowFetch` [Açık](#open) üye işlevinde seçeneği belirterek toplu satır alma uygulamış olması gerekir.

`RefreshRowset`ODBC API işlevini `SQLSetPos`çağırır. *wLockType* parametresi, yürütüldükten sonra `SQLSetPos` satırın kilit durumunu belirtir. Aşağıdaki *tabloda wLockType*için olası değerleri açıklanır.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı, satırın daha önce `RefreshRowset` çağrıldığı gibi kilitlenmiş veya kilitsiz durumda olmasını sağlar.|
|SQL_LOCK_EXCLUSIVE|Sürücü veya veri kaynağı satırı yalnızca kilitler. Tüm veri kaynakları bu tür bir kilidi desteklemez.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı satırın kilidini açar. Tüm veri kaynakları bu tür bir kilidi desteklemez.|

Hakkında daha `SQLSetPos`fazla bilgi için Windows SDK'ya bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetrequery"></a><a name="requery"></a>CRecordset::Yeniden sorgu

Bir kayıt kümesini yeniden çalışır (yeniler).

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi başarıyla yeniden oluşturulmuşsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesinin sizin veya diğer kullanıcıların veri kaynağına yaptığı eklemeleri ve silmeleri yansıtması için, 'yi arayarak `Requery`kayıt kümesini yeniden oluşturmanız gerekir. Kayıt kümesi bir dinamitse, sizin veya diğer kullanıcıların varolan kayıtlarına (eklemeler değil) yaptığınız güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi anlık görüntüyse, diğer `Requery` kullanıcıların düzenlemelerini ve eklemeleri ve silmeleri yansıtmak için aramanız gerekir.

Bir dinamit veya anlık `Requery` görüntü için, yeni bir filtre veya sıralama veya yeni parametre değerleri kullanarak kayıt kümesini yeniden oluşturmak istediğinizde arayın. Yeni filtreyi ayarlayın veya özelliği ni `m_strFilter` aramadan `m_strSort` `Requery`önce yeni değerler atayarak sıralayın. Aramadan önce parametre veri üyelerine yeni `Requery`değerler atayarak yeni parametreler ayarlayın. Filtre ve sıralama dizeleri değişmemişse, performansı artıran sorguyu yeniden kullanabilirsiniz.

Kayıt kümesini yeniden oluşturma girişimi başarısız olursa, kayıt kümesi kapatılır. Aramadan `Requery`önce, üye işlevi arayarak kayıt kümesinin `CanRestart` yeniden sorgulanıp yeniden sorgulanamayacağını belirleyebilirsiniz. `CanRestart`başarılı `Requery` olacağını garanti etmez.

> [!CAUTION]
> Yalnızca `Requery` [Aç'ı](#open)aradıktan sonra arayın.

### <a name="example"></a>Örnek

Bu örnek, farklı bir sıralama sırası uygulamak için bir kayıt kümesini yeniden birebir yeniden ayarlar.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CRecordset::SetAbsolutePosition

Kayıt kümesini belirtilen kayıt numarasına karşılık gelen kayıt kümesine konumlandırın.

```cpp
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Parametreler

*Nrows*<br/>
Kayıt kümesindeki geçerli kayıt için tek tabanlı ordinal konum.

### <a name="remarks"></a>Açıklamalar

`SetAbsolutePosition`geçerli kayıt işaretçisini bu ordinal konuma göre hareket ettirir.

> [!NOTE]
> Bu üye işlev yalnızca ileri kayıt kümelerinde geçerli değildir.

ODBC kayıt kümeleri için, 1'in mutlak konum ayarı, kayıt kümesindeki ilk kayda işaret eder; 0 ayarı, dosyanın başlangıcı (BOF) konumuna başvurur.

Negatif değerleri `SetAbsolutePosition`de . Bu durumda kayıt setinin konumu kayıt setinin sonundan itibaren değerlendirilir. Örneğin, `SetAbsolutePosition( -1 )` geçerli kayıt işaretçisini kayıt kümesindeki son kayda taşır.

> [!NOTE]
> Mutlak pozisyon, vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Önceki kayıtlar silindiğinde kaydın konumu değiştiğinden, yer imleri hala belirli bir konumu tutmanın ve geri döndürmenin önerilen yoludur. Buna ek olarak, bir **ORDER BY** yan tümcesi kullanılarak bir SQL deyimi yle oluşturulmadığı sürece kayıt kümesi yeniden oluşturulduğunda belirli bir kaydın aynı mutlak konuma sahip olacağından emin olamazsınız.

Kayıt kümesi gezintisi ve yer imleri hakkında daha fazla bilgi için [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [Recordset: Yer Imleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md)makalelerine bakın.

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>CRecordset::SetBookmark

Kaydedilen kayıtları belirtilen yer işaretini içeren kayıt tasnmı.

```cpp
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Belirli bir kayıt için yer imi değerini içeren [CDBVariant](../../mfc/reference/cdbvariant-class.md) nesnesine başvuru.

### <a name="remarks"></a>Açıklamalar

Kayıt setinde yer imlerinin desteklenip desteklenmedigerekden belirlemek için [CanBookmark'ı](#canbookmark)arayın. Yer imlerini desteklenirse kullanılabilir hale getirmek `CRecordset::useBookmarks` için, seçeneği [Açık](#open) üye işlevinin *dwOptions* parametresinde ayarlamanız gerekir.

> [!NOTE]
> Yer imleri desteklenmezse veya kullanılamıyorsa, arama `SetBookmark` bir özel durum atılmasına neden olur. Yer imleri yalnızca ileri kayıt kümelerinde desteklenmez.

Geçerli kaydın yer işaretini almak için önce, yer imi değerini bir `CDBVariant` nesneye kaydeden [GetBookmark'ı](#getbookmark)arayın. Daha sonra, kaydedilen yer imi değerini kullanarak arayarak `SetBookmark` bu kayda dönebilirsiniz.

> [!NOTE]
> Belirli kayıt kümesi işlemlerden sonra, aramadan `SetBookmark`önce yer imi kalıcılığını kontrol etmelisiniz. Örneğin, yer imi ile `GetBookmark` bir yer `Requery`imi alır ve ardından ararsanız, yer imi artık geçerli olmayabilir. CDatabase'i arayın::Güvenli bir şekilde arayıp arayamayacağınızı kontrol etmek için [GetBookmarkPersistence'](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) ı arayın. `SetBookmark`

Yer imleri ve kayıt kümesi gezintisi hakkında daha fazla bilgi için [Recordset: Bookmarks and Absolute Positions (ODBC) ve](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)makalelerine bakın.

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>CRecordset::SetFieldDirty

Kayıt kümesinin alan veri üyesini değiştirilmiş veya değişmemiş olarak işaretler.

```cpp
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Kayıt kümesinde veya NULL'da bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL veritabanı terminolojisinde Null ile aynı değildir, yani "değeri yoktur.")

*bKirli*<br/>
Alan veri üyesi "kirli" (değiştirildi) olarak işaretlenecekse DOĞRU. Aksi takdirde alan veri üyesi "temiz" (değişmeden) olarak işaretlenecekse FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değişmemiş olarak işaretleme, alanın güncelleştirilmemesini ve daha az SQL trafiğiyle sonuçlanmasını sağlar.

> [!NOTE]
> Bu üye işlev, toplu satır alma kullanan kayıt kümelerinde geçerli değildir. Toplu satır alma uyguladıysanız, başarısız `SetFieldDirty` bir iddiayla sonuçlanır. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Çerçeve işaretleri, kayıt alanı değişimi (RFX) mekanizması tarafından veri kaynağına yazılmasını sağlamak için alan veri üyelerini değiştirdi. Bir alanın değerini değiştirmek genellikle alanı otomatik olarak kirli ayarlar, bu `SetFieldDirty` nedenle nadiren kendinizi aramanız gerekir, ancak bazen alan veri üyesinin değeri ne olursa olsun sütunların açıkça güncelleştirildiğinden veya eklenmediğinden emin olmak isteyebilirsiniz.

> [!CAUTION]
> Bu üye işlevini yalnızca [Edit](#edit) veya [AddNew'ı](#addnew)aradıktan sonra arayın.

İşlevin ilk bağımsız değişkeni için NULL'un kullanılması `param` işlevi alanlara değil, yalnızca alanlara `outputColumn` uygular. Örneğin, arama

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanları NULL olarak ayarlar; `param` alanlar etkilenmez.

`param` Alanlarda çalışmak için, üzerinde çalışmak istediğiniz kişinin `param` gerçek adresini sağlamanız gerekir:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, tüm `param` alanları, alanlar ile `outputColumn` yapabildiğiniz gibi NULL olarak ayarlayamayacağınız anlamına gelir.

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>CRecordset::SetFieldNull

Kayıt kümesinin alan veri üyesini Null (özellikle değeri olmayan) veya Null olmayan olarak işaretler.

```cpp
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Kayıt kümesinde veya NULL'da bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL veritabanı terminolojisinde Null ile aynı değildir, yani "değeri yoktur.")

*bNull*<br/>
Alan veri üyesi hiçbir değeri (Null) olarak işaretlenecekise Nonzero. Aksi takdirde alan veri üyesi null olmayan olarak işaretlenecekse 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlanır ve "kirli" (değiştirildi) olarak işaretlenir. Bir veri kaynağından bir kayıt aldığınızda, sütunlarının zaten değerleri vardır veya Null'dadır.

> [!NOTE]
> Toplu satır alma kullanan kayıt kümelerinde bu üye işlevi aramayın. Toplu satır alma uyguladıysanız, arama `SetFieldNull` başarısız bir iddiayla sonuçlanır. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Geçerli kaydın bir alanını özellikle bir değere sahip değil `SetFieldNull` olarak belirtmek istiyorsanız, null olarak işaretlemek için TRUE olarak ayarlanmış *bNull'u* arayın. Bir alan daha önce Null olarak işaretlenmişse ve şimdi ona bir değer vermek istiyorsanız, yeni değerini ayarlamanız yeterlidir. Null bayrağını `SetFieldNull`' la kaldırmanız gerekmez. Alanın Null olup olmadığını belirlemek için. `IsFieldNullable`

> [!CAUTION]
> Bu üye işlevini yalnızca [Edit](#edit) veya [AddNew'ı](#addnew)aradıktan sonra arayın.

İşlevin ilk bağımsız değişkeni için NULL'un kullanılması `param` işlevi alanlara değil, yalnızca alanlara `outputColumn` uygular. Örneğin, arama

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca `outputColumn` alanları NULL olarak ayarlar; `param` alanlar etkilenmez.

`param` Alanlarda çalışmak için, üzerinde çalışmak istediğiniz kişinin `param` gerçek adresini sağlamanız gerekir:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Bu, tüm `param` alanları, alanlar ile `outputColumn` yapabildiğiniz gibi NULL olarak ayarlayamayacağınız anlamına gelir.

> [!NOTE]
> Parametreleri Null'a ayarlarken, kayıt kümesi açılmadan önce yapılan `SetFieldNull` bir arama bir iddiayla sonuçlanır. Bu durumda, [SetParamNull'u](#setparamnull)arayın.

`SetFieldNull`[DoFieldExchange](#dofieldexchange)üzerinden uygulanmaktadır.

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>CRecordset::SetLockingMode

Kilitleme modunu "iyimser" kilitleme (varsayılan) veya "kötümser" kilitleme olarak ayarlar. Güncelleştirmeler için kayıtların nasıl kilitlendirilebildiğini belirler.

```cpp
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Parametreler

*nMode*<br/>
Aşağıdaki değerlerden birini `enum LockMode`içerir:

- `optimistic`İyimser kilitleme, yalnızca çağrı sırasında `Update`güncelleştirilen kaydı kilitler.

- `pessimistic`Kötümser kilitleme, çağrılır `Edit` çağrılmaz kaydı kilitler `Update` ve arama tamamlanana veya yeni bir kayda taşınana kadar kaydı kilitli tutar.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin güncelleştirmeler için kullandığı iki kayıt kilitleme stratejiden hangisini belirtmeniz gerekiyorsa bu üye işlevi arayın. Varsayılan olarak, bir kayıt kümesinin `optimistic`kilitleme modu. Bunu daha dikkatli `pessimistic` bir kilitleme stratejisine çevirebilirsiniz. Kayıt `SetLockingMode` kümesi nesnesini oluşturup açtıktan sonra `Edit`ancak aramadan önce arayın.

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>CRecordset::SetParamNull

Bir parametreyi Null (özellikle değeri olmayan) veya Null olmayan olarak işaretler.

```cpp
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Parametrenin sıfır tabanlı dizin.

*bNull*<br/>
TRUE (varsayılan değer) ise, parametre Null olarak işaretlenir. Aksi takdirde, parametre Null olmayan olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

[SetFieldNull](#setfieldnull)aksine, kayıt `SetParamNull` kümesini açmadan önce arayabilirsiniz.

`SetParamNull`genellikle önceden tanımlanmış sorgularla (depolanan yordamlar) kullanılır.

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition

İmleci geçerli satır kümesi içinde bir satıra taşır.

```cpp
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Geçerli satır kümesindeki bir satırın tek tabanlı konumu. Bu değer, satır kümesinin boyutu 1 arasında değişebilir.

*wLockType*<br/>
Yenilenen satırın nasıl kilitlendiğini gösteren değer. Ayrıntılar için Açıklamalar'a bakın.

### <a name="remarks"></a>Açıklamalar

Toplu satır alma uygularken, kayıtlar getirilen satır kümesindeki ilk kaydın geçerli kayıt olduğu satır kümeleri tarafından alınır. Satır kümesi içinde başka bir kayıt yapmak için `SetRowsetCursorPosition`geçerli kaydı arayın. Örneğin, kayıt setinizin herhangi bir kaydından verileri dinamik olarak almak için `SetRowsetCursorPosition` [GetFieldValue](#getfieldvalue) üye işlevi ile birleştirebilirsiniz.

Kullanmak `SetRowsetCursorPosition`için, [Açık](#open) üye işlevinde *dwOptions* `CRecordset::useMultiRowFetch` parametre seçeneğini belirterek toplu satır alma uygulamış olması gerekir.

`SetRowsetCursorPosition`ODBC API işlevini `SQLSetPos`çağırır. *wLockType* parametresi, yürütüldükten sonra `SQLSetPos` satırın kilit durumunu belirtir. Aşağıdaki *tabloda wLockType*için olası değerleri açıklanır.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı, satırın daha önce `SetRowsetCursorPosition` çağrıldığı gibi kilitlenmiş veya kilitsiz durumda olmasını sağlar.|
|SQL_LOCK_EXCLUSIVE|Sürücü veya veri kaynağı satırı yalnızca kilitler. Tüm veri kaynakları bu tür bir kilidi desteklemez.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı satırın kilidini açar. Tüm veri kaynakları bu tür bir kilidi desteklemez.|

Hakkında daha `SQLSetPos`fazla bilgi için Windows SDK'ya bakın. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>CRecordset::SetRowsetSize

Bir getirme sırasında almak istediğiniz kayıt sayısını belirtir.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Parametreler

*dwNewRowsetSize*<br/>
Belirli bir getirme sırasında alınacak satır sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlevi, toplu satır alma kullanırken tek bir getirme sırasında almak istediğiniz satır kaç belirtir. Toplu satır alma uygulamak için, `CRecordset::useMultiRowFetch` [seçeneği Open](#open) üye işlevinin *dwOptions* parametresinde ayarlamanız gerekir.

> [!NOTE]
> Toplu `SetRowsetSize` satır alma uygulamadan arama başarısız bir iddia neden olur.

Başlangıçta `SetRowsetSize` recordset için rowset boyutunu ayarlamak için aramadan önce arayın. `Open` Toplu satır alma uygularken varsayılan satır kümesi boyutu 25'tir.

> [!NOTE]
> Ararken `SetRowsetSize`dikkatli olun. Veriler için depolama alanını el ile ayırıyorsanız `CRecordset::userAllocMultiRowBuffers` (dwOptions `Open`parametreseçeneğinde belirtildiği gibi), bu depolama arabelleklerini aradıktan `SetRowsetSize`sonra yeniden tahsis etmeniz gerekip gerekmediğini, ancak imleç gezintisi işlemini gerçekleştirmeden önce kontrol etmelisiniz.

Satır kümesi boyutu için geçerli ayarı elde etmek için [GetRowsetSize'ı](#getrowsetsize)arayın.

Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

## <a name="crecordsetupdate"></a><a name="update"></a>CRecordset::Güncelleme

Yeni veya `AddNew` `Edit` düzenlenen verileri veri kaynağına kaydederek bir işlemi veya işlemi tamamlar.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt başarıyla güncelleştirildiyse sıfırsız; aksi takdirde sütun lar değişmediyse 0. Hiçbir kayıt güncelleştirildiyse veya birden fazla kayıt güncelleştirildiyse, bir özel durum atılır. Veri kaynağındaki başka bir hata için de bir özel durum atılır.

### <a name="remarks"></a>Açıklamalar

[AddNew](#addnew) veya [Edit](#edit) üye işlevini aramadan sonra bu üye işlevini arayın. Bu çağrının `AddNew` veya `Edit` işlemi tamamlamak için gerekli olması gerekir.

> [!NOTE]
> Toplu satır alma uyguladıysanız, 'yi `Update`arayamazsınız. Bu başarısız bir iddia neden olur. Sınıf, `CRecordset` toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC API işlevini `SQLSetPos`kullanarak kendi işlevlerinizi yazabilirsiniz. Toplu satır alma hakkında daha fazla bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

Her `AddNew` `Edit` ikisi de ve eklenen veya düzenlenen verilerin veri kaynağına kaydedilmesi için yerleştirildiği bir düzenleme arabelleği hazırlayın. `Update`verileri kaydeder. Yalnızca değiştirilme olarak işaretlenmiş veya algılanan alanlar güncelleştirilir.

Veri kaynağı hareketleri destekliyorsa, `Update` aramayı (ve `AddNew` karşılık `Edit` gelen veya aramasını) bir hareketin parçası yapabilirsiniz. İşlemler hakkında daha fazla bilgi için [Hareket (ODBC)](../../data/odbc/transaction-odbc.md)makalesine bakın.

> [!CAUTION]
> Eğer ilk `Update` ya `AddNew` da `Edit`aramadan ararsanız, `Update` bir `CDBException`atar . Bir `AddNew` `Move` işlemi `Edit`aramadan önce `Update` veya kayıt kümesini veya veri kaynağı bağlantısını kapatmadan önce aramanız gerekir. Aksi takdirde, değişiklikleriniz bildirim yapılmadan kaybolur.

İşlem `Update` hataları yla ilgili ayrıntılar için [Recordset: How Recordsets Update Records (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

Makaleye Bakın [Hareket: Kayıt Kümesinde (ODBC) İşlem Gerçekleştirme.](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView Sınıfı](../../mfc/reference/crecordview-class.md)
