---
title: CDaoRecordset sınıfı
ms.date: 08/27/2018
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
ms.openlocfilehash: 96118645aa656e97fcb93a0fd223045208ab03a3
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78867306"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset sınıfı

Bir veri kaynağından seçilen bir kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset:: CDaoRecordset](#cdaorecordset)|`CDaoRecordset` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset:: AddNew](#addnew)|Yeni bir kayıt eklemeye hazırlar. Ekleme işleminin tamamlanabilmesi için [güncelleştirmeyi](#update) çağırın.|
|[CDaoRecordset:: CanAppend](#canappend)|[AddNew](#addnew) üye işlevi aracılığıyla kayıt kümesine yeni kayıtlar eklenebileceği sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: CanBookmark](#canbookmark)|Kayıt kümesi yer imlerini destekliyorsa sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: CancelUpdate](#cancelupdate)|Bir [düzenleme](#edit) veya [AddNew](#addnew) işlemi nedeniyle bekleyen tüm güncelleştirmeleri iptal eder.|
|[CDaoRecordset:: CanRestart](#canrestart)|Kayıt kümesinin sorgusunu yeniden çalıştırmak için [YenidenSorgula](#requery) çağrılırsa sıfır dışı döndürür.|
|[CDaoRecordset:: CanScroll](#canscroll)|Kayıtlar arasında gezinebilirsiniz, sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: CanUpdate](#canupdate)|Kayıt kümesi güncelleştiribir şekilde (kayıt ekleyebilir, güncelleştirebilir veya silebilirsiniz) sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: Close](#close)|Kayıt kümesini kapatır.|
|[CDaoRecordset::D Sil](#delete)|Kayıt kümesinden geçerli kaydı siler. Silme işleminden sonra açıkça başka bir kayda kaydırma yapmanız gerekir.|
|[CDaoRecordset::D oFieldExchange](#dofieldexchange)|Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki karşılık gelen kayıt arasındaki verileri (her iki yönde) değiş tokuş etmek için çağırılır. DAO Kayıt alanı değişimi (DFX) uygular.|
|[CDaoRecordset:: Edit](#edit)|Geçerli kayıttaki değişikliklere hazırlar. Düzenleme işleminin tamamlanabilmesi için `Update` çağırın.|
|[CDaoRecordset:: FillCache](#fillcache)|ODBC veri kaynağından veri içeren bir kayıt kümesi nesnesi için yerel önbelleğin tümünü veya bir parçasını doldurur.|
|[CDaoRecordset:: Find](#find)|Belirli bir dizenin, belirtilen ölçütlere uyan ve bu kaydı geçerli kayıt yapan bir Recordset içindeki ilk, sonraki, önceki veya son konumunu bulur.|
|[CDaoRecordset:: FindFirst](#findfirst)|Belirtilen ölçütlere uyan bir değişken tür veya anlık görüntü türü kayıt kümesindeki ilk kaydı bulur ve bu kaydı geçerli kayıt yapar.|
|[CDaoRecordset:: FindLast](#findlast)|Belirtilen ölçütlere uyan bir değişken tür veya anlık görüntü türü kayıt kümesindeki son kaydı bulur ve bu kaydı geçerli kayıt yapar.|
|[CDaoRecordset:: Sonrabul](#findnext)|Bir sonraki kaydı, belirtilen ölçütlere uyan bir değişken tür veya anlık görüntü türü kayıt kümesinde bulur ve bu kaydı geçerli kayıt yapar.|
|[CDaoRecordset:: Findöncekini](#findprev)|Bir önceki kaydı, belirtilen ölçütlere uyan bir değişken tür veya anlık görüntü türü kayıt kümesinde bulur ve bu kaydı geçerli kayıt yapar.|
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|Bir kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını döndürür.|
|[CDaoRecordset:: GetBookmark](#getbookmark)|Bir kayıttaki yer işaretini temsil eden bir değer döndürür.|
|[CDaoRecordset:: GetCacheSize](#getcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken türü Recordset içindeki kayıtların sayısını belirten bir değer döndürür.|
|[CDaoRecordset:: GetCacheStart](#getcachestart)|Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir değer döndürür.|
|[CDaoRecordset:: GetCurrentIndex](#getcurrentindex)|Dizine alınmış, tablo türü `CDaoRecordset`en son kullanılan dizin adını içeren `CString` döndürür.|
|[CDaoRecordset:: GetDateCreated](#getdatecreated)|Temel tablonun bir `CDaoRecordset` nesnesinin oluşturulduğu tarih ve saati döndürür|
|[CDaoRecordset:: GetDateLastUpdated](#getdatelastupdated)|`CDaoRecordset` nesnesi temel aldığı temel tablonun tasarımında yapılan en son değişikliğin tarih ve saatini döndürür.|
|[CDaoRecordset:: GetDefaultDBName](#getdefaultdbname)|Varsayılan veri kaynağının adını döndürür.|
|[CDaoRecordset:: GetDefaultSQL](#getdefaultsql)|Yürütülecek varsayılan SQL dizesini almak için çağırılır.|
|[CDaoRecordset:: GetEditMode](#geteditmode)|Geçerli kayıt için düzenlemenin durumunu gösteren bir değer döndürür.|
|[CDaoRecordset:: GetFieldCount](#getfieldcount)|Bir kayıt kümesindeki alan sayısını temsil eden bir değer döndürür.|
|[CDaoRecordset:: GetFieldInfo](#getfieldinfo)|Kayıt kümesindeki alanlarla ilgili belirli tür bilgileri döndürür.|
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|Bir kayıt kümesindeki bir alanın değerini döndürür.|
|[CDaoRecordset:: GetIndexCount](#getindexcount)|Bir kayıt kümesini temel alan bir tablodaki dizinlerin sayısını alır.|
|[CDaoRecordset:: GetIndexInfo](#getindexinfo)|Bir dizinle ilgili çeşitli bilgi türlerini döndürür.|
|[CDaoRecordset:: GetLastModifiedBookmark](#getlastmodifiedbookmark)|En son eklenen veya güncelleştirilmiş kaydı belirlemede kullanılır.|
|[CDaoRecordset:: GetLockingMode](#getlockingmode)|Düzen sırasında geçerli olan kilitleme türünü gösteren bir değer döndürür.|
|[CDaoRecordset:: GetName](#getname)|Kayıt kümesinin adını içeren `CString` döndürür.|
|[CDaoRecordset:: GetParamValue](#getparamvalue)|Temel alınan Baoparameter nesnesinde depolanan belirtilen parametrenin geçerli değerini alır.|
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|Geçerli kaydın konumunu toplam kayıt sayısının yüzdesi olarak döndürür.|
|[CDaoRecordset:: GetRecordCount](#getrecordcount)|Bir kayıt kümesi nesnesinde erişilen kayıt sayısını döndürür.|
|[CDaoRecordset:: GetSQL](#getsql)|Kayıt kümesi için kayıt seçmek üzere kullanılan SQL dizesini alır.|
|[CDaoRecordset:: GetType](#gettype)|Bir kayıt kümesinin türünü belirlemekte çağırılır: tablo türü, Dynaset türü veya anlık görüntü türü.|
|[CDaoRecordset:: GetValidationRule](#getvalidationrule)|Bir alana girildiği için verileri doğrulayan değeri içeren `CString` döndürür.|
|[CDaoRecordset:: GetValidationText](#getvalidationtext)|Doğrulama kuralı karşılanmadığı zaman görüntülenen metni alır.|
|[CDaoRecordset:: IsBOF](#isbof)|Kayıt kümesi ilk kayıttan önce konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.|
|[CDaoRecordset:: IsDeleted](#isdeleted)|Kayıt kümesi silinen bir kayıt üzerinde konumlandırılmışsa sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: IOF](#iseof)|Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfır dışında bir değer döndürür. Geçerli kayıt yok.|
|[CDaoRecordset:: IsFieldDirty](#isfielddirty)|Geçerli kayıttaki belirtilen alan değiştirilmişse sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: IsFieldNull](#isfieldnull)|Geçerli kayıttaki belirtilen alan null ise (hiçbir değer olmadan) sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: Isfieldnullenebilir](#isfieldnullable)|Geçerli kayıttaki belirtilen alan null (değer olmadan) olarak ayarlandıysa sıfır dışında bir değer döndürür.|
|[CDaoRecordset:: IsOpen](#isopen)|[Open](#open) önceden çağrılırsa sıfır olmayan bir değer döndürür.|
|[CDaoRecordset:: Move](#move)|Kayıt kümesini geçerli kayıttaki belirtilen sayıda kayda her iki yönde konumlandırır.|
|[CDaoRecordset:: MoveFirst](#movefirst)|Kayıt kümesindeki ilk kayıttaki geçerli kaydı konumlandırır.|
|[CDaoRecordset:: MoveLast](#movelast)|Kayıt kümesindeki son kayıttaki geçerli kaydı konumlandırır.|
|[CDaoRecordset:: MoveNext](#movenext)|Kayıt kümesindeki bir sonraki kayıttaki geçerli kaydı konumlandırır.|
|[CDaoRecordset:: Moveöncekini](#moveprev)|Kayıt kümesindeki önceki kayıttaki geçerli kaydı konumlandırır.|
|[CDaoRecordset:: Open](#open)|Bir tablo, dynaset veya anlık görüntüden yeni bir kayıt kümesi oluşturur.|
|[CDaoRecordset:: Requery](#requery)|Seçilen kayıtları yenilemek için kayıt kümesinin sorgusunu yeniden çalıştırır.|
|[CDaoRecordset:: Seek](#seek)|Kaydı, geçerli dizin için belirtilen ölçütlere uyan bir dizinli tablo türü kayıt kümesi nesnesinde bulur ve bu kaydı geçerli kayıt yapar.|
|[CDaoRecordset:: SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını ayarlar.|
|[CDaoRecordset:: SetBookmark](#setbookmark)|Kayıt kümesini belirtilen yer işaretini içeren bir kayıt üzerinde konumlandırır.|
|[CDaoRecordset:: SetCacheSize](#setcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken türü Recordset içindeki kayıt sayısını belirten bir değer ayarlar.|
|[CDaoRecordset:: SetCacheStart](#setcachestart)|Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir değer ayarlar.|
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|Tablo türü bir kayıt kümesinde dizin ayarlamak için çağırılır.|
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|Geçerli kayıttaki belirtilen alanı değiştirildi olarak işaretler.|
|[CDaoRecordset:: SetFieldNull](#setfieldnull)|Geçerli kayıttaki belirtilen alanın değerini null olarak ayarlar (hiçbir değer olmadan).|
|[CDaoRecordset:: SetFieldValue](#setfieldvalue)|Bir kayıt kümesindeki bir alanın değerini ayarlar.|
|[CDaoRecordset:: SetFieldValueNull](#setfieldvaluenull)|Kayıt kümesindeki bir alanın değerini null olarak ayarlar. (değer olmadan).|
|[CDaoRecordset:: SetLockingMode](#setlockingmode)|Düzen sırasında yürürlüğe konacak kilit türünü gösteren bir değer ayarlar.|
|[CDaoRecordset:: SetParamValue](#setparamvalue)|Temel alınan Baoparameter nesnesinde depolanan belirtilen parametrenin geçerli değerini ayarlar|
|[CDaoRecordset:: SetParamValueNull](#setparamvaluenull)|Belirtilen parametrenin geçerli değerini null olarak ayarlar (hiçbir değer olmadan).|
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|Geçerli kaydın konumunu bir kayıt kümesindeki toplam kayıt sayısının yüzdesine karşılık gelen bir konuma ayarlar.|
|[CDaoRecordset:: Update](#update)|Yeni veya düzenlenmiş verileri veri kaynağına kaydederek bir `AddNew` veya `Edit` işlemi tamamlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset:: m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Alanların otomatik olarak değiştirilmiş olarak işaretlenip işaretlenmediğini belirten bir bayrak içerir.|
|[CDaoRecordset:: m_nFields](#m_nfields)|Kayıt kümesi sınıfındaki alan veri üyelerinin sayısını ve veri kaynağından kayıt kümesi tarafından seçilen sütun sayısını içerir.|
|[CDaoRecordset:: m_nParams](#m_nparams)|Kayıt kümesi sınıfındaki parametre veri üyelerinin sayısını içerir — kayıt kümesi sorgusuyla geçilen parametrelerin sayısı|
|[CDaoRecordset:: m_pDAORecordset](#m_pdaorecordset)|Kayıt kümesi nesnesini temel alan DAO arabirimine yönelik bir işaretçi.|
|[CDaoRecordset:: m_pDatabase](#m_pdatabase)|Bu sonuç kümesi için kaynak veritabanı. Bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine yönelik bir işaretçi içerir.|
|[CDaoRecordset:: m_strFilter](#m_strfilter)|SQL **WHERE** ifadesini oluşturmak için kullanılan bir dize içerir.|
|[CDaoRecordset:: m_strSort](#m_strsort)|SQL **order by** ifadesinin oluşturulması için kullanılan dizeyi içerir.|

## <a name="remarks"></a>Açıklamalar

"Kayıt kümeleri" olarak bilinen `CDaoRecordset` nesneleri aşağıdaki üç biçimde mevcuttur:

- Tablo türü kayıt kümeleri, tek bir veritabanı tablosundan kayıtları incelemek, eklemek, değiştirmek veya silmek için kullanabileceğiniz bir temel tabloyu temsil eder.

- Değişken tür kayıt kümeleri, güncelleştirilebilir kayıtları olan bir sorgunun sonucudur. Bu kayıt kümeleri, temel bir veritabanı tablosu veya tablolarından kayıtları incelemek, eklemek, değiştirmek veya silmek için kullanabileceğiniz bir kayıt kümesidir. DYNASET türü kayıt kümeleri, bir veritabanındaki bir veya daha fazla tablodan alan içerebilir.

- Anlık görüntü türü kayıt kümeleri, veri bulmak veya rapor oluşturmak için kullanabileceğiniz bir kayıt kümesinin statik kopyasıdır. Bu kayıt kümeleri, bir veritabanındaki bir veya daha fazla tablodan alan içerebilir, ancak güncelleştirilemez.

Her kayıt kümesi formu, kayıt kümesi açıldığı sırada düzeltilen bir kayıt kümesini temsil eder. Tablo türü bir kayıt kümesindeki veya bir dinamik küme türü kayıt kümesindeki bir kayda kaydırdığınızda, kayıt kümesi açıldıktan sonra, diğer kullanıcılar ya da uygulamanızdaki diğer kayıt kümeleri tarafından yapılan değişiklikleri yansıtır. (Bir anlık görüntü türü kayıt kümesi güncelleştirilemez.) `CDaoRecordset` doğrudan kullanabilir veya `CDaoRecordset`, uygulamaya özel bir kayıt kümesi sınıfını türetebilirsiniz. Daha sonra şunları yapabilirsiniz:

- Kayıtlarda ilerleyin.

- Bir dizin ayarlayın ve [Seek](#seek) (yalnızca tablo türü kayıt kümeleri) kullanarak kayıtları hızlıca arayın.

- Bir dize karşılaştırmasına göre kayıtları bulma: "<", "\<=", "=", "> =" veya ">" (Dynaset türü ve anlık görüntü türü kayıt kümeleri).

- Kayıtları güncelleştirin ve kilitleme modu (anlık görüntü türü kayıt kümeleri hariç) belirtin.

- Veri kaynağında kullanılabilir olanlardan seçim yaptığı kayıtları kısıtlamak için kayıt kümesini filtreleyin.

- Kayıt kümesini sıralayın.

- Çalışma zamanına kadar bilinmeyen bilgilerle seçimini özelleştirmek için kayıt kümesini parametreleştirin.

Sınıf `CDaoRecordset`, sınıf `CRecordset`benzer bir arabirim sağlar. Temel fark, sınıfın OLE tabanlı bir veri erişim nesnesi (DAO) yoluyla verilere eriştiği `CDaoRecordset`. Sınıf `CRecordset` DBMS 'ye açık veritabanı bağlantısı (ODBC) ve bu DBMS için bir ODBC sürücüsü aracılığıyla erişir.

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına yine de DAO sınıfları ile erişebilirsiniz; DAO sınıfları, Microsoft Jet veritabanı altyapısına özgü olduklarından üstün yetenekler sunar.

`CDaoRecordset` doğrudan kullanabilir veya `CDaoRecordset`bir sınıf türetebilirsiniz. Her iki durumda da bir kayıt kümesi sınıfı kullanmak için bir veritabanı açın ve bir kayıt kümesi nesnesi oluşturun ve oluşturucuyu `CDaoDatabase` nesneniz için bir işaretçi geçirerek. Ayrıca, bir `CDaoRecordset` nesnesi oluşturabilir ve MFC 'nin sizin için geçici bir `CDaoDatabase` nesnesi oluşturmasını sağlayabilirsiniz. Ardından, nesnenin bir tablo türü kayıt kümesi, bir değişken türü kayıt kümesi veya bir anlık görüntü türü kayıt kümesi olup olmadığını belirterek kayıt kümesinin [Açık](#open) üye işlevini çağırın. `Open` çağırmak, veritabanından veri seçer ve ilk kaydı alır.

Kayıtlarda gezinmek ve üzerinde işlem yapmak için nesnenin üye işlevlerini ve veri üyelerini kullanın. Kullanılabilir işlemler, nesnenin tablo türü bir kayıt kümesi, değişken tür bir kayıt kümesi veya bir anlık görüntü türü kayıt kümesi olmasına ve güncelleştirilebilir mi yoksa salt okunurdur mi olduğunu, bu veritabanının özelliğine veya açık veritabanı bağlantısına (ODBC) bağlı olmasına bağlıdır. veri kaynağı. `Open` çağrısından bu yana değiştirilmiş veya eklenmiş olabilecek kayıtları yenilemek için, nesnenin [YenidenSorgula](#requery) üye işlevini çağırın. Nesnenin `Close` üye işlevini çağırın ve ile bitirdiğinizde nesneyi yok edin.

`CDaoRecordset`, `CDaoRecordset` veya `CDaoRecordset`türetilmiş sınıfınızın tür açısından güvenli C++ üyeleri aracılığıyla kayıt alanlarını okumayı ve güncelleştirmeyi desteklemek için dao kayıt alanı DEĞIŞIMI (DFX) kullanır. [GetFieldValue](#getfieldvalue) ve [SETFIELDVALUE](#setfieldvalue)kullanarak DFX mekanizmasına gerek kalmadan, bir veritabanındaki sütunların dinamik bağlamasını da uygulayabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "kayıt kümesi nesnesi" konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

##  <a name="addnew"></a>CDaoRecordset:: AddNew

Tablo türü veya Dynaset türü bir kayıt kümesine yeni bir kayıt eklemek için bu üye işlevini çağırın.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Kaydın alanları başlangıçta null. (Veritabanı terimlerinde null "değer yok" anlamına gelir ve içinde C++null ile aynı değildir.) İşlemi gerçekleştirmek için, [Update](#update) member işlevini çağırmanız gerekir. `Update`, veri kaynağına yaptığınız değişiklikleri kaydeder.

> [!CAUTION]
>  Bir kaydı düzenleyip `Update`aramadan başka bir kayda kayırsanız değişiklikleriniz uyarı vermeden kaybedilir.

[AddNew](#addnew)' ı çağırarak Dynaset türünde bir kayıt kümesine bir kayıt eklerseniz, kayıt, kayıt kümesinde görünür olur ve yeni `CDaoRecordset` nesneleri tarafından görünür hale geldiği temel tabloya dahil edilir.

Yeni kaydın konumu, kayıt kümesinin türüne bağlıdır:

- Yeni kaydın eklendiği, değişken tür bir kayıt kümesinde garanti edilmez. Bu davranış, performans ve eşzamanlılık nedeniyle Microsoft Jet 3,0 ile değiştirilmiştir. Amacınız yeni eklenen kaydı geçerli kayıt yapmak istiyorsanız, son değiştirilen kaydın yer işaretini alın ve bu yer işaretine geçin:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- Bir dizinin belirtildiği tablo türü bir kayıt kümesinde, kayıtlar sıralama düzeninde doğru yerde döndürülür. Dizin belirtilmemişse, kayıt kümesinin sonunda yeni kayıtlar döndürülür.

`AddNew` kullanılmadan önce geçerli olan kayıt geçerli kalır. Yeni kaydı geçerli yapmak ve kayıt kümesini, yer imlerini desteklemek istiyorsanız, temel alınan DAO Kayıt kümesi nesnesinin LastModified özelliği ayarıyla tanımlanan yer işaretine [SetBookmark](#setbookmark) çağrısı yapın. Bunun yapılması, eklenen bir kayıttaki sayaç (otomatik artırma) alanlarının değerini belirlemek için faydalıdır. Daha fazla bilgi için bkz. [GetLastModifiedBookmark](#getlastmodifiedbookmark).

Veritabanı işlemleri destekliyorsa `AddNew` bir işlemin parçası olarak çağrı yapabilirsiniz. İşlemler hakkında daha fazla bilgi için bkz. Class [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). `AddNew`çağrılmadan önce [CDaoWorkspace:: BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) çağrısı yapmanız gerektiğini unutmayın.

[Açık](#open) üye işlevi çağrılmayan bir kayıt kümesi için `AddNew` çağrısı geçersizdir. Eklenmemiş bir kayıt kümesi için `AddNew` çağırırsanız `CDaoException` atılır. Kayıt kümesinin [CanAppend](#canappend)çağırarak güncelleştirilebilir olup olmadığını belirleyebilirsiniz.

Çerçeve, veri kaynağındaki kayda DAO Kayıt alanı değişimi (DFX) mekanizması tarafından yazıldıklarından emin olmak için alan veri üyelerini işaretler. Bir alanın değerini değiştirmek genellikle alanı kirli olarak ayarlar. bu nedenle, genel olarak [SetFieldDirty](#setfielddirty) çağrısı yapmanız gerekir, ancak bazen, alan veri üyesinde hangi değerin olduğuna bakılmaksızın sütunların açıkça güncelleştirilmesini veya eklenmesini sağlamak isteyebilirsiniz. DFX mekanizması **sözde null**kullanımını da kullanır. Daha fazla bilgi için bkz. [Cdadofieldexchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamamaktadır. Bu durumda, alanı kirli olarak ayarlamak gerekli olacaktır. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) bulunan bayrak, bu otomatik alan denetimini denetler.

> [!NOTE]
> Kayıtlar çift arabelleğe alıyorsa (yani, otomatik alan denetimi etkinse), `CancelUpdate` çağrısı, üye değişkenlerini `AddNew` veya `Edit` çağrılmadan önce sahip oldukları değerlere geri yükler.

İlgili bilgiler için, DAO yardımı 'nda "AddNew yöntemi", "CancelUpdate Yöntemi", "LastModified özelliği" ve "EditMode özelliği" konularına bakın.

##  <a name="canappend"></a>CDaoRecordset:: CanAppend

Daha önce açılan kayıt kümesinin [AddNew](#addnew) üye işlevini çağırarak yeni kayıtlar eklemenize izin verip sağlamamadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yeni kayıtlar eklemeye izin veriyorsa sıfır dışı; Aksi takdirde 0. kayıt kümesini salt okunurdur olarak açtıysanız `CanAppend` 0 döndürür.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "ekleme yöntemi" konusuna bakın.

##  <a name="canbookmark"></a>CDaoRecordset:: CanBookmark

Daha önce açılan kayıt kümesinin, kayıt imlerini kullanarak kayıtları tek tek işaretlemenizi isteyip istemediğinizi öğrenmek için bu üye işlevi çağırın.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yer imlerini destekliyorsa sıfır dışında 0.

### <a name="remarks"></a>Açıklamalar

Yalnızca Microsoft Jet veritabanı altyapısı tabloları tabanlı kayıt kümeleri kullanıyorsanız, yer işaretleri, salt ileri kaydırma kayıt kümeleri olarak işaretlenen anlık görüntü türü kayıt kümeleri dışında kullanılabilir. Diğer veritabanı ürünleri (dış ODBC veri kaynakları) yer işaretlerini desteklemiyor olabilir.

İlgili bilgiler için, DAO yardımı 'nda "Bookmarkable özelliği" konusuna bakın.

##  <a name="cancelupdate"></a>CDaoRecordset:: CancelUpdate

`CancelUpdate` üye işlevi, bir [düzenleme](#edit) veya [AddNew](#addnew) işlemi nedeniyle bekleyen tüm güncelleştirmeleri iptal eder.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

Örneğin, bir uygulama `Edit` veya `AddNew` üye işlevini çağırırsa ve [güncelleştirme](#update)çağrılmışsa, `CancelUpdate` `Edit` veya `AddNew` çağrıldıktan sonra yapılan değişiklikleri iptal eder.

> [!NOTE]
>  Kayıtlar çift arabelleğe alıyorsa (yani, otomatik alan denetimi etkinse), `CancelUpdate` çağrısı, üye değişkenlerini `AddNew` veya `Edit` çağrılmadan önce sahip oldukları değerlere geri yükler.

`Edit` veya `AddNew` işlemi beklenmemişse, `CancelUpdate` MFC 'nin bir özel durum oluşturmasına neden olur. İptal edilebilir bekleyen bir işlem olup olmadığını öğrenmek için [GetEditMode](#geteditmode) üye işlevini çağırın.

İlgili bilgiler için, DAO yardımı 'nda "CancelUpdate Yöntemi" konusuna bakın.

##  <a name="canrestart"></a>CDaoRecordset:: CanRestart

`Requery` üye işlevini çağırarak, kayıt kümesinin sorgunun yeniden başlatılmasını (kayıtlarını yenilemek için) izin verip sağlamamadığını öğrenmek için bu üye işlevi çağırın.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesinin sorgusunu tekrar çalıştırmak için `Requery` çağrılırsa sıfır değil, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Tablo türü kayıt kümeleri `Requery`desteklemez.

`Requery` desteklenmiyorsa, verileri yenilemek için [Kapat](#close) ' ı ve sonra [Aç](#open) ' ı çağırın. Parametre değerleri değiştirildikten sonra bir kayıt kümesi nesnesinin temel alınan parametre sorgusunu güncelleştirmek için `Requery` çağırabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "yeniden başlatılabilir özellik" konusuna bakın.

##  <a name="canscroll"></a>CDaoRecordset:: CanScroll

Kayıt kümesinin kaydırmaya izin verip içermediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıtlar arasında gezin, aksi takdirde 0 dışında geçiş yapabilirsiniz.

### <a name="remarks"></a>Açıklamalar

`dbForwardOnly`ile [Aç](#open) ' ı çağırırsanız, kayıt kümesi yalnızca ileri doğru kaydırabilirler.

İlgili bilgiler için, DAO yardımı 'nda "geçerli kayıt Işaretçisini DAO ile konumlandırma" konusuna bakın.

##  <a name="cantransact"></a>CDaoRecordset:: CanTransact

Kayıt kümesinin işlemlere izin verip sağlamamadığını öğrenmek için bu üye işlevini çağırın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan veri kaynağı işlemleri destekliyorsa sıfır dışı, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "Işlemler özelliği" konusuna bakın.

##  <a name="canupdate"></a>CDaoRecordset:: CanUpdate

Kayıt kümesinin güncelleştirilip güncelleştirimeyeceğini anlamak için bu üye işlevi çağırın.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirilemeyebilir (kayıtları ekleyin, güncelleştirin ve silin), aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi, temel alınan veri kaynağı salt okunurdur veya kayıt kümesi için [Aç](#open) ' i çağırdığınızda *noseçenekler* için `dbReadOnly` belirlediyseniz salt okunurdur.

İlgili bilgiler için, DAO yardımı 'nda "AddNew yöntemi", "düzenleme yöntemi", "silme yöntemi", "güncelleştirme yöntemi" ve "güncelleştirilebilir özellik" konularına bakın.

##  <a name="cdaorecordset"></a>CDaoRecordset:: CDaoRecordset

`CDaoRecordset` nesnesi oluşturur.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) NESNESI veya null değeri için bir işaretçi içerir. NULL değilse ve `CDaoDatabase` nesnenin `Open` üye işlevi onu veri kaynağına bağlamak için çağrılmışsa, kayıt kümesi kendi [Açık](#open) çağrısı sırasında sizin için açmaya çalışır. NULL geçirirseniz, `CDaoRecordset`kayıt kümesi sınıfınızı türettiğiniz takdirde belirttiğiniz veri kaynağı bilgileri kullanılarak bir `CDaoDatabase` nesnesi oluşturulur ve sizin için bağlanır.

### <a name="remarks"></a>Açıklamalar

`CDaoRecordset` doğrudan kullanabilir ya da uygulamaya özgü bir sınıfı `CDaoRecordset`türetebilirsiniz. Kayıt kümesi sınıflarınızı türetmek için ClassWizard ' i kullanabilirsiniz.

> [!NOTE]
>  Bir `CDaoRecordset` sınıfı türetirsiniz, türetilmiş sınıfınızın kendi oluşturucusunu sağlaması gerekir. Türetilmiş sınıfınızın oluşturucusunda, ile ilgili parametreleri geçirerek Oluşturucu `CDaoRecordset::CDaoRecordset`çağırın.

Sizin için otomatik olarak bir `CDaoDatabase` nesnesinin oluşturulmasını ve bağlanmasını sağlamak için kayıt kümesi yapıcısına NULL geçirin. Bu, kayıt kümenizin oluşturmadan önce bir `CDaoDatabase` nesnesi oluşturup bağlamanıza gerek olmayan yararlı bir kısayoldur. `CDaoDatabase` nesnesi açık değilse, sizin için varsayılan çalışma alanını kullanan bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi de oluşturulur. Daha fazla bilgi için bkz. [CDaoDatabase:: CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

##  <a name="close"></a>CDaoRecordset:: Close

Bir `CDaoRecordset` nesnenin kapatılması, ilişkili veritabanındaki açık kayıt kümeleri koleksiyonundan kaldırılır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

`Close` `CDaoRecordset` nesnesini yok etmez, aynı veri kaynağına veya farklı bir veri kaynağına `Open` çağırarak nesneyi yeniden kullanabilirsiniz.

Tüm bekleyen [AddNew](#addnew) veya [Edit](#edit) deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Bekleyen eklemeleri veya düzenlemeleri korumak istiyorsanız, her bir kayıt kümesi için `Close` çağırmadan önce [güncelleştirme](#update) çağırın.

`Close`çağrıldıktan sonra `Open` yeniden çağırabilirsiniz. Bu, kayıt kümesi nesnesini yeniden kullanmanıza olanak sağlar. Mümkünse, yeniden [sorgula](#requery)çağrısı yapmanız daha iyi bir alternatiftir.

İlgili bilgiler için, DAO yardımı 'nda "Yöntem kapatma" konusuna bakın.

##  <a name="delete"></a>CDaoRecordset::D Sil

Açık bir Dynaset türü veya tablo türü Recordset nesnesindeki geçerli kaydı silmek için bu üye işlevini çağırın.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı bir silme işleminden sonra, kayıt kümesinin alan verisi üyeleri bir boş değere ayarlanır ve silinen kaydın dışına geçmek için kayıt kümesi gezinti üye işlevlerinden birini ( [Move](#move), [Seek](#seek), [SetBookmark](#setbookmark), vb.) açıkça çağırmanız gerekir. Kayıtları bir kayıt kümesinden sildiğinizde, `Delete`çağırmadan önce kayıt kümesinde geçerli bir kayıt olmalıdır; Aksi halde MFC bir özel durum oluşturur.

`Delete` geçerli kaydı kaldırır ve erişilmez hale getirir. Silinen kaydı düzenleyemez veya kullanamazsınız, ancak geçerli kalır. Ancak, başka bir kayda geçtiğinizde, silinen kaydı yeniden geçerli yapamazsınız.

> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir olmalıdır ve `Delete`çağırdığınızda kayıt kümesinde geçerli olan geçerli bir kayıt olmalıdır. Örneğin, bir kaydı siler ancak `Delete` yeniden çağırmadan önce yeni bir kayda kaydıramıyorsunuz `Delete` bir [Cdaoözel durumu](../../mfc/reference/cdaoexception-class.md)oluşturur.

İşlemleri kullanırsanız ve [CDaoWorkspace:: Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevini çağırırsanız bir kaydın silmeyi geri alabilirsiniz. Temel tablo, bir basamaklı silme ilişkisinde birincil tablo ise, geçerli kaydın silinmesi yabancı bir tablodaki bir veya daha fazla kaydı da silebilir. Daha fazla bilgi için, DAO yardımı 'nda "basamaklı silme" tanımına bakın.

`AddNew` ve `Edit`aksine, bir `Delete` çağrısının ardından `Update`çağrısı olmaz.

İlgili bilgiler için, DAO yardımı 'nda "AddNew yöntemi", "düzenleme yöntemi", "silme yöntemi", "güncelleştirme yöntemi" ve "güncelleştirilebilir özellik" konularına bakın.

##  <a name="dofieldexchange"></a>CDaoRecordset::D oFieldExchange

Framework, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasında otomatik olarak veri alışverişi yapmak için bu üye işlevini çağırır.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Türk*<br/>
`CDaoFieldExchange` nesnesine yönelik bir işaretçi içerir. Çerçeve, alan değişim işlemi için bir bağlam belirtmek üzere bu nesneyi zaten ayarlamış.

### <a name="remarks"></a>Açıklamalar

Ayrıca, varsa parametre veri üyelerinizi, kayıt kümesinin seçimine yönelik SQL deyimindeki parametre yer tutucularına bağlar. DAO Kayıt alanı değişimi (DFX) olarak adlandırılan alan verileri alışverişi her iki yönde de işe yarar: kayıt kümesi nesnesinin alan veri üyelerinden veri kaynağındaki kaydın alanları ve veri kaynağındaki kayıttan kayıt kümesi nesnesi. Sütunları dinamik olarak bağlıyorsanız `DoFieldExchange`uygulamanız gerekmez.

Yalnızca türetilmiş kayıt kümesi sınıfınız için `DoFieldExchange` uygulamak için gerçekleştirmeniz gereken tek eylem, sınıfı ClassWizard ile oluşturmak ve alan veri üyelerinin adlarını ve veri türlerini belirtmek içindir. Ayrıca, parametre veri üyelerini belirtmek için ClassWizard 'ın yazdığı kodu ekleyebilirsiniz. Tüm alanlar dinamik olarak bağlanmışsa, parametre veri üyelerini belirtmediğiniz takdirde bu işlev devre dışı bırakılır.

Türetilmiş kayıt kümesi sınıfınızı ClassWizard ile bildirdiğinizde, sihirbaz sizin için `DoFieldExchange` bir geçersiz kılma yazar ve bu örnek aşağıdaki örneğe benzer:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>CDaoRecordset:: Edit

Geçerli kayıtta değişikliklere izin vermek için bu üye işlevi çağırın.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

`Edit` üye işlevini çağırdığınızda, geçerli kaydın alanlarında yapılan değişiklikler kopya arabelleğine kopyalanır. Kayıt üzerinde istediğiniz değişiklikleri yaptıktan sonra değişikliklerinizi kaydetmek için `Update` çağırın. `Edit`, kayıt kümesinin veri üyelerinin değerlerini kaydeder. `Edit`çağırır, değişiklikler yaparsanız ve `Edit` yeniden çağırırsanız, kaydın değerleri ilk `Edit` çağrısından önceki duruma geri yüklenir.

> [!CAUTION]
>  Bir kaydı düzenlerseniz ve sonra `Update`çağrılmadan başka bir kayda taşınan tüm işlemleri gerçekleştirirseniz, değişiklikleriniz uyarı vermeden kaybedilir. Ayrıca, kayıt kümesini veya üst veritabanını kapatırsanız, düzenlenen kaydınız uyarı vermeden atılır.

Bazı durumlarda, null (veri içermeyen) yaparak bir sütunu güncelleştirmek isteyebilirsiniz. Bunu yapmak için, alanı null olarak işaretlemek üzere TRUE parametresiyle birlikte `SetFieldNull` çağırın; Bu, sütunun güncelleştirilmesine de neden olur. Değer değişmemiş olmasına rağmen bir alanın veri kaynağına yazılmasını istiyorsanız, doğru bir parametresiyle `SetFieldDirty` çağırın. Bu, alanda null değeri olsa bile işe yarar.

Çerçeve, veri kaynağındaki kayda DAO Kayıt alanı değişimi (DFX) mekanizması tarafından yazıldıklarından emin olmak için alan veri üyelerini işaretler. Bir alanın değerini değiştirmek genellikle alanı kirli olarak ayarlar. bu nedenle, genel olarak [SetFieldDirty](#setfielddirty) çağrısı yapmanız gerekir, ancak bazen, alan veri üyesinde hangi değerin olduğuna bakılmaksızın sütunların açıkça güncelleştirilmesini veya eklenmesini sağlamak isteyebilirsiniz. DFX mekanizması **sözde null**kullanımını da kullanır. Daha fazla bilgi için bkz. [Cdadofieldexchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamamaktadır. Bu durumda, alanı kirli olarak ayarlamak gerekli olacaktır. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) bulunan bayrak, bu otomatik alan denetimini denetler.

Bir çok kullanıcılı ortamda pessimistically kayıt kümesi nesnesi kilitlendiğinde, güncelleştirme tamamlanana kadar `Edit`, kayıt zaman kilitli kalır. Kayıt kümesi optimizasyonu bir şekilde kilitliyse, kayıt kilitlenir ve veritabanında güncelleştirildikten hemen önce önceden düzenlenen kayıtla karşılaştırılır. `Edit`çağrıldıktan sonra kayıt değiştiyse, `Update` işlemi başarısız olur ve MFC bir özel durum oluşturur. Kilitleme modunu `SetLockingMode`değiştirebilirsiniz.

> [!NOTE]
>  İyimser kilitleme, ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimlerinde her zaman kullanılır.

`Edit`çağırdıktan sonra geçerli kayıt geçerli kalır. `Edit`çağırmak için, geçerli bir kayıt olmalıdır. Geçerli bir kayıt yoksa veya kayıt kümesi açık bir tablo türü veya Dynaset türü bir Recordset nesnesine başvurmaz, bir özel durum oluşur. `Edit` çağırmak aşağıdaki koşullarda bir `CDaoException` oluşturulmasına neden olur:

- Geçerli kayıt yok.

- Veritabanı veya kayıt kümesi salt okunurdur.

- Kayıttaki hiçbir alan güncelleştirilebilir değil.

- Veritabanı veya kayıt kümesi, başka bir kullanıcı tarafından özel kullanım için açıldı.

- Başka bir kullanıcı kaydınızı içeren sayfayı kilitlediği.

Veri kaynağı işlemleri destekliyorsa, `Edit` çağrısı bir işlemin parçası yapabilirsiniz. `Edit` çağrılmadan önce ve kayıt kümesi açıldıktan sonra `CDaoWorkspace::BeginTrans` çağırmanız gerektiğini unutmayın. Ayrıca, `Edit` işlemini tamamlamaya `Update` çağırmak için `CDaoWorkspace::CommitTrans` çağırma işleminin yerine konmadığını unutmayın. İşlemler hakkında daha fazla bilgi için bkz. sınıf `CDaoWorkspace`.

İlgili bilgiler için, DAO yardımı 'nda "AddNew yöntemi", "düzenleme yöntemi", "silme yöntemi", "güncelleştirme yöntemi" ve "güncelleştirilebilir özellik" konularına bakın.

##  <a name="fillcache"></a>CDaoRecordset:: FillCache

Kayıt kümesinden belirtilen sayıda kaydı önbelleğe almak için bu üye işlevi çağırın.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Parametreler

*Psıze*<br/>
Önbellekte doldurulacak satır sayısını belirtir. Bu parametreyi atlarsanız, değer temel alınan DAO nesnesinin CacheSize özelliği ayarıyla belirlenir.

*pBookmark*<br/>
Bir yer işareti belirten [Cotavariant](../../mfc/reference/colevariant-class.md) . Önbellek, bu yer işaretinin gösterdiği kayıttan başlayarak doldurulur. Bu parametreyi atlarsanız, önbellek, temel alınan DAO nesnesinin CacheStart özelliği tarafından belirtilen kayıttan başlayarak doldurulur.

### <a name="remarks"></a>Açıklamalar

Önbelleğe alma, uzak bir sunucudan veri alan veya getiren bir uygulamanın performansını geliştirir. Önbellek, sunucudan en son getirilen verileri tutan, verilerin büyük olasılıkla uygulama çalışırken tekrar istendiğinin varsayımına sahip olan yerel bellekteki alandır. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, verileri sunucudan getirmek yerine önce, daha fazla zaman alan verileri denetler. ODBC olmayan veri kaynaklarında veri önbelleğe alma özelliğinin kullanılması, veriler önbellekte kaydedilmediğinden hiçbir etkiye sahip değildir.

Önbellek, getirilen kayıtlarla doldurulmayı beklemek yerine, `FillCache` üye işlevini çağırarak önbelleği dilediğiniz zaman açık bir şekilde doldurabilirsiniz. Bu, `FillCache` her seferinde tek bir yerine birden çok kayıt getirtiğinden önbelleği doldurmanız daha hızlı bir yoldur. Örneğin, her bir kayıt görüntülenirken, uygulamanızın bir sonraki ekranda kayıtları getirmek için `FillCache` çağrısı yapabilirsiniz.

Kayıt kümesi nesneleriyle erişilen tüm ODBC veritabanları yerel bir önbelleğe sahip olabilir. Önbellek oluşturmak için, uzak veri kaynağından bir kayıt kümesi nesnesi açın ve ardından kayıt kümesinin `SetCacheSize` ve `SetCacheStart` üye işlevlerini çağırın. *LSize* ve *lbookmark* , `SetCacheSize` ve `SetCacheStart`tarafından belirtilen aralığın dışında kısmen veya tamamen dışarıda olan bir Aralık oluşturur, bu aralığın dışında kayıt kümesinin bölümü yok sayılır ve önbelleğe yüklenmez. `FillCache`, uzak veri kaynağında kalacağından daha fazla kayıt isterse, yalnızca kalan kayıtlar getirilir ve hiçbir özel durum oluşturulmaz.

Önbellekten getirilen kayıtlar, diğer kullanıcılar tarafından kaynak verilerde aynı anda yapılan değişiklikleri yansıtmaz.

`FillCache` yalnızca önceden önbelleğe alınmamış kayıtları getirir. Önbelleğe alınmış tüm verilerin güncelleştirilmesini zorlamak için, `SetCacheSize` member işlevini 0 ' a eşit bir *lSize* parametresiyle çağırın, *lSize* parametresini ilk istediğiniz önbelleğin boyutuna eşit olarak `SetCacheSize` çağırın ve ardından `FillCache`çağırın.

İlgili bilgiler için, DAO yardımı 'nda "FillCache yöntemi" konusuna bakın.

##  <a name="find"></a>CDaoRecordset:: Find

Bir karşılaştırma işleci kullanarak Dynaset veya anlık görüntü türü bir kayıt kümesinde belirli bir dizeyi bulmak için bu üye işlevi çağırın.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lFindType*<br/>
İstenen bulma işlemi türünü gösteren bir değer. Olası değerler şunlardır:

- Eşleşen bir dizenin sonraki konumunu bulmak AFX_DAO_NEXT.

- Eşleşen bir dizenin önceki konumunu bulmak AFX_DAO_PREV.

- AFX_DAO_FIRST eşleşen bir dizenin ilk konumunu bulur.

- AFX_DAO_LAST eşleşen bir dizenin son konumunu bulur.

*lpszFilter*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi (WHERE yan tümcesi **WHERE**yan tümcesi olmadan bir SQL **deyiminde olduğu gibi** ). Örnek:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

Dizenin ilk, sonraki, önceki veya son örneğini bulabilirsiniz. `Find` sanal bir işlevdir, bu sayede onu geçersiz kılabilir ve kendi uygulamanızı ekleyebilirsiniz. `FindFirst`, `FindLast`, `FindNext`ve `FindPrev` üye işlevleri `Find` üye işlevini çağırır, böylece tüm bulma işlemlerinin davranışını denetlemek için `Find` kullanabilirsiniz.

Tablo türü bir kayıt kümesindeki bir kaydı bulmak için [Seek](#seek) üye işlevini çağırın.

> [!TIP]
>  Sahip olduğunuz kayıt kümesi ne kadar küçükse, daha etkili `Find` olur. Genel olarak ve özellikle ODBC verileri ile, yalnızca istediğiniz kayıtları alan yeni bir sorgu oluşturmak daha iyidir.

İlgili bilgiler için, DAO yardımı 'nda "FindFirst, FindLast, Sonrabul, FindPrevious yöntemleri" konusuna bakın.

##  <a name="findfirst"></a>CDaoRecordset:: FindFirst

Belirtilen bir koşulla eşleşen ilk kaydı bulmak için bu üye işlevi çağırın.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi (WHERE yan tümcesi **WHERE**yan tümcesi olmadan bir SQL **deyiminde olduğu gibi** ).

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

`FindFirst` member işlevi, kayıt kümesinin başından itibaren aramasını başlatır ve kayıt kümesinin sonuna kadar arama yapar.

Aramanıza tüm kayıtları eklemek istiyorsanız (yalnızca belirli bir koşula uyan olanları değil), kayıttan kayda geçiş yapmak için taşıma işlemlerinden birini kullanın. Tablo türü bir kayıt kümesindeki bir kaydı bulmak için `Seek` member işlevini çağırın.

Ölçütlerle eşleşen bir kayıt bulunamıyorsa, geçerli kayıt işaretçisi belirlenmez ve `FindFirst` sıfır döndürür. Kayıt kümesi ölçütlere uyan birden fazla kayıt içeriyorsa, `FindFirst` ilk oluşumu bulur, sonraki oluşumu bulur `FindNext` ve bu şekilde devam eder.

> [!CAUTION]
>  Geçerli kaydı düzenlerseniz, başka bir kayda geçmeden önce `Update` üye işlevini çağırarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirme olmadan başka bir kayda geçiş yaparsanız değişiklikleriniz uyarı vermeden kaybedilir.

`Find` üye işlevleri, konumdan ve aşağıdaki tabloda belirtilen yönde arama yapılır:

|İşlemleri bul|BAŞLA|Arama yönü|
|---------------------|-----------|----------------------|
|`FindFirst`|Kayıt kümesi başlangıcı|Kayıt kümesi sonu|
|`FindLast`|Kayıt kümesi sonu|Kayıt kümesi başlangıcı|
|`FindNext`|Geçerli kayıt|Kayıt kümesi sonu|
|`FindPrevious`|Geçerli kayıt|Kayıt kümesi başlangıcı|

> [!NOTE]
>  `FindLast`çağırdığınızda, Microsoft Jet veritabanı altyapısı, henüz yapmadıysanız, aramaya başlamadan önce kayıt kümenizin sonuna tam olarak doldurur. İlk arama sonraki aramalardan daha uzun sürebilir.

Find işlemlerinden birinin kullanılması, çağırma `MoveFirst` veya `MoveNext`aynı değildir, ancak bir koşul belirtmeden ilk veya sonraki kaydı geçerli hale getirir. Bir Move işlemiyle bir Find işlemini izleyebilirsiniz.

Bulma işlemlerini kullanırken şunları aklınızda tutun:

- `Find` sıfır dışında bir değer döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda doğru konumlandırmalısınız.

- Yalnızca ileriye dönük bir kayan görüntü türü kayıt kümesiyle bir bul işlemi kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyor olsanız bile tarihleri içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmanız gerekir. Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanları ve büyük dinamik kümeler ile çalışırken, özellikle büyük kayıt kümeleriyle çalışırken bul işlemlerini kullanmanın yavaş olduğunu fark edebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya belirli dizine alınmış kayıtları alan `CDaoQuerydef` nesneleri ile SQL sorguları kullanarak performansı artırabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "FindFirst, FindLast, Sonrabul, FindPrevious yöntemleri" konusuna bakın.

##  <a name="findlast"></a>CDaoRecordset:: FindLast

Belirtilen bir koşulla eşleşen son kaydı bulmak için bu üye işlevi çağırın.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi (WHERE yan tümcesi **WHERE**yan tümcesi olmadan bir SQL **deyiminde olduğu gibi** ).

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

`FindLast` member işlevi, kayıt kümesinin sonunda aramasını başlatır ve kayıt kümesinin başlangıcında geriye doğru arar.

Aramanıza tüm kayıtları eklemek istiyorsanız (yalnızca belirli bir koşula uyan olanları değil), kayıttan kayda geçiş yapmak için taşıma işlemlerinden birini kullanın. Tablo türü bir kayıt kümesindeki bir kaydı bulmak için `Seek` member işlevini çağırın.

Ölçütlerle eşleşen bir kayıt bulunamıyorsa, geçerli kayıt işaretçisi belirlenmez ve `FindLast` sıfır döndürür. Kayıt kümesi ölçütlere uyan birden fazla kayıt içeriyorsa, `FindFirst` ilk oluşumu bulur, `FindNext` ilk oluşumdan sonra bir sonraki oluşumu bulur ve bu şekilde devam eder.

> [!CAUTION]
>  Geçerli kaydı düzenlerseniz, başka bir kayda geçmeden önce `Update` üye işlevini çağırarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirme olmadan başka bir kayda geçiş yaparsanız değişiklikleriniz uyarı vermeden kaybedilir.

Find işlemlerinden birinin kullanılması, çağırma `MoveFirst` veya `MoveNext`aynı değildir, ancak bir koşul belirtmeden ilk veya sonraki kaydı geçerli hale getirir. Bir Move işlemiyle bir Find işlemini izleyebilirsiniz.

Bulma işlemlerini kullanırken şunları aklınızda tutun:

- `Find` sıfır dışında bir değer döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda doğru konumlandırmalısınız.

- Yalnızca ileriye dönük bir kayan görüntü türü kayıt kümesiyle bir bul işlemi kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyor olsanız bile tarihleri içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmanız gerekir. Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanları ve büyük dinamik kümeler ile çalışırken, özellikle büyük kayıt kümeleriyle çalışırken bul işlemlerini kullanmanın yavaş olduğunu fark edebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya belirli dizine alınmış kayıtları alan `CDaoQuerydef` nesneleri ile SQL sorguları kullanarak performansı artırabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "FindFirst, FindLast, Sonrabul, FindPrevious yöntemleri" konusuna bakın.

##  <a name="findnext"></a>CDaoRecordset:: Sonrabul

Belirtilen koşulla eşleşen bir sonraki kaydı bulmak için bu üye işlevi çağırın.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi (WHERE yan tümcesi **WHERE**yan tümcesi olmadan bir SQL **deyiminde olduğu gibi** ).

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

`FindNext` member işlevi, geçerli kayıtta aramasını başlatır ve kayıt kümesinin sonuna kadar arama yapar.

Aramanıza tüm kayıtları eklemek istiyorsanız (yalnızca belirli bir koşula uyan olanları değil), kayıttan kayda geçiş yapmak için taşıma işlemlerinden birini kullanın. Tablo türü bir kayıt kümesindeki bir kaydı bulmak için `Seek` member işlevini çağırın.

Ölçütlerle eşleşen bir kayıt bulunamıyorsa, geçerli kayıt işaretçisi belirlenmez ve `FindNext` sıfır döndürür. Kayıt kümesi ölçütlere uyan birden fazla kayıt içeriyorsa, `FindFirst` ilk oluşumu bulur, sonraki oluşumu bulur `FindNext` ve bu şekilde devam eder.

> [!CAUTION]
>  Geçerli kaydı düzenlerseniz, başka bir kayda geçmeden önce `Update` üye işlevini çağırarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirme olmadan başka bir kayda geçiş yaparsanız değişiklikleriniz uyarı vermeden kaybedilir.

Find işlemlerinden birinin kullanılması, çağırma `MoveFirst` veya `MoveNext`aynı değildir, ancak bir koşul belirtmeden ilk veya sonraki kaydı geçerli hale getirir. Bir Move işlemiyle bir Find işlemini izleyebilirsiniz.

Bulma işlemlerini kullanırken şunları aklınızda tutun:

- `Find` sıfır dışında bir değer döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda doğru konumlandırmalısınız.

- Yalnızca ileriye dönük bir kayan görüntü türü kayıt kümesiyle bir bul işlemi kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyor olsanız bile tarihleri içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmanız gerekir. Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanları ve büyük dinamik kümeler ile çalışırken, özellikle büyük kayıt kümeleriyle çalışırken bul işlemlerini kullanmanın yavaş olduğunu fark edebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya belirli dizine alınmış kayıtları alan `CDaoQuerydef` nesneleri ile SQL sorguları kullanarak performansı artırabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "FindFirst, FindLast, Sonrabul, FindPrevious yöntemleri" konusuna bakın.

##  <a name="findprev"></a>CDaoRecordset:: Findöncekini

Belirtilen bir koşulla eşleşen önceki kaydı bulmak için bu üye işlevi çağırın.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFilter*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi (WHERE yan tümcesi **WHERE**yan tümcesi olmadan bir SQL **deyiminde olduğu gibi** ).

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

`FindPrev` member işlevi, geçerli kayıtta aramasını başlatır ve kayıt kümesinin başlangıcına doğru bir şekilde arar.

Aramanıza tüm kayıtları eklemek istiyorsanız (yalnızca belirli bir koşula uyan olanları değil), kayıttan kayda geçiş yapmak için taşıma işlemlerinden birini kullanın. Tablo türü bir kayıt kümesindeki bir kaydı bulmak için `Seek` member işlevini çağırın.

Ölçütlerle eşleşen bir kayıt bulunamıyorsa, geçerli kayıt işaretçisi belirlenmez ve `FindPrev` sıfır döndürür. Kayıt kümesi ölçütlere uyan birden fazla kayıt içeriyorsa, `FindFirst` ilk oluşumu bulur, sonraki oluşumu bulur `FindNext` ve bu şekilde devam eder.

> [!CAUTION]
>  Geçerli kaydı düzenlerseniz, başka bir kayda geçmeden önce `Update` üye işlevini çağırarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirme olmadan başka bir kayda geçiş yaparsanız değişiklikleriniz uyarı vermeden kaybedilir.

Find işlemlerinden birinin kullanılması, çağırma `MoveFirst` veya `MoveNext`aynı değildir, ancak bir koşul belirtmeden ilk veya sonraki kaydı geçerli hale getirir. Bir Move işlemiyle bir Find işlemini izleyebilirsiniz.

Bulma işlemlerini kullanırken şunları aklınızda tutun:

- `Find` sıfır dışında bir değer döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda doğru konumlandırmalısınız.

- Yalnızca ileriye dönük bir kayan görüntü türü kayıt kümesiyle bir bul işlemi kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyor olsanız bile tarihleri içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmanız gerekir. Aksi takdirde, eşleşen kayıtlar bulunamamış olabilir.

- ODBC veritabanları ve büyük dinamik kümeler ile çalışırken, özellikle büyük kayıt kümeleriyle çalışırken bul işlemlerini kullanmanın yavaş olduğunu fark edebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya belirli dizine alınmış kayıtları alan `CDaoQuerydef` nesneleri ile SQL sorguları kullanarak performansı artırabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "FindFirst, FindLast, Sonrabul, FindPrevious yöntemleri" konusuna bakın.

##  <a name="getabsoluteposition"></a>CDaoRecordset:: GetAbsolutePosition

Bir kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını döndürür.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısına 0 ' dan bir tamsayı. Kayıt kümesindeki geçerli kaydın sıra konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

Temel alınan DAO nesnesinin AbsolutePosition özelliği değeri sıfır tabanlıdır; 0 ayarı, kayıt kümesindeki ilk kayda başvurur. [GetRecordCount](#getrecordcount)' i çağırarak kayıt kümesindeki doldurulmuş kayıt sayısını belirleyebilirsiniz. `GetRecordCount` çağrısı bir süre sürebilir, çünkü sayıyı belirlemede tüm kayıtlara erişmesi gerekir.

Geçerli kayıt yoksa, kayıt kümesinde kayıt olmadığı gibi,-1 döndürülür. Geçerli kayıt silinirse, AbsolutePosition özelliği değeri tanımlı değildir ve başvuru varsa MFC bir özel durum oluşturur. Dinamik küme türü kayıt kümeleri için, sıranın sonuna yeni kayıtlar eklenir.

> [!NOTE]
>  Bu özellik, bir vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri, belirli bir konuma devam etmek ve geri dönmek için önerilen bir yoldur ve geçerli kaydı tüm kayıt kümesi nesne türleri arasında konumlandırmanız için tek yoldur. Özellikle, belirli bir kaydın konumu, kendisinden önceki kayıtlar silindikten sonra değişir. Ayrıca, bir kayıt kümesi içindeki tek kayıtların sırası bir **ORDERBY** yan TÜMCESI kullanılarak SQL deyimi ile oluşturulmadığı müddetçe, belirli bir kaydın aynı mutlak konuma sahip olacağı bir güvence yoktur.

> [!NOTE]
>  Bu üye işlevi yalnızca dinamik küme türü ve anlık görüntü türü kayıt kümeleri için geçerlidir.

İlgili bilgiler için, DAO yardımı 'nda "AbsolutePosition özelliği" konusuna bakın.

##  <a name="getbookmark"></a>CDaoRecordset:: GetBookmark

Belirli bir kayıttaki yer işareti değerini almak için bu üye işlevini çağırın.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıttaki yer işaretini temsil eden bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, bu kayıtların her birinin destekliyorsa benzersiz bir yer işareti vardır. Bir kayıt kümesinin yer imlerini destekleyip desteklemediğini anlamak için `CanBookmark` çağırın.

Yer işaretinin değerini bir `COleVariant` nesnesine atayarak, geçerli kayıt için yer işaretini kaydedebilirsiniz. Farklı bir kayda geçtikten sonra istediğiniz zaman bu kayda hızlıca dönmek için, bu `COleVariant` nesnesinin değerine karşılık gelen bir parametreyle `SetBookmark` çağırın.

> [!NOTE]
>  [YenidenSorgula](#requery) ÇAĞRıSı, DAO yer imlerini değiştirir.

İlgili bilgiler için, DAO yardımı 'nda "yer Işareti özelliği" konusuna bakın.

##  <a name="getcachesize"></a>CDaoRecordset:: GetCacheSize

Önbelleğe alınan kayıt sayısını almak için bu üye işlevi çağırın.

```
long GetCacheSize();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken türü Recordset içindeki kayıtların sayısını belirten bir değer.

### <a name="remarks"></a>Açıklamalar

Veri önbelleğe alma, dinamik bir sunucudan verileri alan ve değişken türü kayıt kümesi nesneleri aracılığıyla bir uygulamanın performansını geliştirir. Önbellek, uygulama çalışırken verilerin yeniden istenmesi durumunda sunucudan en son alınan verileri tutan yerel bellekteki bir alandır. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, verileri sunucudan almak yerine önce istenen verilerin önbelleğini denetler, bu da daha fazla zaman alır. ODBC veri kaynağından gelmeyen veriler önbellekte kaydedilmez.

Ekli tablo gibi tüm ODBC veri kaynakları yerel bir önbelleğe sahip olabilir.

İlgili bilgiler için, DAO yardımı 'nda "CacheSize, CacheStart özellikleri" konusuna bakın.

##  <a name="getcachestart"></a>CDaoRecordset:: GetCacheStart

Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işareti değerini almak için bu üye işlevini çağırın.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Dönüş Değeri

Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten `COleVariant`.

### <a name="remarks"></a>Açıklamalar

Microsoft Jet veritabanı altyapısı, önbellekten önbellek aralığı içinde kayıt ister ve sunucudan önbellek aralığı dışında kayıtlar ister.

> [!NOTE]
>  Önbellekten alınan kayıtlar, diğer kullanıcılar tarafından kaynak verilerde aynı anda yapılan değişiklikleri yansıtmaz.

İlgili bilgiler için, DAO yardımı 'nda "CacheSize, CacheStart özellikleri" konusuna bakın.

##  <a name="getcurrentindex"></a>CDaoRecordset:: GetCurrentIndex

Dizine alınmış bir tablo türü `CDaoRecordset` nesnesinde kullanılmakta olan dizini öğrenmek için bu üye işlevini çağırın.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Dönüş Değeri

Halen tablo türü bir kayıt kümesiyle kullanımda olan dizinin adını içeren bir `CString`. Bir dizin ayarlanmamışsa boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu dizin, tablo türü bir kayıt kümesindeki kayıtları sıralamak için temeldir ve kayıtları bulmak için [Seek](#seek) üye işlevi tarafından kullanılır.

Bir `CDaoRecordset` nesnesi birden fazla dizine sahip olabilir, ancak aynı anda yalnızca bir dizin kullanabilir (bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi üzerinde birçok dizine tanımlanmış olabilir).

İlgili bilgiler için, DAO yardımı 'nda "Dizin nesnesi" ve tanım "geçerli dizin" konusuna bakın.

##  <a name="getdatecreated"></a>CDaoRecordset:: GetDateCreated

Bir temel tablonun oluşturulduğu tarih ve saati almak için bu üye işlevini çağırın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel tablonun oluşturulduğu tarih ve saati içeren bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu bilgisayardan türetilir.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getdatelastupdated"></a>CDaoRecordset:: GetDateLastUpdated

Şemanın en son güncelleştirildiği tarihi ve saati almak için bu üye işlevi çağırın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel tablo yapısının (şema) son güncelleştirildiği tarih ve saati içeren bir [Cotadatetime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablo yapısının (şema) en son güncelleştirildiği bilgisayardan türetilir.

İlgili bilgiler için, DAO yardımı 'nda "DateCreated, LastUpdated özellikleri" konusuna bakın.

##  <a name="getdefaultdbname"></a>CDaoRecordset:: GetDefaultDBName

Bu kayıt kümesi için veritabanının adını öğrenmek üzere bu üye işlevi çağırın.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Dönüş Değeri

Bu kayıt kümesinin türetildiği veritabanının yolunu ve adını içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi, bir [cdaoveritabanı](../../mfc/reference/cdaodatabase-class.md)işaretçisi olmadan oluşturulduysa, bu yol kayıt kümesi tarafından varsayılan veritabanını açmak için kullanılır. Varsayılan olarak, bu işlev boş bir dize döndürür. ClassWizard `CDaoRecordset`yeni bir kayıt kümesi türettiği zaman sizin için bu işlevi oluşturacaktır.

Aşağıdaki örnek, dizenin doğru yorumlanması için gerekli olduğu gibi, dizesinde çift ters eğik çizgi (\\\\) kullanımını gösterir.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>CDaoRecordset:: GetDefaultSQL

Çerçeve, üzerinde kayıt kümesinin temel aldığı varsayılan SQL ifadesini almak için bu üye işlevini çağırır.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan SQL ifadesini içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Bu bir tablo adı veya bir SQL **Select** bildirisi olabilir.

Sınıf Sihirbazı ile kayıt kümesi sınıfınızı bildirerek varsayılan SQL ifadesini dolaylı olarak tanımlarsınız ve ClassWizard bu görevi sizin için gerçekleştirir.

[Açmak](#open)için null bir SQL dizesi geçirirseniz bu işlev, kayıt kümeniz için tablo adını veya SQL 'i belirlemekte çağrılır.

##  <a name="geteditmode"></a>CDaoRecordset:: GetEditMode

Aşağıdaki değerlerden biri olan düzenlemenin durumunu öğrenmek için bu üye işlevi çağırın:

```
short GetEditMode();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıt için düzenlemenin durumunu gösteren bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

|Değer|Açıklama|
|-----------|-----------------|
|`dbEditNone`|Devam eden bir Düzenle işlemi yok.|
|`dbEditInProgress`|`Edit` çağrıldı.|
|`dbEditAdd`|`AddNew` çağrıldı.|

İlgili bilgiler için, DAO yardımı 'nda "EditMode özelliği" konusuna bakın.

##  <a name="getfieldcount"></a>CDaoRecordset:: GetFieldCount

Kayıt kümesinde tanımlanan alan (sütun) sayısını almak için bu üye işlevi çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki alan sayısı.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "Count Property" konusuna bakın.

##  <a name="getfieldinfo"></a>CDaoRecordset:: GetFieldInfo

Bir kayıt kümesindeki alanlarla ilgili bilgi edinmek için bu üye işlevi çağırın.

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

*nDizin*<br/>
Dizine göre arama için kayıt kümesinin Fields koleksiyonundaki önceden tanımlanmış alanın sıfır tabanlı dizini.

*sağlanırken*<br/>
[Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak kayıt kümesiyle ilgili bilgileri belirleyen seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte listelenir. En iyi performansı elde etmek için yalnızca ihtiyacınız olan bilgi düzeyini alın:

- `AFX_DAO_PRIMARY_INFO` (varsayılan) ad, tür, boyut, öznitelik

- Birincil bilgileri `AFX_DAO_SECONDARY_INFO`, ayrıca: sıralı konum, gerekli, sıfır uzunluğa Izin ver, harmanlama sırası, yabancı ad, kaynak alanı, kaynak tablo

- Birincil ve ikincil bilgileri `AFX_DAO_ALL_INFO`, ayrıca: varsayılan değer, doğrulama kuralı, doğrulama metni

*lpszName*<br/>
Alanın adı.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü bir alanı dizine göre arama yapmanızı sağlar. Diğer sürüm, bir alanı adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için bkz. [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getfieldvalue"></a>CDaoRecordset:: GetFieldValue

Bir kayıt kümesindeki verileri almak için bu üye işlevini çağırın.

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
Bir alanın değerini depolayacak `COleVariant` nesnesine bir başvuru.

*nDizin*<br/>
Dizine göre arama için kayıt kümesinin Fields koleksiyonundaki alanın sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir değer döndüren `GetFieldValue` iki sürümü, bir alanın değerini içeren bir [Cotavariant](../../mfc/reference/colevariant-class.md) nesnesi döndürür.

### <a name="remarks"></a>Açıklamalar

Bir alanı ada veya sıralı konuma göre arayabilirsiniz.

> [!NOTE]
>  Bir `COleVariant` nesnesi döndüren sürümü çağırmak yerine, bir `COleVariant` nesne başvurusunu bir parametre olarak alan bu üye işlevinin sürümlerinden birini çağırmak daha etkilidir. Bu işlevin ikinci sürümleri geriye dönük uyumluluk için tutulur.

[DoFieldExchange](#dofieldexchange) mekanizmasını kullanarak sütunları statik olarak bağlama yerine çalışma zamanında dinamik olarak bağlamak için `GetFieldValue` ve [SetFieldValue](#setfieldvalue) kullanın.

`GetFieldValue` ve `DoFieldExchange` mekanizması performansı artırmak için birleştirilebilir. Örneğin, yalnızca talep üzerine ihtiyacınız olan bir değeri almak için `GetFieldValue` kullanın ve bu çağrıyı, arabirimdeki "daha fazla bilgi" düğmesine atayın.

İlgili bilgiler için, DAO yardımı 'nda "alan nesnesi" ve "değer özelliği" konularına bakın.

##  <a name="getindexcount"></a>CDaoRecordset:: GetIndexCount

Tablo türü kayıt kümesindeki kullanılabilir dizinlerin sayısını öğrenmek için bu üye işlevi çağırın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo türü kayıt kümesindeki dizinlerin sayısı.

### <a name="remarks"></a>Açıklamalar

`GetIndexCount`, kayıt kümesindeki tüm dizinlerde döngü için yararlıdır. Bu amaçla, [Getındexinfo](#getindexinfo)ile birlikte `GetIndexCount` kullanın. Bu üye işlevini Dynaset türü veya anlık görüntü türü kayıt kümelerinde çağırırsanız, MFC bir özel durum oluşturur.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getindexinfo"></a>CDaoRecordset:: GetIndexInfo

Bir kayıt kümesini temel tabloda tanımlanan bir dizin hakkında çeşitli bilgiler almak için bu üye işlevini çağırın.

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

*nDizin*<br/>
Sayısal konuma göre arama için tablonun dizinler koleksiyonundaki sıfır tabanlı dizin.

*ındexınfo*<br/>
Bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına başvuru.

*dwInfoOptions*<br/>
Alınacak dizin hakkındaki bilgileri belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte listelenir. En iyi performansı elde etmek için yalnızca ihtiyacınız olan bilgi düzeyini alın:

- `AFX_DAO_PRIMARY_INFO` (varsayılan) ad, alan bilgisi, alanlar

- `AFX_DAO_SECONDARY_INFO` birincil bilgiler, ayrıca: birincil, benzersiz, kümelenmiş, IgnoreNulls, gerekli, yabancı

- Birincil ve ikincil bilgileri `AFX_DAO_ALL_INFO`, ayrıca: ayrı sayım

*lpszName*<br/>
Ada göre arama için dizin nesnesinin adına yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, koleksiyondaki konumuyla bir dizin araması yapmanızı sağlar. Diğer sürüm, dizin adına göre arama yapmanızı sağlar.

Döndürülen bilgilerin açıklaması için, [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions*açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

İlgili bilgiler için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset:: GetLastModifiedBookmark

En son eklenen veya güncelleştirilmiş kaydın yer işaretini almak için bu üye işlevini çağırın.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

En son eklenen veya değiştirilen kaydı belirten bir yer işareti içeren `COleVariant`.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, bu kayıtların her birinin destekliyorsa benzersiz bir yer işareti vardır. Kayıt kümesinin yer imlerini destekleyip desteklemediğini anlamak için [GetBookmark](#getbookmark) öğesini çağırın. Kayıt kümesi yer imlerini desteklemiyorsa, bir `CDaoException` oluşturulur.

Bir kayıt eklediğinizde, kayıt kümesinin sonunda görünür ve geçerli kayıt değildir. Yeni kaydı güncel hale getirmek için `GetLastModifiedBookmark` çağırın ve sonra yeni eklenen kayda dönmek için `SetBookmark` çağırın.

İlgili bilgiler için, DAO yardımı 'nda "LastModified özelliği" konusuna bakın.

##  <a name="getlockingmode"></a>CDaoRecordset:: GetLockingMode

Kayıt kümesi için etkin olan kilitleme türünü öğrenmek için bu üye işlevini çağırın.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Dönüş Değeri

Kilitleme türü kötümser ise sıfır olmayan, iyimser kayıt kilitleme için 0.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme etkin olduğunda, düzenleme yaptığınız kaydı içeren veri sayfası, üye [Düzenle](#edit) işlevini çağırır almaz kilitlenir. [Update](#update) veya [Close](#close) üye Işlevini veya Move veya Find işlemlerinden birini çağırdığınızda sayfanın kilidi açılır.

İyimser kilitleme etkin olduğunda, kaydı içeren veri sayfası yalnızca kayıt `Update` üye işleviyle güncelleştirilirken kilitlenir.

ODBC veri kaynaklarıyla çalışırken kilitleme modu her zaman iyimser olur.

İlgili bilgiler için, DAO yardımı 'nda "LockEdits özelliği" ve "çok kullanıcılı uygulamalarda kilitleme davranışı" konularına bakın.

##  <a name="getname"></a>CDaoRecordset:: GetName

Kayıt kümesinin adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesinin adını içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin adı bir harfle başlamalı ve en fazla 40 karakter içerebilir. Sayılar ve alt çizgi karakterlerini içerebilir, ancak noktalama veya boşluk içeremez.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

##  <a name="getparamvalue"></a>CDaoRecordset:: GetParamValue

Temel alınan Baoparameter nesnesinde depolanan belirtilen parametrenin geçerli değerini almak için bu üye işlevini çağırın.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Temel alınan Davoparemeter nesnesindeki parametrenin sayısal konumu.

*lpszName*<br/>
Değerini istediğiniz parametrenin adı.

### <a name="return-value"></a>Dönüş Değeri

Parametrenin değerini içeren [Cotavariant](../../mfc/reference/colevariant-class.md) sınıfının bir nesnesi.

### <a name="remarks"></a>Açıklamalar

Parametreye ada veya koleksiyondaki sayısal konumuna göre erişebilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "parametre nesnesi" konusuna bakın.

##  <a name="getpercentposition"></a>CDaoRecordset:: GetPercentPosition

DYNASET türü veya anlık görüntü türü bir kayıt kümesiyle çalışırken, kayıt kümesini tamamen doldurmadan önce `GetPercentPosition` çağırırsanız, hareket miktarı [GetRecordCount](#getrecordcount)çağırarak belirtilen kayıt sayısına göre değişir.

```
float GetPercentPosition();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıtların yüzdesine göre kayıt kümesi nesnesindeki geçerli kaydın yaklaşık konumunu gösteren 0 ile 100 arasında bir sayı.

### <a name="remarks"></a>Açıklamalar

Tüm kayıt kümelerinin popülasyonunu tamamlayabilmeniz için [MoveLast yöntemini](#movelast) çağırarak son kayda geçebilirsiniz. Bu işlem, önemli ölçüde zaman alabilir.

Dizinleri olmayan tablolar da dahil olmak üzere, her üç türdeki kayıt kümesi nesnesi üzerinde `GetPercentPosition` çağırabilirsiniz. Ancak, salt ileri kaydırılan anlık görüntülerle veya bir geçiş sorgusundan bir dış veritabanına yönelik açılan bir kayıt kümesinde `GetPercentPosition` çağırılamaz. Geçerli kayıt yoksa veya geçerli kayıt silinmişse bir `CDaoException` oluşturulur.

İlgili bilgiler için, DAO yardımı 'nda "PercentPosition Özelliği" konusuna bakın.

##  <a name="getrecordcount"></a>CDaoRecordset:: GetRecordCount

Bir kayıt kümesindeki kaç kayda erişildiğini öğrenmek için bu üye işlevini çağırın.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesi nesnesinde erişilen kayıt sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

`GetRecordCount`, tüm kayıtlara erişilene kadar Dynaset türü veya anlık görüntü türü bir kayıt kümesinde kaç kayıt bulunduğunu göstermez. Bu üye işlev çağrısının tamamlanması, önemli miktarda zaman alabilir.

Son kayda erişildikten sonra, dönüş değeri, kayıt kümesindeki silinmeyen kayıtların toplam sayısını gösterir. Son kayda erişilmesine zorlamak için, kayıt kümesi için `MoveLast` veya `FindLast` üye işlevini çağırın. Sorgunuzun döndürdüğü kayıtların yaklaşık sayısını öğrenmek için bir SQL Count de kullanabilirsiniz.

Uygulamanız, kayıt kümesi türündeki bir Recordset içindeki kayıtları sildiği için `GetRecordCount` dönüş değeri azalır. Ancak, diğer kullanıcılar tarafından silinen kayıtlar, geçerli kayıt silinmiş bir kayda yerleştirilene kadar `GetRecordCount` yansıtılmaz. Kayıt sayısını etkileyen ve sonra işlemi geri alan bir işlem yürütüyor, `GetRecordCount` kalan kayıtların gerçek sayısını yansıtmayacaktır.

Bir anlık görüntü türü kayıt kümesinden `GetRecordCount` değeri, temel tablolardaki değişikliklerden etkilenmez.

Tablo türü bir kayıt kümesinden `GetRecordCount` değeri, tablodaki yaklaşık kayıt sayısını yansıtır ve tablo kayıtları eklenip silindiğine hemen etkilenir.

Kayıt içermeyen bir kayıt kümesi 0 değerini döndürür. Eklenmiş tablolar veya ODBC veritabanları ile çalışırken `GetRecordCount` her zaman-1 döndürür. Bir kayıt kümesinde `Requery` member işlevinin çağrılması, sorgunun yeniden yürütüldüğünden olduğu gibi `GetRecordCount` değerini sıfırlar.

İlgili bilgiler için, DAO yardımı 'nda "RecordCount özelliği" konusuna bakın.

##  <a name="getsql"></a>CDaoRecordset:: GetSQL

Açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL ifadesini almak için bu üye işlevi çağırın.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

SQL ifadesini içeren bir `CString`.

### <a name="remarks"></a>Açıklamalar

Bu, genellikle bir SQL **Select** deyimidir.

`GetSQL` tarafından döndürülen dize, genellikle *lpszSQL* parametresindeki kayıt kümesine [Açık](#open) üye işlevine geçirilebileceğiniz herhangi bir dizeden farklıdır. Bunun nedeni, kayıt kümesinin `Open`ne geçirdiklerinizi, ClassWizard ile belirtilerinizi ve [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) veri üyelerinde neleri belirtdiklerinizi temel alan tam bir SQL ifadesini oluşturur.

> [!NOTE]
>  Bu üye işlevini yalnızca `Open`çağrıldıktan sonra çağırın.

İlgili bilgiler için, DAO yardımı 'nda "SQL özelliği" konusuna bakın.

##  <a name="gettype"></a>CDaoRecordset:: GetType

Kayıt kümesi nesnesinin türünü öğrenmek için kayıt kümesini açtıktan sonra bu üye işlevini çağırın.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesinin türünü gösteren aşağıdaki değerlerden biri:

- `dbOpenTable` tablo türü kayıt kümesi

- `dbOpenDynaset` değişken kümesi türü Recordset

- `dbOpenSnapshot` anlık görüntü türü kayıt kümesi

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

##  <a name="getvalidationrule"></a>CDaoRecordset:: GetValidationRule

Verileri doğrulamak için kullanılan kuralı öğrenmek için bu üye işlevi çağırın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayda değiştiği veya tabloya eklendiği için bir kayıttaki verileri doğrulayan bir değeri içeren `CString` nesne.

### <a name="remarks"></a>Açıklamalar

Bu kural metin tabanlıdır ve temel alınan tablonun her değiştirildiği her seferinde uygulanır. Veriler geçerli değilse, MFC bir özel durum oluşturur. Döndürülen hata iletisi, temeldeki alan nesnesinin ValidationText özelliğinin, belirtilmişse veya temel alan nesnesinin ValidationRule özelliği tarafından belirtilen ifadenin metni. Hata iletisinin metnini almak için [GetValidationText](#getvalidationtext) öğesini çağırabilirsiniz.

Örneğin, ayın gününü gerektiren bir kayıttaki bir alan, "1 Ile 31 arasında gün" gibi bir doğrulama kuralına sahip olabilir.

İlgili bilgiler için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın.

##  <a name="getvalidationtext"></a>CDaoRecordset:: GetValidationText

Temel alan nesnesinin ValidationText özelliğinin metnini almak için bu üye işlevini çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

Bir alanın değeri, temel alan nesnesinin doğrulama kuralına uygun değilse görüntülenen iletinin metnini içeren `CString` nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın.

##  <a name="isbof"></a>CDaoRecordset:: IsBOF

Kayıt kümesinin ilk kaydından önce ilerlemeyeceğinizi öğrenmek için kayıttan kayda geçmeden önce Bu üye işlevini çağırın.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermiyorsa veya ilk kayıttan önce geriye doğru kaydırdıysanız sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin herhangi bir kayıt içerip içermediğini veya boş olduğunu anlamak için `IsEOF` birlikte `IsBOF` de çağırabilirsiniz. `Open`çağırdıktan hemen sonra, kayıt kümesi hiçbir kayıt içermiyorsa, `IsBOF` sıfır dışında bir değer döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, ilk kayıt geçerli kayıttır ve `IsBOF` 0 döndürür.

İlk kayıt geçerli kayıttır ve `MovePrev`çağırırsanız, `IsBOF` daha sonra sıfır dışında bir değer döndürür. `IsBOF` sıfır dışında bir değer döndürürse ve `MovePrev`çağırırsanız, bir özel durum oluşturulur. `IsBOF` sıfır dışında bir değer döndürürse, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektiren herhangi bir eylem, özel durum oluşmasına neden olur.

`IsBOF` ve `IsEOF` ayarlarındaki belirli yöntemlerin etkisi:

- `Open*` çağırarak, `MoveFirst`çağırarak kayıt kümesindeki ilk kaydı geçerli kayıt yapar. Bu nedenle, boş bir kayıt kümesinde `Open` çağırmak `IsBOF` ve `IsEOF` sıfır dışında dönüşmesine neden olur. (Başarısız bir `MoveFirst` veya `MoveLast` çağrısının davranışı için aşağıdaki tabloya bakın.)

- Bir kaydı başarıyla bulmayla ilgili tüm taşıma işlemleri, hem `IsBOF` hem de `IsEOF` 0 döndürmesine neden olur.

- Yeni bir kaydı başarıyla ekleyen bir `Update` çağrısı tarafından izlenen bir `AddNew` çağrısı, `IsBOF` 0 döndürmesini sağlar ancak yalnızca `IsEOF` sıfır dışında bir değer içeriyorsa. `IsEOF` durumu her zaman değişmeden kalır. Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi, boş bir kayıt kümesinin geçerli kayıt işaretçisi dosyanın sonunda bulunur, bu nedenle geçerli kayıttan sonra tüm yeni kayıtlar eklenir.

- Herhangi bir `Delete` çağrısı, bir kayıt kümesinden kalan kaydı kaldırsa bile, `IsBOF` veya `IsEOF`değerini değiştirmez.

Bu tablo, `IsBOF`/ `IsEOF`farklı birleşimleriyle hangi taşıma işlemlerine izin verileceğini gösterir.

||MoveFirst, MoveLast|MovePrev<br /><br /> < 0 taşı|0 taşı|Iken<br /><br /> > 0 taşı|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= sıfır dışında,<br /><br /> `IsEOF`= 0|İzin Verildi|Özel durum|Özel durum|İzin Verildi|
|`IsBOF`= 0,<br /><br /> `IsEOF`= sıfır dışında|İzin Verildi|İzin Verildi|Özel durum|Özel durum|
|Sıfır dışında|Özel durum|Özel durum|Özel durum|Özel durum|
|Her ikisi de 0|İzin Verildi|İzin Verildi|İzin Verildi|İzin Verildi|

Taşıma işlemine izin verilmesi, işlemin başarıyla bir kayıt bulabileceği anlamına gelmez. Yalnızca belirtilen taşıma işlemini gerçekleştirme denemesinin izin verileceğini ve bir özel durum oluşturmadığını gösterir. `IsBOF` ve `IsEOF` member işlevlerinin değeri, denenen taşımanın sonucu olarak değişebilir.

`IsBOF` değerinde bir kayıt bulmayan taşıma işlemlerinin etkisi ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.

||IsBOF|IOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır olmayan|Sıfır olmayan|
|`Move` 0|Değişiklik yok|Değişiklik yok|
|`MovePrev`, `Move` < 0|Sıfır olmayan|Değişiklik yok|
|`MoveNext`, `Move` > 0|Değişiklik yok|Sıfır olmayan|

İlgili bilgiler için, DAO yardımı 'nda "BOF, EOF özellikleri" konusuna bakın.

##  <a name="isdeleted"></a>CDaoRecordset:: IsDeleted

Geçerli kaydın silinip silinmediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayıtta konumlandırılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kayırsanız ve `IsDeleted` TRUE (sıfır dışında) döndürürse, başka bir kayıt kümesi işlemini gerçekleştirebilmek için önce başka bir kayda kaydırmanız gerekir.

> [!NOTE]
>  Bir anlık görüntü veya tablo türü kayıt kümesindeki kayıtlar için silinen durumu denetlemeniz gerekmez. Kayıtlar bir anlık görüntüden silinemediğinden `IsDeleted`çağırmanız gerekmez. Tablo türü kayıt kümeleri için, silinen kayıtlar aslında kayıt kümesinden kaldırılır. Siz, başka bir Kullanıcı ya da başka bir kayıt kümesi tarafından bir kayıt silindikten sonra, bu kayda geri kaydıramıyorsunuz. Bu nedenle, `IsDeleted`çağırmanız gerekmez.

Bir kayıt kümesinden bir kaydı sildiğinizde, kayıt kümesinden kaldırılır ve bu kayda geri kaydıramıyorsunuz. Ancak, bir Dynaset içindeki bir kayıt, başka bir kullanıcı tarafından veya aynı tabloyu temel alan başka bir kayıt kümesinde silinirse, daha sonra bu kayda kaydığınızda, `IsDeleted` TRUE döndürür.

İlgili bilgiler için, DAO yardımı 'nda "silme yöntemi", "LastModified özelliği" ve "EditMode özelliği" konularına bakın.

##  <a name="iseof"></a>CDaoRecordset:: IOF

Kayıt kümesinin son kaydını aşıp geçmeyeceğinizi öğrenmek için kayıttan kayda gittiğinden bu üye işlevi çağırın.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi hiçbir kayıt içermiyorsa veya son kaydın ötesine kaydırdıysanız sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Ayrıca, kayıt kümesinin herhangi bir kayıt içerip içermediğini veya boş olduğunu anlamak için `IsEOF` çağırabilirsiniz. `Open`çağırdıktan hemen sonra, kayıt kümesi hiçbir kayıt içermiyorsa, `IsEOF` sıfır dışında bir değer döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, ilk kayıt geçerli kayıttır ve `IsEOF` 0 döndürür.

`MoveNext`çağırdığınızda son kayıt geçerli kayıt ise, `IsEOF` daha sonra sıfır dışında bir değer döndürür. `IsEOF` sıfır dışında bir değer döndürürse ve `MoveNext`çağırırsanız, bir özel durum oluşturulur. `IsEOF` sıfır dışında bir değer döndürürse, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektiren herhangi bir eylem, özel durum oluşmasına neden olur.

`IsBOF` ve `IsEOF` ayarlarındaki belirli yöntemlerin etkisi:

- `Open` çağırarak, `MoveFirst`çağırarak kayıt kümesindeki ilk kaydı geçerli kayıt yapar. Bu nedenle, boş bir kayıt kümesinde `Open` çağırmak `IsBOF` ve `IsEOF` sıfır dışında dönüşmesine neden olur. (Başarısız `MoveFirst` çağrısının davranışı için aşağıdaki tabloya bakın.)

- Bir kaydı başarıyla bulmayla ilgili tüm taşıma işlemleri, hem `IsBOF` hem de `IsEOF` 0 döndürmesine neden olur.

- Yeni bir kaydı başarıyla ekleyen bir `Update` çağrısı tarafından izlenen bir `AddNew` çağrısı, `IsBOF` 0 döndürmesini sağlar ancak yalnızca `IsEOF` sıfır dışında bir değer içeriyorsa. `IsEOF` durumu her zaman değişmeden kalır. Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi, boş bir kayıt kümesinin geçerli kayıt işaretçisi dosyanın sonunda bulunur, bu nedenle geçerli kayıttan sonra tüm yeni kayıtlar eklenir.

- Herhangi bir `Delete` çağrısı, bir kayıt kümesinden kalan kaydı kaldırsa bile, `IsBOF` veya `IsEOF`değerini değiştirmez.

Bu tablo, `IsBOF`/ `IsEOF`farklı birleşimleriyle hangi taşıma işlemlerine izin verileceğini gösterir.

||MoveFirst, MoveLast|MovePrev<br /><br /> < 0 taşı|0 taşı|Iken<br /><br /> > 0 taşı|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= sıfır dışında,<br /><br /> `IsEOF`= 0|İzin Verildi|Özel durum|Özel durum|İzin Verildi|
|`IsBOF`= 0,<br /><br /> `IsEOF`= sıfır dışında|İzin Verildi|İzin Verildi|Özel durum|Özel durum|
|Sıfır dışında|Özel durum|Özel durum|Özel durum|Özel durum|
|Her ikisi de 0|İzin Verildi|İzin Verildi|İzin Verildi|İzin Verildi|

Taşıma işlemine izin verilmesi, işlemin başarıyla bir kayıt bulabileceği anlamına gelmez. Yalnızca belirtilen taşıma işlemini gerçekleştirme denemesinin izin verileceğini ve bir özel durum oluşturmadığını gösterir. `IsBOF` ve `IsEOF` member işlevlerinin değeri, denenen taşımanın sonucu olarak değişebilir.

`IsBOF` değerinde bir kayıt bulmayan taşıma işlemlerinin etkisi ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.

||IsBOF|IOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır olmayan|Sıfır olmayan|
|`Move` 0|Değişiklik yok|Değişiklik yok|
|`MovePrev`, `Move` < 0|Sıfır olmayan|Değişiklik yok|
|`MoveNext`, `Move` > 0|Değişiklik yok|Sıfır olmayan|

İlgili bilgiler için, DAO yardımı 'nda "BOF, EOF özellikleri" konusuna bakın.

##  <a name="isfielddirty"></a>CDaoRecordset:: IsFieldDirty

Bir Dynaset 'in belirtilen alan verisi üyesinin "kirli" (değiştirildi) olarak işaretlenip işaretlenmediğini öğrenmek için bu üye işlevi çağırın.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin kirli olup olmadığını belirleme NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan verisi üyesi kirli olarak işaretlense sıfır dışında; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Geçerli kayıt, `CDaoRecordset` `Update` üye işlevine yapılan bir çağrı (`Edit` veya `AddNew`bir çağrıdan sonra) tarafından güncelleştirildiği zaman, tüm kirli alan verileri üyelerinde veri kaynağındaki kayda aktarılır. Bu bilgi ile, alanı veri kaynağına yazılmayacak şekilde işaretlemek için alan veri üyesinin işaretini kaldırma gibi daha fazla adım alabilirsiniz.

`IsFieldDirty`, `DoFieldExchange`ile uygulanır.

##  <a name="isfieldnull"></a>CDaoRecordset:: IsFieldNull

Bir kayıt kümesinin belirtilen alan verisi üyesinin null olarak işaretlenip işaretlenmediğini öğrenmek için bu üye işlevini çağırın.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin null olup olmadığını belirleme NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan verisi üyesi null olarak işaretlense sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

(Veritabanı terimlerinde null "değer yok" anlamına gelir ve içinde C++null ile aynı değildir.) Bir alan veri üyesine null olarak bayrak eklenmiş ise, geçerli kaydın değeri olmayan bir sütun olarak yorumlanır.

> [!NOTE]
>  Bazı durumlarda, aşağıdaki kod örneğinde gösterildiği gibi `IsFieldNull` kullanımı verimsiz olabilir:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  `CDaoRecordset`türetmeden dinamik kayıt bağlama kullanıyorsanız, örnekte gösterildiği gibi VT_NULL kullandığınızdan emin olun.

##  <a name="isfieldnullable"></a>CDaoRecordset:: Isfieldnullenebilir

Belirtilen alan verisi üyesinin "Nullable" olup olmadığını ve null değere ayarlanamayacağını öğrenmek için bu üye işlevi çağırın; C++ Null, Veritabanı terminolojisinde "hiçbir değer yok" anlamına gelen null ile aynı değildir.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Durumu denetlemek istediğiniz alan verisi üyesine yönelik bir işaretçi veya alanlardan birinin null olup olmadığını belirleme NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan verisi üyesi null yapılırsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Null olmayan bir alan bir değere sahip olmalıdır. Bir kaydı eklerken veya güncelleştirirken bu tür bir alanı null olarak ayarlamaya çalışırsanız, veri kaynağı ekleme veya güncelleştirmeyi reddeder ve `Update` bir özel durum oluşturur. Özel durum, `SetFieldNull`çağırdığınızda değil `Update`çağırdığınızda oluşur.

##  <a name="isopen"></a>CDaoRecordset:: IsOpen

Kayıt kümesinin açık olup olmadığını anlamak için bu üye işlevini çağırın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi nesnesinin `Open` veya `Requery` member işlevi daha önce çağrılırsa ve kayıt kümesi kapanmamış ise sıfır dışı. Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: m_bCheckCacheForDirtyFields

Önbelleğe alınmış alanların otomatik olarak kirli (değiştirilmiş) ve null olarak işaretlenip işaretlenmeyeceğini belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Bayrak varsayılan olarak TRUE değerini alır. Bu veri üyesinde ayarı, tüm çift arabelleğe alma mekanizmasını denetler. Bayrağını TRUE olarak ayarlarsanız, DFX mekanizmayı kullanarak alan temelinde önbelleğe alma işlemini kapatabilirsiniz. Bayrağını FALSE olarak ayarlarsanız, `SetFieldDirty` ve `SetFieldNull` çağırmanız gerekir.

`Open`çağrılmadan önce bu veri üyesini ayarlayın. Bu mekanizma öncelikli olarak kullanım kolaylığı içindir. Değişiklikler yapıldığından alanların çift arabelleğe alınması nedeniyle performans daha yavaş olabilir.

##  <a name="m_nfields"></a>CDaoRecordset:: m_nFields

Kayıt kümesi sınıfındaki alan veri üyelerinin sayısını ve veri kaynağından kayıt kümesi tarafından seçilen sütun sayısını içerir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfına yönelik oluşturucunun doğru sayıda statik olarak ilişkili alan `m_nFields` başlatması gerekir. ClassWizard, kayıt kümesi sınıfınızı bildirmek için kullandığınızda bu başlatmayı sizin için yazar. Ayrıca, el ile de yazabilirsiniz.

Framework, alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasındaki etkileşimi yönetmek için bu numarayı kullanır.

> [!NOTE]
>  Bu sayı, `CDaoFieldExchange::outputColumn`parametresiyle `SetFieldType` çağrısından sonra `DoFieldExchange` kayıtlı olan çıktı sütunlarının sayısına karşılık gelmelidir.

Sütunları `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue`şekilde dinamik olarak bağlayabilirsiniz. Bunu yaparsanız, `DoFieldExchange` üye işlevinizdeki DFX işlev çağrılarının sayısını yansıtmak için `m_nFields` sayısını artırmanız gerekmez.

##  <a name="m_nparams"></a>CDaoRecordset:: m_nParams

Kayıt kümesi sınıfındaki parametre veri üyelerinin sayısını içerir — kayıt kümesi sorgusuyla geçilen parametre sayısı.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızın herhangi bir parametre veri üyesi varsa, sınıfın oluşturucusunun doğru sayıyla *m_nParams* başlatması gerekir. *M_nParams* değeri varsayılan olarak 0 ' dır. El ile yapmanız gereken parametre veri üyelerini eklerseniz, parametre sayısını yansıtmak için sınıf oluşturucusunda bir başlatma da eklemeniz gerekir (Bu, en azından *m_strFilter* veya *m_strSort* dizesindeki ' ' yer tutucuları sayısı kadar büyük olmalıdır).

Çerçeve, kayıt kümesinin sorgusunu parametrelendirtiğinde bu numarayı kullanır.

> [!NOTE]
>  Bu sayı, `CFieldExchange::param`parametresiyle `SetFieldType` çağrısından sonra `DoFieldExchange` kayıtlı olan "params" sayısına karşılık gelmelidir.

İlgili bilgiler için, DAO yardımı 'nda "parametre nesnesi" konusuna bakın.

##  <a name="m_pdaorecordset"></a>CDaoRecordset:: m_pDAORecordset

`CDaoRecordset` nesnesini temel alan DAO Kayıt kümesi nesnesi için OLE arabirimine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

İlgili bilgiler için, DAO yardımı 'nda "kayıt kümesi nesnesi" konusuna bakın.

##  <a name="m_pdatabase"></a>CDaoRecordset:: m_pDatabase

Kayıt kümesinin bir veri kaynağına bağlı olduğu `CDaoDatabase` nesnesine yönelik bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu değişken iki şekilde ayarlanır. Genellikle, kayıt kümesi nesnesini oluştururken zaten açık olan bir `CDaoDatabase` nesnesine bir işaretçi geçirirsiniz. Bunun yerine NULL geçirirseniz `CDaoRecordset`, sizin için bir `CDaoDatabase` nesnesi oluşturur ve açar. Her iki durumda da, `CDaoRecordset` işaretçiyi Bu değişkende depolar.

Normalde, `m_pDatabase`' de depolanan işaretçiyi doğrudan kullanmanız gerekmez. `CDaoRecordset`için kendi uzantılarınızı yazarsanız, işaretçiyi kullanmanız gerekebilir. Örneğin, kendi `CDaoException`belirtirseniz işaretçiye gerek duyabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "veritabanı nesnesi" konusuna bakın.

##  <a name="m_strfilter"></a>CDaoRecordset:: m_strFilter

Bir SQL ifadesinin **WHERE** yan tümcesini oluşturmak için kullanılan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesine filtre uygulanacak **olan** ayrılmış kelimeyi içermez. Bu veri üyesinin kullanımı tablo türü kayıt kümeleri için geçerli değildir. `m_strFilter` kullanımı, bir `CDaoQueryDef` işaretçisi kullanarak bir kayıt kümesi açılırken hiçbir etkiye sahip değildir.

Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyor olsanız bile tarihleri içeren alanları filtreleyerek ABD tarih biçimini kullanın (ay-gün-yıl). Aksi takdirde, veriler beklenen şekilde filtrelenmemiş olabilir.

İlgili bilgiler için, DAO yardımı 'nda "filtre özelliği" konusuna bakın.

##  <a name="m_strsort"></a>CDaoRecordset:: m_strSort

Ayrılmış kelimeleri **OrderBy**olmayan bir SQL deyimi **OrderBy** yan tümcesini içeren bir dize içerir.

### <a name="remarks"></a>Açıklamalar

DYNASET ve anlık görüntü türü kayıt kümesi nesnelerinde sıralama yapabilirsiniz.

Tablo türü kayıt kümesi nesnelerini sıralayamazsınız. Tablo türü bir kayıt kümesinin sıralama düzenini öğrenmek için [SetCurrentIndex](#setcurrentindex)' i çağırın.

*M_strSort* kullanımı, bir `CDaoQueryDef` işaretçisi kullanarak bir kayıt kümesi açılırken hiçbir etkiye sahip değildir.

İlgili bilgiler için, DAO yardımı 'nda "sıralama özelliği" konusuna bakın.

##  <a name="move"></a>CDaoRecordset:: Move

Kayıt kümesi *lRows* kayıtlarını geçerli kayıttan konumlandırmak için bu üye işlevini çağırın.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Parametreler

*lRows*<br/>
İleri veya geri taşınacak kayıt sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru ileri doğru taşınır. Negatif değerler geriye doğru, başlangıca taşınır.

### <a name="remarks"></a>Açıklamalar

İleri veya geri gidebilirsiniz. `Move( 1 )` `MoveNext`eşdeğerdir ve `Move( -1 )` `MovePrev`eşdeğerdir.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Genel olarak, kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için bir taşıma işleminden önce hem `IsBOF` hem de `IsEOF` çağırın. `Open` veya `Requery`çağırdıktan sonra, `IsBOF` ya da `IsEOF`çağırın.

> [!NOTE]
>  Kayıt kümesinin başlangıcını veya sonunu (`IsBOF` veya `IsEOF` sıfır dışında bir değer döndürür) daha önce kaydırdıysanız, bir `Move` çağrısı `CDaoException`oluşturur.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Yalnızca ileri yönlü bir kayan görüntüde `Move` çağırdığınızda, *lRows* parametresi pozitif bir tamsayı olmalıdır ve yer işaretlerine yalnızca ileri taşıyabilirsiniz.

Geçerli kayıt bir kayıt kümesinde ilk, son, sonraki veya önceki kaydı yapmak için `MoveFirst`, `MoveLast`, `MoveNext`veya `MovePrev` member işlevini çağırın.

İlgili bilgiler için, DAO yardımı 'nda "taşıma yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

##  <a name="movefirst"></a>CDaoRecordset:: MoveFirst

Kayıt kümesindeki (varsa) ilk kaydı geçerli kayıt yapmak için bu üye işlevi çağırın.

```
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Kayıt kümesini açtıktan hemen sonra `MoveFirst` çağırmanız gerekmez. Bu sırada, ilk kayıt (varsa) otomatik olarak geçerli kayıt olur.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Genel olarak, kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için bir taşıma işleminden önce hem `IsBOF` hem de `IsEOF` çağırın. `Open` veya `Requery`çağırdıktan sonra, `IsBOF` ya da `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Bir koşul uygulamadan kayıttan kayda geçmek için `Move` işlevlerini kullanın. Belirli bir koşulu karşılayan bir değişken tür veya anlık görüntü türü kayıt kümesi nesnesinde kayıtları bulmak için bulma işlemlerini kullanın. Tablo türü bir kayıt kümesi nesnesinde bir kaydı bulmak için `Seek`çağırın.

Kayıt kümesi tablo türü bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Geçerli dizini, temel alınan DAO nesnesinin Index özelliğini kullanarak ayarlayabilirsiniz. Geçerli dizini ayarlanmamışsa döndürülen kayıtların sırası tanımsızdır.

Bir SQL sorgusunu veya QueryDef 'i temel alan bir kayıt kümesi nesnesinde `MoveLast` çağırırsanız, sorgu tamamlamaya zorlanır ve kayıt kümesi nesnesi tamamen doldurulur.

`MoveFirst` veya `MovePrev` üye işlevini yalnızca ileriye doğru bir kayan görüntüyle çağıramezsiniz.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu belirli bir kayıt veya geriye doğru bir şekilde taşımak için `Move`çağırın.

İlgili bilgiler için, DAO yardımı 'nda "taşıma yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

##  <a name="movelast"></a>CDaoRecordset:: MoveLast

Geçerli kaydın kayıt kümesindeki son kaydı (varsa) yapmak için bu üye işlevi çağırın.

```
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Genel olarak, kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için bir taşıma işleminden önce hem `IsBOF` hem de `IsEOF` çağırın. `Open` veya `Requery`çağırdıktan sonra, `IsBOF` ya da `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Bir koşul uygulamadan kayıttan kayda geçmek için `Move` işlevlerini kullanın. Belirli bir koşulu karşılayan bir değişken tür veya anlık görüntü türü kayıt kümesi nesnesinde kayıtları bulmak için bulma işlemlerini kullanın. Tablo türü bir kayıt kümesi nesnesinde bir kaydı bulmak için `Seek`çağırın.

Kayıt kümesi tablo türü bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Geçerli dizini, temel alınan DAO nesnesinin Index özelliğini kullanarak ayarlayabilirsiniz. Geçerli dizini ayarlanmamışsa döndürülen kayıtların sırası tanımsızdır.

Bir SQL sorgusunu veya QueryDef 'i temel alan bir kayıt kümesi nesnesinde `MoveLast` çağırırsanız, sorgu tamamlamaya zorlanır ve kayıt kümesi nesnesi tamamen doldurulur.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu belirli bir kayıt veya geriye doğru bir şekilde taşımak için `Move`çağırın.

İlgili bilgiler için, DAO yardımı 'nda "taşıma yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

##  <a name="movenext"></a>CDaoRecordset:: MoveNext

Kayıt kümesindeki bir sonraki kaydı geçerli kayıt haline getirmek için bu üye işlevi çağırın.

```
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Önceki kayda geçiş yapmayı denemeden önce `IsBOF` çağırmanız önerilir. `MovePrev` çağrısı, `IsBOF` sıfır dışında bir değer döndürürse, ilk kayıttan önce kaydırıldığınız ya da kayıt kümesi tarafından hiçbir kaydın seçilmediğini belirten bir `CDaoException` oluşturur.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Genel olarak, kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için bir taşıma işleminden önce hem `IsBOF` hem de `IsEOF` çağırın. `Open` veya `Requery`çağırdıktan sonra, `IsBOF` ya da `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Bir koşul uygulamadan kayıttan kayda geçmek için `Move` işlevlerini kullanın. Belirli bir koşulu karşılayan bir değişken tür veya anlık görüntü türü kayıt kümesi nesnesinde kayıtları bulmak için bulma işlemlerini kullanın. Tablo türü bir kayıt kümesi nesnesinde bir kaydı bulmak için `Seek`çağırın.

Kayıt kümesi tablo türü bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Geçerli dizini, temel alınan DAO nesnesinin Index özelliğini kullanarak ayarlayabilirsiniz. Geçerli dizini ayarlanmamışsa döndürülen kayıtların sırası tanımsızdır.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu belirli bir kayıt veya geriye doğru bir şekilde taşımak için `Move`çağırın.

İlgili bilgiler için, DAO yardımı 'nda "taşıma yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

##  <a name="moveprev"></a>CDaoRecordset:: Moveöncekini

Kayıt kümesindeki önceki kaydı geçerli kayıt haline getirmek için bu üye işlevi çağırın.

```
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Önceki kayda geçiş yapmayı denemeden önce `IsBOF` çağırmanız önerilir. `MovePrev` çağrısı, `IsBOF` sıfır dışında bir değer döndürürse, ilk kayıttan önce kaydırıldığınız ya da kayıt kümesi tarafından hiçbir kaydın seçilmediğini belirten bir `CDaoException` oluşturur.

> [!CAUTION]
>  `Move` işlevlerden herhangi birini çağırmak, kayıt kümesinde kayıt yoksa bir özel durum oluşturur. Genel olarak, kayıt kümesinde herhangi bir kayıt olup olmadığını anlamak için bir taşıma işleminden önce hem `IsBOF` hem de `IsEOF` çağırın. `Open` veya `Requery`çağırdıktan sonra, `IsBOF` ya da `IsEOF`çağırın.

> [!NOTE]
>  Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerinden herhangi birini çağırırsanız, güncelleştirmeler uyarı vermeden kaybedilir.

Bir koşul uygulamadan kayıttan kayda geçmek için `Move` işlevlerini kullanın. Belirli bir koşulu karşılayan bir değişken tür veya anlık görüntü türü kayıt kümesi nesnesinde kayıtları bulmak için bulma işlemlerini kullanın. Tablo türü bir kayıt kümesi nesnesinde bir kaydı bulmak için `Seek`çağırın.

Kayıt kümesi tablo türü bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Geçerli dizini, temel alınan DAO nesnesinin Index özelliğini kullanarak ayarlayabilirsiniz. Geçerli dizini ayarlanmamışsa döndürülen kayıtların sırası tanımsızdır.

`MoveFirst` veya `MovePrev` üye işlevini yalnızca ileriye doğru bir kayan görüntüyle çağıramezsiniz.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu belirli bir kayıt veya geriye doğru bir şekilde taşımak için `Move`çağırın.

İlgili bilgiler için, DAO yardımı 'nda "taşıma yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

##  <a name="open"></a>CDaoRecordset:: Open

Kayıt kümesine ait kayıtları almak için bu üye işlevini çağırmanız gerekir.

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

- Çift yönlü kaydırma içeren bir değişken türü kayıt kümesi `dbOpenDynaset`. Bu varsayılandır.

- Çift yönlü kaydırma içeren tablo türü bir kayıt kümesi `dbOpenTable`.

- Çift yönlü kaydırma içeren bir anlık görüntü türü kayıt kümesi `dbOpenSnapshot`.

*lpszSQL*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- NULL işaretçi.

- Bir veya daha fazla TableDefs ve/veya QueryDefs (virgülle ayrılmış) adı.

- Bir SQL **Select** deyimi (isteğe bağlı olarak bir SQL **WHERE** veya **ORDERBY** yan tümcesi ile).

- Doğrudan sorgu.

*Önemli seçenekler*<br/>
Aşağıda listelenen seçeneklerden biri veya birkaçı. Varsayılan değer 0’dır. Olası değerler aşağıdaki gibidir:

- `dbAppendOnly` yalnızca yeni kayıtları (yalnızca Dynaset türü kayıt kümesi) ekleyebilirsiniz. Bu seçenek, kayıtların yalnızca eklenebileceği anlamına gelir. MFC ODBC veritabanı sınıfları, kayıtların alınmasına ve eklenmiş olmasına izin veren bir APPEND seçeneği vardır.

- kayıt kümesi, salt ileri kaydırılan bir anlık görüntüdür `dbForwardOnly`.

- `dbSeeChanges` başka bir Kullanıcı düzenlemekte olduğunuz verileri değiştirirken bir özel durum oluşturur.

- `dbDenyWrite` diğer kullanıcılar kayıtları değiştiremez veya ekleyemez.

- `dbDenyRead` diğer kullanıcılar kayıtları görüntüleyemez (yalnızca tablo türü kayıt kümesi).

- `dbReadOnly` kayıtları yalnızca görüntüleyebilirsiniz; diğer kullanıcılar bunları değiştirebilir.

- `dbInconsistent` tutarsız güncelleştirmelere izin verilir (yalnızca Dynaset türü kayıt kümesi).

- Yalnızca tutarlı güncelleştirmelere `dbConsistent` izin verilir (yalnızca Dynaset türü kayıt kümesi).

> [!NOTE]
>  `dbConsistent` ve `dbInconsistent` sabitleri birbirini dışlıyor. Yalnızca belirli bir `Open`örneğinde değil, birini veya diğerini kullanabilirsiniz.

*pTableDef*<br/>
Bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesine yönelik bir işaretçi. Bu sürüm yalnızca tablo türü kayıt kümeleri için geçerlidir. Bu seçenek kullanılırken, `CDaoRecordset` oluşturmak için kullanılan `CDaoDatabase` işaretçisi kullanılmaz; Bunun yerine, TableDef 'in bulunduğu veritabanı kullanılır.

*pQueryDef*<br/>
Bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesine yönelik bir işaretçi. Bu sürüm yalnızca dinamik küme türü ve anlık görüntü türü kayıt kümeleri için geçerlidir. Bu seçenek kullanılırken, `CDaoRecordset` oluşturmak için kullanılan `CDaoDatabase` işaretçisi kullanılmaz; Bunun yerine, QueryDef 'in bulunduğu veritabanı kullanılır.

### <a name="remarks"></a>Açıklamalar

`Open`çağrılmadan önce, kayıt kümesi nesnesi oluşturmanız gerekir. Bunu yapmak için çeşitli yollar vardır:

- Kayıt kümesi nesnesi oluşturduğunuzda, zaten açık olan bir `CDaoDatabase` nesnesine bir işaretçi geçirin.

- Kayıt kümesi nesnesini oluştururken açık olmayan `CDaoDatabase` nesnesine bir işaretçi geçirin. Kayıt kümesi bir `CDaoDatabase` nesnesi açar, ancak kayıt kümesi nesnesi kapandığında bunu kapatmaz.

- Kayıt kümesi nesnesi oluşturduğunuzda, NULL bir işaretçi geçirin. Kayıt kümesi nesnesi, Microsoft Access 'in adını almak için `GetDefaultDBName` çağırır. MDB dosyasını açın. Kayıt kümesi daha sonra bir `CDaoDatabase` nesnesi açar ve kayıt kümesi açık olduğu sürece açık tutar. Kayıt kümesinde `Close` çağırdığınızda `CDaoDatabase` nesnesi de kapatılır.

    > [!NOTE]
    >  Kayıt kümesi `CDaoDatabase` nesnesini açtığında, veri kaynağını özel olmayan erişimle açar.

*LpszSQL* parametresini kullanan `Open` sürümü için, kayıt kümesi açık olduktan sonra kayıtları birkaç şekilde alabilirsiniz. İlk seçenek `DoFieldExchange`DFX işlevleridir. İkinci seçenek `GetFieldValue` üye işlevini çağırarak dinamik bağlama kullanmaktır. Bu seçenekler, ayrı olarak veya birleşimine uygulanabilir. Birleştirilirse, SQL deyiminizi `Open`çağrısında kendiniz geçirmeniz gerekir.

`CDaoTableDef` nesnesini geçirdiğiniz `Open` ikinci sürümünü kullandığınızda, sonuçta elde edilen sütunlar `DoFieldExchange` ve DFX mekanizmasıyla bağlamalısınız ve/veya `GetFieldValue`aracılığıyla dinamik olarak bağlanır.

> [!NOTE]
>  Yalnızca tablo türü kayıt kümeleri için bir `CDaoTableDef` nesnesi kullanarak `Open` çağırabilirsiniz.

`CDaoQueryDef` nesnesini geçirdiğiniz `Open` üçüncü sürümünü kullandığınızda, bu sorgu yürütülür ve elde edilen sütunlar `DoFieldExchange` ve DFX mekanizmasıyla bağlamalısınız ve/veya `GetFieldValue`aracılığıyla dinamik olarak bağlanır.

> [!NOTE]
>  Yalnızca değişken türü ve anlık görüntü türü kayıt kümeleri için bir `CDaoQueryDef` nesnesi kullanarak `Open` çağırabilirsiniz.

`lpszSQL` parametresini kullanan `Open` ilk sürümü için, kayıtlar aşağıdaki tabloda gösterilen ölçütlere göre seçilir.

|`lpszSQL` parametresinin değeri|Seçilen kayıtlar şunları belirler|Örnek|
|--------------------------------------|----------------------------------------|-------------|
|NULL|`GetDefaultSQL`tarafından döndürülen dize.||
|Bir veya daha fazla TableDefs ve/veya QueryDef adının virgülle ayrılmış listesi.|`DoFieldExchange`temsil edilen tüm sütunlar.|`"Customer"`|
|**Tablo listesinden** sütun listesi **seçin**|Belirtilen TableDef ve/veya QueryDef öğeleri için belirtilen sütunlar.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Her zamanki yordam `Open`NULL değer geçirmektir; Bu durumda, `CDaoRecordset`türetilmiş bir sınıf oluşturulurken ClassWizard tarafından oluşturulan geçersiz kılınabilir bir üye işlevi olan `GetDefaultSQL``Open` çağırır. Bu değer, ClassWizard 'da belirttiğiniz TableDef (s) ve/veya QueryDef adlarını verir. Bunun yerine, *lpszSQL* parametresindeki diğer bilgileri belirtebilirsiniz.

Her ne olursa olsun `Open`, sorgu için son bir SQL dizesi (dize, geçirdiğiniz *lpszSQL* DIZESINE eklenen SQL **WHERE** ve **ORDERBY** yan tümceleri olabilir) ve sonra sorguyu yürütür. `Open`çağrıldıktan sonra `GetSQL` çağırarak oluşturulmuş dizeyi inceleyebilirsiniz.

Kayıt kümesi sınıfınızın alan veri üyeleri, seçilen verilerin sütunlarına bağlanır. Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesi için bir filtre veya sıralama gibi seçenekler ayarlamak istiyorsanız, kayıt kümesi nesnesini oluşturduktan sonra, ancak `Open`çağırmadan önce `m_strSort` veya `m_strFilter` ayarlayın. Kayıt kümesi zaten açık olduktan sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız, `Requery`çağırın.

Bir değişken türü veya anlık görüntü türü kayıt kümesinde `Open` çağırırsanız veya veri kaynağı bir SQL ifadesine ya da eklenmiş bir tabloyu temsil eden bir TableDef öğesine başvuruyorsa, tür bağımsız değişkeni için `dbOpenTable` kullanamazsınız; Bunu yaparsanız, MFC bir özel durum oluşturur. Bir TableDef nesnesinin ekli bir tabloyu temsil edip etmediğini anlamak için, bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi oluşturun ve [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevini çağırın.

Aynı kaydı düzenlediğinizde veya silerken başka bir kullanıcı veya makinenizde başka bir program tarafından yapılan değişiklikleri yakalamak istiyorsanız `dbSeeChanges` bayrağını kullanın. Örneğin, iki kullanıcı aynı kaydı düzenlemeyle başlamazsa, `Update` üye işlevini çağıran ilk kullanıcı başarılı olur. `Update` ikinci Kullanıcı tarafından çağrıldığında bir `CDaoException` oluşturulur. Benzer şekilde, ikinci Kullanıcı kaydı silmek için `Delete` çağırmayı dener ve ilk Kullanıcı tarafından zaten değiştirilmişse, bir `CDaoException` oluşur.

Genellikle, Kullanıcı güncelleştirme sırasında bu `CDaoException` alırsa, kodunuzun alanların içeriğini yenilemesi ve yeni değiştirilen değerleri alması gerekir. Özel durum silme sürecinde gerçekleşirse, kodunuz kullanıcıya yeni kayıt verilerini ve verilerin yakın zamanda değiştiğini belirten bir ileti görüntüleyebilir. Bu noktada, kodunuz kullanıcının hala kaydı silmesini istediğini belirten bir onaylama isteğinde bulunabilir.

> [!TIP]
>  Uygulamanız ODBC veri kaynağından açılan bir kayıt kümesinden tek bir geçiş yaptığında performansı artırmak için salt ileri kaydırma seçeneğini (`dbForwardOnly`) kullanın.

İlgili bilgiler için, DAO yardımı 'nda "OpenRecordset yöntemi" konusuna bakın.

##  <a name="requery"></a>CDaoRecordset:: Requery

Bir kayıt kümesini yeniden oluşturmak (yenilemek) için bu üye işlevi çağırın.

```
virtual void Requery();
```

### <a name="remarks"></a>Açıklamalar

Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesinin, sizin veya diğer kullanıcıların veri kaynağına yaptığı eklemeleri ve silmeleri yansıtması için, `Requery`çağırarak kayıt kümesini yeniden oluşturmanız gerekir. Kayıt kümesi bir Dynaset ise, sizin veya diğer kullanıcıların mevcut kayıtları (eklemeler) üzerinde yaptığı güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntüdür, diğer kullanıcıların yanı sıra eklemeleri ve silmeleri yansıtmak için `Requery` çağırmanız gerekir.

DYNASET veya anlık görüntü için, parametre değerlerini kullanarak kayıt kümesini yeniden derlemek istediğiniz zaman `Requery` çağırın. `Requery`çağrılmadan önce [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) ayarlayarak yeni filtre veya sıralama belirleyin. `Requery`çağrılmadan önce parametre veri üyelerine yeni değerler atayarak yeni parametreler ayarlayın.

Kayıt kümesini yeniden derleme girişimi başarısız olursa, kayıt kümesi kapalıdır. `Requery`çağırmadan önce, [CanRestart](#canrestart) üye işlevini çağırarak kayıt kümesinin yeniden sorgulama yapıp kullanamayacağını belirleyebilirsiniz. `CanRestart`, `Requery` başarılı olacağını garanti etmez.

> [!CAUTION]
>  Yalnızca `Open`çağrıldıktan sonra `Requery` çağırın.

> [!NOTE]
>  [YenidenSorgula](#requery) ÇAĞRıSı, DAO yer imlerini değiştirir.

Çağırma `CanRestart` 0 döndürürse veya onu tablo türü bir kayıt kümesinde kullanabileceğiniz bir değişken tür veya anlık görüntü türü kayıt kümesinde `Requery` çağırılamaz.

`Requery`çağırdıktan sonra hem `IsBOF` hem de `IsEOF` sıfır dışında bir değere döndürürse, sorgu hiçbir kayıt döndürmez ve kayıt kümesi hiçbir veri içermeyecektir.

İlgili bilgiler için, DAO yardımı 'nda "YenidenSorgula yöntemi" konusuna bakın.

##  <a name="seek"></a>CDaoRecordset:: Seek

Geçerli dizin için belirtilen ölçütlere uyan bir dizinli tablo türü kayıt kümesi nesnesinde kaydı bulmak için bu üye işlevini çağırın ve bu kaydı geçerli kayıt yapar.

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
Şu dize ifadelerinden biri: "<", "\<=", "=", "> =" veya ">".

*pKey1*<br/>
Değeri dizindeki ilk alana karşılık gelen bir [Cotavariant](../../mfc/reference/colevariant-class.md) işaretçisi. Gereklidir.

*pKey2*<br/>
Değeri dizinde ikinci alana karşılık gelen bir `COleVariant` işaretçisi (varsa). Varsayılan olarak NULL değerini alır.

*pKey3*<br/>
Değeri dizinde üçüncü alana karşılık gelen bir `COleVariant` işaretçisi (varsa). Varsayılan olarak NULL değerini alır.

*pKeyArray*<br/>
Bir çeşit dizisine yönelik bir işaretçi. Dizi boyutu, dizindeki alan sayısına karşılık gelir.

*nKeys 'ler*<br/>
Dizinin boyutuna karşılık gelen ve dizindeki alanların sayısı olan bir tamsayı.

> [!NOTE]
>  Anahtarlarda joker karakter belirtmeyin. Joker karakterler `Seek` eşleşen kayıtlar döndürmesine neden olur.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır değilse 0.

### <a name="remarks"></a>Açıklamalar

Dört alan dizinini veya daha fazlasını işlemek için `Seek` ikinci (dizi) sürümünü kullanın.

`Seek` tablo türü kayıt kümelerinde yüksek performanslı Dizin aramayı mümkün. `Seek`çağrılmadan önce `SetCurrentIndex` çağırarak geçerli dizini ayarlamanız gerekir. Dizin, benzersiz olmayan bir anahtar alanı veya alanı tanımlarsa, ölçütleri karşılayan ilk kaydı bulur `Seek`. Bir dizin ayarlanmamışsa, bir özel durum oluşturulur.

Bir UNICODE kayıt kümesi oluşturmadıysanız, `COleVariant` nesnelerinin açıkça ANSI olarak bildirilmesini gerektiğini unutmayın. Bu işlem, *vtSrc* 'nin `VT_BSTRT` (ANSI) olarak ayarlandığı **ya da `COleVariant`** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszSrc* **,** *vtSrc* **)** *ile birlikte `VT_BSTRT`olarak ayarlanmış bir* Oluşturucu olan [cotavaryant:: copavariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc*

`Seek`çağırdığınızda bir veya daha fazla anahtar değeri ve bir karşılaştırma işleci ("<", "\<=", "=", "> =" veya ">") geçirin. `Seek`, belirtilen anahtar alanlarında arama yapar ve *lpszComparison* ve *pKey1*tarafından belirtilen ölçütlere uyan ilk kaydı bulur. `Seek`, sıfır dışında bir değer döndürür ve bu kaydı geçerli hale getirir. `Seek` eşleşme bulamazsa, `Seek` sıfır döndürür ve geçerli kayıt tanımsızdır. Doğrudan DAO kullanırken NoMatch özelliğini açıkça denetlemeniz gerekir.

`lpszComparison` "=", "> =" veya ">" ise, `Seek` dizinin başlangıcında başlatılır. *LpszComparison* "<" veya "< =" ise, `Seek` dizinin sonunda başlar ve sonunda yinelenen dizin girişleri olmadıkça geriye doğru arar. Bu durumda `Seek` Dizin sonundaki yinelenen dizin girişleri arasında rastgele bir girdiyle başlar.

`Seek`kullandığınızda geçerli bir kayıt olması gerekmez.

Belirli bir koşulu karşılayan bir değişken türü veya anlık görüntü türü kayıt kümesindeki bir kaydı bulmak için bulma işlemlerini kullanın. Yalnızca belirli bir koşulu karşılayan olanları değil, tüm kayıtları dahil etmek için, kayıttan kayda geçmek için taşıma işlemlerini kullanın.

Eklenmiş tabloların değişken tür veya anlık görüntü türü kayıt kümeleri olarak açılması gerektiğinden, herhangi bir türdeki ekli tabloda `Seek` çağırılamaz. Ancak, yüklenebilir bir ISAM veritabanını doğrudan açmak için `CDaoDatabase::Open` çağırırsanız, bu veritabanındaki tablolarda `Seek` çağırabilirsiniz, ancak performans yavaş olabilir.

İlgili bilgiler için, DAO yardımı 'nda "arama yöntemi" konusuna bakın.

##  <a name="setabsoluteposition"></a>CDaoRecordset:: SetAbsolutePosition

Bir kayıt kümesi nesnesinin geçerli kaydının göreli kayıt numarasını ayarlar.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Parametreler

*lPosition*<br/>
Kayıt kümesindeki geçerli kaydın sıra konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

`SetAbsolutePosition` çağırmak, geçerli kayıt işaretçisini, küme türü veya anlık görüntü türü bir kayıt kümesindeki sıra konumuna göre belirli bir kayda konumlandırabilmenizi sağlar. Ayrıca, [GetAbsolutePosition](#getabsoluteposition)' i çağırarak geçerli kayıt numarasını belirleyebilirsiniz.

> [!NOTE]
>  Bu üye işlevi yalnızca dinamik küme türü ve anlık görüntü türü kayıt kümeleri için geçerlidir.

Temel alınan DAO nesnesinin AbsolutePosition özelliği değeri sıfır tabanlıdır; 0 ayarı, kayıt kümesindeki ilk kayda başvurur. Doldurulmuş kayıt sayısından daha büyük bir değer ayarlandığında MFC 'nin bir özel durum oluşturması neden olur. `GetRecordCount` üye işlevini çağırarak, kayıt kümesindeki doldurulmuş kayıt sayısını belirleyebilirsiniz.

Geçerli kayıt silinirse, AbsolutePosition özelliği değeri tanımlı değildir ve başvuru varsa MFC bir özel durum oluşturur. Yeni kayıtlar sıranın sonuna eklenir.

> [!NOTE]
>  Bu özellik, bir vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri hala, belirli bir konuma devam etmek ve döndürmek için önerilen bir yoldur ve geçerli kaydı, yer işaretlerini destekleyen tüm kayıt kümesi nesnesi türlerinde konumlandırın tek yoludur. Özellikle, belirli bir kaydın konumu, kendisinden önceki kayıtlar silindikten sonra değişir. Ayrıca, bir kayıt kümesi içindeki tek kayıtların sırası bir **ORDERBY** yan TÜMCESI kullanılarak SQL deyimi ile oluşturulmadığı müddetçe, belirli bir kaydın aynı mutlak konuma sahip olacağı bir güvence yoktur.

İlgili bilgiler için, DAO yardımı 'nda "AbsolutePosition özelliği" konusuna bakın.

##  <a name="setbookmark"></a>CDaoRecordset:: SetBookmark

Kayıt kümesini belirtilen yer işaretini içeren kayıtta konumlandırmak için bu üye işlevini çağırın.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Belirli bir kayıt için yer işareti değerini içeren [Cotavariant](../../mfc/reference/colevariant-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, kayıtlarının her birinin zaten benzersiz bir yer işareti vardır. `GetBookmark` çağırarak ve değeri bir `COleVariant` nesnesine kaydederek geçerli kayıt için yer işaretini alabilirsiniz. Daha sonra, kaydedilen yer işareti değerini kullanarak `SetBookmark` çağırarak bu kayda geri dönebilirsiniz.

> [!NOTE]
>  [YenidenSorgula](#requery) ÇAĞRıSı, DAO yer imlerini değiştirir.

Bir UNICODE kayıt kümesi oluşturmadıysanız, `COleVariant` nesnesinin açıkça ANSI olarak bildirilmesini gerektiğini unutmayın. Bu işlem, *vtSrc* 'nin `VT_BSTRT` (ANSI) olarak ayarlandığı **ya da `COleVariant`** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszSrc* **,** *vtSrc* **)** *ile birlikte `VT_BSTRT`olarak ayarlanmış bir* Oluşturucu olan [cotavaryant:: copavariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc*

İlgili bilgiler için, DAO yardımı 'nda "yer Işareti özelliği" ve Bookmarkable özelliği "konularına bakın.

##  <a name="setcachesize"></a>CDaoRecordset:: SetCacheSize

Önbelleğe alınacak kayıt sayısını ayarlamak için bu üye işlevini çağırın.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Parametreler

*lSize dili*<br/>
Kayıt sayısını belirtir. Tipik bir değer 100 ' dir. 0 ayarı önbelleğe almayı kapatır. Ayar 5 ile 1200 kayıt arasında olmalıdır. Önbellek, önemli miktarda bellek kullanabilir.

### <a name="remarks"></a>Açıklamalar

Önbellek, uygulama çalışırken verilerin yeniden istenmesi durumunda sunucudan en son alınan verileri tutan yerel bellekteki bir alandır. Veri önbelleğe alma, dinamik bir sunucudan verileri alan ve değişken türü kayıt kümesi nesneleri aracılığıyla bir uygulamanın performansını geliştirir. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, verileri sunucudan almak yerine önce istenen verilerin önbelleğini denetler, bu da daha fazla zaman alır. ODBC veri kaynağından gelmeyen veriler önbellekte kaydedilmez.

Ekli tablo gibi tüm ODBC veri kaynakları yerel bir önbelleğe sahip olabilir. Önbellek oluşturmak için, uzak veri kaynağından bir kayıt kümesi nesnesi açın, `SetCacheSize` ve `SetCacheStart` üye işlevlerini çağırın, sonra `FillCache` üye işlevini çağırın veya taşıma işlemlerinden birini kullanarak kayıtlarda gezinin. `SetCacheSize` member işlevinin *lSize* parametresi, uygulamanızın tek seferde üzerinde çalıştığı kayıt sayısına bağlı olabilir. Örneğin, ekranda görüntülenecek verilerin kaynağı olarak bir kayıt kümesi kullanıyorsanız, 20 kaydı tek seferde göstermek için `SetCacheSize` *lSize* parametresini 20 olarak geçirebilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "CacheSize, CacheStart özellikleri" konusuna bakın.

##  <a name="setcachestart"></a>CDaoRecordset:: SetCacheStart

Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirtmek için bu üye işlevini çağırın.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir [Cotavariant](../../mfc/reference/colevariant-class.md) .

### <a name="remarks"></a>Açıklamalar

`SetCacheStart` member işlevinin *varBookmark* parametresi için herhangi bir kaydın yer işareti değerini kullanabilirsiniz. Önbelleği geçerli kayıt ile başlatmak istediğiniz kaydı yapın, [SetBookmark](#setbookmark)kullanarak bu kayıt için bir yer işareti oluşturun ve bookmark değerini `SetCacheStart` member işlevinin parametresi olarak geçirin.

Microsoft Jet veritabanı altyapısı, önbellekten önbellek aralığı içinde kayıt ister ve sunucudan önbellek aralığı dışında kayıtlar ister.

Önbellekten alınan kayıtlar, diğer kullanıcılar tarafından kaynak verilerde aynı anda yapılan değişiklikleri yansıtmaz.

Önbelleğe alınmış tüm verilerin güncelleştirilmesini zorlamak için, `SetCacheSize` *lSize* parametresini 0 olarak geçirin, ilk olarak istediğiniz önbelleğin boyutuyla yeniden `SetCacheSize` çağırın ve ardından `FillCache` üye işlevini çağırın.

Bir UNICODE kayıt kümesi oluşturmadıysanız, `COleVariant` nesnesinin açıkça ANSI olarak bildirilmesini gerektiğini unutmayın. Bu işlem, *vtSrc* 'nin `VT_BSTRT` (ANSI) olarak ayarlandığı **ya da `COleVariant`** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszSrc* **,** *vtSrc* **)** *ile birlikte `VT_BSTRT`olarak ayarlanmış bir* Oluşturucu olan [cotavaryant:: copavariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc*

İlgili bilgiler için, DAO yardımı 'nda CacheSize, CacheStart özellikleri "konusuna bakın.

##  <a name="setcurrentindex"></a>CDaoRecordset:: SetCurrentIndex

Tablo türü bir kayıt kümesinde bir dizin ayarlamak için bu üye işlevini çağırın.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
Ayarlanacak dizinin adını içeren bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel tablolardaki kayıtlar belirli bir sırada depolanmaz. Bir dizin ayarlandığında, veritabanından döndürülen kayıtların sırası değişir, ancak kayıtların depolandığı sırayı etkilemez. Belirtilen dizin zaten tanımlanmış olmalıdır. Varolmayan bir dizin nesnesi kullanmayı denerseniz veya [arama](#seek)çağrısı yaptığınızda Dizin ayarlanmamışsa, MFC bir özel durum oluşturur.

[CDaoTableDef:: CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) ' i çağırarak ve sonra, [CDaoTableDef:: Append](../../mfc/reference/cdaotabledef-class.md#append)öğesini çağırarak ve sonra kayıt kümesini yeniden açarak temel alınan TableDef 'in Indexes koleksiyonuna yeni dizin ekleyerek tablo için yeni bir dizin oluşturabilirsiniz.

Tablo türü bir kayıt kümesinden döndürülen kayıtlar yalnızca temel alınan TableDef için tanımlanan dizinlerde sıralanabilir. Kayıtları başka bir sırada sıralamak için, [CDaoRecordset:: m_strSort](#m_strsort)içinde depolanan bir SQL **ORDERBY** yan tümcesini kullanarak değişken türü veya anlık görüntü türü bir kayıt kümesi açabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "Dizin nesnesi" ve tanım "geçerli dizin" konusuna bakın.

##  <a name="setfielddirty"></a>CDaoRecordset:: SetFieldDirty

Kayıt kümesinin alan veri üyesini değiştirilmiş veya değiştirilmemiş olarak işaretlemek için bu üye işlevini çağırın.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Kayıt kümesindeki bir alan veri üyesinin adresini veya NULL değerini içerir. NULL ise, kayıt kümesindeki tüm alan verisi üyeleri işaretlenir. (C++ Null, Veritabanı terminolojisinde null ile aynı değildir, yani "hiçbir değer yok" anlamına gelir.)

*bDirty*<br/>
Alan veri üyesi "kirli" (değiştirilmiş) olarak işaretlenmek için TRUE. Aksi takdirde, alan veri üyesi "temiz" (değiştirilmemiş) olarak işaretlenmek için FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değiştirilmemiş olarak işaretlemek alanın güncelleştirilmesini sağlar.

Çerçeve, veri kaynağındaki kayda DAO Kayıt alanı değişimi (DFX) mekanizması tarafından yazıldıklarından emin olmak için alan veri üyelerini işaretler. Bir alanın değerini değiştirmek genellikle alanı kirli olarak ayarlar. bu nedenle, nadiren `SetFieldDirty` çağırmanız gerekir, ancak bazen, alan veri üyesinde hangi değerin olduğuna bakılmaksızın sütunların açıkça güncelleştirilmesini veya eklenmesini sağlamak isteyebilirsiniz. DFX mekanizması, sözde kullanım kullanımını da kullanır. Daha fazla bilgi için bkz. [Cdadofieldexchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamamaktadır. Bu durumda, alanı açıkça kirli olarak ayarlamanız gerekir. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) bulunan bayrak, bu otomatik alan denetimini denetler.

> [!NOTE]
>  Yalnızca [Edit](#edit) veya [AddNew](#addnew)çağrıldıktan sonra bu üye işlevini çağırın.

İşlevin ilk bağımsız değişkeni için NULL kullanmak, işlevi, `CDaoFieldExchange`**param** alanlarını değil, tüm `outputColumn` alanlarına uygular. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

yalnızca `outputColumn` alanlarını NULL olarak ayarlar; **param** alanları etkilenmeyecektir.

Bir **param**üzerinde çalışmak için, çalışmak istediğiniz bağımsız **param** 'ın gerçek adresini sağlamanız gerekir, örneğin:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Bu, `outputColumn` alanları sayesinde, tüm **param** alanlarını null olarak ayarlayamayacağı anlamına gelir.

`SetFieldDirty`, `DoFieldExchange`ile uygulanır.

##  <a name="setfieldnull"></a>CDaoRecordset:: SetFieldNull

Kayıt kümesinin alan veri üyesini null (özellikle değer olmadan) veya null olmayan olarak işaretlemek için bu üye işlevini çağırın.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*bakın*<br/>
Kayıt kümesindeki bir alan veri üyesinin adresini veya NULL değerini içerir. NULL ise, kayıt kümesindeki tüm alan verisi üyeleri işaretlenir. (C++ Null, Veritabanı terminolojisinde null ile aynı değildir, yani "hiçbir değer yok" anlamına gelir.)

*bNull*<br/>
Alan verisi üyesinin değer yok (null) olarak işaretlenmek için sıfır dışında. Aksi takdirde 0 alan verisi üyesi null olarak işaretlenir.

### <a name="remarks"></a>Açıklamalar

`SetFieldNull`, `DoFieldExchange` mekanizmasında bağlantılı alanlar için kullanılır.

Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta null değere ayarlanır ve "kirli" (değiştirildi) olarak işaretlenir. Bir veri kaynağından bir kayıt aldığınızda, sütunlarının değerleri zaten var ya da null. Alanı null yapmak için uygun değilse, bir [CDaoException](../../mfc/reference/cdaoexception-class.md) oluşturulur.

Çift arabelleğe alma mekanizması kullanıyorsanız, örneğin, özellikle geçerli kaydın bir alanını bir değer içermeyecek şekilde atamak istiyorsanız, null olarak işaretlemek için *bNull* değeri true olarak ayarlandığında `SetFieldNull` çağırın. Bir alan önceden null olarak işaretlenmişse ve bundan böyle bir değer vermek istiyorsanız, yeni değerini ayarlamanız yeterlidir. Null bayrağını `SetFieldNull`kaldırmak zorunda değilsiniz. Alanın null olmasına izin verilip verilmeyeceğini anlamak için, [Isfieldnullenebilir](#isfieldnullable)çağırın.

Çift arabelleğe alma mekanizmasını kullanmıyorsanız, alanın değerini değiştirmek alanı kirli ve null olmayan şekilde otomatik olarak ayarlar. Yalnızca Dirty ve null olmayan alanları ayarlamanız gerekir. [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) bulunan bayrak, bu otomatik alan denetimini denetler.

DFX mekanizması, sözde kullanım kullanımını kullanır. Daha fazla bilgi için bkz. [Cdadofieldexchange:: m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
>  Yalnızca [Edit](#edit) veya [AddNew](#addnew)çağrıldıktan sonra bu üye işlevini çağırın.

İşlevin ilk bağımsız değişkeni için NULL kullanmak, işlevi yalnızca `outputColumn` alanlara uygular, bu, `CDaoFieldExchange`**param** alanları değildir. Örneğin, çağrı

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

yalnızca `outputColumn` alanlarını NULL olarak ayarlar; **param** alanları etkilenmeyecektir.

##  <a name="setfieldvalue"></a>CDaoRecordset:: SetFieldValue

Bir alanın değerini sıra konumuna göre veya dizenin değerini değiştirerek ayarlamak için bu üye işlevini çağırın.

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
Alan içeriğinin değerini içeren bir [Cotavariant](../../mfc/reference/colevariant-class.md) nesnesine başvuru.

*nDizin*<br/>
Kayıt kümesinin Fields koleksiyonundaki (sıfır tabanlı) alanın sıra konumunu temsil eden bir tamsayı.

*lpszValue*<br/>
Alan içeriğinin değerini içeren bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

[DoFieldExchange](#dofieldexchange) mekanizmasını kullanarak sütunları statik olarak bağlama yerine çalışma zamanında dinamik olarak bağlamak için `SetFieldValue` ve [GetFieldValue](#getfieldvalue) kullanın.

Bir UNICODE kayıt kümesi oluşturmadıysanız, bir `COleVariant` parametresi içermeyen `SetFieldValue` bir form kullanmanız gerektiğini veya `COleVariant` nesnesinin açıkça ANSI olarak bildirilmesini gerektiğini unutmayın. Bu işlem, *vtSrc* 'nin `VT_BSTRT` (ANSI) olarak ayarlandığı **ya da `COleVariant`** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszSrc* **,** *vtSrc* **)** *ile birlikte `VT_BSTRT`olarak ayarlanmış bir* Oluşturucu olan [cotavaryant:: copavariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc*

İlgili bilgiler için, DAO yardımı 'nda "alan nesnesi" ve "değer özelliği" konularına bakın.

##  <a name="setfieldvaluenull"></a>CDaoRecordset:: SetFieldValueNull

Alanı boş bir değere ayarlamak için bu üye işlevini çağırın.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Sıfır tabanlı dizine göre arama için kayıt kümesindeki alanın dizini.

*lpszName*<br/>
Ada göre arama için, kayıt kümesindeki alanın adı.

### <a name="remarks"></a>Açıklamalar

C++NULL, Veritabanı terminolojisinde "değer olmadan" anlamına gelen null ile aynı değildir.

İlgili bilgiler için, DAO yardımı 'nda "alan nesnesi" ve "değer özelliği" konularına bakın.

##  <a name="setlockingmode"></a>CDaoRecordset:: SetLockingMode

Kayıt kümesine yönelik kilitleme türünü ayarlamak için bu üye işlevi çağırın.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Parametreler

*Bkötümser*<br/>
Kilitleme türünü gösteren bir bayrak.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme etkin olduğunda, `Edit` üye işlevini çağırdığınızda, düzenlemekte olduğunuz kaydı içeren 2K sayfası kilitlenir. `Update` veya `Close` üye işlevini veya taşıma ya da bulma işlemlerinden birini çağırdığınızda sayfanın kilidi açılır.

İyimser kilitleme etkin olduğunda, kaydı içeren 2K sayfası yalnızca kayıt `Update` üye işleviyle güncelleştirilirken kilitlenir.

Bir sayfa kilitliyse, başka hiçbir Kullanıcı kayıtları aynı sayfada düzenleyemez. `SetLockingMode` çağırır ve sıfır dışında bir değer geçirirseniz ve başka bir kullanıcı zaten sayfayı kilitlediyseniz, `Edit`çağırdığınızda bir özel durum oluşturulur. Diğer kullanıcılar, kilitli sayfalardan verileri okuyabilir.

Sıfır değeri olan `SetLockingMode` çağırırsanız ve daha sonra `Update` çağrı, sayfa başka bir kullanıcı tarafından kilitliyken, bir özel durum oluşur. Kayıt sırasında başka bir kullanıcı tarafından yapılan değişiklikleri görmek için (ve değişikliklerinizi kaybetmek), `SetBookmark` üye işlevini geçerli kaydın yer işareti değeriyle çağırın.

ODBC veri kaynaklarıyla çalışırken kilitleme modu her zaman iyimser olur.

##  <a name="setparamvalue"></a>CDaoRecordset:: SetParamValue

Çalışma zamanında kayıt kümesindeki bir parametrenin değerini ayarlamak için bu üye işlevini çağırın.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
QueryDef 'in Parameters koleksiyonundaki parametrenin sayısal konumu.

*var*<br/>
Ayarlanacak değer; bkz. açıklamalar.

*lpszName*<br/>
Değerini ayarlamak istediğiniz parametrenin adı.

### <a name="remarks"></a>Açıklamalar

Parametrenin, kayıt kümesinin SQL dizesinin parçası olarak zaten oluşturulmuş olması gerekir. Parametreye adına veya koleksiyondaki dizin konumuna göre erişebilirsiniz.

`COleVariant` nesne olarak ayarlanacak değeri belirtin. `COleVariant` nesneniz için istenen değeri ve türü ayarlama hakkında daha fazla bilgi için bkz. sınıf [Cotavariant](../../mfc/reference/colevariant-class.md). Bir UNICODE kayıt kümesi oluşturmadıysanız, `COleVariant` nesnesinin açıkça ANSI olarak bildirilmesini gerektiğini unutmayın. Bu işlem, *vtSrc* 'nin `VT_BSTRT` (ANSI) olarak ayarlandığı **ya da `COleVariant`** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring) **(** *lpszSrc* **,** *vtSrc* **)** *ile birlikte `VT_BSTRT`olarak ayarlanmış bir* Oluşturucu olan [cotavaryant:: copavariant](../../mfc/reference/colevariant-class.md#colevariant) **(** *lpszSrc*

##  <a name="setparamvaluenull"></a>CDaoRecordset:: SetParamValueNull

Parametreyi null değere ayarlamak için bu üye işlevi çağırın.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Sıfır tabanlı dizine göre arama için kayıt kümesindeki alanın dizini.

*lpszName*<br/>
Ada göre arama için, kayıt kümesindeki alanın adı.

### <a name="remarks"></a>Açıklamalar

C++NULL, Veritabanı terminolojisinde "değer olmadan" anlamına gelen null ile aynı değildir.

##  <a name="setpercentposition"></a>CDaoRecordset:: SetPercentPosition

Kayıt kümesindeki kayıtların yüzdesine göre kayıt kümesi nesnesindeki geçerli kaydın yaklaşık konumunu değiştiren bir değer ayarlamak için bu üye işlevini çağırın.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Parametreler

*fPosition*<br/>
0 ile 100 arasında bir sayı.

### <a name="remarks"></a>Açıklamalar

DYNASET türü veya anlık görüntü türü bir kayıt kümesiyle çalışırken, önce `SetPercentPosition`çağırmadan önce son kayda geçerek kayıt kümesini doldurun. Kayıt kümesini tamamen doldurmadan önce `SetPercentPosition` çağırırsanız, hareket miktarı [GetRecordCount](#getrecordcount)değeri tarafından belirtilen şekilde erişilen kayıt sayısına göre değişir. `MoveLast`çağırarak son kayda geçebilirsiniz.

`SetPercentPosition`çağırdıktan sonra, bu değere karşılık gelen yaklaşık konumdaki kayıt geçerli olur.

> [!NOTE]
>  Geçerli kaydı bir kayıt kümesindeki belirli bir kayda taşımak için `SetPercentPosition` çağrısı yapmanız önerilmez. Bunun yerine [SetBookmark](#setbookmark) üye işlevini çağırın.

İlgili bilgiler için, DAO yardımı 'nda "PercentPosition Özelliği" konusuna bakın.

##  <a name="update"></a>CDaoRecordset:: Update

`AddNew` veya `Edit` member işlevine yapılan çağrıdan sonra bu üye işlevini çağırın.

```
virtual void Update();
```

### <a name="remarks"></a>Açıklamalar

`AddNew` veya `Edit` işleminin tamamlanabilmesi için bu çağrı gereklidir.

Hem `AddNew` hem de `Edit` veri kaynağına kaydetmek için eklenen veya düzenlenen verilerin yerleştirildiği bir düzenleme arabelleği hazırlayın. `Update` verileri kaydeder. Yalnızca değiştirilen veya değiştirilmiş olarak algılanan alanlar güncelleştirilir.

Veri kaynağı işlemleri destekliyorsa, `Update` çağrısını (ve buna karşılık gelen `AddNew` veya `Edit` çağrısını) bir işlemin parçası yapabilirsiniz.

> [!CAUTION]
> Önce `AddNew` veya `Edit`çağırılmadan `Update` çağırırsanız `Update` bir `CDaoException`oluşturur. `AddNew` veya `Edit`çağırırsanız, [MoveNext](#movenext) 'i çağırmadan önce `Update` çağırmanız veya kayıt kümesini ya da veri kaynağı bağlantısını kapatmanız gerekir. Aksi takdirde, değişiklikleriniz bildirim olmadan kaybedilir.

Bir çok kullanıcılı ortamda pessimistically kayıt kümesi nesnesi kilitlendiğinde, güncelleştirme tamamlanana kadar `Edit`, kayıt zaman kilitli kalır. Kayıt kümesi optimizasyonu bir şekilde kilitliyse, kayıt kilitlenir ve veritabanında güncelleştirildikten hemen önce önceden düzenlenen kayıtla karşılaştırılır. `Edit`çağrıldıktan sonra kayıt değiştiyse, `Update` işlemi başarısız olur ve MFC bir özel durum oluşturur. Kilitleme modunu `SetLockingMode`değiştirebilirsiniz.

> [!NOTE]
> İyimser kilitleme, ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimlerinde her zaman kullanılır.

İlgili bilgiler için, DAO yardımı 'nda "AddNew yöntemi", "CancelUpdate Yöntemi", "Delete yöntemi", "LastModified özelliği", "güncelleştirme yöntemi" ve "EditMode özelliği" konularına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace Sınıfı](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
