---
title: CDaoRecordset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 08e5433cfd7d1627babb4750c94396602a8f276c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400542"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset sınıfı

Bir veri kaynağından seçilen kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Oluşturur bir `CDaoRecordset` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordset::AddNew](#addnew)|Yeni bir kayıt eklemek için hazırlar. Çağrı [güncelleştirme](#update) eklenmesi tamamlanması.|
|[CDaoRecordset::CanAppend](#canappend)|Yeni kayıtlar kayıt kümesine eklenebilir, sıfır döndürür [AddNew](#addnew) üye işlevi.|
|[CDaoRecordset::CanBookmark](#canbookmark)|Kayıt kümesi yer işaretleri destekliyorsa, sıfır döndürür.|
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Beklemedeki Güncelleştirmeleri nedeniyle iptal bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi.|
|[CDaoRecordset::CanRestart](#canrestart)|Döndürür gösterimiyse [Requery](#requery) kümesinin sorguyu yeniden çalıştırmayı çağrılabilir.|
|[CDaoRecordset::CanScroll](#canscroll)|Kayıtlarda gezinmek, sıfır döndürür.|
|[CDaoRecordset::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa, sıfır döndürür.|
|[CDaoRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilebilir, sıfır döndürür (ekleyebilir, güncelleştirme veya kayıtlarını sil).|
|[CDaoRecordset::Close](#close)|Kayıt kümesi kapatır.|
|[CDaoRecordset::Delete](#delete)|Geçerli kayıt kayıt kümesinden siler. Silindikten sonra başka bir kayıtla açıkça kaydırma gerekir.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Kayıt alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements DAO alanı değişimi (DFX) kaydedin.|
|[CDaoRecordset::Edit](#edit)|Değişiklikleri geçerli kayda hazırlar. Çağrı `Update` düzenlemeyi tamamlamak için.|
|[CDaoRecordset::FillCache](#fillcache)|Dolgular tüm veya bir yerel önbellek bir ODBC veri kaynağından alınan veriler içeren bir kayıt kümesi nesnesi için bir parçası.|
|[CDaoRecordset::Find](#find)|İlk olarak, sonraki bulur geçerli kayıt kaydı yapar ve belirtilen ölçütleri karşılayan bir dinamik tür kümesinde belirli bir dizenin önceki ya da son konum.|
|[CDaoRecordset::FindFirst](#findfirst)|Bir dinamik tür ya da anlık görüntü türü kayıt kümesi geçerli kayıt kaydı yapar ve belirtilen ölçütleri karşılayan ilk kaydı bulur.|
|[CDaoRecordset::FindLast](#findlast)|Son kayda bir dinamik tür ya da geçerli kayıt kaydı yapar ve belirtilen ölçütleri karşılayan bir anlık görüntü türü kayıt kümesi bulur.|
|[CDaoRecordset::FindNext](#findnext)|Sonraki kayda bir dinamik tür ya da geçerli kayıt kaydı yapar ve belirtilen ölçütleri karşılayan bir anlık görüntü türü kayıt kümesi bulur.|
|[CDaoRecordset::FindPrev](#findprev)|Dinamik tür ya da geçerli kayıt kaydı yapar ve belirtilen ölçütleri karşılayan bir anlık görüntü türü kayıt kümesi içinde önceki kaydı bulur.|
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını döndürür.|
|[CDaoRecordset::GetBookmark](#getbookmark)|Bir kayıtta yer işareti temsil eden bir değer döndürür.|
|[CDaoRecordset::GetCacheSize](#getcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dinamik türü kayıt kümesindeki kayıt sayısını belirten bir değeri döndürür.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|Önbelleğe alınacak kayıt kümesinde yer ilk kaydın belirten bir değeri döndürür.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Döndürür bir `CString` dizinin adını içeren en son kullanılan dizini bir tablo-türü `CDaoRecordset`.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Temel tablo temel tarihi ve saati döndürür. bir `CDaoRecordset` nesnesi oluşturuldu|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Tarih ve saat, temel alınan temel tablo tasarımı için yapılan en son değişikliği döndürür bir `CDaoRecordset` nesne.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Varsayılan veri kaynağı adını döndürür.|
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Yürütmek için varsayılan SQL dizesini almak için çağrılır.|
|[CDaoRecordset::GetEditMode](#geteditmode)|Düzenleme için geçerli kayıt durumunu gösteren bir değer döndürür.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Bir kayıt içindeki alanların sayısını temsil eden bir değer döndürür.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Kayıt kümesinde belirli tür alanları hakkında bilgileri döndürür.|
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Bir kayıt kümesinde bir alanın değerini döndürür.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|Bir kayıt kümesi temel alınan tablodaki dizinler sayısını alır.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Çeşitli dizin hakkında bilgi döndürür.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|En son eklenen veya güncelleştirilen kaydı belirlemek için kullanılır.|
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Düzenleme sırasında yürürlükte olan kilitleme türünü belirten bir değer döndürür.|
|[CDaoRecordset::GetName](#getname)|Döndürür bir `CString` kayıt kümesi adını içeren.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|Temel alınan DAOParameter nesnesinde depolanan belirtilen parametresinin geçerli değerini alır.|
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Geçerli kayıt konumunu toplam kayıt sayısı yüzdesi olarak döndürür.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Bir kayıt kümesi nesnesi erişilen kayıt sayısını döndürür.|
|[CDaoRecordset::GetSQL](#getsql)|Kayıt kümesi kayıtları seçmek için kullanılan SQL dizesi alır.|
|[CDaoRecordset::GetType](#gettype)|Bir kayıt türünü belirlemek için çağırılır: Tablo türü, dinamik küme türü veya anlık görüntü türü.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Döndürür bir `CString` alana girerken, verileri doğrular değerini içeren.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Bir doğrulama kuralı koşullar karşılanırsa görüntülenen metni alır.|
|[CDaoRecordset::IsBOF](#isbof)|İlk kayıttan önce kayıt üzere konumlandırmıştır sıfır olmayan döndürür. Geçerli kayıt yok.|
|[CDaoRecordset::IsDeleted](#isdeleted)|Kayıt kümesini silinmiş bir kayda konumlandırıldı, sıfır döndürür.|
|[CDaoRecordset::IsEOF](#iseof)|Son kayıttan sonra kayıt üzere konumlandırmıştır, sıfır döndürür. Geçerli kayıt yok.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Belirtilen alan geçerli kayıt değiştirilmişse, sıfır döndürür.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıt belirtilen alan Null (hiçbir değer yok) ise sıfır döndürür.|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|(Hiçbir değer yok), geçerli kayıtta belirtilen alan Null olarak ayarlanabilir, sıfır döndürür.|
|[CDaoRecordset::IsOpen](#isopen)|Döndürür gösterimiyse [açık](#open) daha önce çağırıldı.|
|[CDaoRecordset::Move](#move)|Kayıt belirli bir kayıt sayısı için herhangi bir yönde geçerli kaydından yerleştirir.|
|[CDaoRecordset::MoveFirst](#movefirst)|İlk kayıt kayıt kümesindeki geçerli kayıt yerleştirir.|
|[CDaoRecordset::MoveLast](#movelast)|Kümesinde son kayıtta geçerli kayıt yerleştirir.|
|[CDaoRecordset::MoveNext](#movenext)|Sonraki kayıt kayıt kümesindeki geçerli kayıt yerleştirir.|
|[CDaoRecordset::MovePrev](#moveprev)|Önceki kayıt kayıt kümesindeki geçerli kayıt yerleştirir.|
|[CDaoRecordset::Open](#open)|Yeni bir kayıt tablosu, dinamik veya anlık görüntü oluşturur.|
|[CDaoRecordset::Requery](#requery)|Yeniden seçilen kayıtları yenilemek için kayıt kümesinin sorgusu çalıştırır.|
|[CDaoRecordset::Seek](#seek)|Geçerli kayıt kaydı yapar ve geçerli dizin için belirtilen ölçütleri karşılayan bir dizinlenmiş tablo türü kayıt kümesi nesnesi içinde kaydı bulur.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını ayarlar.|
|[CDaoRecordset::SetBookmark](#setbookmark)|Belirtilen yer işareti içeren bir kayda kayıt kümesini yerleştirir.|
|[CDaoRecordset::SetCacheSize](#setcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dinamik türü kayıt kümesindeki kayıt sayısını belirten bir değeri ayarlar.|
|[CDaoRecordset::SetCacheStart](#setcachestart)|Önbelleğe alınacak kayıt kümesinde yer ilk kaydın belirten bir değeri ayarlar.|
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Bir dizin üzerinde tablo türünde bir kayıt kümesi ayarlamak için çağrılır.|
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıt belirtilen alan değiştirilmiş olarak işaretler.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Null (hiçbir değer yok) geçerli kayıttaki belirtilen alanın değerini ayarlar.|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Bir kayıt kümesinde bir alanın değerini ayarlar.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Bir kayıt kümesi null bir alanın değerini ayarlar. (hiçbir değer yok).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Düzenleme sırasında yürürlüğe koymak için kilitleme türünü belirten bir değer ayarlar.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|Temel alınan DAOParameter nesnesinde depolanan belirtilen parametresinin geçerli değerini ayarlar.|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Belirtilen parametre geçerli değeri Null (hiçbir değer yok) olarak ayarlar.|
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Bir kayıt kümesindeki kayıtları toplam sayısının yüzdesi karşılık gelen bir konuma geçerli kayıt konumunu ayarlar.|
|[CDaoRecordset::Update](#update)|Tamamlanan bir `AddNew` veya `Edit` yeni veya düzenlenmiş verilerin veri kaynağında kaydederek işlemi.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Alanları otomatik olarak değiştirilmiş olarak işaretlenmiş olup olmadığını belirten bir bayrak içerir.|
|[CDaoRecordset::m_nFields](#m_nfields)|Alan veri üyeleri kayıt kümesi sınıfında sayısı ve kayıt veri kaynağından seçili sütun sayısını içerir.|
|[CDaoRecordset::m_nParams](#m_nparams)|Kayıt kümesi sınıfı parametre veri üyeleri sayısını içerir — parametrelerin sayısı geçirilen kümesinin sorgu|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Kayıt kümesi nesnesi temel DAO arabirim işaretçisi.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Bu sonuç kümesi için kaynak veritabanı. Bir işaretçi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.|
|[CDaoRecordset::m_strFilter](#m_strfilter)|Bir SQL oluşturmak için kullanılan bir dize içeren **burada** deyimi.|
|[CDaoRecordset::m_strSort](#m_strsort)|Bir SQL oluşturmak için kullanılan bir dize içeren **ORDER BY** deyimi.|

## <a name="remarks"></a>Açıklamalar

"Kayıt kümeleri," bilinen `CDaoRecordset` aşağıdaki üç formlarında nesneleri kullanılabilir:

- Tablo türü kayıt kümeleri inceleyin, ekleme, değiştirme veya bir tek veritabanı tablosundan kayıtları silmek için kullanabileceğiniz bir temel tablo temsil eder.

- Dinamik tür kayıt kümeleri güncelleştirilebilir kayıtlarını içeren bir sorgu sonucudur. Bu kayıt kümeleri, inceleyin, eklemek, değiştirmek veya temel bir veritabanı tablosu ya da tablo kayıtlarını silmek için kullanabileceğiniz bir kayıt kümesidir. Dinamik tür kayıt kümeleri bir veritabanındaki bir veya daha fazla tablolardan alanlar içerebilir.

- Anlık görüntü türü kayıt kümeleri, veri bulma veya raporlar oluşturmak için kullanabileceğiniz bir kayıt kümesini statik bir kopyasını ' dir. Bu kayıt kümeleri, bir veritabanındaki bir veya daha fazla tablolardan alanlar içerebilir ancak güncelleştirilemiyor.

Her form kümesinin kayıt açıldığında sabit kayıt kümesini temsil eder. Tablo türünde bir kayıt kümesi veya dinamik türünde bir kayıt kümesi bir kayıtta gidin, kayıt kümesi açıldı diğer kullanıcılar tarafından veya uygulamanızdaki diğer kayıt kümeleri tarafından kaydı yapılan değişiklikleri yansıtır. (Bir anlık görüntü türü kayıt güncelleştirilemiyor.) Kullanabileceğiniz `CDaoRecordset` doğrudan veya bir uygulamaya özgü kayıt sınıfından türetilir `CDaoRecordset`. Ardından şunları yapabilirsiniz:

- Kayıtlarda gezinin.

- Dizin ayarlama ve hızlı bir şekilde kullanarak kayıtları arar [arama](#seek) (yalnızca tablo türü kayıt kümeleri).

- Dize karşılaştırma üzerine dayalı kayıtları bulma: "<","\<=", "=", "> =", veya ">" (dinamik tür ve anlık görüntü türü kayıt kümeleri).

- Kayıtları güncelleştirmek ve (anlık görüntü türü kayıt kümeleri dışında) bir kilitleme modunu belirtin.

- Veri kaynağında mevcut kodlar arasından seçen kayıtları sınırlamak için kayıt filtreleyin.

- Kayıt kümesi sıralayın.

- Çalışma zamanına kadar bilinmiyor bilgilerle, seçim özelleştirmek için kayıt kümesini parametreleştirme.

Sınıf `CDaoRecordset` sınıfı için benzer bir arabirim sağlayan `CRecordset`. Bu sınıf ana fark `CDaoRecordset` veri aracılığıyla bir veri erişim nesnesi (OLE üzerinde temel DAO) erişir. Sınıf `CRecordset` DBMS bu DBMS için açık veritabanı bağlantısı (ODBC) ve ODBC sürücüsü aracılığıyla erişir.

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. Hala DAO sınıfları ile ODBC veri kaynaklarına erişim de kullanabilirsiniz. DAO sınıfları, genellikle Microsoft Jet veritabanı altyapısına özgü olduğundan üstün özellikler sunar.

Kullanabilir `CDaoRecordset` doğrudan veya bir sınıftan türetilen `CDaoRecordset`. Her iki durumda da bir kayıt kümesi sınıfını kullanmak için bir veritabanı açın ve oluşturucusu için bir işaretçi geçirerek bir kayıt kümesi nesnesi oluşturun, `CDaoDatabase` nesne. Ayrıca oluşturabilirsiniz bir `CDaoRecordset` nesne ve geçici bir oluşturma MFC izin `CDaoDatabase` nesnesi. Ardından kayıt kümesinin çağrı [açık](#open) üye işlevi, nesnenin bir tablo türü kayıt, dinamik türünde bir kayıt kümesi ya da bir anlık görüntü türü kayıt olup olmadığını belirleme. Çağırma `Open` veritabanından verileri seçer ve ilk kaydı alır.

Nesnenin üye işlevler ve veriler üyeleri kayıtlarda gezinin ve üzerlerinde çalışmak için kullanır. Nesnesi bir tablo türü kayıt, dinamik türünde bir kayıt kümesi ya da bir anlık görüntü türü kayıt olup olmadığı ve güncelleştirilebilir veya salt okunur olup kullanılabilen işlemleri bağlıdır; bu veritabanı veya açık veritabanı bağlantısı (ODBC) yeteneğini bağlıdır veri kaynağı. Değiştirilmiş veya olabilir beri eklenen kayıtları yenilemek için `Open` çağrı, nesnenin çağrı [Requery](#requery) üye işlevi. Nesnenin `Close` üye işlev ve ile işiniz bittiğinde nesneyi yok edin.

`CDaoRecordset` DAO kayıt alanı değişimi (DFX) tür kullanımı uyumlu C++ üye okuma ve kayıt alanlarının güncelleştirmeyi desteklemek için kullanır, `CDaoRecordset` veya `CDaoRecordset`-türetilmiş sınıf. DFX mekanizması kullanılarak kullanmadan bir veritabanında sütunların dinamik bağlama uygulayabilirsiniz [GetFieldValue](#getfieldvalue) ve [SetFieldValue](#setfieldvalue).

İlgili bilgiler için DAO Yardımı'nda "kayıt kümesi nesnesi" konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="addnew"></a>  CDaoRecordset::AddNew

Bir tablo türü veya tür dinamik kayıt kümesine yeni bir kayıt eklemek için bu üye işlevini çağırın.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Kaydın alanları başlangıçta Null. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve C++'ta NULL ile aynı değildir.) İşlemi tamamlamak için çağırmalıdır [güncelleştirme](#update) üye işlevi. `Update` yaptığınız değişiklikleri veri kaynağına kaydeder.

> [!CAUTION]
>  Bir kaydı düzenlemek ve başka bir kayıt çağırmadan kaydırarak `Update`, uyarı vermeden değişiklikleriniz kaybolur.

Çağırarak bir kayıt türü dinamik kayıt kümesine eklerseniz [AddNew](#addnew), kayıt kümesinde görünür ve burada bunu görünür hale gelir herhangi yeni temel alınan tabloda bulunan `CDaoRecordset` nesneleri.

Yeni kayıt konumunu, kayıt kümesinin türüne bağlıdır:

- Dinamik tür burada yeni bir kayıt eklenir kayıt garanti edilmez. Bu davranış nedeniyle, performans ve eşzamanlılık Microsoft Jet 3. 0'ile değiştirildi. Amacınız, yeni eklenen kaydı geçerli kayıt yapmak için ise, son değiştirilen kaydın yer alın ve bu yer işaretine Taşı:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- Bir dizin belirtilen bir tablo türü kayıt kümesindeki kayıtları, uygun bir yerden sıralama düzeninde döndürülür. Belirtilen dizin yok, kayıt sonunda yeni kayıtlar döndürülür.

Kullandığınız önce geçerli kaydı `AddNew` geçerli olmaya devam eder. Yeni kayıt geçerli yapmak istediğiniz ve kayıt yer işaretleri, çağrı destekliyorsa [SetBookmark](#setbookmark) DAO kayıt nesnesini LastModified özelliği ayarı tarafından belirlenen yer işareti. Bunun yapılması, sayaç (otomatik artış) alanlarına eklenen bir kayıt değeri belirlemek için yararlıdır. Daha fazla bilgi için [GetLastModifiedBookmark](#getlastmodifiedbookmark).

Veritabanı işlemleri destekliyorsa, yapabileceğiniz, `AddNew` arama işlemlerinin bir parçası. İşlemler hakkında daha fazla bilgi için bkz. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Çağırmalısınız Not [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) çağırmadan önce `AddNew`.

Çağırmak geçersizdir `AddNew` bir kayıt kümesi için olan [açık](#open) üye işlev çağrılmadı. A `CDaoException` çağırırsanız durum `AddNew` eklenemiyor bir kayıt kümesi için. Kayıt kümesi çağırarak güncelleştirilebilir olup olmadığını belirleyebilir [CanAppend](#canappend).

Framework işaretleri alan veri üyeleri, veri kaynağında kayıt DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için değiştirildi. Genellikle bir alanın değerini değiştirme alanı kirli otomatik olarak ayarlar, nadiren çağırmanız gerekir böylece [SetFieldDirty](#setfielddirty) kendiniz, ancak bazen isteyebileceğiniz sütunları açıkça güncelleştirildi veya kaldırılacak bakılmaksızın eklenen emin emin olmak hangi alanın veri üyesi değeridir. DFX mekanizması kullanımını da kullanan **SÖZDE NULL**. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

İki kez arabelleğe alma mekanizması kullanılmadığından, ardından bir alanın değerini değiştirerek otomatik olarak alanın kirli olarak ayarlamaz. Bu durumda, açıkça alan kirli olarak ayarlamak gerekli olacaktır. Bulunan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) otomatik alan denetleniyor kontrol eder.

> [!NOTE]
> Kayıtlarını ise iki kez arabelleğe alınan (diğer bir deyişle, otomatik alan denetimi, çağırma etkin) `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir `AddNew` veya `Edit` çağrıldı.

İlgili bilgiler için "AddNew yöntemi", "CancelUpdate yöntemi", "LastModified özelliği" ve "EditMode özelliği" DAO Yardımı'ndaki konulara bakın.

##  <a name="canappend"></a>  CDaoRecordset::CanAppend

Önceden açılmış kayıt çağırarak yeni kayıtlar eklemenize izin verip vermeyeceğini belirlemek için bu üye işlevi çağrısı [AddNew](#addnew) üye işlevi.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yeni kayıtlar ekleyerek kayıt kümesini sağlayan olursa sıfır dışı; Aksi durumda 0. `CanAppend` kayıt kümesi salt okunur olarak açıldıysa 0 döndürür.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'nda "yöntemi ekleme" konusuna bakın.

##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark

Önceden açılmış kayıt, tek tek kayıtlar yer işaretlerini kullanma işaretlemek izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yer işaretleri, aksi durumda 0 destekliyorsa, sıfır dışında.

### <a name="remarks"></a>Açıklamalar

Kayıt kümeleri tamamen Microsoft Jet veritabanı altyapısı tablolarına bağlı kullanıyorsanız, yer işaretleri dışında yalnızca iletme kayan kayıt kümeleri işaretlenmiş bir anlık görüntü türü kayıt kümeleri üzerinde kullanılabilir. Diğer veritabanı ürünleri (Dış ODBC veri kaynakları), yer işaretleri desteklemeyebilir.

İlgili bilgiler için DAO Yardımı'nda "Bookmarkable özelliği" konusuna bakın.

##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate

`CancelUpdate` Üye işlevi, beklemedeki güncelleştirmeleri nedeniyle iptal bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

Örneğin, bir uygulama çağrıları `Edit` veya `AddNew` üye işlevi ve değil çağırdı [güncelleştirme](#update), `CancelUpdate` sonra yapılan değişiklikleri iptal eder `Edit` veya `AddNew` çağrıldı.

> [!NOTE]
>  Kayıtlarını ise iki kez arabelleğe alınan (diğer bir deyişle, otomatik alan denetimi, çağırma etkin) `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir `AddNew` veya `Edit` çağrıldı.

Yoksa hiçbir `Edit` veya `AddNew` işlemi beklemede, `CancelUpdate` MFC özel durum oluşturmasına neden olur. Çağrı [GetEditMode](#geteditmode) iptal edilebilir bekleyen bir işlem olup olmadığını belirlemek için üye işlevi.

İlgili bilgiler için DAO Yardımı'nda "CancelUpdate yöntemi" konusuna bakın.

##  <a name="canrestart"></a>  CDaoRecordset::CanRestart

Kayıt kümesi (kayıtlarını yenilemek için), sorgu çağırarak yeniden izin verip vermeyeceğini belirlemek için bu üye işlevi çağrısı `Requery` üye işlevi.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `Requery` kümesinin sorgusunu yeniden, aksi durumda 0'ı çalıştırmak için çağrılır.

### <a name="remarks"></a>Açıklamalar

Tablo türü kayıt kümelerini desteklemez `Requery`.

Varsa `Requery` olan çağrı desteklenmiyor, [Kapat](#close) ardından [açık](#open) verileri yenilemek için. Çağırabilirsiniz `Requery` parametre değerlerini değiştikten sonra bir kayıt kümesi nesnesi güncelleştirmek için parametre sorgu temel.

İlgili bilgiler için DAO Yardımı'nda "yeniden başlatılabilir özelliği" konusuna bakın.

##  <a name="canscroll"></a>  CDaoRecordset::CanScroll

Kayıt kaydırma izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıtlarda, aksi durumda 0 kaydırırsanız sıfır.

### <a name="remarks"></a>Açıklamalar

Eğer [açık](#open) ile `dbForwardOnly`, kayıt yalnızca ileri gezinebilirsiniz.

İlgili bilgiler için "Konumlandırma geçerli kayıt işaretçi ile DAO'da" DAO Yardım konusuna bakın.

##  <a name="cantransact"></a>  CDaoRecordset::CanTransact

Kayıt işlemleri izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan veri kaynağı işlemleri, aksi durumda 0 destekliyorsa sıfır.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'nda "işlemleri özelliği" konusuna bakın.

##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate

Kayıt kümesi güncelleştirilebilir olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirilebilir olursa sıfır dışı (ekleme, güncelleştirme ve kayıtlarını sil), aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi veri kaynağındaki salt okunur ise veya belirttiyseniz salt okunur olabilir `dbReadOnly` için *nOptions* aradığınız ne zaman [açık](#open) kayıt kümesi için.

İlgili bilgiler için "AddNew yöntemi", "Yöntemi Düzenle", "Delete yöntemi", "Güncelleştirme yöntemi" ve DAO Yardımı'nda "güncelleştirilebilir özelliği" konulara bakın.

##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset

Oluşturur bir `CDaoRecordset` nesne.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir işaretçi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne veya NULL değeri. BOŞ değilse ve `CDaoDatabase` nesnenin `Open` veri kaynağına bağlanmak için üye işlev çağrılmadı, kayıt, sizin için kendi sırasında açmaya [açın](#open) çağırın. NULL, başarılı olursa bir `CDaoDatabase` nesne oluşturulur ve size, kayıt kümesi sınıfından türetilen, belirttiğiniz veri kaynağı bilgilerini kullanarak bağlı `CDaoRecordset`.

### <a name="remarks"></a>Açıklamalar

Kullanabilir `CDaoRecordset` doğrudan veya bir uygulamaya özgü sınıfından türetilir `CDaoRecordset`. ClassWizard kayıt kümesi sınıflarını türetmek için kullanabilirsiniz.

> [!NOTE]
>  Türetirseniz bir `CDaoRecordset` sınıfı, türetilmiş sınıf kendi Oluşturucu sağlaması gerekir. Türetilmiş sınıfınızın oluşturucuda oluşturucusunu `CDaoRecordset::CDaoRecordset`, kendisine boyunca uygun parametreleri geçirme.

NULL geçirmek için kayıt kümesi oluşturucusuna bir `CDaoDatabase` nesne oluşturulur ve sizin için otomatik olarak bağlı. Bu, oluşturmak ve bağlantı gerektirmez için yararlı bir kısayol bir `CDaoDatabase` kümenizin oluşturmak önce nesne. Varsa `CDaoDatabase` nesne açık değil bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesne de oluşturulacaktır sizin için varsayılan çalışma alanı kullanır. Daha fazla bilgi için [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

##  <a name="close"></a>  CDaoRecordset::Close

Kapatma bir `CDaoRecordset` nesne koleksiyondan ilişkili veritabanında açık kümelerinin onu kaldırır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Çünkü `Close` yok `CDaoRecordset` nesnesi yeniden nesne çağırarak `Open` aynı veri kaynağına veya farklı bir veri kaynağı.

Tüm bekleyen [AddNew](#addnew) veya [Düzenle](#edit) deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Eklemeler veya düzenlemeleri korumak istiyorsanız, çağrı [güncelleştirme](#update) çağırmadan önce `Close` her kayıt için.

Çağırabilirsiniz `Open` arama sonra yeniden `Close`. Bu, kayıt kümesi nesnesi yeniden kullanmanıza olanak sağlar. Daha iyi bir alternatif çağırmaktır [Requery](#requery), mümkünse.

İlgili bilgiler için "Kapat yöntemi" DAO Yardım konusuna bakın.

##  <a name="delete"></a>  CDaoRecordset::Delete

Açık bir dinamik türü veya tablo türündeki kayıt kümesi nesnesi geçerli kayıt silmek için bu üye işlevini çağırın.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı silindikten sonra kayıt kümesinin alan veri üyeleri bir Null değere ayarlanır ve bir kayıt kümesi Gezinti üye işlevleri, açıkça çağırmalıdır ( [taşıma](#move), [arama](#seek), [ SetBookmark](#setbookmark), vb.) silinen kayıt taşımak için. Bir kayıt kümesinden kayıtlarını sildiğinizde, olmalıdır geçerli bir kayıt kümenize çağırmadan önce `Delete`; Aksi takdirde, MFC, bir özel durum oluşturur.

`Delete` Geçerli kayıt kaldırır ve erişilemez hale getirir. Düzenleme veya silinen kaydı kullanın, ancak geçerli kalır. Başka bir kayıtla taşıdığınızda, ancak, silinen kaydı yeniden geçerli yapamazsınız.

> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir olmalıdır ve olmalıdır geçerli bir kayıt kümenize geçerli çağırdığınızda `Delete`. Örneğin, bir kaydı silmek, ancak çağırmadan önce yeni bir kayıt için kaydırma değil `Delete` yeniden `Delete` oluşturur bir [CDaoException](../../mfc/reference/cdaoexception-class.md).

Kayıt işlemleri kullanırsanız ve çağırmanızı geri alınabilir [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevi. Temel tablo birincil tablonun ilişki içinde bir cascade delete, geçerli kayıt silme yabancı bir tablodaki bir veya daha fazla kayıt de silebilirsiniz. Daha fazla bilgi için "delete tanımı cascade" DAO Yardımı'ndaki bakın.

Farklı `AddNew` ve `Edit`, çağrı `Delete` bir çağrı tarafından izlenmiyor `Update`.

İlgili bilgiler için "AddNew yöntemi", "Yöntemi Düzenle", "Delete yöntemi", "Güncelleştirme yöntemi" ve DAO Yardımı'nda "güncelleştirilebilir özelliği" konulara bakın.

##  <a name="dofieldexchange"></a>  CDaoRecordset::DoFieldExchange

Framework otomatik olarak, kayıt kümesi nesnesi alan veri üyeleri geçerli kaydın veri kaynağında karşılık gelen sütunlara arasında veri değişimi için bu üye işlevini çağırır.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*pFX*<br/>
Bir işaretçi içeren bir `CDaoFieldExchange` nesne. Çerçeve zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.

### <a name="remarks"></a>Açıklamalar

Ayrıca, parametre veri üyeleri varsa kayıt kümesinin seçimi için SQL deyim dizesi parametre yer tutucularını bağlar. Her iki yönde DAO kayıt alanı değişimi (DFX) adlı alan veri alışverişi çalışır: kayıt nesnenin alan veri üyeleri alanlara veri kaynağında kayıt ve kayıt kümesi nesnesi için veri kaynağında kayıt. Sütunları dinamik olarak bağlıyorsanız, uygulama gerekmez `DoFieldExchange`.

Normal olarak yapmanız gereken uygulamak için tek eylem `DoFieldExchange` türetilmiş kümeniz için sınıf ClassWizard ile oluşturup alan veri üyeleri adları ve veri türlerini belirtmek için sınıftır. Ayrıca, hangi ClassWizard parametre veri üyeleri belirtmek yazar için kod ekleyebilirsiniz. Tüm alanları, dinamik olarak bağlı ise, parametre veri üyelerini belirtmediğiniz sürece bu işlevi devre dışı bırakılır.

ClassWizard ile türetilmiş kayıt kümesi sınıfı bildirdiğinizde, sihirbaz geçersiz kılma Yazar `DoFieldExchange` sizin için hangi benzer aşağıdaki örnekte:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>  CDaoRecordset::Edit

Değişiklikleri geçerli kayda izin vermek için bu üye işlevini çağırın.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

Bir kez çağırmanız `Edit` üye işlevi, geçerli kaydın alanları yapılan değişiklikleri kopyalama arabelleğine kopyalar. Kayda istediğiniz değişiklikleri yaptıktan sonra çağrı `Update` yaptığınız değişiklikleri kaydedin. `Edit` kayıt kümesi veri üyelerinin değerlerini kaydeder. Çağırırsanız `Edit`, ardından çağırın değişiklik `Edit` ne ilk önce oldukları için kaydın değerleri yeniden geri `Edit` çağırın.

> [!CAUTION]
>  Bir kaydı düzenlemek ve ardından başka bir kayıt ilk çağırmadan taşır herhangi bir işlem gerçekleştirmek `Update`, uyarı vermeden değişiklikleriniz kaybolur. Ayrıca, kayıt kümesi veya üst veritabanı kapatırsanız düzenlenen kaydınızı uyarı vermeden göz ardı edilir.

Bazı durumlarda, bir sütun Null (hiçbir veri içeren) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için çağrı `SetFieldNull` parametresi Null; alanı işareti true ile bu da güncelleştirilmesi sütun neden olur. Bir alanın değerini değişmemiş olsa da veri kaynağına yazılması, çağrı istiyorsanız `SetFieldDirty` parametresi true. ' % S'değeri boş alan olsa bile bu çalışır.

Framework işaretleri alan veri üyeleri, veri kaynağında kayıt DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için değiştirildi. Genellikle bir alanın değerini değiştirme alanı kirli otomatik olarak ayarlar, nadiren çağırmanız gerekir böylece [SetFieldDirty](#setfielddirty) kendiniz, ancak bazen isteyebileceğiniz sütunları açıkça güncelleştirildi veya kaldırılacak bakılmaksızın eklenen emin emin olmak hangi alanın veri üyesi değeridir. DFX mekanizması kullanımını da kullanan **SÖZDE NULL**. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

İki kez arabelleğe alma mekanizması kullanılmadığından, ardından bir alanın değerini değiştirerek otomatik olarak alanın kirli olarak ayarlamaz. Bu durumda, açıkça alan kirli olarak ayarlamak gerekli olacaktır. Bulunan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) otomatik alan denetleniyor kontrol eder.

Kayıt kümesi nesnesi çok kullanıcılı bir ortamda zor kilitliyken kayıt kilitli kalır `Edit` güncelleştirme tamamlanana kadar kullanılır. Kayıt kümesi iyimser kilitliyse kayıt kilitli ve veritabanında güncelleştirilmeden önce düzenlenmeden kayıtla karşılaştırılır. Aradığınız kaydı değişmişse `Edit`, `Update` işleminin başarısız olması ve MFC bir özel durum oluşturur. Kilitleme moduyla değiştirebilirsiniz `SetLockingMode`.

> [!NOTE]
>  İyimser kilitleme ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimleri hakkında her zaman kullanılır.

Geçerli kayıt çağırdıktan sonra geçerli kaldığı `Edit`. Çağrılacak `Edit`, geçerli bir kayıt olmalıdır. Geçerli bir kayıt varsa veya kayıt kümesi için bir tablo türü veya dinamik türünde bir kayıt kümesi nesnesi belirtmiyorsa, bir özel durum oluşur. Çağırma `Edit` neden olan bir `CDaoException` aşağıdaki koşullarda oluşturulması için:

- Geçerli kayıt yok.

- Veritabanı ya da kayıt salt okunur.

- Kayıttaki alan yok güncelleştirilebilir.

- Veritabanı ya da kayıt başka bir kullanıcı tarafından özel kullanım için açıldı.

- Başka bir kullanıcı, kayıt içeren sayfa kilitledi.

Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz `Edit` arama işlemlerinin bir parçası. Çağırmalısınız Not `CDaoWorkspace::BeginTrans` çağırmadan önce `Edit` ve kayıt açıldıktan sonra. Ayrıca, arama unutmayın `CDaoWorkspace::CommitTrans` çağırmak yerine değil `Update` tamamlanması `Edit` işlemi. İşlemler hakkında daha fazla bilgi için bkz. `CDaoWorkspace`.

İlgili bilgiler için "AddNew yöntemi", "Yöntemi Düzenle", "Delete yöntemi", "Güncelleştirme yöntemi" ve DAO Yardımı'nda "güncelleştirilebilir özelliği" konulara bakın.

##  <a name="fillcache"></a>  CDaoRecordset::FillCache

Belirli bir kayıt kümesindeki kayıt sayısı önbelleğe almak için bu üye işlevini çağırın.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Parametreler

*pSize*<br/>
Önbellekte doldurmak için satır sayısını belirtir. Bu parametreyi unutursanız, değeri DAO nesnesini CacheSize özelliği ayarı tarafından belirlenir.

*pBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) bir yer işareti belirtme. Önbellek, bu yer işaretinin tarafından belirtilen kayıt başlayarak doldurulur. Bu parametreyi unutursanız, önbellek nesnesini DAO CacheStart özelliği tarafından belirtilen kayıt başlayarak doldurulur.

### <a name="remarks"></a>Açıklamalar

Önbelleğe alma alır ya da getirir, uzak bir sunucuya verilerden bir uygulama performansını artırır. Bir önbellek, en son uygulama çalışırken verileri büyük olasılıkla yeniden istenir, varsayımına sunucudan alınan verileri tutan yerel belleğe alandır. Veri istendiğinde Microsoft Jet veritabanı altyapısı veriler için ilk daha uzun sürer sunucudan getiriliyor yerine denetler. Veriler önbellekte değil olarak olmayan ODBC veri kaynakları üzerinde önbelleğe alma verileri kullanarak etkisizdir.

Önbelleğe alınan gibi kayıtlarla doldurulacak beklemek yerine, açıkça Önbellek herhangi bir zamanda çağırarak doldurabilirsiniz `FillCache` üye işlevi. Bu önbellek çünkü doldurmak için daha hızlı bir yoludur `FillCache` teker teker yerine tek seferde birden çok kayıt getirir. Örneğin, her dolusu kaydı görüntülenir, ancak uygulama aramanız olabilir `FillCache` sonraki ekran kayıtları dolusu getirilemedi.

Kayıt kümesi nesnelere herhangi bir ODBC veritabanı yerel önbellek olabilir. Önbellek oluşturmak için bir kayıt kümesi nesnesi uzak veri kaynağını açın ve sonra çağrı `SetCacheSize` ve `SetCacheStart` kümesinin üye işlevleri. Varsa *lSize* ve *lBookmark* kısmen veya tamamen tarafından belirtilen aralık dışında bir aralığı oluşturma `SetCacheSize` ve `SetCacheStart`, kayıt bu aralığın dışında kalan kısmını göz ardı edilir ve değil önbelleğine yüklenir. Varsa `FillCache` hiçbir özel durum uzak veri kaynağında çok kayıt kalır ve yalnızca kalan kayıtları getirilen ister.

Kayıtlar önbellekten alınan eşzamanlı olarak diğer kullanıcılar tarafından kaynak verilerde yapılan değişiklikleri yansıtmaz.

`FillCache` henüz önbelleğe kayıtları getirir. Tüm önbelleğe alınan verilerin bir güncelleştirmeyi zorlamak için çağrı `SetCacheSize` üye işlevi bir *lSize* parametresi 0'a çağrı `SetCacheSize` ile yeniden *lSize* parametresi önbellek boyutuna eşit Başlangıçta istenen ve sonra çağrı `FillCache`.

İlgili bilgiler için DAO Yardımı'nda "FillCache yöntemi" konusuna bakın.

##  <a name="find"></a>  CDaoRecordset::Find

Belirli bir dize karşılaştırma işlecini kullanarak dinamik veya anlık görüntü türü kayıt kümesinde bulmak için bu üye işlevini çağırın.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lFindType*<br/>
İstenen bulma işlemi türünü belirten bir değer. Olası değerler şunlardır:

- AFX_DAO_NEXT eşleşen bir dize sonraki konumunu bulun.

- AFX_DAO_PREV eşleşen bir dize önceki konumunu bulun.

- AFX_DAO_FIRST eşleşen bir dizenin ilk konumu bulur.

- AFX_DAO_LAST eşleşen bir dize son konumunu bulun.

*lpszFilter*<br/>
Bir dize ifadesi (gibi **burada** yan tümcesinde sözcüğünü içermeyen bir SQL deyimi **burada**) kaydı bulmak için kullanılır. Örneğin:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

İlk olarak, sonraki bulabilirsiniz dize önceki ya da son örneği. `Find` bir sanal işlev olduğundan bunu geçersiz kılmasına ve kendi uygulamanızı ekleyin. `FindFirst`, `FindLast`, `FindNext`, Ve `FindPrev` üye işlevleri çağrı `Find` üye işlevi kullanabilirsiniz, böylece `Find` tüm bulma işlemleri davranışını denetlemek için.

Bir tablo türü kayıt kümesinde bir kaydı bulmak için arama [arama](#seek) üye işlevi.

> [!TIP]
>  Kayıt daha etkili sahip olduğunuz, daha küçük kümesini `Find` olacaktır. Genel olarak ve özellikle ODBC veri ile tam olarak istediğiniz kayıtları alır. yeni bir sorgu oluşturmak daha iyidir.

İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.

##  <a name="findfirst"></a>  CDaoRecordset::FindFirst

Belirtilen bir koşulu karşılayan ilk kaydı bulmak için bu üye işlevini çağırın.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Bir dize ifadesi (gibi **burada** yan tümcesinde sözcüğünü içermeyen bir SQL deyimi **burada**) kaydı bulmak için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

`FindFirst` Üye işlevi, arama kayıt kümesinin başlangıç ve kayıt sonuna aramaları başlar.

Tüm arama (yalnızca bu belirli bir koşulu karşılayan) kayıtlara taşıma işlemlerini kayıttan diğerine taşımak için birini eklemek istiyorsanız. Bir tablo türü kayıt kümesinde bir kaydı bulmak için arama `Seek` üye işlevi.

Ölçütlerle eşleşen bir kaydı bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindFirst` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan birden fazla kayıtla içeriyorsa `FindFirst` ilk oluşumunu bulur `FindNext` Sonrakini vb. bulur.

> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak değişiklikleri kaydettiğinizden emin olun `Update` başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarı vermeden değişiklikleriniz kaybolur.

`Find` Üye işlevleri, konumundan ve aşağıdaki tabloda belirtilen yönde arayın:

|İşlemleri Bul|başlayın|Arama yönü|
|---------------------|-----------|----------------------|
|`FindFirst`|Kayıt kümesi başına|Kayıt kümesi sonu|
|`FindLast`|Kayıt kümesi sonu|Kayıt kümesi başına|
|`FindNext`|Geçerli kayıt|Kayıt kümesi sonu|
|`FindPrevious`|Geçerli kayıt|Kayıt kümesi başına|

> [!NOTE]
>  Çağırdığınızda `FindLast`, bu zaten yapılmadı, Microsoft Jet veritabanı altyapısı tam olarak kümenizin arama başlamadan önce doldurur. İlk arama sonraki aramaları uzun sürebilir.

Bulma işlemi birini kullanarak değil çağırma aynı `MoveFirst` veya `MoveNext`, ancak yalnızca getiren ilk veya sonraki kaydın geçerli bir koşul belirtmeden. Bir bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.

Bulma işlemi kullanırken, aşağıdakileri göz önünde bulundurun:

- Varsa `Find` geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisini geçerli kayda geri getirin.

- Bulma işlemi bir salt iletme kaydırma anlık görüntü türü kayıt kümesi ile kullanamazsınız.

- ABD tarih biçimi (ay gün yıl) kullanmanız gerekir; Microsoft Jet Veritabanı Altyapısı'nın ABD sürümü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanı ve büyük dynaset'ler ile çalışırken, bulma işlemleri kullanarak özellikle büyük kümeleriyle çalışırken yavaş olduğunu fark edebilirsiniz. SQL sorgularını kullanarak performansı artırabilirsiniz ile özelleştirilmiş **ORDERBY** veya **burada** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizinli kayıtları nesneleri.

İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.

##  <a name="findlast"></a>  CDaoRecordset::FindLast

Belirtilen bir koşul ile eşleşen en son kaydını bulmak için bu üye işlevini çağırın.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Bir dize ifadesi (gibi **burada** yan tümcesinde sözcüğünü içermeyen bir SQL deyimi **burada**) kaydı bulmak için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

`FindLast` Üye işlevi kayıt kümesinin sonunda, arama ve arama kümesi başına doğru geriye dönük başlar.

Tüm arama (yalnızca bu belirli bir koşulu karşılayan) kayıtlara taşıma işlemlerini kayıttan diğerine taşımak için birini eklemek istiyorsanız. Bir tablo türü kayıt kümesinde bir kaydı bulmak için arama `Seek` üye işlevi.

Ölçütlerle eşleşen bir kaydı bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindLast` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan birden fazla kayıtla içeriyorsa `FindFirst` ilk oluşumunu bulur `FindNext` ilk geçtiği ve benzeri sonra sonraki tekrarı bulur.

> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak değişiklikleri kaydettiğinizden emin olması `Update` başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarı vermeden değişiklikleriniz kaybolur.

Bulma işlemi birini kullanarak değil çağırma aynı `MoveFirst` veya `MoveNext`, ancak yalnızca getiren ilk veya sonraki kaydın geçerli bir koşul belirtmeden. Bir bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.

Bulma işlemi kullanırken, aşağıdakileri göz önünde bulundurun:

- Varsa `Find` geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisini geçerli kayda geri getirin.

- Bulma işlemi bir salt iletme kaydırma anlık görüntü türü kayıt kümesi ile kullanamazsınız.

- ABD tarih biçimi (ay gün yıl) kullanmanız gerekir; Microsoft Jet Veritabanı Altyapısı'nın ABD sürümü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanı ve büyük dynaset'ler ile çalışırken, bulma işlemleri kullanarak özellikle büyük kümeleriyle çalışırken yavaş olduğunu fark edebilirsiniz. SQL sorgularını kullanarak performansı artırabilirsiniz ile özelleştirilmiş **ORDERBY** veya **burada** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizinli kayıtları nesneleri.

İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.

##  <a name="findnext"></a>  CDaoRecordset::FindNext

Belirtilen bir koşul ile eşleşen bir sonraki kaydı bulmak için bu üye işlevini çağırın.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Bir dize ifadesi (gibi **burada** yan tümcesinde sözcüğünü içermeyen bir SQL deyimi **burada**) kaydı bulmak için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

`FindNext` Üye işlevi, geçerli kayıt sırasında arama başlar ve kümesinin sonuna arar.

Tüm arama (yalnızca bu belirli bir koşulu karşılayan) kayıtlara taşıma işlemlerini kayıttan diğerine taşımak için birini eklemek istiyorsanız. Bir tablo türü kayıt kümesinde bir kaydı bulmak için arama `Seek` üye işlevi.

Ölçütlerle eşleşen bir kaydı bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindNext` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan birden fazla kayıtla içeriyorsa `FindFirst` ilk oluşumunu bulur `FindNext` Sonrakini vb. bulur.

> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak değişiklikleri kaydettiğinizden emin olması `Update` başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarı vermeden değişiklikleriniz kaybolur.

Bulma işlemi birini kullanarak değil çağırma aynı `MoveFirst` veya `MoveNext`, ancak yalnızca getiren ilk veya sonraki kaydın geçerli bir koşul belirtmeden. Bir bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.

Bulma işlemi kullanırken, aşağıdakileri göz önünde bulundurun:

- Varsa `Find` geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisini geçerli kayda geri getirin.

- Bulma işlemi bir salt iletme kaydırma anlık görüntü türü kayıt kümesi ile kullanamazsınız.

- ABD tarih biçimi (ay gün yıl) kullanmanız gerekir; Microsoft Jet Veritabanı Altyapısı'nın ABD sürümü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanı ve büyük dynaset'ler ile çalışırken, bulma işlemleri kullanarak özellikle büyük kümeleriyle çalışırken yavaş olduğunu fark edebilirsiniz. SQL sorgularını kullanarak performansı artırabilirsiniz ile özelleştirilmiş **ORDERBY** veya **burada** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizinli kayıtları nesneleri.

İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.

##  <a name="findprev"></a>  CDaoRecordset::FindPrev

Belirtilen bir koşul ile eşleşen bir önceki kaydı bulmak için bu üye işlevini çağırın.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Bir dize ifadesi (gibi **burada** yan tümcesinde sözcüğünü içermeyen bir SQL deyimi **burada**) kaydı bulmak için kullanılır.

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

`FindPrev` Üye işlevi, arama sırasında geçerli kayıt başlar ve kayıt başına doğru geriye doğru arar.

Tüm arama (yalnızca bu belirli bir koşulu karşılayan) kayıtlara taşıma işlemlerini kayıttan diğerine taşımak için birini eklemek istiyorsanız. Bir tablo türü kayıt kümesinde bir kaydı bulmak için arama `Seek` üye işlevi.

Ölçütlerle eşleşen bir kaydı bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindPrev` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan birden fazla kayıtla içeriyorsa `FindFirst` ilk oluşumunu bulur `FindNext` Sonrakini vb. bulur.

> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak değişiklikleri kaydettiğinizden emin olması `Update` başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarı vermeden değişiklikleriniz kaybolur.

Bulma işlemi birini kullanarak değil çağırma aynı `MoveFirst` veya `MoveNext`, ancak yalnızca getiren ilk veya sonraki kaydın geçerli bir koşul belirtmeden. Bir bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.

Bulma işlemi kullanırken, aşağıdakileri göz önünde bulundurun:

- Varsa `Find` geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisini geçerli kayda geri getirin.

- Bulma işlemi bir salt iletme kaydırma anlık görüntü türü kayıt kümesi ile kullanamazsınız.

- ABD tarih biçimi (ay gün yıl) kullanmanız gerekir; Microsoft Jet Veritabanı Altyapısı'nın ABD sürümü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanı ve büyük dynaset'ler ile çalışırken, bulma işlemleri kullanarak özellikle büyük kümeleriyle çalışırken yavaş olduğunu fark edebilirsiniz. SQL sorgularını kullanarak performansı artırabilirsiniz ile özelleştirilmiş **ORDERBY** veya **burada** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizinli kayıtları nesneleri.

İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.

##  <a name="getabsoluteposition"></a>  CDaoRecordset::GetAbsolutePosition

Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını döndürür.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısı bir tamsayı 0. Kayıt kümesi geçerli kaydın sıralı konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

DAO nesnesini AbsolutePosition özellik değeri, sıfır tabanlıdır; kayıt kümesindeki ilk kayıt için 0 ayarı gösterir. Doldurulmuş bir kayıt kümesinde sayısını çağırarak belirleyebilirsiniz [GetRecordCount](#getrecordcount). Çağırma `GetRecordCount` sayısını belirlemek için tüm kayıtları erişmeniz gerekir çünkü biraz zaman alabilir.

Geçerli kayıt yok, olarak kayıt kümesindeki kayıt olduğunda - 1 döndürülür Geçerli kaydı silinirse, AbsolutePosition özellik değeri tanımlı değil ve başvuru MFC bir özel durum oluşturur. Dinamik tür kayıt kümeleri için yeni kayıtlar dizinin sonuna eklenir.

> [!NOTE]
>  Bu özellik, bir yedek kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri, yine de koruma ve belirli bir konuma döndürerek için önerilen yoldur ve tüm kayıt nesne türlerini geçerli kayıt konumuna tek yoludur. Özellikle, kendisinden kayıtları silinen verilen kayıt konumunu değiştirir. Ayrıca bir kayıt kümesi içinde bireysel kayıt sırasını kullanarak bir SQL deyimi oluşturulmadıkça kesin değildir çünkü kayıt yeniden yeniden oluşturulursa, belirli bir kaydı aynı mutlak konumunu olacağını hiçbir güvencesi yoktur bir  **ORDERBY** yan tümcesi.

> [!NOTE]
>  Bu üye işlevi, yalnızca dinamik tür ve anlık görüntü türü kayıt kümeleri için geçerlidir.

İlgili bilgiler için DAO Yardımı'nda "AbsolutePosition özelliğini" konusuna bakın.

##  <a name="getbookmark"></a>  CDaoRecordset::GetBookmark

Belirli bir kayıtta yer işareti değeri elde etmek için bu üye işlevini çağırın.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıtta yer işareti temsil eden bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi nesnesi oluşturulduğunda veya açık olduğunda, bunları destekleyen, kayıtların her birinde zaten benzersiz bir yer işareti vardır. Çağrı `CanBookmark` kayıt yer işaretleri destekleyip desteklemediğini belirlemek için.

Yer işareti için geçerli kayıt yer işaretine değerini atayarak kaydedebileceğiniz bir `COleVariant` nesne. Hızlı bir şekilde başka bir kayıda taşıdıktan herhangi bir zamanda kayda döndürmek için çağrı `SetBookmark` , söz konusu değerine karşılık gelen parametre ile `COleVariant` nesne.

> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.

İlgili bilgiler için DAO Yardımı'nda "Bookmark özelliğini" konusuna bakın.

##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize

Önbelleğe alınan kayıt sayısını almak için bu üye işlevini çağırın.

```
long GetCacheSize();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dinamik türü kayıt kümesindeki kayıt sayısını belirten bir değeri.

### <a name="remarks"></a>Açıklamalar

Verileri önbelleğe almayı dynaset türündeki kayıt kümesi nesneleri aracılığıyla uzak bir sunucudan veri alır. bir uygulamanın performansını artırır. Bir önbellek bir uygulama çalışırken verileri yeniden istenecektir olay o sunucudan en son alınan verileri tutan yerel belleğe alandır. Veri istendiğinde Microsoft Jet veritabanı altyapısı istenen veriler için ilk daha uzun sürer sunucudan almak yerine denetler. Bir ODBC veri kaynağından gelmeyen veri önbellekte kaydedilmez.

Ekli bir tablo gibi herhangi bir ODBC veri kaynağı, yerel bir önbellek sağlayabilirsiniz.

İlgili bilgiler için DAO Yardımı'ndaki "CacheSize CacheStart Özellikler" bölümüne bakın.

##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart

Önbelleğe alınacak kayıt kümesindeki ilk kayıt yer işareti değeri elde etmek için bu üye işlevini çağırın.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Dönüş Değeri

A `COleVariant` önbelleğe alınacak kayıt kümesinde yer ilk kaydın belirtir.

### <a name="remarks"></a>Açıklamalar

Microsoft Jet veritabanı altyapısı, önbellekten önbellek aralığı içinde kayıt isteklerini ve sunucudan önbellek aralığın dışında kayıtları ister.

> [!NOTE]
>  Kayıtlar önbellekten eşzamanlı olarak diğer kullanıcılar tarafından kaynak verilerde yapılan değişiklikleri yansıtmaz.

İlgili bilgiler için DAO Yardımı'ndaki "CacheSize CacheStart Özellikler" bölümüne bakın.

##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex

Dizini oluşturulmuş bir tablo türü şu anda kullanımda dizini belirlemek için bu üye işlevi çağrısı `CDaoRecordset` nesne.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` dizin şu anda kullanılmakta olan bir tablo türü kayıt kümesi adını içeren. Hiçbir dizin ayarlarsanız, boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu dizin, bir tablo türü kayıt kümesindeki kayıtları sıralama temelidir ve tarafından kullanılan [arama](#seek) kayıtları bulmak için üye işlevi.

A `CDaoRecordset` nesne birden fazla dizine sahip olabilir, ancak aynı anda yalnızca bir dizini kullanabilirsiniz (rağmen bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesne üzerinde tanımlanan birden fazla dizin olabilir).

Konu "Dizin nesnesi" ve "geçerli dizinde" DAO Yardım tanımı ilgili bilgi için bkz.

##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated

Tarih ve saat temel tablonun oluşturulma biçiminin almak için bu üye işlevini çağırın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) temel tablo oluşturulduğu saat ve tarihi içeren nesne.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarlarını temel tablo oluşturulduğu bilgisayardan türetilir.

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated

Tarih ve saat şemanın en son güncelleştirildiği almak için bu üye işlevini çağırın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) temel tablo yapısı (şema) son güncelleştirme saati ve tarihi içeren nesne.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarlarını temel tablo yapısı (şema) en son güncelleştirildiği bilgisayardan türetilir.

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName

Bu kayıt kümesi için veritabanı adını belirlemek için bu üye işlevini çağırın.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` , bu kayıt türetilmiştir veritabanının adını ve yolunu içerir.

### <a name="remarks"></a>Açıklamalar

İşaretçi olmayan bir kayıt oluşturduysanız bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), bu yol varsayılan veritabanı kayıt kümesi tarafından kullanılır. Varsayılan olarak, bu işlev boş bir dize döndürür. Ne zaman ClassWizard türeyen yeni bir kayıt kümesinden `CDaoRecordset`, sizin için bu işlevi oluşturur.

Aşağıdaki örnek çift ters eğik çizgi kullanımını gösterir (\\\\) dizesi içinde olduğu gibi dize doğru yorumlanması gerekli.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL

Framework, kayıt temel varsayılan SQL durumunu almak için bu üye işlevini çağırır.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` , varsayılan SQL deyimi içerir.

### <a name="remarks"></a>Açıklamalar

Bu tablo adı veya bir SQL olabilir **seçin** deyimi.

Dolaylı olarak ClassWizard ile kayıt kümesi sınıfı bildirerek varsayılan SQL deyimini tanımlayın ve bu görevi, ClassWizard gerçekleştirir.

Boş bir SQL dize geçirirseniz [açık](#open), sonra da bu işlev, SQL ve tablo adı için kümenizin belirlemek için çağrılır.

##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode

Aşağıdaki değerlerden biri olan düzenleme, durumunu belirlemek için bu üye işlevini çağırın:

```
short GetEditMode();
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme için geçerli kayıt durumunu gösteren bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

|Değer|Açıklama|
|-----------|-----------------|
|`dbEditNone`|Hiç bir düzenleme işleminin devam ediyor.|
|`dbEditInProgress`|`Edit` çağrıldı.|
|`dbEditAdd`|`AddNew` çağrıldı.|

İlgili bilgiler için DAO Yardımı'nda "EditMode özelliği" konusuna bakın.

##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount

Kayıt kümesinde tanımlanan alan (sütun) almak için bu üye işlevini çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt alan sayısı.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'nda "Count özelliğini" konusuna bakın.

##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo

Bir kayıt alanları hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizine göre arama için kayıt kümesinin alanlar koleksiyonu önceden tanımlanmış alanı sıfır tabanlı dizini.

*FieldInfo*<br/>
Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.

*dwInfoOptions*<br/>
Seçenekleri hangi bilgilerini almak için kayıt kümesi belirtin. Kullanılabilir seçenekler burada ne bunlar döndürmek işlev neden birlikte listelenir. En iyi performans için yalnızca gereksinim duyduğunuz bilgileri düzeyini alın:

- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Adı, türü, boyut öznitelikleri

- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: sıra gerekli, konum, sıfır uzunluk harmanlama sırası, yabancı adı, kaynak alan kaynak tablosunda izin ver

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: varsayılan değer, doğrulama kuralı doğrulaması metni

*lpszName*<br/>
Alanın adı.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümünü bir alanından dizine göre aramak olanak sağlar. Başka bir sürüm bir alan adına göre aramak olanak sağlar.

Döndürülen bilgileri açıklaması için bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediğinizde de önceki tüm düzeylerde hakkında bilgi alın.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getfieldvalue"></a>  CDaoRecordset::GetFieldValue

Bir kayıt kümesi verileri almak için bu üye işlevini çağırın.

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);


virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir alanın adını içeren bir dize işaretçisi.

*varValue*<br/>
Bir başvuru bir `COleVariant` bir alanın değerini depolayan bir nesne.

*nIndex*<br/>
Alanın dizine göre arama için kayıt kümesinin alanlar koleksiyonuna bir sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

İki sürümü `GetFieldValue` , bir değer döndürür dönüş bir [COleVariant](../../mfc/reference/colevariant-class.md) bir alanın değerini içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bir alan adı veya sıra konumuna bakabilirsiniz.

> [!NOTE]
>  Çağrı alan bu üye işlevin sürümlerinden daha verimli bir `COleVariant` parametresi yerine döndüren bir sürümünü çağırma nesne başvurusu bir `COleVariant` nesne. Bu işlevin ikinci sürümleri, geriye dönük uyumluluk için tutulur.

Kullanım `GetFieldValue` ve [SetFieldValue](#setfieldvalue) alanlar, çalışma zamanı yerine statik bağlama sütunları kullanarak dinamik olarak bağlamak için [DoFieldExchange](#dofieldexchange) mekanizması.

`GetFieldValue` ve `DoFieldExchange` mekanizması, performansı artırmak için birleştirilebilir. Örneğin, `GetFieldValue` yalnızca isteğe bağlı olarak gereken bir değer almanıza ve bu çağrı arabirimindeki "Daha fazla bilgi" düğmesine atayın.

İlgili bilgiler için "Alanı nesnesi" ve DAO Yardımı'nda "Value özelliği" konularına bakın.

##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount

Tablo türü kayıt kümesinde kullanılabilir dizinler sayısını belirlemek için bu üye işlevini çağırın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo türü kümesinde dizinleri sayısı.

### <a name="remarks"></a>Açıklamalar

`GetIndexCount` kayıt kümesindeki tüm dizinleri döngü için kullanışlıdır. Bu amaçla kullanabileceğiniz `GetIndexCount` birlikte [GetIndexInfo](#getindexinfo). Dinamik tür veya anlık görüntü türü kayıt kümeleri bu üye işlevini çağırın, MFC özel durum oluşturur.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo

Çeşitli arka plandaki bir kayıt içindeki temel tablo tanımlanan dizin hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);


void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Sayısal konumuna göre arama için tablonun dizinler koleksiyonu sıfır tabanlı dizin.

*indexinfo*<br/>
Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.

*dwInfoOptions*<br/>
Seçenekler hangi bilgilerini almak için dizini belirtin. Kullanılabilir seçenekler burada ne bunlar döndürmek işlev neden birlikte listelenir. En iyi performans için yalnızca gereksinim duyduğunuz bilgileri düzeyini alın:

- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Ad alanı bilgisi alanları

- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: birincil, benzersiz, kümelenmiş, gerekli IgnoreNulls, yabancı

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: ayrı sayım

*lpszName*<br/>
Ada göre arama için dizin nesnesi adı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümünü, koleksiyondaki konumuna göre bir dizini arayın sağlar. Başka bir sürüm dizini adına göre aramak olanak sağlar.

Döndürülen bilgileri açıklaması için bkz: [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediğinizde de önceki tüm düzeylerde hakkında bilgi alın.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark

En son eklenen veya güncelleştirilen kaydının yer almak için bu üye işlevini çağırın.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

A `COleVariant` içeren en son gösteren bir yer işareti eklendiğinde veya değiştirilmiş kayıt.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi nesnesi oluşturulduğunda veya açık olduğunda, bunları destekleyen, kayıtların her birinde zaten benzersiz bir yer işareti vardır. Çağrı [GetBookmark](#getbookmark) kayıt yer işaretleri destekleyip desteklemediğini belirlemek için. Kayıt kümesi yer işaretleri, desteklemiyorsa bir `CDaoException` oluşturulur.

Bir kayıt eklemek, kayıt sonunda görünür ve geçerli kaydı değildir. Yeni kayıt geçerli hale getirmek için çağrı `GetLastModifiedBookmark` ve sonra çağrı `SetBookmark` yeni eklenen kayda dönün.

İlgili bilgiler için DAO Yardımı'nda "LastModified özelliği" konusuna bakın.

##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode

Kayıt kümesi için geçerli kilitleme türünü belirlemek için bu üye işlevini çağırın.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Dönüş Değeri

Kilitleme tür kötümser, ise sıfır olmayan kayıt İyimser kilitleme için Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme aslında düzenlemekte olduğunuz kaydı içeren veri sayfası olduğunda çağırmanızı hemen sonra kilitli [Düzenle](#edit) üye işlevi. Çağırdığınızda sayfanın açılmış [güncelleştirme](#update) veya [Kapat](#close) taşıma veya Bul işlemlerden birini ya da bir üye işlevi.

Yalnızca kaydı ile güncelleştirilirken İyimser kilitleme etkindir, kaydı içeren veri sayfası kilitlenir `Update` üye işlevi.

ODBC veri kaynakları ile çalışırken, kilitleme zaman iyimser modudur.

İlgili bilgiler için "LockEdits özelliği" ve "Kilitleme davranışı, çok kullanıcılı uygulamalarında" DAO Yardım konularına bakın.

##  <a name="getname"></a>  CDaoRecordset::GetName

Kayıt kümesi adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` kayıt kümesi adını içeren.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi adı bir harf ile başlamalı ve en fazla 40 karakter içerebilir. Sayılar içerebilir ve alt çizgi karakterleri, ancak noktalama işaretleri veya boşluk içeremez.

İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue

Temel alınan DAOParameter nesnesinde depolanan belirtilen parametresinin geçerli değerini almak için bu üye işlevini çağırın.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Temel alınan nesnede DAOParameter parametresi sayısal konumu.

*lpszName*<br/>
Değer, istediğiniz parametrenin adı.

### <a name="return-value"></a>Dönüş Değeri

Sınıfın bir nesnesi [COleVariant](../../mfc/reference/colevariant-class.md) içeren parametrenin değeri.

### <a name="remarks"></a>Açıklamalar

Parametre adı veya koleksiyon içindeki sayısal konumuna erişebilir.

İlgili bilgiler için DAO Yardımı'nda "parametresi nesne" konusuna bakın.

##  <a name="getpercentposition"></a>  CDaoRecordset::GetPercentPosition

Eğer bir dinamik tür veya anlık görüntü türü kayıt ile çalışırken `GetPercentPosition` kayıt kümesinin tam doldurma önce taşıma çağırarak belirtildiği gibi erişilen kayıt sayısıyla miktarıdır [GetRecordCount](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesinde yüzdesine göre kayıt kümesi nesnesi geçerli kayıt yaklaşık konumunu gösteren 0 ile 100 arasında bir sayı.

### <a name="remarks"></a>Açıklamalar

Çağırarak kayıt son taşıyabilirsiniz [MoveLast](#movelast) tam doldurma tüm kayıt kümelerini, ancak bu oldukça uzun sürebilir.

Çağırabilirsiniz `GetPercentPosition` dizini olmayan tablolar üzerinde tüm üç tür kayıt nesnelerin dahil. Ancak, çağıramazsınız `GetPercentPosition` yalnızca iletme kaydırma anlık görüntülerini veya harici bir veritabanına karşı doğrudan bir sorgudan açılan bir kayıt kümesi. Geçerli kayıt yok veya geçerli he kaydı silinmiş, bir `CDaoException` oluşturulur.

İlgili bilgiler için DAO Yardımı'nda "PercentPosition özelliği" konusuna bakın.

##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount

Bir kayıt kümesinde kaç tane kaydın erişildiğini bulmak için bu üye işlevini çağırın.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesi nesnesi erişilen kayıt sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

`GetRecordCount` tüm kayıtları erişilen kadar kaç tane kaydın bir dinamik tür veya anlık görüntü türü kayıt kümesi içinde bulunan göstermez. Bu üye işlev çağrısı, önemli miktarda tamamlanması zaman alabilir.

Son kayda erişildikten sonra dönüş değeri silinmemiş kayıt kümesinde toplam sayısını gösterir. Son kayda erişilecek zorlamak için çağrı `MoveLast` veya `FindLast` kayıt kümesi için üye işlevi. Bir SQL sayısı, kayıtlar sorgunuzun döndürür yaklaşık sayısını belirlemek için de kullanabilirsiniz.

Uygulamanız, dönüş değeri dynaset türü kayıt kümesindeki kayıtları siler `GetRecordCount` azaltır. Ancak, diğer kullanıcılar tarafından silinen kayıtlar tarafından yansıtılmaz `GetRecordCount` kadar geçerli kaydı silinen bir kayda konumlandırıldı. Kayıt sayısı etkileyen bir işlem yürütme ve daha sonra işlemi geri `GetRecordCount` gerçek kalan kayıt sayısı yansıtmaz.

Değerini `GetRecordCount` bir anlık görüntü türü kayıt kümesinden tablolardaki değişikliklerden etkilenmez.

Değerini `GetRecordCount` bir tablo türü kayıt yaklaşık tablosundaki kayıt sayısını yansıtır ve tablo kayıtlarını eklenen ve Silinen hemen etkilenir.

Bir kayıt kümesi ile hiçbir kayıt 0 değerini döndürür. Bağlı tablolar veya ODBC veritabanlarının ile çalışırken `GetRecordCount` her zaman döndürür - 1. Çağırma `Requery` üye işlevi bir kayıt kümesinde sıfırlar değerini `GetRecordCount` sanki yalnızca sorguyu yeniden çalıştırılır.

İlgili bilgiler için DAO Yardımı'nda "RecordCount özelliği" konusuna bakın.

##  <a name="getsql"></a>  CDaoRecordset::GetSQL

Açıldığında kayıt kümesinin kayıtları seçmek için kullanılan SQL durumunu almak için bu üye işlevini çağırın.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` SQL deyimini içeren.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle bir SQL olacaktır **seçin** deyimi.

Tarafından döndürülen dize `GetSQL` kümenize için geçirilen herhangi bir dize genellikle farklı *lpszSQL* parametresi [açık](#open) üye işlevi. Kayıt kümesi ne sizin için geçen dayalı tam bir SQL deyimi oluşturur olmasıdır `Open`ClassWizard ile belirtilen ve hangi belirttiğiniz [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) veri üyeleri.

> [!NOTE]
>  Bu üye işlevi çağırdıktan sonra yalnızca çağrı `Open`.

İlgili bilgiler için DAO Yardımı'nda "SQL özelliğini" konusuna bakın.

##  <a name="gettype"></a>  CDaoRecordset::GetType

Kayıt kümesi nesnesi türünü belirlemek için kayıt açtıktan sonra bu üye işlevini çağırın.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt türünü gösteren aşağıdaki değerlerden biri:

- `dbOpenTable` Tablo türünde bir kayıt kümesi

- `dbOpenDynaset` Dinamik türünde bir kayıt kümesi

- `dbOpenSnapshot` Anlık görüntü türü kayıt kümesi

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'nda "Type özelliği" konusuna bakın.

##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule

Verileri doğrulamak için kullanılan kural belirlemek için bu üye işlevini çağırın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` değiştirildi veya tabloya eklenen bir kayıttaki veriler doğrulayan bir değer içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu kural, metin tabanlı ve temel alınan tabloda her değiştirildiğinde uygulanır. Verilerin yasal değil ise, MFC özel durum oluşturur. Döndürülen hata iletisi, belirtilmişse nesnenin temel alan ValidationText özelliğinin metin veya metin alanı nesnesini ValidationRule özelliği tarafından belirtilen ifadenin ' dir. Çağırabilirsiniz [GetValidationText](#getvalidationtext) hata iletisinin metni elde edilir.

Örneğin, ayın gününü gerektiren kaydındaki alan bir doğrulama kuralı gibi olabilir "günlük BETWEEN 1 ve 31."

İlgili bilgiler için DAO Yardımı'nda "ValidationRule özelliğini" konusuna bakın.

##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText

Temel alan nesnenin ValidationText özelliğinin metni almak için bu üye işlevini çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` bir alanın değerini temel alan nesnenin doğrulama kuralı karşılamaz, görüntülenen iletinin metni içeren nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardımı'nda "ValidationText özelliği" konusuna bakın.

##  <a name="isbof"></a>  CDaoRecordset::IsBOF

Kayıttan önce ilk kaydı kümesi ilerlemiş olup olmadığını öğrenmek için kayıt kaydırarak önce bu üye işlevini çağırın.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içeriyorsa veya geriye doğru ilk kaydı önce kaydırılan sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, çağırabilirsiniz `IsBOF` ile birlikte `IsEOF` kayıt herhangi bir kayıt içerip boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra `Open`, kayıt, kayıt bulundurmuyorsa `IsBOF` sıfır döndürür. En az bir kaydına sahip bir kayıt kümesi açtığınızda, geçerli kaydın ilk kaydıdır ve `IsBOF` 0 döndürür.

Geçerli kaydı ilk kaydı ise ve çağırmanızı `MovePrev`, `IsBOF` sonradan sıfır döndürür. Varsa `IsBOF` sıfır döndürür ve çağrı `MovePrev`, bir özel durum oluşturulur. Varsa `IsBOF` sıfır döndürür, geçerli kayıt tanımsız olur ve geçerli bir kayıt gerektiren herhangi bir işlem, bir özel durumu oluşur.

Üzerinde belirli yöntemler etkisi `IsBOF` ve `IsEOF` ayarları:

- Çağırma `Open*` dahili olarak ilk kaydı kayıt kümesindeki geçerli kayıt çağırarak yapar `MoveFirst`. Bu nedenle, çağırma `Open` kayıtları neden bir boş dizi `IsBOF` ve `IsEOF` sıfır döndürülecek. (Başarısız davranışı için aşağıdaki tabloya bakın `MoveFirst` veya `MoveLast` arayın.)

- Her ikisi de başarıyla bir kaydı bulmak tüm taşıma işlemlerini neden `IsBOF` ve `IsEOF` 0 dönün.

- Bir `AddNew` çağrısı ve ardından bir `Update` başarıyla yeni bir kayıt ekler çağrı neden olacak `IsBOF` 0, ancak yalnızca döndürülecek `IsEOF` zaten sıfır değil. Durumunu `IsEOF` her zaman değişmeden kalır. Geçerli kayıt sonra yeni bir kayıt eklenir, böylece Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi geçerli kayıt boş bir kümesinin bir dosya sonunda işaretçisidir.

- Tüm `Delete` çağrısı, bir kayıt kümesinden tek kalan kayıt kaldırır bile değişmeyecek değerini `IsBOF` veya `IsEOF`.

Bu tabloda, farklı birleşimlerini ile hangi taşıma işlemlerine izin gösterilmektedir `IsBOF` /  `IsEOF`.

||MoveFirst MoveLast|MovePrev,<br /><br /> < 0 Taşı|0 Taşı|MoveNext,<br /><br /> > 0 Taşı|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`sıfır olmayan =<br /><br /> `IsEOF`=0|İzin verilen|Özel Durum|Özel Durum|İzin verilen|
|`IsBOF`=0,<br /><br /> `IsEOF`sıfır olmayan =|İzin verilen|İzin verilen|Özel Durum|Özel Durum|
|Her ikisi de sıfır olmayan|Özel Durum|Özel Durum|Özel Durum|Özel Durum|
|Her iki 0|İzin verilen|İzin verilen|İzin verilen|İzin verilen|

Bir taşıma işlemi izin verme işlemi başarıyla bir kaydı bulmak anlamına gelmez. Yalnızca belirtilen taşıma işlemi gerçekleştirme girişimi izin verilir ve bir özel durum oluşturmayacağını belirtir. Değerini `IsBOF` ve `IsEOF` üye işlevleri, denenen taşıma nedeniyle değişebilir.

Bir kayıt değeri temel bulundurmayın taşıma işlemlerini etkisini `IsBOF` ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır dışında|Sıfır dışında|
|`Move` 0|Değişiklik yok|Değişiklik yok|
|`MovePrev`, `Move` < 0|Sıfır dışında|Değişiklik yok|
|`MoveNext`, `Move` > 0|Değişiklik yok|Sıfır dışında|

İlgili bilgi için Ek Yardım konusuna "BOF, EOF özellikleri" DAO Yardımı'nda.

##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted

Geçerli kaydı silinmiş olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayda konumlandırıldı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kaydırırsanız ve `IsDeleted` doğru (sıfırdan farklı) döndürür ve herhangi bir kayıt işlemi gerçekleştirmek için önce başka bir kayıtla kaydırın.

> [!NOTE]
>  Anlık görüntü veya tablo türünde bir kayıt kümesindeki kayıtları silinen durumunu denetleyin gerek yoktur. Anlık görüntüden kayıtları silinemiyor çünkü çağırmaya gerek yoktur `IsDeleted`. Tablo türü kayıt kümeleri için silinen kayıtlar gerçekten kayıt kümesinden kaldırılır. Bir kayıt, siz başka bir kullanıcı veya başka bir kayıt kümesi silindikten sonra geri kayda gidemez. Bu nedenle, çağırmaya gerek yoktur `IsDeleted`.

Bir dinamik kayıt silme, kayıt kümesinden kaldırılır ve yeniden kayda'e gidin. Ancak, bir kayıtta dinamik küme başka bir kullanıcı tarafından veya başka bir kayıt kümesi aynı tabloya göre silinir `IsDeleted` kayda daha sonra kaydırdığınızda TRUE döndürür.

İlgili bilgiler için "Delete yöntemi", "LastModified özelliği" ve DAO Yardımı'nda "EditMode özelliği" konularına bakın.

##  <a name="iseof"></a>  CDaoRecordset::IsEOF

Kayıt kümesi en son kaydını ilerlemiş olup olmadığını öğrenmek için kayda kaydından gezinirken bu üye işlevini çağırın.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içeriyorsa veya en son kaydını kaydırırsanız sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, çağırabilirsiniz `IsEOF` kayıt herhangi bir kayıt içerip boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra `Open`, kayıt, kayıt bulundurmuyorsa `IsEOF` sıfır döndürür. En az bir kaydına sahip bir kayıt kümesi açtığınızda, geçerli kaydın ilk kaydıdır ve `IsEOF` 0 döndürür.

Son kayda çağırdığınızda geçerli kayıt olup olmadığını `MoveNext`, `IsEOF` sonradan sıfır döndürür. Varsa `IsEOF` sıfır döndürür ve çağrı `MoveNext`, bir özel durum oluşturulur. Varsa `IsEOF` sıfır döndürür, geçerli kayıt tanımsız olur ve geçerli bir kayıt gerektiren herhangi bir işlem, bir özel durumu oluşur.

Üzerinde belirli yöntemler etkisi `IsBOF` ve `IsEOF` ayarları:

- Çağırma `Open` dahili olarak ilk kaydı kayıt kümesindeki geçerli kayıt çağırarak yapar `MoveFirst`. Bu nedenle, çağırma `Open` kayıtları neden bir boş dizi `IsBOF` ve `IsEOF` sıfır döndürülecek. (Başarısız davranışı için aşağıdaki tabloya bakın `MoveFirst` arayın.)

- Her ikisi de başarıyla bir kaydı bulmak tüm taşıma işlemlerini neden `IsBOF` ve `IsEOF` 0 dönün.

- Bir `AddNew` çağrısı ve ardından bir `Update` başarıyla yeni bir kayıt ekler çağrı neden olacak `IsBOF` 0, ancak yalnızca döndürülecek `IsEOF` zaten sıfır değil. Durumunu `IsEOF` her zaman değişmeden kalır. Geçerli kayıt sonra yeni bir kayıt eklenir, böylece Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi geçerli kayıt boş bir kümesinin bir dosya sonunda işaretçisidir.

- Tüm `Delete` çağrısı, bir kayıt kümesinden tek kalan kayıt kaldırır bile değişmeyecek değerini `IsBOF` veya `IsEOF`.

Bu tabloda, farklı birleşimlerini ile hangi taşıma işlemlerine izin gösterilmektedir `IsBOF` /  `IsEOF`.

||MoveFirst MoveLast|MovePrev,<br /><br /> < 0 Taşı|0 Taşı|MoveNext,<br /><br /> > 0 Taşı|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`sıfır olmayan =<br /><br /> `IsEOF`=0|İzin verilen|Özel Durum|Özel Durum|İzin verilen|
|`IsBOF`=0,<br /><br /> `IsEOF`sıfır olmayan =|İzin verilen|İzin verilen|Özel Durum|Özel Durum|
|Her ikisi de sıfır olmayan|Özel Durum|Özel Durum|Özel Durum|Özel Durum|
|Her iki 0|İzin verilen|İzin verilen|İzin verilen|İzin verilen|

Bir taşıma işlemi izin verme işlemi başarıyla bir kaydı bulmak anlamına gelmez. Yalnızca belirtilen taşıma işlemi gerçekleştirme girişimi izin verilir ve bir özel durum oluşturmayacağını belirtir. Değerini `IsBOF` ve `IsEOF` üye işlevleri, denenen taşıma nedeniyle değişebilir.

Bir kayıt değeri temel bulundurmayın taşıma işlemlerini etkisini `IsBOF` ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır dışında|Sıfır dışında|
|`Move` 0|Değişiklik yok|Değişiklik yok|
|`MovePrev`, `Move` < 0|Sıfır dışında|Değişiklik yok|
|`MoveNext`, `Move` > 0|Değişiklik yok|Sıfır dışında|

İlgili bilgi için Ek Yardım konusuna "BOF, EOF özellikleri" DAO Yardımı'nda.

##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty

Bir dinamik belirtilen alan veri üyesi "kirli" işaretlenmiş durumda olup olmadığını belirlemek için (değiştirilmiş) Bu üye işlevini çağırın.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya herhangi bir alanı olumsuz olup olmadığını belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi kirli olarak işaretlenmiş olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yapılan bir çağrıyla geçerli kayıt güncelleştirildiğinde tüm kirli alan veri üyeleri verileri kaydı veri kaynağında aktarılır `Update` üye işlevinin `CDaoRecordset` (çağrıyı izleyen `Edit` veya `AddNew`). Bu bilgiyle başka adımlar gibi uygulayabileceğiniz unflagging sütunu için veri kaynağına yazılmayacak işaretlemek için alan veri üyesi.

`IsFieldDirty` aracılığıyla uygulanır `DoFieldExchange`.

##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull

Bir kayıt kümesi belirtilen alan veri üyesi Null olarak işaretlenmiş durumda olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya tüm alanları boş olup olmadığını belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null olarak işaretlenen olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

(Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve C++'ta NULL ile aynı değildir.) Alan veri üyesi Null olarak işaretlenmişse, kendisi için bir değer yoktur geçerli kaydın bir sütun olarak yorumlanır.

> [!NOTE]
>  Bazı durumlarda, kullanarak `IsFieldNull` aşağıdaki kod örneğinde gösterildiği gibi verimsiz olabilir:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  Öğesinden türetme olmadan dinamik kayıt bağlama kullanıyorsanız `CDaoRecordset`, örnekte gösterildiği gibi VT_NULL kullandığınızdan emin olun.

##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable

Belirtilen alan veri üyesi "NULL" olup olmadığını belirlemek için (bir Null değer; olabilir, bu üye işlevini çağırın C++ NULL değil diğer bir deyişle, Veritabanı terminolojisinde, Null, aynı "değeri olan").

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Durumu denetlemek veya tüm alanları boş olup olmadığını belirlemek için boş istediğiniz alanın veri üyesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null yapılabilir olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir alan boş olamaz, bir değere sahip olmalıdır. Böyle bir alan ekleme veya bir kayıt güncelleştirirken Null olarak ayarlamak çalışırsanız, veri kaynağı ekleme veya güncelleştirme, reddeder ve `Update` bir özel durum oluşturur. Çağırdığınızda özel durum oluşur `Update`, arama yaparken `SetFieldNull`.

##  <a name="isopen"></a>  CDaoRecordset::IsOpen

Kayıt kümesi açık olup olmadığını belirlemek için bu üye işlevini çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ancak kayıt kümesi nesnesinin `Open` veya `Requery` üye işlev önceden çağrıldıktan ve kayıt kapalı değil; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset::m_bCheckCacheForDirtyFields

Önbelleğe alınan alanları otomatik olarak kirli olarak (değiştirilmiş) işaretlenmiş olup olmadığını belirten bir bayrak içerir ve Null.

### <a name="remarks"></a>Açıklamalar

Bayrak varsayılan olarak true'dur. Bu veri üyesi ayarı tüm iki kez arabelleğe alma mekanizması denetler. Bayrağı TRUE olarak ayarlarsanız, DFX mekanizması kullanılarak bir alanlar tarafından temelinde önbelleğe almayı devre dışı kapatabilirsiniz. Bayrağı FALSE olarak ayarlarsanız, çağırmalıdır `SetFieldDirty` ve `SetFieldNull` kendiniz.

Çağırmadan önce bu veri kümesi `Open`. Öncelikle kolay kullanım için mekanizmadır. Performans değişiklikler yapıldıkça iki kez arabelleğe alma nedeniyle alanlarının yavaşlayabilir.

##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields

Alan veri üyeleri kayıt kümesi sınıfında sayısı ve kayıt veri kaynağından seçili sütun sayısını içerir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfı için oluşturucu başlatmalıdır `m_nFields` statik olarak bağlı alanlarının doğru sayısı ile. Kayıt kümesi sınıfı bildirmek için kullandığınızda, bu başlatma ClassWizard yazar. Ayrıca, el ile yazabilirsiniz.

Framework, alan veri üyeleri geçerli kaydın veri kaynağında karşılık gelen sütunlara arasındaki etkileşimi yönetmek için bu sayıyı kullanır.

> [!NOTE]
>  Bu sayı kayıtlı çıkış sütunu sayısı karşılık gelmelidir `DoFieldExchange` çağrısı yapıldıktan sonra `SetFieldType` parametresiyle `CDaoFieldExchange::outputColumn`.

Sütunları dinamik olarak tarafından yolu bağlayabilirsiniz `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue`. Bunu yaparsanız, sayısı artırılamıyor gerekmez `m_nFields` DFX işlevi sayısını çağrıları yansıtacak şekilde, `DoFieldExchange` üye işlevi.

##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams

Kayıt kümesi sınıfı parametre veri üyeleri sayısını içerir — parametrelerin sayısı geçirilen kümesinin sorgu.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızın herhangi bir parametre veri üyesi varsa, sınıfın oluşturucusunda başlatmanız gerekir *m_nParams* doğru numarasına sahip. Değerini *m_nParams* varsayılan ayar: 0. Parametre veri üyeleri eklerseniz — hangi el ile yapmanız gerekir — parametre sayısını yansıtacak şekilde sınıfı oluşturucusunda bir başlatma el ile eklemelisiniz (en az sayıda kadar büyük olması gereken '' içindeki yer tutucuları, *m_strFilter*  veya *m_strSort* dize).

Framework kümesinin sorgu parametreleştiren bu sayıyı kullanır.

> [!NOTE]
>  Bu sayı "kaydedilmiş params" sayısına karşılık gelmelidir `DoFieldExchange` çağrısı yapıldıktan sonra `SetFieldType` parametresiyle `CFieldExchange::param`.

İlgili bilgiler için DAO Yardımı'nda "parametresi nesne" konusuna bakın.

##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset

DAO kayıt kümesi nesnesi temel OLE arabirimi için bir işaretçi içeren `CDaoRecordset` nesne.

### <a name="remarks"></a>Açıklamalar

DAO arabirimi doğrudan erişim gerekiyorsa, bu işaretçi kullanın.

İlgili bilgiler için DAO Yardımı'nda "kayıt kümesi nesnesi" konusuna bakın.

##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase

Bir işaretçi içeren `CDaoDatabase` üzerinden kayıt bir veri kaynağına bağlıysa nesne.

### <a name="remarks"></a>Açıklamalar

Bu değişken, iki şekilde ayarlanır. Genellikle, bir işaretçi bir zaten açık geçirdiğiniz `CDaoDatabase` kayıt kümesi nesnesi oluştururken nesne. Bunun yerine, NULL geçirirseniz `CDaoRecordset` oluşturur bir `CDaoDatabase` nesnesi ve onu açar. Her iki durumda da `CDaoRecordset` işaretçiyi bu değişkeninde depolar.

Normalde, doğrudan depolanmış işaretçiyi kullanın gerekmez `m_pDatabase`. Kendi uzantılarınızı yazarsanız `CDaoRecordset`, ancak işaretçi kullanmanız gerekebilir. Durum, örneğin, işaretçiyi kendi ihtiyacınız olabilecek `CDaoException`(s).

İlgili bilgiler için DAO Yardımı'nda "veritabanı nesnesi" konusuna bakın.

##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter

Oluşturmak için kullanılan bir dize içeren **nerede** SQL deyiminin yan tümcesi.

### <a name="remarks"></a>Açıklamalar

Ayrılmış bir sözcük içermez **burada** kayıt kümesini filtrelemek için. Bu veri üyesi kullanımını tablo türü kayıt kümeleri için geçerli değildir. Kullanımını `m_strFilter` kullanarak bir kayıt kümesi açılırken etkisizdir bir `CDaoQueryDef` işaretçi.

(Ay gün yıl) ABD tarih biçimini kullanın; Microsoft Jet Veritabanı Altyapısı'nın ABD sürümü kullanmıyorsanız bile tarihleri içeren alanlar filtre beklediğiniz gibi Aksi halde veriler filtrelenebilir değil.

İlgili bilgiler için DAO Yardımı'nda "filtre özelliği" konusuna bakın.

##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort

İçeren bir dize içeren **ORDERBY** ayrılmış sözcükler olmadan SQL deyiminin yan tümcesinde **ORDERBY**.

### <a name="remarks"></a>Açıklamalar

Dinamik ve anlık görüntü türü kayıt nesneler üzerinde sıralayabilirsiniz.

Tablo türündeki kayıt kümesi nesneler sıralanamaz. Bir tablo türü kümesinin sıralama düzeni belirlemek için çağrı [SetCurrentIndex](#setcurrentindex).

Kullanımını *m_strSort* kullanarak bir kayıt kümesi açılırken etkisizdir bir `CDaoQueryDef` işaretçi.

İlgili bilgiler için DAO Yardımı'nda "sıralama özelliği" konusuna bakın.

##  <a name="move"></a>  CDaoRecordset::Move

Kayıt kümesi yerleştirmek için bu üye işlevi çağrısı *lRows* geçerli kayıt kayıtları.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Parametreler

*lRows*<br/>
İleriye veya geriye doğru gitme kayıt sayısı. Pozitif değerlere, kayıt kümesinin sonuna doğru ileriye taşıyın. Negatif değerler başına doğru geriye doğru taşıyın.

### <a name="remarks"></a>Açıklamalar

İleriye veya geriye doğru bir şekilde taşıyabilirsiniz. `Move( 1 )` eşdeğerdir `MoveNext`, ve `Move( -1 )` eşdeğerdir `MovePrev`.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de arama `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işleminden önce. Çağırdıktan sonra `Open` veya `Requery`, çağırın ya da `IsBOF` veya `IsEOF`.

> [!NOTE]
>  Başta veya sonda kümesinin kaydırılan varsa ( `IsBOF` veya `IsEOF` sıfır döndürür), bir çağrı `Move` oluşturur bir `CDaoException`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Çağırdığınızda `Move` yalnızca iletme kaydırma anlık üzerinde *lRows* parametresi pozitif bir tamsayı olmalıdır ve yer işaretleri izin verilmez, böylece ileriye yalnızca taşıyabilirsiniz.

İlk, son yapmak için sonraki veya önceki bir kayıt kümesindeki geçerli kayıt, çağrı kayıt `MoveFirst`, `MoveLast`, `MoveNext`, veya `MovePrev` üye işlevi.

İlgili bilgiler için "Taşıma yöntemi" konularına bakın ve "MoveFirst, MoveLast MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.

##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst

İlk kayıt kümenize (varsa) yapmak için bu üye işlev çağrısı geçerli kayıt.

```
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Çağrı gerekmez `MoveFirst` kayıt açıldıktan hemen sonra. O anda (varsa) ilk kaydı otomatik olarak geçerli kaydı olur.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de arama `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işleminden önce. Çağırdıktan sonra `Open` veya `Requery`, çağırın ya da `IsBOF` veya `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kullanım `Move` bir koşul uygulamadan kayıttan diğerine taşımak için işlevleri. Bir dinamik tür ya da belirli bir koşulu karşılayan anlık görüntü türü kayıt kümesi nesnesi kayıtları bulmak için bulma işlemi kullanın. Bir tablo türü kayıt kümesi nesnesi bir kaydı bulmak için arama `Seek`.

Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. Geçerli dizin, dizin özelliğini DAO nesnesini kullanarak ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız, döndürülen kayıtları sıralamasını tanımsızdır.

Eğer `MoveLast` bir SQL sorgusu veya querydef göre bir kayıt kümesi nesnesi üzerinde sorgu tamamlanana kadar zorlanır ve kayıt kümesi nesnesi tam olarak doldurulur.

Çağıramazsınız `MoveFirst` veya `MovePrev` yalnızca iletme kayan bir anlık görüntüyle üye işlevi.

Geçerli konumu bir kayıt kümesi nesnesi sayısı kayıtlarını İleri veya geri belirli bir kayıt taşımak için çağrı `Move`.

İlgili bilgiler için "Taşıma yöntemi" konularına bakın ve "MoveFirst, MoveLast MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.

##  <a name="movelast"></a>  CDaoRecordset::MoveLast

Geçerli kayıt kümenize (varsa) en son kaydını yapmak için bu üye işlevini çağırın.

```
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de arama `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işleminden önce. Çağırdıktan sonra `Open` veya `Requery`, çağırın ya da `IsBOF` veya `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kullanım `Move` bir koşul uygulamadan kayıttan diğerine taşımak için işlevleri. Bir dinamik tür ya da belirli bir koşulu karşılayan anlık görüntü türü kayıt kümesi nesnesi kayıtları bulmak için bulma işlemi kullanın. Bir tablo türü kayıt kümesi nesnesi bir kaydı bulmak için arama `Seek`.

Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. Geçerli dizin, dizin özelliğini DAO nesnesini kullanarak ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız, döndürülen kayıtları sıralamasını tanımsızdır.

Eğer `MoveLast` bir SQL sorgusu veya querydef göre bir kayıt kümesi nesnesi üzerinde sorgu tamamlanana kadar zorlanır ve kayıt kümesi nesnesi tam olarak doldurulur.

Geçerli konumu bir kayıt kümesi nesnesi sayısı kayıtlarını İleri veya geri belirli bir kayıt taşımak için çağrı `Move`.

İlgili bilgiler için "Taşıma yöntemi" konularına bakın ve "MoveFirst, MoveLast MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.

##  <a name="movenext"></a>  CDaoRecordset::MoveNext

Geçerli kayıt kümenize sonraki kayıt olmak için bu üye işlevini çağırın.

```
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Önerilen çağırmanızı `IsBOF` önceki kayda girişiminde bulunmadan önce. Bir çağrı `MovePrev` oluşturmaz bir `CDaoException` varsa `IsBOF` önce ilk kaydı zaten kaydırılan veya hiçbir kayıt kayıt tarafından seçilmedi gösteren, sıfır döndürür.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de arama `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işleminden önce. Çağırdıktan sonra `Open` veya `Requery`, çağırın ya da `IsBOF` veya `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kullanım `Move` bir koşul uygulamadan kayıttan diğerine taşımak için işlevleri. Bir dinamik tür ya da belirli bir koşulu karşılayan anlık görüntü türü kayıt kümesi nesnesi kayıtları bulmak için bulma işlemi kullanın. Bir tablo türü kayıt kümesi nesnesi bir kaydı bulmak için arama `Seek`.

Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. Geçerli dizin, dizin özelliğini DAO nesnesini kullanarak ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız, döndürülen kayıtları sıralamasını tanımsızdır.

Geçerli konumu bir kayıt kümesi nesnesi sayısı kayıtlarını İleri veya geri belirli bir kayıt taşımak için çağrı `Move`.

İlgili bilgiler için "Taşıma yöntemi" konularına bakın ve "MoveFirst, MoveLast MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.

##  <a name="moveprev"></a>  CDaoRecordset::MovePrev

Geçerli kayıt kümenize önceki kaydı yapmak için bu üye işlevini çağırın.

```
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Önerilen çağırmanızı `IsBOF` önceki kayda girişiminde bulunmadan önce. Bir çağrı `MovePrev` oluşturmaz bir `CDaoException` varsa `IsBOF` önce ilk kaydı zaten kaydırılan veya hiçbir kayıt kayıt tarafından seçilmedi gösteren, sıfır döndürür.

> [!CAUTION]
>  Herhangi bir çağırma `Move` işlevleri kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de arama `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işleminden önce. Çağırdıktan sonra `Open` veya `Requery`, çağırın ya da `IsBOF` veya `IsEOF`.

> [!NOTE]
>  Herhangi bir çağırırsanız `Move` geçerli kayıt yüklenirken işlevleri güncelleştirildi veya eklendi, güncelleştirmeleri uyarı vermeden kaybolur.

Kullanım `Move` bir koşul uygulamadan kayıttan diğerine taşımak için işlevleri. Bir dinamik tür ya da belirli bir koşulu karşılayan anlık görüntü türü kayıt kümesi nesnesi kayıtları bulmak için bulma işlemi kullanın. Bir tablo türü kayıt kümesi nesnesi bir kaydı bulmak için arama `Seek`.

Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. Geçerli dizin, dizin özelliğini DAO nesnesini kullanarak ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız, döndürülen kayıtları sıralamasını tanımsızdır.

Çağıramazsınız `MoveFirst` veya `MovePrev` yalnızca iletme kayan bir anlık görüntüyle üye işlevi.

Geçerli konumu bir kayıt kümesi nesnesi sayısı kayıtlarını İleri veya geri belirli bir kayıt taşımak için çağrı `Move`.

İlgili bilgiler için "Taşıma yöntemi" konularına bakın ve "MoveFirst, MoveLast MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.

##  <a name="open"></a>  CDaoRecordset::Open

Kayıt kümesi için kayıtları almak için bu üye işlevi çağırmanız gerekir.

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);


virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);


virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>Parametreler

*nOpenType*<br/>
Aşağıdaki değerlerden biri:

- `dbOpenDynaset` Çift yönlü kaydırma ile dinamik türü kayıt. Bu varsayılandır.

- `dbOpenTable` Çift yönlü kaydırma ile bir tablo türü kayıt.

- `dbOpenSnapshot` Çift yönlü kaydırma ile bir anlık görüntü türü kayıt.

*lpszSQL*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- Bir NULL işaretçi.

- Bir veya daha fazla tabledefs ve/veya querydefs (virgülle ayrılmış) adı.

- Bir SQL **seçin** deyimi (isteğe bağlı olarak bir SQL ile **burada** veya **ORDERBY** yan tümcesi).

- Bir doğrudan sorgudur.

*nOptions*<br/>
Bir veya birkaçını aşağıda listelenen seçenekler. Varsayılan değer 0’dır. Olası değerler aşağıdaki gibidir:

- `dbAppendOnly` Yalnızca yeni kayıtları (yalnızca dinamik tür recordset) ekleyebilirsiniz. Bu seçenek, kayıt yalnızca eklenebilir tam anlamıyla anlamına gelir. MFC ODBC veritabanı sınıfları kayıtlar alınır ve eklenen izin veren bir salt ekleme seçeneğiniz vardır.

- `dbForwardOnly` Kayıt kümesi yalnızca iletme kaydırma anlık görüntüsüdür.

- `dbSeeChanges` Düzenlemekte olduğunuz veri başka bir kullanıcı değişiyorsa, bir özel durum oluşturur.

- `dbDenyWrite` Diğer kullanıcıların değiştiremez veya kayıt ekleyin.

- `dbDenyRead` Diğer kullanıcıların kayıt (yalnızca tablo türündeki kayıt kümesi) görüntüleyemezsiniz.

- `dbReadOnly` Kayıtları yalnızca görebilirsiniz; diğer kullanıcıların bunları değiştirebilirsiniz.

- `dbInconsistent` Tutarsız güncelleştirmeleri (yalnızca dinamik tür recordset) izin verilir.

- `dbConsistent` Yalnızca tutarlı güncelleştirmeleri (yalnızca dinamik tür recordset) izin verilir.

> [!NOTE]
>  Sabitler `dbConsistent` ve `dbInconsistent` karşılıklı olarak birbirini dışlar. Kullanabilirsiniz veya diğer, ikisi de belirli bir örneğini `Open`.

*pTableDef*<br/>
Bir işaretçi bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesne. Bu sürümü yalnızca tablo türü kayıt kümeleri için geçerli değildir. Bu seçenek kullanıldığında `CDaoDatabase` işaretçi oluşturmak için kullanılan `CDaoRecordset` kullanılmaz; bunun yerine, tabledef bulunduğu veritabanı kullanılır.

*pQueryDef*<br/>
Bir işaretçi bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesne. Bu sürüm, yalnızca dinamik tür ve anlık görüntü türü kayıt kümeleri için geçerlidir. Bu seçenek kullanıldığında `CDaoDatabase` işaretçi oluşturmak için kullanılan `CDaoRecordset` kullanılmaz; bunun yerine, querydef bulunduğu veritabanı kullanılır.

### <a name="remarks"></a>Açıklamalar

Çağırmadan önce `Open`, kayıt kümesi nesnesi oluşturmalıdır. Bunu yapmanın birkaç yolu vardır:

- Kayıt kümesi nesnesi oluştururken, bir işaretçi geçirin bir `CDaoDatabase` zaten açık olan nesne.

- Kayıt kümesi nesnesi oluştururken, bir işaretçi geçirin bir `CDaoDatabase` açık değil bir nesne. Kayıt kümesi açılır bir `CDaoDatabase` nesnesi ancak kayıt kümesi nesnesi kapandığında kapanmaz.

- Kayıt kümesi nesnesi oluştururken, bir NULL işaretçi geçirin. Kayıt kümesi nesnesi çağrıları `GetDefaultDBName` Microsoft Access adını almak için. Açılacak dosyayı MDB. Kayıt kümesi sonra açılır bir `CDaoDatabase` nesne ve kayıt kümesinin açık olduğu sürece açmadan tutar. Çağırdığınızda `Close` Recordset `CDaoDatabase` nesnesi de kapalı.

    > [!NOTE]
    >  Kayıt kümesi açıldığında `CDaoDatabase` nesne özel kullanım erişimi ile veri kaynağı açar.

Sürümü için `Open` kullanan *lpszSQL* parametresi, kayıt açıldıktan sonra kayıt birkaç yoldan biriyle alabilirsiniz. DFX işlevleri zorunda ilk seçenektir, `DoFieldExchange`. İkinci seçenek çağırarak dinamik bağlama kullanmak, `GetFieldValue` üye işlevi. Bu seçenekler, ayrı ayrı veya birlikte uygulanabilir. Bunlar birleştirilir, SQL deyiminde kendiniz çağrı aktarmak gerekir `Open`.

İkinci sürümü kullandığınızda `Open` geçirmek burada bir `CDaoTableDef` nesne, sonuçta elde edilen sütun, aracılığıyla bağlamak kullanılabilir olacak `DoFieldExchange` ve DFX mekanizması ve/veya aracılığıyla dinamik olarak bağlama `GetFieldValue`.

> [!NOTE]
>  Yalnızca çağırabilirsiniz `Open` kullanarak bir `CDaoTableDef` tablo türü kayıt kümeleri için nesne.

Üçüncü sürümünü kullandığınızda `Open` geçirmek burada bir `CDaoQueryDef` nesne, sorgu yürütülür ve sonuçta elde edilen sütun, aracılığıyla bağlamak kullanılabilir olacak `DoFieldExchange` ve DFX mekanizması ve/veya aracılığıyla dinamik olarak bağlama `GetFieldValue`.

> [!NOTE]
>  Yalnızca çağırabilirsiniz `Open` kullanarak bir `CDaoQueryDef` dynaset-type ve anlık görüntü türü kayıt kümeleri için nesne.

İlk sürümü için `Open` kullanan `lpszSQL` parametresi kayıtları aşağıdaki tabloda gösterilen seçilen göre ölçütleri olan.

|Değeri `lpszSQL` parametresi|Seçilen kayıt tarafından belirlenir|Örnek|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Tarafından döndürülen dize `GetDefaultSQL`.||
|Bir veya daha fazla tabledefs ve/veya querydef adlarının virgülle ayrılmış listesi.|Tüm sütunları temsil `DoFieldExchange`.|`"Customer"`|
|**SEÇİN** sütun listesi **FROM** Tablo listesi|Belirtilen sütunları belirtilen tabledef(s) ve/veya querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

NULL olarak geçirmek için normal yordamdır `Open`; bu durumda, `Open` çağrıları `GetDefaultSQL`, oluştururken ClassWizard oluşturan bir geçersiz kılınabilir üye işlevi bir `CDaoRecordset`-türetilmiş sınıf. Bu değer, ClassWizard'içinde belirtilen tabledef(s) ve/veya querydef adları sağlar. Bunun yerine diğer bilgileri belirtebilirsiniz *lpszSQL* parametresi.

İnovasyonunuz ne olursa olsun geçirdiğiniz `Open` sorgu için son SQL dizesi oluşturur (SQL dizesi olabilir **burada** ve **ORDERBY** yan tümceleri eklenmiş için *lpszSQL* dize geçirilen) ve ardından sorguyu yürütür. Çağırarak oluşturulmuş dize inceleyebilirsiniz `GetSQL` arama sonra `Open`.

Kayıt kümesi sınıfınızın alan veri üyeleri, seçili veri sütunlarının bağlıdır. Hiçbir kayıt döndürülmezse, ilk kayıt geçerli kayıt haline gelir.

Kayıt kümesi gibi bir filtre veya sıralama seçeneklerini ayarlamak istiyorsanız `m_strSort` veya `m_strFilter` kayıt kümesi nesnesi oluşturduktan sonra ancak çağırmadan önce `Open`. Sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız recordset zaten açık olan, çağrı `Requery`.

Çağırırsanız `Open` dynaset türü veya anlık görüntü türü kayıt veya veri kaynağı bir SQL deyimi veya eklenen tablonun temsil eden değer özelliği başvuruyorsa kullanamazsınız `dbOpenTable` bunu yaparsanız, tür bağımsız değişkeni; MFC özel durum oluşturur. Tabledef nesnesi eklenen tablonun temsil edip etmediğini belirlemek için oluşturun bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesne ve çağrı kendi [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevi.

Kullanım `dbSeeChanges` düzenlerken veya aynı kayıt silme başka bir kullanıcı veya başka bir program makinenizde yapılan değişiklikleri yakalamak istiyorsanız bayrak. Örneğin, iki kullanıcı aynı çağrı yapılacak ilk kullanıcının kayıt düzenleme başlatırsanız `Update` üye işlevi başarılı olur. Zaman `Update` ikinci kullanıcı tarafından adlandırılan bir `CDaoException` oluşturulur. Benzer şekilde, ikinci kullanıcı çağırmaya çalışırsa `Delete` ve kayıt silme zaten ilk kullanıcı tarafından değiştirildi bir `CDaoException` gerçekleşir.

Genellikle, kullanıcı bu alırsa `CDaoException` güncelleştirilirken, kodunuzu alanların içeriğini yenileyin ve yeni değiştirilmiş değerlerini alma. Silme işleminde özel durum meydana gelirse, kodunuzu kullanıcı ve veri yakın zamanda değiştiğini gösteren bir ileti için yeni kayıt verilerini görüntüleyebilirsiniz. Bu noktada, kodunuzu, kullanıcı hala kaydı silmek istediğini bir onay isteyebilir.

> [!TIP]
>  Yalnızca iletme kaydırma seçeneğini kullanın (`dbForwardOnly`), uygulamanızın bir kayıt kümesi tek bir geçiş yaptığında, performansı artırmak için bir ODBC veri kaynağından açılır.

İlgili bilgiler için DAO Yardımı'nda "OpenRecordset yöntemi" konusuna bakın.

##  <a name="requery"></a>  CDaoRecordset::Requery

Bir kayıt kümesi (yenileme) yeniden oluşturmak için bu üye işlevini çağırın.

```
virtual void Requery();
```

### <a name="remarks"></a>Açıklamalar

Hiçbir kayıt döndürülmezse, ilk kayıt geçerli kayıt haline gelir.

Ekleme ve veri kaynağına, sizin veya diğer kullanıcıların kuran silme işlemleri yansıtacak şekilde kayıt kümesi için sırada çağırarak kayıt derlemelisiniz `Requery`. Kayıt kümesi bir dinamik ise, sizin veya diğer kullanıcıların, var olan kayıtların (ancak değil eklemeleri) olun güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntüyse çağırmalısınız `Requery` düzenlemeleri diğer kullanıcıların yanı sıra ekleme ve silme işlemleri tarafından yansıtmak için.

Bir dinamik veya bir anlık görüntü için çağrı `Requery` parametre değerlerini kullanarak kayıt yeniden oluşturmak için istediğiniz zaman. Yeni filtre veya sıralama ayarlayarak [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) çağırmadan önce `Requery`. Parametre veri üyeleri çağırmadan önce yeni değerler atayarak yeni parametreler Ayarla `Requery`.

Kayıt yeniden deneme başarısız olursa, kayıt kapatılır. Çağırmadan önce `Requery`, kayıt çağırarak yeniden olup olmadığını belirlemek [CanRestart](#canrestart) üye işlevi. `CanRestart` garanti etmez `Requery` başarılı olur.

> [!CAUTION]
>  Çağrı `Requery` yalnızca çağrısı yapmanız sonrasında `Open`.

> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.

Çağıramazsınız `Requery` dynaset türü veya çağırma varsa anlık görüntü türü kayıt `CanRestart` 0 döndürür ya da bir tablo türü kayıt üzerinde kullanabilirsiniz.

Her iki `IsBOF` ve `IsEOF` çağırdıktan sonra sıfır dönüş `Requery`, herhangi bir kayıt ve kayıt veri içeren sorgu döndürmedi.

İlgili bilgiler için "Requery yöntemi" DAO Yardım konusuna bakın.

##  <a name="seek"></a>  CDaoRecordset::Seek

Belirtilen ölçüt için geçerli dizin ve geçerli kayıt kayıt olun karşılayan bir dizinlenmiş tablo türü kayıt kümesi nesnesi içinde kaydı bulmak için bu üye işlevini çağırın.

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);


BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>Parametreler

*lpszComparison*<br/>
Aşağıdaki dizeyi ifadelerden biri: "<","\<=", "=", "> =", veya ">".

*pKey1*<br/>
Bir işaretçi bir [COleVariant](../../mfc/reference/colevariant-class.md) değeri dizini ilk alanına karşılık gelir. Gerekli.

*pKey2*<br/>
Bir işaretçi bir `COleVariant` değeri karşılık gelen dizin ikinci alan için varsa. Varsayılan olarak NULL.

*pKey3*<br/>
Bir işaretçi bir `COleVariant` değeri karşılık gelen alan dizinde varsa. Varsayılan olarak NULL.

*pKeyArray*<br/>
Bir dizi çeşitleri için bir işaretçi. Dizi boyutu dizini alanlarda sayısına karşılık gelir.

*nKeys*<br/>
Dizin alanlarına sayısı dizisinin boyutuna karşılık gelen bir tamsayı.

> [!NOTE]
>  Joker karakterler anahtarları belirtmeyin. Joker karakterler neden `Seek` hiçbir eşleşen kayıtları döndürmek için.

### <a name="return-value"></a>Dönüş Değeri

Sıfır, aksi durumda 0 eşleşen kayıtları bulundu.

### <a name="remarks"></a>Açıklamalar

İkinci (dizi) sürümünü kullanmanız `Seek` dört alan dizinleri ya da daha fazla işlemek için.

`Seek` yüksek performanslı dizini tablo türü kümelerinde arama sağlar. Çağırarak geçerli dizini ayarlamalısınız `SetCurrentIndex` çağırmadan önce `Seek`. Dizini benzersiz olmayan bir anahtar alan veya alanlar tanımlıyorsa `Seek` ölçütleri karşılayan ilk kaydı bulur. Dizin ayarlamazsanız, bir özel durum oluşturulur.

Bir UNICODE kayıt oluşturmadığınızı unutmayın, `COleVariant` nesneleri ANSI açıkça da bildirilmelidir. Bu kullanarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  oluşturucuyla biçiminin *vtSrc* kümesine `VT_BSTRT` (ANSI) kullanarak veya `COleVariant` işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** ile *vtSrc* kümesine `VT_BSTRT`.

Çağırdığınızda `Seek`, bir veya daha fazla anahtar değerleri ve bir karşılaştırma işleci geçirdiğiniz ("<","\<=", "=", "> =", veya ">"). `Seek` Belirtilen anahtar alanları arar ve tarafından belirtilen ölçütleri karşılayan ilk kaydı bulur *lpszComparison* ve *pKey1*. Bir kez bulundu, `Seek` sıfır döndürür ve kaydın geçerli hale getirir. Varsa `Seek` bir eşleşme bulamazsa `Seek` sıfır döndürür ve geçerli kayıt tanımsızdır. DAO doğrudan kullanırken NoMatch özelliği açıkça işaretlemeniz gerekir.

Varsa `lpszComparison` olan "=", "> =", veya ">", `Seek` dizinin başından başlar. Varsa *lpszComparison* olan "<" veya "< =", `Seek` dizini sonunda başlar ve sonunda yinelenen dizin girişlerini sürece geriye doğru arama yapar. Bu durumda, `Seek` dizini sonunda yinelenen dizin girişlerini arasında rastgele bir giriş başlar.

Orada yok kullanırken geçerli bir kayıt olarak `Seek`.

Bir kaydı bir dinamik tür ya da belirli bir koşulu karşılayan bir anlık görüntü türü kayıt kümesi bulmak için bulma işlemi kullanın. Yalnızca bu belirli bir koşulu karşılayan tüm kayıtları eklemek için kayıttan diğerine taşımak için taşıma işlemlerini kullanın.

Çağıramazsınız `Seek` herhangi bir ekli tablosunda dynaset türü veya anlık görüntü türü kayıt kümeleri olarak bağlı tablolar açılması gerekir çünkü yazın. Ancak, çağırırsanız `CDaoDatabase::Open` yüklenebilir bir ISAM veritabanı doğrudan açmak için çağırabilirsiniz `Seek` bu veritabanındaki tablolar üzerinde performans olabilir ancak yavaş.

İlgili bilgiler için DAO Yardımı'nda "yöntemi arama" konusuna bakın.

##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition

Kayıt kümesi nesnesinin geçerli kayıt göreli kayıt sayısını ayarlar.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Parametreler

*lPosition*<br/>
Kayıt kümesi geçerli kaydın sıralı konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

Çağırma `SetAbsolutePosition` dinamik tür ya da anlık görüntü türü kayıt içindeki sıralı konumuna göre belirli bir kaydı için geçerli kayıt işaretçiyi sağlar. Ayrıca, çağırarak geçerli kayıt numarasını belirleyebilirsiniz [GetAbsolutePosition](#getabsoluteposition).

> [!NOTE]
>  Bu üye işlevi, yalnızca dinamik tür ve anlık görüntü türü kayıt kümeleri için geçerlidir.

DAO nesnesini AbsolutePosition özellik değeri, sıfır tabanlıdır; kayıt kümesindeki ilk kayıt için 0 ayarı gösterir. Doldurulmuş kayıtları nedenleri MFC özel durum sayısından büyük bir değere ayarlamak. Doldurulmuş bir kayıt kümesinde sayısını çağırarak belirleyebilirsiniz `GetRecordCount` üye işlevi.

Geçerli kaydı silinirse, AbsolutePosition özellik değeri tanımlı değil ve başvuru MFC bir özel durum oluşturur. Yeni kayıtlar dizinin sonuna eklenir.

> [!NOTE]
>  Bu özellik, bir yedek kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri, yine de koruma ve belirli bir konuma döndürerek için önerilen yoldur ve tüm yer işaretlerini destekleyen kayıt nesneleri türlerinde geçerli kayıt konumuna tek yoludur. Özellikle, kendisinden kayıtları silinen verilen kayıt konumunu değiştirir. Ayrıca bir kayıt kümesi içinde bireysel kayıt sırasını kullanarak bir SQL deyimi oluşturulmadıkça kesin değildir çünkü kayıt yeniden yeniden oluşturulursa, belirli bir kaydı aynı mutlak konumunu olacağını hiçbir güvencesi yoktur bir  **ORDERBY** yan tümcesi.

İlgili bilgiler için DAO Yardımı'nda "AbsolutePosition özelliğini" konusuna bakın.

##  <a name="setbookmark"></a>  CDaoRecordset::SetBookmark

Kayıt kümesi belirtilen yer işareti içeren kayıt üzerinde yerleştirmek için bu üye işlevini çağırın.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) belirli bir kaydı için yer işareti değeri içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi nesnesi oluşturulduğunda veya açık olduğunda, kayıtların her birinde benzersiz bir yer işareti zaten sahip. Yer işareti için geçerli kayıt çağırarak alabilirsiniz `GetBookmark` değerine kaydederek bir `COleVariant` nesne. Kayda çağırarak daha sonra geri dönebilirsiniz `SetBookmark` kaydedilmiş bu yer işaretini değerini kullanarak.

> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.

Bir UNICODE kayıt oluşturmadığınızı unutmayın, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  oluşturucuyla biçiminin *vtSrc* kümesine `VT_BSTRT` (ANSI) kullanarak veya `COleVariant` işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** ile *vtSrc* kümesine `VT_BSTRT`.

İlgili bilgiler için "yer işareti" Bookmarkable özellik ve DAO Yardımı'nda bkz".

##  <a name="setcachesize"></a>  CDaoRecordset::SetCacheSize

Önbelleğe alınacak kayıt sayısını ayarlamak için bu üye işlevini çağırın.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Parametreler

*lSize*<br/>
Kayıt sayısını belirtir. Tipik bir değer 100'dür. 0 ayarı önbelleğe almayı devre dışı bırakır. Ayarı, 5 ve 1200 kayıtlar arasında olmalıdır. Önbellek, önemli miktarda bellek kullanabilir.

### <a name="remarks"></a>Açıklamalar

Bir önbellek bir uygulama çalışırken verileri yeniden istenecektir olay o sunucudan en son alınan verileri tutan yerel belleğe alandır. Verileri önbelleğe almayı dynaset türündeki kayıt kümesi nesneleri aracılığıyla uzak bir sunucudan veri alır. bir uygulamanın performansını artırır. Veri istendiğinde Microsoft Jet veritabanı altyapısı istenen veriler için ilk daha uzun sürer sunucudan almak yerine denetler. Bir ODBC veri kaynağından gelmeyen veri önbellekte kaydedilmez.

Ekli bir tablo gibi herhangi bir ODBC veri kaynağı, yerel bir önbellek sağlayabilirsiniz. Önbellek oluşturmak için bir kayıt kümesi nesnesi uzak veri kaynağı, çağrı açın `SetCacheSize` ve `SetCacheStart` üye işlevleri ve sonra çağrı `FillCache` üye işlevini veya taşıma işlemlerini birini kullanarak kayıt adımlayın. *LSize* parametresinin `SetCacheSize` üye işlev uygulamanızı çalışabilir ile tek seferde kayıt sayısı üzerinde temel alabilir. Örneğin, ekranda görüntülenecek veri kaynağı olarak bir kayıt kümesi kullanıyorsanız çağrılsaydı `SetCacheSize` *lSize* parametre olarak 20 kayıtları tek seferde görüntülemek için 20.

İlgili bilgiler için DAO Yardımı'ndaki "CacheSize CacheStart Özellikler" bölümüne bakın.

##  <a name="setcachestart"></a>  CDaoRecordset::SetCacheStart

Önbelleğe alınacak kayıt kümesinde yer ilk kaydın belirtmek için bu üye işlevini çağırın.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
A [COleVariant](../../mfc/reference/colevariant-class.md) önbelleğe alınacak kayıt kümesinde yer ilk kaydın belirtir.

### <a name="remarks"></a>Açıklamalar

Yer işareti değeri için herhangi bir kayıttan kullanabileceğiniz *varBookmark* parametresinin `SetCacheStart` üye işlevi. Geçerli kayıtla önbelleği başlatmak, kullanarak kayıt için bir yer işareti oluşturmak istediğiniz kayıt olun [SetBookmark](#setbookmark)ve parametresi için olarak yer işareti değeri geçirin `SetCacheStart` üye işlevi.

Microsoft Jet veritabanı altyapısı, önbellekten önbellek aralığı içinde kayıt isteklerini ve sunucudan önbellek aralığın dışında kayıtları ister.

Kayıtlar önbellekten eşzamanlı olarak diğer kullanıcılar tarafından kaynak verilerde yapılan değişiklikleri yansıtmaz.

Tüm önbelleğe alınan verilerin bir güncelleştirmeyi zorlamak için geçirmek *lSize* parametresinin `SetCacheSize` 0 çağrı `SetCacheSize` yeniden önbellek boyutu, başlangıçta istenen ve sonra çağrı `FillCache` üye işlevi.

Bir UNICODE kayıt oluşturmadığınızı unutmayın, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  oluşturucuyla biçiminin *vtSrc* kümesine `VT_BSTRT` (ANSI) kullanarak veya `COleVariant` işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** ile *vtSrc* kümesine `VT_BSTRT`.

İlgili bilgiler için CacheSize CacheStart özelliklerini DAO Yardımı'ndaki konusuna".

##  <a name="setcurrentindex"></a>  CDaoRecordset::SetCurrentIndex

Bir dizin üzerinde tablo türünde bir kayıt kümesi ayarlamak için bu üye işlevini çağırın.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
Ayarlanacak dizinin adını içeren bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel tablolarındaki kayıtlara herhangi belirli bir sırada depolanmaz. Dizin ayarlama veritabanından döndürülen kayıtları sırasını değiştirir, ancak kayıtları depolandığı sırayı etkilemez. Belirtilen dizinde zaten tanımlanmış olması gerekir. Var olmayan bir dizin nesnesi kullanmayı denerseniz veya çağırdığınızda dizini ayarlanmazsa [arama](#seek), MFC, bir özel durum oluşturur.

Yeni bir dizin tablosu için çağırarak oluşturabilirsiniz [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) ve yeni bir dizin çağırarak temel alınan TableDef dizinleri koleksiyona ekleme [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), ve kapatıp yeniden açmayı kayıt.

Bir tablo türü kayıt kümesinden döndürülen kayıtları yalnızca temel alınan değer özelliği tanımlanmış dizinleri göre sıralanabilir. Kayıtları başka bir düzende sıralamak için dinamik tür veya anlık görüntü türü kayıt kümesi bir SQL kullanarak açabilirsiniz **ORDERBY** yan tümcesi içinde depolanan [CDaoRecordset::m_strSort](#m_strsort).

Konu "Dizin nesnesi" ve "geçerli dizinde" DAO Yardım tanımı ilgili bilgi için bkz.

##  <a name="setfielddirty"></a>  CDaoRecordset::SetFieldDirty

Alan veri üyesi olarak değiştirilmiş veya değişmemiş olarak kümesinin bayrağı için bu üye işlevini çağırın.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Kayıt kümesi veya NULL bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL değil Null ile aynı veritabanı terminolojisinde, "herhangi bir değere sahip." anlamına gelir)

*bDirty*<br/>
"(Değiştirilmiş) kirli olarak" işaretlenmesini alan veri üyesi ise, TRUE. "(Değişmeden) temiz olarak" işaretlenmesini alan veri üyesi ise, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değişmemiş olarak işaretlenmesi, alanı güncelleştirilmez sağlar.

Framework işaretleri alan veri üyeleri, veri kaynağında kayıt DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için değiştirildi. Genellikle bir alanın değerini değiştirme alanı kirli otomatik olarak ayarlar, nadiren çağırmanız gerekir böylece `SetFieldDirty` kendiniz, ancak bazen isteyebileceğiniz sütunları açıkça güncelleştirildi veya kaldırılacak alanı verileri hangi değeri bağımsız olarak eklenen emin emin olmak üye. DFX mekanizması PSEUDONULL kullanımını da kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

İki kez arabelleğe alma mekanizması kullanılmadığından, ardından bir alanın değerini değiştirerek otomatik olarak alanın kirli olarak ayarlamaz. Bu durumda, alan açıkça kirli olarak ayarlamak gerekli olacaktır. Bulunan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) otomatik alan denetleniyor kontrol eder.

> [!NOTE]
>  Yalnızca çağrısı yapmanız sonrasında bu üye işlevi çağrısı [Düzenle](#edit) veya [AddNew](#addnew).

İşlevinin ilk bağımsız değişken işlev tümüne uygulanacak için NULL kullanarak `outputColumn` alanları değil **param** alanlarını `CDaoFieldExchange`. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

yalnızca ayarlar `outputColumn` null; alanlar **param** alanları etkilenmez.

Üzerinde çalışmak için bir **param**, tek tek gerçek adresi sağlamalısınız **param** gibi çalışmak istediğiniz:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Yani tüm ayarlayamıyor **param** ile yapabildiğiniz gibi alanları NULL olarak `outputColumn` alanları.

`SetFieldDirty` aracılığıyla uygulanır `DoFieldExchange`.

##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull

Alan veri üyesi kayıt kümesinin (özellikle hiçbir değer yok) Null veya boş olmayan olarak işaretlemek için bu üye işlevini çağırın.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*BD*<br/>
Kayıt kümesi veya NULL bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL değil Null ile aynı veritabanı terminolojisinde, "herhangi bir değere sahip." anlamına gelir)

*bNull*<br/>
Alan veri üyesi değeri (Null) sahip olarak işaretlenen ise sıfır olmayan. Null olmayan işaretlenmesine alan veri üyesi ise, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

`SetFieldNull` içinde bağlı alanlar için kullanılan `DoFieldExchange` mekanizması.

Yeni bir kayıt için bir kayıt kümesi eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlayın ve "(değiştirilmiş) kirli olarak" bayrak. Bir veri kaynağındaki bir kaydı aldığınızda, sütunlarını ya da zaten değerlere sahip veya Null. Bir alan Null yapmak uygun değilse bir [CDaoException](../../mfc/reference/cdaoexception-class.md) oluşturulur.

Örneğin, özel bir alan geçerli kaydın çağrısı bir değer olmaması olarak atamak istiyorsanız iki kez arabelleğe alma mekanizması kullanıyorsanız, `SetFieldNull` ile *bNull* boş olarak işaretlemek için TRUE olarak ayarlayın. Bir alan daha önce Null olarak işaretlendi ve artık bir değeri vermek istiyorsanız, yeni değeri ayarlamanız yeterlidir. Null bayrağıyla kaldırmak zorunda değilsiniz `SetFieldNull`. Alan Null olmasına izin verilip verilmeyeceğini belirlemek için çağrı [IsFieldNullable](#isfieldnullable).

İki kez arabelleğe alma mekanizması kullanmıyorsanız, ardından bir alanın değerini değiştirerek otomatik olarak alanın kirli ve Null olarak ayarlamaz. Özellikle, kirli ve Null olmayan alanları ayarlamanız gerekir. Bulunan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) otomatik alan denetleniyor kontrol eder.

DFX mekanizması PSEUDONULL kullanımını kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
>  Yalnızca çağrısı yapmanız sonrasında bu üye işlevi çağrısı [Düzenle](#edit) veya [AddNew](#addnew).

İşlevinin ilk bağımsız değişkeni yalnızca işlev geçerlidir NULL kullanarak `outputColumn` alanları değil **param** alanlarını `CDaoFieldExchange`. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

yalnızca ayarlar `outputColumn` null; alanlar **param** alanları etkilenmez.

##  <a name="setfieldvalue"></a>  CDaoRecordset::SetFieldValue

Sıralı konumu veya dize değerini değiştirerek bir alanın değerini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);


virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);


void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);


void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Bir alanın adını içeren bir dize işaretçisi.

*varValue*<br/>
Bir başvuru bir [COleVariant](../../mfc/reference/colevariant-class.md) alanın içeriğini değerini içeren nesne.

*nIndex*<br/>
(Sıfır tabanlı) kayıt kümesinin alanlar koleksiyonu sıralı alanın konumunu temsil eden bir tamsayı.

*lpszValue*<br/>
Alanın içeriğini değerini içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

Kullanım `SetFieldValue` ve [GetFieldValue](#getfieldvalue) alanlar, çalışma zamanı yerine statik bağlama sütunları kullanarak dinamik olarak bağlamak için [DoFieldExchange](#dofieldexchange) mekanizması.

Bir UNICODE kayıt oluşturmuyorsanız, ya da bir formu kullanmanız gerektiğini unutmayın `SetFieldValue` içermeyen bir `COleVariant` parametresi veya `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  oluşturucuyla biçiminin *vtSrc* kümesine `VT_BSTRT` (ANSI) kullanarak veya `COleVariant` işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** ile *vtSrc* kümesine `VT_BSTRT`.

İlgili bilgiler için "Alanı nesnesi" ve DAO Yardımı'nda "Value özelliği" konularına bakın.

##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull

Alanın bir Null değerine ayarlamak için bu üye işlevini çağırın.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Kayıt kümesi için sıfır tabanlı dizine göre arama alanı dizini.

*lpszName*<br/>
Ada göre arama kümesinde, alanın adı.

### <a name="remarks"></a>Açıklamalar

C++ NULL değil diğer bir deyişle, Veritabanı terminolojisinde, Null, aynı "herhangi bir değere sahip."

İlgili bilgiler için "Alanı nesnesi" ve DAO Yardımı'nda "Value özelliği" konularına bakın.

##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode

Kayıt kümesi için kilitleme türünü ayarlamak için bu üye işlevini çağırın.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Parametreler

*bPessimistic*<br/>
Kilitleme türünü gösteren bir bayrak.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme aslında düzenlemekte olduğunuz kayıt içeren 2 K sayfası olduğunda çağırmanızı hemen sonra kilitli `Edit` üye işlevi. Çağırdığınızda sayfanın açılmış `Update` veya `Close` taşıma veya Bul işlemlerden birini ya da bir üye işlevi.

Yalnızca kaydı ile güncelleştirilirken İyimser kilitleme etkindir, kayıt içeren 2 K sayfası kilitlenir `Update` üye işlevi.

Bir sayfa kilitliyse, başka bir kullanıcı aynı sayfadaki kayıtları düzenleyebilirsiniz. Eğer `SetLockingMode` ve sıfır olmayan bir değer geçirin ve başka bir kullanıcı kilitli sayfası zaten sahipse, çağırdığınızda bir özel durum `Edit`. Diğer kullanıcıların, kilitli sayfalarından verileri okuyabilir.

Eğer `SetLockingMode` sıfır değeri ile ve sonraki çağrı `Update` sayfanın başka bir kullanıcı tarafından kilitliyken, bu bir özel durum oluşur. Kaydınız için başka bir kullanıcı tarafından yapılan değişiklikleri (ve değişiklikleri kaybetmek için), çağrı `SetBookmark` üye işlevi geçerli kaydın yer işareti değeri.

ODBC veri kaynakları ile çalışırken, kilitleme zaman iyimser modudur.

##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue

Bir parametrenin değeri, çalışma zamanında kümenize ayarlamak için bu üye işlevini çağırın.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);


virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Parametre querydef ait parametre koleksiyonunda sayısal konumu.

*var*<br/>
Ayarlanacak değer; Açıklamalara bakın.

*lpszName*<br/>
Değer, ayarlamak istediğiniz parametrenin adı.

### <a name="remarks"></a>Açıklamalar

Parametre zaten SQL dizesi kümesinin bir parçası olarak kurulmuş gerekir. Parametre adını veya koleksiyon içindeki dizin konumu erişebilirsiniz.

Değeri olarak ayarlamak için belirtin bir `COleVariant` nesne. İstenen değeri ve türü ayarlama hakkında bilgi için `COleVariant` nesne, sınıfına bakın [COleVariant](../../mfc/reference/colevariant-class.md). Bir UNICODE kayıt oluşturmadığınızı unutmayın, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)**  oluşturucuyla biçiminin *vtSrc* kümesine `VT_BSTRT` (ANSI) kullanarak veya `COleVariant` işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *lpszSrc* **,** *vtSrc* **)** ile *vtSrc* kümesine `VT_BSTRT`.

##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull

Parametre için Null değeri ayarlamak için bu üye işlevini çağırın.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Kayıt kümesi için sıfır tabanlı dizine göre arama alanı dizini.

*lpszName*<br/>
Ada göre arama kümesinde, alanın adı.

### <a name="remarks"></a>Açıklamalar

C++ NULL değil diğer bir deyişle, Veritabanı terminolojisinde, Null, aynı "herhangi bir değere sahip."

##  <a name="setpercentposition"></a>  CDaoRecordset::SetPercentPosition

Bir kayıt kümesinde yüzdesine göre kayıt kümesi nesnesi geçerli kayıt yaklaşık konumunu değiştiren bir değer ayarlamak için bu üye işlevini çağırın.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Parametreler

*fPosition*<br/>
0 ile 100 arasında bir sayı.

### <a name="remarks"></a>Açıklamalar

Dinamik tür veya anlık görüntü türü kayıt kümesi ile çalışırken, ilk kayıt kümesini çağırmadan önce son kayıt taşıyarak doldurmak `SetPercentPosition`. Eğer `SetPercentPosition` kayıt kümesinin tam doldurma önce taşıma değeri gösterilen erişilen kayıt sayısıyla miktarıdır [GetRecordCount](#getrecordcount). Çağırarak kayıt son taşıyabilirsiniz `MoveLast`.

Bir kez çağırmanız `SetPercentPosition`, o değerine karşılık gelen yaklaşık bir konumda kayıt geçerli olur.

> [!NOTE]
>  Çağırma `SetPercentPosition` bir kayıt kümesindeki belirli bir kaydı için geçerli kayıt önerilmez taşımak için. Çağrı [SetBookmark](#setbookmark) üye işlevini yerine.

İlgili bilgiler için DAO Yardımı'nda "PercentPosition özelliği" konusuna bakın.

##  <a name="update"></a>  CDaoRecordset::Update

Bu üye işlevi çağrısı yapıldıktan sonra çağırma `AddNew` veya `Edit` üye işlevi.

```
virtual void Update();
```

### <a name="remarks"></a>Açıklamalar

Bu çağrı tamamlamak için gereken `AddNew` veya `Edit` işlemi.

Her ikisi de `AddNew` ve `Edit` eklendi veya düzenlenmiş verilerin yerleştirilir düzenleme arabelleği veri kaynağına kaydetmek için hazırlayın. `Update` verileri kaydeder. İşaretli veya değiştirilmiş olarak algılanan yalnızca bu alanları güncelleştirilir.

Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz `Update` çağırın (ve kendi ilişkili `AddNew` veya `Edit` çağrısı) bir işlemin bir parçası.

> [!CAUTION]
> Eğer `Update` ilk ya da çağırma `AddNew` veya `Edit`, `Update` oluşturur bir `CDaoException`. Eğer `AddNew` veya `Edit`, çağırmalısınız `Update` çağırmadan önce [MoveNext](#movenext) veya kayıt veya veri kaynağı bağlantısı'nı kapatın. Aksi takdirde, bildirim yapılmadan değişiklikleriniz kaybolur.

Kayıt kümesi nesnesi çok kullanıcılı bir ortamda zor kilitliyken kayıt kilitli kalır `Edit` güncelleştirme tamamlanana kadar kullanılır. Kayıt kümesi iyimser kilitliyse kayıt kilitli ve veritabanında güncelleştirilmeden önce düzenlenmeden kayıtla karşılaştırılır. Aradığınız kaydı değişmişse `Edit`, `Update` işleminin başarısız olması ve MFC bir özel durum oluşturur. Kilitleme moduyla değiştirebilirsiniz `SetLockingMode`.

> [!NOTE]
> İyimser kilitleme ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimleri hakkında her zaman kullanılır.

İlgili bilgiler için "AddNew yöntemi", "CancelUpdate yöntemi", "Delete yöntemi", "LastModified özelliği", "Güncelleştirme yöntemi" ve DAO Yardımı'nda "EditMode özelliği" konulara bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
