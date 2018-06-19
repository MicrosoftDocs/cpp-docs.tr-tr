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
ms.openlocfilehash: 683f1d612a57e4f6e2d8661af17faa73f725d3d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378741"
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
|[CRecordset::CRecordset](#crecordset)|Oluşturan bir `CRecordset` nesnesi. Türetilmiş sınıf bunu çağıran bir oluşturucu sağlamanız gerekir.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|Yeni bir kayıt eklemek için hazırlar. Çağrı `Update` eklenmesi tamamlamak için.|  
|[CRecordset::CanAppend](#canappend)|Yeni kayıtlar kayıt kümesine eklenebilir, sıfır olmayan döndürür `AddNew` üye işlevi.|  
|[CRecordset::CanBookmark](#canbookmark)|Yer işaretleri kayıt destekliyorsa, sıfır olmayan bir değer döndürür.|  
|[CRecordset::Cancel](#cancel)|Zaman uyumsuz bir işlem veya ikinci bir iş parçacığı işleminden iptal eder.|  
|[CRecordset::CancelUpdate](#cancelupdate)|Tüm bekleyen güncelleştirmeleri nedeniyle iptal eder bir `AddNew` veya `Edit` işlemi.|  
|[CRecordset::CanRestart](#canrestart)|Döndürür sıfır olmayan IF `Requery` kümesinin sorguyu yeniden çalıştırmak için çağrılır.|  
|[CRecordset::CanScroll](#canscroll)|Kayıtlarda kaydırırsanız, sıfır olmayan bir değer döndürür.|  
|[CRecordset::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır olmayan döndürür.|  
|[CRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilmiş sıfır olmayan döndürür (ekleyebilir, güncelleştirme veya kayıtlarını sil).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|Kayıt getirme sırasında oluşturulan hatalar işlemek üzere çağrılır.|  
|[CRecordset::Close](#close)|Kayıt kümesi ve ODBC kapatır **HSTMT** kendisiyle ilişkilendirilmiş.|  
|[CRecordset::Delete](#delete)|Geçerli kayıt kayıt kümesinden siler. Açıkça silindikten sonra başka bir kayıtla kaydırma gerekir.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Toplu satır kayıt kümesine veri kaynağından veri gönderip almak için çağrılır. Toplu kayıt alanı değişimi (Toplu RFX) olarak uygular.|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|Kayıt kümesi alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements alanı değişimi (RFX) kaydedin.|  
|[CRecordset::Edit](#edit)|Değişiklikler geçerli kayıt için hazırlar. Çağrı `Update` düzenlemeyi tamamlamak için.|  
|[CRecordset::FlushResultSet](#flushresultset)|Önceden tanımlanmış sorgu kullanırken alınması için başka bir sonuç ise sıfır olmayan döndürür ayarlayın.|  
|[CRecordset::GetBookmark](#getbookmark)|Bir kayıt yer işareti değeri parametresi nesneye atar.|  
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Varsayılan bağlantı dizesini almak için çağrılır.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Varsayılan SQL dizesi yürütülemedi almak için çağrılır.|  
|[CRecordset::GetFieldValue](#getfieldvalue)|Kayıt kümesinde bir alanın değerini döndürür.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Kayıt kümesinde alan sayısını döndürür.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Alanlar hakkında bilgi belirli türde bir kayıt döndürür.|  
|[CRecordset::GetRecordCount](#getrecordcount)|Kayıt kümesindeki kayıt sayısını döndürür.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|Tek bir getirme sırasında almak istediğiniz kayıt sayısını döndürür.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|Gerçek bir getirme sırasında alınan satır sayısını döndürür.|  
|[CRecordset::GetRowStatus](#getrowstatus)|Satır durumunu getirmeden sonra döndürür.|  
|[CRecordset::GetSQL](#getsql)|Kayıt kümesi kayıtları seçmek için kullanılan SQL dizesini alır.|  
|[CRecordset::GetStatus](#getstatus)|Kayıt kümesi durumunu alır: geçerli kaydı ve son kayıt sayısı bir olup elde dizini.|  
|[CRecordset::GetTableName](#gettablename)|Kayıt kümesi'ne temel tablosunun adını alır.|  
|[CRecordset::IsBOF](#isbof)|Kayıt kümesi önce ilk kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.|  
|[CRecordset::IsDeleted](#isdeleted)|Kayıt kümesi silinmiş bir kayda konumlandırıldı sıfır olmayan döndürür.|  
|[CRecordset::IsEOF](#iseof)|Kayıt kümesi sonra son kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|Geçerli kayıttaki belirtilen alanın değiştirdiyseniz sıfır olmayan bir değer döndürür.|  
|[CRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıt belirtilen alan null ise sıfır olmayan döndürür (değeri yok).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|Geçerli kayıttaki belirtilen alanın (hiçbir değer sahip) null olarak ayarlarsanız, sıfır olmayan bir değer döndürür.|  
|[CRecordset::IsOpen](#isopen)|Döndürür sıfır olmayan IF `Open` daha önce çağrılır.|  
|[CRecordset::Move](#move)|Kayıt kümesi belirli bir kayıt sayısı için her iki yönde geçerli kayıttaki yerleştirir.|  
|[CRecordset::MoveFirst](#movefirst)|İlk kaydı kayıt kümesindeki geçerli kayıt yerleştirir. İçin test `IsBOF` ilk.|  
|[CRecordset::MoveLast](#movelast)|Geçerli kayıt son kaydı veya son satır yerleştirir. İçin test `IsEOF` ilk.|  
|[CRecordset::MoveNext](#movenext)|Geçerli kayıt sonraki kaydı veya sonraki satır yerleştirir. İçin test `IsEOF` ilk.|  
|[CRecordset::MovePrev](#moveprev)|Geçerli kayıt önceki kaydın veya önceki satır yerleştirir. İçin test `IsBOF` ilk.|  
|[CRecordset::OnSetOptions](#onsetoptions)|(Seçimini kullanılır) seçeneklerini ayarlamak için belirtilen ODBC deyim için çağrılır.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|İçin belirtilen ODBC deyimini (güncelleştirme kullanılır) seçeneklerini ayarlamak için çağrılır.|  
|[CRecordset::Open](#open)|Kayıt kümesi tablo alma veya kayıt kümesini temsil eden sorgu gerçekleştirme açar.|  
|[CRecordset::RefreshRowset](#refreshrowset)|Veri ve belirtilen satırlara durumunu yeniler.|  
|[CRecordset::Requery](#requery)|Seçili kayıtları yeniden yenilemek için kümesinin sorgusunu çalıştırır.|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Belirtilen kayıt sayısı için karşılık gelen kayıt kayıt yerleştirir.|  
|[CRecordset::SetBookmark](#setbookmark)|Yer işareti tarafından belirtilen kayıtta kayıt yerleştirir.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıt belirtilen alan değiştirilmiş olarak işaretler.|  
|[CRecordset::SetFieldNull](#setfieldnull)|Null (hiçbir değer sahip) için geçerli kayıttaki belirtilen alanın değerini ayarlar.|  
|[CRecordset::SetLockingMode](#setlockingmode)|"İyimser" (varsayılan) kilitleme ya da "kötümser" kilitleme Kilitleme modunu ayarlar. Güncelleştirmeleri kayıtların nasıl kilitlenmiş belirler.|  
|[CRecordset::SetParamNull](#setparamnull)|Belirtilen parametre null (hiçbir değer sahip) ayarlar.|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Satır kümesi içinde belirtilen satırda imleci yerleştirir.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|Getirme sırasında almak istediğiniz kayıt sayısını belirtir.|  
|[CRecordset::Update](#update)|Tamamlanan bir `AddNew` veya `Edit` veri kaynağı üzerinde yeni veya düzenlenen veriler kaydederek işlemi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|Kayıt kümesi için ODBC deyim tanıtıcısı içerir. Türü `HSTMT`.|  
|[CRecordset::m_nFields](#m_nfields)|Alan veri üyeleri kümesinde sayısını içerir. Türü `UINT`.|  
|[CRecordset::m_nParams](#m_nparams)|Parametre veri üyeleri kümesinde sayısını içerir. Türü `UINT`.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|Bir işaretçi içeriyor `CDatabase` üzerinden kayıt bağlı bir veri kaynağı nesnesi.|  
|[CRecordset::m_strFilter](#m_strfilter)|İçeren bir `CString` yapılandırılmış sorgu dili (SQL) belirleyen `WHERE` yan tümcesi. Yalnızca belirli ölçütlere uyan kayıtları seçmek için filtre olarak kullanılır.|  
|[CRecordset::m_strSort](#m_strsort)|İçeren bir `CString` bir SQL belirleyen `ORDER BY` yan tümcesi. Kayıtların nasıl sıralandığını denetlemek için kullanılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Kayıt kümeleri," bilinen `CRecordset` nesneleri genellikle iki formlarında kullanılan: dinamik kümeler ve anlık görüntüler. Bir dinamik diğer kullanıcılar tarafından yapılan veri Güncelleştirmeler ile eşitlenmiş kalır. Statik bir görünüm verilerin bir anlık görüntüdür. Her form kayıt açıldığında sabit kayıt kümesini temsil eder, ancak dinamik küme içindeki bir kayıt kaydırma yaptığınızda kayda diğer kullanıcılar tarafından veya diğer kayıt kümeleri, uygulamanızın içinde tarafından yapılmış değişiklikleri yansıtır.  
  
> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, bir sınıf kullanma [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) yerine. Daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).  
  
 Her iki tür bir kayıt kümesi ile çalışmak için genellikle bir uygulamaya özgü kayıt kümesi sınıfından türetilen `CRecordset`. Kayıt kümeleri kayıtları veri kaynağını seçin ve sonra şunları yapabilirsiniz:  
  
-   Kayıtlarında gezinin.  
  
-   Kayıtları güncelleştirmek ve kilitleme modunu belirtin.  
  
-   Veri kaynağı üzerinde kullanılabilir olanlardan seçer kaydeden sınırlamak için kayıt kümesi filtreleyin.  
  
-   Kayıt kümesi sıralayın.  
  
-   Çalışma zamanına kadar bilinmiyor bilgilerle kendi seçimi özelleştirmek için kayıt kümesini parametreleştirme.  
  
 Sınıfınızda kullanmak için bir veritabanı açın ve bir işaretçi Oluşturucusu geçirme bir kayıt kümesi nesnesi oluşturun, `CDatabase` nesnesi. Ardından kayıt kümesinin çağıran **açık** nesnesinin bir dynaset veya bir anlık görüntü olup belirtebileceğiniz üye işlevi. Çağırma **açık** veri kaynağından verileri seçer. Kayıt kümesi nesnesi açıldıktan sonra üye işlevleri ve veri üyelerine kayıtlarda kaydırma ve bunlar üzerinde çalıştırmak için kullanın. Güncelleştirilebilir veya salt okunur olup olmadığını kullanılabilir işlemleri nesne bir dynaset veya bir anlık görüntü olmasına göre değişir (açık veritabanı bağlantısı (ODBC) veri kaynağının yeteneğini bağlıdır), ve olup toplu satır getirme uyguladık. Değiştirilmiş veya bu yana eklenen kayıtları yenilemek için **açık** çağrısı, nesnenin çağrısı **Requery** üye işlevi. Nesnenin çağrı **Kapat** üye işlev ve ile işiniz bittiğinde nesneyi yok.  
  
 Türetilen bir `CRecordset` sınıfı, kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Toplu RFX) okuma ve kayıt alanlarının güncelleştirme desteklemek için kullanılır.  
  
 Kayıt kümeleri ve kayıt alanı değişimi hakkında daha fazla bilgi için makalelerine bakın [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md), [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: Kayıtları toplu (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), ve [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md). Dinamik kümeler ve anlık görüntüler bir odak için makalelerine bakın [Dynaset](../../data/odbc/dynaset.md) ve [anlık görüntü](../../data/odbc/snapshot.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdb.h  
  
##  <a name="addnew"></a>  CRecordset::AddNew  
 Yeni bir kayıt tablosuna eklemek için hazırlar.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız [Requery](#requery) yeni eklenen kaydın görmek için üye işlevi. Kaydın alanları başlangıçta Null. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve aynı değil **NULL** c++.) İşlemi tamamlamak için çağırmalısınız [güncelleştirme](#update) üye işlevi. **Güncelleştirme** veri kaynağına yaptığınız değişiklikleri kaydeder.  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız `AddNew`. Bu başarısız bir onaylama neden olacaktır. Ancak sınıfı `CRecordset` bir mekanizma sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevleri ODBC API işlevini kullanarak yazabilirsiniz **SQLSetPos**. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `AddNew` kayıt kümesinin alan veri üyeleri kullanarak yeni, boş bir kayıt hazırlar. Çağırdıktan sonra `AddNew`, kayıt kümesinin alan veri üyeleri istediğiniz değerleri ayarlayın. (Çağrı gerekmez [Düzenle](#edit) üye işlevi bu amaçla; kullanım **Düzenle** yalnızca var olan kayıtlar için.) Daha sonra çağırdığınızda **güncelleştirme**, değiştirilen alan veri üyeleri değerleri, veri kaynağında kaydedilir.  
  
> [!CAUTION]
>  Çağırmadan önce yeni bir kayıt kaydırma varsa **güncelleştirme**, yeni kayıttaki kaybolur ve herhangi bir uyarı verilir.  
  
 Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz, `AddNew` çağrısı bir işlemin parçası. İşlemler hakkında daha fazla bilgi için bkz [CDatabase](../../mfc/reference/cdatabase-class.md). Çağırmalısınız Not [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağırmadan önce `AddNew`.  
  
> [!NOTE]
>  Dinamik kümeler için yeni kayıtlar kayıt kümesine son kayıt olarak eklenir. Eklenen kayıtlar için anlık görüntü eklenmez; çağırmalısınız **Requery** kayıt yenilenecek.  
  
 Çağrı geçersiz `AddNew` bir kayıt kümesi için **açık** üye işlevi çağrılmadı. A `CDBException` çağırırsanız durum `AddNew` için eklenemiyor bir kayıt kümesi için. Çağırarak kayıt güncelleştirilebilir olup olmadığını belirlemek [CanAppend](#canappend).  
  
 Daha fazla bilgi için aşağıdaki makalelere bakın: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), ve [işlem () ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Örnek  
 Makalesine bakın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="canappend"></a>  CRecordset::CanAppend  
 Daha önce açılmış kayıt kümesi yeni kayıtlar eklemenize izin verip vermeyeceğini belirler.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni kayıtlar ekleme kayıt izin veriyorsa sıfır olmayan; Aksi takdirde 0. `CanAppend` kayıt kümesi salt okunur olarak açıldıysa 0 döndürür.  
  
##  <a name="canbookmark"></a>  CRecordset::CanBookmark  
 Kayıt kümesi, yer işaretlerini kullanma kayıtları işaretlemek izin verip vermeyeceğini belirler.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yer işaretleri kayıt destekliyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bağımsız olarak **CRecordset::useBookmarks** seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi. `CanBookmark` verilen ODBC sürücüsü ve imleç desteği yer işaretleri türü olup olmadığını gösterir. **CRecordset::useBookmarks** bunların desteklendiği sağlanan yer işaretleri kullanılabilir durumda olup olmadığını gösterir.  
  
> [!NOTE]
>  Yer işaretleri salt iletme kayıt kümeleri desteklenmez.  
  
 Yer işaretleri ve kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cancel"></a>  CRecordset::Cancel  
 Veri kaynağı zaman uyumsuz bir işlem devam ediyor veya ikinci bir iş parçacığı işleminden iptal istek sayısı.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Açıklamalar  
 MFC ODBC sınıfları artık zaman uyumsuz işleme kullandığını unutmayın; bir asychronous işlemi gerçekleştirmek için doğrudan ODBC API işlevini çağırmanız gerekir **SQLSetConnectOption**. Daha fazla bilgi için bkz: Konu "Yürütme işlevleri zaman uyumsuz olarak" *ODBC SDK Programcı Kılavuzu*.  
  
##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate  
 Bekleyen tüm güncelleştirmeleri nedeni, iptal bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi, önce [güncelleştirme](#update) olarak adlandırılır.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu üye işlevi böyle kayıt kümeleri çağrılamıyor beri toplu satır, getirme kullanarak kümelerinde uygulanamaz **Düzenle**, `AddNew`, veya **güncelleştirme**. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Otomatik kirli alan denetimi etkinse, `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir **Düzenle** veya `AddNew` ; tersi durumda, değer değişikliklerini kalır. Kayıt kümesi açıldığında, varsayılan olarak otomatik alan denetimi etkindir. Devre dışı bırakmak, belirtmelisiniz **CRecordset::noDirtyFieldCheck** içinde `dwOptions` parametresinin [açık](#open) üye işlevi.  
  
 Verileri güncelleştirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  
  
##  <a name="canrestart"></a>  CRecordset::CanRestart  
 Kayıt kümesi (kayıtlarını yenilemek için), sorgu çağırarak yeniden başlatmayı izin verip vermeyeceğini belirler **Requery** üye işlevi.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Requery izin verilip verilmediğini sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="canscroll"></a>  CRecordset::CanScroll  
 Kayıt kaydırma izin verip vermeyeceğini belirler.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kaydırma veriyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Makaleyi kaydırma hakkında daha fazla bilgi için bkz: [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cantransact"></a>  CRecordset::CanTransact  
 Kayıt işlemleri izin verip vermeyeceğini belirler.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt işlemleri veriyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>  CRecordset::CanUpdate  
 Kayıt kümesi güncelleştirme olup olmadığını belirler.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi güncelleştirilmiş sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayıt temel alınan veri kaynağı salt okunur olup olmadığını belirttiyseniz salt okunur olabilir **CRecordset::readOnly** içinde `dwOptions` kayıt açıldığında parametresi.  
  
##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError  
 Kayıt getirme sırasında oluşturulan hatalar işlemek üzere çağrılır.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRetCode`  
 Bir ODBC API işlevi dönüş kodu. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sanal üye işlevi kayıtları getirilen kullanırken oluşan hatalarını ele alır ve toplu satır getirme sırasında faydalıdır. Geçersiz kılma düşünmek isteyebilirsiniz `CheckRowsetError` kendi hata işleme uygulamak için.  
  
 `CheckRowsetError` bir imleç Gezinti işleminde gibi otomatik olarak çağrılır **açık**, **Requery**, veya tüm **taşıma** işlemi. ODBC API işlevinin dönüş değeri geçirilen **SQLExtendedFetch**. İçin olası değerler aşağıdaki tabloda listelenmektedir `nRetCode` parametresi.  
  
|nRetCode|Açıklama|  
|--------------|-----------------|  
|**SQL_SUCCESS**|İşlev başarıyla tamamlandı; ek bilgi yok kullanılabilir.|  
|**SQL_SUCCESS_WITH_INFO**|İşlev, büyük olasılıkla önemli olmayan bir hata ile tamamlandı. Ek bilgi elde edilebilir çağırarak **SQLError**.|  
|**SQL_NO_DATA_FOUND**|Sonuç Kümesi'den tüm satırlar getirildi.|  
|**SQL_ERROR HATASI**|İşlevi başarısız oldu. Ek bilgi elde edilebilir çağırarak **SQLError**.|  
|**SQL_INVALID_HANDLE**|İşlevi geçersiz ortam işleyici, bağlantı tanıtıcısı veya deyim tanıtıcısı nedeniyle başarısız oldu. Bu bir programlama hatası gösterir. Ek bilgi yok kullanılabilir **SQLError**.|  
|`SQL_STILL_EXECUTING`|Zaman uyumsuz olarak başlatıldığı bir işlev hala yürütüyor. Varsayılan olarak, MFC hiçbir zaman bu değere geçeceğini Not `CheckRowsetError`; MFC arama devam **SQLExtendedFetch** artık dönene kadar `SQL_STILL_EXECUTING`.|  
  
 Hakkında daha fazla bilgi için **SQLError**, Windows SDK konusuna bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="close"></a>  CRecordset::Close  
 Kayıt kümesi kapatır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 ODBC **HSTMT** ve tüm bellek kayıt kümesi için ayrılan framework serbest bırakıldı. Genellikle çağırdıktan sonra **Kapat**, ile ayırdığınızda C++ kayıt kümesi nesnesi silme **yeni**.  
  
 Çağırabilirsiniz **açık** çağırdıktan sonra yeniden **Kapat**. Bu, kayıt kümesi nesnesi yeniden kullanmanıza olanak sağlar. Alternatif çağırmaktır **Requery**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>  CRecordset::CRecordset  
 Oluşturan bir `CRecordset` nesnesi.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDatabase`  
 Bir işaretçi içeren bir `CDatabase` nesne veya değer **NULL**. Aksi takdirde **NULL** ve `CDatabase` nesnenin **açmak** veri kaynağına bağlanmak için üye işlevi çağrılmamışsa, kayıt kümesinin onu sizin için kendi sırasında açmaya çalıştığında **açın**  çağırın. Geçirirseniz **NULL**, `CDatabase` nesnesi oluşturulur ve belirtilen kayıt kümesi sınıfınız ClassWizard ile türetilmiş ne zaman veri kaynağı bilgileri kullanarak bağlandı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabilir `CRecordset` doğrudan veya bir uygulamaya özgü sınıfından türetilen `CRecordset`. Kayıt kümesi sınıflarınızı çıkarmaya ClassWizard kullanabilirsiniz.  
  
> [!NOTE]
>  Türetilmiş bir sınıf *gerekir* kendi Oluşturucusu sağlayın. Türetilmiş sınıf oluşturucu Oluşturucusu çağrı `CRecordset::CRecordset`, uygun parametreleri boyunca kendisine geçirme.  
  
 Geçirmek **NULL** , kayıt kümesi oluşturucuya sahip bir `CDatabase` nesnesi oluşturulur ve sizin için otomatik olarak bağlı. Bu, oluşturmak ve bağlamak gerektirmez yararlı bir toplu özelliktir bir `CDatabase` kayıt oluşturma önce nesnesi.  
  
### <a name="example"></a>Örnek  
 Daha fazla bilgi için bkz: [kayıt kümesi: bir tablo (ODBC için) bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
##  <a name="delete"></a>  CRecordset::Delete  
 Geçerli kaydı siler.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başarılı silindikten sonra kayıt kümesinin alan veri üyeleri bir Null değere ayarlanır ve açıkça birini çağırmalıdır **taşıma** silinmiş kayda için işlevleri. Silinen kayda sonra dönün mümkün değildir. Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz **silmek** çağrısı bir işlemin parçası. Daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız **silmek**. Bu başarısız bir onaylama neden olacaktır. Ancak sınıfı `CRecordset` bir mekanizma sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevleri ODBC API işlevini kullanarak yazabilirsiniz **SQLSetPos**. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir ve olmalıdır geçerli bir kayıt kayıt kümesindeki geçerli çağırdığınızda **silmek**; Aksi takdirde hata oluşur. Örneğin, bir kaydını silin, ancak çağırmadan önce yeni bir kayıt kaydırma değil **silmek** yeniden **silmek** oluşturur bir [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Farklı [AddNew](#addnew) ve [Düzenle](#edit), çağrı **silmek** yapılan bir çağrı tarafından izlenmeyen [güncelleştirme](#update). Varsa bir **silmek** çağrısı başarısız olursa, değişmeden üyeleri bırakılır alan verileri.  
  
### <a name="example"></a>Örnek  
 Bu örnek, bir işlev çerçeve üzerinde oluşturulan bir kayıt gösterir. Örnek varlığını varsayar `m_dbCust`, üye değişkeni türü `CDatabase` veri kaynağına zaten bağlı.  
  
 [!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange  
 Toplu satır kayıt kümesine veri kaynağından veri gönderip almak için çağrılır. Toplu kayıt alanı değişimi (Toplu RFX) olarak uygular.  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesi. Framework zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme uygulandığında framework otomatik olarak verileri veri kaynağından kayıt kümesi nesnesine aktarmak için bu üye işlevi çağırır. `DoBulkFieldExchange` Ayrıca, parametre veri üyeleri varsa kayıt kümesinin seçimi için SQL deyimi dizesi parametre yer tutucularını bağlar.  
  
 Toplu satır getirme uygulanmadıysa, framework çağırması [DoFieldExchange](#dofieldexchange). Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği `dwOptions` parametresinde [açık](#open) üye işlevi.  
  
> [!NOTE]
> `DoBulkFieldExchange` yalnızca türetilmiş bir sınıf kullanıyorsanız kullanılabilir `CRecordset`. Doğrudan kayıt kümesi nesnesi oluşturduysanız `CRecordset`, çağırmalısınız [GetFieldValue](#getfieldvalue) veri almak için üye işlevi.  
  
 Toplu kayıt alanı değişimi (Toplu RFX) kayıt alanı değişimi (RFX) benzer. Veri, kayıt kümesi nesnesi için veri kaynağı'ndan otomatik olarak aktarılır. Ancak, çağıramazsınız `AddNew`, **Düzenle**, **silmek**, veya **güncelleştirme** veri kaynağına yapılan değişiklikleri aktarmak için. Sınıf `CRecordset` şu anda veri; toplu satırlarını güncelleştirmek için bir mekanizma sağlamaz ODBC API işlevini kullanarak kendi işlevlerinizi ancak yazabilirsiniz **SQLSetPos**.  
  
 Not ClassWizard toplu kayıt alanı değişimi desteklemiyor; Bu nedenle, kılmalıdır `DoBulkFieldExchange` toplu RFX işlevleri çağrıları yazarak el ile. Bu işlevler hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).  
  
 Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Makaleyi ilgili bilgi için bkz [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange  
 Kayıt kümesi alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements alanı değişimi (RFX) kaydedin.  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesi. Framework zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme uygulanmadı, framework otomatik olarak kayıt kümesi nesnenizi alan veri üyeleri geçerli kayıt veri kaynağı için karşılık gelen sütunlara arasında veri değişimi için bu üye işlevi çağırır. `DoFieldExchange` Ayrıca, parametre veri üyeleri varsa kayıt kümesinin seçimi için SQL deyimi dizesi parametre yer tutucularını bağlar.  
  
 Toplu satır getirme uygulanmışsa framework çağırması [DoBulkFieldExchange](#dobulkfieldexchange). Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği `dwOptions` parametresinde [açık](#open) üye işlevi.  
  
> [!NOTE]
> `DoFieldExchange` yalnızca türetilmiş bir sınıf kullanıyorsanız kullanılabilir `CRecordset`. Doğrudan kayıt kümesi nesnesi oluşturduysanız `CRecordset`, çağırmalısınız [GetFieldValue](#getfieldvalue) veri almak için üye işlevi.  
  
 Kayıt alanı değişimi (RFX) olarak adlandırılan alan verisi, exchange her iki yönde de işe yarar: kayıt kümesi nesnesinin alan veri üyeleri veri kaynağındaki alan ve kayıt kümesi nesnesi için veri kaynağı kaydı.  
  
 Normal olarak yapmanız gereken uygulamak için tek eylem `DoFieldExchange` türetilmiş kümeniz için ClassWizard ile sınıf oluşturun ve alan veri üyeleri adları ve veri türlerini belirtmek için bir sınıftır. Kod ne ClassWizard parametre veri üyeleri belirtin veya herhangi bir sütundan dinamik olarak bağlama dağıtılacak yazar için de ekleyebilirsiniz. Daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Türetilen kayıt kümesi sınıfınız ClassWizard ile bildirirken sihirbaz geçersiz kılma Yazar `DoFieldExchange` sizin için hangi benzer aşağıdaki örnek:  
  
 [!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 RFX işlevleri hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md).  
  
 Daha fazla örnekler ve ayrıntılarını `DoFieldExchange`, makaleye bakın [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md). RFX hakkında genel bilgi için bkz: [kayıt alanı değişimi](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="edit"></a>  CRecordset::Edit  
 Değişiklik geçerli kayıt yapılmasına izin verir.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **Düzenle**, doğrudan değerleriyle sıfırlanarak alan veri üyeleri değiştirebilirsiniz. Daha sonra çağırdığınızda işlem tamamlanmadan [güncelleştirme](#update) veri kaynağı üzerinde yaptığınız değişiklikleri kaydetmek için üye işlevi.  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız **Düzenle**. Bu başarısız bir onaylama neden olacaktır. Ancak sınıfı `CRecordset` bir mekanizma sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevleri ODBC API işlevini kullanarak yazabilirsiniz **SQLSetPos**. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 **Düzen** kümesinin veri üyelerinin değerlerini kaydeder. Çağırırsanız **Düzenle**, ardından çağıran değişiklik **Düzenle** kaydın değerleri ne ilk önce oldukları için yeniden geri **Düzenle** çağırın.  
  
 Bazı durumlarda, bir sütun Null (hiçbir veri içeren) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için arama [SetFieldNull](#setfieldnull) bir parametresi ile **TRUE** Null; alan işaretlemek için bu da güncelleştirilmesi sütun neden olur. Bir alanın değerini değişmediğini olsa bile veri kaynağına yazılması, çağrı istiyorsanız [SetFieldDirty](#setfielddirty) bir parametresi ile **doğru**. Bu alan Null değere sahip olsa bile çalışır.  
  
 Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz **Düzenle** çağrısı bir işlemin parçası. Çağırmalısınız Not [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) çağırmadan önce **Düzenle** ve kayıt açıldıktan sonra. Ayrıca, arama unutmayın [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) çağırmak için bir alternatif değildir **güncelleştirme** tamamlamak için **Düzenle** işlemi. İşlemler hakkında daha fazla bilgi için bkz [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Geçerli kilitleme modunu bağlı olarak güncelleştirilmesini kaydı tarafından kilitlenmiş olabilir **Düzenle** çağırmanız kadar **güncelleştirme** veya başka bir kayıtla kaydırın veya yalnızca sırasında kilitlenebilir **Düzenle** çağırın. Kilitleme moduyla değiştirebileceğiniz [CRecordset::pessimistic](#setlockingmode).  
  
 Çağırmadan önce yeni bir kayda kaydırırsanız, geçerli kayıt önceki değerini geri **güncelleştirme**. A `CDBException` çağırırsanız durum **Düzenle** güncelleştirilemez bir kayıt veya geçerli bir kayıt olup olmadığını.  
  
 Daha fazla bilgi için makalelere bakın [işlem (ODBC)](../../data/odbc/transaction-odbc.md) ve [kayıt kümesi: kilitleme kayıtları (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>  CRecordset::FlushResultSet  
 Birden çok sonuç kümesi varsa önceden tanımlanmış sorgu (saklı yordam), bir sonraki sonuç kümesini alır.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Alınacak daha fazla sonuç kümeleri varsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmalısınız `FlushResultSet` yalnızca tamamen geçerli sonuç kümesi imleç tamamlandığında. Sonraki sonuç çağırarak kümesi aldığınızda unutmayın `FlushResultSet`, imleci bu sonuç kümesi üzerinde geçerli değil; çağırmalısınız [MoveNext](#movenext) üye işlevini çağırdıktan sonra `FlushResultSet`.  
  
 Önceden tanımlanmış sorgu çıktı parametresi veya giriş/çıkış parametreleri kullanıyorsa, çağırmalısınız `FlushResultSet` döndürdüğü kadar `FALSE` (Bu parametre değerlerini almak için değer 0).  
  
 `FlushResultSet` ODBC API işlev çağrılarını `SQLMoreResults`. Varsa `SQLMoreResults` döndürür `SQL_ERROR` veya `SQL_INVALID_HANDLE`, ardından `FlushResultSet` bir özel durum oluşturur. Hakkında daha fazla bilgi için `SQLMoreResults`, Windows SDK konusuna bakın.  
  
 Saklı yordam çağrısı istiyorsanız alanları bağlı gerekiyor `FlushResultSet`.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod varsayar `COutParamRecordset` olan bir `CRecordset`-türetilen nesne giriş parametresi bir output parametresi ile önceden tanımlanmış bir sorguyu temel ve birden çok sonuç kümesi sahip. Yapısını Not [DoFieldExchange](#dofieldexchange) geçersiz kılar.  
  
 [!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>  CRecordset::GetBookmark  
 Geçerli kayıt yer işareti değeri alır.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parametreler  
 `varBookmark`  
 Bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) yer geçerli kayıtta temsil eden nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yer işaretleri kayıt kümesinde desteklenip desteklenmediğini belirlemek için arama [CanBookmark](#canbookmark). Bunlar destekleniyorsa yer işaretleri kullanılabilir hale getirmek ayarlamalısınız **CRecordset::useBookmarks** seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi.  
  
> [!NOTE]
>  Yer işaretleri desteklenmeyen veya kullanılamayan çağrılmadan `GetBookmark` oluşturulan bir özel durum neden olur. Yer işaretleri salt iletme kayıt kümeleri desteklenmez.  
  
 `GetBookmark` yer işareti geçerli kayıt için değer atayan bir `CDBVariant` nesnesi. Farklı bir kayda taşıdıktan herhangi bir zamanda bu kayda dönmek için çağrı [SetBookmark](#setbookmark) karşılık gelen `CDBVariant` nesnesi.  
  
> [!NOTE]
>  Belirli kayıt işlemlerinden sonra yer işaretleri artık geçerli olmayabilir. Örneğin, çağırırsanız `GetBookmark` arkasından **Requery**, kayıtla geri dönmek mümkün olmayabilir `SetBookmark`. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenle çağırabilirsiniz olup olmadığını denetlemek için `SetBookmark`.  
  
 Yer işaretleri ve kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="getdefaultconnect"></a>  CRecordset::GetDefaultConnect  
 Varsayılan bağlantı dizesini almak için çağrılır.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` varsayılan bağlantı dizesini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework kayıt temel aldığı veri kaynağı için varsayılan bağlantı dizesini almak için bu üye işlevi çağırır. ClassWizard ClassWizard tablolar ve sütunlar hakkında bilgi almak için kullandığınız aynı veri kaynağı belirleyerek bu işlev sizin için uygular. Büyük olasılıkla, uygulamanızı geliştirme sırasında bu varsayılan bağlantı güvenemeyeceklerini uygun bulacaksınız. Ancak, varsayılan bağlantı uygulamanızı kullanıcılar için uygun olmayabilir. Bu durumda, bu işlev ClassWizard'ın sürümü atılıyor yeniden uygulamalı. Bağlantı dizeleri hakkında daha fazla bilgi için bkz: [veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md).  
  
##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL  
 Varsayılan SQL dizesi yürütülemedi almak için çağrılır.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` varsayılan SQL deyimini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework kayıt dayandığı varsayılan SQL deyimini almak için bu üye işlevi çağırır. Bu tablo adı veya bir SQL olabilir **seçin** deyimi.  
  
 Dolaylı olarak kayıt kümesi sınıfınız ClassWizard ile bildirerek varsayılan SQL deyimini tanımlayın ve ClassWizard bu görevi sizin için gerçekleştirir.  
  
 Kendi kullanımınız için SQL deyimi dizesi gerekiyorsa, çağrı `GetSQL`, açıldığı zaman kayıt kümesinin kayıtları seçmek için kullanılan SQL ifadesi döndürür. Varsayılan SQL dizesi sınıfınızın geçersiz kılma içinde düzenleyebilirsiniz `GetDefaultSQL`. Örneğin, kullanarak önceden tanımlanmış sorgu için bir çağrı belirtebilirsiniz bir **ÇAĞRISI** deyimi. (Not, ancak olması durumunda, düzenleme `GetDefaultSQL`, aynı zamanda değiştirmeniz gerekir `m_nFields` veri kaynağındaki sütunları sayısıyla eşleşmelidir.)  
  
 Daha fazla bilgi için bkz: [kayıt kümesi: bir tablo (ODBC için) bir sınıf bildirme](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
> [!CAUTION]
>  Tablo adı framework bir tablo adı birden çok tablo adları sağlandıysa veya tanımlanamadı, boş bir **ÇAĞRISI** deyimi yorumlanmaması. Kullanırken dikkat edin bir **ÇAĞRISI** deyimi, kuşak arasında boşluk eklemelisiniz değil ve **ÇAĞRISI** anahtar sözcüğü ya da boşluk kuşak önce veya önce eklemeniz gerekir  **SEÇİN** in anahtar sözcüğü bir **seçin** deyimi.  
  
##  <a name="getfieldvalue"></a>  CRecordset::GetFieldValue  
 Geçerli kayıttaki alan verileri alır.  
  
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
 `lpszName`  
 Bir alanın adı.  
  
 *varValu*e  
 Bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) alanın değerini depolar nesnesi.  
  
 `nFieldType`  
 Alan ODBC C veri türü. Varsayılan değer kullanılarak **DEFAULT_FIELD_TYPE**, zorlar `GetFieldValue` SQL veri türü C veri türünden belirlemek için aşağıdaki tabloda temel. Aksi takdirde, verileri doğrudan yazın veya bir uyumlu veri türü seçin belirtebilirsiniz; Örneğin, herhangi bir veri türü depolayabilir **SQL_C_CHAR**.  
  
|C veri türü|SQL veri türü|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 ODBC veri türleri hakkında daha fazla bilgi için "SQL veri türleri" ve "C veri türleri" ek d Windows SDK'ın konularına bakın.  
  
 `nIndex`  
 Alan sıfır tabanlı dizini.  
  
 `strValue`  
 Bir başvuru bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) alanın veri türü ne olursa olsun metin alanın değerini depolar nesne dönüştürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir alan adı veya dizin göre bakabilirsiniz. Alan değeri ya da depolayabilirsiniz bir `CDBVariant` nesnesi veya bir `CString` nesnesi.  
  
 Toplu satır getirme uyguladıysanız, geçerli kayıt her zaman bir satır kümesindeki ilk kaydı yer alır. Kullanılacak `GetFieldValue` belirli bir satır kümesi içinde bir kayıt üzerinde ilk çağırmalısınız [SetRowsetCursorPosition](#setrowsetcursorposition) imleç istenen satır, satır kümesi içinde taşımak için üye işlevi. ' I çağırın `GetFieldValue` ilgili satır. Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği `dwOptions` parametresinde [açık](#open) üye işlevi.  
  
 Kullanabileceğiniz `GetFieldValue` alanları statik olarak bunları tasarım zamanında bağlama yerine çalışma zamanında dinamik olarak getirilemedi. Örneğin, bir kayıt kümesi nesnesi doğrudan bildirilen `CRecordset`, kullanmalısınız `GetFieldValue` almak için alan verileri; kayıt alanı değişimi (RFX) veya toplu kayıt alanı değişimi (Toplu RFX) uygulanmadı.  
  
> [!NOTE]
>  Türetme olmadan bir kayıt kümesi nesnesi bildirirseniz `CRecordset`, yüklenen ODBC imleç kitaplığı yok. İmleç Kitaplığı kayıt kümesi en az bir ilişkili sütun sahip olmasını gerektirir; Ancak, kullandığınızda `CRecordset` sütunları hiçbiri doğrudan bağlanır. Üye işlevleri [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) ve [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) imleç kitaplığı yüklü olup olmadığını denetleme.  
  
 `GetFieldValue` ODBC API işlev çağrılarını **SQLGetData**. Değeri, sürücü çıkışı yapıyorsa **SQL_NO_TOTAL** alan değeri gerçek uzunluğu `GetFieldValue` bir özel durum oluşturur. Hakkında daha fazla bilgi için **SQLGetData**, Windows SDK konusuna bakın.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnek kod çağrıları gösterilir `GetFieldValue` doğrudan kayıt kümesi nesnesi bildirilen için `CRecordset`.  
  
 [!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  DAO sınıfı aksine `CDaoRecordset`, `CRecordset` sahip olmayan bir `SetFieldValue` üye işlevi. Doğrudan bir nesne oluşturursanız, `CRecordset`, etkili bir şekilde salt okunurdur.  
  
 Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount  
 Kayıt kümesi nesnesi alanları toplam sayısını alır.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi alanlarına sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz: [kayıt kümesi: oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
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
 `lpszName`  
 Bir alanın adı.  
  
 `fieldinfo`  
 Bir başvuru bir `CODBCFieldInfo` yapısı.  
  
 `nIndex`  
 Alan sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi bir sürümü, bir alan adına göre aramak olanak tanır. Başka bir sürüm dizini tarafından bir alanından aramak olanak sağlar.  
  
 Döndürülen bilgiler hakkında açıklama için bkz: [Codbcfieldınfo](../../mfc/reference/codbcfieldinfo-structure.md) yapısı.  
  
 Kayıt kümeleri oluşturma hakkında daha fazla bilgi için bkz: [kayıt kümesi: oluşturma ve kapatma (ODBC) kayıt kümeleri](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount  
 Kayıt kümesi boyutunu belirler.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesindeki kayıt sayısı; kayıt kümesi hiçbir kayıt içeriyorsa 0; veya kayıt sayısı belirlenemiyorsa, -1.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Kayıt sayısı "yüksek su işareti," en yüksek numaralı kayıt tutulan henüz kullanıcı kayıtlarda taşınırken görülür. Kullanıcı son kaydı taşındıktan sonra kayıtlarının toplam sayısı yalnızca denir. Çağırdığınızda performans nedenleriyle sayısı güncelleştirilmez `MoveLast`. Kayıtları kendiniz saymak için arama `MoveNext` kadar sürekli `IsEOF` sıfır olmayan bir değer döndürür. Bir kayıt aracılığıyla ekleme **CRecordset:AddNew** ve **güncelleştirme** sayısı da artar; aracılığıyla kayıt silme `CRecordset::Delete` sayısı azalır.  
  
##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize  
 Belirli bir getirme sırasında almak istediğiniz satır sayısı için geçerli ayarları alır.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirli bir getirme sırasında alınacak satır sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme kullanıyorsanız, kayıt kümesi açıldığında varsayılan satır kümesi boyutu 25'tir; Aksi takdirde, 1 olur.  
  
 Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi. Satır kümesi boyutu ayarını değiştirmek için arama [SetRowsetSize](#setrowsetsize).  
  
 Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched  
 Kaç tane kayıt gerçekten getirmeden sonra alındı belirler.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Satır sayısı belirli bir getirmeden sonra veri kaynağından alınan.  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme uygulandığında, bu yararlıdır. Satır kümesi boyutu, normalde bir getirme satır sayısını alınır gösterir; Ancak, satır kümesinde toplam sayısını da bir satır kümesinde satır sayısını alınır etkiler. Kümenizin 4 satır kümesi boyutu ayarı olan 10 kayıt varsa, örneğin, daha sonra kayıt kümesi içinde çağırarak döngü `MoveNext` yalnızca 2 kayıtları sahip son satır kümesinde neden olur.  
  
 Toplu satır getirme uygulamak için belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi. Satır kümesi boyutu belirtmek için arama [SetRowsetSize](#setrowsetsize).  
  
 Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus  
 Geçerli satır kümesindeki durumunu alır.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `wRow`  
 Tabanlı konumu bir satır geçerli satır kümesi. Bu değer 1'den satır boyutunu arasında değişebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Satır durum değeri. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetRowStatus` veri kaynağı veya, son başlatıldığından beri ya da herhangi bir değişikliği satır durumunu gösteren bir değer alınan döndürür hiçbir satır karşılık gelen `wRow` getirildi. Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.  
  
|Durum değeri|Açıklama|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|Satır değiştirilmez.|  
|`SQL_ROW_UPDATED`|Satır güncelleştirildi.|  
|`SQL_ROW_DELETED`|Satır silindi.|  
|`SQL_ROW_ADDED`|Satır eklendi.|  
|`SQL_ROW_ERROR`|Bir hata nedeniyle getirilemez satırıdır.|  
|`SQL_ROW_NOROW`|Karşılık gelen bir satır yok `wRow`.|  
  
 Daha fazla bilgi için bkz: ODBC API işlevi **SQLExtendedFetch** Windows SDK'sındaki.  
  
##  <a name="getstatus"></a>  CRecordset::GetStatus  
 Kayıt kümesi ve son kaydı bir olup olmadığı görülen geçerli kayıt dizinini belirler.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rStatus`  
 Bir başvuru bir **CRecordsetStatus** nesnesi. Daha fazla bilgi için Açıklamalar bölümüne bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 `CRecordset` Dizin izlemek çalışır, ancak bazı durumlarda bu mümkün olmayabilir. Bkz: [GetRecordCount](#getrecordcount) için bir açıklama.  
  
 **CRecordsetStatus** yapısı aşağıdaki biçime sahiptir:  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 İki üyeleri **CRecordsetStatus** şu anlama gelir:  
  
- **m_lCurrentRecord** biliniyorsa, kayıt kümesindeki geçerli kayıt sıfır tabanlı dizini içerir. Dizin belirlenemiyorsa, bu üyeyi içeren **AFX_CURRENT_RECORD_UNDEFINED** (-2). Varsa `IsBOF` olan **TRUE** (kayıt kümesi boş veya önce ilk kayıt kaydırma denemesi), ardından **m_lCurrentRecord** ayarlanır **AFX_CURRENT_RECORD_BOF** (-1). İlk kaydını da 0 olarak ayarlanırsa, ikinci 1 kaydetmek ve benzeri.  
  
- **m_bRecordCountFinal** toplam kayıt kümesindeki kayıt sayısı belirlendiğinde Nonzero. Genellikle bu kayıt kümesinin başında başlatma ve çağırma gerçekleştirilmesi gereken `MoveNext` kadar `IsEOF` sıfır olmayan bir değer döndürür. Bu üye sıfırsa kayıt sayısı tarafından döndürülen `GetRecordCount`, değil -1, yoksa yalnızca "yüksek su işareti" sayısını kaydeder.  
  
##  <a name="getsql"></a>  CRecordset::GetSQL  
 Açıldığında kayıt kümesinin kayıtları seçmek için kullanılan SQL deyimini almak için bu üye işlevini çağırın.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **const** başvuru bir `CString` SQL deyimi içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle bir SQL olacaktır **seçin** deyimi. Tarafından döndürülen dize `GetSQL` salt okunurdur.  
  
 Tarafından döndürülen dize `GetSQL` kayıt kümesinde için geçirilen herhangi bir dize genellikle farklı `lpszSQL` parametresi **açık** üye işlevi. Kayıt kümesi ne, geçirilen temel tam bir SQL deyimini oluşturur olmasıdır **açık**, ne belirttiğiniz ClassWizard ile belirtilen **m_strFilter** ve `m_strSort` veri üyeleri ve herhangi bir parametre belirtmiş olabilirsiniz. Kayıt kümesi bu SQL deyimini nasıl oluşturur hakkında ayrıntıları görmek için makaleyi [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
> [!NOTE]
>  Yalnızca çağrıldıktan sonra bu üye işlevini çağırın [açık](#open).  
  
##  <a name="gettablename"></a>  CRecordset::GetTableName  
 Kayıt kümesinin sorgu dayandığı SQL tablosunun adını alır.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **const** başvuru bir `CString` tabloyu içeren adı, kayıt kümesi varsa dayalı olarak bir tablo; tersi durumda, boş bir dize.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetTableName` yalnızca bir tabloda, bir birleşim değil birden çok tablo veya önceden tanımlanmış sorgu (saklı yordam) kayıt dayanıyorsa geçerli değil. Salt okunur addır.  
  
> [!NOTE]
>  Yalnızca çağrıldıktan sonra bu üye işlevini çağırın [açık](#open).  
  
##  <a name="isbof"></a>  CRecordset::IsBOF  
 Kayıt kümesi önce ilk kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi hiçbir kayıt içeriyorsa veya, geriye doğru ilk kaydı önce kaydırırsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaydından önce ilk kaydı kayıt kümesinin ilerlemiş olup olmadığını öğrenmek için kayıt kaydırma önce bu üye işlevini çağırın. Aynı zamanda `IsBOF` ile birlikte `IsEOF` kayıt herhangi bir kayıt içeren boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra **açık**, kayıt kümesinin hiçbir kayıt içeriyorsa `IsBOF` sıfır olmayan bir değer döndürür. En az bir kayda sahip bir kayıt kümesi açtığınızda, ilk kayıt geçerli kayıttır ve `IsBOF` 0 döndürür.  
  
 Geçerli kaydı ilk kaydı ise ve size çağrı `MovePrev`, `IsBOF` sonradan sıfır olmayan bir değer döndürür. Varsa `IsBOF` sıfır verir ve arama `MovePrev`, bir hata oluşur. Varsa `IsBOF` sıfır olmayan döndürür, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektirir herhangi bir eylem hatayla sonuçlanır.  
  
### <a name="example"></a>Örnek  
 Bu örnekte `IsBOF` ve `IsEOF` kodu her iki yönde kayıt aracılığıyla kayarken bir kayıt kümesinin sınırlarını algılamak için.  
  
 [!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>  CRecordset::IsDeleted  
 Geçerli kayıt silinmiş olup olmadığını belirler.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi silinmiş bir kayda konumlandırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayda kaydırırsanız ve `IsDeleted` döndürür **TRUE** başka herhangi bir kayıt işlemini gerçekleştirmeden önce (sıfır), ardından başka bir kayıtla kaydırma gerekir.  
  
 Sonucu `IsDeleted` belirttiğiniz olup olmadığını kümenizin güncelleştirilebilir, olup, kayıt kümesi türü gibi birçok faktöre bağlıdır **CRecordset::skipDeletedRecords** seçeneği kayıt kümesi olup açıldığında, sürücü paketleri silinmiş kayıtlar ve birden çok kullanıcı olsun.  
  
 Hakkında daha fazla bilgi için **CRecordset::skipDeletedRecords** ve paket, sürücü [açık](#open) üye işlevi.  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız değil çağırmalısınız `IsDeleted`. Bunun yerine, çağrı [GetRowStatus](#getrowstatus) üye işlevi. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="iseof"></a>  CRecordset::IsEOF  
 Kayıt kümesi sonra son kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi hiçbir kayıt içeriyorsa veya son kaydı kaydırırsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi son kaydı ilerlemiş olup olmadığını öğrenmek için kayıt kaydından kaydırın gibi bu üye işlevini çağırın. Aynı zamanda `IsEOF` kayıt herhangi bir kayıt içeren boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra **açık**, kayıt kümesinin hiçbir kayıt içeriyorsa `IsEOF` sıfır olmayan bir değer döndürür. En az bir kayda sahip bir kayıt kümesi açtığınızda, ilk kayıt geçerli kayıttır ve `IsEOF` 0 döndürür.  
  
 Çağırdığınızda son kaydı geçerli kayıt olup olmadığını `MoveNext`, `IsEOF` sonradan sıfır olmayan bir değer döndürür. Varsa `IsEOF` sıfır verir ve arama `MoveNext`, bir hata oluşur. Varsa `IsEOF` sıfır olmayan döndürür, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektirir herhangi bir eylem hatayla sonuçlanır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [IsBOF](#isbof).  
  
##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty  
 Belirtilen alan veri üyesi itibaren değişip değişmediğini belirleyen [Düzenle](#edit) veya [AddNew](#addnew) çağrıldı.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** alanlar kirli olup olmadığını belirlemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alan veri üyesi arama beri değişmişse sıfır olmayan `AddNew` veya **Düzenle**; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli kayıt için bir çağrı tarafından güncelleştirildiğinde tüm kirli alan veri üyeleri verilerde kayda veri kaynağında aktarılacak [güncelleştirme](#update) üye işlevini `CRecordset` (bir çağrısından **Düzenle**veya `AddNew`).  
  
> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, daha sonra uyguladıysanız `IsFieldDirty` her zaman döndürülecek **FALSE** ve başarısız bir onaylama işlemi içinde neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Çağırma `IsFieldDirty` çağrıları önceki etkilerini sıfırlayacak [SetFieldDirty](#setfielddirty) alanın kirli durumu tekrar değerlendirilir olduğundan. İçinde `AddNew` durumda, geçerli alan değeri sözde null değerinden farklı olması durumunda alan durumu ayarlanmış kirli. İçinde **Düzenle** alan durumu kirli olarak ayarlanırsa ve alan değeri önbelleğe alınan değerinden farklıysa, bu durumda.  
  
 `IsFieldDirty` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).  
  
 Makaleyi kirli bayrağı hakkında daha fazla bilgi için bkz: [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull  
 Geçerli kayıt belirtilen alan Null ise sıfır olmayan döndürür (değeri yok).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** tüm alanları boş olup olmadığını belirlemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alan veri üyesi boş olarak işaretlenmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayıt kümesi belirtilen alan veri üyesi Null olarak işaretlenmiş olup olmadığını belirlemek için bu üye işlevini çağırın. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve aynı değil **NULL** c++.) Alan veri üyesi boş olarak işaretlenmişse, kendisi için değer yoktur geçerli kaydı bir sütun olarak yorumlanır.  
  
> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, daha sonra uyguladıysanız `IsFieldNull` her zaman döndürülecek **FALSE** ve başarısız bir onaylama işlemi içinde neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `IsFieldNull` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable  
 Geçerli kayıttaki belirtilen alanın Null (hiçbir değer sahip) ayarlanabiliyorsa sıfır olmayan bir değer döndürür.  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** tüm alanları için Null değer ayarlanabilir, belirlemek için.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen alan veri üyesi "NULL" olup olmadığını belirlemek için (bir Null değere; ayarlayın olabilir bu üye işlevini çağırın C++ **NULL** Veritabanı terminolojisinde anlamına gelir, Null ile aynı değil "herhangi bir değer olan").  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız `IsFieldNullable`. Bunun yerine, çağrı [GetODBCFieldInfo](#getodbcfieldinfo) bir alanı Null değerine ayarlanmış olup olmadığını belirlemek için üye işlevi. Her zaman çağırabilirsiniz Not `GetODBCFieldInfo`ne olursa olsun, olup toplu satır getirme uyguladık. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Null olamaz bir alan bir değer içermelidir. Bu tür bir alana ekleme veya bir kayıt güncelleştirilirken Null olarak ayarlamak çalışırsanız, veri kaynağı ekleme veya güncelleştirme, reddeder ve [güncelleştirme](#update) bir özel durum oluşturur. Çağırdığınızda özel durum oluşur **güncelleştirme**, değil çağırdığınızda [SetFieldNull](#setfieldnull).  
  
 Kullanarak **NULL** işlevinin ilk bağımsız değişkeni işlevi yalnızca uygulanır için **outputColumn** alanları değil, **param** alanları. Örneğin, arama  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 yalnızca ayarlayacaktır **outputColumn** alanları **NULL**; **param** alanları etkilenmemesini olacaktır.  
  
 Üzerinde çalışmak için **param** alanları tek tek gerçek adresini sağlamalısınız **param** gibi çalışmak istediğiniz:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Tüm ayarlayamıyor yani **param** alanları **NULL**ile yapabileceğiniz gibi **outputColumn** alanları.  
  
 `IsFieldNullable` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isopen"></a>  CRecordset::IsOpen  
 Kayıt kümesi zaten açık olup olmadığını belirler.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF kayıt kümesi nesnesinin [açık](#open) veya [Requery](#requery) üye işlevi önceden çağrılıp çağrılmadığını ve kayıt kapalı değil; Aksi halde 0.  
  
##  <a name="m_hstmt"></a>  CRecordset::m_hstmt  
 Deyimi ODBC veri yapısını türü için bir tanıtıcı içeren **HSTMT**, kayıt kümesi ile ilişkilendirilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Her bir ODBC veri kaynağı sorgusu ile ilişkili bir **HSTMT**.  
  
> [!CAUTION]
>  Kullanmayın **m_hstmt** önce [açık](#open) çağrıldı.  
  
 Normal olarak erişim gerekmez **HSTMT** doğrudan, ancak SQL deyimlerini doğrudan yürütme için gerekebilir. `ExecuteSQL` Sınıfının üye işlevini `CDatabase` kullanmaya ilişkin bir örnek sağlar **m_hstmt**.  
  
##  <a name="m_nfields"></a>  CRecordset::m_nFields  
 Kayıt kümesi sınıfında yer alan veri üyeleri sayısını içerir; diğer bir deyişle, veri kaynağından kayıt kümesi tarafından seçili sütun sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi sınıfı oluşturucusu başlatmalıdır `m_nFields` doğru numarasına sahip. Toplu satır getirme uygulanmadı, kayıt kümesi sınıfınızı bildirmek için kullandığınızda, bu başlatma ClassWizard yazar. Ayrıca, el ile yazabilirsiniz.  
  
 Çerçeve alan veri üyeleri geçerli kayıt veri kaynağı için karşılık gelen sütunlara arasındaki etkileşimi yönetmek için bu sayıyı kullanır.  
  
> [!CAUTION]
>  Bu sayı, "kayıtlı çıktı sütunu sayısı" karşılık gelmelidir `DoFieldExchange` veya `DoBulkFieldExchange` çağrısı yapıldıktan sonra [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametresiyle **CFieldExchange::outputColumn**.  
  
 Sütunları dinamik olarak makalesinde açıklandığı gibi bağlayabilirsiniz "kayıt kümesi: dinamik olarak bağlama veri sütunlarını." Bunu yaparsanız, sayıma artırmanız gerekir `m_nFields` RFX veya toplu RFX işlevi sayısı çağrıları yansıtacak şekilde, `DoFieldExchange` veya `DoBulkFieldExchange` dinamik olarak bağlı sütunlar için üye işlevi.  
  
 Daha fazla bilgi için makalelere bakın [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) ve [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
 Makalesine bakın [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_nparams"></a>  CRecordset::m_nParams  
 Kayıt kümesi sınıfında parametre veri üyeleri sayısını içerir; diğer bir deyişle, parametrelerin sayısı kayıt kümesinin sorguyla geçirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi sınıfınız herhangi bir parametre veri üyesi varsa, sınıf oluşturucusu başlatmalıdır `m_nParams` doğru numarasına sahip. Değeri `m_nParams` varsayılan ayar: 0. (El ile yapmanız gerekir) parametre veri üyeleri eklerseniz, bir başlatma parametreleri numarasını yansıtacak şekilde sınıfı oluşturucuda el ile de eklemelisiniz (olması gerekir en az sayıda büyüklüğünde '' yer tutucuları, **m_strFilter**  veya `m_strSort` dize).  
  
 Çerçeve kümesinin sorgusunu parameterizes bu sayıyı kullanır.  
  
> [!CAUTION]
>  Bu sayı "kayıtlı params" sayısı karşılık gelmelidir `DoFieldExchange` veya `DoBulkFieldExchange` çağrısı yapıldıktan sonra [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametre değeriyle **CFieldExchange::inputParam**,  **CFieldExchange::param**, **CFieldExchange::outputParam**, veya **CFieldExchange::inoutParam**.  
  
### <a name="example"></a>Örnek  
  Makalelerine bakın [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) ve [kayıt alanı değişimi: RFX kullanma](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase  
 Bir işaretçi içeriyor `CDatabase` üzerinden kayıt bağlı bir veri kaynağı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişken, iki şekilde ayarlanır. Genellikle, bir işaretçi bir zaten bağlı geçirdiğiniz `CDatabase` nesne olduğunda kayıt kümesi nesnesi oluşturun. Geçirirseniz **NULL** bunun yerine, `CRecordset` oluşturur bir `CDatabase` sizin için nesne ve onu bağlanır. Her iki durumda da `CRecordset` işaretçinin bu değişkeninde depolar.  
  
 Normalde, doğrudan depolanan işaretçiyi kullanın gerekmez **m_pDatabase**. Kendi uzantıları yazarsanız `CRecordset`, ancak işaretçiyi kullanmanız gerekebilir. Throw, örneğin, işaretçi kendi gereksiniminiz olabilir `CDBException`s. Ya da aynı kullanarak bir şey yapmanız gerekirse gerekebilecek `CDatabase` çalışan işlemler, ayarı zaman aşımı veya çağırma gibi nesne `ExecuteSQL` sınıfının üye işlevini `CDatabase` doğrudan SQL deyimlerini yürütmek için.  
  
##  <a name="m_strfilter"></a>  CRecordset::m_strFilter  
 Kayıt kümesi nesnesi oluşturun sonra ancak çağırmadan önce kendi **açık** üye işlev, bu veri üyesi depolamak için kullanmak bir `CString` bir SQL içeren **burada** yan tümcesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi seçtiği sırasında kayıtları sınırlamak (veya filtrelemek için) bu dizeyi kullanır **açık** veya **Requery** çağırın. Bu kayıtların tüm "satış temsilcisi İzmir'de temel" gibi bir alt kümesini seçmek için yararlıdır ("durumu CA ="). ODBC SQL söz dizimi bir **burada** yan tümcesi  
  
 `WHERE search-condition`  
  
 Dahil Not **burada** dizenizi anahtar sözcük. Framework bunu sağlar.  
  
 Filtre dizesi yerleştirerek de Parametreleştirme '' sınıfınızda parametre veri üyesi için her bir yer tutucu bildirme ve kayıt kümesine parametreleri geçirme yer tutucuları, çalışma zamanında. Bu, çalışma zamanında filtresi oluşturmak sağlar. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 SQL hakkında daha fazla bilgi için **nerede** yan tümceleri, başlıklı makaleye bakın [SQL](../../data/odbc/sql.md). Seçme ve kayıtları filtreleme hakkında daha fazla bilgi için bkz: [kayıt kümesi: kayıtları filtreleme (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>  CRecordset::m_strSort  
 Kayıt kümesi nesnesi oluşturun sonra ancak çağırmadan önce kendi **açık** üye işlev, bu veri üyesi depolamak için kullanmak bir `CString` bir SQL içeren **ORDER BY** yan tümcesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi seçer sırasında kayıtları sıralamak için bu dizeyi kullanır **açık** veya **Requery** çağırın. Bir kayıt kümesinde bir veya daha fazla sütun sıralamak için bu özelliği kullanın. ODBC SQL söz dizimi bir **ORDER BY** yan tümcesi  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 Sıralama belirtimi bir tamsayı ya da bir sütun adı olduğu. (Varsayılan olarak artan) artan veya azalan sıralama "ASC" veya "DESC" sıralama dizesi sütun listesinde ekleyerek de belirtebilirsiniz. Seçili kayıtları ilk listelenen ilk sütun, sonra ikinci vb. göre sıralanır. Örneğin, "Müşteriler" kayıt kümesi Soyadı, ardından ad sipariş. Listelemek sütun sayısı veri kaynağına bağlıdır. Daha fazla bilgi için Windows SDK'sı bakın.  
  
 Dahil Not **ORDER BY** dizenizi anahtar sözcük. Framework bunu sağlar.  
  
 SQL yan tümceleri hakkında daha fazla bilgi için bkz: [SQL](../../data/odbc/sql.md). Makale kayıtları sıralama hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları sıralama (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>  CRecordset::Move  
 Geçerli kayıt işaretçisi ileriye veya geriye dönük kayıt kümesi içinde taşır.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRows`  
 İleriye veya geriye doğru taşımak için satır sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru gitmenizi sağlar. Negatif değerler geriye doğru başına doğru taşıyın.  
  
 `wFetchType`  
 Satır kümesi belirler, **taşıma** getirir. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin 0 değeri geçirirseniz `nRows`, **taşıma** geçerli kaydı; yeniler **Taşıma** tüm geçerli sona erer `AddNew` veya **Düzenle** modunu ve önce geçerli kaydın değerini geri yükler `AddNew` veya **Düzenle** çağrıldı.  
  
> [!NOTE]
>  Kayıt kümesi içinde taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [CRecordset::IsDeleted](#isdeleted) daha fazla bilgi için. Açtığınızda bir `CRecordset` ile **skipDeletedRecords** seçenek kümesi **taşıma** varsa onaylar `nRows` parametresi: 0. Bu davranış, yenileme aynı verileri kullanarak diğer istemci uygulamaları tarafından silinen satır engeller. Bkz: `dwOption` parametresinde [açık](#open) bir açıklaması için **skipDeletedRecords**.  
  
 **Taşıma** kayıt satır kümeleri tarafından yeniden konumlandırır. İçin değerlere göre `nRows` ve `wFetchType`, **taşıma** uygun satır kümesi getirir ve ardından bu satır kümesinde ilk kaydı geçerli kayıt yapar. Toplu satır getirme değil uyguladıysanız, ardından satır kümesi boyutu her zaman 1'dir. Bir satır kümesi getirilirken **taşıma** doğrudan çağıran [CheckRowsetError](#checkrowseterror) getirme kaynaklanan hataları işlemek için üye işlev.  
  
 Geçirdiğiniz, değerleri bağlı olarak **taşıma** diğer eşdeğerdir `CRecordset` üye işlevleri. Özellikle, değeri `wFetchType` daha sezgisel bir üye işlevini ve genellikle geçerli kaydın taşınması için tercih edilen yöntem gösterebilir.  
  
 İçin olası değerler aşağıdaki tabloda listelenmektedir `wFetchType`, satır kümesi, **taşıma** getirir göre `wFetchType` ve `nRows`ve karşılık gelen herhangi bir eşdeğer üye işlevini `wFetchType`.  
  
|wFetchType|Getirilen satır kümesi|Eşdeğer üye işlevi|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE` (varsayılan değer)|Satır kümesi başlangıç `nRows` geçerli satır kümesindeki ilk satırdan satırlara.||  
|`SQL_FETCH_NEXT`|Sonraki satır kümesi; `nRows` göz ardı edilir.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|Önceki satır kümesi; `nRows` göz ardı edilir.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|İlk satır kümesinde; `nRows` göz ardı edilir.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|Son tam satır kümesinde; `nRows` göz ardı edilir.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|Varsa `nRows` > 0, başlangıç satır kümesi `nRows` kümesinin başından satırlara. Varsa `nRows` < 0, başlangıç satır kümesi `nRows` kayıt sonundan satırlara. Varsa `nRows` = 0, bir dosya başına (BOF) koşulu verilir.|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|Yer işareti değeri karşılık gelen satır başlayarak satır kümesi `nRows`.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  Salt iletme kayıt kümeleri için **taşıma** yalnızca bir değeri ile geçerlidir `SQL_FETCH_NEXT` için `wFetchType`.  
  
> [!CAUTION]
>  Çağırma **taşıma** hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı [IsBOF](#isbof) ve [IsEOF](#iseof).  
  
> [!NOTE]
>  Başında ve sonunda kayıt kümesinin kaydırılan varsa ( `IsBOF` veya `IsEOF` sıfır olmayan bir değer döndürür), çağıran bir **taşımak** işlevi oluşturur büyük olasılıkla bir `CDBException`. Örneğin, varsa `IsEOF` sıfır olmayan bir değer döndürür ve `IsBOF` sonra desteklemez, `MoveNext` bir özel durum oluşturur ama `MovePrev` almayacak.  
  
> [!NOTE]
>  Çağırırsanız **taşıma** geçerli kayıt yüklenirken güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). ODBC API işlevi ilgili bilgi için bkz **SQLExtendedFetch** Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>  CRecordset::MoveFirst  
 İlk kaydı ilk satır kümesinde geçerli kayıt yapar.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Olup toplu satır getirme uygulanmıştır bağımsız olarak, bu kayıt kümesindeki ilk kaydı her zaman olacaktır.  
  
 Çağrı gerekmez **MoveFirst** kayıt açtıktan hemen sonra. O anda ilk kayıt (varsa) otomatik olarak geçerli kayıttır.  
  
> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.  
  
> [!NOTE]
>  Kayıt kümesi içinde taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsBOF](#isbof).  
  
##  <a name="movelast"></a>  CRecordset::MoveLast  
 İlk kaydı son tam satır kümesinde geçerli kayıt yapar.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme değil uyguladıysanız, kümenizin satır kümesi boyutu 1, bu nedenle sahip `MoveLast` yalnızca kaydı kayıt kümesinde son taşır.  
  
> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.  
  
> [!NOTE]
>  Kayıt kümesi içinde taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsBOF](#isbof).  
  
##  <a name="movenext"></a>  CRecordset::MoveNext  
 İlk kayıttan sonraki satır kümesinde geçerli kayıt yapar.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme değil uyguladıysanız, kümenizin satır kümesi boyutu 1, bu nedenle sahip `MoveNext` yalnızca sonraki kayda taşır.  
  
> [!NOTE]
>  Kayıt kümesi içinde taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.  
  
> [!NOTE]
>  Ayrıca, arama önerilir `IsEOF` çağırmadan önce `MoveNext`. Örneğin, kayıt kümesi sonunun kaydırırsanız `IsEOF` sıfır olmayan; döndürülecek bir sonraki çağrı `MoveNext` bir özel durum.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsBOF](#isbof).  
  
##  <a name="moveprev"></a>  CRecordset::MovePrev  
 İlk kayıttan önceki satır kümesinde geçerli kayıt yapar.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme değil uyguladıysanız, kümenizin satır kümesi boyutu 1, bu nedenle sahip `MovePrev` yalnızca önceki kayda taşır.  
  
> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri için geçerli değil.  
  
> [!NOTE]
>  Kayıt kümesi içinde taşıdığınızda, silinen kayıtlar atlayamazsınız. Bkz: [IsDeleted](#isdeleted) Ayrıntılar için üye işlevi.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Kayıt kümesi herhangi bir kayıt olup olmadığını belirlemek için çağrı `IsBOF` ve `IsEOF`.  
  
> [!NOTE]
>  Ayrıca, arama önerilir `IsBOF` çağırmadan önce `MovePrev`. Örneğin, kayıt kümesi başına öncesinde kaydırırsanız `IsBOF` sıfır olmayan; döndürülecek bir sonraki çağrı `MovePrev` bir özel durum.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [IsBOF](#isbof).  
  
##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions  
 (Seçimini kullanılır) seçeneklerini ayarlamak için belirtilen ODBC deyim için çağrılır.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parametreler  
 `hstmt`  
 **HSTMT** olan seçeneklerdir ayarlanacak ODBC deyiminin.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `OnSetOptions` için belirtilen ODBC deyimini (seçimini kullanılır) seçeneklerini ayarlamak için. Framework kayıt kümesi için başlangıç seçeneklerini ayarlamak için bu üye işlevi çağırır. `OnSetOptions` kaydırılabilir imleçler ve imleci eşzamanlılık için veri kaynağı destek belirler ve kayıt kümesinin seçenekleri uygun şekilde ayarlar. (Ancak `OnSetOptions` seçimi işlemleri için kullanılan `OnSetUpdateOptions` güncelleştirme işlemleri için kullanılır.)  
  
 Geçersiz kılma `OnSetOptions` seçeneklerini belirli sürücü veya veri kaynağı ayarlamak için. Örneğin, özel erişim için açma destekler, veri kaynağı varsa, geçersiz kılabilir `OnSetOptions` bu yeteneği yararlanmak için.  
  
 İmleçler hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions  
 İçin belirtilen ODBC deyimini (güncelleştirme kullanılır) seçeneklerini ayarlamak için çağrılır.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parametreler  
 `hstmt`  
 **HSTMT** olan seçeneklerdir ayarlanacak ODBC deyiminin.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `OnSetUpdateOptions` için belirtilen ODBC deyimini (güncelleştirme kullanılır) seçeneklerini ayarlamak için. Bir kayıt kümesinde kayıtlarını güncelleştirmek üzere bir HSTMT oluşturduktan sonra framework bu üye işlevi çağırır. (Ancak `OnSetOptions` seçimi işlemleri için kullanılan `OnSetUpdateOptions` güncelleştirme işlemleri için kullanılır.) `OnSetUpdateOptions` kaydırılabilir imleçler ve imleci eşzamanlılık için veri kaynağı destek belirler ve kayıt kümesinin seçenekleri uygun şekilde ayarlar.  
  
 Geçersiz kılma `OnSetUpdateOptions` bu deyim bir veritabanına erişmek için kullanılmadan önce bir ODBC deyiminin seçeneklerini ayarlamak için.  
  
 İmleçler hakkında daha fazla bilgi için bkz: [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="open"></a>  CRecordset::Open  
 Kayıt kümesi tablo alma veya kayıt kümesini temsil eden sorgu gerçekleştirme açar.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>Parametreler  
 `nOpenType`  
 Varsayılan değeri kabul **AFX_DB_USE_DEFAULT_TYPE**, ya da aşağıdaki değerleri kullanın **enum OpenType**:  
  
- **CRecordset::dynaset** çift yönlü kaydırma içeren bir kayıt kümesi. Üyelik ve kayıtları sıralama kayıt açıldığında ama veri değerlerine diğer kullanıcılar tarafından yapılan değişiklikleri getirme işlemi aşağıdaki görünür belirlenir. Dinamik kümeler anahtar kümesi temelli kayıt kümeleri de verilir.  
  
- **CRecordset::snapshot** çift yönlü kaydırma ile statik bir kayıt kümesi. Kayıt kümesi açıldığında, üyelik ve kayıtları sıralama belirlenir; kayıtları getirilen olduğunda veri değerleri belirlenir. Kayıt kümesi kapatılıp yeniden açıldığında kadar diğer kullanıcılar tarafından yapılan değişiklikleri görünür değildir.  
  
- **CRecordset::dynamic** çift yönlü kaydırma içeren bir kayıt kümesi. Üyelik, sıralama ve veri değerleri için diğer kullanıcılar tarafından yapılan değişiklikleri getirme işlemi aşağıdaki görünür. Bu tür bir kayıt kümesi desteklemiyor birçok ODBC sürücüsü unutmayın.  
  
- **CRecordset::forwardOnly** yalnızca ileri kaydırma ile salt okunur bir kayıt kümesi.  
  
     İçin `CRecordset`, varsayılan değer **CRecordset::snapshot**. Varsayılan değer mekanizması hem ODBC ile etkileşim kurmak Visual C++ sihirbazları sağlar `CRecordset` ve DAO `CDaoRecordset`, farklı varsayılan ayarlar vardır.  
  
 Bu kayıt türleri hakkında daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). İlgili bilgi için "Kullanarak blok ve kaydırılabilir imleçler" Windows SDK'sındaki makalesine bakın.  
  
> [!CAUTION]
>  İstenen tür desteklenmiyorsa framework bir özel durum oluşturur.  
  
 `lpszSQL`  
 Aşağıdakilerden birini içeren bir dize işaretçi:  
  
-   A **NULL** işaretçi.  
  
-   Bir tablonun adı.  
  
-   Bir SQL **seçin** deyimi (isteğe bağlı olarak bir SQL **nerede** veya **ORDER BY** yan tümcesi).  
  
-   A **ÇAĞRISI** önceden tanımlanmış sorgu (saklı yordam) adı belirterek deyimi. Süslü ayraç arasında boşluk koymayın dikkatli olun ve **ÇAĞRISI** anahtar sözcüğü.  
  
 Bu dize hakkında daha fazla bilgi için tablo ve ClassWizard'ın rol açıklamalar altında tartışma bakın.  
  
> [!NOTE]
>  Sonuç kümesindeki sütunların sırasını RFX sırasını eşleşmelidir veya toplu RFX işlev çağrıları, [DoFieldExchange](#dofieldexchange) veya [DoBulkFieldExchange](#dobulkfieldexchange) geçersiz kılma işlev.  
  
 `dwOptions`  
 Aşağıda listelenen değerler bileşimini belirtebileceğiniz bir bit maskesi. Bunlardan bazıları karşılıklı olarak birbirini dışlar. Varsayılan değer **hiçbiri**.  
  
- **CRecordset::none** seçenekleri ayarlanmadı. Diğer tüm değerler ile birbirini dışlayan Bu parametre değeridir. Varsayılan olarak, kayıt kümesi ile güncelleştirilebilir [Düzenle](#edit) veya [silmek](#delete) ve yeni kayıtlar ekleme verir [AddNew](#addnew). Güncelleştirilebilirlik bağımlı veri kaynağı üzerinde de olarak `nOpenType` belirttiğiniz seçeneği. İyileştirme toplu eklemeler için kullanılamaz. Toplu satır getirme gerçekleştirilmez. Silinmiş kayıtlar, kayıt kümesi gezinti sırasında atlandı değildir. Yer işaretleri kullanılabilir değil. Otomatik kirli alan denetimi uygulanır.  
  
- **CRecordset::appendOnly** izin verme **Düzenle** veya **silmek** kayıt kümesi üzerinde. İzin `AddNew` yalnızca. Bu seçenek ile birbirini dışlayan **CRecordset::readOnly**.  
  
- **CRecordset::readOnly** salt okunur olarak kayıt kümesi'ni açın. Bu seçenek ile birbirini dışlayan **CRecordset::appendOnly**.  
  
- **CRecordset::optimizeBulkAdd** aynı anda çok sayıda kayıt ekleme en iyi duruma getirmek için hazırlanmış bir SQL deyimini kullanın. Yalnızca ODBC API işlevi kullanmıyorsanız geçerlidir **SQLSetPos** kayıt kümesi güncelleştirilemedi. Hangi alanların kirli olarak işaretlenmiş ilk güncelleştirme belirler. Bu seçenek ile birbirini dışlayan `CRecordset::useMultiRowFetch`.  
  
- `CRecordset::useMultiRowFetch` Bir tek getirme işlemi alınması birden çok satır izin vermek için toplu satır getirme uygulayın. Bu, performansı iyileştirmek için tasarlanmış, Gelişmiş bir özelliktir; Ancak, toplu kayıt alanı değişimi ClassWizard tarafından desteklenmiyor. Bu seçenek ile birbirini dışlayan **CRecordset::optimizeBulkAdd**. Belirttiğiniz gerçekleştiriyorsanız `CRecordset::useMultiRowFetch`, ardından seçeneği **CRecordset::noDirtyFieldCheck** otomatik olarak kapatılacak (iki kez arabelleğe alma kullanılamaz); salt iletme kayıt kümeleri, seçeneği üzerinde  **CRecordset::useExtendedFetch** otomatik olarak kapatılacak. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
- **CRecordset::skipDeletedRecords** tüm silinmiş kayıtlar kayıt kümesi içinde gezinirken atlayın. Bu, belirli göreli öğesinden performansı düşürür. Bu seçenek salt iletme kayıt kümeleri üzerinde geçerli değil. Çağırırsanız [taşıma](#move) ile `nRows` parametresi 0 olarak ayarlanmış ve **CRecordset::skipDeletedRecords** seçenek kümesi **taşıma** assert. Unutmayın **CRecordset::skipDeletedRecords** benzer *sürücü sevk*, silinen satır anlamına kayıt kümesinden kaldırılır. Ancak, kayıtları, sürücü paketleri varsa, bu silme kayıtları atlayın; kayıt kümesi açıkken diğer kullanıcılar tarafından silinen kayıtlar atlayın değil. **CRecordset::skipDeletedRecords** diğer kullanıcılar tarafından silinen satır atlar.  
  
- **CRecordset::useBookmarks** yer işaretleri kayıt kümesinde destekleniyorsa kullanabilir. Yer işaretleri veri alma yavaş ancak veri Gezinti performansını. Salt iletme kayıt kümeleri üzerinde geçerli değil. Daha fazla bilgi için bkz: [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
- **CRecordset::noDirtyFieldCheck** otomatik kirli alan denetimi (iki kez arabelleğe alma devre dışı) açın. Bu performansı iyileştirir; Ancak, el ile alanları olarak kirli çağırarak işaretlemelisiniz `SetFieldDirty` ve `SetFieldNull` üye işlevleri. Bu iki sınıfında kez arabelleğe alma Not `CRecordset` sınıfında çift arabelleğe alma için benzer `CDaoRecordset`. Bununla birlikte, `CRecordset`, tek tek alanlarda iki kez arabelleğe alma etkinleştiremiyor; tüm alanlar için etkinleştirin veya tüm alanlar için devre dışı bırakın. Seçeneğini belirtirseniz, Not `CRecordset::useMultiRowFetch`, ardından **CRecordset::noDirtyFieldCheck** kapatılacak otomatik olarak; ancak, `SetFieldDirty` ve `SetFieldNull` toplu satır getirme uygulayan kayıt kümelerinde kullanılamaz.  
  
- **CRecordset::executeDirect** hazırlanmış bir SQL deyimi kullanmayın. Geliştirilmiş performans için bu seçeneği belirtin **Requery** üye işlevi hiçbir zaman çağrılır.  
  
- **CRecordset::useExtendedFetch** uygulama **SQLExtendedFetch** yerine **SQLFetch**. Bu, toplu satır salt iletme kayıt kümeleri getirme uygulamak için tasarlanmıştır. Seçeneğini belirtirseniz, `CRecordset::useMultiRowFetch` salt iletme kayıt kümesinde, ardından **CRecordset::useExtendedFetch** otomatik olarak kapatılacak.  
  
- **CRecordset::userAllocMultiRowBuffers** kullanıcı verilerini depolama arabellekleri ayırır. Bu seçenek ile birlikte kullanın `CRecordset::useMultiRowFetch` kendi depolama; ayırmak istiyorsanız, aksi takdirde, framework otomatik olarak gerekli depolama ayırır. Daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Bu belirtme Not **CRecordset::userAllocMultiRowBuffers** belirtmeden `CRecordset::useMultiRowFetch` başarısız bir onaylama neden olur.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CRecordset` nesnesi başarıyla açılan; Aksi takdirde 0 ise [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (çağrıldıklarında) 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevini çağırmanız gerekir. Çağırmadan önce **açık**, kayıt kümesi nesnesi oluşturmalıdır.  
  
 Kayıt kümesi çağırmadan önce nasıl oluşturmak bu kayıt kümesinin bağlantı veri kaynağına bağlıdır **açık**. Geçirirseniz bir [CDatabase](../../mfc/reference/cdatabase-class.md) nesne veri kaynağına bağlı değil kayıt kümesi oluşturucuya bu üye fonksiyonu kullanır [GetDefaultConnect](#getdefaultconnect) veritabanı nesnesini açmak çalışır. Geçirirseniz **NULL** kayıt kümesi oluşturucuya Oluşturucusu oluşturur bir `CDatabase` sizin için nesne ve **açık** veritabanı nesnesi bağlanmayı dener. Kayıt kümesi ve değişen bu koşullarda bağlantı kapatma hakkında ayrıntılar için bkz: [Kapat](#close).  
  
> [!NOTE]
>  Bir veri kaynağına erişim bir `CRecordset` nesne her zaman paylaşılır. Farklı `CDaoRecordset` sınıfı, kullanamaz bir `CRecordset` veri kaynağı ile özel erişim açmak için nesne.  
  
 Çağırdığınızda **açık**, genellikle bir SQL sorgu **seçin** deyimi, aşağıdaki tabloda gösterilen ölçütleri temel alarak kayıtları seçer.  
  
|LpszSQL parametresinin değeri|Seçilen kayıt tarafından belirlenir|Örnek|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|Tarafından döndürülen dize `GetDefaultSQL`.||  
|SQL tablosu adı|Tablo listesinde tüm sütunları `DoFieldExchange` veya `DoBulkFieldExchange`.|`"Customer"`|  
|Önceden tanımlanmış sorgu (saklı yordam) adı|Sorgu döndürmek için tanımlanan sütunları.|`"{call OverDueAccts}"`|  
|**SEÇİN** sütun listesi **FROM** Tablo listesi|Belirtilen tablo belirtilen sütunlarından.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  Ek boşluk SQL dizenizi yerleştirmeyin dikkatli olun. Süslü ayraç arasında boşluk eklerseniz, örneğin ve **ÇAĞRISI** anahtar sözcüğü, MFC SQL dizesi olarak bir tablo adı hatalı yorumlayan ve içine dahil bir **seçin** sonuçlanır deyimi bir oluşturulan özel durum. Önceden tanımlanmış sorgu çıktı parametresi kullanıyorsa, kuşak arasında boşluk benzer şekilde, eklemeyin ve '' simgesi. Son olarak, boşluk kaşlı ayraç önce eklemeniz gerekir olmayan bir **ÇAĞRISI** deyimi veya önce **seçin** in anahtar sözcüğü bir **seçin** deyimi.  
  
 Normal yordamını geçirmektir **NULL** için **açık**; bu durumda, **açık** çağrıları [GetDefaultSQL](#getdefaultsql). Türetilmiş kullanıyorsanız `CRecordset` sınıfı, **GetDefaultSQL** ClassWizard içinde belirttiğiniz tablo adlarını sağlar. Bunun yerine diğer bilgileri belirtebilirsiniz `lpszSQL` parametresi.  
  
 Ne olursa olsun geçirdiğiniz **açık** bir son sorgu SQL dizesi oluşturur (dize SQL olabilir **nerede** ve **ORDER BY** yan tümceleri eklenmiş için `lpszSQL` , dize geçirilen) ve ardından sorguyu çalıştırır. Çağrılarak oluşturulan dize inceleyebilirsiniz [GetSQL](#getsql) çağırdıktan sonra **açık**. Kayıt kümesi bir SQL deyimi oluşturur ve kayıtları, seçer hakkında ek ayrıntıları görmek için makaleyi [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
 Kayıt kümesi sınıfınız alan veri üyeleri, seçtiğiniz veri sütunlarının bağlıdır. Hiçbir kayıt döndürülmezse, ilk kaydı geçerli kaydı olur.  
  
 Filtre veya sıralama gibi kayıt seçeneklerini ayarlamak istiyorsanız kayıt kümesi nesnesi oluşturun sonra ancak çağırmadan önce bu belirtin **açık**. Sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız kayıt kümesi zaten açık, çağrı [Requery](#requery).  
  
 Makaleleri ek örnekler dahil olmak üzere daha fazla bilgi için bkz: [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md), [kayıt kümesi: nasıl kayıt kümeleri seçin kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), ve [kayıt kümesi: oluşturma ve kapatma Kayıt kümeleri (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örnekleri farklı biçimlerde Göster **açık** çağırın.  
  
 [!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset  
 Veri ve geçerli satır kümesindeki durumunu güncelleştirir.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parametreler  
 `wRow`  
 Tabanlı konumu bir satır geçerli satır kümesi. Bu değer, satır boyutu sıfırdan değişebilir.  
  
 `wLockType`  
 Bunu yenilendikten sonra satır kilitlemek nasıl belirten bir değer. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin sıfır değeri geçirirseniz `wRow`, her satır kümesinde yenilenecek sonra.  
  
 Kullanılacak `RefreshRowset`, belirterek toplu satır getirme uygulanan gerekir **CRecordset::useMulitRowFetch** seçeneğini [açık](#open) üye işlevi.  
  
 `RefreshRowset` ODBC API işlev çağrılarını **SQLSetPos**. `wLockType` Parametresi, sonra satır kilit durumunu belirtir **SQLSetPos** yürütüldü. Aşağıdaki tabloda olası değerleri açıklanmaktadır `wLockType`.  
  
|wLockType|Açıklama|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (varsayılan değer)|Sürücü veya veri kaynağı önce olduğu gibi satır aynı kilitli veya kilidi açılmış durumda olmasını sağlar `RefreshRowset` çağrıldı.|  
|`SQL_LOCK_EXCLUSIVE`|Sürücü veya veri kaynağı, satır özel olarak kilitler. Tüm veri kaynakları bu kilit türünü destekler.|  
|`SQL_LOCK_UNLOCK`|Sürücü veya veri kaynağı, satır kilidini açar. Tüm veri kaynakları bu kilit türünü destekler.|  
  
 Hakkında daha fazla bilgi için **SQLSetPos**, Windows SDK konusuna bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="requery"></a>  CRecordset::Requery  
 Yeniden oluşturur (yenilemeleri) bir kayıt kümesi.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi başarıyla yeniden oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir kayıt döndürülmezse, ilk kaydı geçerli kaydı olur.  
  
 Kayıt kümesinin ekleme ve siz veya diğer kullanıcılar için veri kaynağı kuran silmeleri yansıtmak sırayla çağırarak kayıt döndürmelisiniz **Requery**. Kayıt kümesi bir dinamik ise, sizin veya diğer kullanıcıların kendi mevcut kayıtları (ancak değil eklemeleri) olun güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntü ise, çağırmalısınız **Requery** diğer kullanıcıların yanı sıra ekleme ve silme işlemleri tarafından düzenlemeleri yansıtmak için.  
  
 Dinamik küme veya anlık görüntü için çağrı **Requery** yeni bir filtre veya sıralama ya da yeni parametre değerlerini kullanarak kayıt yeniden oluşturmak için istediğiniz zaman. Yeni değerler atayarak yeni filtre veya sıralama özelliğini ayarlayın **m_strFilter** ve `m_strSort` çağırmadan önce **Requery**. Parametre veri üyeleri çağırmadan önce yeni değerleri atayarak yeni parametreler Ayarla **Requery**. Filtrelemek ve sıralamak dizeleri aynıdır, sorgu performansını artırır yeniden kullanabilirsiniz.  
  
 Kayıt kümesi yeniden denemesi başarısız olursa, kayıt kümesinin kapalı. Çağırmadan önce **Requery**, kayıt kümesinin çağırarak yeniden olup olmadığını belirlemek `CanRestart` üye işlevi. `CanRestart` garanti etmez **Requery** başarılı olur.  
  
> [!CAUTION]
>  Çağrı **Requery** yalnızca adlı sonra [açık](#open).  
  
### <a name="example"></a>Örnek  
 Bu örnekte, farklı bir sıralama düzeni uygulamak için bir kayıt oluşturur.  
  
 [!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition  
 Belirtilen kayıt sayısı için karşılık gelen kayıt kayıt yerleştirir.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>Parametreler  
 `nRows`  
 Bir temel sıralı bir konum geçerli kayıt kümesinde.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAbsolutePosition` Bu sıra konumuna bağlı geçerli kayıt işaretçisi taşır.  
  
> [!NOTE]
>  Bu üye işlevi salt iletme kayıt kümeleri üzerinde geçerli değil.  
  
 ODBC kayıt kümeleri için kayıt kümesindeki ilk kaydı bir mutlak konum ayarı 1'in başvurduğu; 0 ayarı dosya başına (BOF) konuma başvuruyor.  
  
 Negatif değerler geçebilen `SetAbsolutePosition`. Bu durumda kayıt kümesinin konumu kayıt sonundan değerlendirilir. Örneğin, `SetAbsolutePosition( -1 )` son kaydı kayıt kümesindeki geçerli kayıt işaretçisi taşır.  
  
> [!NOTE]
>  Mutlak konum yedek kayıt numarası kullanılmak üzere tasarlanmamıştır. Yer işaretleri hala korur ve belirli bir konuma önceki kayıtları silindiğinde bir kaydın konum değişiklikleri itibaren döndürme için önerilen yoldur. Ayrıca, bir SQL deyimi kullanarak bir yapılandırılmadığısürecebirkayıtkümesiiçindetektekkayıtlarınsırasıkesindeğildirçünkükayıtyenidenyenidenoluşturulursa,verilenbirkaydınaynımutlakkonumgerekirgarantiedilemez**ORDER BY** yan tümcesi.  
  
 Kayıt kümesi gezinti ve yer işaretleri hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) ve [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="setbookmark"></a>  CRecordset::SetBookmark  
 Kayıt kümesi belirtilen yer işareti içeren kaydında yerleştirir.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parametreler  
 `varBookmark`  
 Bir başvuru bir [CDBVariant](../../mfc/reference/cdbvariant-class.md) belirli bir kayıt yer işareti değeri içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Yer işaretleri kayıt kümesinde desteklenip desteklenmediğini belirlemek için arama [CanBookmark](#canbookmark). Bunlar destekleniyorsa yer işaretleri kullanılabilir hale getirmek ayarlamalısınız **CRecordset::useBookmarks** seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi.  
  
> [!NOTE]
>  Yer işaretleri desteklenmeyen veya kullanılamayan çağrılmadan `SetBookmark` oluşturulan bir özel durum neden olur. Yer işaretleri salt iletme kayıt kümeleri desteklenmez.  
  
 Önce geçerli kayıt için yer almak için arama [GetBookmark](#getbookmark), yer işareti değeri kaydeder bir `CDBVariant` nesnesi. Çağırarak kayda daha sonra dönebilmek `SetBookmark` kaydedilmiş yer işareti değeri kullanılarak.  
  
> [!NOTE]
>  Belirli kayıt işlemlerinden sonra çağırmadan önce yer işareti Kalıcılık denetlemelisiniz `SetBookmark`. Örneğin, bir yer işareti ile alırsanız `GetBookmark` ve ardından arama **Requery**, yer işareti artık geçerli olmayabilir. Çağrı [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) güvenle çağırabilirsiniz olup olmadığını denetlemek için `SetBookmark`.  
  
 Yer işaretleri ve kayıt kümesi gezinme hakkında daha fazla bilgi için makalelerine bakın [kayıt kümesi: yer işaretleri ve Mutlak Konumlar (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) ve [kayıt kümesi: kaydırma (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty  
 Alan veri üyesi kümesinin değiştirilmiş veya değişmemiş olarak işaretler.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Alan veri üyesi kümesinde adresini içerir veya **NULL**. Varsa **NULL**, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ **NULL** Null aynı veritabanı terminolojisinde değil "hiçbir değere sahip." anlamına gelir)  
  
 `bDirty`  
 **DOĞRU** alan veri üyesi kirli"(değiştirilmiş)"olarak işaretlenmiş ise. Aksi takdirde **FALSE** alan veri üyesi temizleme"(değişmeden)"olarak işaretlenmiş ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Alanlar değiştirilmemiş olarak işaretleme alan güncelleştirilmez ve daha az SQL trafik sonuçları sağlar.  
  
> [!NOTE]
>  Bu üye işlevi toplu satır getirme kullanarak kümelerinde geçerli değildir. Toplu satır getirme, daha sonra uyguladıysanız `SetFieldDirty` içinde başarısız onaylama neden olur. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Bunlar veri kaynağı kaydı kayıt alanı değişimi (RFX) mekanizması tarafından yazılır emin olmak için alan veri üyeleri framework işaretleri değiştirildi. Genellikle bir alanın değerini değiştirme ayarlar alan kirli otomatik olarak nadiren çağırmanız gerekir böylece `SetFieldDirty` kendiniz ancak, bazen isteyebileceğiniz sütunları açıkça güncelleştirilmiş veya kaldırılacak hangi değeri alanı verileri bağımsız olarak eklenir, emin olmak üye.  
  
> [!CAUTION]
>  Yalnızca adlı sonra bu üye işlevini çağırın [Düzenle](#edit) veya [AddNew](#addnew).  
  
 Kullanarak **NULL** işlevinin ilk bağımsız değişkeni işlevi yalnızca uygulanır için **outputColumn** alanları değil, **param** alanları. Örneğin, arama  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 yalnızca ayarlayacaktır **outputColumn** alanları **NULL**; **param** alanları etkilenmemesini olacaktır.  
  
 Üzerinde çalışmak için **param** alanları tek tek gerçek adresini sağlamalısınız **param** gibi çalışmak istediğiniz:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Tüm ayarlayamıyor yani **param** alanları **NULL**ile yapabileceğiniz gibi **outputColumn** alanları.  
  
##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull  
 Alan veri kayıt kümesinin üyesi (özellikle herhangi bir değer sahip) Null veya boş olmayan olarak işaretler.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Alan veri üyesi kümesinde adresini içerir veya **NULL**. Varsa **NULL**, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ **NULL** Null aynı veritabanı terminolojisinde değil "hiçbir değere sahip." anlamına gelir)  
  
 `bNull`  
 Herhangi bir değer (boş) sahip olarak işaretlenmesini alan veri üyesi ise, sıfır olmayan. Null olmayan işaretlenmesini alan veri üyesi ise, aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlayın ve kirli"(değiştirilmiş)"olarak işaretlenmiş. Bir kayıt bir veri kaynağından veri almak, sütunlarını zaten değerlere sahip ya da Null şunlardır.  
  
> [!NOTE]
>  Toplu satır getirme kullanarak kümelerinde bu üye işlevini çağırmanız gerekmez. Toplu satır getirme uyguladıysanız, çağırma `SetFieldNull` sonuçları başarısız bir onaylama. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Özellikle geçerli kayıt alanı çağrısı bir değer olmaması olarak atamak istiyorsanız `SetFieldNull` ile `bNull` kümesine **TRUE** Null olarak işaretleyemedi. Bir alan daha önce Null işaretlendi ve artık bir değere vermek istediğiniz, yalnızca yeni değerini ayarlayın. Null bayrağı ile kaldırmak zorunda değilsiniz `SetFieldNull`. Alanın Null olmasına izin verilip verilmediğini belirlemek için arama `IsFieldNullable`.  
  
> [!CAUTION]
>  Yalnızca adlı sonra bu üye işlevini çağırın [Düzenle](#edit) veya [AddNew](#addnew).  
  
 Kullanarak **NULL** işlevinin ilk bağımsız değişkeni işlevi yalnızca uygulanır için **outputColumn** alanları değil, **param** alanları. Örneğin, arama  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 yalnızca ayarlayacaktır **outputColumn** alanları **NULL**; **param** alanları etkilenmemesini olacaktır.  
  
 Üzerinde çalışmak için **param** alanları tek tek gerçek adresini sağlamalısınız **param** gibi çalışmak istediğiniz:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Tüm ayarlayamıyor yani **param** alanları **NULL**ile yapabileceğiniz gibi **outputColumn** alanları.  
  
> [!NOTE]
>  Null, çağrı için parametreler ayarlanırken `SetFieldNull` önce kayıt onayı ifade açılan sonuçlanır. Bu durumda, çağrı [SetParamNull](#setparamnull).  
  
 `SetFieldNull` aracılığıyla uygulanır [DoFieldExchange](#dofieldexchange).  
  
##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode  
 "İyimser" (varsayılan) kilitleme ya da "kötümser" kilitleme Kilitleme modunu ayarlar. Güncelleştirmeleri kayıtların nasıl kilitlenmiş belirler.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMode`  
 Aşağıdaki değerlerden birini içeren **enum LockMode**:  
  
- **İyimser** İyimser kilitleme kilitler çağrı sırasında yalnızca güncelleştirilmekte kayıt **güncelleştirme**.  
  
- **Kötümser** kötümser kilitleme kilitler kaydı hemen **Düzenle** adı verilir ve bu kadar kilitli tutar **güncelleştirme** çağrısı tamamlandığında veya yeni bir kayda gider.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi için güncelleştirmeleri kullanarak iki kayıt kilitleme stratejileri belirtmek gerekirse bu üye işlevini çağırın. Varsayılan olarak, bir kayıt kümesinin kilitleme modudur **iyimser**. Daha dikkatli değiştirmek için **kötümser** stratejisi kilitleme. Çağrı `SetLockingMode` oluşturmak ve kayıt kümesi nesnesi açtıktan sonra ancak çağırmadan önce **Düzenle**.  
  
##  <a name="setparamnull"></a>  CRecordset::SetParamNull  
 Bir parametre (özellikle herhangi bir değer sahip) Null veya boş olmayan olarak işaretler.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Parametre sıfır tabanlı dizini.  
  
 `bNull`  
 Varsa **TRUE** (varsayılan değer) parametresi boş olarak işaretlenir. Aksi takdirde, parametre Null olmayan işaretlenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Farklı [SetFieldNull](#setfieldnull), çağırabilirsiniz `SetParamNull` kayıt açılmadan.  
  
 `SetParamNull` genellikle önceden tanımlanmış sorgular (saklı yordamları) kullanılır.  
  
##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition  
 Geçerli satır kümesi içinde bir satır için imleci taşır.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parametreler  
 `wRow`  
 Tabanlı konumu bir satır geçerli satır kümesi. Bu değer 1'den satır boyutunu arasında değişebilir.  
  
 `wLockType`  
 Bunu yenilendikten sonra satır kilitlemek nasıl belirten değer. Açıklamalar Ayrıntılar için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Toplu satır getirme uygularken kayıtları ilk kaydı getirilen satır kümesindeki geçerli kayıt olduğu satır kümeleri tarafından alınır. Geçerli kayıt başka bir kayıtla satır içinde yapmak için arama `SetRowsetCursorPosition`. Örneğin, birleştirebilirsiniz `SetRowsetCursorPosition` ile [GetFieldValue](#getfieldvalue) veri kümenizin herhangi kaydından dinamik olarak almak için üye işlevi.  
  
 Kullanılacak `SetRowsetCursorPosition`, belirterek toplu satır getirme uygulanan gerekir `CRecordset::useMultiRowFetch` seçeneği `dwOptions` parametresinde [açık](#open) üye işlevi.  
  
 `SetRowsetCursorPosition` ODBC API işlev çağrılarını **SQLSetPos**. `wLockType` Parametresi, sonra satır kilit durumunu belirtir **SQLSetPos** yürütüldü. Aşağıdaki tabloda olası değerleri açıklanmaktadır `wLockType`.  
  
|wLockType|Açıklama|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (varsayılan değer)|Sürücü veya veri kaynağı önce olduğu gibi satır aynı kilitli veya kilidi açılmış durumda olmasını sağlar `SetRowsetCursorPosition` çağrıldı.|  
|`SQL_LOCK_EXCLUSIVE`|Sürücü veya veri kaynağı, satır özel olarak kilitler. Tüm veri kaynakları bu kilit türünü destekler.|  
|`SQL_LOCK_UNLOCK`|Sürücü veya veri kaynağı, satır kilidini açar. Tüm veri kaynakları bu kilit türünü destekler.|  
  
 Hakkında daha fazla bilgi için **SQLSetPos**, Windows SDK konusuna bakın. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize  
 Getirme sırasında almak istediğiniz kayıt sayısını belirtir.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>Parametreler  
 *dwNewRowsetSize*  
 Belirli bir getirme sırasında alınacak satır sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sanal üye işlevi, tek bir getirme sırasında toplu satır getirme kullanırken almak istediğiniz satır sayısını belirtir. Toplu satır getirme uygulamak için ayarlamalısınız `CRecordset::useMultiRowFetch` seçeneğini `dwOptions` parametresinin [açık](#open) üye işlevi.  
  
> [!NOTE]
>  Çağırma `SetRowsetSize` toplu uygulamadan satır getirme başarısız onaylama içinde neden olur.  
  
 Çağrı `SetRowsetSize` çağırmadan önce **açık** başlangıçta kayıt kümesi satır kümesi boyutunu ayarlamak için. Toplu satır getirme uygularken varsayılan satır kümesi boyutu 25'tir.  
  
> [!NOTE]
>  Çağrılırken dikkatli `SetRowsetSize`. Depolama alanı için verileri el ile ayrılırken varsa (belirtildiği gibi **CRecordset::userAllocMultiRowBuffers** dwOptions parametresinde seçeneği **açık**), gerekip gerekmediğini denetleyin çağırdıktan sonra bu depolama arabellekleri yeniden tahsis `SetRowsetSize`, ancak herhangi bir imleç gezinme işlemi gerçekleştirmeden önce.  
  
 Satır kümesi boyutu için geçerli ayarları almak için arama [GetRowsetSize](#getrowsetsize).  
  
 Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="update"></a>  CRecordset::Update  
 Tamamlanan bir `AddNew` veya **Düzenle** veri kaynağı üzerinde yeni veya düzenlenen veriler kaydederek işlemi.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kayıt başarıyla güncelleştirildiyse sıfır olmayan; Hiçbir sütun değiştirdiyseniz, aksi takdirde 0. Hiçbir kayıtlar güncelleştirildi ya da birden fazla bir kayıt güncelleştirildi, özel durum oluşur. Özel veri kaynağı için herhangi bir hata durum oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı sonra bu üye işlevini çağırın [AddNew](#addnew) veya [Düzenle](#edit) üye işlevi. Bu çağrı tamamlamak için gereken `AddNew` veya **Düzenle** işlemi.  
  
> [!NOTE]
>  Toplu satır getirme uyguladıysanız, çağıramazsınız **güncelleştirme**. Bu başarısız bir onaylama neden olacaktır. Ancak sınıfı `CRecordset` bir mekanizma sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevleri ODBC API işlevini kullanarak yazabilirsiniz **SQLSetPos**. Toplu satır getirme hakkında daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Her ikisi de `AddNew` ve **Düzenle** kaydetme veri kaynağına eklenen veya düzenlenen verilerin yerleştirilir düzenleme arabelleği hazırlayın. **Güncelleştirme** verileri kaydeder. İşaretlenen veya değiştirilen olarak algılanan yalnızca bu alanları güncelleştirilir.  
  
 Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz **güncelleştirme** çağrı (ve ilgili `AddNew` veya **Düzenle** çağrısı) bir işlemin parçası. İşlemler hakkında daha fazla bilgi için bkz: [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!CAUTION]
>  Çağırırsanız **güncelleştirme** ilk ya da çağırma `AddNew` veya **Düzenle**, **güncelleştirme** oluşturur bir `CDBException`. Çağırırsanız `AddNew` veya **Düzenle**, çağırmalısınız **güncelleştirme** çağırmadan önce bir **taşıma** işlem veya kayıt kümesi veya veri kaynağı bağlantısı kapatmadan önce. Aksi takdirde, bildirim değişiklikleriniz kaybolur.  
  
 İşleme hakkında ayrıntılı bilgi için **güncelleştirme** hataları, başlıklı makaleye bakın [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
### <a name="example"></a>Örnek  
 Makalesine bakın [işlem: bir kayıt kümesi (ODBC) işlem gerçekleştirme](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDatabase sınıfı](../../mfc/reference/cdatabase-class.md)   
 [CRecordView Sınıfı](../../mfc/reference/crecordview-class.md)
