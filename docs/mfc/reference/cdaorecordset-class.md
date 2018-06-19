---
title: CDaoRecordset sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 603cd1658af417dfbb7f2d8aa8022275e866a706
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378910"
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
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Oluşturan bir `CDaoRecordset` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoRecordset::AddNew](#addnew)|Yeni bir kayıt eklemek için hazırlar. Çağrı [güncelleştirme](#update) eklenmesi tamamlamak için.|  
|[CDaoRecordset::CanAppend](#canappend)|Yeni kayıtlar kayıt kümesine eklenebilir, sıfır olmayan döndürür [AddNew](#addnew) üye işlevi.|  
|[CDaoRecordset::CanBookmark](#canbookmark)|Yer işaretleri kayıt destekliyorsa, sıfır olmayan bir değer döndürür.|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Tüm bekleyen güncelleştirmeleri nedeniyle iptal eder bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi.|  
|[CDaoRecordset::CanRestart](#canrestart)|Döndürür sıfır olmayan IF [Requery](#requery) kümesinin sorguyu yeniden çalıştırmak için çağrılır.|  
|[CDaoRecordset::CanScroll](#canscroll)|Kayıtlarda kaydırırsanız, sıfır olmayan bir değer döndürür.|  
|[CDaoRecordset::CanTransact](#cantransact)|Veri kaynağı işlemleri destekliyorsa sıfır olmayan döndürür.|  
|[CDaoRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilmiş sıfır olmayan döndürür (ekleyebilir, güncelleştirme veya kayıtlarını sil).|  
|[CDaoRecordset::Close](#close)|Kayıt kümesi kapatır.|  
|[CDaoRecordset::Delete](#delete)|Geçerli kayıt kayıt kümesinden siler. Açıkça silindikten sonra başka bir kayıtla kaydırma gerekir.|  
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Kayıt kümesi alan veri üyeleri ve ilgili kaydı veri kaynağında arasında (her iki yönde) veri değişimi için çağrılır. Implements DAO alanı değişimi (DFX) kaydedin.|  
|[CDaoRecordset::Edit](#edit)|Değişiklikler geçerli kayıt için hazırlar. Çağrı **güncelleştirme** düzenlemeyi tamamlamak için.|  
|[CDaoRecordset::FillCache](#fillcache)|Tüm dolgular veya bir ODBC veri kaynağından alınan veriler içeren bir kayıt kümesi nesnesi için yerel önbellek parçası.|  
|[CDaoRecordset::Find](#find)|İlk olarak, sonraki bulur geçerli kaydıyla yapar ve belirtilen ölçütleri karşılayan dynaset türü kümesinde belirli bir dizenin önceki ya da son konum.|  
|[CDaoRecordset::FindFirst](#findfirst)|İlk kaydı dynaset türü ya da geçerli kaydıyla yapar ve belirtilen ölçütleri karşılayan anlık görüntü türündeki kayıt kümesi bulur.|  
|[CDaoRecordset::FindLast](#findlast)|Son kayda dynaset türü ya da geçerli kaydıyla yapar ve belirtilen ölçütleri karşılayan anlık görüntü türündeki kayıt kümesi bulur.|  
|[CDaoRecordset::FindNext](#findnext)|Sonraki kaydı dynaset türü ya da geçerli kaydıyla yapar ve belirtilen ölçütleri karşılayan anlık görüntü türündeki kayıt kümesi bulur.|  
|[CDaoRecordset::FindPrev](#findprev)|Önceki kaydın dynaset türü ya da geçerli kaydıyla yapar ve belirtilen ölçütleri karşılayan anlık görüntü türündeki kayıt kümesi bulur.|  
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını döndürür.|  
|[CDaoRecordset::GetBookmark](#getbookmark)|Yer işareti bir kayıtta temsil eden bir değer döndürür.|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken küme türü kayıt kümesindeki kayıt sayısını belirten bir değer döndürür.|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|Önbelleğe alınacak kayıt kümesinde yer ilk kaydının belirten bir değer döndürür.|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Döndürür bir `CString` dizinin adını içeren en son kullanılan üzerinde oluşturulmuş, bir tablo türü `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Temel tablo arka plandaki tarihi ve saati döndürür bir `CDaoRecordset` nesnesi oluşturuldu|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Tarih ve saat temel temel tablo tasarımı için yapılan en son değişikliğin döndürür bir `CDaoRecordset` nesnesi.|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Varsayılan veri kaynağının adını döndürür.|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Varsayılan SQL dizesi yürütülemedi almak için çağrılır.|  
|[CDaoRecordset::GetEditMode](#geteditmode)|Geçerli kaydı için düzenleme durumunu gösteren bir değer döndürür.|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Bir kayıt kümesindeki alan sayısını temsil eden bir değer döndürür.|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Kayıt kümesinde belirli tür alanları hakkında bilgi döndürür.|  
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Kayıt kümesinde bir alanın değerini döndürür.|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|Bir kayıt temel tablodaki dizinler sayısını alır.|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Çeşitli dizin hakkında bilgi döndürür.|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|En son eklenen veya kayıt güncelleştirildiği belirlemek için kullanılır.|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Düzenleme sırasında yürürlükte olan kilitleme türünü belirten bir değer döndürür.|  
|[CDaoRecordset::GetName](#getname)|Döndürür bir `CString` kayıt kümesi adını içeren.|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|Temel alınan DAOParameter nesnesindeki belirtilen parametresinin geçerli değeri alır.|  
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Geçerli kayıt konumu kayıtlarının toplam sayısı yüzdesi olarak döndürür.|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Bir kayıt kümesi nesnesi erişilen kayıt sayısını döndürür.|  
|[CDaoRecordset::GetSQL](#getsql)|Kayıt kümesi kayıtları seçmek için kullanılan SQL dizesini alır.|  
|[CDaoRecordset::GetType](#gettype)|Bir kayıt türü belirlemek üzere çağrılır: Tablo türü, dinamik küme türünde veya anlık görüntü türü.|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Döndürür bir `CString` alana girilen gibi verileri doğrulama değerini içeren.|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Bir doğrulama kuralı sağlanmıyorsa zaman görüntülenen metni alır.|  
|[CDaoRecordset::IsBOF](#isbof)|Kayıt kümesi önce ilk kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.|  
|[CDaoRecordset::IsDeleted](#isdeleted)|Kayıt kümesi silinmiş bir kayda konumlandırıldı sıfır olmayan döndürür.|  
|[CDaoRecordset::IsEOF](#iseof)|Kayıt kümesi sonra son kayda konumlandırıldı sıfır olmayan döndürür. Geçerli kayıt yok.|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Geçerli kayıttaki belirtilen alanın değiştirdiyseniz sıfır olmayan bir değer döndürür.|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıttaki belirtilen alanın Null (hiçbir değer sahip) ise sıfır olmayan bir değer döndürür.|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Geçerli kayıttaki belirtilen alanın Null (hiçbir değer sahip) ayarlanabiliyorsa sıfır olmayan bir değer döndürür.|  
|[CDaoRecordset::IsOpen](#isopen)|Döndürür sıfır olmayan IF [açık](#open) daha önce çağrılır.|  
|[CDaoRecordset::Move](#move)|Kayıt kümesi belirli bir kayıt sayısı için her iki yönde geçerli kayıttaki yerleştirir.|  
|[CDaoRecordset::MoveFirst](#movefirst)|İlk kaydı kayıt kümesindeki geçerli kayıt yerleştirir.|  
|[CDaoRecordset::MoveLast](#movelast)|Son kaydı kayıt kümesindeki geçerli kayıt yerleştirir.|  
|[CDaoRecordset::MoveNext](#movenext)|Sonraki kaydı kayıt kümesindeki geçerli kayıt yerleştirir.|  
|[CDaoRecordset::MovePrev](#moveprev)|Önceki kaydı kayıt kümesindeki geçerli kayıt yerleştirir.|  
|[CDaoRecordset::Open](#open)|Yeni bir kayıt tablosu, dynaset veya anlık görüntü oluşturur.|  
|[CDaoRecordset::Requery](#requery)|Seçili kayıtları yeniden yenilemek için kümesinin sorgusunu çalıştırır.|  
|[CDaoRecordset::Seek](#seek)|Geçerli kayıt kaydı yapar ve geçerli dizin için belirtilen ölçütleri karşılayan bir dizinlenmiş tablo türü kayıt kümesi nesnesinde kaydı bulur.|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını ayarlar.|  
|[CDaoRecordset::SetBookmark](#setbookmark)|Kayıt kümesi belirtilen yer işareti içeren bir kayda yerleştirir.|  
|[CDaoRecordset::SetCacheSize](#setcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken küme türü kayıt kümesindeki kayıt sayısını belirten bir değer ayarlar.|  
|[CDaoRecordset::SetCacheStart](#setcachestart)|Önbelleğe alınacak kayıt kümesinde yer ilk kaydının belirten bir değer ayarlar.|  
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Bir tablo türü kayıt kümesinde bir dizin ayarlamak için çağrılır.|  
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıt belirtilen alan değiştirilmiş olarak işaretler.|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Null (hiçbir değer sahip) geçerli kayıttaki belirtilen alanın değerini ayarlar.|  
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Kayıt kümesinde bir alanın değerini ayarlar.|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Null bir kayıt kümesinde bir alanın değerini ayarlar. (sahip. değer yok).|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Düzenleme sırasında yürürlüğe koymak için kilitleme türünü belirten bir değer ayarlar.|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|Temel alınan DAOParameter nesnesindeki belirtilen parametresinin geçerli değeri ayarlar|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Belirtilen parametre geçerli değeri Null (hiçbir değer sahip) olarak ayarlar.|  
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Bir kayıt kümesindeki kayıt sayısı toplam yüzdesi karşılık gelen bir konuma geçerli kayıt konumunu ayarlar.|  
|[CDaoRecordset::Update](#update)|Tamamlanan bir `AddNew` veya **Düzenle** veri kaynağı üzerinde yeni veya düzenlenen veriler kaydederek işlemi.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Alanları otomatik olarak değiştirilmiş olarak işaretlenmiş olup olmadığını belirten bir bayrak içeriyor.|  
|[CDaoRecordset::m_nFields](#m_nfields)|Kayıt kümesi sınıfında yer alan veri üyeleri sayısı ve veri kaynağından kayıt kümesi tarafından seçilen sütunların sayısını içerir.|  
|[CDaoRecordset::m_nParams](#m_nparams)|Kayıt kümesi sınıfında parametre veri üyeleri sayısını içerir — parametrelerin sayısı geçirilen kümesinin sorgu|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Kayıt kümesi nesnesi için temel alınan DAO arabirimi için bir işaretçi.|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Bu sonuç kümesi için kaynak veritabanı. Bir işaretçi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|Bir SQL oluşturmak için kullanılan bir dize içeriyor **burada** deyimi.|  
|[CDaoRecordset::m_strSort](#m_strsort)|Bir SQL oluşturmak için kullanılan bir dize içeriyor **ORDER BY** deyimi.|  
  
## <a name="remarks"></a>Açıklamalar  
 "Kayıt kümeleri," bilinen `CDaoRecordset` aşağıdaki üç formlarında nesneleri kullanılabilir:  
  
-   Tablo türündeki kayıt kümeleri inceleyin, eklemek, değiştirmek veya tek veritabanı tablosundan kayıtları silmek için kullanabileceğiniz bir temel tablo temsil eder.  
  
-   Dynaset türü kayıt kümeleri güncelleştirilebilir kayıtları olabilen bir sorgu sonucudur. Bu kayıt kümeleri inceleyin, eklemek, değiştirmek veya temel bir veritabanı tablosu veya tabloları kayıtları silmek için kullanabileceğiniz bir kayıt kümesinde ' dir. Dynaset türü kayıt kümeleri bir veritabanında bir veya daha fazla tablolardan alanlar içerebilir.  
  
-   Anlık görüntü türü kayıt kümeleri veri bulmak veya raporlar oluşturmak için kullanabileceğiniz bir kayıt kümesinde statik bir kopyasını ' dir. Bu kayıt kümeleri bir veritabanında bir veya daha fazla tablolardan alanlar içerebilir ancak güncelleştirilemiyor.  
  
 Her form kümesinin bir kayıt kümesi açıldığında sabit kayıt kümesini temsil eder. Tablo türündeki kayıt kümesi veya dynaset türünde bir kayıt kümesi içindeki bir kayıt kaydırma yaptığınızda, diğer kullanıcılar tarafından veya diğer kayıt kümeleri, uygulamanızın içinde tarafından kayıt açıldıktan sonra kayda yapılan değişiklikleri yansıtır. (Bir anlık görüntü türündeki kayıt kümesi güncelleştirilemiyor.) Kullanabileceğiniz `CDaoRecordset` doğrudan veya bir uygulamaya özgü kayıt kümesi sınıfından türetilen `CDaoRecordset`. Sonra şunları yapabilirsiniz:  
  
-   Kayıtlarında gezinin.  
  
-   Bir dizine ayarlayın ve hızlı bir şekilde kullanarak kayıtları aramak [Seek](#seek) (yalnızca tablo türü kayıt kümeleri).  
  
-   Dize karşılaştırması hakkında temel alarak kayıtları bulun: "<","\<=", "=" "> =", veya ">" (dynaset türü ve anlık görüntü türü kayıt kümeleri).  
  
-   Kayıtları güncelleştirmek ve kilitleme modunu (dışında anlık görüntü türü kayıt kümeleri) belirtin.  
  
-   Veri kaynağı üzerinde kullanılabilir olanlardan seçer kaydeden sınırlamak için kayıt kümesi filtreleyin.  
  
-   Kayıt kümesi sıralayın.  
  
-   Çalışma zamanına kadar bilinmiyor bilgilerle kendi seçimi özelleştirmek için kayıt kümesini parametreleştirme.  
  
 Sınıf `CDaoRecordset` sınıfı için benzer bir arabirim sağlayan `CRecordset`. Bu sınıf ana farktır `CDaoRecordset` veri aracılığıyla bir veri erişim nesnesi (OLE üzerinde temel DAO) erişir. Sınıf `CRecordset` DBMS bu DBMS için açık veritabanı bağlantısı (ODBC) ve ODBC sürücüsü erişir.  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala yapabilecekleriniz; Microsoft Jet veritabanı altyapısı için belirli olduklarından DAO sınıfları genellikle üstün yetenekleri sunar.  
  
 Kullanabilir `CDaoRecordset` doğrudan veya öğesinden bir sınıf türetin `CDaoRecordset`. Kayıt kümesi sınıfı her iki durumda da kullanmak için bir veritabanı açın ve bir işaretçi Oluşturucusu geçirme bir kayıt kümesi nesnesi oluşturun, `CDaoDatabase` nesnesi. Ayrıca oluşturabileceğiniz bir `CDaoRecordset` nesne ve geçici bir oluşturma MFC izin `CDaoDatabase` nesnesi. Ardından kayıt kümesinin çağırın [açık](#open) üye işlevi, nesne bir tablo türü kayıt, dinamik küme türü kayıt veya bir anlık görüntü türü kayıt olup olmadığını belirleme. Çağırma **açık** veritabanından verileri seçer ve ilk kaydı alır.  
  
 Nesnenin üye işlevleri ve veri üyeleri kayıtlarda kaydırma ve bunlar üzerinde çalıştırmak için kullanın. Nesne bir tablo türü kayıt, dinamik küme türünde bir kayıt kümesi ya da bir anlık görüntü türündeki kayıt kümesi olup olmadığı ve güncelleştirilebilir veya salt okunur olup kullanılabilir işlemleri bağlı — bu veritabanı veya açık veritabanı bağlantısı (ODBC) yeteneğini bağlıdır veri kaynağı. Değiştirilmiş veya bu yana eklenen kayıtları yenilemek için **açık** çağrısı, nesnenin çağrısı [Requery](#requery) üye işlevi. Nesnenin çağrı **Kapat** üye işlev ve ile işiniz bittiğinde nesneyi yok.  
  
 `CDaoRecordset` tür kullanımı uyumlu C++ üyeleri okuma ve kayıt alanlarının güncelleştirme desteklemek için DAO kayıt alanı değişimi (DFX) kullanır, `CDaoRecordset` veya `CDaoRecordset`-türetilmiş sınıf. DFX mekanizmasını kullanarak kullanmadan bir veritabanında dinamik sütun bağlama uygulayabilirsiniz [GetFieldValue](#getfieldvalue) ve [SetFieldValue](#setfieldvalue).  
  
 İlgili bilgi için DAO Yardımı'ndaki "kayıt kümesi nesnesi" konusuna bakın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="addnew"></a>  CDaoRecordset::AddNew  
 Bir tablo veya dynaset tipi kayıt kümesine yeni bir kayıt eklemek için bu üye işlevini çağırın.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kaydın alanları başlangıçta Null. (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve aynı değil **NULL** c++.) İşlemi tamamlamak için çağırmalısınız [güncelleştirme](#update) üye işlevi. **Güncelleştirme** veri kaynağına yaptığınız değişiklikleri kaydeder.  
  
> [!CAUTION]
>  Bir kayıt düzenleyin ve ardından başka bir kayıtla çağırmadan kaydırın **güncelleştirme**, uyarmadan değişiklikleriniz kaybolur.  
  
 Çağırarak bir kayıt dynaset türü kayıt kümesine eklerseniz [AddNew](#addnew), kayıt kümesinde görünür ve burada da görünür hale gelir herhangi yeni temel alınan tabloda dahil `CDaoRecordset` nesneleri.  
  
 Yeni kayıttaki konumunu kayıt kümesinin türüne bağlıdır:  
  
-   Burada yeni kayda eklenen kayıt kümesi, dinamik küme türü garanti edilmez. Bu davranış, performans ve eşzamanlılık nedenlerini Microsoft Jet 3.0 ile değiştirildi. Amacınız yeni eklenen kaydı geçerli kayıt yapmak istiyorsanız son değiştirilen kayıt işaretinin alın ve bu işaretine Taşı:  
  
 [!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   Bir dizin belirtilen bir tablo türü kayıt kümesindeki kayıtları sıralama düzenini uygun yerine döndürülür. Herhangi bir dizin belirtilirse yeni kayıtlar kayıt kümesinin sonunda döndürülür.  
  
 Kullandığınız önce geçerli kayıt `AddNew` geçerli olmaya devam eder. Yeni kayıttaki geçerli yapmak istediğiniz ve kayıt yer işaretleri, çağrı destekliyorsa [SetBookmark](#setbookmark) DAO kayıt kümesi nesnesini LastModified özellik ayarı tarafından tanımlanan işaretine. Bunun yapılması, eklenen bir kayıttaki sayaç (otomatik artım) alanları değeri belirlemede yararlıdır. Daha fazla bilgi için bkz: [GetLastModifiedBookmark](#getlastmodifiedbookmark).  
  
 Veritabanı işlemleri destekliyorsa, yapabileceğiniz, `AddNew` çağrısı bir işlemin parçası. İşlemler hakkında daha fazla bilgi için bkz [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Çağırmalısınız Not [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) çağırmadan önce `AddNew`.  
  
 Çağrı geçersiz `AddNew` bir kayıt kümesi için [açık](#open) üye işlevi çağrılmadı. A `CDaoException` çağırırsanız durum `AddNew` eklenemiyor bir kayıt kümesi için. Çağırarak kayıt güncelleştirilebilir olup olmadığını belirleyebilirsiniz [CanAppend](#canappend).  
  
 Bunlar veri kaynağındaki DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için alan veri üyeleri framework işaretleri değiştirildi. Genellikle bir alanın değerini değiştirme ayarlar alan kirli otomatik olarak nadiren çağırmanız gerekir böylece [SetFieldDirty](#setfielddirty) kendiniz ancak, bazen isteyebileceğiniz sütunları açıkça güncelleştirilmiş veya kaldırılacak bakılmaksızın eklenmiş olduğundan emin olmak hangi alan veri üyesi değeridir. DFX mekanizması kullanımını da kullanan **SÖZDE NULL**. Daha fazla bilgi için bkz: [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 İki kez arabelleğe alma mekanizması kullanılmadığından, alanın değerini değiştirme otomatik olarak alan kirli olarak ayarlamaz. Bu durumda, açıkça alan kirli ayarlamak gerekli olacaktır. İçinde yer alan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) denetimleri otomatik alan denetleniyor.  
  
> [!NOTE]
>  İki kez arabelleğe alınan kayıtları olması durumunda (diğer bir deyişle, otomatik alan denetimi, çağırma etkin) `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir `AddNew` veya **Düzenle** çağrıldı.  
  
 İlgili bilgi için "AddNew yöntemi", "CancelUpdate yöntemi", "LastModified özelliği" ve DAO Yardımı'ndaki "EditMode özelliği" konularına bakın.  
  
##  <a name="canappend"></a>  CDaoRecordset::CanAppend  
 Daha önce açılmış kayıt kümesi çağırarak yeni kayıtlar eklemenize izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın [AddNew](#addnew) üye işlevi.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni kayıtlar ekleme kayıt izin veriyorsa sıfır olmayan; Aksi takdirde 0. `CanAppend` kayıt kümesi salt okunur olarak açıldıysa 0 döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgi için DAO Yardımı'ndaki "yöntemi ekleme" konusuna bakın.  
  
##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark  
 Daha önce açılmış kayıt kümesi, tek tek yer işaretlerini kullanma kayıtları işaretlemek izin verip vermeyeceğini belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yer işaretleri, aksi halde 0 kayıt destekliyorsa, sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümeleri tamamen Microsoft Jet veritabanı altyapısı tablolara kullanıyorsanız, yer işaretleri dışında yalnızca ileri kaydırma kayıt kümeleri işaretlenmiş anlık görüntü türü kayıt kümeleri üzerinde kullanılabilir. Diğer veritabanı ürünleri (Dış ODBC veri kaynakları) yer işaretleri desteklemiyor olabilir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Bookmarkable özelliği" konusuna bakın.  
  
##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate  
 `CancelUpdate` Üye işlevi nedeniyle bekleyen tüm güncelleştirmeleri iptal bir [Düzenle](#edit) veya [AddNew](#addnew) işlemi.  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, bir uygulama çağırırsa **Düzenle** veya `AddNew` üye işlevini ve değil çağırdı [güncelleştirme](#update), `CancelUpdate` sonra yapılan değişiklikleri iptal eder **Düzenle**veya `AddNew` çağrıldı.  
  
> [!NOTE]
>  İki kez arabelleğe alınan kayıtları olması durumunda (diğer bir deyişle, otomatik alan denetimi, çağırma etkin) `CancelUpdate` üye değişkenleri önce sahip oldukları değerlere geri yüklenir `AddNew` veya **Düzenle** çağrıldı.  
  
 Varsa hiçbir **Düzenle** veya `AddNew` işlemi beklemede, `CancelUpdate` bir özel durum MFC neden olur. Çağrı [GetEditMode](#geteditmode) iptal edilebilir bekleyen bir işlem olup olmadığını belirlemek için üye işlevi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "CancelUpdate yöntemi" konusuna bakın.  
  
##  <a name="canrestart"></a>  CDaoRecordset::CanRestart  
 Kayıt kümesi (kayıtlarını yenilemek için), sorgu çağırarak yeniden başlatmayı izin verip vermediğini belirlemek için bu üye işlevini çağırın **Requery** üye işlevi.  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF **Requery** kümesinin sorgusunu yeniden, aksi halde 0 çalışması için çağrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Tablo türündeki kayıt kümeleri desteklemez **Requery**.  
  
 Varsa **Requery** olduğu çağrı desteklenmiyor, [Kapat](#close) sonra [açık](#open) verileri yenilemek için. Çağırabilirsiniz **Requery** parametre değerlerini değiştikten sonra bir kayıt kümesi nesnesi güncelleştirmek için parametre sorguyla.  
  
 İlgili bilgi için DAO Yardımı'ndaki "yeniden başlatılabilir özellik" konusuna bakın.  
  
##  <a name="canscroll"></a>  CDaoRecordset::CanScroll  
 Kayıt kaydırma izin verip vermediğini belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıtlarda, aksi halde 0 kaydırırsanız, sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırırsanız [açık](#open) ile **dbForwardOnly**, kayıt kümesi yalnızca ileri kaydırma yapabilirsiniz.  
  
 İlgili bilgi için "Konumlandırma geçerli kayıt işaretçisi ile DAO'da" DAO Yardım konusuna bakın.  
  
##  <a name="cantransact"></a>  CDaoRecordset::CanTransact  
 Kayıt işlemleri izin verip vermediğini belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Veri kaynağındaki işlemleri, aksi halde 0 destekliyorsa sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgi için "İşlemler özelliğinde" DAO Yardım konusuna bakın.  
  
##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate  
 Kayıt kümesi güncelleştirilebilir olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi güncelleştirilmiş sıfır olmayan (ekleme, güncelleştirme ve kayıtlarını sil), aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayıt temel alınan veri kaynağı salt okunur olup olmadığını belirttiyseniz salt okunur olabilir **dbReadOnly** için `nOptions` zaman aradığınız [açık](#open) kayıt kümesi için.  
  
 İlgili bilgi için "AddNew yöntemi", "Edit yöntemi", "Delete yöntemini", "Güncelleştirme yöntemi" ve "Güncelleştirilebilir özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset  
 Oluşturan bir `CDaoRecordset` nesnesi.  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDatabase`  
 Bir işaretçi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne veya değer **NULL**. Aksi takdirde **NULL** ve `CDaoDatabase` nesnenin **açmak** veri kaynağına bağlanmak için üye işlevi çağrılmamışsa, kayıt kümesinin onu sizin için kendi sırasında açmaya çalıştığında [açın ](#open) çağırın. Geçirirseniz **NULL**, `CDaoDatabase` nesnesi oluşturulur ve belirtilen kayıt kümesi sınıfından türetilen, veri kaynağı bilgileri kullanarak bağlandı `CDaoRecordset`.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabilir `CDaoRecordset` doğrudan veya bir uygulamaya özgü sınıfından türetilen `CDaoRecordset`. Kayıt kümesi sınıflarınızı çıkarmaya ClassWizard kullanabilirsiniz.  
  
> [!NOTE]
>  Türetirseniz, bir `CDaoRecordset` sınıfı, türetilmiş sınıf kendi Oluşturucusu sağlamanız gerekir. Türetilmiş sınıf oluşturucu Oluşturucusu çağrı `CDaoRecordset::CDaoRecordset`, uygun parametreleri boyunca kendisine geçirme.  
  
 Geçirmek **NULL** , kayıt kümesi oluşturucuya sahip bir `CDaoDatabase` nesnesi oluşturulur ve sizin için otomatik olarak bağlı. Bu, oluşturmak ve bağlamak gerektirmez yararlı bir kısayol olur bir `CDaoDatabase` kayıt oluşturma önce nesnesi. Varsa `CDaoDatabase` nesne açık değil bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesne de oluşturulacaktır varsayılan çalışma alanını kullanan sizin için. Daha fazla bilgi için bkz: [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).  
  
##  <a name="close"></a>  CDaoRecordset::Close  
 Kapatma bir `CDaoRecordset` nesne koleksiyondan ilişkili veritabanındaki açık kümelerinin onu kaldırır.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çünkü **Kapat** yok `CDaoRecordset` nesne yeniden nesne çağırarak **açık** aynı veri kaynağı veya farklı bir veri kaynağı.  
  
 Tüm bekleyen [AddNew](#addnew) veya [Düzenle](#edit) deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır. Eklemeleri ve düzenlemeleri korumak istiyorsanız, çağrı [güncelleştirme](#update) çağırmadan önce **Kapat** her kayıt kümesi için.  
  
 Çağırabilirsiniz **açık** çağırdıktan sonra yeniden **Kapat**. Bu, kayıt kümesi nesnesi yeniden kullanmanıza olanak sağlar. Daha iyi bir alternatif çağırmaktır [Requery](#requery), mümkün olduğunda.  
  
 İlgili bilgiler için "Kapat yönteminde" DAO Yardım konusuna bakın.  
  
##  <a name="delete"></a>  CDaoRecordset::Delete  
 Bir açık dynaset türü veya tablo türündeki kayıt kümesi nesnesi geçerli kayıt silmek için bu üye işlevini çağırın.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başarılı silindikten sonra kayıt kümesinin alan veri üyeleri bir Null değere ayarlanır ve açıkça kümesi Gezinti üye işlevleri birini çağırmalıdır ( [taşıma](#move), [Seek](#seek), [ SetBookmark](#setbookmark), vb.) silinen kayda üzere. Bir kayıt kümesinden kayıtları sildiğinizde olmalıdır geçerli bir kayıt kayıt kümesinde çağırmadan önce **silmek**; Aksi halde, MFC bir özel durum oluşturur.  
  
 **Silme** geçerli kaydı kaldırır ve erişilemez hale getirir. Düzenleme veya silinen kaydı kullanın, ancak geçerli kalır. Başka bir kayda geçtiğinizde, ancak, silinen kaydı yeniden geçerli yapamazsınız.  
  
> [!CAUTION]
>  Kayıt kümesi güncelleştirilebilir ve olmalıdır geçerli bir kayıt kayıt kümesindeki geçerli çağırdığınızda **silmek**. Örneğin, bir kaydını silin, ancak çağırmadan önce yeni bir kayıt kaydırma değil **silmek** yeniden **silmek** oluşturur bir [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Bir kayıt işlemleri kullanıyorsanız ve çağırmanız geri alınabilir [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) üye işlevi. Temel tablo birincil tablo ise bir cascade ilişkiyi silmek, geçerli kayıt yabancı bir tablodaki bir veya daha fazla kayıt silindiğinde da. Daha fazla bilgi için "delete tanımı cascade" DAO Yardımı'nda bkz.  
  
 Farklı `AddNew` ve **Düzenle**, çağrı **silmek** yapılan bir çağrı tarafından izlenmeyen **güncelleştirme**.  
  
 İlgili bilgi için "AddNew yöntemi", "Edit yöntemi", "Delete yöntemini", "Güncelleştirme yöntemi" ve "Güncelleştirilebilir özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="dofieldexchange"></a>  CDaoRecordset::DoFieldExchange  
 Framework otomatik olarak kayıt kümesi nesnenizi alan veri üyeleri geçerli kayıt veri kaynağı için karşılık gelen sütunlara arasında veri değişimi için bu üye işlevi çağırır.  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parametreler  
 `pFX`  
 Bir işaretçi içeren bir `CDaoFieldExchange` nesnesi. Framework zaten bu nesnesini alan değiştirme işlemi için bir bağlam belirtmek için kurmanız gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, parametre veri üyeleri varsa kayıt kümesinin seçimi için SQL deyimi dizesi parametre yer tutucularını bağlar. DAO kayıt alanı değişimi (DFX) olarak adlandırılan alan verisi, exchange her iki yönde de işe yarar: kayıt kümesi nesnesinin alan veri üyeleri veri kaynağındaki alan ve kayıt kümesi nesnesi için veri kaynağı kaydı. Sütunları dinamik olarak bağlıyorsanız uygulamak gerekmez `DoFieldExchange`.  
  
 Normal olarak yapmanız gereken uygulamak için tek eylem `DoFieldExchange` türetilmiş kümeniz için ClassWizard ile sınıf oluşturun ve alan veri üyeleri adları ve veri türlerini belirtmek için bir sınıftır. Kod ne ClassWizard parametre veri üyeleri belirtmek Yazar de ekleyebilirsiniz. Tüm alanları dinamik olarak bağlı ise, parametre veri üyeleri belirtmediğiniz sürece bu işlev etkin olacaktır.  
  
 Türetilen kayıt kümesi sınıfınız ClassWizard ile bildirirken sihirbaz geçersiz kılma Yazar `DoFieldExchange` sizin için hangi benzer aşağıdaki örnek:  
  
 [!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>  CDaoRecordset::Edit  
 Değişiklikleri geçerli kayda izin vermek için bu üye işlevini çağırın.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmanız sonra **Düzenle** üye işlevi, geçerli kaydın alanlarında yapılan değişiklikler, kopyalama arabelleğine kopyalanır. Kayda istediğiniz değişiklikleri yaptıktan sonra arama **güncelleştirme** yaptığınız değişiklikleri kaydetmek için. **Düzen** kümesinin veri üyelerinin değerlerini kaydeder. Çağırırsanız **Düzenle**, ardından çağıran değişiklik **Düzenle** kaydın değerleri ne ilk önce oldukları için yeniden geri **Düzenle** çağırın.  
  
> [!CAUTION]
>  Bir kayıt düzenleyip ilk çağırmadan başka bir kayıtla taşır herhangi bir işlem gerçekleştirmek **güncelleştirme**, uyarmadan değişiklikleriniz kaybolur. Ayrıca, kayıt ya üst veritabanı kapatırsanız, düzenlenen kaydınız uyarmadan göz ardı edilir.  
  
 Bazı durumlarda, bir sütun Null (hiçbir veri içeren) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için arama `SetFieldNull` bir parametresi ile **TRUE** Null; alan işaretlemek için bu da güncelleştirilmesi sütun neden olur. Bir alanın değerini değişmediğini olsa bile veri kaynağına yazılması, çağrı istiyorsanız `SetFieldDirty` bir parametresi ile **doğru**. Bu alan Null değere sahip olsa bile çalışır.  
  
 Bunlar veri kaynağındaki DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için alan veri üyeleri framework işaretleri değiştirildi. Genellikle bir alanın değerini değiştirme ayarlar alan kirli otomatik olarak nadiren çağırmanız gerekir böylece [SetFieldDirty](#setfielddirty) kendiniz ancak, bazen isteyebileceğiniz sütunları açıkça güncelleştirilmiş veya kaldırılacak bakılmaksızın eklenmiş olduğundan emin olmak hangi alan veri üyesi değeridir. DFX mekanizması kullanımını da kullanan **SÖZDE NULL**. Daha fazla bilgi için bkz: [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 İki kez arabelleğe alma mekanizması kullanılmadığından, alanın değerini değiştirme otomatik olarak alan kirli olarak ayarlamaz. Bu durumda, açıkça alan kirli ayarlamak gerekli olacaktır. İçinde yer alan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) denetimleri otomatik alan denetleniyor.  
  
 Kayıt kümesi nesnesi çok kullanıcılı bir ortamda zor kilitlendiğinde kayıt kilitli kalır **Düzenle** güncelleştirme tamamlanana kadar kullanılır. Kayıt kümesi iyimser kilitliyse kayıt kilitli ve veritabanında güncelleştirilmeden önce önceden düzenlenmiş kayıtla karşılaştırılır. Aradığınız kaydı değişmişse **Düzenle**, **güncelleştirme** işlemi başarısız olur ve MFC bir özel durum oluşturur. Kilitleme moduyla değiştirebileceğiniz `SetLockingMode`.  
  
> [!NOTE]
>  İyimser kilitleme ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimleri üzerinde her zaman kullanılır.  
  
 Geçerli kayıt çağırdıktan sonra geçerli kaldığı **Düzenle**. Çağrılacak **Düzenle**, geçerli bir kayıt olması gerekir. Geçerli kayıt yok ise ya da kayıt için bir tablo türü veya dynaset türündeki kayıt kümesi nesnesi belirtmiyorsa bir özel durum oluşur. Çağırma **Düzenle** neden olan bir `CDaoException` aşağıdaki koşullar altında durum için:  
  
-   Geçerli kayıt yok.  
  
-   Veritabanı veya kayıt kümesi salt okunur durumdadır.  
  
-   Kayıttaki alan bulunmadığından güncelleştirilebilir.  
  
-   Veritabanı veya kayıt kümesi özel kullanım için başka bir kullanıcı tarafından açılmış.  
  
-   Başka bir kullanıcı, kaydı içeren sayfasını kilitledi.  
  
 Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz **Düzenle** çağrısı bir işlemin parçası. Çağırmalısınız Not `CDaoWorkspace::BeginTrans` çağırmadan önce **Düzenle** ve kayıt açıldıktan sonra. Ayrıca, arama unutmayın `CDaoWorkspace::CommitTrans` çağırmak için bir alternatif değildir **güncelleştirme** tamamlamak için **Düzenle** işlemi. İşlemler hakkında daha fazla bilgi için bkz. `CDaoWorkspace`.  
  
 İlgili bilgi için "AddNew yöntemi", "Edit yöntemi", "Delete yöntemini", "Güncelleştirme yöntemi" ve "Güncelleştirilebilir özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="fillcache"></a>  CDaoRecordset::FillCache  
 Belirli bir kayıt kümesindeki kayıt sayısı önbelleğe almak için bu üye işlevini çağırın.  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSize`  
 Önbellekte doldurmak için satır sayısını belirtir. Bu parametresini atlarsanız, değer DAO nesnesini CacheSize özellik ayarı tarafından belirlenir.  
  
 `pBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) yer işareti belirtme. Önbellek tarafından bu yer işaretinin gösterdiği kayıttan başlayarak doldurulur. Bu parametresini atlarsanız, önbellek DAO nesnesini CacheStart özelliği tarafından belirtilen kayıt başlayarak doldurulur.  
  
### <a name="remarks"></a>Açıklamalar  
 Önbelleğe alma alır ya da getirir, verileri uzak bir sunucudan bir uygulama performansını artırır. Bir önbellek son uygulama çalışırken veriler büyük olasılıkla yeniden istenecektir olduğunu varsayımına sunucudan alınan verileri tutar yerel bellek alanı kullanılıyor. Veri istendiğinde, Microsoft Jet veritabanı altyapısı için veri önbelleği ilk daha uzun sürer sunucudan getiriliyor yerine denetler. Verileri önbelleğe kaydedilmez gibi veri olmayan ODBC veri kaynakları önbelleğe alma kullanarak hiçbir etkisi olmaz.  
  
 Bunlar getirilen gibi kayıtlarıyla doldurulacak önbelleği için beklemek yerine, açıkça Önbellek herhangi bir zamanda çağırarak doldurabilirsiniz `FillCache` üye işlevi. Bu önbellek çünkü doldurmak için daha hızlı bir yoludur `FillCache` birden fazla kayıt aynı anda bir kerede yerine getirir. Örneğin, her dolusu kaydı görüntülendiği sırada uygulama aramanız olabilir `FillCache` sonraki dolusu kaydı getirilemedi.  
  
 Kayıt kümesi nesneleriyle erişilen herhangi bir ODBC veritabanı yerel bir önbelleğe sahip olabilir. Önbellek oluşturmak için bir kayıt kümesi nesnesi uzak veri kaynağından açın ve ardından arama `SetCacheSize` ve `SetCacheStart` üye işlevleri kümesi. Varsa `lSize` ve *lBookmark* tarafından belirtilen aralık kısmen veya tamamen dışında bir aralık oluşturmak `SetCacheSize` ve `SetCacheStart`, kayıt kümesinin bu aralığın dışında kalan kısmı dikkate alınmaz ve önbelleğe yüklü değil. Varsa `FillCache` uzak veri kaynağında'den daha fazla kayıt kalır, sadece kalan kayıtları getirilen ve hiçbir özel durum ister.  
  
 Kayıtlar önbellekten alınan eşzamanlı olarak kaynak verilere diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaz.  
  
 `FillCache` yalnızca henüz önbelleğe kayıtları getirir. Önbellekte saklanan tüm veriler güncelleştirmesini zorlamak için arama `SetCacheSize` üye işleviyle bir `lSize` parametresi 0, çağrı eşit `SetCacheSize` yeniden `lSize` parametre önbellek boyutuna eşit, başlangıçta istenen ve çağırın`FillCache`.  
  
 İlgili bilgi için DAO Yardımı'ndaki "FillCache yöntemi" konusuna bakın.  
  
##  <a name="find"></a>  CDaoRecordset::Find  
 Bir karşılaştırma işleci kullanılarak dynaset veya anlık görüntü türü kayıt kümesinde belirli bir dizeyi bulmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 *lFindType*  
 Bulma işlemi istenen türünü belirten bir değer. Olası değerler şunlardır:  
  
- **AFX_DAO_NEXT** eşleşen bir dize sonraki konumunu bulun.  
  
- **AFX_DAO_PREV** eşleşen bir dize önceki konumunu bulun.  
  
- **AFX_DAO_FIRST** eşleşen bir dize ilk konumu bulur.  
  
- **AFX_DAO_LAST** eşleşen bir dize son konumunu bulun.  
  
 `lpszFilter`  
 Bir dize ifadesi (gibi **nerede** sözcüğü olmadan SQL deyimindeki yan tümcesi **burada**) kaydı bulmak için kullanılır. Örneğin:  
  
 [!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk olarak, sonraki bulabilirsiniz dize önceki ya da son örneği. **Bul** geçersiz kılmak ve kendi uygulama eklemek için sanal bir işlev değil. `FindFirst`, `FindLast`, `FindNext`, Ve `FindPrev` üye işlevlerini çağrısı **Bul** kullanabilmek için üye işlevi **Bul** tüm bulma işlemleri davranışını denetlemek için .  
  
 Tablo türündeki kayıt kümesinde bir kayıt bulmak için arama [Seek](#seek) üye işlevi.  
  
> [!TIP]
>  Sahip olduğunuz kayıt daha fazla etkili küçük kümesini **Bul** olacaktır. Genel ve özellikle ODBC veri ile tam olarak kayıtları alır yeni bir sorgu oluşturmak daha iyidir.  
  
 İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.  
  
##  <a name="findfirst"></a>  CDaoRecordset::FindFirst  
 Belirtilen bir koşul ile eşleşen ilk kaydı bulmak için bu üye işlevini çağırın.  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFilter`  
 Bir dize ifadesi (gibi **nerede** sözcüğü olmadan SQL deyimindeki yan tümcesi **burada**) kaydı bulmak için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 `FindFirst` Üye işlevi kayıt kümesinin başından kendi arama ve aramaları kümesinin sonuna başlar.  
  
 Tüm kayıt kaydı taşımak için kullanın aramanızı (yalnızca bu belirli bir koşulu karşılayan) kayıtları taşıma işlemlerden biri, dahil etmek istiyorsanız. Tablo türündeki kayıt kümesinde bir kayıt bulmak için arama `Seek` üye işlevi.  
  
 Ölçütlerle eşleşen bir kayıt bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindFirst` sıfır döndürür. Kayıt kümesi ölçütlerini karşılayan birden fazla kayıt içeriyorsa `FindFirst` ilk oluşum bulur `FindNext` Sonrakini vb. bulur.  
  
> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, değişiklikler çağırarak kaydettiğinizden emin olun **güncelleştirme** başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarmadan değişiklikleriniz kaybolur.  
  
 **Bul** üye işlevleri arama konumundan ve aşağıdaki tabloda belirtilen yönde:  
  
|Operations Bul|Başlangıç|Arama yönü|  
|---------------------|-----------|----------------------|  
|`FindFirst`|Kayıt kümesi başlangıcı|Kayıt kümesi sonuna|  
|`FindLast`|Kayıt kümesi sonuna|Kayıt kümesi başlangıcı|  
|`FindNext`|Geçerli kayıt|Kayıt kümesi sonuna|  
|**FindPrevious**|Geçerli kayıt|Kayıt kümesi başlangıcı|  
  
> [!NOTE]
>  Çağırdığınızda `FindLast`, bu değil zaten yapılmamışsa Microsoft Jet veritabanı altyapısı tam olarak kümenizin arama başlamadan önce doldurur. İlk arama sonraki aramalar uzun sürebilir.  
  
 Bulma işlemleri birini kullanarak değil arama aynı **MoveFirst** veya `MoveNext`, ancak hangi yalnızca yapar ilk veya sonraki kaydı geçerli bir koşul belirtmeden. Bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.  
  
 Bulma işlemleri kullanırken aşağıdakileri göz önünde bulundurun:  
  
-   Varsa **Bul** geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisi geçerli kayda geri getirin.  
  
-   Bulma işlemi bir salt iletme kaydırma anlık görüntü türündeki kayıt kümesi ile kullanamazsınız.  
  
-   ABD tarih biçimini (ay-günlük-yıl) kullanması gereken Microsoft Jet veritabanı altyapısı; ABD sürümünü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamayabilir.  
  
-   Büyük dinamik kümeler ODBC veritabanları ile çalışırken, bulma işlemleri kullanarak özellikle büyük veritabanları ile çalışırken, yavaş olduğunu fark edebilirsiniz. SQL sorguları kullanarak performansı artırabilir ile özelleştirilmiş **ORDERBY** veya **nerede** yan tümceleri, parametre sorguları veya **CDaoQuerydef** belirli almak nesneleri Dizinli kaydeder.  
  
 İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.  
  
##  <a name="findlast"></a>  CDaoRecordset::FindLast  
 Belirtilen bir koşul ile eşleşen son kaydı bulmak için bu üye işlevini çağırın.  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFilter`  
 Bir dize ifadesi (gibi **nerede** sözcüğü olmadan SQL deyimindeki yan tümcesi **burada**) kaydı bulmak için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 `FindLast` Üye işlevi, kayıt işleminin sonunda, arama ve kayıt kümesi başına doğru geriye doğru arama başlar.  
  
 Tüm kayıt kaydı taşımak için kullanın aramanızı (yalnızca bu belirli bir koşulu karşılayan) kayıtları taşıma işlemlerden biri, dahil etmek istiyorsanız. Tablo türündeki kayıt kümesinde bir kayıt bulmak için arama `Seek` üye işlevi.  
  
 Ölçütlerle eşleşen bir kayıt bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindLast` sıfır döndürür. Kayıt kümesi ölçütlerini karşılayan birden fazla kayıt içeriyorsa `FindFirst` ilk oluşum bulur `FindNext` Sonrakini ilk oluşum vb. sonra bulur.  
  
> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak Değişiklikleri Kaydet mutlaka **güncelleştirme** başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarmadan değişiklikleriniz kaybolur.  
  
 Bulma işlemleri birini kullanarak değil arama aynı **MoveFirst** veya `MoveNext`, ancak hangi yalnızca yapar ilk veya sonraki kaydı geçerli bir koşul belirtmeden. Bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.  
  
 Bulma işlemleri kullanırken aşağıdakileri göz önünde bulundurun:  
  
-   Varsa **Bul** geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisi geçerli kayda geri getirin.  
  
-   Bulma işlemi bir salt iletme kaydırma anlık görüntü türündeki kayıt kümesi ile kullanamazsınız.  
  
-   ABD tarih biçimini (ay-günlük-yıl) kullanması gereken Microsoft Jet veritabanı altyapısı; ABD sürümünü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamayabilir.  
  
-   Büyük dinamik kümeler ODBC veritabanları ile çalışırken, bulma işlemleri kullanarak özellikle büyük veritabanları ile çalışırken, yavaş olduğunu fark edebilirsiniz. SQL sorguları kullanarak performansı artırabilir ile özelleştirilmiş **ORDERBY** veya **nerede** yan tümceleri, parametre sorguları veya **CDaoQuerydef** belirli almak nesneleri Dizinli kaydeder.  
  
 İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.  
  
##  <a name="findnext"></a>  CDaoRecordset::FindNext  
 Belirtilen bir koşul ile eşleşen bir sonraki kaydı bulmak için bu üye işlevini çağırın.  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFilter`  
 Bir dize ifadesi (gibi **nerede** sözcüğü olmadan SQL deyimindeki yan tümcesi **burada**) kaydı bulmak için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 `FindNext` Üye işlevi geçerli kaydın sonunda, aramayı başlatır ve kayıt kümesinin sonuna arar.  
  
 Tüm kayıt kaydı taşımak için kullanın aramanızı (yalnızca bu belirli bir koşulu karşılayan) kayıtları taşıma işlemlerden biri, dahil etmek istiyorsanız. Tablo türündeki kayıt kümesinde bir kayıt bulmak için arama `Seek` üye işlevi.  
  
 Ölçütlerle eşleşen bir kayıt bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindNext` sıfır döndürür. Kayıt kümesi ölçütlerini karşılayan birden fazla kayıt içeriyorsa `FindFirst` ilk oluşum bulur `FindNext` Sonrakini vb. bulur.  
  
> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak Değişiklikleri Kaydet mutlaka **güncelleştirme** başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarmadan değişiklikleriniz kaybolur.  
  
 Bulma işlemleri birini kullanarak değil arama aynı **MoveFirst** veya `MoveNext`, ancak hangi yalnızca yapar ilk veya sonraki kaydı geçerli bir koşul belirtmeden. Bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.  
  
 Bulma işlemleri kullanırken aşağıdakileri göz önünde bulundurun:  
  
-   Varsa **Bul** geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisi geçerli kayda geri getirin.  
  
-   Bulma işlemi bir salt iletme kaydırma anlık görüntü türündeki kayıt kümesi ile kullanamazsınız.  
  
-   ABD tarih biçimini (ay-günlük-yıl) kullanması gereken Microsoft Jet veritabanı altyapısı; ABD sürümünü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamayabilir.  
  
-   Büyük dinamik kümeler ODBC veritabanları ile çalışırken, bulma işlemleri kullanarak özellikle büyük veritabanları ile çalışırken, yavaş olduğunu fark edebilirsiniz. SQL sorguları kullanarak performansı artırabilir ile özelleştirilmiş **ORDERBY** veya **nerede** yan tümceleri, parametre sorguları veya **CDaoQuerydef** belirli almak nesneleri Dizinli kaydeder.  
  
 İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.  
  
##  <a name="findprev"></a>  CDaoRecordset::FindPrev  
 Belirtilen bir koşul ile eşleşen önceki kayıt bulmak için bu üye işlevini çağırın.  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszFilter`  
 Bir dize ifadesi (gibi **nerede** sözcüğü olmadan SQL deyimindeki yan tümcesi **burada**) kaydı bulmak için kullanılır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 `FindPrev` Üye işlevi geçerli kayıt kendi arama başlar ve geriye doğru kayıt kümesi başına doğru arar.  
  
 Tüm kayıt kaydı taşımak için kullanın aramanızı (yalnızca bu belirli bir koşulu karşılayan) kayıtları taşıma işlemlerden biri, dahil etmek istiyorsanız. Tablo türündeki kayıt kümesinde bir kayıt bulmak için arama `Seek` üye işlevi.  
  
 Ölçütlerle eşleşen bir kayıt bulunamazsa, geçerli kayıt işaretçisi yapılmadığı ve `FindPrev` sıfır döndürür. Kayıt kümesi ölçütlerini karşılayan birden fazla kayıt içeriyorsa `FindFirst` ilk oluşum bulur `FindNext` Sonrakini vb. bulur.  
  
> [!CAUTION]
>  Geçerli kayıt düzenlerseniz, çağırarak Değişiklikleri Kaydet mutlaka **güncelleştirme** başka bir kayıtla taşımadan önce üye işlevi. Başka bir kayıtla güncelleştirmeden taşırsanız, uyarmadan değişiklikleriniz kaybolur.  
  
 Bulma işlemleri birini kullanarak değil arama aynı **MoveFirst** veya `MoveNext`, ancak hangi yalnızca yapar ilk veya sonraki kaydı geçerli bir koşul belirtmeden. Bulma işlemi bir taşıma işlemi ile izleyebilirsiniz.  
  
 Bulma işlemleri kullanırken aşağıdakileri göz önünde bulundurun:  
  
-   Varsa **Bul** geçerli kayıt tanımlı değil, sıfır döndürür. Bu durumda, geçerli kayıt işaretçisi geçerli kayda geri getirin.  
  
-   Bulma işlemi bir salt iletme kaydırma anlık görüntü türündeki kayıt kümesi ile kullanamazsınız.  
  
-   ABD tarih biçimini (ay-günlük-yıl) kullanması gereken Microsoft Jet veritabanı altyapısı; ABD sürümünü kullanmıyorsanız bile tarihleri içeren alanlar için arama yaparken Aksi takdirde, eşleşen kayıtlar bulunamayabilir.  
  
-   Büyük dinamik kümeler ODBC veritabanları ile çalışırken, bulma işlemleri kullanarak özellikle büyük veritabanları ile çalışırken, yavaş olduğunu fark edebilirsiniz. SQL sorguları kullanarak performansı artırabilir ile özelleştirilmiş **ORDERBY** veya **nerede** yan tümceleri, parametre sorguları veya **CDaoQuerydef** belirli almak nesneleri Dizinli kaydeder.  
  
 İlgili bilgiler için DAO Yardımı'nda, "FindFirst, FindLast, FindNext, FindPrevious Yöntemleri" konusuna bakın.  
  
##  <a name="getabsoluteposition"></a>  CDaoRecordset::GetAbsolutePosition  
 Kayıt kümesi nesnesinin geçerli kayıt kayıt sayısını döndürür.  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tamsayıya 0'dan kayıt kümesindeki kayıt sayısı. Geçerli kayıt kümesinde sıralı konumuna karşılık gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 DAO nesnesini AbsolutePosition özellik değerinin sıfır tabanlı olup; 0 ayarı, kayıt kümesindeki ilk kaydı ifade eder. Çağırarak doldurulan kayıt kümesinde sayısını belirleyebilirsiniz [GetRecordCount](#getrecordcount). Çağırma `GetRecordCount` sayısını belirlemek için tüm kayıtları erişmeniz gerekir çünkü biraz zaman alabilir.  
  
 Geçerli kayıt yok, olarak kayıt kümesinde hiç kayıt olduğunuzda - 1 döndürülür Geçerli kaydı silinirse, AbsolutePosition özellik değeri tanımlı değil ve onu başvuruluyorsa MFC özel durum oluşturur. Dynaset türü kayıt kümeleri için yeni kayıtlar dizinin sonuna eklenir.  
  
> [!NOTE]
>  Bu özellik, bir yedek kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri hala korur ve belirli bir konuma döndürmek için önerilen yoldur ve tüm kayıt kümesi nesne türlerini geçerli kayıt konumuna tek yoludur. Özellikle, kendisinden kayıt silindiğinde verilen kayıt konumunu değiştirir. Ayrıca bir SQL deyimi kullanarak ile yapılandırılmadığı sürece bir kayıt kümesi içinde tek tek kayıtların sırası kesin değildir çünkü kayıt yeniden yeniden oluşturulursa, verilen bir kaydın aynı mutlak konum gerekir herhangi bir güvencesi yoktur bir  **ORDERBY** yan tümcesi.  
  
> [!NOTE]
>  Bu üye işlevi yalnızca dynaset türü ve anlık görüntü türü kayıt kümeleri için geçerli değil.  
  
 İlgili bilgi için DAO Yardımı'ndaki "AbsolutePosition özelliğini" konusuna bakın.  
  
##  <a name="getbookmark"></a>  CDaoRecordset::GetBookmark  
 Belirli bir kayıttaki yer işareti değeri elde etmek için bu üye işlevini çağırın.  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kayıt üzerinde yer işareti temsil eden bir değer döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, bunları destekliyorsa, her birinin kayıtlarını zaten benzersiz bir yer işareti vardır. Çağrı `CanBookmark` kayıt yer işaretleri destekleyip desteklemediğini belirlemek için.  
  
 Geçerli kayıt için yer işaretine değerini atayarak kaydedebileceğiniz bir `COleVariant` nesnesi. Hızlı bir şekilde farklı bir kayda taşıdıktan herhangi bir zamanda bu kayda dönmek için çağrı `SetBookmark` , değerine karşılık gelen bir parametre ile `COleVariant` nesnesi.  
  
> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "yer işareti özellik" konusuna bakın.  
  
##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize  
 Önbelleğe alınan kayıt sayısını elde etmek için bu üye işlevini çağırın.  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren bir değişken küme türü kayıt kümesindeki kayıt sayısını belirten bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri önbelleğe alma dynaset türündeki kayıt kümesi nesneleri üzerinden uzak bir sunucudan verileri alan bir uygulamanın performansını artırır. Bir boşluk uygulama çalışırken verileri yeniden istenecektir gerektiğinde, sunucudan en son alınan verileri tutar, yerel bellekte önbelleğidir. Veri istendiğinde, Microsoft Jet veritabanı altyapısı için istenen veri önbelleği ilk daha uzun sürer sunucudan alınıyor yerine denetler. Bir ODBC veri kaynağından gelmez veri önbellekte kaydedilmez.  
  
 ODBC veri kaynağını, ekli bir tablo gibi bir yerel önbelleği olabilir.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "CacheSize, CacheStart özellikleri" konusuna bakın.  
  
##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart  
 Önbelleğe alınacak kayıt kümesindeki ilk kaydı yer işareti değeri elde etmek için bu üye işlevini çağırın.  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `COleVariant` önbelleğe alınacak kayıt kümesinde yer ilk kaydının belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Jet veritabanı altyapısı önbellekten önbellek aralıkta kayıt isteklerini ve sunucudan önbellek aralığın dışında kayıtları ister.  
  
> [!NOTE]
>  Önbellekten alınan kayıtlar eşzamanlı olarak kaynak verilere diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaz.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "CacheSize, CacheStart özellikleri" konusuna bakın.  
  
##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex  
 Dizin oluşturulmuş bir tablo türü şu anda kullanımda belirlemek için bu üye işlevini çağırın `CDaoRecordset` nesnesi.  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` şu anda kullanılmakta olan bir tablo türü kayıt dizinin adını içeren. Herhangi bir dizin ayarlarsanız boş bir dize döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizin, bir tablo türü kayıt kümesindeki kayıtları sıralama temelidir ve tarafından kullanılan [Seek](#seek) üye işlevi kayıtları bulun.  
  
 A `CDaoRecordset` nesne birden fazla dizine sahip olabilir, ancak aynı anda yalnızca bir dizini kullanabilir (rağmen bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi üzerinde tanımlı çeşitli dizinler olabilir).  
  
 İlgili bilgi için bkz: "Dizin nesnesi" bölümüne ve DAO Yardımı'ndaki "geçerli dizin" tanımı.  
  
##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated  
 Temel tablo oluşturulduğu saat ve tarihi almak için bu üye işlevini çağırın.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) temel tablo oluşturulduğu saat ve tarihi içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarih ve saat ayarları temel tablo oluşturulduğu bilgisayardan türetilir.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated  
 Tarih ve saat şemanın en son güncelleştirildiği almak için bu üye işlevini çağırın.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) temel tablo yapısı (şema) en son güncelleştirilen saat ve tarihi içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarih ve saat ayarları temel tablo yapısı (şema) en son güncelleştirildiği bilgisayardan türetilir.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName  
 Bu kayıt kümesinin veritabanı adını belirlemek için bu üye işlevini çağırın.  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` , bu kayıt kümesinin elde edilmiştir veritabanının adını ve yolunu içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayıt kümesi için bir işaretçi olmadan oluşturulursa bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), bu yol varsayılan veritabanı açmak için kayıt kümesi tarafından kullanılır. Varsayılan olarak, bu işlev boş bir dize döndürür. Ne zaman ClassWizard türeyen yeni bir kayıt kümesinden `CDaoRecordset`, sizin için bu işlev oluşturur.  
  
 Aşağıdaki örnek çift ters eğik çizgi kullanımını göstermektedir (\\\\) dizesi içinde olduğu gibi dize doğru yorumlanması gerekli.  
  
 [!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL  
 Framework kayıt dayandığı varsayılan SQL deyimini almak için bu üye işlevi çağırır.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` varsayılan SQL deyimini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu tablo adı veya bir SQL olabilir **seçin** deyimi.  
  
 Dolaylı olarak kayıt kümesi sınıfınız ClassWizard ile bildirerek varsayılan SQL deyimini tanımlayın ve ClassWizard bu görevi sizin için gerçekleştirir.  
  
 Bir null SQL dizesi geçirirseniz [açık](#open), sonra da bu işlev tablo adını veya SQL kümeniz için belirlemek için çağrılır.  
  
##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode  
 Aşağıdaki değerlerden biri olan düzenleme, durumunu belirlemek için bu üye işlevini çağırın:  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kaydı için düzenleme durumunu gösteren bir değer döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
  
|Değer|Açıklama|  
|-----------|-----------------|  
|**dbEditNone**|Hiçbir düzenleme işlemi devam ediyor.|  
|**dbEditInProgress**|**Düzen** çağrıldı.|  
|**dbEditAdd**|`AddNew` çağrıldı.|  
  
 İlgili bilgi için DAO Yardımı'ndaki "EditMode özelliği" konusuna bakın.  
  
##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount  
 Kayıt kümesinde tanımlanan alanları (sütunları) sayısını almak üzere bu üye işlevini çağırın.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi alanlarına sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgi için DAO Yardımı'ndaki "Count özelliğini" konusuna bakın.  
  
##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo  
 Kayıt alanları hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 `nIndex`  
 Dizine göre arama için kayıt kümesinin alanlar koleksiyonu önceden tanımlanmış alanında sıfır tabanlı dizini.  
  
 `fieldinfo`  
 Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için kayıt kümesi belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte burada listelenir. En iyi performans için yalnızca gereksinim duyduğunuz bilgileri düzeyini Al:  
  
- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Ad, tür, boyut öznitelikleri  
  
- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: gerekli, sıra konumu sıfır uzunluk, harmanlama sırası yabancı adı, kaynak alanı, kaynak tablo izin ver  
  
- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: varsayılan değer, doğrulama kuralı geçerlilik metni  
  
 `lpszName`  
 Alanın adı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevin bir sürüm dizini tarafından bir alanından aramak olanak sağlar. Başka bir sürüm bir alan adına göre aramak olanak sağlar.  
  
 Döndürülen bilgi açıklaması için bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istemek için de önceki tüm düzeylerde bilgi alın.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
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
 `lpszName`  
 Bir alanın adını içeren bir dize için bir işaretçi.  
  
 `varValue`  
 Bir başvuru bir `COleVariant` bir alanın değerini depolar nesnesi.  
  
 `nIndex`  
 Dizine göre arama için kayıt kümesinin alanlar koleksiyonu alanında sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İki sürümü `GetFieldValue` , dönüş değeri dönüş bir [COleVariant](../../mfc/reference/colevariant-class.md) bir alanın değerini içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir alan adı veya sıralı konumu tarafından da bakabilirsiniz.  
  
> [!NOTE]
>  Çağrı isteyen bu üye işlevi sürümlerinden birini daha verimli bir `COleVariant` bir parametre yerine döndüren bir sürüm çağırma nesne başvurusu bir `COleVariant` nesnesi. Bu işlev sonraki sürümleri geriye dönük uyumluluk için tutulur.  
  
 Kullanım `GetFieldValue` ve [SetFieldValue](#setfieldvalue) alanları çalıştırma yerine statik olarak kullanarak bağlama sütunları dinamik olarak bağlamak için [DoFieldExchange](#dofieldexchange) mekanizması.  
  
 `GetFieldValue` ve `DoFieldExchange` mekanizması, performansı artırmak için birleştirilebilir. Örneğin, `GetFieldValue` yalnızca isteğe bağlı olarak gereksinim değerini almak ve "Daha fazla bilgi" düğmesine arabiriminde bu çağrı atamak için.  
  
 İlgili bilgi için "Alanı nesnesi" ve "Değer özelliği" DAO Yardım konularına bakın.  
  
##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount  
 Tablo türündeki kayıt kümesi üzerinde kullanılabilir dizinler sayısını belirlemek için bu üye işlevini çağırın.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tablo türündeki kayıt kümesi dizinlerde sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetIndexCount` kayıt kümesindeki tüm dizinleri döngü için yararlıdır. Bu amaçla `GetIndexCount` birlikte [GetIndexInfo](#getindexinfo). Bu üye işlevini dynaset türü veya anlık görüntü türü kayıt kümeleri çağırırsanız, MFC özel durum oluşturur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo  
 Çeşitli bir kayıt temel temel tabloda tanımlanan dizin hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 `nIndex`  
 Sayısal konuma göre arama için tablonun dizinler koleksiyonu içindeki sıfır tabanlı dizin.  
  
 `indexinfo`  
 Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için dizini belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte burada listelenir. En iyi performans için yalnızca gereksinim duyduğunuz bilgileri düzeyini Al:  
  
- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Ad alanı bilgisi alanları  
  
- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: birincil, benzersiz, kümelenmiş, gerekli IgnoreNulls yabancı  
  
- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: ayrı sayım  
  
 `lpszName`  
 Ada göre arama dizini nesne adını gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi bir sürümü, bir dizin koleksiyondaki konumuyla aramak olanak tanır. Başka bir sürüm bir dizin oluşturan adına göre aramak olanak sağlar.  
  
 Döndürülen bilgi açıklaması için bkz: [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istemek için de önceki tüm düzeylerde bilgi alın.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark  
 En son eklenen veya güncelleştirilen kaydının yer almak için bu üye işlevini çağırın.  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `COleVariant` en son gösteren yer işareti içeren eklenen veya değiştirilen kayıt.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, bunları destekliyorsa, her birinin kayıtlarını zaten benzersiz bir yer işareti vardır. Çağrı [GetBookmark](#getbookmark) kayıt yer işaretleri destekleyip desteklemediğini belirlemek için. Kayıt kümesi yer işaretleri, desteklemiyorsa bir `CDaoException` oluşturulur.  
  
 Bir kayıt eklediğinizde, kayıt kümesinin sonunda görüntülenir ve geçerli kaydı değildir. Yeni kayıttaki geçerli yapmak için arama `GetLastModifiedBookmark` ve ardından arama `SetBookmark` yeni eklenen kayda dönün.  
  
 İlgili bilgi için DAO Yardımı'ndaki "LastModified özelliği" konusuna bakın.  
  
##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode  
 Geçerli kayıt kümesi için kilitleme türünü belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kilitleme türünü kötümser, ise sıfır olmayan iyimser kayıt kilitleme aksi 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kötümser kilitleme etkin düzenlemekte kayıt içeren veri sayfası olduğunda sizi aramasını hemen kilitli [Düzenle](#edit) üye işlevi. Çağırdığınızda kilidi sayfasıdır [güncelleştirme](#update) veya [Kapat](#close) üye işlevini veya taşıma veya bulma işlemleri.  
  
 Yalnızca kaydı ile güncelleştirilirken İyimser kilitleme etkindir, kayıt içeren veri sayfası kilitlenir **güncelleştirme** üye işlevi.  
  
 ODBC veri kaynakları ile çalışırken, kilitleme zaman iyimser modudur.  
  
 İlgili bilgi için "LockEdits özelliği" ve "Kilitleme davranışı, çok kullanıcılı uygulamalarda" DAO Yardım konularına bakın.  
  
##  <a name="getname"></a>  CDaoRecordset::GetName  
 Kayıt kümesi adını almak için bu üye işlevini çağırın.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` kayıt kümesi adını içeren.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi adı bir harf ile başlamalı ve en çok 40 karakter içerebilir. Sayı içerebilir ve alt çizgi karakterleri ancak noktalama veya boşluk içeremez.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue  
 Temel alınan DAOParameter nesnesindeki belirtilen parametresinin geçerli değeri almak için bu üye işlevini çağırın.  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Sayısal konumu parametresi DAOParameter nesnesini.  
  
 `lpszName`  
 Değer istediğiniz parametresinin adı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıfın bir nesnesi [COleVariant](../../mfc/reference/colevariant-class.md) parametrenin değeri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre adı veya koleksiyon içinde sayısal konumuna göre erişebilirsiniz.  
  
 İlgili bilgi için DAO Yardımı'ndaki "parametre nesnesi" konusuna bakın.  
  
##  <a name="getpercentposition"></a>  CDaoRecordset::GetPercentPosition  
 Çağırırsanız dynaset türü veya anlık görüntü türündeki kayıt kümesi ile çalışırken `GetPercentPosition` kayıt tam doldurma önce taşıma miktarını çağırarak belirtildiği gibi erişilen kayıt sayısını görelidir [GetRecordCount](#getrecordcount).  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli kayıt kayıt kümesindeki kayıt yüzdesine göre numaralandırır yaklaşık konumunu gösteren 0 ile 100 arasında bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak kayıt son taşıyabilirsiniz [MoveLast](#movelast) tam tüm kayıt kümeleri, ancak bu popülasyonunu önemli miktarda zaman alabilir.  
  
 Çağırabilirsiniz `GetPercentPosition` dizinleri olmayan tablolar üzerinde tüm üç tür kayıt nesnesinin dahil olmak üzere. Ancak, çağıramazsınız `GetPercentPosition` yalnızca ileri kaydırma anlık görüntüler veya dış veritabanı geçiş sorgusundan açılan bir kayıt kümesi. Geçerli kayıt yok ya da he geçerli kaydı silinmiş, bir `CDaoException` oluşturulur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "PercentPosition özelliği" konusuna bakın.  
  
##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount  
 Kayıt kümesindeki kaç kayıtları erişildiğini bulmak için bu üye işlevini çağırın.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kayıt kümesi nesnesi erişilen kayıt sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetRecordCount` tüm kayıtları erişim kadar kaç kayıt dynaset türü ya da anlık görüntü türündeki kayıt kümesi içerdiği göstermez. Bu üye işlev çağrısı önemli miktarda tamamlanması zaman alabilir.  
  
 Son kayda erişildikten sonra dönüş değeri silinmemiş kayıtlar kayıt kümesindeki toplam sayısını gösterir. Erişilecek Son kaydı zorlamak için arama `MoveLast` veya `FindLast` kayıt kümesinin üyesi işlevi. Bir SQL sayısı, kayıt, sorgunuzun döndüreceği yaklaşık sayısını belirlemek için de kullanabilirsiniz.  
  
 Uygulamanızı dönüş değerini dynaset türü kayıt kümesindeki kayıtları siler gibi `GetRecordCount` azaltır. Ancak, diğer kullanıcılar tarafından silinen kayıtlar tarafından yansıtılmaz `GetRecordCount` kadar geçerli kaydı silinen bir kayda konumlandırıldı. Kayıt sayısı etkileyen bir işlem yürütme ve daha sonra işlemi geri `GetRecordCount` gerçek kalan kayıt sayısı yansıtmaz.  
  
 Değeri `GetRecordCount` bir anlık görüntü türü kayıt kümesinden tablolardaki değişikliklerden etkilenmez.  
  
 Değeri `GetRecordCount` bir tablo türü kayıt kümesi tablodaki kayıtları yaklaşık sayısını yansıtır ve tablo kayıtlarını eklenen ve Silinen hemen etkilenir.  
  
 0 değeri hiçbir kayıt sahip bir kayıt döndürür. Bağlı tablolar veya ODBC veritabanları ile çalışırken `GetRecordCount` her zaman döndürür - 1. Çağırma **Requery** üye işlevi bir kayıt kümesinde sıfırlar değerini `GetRecordCount` yalnızca sorguyu yeniden yürütülen değilmiş gibi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "RecordCount özelliği" konusuna bakın.  
  
##  <a name="getsql"></a>  CDaoRecordset::GetSQL  
 Açıldığında kayıt kümesinin kayıtları seçmek için kullanılan SQL deyimini almak için bu üye işlevini çağırın.  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` SQL deyimi içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle bir SQL olacaktır **seçin** deyimi.  
  
 Tarafından döndürülen dize `GetSQL` kayıt kümesinde için geçirilen herhangi bir dize genellikle farklı `lpszSQL` parametresi [açık](#open) üye işlevi. Kayıt kümesi ne, geçirilen temel tam bir SQL deyimini oluşturur olmasıdır **açık**ClassWizard ile belirtilen ve ne belirttiğiniz [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) veri üyeleri.  
  
> [!NOTE]
>  Yalnızca çağrıldıktan sonra bu üye işlevini çağırın **açık**.  
  
 İlgili bilgi için DAO Yardımı'ndaki "SQL özellik" konusuna bakın.  
  
##  <a name="gettype"></a>  CDaoRecordset::GetType  
 Kayıt kümesi nesnesi türünü belirlemek için kayıt kümesi açtıktan sonra bu üye işlevini çağırın.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kayıt türünü gösteren aşağıdaki değerlerden biri:  
  
- **dbOpenTable** tablo türündeki kayıt kümesi  
  
- **dbOpenDynaset** Dynaset türü kayıt kümesi  
  
- **dbOpenSnapshot** anlık görüntü türündeki kayıt kümesi  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgi için DAO Yardımı'ndaki "Type özelliği" konusuna bakın.  
  
##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule  
 Verileri doğrulamak için kullanılan kural belirlemek için bu üye işlevini çağırın.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` değiştirilmiş veya tabloya eklenen bir kayıttaki verileri doğrulayan bir değer içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu kural, metin tabanlı ve temel tablo her değiştirildiğinde uygulanır. Veriler geçerli değilse, MFC özel durum oluşturur. Döndürülen hata iletisi ValidationText belirtilmişse temel alan nesnesinin özelliği, metin veya metin alanı nesnesini ValidationRule özelliği tarafından belirtilen ifadesinin değil. Çağırabilirsiniz [GetValidationText](#getvalidationtext) hata iletisinin metni elde edilir.  
  
 Örneğin, ayın günü gerektiren kaydındaki alan bir doğrulama kuralı gibi olabilir "gün BETWEEN 1 ile 31."  
  
 İlgili bilgi için "ValidationRule özelliğinde" DAO Yardım konusuna bakın.  
  
##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText  
 Metin alanı nesnesini ValidationText özelliğinin almak için bu üye işlevini çağırın.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` bir alanın değerini alan nesnesini doğrulama kuralının karşılamadığı, görüntülenen ileti metni içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgi için DAO Yardımı'ndaki "ValidationText özelliği" konusuna bakın.  
  
##  <a name="isbof"></a>  CDaoRecordset::IsBOF  
 Kaydından önce ilk kaydı kayıt kümesinin ilerlemiş olup olmadığını öğrenmek için kayıt kaydırma önce bu üye işlevini çağırın.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi hiçbir kayıt içeriyorsa veya, geriye doğru ilk kaydı önce kaydırırsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, çağırabilirsiniz `IsBOF` ile birlikte `IsEOF` kayıt herhangi bir kayıt içeren boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra **açık**, kayıt kümesinin hiçbir kayıt içeriyorsa `IsBOF` sıfır olmayan bir değer döndürür. En az bir kayda sahip bir kayıt kümesi açtığınızda, ilk kayıt geçerli kayıttır ve `IsBOF` 0 döndürür.  
  
 Geçerli kaydı ilk kaydı ise ve size çağrı `MovePrev`, `IsBOF` sonradan sıfır olmayan bir değer döndürür. Varsa `IsBOF` sıfır verir ve arama `MovePrev`, bir özel durum. Varsa `IsBOF` sıfır olmayan döndürür, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektirir herhangi bir eylem bir özel durum oluşur.  
  
 Belirli yöntemler etkisini `IsBOF` ve `IsEOF` ayarları:  
  
-   Çağırma **açık** dahili olarak ilk kaydı kayıt kümesindeki geçerli kayıt çağırarak yapar **MoveFirst**. Bu nedenle, çağırma **açık** kayıtları nedenler boş dizi `IsBOF` ve `IsEOF` sıfır olmayan dönün. (Başarısız davranışını için aşağıdaki tabloya bakın **MoveFirst** veya `MoveLast` çağırın.)  
  
-   Kaydı başarıyla yerleştirmek tüm taşıma işlemleri hem neden `IsBOF` ve `IsEOF` 0 dönün.  
  
-   Bir `AddNew` çağrı tarafından izlenen bir **güncelleştirme** başarıyla yeni bir kayıt ekler çağrısı neden olacak `IsBOF` 0, ancak yalnızca döndürülecek `IsEOF` sıfır olmayan zaten. Durumu `IsEOF` her zaman değişmeden kalır. Yeni bir kayıt sonra geçerli kaydı eklenmiş şekilde boş bir kayıt kümesinin geçerli kayıt işaretçisi Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi bir dosya sonunda olup.  
  
-   Tüm **silmek** çağrı, bir kayıt kümesinden yalnızca kalan kaydı kaldırır olsa bile değiştirmez değerini `IsBOF` veya `IsEOF`.  
  
 Bu tablo gösterir farklı bileşimleri ile hangi taşıma işlemlerine izin `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> < 0 taşıma|0 taşıma|MoveNext,<br /><br /> > 0 taşıma|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`sıfır olmayan =<br /><br /> `IsEOF`=0|İzin verilen|Özel Durum|Özel Durum|İzin verilen|  
|`IsBOF`=0,<br /><br /> `IsEOF`sıfır olmayan =|İzin verilen|İzin verilen|Özel Durum|Özel Durum|  
|Her ikisi de sıfır olmayan|Özel Durum|Özel Durum|Özel Durum|Özel Durum|  
|Her iki 0|İzin verilen|İzin verilen|İzin verilen|İzin verilen|  
  
 Bir taşıma işlemi izin verme işlemi başarılı bir şekilde bir kayıt bulmak anlamına gelmez. Yalnızca belirtilen taşıma işlemi gerçekleştirme girişimi izin verilir ve bir özel durum oluşturmayacağını belirtir. Değeri `IsBOF` ve `IsEOF` üye işlevleri sonucunda denenen taşıma değişebilir.  
  
 Bir kayıt değeri üzerinde bulundurmayın taşıma işlemleri etkisini `IsBOF` ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**, `MoveLast`|Sıfır olmayan|Sıfır olmayan|  
|**Taşıma** 0|Değişiklik yok|Değişiklik yok|  
|`MovePrev`, **Taşıma** < 0|Sıfır olmayan|Değişiklik yok|  
|`MoveNext`, **Taşıma** > 0|Değişiklik yok|Sıfır olmayan|  
  
 İlgili bilgi için Ek Yardım konusuna "BOF, EOF özellikleri" DAO Yardımı'nda.  
  
##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted  
 Geçerli kayıt silinmiş olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi silinmiş bir kayda konumlandırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir kayda kaydırırsanız ve `IsDeleted` döndürür **TRUE** başka herhangi bir kayıt işlemini gerçekleştirmeden önce (sıfır), ardından başka bir kayıtla kaydırma gerekir.  
  
> [!NOTE]
>  Anlık görüntü veya tablo türü kayıt kümesindeki kayıtları silinen durumunu denetlemek gerekmez. Bir anlık görüntüden kayıtlar silinemez çünkü çağırmak için gerek yoktur `IsDeleted`. Tablo türündeki kayıt kümeleri için silinen kayıtlar gerçekten kayıt kümesinden kaldırılır. Bir kayıt, başka bir kullanıcı tarafından veya başka bir kayıt kümesi silindikten sonra geri kayda gidemez. Bu nedenle, çağırmak için gerek yoktur `IsDeleted`.  
  
 Dynaset bir kaydı sildiğinizde, kayıt kümesinden kaldırılır ve yeniden kayda'e gidin. Ancak, bir kayıt bir dynaset başka bir kullanıcı tarafından veya başka bir kayıt kümesi aynı tabloya dayalı silinir `IsDeleted` döndürülecek **TRUE** olduğunda, daha sonra kaydırın kayda.  
  
 İlgili bilgiler için "Delete yöntemini", "LastModified özelliği" ve "EditMode özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="iseof"></a>  CDaoRecordset::IsEOF  
 Kayıt kümesi son kaydı ilerlemiş olup olmadığını öğrenmek için kayıt kaydından kaydırın gibi bu üye işlevini çağırın.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt kümesi hiçbir kayıt içeriyorsa veya son kaydı kaydırırsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrıca, çağırabilirsiniz `IsEOF` kayıt herhangi bir kayıt içeren boş olup olmadığını belirlemek için. Çağırdıktan hemen sonra **açık**, kayıt kümesinin hiçbir kayıt içeriyorsa `IsEOF` sıfır olmayan bir değer döndürür. En az bir kayda sahip bir kayıt kümesi açtığınızda, ilk kayıt geçerli kayıttır ve `IsEOF` 0 döndürür.  
  
 Çağırdığınızda son kaydı geçerli kayıt olup olmadığını `MoveNext`, `IsEOF` sonradan sıfır olmayan bir değer döndürür. Varsa `IsEOF` sıfır verir ve arama `MoveNext`, bir özel durum. Varsa `IsEOF` sıfır olmayan döndürür, geçerli kayıt tanımsızdır ve geçerli bir kayıt gerektirir herhangi bir eylem bir özel durum oluşur.  
  
 Belirli yöntemler etkisini `IsBOF` ve `IsEOF` ayarları:  
  
-   Çağırma **açık** dahili olarak ilk kaydı kayıt kümesindeki geçerli kayıt çağırarak yapar **MoveFirst**. Bu nedenle, çağırma **açık** kayıtları nedenler boş dizi `IsBOF` ve `IsEOF` sıfır olmayan dönün. (Başarısız davranışını için aşağıdaki tabloya bakın **MoveFirst** çağırın.)  
  
-   Kaydı başarıyla yerleştirmek tüm taşıma işlemleri hem neden `IsBOF` ve `IsEOF` 0 dönün.  
  
-   Bir `AddNew` çağrı tarafından izlenen bir **güncelleştirme** başarıyla yeni bir kayıt ekler çağrısı neden olacak `IsBOF` 0, ancak yalnızca döndürülecek `IsEOF` sıfır olmayan zaten. Durumu `IsEOF` her zaman değişmeden kalır. Yeni bir kayıt sonra geçerli kaydı eklenmiş şekilde boş bir kayıt kümesinin geçerli kayıt işaretçisi Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi bir dosya sonunda olup.  
  
-   Tüm **silmek** çağrı, bir kayıt kümesinden yalnızca kalan kaydı kaldırır olsa bile değiştirmez değerini `IsBOF` veya `IsEOF`.  
  
 Bu tablo gösterir farklı bileşimleri ile hangi taşıma işlemlerine izin `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> < 0 taşıma|0 taşıma|MoveNext,<br /><br /> > 0 taşıma|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`sıfır olmayan =<br /><br /> `IsEOF`=0|İzin verilen|Özel Durum|Özel Durum|İzin verilen|  
|`IsBOF`=0,<br /><br /> `IsEOF`sıfır olmayan =|İzin verilen|İzin verilen|Özel Durum|Özel Durum|  
|Her ikisi de sıfır olmayan|Özel Durum|Özel Durum|Özel Durum|Özel Durum|  
|Her iki 0|İzin verilen|İzin verilen|İzin verilen|İzin verilen|  
  
 Bir taşıma işlemi izin verme işlemi başarılı bir şekilde bir kayıt bulmak anlamına gelmez. Yalnızca belirtilen taşıma işlemi gerçekleştirme girişimi izin verilir ve bir özel durum oluşturmayacağını belirtir. Değeri `IsBOF` ve `IsEOF` üye işlevleri sonucunda denenen taşıma değişebilir.  
  
 Bir kayıt değeri üzerinde bulundurmayın taşıma işlemleri etkisini `IsBOF` ve `IsEOF` ayarları aşağıdaki tabloda gösterilmiştir.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**, `MoveLast`|Sıfır olmayan|Sıfır olmayan|  
|**Taşıma** 0|Değişiklik yok|Değişiklik yok|  
|`MovePrev`, **Taşıma** < 0|Sıfır olmayan|Değişiklik yok|  
|`MoveNext`, **Taşıma** > 0|Değişiklik yok|Sıfır olmayan|  
  
 İlgili bilgi için Ek Yardım konusuna "BOF, EOF özellikleri" DAO Yardımı'nda.  
  
##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty  
 Bir dinamik belirtilen alan veri üyesi "kirli" olarak işaretlendi olup olmadığını belirlemek için (değiştirilmiş) Bu üye işlevini çağırın.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** alanlar kirli olup olmadığını belirlemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alan veri üyesi kirli olarak işaretlenmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli kayıt için bir çağrı tarafından güncelleştirildiğinde tüm kirli alan veri üyeleri verilerde kayda veri kaynağında aktarılacak **güncelleştirme** üye işlevini `CDaoRecordset` (bir çağrısından **Düzenle**veya `AddNew`). Bu bilgiyle, ek adımlar, gibi yapabileceğiniz unflagging veri kaynağına yazılmayacak şekilde sütun işaretlemek için alan veri üyesi.  
  
 `IsFieldDirty` aracılığıyla uygulanır `DoFieldExchange`.  
  
##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull  
 Bir kayıt kümesi belirtilen alan veri üyesi Null olarak işaretlenmiş olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** tüm alanları boş olup olmadığını belirlemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alan veri üyesi boş olarak işaretlenmişse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 (Veritabanı terminolojisinde Null "değer olan" anlamına gelir ve aynı değil **NULL** c++.) Alan veri üyesi boş olarak işaretlenmişse, kendisi için değer yoktur geçerli kaydı bir sütun olarak yorumlanır.  
  
> [!NOTE]
>  Bazı durumlarda, kullanarak `IsFieldNull` aşağıdaki kod örneğinde gösterildiği gibi verimsiz, olabilir:  
  
 [!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  Türetme olmadan dinamik kayıt bağlama kullanıyorsanız, `CDaoRecordset`, kullandığınızdan emin olun **VT_NULL** örnekte gösterildiği gibi.  
  
##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable  
 Belirtilen alan veri üyesi "NULL" olup olmadığını belirlemek için (bir Null değere; ayarlayın olabilir bu üye işlevini çağırın C++ **NULL** Veritabanı terminolojisinde anlamına gelir, Null ile aynı değil "herhangi bir değer olan").  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Durumu denetlemek istediğiniz alan veri üyesi için bir işaretçi veya **NULL** tüm alanları boş olup olmadığını belirlemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen alan veri üyesi Null yapılabilir, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Null olamaz bir alan bir değer içermelidir. Böyle bir alan ekleyerek veya bir kayıt güncelleştirilirken Null olarak ayarlamak çalışırsanız, veri kaynağı ekleme veya güncelleştirme, reddeder ve **güncelleştirme** bir özel durum oluşturur. Çağırdığınızda özel durum oluşur **güncelleştirme**, değil çağırdığınızda `SetFieldNull`.  
  
##  <a name="isopen"></a>  CDaoRecordset::IsOpen  
 Kayıt kümesi açık olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF kayıt kümesi nesnesinin **açık** veya **Requery** üye işlevi önceden çağrılıp çağrılmadığını ve kayıt kapalı değil; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset::m_bCheckCacheForDirtyFields  
 Önbelleğe alınan alanları otomatik olarak kirli olarak (değiştirilmiş) işaretlenen olup olmadığını belirten bir bayrak içeriyor ve Null.  
  
### <a name="remarks"></a>Açıklamalar  
 Bayrak varsayılan olarak **doğru**. Bu veri üyesi ayarında tüm çift arabelleğe alma mekanizması denetler. Bayrağı ayarlarsanız **doğru**, DFX mekanizmasını kullanarak bir alan alanını temelinde önbelleğe almayı devre dışı bırakabilir. Bayrağı ayarlarsanız **FALSE**, çağırmalısınız `SetFieldDirty` ve `SetFieldNull` kendiniz.  
  
 Çağırmadan önce bu veri üye kümesi **açık**. Öncelikle--kullanım kolaylığı için mekanizmadır. Performans yapılan bir değişiklik gibi daha yavaş İkili Önbellekleme nedeniyle alanlarının olabilir.  
  
##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields  
 Kayıt kümesi sınıfında yer alan veri üyeleri sayısı ve veri kaynağından kayıt kümesi tarafından seçilen sütunların sayısını içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi sınıfı oluşturucusu başlatmalıdır `m_nFields` statik olarak bağlı alanlar doğru sayısıyla. Kayıt kümesi sınıfınızı bildirmek için kullandığınızda, bu başlatma ClassWizard yazar. Ayrıca, el ile yazabilirsiniz.  
  
 Çerçeve alan veri üyeleri geçerli kayıt veri kaynağı için karşılık gelen sütunlara arasındaki etkileşimi yönetmek için bu sayıyı kullanır.  
  
> [!NOTE]
>  Bu sayı kayıtlı çıktı sütun sayısı karşılık gelmelidir `DoFieldExchange` çağrısı yapıldıktan sonra `SetFieldType` parametresiyle **CDaoFieldExchange::outputColumn**.  
  
 Sütunları dinamik olarak tarafından yolu bağlayabilirsiniz `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue`. Bunu yaparsanız, sayısı artırılamıyor gerekmez `m_nFields` DFX işlevi sayısı çağrıları yansıtacak şekilde, `DoFieldExchange` üye işlevi.  
  
##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams  
 Kayıt kümesi sınıfında parametre veri üyeleri sayısını içerir — parametrelerin sayısı geçirilen kümesinin sorgu.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi sınıfınız herhangi bir parametre veri üyesi varsa, sınıf oluşturucusu başlatmalıdır `m_nParams` doğru numarasına sahip. Değeri `m_nParams` varsayılan ayar: 0. Parametre veri üyeleri eklerseniz —, el ile yapmanız gerekir — bir başlatma parametreleri numarasını yansıtacak şekilde sınıfı oluşturucuda de el ile eklemeniz gerekir (olması gerekir en az sayıda büyüklüğünde '' yer tutucuları, **m_strFilter**  veya `m_strSort` dize).  
  
 Çerçeve kümesinin sorgusunu parameterizes bu sayıyı kullanır.  
  
> [!NOTE]
>  Bu sayı "kayıtlı params" sayısı karşılık gelmelidir `DoFieldExchange` çağrısı yapıldıktan sonra `SetFieldType` parametresiyle **CFieldExchange::param**.  
  
 İlgili bilgi için DAO Yardımı'ndaki "parametre nesnesi" konusuna bakın.  
  
##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset  
 DAO kayıt kümesi nesnesi temel için OLE arabirimi için bir işaretçi içeriyor `CDaoRecordset` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 DAO arabirimi doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.  
  
 İlgili bilgi için DAO Yardımı'ndaki "kayıt kümesi nesnesi" konusuna bakın.  
  
##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase  
 Bir işaretçi içeriyor `CDaoDatabase` üzerinden kayıt bağlı bir veri kaynağı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değişken, iki şekilde ayarlanır. Genellikle, bir işaretçi bir zaten açık geçirdiğiniz `CDaoDatabase` nesne olduğunda kayıt kümesi nesnesi oluşturun. Geçirirseniz **NULL** bunun yerine, **CDaoRecordset** oluşturur bir `CDaoDatabase` nesnesi ve açar. Her iki durumda da `CDaoRecordset` işaretçinin bu değişkeninde depolar.  
  
 Normalde, doğrudan depolanan işaretçiyi kullanın gerekmez **m_pDatabase**. Kendi uzantıları yazarsanız `CDaoRecordset`, ancak işaretçiyi kullanmanız gerekebilir. Throw, örneğin, işaretçi kendi gereksiniminiz olabilir `CDaoException`(s).  
  
 İlgili bilgi için DAO Yardımı'ndaki "veritabanı nesnesi" konusuna bakın.  
  
##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter  
 Oluşturmak için kullanılan bir dize içeriyor **burada** SQL deyiminin yan tümcesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Özel amaçlı sözcük içermez **burada** kayıt kümesini filtrelemek için. Bu veri üyesi kullanımını tablo türü kayıt kümeleri için geçerli değildir. Kullanımını **m_strFilter** kullanarak bir kayıt kümesi açarken etkisizdir bir `CDaoQueryDef` işaretçi.  
  
 ABD tarih biçimini (ay-gün-yıl) kullanan Microsoft Jet veritabanı altyapısı; ABD sürümünü kullanmıyorsanız bile tarihleri içeren alanlar filtre beklediğiniz gibi Aksi halde, verileri filtre uygulanabilir değildir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "filtre özelliği" konusuna bakın.  
  
##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort  
 İçeren bir dize içeriyor **ORDERBY** ayrılmış sözcükler olmadan SQL deyiminin yan tümcesinde **ORDERBY**.  
  
### <a name="remarks"></a>Açıklamalar  
 Dynaset ve anlık görüntü türü kayıt kümesi nesnelerde sıralayabilirsiniz.  
  
 Tablo türündeki kayıt kümesi nesneleri sıralanamaz. Tablo türündeki kayıt kümesi sıralama düzenini belirlemek için arama [SetCurrentIndex](#setcurrentindex).  
  
 Kullanımını `m_strSort` kullanarak bir kayıt kümesi açarken etkisizdir bir `CDaoQueryDef` işaretçi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "sıralama özelliği" konusuna bakın.  
  
##  <a name="move"></a>  CDaoRecordset::Move  
 Kayıt kümesi konumlandırmak için bu üye işlevini çağırın `lRows` geçerli kayıttan kaydeder.  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>Parametreler  
 `lRows`  
 İleriye veya geriye doğru taşımak için kayıt sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru gitmenizi sağlar. Negatif değerler geriye doğru başına doğru taşıyın.  
  
### <a name="remarks"></a>Açıklamalar  
 İleriye veya geriye doğru taşıyabilirsiniz. `Move( 1 )` eşdeğer olan `MoveNext`, ve `Move( -1 )` eşdeğerdir `MovePrev`.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de çağrısı `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işlemi önce. Çağırdıktan sonra **açık** veya **Requery**, ya da çağrısı `IsBOF` veya `IsEOF`.  
  
> [!NOTE]
>  Başında ve sonunda kayıt kümesinin kaydırılan varsa ( `IsBOF` veya `IsEOF` sıfır olmayan döndürür), bir çağrı **taşıma** oluşturur bir `CDaoException`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Çağırdığınızda **taşıma** bir salt iletme kaydırma anlık görüntüsü üzerinde `lRows` parametresi pozitif bir tamsayı olmalıdır ve yer işaretleri izin verilmez, İleri yalnızca taşıyabilirsiniz şekilde.  
  
 İlk, son yapmak için sonraki veya önceki bir kayıt kümesindeki geçerli kayıt, çağrı kayıt **MoveFirst**, `MoveLast`, `MoveNext`, veya `MovePrev` üye işlevi.  
  
 İlgili bilgi için "Move yöntemini" konulara bakın ve "MoveFirst, MoveLast, MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.  
  
##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst  
 İlk kaydı kayıt kümesinde (varsa) yapmak için bu üye işlev çağrısı geçerli kayıt.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı gerekmez **MoveFirst** kayıt açtıktan hemen sonra. O anda ilk kayıt (varsa) otomatik olarak geçerli kayıttır.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de çağrısı `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işlemi önce. Çağırdıktan sonra **açık** veya **Requery**, ya da çağrısı `IsBOF` veya `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kullanım **taşıma** bir koşul uygulamadan kayıt kaydı taşımak için işlevleri. Dynaset türü ya da belirli bir koşulla karşılayan anlık görüntü türündeki kayıt kümesi nesnesi kayıtları bulmak için bulma işlemleri kullanın. Bir tablo türündeki kayıt kümesi nesnesi bir kayıt bulmak için arama `Seek`.  
  
 Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. DAO nesnesini Index özelliğini kullanarak, geçerli dizin ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız döndürülen kayıtların sırası tanımlanmamıştır.  
  
 Çağırırsanız `MoveLast` bir SQL sorgusu veya querydef dayanan bir kayıt kümesi nesnesi üzerinde sorgu tamamlanıncaya kadar zorlanır ve kayıt kümesi nesnesi tam olarak doldurulur.  
  
 Çağıramazsınız **MoveFirst** veya `MovePrev` üye işlevi yalnızca ileri kaydırma anlık görüntüleri.  
  
 Geçerli konumunu kaydı bir kayıt kümesi nesnesi belirli bir ileriye doğru kayıt sayısı veya geri taşımak için arama **taşıma**.  
  
 İlgili bilgi için "Move yöntemini" konulara bakın ve "MoveFirst, MoveLast, MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.  
  
##  <a name="movelast"></a>  CDaoRecordset::MoveLast  
 Bu üye işlevi (varsa) son kaydı yapmak için kayıt kümesindeki geçerli kayıt çağırın.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de çağrısı `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işlemi önce. Çağırdıktan sonra **açık** veya **Requery**, ya da çağrısı `IsBOF` veya `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kullanım **taşıma** bir koşul uygulamadan kayıt kaydı taşımak için işlevleri. Dynaset türü ya da belirli bir koşulla karşılayan anlık görüntü türündeki kayıt kümesi nesnesi kayıtları bulmak için bulma işlemleri kullanın. Bir tablo türündeki kayıt kümesi nesnesi bir kayıt bulmak için arama `Seek`.  
  
 Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. DAO nesnesini Index özelliğini kullanarak, geçerli dizin ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız döndürülen kayıtların sırası tanımlanmamıştır.  
  
 Çağırırsanız `MoveLast` bir SQL sorgusu veya querydef dayanan bir kayıt kümesi nesnesi üzerinde sorgu tamamlanıncaya kadar zorlanır ve kayıt kümesi nesnesi tam olarak doldurulur.  
  
 Geçerli konumunu kaydı bir kayıt kümesi nesnesi belirli bir ileriye doğru kayıt sayısı veya geri taşımak için arama **taşıma**.  
  
 İlgili bilgi için "Move yöntemini" konulara bakın ve "MoveFirst, MoveLast, MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.  
  
##  <a name="movenext"></a>  CDaoRecordset::MoveNext  
 Kayıt kümesindeki geçerli kayıt sonraki kaydı yapmak için bu üye işlevini çağırın.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sizi aramasını önerilir `IsBOF` önceki kayda girişiminde bulunmadan önce. Çağrı `MovePrev` özel durum oluşturacak bir `CDaoException` varsa `IsBOF` önce ilk kaydı zaten kaydırılan veya hiçbir kayıt kayıt kümesi tarafından seçilmedi gösteren sıfır döndürür.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de çağrısı `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işlemi önce. Çağırdıktan sonra **açık** veya **Requery**, ya da çağrısı `IsBOF` veya `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kullanım **taşıma** bir koşul uygulamadan kayıt kaydı taşımak için işlevleri. Dynaset türü ya da belirli bir koşulla karşılayan anlık görüntü türündeki kayıt kümesi nesnesi kayıtları bulmak için bulma işlemleri kullanın. Bir tablo türündeki kayıt kümesi nesnesi bir kayıt bulmak için arama `Seek`.  
  
 Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. DAO nesnesini Index özelliğini kullanarak, geçerli dizin ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız döndürülen kayıtların sırası tanımlanmamıştır.  
  
 Geçerli konumunu kaydı bir kayıt kümesi nesnesi belirli bir ileriye doğru kayıt sayısı veya geri taşımak için arama **taşıma**.  
  
 İlgili bilgi için "Move yöntemini" konulara bakın ve "MoveFirst, MoveLast, MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.  
  
##  <a name="moveprev"></a>  CDaoRecordset::MovePrev  
 Önceki kaydın kayıt kümesindeki geçerli kayıt yapmak için bu üye işlevini çağırın.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Sizi aramasını önerilir `IsBOF` önceki kayda girişiminde bulunmadan önce. Çağrı `MovePrev` özel durum oluşturacak bir `CDaoException` varsa `IsBOF` önce ilk kaydı zaten kaydırılan veya hiçbir kayıt kayıt kümesi tarafından seçilmedi gösteren sıfır döndürür.  
  
> [!CAUTION]
>  Herhangi bir arama **taşıma** işlevleri, hiçbir kayıt kayıt varsa, bir özel durum oluşturur. Genel olarak, her ikisi de çağrısı `IsBOF` ve `IsEOF` kayıt herhangi bir kayıt olup olmadığını belirlemek için bir taşıma işlemi önce. Çağırdıktan sonra **açık** veya **Requery**, ya da çağrısı `IsBOF` veya `IsEOF`.  
  
> [!NOTE]
>  Herhangi bir çağırırsanız **taşıma** geçerli kayıt yüklenirken işlevleri güncelleştirilmiş veya eklenir, güncelleştirmelerinin uyarı olmadan kaybolacaktır.  
  
 Kullanım **taşıma** bir koşul uygulamadan kayıt kaydı taşımak için işlevleri. Dynaset türü ya da belirli bir koşulla karşılayan anlık görüntü türündeki kayıt kümesi nesnesi kayıtları bulmak için bulma işlemleri kullanın. Bir tablo türündeki kayıt kümesi nesnesi bir kayıt bulmak için arama `Seek`.  
  
 Kayıt kümesi için bir tablo türü kayıt başvuruyorsa, taşıma tablonun geçerli dizin izler. DAO nesnesini Index özelliğini kullanarak, geçerli dizin ayarlayabilirsiniz. Geçerli dizin ayarlamazsanız döndürülen kayıtların sırası tanımlanmamıştır.  
  
 Çağıramazsınız **MoveFirst** veya `MovePrev` üye işlevi yalnızca ileri kaydırma anlık görüntüleri.  
  
 Geçerli konumunu kaydı bir kayıt kümesi nesnesi belirli bir ileriye doğru kayıt sayısı veya geri taşımak için arama **taşıma**.  
  
 İlgili bilgi için "Move yöntemini" konulara bakın ve "MoveFirst, MoveLast, MoveNext, MovePrevious Yöntemleri" DAO Yardımı'nda.  
  
##  <a name="open"></a>  CDaoRecordset::Open  
 Kayıt kümesi için kayıtları almak için bu üye işlevini çağırmanız gerekir.  
  
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
 `nOpenType`  
 Aşağıdaki değerlerden biri:  
  
- **dbOpenDynaset** çift yönlü kaydırma ile dynaset türü kayıt. Bu varsayılandır.  
  
- **dbOpenTable** çift yönlü kaydırma içeren bir tablo türü kayıt.  
  
- **dbOpenSnapshot** çift yönlü kaydırma ile bir anlık görüntü türündeki kayıt kümesi.  
  
 `lpszSQL`  
 Aşağıdakilerden birini içeren bir dize işaretçi:  
  
-   A **NULL** işaretçi.  
  
-   Bir veya daha fazla tabledefs ve/veya querydefs (virgülle ayrılmış) adı.  
  
-   Bir SQL **seçin** deyimi (isteğe bağlı olarak bir SQL **nerede** veya **ORDERBY** yan tümcesi).  
  
-   Bir doğrudan geçirilen sorgu.  
  
 `nOptions`  
 Bir veya daha fazla aşağıda listelenen seçenekleri. Varsayılan değer 0’dır. Olası değerler aşağıdaki gibidir:  
  
- **dbAppendOnly** yalnızca yeni kayıtları (yalnızca değişken küme türündeki kayıt kümesi) ekleyebilirsiniz. Bu seçenek tam anlamıyla kayıtları yalnızca eklenebilir anlamına gelir. MFC ODBC veritabanı sınıfları alınır ve eklenmiş kayıtlarını veren yalnızca ekleme seçeneğiniz vardır.  
  
- **dbForwardOnly** kayıt kümesi yalnızca ileri kaydırma anlık görüntüsüdür.  
  
- **dbSeeChanges** başka bir kullanıcı verileri düzenlemekte değiştiriyorsa bir özel durum oluşturur.  
  
- **dbDenyWrite** diğer kullanıcıların değiştirin veya kayıtları ekleyin.  
  
- **dbDenyRead** diğer kullanıcıların kayıtları (yalnızca tablo türündeki kayıt kümesi) görüntüleyemezsiniz.  
  
- **dbReadOnly** yalnızca kayıtlarını görüntüleyebilirsiniz; diğer kullanıcıların bunları değiştirebilirsiniz.  
  
- **dbInconsistent** tutarsız güncelleştirmeler (yalnızca değişken küme türündeki kayıt kümesi) izin verilir.  
  
- **dbConsistent** yalnızca tutarlı güncelleştirmeleri (yalnızca değişken küme türündeki kayıt kümesi) izin verilir.  
  
> [!NOTE]
>  Sabitler **dbConsistent** ve **dbInconsistent** karşılıklı olarak birbirini dışlar. Kullanabilirsiniz veya diğer, ancak ikisini birlikte, belirli bir örneğinde **açık**.  
  
 *pTableDef*  
 Bir işaretçi bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi. Bu sürümü yalnızca tablo türü kayıt kümeleri için geçerli değildir. Bu seçenek kullanıldığında `CDaoDatabase` oluşturmak için kullanılan işaretçi `CDaoRecordset` kullanılmaz; bunun yerine, tabledef bulunduğu veritabanı kullanılır.  
  
 *pQueryDef*  
 Bir işaretçi bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesi. Bu sürümü yalnızca dynaset türü ve anlık görüntü türü kayıt kümeleri için geçerli değildir. Bu seçenek kullanıldığında `CDaoDatabase` oluşturmak için kullanılan işaretçi `CDaoRecordset` kullanılmaz; bunun yerine, querydef bulunduğu veritabanı kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmadan önce **açık**, kayıt kümesi nesnesi oluşturmalıdır. Bunu yapmanın birkaç yolu vardır:  
  
-   Kayıt kümesi nesnesi oluşturmak zaman gösteren bir işaretçi başarılı bir `CDaoDatabase` zaten açık olan nesne.  
  
-   Kayıt kümesi nesnesi oluşturmak zaman gösteren bir işaretçi başarılı bir `CDaoDatabase` açık olmadığından nesne. Kayıt kümesi açılır bir `CDaoDatabase` nesnesi, ancak kayıt kümesi nesnesi kapandığında kapanmaz.  
  
-   Kayıt kümesi nesnesi oluşturmak zaman başarılı bir **NULL** işaretçi. Kayıt kümesi nesnesi çağrıları `GetDefaultDBName` Microsoft Access adını almak için. MDB dosyayı açın. Kayıt kümesi ardından açar bir `CDaoDatabase` nesne ve kayıt kümesi açık olduğu sürece açmadan tutar. Çağırdığınızda **Kapat** kayıt kümesinde `CDaoDatabase` nesnesi de kapalı.  
  
    > [!NOTE]
    >  Kayıt kümesi açıldığında `CDaoDatabase` nesnesi, özel kullanım erişimi ile veri kaynağı açar.  
  
 Sürümü için **açmak** kullanan `lpszSQL` parametresi, kayıt kümesinin açıldıktan sonra çeşitli yollardan kayıtlarında alabilirsiniz. DFX işlevleri sağlamak için ilk seçeneğidir, `DoFieldExchange`. İkinci seçenek Dinamik bağlama çağırarak kullanmaktır `GetFieldValue` üye işlevi. Bu seçenekler, ayrı ayrı veya birlikte uygulanabilir. Bunlar birlikte varsa SQL deyiminde kendiniz çağrısı aktarmak gerekecektir **açık**.  
  
 İkinci sürümü kullandığınızda **açık** geçirmek burada bir `CDaoTableDef` nesnesi, sonuçta elde edilen sütunları, aracılığıyla bağlamak kullanılabilir olacak `DoFieldExchange` ve DFX mekanizması ve/veya dinamik olarak aracılığıyla bağlama `GetFieldValue`.  
  
> [!NOTE]
>  Yalnızca çağırabilir **açık** kullanarak bir `CDaoTableDef` tablo türü kayıt kümeleri için nesnesi.  
  
 Üçüncü sürümünü kullandığınızda, **açık** geçirmek burada bir `CDaoQueryDef` nesne, sorgu yürütülür ve sonuçta elde edilen sütunları, aracılığıyla bağlamak kullanılabilir olacak `DoFieldExchange` ve DFX mekanizması ve/veya dinamik olarak bağlama aracılığıyla `GetFieldValue`.  
  
> [!NOTE]
>  Yalnızca çağırabilir **açık** kullanarak bir `CDaoQueryDef` dynaset türü ve anlık görüntü türü kayıt kümeleri için nesnesi.  
  
 İlk sürümü için **açık** kullanan `lpszSQL` parametresi kayıtlarıdır aşağıdaki tabloda gösterilen seçili göre ölçütleri.  
  
|Değeri `lpszSQL` parametresi|Seçilen kayıt tarafından belirlenir|Örnek|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|Tarafından döndürülen dize `GetDefaultSQL`.||  
|Bir veya daha fazla tabledefs ve/veya querydef adlarının virgülle ayrılmış listesi.|Tüm sütunları temsil `DoFieldExchange`.|`"Customer"`|  
|**SEÇİN** sütun listesi **FROM** Tablo listesi|Belirtilen sütunları belirtilen tabledef(s) ve/veya querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 Normal yordamını geçirmektir **NULL** için **açık**; bu durumda, **açık** çağrıları `GetDefaultSQL`, ClassWizard oluştururken oluşturan bir geçersiz kılınabilir üye işlevi bir `CDaoRecordset`-türetilmiş sınıf. Bu değer ClassWizard içinde belirtilen tabledef(s) ve/veya querydef adları sağlar. Bunun yerine diğer bilgileri belirtebilirsiniz `lpszSQL` parametresi.  
  
 Ne olursa olsun geçirdiğiniz **açık** bir son sorgu SQL dizesi oluşturur (dize SQL olabilir **nerede** ve **ORDERBY** yan tümceleri eklenmiş için `lpszSQL` , dize geçirilen) ve ardından sorguyu çalıştırır. Çağrılarak oluşturulan dize inceleyebilirsiniz `GetSQL` çağırdıktan sonra **açık**.  
  
 Kayıt kümesi sınıfınız alan veri üyeleri, seçtiğiniz veri sütunlarının bağlıdır. Hiçbir kayıt döndürülmezse, ilk kaydı geçerli kaydı olur.  
  
 Filtre veya sıralama gibi kayıt seçeneklerini ayarlamak istiyorsanız `m_strSort` veya **m_strFilter** kayıt kümesi nesnesi oluşturun sonra ancak çağırmadan önce **açık**. Sonra kayıt kümesindeki kayıtları yenilemek istiyorsanız kayıt kümesi zaten açık, çağrı **Requery**.  
  
 Çağırırsanız **açık** dynaset türü veya anlık görüntü türündeki kayıt kümesi veya veri kaynağı bir SQL deyimi veya ekli bir tablo temsil eden bir tabledef başvuruyorsa kullanamazsınız **dbOpenTable** türü için bağımsız değişken; Bunu yaparsanız, MFC özel durum oluşturur. Tabledef nesnesi ekli bir tablo temsil edip etmediğini belirlemek için oluşturun bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesne ve çağrı kendi [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevi.  
  
 Kullanım **dbSeeChanges** düzenlerken veya aynı kayıt silme başka bir kullanıcı veya makinenizde başka bir program tarafından yapılan değişiklikleri yakalamak isterseniz bayrak. Örneğin, iki kullanıcı aynı kaydı çağırmak için ilk kullanıcı düzenleme başlatırsanız **güncelleştirme** üye işlevi başarılı olur. Zaman **güncelleştirme** ikinci kullanıcı tarafından adlı bir `CDaoException` oluşturulur. Benzer şekilde, ikinci kullanıcı çağırmak çalışırsa **silmek** kaydı ve silmek için zaten ilk kullanıcı tarafından değiştirildi bir `CDaoException` oluşur.  
  
 Genellikle, kullanıcı bu alırsa `CDaoException` güncelleştirilirken, kodunuzu alanların içeriği yenileyin ve yeni değiştirilen değerleri alma. Silme sürecinde özel durum oluşursa, kodunuzu yeni verileri kaydetmek için kullanıcı ve verileri yakın zamanda değiştiğini belirten bir ileti görüntüleyebilirsiniz. Bu noktada, kodunuzu kullanıcı hala kaydını silmek istediğini için onay isteyebilir.  
  
> [!TIP]
>  Yalnızca iletme kaydırma seçeneği kullanın ( **dbForwardOnly**) uygulamanız bir kayıt kümesi tek bir geçiş yaptığında, performansı artırmak için bir ODBC veri kaynağından açılır.  
  
 İlgili bilgi için DAO Yardımı'ndaki "OpenRecordset yöntemi" konusuna bakın.  
  
##  <a name="requery"></a>  CDaoRecordset::Requery  
 Bu üye işlevi (yenileme) yeniden oluşturmak için bir kayıt kümesi çağırın.  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir kayıt döndürülmezse, ilk kaydı geçerli kaydı olur.  
  
 Kayıt kümesinin ekleme ve siz veya diğer kullanıcılar için veri kaynağı kuran silmeleri yansıtmak sırayla çağırarak kayıt döndürmelisiniz **Requery**. Kayıt kümesi bir dinamik ise, sizin veya diğer kullanıcıların kendi mevcut kayıtları (ancak değil eklemeleri) olun güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi bir anlık görüntü ise, çağırmalısınız **Requery** diğer kullanıcıların yanı sıra ekleme ve silme işlemleri tarafından düzenlemeleri yansıtmak için.  
  
 Dinamik küme veya anlık görüntü için çağrı **Requery** parametre değerlerini kullanarak kayıt yeniden oluşturmak için istediğiniz zaman. Yeni bir filtre veya sıralama ayarlamak için [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) çağırmadan önce **Requery**. Parametre veri üyeleri çağırmadan önce yeni değerleri atayarak yeni parametreler Ayarla **Requery**.  
  
 Kayıt kümesi yeniden denemesi başarısız olursa, kayıt kümesinin kapalı. Çağırmadan önce **Requery**, kayıt kümesinin çağırarak yeniden olup olmadığını belirlemek [CanRestart](#canrestart) üye işlevi. `CanRestart` garanti etmez **Requery** başarılı olur.  
  
> [!CAUTION]
>  Çağrı **Requery** yalnızca adlı sonra **açık**.  
  
> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.  
  
 Çağıramazsınız **Requery** dynaset türü veya çağrılırken, anlık görüntü türündeki kayıt kümesi `CanRestart` 0 döndürür veya bir tablo türü kayıt kümesinde kullanabilirsiniz.  
  
 Her iki `IsBOF` ve `IsEOF` çağırdıktan sonra sıfır olmayan dönmek **Requery**, tüm kayıtlar ve kayıt hiçbir veri içerecek sorgu döndürmedi.  
  
 İlgili bilgi için "Requery yöntemi" DAO Yardım konusuna bakın.  
  
##  <a name="seek"></a>  CDaoRecordset::Seek  
 Belirtilen ölçüt için geçerli dizini oluşturmak ve geçerli kayıt kaydeden olun karşılayan bir dizinlenmiş tablo türü kayıt kümesi nesnesinde kaydı bulmak için bu üye işlevini çağırın.  
  
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
 `lpszComparison`  
 Aşağıdaki dize ifadelerden biri: "<","\<=", "=" "> =", veya ">".  
  
 `pKey1`  
 Bir işaretçi bir [COleVariant](../../mfc/reference/colevariant-class.md) değeri ilk dizin alanında karşılık gelir. Gerekli.  
  
 *pKey2*  
 Bir işaretçi bir `COleVariant` değeri karşılık gelen dizin ikinci alan varsa. Varsayılan olarak **NULL**.  
  
 *pKey3*  
 Bir işaretçi bir `COleVariant` değeri karşılık gelen dizin üçüncü alanında varsa. Varsayılan olarak **NULL**.  
  
 *pKeyArray*  
 Çeşitleri dizisi için bir işaretçi. Dizi boyutu dizinindeki alan sayısını karşılık gelir.  
  
 *nKeys*  
 Dizin alanları sayısıdır dizinin boyutu karşılık gelen bir tam sayı.  
  
> [!NOTE]
>  Joker karakterler anahtarlarında belirtmeyin. Joker karakterler neden olacak `Seek` eşleşen kayıt yok dönün.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eşleşen kayıtları bulunduğunda, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci (dizi) sürümünü kullanmanız `Seek` dört alanlarının dizinleri ya da daha fazla işlemek için.  
  
 `Seek` yüksek performanslı dizin tablo türü kümelerinde arama sağlar. Geçerli dizin çağırarak ayarlamalısınız `SetCurrentIndex` çağırmadan önce `Seek`. Dizini benzersiz olmayan bir anahtar alan veya alanlar tanımlarsa `Seek` ölçütlerini karşılayan ilk kaydı bulur. Bir dizin ayarlanmazsa özel durum oluşur.  
  
 UNICODE kayıt oluşturmadığınızı gerçekleştiriyorsanız, `COleVariant` nesneleri ANSI açıkça da bildirilmelidir. Bu kullanılarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** biçiminde Oluşturucusu ile `vtSrc` kümesine `VT_BSTRT` (ANSI) kullanarak veya **COleVariant** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** ile `vtSrc` kümesine `VT_BSTRT`.  
  
 Çağırdığınızda `Seek`, bir veya daha fazla anahtar değerleri ve bir karşılaştırma işleci geçirdiğiniz ("<","\<=", "=" "> =", veya ">"). `Seek` Belirtilen anahtar alanlarından arar ve tarafından belirtilen ölçütleri karşılayan ilk kaydı bulur `lpszComparison` ve `pKey1`. Bir kez bulundu, `Seek` sıfır olmayan döndürür ve o kaydın geçerli hale getirir. Varsa `Seek` bir eşleşme bulamazsa `Seek` sıfır verir ve geçerli kayıt tanımsızdır. DAO doğrudan kullanırken NoMatch özelliği açıkça işaretlemeniz gerekir.  
  
 Varsa `lpszComparison` olan "=" "> =", veya ">", `Seek` dizini başında başlar. Varsa `lpszComparison` olan "<" veya "< =", `Seek` dizini sonunda başlar ve sonunda yinelenen dizin girişlerini olmadıkça geriye doğru arar. Bu durumda, `Seek` dizini sonunda yinelenen dizin girişlerini arasında rastgele bir giriş başlar.  
  
 Var. yok kullandığınızda geçerli bir kayıt olmasını `Seek`.  
  
 Dynaset türü ya da belirli bir koşula uygun anlık görüntü türündeki kayıt kümesi bir kayıt bulmak için bulma işlemleri kullanın. Yalnızca bu belirli bir koşulu karşılayan tüm kayıtları dahil etmek için kayıt kaydı taşımak için taşıma işlemleri kullanın.  
  
 Çağıramazsınız `Seek` herhangi ekli bir tablo üzerinde iliştirilmiş tablolar dynaset türü veya anlık görüntü türü kayıt kümeleri olarak açılması gerekir çünkü yazın. Ancak, çağırırsanız `CDaoDatabase::Open` doğrudan bir yüklenebilir ISAM veritabanı açmak için çağırabilirsiniz `Seek` performans olabilir ancak bu veritabanında tablolarda yavaşlatabilir.  
  
 İlgili bilgi için "Arama yönteminde" DAO Yardım konusuna bakın.  
  
##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition  
 Kayıt kümesi nesnesinin geçerli kayıt göreli kayıt sayısını ayarlar.  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>Parametreler  
 *lPosition*  
 Geçerli kayıt kümesinde sıralı konumuna karşılık gelir.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırma `SetAbsolutePosition` geçerli kayıt işaretçiyi dynaset türü veya anlık görüntü türündeki kayıt kümesi içindeki sıralı konumuna göre belirli bir kayda olanak tanır. Çağırarak geçerli kayıt numarası belirleyebilirsiniz [GetAbsolutePosition](#getabsoluteposition).  
  
> [!NOTE]
>  Bu üye işlevi yalnızca dynaset türü ve anlık görüntü türü kayıt kümeleri için geçerli değil.  
  
 DAO nesnesini AbsolutePosition özellik değerinin sıfır tabanlı olup; 0 ayarı, kayıt kümesindeki ilk kaydı ifade eder. Bir değer doldurulan kayıtları nedenler MFC bir özel durum sayısından daha ayarlama. Çağırarak doldurulan kayıt kümesinde sayısını belirleyebilirsiniz `GetRecordCount` üye işlevi.  
  
 Geçerli kaydı silinirse, AbsolutePosition özellik değeri tanımlı değil ve onu başvuruluyorsa MFC özel durum oluşturur. Yeni kayıtlar dizinin sonuna eklenir.  
  
> [!NOTE]
>  Bu özellik, bir yedek kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer işaretleri hala korur ve belirli bir konuma döndürmek için önerilen yoldur ve tüm destek yer işaretleri kayıt kümesi nesne türlerini geçerli kayıt konumuna tek yoludur. Özellikle, kendisinden kayıt silindiğinde verilen kayıt konumunu değiştirir. Ayrıca bir SQL deyimi kullanarak ile yapılandırılmadığı sürece bir kayıt kümesi içinde tek tek kayıtların sırası kesin değildir çünkü kayıt yeniden yeniden oluşturulursa, verilen bir kaydın aynı mutlak konum gerekir herhangi bir güvencesi yoktur bir  **ORDERBY** yan tümcesi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "AbsolutePosition özelliğini" konusuna bakın.  
  
##  <a name="setbookmark"></a>  CDaoRecordset::SetBookmark  
 Kayıt kümesi belirtilen yer işareti içeren kaydında konumlandırmak için bu üye işlevini çağırın.  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parametreler  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) belirli bir kayıt yer işareti değeri içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, her kayıtlarını zaten benzersiz bir yer işareti içeriyor. Çağırarak geçerli kayıt için yer alabilir `GetBookmark` ve değerine kaydetme bir `COleVariant` nesnesi. Çağırarak daha sonra bu kayda dönebilmek `SetBookmark` kaydedilmiş yer işareti değeri kullanılarak.  
  
> [!NOTE]
>  Çağırma [Requery](#requery) DAO yer işaretleri değiştirir.  
  
 UNICODE kayıt oluşturmadığınızı gerçekleştiriyorsanız, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanılarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** biçiminde Oluşturucusu ile `vtSrc` kümesine `VT_BSTRT` (ANSI) kullanarak veya **COleVariant** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** ile `vtSrc` kümesine `VT_BSTRT`.  
  
 İlgili bilgi için "yer işareti" Bookmarkable özellik ve DAO Yardımı'nda bkz".  
  
##  <a name="setcachesize"></a>  CDaoRecordset::SetCacheSize  
 Önbelleğe alınacak kayıt sayısını ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>Parametreler  
 `lSize`  
 Kayıt sayısını belirtir. Tipik bir değer 100'dür. 0 ayarı önbelleğe almayı devre dışı bırakır. Bu ayar, 5 ve 1200 kayıtları arasında olmalıdır. Önbellek önemli miktarda bellek kullanabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir boşluk uygulama çalışırken verileri yeniden istenecektir gerektiğinde, sunucudan en son alınan verileri tutar, yerel bellekte önbelleğidir. Veri önbelleğe alma dynaset türündeki kayıt kümesi nesneleri üzerinden uzak bir sunucudan verileri alan bir uygulamanın performansını artırır. Veri istendiğinde, Microsoft Jet veritabanı altyapısı için istenen veri önbelleği ilk daha uzun sürer sunucudan alınıyor yerine denetler. Bir ODBC veri kaynağından gelmez veri önbellekte kaydedilmez.  
  
 ODBC veri kaynağını, ekli bir tablo gibi bir yerel önbelleği olabilir. Önbellek oluşturmak için bir kayıt kümesi nesnesi uzak veri kaynağından çağrısı açın `SetCacheSize` ve `SetCacheStart` üye işlevleri ve ardından çağrı `FillCache` üye işlevi veya taşıma işlemleri birini kullanarak kayıtları ilerleyebilirsiniz. `lSize` Parametresinin `SetCacheSize` üye işlevi uygulamanızı çalışabilir ile aynı anda kayıtlarının sayısı üzerinde temel alabilir. Örneğin, ekranda görüntülenecek veri kaynağı olarak bir kayıt kümesi kullanıyorsanız geçirebilirdiniz `SetCacheSize` `lSize` parametre defada 20 kayıtları görüntülemek için 20 olarak.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "CacheSize, CacheStart özellikleri" konusuna bakın.  
  
##  <a name="setcachestart"></a>  CDaoRecordset::SetCacheStart  
 Önbelleğe alınacak kayıt kümesinde yer ilk kaydının belirtmek için bu üye işlevini çağırın.  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parametreler  
 `varBookmark`  
 A [COleVariant](../../mfc/reference/colevariant-class.md) önbelleğe alınacak kayıt kümesinde yer ilk kaydının belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Yer işareti değeri kayıtlar için kullanabileceğiniz `varBookmark` parametresinin `SetCacheStart` üye işlevi. Önbellek geçerli kayıtla başlatmak için bu kayıt kullanmak için bir yer işareti oluşturmak istediğiniz kayıt olun [SetBookmark](#setbookmark)ve parametre olarak yer işareti değerini geçirin `SetCacheStart` üye işlevi.  
  
 Microsoft Jet veritabanı altyapısı önbellekten önbellek aralıkta kayıt isteklerini ve sunucudan önbellek aralığın dışında kayıtları ister.  
  
 Önbellekten alınan kayıtlar eşzamanlı olarak kaynak verilere diğer kullanıcılar tarafından yapılan değişiklikleri yansıtmaz.  
  
 Önbellekte saklanan tüm veriler güncelleştirmesini zorlamak için geçirmek `lSize` parametresinin `SetCacheSize` 0 çağrı `SetCacheSize` yeniden önbelleğin boyutunu, başlangıçta istenen ve ardından arama `FillCache` üye işlevi.  
  
 UNICODE kayıt oluşturmadığınızı gerçekleştiriyorsanız, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanılarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** biçiminde Oluşturucusu ile `vtSrc` kümesine `VT_BSTRT` (ANSI) kullanarak veya **COleVariant** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** ile `vtSrc` kümesine `VT_BSTRT`.  
  
 İlgili bilgi için CacheSize, CacheStart özelliklerini DAO Yardım konusuna bakın".  
  
##  <a name="setcurrentindex"></a>  CDaoRecordset::SetCurrentIndex  
 Bir tablo türü kayıt kümesinde bir dizin ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszIndex`  
 Ayarlanacak dizinin adını içeren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Temel tabloyu kayıtlarında belirli bir sırada depolanmaz. Bir dizin ayarlama veritabanından döndürülen kayıt sırasını değiştirir, ancak kayıtları depolandığı sırayı etkilemez. Belirtilen dizinde zaten tanımlanmış olması gerekir. Var olmayan bir dizin nesnesi kullanmayı denerseniz veya çağırdığınızda dizini ayarlanmamışsa [arama](#seek), MFC bir özel durum oluşturur.  
  
 Çağırarak tablo için yeni bir dizin oluşturabilirsiniz [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) ve çağırarak temel tabledef dizinler koleksiyonu için yeni bir dizin ekleyerek [CDaoTableDef::Append](../../mfc/reference/cdaotabledef-class.md#append), ve kapatıp yeniden açmayı kayıt kümesi.  
  
 Bir tablo türü kayıt kümesinden döndürülen kayıt için temel alınan tabledef tanımlanan dizinleri göre sıralanabilir. Başka bir sipariş kayıtları sıralamak için dinamik küme türünde veya anlık görüntü türündeki kayıt kümesi bir SQL kullanarak açabilirsiniz **ORDERBY** yan tümcesi depolanır [CDaoRecordset::m_strSort](#m_strsort).  
  
 İlgili bilgi için bkz: "Dizin nesnesi" bölümüne ve DAO Yardımı'ndaki "geçerli dizin" tanımı.  
  
##  <a name="setfielddirty"></a>  CDaoRecordset::SetFieldDirty  
 Alan veri kayıt kümesinin üyesi değiştirilmiş veya değişmemiş olarak olarak işaretlemek için bu üye işlevini çağırın.  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Alan veri üyesi kümesinde adresini içerir veya **NULL**. Varsa **NULL**, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ **NULL** Null aynı veritabanı terminolojisinde değil "hiçbir değere sahip." anlamına gelir)  
  
 `bDirty`  
 **DOĞRU** alan veri üyesi kirli"(değiştirilmiş)"olarak işaretlenmiş ise. Aksi takdirde **FALSE** alan veri üyesi temizleme"(değişmeden)"olarak işaretlenmiş ise.  
  
### <a name="remarks"></a>Açıklamalar  
 Alanlar değiştirilmemiş olarak işaretleme alan güncelleştirilmez sağlar.  
  
 Bunlar veri kaynağındaki DAO kayıt alanı değişimi (DFX) mekanizması tarafından yazılır emin olmak için alan veri üyeleri framework işaretleri değiştirildi. Genellikle bir alanın değerini değiştirme ayarlar alan kirli otomatik olarak nadiren çağırmanız gerekir böylece `SetFieldDirty` kendiniz ancak, bazen isteyebileceğiniz sütunları açıkça güncelleştirilmiş veya kaldırılacak hangi değeri alanı verileri bağımsız olarak eklenir, emin olmak üye. DFX mekanizması kullanımını da kullanan **PSEUDONULL**. Daha fazla bilgi için bkz: [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 İki kez arabelleğe alma mekanizması kullanılmadığından, alanın değerini değiştirme otomatik olarak alan kirli olarak ayarlamaz. Bu durumda, açıkça alan kirli olarak ayarlamak gerekli olacaktır. İçinde yer alan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) denetimleri otomatik alan denetleniyor.  
  
> [!NOTE]
>  Yalnızca adlı sonra bu üye işlevini çağırın [Düzenle](#edit) veya [AddNew](#addnew).  
  
 Kullanarak **NULL** işlevinin ilk bağımsız değişkeni işlevi tümüne uygulanacak için **outputColumn** alanları değil, **param** alanlarını `CDaoFieldExchange`. Örneğin, arama  
  
 [!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 yalnızca ayarlayacaktır **outputColumn** alanları **NULL**; **param** alanları etkilenmemesini olacaktır.  
  
 Üzerinde çalışmak için bir **param**, tek tek gerçek adresini sağlamalısınız **param** gibi çalışmak istediğiniz:  
  
 [!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 Tüm ayarlayamıyor yani **param** alanları **NULL**ile yapabileceğiniz gibi **outputColumn** alanları.  
  
 `SetFieldDirty` aracılığıyla uygulanır `DoFieldExchange`.  
  
##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull  
 Alan veri kayıt kümesinin üyesi (özellikle herhangi bir değer sahip) Null veya boş olmayan olarak işaretlemek için bu üye işlevini çağırın.  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pv`  
 Alan veri üyesi kümesinde adresini içerir veya **NULL**. Varsa **NULL**, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ **NULL** Null aynı veritabanı terminolojisinde değil "hiçbir değere sahip." anlamına gelir)  
  
 `bNull`  
 Herhangi bir değer (boş) sahip olarak işaretlenmesini alan veri üyesi ise, sıfır olmayan. Null olmayan işaretlenmesini alan veri üyesi ise, aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetFieldNull` bağlanan alanlar için kullanılan `DoFieldExchange` mekanizması.  
  
 Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlayın ve kirli"(değiştirilmiş)"olarak işaretlenmiş. Bir kayıt bir veri kaynağından veri almak, sütunlarını zaten değerlere sahip ya da Null şunlardır. Bir alan Null, yapmak uygun değilse, bir [CDaoException](../../mfc/reference/cdaoexception-class.md) atılır.  
  
 Örneğin, özellikle geçerli kayıt alanı çağrısı bir değer olmaması olarak atamak istiyorsanız, iki kez arabelleğe alma mekanizması kullanıyorsanız, `SetFieldNull` ile `bNull` kümesine **TRUE** Null olarak işaretleyemedi. Bir alan daha önce Null işaretlendi ve artık bir değere vermek istediğiniz, yalnızca yeni değerini ayarlayın. Null bayrağı ile kaldırmak zorunda değilsiniz `SetFieldNull`. Alanın Null olmasına izin verilip verilmediğini belirlemek için arama [IsFieldNullable](#isfieldnullable).  
  
 İki kez arabelleğe alma mekanizması kullanmıyorsanız, alanın değerini değiştirme otomatik olarak alan kirli ve Null olarak ayarlamaz. Özellikle, kirli ve Null olmayan alanları ayarlamanız gerekir. İçinde yer alan bayrağı [m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) denetimleri otomatik alan denetleniyor.  
  
 DFX mekanizması kullanımını kullanan **PSEUDONULL**. Daha fazla bilgi için bkz: [CDaoFieldExchange::m_nOperation](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
> [!NOTE]
>  Yalnızca adlı sonra bu üye işlevini çağırın [Düzenle](#edit) veya [AddNew](#addnew).  
  
 Kullanarak **NULL** işlevinin ilk bağımsız değişkeni işlevi yalnızca uygulanır için **outputColumn** alanları değil, **param** alanlarını `CDaoFieldExchange`. Örneğin, arama  
  
 [!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 yalnızca ayarlayacaktır **outputColumn** alanları **NULL**; **param** alanları etkilenmemesini olacaktır.  
  
##  <a name="setfieldvalue"></a>  CDaoRecordset::SetFieldValue  
 Sıra konumuna veya dize değerini değiştirerek bir alanın değerini ayarlamak için bu üye işlevini çağırın.  
  
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
 `lpszName`  
 Bir alanın adını içeren bir dize için bir işaretçi.  
  
 `varValue`  
 Bir başvuru bir [COleVariant](../../mfc/reference/colevariant-class.md) alanın içeriği değerini içeren nesne.  
  
 `nIndex`  
 Kayıt kümesinin alanlar koleksiyonu (sıfır tabanlı) sıralı alanın konumunu temsil eden bir tamsayı.  
  
 `lpszValue`  
 Alanın içeriği değerini içeren bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `SetFieldValue` ve [GetFieldValue](#getfieldvalue) alanları çalıştırma yerine statik olarak kullanarak bağlama sütunları dinamik olarak bağlamak için [DoFieldExchange](#dofieldexchange) mekanizması.  
  
 UNICODE kayıt kümesi oluşturuyorsanız değil, bir tür ya da kullanmalıdır Not `SetFieldValue` içermeyen bir `COleVariant` parametresi veya `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanılarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** biçiminde Oluşturucusu ile `vtSrc` kümesine `VT_BSTRT` (ANSI) kullanarak veya **COleVariant** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** ile `vtSrc` kümesine `VT_BSTRT`.  
  
 İlgili bilgi için "Alanı nesnesi" ve "Değer özelliği" DAO Yardım konularına bakın.  
  
##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull  
 Alan için Null değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Sıfır tabanlı dizin aramasından için kayıt kümesindeki alan dizini.  
  
 `lpszName`  
 Ada göre arama kümesinde alan adı.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ **NULL** Veritabanı terminolojisinde anlamına gelir, Null ile aynı değil "hiçbir değere sahip."  
  
 İlgili bilgi için "Alanı nesnesi" ve "Değer özelliği" DAO Yardım konularına bakın.  
  
##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode  
 Kayıt kümesi için kilitleme türünü ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>Parametreler  
 *bPessimistic*  
 Kilitleme türünü belirten bir bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Kötümser kilitleme etkin düzenlemekte kayıt içeren 2 K sayfası olduğunda sizi aramasını hemen kilitli **Düzenle** üye işlevi. Çağırdığınızda kilidi sayfasıdır **güncelleştirme** veya **Kapat** üye işlevini veya taşıma veya bulma işlemleri.  
  
 Yalnızca kaydı ile güncelleştirilirken İyimser kilitleme etkindir, kaydın bulunduğu 2 K sayfası kilitlenir **güncelleştirme** üye işlevi.  
  
 Bir sayfa kilitliyse, başka bir kullanıcı kayıtları aynı sayfada düzenleyebilirsiniz. Çağırırsanız `SetLockingMode` ve sıfır olmayan bir değer geçirmek ve başka bir kullanıcı kilitli sayfa zaten sahipse, çağırdığınızda bir özel durum **Düzenle**. Diğer kullanıcıların kilitli sayfalardaki verileri okuyabilir.  
  
 Çağırırsanız `SetLockingMode` sıfır değerine sahip ve sonraki çağrı **güncelleştirme** sayfa başka bir kullanıcı tarafından kilitliyken bir özel durum oluşur. Kaydınız için başka bir kullanıcı tarafından yapılan değişiklikleri görmek (ve değişiklikleri kaybetmek için), çağrı `SetBookmark` üye işlevi geçerli kayıt yer işareti değerine sahip.  
  
 ODBC veri kaynakları ile çalışırken, kilitleme zaman iyimser modudur.  
  
##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue  
 Çalışma zamanında kayıt kümesinde bir parametrenin değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Sayısal konumu parametresi querydef ait parametreler koleksiyonu.  
  
 `var`  
 Ayarlanacak değer; Açıklamalar bakın.  
  
 `lpszName`  
 Değer ayarlamak istediğiniz parametresinin adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre zaten kayıt kümenizin SQL dizesi bir parçası olarak kurulmuş gerekir. Parametre adı veya dizin konumuna koleksiyondaki göre erişebilirsiniz.  
  
 Olarak ayarlanacak değer belirtmek bir `COleVariant` nesnesi. İstenen değeri ve türü ayarlama hakkında bilgi için `COleVariant` nesne, sınıfına bakın [COleVariant](../../mfc/reference/colevariant-class.md). UNICODE kayıt oluşturmadığınızı gerçekleştiriyorsanız, `COleVariant` nesne ANSI açıkça da bildirilmelidir. Bu kullanılarak yapılabilir [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** biçiminde Oluşturucusu ile `vtSrc` kümesine `VT_BSTRT` (ANSI) kullanarak veya **COleVariant** işlevi [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** ile `vtSrc` kümesine `VT_BSTRT`.  
  
##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull  
 Parametre için Null değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Sıfır tabanlı dizin aramasından için kayıt kümesindeki alan dizini.  
  
 `lpszName`  
 Ada göre arama kümesinde alan adı.  
  
### <a name="remarks"></a>Açıklamalar  
 C++ **NULL** Veritabanı terminolojisinde anlamına gelir, Null ile aynı değil "hiçbir değere sahip."  
  
##  <a name="setpercentposition"></a>  CDaoRecordset::SetPercentPosition  
 Geçerli kayıt kayıt kümesindeki kayıt yüzdesine göre numaralandırır yaklaşık konumunu değiştiren bir değer ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>Parametreler  
 *fPosition*  
 0 ile 100 arasında bir sayı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dynaset türü veya anlık görüntü türündeki kayıt kümesi ile çalışırken, ilk kayıt çağırmadan önce son kaydı taşıyarak doldurmak `SetPercentPosition`. Çağırırsanız `SetPercentPosition` kayıt tam doldurma önce taşıma miktarını değeri tarafından belirtildiği şekilde erişilen kayıt sayısını görelidir [GetRecordCount](#getrecordcount). Çağırarak kayıt son taşıyabilirsiniz `MoveLast`.  
  
 Çağırmanız sonra `SetPercentPosition`, o değerine karşılık gelen yaklaşık konumdaki kayıt geçerli olur.  
  
> [!NOTE]
>  Çağırma `SetPercentPosition` belirli bir kayda bir kayıt kümesindeki geçerli kayıt önerilmez taşımak için. Çağrı [SetBookmark](#setbookmark) üye işlev yerine.  
  
 İlgili bilgi için DAO Yardımı'ndaki "PercentPosition özelliği" konusuna bakın.  
  
##  <a name="update"></a>  CDaoRecordset::Update  
 Çağrı sonra bu üye işlevini çağırın `AddNew` veya **Düzenle** üye işlevi.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu çağrı tamamlamak için gereken `AddNew` veya **Düzenle** işlemi.  
  
 Her ikisi de `AddNew` ve **Düzenle** kaydetme veri kaynağına eklenen veya düzenlenen verilerin yerleştirilir düzenleme arabelleği hazırlayın. **Güncelleştirme** verileri kaydeder. İşaretlenen veya değiştirilen olarak algılanan yalnızca bu alanları güncelleştirilir.  
  
 Veri kaynağı işlemleri destekliyorsa, yapabileceğiniz **güncelleştirme** çağrı (ve ilgili `AddNew` veya **Düzenle** çağrısı) bir işlemin parçası.  
  
> [!CAUTION]
>  Çağırırsanız **güncelleştirme** ilk ya da çağırma `AddNew` veya **Düzenle**, **güncelleştirme** oluşturur bir `CDaoException`. Çağırırsanız `AddNew` veya **Düzenle**, çağırmalısınız **güncelleştirme** çağırmadan önce [MoveNext](#movenext) ya da kayıt kümesi ve veri kaynağı bağlantısı kapatın. Aksi takdirde, bildirim değişiklikleriniz kaybolur.  
  
 Kayıt kümesi nesnesi çok kullanıcılı bir ortamda zor kilitlendiğinde kayıt kilitli kalır **Düzenle** güncelleştirme tamamlanana kadar kullanılır. Kayıt kümesi iyimser kilitliyse kayıt kilitli ve veritabanında güncelleştirilmeden önce önceden düzenlenmiş kayıtla karşılaştırılır. Aradığınız kaydı değişmişse **Düzenle**, **güncelleştirme** işlemi başarısız olur ve MFC bir özel durum oluşturur. Kilitleme moduyla değiştirebileceğiniz `SetLockingMode`.  
  
> [!NOTE]
>  İyimser kilitleme ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimleri üzerinde her zaman kullanılır.  
  
 İlgili bilgiler için "AddNew yöntemi", "CancelUpdate yöntemi", "Delete yöntemini", "LastModified özelliği", "Güncelleştirme yöntemi" ve DAO Yardımı'ndaki "EditMode özelliği" konularına bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace sınıfı](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
