---
title: CRecordset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d6e1fb04de4097a2cdf1dd51dc12265bef8d6c0b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423136"
---
# <a name="crecordset-class"></a>CRecordset sınıfı

Bir veri kaynağından seçilen kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRecordset::CRecordset](#crecordset)|Oluşturur bir `CRecordset` nesne. Bunu çağıran bir oluşturucu, türetilmiş sınıf sağlamanız gerekir.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|Yeni bir kayıt eklemek için hazırlar. Çağrı `Update` eklenmesi tamamlanması.|
|[CRecordset::CanAppend](#canappend)|Yeni kayıtlar kayıt kümesine eklenebilir, sıfır döndürür `AddNew` üye işlevi.|
|[CRecordset::CanBookmark](#canbookmark)|Kayıt kümesi yer işaretleri destekliyorsa, sıfır döndürür.|
|[CRecordset::Cancel](#cancel)|Zaman uyumsuz bir işlem veya ikinci bir iş parçacığı bir işlem iptal eder.|
|[CRecordset::CancelUpdate](#cancelupdate)|Beklemedeki Güncelleştirmeleri nedeniyle iptal bir `AddNew` veya `Edit` işlemi.|
|[CRecordset::CanRestart](#canrestart)|Döndürür gösterimiyse `Requery` kümesinin sorguyu yeniden çalıştırmayı çağrılabilir.|
|[CRecordset::CanScroll](#canscroll)|Kayıtlarda gezinmek, sıfır döndürür.|
|[CRecordset::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa, sıfır döndürür.|
|[CRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilebilir, sıfır döndürür (ekleyebilir, güncelleştirme veya kayıtlarını sil).|
|[CRecordset::CheckRowsetError](#checkrowseterror)|Kaydı alma sırasında oluşturulan hataları işlemek için çağrılır.|
|[CRecordset::Close](#close)|Kayıt kümesi ve onunla ilişkili ODBC HSTMT kapatır.|
|[CRecordset::Delete](#delete)|Geçerli kayıt kayıt kümesinden siler. Silindikten sonra başka bir kayıtla açıkça kaydırma gerekir.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Toplu satır kayıt veri kaynağından veri değişimi için çağrılır. Toplu kayıt alanı değişimi (Bulk RFX) olarak uygular.|
|[CRecordset::DoFieldExchange](#dofieldexchange)|Kayıt alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements alanı değişimi (RFX) kaydedin.|
|[CRecordset::Edit](#edit)|Değişiklikleri geçerli kayda hazırlar. Çağrı `Update` düzenlemeyi tamamlamak için.|
|[CRecordset::FlushResultSet](#flushresultset)|Önceden tanımlanmış sorgu kullanırken alınması için başka bir sonuç ise sıfır olmayan döndürür ayarlayın.|
|[CRecordset::GetBookmark](#getbookmark)|Yer işareti değeri bir kayıt parametresi nesnesine atar.|
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Varsayılan bağlantı dizesini almak için çağrılır.|
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Yürütmek için varsayılan SQL dizesini almak için çağrılır.|
|[CRecordset::GetFieldValue](#getfieldvalue)|Bir kayıt kümesinde bir alanın değerini döndürür.|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Kayıt kümesinde alanların sayısını döndürür.|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Bir kayıt kümesinde belirli tür alanları hakkında bilgileri döndürür.|
|[CRecordset::GetRecordCount](#getrecordcount)|Kayıt kümesindeki kayıt sayısını döndürür.|
|[CRecordset::GetRowsetSize](#getrowsetsize)|Tek bir getirme sırasında almak istediğiniz kayıt sayısını döndürür.|
|[CRecordset::GetRowsFetched](#getrowsfetched)|Getirme sırasında alınan satır sayısını döndürür.|
|[CRecordset::GetRowStatus](#getrowstatus)|Satır durumunu, getirmeden sonra döndürür.|
|[CRecordset::GetSQL](#getsql)|Kayıt kümesi kayıtları seçmek için kullanılan SQL dizesi alır.|
|[CRecordset::GetStatus](#getstatus)|Kayıt durumunu alır: geçerli kayıt ve son sayısıyla olup elde edilmiş dizini.|
|[CRecordset::GetTableName](#gettablename)|Kayıt kümesi, temel tablonun adını alır.|
|[CRecordset::IsBOF](#isbof)|İlk kayıttan önce kayıt üzere konumlandırmıştır sıfır olmayan döndürür. Geçerli kayıt yok.|
|[CRecordset::IsDeleted](#isdeleted)|Kayıt kümesini silinmiş bir kayda konumlandırıldı, sıfır döndürür.|
|[CRecordset::IsEOF](#iseof)|Son kayıttan sonra kayıt üzere konumlandırmıştır, sıfır döndürür. Geçerli kayıt yok.|
|[CRecordset::IsFieldDirty](#isfielddirty)|Belirtilen alan geçerli kayıt değiştirilmişse, sıfır döndürür.|
|[CRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıt belirtilen alan null ise sıfır olmayan döndürür (değeri yok).|
|[CRecordset::IsFieldNullable](#isfieldnullable)|Geçerli kayıt belirtilen alan null (hiçbir değer yok) olarak ayarlarsanız, sıfır döndürür.|
|[CRecordset::IsOpen](#isopen)|Döndürür gösterimiyse `Open` daha önce çağırıldı.|
|[CRecordset::Move](#move)|Kayıt belirli bir kayıt sayısı için herhangi bir yönde geçerli kaydından yerleştirir.|
|[CRecordset::MoveFirst](#movefirst)|İlk kayıt kayıt kümesindeki geçerli kayıt yerleştirir. Test `IsBOF` ilk.|
|[CRecordset::MoveLast](#movelast)|Son kayda veya son satır kümesi geçerli kayıt yerleştirir. Test `IsEOF` ilk.|
|[CRecordset::MoveNext](#movenext)|Sonraki kayıt veya sonraki satır kümesi geçerli kayıt yerleştirir. Test `IsEOF` ilk.|
|[CRecordset::MovePrev](#moveprev)|Önceki kayda veya önceki satır kümesi geçerli kayıt yerleştirir. Test `IsBOF` ilk.|
|[CRecordset::OnSetOptions](#onsetoptions)|(Seçim kullanılan) seçeneklerini ayarlamak için belirtilen ODBC deyimi için çağrılır.|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Belirtilen ODBC deyimi için (güncelleştirmesinde kullanılır) seçeneklerini ayarlamak için çağrılır.|
|[CRecordset::Open](#open)|Kayıt, tablo almak veya kayıt kümesini temsil eden sorgu gerçekleştirme açılır.|
|[CRecordset::RefreshRowset](#refreshrowset)|Belirtilen satırları durumunu ve verileri yeniler.|
|[CRecordset::Requery](#requery)|Yeniden seçilen kayıtları yenilemek için kayıt kümesinin sorgusu çalıştırır.|
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Belirtilen kayıt numarasına karşılık gelen kayıt kayıt kümesini yerleştirir.|
|[CRecordset::SetBookmark](#setbookmark)|Yer işareti tarafından belirtilen kayıt kayıt kümesini yerleştirir.|
|[CRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıt belirtilen alan değiştirilmiş olarak işaretler.|
|[CRecordset::SetFieldNull](#setfieldnull)|Null (hiçbir değer yok) geçerli kayıttaki belirtilen alanın değerini ayarlar.|
|[CRecordset::SetLockingMode](#setlockingmode)|"İyimser" (varsayılan) kilitleme ya da "kötümser" kilitleme Kilitleme modunu ayarlar. Kayıtların güncelleştirmeleri nasıl kilitlenip belirler.|
|[CRecordset::SetParamNull](#setparamnull)|Belirtilen parametre null (hiçbir değer yok) olarak ayarlar.|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|İmleci belirtilen satırda satır içinde konumlandırır.|
|[CRecordset::SetRowsetSize](#setrowsetsize)|Getirme sırasında almak istediğiniz kayıt sayısını belirtir.|
|[CRecordset::Update](#update)|Tamamlanan bir `AddNew` veya `Edit` yeni veya düzenlenmiş verilerin veri kaynağında kaydederek işlemi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CRecordset::m_hstmt](#m_hstmt)|Kayıt kümesi için ODBC deyim tanıtıcı içerir. Tür `HSTMT`.|
|[CRecordset::m_nFields](#m_nfields)|Alan veri üyeleri kümesinde sayısını içerir. Tür `UINT`.|
|[CRecordset::m_nParams](#m_nparams)|Kayıt kümesi parametre veri üyeleri sayısını içerir. Tür `UINT`.|
|[CRecordset::m_pDatabase](#m_pdatabase)|Bir işaretçi içeren `CDatabase` üzerinden kayıt bir veri kaynağına bağlıysa nesne.|
|[CRecordset::m_strFilter](#m_strfilter)|İçeren bir `CString` yapılandırılmış sorgu dili (SQL) belirten `WHERE` yan tümcesi. Belirli ölçütleri karşılayan kayıtları seçmek için filtre olarak kullanılır.|
|[CRecordset::m_strSort](#m_strsort)|İçeren bir `CString` SQL belirten `ORDER BY` yan tümcesi. Kayıtları nasıl sıralanacağını denetlemek için kullanılır.|

## <a name="remarks"></a>Açıklamalar

"Kayıt kümeleri," bilinen `CRecordset` nesneler genellikle iki formlarında kullanılan: dinamik kümeler ve anlık görüntüler. Bir dinamik diğer kullanıcılar tarafından yapılan veri güncelleştirmeleri ile eşitlenmiş durumda kalır. Verilerin statik görünümünü anlık görüntüsüdür. Her form kayıt açıldığında sabit kayıt kümesini temsil eder, ancak bir dinamik bir kayıtta gidin, kayıt için diğer kullanıcılar tarafından veya uygulamanızdaki diğer kayıt kümeleri tarafından yapılmış değişiklikleri yansıtır.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, sınıf kullanmak [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) yerine. Daha fazla bilgi için bkz [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Kayıt kümesi ya da tür ile çalışmak için genellikle bir uygulamaya özgü kayıt sınıfından türetilir `CRecordset`. Kayıt kümeleri, bir veri kaynağındaki kayıtları seçmek ve ardından şunları yapabilirsiniz:

- Kayıtlarda gezinin.

- Kayıtları güncelleştirmek ve kilitleme modunu belirtin.

- Veri kaynağında mevcut kodlar arasından seçen kayıtları sınırlamak için kayıt filtreleyin.

- Kayıt kümesi sıralayın.

- Çalışma zamanına kadar bilinmiyor bilgilerle, seçim özelleştirmek için kayıt kümesini parametreleştirme.

Sınıfınıza kullanmak için bir veritabanını açmak ve oluşturucu için bir işaretçi geçirerek bir kayıt kümesi nesnesi oluşturun, `CDatabase` nesne. Ardından kayıt kümesinin çağrı `Open` belirleyebileceğiniz bir anlık görüntüsünü veya bir dinamik Nesne olup olmadığını, üye işlevi. Çağırma `Open` veri kaynağından veri seçer. Kayıt kümesi nesnesi açıldıktan sonra üye işlevleri ve veri üyelerini kayıtlarda gezinin ve üzerlerinde çalışmak için kullanın. Güncelleştirilebilir veya salt okunur olup olmadığını kullanılabilen işlemleri nesne bir anlık görüntüsünü veya bir dinamik olmasına göre değişir (açık veritabanı bağlantısı (ODBC) veri kaynağının yeteneğini bağlıdır), ve toplu satır getirme olup uyguladıysanız. Değiştirilmiş veya olabilir beri eklenen kayıtları yenilemek için `Open` çağrı, nesnenin çağrı `Requery` üye işlevi. Nesnenin `Close` üye işlev ve ile işiniz bittiğinde nesneyi yok edin.

Türetilen bir `CRecordset` sınıfı, kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Bulk RFX), okuma ve kayıt alanlarının güncelleştirmeyi desteklemek için kullanılır.

Kayıt kümeleri ve kayıt alanı değişimi hakkında daha fazla bilgi için makalelere göz atın [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md), [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: Kayıtları toplu (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md). Bir odaklanmak için dinamik kümeler ve anlık görüntüleri, makalelere göz atın [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="addnew"></a>  CRecordset::AddNew

Tabloya yeni bir kayıt eklemek için hazırlar.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız [Requery](#requery) yeni eklenen kaydın görmek için üye işlevi. Kaydın alanları başlangıçta Null. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve C++'ta NULL ile aynı değildir.) İşlemi tamamlamak için çağırmalıdır [güncelleştirme](#update) üye işlevi. `Update` yaptığınız değişiklikleri veri kaynağına kaydeder.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `AddNew`. Bu başarısız bir onaylama işlemi neden olur. Ancak sınıf `CRecordset` mekanizması sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevlerinizi ODBC API işlevini kullanarak yazabileceğiniz `SQLSetPos`. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew` kümesinin alan veri üyeleri kullanarak yeni ve boş bir kayda hazırlar. Çağırdıktan sonra `AddNew`, kayıt kümesinin alan veri üyeleri istediğiniz değerleri ayarlayın. (Çağrı gerekmez [Düzenle](#edit) üye işlev bu amaçla; kullanım `Edit` yalnızca için var olan kayıtların.) Daha sonra çağırdığınızda `Update`değişen değerler alan veri üyeleri, veri kaynağında kaydedilir.

> [!CAUTION]
>  Çağırmadan önce yeni bir kayıt için kaydırın, `Update`yeni kayıt kaybolur ve herhangi bir uyarı verilir.

Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz, `AddNew` arama işlemlerinin bir parçası. İşlemler hakkında daha fazla bilgi için bkz. [CDatabase](../../mfc/reference/cdatabase-class.md). Çağırmalısınız Not [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağırmadan önce `AddNew`.

> [!NOTE]
>  Dynaset'ler için yeni kayıt en son kaydını kayıt kümesine eklenir. Eklenen kayıtlar için anlık görüntüleri eklenmez; çağırmalısınız `Requery` kayıt kümesini yenilemek için.

Çağırmak geçersizdir `AddNew` bir kayıt kümesi için olan `Open` üye işlev çağrılmadı. A `CDBException` çağırırsanız durum `AddNew` için bir kayıt kümesi için eklenemiyor. Kayıt kümesi çağırarak güncelleştirilebilir olup olmadığını belirleyebilir [CanAppend](#canappend).

Daha fazla bilgi için aşağıdaki makalelere bakın: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), ve [işlem () ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Örnek

Makaleye göz atın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="canappend"></a>  CRecordset::CanAppend

Önceden açılmış kayıt yeni kayıtlar eklemenize izin verip vermediğini belirler.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni kayıtlar ekleyerek kayıt kümesini sağlayan olursa sıfır dışı; Aksi durumda 0. `CanAppend` kayıt kümesi salt okunur olarak açıldıysa 0 döndürür.

##  <a name="canbookmark"></a>  CRecordset::CanBookmark

Kayıt, kayıt yer işaretlerini kullanma işaretlemek izin verip vermediğini belirler.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yer işaretleri destekliyorsa, sıfır olmayan; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev bağımsız olarak, `CRecordset::useBookmarks` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi. `CanBookmark` Belirtilen ODBC sürücüsünü ve imleç desteği yer işaretleri türü olup olmadığını gösterir. `CRecordset::useBookmarks` Bunlar desteklenir sağlanan yer işaretleri kullanılabilir durumda olup olmadığını gösterir.

> [!NOTE]
>  Yer işaretleri salt iletme kayıt kümeleri desteklenmez.

Yer işaretleri ve kayıt kümesi Gezinti hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cancel"></a>  CRecordset::Cancel

Veri kaynağı zaman uyumsuz bir işlem devam ediyor ya da bir işlemin ikinci bir iş parçacığından iptal isteği.

```
void Cancel();
```

### <a name="remarks"></a>Açıklamalar

MFC ODBC sınıfları artık zaman uyumsuz işleme kullandığını unutmayın. bir Aracıdan işlemi gerçekleştirmek için doğrudan ODBC API işlevini çağırmanız gerekir `SQLSetConnectOption`. Daha fazla bilgi için bölümündeki "Yürütülen işlevler zaman uyumsuz olarak" konusuna bakın. *ODBC SDK Programcı Kılavuzu*.

##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate

Güncelleştirmeleri nedeni, bekleyen iptal bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi, önce [güncelleştirme](#update) çağrılır.

```
void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu üye işlevi gibi kayıt kümeleri çağrılamıyor beri toplu satır, getirme kullanarak kümelerinde uygulanamaz `Edit`, `AddNew`, veya `Update`. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Otomatik kirli alan denetimi etkinse, `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir `Edit` veya `AddNew` ; tersi durumda, değer değişikliklerini kalır. Kayıt kümesi açıldığında, varsayılan olarak, otomatik alan denetimi etkin. Devre dışı bırakmak için belirtmelisiniz `CRecordset::noDirtyFieldCheck` içinde *dwOptions* parametresinin [açık](#open) üye işlevi.

Verileri güncelleştirme hakkında daha fazla bilgi için bkz [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).

##  <a name="canrestart"></a>  CRecordset::CanRestart

Kayıt kümesi (kayıtlarını yenilemek için), sorgu çağırarak yeniden izin verip vermediğini belirler `Requery` üye işlevi.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Dönüş Değeri

Requery izin olursa sıfır dışı; Aksi durumda 0.

##  <a name="canscroll"></a>  CRecordset::CanScroll

Kayıt kaydırma izin verip vermediğini belirler.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kaydırma sağlar olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kaydırma hakkında daha fazla bilgi için bkz [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cantransact"></a>  CRecordset::CanTransact

Kayıt işlemleri izin verip vermediğini belirler.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi işlemlerin başlamasına izin veren olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>  CRecordset::CanUpdate

Kayıt kümesi güncelleştirilebilir olup olmadığını belirler.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirilebilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi veri kaynağındaki salt okunur ise veya belirttiyseniz salt okunur olabilir `CRecordset::readOnly` içinde *dwOptions* kayıt açıldığında parametresi.

##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError

Kaydı alma sırasında oluşturulan hataları işlemek için çağrılır.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Parametreler

*nRetCode*<br/>
ODBC API işlevi dönüş kodu. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlevi, kayıtları getirilen kullanırken oluşan hatalarını ele alır ve toplu satır getirme sırasında yararlıdır. Geçersiz kılma düşünmek isteyebilirsiniz `CheckRowsetError` kendi hata işleme uygulamak için.

`CheckRowsetError` İmleç bir gezinti işlemi gibi otomatik olarak çağrılır `Open`, `Requery`, ya da tüm `Move` işlemi. ODBC API işlev dönüş değeri geçirilir `SQLExtendedFetch`. İçin olası değerler aşağıdaki tabloda *nRetCode* parametresi.

|nRetCode|Açıklama|
|--------------|-----------------|
|SQL_SUCCESS|İşlev; başarıyla tamamlandı ek bilgi kullanılabilir.|
|SQL_SUCCESS_WITH_INFO|İşlev başarılı bir şekilde, büyük olasılıkla önemli olmayan bir hata ile tamamlandı. Ek bilgi elde edilebilir çağırarak `SQLError`.|
|SQL_NO_DATA_FOUND|Sonuç kümesi tablosundan tüm satırları getirildi.|
|SQL_ERROR HATASI|İşlev başarısız oldu. Ek bilgi elde edilebilir çağırarak `SQLError`.|
|SQL_INVALID_HANDLE|İşlev Geçersiz ortam tanıtıcısı, bağlantı tanıtıcısı veya deyim tanıtıcısı nedeniyle başarısız oldu. Bu, bir programlama hatası gösterir. Ek bilgi kullanılabilir `SQLError`.|
|SQL_STILL_EXECUTING|Zaman uyumsuz olarak başlatılan bir işlev hala yürütülüyor. Varsayılan olarak, MFC hiçbir zaman bu değere geçeceğini Not `CheckRowsetError`; MFC arama devam `SQLExtendedFetch` artık sql_stıll_executıng dönene kadar.|

Hakkında daha fazla bilgi için `SQLError`, Windows SDK'sı bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="close"></a>  CRecordset::Close

Kayıt kümesi kapatır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

ODBC HSTMT ve kayıt için ayrılan framework tüm bellek serbest bırakılır. Arama sonra genellikle `Close`, ile ayırdığınızda C++ kayıt kümesi nesnesi silme **yeni**.

Çağırabilirsiniz `Open` arama sonra yeniden `Close`. Bu, kayıt kümesi nesnesi yeniden kullanmanıza olanak sağlar. Alternatif çağırmaktır `Requery`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

##  <a name="crecordset"></a>  CRecordset::CRecordset

Oluşturur bir `CRecordset` nesne.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir işaretçi içeren bir `CDatabase` nesne veya NULL değeri. BOŞ değilse ve `CDatabase` nesnenin `Open` veri kaynağına bağlanmak için üye işlev çağrılmadı, kayıt, sizin için kendi sırasında açmaya `Open` çağırın. NULL, başarılı olursa bir `CDatabase` nesne oluşturulur ve belirttiğiniz zaman, ClassWizard ile kayıt kümesi sınıfı türetilmiş veri kaynağı bilgilerini kullanarak bağlandı.

### <a name="remarks"></a>Açıklamalar

Kullanabilir `CRecordset` doğrudan veya bir uygulamaya özgü sınıfından türetilir `CRecordset`. ClassWizard kayıt kümesi sınıflarını türetmek için kullanabilirsiniz.

> [!NOTE]
>  Türetilmiş bir sınıf *gerekir* kendi Oluşturucu sağlayın. Türetilmiş sınıfınızın oluşturucuda oluşturucusunu `CRecordset::CRecordset`, kendisine boyunca uygun parametreleri geçirme.

NULL geçirmek için kayıt kümesi oluşturucusuna bir `CDatabase` nesne oluşturulur ve sizin için otomatik olarak bağlı. Bu, oluşturmak ve bağlanmak gerektirmeyen yararlı bir toplu özelliktir bir `CDatabase` kümenizin oluşturmak önce nesne.

### <a name="example"></a>Örnek

Daha fazla bilgi için bkz [kayıt kümesi: bir tablo (ODBC için) bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

##  <a name="delete"></a>  CRecordset::Delete

Geçerli kaydı siler.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı silindikten sonra kayıt kümesinin alan veri üyeleri Null değerine ayarlanır ve biri açıkça çağırmalıdır `Move` silinen kayıt taşımak için işlevleri. Silinen bir kaydı taşıdığınızda, geri mümkün değildir. Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz `Delete` arama işlemlerinin bir parçası. Daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `Delete`. Bu başarısız bir onaylama işlemi neden olur. Ancak sınıf `CRecordset` mekanizması sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevlerinizi ODBC API işlevini kullanarak yazabileceğiniz `SQLSetPos`. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir olmalıdır ve olmalıdır geçerli bir kayıt kümenize geçerli çağırdığınızda `Delete`; Aksi takdirde hata oluşur. Örneğin, bir kaydı silmek, ancak çağırmadan önce yeni bir kayıt için kaydırma değil `Delete` yeniden `Delete` oluşturur bir [CDBException](../../mfc/reference/cdbexception-class.md).

Farklı [AddNew](#addnew) ve [Düzenle](#edit), çağrı `Delete` bir çağrı tarafından izlenmiyor [güncelleştirme](#update). Varsa bir `Delete` çağrısı başarısız olursa, değiştirmeden üyeleri bırakılır alan verisi.

### <a name="example"></a>Örnek

Bu örnek, bir işlevin karesinde oluşturulan bir kayıt kümesi gösterir. Örnek varsayar `m_dbCust`, bir üye değişkeni türü `CDatabase` zaten veri kaynağına bağlı.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange

Toplu satır kayıt veri kaynağından veri değişimi için çağrılır. Toplu kayıt alanı değişimi (Bulk RFX) olarak uygular.

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesne. Çerçeve zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulandığında framework otomatik olarak veri kaynağından veri kayıt nesnenizin aktarmak için bu üye işlevini çağırır. `DoBulkFieldExchange` Ayrıca, parametre veri üyeleri, varsa kayıt kümesinin seçimi için SQL deyim dizesi parametre yer tutucularını bağlar.

Toplu satır getirme uygulanmadı, framework çağırır [DoFieldExchange](#dofieldexchange). Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği *dwOptions* parametresinde [açık](#open) üye işlevi.

> [!NOTE]
> `DoBulkFieldExchange` türetilen bir sınıf kullanıyorsanız kullanılabilir `CRecordset`. Doğrudan kayıt kümesi nesnesi oluşturduysanız `CRecordset`, çağırmalısınız [GetFieldValue](#getfieldvalue) veri almak için üye işlevi.

Kayıt alanı değişimi (RFX) için toplu kayıt alanı değişimi (Bulk RFX) benzer. Veriler, kayıt kümesi nesnesi için veri kaynağından otomatik olarak aktarılır. Ancak, çağıramazsınız `AddNew`, `Edit`, `Delete`, veya `Update` veri kaynağına yapılan değişiklikleri aktarmak için. Sınıf `CRecordset` şu anda veri; toplu satırı güncelleştirmek için bir mekanizma sağlamaz ODBC API işlevini kullanarak kendi işlevlerinizi ancak yazabilirsiniz `SQLSetPos`.

ClassWizard toplu kayıt alanı değişimi desteklemediğini unutmayın. Bu nedenle, kılmalı `DoBulkFieldExchange` toplu RFX işlevleri çağrıları yazarak el ile. Bu işlevler hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).

Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). İlgili bilgi için bkz [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange

Kayıt alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements alanı değişimi (RFX) kaydedin.

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesne. Çerçeve zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulanmadı framework otomatik olarak, kayıt kümesi nesnesi alan veri üyeleri geçerli kaydın veri kaynağında karşılık gelen sütunlara arasında veri değişimi için bu üye işlevini çağırır. `DoFieldExchange` Ayrıca, parametre veri üyeleri, varsa kayıt kümesinin seçimi için SQL deyim dizesi parametre yer tutucularını bağlar.

Toplu satır getirme uygulanmışsa framework çağırır [DoBulkFieldExchange](#dobulkfieldexchange). Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği *dwOptions* parametresinde [açık](#open) üye işlevi.

> [!NOTE]
> `DoFieldExchange` türetilen bir sınıf kullanıyorsanız kullanılabilir `CRecordset`. Doğrudan kayıt kümesi nesnesi oluşturduysanız `CRecordset`, çağırmalısınız [GetFieldValue](#getfieldvalue) veri almak için üye işlevi.

Kayıt alanı değişimi (RFX) adlı alan veri alışverişi her iki yönde de çalışır: kayıt nesnenin alan veri üyeleri alanlara veri kaynağında kayıt ve kayıt kümesi nesnesi için veri kaynağında kayıt.

Normal olarak yapmanız gereken uygulamak için tek eylem `DoFieldExchange` türetilmiş kümeniz için sınıf ClassWizard ile oluşturup alan veri üyeleri adları ve veri türlerini belirtmek için sınıftır. Ayrıca, hangi ClassWizard parametre veri üyeleri belirtin veya dinamik olarak bağlama tüm sütunları ile uğraşmak yazar için kod ekleyebilirsiniz. Daha fazla bilgi için bkz [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

ClassWizard ile türetilmiş kayıt kümesi sınıfı bildirdiğinizde, sihirbaz geçersiz kılma Yazar `DoFieldExchange` sizin için hangi benzer aşağıdaki örnekte:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

RFX işlevleri hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).

Daha ayrıntılı örnekler ve ayrıntılar hakkında `DoFieldExchange`, makaleye göz atın [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md). RFX hakkında genel bilgi için bkz [kayıt alanı değişimi](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="edit"></a>  CRecordset::Edit

Değişiklik geçerli kayda izin verir.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `Edit`, doğrudan değerlerine sıfırlayarak alan veri üyelerini değiştirebilirsiniz. Daha sonra çağırdığınızda, işlem tamamlanmadan [güncelleştirme](#update) veri kaynağı üzerinde yaptığınız değişiklikleri kaydetmek için üye işlevi.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `Edit`. Bu başarısız bir onaylama işlemi neden olur. Ancak sınıf `CRecordset` mekanizması sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevlerinizi ODBC API işlevini kullanarak yazabileceğiniz `SQLSetPos`. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit` kayıt kümesi veri üyelerinin değerlerini kaydeder. Çağırırsanız `Edit`, ardından çağırın değişiklik `Edit` ne ilk önce oldukları için kaydın değerleri yeniden geri `Edit` çağırın.

Bazı durumlarda, bir sütun Null (hiçbir veri içeren) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için çağrı [SetFieldNull](#setfieldnull) parametresi Null; alanı işareti true ile bu da güncelleştirilmesi sütun neden olur. Bir alanın değerini değişmemiş olsa da veri kaynağına yazılması, çağrı istiyorsanız [SetFieldDirty](#setfielddirty) parametresi true. ' % S'değeri boş alan olsa bile bu çalışır.

Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz `Edit` arama işlemlerinin bir parçası. Çağırmalısınız Not [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağırmadan önce `Edit` ve kayıt açıldıktan sonra. Ayrıca, arama unutmayın [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) çağırmak yerine değil `Update` tamamlanması `Edit` işlemi. İşlemler hakkında daha fazla bilgi için bkz. [CDatabase](../../mfc/reference/cdatabase-class.md).

Geçerli kilitleme modunuza bağlı olarak güncelleştirilen bir kaydı tarafından kilitlenmiş olabilir `Edit` , çağırana kadar `Update` veya başka bir kayıt gidin veya yalnızca sırasında kilitlenebilir `Edit` çağırın. Kilitleme moduyla değiştirebilirsiniz [CRecordset::pessimistic](#setlockingmode).

Geçerli kayıt önceki değerine geri çağırmadan önce yeni bir kayıt için kaydırırsanız `Update`. A `CDBException` çağırırsanız durum `Edit` güncelleştirilemiyor bir kayıt veya geçerli bir kayıt olup olmadığını.

Daha fazla bilgi için makalelere bakın [işlem (ODBC)](../../data/odbc/transaction-odbc.md) ve [kayıt kümesi: kilitleme kayıtları (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

##  <a name="flushresultset"></a>  CRecordset::FlushResultSet

Birden çok sonuç kümesi varsa (saklı yordam), önceden tanımlanmış sorgu sonraki sonuç kümesini alır.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Dönüş Değeri

Alınacak daha fazla sonuç kümesi yoksa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Çağırmalısınız `FlushResultSet` yalnızca geçerli sonuç kümesi imleç tamamen tamamlanmış olduğunuzda. Sonraki sonuç çağırarak kümesini alırken unutmayın `FlushResultSet`, imleç, sonuç kümesi üzerinde geçerli değil; çağırmalısınız [MoveNext](#movenext) üye işlevini çağırmadan sonra `FlushResultSet`.

Önceden tanımlanmış sorgu çıkış parametresi veya giriş/çıkış parametrelerini kullanıyorsa, çağırmalıdır `FlushResultSet` döndürür kadar `FALSE` (Bu parametre değerlerini almak için değer 0).

`FlushResultSet` ODBC API işlevini çağıran `SQLMoreResults`. Varsa `SQLMoreResults` SQL_ERROR hatası veya SQL_INVALID_HANDLE, ardından döndürür `FlushResultSet` bir özel durum oluşturur. Hakkında daha fazla bilgi için `SQLMoreResults`, Windows SDK'sı bakın.

Depolanmış yordamınızdaki çağırmak istiyorsanız alanlar bağlı gerekiyor `FlushResultSet`.

### <a name="example"></a>Örnek

Aşağıdaki kod, varsayar `COutParamRecordset` olduğu bir `CRecordset`-birden çok sonuç kümesi olan ve giriş parametresi ve bir output parametresi önceden tanımlanmış sorgu temel türetilmiş nesne. Yapısını Not [DoFieldExchange](#dofieldexchange) geçersiz kılar.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

##  <a name="getbookmark"></a>  CRecordset::GetBookmark

Geçerli kayıt için yer işareti değeri elde eder.

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) geçerli kayıtta yer işareti temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

Yer işaretleri kayıt kümesinde desteklenip desteklenmediğini belirlemek için çağrı [CanBookmark](#canbookmark). Destekleniyorsa yer işaretleri kullanılabilir hale getirmek için ayarlamalısınız `CRecordset::useBookmarks` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi.

> [!NOTE]
>  Yer işaretleri desteklenmeyen veya kullanılamıyor, çağırma `GetBookmark` oluşturulan bir özel durumu oluşur. Yer işaretleri salt iletme kayıt kümeleri desteklenmez.

`GetBookmark` yer işareti için geçerli kayda değerini atar bir `CDBVariant` nesne. Başka bir kayıda taşıdıktan herhangi bir zamanda kayda döndürmek için çağrı [SetBookmark](#setbookmark) ile karşılık gelen `CDBVariant` nesne.

> [!NOTE]
>  Belirli kayıt işlemlerinden sonra yer işaretlerini artık geçerli olmayabilir. Örneğin, eğer `GetBookmark` ardından `Requery`, kayıtla dönmek mümkün olmayabilir `SetBookmark`. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenli bir şekilde çağırıp çağırmayacağınızı denetlenecek `SetBookmark`.

Yer işaretleri ve kayıt kümesi Gezinti hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="getdefaultconnect"></a>  CRecordset::GetDefaultConnect

Varsayılan bağlantı dizesini almak için çağrılır.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` , varsayılan bağlantı dizesini içerir.

### <a name="remarks"></a>Açıklamalar

Framework ' kayıt kümesi temel aldığı veri kaynağı için varsayılan bağlantı dizesini almak için bu üye işlevi çağırır. ClassWizard ClassWizard tablolar ve sütunlar hakkında bilgi almak için kullandığınız aynı veri kaynağını tanımlayarak bu işlev, uygular. Büyük olasılıkla, uygulamanızı geliştirme sırasında bu varsayılan bağlantı etmenin kolay bulacaksınız. Ancak, varsayılan bağlantı uygulamanızın kullanıcıları için uygun olmayabilir. Bu durumda, bu işlev, ClassWizard'ın sürümü atılıyor yeniden uygulayın. Bağlantı dizeleri hakkında daha fazla bilgi için bkz [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).

##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL

Yürütmek için varsayılan SQL dizesini almak için çağrılır.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` , varsayılan SQL deyimi içerir.

### <a name="remarks"></a>Açıklamalar

Framework, kayıt temel varsayılan SQL durumunu almak için bu üye işlevini çağırır. Bu tablo adı veya bir SQL olabilir **seçin** deyimi.

Dolaylı olarak ClassWizard ile kayıt kümesi sınıfı bildirerek varsayılan SQL deyimini tanımlayın ve bu görevi, ClassWizard gerçekleştirir.

Kendi kullanımınız için SQL deyimi dizeye gereksiniminiz varsa, çağrı `GetSQL`, açıldığında kayıt kümesinin kayıtları seçmek için kullanılan SQL ifadesi döndürür. Varsayılan SQL dizesinde geçersiz kılma sınıfınızın düzenleyebileceğiniz `GetDefaultSQL`. Örneğin, kullanarak bir önceden tanımlanmış sorgu için bir çağrı belirtebilirsiniz bir **çağrı** deyimi. (Not olması durumunda, ancak düzenleme `GetDefaultSQL`, değiştirmeniz gerekir `m_nFields` veri kaynağındaki sütun sayısı eşleştirilecek.)

Daha fazla bilgi için bkz [kayıt kümesi: bir tablo (ODBC için) bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
>  Tablo adı framework birden çok tablo adları belirttiğinizde veya bir tablo adı tanımlanamadı değeri boş bir **çağrı** deyimi değil yorumlanabilir. Kullanırken dikkat bir **çağrı** deyim, küme ayracı arasında boşluk eklememeniz gerekir ve **çağrı** anahtar sözcüğü, ya da önce küme ayracı veya önce boşluk eklemeniz gerekir  **SEÇİN** anahtar sözcüğü bir **seçin** deyimi.

##  <a name="getfieldvalue"></a>  CRecordset::GetFieldValue

Geçerli kayıt alanı verileri alır.

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

*varValu*e bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) alanın değerini depolayan bir nesne.

*nFieldType*<br/>
ODBC C alanın veri türü. Varsayılan değer, DEFAULT_FIELD_TYPE, kullanarak zorlar `GetFieldValue` aşağıdaki tabloda temel C veriler SQL veri türü belirlenemiyor. Aksi takdirde, verileri doğrudan yazın veya uyumlu bir veri türü seçin belirtebilirsiniz; Örneğin, herhangi bir veri türü SQL_C_CHAR içine depolayabilirsiniz.

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

ODBC veri türleri hakkında daha fazla bilgi için "SQL veri türleri" ve "C veri türleri" ek d Windows SDK'sının konularına bakın.

*nIndex*<br/>
Alan sıfır tabanlı dizini.

*strValue*<br/>
Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alanın değerini depolayan bir nesne, metin, alanın veri türünü bağımsız olarak dönüştürülür.

### <a name="remarks"></a>Açıklamalar

Bir alan adı veya dizin bakabilirsiniz. Alan değeri ya da depolayabilirsiniz bir `CDBVariant` nesnesi veya bir `CString` nesne.

Toplu satır getirme uyguladıysanız, bir satır kümesinde bulunan ilk kayda üzerinde her zaman geçerli kayda konumlandırıldı. Kullanılacak `GetFieldValue` belirli bir satır kümesindeki bir kayıt üzerinde ilk çağırmalısınız [SetRowsetCursorPosition](#setrowsetcursorposition) imleç istenen satır, satır içinde taşımak için üye işlevi. Ardından çağırın `GetFieldValue` ilgili satır için. Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği *dwOptions* parametresinde [açık](#open) üye işlevi.

Kullanabileceğiniz `GetFieldValue` dinamik olarak bunları tasarım zamanında statik bağlama yerine çalışma zamanı alanları getirilemedi. Örneğin, bir kayıt kümesi nesnesi doğrudan bildirilmişlerse `CRecordset`, kullanmalısınız `GetFieldValue` almak için veri alanının; kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Bulk RFX) henüz uygulanmadı.

> [!NOTE]
>  Kayıt kümesi nesnesi türetme olmadan bildirirseniz `CRecordset`, yüklenen ODBC imleç kitaplığı izniniz yok. İmleç Kitaplığı kayıt kümesi en az bir ilişkili sütun olmasını gerektirir; Ancak, kullandığınızda `CRecordset` sütunların hiçbirinin doğrudan bağlanır. Üye işlevleri [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) ve [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) imleç kitaplığı yüklü olup olmadığını denetleme.

`GetFieldValue` ODBC API işlevini çağıran `SQLGetData`. Alan değeri, gerçek uzunluk değeri SQL_NO_TOTAL sürücünüzü çıkışını veriyorsa `GetFieldValue` bir özel durum oluşturur. Hakkında daha fazla bilgi için `SQLGetData`, Windows SDK'sı bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek kod çağrıları gösterir `GetFieldValue` doğrudan bir kayıt kümesi nesnesi bildirilen `CRecordset`.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
>  DAO sınıfının aksine `CDaoRecordset`, `CRecordset` sahip olmadığı bir `SetFieldValue` üye işlevi. Doğrudan bir nesne oluşturursanız `CRecordset`, etkili bir şekilde salt okunur.

Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount

Kayıt kümesi nesnenizin alanlarında toplam sayısını alır.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt alan sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz [kayıt kümesi: oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo

Kayıt kümesi alanları hakkında bilgi edinir.

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

*FieldInfo*<br/>
Bir başvuru bir `CODBCFieldInfo` yapısı.

*nIndex*<br/>
Alan sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümünü, bir alan adına göre aramak sağlar. Başka bir sürüm dizin ile bir alanı Ara olanak sağlar.

Döndürülen bilgiler hakkında daha fazla açıklaması için bkz. [Codbcfieldınfo](../../mfc/reference/codbcfieldinfo-structure.md) yapısı.

Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz [kayıt kümesi: oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount

Kayıt kümesi boyutunu belirler.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısı; kayıt kümesi kayıt bulundurmuyorsa 0; veya kayıt sayısı belirlenemiyorsa, -1.

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Kayıt sayısı "yüksek su işareti," en yüksek numaralı kaydı tutulan henüz kullanıcı kayıtlar arasında hareket ettikçe görülür. Kullanıcının son kaydını taşındıktan sonra toplam kayıt sayısı yalnızca bilinir. Performansla ilgili nedenlerden dolayı çağırdığınızda sayısı güncelleştirilmez `MoveLast`. Kayıtları kendiniz saymak için çağrı `MoveNext` kadar sürekli olarak `IsEOF` sıfır döndürür. Bir kayıt aracılığıyla ekleme `CRecordset:AddNew` ve `Update` sayısını artırır; aracılığıyla kayıt silme `CRecordset::Delete` sayısı azalır.

##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize

Belirli bir getirme sırasında almak istediğiniz satır sayısı için geçerli ayarını alır.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Belirli bir getirme sırasında almak için satır sayısı.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme kullanıyorsanız, kayıt açıldığında varsayılan satır boyutu 25'tir; Aksi takdirde, 1'dir.

Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi. Satır kümesi boyutu için ayarı değiştirmek için çağrı [SetRowsetSize](#setrowsetsize).

Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched

Kaç tane kaydın getirmeden sonra gerçekte alınan belirler.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Dönüş Değeri

Satır sayısı, belirli bir getirmeden sonra veri kaynağından alınan.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygulandığında, bu yararlıdır. Satır kümesi boyutunu, normalde bir getirme kaç satır alınır gösterir; Ancak, satır kümesinde toplam sayısını da satır içinde kaç satır alınır etkiler. Kümenizin 4 satır boyutu ayarı 10 kayıt varsa, örneğin, ardından kayıt kümesi içinde çağırarak döngü `MoveNext` yalnızca 2 kayıtları sahip son satır kümesinde neden olur.

Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi. Satır kümesi boyutunu belirlemek için çağrı [SetRowsetSize](#setrowsetsize).

Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus

Geçerli satır kümesindeki bir satır için durumu alır.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Bir tabanlı konumu bir satır satır kümesi geçerli. Bu değer 1'den satır boyutunu değişebilir.

### <a name="return-value"></a>Dönüş Değeri

Satır için bir durum değeri. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

`GetRowStatus` alınan veri kaynağına veya, son başlatıldığından beri ya da herhangi bir değişiklik durumunda, satıra gösteren bir değer döndürür. hiçbir satır karşılık gelen *wRow* getirildi. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Durum değeri|Açıklama|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Satır değiştirilmez.|
|SQL_ROW_UPDATED|Satır güncelleştirildi.|
|SQL_ROW_DELETED|Satır silindi.|
|SQL_ROW_ADDED|Satır eklendi.|
|SQL_ROW_ERROR|Satır bir hata nedeniyle getirilemez.|
|SQL_ROW_NOROW|Karşılık gelen satır yok *wRow*.|

Daha fazla bilgi için bkz: ODBC API işlevini `SQLExtendedFetch` Windows SDK.

##  <a name="getstatus"></a>  CRecordset::GetStatus

Kayıt kümesi ve en son kaydını olup yakaladı geçerli kayıt dizinini belirler.

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Parametreler

*rStatus*<br/>
Bir başvuru bir `CRecordsetStatus` nesne. Daha fazla bilgi için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

`CRecordset` Dizin izlemek çalışır ancak bazı durumlarda bu mümkün olmayabilir. Bkz: [GetRecordCount](#getrecordcount) açıklaması.

`CRecordsetStatus` Yapısı aşağıdaki biçime sahiptir:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

İki üyesi `CRecordsetStatus` aşağıdaki anlamlara sahiptir:

- `m_lCurrentRecord` Geçerli kayıt kümesinde, sıfır tabanlı dizini biliniyorsa içerir. Dizin belirlenemiyorsa, bu üye AFX_CURRENT_RECORD_UNDEFINED-(2) içerir. Varsa `IsBOF` olduğu (boş bir kayıt kümesi veya önce ilk kaydı kaydırma denemesi), ardından TRUE `m_lCurrentRecord` AFX_CURRENT_RECORD_BOF (-1) için ayarlanır. İlk kayda, ardından bu 0 olarak ayarlanırsa, ikinci 1 kaydedin ve benzeri.

- `m_bRecordCountFinal` Toplam kayıt kümesindeki kayıt sayısı belirlendiğinde sıfır. Genellikle bu kayıt başlangıcında başlangıç ve çağırma gerçekleştirilmesi gereken `MoveNext` kadar `IsEOF` sıfır döndürür. Bu üye sıfırsa kayıt sayısı tarafından döndürülen `GetRecordCount`değil -1'dir, yalnızca "yüksek su işareti" sayısını kaydeder.

##  <a name="getsql"></a>  CRecordset::GetSQL

Açıldığında kayıt kümesinin kayıtları seçmek için kullanılan SQL durumunu almak için bu üye işlevini çağırın.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** başvurusu bir `CString` SQL deyimini içeren.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle bir SQL olacaktır **seçin** deyimi. Tarafından döndürülen dize `GetSQL` salt okunur.

Tarafından döndürülen dize `GetSQL` kümenize için geçirilen herhangi bir dize genellikle farklı *lpszSQL* parametresi `Open` üye işlevi. Kayıt kümesi ne sizin için geçen dayalı tam bir SQL deyimi oluşturur olmasıdır `Open`, ClassWizard ne belirttiğiniz ile belirtilen `m_strFilter` ve `m_strSort` veri üyeleri ve sahip olabileceğiniz herhangi bir parametre Belirtilen. Kayıt kümesi bu SQL deyimi nasıl yapıları hakkında ayrıntılar için bkz. makaleyi [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

> [!NOTE]
>  Bu üye işlevi çağırdıktan sonra yalnızca çağrı [açık](#open).

##  <a name="gettablename"></a>  CRecordset::GetTableName

Kayıt kümesinin sorgu temel SQL tablosunun adını alır.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Dönüş Değeri

A **const** başvurusu bir `CString` içeren tablo adı, kayıt varsa bağlı olarak bir tablo; Aksi takdirde boş bir dize.

### <a name="remarks"></a>Açıklamalar

`GetTableName` yalnızca bir tablo, bir birleşim değil birden fazla tablo ya da önceden tanımlanmış sorgu (saklı yordam) kayıt temel alıyorsa geçerlidir. Adı salt okunurdur.

> [!NOTE]
>  Bu üye işlevi çağırdıktan sonra yalnızca çağrı [açık](#open).

##  <a name="isbof"></a>  CRecordset::IsBOF

İlk kayıttan önce kayıt üzere konumlandırmıştır sıfır olmayan döndürür. Geçerli kayıt yok.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içeriyorsa veya geriye doğru ilk kaydı önce kaydırılan sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kayıttan önce ilk kaydı kümesi ilerlemiş olup olmadığını öğrenmek için kayıt kaydırarak önce bu üye işlevini çağırın. Ayrıca `IsBOF` ile birlikte `IsEOF` kayıt herhangi bir kayıt içerip boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra `Open`, kayıt, kayıt bulundurmuyorsa `IsBOF` sıfır döndürür. En az bir kaydına sahip bir kayıt kümesi açtığınızda, geçerli kaydın ilk kaydıdır ve `IsBOF` 0 döndürür.

Geçerli kaydı ilk kaydı ise ve çağırmanızı `MovePrev`, `IsBOF` sonradan sıfır döndürür. Varsa `IsBOF` sıfır döndürür ve çağrı `MovePrev`, bir hata oluşur. Varsa `IsBOF` sıfır döndürür, geçerli kayıt tanımsız olur ve geçerli bir kayıt gerektiren herhangi bir eylem hataya neden.

### <a name="example"></a>Örnek

Bu örnekte `IsBOF` ve `IsEOF` kodu her iki yönde de kayıt aracılığıyla kayarken bir kayıt kümesinin sınırlarını algılamak için.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

##  <a name="isdeleted"></a>  CRecordset::IsDeleted

Geçerli kaydı silinmiş olup olmadığını belirler.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayda konumlandırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kaydırırsanız ve `IsDeleted` doğru (sıfırdan farklı) döndürür ve herhangi bir kayıt işlemi gerçekleştirmek için önce başka bir kayıtla kaydırın.

Sonucu `IsDeleted` belirttiğiniz olmadığını kümenizin güncelleştirilebilir, olup olmadığını, kayıt kümesi türü gibi birçok faktöre bağlıdır `CRecordset::skipDeletedRecords` , sürücü paketleri kayıtları silinen olmadığını kayıt açıldığında olup olmadığına dair seçeneği birden çok kullanıcı.

Hakkında daha fazla bilgi için `CRecordset::skipDeletedRecords` ve paketleme, sürücü [açık](#open) üye işlevi.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız değil, çağırmalıdır `IsDeleted`. Bunun yerine çağrı [GetRowStatus](#getrowstatus) üye işlevi. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="iseof"></a>  CRecordset::IsEOF

Son kayıttan sonra kayıt üzere konumlandırmıştır, sıfır döndürür. Geçerli kayıt yok.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içeriyorsa veya en son kaydını kaydırırsanız sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi en son kaydını ilerlemiş olup olmadığını öğrenmek için kayda kaydından gezinirken bu üye işlevini çağırın. Ayrıca `IsEOF` kayıt herhangi bir kayıt içerip boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra `Open`, kayıt, kayıt bulundurmuyorsa `IsEOF` sıfır döndürür. En az bir kaydına sahip bir kayıt kümesi açtığınızda, geçerli kaydın ilk kaydıdır ve `IsEOF` 0 döndürür.

Son kayda çağırdığınızda geçerli kayıt olup olmadığını `MoveNext`, `IsEOF` sonradan sıfır döndürür. Varsa `IsEOF` sıfır döndürür ve çağrı `MoveNext`, bir hata oluşur. Varsa `IsEOF` sıfır döndürür, geçerli kayıt tanımsız olur ve geçerli bir kayıt gerektiren herhangi bir eylem hataya neden.

### <a name="example"></a>Örnek

Örneğin bakın [IsBOF](#isbof).

##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty

Belirtilen alan veri üyesi bu yana değiştirilip değiştirilmediğini belirler [Düzenle](#edit) veya [AddNew](#addnew) çağrıldı.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya herhangi bir alanı olumsuz olup olmadığını belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi arama bu yana değişmişse sıfır olmayan `AddNew` veya `Edit`; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yapılan bir çağrıyla geçerli kayıt güncelleştirildiğinde tüm kirli alan veri üyeleri verileri kaydı veri kaynağında aktarılır [güncelleştirme](#update) üye işlevinin `CRecordset` (çağrıyı izleyen `Edit` veya `AddNew`).

> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, ardından uyguladıysanız `IsFieldDirty` başarısız bir onaylama işlemi neden olur ve her zaman FALSE döndürür. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Çağırma `IsFieldDirty` çağrıları önceki etkilerini sıfırlar [SetFieldDirty](#setfielddirty) beri alanın kirli durumu yeniden değerlendirilir. İçinde `AddNew` durumda, güncel alan değerini sözde null değerinden farklı olması durumunda alan durumu ayarlanmış kirli. İçinde `Edit` alan değeri alan durumu kirli olarak ayarlayın daha sonra önbelleğe alınan değeri farklıysa, servis talebi.

`IsFieldDirty` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).

Kirli bayrağı hakkında daha fazla bilgi için bkz [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull

Geçerli kayıt belirtilen alan Null ise sıfır olmayan döndürür (değeri yok).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya tüm alanları boş olup olmadığını belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null olarak işaretlenen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi belirtilen alan veri üyesi Null olarak işaretlenmiş durumda olup olmadığını belirlemek için bu üye işlevini çağırın. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve C++'ta NULL ile aynı değildir.) Alan veri üyesi Null olarak işaretlenmişse, kendisi için bir değer yoktur geçerli kaydın bir sütun olarak yorumlanır.

> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, ardından uyguladıysanız `IsFieldNull` başarısız bir onaylama işlemi neden olur ve her zaman FALSE döndürür. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).

##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable

(Hiçbir değer yok), geçerli kayıtta belirtilen alan Null olarak ayarlanabilir, sıfır döndürür.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya alanlar için Null değer ayarlanabilir, belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Belirtilen alan veri üyesi "NULL" olup olmadığını belirlemek için (bir Null değer; olabilir, bu üye işlevini çağırın C++ NULL değil diğer bir deyişle, Veritabanı terminolojisinde, Null, aynı "değeri olan").

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `IsFieldNullable`. Bunun yerine çağrı [GetODBCFieldInfo](#getodbcfieldinfo) alana Null değerine ayarlanmış olup olmadığını belirlemek için üye işlevi. Her zaman çağırabilirsiniz Not `GetODBCFieldInfo`olup toplu satır getirme uyguladıysanız bakılmaksızın. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bir alan boş olamaz, bir değere sahip olmalıdır. Böyle bir alana eklerken veya bir kaydı güncelleştirme Null olarak ayarlamak çalışırsanız, veri kaynağı ekleme veya güncelleştirme, reddeder ve [güncelleştirme](#update) bir özel durum oluşturur. Çağırdığınızda özel durum oluşur `Update`, arama yaparken [SetFieldNull](#setfieldnull).

İşlevinin ilk bağımsız değişkeni yalnızca işlev geçerlidir NULL kullanarak `outputColumn` alanları değil `param` alanları. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca ayarlar `outputColumn` null; alanlar `param` alanları etkilenmez.

Üzerinde çalışılacak `param` alanları, ayrı ayrı gerçek adresi sağlamanız gerekir `param` gibi çalışmak istediğiniz:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Yani tüm ayarlayamıyor `param` ile yapabildiğiniz gibi alanları NULL olarak `outputColumn` alanları.

`IsFieldNullable` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).

##  <a name="isopen"></a>  CRecordset::IsOpen

Kayıt kümesi zaten açık olup olmadığını belirler.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ancak kayıt kümesi nesnesinin [açık](#open) veya [Requery](#requery) üye işlev önceden çağrıldıktan ve kayıt kapalı değil; Aksi durumda 0.

##  <a name="m_hstmt"></a>  CRecordset::m_hstmt

Kayıt kümesi ile ilişkili tür HSTMT, ODBC deyimi veri yapısı için bir tanıtıcı içerir.

### <a name="remarks"></a>Açıklamalar

Her sorgu bir ODBC veri kaynağı için bir HSTMT ile ilişkilidir.

> [!CAUTION]
>  Kullanmayın `m_hstmt` önce [açık](#open) çağrıldı.

Normalde HSTMT doğrudan erişimi gerekmez, ancak doğrudan SQL deyimlerini yürütme için gerekebilir. `ExecuteSQL` Sınıfının üye işlevinde `CDatabase` kullanarak bir örnek sağlar `m_hstmt`.

##  <a name="m_nfields"></a>  CRecordset::m_nFields

Alan veri üyeleri kayıt kümesi sınıfında sayısını içerir. diğer bir deyişle, veri kaynağından kayıt tarafından seçilen sütunların sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfı için oluşturucu başlatmalıdır `m_nFields` doğru numarasına sahip. Toplu satır getirme uygulanmadı, ClassWizard kayıt sınıfınıza bildirmek için kullanırken bu başlatmayı sizin için yazar. Ayrıca, el ile yazabilirsiniz.

Framework, alan veri üyeleri geçerli kaydın veri kaynağında karşılık gelen sütunlara arasındaki etkileşimi yönetmek için bu sayıyı kullanır.

> [!CAUTION]
>  Bu sayı "çıkış sütunları kayıtlı" sayısına karşılık gelmelidir `DoFieldExchange` veya `DoBulkFieldExchange` çağrısı yapıldıktan sonra [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametresiyle `CFieldExchange::outputColumn`.

Sütunları makalesinde açıklandığı gibi dinamik olarak bağlama "kayıt kümesi: dinamik olarak bağlama veri sütunlarını." Bunu yaparsanız, sayı artırmalıdır `m_nFields` RFX veya Bulk RFX işlev sayısı çağrıları yansıtacak şekilde, `DoFieldExchange` veya `DoBulkFieldExchange` dinamik olarak bağlı sütun için üye işlevi.

Daha fazla bilgi için makalelere bakın [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) ve [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

Makaleye göz atın [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_nparams"></a>  CRecordset::m_nParams

Kayıt kümesi sınıfı parametre veri üyeleri sayısını içerir. diğer bir deyişle, parametrelerin sayısı kayıt kümesinin sorgusuyla geçirildi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızın herhangi bir parametre veri üyesi varsa, sınıfın oluşturucusunda başlatmanız gerekir `m_nParams` doğru numarasına sahip. Değerini `m_nParams` varsayılan ayar: 0. (El ile yapmanız gerekir) parametre veri üyeleri eklerseniz, parametre sayısını yansıtacak şekilde sınıfı oluşturucusunda bir başlatma el ile eklemelisiniz (en az sayıda kadar büyük olması gereken '' içindeki yer tutucuları, `m_strFilter` veya `m_strSort`dize).

Framework kümesinin sorgu parametreleştiren bu sayıyı kullanır.

> [!CAUTION]
>  Bu sayı "kaydedilmiş params" sayısına karşılık gelmelidir `DoFieldExchange` veya `DoBulkFieldExchange` çağrısı yapıldıktan sonra [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametre değerini `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, veya `CFieldExchange::inoutParam`.

### <a name="example"></a>Örnek

  Makalelerine bakın [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) ve [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase

Bir işaretçi içeren `CDatabase` üzerinden kayıt bir veri kaynağına bağlıysa nesne.

### <a name="remarks"></a>Açıklamalar

Bu değişken, iki şekilde ayarlanır. Genellikle, bir işaretçi bir zaten bağlı geçirdiğiniz `CDatabase` kayıt kümesi nesnesi oluştururken nesne. Bunun yerine, NULL geçirirseniz `CRecordset` oluşturur bir `CDatabase` sizin için nesne ve bağlar. Her iki durumda da `CRecordset` işaretçiyi bu değişkeninde depolar.

Normalde, doğrudan depolanmış işaretçiyi kullanın gerekmez `m_pDatabase`. Kendi uzantılarınızı yazarsanız `CRecordset`, ancak işaretçi kullanmanız gerekebilir. Durum, örneğin, işaretçiyi kendi ihtiyacınız olabilecek `CDBException`s. Ya da aynı şey istiyorsanız buna ihtiyaç duyabilirsiniz `CDatabase` çalıştıran ayarı zaman aşımları, işlem veya arama gibi nesne `ExecuteSQL` sınıfının üye işlevinde `CDatabase` doğrudan SQL deyimlerini yürütmek için.

##  <a name="m_strfilter"></a>  CRecordset::m_strFilter

Kayıt kümesi nesnesi oluşturduktan sonra ancak çağırmadan önce kendi `Open` üye işlev, bu veri üyesi depolamak için kullanmak bir `CString` içeren bir SQL **burada** yan tümcesi.

### <a name="remarks"></a>Açıklamalar

Kayıt sırasında seçtiği kayıtları sınırlamak (veya filtrelemek için) bu dizeyi kullanır `Open` veya `Requery` çağırın. Kayıtların, "California'da bağlı tüm satış temsilcisi" gibi bir alt kümesini seçmek için kullanışlıdır ("durumu CA ="). ODBC SQL söz dizimi bir **burada** yan tümcesi

`WHERE search-condition`

Dahil etmezseniz Not **burada** anahtar sözcük, dize. Framework, sağlar.

Yerleştirerek, filtre dizesi parametreleştirebilirsiniz '' sınıfınıza parametre veri üyesi için her bir yer tutucu bildirme ve parametreleri kayıt kümesine geçirme yer tutucuları, çalışma zamanında. Bu, çalışma zamanında bir filtre oluşturmak sağlar. Daha fazla bilgi için bkz [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

SQL hakkında daha fazla bilgi için **burada** yan tümceleri, başlıklı makaleye bakın [SQL](../../data/odbc/sql.md). Seçme ve kayıtları filtreleme hakkında daha fazla bilgi için bkz [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

##  <a name="m_strsort"></a>  CRecordset::m_strSort

Kayıt kümesi nesnesi oluşturduktan sonra ancak çağırmadan önce kendi `Open` üye işlev, bu veri üyesi depolamak için kullanmak bir `CString` içeren bir SQL **ORDER BY** yan tümcesi.

### <a name="remarks"></a>Açıklamalar

Kayıt sırasında seçtiği kayıtları sıralamak için bu dizeyi kullanır. `Open` veya `Requery` çağırın. Bir kayıt kümesi bir veya daha fazla sütunlarda sıralamak için bu özelliği kullanabilirsiniz. ODBC SQL söz dizimi bir **ORDER BY** yan tümcesi

`ORDER BY sort-specification [, sort-specification]...`

Burada bir sıralama belirtimi bir tamsayı ya da bir sütun adı ' dir. Artan veya azalan sıralama (order varsayılan olarak artan) sıralama dizedeki sütun listesi için "ASC" veya "DESC" ekleyerek de belirtebilirsiniz. Seçilen kayıtları ilk tarafından saniye vb. sonra listelenen ilk sütuna göre sıralanır. Örneğin, "Müşteri" kayıt, Soyadı, daha sonra ad sipariş. Listelemek sütun sayısı, veri kaynağına bağlıdır. Daha fazla bilgi için Windows SDK'sı bakın.

Dahil etmezseniz Not **ORDER BY** anahtar sözcük, dize. Framework, sağlar.

SQL yan tümceleri hakkında daha fazla bilgi için bkz [SQL](../../data/odbc/sql.md). Kayıtları sıralama hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

##  <a name="move"></a>  CRecordset::Move

Kayıt kümesi, öne veya arkaya geçerli kayıt işaretçinin taşır.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Parametreler

*nRows*<br/>
İleriye veya geriye doğru gitme satırların sayısı. Pozitif değerlere, kayıt kümesinin sonuna doğru ileriye taşıyın. Negatif değerler başına doğru geriye doğru taşıyın.

*wFetchType*<br/>
Satır kümesi belirler, `Move` getirir. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

İçin 0 değeri geçirirseniz *nRows*, `Move` ; geçerli kaydı yeniler `Move` herhangi bir geçerli sona erecek `AddNew` veya `Edit` modunda ve önceki değer geçerli kaydın geri `AddNew` veya `Edit` çağrıldı.

> [!NOTE]
>  Bir kayıt kümesi taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [CRecordset::IsDeleted](#isdeleted) daha fazla bilgi için. Açtığınızda bir `CRecordset` ile `skipDeletedRecords` seçenek kümesi, `Move` , onaylar *nRows* 0 parametredir. Bu davranış, yenileme aynı verileri kullanarak diğer istemci uygulamalar tarafından silinen satır engeller. Bkz: *dwOption* parametresinde [açık](#open) açıklamasını `skipDeletedRecords`.

`Move` kayıt kümesi satır kümeleri tarafından yeniden konumlandırır. İçin değerlere göre *nRows* ve *wFetchType*, `Move` uygun satır kümesi getirir ve ardından söz konusu satır kümesinde ilk kaydı geçerli kayıt yapar. Toplu satır getirme uyguladıysanız değil, satır boyutu her zaman 1 olur. Bir satır kümesi getirilirken `Move` doğrudan çağıran [CheckRowsetError](#checkrowseterror) getirme kaynaklanan hataları işlemek için üye işlevi.

Geçirdiğiniz, değerleri bağlı olarak `Move` diğer eşdeğerdir `CRecordset` üye işlevleri. Özellikle, değerini *wFetchType* daha sezgisel bir üye işlevine ve genellikle geçerli kaydın taşınması için tercih edilen yöntem gösteriyor olabilir.

İçin olası değerler aşağıdaki tabloda *wFetchType*, satır kümesi, `Move` getirir göre *wFetchType* ve *nRows*ve herhangi bir eşdeğer üye işlevi için karşılık gelen *wFetchType*.

|wFetchType|Getirilen satır kümesi|Eşdeğer üye işlevi|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (varsayılan değer)|Satır kümesi başlangıç *nRows* geçerli satır kümesindeki ilk satırdan satır.||
|SQL_FETCH_NEXT|Sonraki satır kümesi; *nRows* göz ardı edilir.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|Önceki satır kümesi; *nRows* göz ardı edilir.|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|İlk satır kümesinde; *nRows* göz ardı edilir.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Son tam satır kümesinde; *nRows* göz ardı edilir.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|Varsa *nRows* > 0, başlangıç satır kümesi *nRows* baştan başlayarak bir satır kümesi. Varsa *nRows* < 0, başlangıç satır kümesi *nRows* satır sonundan itibaren kayıt. Varsa *nRows* = 0, dosya başına (BOF) koşul verilir.|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Yer işareti değeri karşılık gelen satırda başlayan satır kümesi *nRows*.|[SetBookmark](#setbookmark)|

> [!NOTE]
>  Salt iletme kayıt kümeleri için `Move` yalnızca SQL_FETCH_NEXT için değerinin geçerli olduğundan *wFetchType*.

> [!CAUTION]
>  Çağırma `Move` kayıt kayıt içermeyen bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı [IsBOF](#isbof) ve [IsEOF](#iseof).

> [!NOTE]
>  Başta veya sonda kümesinin kaydırılan varsa (`IsBOF` veya `IsEOF` sıfır döndürür), çağıran bir `Move` işlevi oluşturur büyük olasılıkla bir `CDBException`. Örneğin, varsa `IsEOF` sıfır döndürür ve `IsBOF` ardından yok, `MoveNext` bir özel durum oluşturmaz ancak `MovePrev` erişemez.

> [!NOTE]
>  Eğer `Move` geçerli kayıt yüklenirken güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). İlgili bilgiler için bkz: ODBC API işlevini `SQLExtendedFetch` Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

##  <a name="movefirst"></a>  CRecordset::MoveFirst

İlk kayıt ilk satır kümesi geçerli kayıt yapar.

```
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Olup toplu satır getirme uygulanmıştır bağımsız olarak, bu kayıt kümesindeki ilk kayıt her zaman olacaktır.

Çağrı gerekmez `MoveFirst` kayıt açıldıktan hemen sonra. O anda (varsa) ilk kaydı otomatik olarak geçerli kaydı olur.

> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  Örneğin bakın [IsBOF](#isbof).

##  <a name="movelast"></a>  CRecordset::MoveLast

İlk kaydı son tam satır kümesi geçerli kayıt yapar.

```
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme değil uyguladıysanız, kümenizin 1 satır kümesi boyutunu serileştirilmesini `MoveLast` yalnızca son kayıt kümenize taşır.

> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  Örneğin bakın [IsBOF](#isbof).

##  <a name="movenext"></a>  CRecordset::MoveNext

İlk kayıt sonraki satır kümesi geçerli kayıt yapar.

```
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme değil uyguladıysanız, kümenizin 1 satır kümesi boyutunu serileştirilmesini `MoveNext` yalnızca sonraki kayda taşır.

> [!NOTE]
>  Bir kayıt kümesi taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.

> [!NOTE]
>  Ayrıca çağırmanızı önerilir `IsEOF` çağırmadan önce `MoveNext`. Örneğin, kayıt kümesi sonundan kaydırırsanız `IsEOF` sıfır; döndürür bir sonraki çağrı `MoveNext` bir özel durum oluşturması.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  Örneğin bakın [IsBOF](#isbof).

##  <a name="moveprev"></a>  CRecordset::MovePrev

İlk kayıt önceki satır kümesi geçerli kayıt yapar.

```
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme değil uyguladıysanız, kümenizin 1 satır kümesi boyutunu serileştirilmesini `MovePrev` yalnızca önceki kayıda taşır.

> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.

> [!NOTE]
>  Bir kayıt kümesi taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.

> [!NOTE]
>  Ayrıca çağırmanızı önerilir `IsBOF` çağırmadan önce `MovePrev`. Örneğin, kayıt kümesi başına önüne kaydırırsanız `IsBOF` sıfır; döndürür bir sonraki çağrı `MovePrev` bir özel durum oluşturması.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kayıt kümesi gezintisi hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

  Örneğin bakın [IsBOF](#isbof).

##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions

(Seçim kullanılan) seçeneklerini ayarlamak için belirtilen ODBC deyimi için çağrılır.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*hstmt*<br/>
HSTMT ODBC deyiminin ayarlanacak olan seçeneklerdir.

### <a name="remarks"></a>Açıklamalar

Çağrı `OnSetOptions` için belirtilen ODBC deyimini (seçimde kullanılır) seçeneklerini ayarlamak için. Framework ilk kayıt seçeneklerini ayarlamak için bu üye işlevini çağırır. `OnSetOptions` veri kaynağının destek kaydırılabilir işaretçiler ve imleç eşzamanlılık belirler ve buna göre kayıt kümesinin seçeneklerini ayarlar. (Ancak `OnSetOptions` seçimi işlemleri için kullanılan `OnSetUpdateOptions` güncelleştirme işlemleri için kullanılır.)

Geçersiz kılma `OnSetOptions` seçeneklerini belirli sürücü veya veri kaynağı ayarlamak için. Örneğin, özel erişim için açma destekler, veri kaynağı ise, geçersiz kılabilir `OnSetOptions` bu özelliği yararlanmak için.

İşaretçiler hakkında daha fazla bilgi için bkz [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions

Belirtilen ODBC deyimi için (güncelleştirmesinde kullanılır) seçeneklerini ayarlamak için çağrılır.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parametreler

*hstmt*<br/>
HSTMT ODBC deyiminin ayarlanacak olan seçeneklerdir.

### <a name="remarks"></a>Açıklamalar

Çağrı `OnSetUpdateOptions` için belirtilen ODBC deyimini (güncelleştirmesinde kullanılır) seçeneklerini ayarlamak için. Bir kayıt kümesindeki kayıtları güncelleştirmek için bir HSTMT oluşturduktan sonra framework bu üye işlevini çağırır. (Ancak `OnSetOptions` seçimi işlemleri için kullanılan `OnSetUpdateOptions` güncelleştirme işlemleri için kullanılır.) `OnSetUpdateOptions` kaydırılabilir işaretçiler için ve imleç eşzamanlılık veri kaynağının desteği belirler ve buna göre kayıt kümesinin seçeneklerini ayarlar.

Geçersiz kılma `OnSetUpdateOptions` bu deyim, bir veritabanına erişmek için kullanılmadan önce bir ODBC deyiminin seçeneklerini ayarlamak için.

İşaretçiler hakkında daha fazla bilgi için bkz [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="open"></a>  CRecordset::Open

Kayıt, tablo almak veya kayıt kümesini temsil eden sorgu gerçekleştirme açılır.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Parametreler

*nOpenType*<br/>
Varsayılan değer, AFX_DB_USE_DEFAULT_TYPE ya da aşağıdakilerden birini değerleri kullanmak kabul `enum OpenType`:

- `CRecordset::dynaset` İki yönlü kaydırma ile bir kayıt kümesi. Üyelik ve kayıtları sıralama kayıt kümesi açıldı, ancak veri değerleri için diğer kullanıcılar tarafından yapılan değişiklikler, aşağıdaki getirme işlemi görülebilir belirlenir. Dynaset'ler dynasets'te kayıt kümeleri de verilir.

- `CRecordset::snapshot` İki yönlü kaydırma ile statik bir kayıt. Kayıt kümesi açıldığında, üyelik ve kayıtları sıralama belirlenir; veri değerleri, kayıtları getirilen olduğunda belirlenir. Kayıt kümesi kapatılıp yeniden açıldığında kadar diğer kullanıcılar tarafından yapılan değişiklikleri görünür değildir.

- `CRecordset::dynamic` İki yönlü kaydırma ile bir kayıt kümesi. Üyelik, sipariş ve veri değerleri için diğer kullanıcılar tarafından yapılan değişiklikler, aşağıdaki getirme işlemi görülebilir. Bu tür bir kayıt kümesi birçok ODBC sürücüleri desteklemez unutmayın.

- `CRecordset::forwardOnly` Sadece ileri kaydırma ile salt okunur kayıt.

     İçin `CRecordset`, varsayılan değer `CRecordset::snapshot`. Varsayılan değer mekanizması sağlar hem ODBC ile etkileşim kurmak Visual C++ sihirbazları `CRecordset` ve DAO `CDaoRecordset`, varsayılan değerleri farklı olan.

Bu kayıt türleri hakkında daha fazla bilgi için bkz [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). Makaleyi "Kullanarak blok ve kaydırılabilir imleçler" Windows SDK'sı ilgili bilgi için bkz.

> [!CAUTION]
>  İstenen türü desteklenmiyorsa framework özel durum oluşturur.

*lpszSQL*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- Bir NULL işaretçi.

- Bir tablonun adı.

- Bir SQL **seçin** deyimi (isteğe bağlı olarak bir SQL ile **burada** veya **ORDER BY** yan tümcesi).

- A **çağrı** (saklı yordam) önceden tanımlanmış sorgu adı belirterek deyimi. Küme ayracı arasında boşluk yerleştirmeyin dikkatli olun ve **çağrı** anahtar sözcüğü.

Bu dize hakkında daha fazla bilgi için tablo ve açıklamalar altında ClassWizard'ın rolünün tartışmaya bakın.

> [!NOTE]
>  Sonuç kümenizi sütunların sırasını RFX eşleşmesi gerekir ya da toplu RFX işlev çağrıları, [DoFieldExchange](#dofieldexchange) veya [DoBulkFieldExchange](#dobulkfieldexchange) geçersiz kılma işlevi.

*dwOptions*<br/>
Aşağıda listelenen değerlerinin bir birleşimini belirtebileceğiniz bir bit maskesi. Bunlardan bazıları birbirini dışlar. Varsayılan değer **hiçbiri**.

- `CRecordset::none` Hiçbir seçenek ayarlanmadı. Diğer tüm değerler ile birbirini dışlayan Bu parametre değeridir. Varsayılan olarak, kayıt kümesi ile güncelleştirilebilir [Düzenle](#edit) veya [Sil](#delete) ve yenileriyle ekleme sağlayan [AddNew](#addnew). Güncelleştirilebilirlik bağlıdır veri kaynağında da itibariyle *nOpenType* seçeneği belirtirsiniz. En iyi duruma getirme toplu ekleme kullanılamaz. Toplu satır getirme gerçekleştirilmez. Silinmiş kayıtlar, kayıt kümesi gezinti sırasında atlandı değildir. Yer işaretleri kullanılabilir değil. Otomatik kirli alan denetimi gerçekleştirilir.

- `CRecordset::appendOnly` İzin verme `Edit` veya `Delete` kayıt üzerinde. İzin `AddNew` yalnızca. Bu seçenek ile birbirini dışlayan `CRecordset::readOnly`.

- `CRecordset::readOnly` Kayıt kümesi salt okunur olarak açın. Bu seçenek ile birbirini dışlayan `CRecordset::appendOnly`.

- `CRecordset::optimizeBulkAdd` Tek seferde çok sayıda kayıt ekleme iyileştirmek için hazırlanmış bir SQL deyimini kullanın. Yalnızca ODBC API işlevini kullanmıyorsanız geçerlidir `SQLSetPos` kayıt kümesini güncelleştirmek için. Hangi alanların kirli olarak işaretlenmiş ilk güncelleştirme belirler. Bu seçenek ile birbirini dışlayan `CRecordset::useMultiRowFetch`.

- `CRecordset::useMultiRowFetch` Bir tek getirme işleminde alınacak birden çok satır izin vermek için toplu satır getirme uygulayın. Bu, performansı iyileştirmek için tasarlanmış, Gelişmiş bir özelliktir; Ancak, toplu kayıt alanı değişimi ClassWizard tarafından desteklenmiyor. Bu seçenek ile birbirini dışlayan `CRecordset::optimizeBulkAdd`. Belirtirseniz unutmayın `CRecordset::useMultiRowFetch`, ardından seçeneği `CRecordset::noDirtyFieldCheck` otomatik olarak kapatılacak (iki kez arabelleğe alma kullanılabilir olmayacak); üzerinde salt iletme kayıt kümeleri, seçeneği `CRecordset::useExtendedFetch` otomatik olarak kapatılacak. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords` Tüm silinen kayıtlar, kayıt kümesi içinde gezindiğinizde atlayın. Bu, belirli göreli öğesinden performansı düşürür. Bu seçenek yalnızca iletme kayıt kümeleri üzerinde geçerli değil. Eğer [taşıma](#move) ile *nRows* parametresi 0 olarak ayarlayın ve `CRecordset::skipDeletedRecords` seçenek kümesi, `Move` assert. Unutmayın `CRecordset::skipDeletedRecords` benzer *sürücü paketleme*, silinen satır anlamına kayıt kümesinden kaldırılır. Ancak, kayıtları, sürücü paketleri, sildiğiniz kayıtları atla; kayıt kümesi açıkken, diğer kullanıcılar tarafından silinen kayıtlar atlayın değil. `CRecordset::skipDeletedRecords` diğer kullanıcılar tarafından silinmiş satırları atlar.

- `CRecordset::useBookmarks` Yer işaretleri destekleniyorsa, kayıt kümesi üzerinde kullanabilir. Yer işaretleri, veri alma yavaş ancak veri gezinme için performansı. Salt iletme kayıt kümeleri üzerinde geçerli değil. Daha fazla bilgi için bkz [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- `CRecordset::noDirtyFieldCheck` (İki kez arabelleğe alma) denetleniyor otomatik kirli alan devre dışı bırakın. Bu, performansı iyileştirir; Ancak, el ile alanları kirli olarak çağırarak işaretlemelisiniz `SetFieldDirty` ve `SetFieldNull` üye işlevleri. Sınıfta çift o arabelleğe almayı unutmayın `CRecordset` iki sınıfta kez arabelleğe alma için benzer `CDaoRecordset`. Bununla birlikte, `CRecordset`, tek tek alanlarda iki kez arabelleğe alma etkinleştirilemiyor; tüm alanlar için etkinleştirmek veya tüm alanlar için devre dışı bırakın. Seçeneğini belirtirseniz unutmayın `CRecordset::useMultiRowFetch`, ardından `CRecordset::noDirtyFieldCheck` kapatılacak otomatik olarak; ancak `SetFieldDirty` ve `SetFieldNull` toplu satır getirme uygulayan kümelerinde kullanılamaz.

- `CRecordset::executeDirect` Hazırlanmış bir SQL deyimi kullanmayın. Daha iyi performans için bu seçeneği belirtin `Requery` üye işlev hiçbir zaman çağrılır.

- `CRecordset::useExtendedFetch` Uygulama `SQLExtendedFetch` yerine `SQLFetch`. Bu işlem, toplu satır salt iletme kayıt kümeleri getirme uygulamak için tasarlanmıştır. Seçeneğini belirtirseniz `CRecordset::useMultiRowFetch` salt iletme kayıt kümesinde, ardından `CRecordset::useExtendedFetch` otomatik olarak kapatılacak.

- `CRecordset::userAllocMultiRowBuffers` Kullanıcı verilerini depolama arabelleği ayırır. Bu seçeneği ile birlikte kullanarak `CRecordset::useMultiRowFetch` kendi depolama; ayırmak istiyorsanız Aksi takdirde, framework otomatik olarak gereken depolama alanı ayırır. Daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Bu belirleme unutmayın `CRecordset::userAllocMultiRowBuffers` belirtmeden `CRecordset::useMultiRowFetch` başarısız bir onaylama işlemi neden olur.

### <a name="return-value"></a>Dönüş Değeri

Yalnız `CRecordset` nesne başarıyla açıldı; Aksi durumda 0 ise [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (çağrılırsa) 0 değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevi çağırmanız gerekir. Çağırmadan önce `Open`, kayıt kümesi nesnesi oluşturmalıdır.

Kayıt kümesi çağırmadan önce nasıl oluşturmak bu kümesinin bağlantı veri kaynağına bağlıdır `Open`. Geçirirseniz bir [CDatabase](../../mfc/reference/cdatabase-class.md) nesnesini veri kaynağına bağlı olmayan bir kayıt kümesi oluşturucusu için bu üye işlevi kullanır [GetDefaultConnect](#getdefaultconnect) veritabanı nesnesi denemek için. Kayıt kümesi oluşturucuya NULL geçirirseniz, oluşturucu oluşturur bir `CDatabase` nesne, için ve `Open` veritabanı nesnesi bağlanmayı dener. Kayıt kümesi ve bu çeşitli koşullar altında bağlantı kapatma hakkında daha fazla bilgi için bkz [Kapat](#close).

> [!NOTE]
>  Bir veri kaynağı erişimi bir `CRecordset` nesne her zaman paylaşılır. Farklı `CDaoRecordset` sınıfı kullanamaz bir `CRecordset` bir veri kaynağına özel erişim ile açmak için nesne.

Çağırdığınızda `Open`, genellikle bir SQL sorgu **seçin** deyimi, kayıtları aşağıdaki tabloda belirtilen ölçütlere göre seçer.

|LpszSQL parametresinin değeri|Seçilen kayıt tarafından belirlenir|Örnek|
|------------------------------------|----------------------------------------|-------------|
|NULL|Tarafından döndürülen dize `GetDefaultSQL`.||
|SQL tablo adı|Tablo listesinde tüm sütunları `DoFieldExchange` veya `DoBulkFieldExchange`.|`"Customer"`|
|Önceden tanımlanmış sorgu (saklı yordam) adı|Sorgu döndürmek için tanımlanan sütunları.|`"{call OverDueAccts}"`|
|**SEÇİN** sütun listesi **FROM** Tablo listesi|Belirtilen tablo belirtilen sütunları.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
>  Ek boşluk SQL dizenizi eklemeyin dikkat edin. Örneğin, küme ayracı arasında boşluk ekleyin ve **çağrı** anahtar sözcüğü, MFC SQL dizesi olarak bir tablo adı hatalı yorumlayan ve içine dahil edilip derecelendirilir bir **seçin** sonuçlanır deyimi, bir oluşturulan özel durum. Önceden tanımlanmış sorgunuzu çıkış parametresi kullanıyorsa, küme ayracı arasında boşluk benzer şekilde, eklemeyin ve '' simgesi. Son olarak, küme ayracı önce boşluk eklemeniz gerekir değil bir **çağrı** deyimi veya önce **seçin** anahtar sözcüğü bir **seçin** deyimi.

NULL olarak geçirmek için normal yordamdır `Open`; bu durumda, `Open` çağrıları [GetDefaultSQL](#getdefaultsql). Türetilmiş kullanıyorsanız `CRecordset` sınıfı `GetDefaultSQL` ClassWizard içinde belirttiğiniz tablo adlarını sağlar. Bunun yerine diğer bilgileri belirtebilirsiniz `lpszSQL` parametresi.

İnovasyonunuz ne olursa olsun, geçirdiğiniz, `Open` sorgu için son SQL dizesi oluşturur (SQL dizesi olabilir **burada** ve **ORDER BY** yan tümceleri eklenmiş için `lpszSQL` , geçirilen dize) ve ardından yürütür Sorgu. Çağırarak oluşturulmuş dize inceleyebilirsiniz [GetSQL](#getsql) arama sonra *`Open`. Kayıt kümesi bir SQL deyimi oluşturur ve kayıt seçer hakkında ek ayrıntılar için bkz. makaleyi [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

Kayıt kümesi sınıfınızın alan veri üyeleri, seçili veri sütunlarının bağlıdır. Hiçbir kayıt döndürülmezse, ilk kayıt geçerli kayıt haline gelir.

Kayıt kümesi gibi bir filtre veya sıralama seçeneklerini ayarlamak isterseniz kayıt kümesi nesnesi oluşturduktan sonra ancak çağırmadan önce bunları belirlemenin `Open`. Sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız recordset zaten açık olan, çağrı [Requery](#requery).

Ek örnekler de dahil olmak üzere daha fazla bilgi için makalelere göz atın [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), ve [kayıt kümesi: oluşturma ve kapatma Kayıt kümeleri (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Örnek

Aşağıdaki kod örnekleri, farklı formlarda gösterilen `Open` çağırın.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset

Veri ve geçerli satır kümesindeki bir satır durumunu güncelleştirir.

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Bir tabanlı konumu bir satır satır kümesi geçerli. Bu değer, sıfırdan satır boyutu değişebilir.

*wLockType*<br/>
Bunu yenilendikten satır kilitleme belirten bir değer. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

İçin sıfır değeri geçirirseniz *wRow*, ardından her bir satır kümesinde yenilenir.

Kullanılacak `RefreshRowset`, belirterek toplu satır getirme uygulanan gerekir `CRecordset::useMulitRowFetch` seçeneğini [açık](#open) üye işlevi.

`RefreshRowset` ODBC API işlevini çağıran `SQLSetPos`. *WLockType* parametresinin belirttiği sonuna satır kilidi durumunu `SQLSetPos` yürütüldü. Aşağıdaki tabloda olası değerleri açıklanmaktadır *wLockType*.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı önce olduğu gibi satır aynı kilitli veya kilidi açılmış durumda olmasını sağlar. `RefreshRowset` çağrıldı.|
|SQL_LOCK_EXCLUSIVE|Satır bir sürücü veya veri kaynağı özel olarak kilitler. Bu tür bir kilit tüm veri kaynaklarını destekler.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı, satır kilidini açar. Bu tür bir kilit tüm veri kaynaklarını destekler.|

Hakkında daha fazla bilgi için `SQLSetPos`, Windows SDK'sı bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="requery"></a>  CRecordset::Requery

(Yenileme) oluşturur. bir kayıt kümesi.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi başarıyla yeniden oluşturuldu olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Hiçbir kayıt döndürülmezse, ilk kayıt geçerli kayıt haline gelir.

Ekleme ve veri kaynağına, sizin veya diğer kullanıcıların kuran silme işlemleri yansıtacak şekilde kayıt kümesi için sırada çağırarak kayıt derlemelisiniz `Requery`. Kayıt kümesi bir dinamik ise, sizin veya diğer kullanıcıların, var olan kayıtların (ancak değil eklemeleri) olun güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntüyse çağırmalısınız `Requery` düzenlemeleri diğer kullanıcıların yanı sıra ekleme ve silme işlemleri tarafından yansıtmak için.

Bir dinamik veya bir anlık görüntü için çağrı `Requery` yeni bir filtre veya sıralama ya da yeni parametre değerlerini kullanarak kayıt kümesini yeniden oluşturmak için istediğiniz zaman. İçin yeni değerler atayarak yeni bir filtre veya sıralama özelliğini ayarlayın `m_strFilter` ve `m_strSort` çağırmadan önce `Requery`. Parametre veri üyeleri çağırmadan önce yeni değerler atayarak yeni parametreler Ayarla `Requery`. Filtreleme ve sıralama dizeleri aynıdır, sorgu performansı geliştirir yeniden kullanabilirsiniz.

Kayıt yeniden deneme başarısız olursa, kayıt kapatılır. Çağırmadan önce `Requery`, kayıt çağırarak yeniden olup olmadığını belirlemek `CanRestart` üye işlevi. `CanRestart` garanti etmez `Requery` başarılı olur.

> [!CAUTION]
>  Çağrı `Requery` yalnızca çağrısı yapmanız sonrasında [açık](#open).

### <a name="example"></a>Örnek

Bu örnekte, farklı bir sıralama düzeni uygulamak için bir kayıt oluşturur.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition

Belirtilen kayıt numarasına karşılık gelen kayıt kayıt kümesini yerleştirir.

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Parametreler

*nRows*<br/>
Bir tabanlı sıralı konumu için geçerli kayıt kümesinde.

### <a name="remarks"></a>Açıklamalar

`SetAbsolutePosition` Bu sıralı konumlarına göre geçerli kayıt işaretçisi taşır.

> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri üzerinde geçerli değil.

ODBC kayıt kümeleri için ilk kayıt kümesinde bir mutlak konumu ayarı 1'in başvurduğu; dosya başına (BOF) konumu için 0 ayarı gösterir.

Negatif değerleri de geçirebilirsiniz `SetAbsolutePosition`. Bu durumda kayıt kümesinin konumu kayıt sonundan değerlendirilir. Örneğin, `SetAbsolutePosition( -1 )` son kaydını kayıt kümesindeki geçerli kayıt işaretçisine taşır.

> [!NOTE]
>  Mutlak konumu, bir yedek kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri hala korur ve sonraki önceki kayıtları silinen bir kaydın konumu değişiklikler belirli bir konuma döndürerek için önerilen yoldur. Ayrıca, bir SQL deyimi kullanarak bir oluşturulmadıkçabirkayıtiçindekitektekkayıtlarısıralamasınıkesindeğildirçünkükayıtyenidenyenidenoluşturulursa,belirlibirkaydıaynımutlakkonumunusahipolacağınıgarantiedilemez**ORDER BY** yan tümcesi.

Kayıt kümesi gezinti ve yer işaretleri hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="setbookmark"></a>  CRecordset::SetBookmark

Kayıtta belirtilen yer işareti içeren kayıt kümesini yerleştirir.

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) belirli bir kaydı için yer işareti değeri içeren nesne.

### <a name="remarks"></a>Açıklamalar

Yer işaretleri kayıt kümesinde desteklenip desteklenmediğini belirlemek için çağrı [CanBookmark](#canbookmark). Destekleniyorsa yer işaretleri kullanılabilir hale getirmek için ayarlamalısınız `CRecordset::useBookmarks` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi.

> [!NOTE]
>  Yer işaretleri desteklenmeyen veya kullanılamıyor, çağırma `SetBookmark` oluşturulan bir özel durumu oluşur. Yer işaretleri salt iletme kayıt kümeleri desteklenmez.

Yer işareti için geçerli kayıt ilk almak için arama [GetBookmark](#getbookmark), yer işareti değeri kaydeder bir `CDBVariant` nesne. Çağırarak kayda daha sonra geri dönebilirsiniz `SetBookmark` kaydedilmiş bu yer işaretini değerini kullanarak.

> [!NOTE]
>  Belirli kayıt işlemlerinden sonra yer işareti Kalıcılık çağırmadan önce denetlemelisiniz `SetBookmark`. Örneğin, bir yer işareti ile alırsanız `GetBookmark` ve sonra çağrı `Requery`, yer işareti artık geçerli olmayabilir. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenli bir şekilde çağırıp çağırmayacağınızı denetlenecek `SetBookmark`.

Yer işaretleri ve kayıt kümesi Gezinti hakkında daha fazla bilgi için makalelere göz atın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty

Alan veri üyesi kümesinin değiştirilmiş veya değişmemiş olarak işaretler.

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Kayıt kümesi veya NULL bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL değil Null ile aynı veritabanı terminolojisinde, "herhangi bir değere sahip." anlamına gelir)

*bDirty*<br/>
"(Değiştirilmiş) kirli olarak" işaretlenmesini alan veri üyesi ise, TRUE. "(Değişmeden) temiz olarak" işaretlenmesini alan veri üyesi ise, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değişmemiş olarak işaretleme alanı güncelleştirilmez ve az SQL trafiğini sonuçlarını sağlar.

> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, ardından uyguladıysanız `SetFieldDirty` başarısız bir onaylama işlemi neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Framework işaretleri alan veri üyeleri, veri kaynağında kayıt kayıt alanı değişimi (RFX) mekanizması tarafından yazılır emin olmak için değiştirildi. Genellikle bir alanın değerini değiştirme alanı kirli otomatik olarak ayarlar, nadiren çağırmanız gerekir böylece `SetFieldDirty` kendiniz, ancak bazen isteyebileceğiniz sütunları açıkça güncelleştirildi veya kaldırılacak alanı verileri hangi değeri bağımsız olarak eklenen emin emin olmak üye.

> [!CAUTION]
>  Yalnızca çağrısı yapmanız sonrasında bu üye işlevi çağrısı [Düzenle](#edit) veya [AddNew](#addnew).

İşlevinin ilk bağımsız değişkeni yalnızca işlev geçerlidir NULL kullanarak `outputColumn` alanları değil `param` alanları. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca ayarlar `outputColumn` null; alanlar `param` alanları etkilenmez.

Üzerinde çalışılacak `param` alanları, ayrı ayrı gerçek adresi sağlamanız gerekir `param` gibi çalışmak istediğiniz:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Yani tüm ayarlayamıyor `param` ile yapabildiğiniz gibi alanları NULL olarak `outputColumn` alanları.

##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull

Kayıt alanı veri üyesi (özellikle hiçbir değer yok) Null veya boş olmayan olarak işaretler.

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Kayıt kümesi veya NULL bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL değil Null ile aynı veritabanı terminolojisinde, "herhangi bir değere sahip." anlamına gelir)

*bNull*<br/>
Alan veri üyesi değeri (Null) sahip olarak işaretlenen ise sıfır olmayan. Null olmayan işaretlenmesine alan veri üyesi ise, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yeni bir kayıt için bir kayıt kümesi eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlayın ve "(değiştirilmiş) kirli olarak" bayrak. Bir veri kaynağındaki bir kaydı aldığınızda, sütunlarını ya da zaten değerlere sahip veya Null.

> [!NOTE]
>  Bu üye işlevi, toplu satır getirme kullanarak kümelerinde çağırmayın. Toplu satır getirme uyguladıysanız, çağırma `SetFieldNull` sonuçları başarısız bir onaylama işlemi. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Özel bir alan geçerli kaydın çağrısı bir değer olmaması olarak atamak istiyorsanız `SetFieldNull` ile *bNull* boş olarak işaretlemek için TRUE olarak ayarlayın. Bir alan daha önce Null olarak işaretlendi ve artık bir değeri vermek istiyorsanız, yeni değeri ayarlamanız yeterlidir. Null bayrağıyla kaldırmak zorunda değilsiniz `SetFieldNull`. Alan Null olmasına izin verilip verilmeyeceğini belirlemek için çağrı `IsFieldNullable`.

> [!CAUTION]
>  Yalnızca çağrısı yapmanız sonrasında bu üye işlevi çağrısı [Düzenle](#edit) veya [AddNew](#addnew).

İşlevinin ilk bağımsız değişkeni yalnızca işlev geçerlidir NULL kullanarak `outputColumn` alanları değil `param` alanları. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

yalnızca ayarlar `outputColumn` null; alanlar `param` alanları etkilenmez.

Üzerinde çalışılacak `param` alanları, ayrı ayrı gerçek adresi sağlamanız gerekir `param` gibi çalışmak istediğiniz:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Yani tüm ayarlayamıyor `param` ile yapabildiğiniz gibi alanları NULL olarak `outputColumn` alanları.

> [!NOTE]
>  Parametreleri NULL, çağrı ayarlarken `SetFieldNull` önce kayıt onaylama açılan sonuçlanır. Bu durumda, çağrı [SetParamNull](#setparamnull).

`SetFieldNull` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).

##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode

"İyimser" (varsayılan) kilitleme ya da "kötümser" kilitleme Kilitleme modunu ayarlar. Kayıtların güncelleştirmeleri nasıl kilitlenip belirler.

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Parametreler

*nMode*<br/>
Aşağıdaki değerlerden birini içeren `enum LockMode`:

- `optimistic` İyimser kilitleme kilitler çağrı sırasında yalnızca güncelleştirilen kaydı `Update`.

- `pessimistic` Kötümser kilitleme kilitler kaydı hemen sonra `Edit` olarak adlandırılır ve tutar kadar kilitli `Update` çağrı tamamlanana veya yeni kayıt için taşıyın.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi güncelleştirmeleri kullanan iki kayıt kilitleme stratejileri belirtmek gerekirse, bu üye işlevini çağırın. Varsayılan olarak, kayıt kilitleme modudur `optimistic`. Daha dikkatli değiştirebilir miyim `pessimistic` stratejisi kilitleme. Çağrı `SetLockingMode` oluşturmak ve kayıt kümesi nesnesi açılamadı sonra ancak çağırmadan önce `Edit`.

##  <a name="setparamnull"></a>  CRecordset::SetParamNull

Bir parametre (özellikle hiçbir değer yok) Null veya boş olmayan olarak işaretler.

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Parametre sıfır tabanlı dizini.

*bNull*<br/>
Değilse (varsayılan değer) TRUE, parametre Null olarak işaretlenir. Aksi takdirde, parametre Null olmayan işaretlenir.

### <a name="remarks"></a>Açıklamalar

Farklı [SetFieldNull](#setfieldnull), çağırabilirsiniz `SetParamNull` kayıt açılmadan.

`SetParamNull` genellikle önceden tanımlanmış sorgular (saklı yordamlar) kullanılır.

##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition

İmleç geçerli satır içinde bir satıra taşır.

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parametreler

*wRow*<br/>
Bir tabanlı konumu bir satır satır kümesi geçerli. Bu değer 1'den satır boyutunu değişebilir.

*wLockType*<br/>
Bunu yenilendikten satır kilitleme belirten değer. Ayrıntılar için açıklamalara bakın.

### <a name="remarks"></a>Açıklamalar

Toplu satır getirme uygularken kayıtları ilk kaydı getirilen satır kümesindeki geçerli kayıt olduğu satır kümeleri tarafından alınır. Geçerli kayıt başka bir kayıt satır içinde yapmak için çağrı `SetRowsetCursorPosition`. Örneğin, birleştirebilirsiniz `SetRowsetCursorPosition` ile [GetFieldValue](#getfieldvalue) veri kümeniz herhangi bir kayıttan dinamik olarak almak için üye işlevi.

Kullanılacak `SetRowsetCursorPosition`, belirterek toplu satır getirme uygulanan gerekir `CRecordset::useMultiRowFetch` seçeneği *dwOptions* parametresinde [açık](#open) üye işlevi.

`SetRowsetCursorPosition` ODBC API işlevini çağıran `SQLSetPos`. *WLockType* parametresinin belirttiği sonuna satır kilidi durumunu `SQLSetPos` yürütüldü. Aşağıdaki tabloda olası değerleri açıklanmaktadır *wLockType*.

|wLockType|Açıklama|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (varsayılan değer)|Sürücü veya veri kaynağı önce olduğu gibi satır aynı kilitli veya kilidi açılmış durumda olmasını sağlar. `SetRowsetCursorPosition` çağrıldı.|
|SQL_LOCK_EXCLUSIVE|Satır bir sürücü veya veri kaynağı özel olarak kilitler. Bu tür bir kilit tüm veri kaynaklarını destekler.|
|SQL_LOCK_UNLOCK|Sürücü veya veri kaynağı, satır kilidini açar. Bu tür bir kilit tüm veri kaynaklarını destekler.|

Hakkında daha fazla bilgi için `SQLSetPos`, Windows SDK'sı bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize

Getirme sırasında almak istediğiniz kayıt sayısını belirtir.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Parametreler

*dwNewRowsetSize*<br/>
Belirli bir getirme sırasında almak için satır sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sanal üye işlevi, tek bir getirme sırasında toplu satır getirme kullanırken almak istediğiniz kaç satır belirtir. Toplu satır getirme uygulamak için ayarlamalısınız `CRecordset::useMultiRowFetch` seçeneğini *dwOptions* parametresinin [açık](#open) üye işlevi.

> [!NOTE]
>  Çağırma `SetRowsetSize` uygulamadan toplu satır getirme başarısız bir onaylama işlemi içinde neden olur.

Çağrı `SetRowsetSize` çağırmadan önce `Open` başlangıçta kayıt satır kümesi boyutunu ayarlamak için. Toplu satır getirme uygularken varsayılan satır boyutu 25'tir.

> [!NOTE]
>  Çağırırken dikkatli `SetRowsetSize`. Depolama verilerini el ile ayırma varsa (belirtildiği gibi `CRecordset::userAllocMultiRowBuffers` bulunan dwOptions parametrenin seçeneği `Open`), çağırdıktan sonra bu depolama arabellekleri yeniden tahsis gerek olup olmadığını denetlemelisiniz `SetRowsetSize`, önce herhangi bir imleç gezinme işlemi gerçekleştirin.

Satır kümesi boyutu için geçerli ayarı almak için çağrı [GetRowsetSize](#getrowsetsize).

Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="update"></a>  CRecordset::Update

Tamamlanan bir `AddNew` veya `Edit` yeni veya düzenlenmiş verilerin veri kaynağında kaydederek işlemi.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kaydı başarıyla güncelleştirildi olursa sıfır dışı; Hiçbir sütun değiştirdiyseniz, aksi durumda 0. Hiçbir kayıt güncelleştirildi veya daha fazlası tek bir kayıtta güncelleştirildi, bir özel durum oluşturulur. Bir özel durum, veri kaynağında da bir durum için herhangi bir hata oluşturulur.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi çağrısı yapıldıktan sonra çağırma [AddNew](#addnew) veya [Düzenle](#edit) üye işlevi. Bu çağrı tamamlamak için gereken `AddNew` veya `Edit` işlemi.

> [!NOTE]
>  Toplu satır getirme uyguladıysanız çağıramazsınız `Update`. Bu başarısız bir onaylama işlemi neden olur. Ancak sınıf `CRecordset` mekanizması sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevlerinizi ODBC API işlevini kullanarak yazabileceğiniz `SQLSetPos`. Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Her ikisi de `AddNew` ve `Edit` eklendi veya düzenlenmiş verilerin yerleştirilir düzenleme arabelleği veri kaynağına kaydetmek için hazırlayın. `Update` verileri kaydeder. İşaretli veya değiştirilmiş olarak algılanan yalnızca bu alanları güncelleştirilir.

Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz `Update` çağırın (ve kendi ilişkili `AddNew` veya `Edit` çağrısı) bir işlemin bir parçası. İşlemler hakkında daha fazla bilgi için bkz [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

> [!CAUTION]
>  Eğer `Update` ilk ya da çağırma `AddNew` veya `Edit`, `Update` oluşturur bir `CDBException`. Eğer `AddNew` veya `Edit`, çağırmalısınız `Update` çağırmadan önce bir `Move` işlem veya kayıt veya veri kaynağı bağlantısı kapatmadan önce. Aksi takdirde, bildirim yapılmadan değişiklikleriniz kaybolur.

İşleme hakkında ayrıntılı bilgi için `Update` hataları, bkz makaleyi [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

### <a name="example"></a>Örnek

Makaleye göz atın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDatabase Sınıfı](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView Sınıfı](../../mfc/reference/crecordview-class.md)
