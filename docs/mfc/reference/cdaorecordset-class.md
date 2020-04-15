---
title: CDaoRecordset Sınıfı
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
ms.openlocfilehash: 5b4b2919405696c748ce01217ac82afeac316de2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377159"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset Sınıfı

Veri kaynağından seçilen bir kayıt kümesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Bir `CDaoRecordset` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset::AddNew](#addnew)|Yeni bir kayıt eklemeye hazırlanıyor. Eklemeyi tamamlamak için [Güncelleştirme'yi](#update) arayın.|
|[CDaoRecordset::CanAppend](#canappend)|[AddNew](#addnew) üye işlevi aracılığıyla kayıt kümesine yeni kayıtlar eklenebiliyorsa sıfırsız döndürür.|
|[CDaoRecordset::CanBookmark](#canbookmark)|Kayıt kümesi yer imlerini destekliyorsa sıfırsız döndürür.|
|[CDaoRecordset::CancelUpdate](#cancelupdate)|[Bir Edit](#edit) veya [AddNew](#addnew) işlemi nedeniyle bekleyen güncelleştirmeleri iptal eder.|
|[CDaoRecordset::CanRestart](#canrestart)|Kayıt kümesinin sorgusunu yeniden çalıştırmak için [Requery](#requery) çağrılanabiliyorsa sıfırsız döndürür.|
|[CDaoRecordset::CanScroll](#canscroll)|Kayıtlar arasında gezinebilirseniz sıfırsız döndürür.|
|[CDaoRecordset::CanTransact](#cantransact)|Veri kaynağı hareketleri destekliyorsa sıfırsız döndürür.|
|[CDaoRecordset::CanUpdate](#canupdate)|Kayıt kümesi güncelleştirilebiliyorsa sıfırsız döndürür (kayıtları ekleyebilir, güncelleyebilir veya silebilirsiniz).|
|[CDaoRecordset::Kapat](#close)|Kayıt kümesini kapatır.|
|[CDaoRecordset::Delete](#delete)|Geçerli kaydı kayıt kümesinden siler. Silme işleminden sonra açıkça başka bir kayda kaydırmanız gerekir.|
|[CDaoRecordset::DoFieldExchange](#dofieldexchange)|Kayıt kümesinin alan veri üyeleri ile veri kaynağındaki ilgili kayıt arasında veri alışverişi (her iki yönde de) çağrılır. DAO kayıt alanı değişimini (DFX) uygular.|
|[CDaoRecordset::Edit](#edit)|Geçerli kayıtta yapılan değişiklikler için hazırlandığız. Yapılan `Update` mayı tamamlamak için arayın.|
|[CDaoRecordset::FillÖnbellek](#fillcache)|ODBC veri kaynağından veri içeren bir kayıt kümesi nesnesi için yerel önbelleğin tamamını veya bir kısmını doldurur.|
|[CDaoRecordset::Bul](#find)|Belirtilen ölçütleri karşılayan ve geçerli kaydı kaydeden bir dinamit türü kayıt kümesinde belirli bir dizedeki ilk, sonraki, önceki veya son konumunu bulur.|
|[CDaoRecordset::İlk bul](#findfirst)|Belirtilen ölçütleri karşılayan ve geçerli kaydı kaydeden bir dynaset türü veya anlık görüntü tipi kayıt kümesindeki ilk kaydı bulur.|
|[CDaoRecordset::FindLast](#findlast)|Belirtilen ölçütleri karşılayan ve geçerli kaydı kaydeden dynaset türü veya anlık görüntü tipi kayıt kümesindeki son kaydı bulur.|
|[CDaoRecordset::Find](#findnext)|Belirtilen ölçütleri karşılayan ve geçerli kaydı kaydeden bir dynaset türü nde veya anlık görüntü tipi kayıt kümesinde bir sonraki kaydı bulur.|
|[CDaoRecordset::FindPrev](#findprev)|Belirtilen ölçütleri karşılayan ve geçerli kaydı kaydeden bir dynaset türünde veya anlık görüntü tipi kayıt kümesinde önceki kaydı bulur.|
|[CDaoRecordset::GetAbsolutePosition](#getabsoluteposition)|Kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını verir.|
|[CDaoRecordset::GetBookmark](#getbookmark)|Kayıttaki yer işaretini temsil eden bir değer verir.|
|[CDaoRecordset::GetÖnbellek](#getcachesize)|ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dynaset türü kayıt kümesindeki kayıt sayısını belirten bir değer verir.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir değer verir.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Dizinlenmiş, tablo türünde `CString` `CDaoRecordset`en son kullanılan dizin adını içeren bir sözcük döndürür.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|`CDaoRecordset` Nesnenin altında yatan temel tablonun oluşturulduğu tarihi ve saati döndürür|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|`CDaoRecordset` Nesnenin altında yatan bir taban tablonun tasarımında yapılan en son değişikliğin tarih ve saatini döndürür.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Varsayılan veri kaynağının adını döndürür.|
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Varsayılan SQL dizesini çalıştırmak için çağrıldı.|
|[CDaoRecordset::GetEditMode](#geteditmode)|Geçerli kaydın düzenleme durumunu gösteren bir değer verir.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Kayıt kümesindeki alan sayısını temsil eden bir değer verir.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Kayıt kümesindeki alanlar hakkında belirli türde bilgiler verir.|
|[CDaoRecordset::GetFieldValue](#getfieldvalue)|Bir kayıt kümesindeki alanın değerini verir.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|Bir kayıt kümesinin altında yatan tablodaki dizin sayısını alır.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Dizin hakkında çeşitli bilgiler verir.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|En son eklenen veya güncelleştirilen kaydı belirlemek için kullanılır.|
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Düzenleme sırasında geçerli olan kilitleme türünü gösteren bir değer verir.|
|[CDaoRecordset::GetName](#getname)|Kayıt `CString` kümesinin adını içeren bir verir.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|Altta yatan DAOParameter nesnesinde depolanan belirtilen parametrenin geçerli değerini alır.|
|[CDaoRecordset::GetPercentPosition](#getpercentposition)|Geçerli kaydın konumunu toplam kayıt sayısının yüzdesi olarak verir.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Kayıt kümesi nesnesinde erişilen kayıt sayısını verir.|
|[CDaoRecordset::GetSQL](#getsql)|Kayıt kümesi nin kayıtlarını seçmek için kullanılan SQL dizesini alır.|
|[CDaoRecordset::GetType](#gettype)|Kayıt kümesinin türünü belirlemek için çağrıldı: tablo tipi, dynaset türü veya anlık görüntü türü.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Bir `CString` alana girilirken verileri doğrulayan bir değer içeren bir verir.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Doğrulama kuralı karşılanmadığında görüntülenen metni alır.|
|[CDaoRecordset::IsBOF](#isbof)|Kayıt kümesi ilk kayıtöncesinde konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.|
|[CDaoRecordset::Silinmiş](#isdeleted)|Kayıt kümesi silinmiş bir kayıt ta konumlandırılmışsa sıfırsız döndürür.|
|[CDaoRecordset::IsEOF](#iseof)|Kayıt kümesi son kayıttan sonra konumlandırılmışsa sıfırsız döndürür. Geçerli bir kayıt yok.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Geçerli kayıtta belirtilen alan değiştirildiyse sıfırsız döndürür.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Geçerli kayıtta belirtilen alan Null ise (değeri olmayan) sıfırsız döndürür.|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Geçerli kayıtta belirtilen alan Null olarak ayarlanabiliyorsa (değeri olmayan) sıfırsız döndürür.|
|[CDaoRecordset::Açık](#isopen)|[Açık](#open) daha önce çağrıldıysa sıfırsız döndürür.|
|[CDaoRecordset::Taşı](#move)|Kayıtları her iki yönde de geçerli kayıttan belirli bir sayıda ki kayıt sayısına konumlandırın.|
|[CDaoRecordset::MoveFirst](#movefirst)|Geçerli kaydı kayıt kümesindeki ilk kayıtta konumlandırın.|
|[CDaoRecordset::MoveLast](#movelast)|Geçerli kaydı kayıt kümesindeki son kayıtta konumlandırın.|
|[CDaoRecordset::MoveNext](#movenext)|Geçerli kaydı kayıt kümesindeki bir sonraki kayıtta konumlandırın.|
|[CDaoRecordset::MovePrev](#moveprev)|Geçerli kaydı kayıt kümesindeki önceki kayıtta konumlandırın.|
|[CDaoRecordset::Aç](#open)|Tablo, dynaset veya anlık görüntüden yeni bir kayıt kümesi oluşturur.|
|[CDaoRecordset::Yeniden sorgu](#requery)|Seçili kayıtları yenilemek için kayıt kümesinin sorgusunu yeniden çalıştırın.|
|[CDaoRecordset::Ara](#seek)|Geçerli dizin için belirtilen ölçütleri karşılayan ve bu kaydı geçerli kaydı yapan dizinlenmiş tablo türü kaydedici kümesi nesnesinde kaydı bulur.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını ayarlar.|
|[CDaoRecordset::SetBookmark](#setbookmark)|Kayıt kümesini belirtilen yer işaretini içeren bir kayda konumlandırın.|
|[CDaoRecordset::SetÖnbellek Boyutu](#setcachesize)|Bir ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dynaset türü ndeki kayıt sayısını belirten bir değer ayarlar.|
|[CDaoRecordset::SetÖnbellekBaşlat](#setcachestart)|Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir değer ayarlar.|
|[CDaoRecordset::SetCurrentIndex](#setcurrentindex)|Tablo türünde bir kayıt kümesiüzerinde dizin ayarlamak için çağrıldı.|
|[CDaoRecordset::SetFieldDirty](#setfielddirty)|Geçerli kayıtta belirtilen alanı değiştirilmiş olarak işaretler.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Geçerli kayıtta belirtilen alanın değerini Null (değeri olmayan) olarak ayarlar.|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Bir alanın değerini bir kayıt kümesinde ayarlar.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Bir kayıt kümesindeki alanın değerini Null olarak ayarlar. (hiçbir değeri vardır).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Düzenleme sırasında yürürlüğe koymak için kilitleme türünü gösteren bir değer ayarlar.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|Dayanak DAOParameter nesnesinde depolanan belirtilen parametrenin geçerli değerini ayarlar|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Belirtilen parametrenin geçerli değerini Null (değeri olmayan) olarak ayarlar.|
|[CDaoRecordset::SetPercentPosition](#setpercentposition)|Geçerli kaydın konumunu, kayıt kümesindeki toplam kayıt sayısının yüzdesine karşılık gelen bir konuma ayarlar.|
|[CDaoRecordset::Güncelleme](#update)|Yeni veya `AddNew` `Edit` düzenlenen verileri veri kaynağına kaydederek bir işlemi veya işlemi tamamlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoRecordset::m_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields)|Alanların otomatik olarak değiştiriliyor olarak işaretlenip işaretlenmediğini belirten bir bayrak içerir.|
|[CDaoRecordset::m_nFields](#m_nfields)|Recordset sınıfındaki alan veri üyesi sayısını ve veri kaynağından kayıt kümesi tarafından seçilen sütun sayısını içerir.|
|[CDaoRecordset::m_nParams](#m_nparams)|Recordset sınıfındaki parametre veri üye sayısını içerir — kayıt kümesinin sorgusuyla geçirilen parametre sayısı|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Kayıt kümesi nesnesinin altında yatan DAO arabirimine işaretçi.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Bu sonuç kümesi için kaynak veritabanı. [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine işaretçi içerir.|
|[CDaoRecordset::m_strFilter](#m_strfilter)|SQL **WHERE** deyimi oluşturmak için kullanılan bir dize içerir.|
|[CDaoRecordset::m_strSort](#m_strsort)|SQL **ORDER BY** deyimini oluşturmak için kullanılan bir dize içerir.|

## <a name="remarks"></a>Açıklamalar

"Kayıt kümeleri" `CDaoRecordset` olarak bilinen nesneler aşağıdaki üç formda kullanılabilir:

- Tablo türü kayıt kümeleri, tek bir veritabanı tablosundaki kayıtları incelemek, eklemek, değiştirmek veya silmek için kullanabileceğiniz bir taban tabloyu temsil ediyor.

- Dynaset türündeki kayıt kümeleri, güncelleştirilebilir kayıtlara sahip bir sorgunun sonucudur. Bu kayıt kümeleri, temel veritabanı tablosundan veya tablolarından kayıtları incelemek, eklemek, değiştirmek veya silmek için kullanabileceğiniz bir kayıt kümesidir. Dynaset türündeki kayıt kümeleri, veritabanındaki bir veya daha fazla tablodan alanlar içerebilir.

- Anlık görüntü türü kayıt kümeleri, verileri bulmak veya rapor oluşturmak için kullanabileceğiniz bir kayıt kümesinin statik kopyasıdır. Bu kayıt kümeleri bir veritabanında bir veya daha fazla tablodan alanlar içerebilir, ancak güncelleştirilemez.

Kayıt kümesinin her formu, kayıt kümesinin açıldığı anda sabitlenmiş bir kayıt kümesini temsil eder. Tablo tipi kayıt kümesinde veya dynaset tipi kayıt setinde bir kayda kaydırdığınızda, kayıt kümesi açıldıktan sonra, diğer kullanıcılar veya uygulamanızdaki diğer kayıt kümeleri tarafından kaydedilen yapılan değişiklikleri yansıtır. (Anlık görüntü türünde kayıt kümesi güncelleştirilemez.) Doğrudan kullanabilir `CDaoRecordset` veya `CDaoRecordset`uygulamaya özgü bir kayıt kümesi sınıf. Ardından şunları yapabilirsiniz:

- Kayıtlar arasında ilerleyin.

- Bir dizin ayarlayın ve [Seek](#seek) 'i kullanarak kayıtları hızla arayın (yalnızca tablo türünde kayıt kümeleri).

- "<", "=",\<"=", ">="veya ">" (dynaset türü ve anlık görüntü tipi kayıt kümeleri) gibi bir dize karşılaştırması temel alan kayıtları bulun.

- Kayıtları güncelleştirin ve kilitleme modu (anlık görüntü türü kayıt kümeleri hariç) belirtin.

- Kayıt kümesini, veri kaynağında bulunanlardan hangi kayıtları seçerek sınırlandıracak şekilde filtreleyin.

- Kayıt kümesini sıralayın.

- Seçimin çalışma süresine kadar bilinmeyen bilgilerle özelleştirilmesi için kayıt kümesini parametreleştirin.

Sınıf, `CDaoRecordset` sınıfınkine `CRecordset`benzer bir arabirim sağlar. Temel fark, sınıfın `CDaoRecordset` Veri Erişim Nesnesi (DAO) üzerinden OLE'ye dayalı verilere erişmesidir. Sınıf, `CRecordset` Açık Veritabanı Bağlantısı (ODBC) ve bu DBMS için bir ODBC sürücüsü aracılığıyla DBMS'ye erişer.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DaO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz; DAO sınıfları genellikle microsoft jet veritabanı altyapısına özgü olduğundan üstün özellikler sunar.

Ya doğrudan `CDaoRecordset` kullanabilirsiniz ya da `CDaoRecordset`bir sınıf türetin. Her iki durumda da bir kayıt kümesi sınıfı kullanmak için, bir veritabanı açın ve `CDaoDatabase` bir kayıt kümesi nesnesi oluşturmak, oluşturucu nesnenize bir işaretçi geçerek. Ayrıca bir `CDaoRecordset` nesne oluşturabilir ve MFC'nin sizin için geçici `CDaoDatabase` bir nesne oluşturmasına izin verebilirsiniz. Ardından, nesnenin tablo tipi bir kayıt kümesi mi, dynaset türü kayıt kümesi mi yoksa anlık görüntü tipi kayıt kümesi mi olduğunu belirterek, kaydedici nin [Açık](#open) üye işlevini arayın. Arama `Open` veritabanından verileri seçer ve ilk kaydı alır.

Kayıtları kaydırmak ve bunları çalıştırmak için nesnenin üye işlevlerini ve veri üyelerini kullanın. Kullanılabilir işlemler, nesnenin tablo tipi bir kayıt kümesi mi, dynaset türü kayıt kümesi mi yoksa anlık görüntü türü kayıt kümesi mi, güncelleştirilebilir veya salt okunur olup olmadığına bağlıdır — bu veritabanının veya Açık Veritabanı Bağlantısı (ODBC) veri kaynağının özelliğine bağlıdır. `Open` Aramadan sonra değiştirilmiş veya eklenmiş olabilecek kayıtları yenilemek için nesnenin [Requery](#requery) üye işlevini arayın. Nesnenin `Close` üye işlevini çağırın ve onunla bitirdiğinizde nesneyi yok edin.

`CDaoRecordset`tür güvenli C++ üyeleri aracılığıyla kayıt alanlarının okunmasını ve güncellenmesini desteklemek için `CDaoRecordset` DAO kayıt alanı değişimini `CDaoRecordset`(DFX) kullanır. Ayrıca [GetFieldValue](#getfieldvalue) ve [SetFieldValue](#setfieldvalue)kullanarak DFX mekanizmasını kullanmadan bir veritabanında sütundinamik bağlama uygulayabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Recordset Object" konusuna bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaorecordsetaddnew"></a><a name="addnew"></a>CDaoRecordset::AddNew

Tablo türüne veya dynaset türüne yeni bir kayıt eklemek için bu üye işlevini arayın.

```
virtual void AddNew();
```

### <a name="remarks"></a>Açıklamalar

Kaydın alanları başlangıçta Null'tur. (Veritabanı terminolojisinde Null "değeri yoktur" anlamına gelir ve C++'daki NULL ile aynı değildir.) İşlemi tamamlamak [için, Update](#update) üye işlevini aramanız gerekir. `Update`değişikliklerinizi veri kaynağına kaydeder.

> [!CAUTION]
> Bir kaydı ve ardından aramadan `Update`başka bir kayda kaydırırsanız, değişiklikleriniz uyarı yapılmadan kaybolur.

[AddNew'ı](#addnew)arayarak bir dynaset tipi kayıt kümesine bir kayıt eklerseniz, kayıt kayıt kümesinde görünür ve altta `CDaoRecordset` yatan tabloya eklenir ve bu kayıt yeni nesneler tarafından görülebilir hale gelir.

Yeni kaydın konumu kayıt kümesinin türüne bağlıdır:

- Yeni kaydın eklendiği dynaset tipi kayıt setinde garanti edilmez. Bu davranış, performans ve eşzamanlılık nedenleriyle Microsoft Jet 3.0 ile değiştirildi. Amacınız yeni eklenen kaydı geçerli kaydı kaydetmekse, değiştirilen son kaydın yer işaretini alın ve bu yer imine geçin:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- Bir dizin belirtilen tablo türü kayıt kümesinde, kayıtlar sıralama sırasına göre uygun yerlerde döndürülür. Dizin belirtilmemişse, kayıt kümesinin sonunda yeni kayıtlar döndürülür.

Kullanmadan `AddNew` önce geçerli olan kayıt geçerli kalır. Yeni kaydı güncel hale getirmek istiyorsanız ve kayıt kümesi yer imlerini destekliyorsa, Temel DAO kayıt kümesi nesnesinin LastModified özellik ayarı tarafından tanımlanan yer imi için [SetBookmark'ı](#setbookmark) arayın. Bunu yapmak, ekbir kayıttaki sayaç (otomatik artış) alanlarının değerini belirlemek için yararlıdır. Daha fazla bilgi için [GetLastModifiedBookmark'a](#getlastmodifiedbookmark)bakın.

Veritabanı hareketleri destekliyorsa, aramanızı `AddNew` bir hareketin parçası yapabilirsiniz. İşlemler hakkında daha fazla bilgi için [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)sınıfına bakın. CDaoWorkspace'i aramanız gerektiğini [unutmayın::BeginTrans'ı](../../mfc/reference/cdaoworkspace-class.md#begintrans) aramadan `AddNew`önce.

Açık üye işlevi `AddNew` çağrılmayan [Open](#open) bir kayıt kümesi ni çağırmak yasa dışıdır. Eklenen `CDaoException` bir kayıt `AddNew` kümesi için ararsanız A atılır. Kayıt kümesinin güncellenebilir olup olmadığını [CanAppend'i](#canappend)arayarak belirleyebilirsiniz.

Çerçeve işaretleri, DAO kayıt alanı değişimi (DFX) mekanizması tarafından veri kaynağına yazılmasını sağlamak için alan veri üyelerini değiştirdi. Bir alanın değerini değiştirmek genellikle alanı otomatik olarak kirli ayarlar, bu nedenle nadiren [SetFieldDirty'i](#setfielddirty) kendiniz aramanız gerekir, ancak bazen alan veri üyesinin değeri ne olursa olsun sütunların açıkça güncelleştirildiğinden veya eklenmesini sağlamak isteyebilirsiniz. DFX mekanizması da **PSEUDO NULL**kullanımını kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation.](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamaz. Bu durumda, açıkça alanı kirli ayarlamak için gerekli olacaktır. [m_bCheckCacheForDirtyFields'da](#m_bcheckcachefordirtyfields) bulunan bayrak bu otomatik alan denetimini kontrol eder.

> [!NOTE]
> Kayıtlar çift arabelleğe allarsa (diğer bir şekilde otomatik `CancelUpdate` alan denetimi etkinse), çağrı `AddNew` üye `Edit` değişkenleri daha önce sahip oldukları veya çağrıldıkları değerlere geri yüklenir.

İlgili bilgiler için DAO Help'de "AddNew Method", "CancelUpdate Method", "LastModified Property" ve "EditMode Property" konularına bakın.

## <a name="cdaorecordsetcanappend"></a><a name="canappend"></a>CDaoRecordset::CanAppend

Daha önce açılmış olan kayıt kümesinin [AddNew](#addnew) üye işlevini arayarak yeni kayıtlar eklemenize izin verip vermediğini belirlemek için bu üye işlevini arayın.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yeni kayıtlar eklenmesine izin veriyorsa sıfıra inme; aksi takdirde 0. `CanAppend`yalnızca okunur olarak kayıt kümesini açtıysanız 0 döndürecektir.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "Uygulama Yöntemi" konusuna bakın.

## <a name="cdaorecordsetcanbookmark"></a><a name="canbookmark"></a>CDaoRecordset::CanBookmark

Daha önce açılmış kayıt kümesinin yer imlerini kullanarak kayıtları tek tek işaretlemenize izin verip vermediğini belirlemek için bu üye işlevini arayın.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi yer imlerini destekliyorsa sıfır yok, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tamamen Microsoft Jet veritabanı altyapısı tablolarına dayalı kayıt kümeleri kullanıyorsanız, yalnızca ileri kaydırma kayıt kümeleri olarak işaretlenmiş anlık görüntü türü kayıt kümeleri dışında yer imleri kullanılabilir. Diğer veritabanı ürünleri (harici ODBC veri kaynakları) yer imlerini desteklemeyebilir.

İlgili bilgiler için DAO Yardım'daki "Yer İşaretli Özellik" konusuna bakın.

## <a name="cdaorecordsetcancelupdate"></a><a name="cancelupdate"></a>CDaoRecordset::CancelUpdate

Üye `CancelUpdate` işlevi, bir [Edit](#edit) veya [AddNew](#addnew) işlemi nedeniyle bekleyen güncelleştirmeleri iptal eder.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Açıklamalar

Örneğin, bir uygulama veya `Edit` `AddNew` üye işlevini çağırır ve `CancelUpdate` [Güncelleştirme'yi](#update)çağırmadıysa, sonra `Edit` yapılan veya `AddNew` çağrılan değişiklikleri iptal eder.

> [!NOTE]
> Kayıtlar çift arabelleğe allarsa (diğer bir şekilde otomatik `CancelUpdate` alan denetimi etkinse), çağrı `AddNew` üye `Edit` değişkenleri daha önce sahip oldukları veya çağrıldıkları değerlere geri yüklenir.

Bekleyen bir `Edit` `AddNew` işlem yoksa, `CancelUpdate` MFC'nin bir özel durum atmasını sağlar. İptal edilebilen bekleyen bir işlem olup olmadığını belirlemek için [GetEditMode](#geteditmode) üye işlevini arayın.

İlgili bilgiler için DAO Yardım'daki "CancelUpdate Method" konusuna bakın.

## <a name="cdaorecordsetcanrestart"></a><a name="canrestart"></a>CDaoRecordset::CanRestart

Kayıt kümesinin `Requery` üye işlevi arayarak sorgusunu yeniden başlatmaya (kayıtlarını yenilemek için) izin verip vermediğini belirlemek için bu üye işlevini arayın.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan, kayıt kümesinin sorgusunu yeniden çalıştırmak için çağrılabiliyorsa, `Requery` aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tablo türünde kayıt kümeleri desteklenmez. `Requery`

Desteklenmiyorsa, `Requery` verileri yenilemek için [Kapat'ı](#close) ve [Aç'ı](#open) arayın. Parametre `Requery` değerleri değiştirildikten sonra kayıt kümesi nesnesinin temel parametre sorgusunu güncelleştirmek için arayabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Yeniden Başlatılabilir Özellik" konusuna bakın.

## <a name="cdaorecordsetcanscroll"></a><a name="canscroll"></a>CDaoRecordset::CanScroll

Kayıt kümesinin kaydırmaya izin verip vermediğini belirlemek için bu üye işlevini arayın.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sıfır olmayan eğer kayıtlar arasında kaydırma yapabilirsiniz, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

[Open'ı](#open) çağırırsanız, `dbForwardOnly`kayıt kümesi yalnızca ileri kaydırılabilir.

İlgili bilgiler için DAO Yardımı'nda "Geçerli Kayıt İşaretçisini DAO ile Konumlandırma" konusuna bakın.

## <a name="cdaorecordsetcantransact"></a><a name="cantransact"></a>CDaoRecordset::CanTransact

Kayıt kümesinin hareketlere izin verip vermeyemeyeceğini belirlemek için bu üye işlevini arayın.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Dönüş Değeri

Temel veri kaynağı hareketleri destekliyorsa sıfırsız, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "İşlemler Özelliği" konusuna bakın.

## <a name="cdaorecordsetcanupdate"></a><a name="canupdate"></a>CDaoRecordset::CanUpdate

Kayıt kümesinin güncelleştirilip güncelleştirilemeyeceğini belirlemek için bu üye işlevini arayın.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi güncelleştirilebiliyorsa (kayıtları ekle, güncelleştir ve sil) sıfıra inmez, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi için [Aç'ı](#open) çağırdığınızda, yalnızca temel veri kaynağı `dbReadOnly` salt okunursa veya *nOptions* için belirtilmişseniz, yalnızca bir kayıt kümesi okunabilir.

İlgili bilgiler için DAO Help'de "Yeni Yöntem Ekle", "Düzenle Yöntemi", "Silme Yöntemi", "Güncelleştirme Yöntemi" ve "Güncellenebilir Özellik" konularına bakın.

## <a name="cdaorecordsetcdaorecordset"></a><a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset

Bir `CDaoRecordset` nesne inşa eder.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
[CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesine veya NULL değerine işaretçi içerir. NULL değilse ve `CDaoDatabase` nesnenin `Open` üye işlevi veri kaynağına bağlamak için çağrılmazsa, kayıt kümesi kendi [Açık](#open) araması sırasında onu sizin için açmaya çalışır. NULL'u geçerseniz, kayıt kümesi sınıfınızı .'dan `CDaoDatabase` `CDaoRecordset`türetilmişseniz belirttiğiniz veri kaynağı bilgilerini kullanarak bir nesne oluşturulur ve sizin için bağlanır.

### <a name="remarks"></a>Açıklamalar

Doğrudan kullanabilir `CDaoRecordset` veya `CDaoRecordset`uygulamaya özgü bir sınıf türetebilirsiniz. Kayıt kümesi sınıflarınızı türetmek için ClassWizard'ı kullanabilirsiniz.

> [!NOTE]
> Bir `CDaoRecordset` sınıf türediyorsanız, türemiş sınıfınız kendi oluşturucusu sağlamalıdır. Türemiş sınıfınızın oluşturucusunda, `CDaoRecordset::CDaoRecordset`uygun parametreleri ona ileterek oluşturucuyu arayın.

Bir `CDaoDatabase` nesnenin sizin için otomatik olarak oluşturulması ve bağlanması için NULL'u kayıt ayarlı oluşturucunuza geçirin. Bu, kayıt setinizi oluşturmadan önce bir nesne `CDaoDatabase` oluşturmanızı ve bağlamanızı gerektirmeyen kullanışlı bir kısayoldur. `CDaoDatabase` Nesne açık değilse, varsayılan çalışma alanını kullanan sizin için bir [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) nesnesi de oluşturulur. Daha fazla bilgi için [Bkz. CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

## <a name="cdaorecordsetclose"></a><a name="close"></a>CDaoRecordset::Kapat

Nesneyi `CDaoRecordset` kapatmak, nesneyi ilişkili veritabanındaki açık kayıt kümeleri koleksiyonundan kaldırır.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Nesneyi yok `Close` `CDaoRecordset` etmediğinden, aynı veri kaynağını `Open` veya farklı bir veri kaynağını arayarak nesneyi yeniden kullanabilirsiniz.

Bekleyen tüm [AddNew](#addnew) veya [Edit](#edit) ifadeleri iptal edilir ve bekleyen tüm hareketler geri alınır. Bekleyen eklemeleri veya güncellemeleri korumak istiyorsanız, her kayıt `Close` kümesi için aramadan önce [Güncelleştirme'yi](#update) arayın.

Aradıktan `Open` sonra tekrar `Close`arayabilirsiniz. Bu, kayıt kümesi nesnesini yeniden kullanmanıza olanak tanır. Daha iyi bir alternatif [Requery](#requery)aramaktır , mümkünse.

İlgili bilgiler için DAO Yardım'daki "Yöntemi Kapat" konusuna bakın.

## <a name="cdaorecordsetdelete"></a><a name="delete"></a>CDaoRecordset::Delete

Açık bir dinamit türü veya tablo tipi kayıt kümesi nesnesi geçerli kaydı silmek için bu üye işlevi arayın.

```
virtual void Delete();
```

### <a name="remarks"></a>Açıklamalar

Başarılı bir silme işleminden sonra, kayıt kümesinin alan veri üyeleri Null değerine ayarlanır ve silinen kayıttan çıkmak için kayıt kümesinin gezinti üye işlevlerinden birini [(Taşı](#move), [Ara](#seek), [SetBookmark](#setbookmark)vb.) açıkça aramanız gerekir. Kayıtları bir kayıt kümesinden sildiğinizde, aramadan `Delete`önce kayıt kümesinde geçerli bir kayıt olmalıdır; aksi takdirde, MFC bir özel durum atar.

`Delete`geçerli kaydı kaldırır ve erişilemez hale getirir. Silinen kaydı kaldıramaz veya kullanamazsınız, ancak geçerli kalır. Ancak, başka bir kayda geçildikten sonra silinen kaydı yeniden güncel yapamazsınız.

> [!CAUTION]
> Kayıt kümesi güncellenebilir olmalı ve 'yi aradiğinizde `Delete`kayıt setinde geçerli bir kayıt akımı olmalıdır. Örneğin, bir kaydı siler, ancak yeniden aramadan `Delete` önce `Delete` yeni bir kayda kaydırmazsanız, [cdaoException](../../mfc/reference/cdaoexception-class.md)atar.

Hareketleri kullanırsanız ve [CDaoWorkspace'i](../../mfc/reference/cdaoworkspace-class.md#rollback) ararsanız kaydı silebilirsiniz::Rollback üye işlevi. Taban tablo basamaklı silme ilişkisindeki birincil tabloysa, geçerli kaydı silmek yabancı bir tablodaki bir veya daha fazla kaydı da silebilir. Daha fazla bilgi için DAO Yardım'daki "basamaklı silme" tanımına bakın.

Aksine `AddNew` `Edit`ve , `Delete` bir çağrı için `Update`bir çağrı takip edilmez .

İlgili bilgiler için DAO Help'de "Yeni Yöntem Ekle", "Düzenle Yöntemi", "Silme Yöntemi", "Güncelleştirme Yöntemi" ve "Güncellenebilir Özellik" konularına bakın.

## <a name="cdaorecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CDaoRecordset::DoFieldExchange

Çerçeve, bu üye işlevini, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasında otomatik olarak veri alışverişi yapmak için çağırır.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Parametreler

*Pfx*<br/>
Bir `CDaoFieldExchange` nesneye işaretçi içerir. Çerçeve, alan değişimi işlemi için bir bağlam belirtmek için bu nesneyi zaten ayarlamış olacaktır.

### <a name="remarks"></a>Açıklamalar

Ayrıca, parametre veri üyelerinizi, varsa, kayıt kümesinin seçimi için SQL deyimi dizesindeki parametre yer sahiplerine bağlar. DAO kayıt alanı değişimi (DFX) adı verilen alan veri alışverişi her iki yönde de çalışır: kayıt kümesi nesnesinin alan veri üyelerinden veri kaynağındaki kayıt alanlarına ve veri kaynağındaki kayıttan kayıt kümesi nesnesine kadar. Sütunları dinamik olarak bağlıyorsanız, uygulamanız `DoFieldExchange`gerekmez.

Türemiş kayıt kümesi sınıfınız `DoFieldExchange` için normalde uygulamanız gereken tek eylem ClassWizard ile sınıfı oluşturmak ve alan veri üyelerinin adlarını ve veri türlerini belirtmektir. Ayrıca, parametre veri üyelerini belirtmek için ClassWizard'ın yazdıklarına kod ekleyebilirsiniz. Tüm alanlar dinamik olarak bağlanacaksa, parametre veri üyeleri belirtmediğiniz sürece bu işlev etkin değil.

Türemiş kayıt kümesi sınıfınızı ClassWizard ile beyan ettiğinizde, sihirbaz sizin `DoFieldExchange` için aşağıdaki örneğe benzeyen bir geçersiz kılma yazar:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

## <a name="cdaorecordsetedit"></a><a name="edit"></a>CDaoRecordset::Edit

Geçerli kayıtta değişikliklere izin vermek için bu üye işlevi arayın.

```
virtual void Edit();
```

### <a name="remarks"></a>Açıklamalar

`Edit` Üye işlevi aradıktan sonra, geçerli kaydın alanlarında yapılan değişiklikler kopya arabelleği kopyalanır. Kayıtta istenen değişiklikleri yaptıktan sonra, `Update` değişikliklerinizi kaydetmek için arayın. `Edit`kaydedici nin veri üyelerinin değerlerini kaydeder. Ararsanız, `Edit`değişiklik yaparsanız, `Edit` sonra yeniden arayın, kaydın değerleri ilk `Edit` çağrıdan önce oldukları şekilde geri yüklenir.

> [!CAUTION]
> Bir kaydı düzenlediyseniz ve sonra ilk aramadan `Update`başka bir kayda geçen herhangi bir işlemi gerçekleştirirseniz, değişiklikleriniz uyarı yapılmadan kaybolur. Ayrıca, kayıt kümesini veya üst veritabanını kapatırsanız, düzenlenen kaydınız uyarı yapılmadan atılır.

Bazı durumlarda, bir sütunu Null (veri içermeden) yaparak güncelleştirmek isteyebilirsiniz. Bunu yapmak için, alan Null işaretlemek için TRUE bir parametre ile arayın; `SetFieldNull` bu da sütunun güncelleştirilmesine neden olur. Değeri değişmemiş olsa bile bir alanın veri kaynağına yazılmasını `SetFieldDirty` istiyorsanız, TRUE parametresi ile arayın. Alan Null değerine sahip olsa bile bu işe yarar.

Çerçeve işaretleri, DAO kayıt alanı değişimi (DFX) mekanizması tarafından veri kaynağına yazılmasını sağlamak için alan veri üyelerini değiştirdi. Bir alanın değerini değiştirmek genellikle alanı otomatik olarak kirli ayarlar, bu nedenle nadiren [SetFieldDirty'i](#setfielddirty) kendiniz aramanız gerekir, ancak bazen alan veri üyesinin değeri ne olursa olsun sütunların açıkça güncelleştirildiğinden veya eklenmesini sağlamak isteyebilirsiniz. DFX mekanizması da **PSEUDO NULL**kullanımını kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation.](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamaz. Bu durumda, açıkça alanı kirli ayarlamak için gerekli olacaktır. [m_bCheckCacheForDirtyFields'da](#m_bcheckcachefordirtyfields) bulunan bayrak bu otomatik alan denetimini kontrol eder.

Kayıt kümesi nesnesi çok kullanıcılı bir ortamda kötümser bir şekilde `Edit` kilitlendiğinde, güncelleştirme tamamlanana kadar kayıt kullanılan andan itibaren kilitli kalır. Kayıt kümesi iyimser bir şekilde kilitlenirse, kayıt kilitlenir ve veritabanında güncelleştirilmeden hemen önce önceden düzenlenmiş kayıtla karşılaştırılır. Aradığından `Edit`beri kayıt değiştiyse, `Update` işlem başarısız olur ve MFC bir özel durum oluşturur. Kilitleme modunu `SetLockingMode`' ile değiştirebilirsiniz.

> [!NOTE]
> İyimser kilitleme her zaman ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimlerinde kullanılır.

Siz aradıktan `Edit`sonra geçerli kayıt geçerli kalır. Aramak `Edit`için geçerli bir kayıt olması gerekir. Geçerli bir kayıt yoksa veya kayıt kümesi açık bir tablo türüne veya dynaset tipi kayıt kümesi nesnesine atıfta bulunmuyorsa, bir özel durum oluşur. Arama, `Edit` `CDaoException` a'nın aşağıdaki koşullar altında atılmasına neden olur:

- Geçerli bir kayıt yok.

- Veritabanı veya kayıt kümesi salt okunur.

- Kayıtlardaki hiçbir alan güncel değildir.

- Veritabanı veya kayıt kümesi başka bir kullanıcı tarafından özel kullanım için açıldı.

- Başka bir kullanıcı kaydınızı içeren sayfayı kilitledi.

Veri kaynağı hareketleri destekliyorsa, `Edit` aramayı bir hareketin parçası yapabilirsiniz. Aramadan `Edit` önce `CDaoWorkspace::BeginTrans` ve kayıt kümesi açıldıktan sonra aramanız gerektiğini unutmayın. Ayrıca, aramanın `CDaoWorkspace::CommitTrans` `Edit` işlemi tamamlamak `Update` için aramanın yerini tutamadığını da unutmayın. Hareketler hakkında daha fazla `CDaoWorkspace`bilgi için sınıfa bakın.

İlgili bilgiler için DAO Help'de "Yeni Yöntem Ekle", "Düzenle Yöntemi", "Silme Yöntemi", "Güncelleştirme Yöntemi" ve "Güncellenebilir Özellik" konularına bakın.

## <a name="cdaorecordsetfillcache"></a><a name="fillcache"></a>CDaoRecordset::FillÖnbellek

Kayıt kümesinden belirli sayıda kaydı önbelleğe almak için bu üye işlevi arayın.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Parametreler

*pSize*<br/>
Önbelleği dolduracak satır sayısını belirtir. Bu parametreyi atlarsanız, değer alttaki DAO nesnesinin Önbellek özelliği ayarı tarafından belirlenir.

*pBookmark*<br/>
Yer imi belirten bir [COleVariant.](../../mfc/reference/colevariant-class.md) Önbellek, bu yer imi tarafından belirtilen kayıttan başlayarak doldurulur. Bu parametreyi atlarsanız, önbellek, alttaki DAO nesnesinin CacheStart özelliğitarafından gösterilen kayıttan başlayarak doldurulur.

### <a name="remarks"></a>Açıklamalar

Önbelleğe alma, uzak bir sunucudan veri alan veya getiren bir uygulamanın performansını artırır. Önbellek, uygulama çalışırken verilerin büyük olasılıkla yeniden isteneceği varsayımıüzerine, sunucudan en son alınan verileri tutan yerel bellekteki alandır. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, sunucudan almak yerine verilerin önbelleğini denetler ve bu da daha fazla zaman alır. Veri önbellekte kaydedilmez gibi ODBC olmayan veri kaynaklarında veri önbelleğe kullanmanın hiçbir etkisi yoktur.

Önbelleğin alınırken kayıtlarla doldurulmasını beklemek yerine, `FillCache` üye işlevi arayarak önbelleği istediğiniz zaman açıkça doldurabilirsiniz. Bu önbelleği doldurmanın daha `FillCache` hızlı bir yoludur, çünkü aynı anda birden çok kaydı birer değil, aynı anda getirir. Örneğin, her ekran dolusu kayıt görüntülenirken, bir sonraki `FillCache` ekran dolusu kaydı almak için uygulama çağrınızı alabilirsiniz.

Kayıt kümesi nesneleri ile erişilen herhangi bir ODBC veritabanı yerel bir önbelleğe sahip olabilir. Önbelleği oluşturmak için, uzak veri kaynağından bir kayıt kümesi `SetCacheSize` `SetCacheStart` nesnesi açın ve ardından kayıt kümesinin ve üye işlevlerini çağırın. *lSize* ve *lBookmark* tarafından `SetCacheSize` belirtilen aralık dışında kısmen veya tamamen `SetCacheStart`bir aralık oluşturursanız ve , bu aralığın dışındaki kayıt kümesinin bölümü yoksayılır ve önbelleğe yüklenmez. `FillCache` Uzak veri kaynağında kalandan daha fazla kayıt isterse, yalnızca kalan kayıtlar getirilir ve özel durum atılmaz.

Önbellekten getirilen kayıtlar, diğer kullanıcılar tarafından kaynak verilerle eş zamanlı olarak yapılan değişiklikleri yansıtmaz.

`FillCache`yalnızca önbelleğe alınmamış kayıtları getirir. Önbelleğe alınan tüm verilerin güncelleştirmesini zorlamak `SetCacheSize` için, üye işlevi 0'a eşit `SetCacheSize` bir *lSize* parametresi ile çağırın, başlangıçta istediğiniz önbelleğin boyutuna eşit *lSize* parametresi ile yeniden arayın ve ardından çağırın. `FillCache`

İlgili bilgiler için DAO Yardım'daki "FillCache Method" konusuna bakın.

## <a name="cdaorecordsetfind"></a><a name="find"></a>CDaoRecordset::Bul

Karşılaştırma işleci kullanarak bir dinamit veya anlık görüntü tipi kayıt kümesinde belirli bir dizeyi bulmak için bu üye işlevi arayın.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lFindType*<br/>
İstenilen Bul işleminin türünü gösteren bir değer. Olası değerler şunlardır:

- AFX_DAO_NEXT Eşleşen bir dizenin sonraki konumunu bulun.

- AFX_DAO_PREV Eşleşen bir dizenin önceki konumunu bulun.

- AFX_DAO_FIRST Eşleşen bir dizenin ilk konumunu bulun.

- AFX_DAO_LAST Eşleşen bir dizenin son konumunu bulun.

*lpszFiltre*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi **(SQL**deyimindeki **WHERE** yan tümcesi gibi) Örneğin:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dizeilk, sonraki, önceki veya son örneğini bulabilirsiniz. `Find`sanal bir işlevdir, böylece geçersiz kılınabilir ve kendi uygulamanızı ekleyebilirsiniz. Üye `FindFirst` `FindPrev` `Find` işlevler üye işlevi çağırır, böylece tüm Bul işlemlerinin davranışını denetlemek için kullanabilirsiniz. `Find` `FindLast` `FindNext`

Tablo türünde bir kayıt kümesinde bir kaydı bulmak [için, Üye Ara](#seek) işlevini arayın.

> [!TIP]
> Sahip olduğunuz kayıt kümesi ne kadar `Find` küçükse, o kadar etkili olur. Genel olarak ve özellikle ODBC verileriyle, yalnızca istediğiniz kayıtları alan yeni bir sorgu oluşturmak daha iyidir.

İlgili bilgiler için DAO Yardım'da "FindFirst, FindLast, FindNext, FindPrevious Methods" konusuna bakın.

## <a name="cdaorecordsetfindfirst"></a><a name="findfirst"></a>CDaoRecordset::İlk bul

Belirtilen durumla eşleşen ilk kaydı bulmak için bu üye işlevini arayın.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFiltre*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi **(SQL**deyimindeki **WHERE** yan tümcesi gibi)

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`FindFirst` Üye işlev, aramasına kayıt kümesinin başından itibaren başlar ve kayıt kümesinin sonuna kadar arama lar.

Aramanızdaki tüm kayıtları (sadece belirli bir koşulu karşılayanlar değil) eklemek istiyorsanız, kayıttan kayda geçmek için Hareket işlemlerinden birini kullanın. Tablo türünde bir kayıt kümesinde bir `Seek` kaydı bulmak için üye işlevi arayın.

Ölçütle eşleşen bir kayıt bulunmazsa, geçerli kayıt işaretçisi belirlenmez ve `FindFirst` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan, ilk oluşumu belirleyen, `FindFirst` `FindNext` bir sonraki oluşumu belirleyen ve benzeri birden fazla kayıt içeriyorsa.

> [!CAUTION]
> Geçerli kaydı düzenlemeniz durumunda, başka bir kayda `Update` geçmeden önce üye işlevi arayarak değişiklikleri kaydettiğinden emin olun. Güncelleştirmeden başka bir kayda geçerseniz, değişiklikleriniz uyarı yapılmadan kaybolur.

Üye `Find` işlevler konumdan ve aşağıdaki tabloda belirtilen yönde arama:

|İşlemleri bulma|Başla|Arama yönü|
|---------------------|-----------|----------------------|
|`FindFirst`|Kayıt kümesinin başlangıcı|Kayıt sonu|
|`FindLast`|Kayıt sonu|Kayıt kümesinin başlangıcı|
|`FindNext`|Geçerli kayıt|Kayıt sonu|
|`FindPrevious`|Geçerli kayıt|Kayıt kümesinin başlangıcı|

> [!NOTE]
> Aradığınızda, `FindLast`Microsoft Jet veritabanı altyapısı, arama başlamadan önce kayıt setinizi tamamen doldurur, eğer bu zaten yapılmamışsa. İlk arama sonraki aramalardan daha uzun sürebilir.

Bul işlemlerinden birini kullanmak, arama `MoveFirst` yla `MoveNext`veya ancak, bir koşul belirtmeden ilk veya sonraki kaydı geçerli kılan la aynı şey değildir. Bir Taşı işlemiyle Bul işlemini takip edebilirsiniz.

Bul işlemlerini kullanırken aşağıdakileri göz önünde bulundurun:

- Sıfırsız `Find` döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda geri konumlandırmanız gerekir.

- Yalnızca ileriye doğru kaydırma anlık görüntü türü kayıt kümesiyle Bul işlemini kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyorsanız bile, tarih içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmalısınız; aksi takdirde, eşleşen kayıtlar bulunamayabilir.

- ODBC veritabanları ve büyük dinamitlerle çalışırken, özellikle büyük kayıt kümeleriyle çalışırken Bul işlemlerini kullanmanın yavaş olduğunu keşfedebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizine sahip kayıtları alan nesnelerle SQL sorgularını kullanarak performansı artırabilirsiniz.

İlgili bilgiler için DAO Yardım'da "FindFirst, FindLast, FindNext, FindPrevious Methods" konusuna bakın.

## <a name="cdaorecordsetfindlast"></a><a name="findlast"></a>CDaoRecordset::FindLast

Belirtilen durumla eşleşen son kaydı bulmak için bu üye işlevini arayın.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFiltre*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi **(SQL**deyimindeki **WHERE** yan tümcesi gibi)

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`FindLast` Üye işlev, kayıt kümesinin sonunda aramaya başlar ve kayıt kümesinin başına doğru geriye doğru arar.

Aramanızdaki tüm kayıtları (sadece belirli bir koşulu karşılayanlar değil) eklemek istiyorsanız, kayıttan kayda geçmek için Hareket işlemlerinden birini kullanın. Tablo türünde bir kayıt kümesinde bir `Seek` kaydı bulmak için üye işlevi arayın.

Ölçütle eşleşen bir kayıt bulunmazsa, geçerli kayıt işaretçisi belirlenmez ve `FindLast` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan, ilk oluşumu belirleyen, `FindFirst` ilk oluşumdan sonraki `FindNext` oluşumu belirleyen ve benzeri birden fazla kayıt içeriyorsa.

> [!CAUTION]
> Geçerli kaydı düzenlemeniz durumunda, başka bir kayda `Update` geçmeden önce üye işlevi arayarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirmeden başka bir kayda geçerseniz, değişiklikleriniz uyarı yapılmadan kaybolur.

Bul işlemlerinden birini kullanmak, arama `MoveFirst` yla `MoveNext`veya ancak, bir koşul belirtmeden ilk veya sonraki kaydı geçerli kılan la aynı şey değildir. Bir Taşı işlemiyle Bul işlemini takip edebilirsiniz.

Bul işlemlerini kullanırken aşağıdakileri göz önünde bulundurun:

- Sıfırsız `Find` döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda geri konumlandırmanız gerekir.

- Yalnızca ileriye doğru kaydırma anlık görüntü türü kayıt kümesiyle Bul işlemini kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyorsanız bile, tarih içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmalısınız; aksi takdirde, eşleşen kayıtlar bulunamayabilir.

- ODBC veritabanları ve büyük dinamitlerle çalışırken, özellikle büyük kayıt kümeleriyle çalışırken Bul işlemlerini kullanmanın yavaş olduğunu keşfedebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizine sahip kayıtları alan nesnelerle SQL sorgularını kullanarak performansı artırabilirsiniz.

İlgili bilgiler için DAO Yardım'da "FindFirst, FindLast, FindNext, FindPrevious Methods" konusuna bakın.

## <a name="cdaorecordsetfindnext"></a><a name="findnext"></a>CDaoRecordset::Find

Belirtilen durumla eşleşen bir sonraki kaydı bulmak için bu üye işlevini arayın.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFiltre*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi **(SQL**deyimindeki **WHERE** yan tümcesi gibi)

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`FindNext` Üye işlev, geçerli kayıtta aramaya başlar ve kayıt kümesinin sonuna kadar arama lar ayarlar.

Aramanızdaki tüm kayıtları (sadece belirli bir koşulu karşılayanlar değil) eklemek istiyorsanız, kayıttan kayda geçmek için Hareket işlemlerinden birini kullanın. Tablo türünde bir kayıt kümesinde bir `Seek` kaydı bulmak için üye işlevi arayın.

Ölçütle eşleşen bir kayıt bulunmazsa, geçerli kayıt işaretçisi belirlenmez ve `FindNext` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan, ilk oluşumu belirleyen, `FindFirst` `FindNext` bir sonraki oluşumu belirleyen ve benzeri birden fazla kayıt içeriyorsa.

> [!CAUTION]
> Geçerli kaydı düzenlemeniz durumunda, başka bir kayda `Update` geçmeden önce üye işlevi arayarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirmeden başka bir kayda geçerseniz, değişiklikleriniz uyarı yapılmadan kaybolur.

Bul işlemlerinden birini kullanmak, arama `MoveFirst` yla `MoveNext`veya ancak, bir koşul belirtmeden ilk veya sonraki kaydı geçerli kılan la aynı şey değildir. Bir Taşı işlemiyle Bul işlemini takip edebilirsiniz.

Bul işlemlerini kullanırken aşağıdakileri göz önünde bulundurun:

- Sıfırsız `Find` döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda geri konumlandırmanız gerekir.

- Yalnızca ileriye doğru kaydırma anlık görüntü türü kayıt kümesiyle Bul işlemini kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyorsanız bile, tarih içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmalısınız; aksi takdirde, eşleşen kayıtlar bulunamayabilir.

- ODBC veritabanları ve büyük dinamitlerle çalışırken, özellikle büyük kayıt kümeleriyle çalışırken Bul işlemlerini kullanmanın yavaş olduğunu keşfedebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizine sahip kayıtları alan nesnelerle SQL sorgularını kullanarak performansı artırabilirsiniz.

İlgili bilgiler için DAO Yardım'da "FindFirst, FindLast, FindNext, FindPrevious Methods" konusuna bakın.

## <a name="cdaorecordsetfindprev"></a><a name="findprev"></a>CDaoRecordset::FindPrev

Belirtilen durumla eşleşen önceki kaydı bulmak için bu üye işlevini arayın.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parametreler

*lpszFiltre*<br/>
Kaydı bulmak için kullanılan bir dize ifadesi **(SQL**deyimindeki **WHERE** yan tümcesi gibi)

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`FindPrev` Üye işlev, geçerli kayıtta aramaya başlar ve kayıt kümesinin başına doğru geriye doğru arar.

Aramanızdaki tüm kayıtları (sadece belirli bir koşulu karşılayanlar değil) eklemek istiyorsanız, kayıttan kayda geçmek için Hareket işlemlerinden birini kullanın. Tablo türünde bir kayıt kümesinde bir `Seek` kaydı bulmak için üye işlevi arayın.

Ölçütle eşleşen bir kayıt bulunmazsa, geçerli kayıt işaretçisi belirlenmez ve `FindPrev` sıfır döndürür. Kayıt kümesi ölçütleri karşılayan, ilk oluşumu belirleyen, `FindFirst` `FindNext` bir sonraki oluşumu belirleyen ve benzeri birden fazla kayıt içeriyorsa.

> [!CAUTION]
> Geçerli kaydı düzenlemeniz durumunda, başka bir kayda `Update` geçmeden önce üye işlevi arayarak değişiklikleri kaydettiğinizden emin olun. Güncelleştirmeden başka bir kayda geçerseniz, değişiklikleriniz uyarı yapılmadan kaybolur.

Bul işlemlerinden birini kullanmak, arama `MoveFirst` yla `MoveNext`veya ancak, bir koşul belirtmeden ilk veya sonraki kaydı geçerli kılan la aynı şey değildir. Bir Taşı işlemiyle Bul işlemini takip edebilirsiniz.

Bul işlemlerini kullanırken aşağıdakileri göz önünde bulundurun:

- Sıfırsız `Find` döndürürse, geçerli kayıt tanımlı değildir. Bu durumda, geçerli kayıt işaretçisini geçerli bir kayda geri konumlandırmanız gerekir.

- Yalnızca ileriye doğru kaydırma anlık görüntü türü kayıt kümesiyle Bul işlemini kullanamazsınız.

- Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmıyorsanız bile, tarih içeren alanları ararken ABD tarih biçimini (ay-gün-yıl) kullanmalısınız; aksi takdirde, eşleşen kayıtlar bulunamayabilir.

- ODBC veritabanları ve büyük dinamitlerle çalışırken, özellikle büyük kayıt kümeleriyle çalışırken Bul işlemlerini kullanmanın yavaş olduğunu keşfedebilirsiniz. Özelleştirilmiş **ORDERBY** veya **WHERE** yan tümceleri, parametre sorguları veya `CDaoQuerydef` belirli dizine sahip kayıtları alan nesnelerle SQL sorgularını kullanarak performansı artırabilirsiniz.

İlgili bilgiler için DAO Yardım'da "FindFirst, FindLast, FindNext, FindPrevious Methods" konusuna bakın.

## <a name="cdaorecordsetgetabsoluteposition"></a><a name="getabsoluteposition"></a>CDaoRecordset::GetAbsolutePosition

Kayıt kümesi nesnesinin geçerli kaydının kayıt numarasını verir.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıt sayısı0'dan bir sonsayı. Kayıt kümesindeki geçerli kaydın ordinal konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

Dayanak DAO nesnesinin AbsolutePosition özellik değeri sıfır tabanlıdır; 0'lık bir ayar, kayıt kümesindeki ilk kayda işaret eder. Kayıt kümesindeki doldurulmuş kayıt sayısını [GetRecordCount'u](#getrecordcount)arayarak belirleyebilirsiniz. Count'u belirlemek için tüm kayıtlara erişmesi gerektiğinden arama `GetRecordCount` biraz zaman alabilir.

Geçerli kayıt yoksa, kayıt kümesinde kayıt olmadığında olduğu gibi- 1 döndürülür. Geçerli kayıt silinirse, AbsolutePosition özellik değeri tanımlanmaz ve başvurulmuşsa MFC bir özel durum atar. Dynaset tipi kayıt kümeleri için, dizinin sonuna yeni kayıtlar eklenir.

> [!NOTE]
> Bu özellik, vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer imleri hala belirli bir konuma koruma ve geri dönmenin önerilen yoludur ve geçerli kaydı tüm kayıt kümesi nesneleri arasında konumlandırmanın tek yoludur. Özellikle, kendisinden önceki kayıt(lar) silindiğinde, belirli bir kaydın konumu değişir. Orderby yan tümcesi kullanılarak bir SQL deyimi yle oluşturulmadığı sürece, kayıt kümesi yeniden oluşturulursa belirli bir kaydın aynı mutlak konuma **ORDERBY** sahip olacağına dair bir güvence de yoktur.

> [!NOTE]
> Bu üye işlev yalnızca dynaset türü ve anlık görüntü tipi kayıt kümeleri için geçerlidir.

İlgili bilgiler için DAO Yardım'daki "AbsolutePosition Property" konusuna bakın.

## <a name="cdaorecordsetgetbookmark"></a><a name="getbookmark"></a>CDaoRecordset::GetBookmark

Belirli bir kayıttaki yer imi değerini elde etmek için bu üye işlevi arayın.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kayıttaki yer işaretini temsil eden bir değer verir.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, kayıtlarının her birinin bunları destekliyorsa zaten benzersiz bir yer imi vardır. Kayıt `CanBookmark` kümesinin yer imlerini destekleyip desteklemediğini belirlemek için arayın.

Yer işaretinin değerini bir `COleVariant` nesneye atayarak yer işaretini geçerli kayıt için kaydedebilirsiniz. Farklı bir kayda geçtikten sonra herhangi bir zamanda `SetBookmark` bu kayda hızlı bir şekilde `COleVariant` dönmek için, o nesnenin değerine karşılık gelen bir parametreyle arayın.

> [!NOTE]
> [Yeniden Sorgu'yı çağırmak](#requery) DAO yer imlerini değiştirir.

İlgili bilgiler için DAO Yardım'daki "Yer Imi Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetcachesize"></a><a name="getcachesize"></a>CDaoRecordset::GetÖnbellek

Önbelleğe alınmış kayıt sayısını elde etmek için bu üye işlevi arayın.

```
long GetCacheSize();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC veri kaynağından yerel olarak önbelleğe alınacak verileri içeren dynaset türündeki kayıt kümesindeki kayıt sayısını belirten bir değer.

### <a name="remarks"></a>Açıklamalar

Veri önbelleğe alma, dynaset türü kayıt kümesi nesneleri aracılığıyla uzak bir sunucudan veri alan bir uygulamanın performansını artırır. Önbellek, uygulama çalışırken verilerin yeniden istenmesi durumunda, en son sunucudan alınan verileri tutan yerel bellekteki bir alandır. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, sunucudan almak yerine istenen verilerin önbelleğini önce denetler ve bu da daha fazla zaman alır. ODBC veri kaynağından gelmeyen veriler önbelleğe kaydedilmez.

Ekli tablo gibi herhangi bir ODBC veri kaynağının yerel önbelleği olabilir.

İlgili bilgiler için DAO Yardımı'ndaki "Önbellek, Önbellek Özellikleri" konusuna bakın.

## <a name="cdaorecordsetgetcachestart"></a><a name="getcachestart"></a>CDaoRecordset::GetCacheStart

Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer imi değerini elde etmek için bu üye işlevi arayın.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Dönüş Değeri

Önbelleğe `COleVariant` alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir kayıt.

### <a name="remarks"></a>Açıklamalar

Microsoft Jet veritabanı altyapısı önbellek aralığındaki kayıtları önbellek ten ister ve sunucudan önbellek aralığının dışındaki kayıtları ister.

> [!NOTE]
> Önbellekten alınan kayıtlar, diğer kullanıcılar tarafından kaynak verilerle eş zamanlı olarak yapılan değişiklikleri yansıtmaz.

İlgili bilgiler için DAO Yardımı'ndaki "Önbellek, Önbellek Özellikleri" konusuna bakın.

## <a name="cdaorecordsetgetcurrentindex"></a><a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex

Dizinlenmiş tablo türü `CDaoRecordset` nesnesinde şu anda kullanılmakta olan dizin belirlemek için bu üye işlevi arayın.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo `CString` türünde bir kayıt kümesiyle kullanılmakta olan dizinin adını içeren bir dizin. Dizin ayarlanmadıysa boş bir dize döndürür.

### <a name="remarks"></a>Açıklamalar

Bu dizin, tablo türü kayıt kümesindeki kayıtları sıralamanın temelini oluşturur ve kayıtları bulmak için [Seek](#seek) üye işlevi tarafından kullanılır.

Bir `CDaoRecordset` nesnenin birden fazla dizini olabilir, ancak aynı anda yalnızca bir dizin kullanabilir [(cdaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi üzerinde tanımlanmış birkaç dizin olsa da).

İlgili bilgiler için, "Dizin Nesnesi" konusuna ve DAO Yardımı'ndaki "geçerli dizin" tanımına bakın.

## <a name="cdaorecordsetgetdatecreated"></a><a name="getdatecreated"></a>CDaoRecordset::GetDateCreated

Bir taban tablooluşturulduğu tarih ve saati almak için bu üye işlevi arayın.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel tablonun oluşturulduğu tarih ve saati içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablonun oluşturulduğu bilgisayardan türetilir.

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaorecordsetgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated

Şeanın en son güncelleştirilen tarih ve saati almak için bu üye işlevini arayın.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel tablo yapısının (şema) en son güncelleştirilme tarihini ve saatini içeren bir [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları, temel tablo yapısının (şema) en son güncelleştirildiği bilgisayardan türetilir.

İlgili bilgiler için DAO Yardım'daki "DateCreated, LastUpdated Properties" konusuna bakın.

## <a name="cdaorecordsetgetdefaultdbname"></a><a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName

Bu kayıt kümesi için veritabanının adını belirlemek için bu üye işlevi arayın.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CString` kayıt kümesinin türetildiği veritabanının yolunu ve adını içeren a.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)için bir işaretçi olmadan oluşturulursa, bu yol varsayılan veritabanını açmak için kayıt kümesi tarafından kullanılır. Varsayılan olarak, bu işlev boş bir dize döndürür. ClassWizard yeni bir kayıt kümesi `CDaoRecordset`türettiğinde, sizin için bu işlevi oluşturur.

Aşağıdaki örnek, dize için gerekli olan\\\\çift eğik çizgi ( ) dizesinin doğru yorumlanması için gerekli olan kullanımı göstermektedir.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

## <a name="cdaorecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL

Çerçeve, kayıt kümesinin dayandığı varsayılan SQL deyimini almak için bu üye işlevi çağırır.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan `CString` SQL deyimini içeren bir.

### <a name="remarks"></a>Açıklamalar

Bu bir tablo adı veya SQL **SELECT** deyimi olabilir.

ClassWizard ile kayıt kümesi sınıfınızı beyan ederek dolaylı olarak varsayılan SQL deyimini tanımlarsınız ve ClassWizard bu görevi sizin yerinize gerçekleştirir.

Null SQL dizesini [Aç'a](#open)geçirirseniz, bu işlev kayıt setinizin tablo adını veya SQL'ini belirlemek için çağrılır.

## <a name="cdaorecordsetgeteditmode"></a><a name="geteditmode"></a>CDaoRecordset::GetEditMode

Aşağıdaki değerlerden biri olan düzenleme durumunu belirlemek için bu üye işlevi arayın:

```
short GetEditMode();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli kaydın düzenleme durumunu gösteren bir değer verir.

### <a name="remarks"></a>Açıklamalar

|Değer|Açıklama|
|-----------|-----------------|
|`dbEditNone`|Düzenleme işlemi devam ediyor.|
|`dbEditInProgress`|`Edit`çağrıldı.|
|`dbEditAdd`|`AddNew`çağrıldı.|

İlgili bilgiler için DAO Yardım'daki "EditMode Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetfieldcount"></a><a name="getfieldcount"></a>CDaoRecordset::GetFieldCount

Kayıt kümesinde tanımlanan alan (sütun) sayısını almak için bu üye işlevi arayın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki alan sayısı.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "Count Property" konusuna bakın.

## <a name="cdaorecordsetgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo

Kayıt kümesindeki alanlar hakkında bilgi almak için bu üye işlevi arayın.

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

*Nındex*<br/>
Dizin tarafından arama için, kayıt kümesinin Alanlar koleksiyonunda önceden tanımlanmış alanın sıfır tabanlı dizin.

*Fieldınfo*<br/>
[CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bir başvuru.

*dwInfoOptions*<br/>
Kayıt kümesi hakkında hangi bilgilerin alınarak alınamasını belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir. En iyi performans için yalnızca ihtiyacınız olan bilgi düzeyini alın:

- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, Tür, Boyut, Öznitelikler

- `AFX_DAO_SECONDARY_INFO`Birincil bilgi, artı: Ordinal Position, Gerekli, İzin Sıfır Uzunluk, Collating Sipariş, Yabancı Ad, Kaynak Alan, Kaynak Tablo

- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgiler, artı: Varsayılan Değer, Doğrulama Kuralı, Doğrulama Metni

*Lpszname*<br/>
Alanın adı.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir alanı dizin olarak aramanızı sağlar. Diğer sürüm, bir alanı ada göre aramanızı sağlar.

Döndürülen bilgilerin açıklaması için [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CDaoRecordset::GetFieldValue

Kayıt kümesindeki verileri almak için bu üye işlevini arayın.

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

*Lpszname*<br/>
Bir alanın adını içeren bir dize için işaretçi.

*varValue*<br/>
Bir alanın `COleVariant` değerini depolayacak bir nesneye başvuru.

*Nındex*<br/>
Dizin tarafından arama için, kayıt kümesinin Alanlar koleksiyonundaki alanın sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

`GetFieldValue` Bu döndürme iki sürümü bir alanın değerini içeren bir [COleVariant](../../mfc/reference/colevariant-class.md) nesnesi döndürür.

### <a name="remarks"></a>Açıklamalar

Bir alanı ada veya ordinal konuma göre ada göre alabilirsiniz.

> [!NOTE]
> Nesne döndüren bir `COleVariant` sürümü `COleVariant` çağırmak yerine, nesne başvurularını parametre olarak alan bu üye işlevin sürümlerinden birini çağırmak daha verimlidir. Bu işlevin ikinci sürümleri geriye dönük uyumluluk için tutulur.

DoFieldExchange mekanizmasını kullanarak statik olarak bağlama sütunları yerine alanları çalışma zamanında dinamik olarak bağlamak için kullanın `GetFieldValue` ve [SetFieldValue.](#setfieldvalue) [DoFieldExchange](#dofieldexchange)

`GetFieldValue`ve `DoFieldExchange` mekanizma performansı artırmak için kombine edilebilir. Örneğin, yalnızca `GetFieldValue` isteğe bağlı olarak ihtiyacınız olan bir değeri almak ve bu aramayı arabirimdeki "Daha Fazla Bilgi" düğmesine atamak için kullanın.

İlgili bilgiler için DAO Yardım'daki "Alan Nesnesi" ve "Değer Özelliği" konularına bakın.

## <a name="cdaorecordsetgetindexcount"></a><a name="getindexcount"></a>CDaoRecordset::GetIndexCount

Tablo türü kayıt kümesinde bulunan dizin sayısını belirlemek için bu üye işlevini arayın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo türü kayıt kümesindeki dizin sayısı.

### <a name="remarks"></a>Açıklamalar

`GetIndexCount`kayıt kümesindeki tüm dizinler arasında döngü kurmak için yararlıdır. Bu amaçla, `GetIndexCount` [GetIndexInfo](#getindexinfo)ile birlikte kullanın. Bu üye işlevi dynaset türünde veya anlık görüntü tipi kayıt kümelerinde çağırırsanız, MFC bir özel durum oluşturur.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetindexinfo"></a><a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo

Bir kayıt kümesinin altında yatan taban tabloda tanımlanan bir dizin hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

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

*Nındex*<br/>
Tablonun Dizinler koleksiyonundaki sıfır tabanlı dizin, sayısal konuma göre arama için.

*indexinfo*<br/>
[CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bir başvuru.

*dwInfoOptions*<br/>
Dizin hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir. En iyi performans için yalnızca ihtiyacınız olan bilgi düzeyini alın:

- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, Alan Bilgisi, Alanlar

- `AFX_DAO_SECONDARY_INFO`Birincil bilgi, artı: Birincil, Benzersiz, Kümelenmiş, IgnoreNulls, Gerekli, Yabancı

- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgiler, artı: Farklı Sayı

*Lpszname*<br/>
Ada göre arama yapmak için dizin nesnesinin adına işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir dizin imi koleksiyondaki konumuna göre aramanızı sağlar. Diğer sürüm, bir dizini ada göre aramanızı sağlar.

Döndürülen bilgilerin açıklaması için [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

İlgili bilgiler için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetlastmodifiedbookmark"></a><a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark

En son eklenen veya güncelleştirilen kaydın yer işaretini almak için bu üye işlevini arayın.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Dönüş Değeri

En `COleVariant` son eklenen veya değiştirilen kaydı gösteren bir yer imi içeren.

### <a name="remarks"></a>Açıklamalar

Bir kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, kayıtlarının her birinin bunları destekliyorsa zaten benzersiz bir yer imi vardır. Kayıt kümesinin yer imlerini destekleyip desteklemeyin için [GetBookmark'](#getbookmark) ı arayarak. Kayıt kümesi yer imlerini desteklemiyorsa, bir `CDaoException` atılır.

Bir kayıt eklediğinizde, kayıt kümesinin sonunda görünür ve geçerli kayıt değildir. Yeni kaydın güncel olmasını `GetLastModifiedBookmark` sağlamak `SetBookmark` için, yeni eklenen kayda dönmek için arayın ve arayın.

İlgili bilgiler için DAO Yardım'daki "LastModiÖzellik" konusuna bakın.

## <a name="cdaorecordsetgetlockingmode"></a><a name="getlockingmode"></a>CDaoRecordset::GetLockingMode

Kayıt kümesi için geçerli olan kilitleme türünü belirlemek için bu üye işlevi arayın.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Dönüş Değeri

Nonzero kilitleme türü kötümser, aksi takdirde 0 iyimser kayıt kilitleme için.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme etkin olduğunda, [düzenle](#edit) üye işlevini çağırır çağırmaz düzenlediğiniz kaydı içeren veri sayfası kilitlenir. Sayfanın kilidi, [ÜyeYi](#update) [Kapat](#close) işlevini veya Taşı veya Bul işlemlerinden herhangi birini aradiğinizde açılır.

İyimser kilitleme etkin olduğunda, kaydı içeren veri sayfası yalnızca `Update` üye işlevle güncelleştirilirken kilitlenir.

ODBC veri kaynakları ile çalışırken, kilitleme modu her zaman iyimserdir.

İlgili bilgiler için DAO Yardım'da "Kilitleme Özelliği" ve "Çok Kullanıcılı Uygulamalarda Kilitleme Davranışı" konularına bakın.

## <a name="cdaorecordsetgetname"></a><a name="getname"></a>CDaoRecordset::GetName

Kayıt kümesinin adını almak için bu üye işlevi arayın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt `CString` kümesinin adını içeren bir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin adı bir harfle başlamalı ve en fazla 40 karakter içerebilir. Sayıları içerebilir ve karakterleri alt çizebilir, ancak noktalama işareti ni veya boşluk içeremez.

İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetparamvalue"></a><a name="getparamvalue"></a>CDaoRecordset::GetParamValue

Altta yatan DAOParameter nesnesinde depolanan belirtilen parametrenin geçerli değerini almak için bu üye işlevi arayın.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Parametrenin altta yatan DAOParameter nesnesindeki sayısal konumu.

*Lpszname*<br/>
Değerini istediğiniz parametrenin adı.

### <a name="return-value"></a>Dönüş Değeri

[COleVariant](../../mfc/reference/colevariant-class.md) sınıfının parametre değerini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Parametreye ada göre veya koleksiyondaki sayısal konumuna göre erişebilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Parametre Nesnesi" konusuna bakın.

## <a name="cdaorecordsetgetpercentposition"></a><a name="getpercentposition"></a>CDaoRecordset::GetPercentPosition

Dynaset tipi veya anlık görüntü tipi kayıt kümesiyle `GetPercentPosition` çalışırken, kayıt kümesini tam olarak doldurmadan önce ararsanız, hareket miktarı [GetRecordCount'u](#getrecordcount)arayarak erişilen kayıt sayısına göredir.

```
float GetPercentPosition();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesindeki kayıtların yüzdesini temel alan, kayıt kümesi nesnesindeki geçerli kaydın yaklaşık konumunu gösteren 0 ile 100 arasındaki bir sayı.

### <a name="remarks"></a>Açıklamalar

Tüm kayıt kümelerinin popülasyonunu tamamlamak için [MoveLast'ı](#movelast) arayarak son kayda geçebilirsiniz, ancak bu önemli miktarda zaman alabilir.

Dizinleri `GetPercentPosition` olmayan tablolar da dahil olmak üzere üç kayıt kümesi nesnesi türünü de arayabilirsiniz. Ancak, yalnızca `GetPercentPosition` ileri kaydırma anlık görüntülerini veya harici bir veritabanına karşı geçiş sorgusundan açılan bir kayıt kümesini çağıramazsınız. Geçerli bir kayıt yoksa veya geçerli kayıt silinmişse, bir `CDaoException` atılmıştır.

İlgili bilgiler için DAO Yardım'daki "PercentPosition Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetrecordcount"></a><a name="getrecordcount"></a>CDaoRecordset::GetRecordCount

Kayıt kümesindeki kaç kayıt kaydına erişildiğini öğrenmek için bu üye işlevini arayın.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi nesnesinde erişilen kayıt sayısını verir.

### <a name="remarks"></a>Açıklamalar

`GetRecordCount`tüm kayıtlara erişilene kadar dynaset türünde veya anlık görüntü tipi kayıt kümesinde kaç kayıt bulunduğunu göstermez. Bu üye işlev çağrısının tamamlanması önemli miktarda zaman alabilir.

Son kayda erişildikten sonra, iade değeri kayıt kümesindeki silinmemiş kayıtların toplam sayısını gösterir. Son kaydın erişilmesiiçin zorlamak için, kayıt kümesi için `MoveLast` veya `FindLast` üye işlevini arayın. Sorgunuzun geri döneceği yaklaşık kayıt sayısını belirlemek için bir SQL Sayısı da kullanabilirsiniz.

Uygulamanız dynaset tipi kayıt kümesindeki kayıtları sildiği için, geri dönüş değeri `GetRecordCount` azalır. Ancak, geçerli kayıt silinen bir `GetRecordCount` kayda yerleştirilene kadar diğer kullanıcılar tarafından silinen kayıtlar yansıtılmaz. Kayıt sayısını etkileyen bir hareketi yürütürseniz ve daha `GetRecordCount` sonra hareketi geri alırsanız, kalan kayıtların gerçek sayısını yansıtmaz.

Anlık görüntü `GetRecordCount` türündeki kayıt kümesinin değeri, temel tablolardaki değişikliklerden etkilenmez.

Tablo türündeki kayıt kümesinin `GetRecordCount` değeri tablodaki yaklaşık kayıt sayısını yansıtır ve tablo kayıtları ekleyip silinir silinmez hemen etkilenir.

Kayıt olmayan bir kayıt kümesi 0 değeri döndürür. Ekli tablolar veya ODBC veritabanları ile `GetRecordCount` çalışırken, her zaman döndürür - 1. `Requery` Üye işlevini kayıt kümesinde çağırmak, sorgu `GetRecordCount` yeniden yürütülür gibi değerini sıfırlar.

İlgili bilgiler için DAO Yardım'daki "RecordCount Property" konusuna bakın.

## <a name="cdaorecordsetgetsql"></a><a name="getsql"></a>CDaoRecordset::GetSQL

Açıldığında kayıt kümesinin kayıtlarını seçmek için kullanılan SQL deyimini almak için bu üye işlevini arayın.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Dönüş Değeri

A, `CString` SQL deyimini içerir.

### <a name="remarks"></a>Açıklamalar

Bu genellikle bir SQL **SELECT** deyimi olacaktır.

Döndürülen `GetSQL` dize genellikle *lpszSQL* parametresinde Open [üye](#open) işlevine geçmiş olabileceğiniz herhangi bir dizeden farklıdır. Bunun nedeni, kayıt kümesinin, classwizard `Open`ile belirttiğiniz ve [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) veri üyelerine ne aktardığınıza göre tam bir SQL deyimi oluşturmasıdır.

> [!NOTE]
> Bu üye işlevini yalnızca `Open`aradıktan sonra arayın.

İlgili bilgiler için DAO Yardım'daki "SQL Özelliği" konusuna bakın.

## <a name="cdaorecordsetgettype"></a><a name="gettype"></a>CDaoRecordset::GetType

Kayıt kümesini açtıktan sonra bu üye işlevi çağırArak kayıt kümesi nesnesinin türünü belirleyin.

```
short GetType();
```

### <a name="return-value"></a>Dönüş Değeri

Bir kayıt kümesitürünü gösteren aşağıdaki değerlerden biri:

- `dbOpenTable`Tablo tipi kayıt seti

- `dbOpenDynaset`Dynaset tipi kayıt seti

- `dbOpenSnapshot`Anlık görüntü tipi kayıt kümesi

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "Özellik Yazın" konusuna bakın.

## <a name="cdaorecordsetgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule

Verileri doğrulamak için kullanılan kuralı belirlemek için bu üye işlevi arayın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo `CString` değiştirildikçe veya eklendikçe kayıttaki verileri doğrulayan bir değer içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu kural metin tabanlıdır ve temel tablo her değiştirilse uygulanır. Veriler yasal değilse, MFC bir özel durum oluşturur. Döndürülen hata iletisi, belirtilirse, alttaki alan nesnesinin Doğrulama Metni özelliğinin metni veya alttaki alan nesnesinin Doğrulama Kuralı özelliği tarafından belirtilen ifademetnidir. Hata iletisinin metnini almak için [GetValidationText'i](#getvalidationtext) arayabilirsiniz.

Örneğin, ayın gününü gerektiren bir kayıttaki bir alanın "1 ILE 31 ARASıNDAKI GÜN" gibi bir doğrulama kuralı olabilir.

İlgili bilgiler için DAO Yardım'daki "Doğrulama Kuralı Özelliği" konusuna bakın.

## <a name="cdaorecordsetgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoRecordset::GetValidationText

Temel alan nesnesinin Doğrulama Metni özelliğinin metnini almak için bu üye işlevi arayın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

Bir `CString` alanın değeri alttaki alan nesnesinin doğrulama kuralını karşılamazsa görüntülenen iletimetnini içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

İlgili bilgiler için DAO Yardım'daki "DoğrulamaMetni Özelliği" konusuna bakın.

## <a name="cdaorecordsetisbof"></a><a name="isbof"></a>CDaoRecordset::IsBOF

Kayıt kümesinin ilk kaydından önce olup olmadığınızı öğrenmek için kayıttan kayda kaydırmadan önce bu üye işlevini arayın.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermisse veya ilk kayıtdan önce geriye kaydırDsanız sıfır aci; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin `IsBOF` herhangi `IsEOF` bir kayıt içermediğini veya boş olup olmadığını belirlemek için de arayabilirsiniz. Aramadan `Open`hemen sonra, kayıt kümesi kayıt `IsBOF` yoksa sıfırsız döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, `IsBOF` ilk kayıt geçerli kayıttır ve 0 döndürür.

İlk kayıt geçerli kayıtsa ve `MovePrev` `IsBOF` ararsanız, daha sonra sıfırsız döndürülecektir. Sıfırsız `IsBOF` döndürür `MovePrev`ve ararsanız, bir özel durum atılır. Sıfırsız `IsBOF` döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem bir özel durumla sonuçlanır.

Belirli yöntemlerin `IsBOF` ve `IsEOF` ayarların etkisi:

- Dahili olarak arama, `Open*` kayıt kümesindeki ilk kaydı `MoveFirst`arayarak geçerli kaydı yapar. Bu nedenle, boş bir kayıt `IsBOF` `IsEOF` kümesini çağırmak `Open` ve sıfırsız dönmek için neden olur. (Başarısız `MoveFirst` bir arama nın davranışı için `MoveLast` aşağıdaki tabloya bakın.)

- Bir kaydı başarıyla bulabilen `IsBOF` tüm `IsEOF` Taşı işlemleri hem neden hem de 0 döndürülecek.

- Yeni `AddNew` bir kaydı `Update` başarıyla ekleyen bir çağrının `IsBOF` ardından yapılan bir arama, `IsEOF` yalnızca zaten sıfır değilse 0'ın döndürülmesine neden olur. Durum her `IsEOF` zaman değişmeden kalacaktır. Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi, boş bir kayıt kümesinin geçerli kayıt işaretçisi bir dosyanın sonundadır, bu nedenle geçerli kayıttan sonra yeni bir kayıt eklenir.

- Herhangi `Delete` bir arama, bir kayıt kümesinden kalan tek kaydı kaldırsa `IsBOF` `IsEOF`bile, veya .

Bu tablo, move işlemlerine farklı kombinasyonlarla `IsBOF` /  `IsEOF`izin verildiğini gösterir.

||Önce Hareket Et, MoveLast|Moveprev<br /><br /> Taşıma < 0|Hareket et 0|Movenext<br /><br /> Taşıma > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=sıfır sız,<br /><br /> `IsEOF`=0 olarak|İzin Verildi|Özel durum|Özel durum|İzin Verildi|
|`IsBOF`=0,<br /><br /> `IsEOF`=sıfır sız|İzin Verildi|İzin Verildi|Özel durum|Özel durum|
|Her ikisi de sıfırsız|Özel durum|Özel durum|Özel durum|Özel durum|
|Her ikisi de 0|İzin Verildi|İzin Verildi|İzin Verildi|İzin Verildi|

Taşı işlemine izin vermek, işlemin bir kaydı başarıyla bulacağı anlamına gelmez. Yalnızca, belirtilen Taşıma işlemini gerçekleştirme girişimine izin verildiğini ve bir özel durum oluşturmayacağını gösterir. Hareket girişimi `IsBOF` sonucunda `IsEOF` üye işlevlerin değeri değişebilir.

Değeri `IsBOF` ve `IsEOF` ayarları üzerinde bir kayıt bulamayan Taşıma işlemlerinin etkisi aşağıdaki tabloda gösterilmiştir.

||ısbof|ıseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır|Sıfır|
|`Move`0|düzeltme sınıfı,|düzeltme sınıfı,|
|`MovePrev`, `Move` < 0|Sıfır|düzeltme sınıfı,|
|`MoveNext`, `Move` > 0|düzeltme sınıfı,|Sıfır|

İlgili bilgiler için DAO Yardım'daki "BOF, EOF Özellikleri" konusuna bakın.

## <a name="cdaorecordsetisdeleted"></a><a name="isdeleted"></a>CDaoRecordset::Silinmiş

Geçerli kaydın silinip silinmediğini belirlemek için bu üye işlevini arayın.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi silinmiş bir kayıt ta konumlandırılırsa sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir kayda kaydırır `IsDeleted` ve TRUE (sıfır olmayan) döndürür, başka bir kayıt kümesi işlemi gerçekleştirebilmek için önce başka bir kayda kaydırmanız gerekir.

> [!NOTE]
> Anlık görüntü veya tablo türü kayıt kümesindeki kayıtlar için silinen durumu denetlemeniz gerekmez. Kayıtlar anlık görüntüden silinemediğinden, aramanız `IsDeleted`gerekmez. Tablo türündeki kayıt kümeleri için silinen kayıtlar aslında kayıt kümesinden kaldırılır. Bir kayıt sizin, başka bir kullanıcı veya başka bir kayıt setinde silindikten sonra, bu kayda geri kaydıramazsınız. Bu nedenle, aramaya `IsDeleted`gerek yoktur.

Bir dinamitten bir kaydı sildiğinizde, kayıt kümesinden kaldırılır ve bu kayda geri kaydıramazsınız. Ancak, bir dinamitteki kayıt başka bir kullanıcı tarafından veya aynı tabloya `IsDeleted` dayalı başka bir kayıt setinde silinirse, daha sonra bu kayda kaydırdığınızda TRUE döndürür.

İlgili bilgiler için DAO Yardım'da "Delete Method", "LastModified Property" ve "EditMode Özelliği" konularına bakın.

## <a name="cdaorecordsetiseof"></a><a name="iseof"></a>CDaoRecordset::IsEOF

Kayıt kümesinin son kaydının ötesine geçip geçmediğinizi öğrenmek için kayıttan kayda geçerken bu üye işlevini arayın.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi kayıt içermadıysa veya son kaydın ötesine geçtiyseniz sıfıra inme; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesinin `IsEOF` herhangi bir kayıt mı yoksa boş mu olduğunu belirlemek için de arayabilirsiniz. Aramadan `Open`hemen sonra, kayıt kümesi kayıt `IsEOF` yoksa sıfırsız döndürür. En az bir kaydı olan bir kayıt kümesini açtığınızda, `IsEOF` ilk kayıt geçerli kayıttır ve 0 döndürür.

Son kayıt, aradığınız `MoveNext`geçerli kayıtsa, `IsEOF` daha sonra sıfırsız döndürecektir. Sıfırsız `IsEOF` döndürür `MoveNext`ve ararsanız, bir özel durum atılır. Sıfırsız `IsEOF` döndürürse, geçerli kayıt tanımsızdır ve geçerli kayıt gerektiren herhangi bir eylem bir özel durumla sonuçlanır.

Belirli yöntemlerin `IsBOF` ve `IsEOF` ayarların etkisi:

- Dahili olarak arama, `Open` kayıt kümesindeki ilk kaydı `MoveFirst`arayarak geçerli kaydı yapar. Bu nedenle, boş bir kayıt `IsBOF` `IsEOF` kümesini çağırmak `Open` ve sıfırsız dönmek için neden olur. (Başarısız `MoveFirst` bir aramanın davranışı için aşağıdaki tabloya bakın.)

- Bir kaydı başarıyla bulabilen `IsBOF` tüm `IsEOF` Taşı işlemleri hem neden hem de 0 döndürülecek.

- Yeni `AddNew` bir kaydı `Update` başarıyla ekleyen bir çağrının `IsBOF` ardından yapılan bir arama, `IsEOF` yalnızca zaten sıfır değilse 0'ın döndürülmesine neden olur. Durum her `IsEOF` zaman değişmeden kalacaktır. Microsoft Jet veritabanı altyapısı tarafından tanımlandığı gibi, boş bir kayıt kümesinin geçerli kayıt işaretçisi bir dosyanın sonundadır, bu nedenle geçerli kayıttan sonra yeni bir kayıt eklenir.

- Herhangi `Delete` bir arama, bir kayıt kümesinden kalan tek kaydı kaldırsa `IsBOF` `IsEOF`bile, veya .

Bu tablo, move işlemlerine farklı kombinasyonlarla `IsBOF` /  `IsEOF`izin verildiğini gösterir.

||Önce Hareket Et, MoveLast|Moveprev<br /><br /> Taşıma < 0|Hareket et 0|Movenext<br /><br /> Taşıma > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`=sıfır sız,<br /><br /> `IsEOF`=0 olarak|İzin Verildi|Özel durum|Özel durum|İzin Verildi|
|`IsBOF`=0,<br /><br /> `IsEOF`=sıfır sız|İzin Verildi|İzin Verildi|Özel durum|Özel durum|
|Her ikisi de sıfırsız|Özel durum|Özel durum|Özel durum|Özel durum|
|Her ikisi de 0|İzin Verildi|İzin Verildi|İzin Verildi|İzin Verildi|

Taşı işlemine izin vermek, işlemin bir kaydı başarıyla bulacağı anlamına gelmez. Yalnızca, belirtilen Taşıma işlemini gerçekleştirme girişimine izin verildiğini ve bir özel durum oluşturmayacağını gösterir. Hareket girişimi `IsBOF` sonucunda `IsEOF` ve üye işlevlerin değeri değişebilir.

Değeri `IsBOF` ve `IsEOF` ayarları üzerinde bir kayıt bulamayan Taşıma işlemlerinin etkisi aşağıdaki tabloda gösterilmiştir.

||ısbof|ıseof|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Sıfır|Sıfır|
|`Move`0|düzeltme sınıfı,|düzeltme sınıfı,|
|`MovePrev`, `Move` < 0|Sıfır|düzeltme sınıfı,|
|`MoveNext`, `Move` > 0|düzeltme sınıfı,|Sıfır|

İlgili bilgiler için DAO Yardım'daki "BOF, EOF Özellikleri" konusuna bakın.

## <a name="cdaorecordsetisfielddirty"></a><a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty

Bir dinamitin belirtilen alan veri üyesinin "kirli" (değiştirildi) olarak işaretlenip işaretlenmediğini belirlemek için bu üye işlevini arayın.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin kirli olup olmadığını belirlemek için NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi kirli olarak işaretlenirse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Tüm `Update` kirli alan veri üyelerindeki veriler, geçerli kayıt üye işlevine yapılan bir çağrı yla güncelleştirildiğinde `CDaoRecordset` (bir `Edit` `AddNew`çağrıyı takip ederek veya sonra) veri kaynağındaki kayda aktarılır. Bu bilgiyle, sütunu işaretlemek için alan veri üyesinin işaretlerini çıkarma gibi daha fazla adım atabilirsiniz, böylece veri kaynağına yazılmaz.

`IsFieldDirty`üzerinden `DoFieldExchange`uygulanır.

## <a name="cdaorecordsetisfieldnull"></a><a name="isfieldnull"></a>CDaoRecordset::IsFieldNull

Bir kayıt kümesinin belirtilen alan veri üyesinin Null olarak işaretlenip işaretlenmediğini belirlemek için bu üye işlevini arayın.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin Null olup olmadığını belirlemek için NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null olarak işaretlenirse sıfıra inmez; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

(Veritabanı terminolojisinde Null "değeri yoktur" anlamına gelir ve C++'daki NULL ile aynı değildir.) Bir alan veri üyesi Null olarak işaretlenirse, geçerli kaydın değeri olmayan bir sütunu olarak yorumlanır.

> [!NOTE]
> Bazı durumlarda, `IsFieldNull` aşağıdaki kod örneğinin gösterdiği gibi, kullanmak verimsiz olabilir:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
> Dinamik kayıt bağlama kullanıyorsanız, kaynak gösterilmeden, `CDaoRecordset`örnekte gösterildiği gibi VT_NULL kullandığınızdan emin olun.

## <a name="cdaorecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable

Belirtilen alan veri üyesinin "nullable" olup olmadığını belirlemek için bu üye işlevini arayın (Null değerine ayarlanabilir; C++ NULL, veritabanı terminolojisinde "değeri olmayan" anlamına gelen Null ile aynı değildir.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Durumunu denetlemek istediğiniz alan veri üyesine bir işaretçi veya alanlardan herhangi birinin Null olup olmadığını belirlemek için NULL.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen alan veri üyesi Null yapılabilirse sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Null olmayan bir alanın bir değeri olmalıdır. Bir kaydı eklerken veya güncellerken böyle bir alanı Null'a ayarlamaya çalışırsanız, `Update` veri kaynağı eklemeyi veya güncelleştirmeyi reddeder ve bir özel durum oluşturur. Özel durum, 'yi `Update`aradiğinizde değil, ' ı aradığınızda `SetFieldNull`oluşur.

## <a name="cdaorecordsetisopen"></a><a name="isopen"></a>CDaoRecordset::Açık

Kayıt kümesinin açık olup olmadığını belirlemek için bu üye işlevini arayın.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt kümesi nesnesinin `Open` veya üye `Requery` işlevinin daha önce çağrılması ve kayıt kümesi nin kapatılmaması durumunda sıfır sızma; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaorecordsetm_bcheckcachefordirtyfields"></a><a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset::m_bCheckCacheForDirtyFields

Önbelleğe alınmış alanların otomatik olarak kirli (değiştirildi) ve Null olarak işaretlenip işaretlenmediğini belirten bir bayrak içerir.

### <a name="remarks"></a>Açıklamalar

Bayrak varsayılan olarak TRUE'ya işaret eder. Bu veri üyesindeki ayar, tüm çift arabelleğe alma mekanizmasını denetler. Bayrağı TRUE olarak ayarlarsanız, DFX mekanizmasını kullanarak önbelleğe alma alanını alan bazında kapatabilirsiniz. Bayrağı FALSE olarak ayarlarsanız, kendiniz `SetFieldDirty` `SetFieldNull` ve kendiniz aramanız gerekir.

Aramadan önce bu `Open`veri üyesini ayarlayın. Bu mekanizma öncelikle kullanım kolaylığı içindir. Değişiklikler yapıldıkça alanların çift arabelleğe alınması nedeniyle performans daha yavaş olabilir.

## <a name="cdaorecordsetm_nfields"></a><a name="m_nfields"></a>CDaoRecordset::m_nFields

Recordset sınıfındaki alan veri üyesi sayısını ve veri kaynağından kayıt kümesi tarafından seçilen sütun sayısını içerir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfının oluşturucusu, `m_nFields` statik olarak bağlı alanların doğru sayısıyla baş harfe bürünmelidir. ClassWizard, kayıt kümesi sınıfınızı bildirmek için kullandığınızda bu başlatmayı sizin için yazar. Ayrıca el ile de yazabilirsiniz.

Çerçeve, alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili sütunları arasındaki etkileşimi yönetmek için bu sayıyı kullanır.

> [!NOTE]
> Bu numara, parametre `DoFieldExchange` `SetFieldType` `CDaoFieldExchange::outputColumn`ile yapılan bir aramadan sonra kayıtlı çıktı sütunlarının sayısına karşılık olmalıdır.

Sütunları dinamik olarak `CDaoRecordset::GetFieldValue` bağlayabilirsiniz. `CDaoRecordset::SetFieldValue` Bunu yaparsanız, üye işlevinizdeki DFX işlev `m_nFields` çağrılarının sayısını yansıtmak için sayıyı artımgerekmez. `DoFieldExchange`

## <a name="cdaorecordsetm_nparams"></a><a name="m_nparams"></a>CDaoRecordset::m_nParams

Recordset sınıfındaki parametre veri üye sayısını içerir — kayıt kümesinin sorgusuyla geçirilen parametrelerin sayısını.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi sınıfınızda herhangi bir parametre veri üyesi varsa, sınıfın oluşturucusu doğru sayıyla *m_nParams* başlatmalıdır. *m_nParams* değeri varsayılan olarak 0'a kadar dır. Parametre veri üyeleri eklerseniz -ki bunu el ile yapmanız gerekir- parametre sayısını yansıtmak için sınıf oluşturucuya el ile bir başlatma eklemeniz gerekir (bu da en azından *m_strFilter* veya *m_strSort* dizenizdeki '' yer tutucu sayısı kadar olmalıdır).

Çerçeve, kayıt kümesinin sorgusunu parametreleştirdiğinde bu sayıyı kullanır.

> [!NOTE]
> Bu numara, parametre `DoFieldExchange` `SetFieldType` `CFieldExchange::param`ile yapılan bir aramadan sonra kayıtlı "param" sayısına karşılık olmalıdır.

İlgili bilgiler için DAO Yardım'daki "Parametre Nesnesi" konusuna bakın.

## <a name="cdaorecordsetm_pdaorecordset"></a><a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset

Nesnenin altında yatan DAO recordset nesnesi `CDaoRecordset` için OLE arabirimine bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

DAO arabirimine doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.

İlgili bilgiler için DAO Yardım'daki "Recordset Object" konusuna bakın.

## <a name="cdaorecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase

Kayıt kümesinin `CDaoDatabase` bir veri kaynağına bağlı olduğu nesneye bir işaretçi içerir.

### <a name="remarks"></a>Açıklamalar

Bu değişken iki şekilde ayarlanır. Genellikle, kayıt kümesi nesnesini oluştursanız, zaten açık `CDaoDatabase` olan bir nesneye işaretçi geçirirsiniz. Bunun yerine NULL'u geçerseniz, `CDaoRecordset` sizin için bir `CDaoDatabase` nesne oluşturur ve açar. Her iki `CDaoRecordset` durumda da işaretçiyi bu değişkende saklar.

Normalde doğrudan depolanan işaretçi kullanmanız `m_pDatabase`gerekmez. `CDaoRecordset`Ancak, kendi uzantılarınızı yazarsanız, işaretçiyi kullanmanız gerekebilir. Örneğin, kendi `CDaoException`(ler) atarsanız işaretçi gerekebilir.

İlgili bilgiler için DAO Yardım'daki "Veritabanı Nesnesi" konusuna bakın.

## <a name="cdaorecordsetm_strfilter"></a><a name="m_strfilter"></a>CDaoRecordset::m_strFilter

SQL deyiminin **WHERE** yan tümcesini oluşturmak için kullanılan bir dize içerir.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesini filtrelemek için ayrılmış SÖZCÜğü **NEREDE** içermez. Bu veri üyesinin kullanımı tablo türündeki kayıt kümeleri için geçerli değildir. Bir `m_strFilter` `CDaoQueryDef` işaretçi kullanarak bir kayıt kümesini açarken kullanımının hiçbir etkisi yoktur.

Microsoft Jet veritabanı altyapısının ABD sürümünü kullanmasanız bile, tarih içeren alanları filtrelerken ABD tarih biçimini (ay-gün-yıl) kullanın; aksi takdirde, veriler beklediğiniz gibi filtrelenmeyebilir.

İlgili bilgiler için DAO Yardım'daki "Filtre Özelliği" konusuna bakın.

## <a name="cdaorecordsetm_strsort"></a><a name="m_strsort"></a>CDaoRecordset::m_strSort

Bir SQL deyiminin **ORDERBY** yan tümcesini içeren bir dize **içerir.**

### <a name="remarks"></a>Açıklamalar

Dynaset ve anlık görüntü türü kayıt kümesi nesnelerinde sıralayabilirsiniz.

Tablo türü kayıt kümesi nesnelerini sıralayamazsınız. Tablo türükayıt kümesinin sıralama sırasını belirlemek için [SetCurrentIndex'i](#setcurrentindex)arayın.

Bir `CDaoQueryDef` işaretçi kullanarak bir kayıt kümesini açarken *m_strSort* kullanımının hiçbir etkisi yoktur.

İlgili bilgiler için DAO Yardım'daki "Özelliği Sırala" konusuna bakın.

## <a name="cdaorecordsetmove"></a><a name="move"></a>CDaoRecordset::Taşı

Recordset *lRows* kayıtlarını geçerli kayıttan konumlandırmak için bu üye işlevi arayın.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Parametreler

*lRows*<br/>
İleri veya geri hareket ettirecek kayıt sayısı. Pozitif değerler, kayıt kümesinin sonuna doğru ilerler. Negatif değerler başa doğru geriye doğru hareket ettirin.

### <a name="remarks"></a>Açıklamalar

İleri veya geri hareket edebilirsiniz. `Move( 1 )`'ye `MoveNext`eşdeğerdir `Move( -1 )` ve `MovePrev`' a eşittir.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Genel olarak, `IsBOF` kayıt `IsEOF` kümesinin herhangi bir kaydı olup olmadığını belirlemek için bir Move işlemini hem de önce arayın. Aradıktan `Open` sonra `Requery`ya `IsBOF` da `IsEOF`, ya da .

> [!NOTE]
> Kayıt kümesinin başlangıcını veya sonunu geçtiyseniz `IsBOF` (veya `IsEOF` sıfırsız döndü) `Move` bir `CDaoException`.

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Yalnızca ileri `Move` kaydırma anlık görüntüsünü çağırdığınızda, *lRows* parametresi pozitif bir tamsayı olmalıdır ve yer imlerine izin verilmez, bu nedenle yalnızca ileriye taşıyabilirsiniz.

Bir kayıt kümesindeki ilk, son, sonraki veya önceki kaydı yapmak `MoveFirst` `MoveLast`için `MoveNext`geçerli `MovePrev` kaydı , , veya üye işlevini arayın.

İlgili bilgiler için DAO Yardım'da "Taşıma Yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

## <a name="cdaorecordsetmovefirst"></a><a name="movefirst"></a>CDaoRecordset::MoveFirst

Kayıt kümesindeki ilk kaydı (varsa) geçerli kaydı yapmak için bu üye işlevini arayın.

```
void MoveFirst();
```

### <a name="remarks"></a>Açıklamalar

Kayıt kümesini açtıktan hemen sonra aramanız `MoveFirst` gerekmez. O zaman, ilk kayıt (varsa) otomatik olarak geçerli kayıttır.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Genel olarak, `IsBOF` kayıt `IsEOF` kümesinin herhangi bir kaydı olup olmadığını belirlemek için bir Move işlemini hem de önce arayın. Aradıktan `Open` sonra `Requery`ya `IsBOF` da `IsEOF`, ya da .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Bir `Move` koşul uygulamadan kayıttan kayda geçmek için işlevleri kullanın. Belirli bir koşulu karşılayan dynaset türündeki veya anlık görüntü tipi kayıt kümesi nesnesindeki kayıtları bulmak için Bul işlemlerini kullanın. Tablo türünde kayıt kümesi nesnesinde bir `Seek`kaydı bulmak için .

Kayıt kümesi tablo tipi bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Altta yatan DAO nesnesinin Dizin özelliğini kullanarak geçerli dizin ayarlayabilirsiniz. Geçerli dizini ayarlamazsanız, döndürülen kayıtların sırası tanımsız olur.

Bir SQL `MoveLast` sorgusuna veya querydef'e dayalı bir kayıt kümesi nesnesini çağırırsanız, sorgu tamamlanmak zorunda kalır ve kayıt kümesi nesnesi tamamen doldurulur.

`MoveFirst` Yalnızca ileri kaydırma `MovePrev` anlık görüntüsüyle veya üye işlevini çağıramazsınız.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu taşımak için belirli sayıda `Move`kaydı ileri veya geri olarak arayın.

İlgili bilgiler için DAO Yardım'da "Taşıma Yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

## <a name="cdaorecordsetmovelast"></a><a name="movelast"></a>CDaoRecordset::MoveLast

Kayıt kümesindeki son kaydı (varsa) geçerli kaydı yapmak için bu üye işlevini arayın.

```
void MoveLast();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Genel olarak, `IsBOF` kayıt `IsEOF` kümesinin herhangi bir kaydı olup olmadığını belirlemek için bir Move işlemini hem de önce arayın. Aradıktan `Open` sonra `Requery`ya `IsBOF` da `IsEOF`, ya da .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Bir `Move` koşul uygulamadan kayıttan kayda geçmek için işlevleri kullanın. Belirli bir koşulu karşılayan dynaset türündeki veya anlık görüntü tipi kayıt kümesi nesnesindeki kayıtları bulmak için Bul işlemlerini kullanın. Tablo türünde kayıt kümesi nesnesinde bir `Seek`kaydı bulmak için .

Kayıt kümesi tablo tipi bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Altta yatan DAO nesnesinin Dizin özelliğini kullanarak geçerli dizin ayarlayabilirsiniz. Geçerli dizini ayarlamazsanız, döndürülen kayıtların sırası tanımsız olur.

Bir SQL `MoveLast` sorgusuna veya querydef'e dayalı bir kayıt kümesi nesnesini çağırırsanız, sorgu tamamlanmak zorunda kalır ve kayıt kümesi nesnesi tamamen doldurulur.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu taşımak için belirli sayıda `Move`kaydı ileri veya geri olarak arayın.

İlgili bilgiler için DAO Yardım'da "Taşıma Yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

## <a name="cdaorecordsetmovenext"></a><a name="movenext"></a>CDaoRecordset::MoveNext

Kayıt kümesindeki bir sonraki kaydı geçerli kayıt yapmak için bu üye işlevini arayın.

```
void MoveNext();
```

### <a name="remarks"></a>Açıklamalar

Önceki kayda geçmeye `IsBOF` çalışmadan önce aramanız önerilir. Sıfırolmayan `MovePrev` bir geri `CDaoException` `IsBOF` dönüş eki, ilk kayıtöncesinde zaten kaydırılmış veya kayıt kümesi tarafından hiçbir kayıt seçilmediğini belirten bir çağrı atar.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Genel olarak, `IsBOF` kayıt `IsEOF` kümesinin herhangi bir kaydı olup olmadığını belirlemek için bir Move işlemini hem de önce arayın. Aradıktan `Open` sonra `Requery`ya `IsBOF` da `IsEOF`, ya da .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Bir `Move` koşul uygulamadan kayıttan kayda geçmek için işlevleri kullanın. Belirli bir koşulu karşılayan dynaset türündeki veya anlık görüntü tipi kayıt kümesi nesnesindeki kayıtları bulmak için Bul işlemlerini kullanın. Tablo türünde kayıt kümesi nesnesinde bir `Seek`kaydı bulmak için .

Kayıt kümesi tablo tipi bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Altta yatan DAO nesnesinin Dizin özelliğini kullanarak geçerli dizin ayarlayabilirsiniz. Geçerli dizini ayarlamazsanız, döndürülen kayıtların sırası tanımsız olur.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu taşımak için belirli sayıda `Move`kaydı ileri veya geri olarak arayın.

İlgili bilgiler için DAO Yardım'da "Taşıma Yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

## <a name="cdaorecordsetmoveprev"></a><a name="moveprev"></a>CDaoRecordset::MovePrev

Kayıt kümesindeki önceki kaydı geçerli kayıt yapmak için bu üye işlevini arayın.

```
void MovePrev();
```

### <a name="remarks"></a>Açıklamalar

Önceki kayda geçmeye `IsBOF` çalışmadan önce aramanız önerilir. Sıfırolmayan `MovePrev` bir geri `CDaoException` `IsBOF` dönüş eki, ilk kayıtöncesinde zaten kaydırılmış veya kayıt kümesi tarafından hiçbir kayıt seçilmediğini belirten bir çağrı atar.

> [!CAUTION]
> Kayıt kümesinde `Move` kayıt yoksa, işlevlerden herhangi birini çağırmak özel bir durum oluşturur. Genel olarak, `IsBOF` kayıt `IsEOF` kümesinin herhangi bir kaydı olup olmadığını belirlemek için bir Move işlemini hem de önce arayın. Aradıktan `Open` sonra `Requery`ya `IsBOF` da `IsEOF`, ya da .

> [!NOTE]
> Geçerli kayıt güncelleştirilirken veya eklenirken `Move` işlevlerden herhangi birini ararsanız, güncelleştirmeler uyarı yapılmadan kaybolur.

Bir `Move` koşul uygulamadan kayıttan kayda geçmek için işlevleri kullanın. Belirli bir koşulu karşılayan dynaset türündeki veya anlık görüntü tipi kayıt kümesi nesnesindeki kayıtları bulmak için Bul işlemlerini kullanın. Tablo türünde kayıt kümesi nesnesinde bir `Seek`kaydı bulmak için .

Kayıt kümesi tablo tipi bir kayıt kümesine başvuruyorsa, hareket tablonun geçerli dizinini izler. Altta yatan DAO nesnesinin Dizin özelliğini kullanarak geçerli dizin ayarlayabilirsiniz. Geçerli dizini ayarlamazsanız, döndürülen kayıtların sırası tanımsız olur.

`MoveFirst` Yalnızca ileri kaydırma `MovePrev` anlık görüntüsüyle veya üye işlevini çağıramazsınız.

Kayıt kümesi nesnesindeki geçerli kaydın konumunu taşımak için belirli sayıda `Move`kaydı ileri veya geri olarak arayın.

İlgili bilgiler için DAO Yardım'da "Taşıma Yöntemi" ve "MoveFirst, MoveLast, MoveNext, MovePrevious Methods" konularına bakın.

## <a name="cdaorecordsetopen"></a><a name="open"></a>CDaoRecordset::Aç

Kayıt kümesinin kayıtlarını almak için bu üye işlevini aramalısınız.

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

- `dbOpenDynaset`Çift yönlü kaydırma ile bir dynaset tipi kayıt kümesi. Bu varsayılandır.

- `dbOpenTable`Çift yönlü kaydırma ile tablo tipi kayıt kümesi.

- `dbOpenSnapshot`Çift yönlü kaydırma ile anlık görüntü türünde bir kayıt kümesi.

*Lpszsql*<br/>
Aşağıdakilerden birini içeren bir dize işaretçisi:

- Null işaretçisi.

- Bir veya daha fazla tablo ve /veya querydefs (virgül ayrılmış) adı.

- Bir SQL **SELECT** deyimi (isteğe bağlı olarak bir SQL **WHERE** veya **ORDERBY** yan tümcesi ile).

- Geçiş sorgusu.

*nSeçenekler*<br/>
Aşağıda listelenen seçeneklerden biri veya birkaçı. Varsayılan değer 0’dır. Olası değerler aşağıdaki gibidir:

- `dbAppendOnly`Yalnızca yeni kayıtları ekleyebilirsiniz (yalnızca dynaset tipi kayıt kümesi). Bu seçenek, tam anlamıyla kayıtların yalnızca eklenebileceği anlamına gelir. MFC ODBC veritabanı sınıfları, kayıtların alınmasını ve ekilmesine izin veren yalnızca ek seçeneğine sahiptir.

- `dbForwardOnly`Kayıt kümesi yalnızca ileriye doğru kaydırma anlık görüntüsüdür.

- `dbSeeChanges`Başka bir kullanıcı düzenlediğiniz verileri değiştiriyorsa bir özel durum oluşturun.

- `dbDenyWrite`Diğer kullanıcılar kayıtları değiştiremez veya ekleyemez.

- `dbDenyRead`Diğer kullanıcılar kayıtları görüntüleyemez (yalnızca tablo türünde kayıt kümesi).

- `dbReadOnly`Yalnızca kayıtları görüntüleyebilirsiniz; diğer kullanıcılar bunları değiştirebilir.

- `dbInconsistent`Tutarsız güncelleştirmeler (yalnızca dynaset tipi kayıt kümesi) izin verilir.

- `dbConsistent`Yalnızca tutarlı güncelleştirmeler (yalnızca dynaset tipi kayıt seti) izin verilir.

> [!NOTE]
> Sabitler `dbConsistent` ve `dbInconsistent` birbirini dışlayan. Birini veya diğerini kullanabilirsiniz, ancak her `Open`ikisini de belirli bir durumda kullanamazsınız.

*pTableDef*<br/>
[CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesine işaretçi. Bu sürüm yalnızca tablo türünde kayıt kümeleri için geçerlidir. Bu seçeneği kullanırken, oluşturmak `CDaoDatabase` `CDaoRecordset` için kullanılan işaretçi kullanılmaz; bunun yerine, tablonun bulunduğu veritabanı kullanılır.

*pQueryDef*<br/>
[CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesine işaretçi. Bu sürüm yalnızca dynaset türü ve anlık görüntü tipi kayıt kümeleri için geçerlidir. Bu seçeneği kullanırken, oluşturmak `CDaoDatabase` `CDaoRecordset` için kullanılan işaretçi kullanılmaz; bunun yerine, querydef'in bulunduğu veritabanı kullanılır.

### <a name="remarks"></a>Açıklamalar

Aramadan `Open`önce, kayıt kümesi nesnesini oluşturmanız gerekir. Bunu yapmanın birkaç yolu vardır:

- Kayıt kümesi nesnesini oluştursanız, işaretçiyi zaten açık olan bir `CDaoDatabase` nesneye geçirin.

- Kayıt kümesi nesnesini oluştursanız, işaretçiyi açık olmayan bir `CDaoDatabase` nesneye geçirin. Kayıt kümesi bir `CDaoDatabase` nesneyi açar, ancak kayıt kümesi nesnesi kapandığında nesneyi kapatmaz.

- Kayıt kümesi nesnesini oluştursanız, bir NULL işaretçisi geçirin. Kayıt kümesi nesnesi Microsoft Access adını almak için çağırır. `GetDefaultDBName` MDB dosyası açılacak. Daha sonra kayıt `CDaoDatabase` kümesi bir nesneyi açar ve kayıt kümesi açık olduğu sürece açık tutar. Kayıt kümesini aradiğinizde, `Close` `CDaoDatabase` nesne de kapatılır.

    > [!NOTE]
    >  Kayıt kümesi nesneyi `CDaoDatabase` açtığında, veri kaynağını münhasır olmayan erişimle açar.

`Open` *LpszSQL* parametresini kullanan sürümü için, kayıt kümesi açıldıktan sonra kayıtları çeşitli yollardan birinde alabilirsiniz. İlk seçenek, DFX işlevlerine `DoFieldExchange`sahip olmaktır. İkinci `GetFieldValue` seçenek, üye işlevi çağırarak dinamik bağlama kullanmaktır. Bu seçenekler ayrı ayrı veya birlikte uygulanabilir. Bunlar birleştirilirse, `Open`''ye yapılan çağrıda SQL deyimini kendiniz geçirmeniz gerekir.

Bir `Open` `CDaoTableDef` nesnede geçtiğiniz yerin ikinci sürümünü kullandığınızda, ortaya çıkan sütunlar dfx mekanizması üzerinden `DoFieldExchange` bağlanabileceğiniz ve/veya dinamik `GetFieldValue`olarak bağlayabildiğiniz.

> [!NOTE]
> Yalnızca tablo `Open` türü `CDaoTableDef` kayıt kümeleri için bir nesne kullanarak arayabilirsiniz.

Bir `Open` `CDaoQueryDef` nesnede geçtiğiniz yerin üçüncü sürümünü kullandığınızda, bu sorgu yürütülür ve ortaya çıkan sütunlar dfx mekanizması üzerinden `DoFieldExchange` bağlamanız ve/veya dinamik olarak `GetFieldValue`bağlamanız için kullanılabilir.

> [!NOTE]
> Yalnızca dynaset `CDaoQueryDef` türü ve anlık görüntü türü kayıt kümeleri için bir nesne kullanarak arayabilirsiniz. `Open`

Parametreyi kullanan `Open` ilk sürümü için, kayıtlar aşağıdaki tabloda gösterilen ölçütlere göre seçilir. `lpszSQL`

|Parametrenin `lpszSQL` değeri|Seçilen kayıtlar tarafından belirlenir|Örnek|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Dize tarafından `GetDefaultSQL`döndürülen.||
|Bir veya daha fazla tablo ve/veya querydef adlarının virgülle ayrılmış listesi.|Tüm sütunlar temsil `DoFieldExchange`edilir.|`"Customer"`|
|**SELECT** sütun listesi **FROM** tablo listesi|Belirtilen tabledef(ler) ve/veya querydef(ler)'den belirtilen sütunlar.|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Her zamanki prosedür NULL `Open`geçmektir; bu durumda, `Open` `GetDefaultSQL`çağrılar , ClassWizard'ın türetilmiş bir `CDaoRecordset`sınıf oluştururken oluşturduğu geçersiz kılınabilir bir üye işlevdir. Bu değer, ClassWizard'da belirttiğiniz tabledef(ler) ve/veya querydef adını verir. Bunun yerine *lpszSQL* parametresinde diğer bilgileri belirtebilirsiniz.

Ne geçerseniz `Open` geçerseniz geçirin, sorgu için son bir SQL dizesi kurar (dize, geçtiğiniz *lpszSQL* dizesine eklenen SQL **WHERE** ve **ORDERBY** yan tümceleri olabilir) ve sonra sorguyu yürütür. 'yi aradıktan `Open`sonra `GetSQL` arayarak yapılandırılan dizeyi inceleyebilirsiniz.

Kayıt kümesi sınıfınızın alan veri üyeleri, seçilen verilerin sütunlarına bağlıdır. Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesi için filtre veya sıralama gibi seçenekler ayarlamak istiyorsanız, `m_strFilter` kayıt kümesi nesnesini ayarladıktan `Open`sonra ancak aramadan önce . `m_strSort` Kayıt kümesi zaten açıldıktan sonra kayıt kümesindeki kayıtları yenilemek `Requery`istiyorsanız, '' 'yi arayın.

Dynaset `Open` türünde veya anlık görüntü tipi bir kayıt kümesini çağırırsanız veya veri kaynağı bir SQL deyimine veya ekli `dbOpenTable` bir tabloyu temsil eden bir tabloya atıfta bulunuyorsa, tür bağımsız değişkeni için kullanamazsınız; bunu yaparsanız, MFC bir özel durum atar. Tabledef nesnesinin ekli bir tabloyu temsil edip etmediğini belirlemek için bir [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) nesnesi oluşturun ve [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) üye işlevini arayın.

Aynı `dbSeeChanges` kaydı düzenlerken veya silerken başka bir kullanıcı veya başka bir program tarafından yapılan değişiklikleri makinenize hapsetmek istiyorsanız bayrağı kullanın. Örneğin, iki kullanıcı aynı kaydı düzenlemeye başlarsa, `Update` üye işlevi arayan ilk kullanıcı başarılı olur. İkinci `Update` kullanıcı tarafından çağrıldığında, bir `CDaoException` atılır. Benzer şekilde, ikinci kullanıcı kaydı `Delete` silmek için aramaya çalışırsa ve ilk kullanıcı tarafından `CDaoException` zaten değiştirildiyse, bir oluşur.

Genellikle, kullanıcı bunu `CDaoException` güncellenirken alırsa, kodunuz alanların içeriğini yenilemeli ve yeni değiştirilen değerleri almalıdır. Özel durum silme işleminde oluşursa, kodunuz yeni kayıt verilerini kullanıcıya ve verilerin son zamanlarda değiştiğini belirten bir ileti görüntüleyebilir. Bu noktada, kodunuz kullanıcının kaydı silmek için hala istediği bir onay isteyebilir.

> [!TIP]
> Uygulamanız Bir ODBC`dbForwardOnly`veri kaynağından açılan bir kayıt setinden tek bir geçiş yaptığında performansı artırmak için yalnızca ileri kaydırma seçeneğini () kullanın.

İlgili bilgiler için DAO Yardım'daki "OpenRecordset Method" konusuna bakın.

## <a name="cdaorecordsetrequery"></a><a name="requery"></a>CDaoRecordset::Yeniden sorgu

Bir kayıt kümesini yeniden oluşturmak (yenilemek) için bu üye işlevi arayın.

```
virtual void Requery();
```

### <a name="remarks"></a>Açıklamalar

Herhangi bir kayıt döndürülürse, ilk kayıt geçerli kayıt olur.

Kayıt kümesinin sizin veya diğer kullanıcıların veri kaynağına yaptığı eklemeleri ve silmeleri yansıtması için, 'yi arayarak `Requery`kayıt kümesini yeniden oluşturmanız gerekir. Kayıt kümesi bir dinamitse, sizin veya diğer kullanıcıların varolan kayıtlarına (eklemeler değil) yaptığınız güncelleştirmeleri otomatik olarak yansıtır. Kayıt kümesi anlık görüntüyse, diğer `Requery` kullanıcıların düzenlemelerini ve eklemeleri ve silmeleri yansıtmak için aramanız gerekir.

Bir dinamit veya anlık `Requery` görüntü için, parametre değerlerini kullanarak kayıt kümesini yeniden oluşturmak istediğinizde arayın. Aramadan `Requery`önce [m_strFilter](#m_strfilter) ve [m_strSort](#m_strsort) ayarlayarak yeni filtreyi ayarlayın veya sıralayın. Aramadan önce parametre veri üyelerine yeni `Requery`değerler atayarak yeni parametreler ayarlayın.

Kayıt kümesini yeniden oluşturma girişimi başarısız olursa, kayıt kümesi kapatılır. Aramadan `Requery`önce, [CanRestart](#canrestart) üye işlevini arayarak kayıt kümesinin yeniden sorgulanıp değiştirilemeyeceğini belirleyebilirsiniz. `CanRestart`başarılı `Requery` olacağını garanti etmez.

> [!CAUTION]
> Sadece `Requery` aradıktan sonra `Open`arayın.

> [!NOTE]
> [Yeniden Sorgu'yı çağırmak](#requery) DAO yer imlerini değiştirir.

0'ı arıyorsanız `Requery` `CanRestart` dynaset türünde veya anlık görüntü tipi kayıt kümesini arayamaz ve tablo tipi kayıt setinde kullanamazsınız.

Her `IsBOF` ikisi `IsEOF` de ve aradıktan `Requery`sonra sıfırsız dönerse, sorgu herhangi bir kayıt döndürmedi ve kayıt kümesi hiçbir veri içermez.

İlgili bilgiler için DAO Yardım'daki "Requery Method" konusuna bakın.

## <a name="cdaorecordsetseek"></a><a name="seek"></a>CDaoRecordset::Ara

Geçerli dizin için belirtilen ölçütleri karşılayan dizine eklenmiş tablo türü kayıt kümesi nesnesinde kaydı bulmak ve bu kaydı geçerli kaydı yapmak için bu üye işlevi arayın.

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

*lpszKarşılaştırma*<br/>
Aşağıdaki dize ifadelerinden biri: "<", "\<=", "=", ">=", veya ">".

*pKey1*<br/>
Değeri dizindeki ilk alana karşılık gelen bir [COleVariant](../../mfc/reference/colevariant-class.md) işaretçisi. Gereklidir.

*pKey2*<br/>
Varsa, değeri `COleVariant` dizindeki ikinci alana karşılık gelen bir işaretçi. Varsayılan olarak NULL'a verilir.

*pKey3*<br/>
Varsa, değeri `COleVariant` dizindeki üçüncü alana karşılık gelen bir işaretçi. Varsayılan olarak NULL'a verilir.

*pKeyArray*<br/>
Bir dizi varyantiçin işaretçi. Dizi boyutu, dizideki alan sayısına karşılık gelir.

*nTuşlar*<br/>
Dizinin boyutuna karşılık gelen bir karşımat, dizideki alan sayısıdır.

> [!NOTE]
> Anahtarlarda joker karakter belirtmeyin. Joker karakterler `Seek` eşleşen hiçbir kaydı döndürmez.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen kayıtlar bulunursa sıfır olmayan, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Dört veya daha fazla `Seek` alanın dizinlerini işlemek için ikinci (dizi) sürümünü kullanın.

`Seek`tablo türü ndeki kayıt kümelerinde yüksek performanslı dizin araması sağlar. Aramadan önce aramadan `SetCurrentIndex` `Seek`önce geçerli dizini ayarlamanız gerekir. Dizin benzersiz olmayan bir anahtar alanı `Seek` veya alanları tanımlıyorsa, ölçütleri karşılayan ilk kaydı bulur. Bir dizin ayarlamazsanız, bir özel durum atılır.

UniCODE kayıt kümesi oluşturmuyorsanız, `COleVariant` nesnelerin açıkça ANSI olarak bildirilmesi gerektiğini unutmayın. Bu [COleVariant kullanılarak yapılabilir::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlanmış `VT_BSTRT` yapıcı formu (ANSI) veya `COleVariant` işlev [SetString](../../mfc/reference/colevariant-class.md#setstring)kullanılarak *(lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlayın `VT_BSTRT`.**(**

Aradığınızda, `Seek`bir veya daha fazla anahtar değeri ve karşılaştırma\<işlecinden ("<", " =", "=", ">=", veya ">") geçersiniz. `Seek`belirtilen anahtar alanları arar ve *lpszKarşılaştırma* ve *pKey1*tarafından belirtilen kriterleri karşılayan ilk kaydı bulur. Bir kez `Seek` bulundu, sıfırsız döndürür ve bu kaydı geçerli yapar. Bir `Seek` eşleşmeyi bulamazsa, `Seek` sıfır döndürür ve geçerli kayıt tanımsız dır. DAO'yu doğrudan kullanırken, NoMatch özelliğini açıkça denetlemeniz gerekir.

"=", `lpszComparison` ">="veya ">" `Seek` ise, dizinin başında başlar. *lpszKarşılaştırma* "<" veya "<=" ise, `Seek` dizin sonunda başlar ve sonunda yinelenen dizin girişleri olmadığı sürece geriye doğru arar. Bu durumda, `Seek` dizin sonunda yinelenen dizin girişleri arasında rasgele bir giriş başlar.

Kullandığınızda `Seek`geçerli bir kayıt olması gerekmez.

Belirli bir koşulu karşılayan dynaset türünde veya anlık görüntü tipi bir kayıt kümesinde bir kaydı bulmak için Bul işlemlerini kullanın. Sadece belirli bir koşulu karşılayan kayıtları değil, tüm kayıtları eklemek için kayıttan kayda geçmek için Taşıma işlemlerini kullanın.

Ekli tablolar `Seek` dynaset türü veya anlık görüntü tipi kayıt kümeleri olarak açılması gerektiğinden, herhangi bir türde ekli bir tabloyu arayamazsınız. Ancak, yüklenebilir `CDaoDatabase::Open` bir ISAM veritabanını doğrudan açmak `Seek` için ararsanız, performans yavaş olsa da, bu veritabanındaki tabloları arayabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Arama Yöntemi" konusuna bakın.

## <a name="cdaorecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition

Kayıt kümesi nesnesinin geçerli kaydının göreli kayıt numarasını ayarlar.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Parametreler

*lPosition*<br/>
Kayıt kümesindeki geçerli kaydın ordinal konumuna karşılık gelir.

### <a name="remarks"></a>Açıklamalar

Arama, `SetAbsolutePosition` geçerli kayıt işaretçisini dinaset türündeki veya anlık görüntü tipi kayıt kümesindeki ordinal konumuna göre belirli bir kayda konumlandırmanızı sağlar. [GetAbsolutePosition'ı](#getabsoluteposition)arayarak geçerli kayıt numarasını da belirleyebilirsiniz.

> [!NOTE]
> Bu üye işlev yalnızca dynaset türü ve anlık görüntü tipi kayıt kümeleri için geçerlidir.

Dayanak DAO nesnesinin AbsolutePosition özellik değeri sıfır tabanlıdır; 0'lık bir ayar, kayıt kümesindeki ilk kayda işaret eder. Doldurulan kayıt sayısından daha büyük bir değer ayarlamak, MFC'nin özel durum atmasını neden olur. `GetRecordCount` Üye işlevi arayarak kayıt kümesindeki doldurulan kayıt sayısını belirleyebilirsiniz.

Geçerli kayıt silinirse, AbsolutePosition özellik değeri tanımlanmaz ve başvurulmuşsa MFC bir özel durum atar. Dizinin sonuna yeni kayıtlar eklenir.

> [!NOTE]
> Bu özellik, vekil kayıt numarası olarak kullanılmak üzere tasarlanmamıştır. Yer imleri hala belirli bir konuma koruma ve geri dönmenin önerilen yoludur ve geçerli kaydı yer imlerini destekleyen tüm kayıt kümesi nesneleri arasında konumlandırmanın tek yoludur. Özellikle, kendisinden önceki kayıt(lar) silindiğinde, belirli bir kaydın konumu değişir. Orderby yan tümcesi kullanılarak bir SQL deyimi yle oluşturulmadığı sürece, kayıt kümesi yeniden oluşturulursa belirli bir kaydın aynı mutlak konuma **ORDERBY** sahip olacağına dair bir güvence de yoktur.

İlgili bilgiler için DAO Yardım'daki "AbsolutePosition Property" konusuna bakın.

## <a name="cdaorecordsetsetbookmark"></a><a name="setbookmark"></a>CDaoRecordset::SetBookmark

Belirtilen yer imi içeren kayıt kümesini konumlandırmak için bu üye işlevini arayın.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Belirli bir kayıt için yer imi değerini içeren [bir COleVariant](../../mfc/reference/colevariant-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Kayıt kümesi nesnesi oluşturulduğunda veya açıldığında, kayıtlarının her birinin zaten benzersiz bir yer imi vardır. Geçerli kaydın yer işaretini, nesneyi `GetBookmark` `COleVariant` arayarak ve kaydederek alabilirsiniz. Daha sonra kaydedilen yer imi değerini kullanarak arayarak `SetBookmark` bu kayda dönebilirsiniz.

> [!NOTE]
> [Yeniden Sorgu'yı çağırmak](#requery) DAO yer imlerini değiştirir.

UNICODE kayıt kümesi oluşturmuyorsanız, nesnenin `COleVariant` açıkça ANSI olarak bildirilmesi gerektiğini unutmayın. Bu [COleVariant kullanılarak yapılabilir::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlanmış `VT_BSTRT` yapıcı formu (ANSI) veya `COleVariant` işlev [SetString](../../mfc/reference/colevariant-class.md#setstring)kullanılarak *(lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlayın `VT_BSTRT`.**(**

İlgili bilgiler için DAO Yardım'daki "Yer Imi Özelliği" ve Yer İşaretli Özellik konularına bakın.

## <a name="cdaorecordsetsetcachesize"></a><a name="setcachesize"></a>CDaoRecordset::SetÖnbellek Boyutu

Önbelleğe alınacak kayıt sayısını ayarlamak için bu üye işlevini arayın.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Parametreler

*lSize*<br/>
Kayıt sayısını belirtir. Tipik bir değer 100'dür. 0 ayarı önbelleğe alma kapatır. Ayar 5 ile 1200 arasında olmalıdır. Önbellek önemli miktarda bellek kullanabilir.

### <a name="remarks"></a>Açıklamalar

Önbellek, uygulama çalışırken verilerin yeniden istenmesi durumunda, en son sunucudan alınan verileri tutan yerel bellekteki bir alandır. Veri önbelleğe alma, dynaset türü kayıt kümesi nesneleri aracılığıyla uzak bir sunucudan veri alan bir uygulamanın performansını artırır. Veriler istendiğinde, Microsoft Jet veritabanı altyapısı, sunucudan almak yerine istenen verilerin önbelleğini önce denetler ve bu da daha fazla zaman alır. ODBC veri kaynağından gelmeyen veriler önbelleğe kaydedilmez.

Ekli tablo gibi herhangi bir ODBC veri kaynağının yerel önbelleği olabilir. Önbelleği oluşturmak için, uzak veri kaynağından bir kayıt `SetCacheSize` `SetCacheStart` kümesi nesnesi açın, ve üye işlevleri arayın ve ardından `FillCache` üye işlevi arayın veya Taşı işlemlerinden birini kullanarak kayıtlara adım atın. Üye işlevin `SetCacheSize` *lSize* parametresi, uygulamanızın aynı anda çalışabileceği kayıt sayısına bağlı olabilir. Örneğin, ekranda görüntülenecek verilerin kaynağı olarak bir kayıt kümesi kullanıyorsanız, `SetCacheSize` *lSize* parametresini aynı anda 20 kaydı görüntülemek için 20 olarak geçirebilirsiniz.

İlgili bilgiler için DAO Yardımı'ndaki "Önbellek, Önbellek Özellikleri" konusuna bakın.

## <a name="cdaorecordsetsetcachestart"></a><a name="setcachestart"></a>CDaoRecordset::SetÖnbellekBaşlat

Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirtmek için bu üye işlevini arayın.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Parametreler

*varBookmark*<br/>
Önbelleğe alınacak kayıt kümesindeki ilk kaydın yer işaretini belirten bir [COleVariant.](../../mfc/reference/colevariant-class.md)

### <a name="remarks"></a>Açıklamalar

Üye işlevin *varBookmark* parametresi için herhangi bir `SetCacheStart` kaydın yer imi değerini kullanabilirsiniz. Önbelleği geçerli kayıtla başlatmak istediğiniz kaydı yapın, [SetBookmark'ı](#setbookmark)kullanarak bu kayıt için bir yer imi `SetCacheStart` ayarlayın ve yer imi değerini üye işlevin parametresi olarak geçirin.

Microsoft Jet veritabanı altyapısı önbellek aralığındaki kayıtları önbellek ten ister ve sunucudan önbellek aralığının dışındaki kayıtları ister.

Önbellekten alınan kayıtlar, diğer kullanıcılar tarafından kaynak verilerle eş zamanlı olarak yapılan değişiklikleri yansıtmaz.

Önbelleğe alınan tüm verilerin güncelleştirmesini zorlamak *için, lSize* parametresini `SetCacheSize` 0 olarak geçirin, başlangıçta istediğiniz önbelleğin boyutunu yeniden arayın `SetCacheSize` ve ardından `FillCache` üye işlevi arayın.

UNICODE kayıt kümesi oluşturmuyorsanız, nesnenin `COleVariant` açıkça ANSI olarak bildirilmesi gerektiğini unutmayın. Bu [COleVariant kullanılarak yapılabilir::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlanmış `VT_BSTRT` yapıcı formu (ANSI) veya `COleVariant` işlev [SetString](../../mfc/reference/colevariant-class.md#setstring)kullanılarak *(lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlayın `VT_BSTRT`.**(**

İlgili bilgiler için, DAO Yardımı'ndaki Önbellek, CacheStart Properties" konusuna bakın.

## <a name="cdaorecordsetsetcurrentindex"></a><a name="setcurrentindex"></a>CDaoRecordset::SetCurrentIndex

Tablo türünde bir kayıt kümesiüzerinde dizin ayarlamak için bu üye işlevi arayın.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Parametreler

*lpszIndex*<br/>
Ayarlanacak dizin adını içeren bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel tablolardaki kayıtlar belirli bir sırada depolanmaz. Dizin belirleme, veritabanından döndürülen kayıtların sırasını değiştirir, ancak kayıtların depolanma sırasını etkilemez. Belirtilen dizin zaten tanımlanmalıdır. Var olmayan bir dizin nesnesi kullanmaya çalışırsanız veya [Arama'yı](#seek)aradığınızda dizin ayarlanmazsa, MFC özel durum atar.

[CDaoTableDef::CreateIndex'i](../../mfc/reference/cdaotabledef-class.md#createindex) arayarak ve [cdaoTableDef::Append'i](../../mfc/reference/cdaotabledef-class.md#append)arayarak ve ardından kayıt kümesini yeniden açarak, alt tablonun Dizinler koleksiyonuna yeni dizin ekleyerek tablo için yeni bir dizin oluşturabilirsiniz.

Tablo türü kayıt kümesinden döndürülen kayıtlar yalnızca temel tablo için tanımlanan dizinler tarafından sıralanabilir. Kayıtları başka bir sırada sıralamak için, [CDaoRecordset::m_strSort'da](#m_strsort)depolanan bir SQL **ORDERBY** yan tümcesini kullanarak dynaset türü veya anlık görüntü tipi kayıt kümesi açabilirsiniz.

İlgili bilgiler için, "Dizin Nesnesi" konusuna ve DAO Yardımı'ndaki "geçerli dizin" tanımına bakın.

## <a name="cdaorecordsetsetfielddirty"></a><a name="setfielddirty"></a>CDaoRecordset::SetFieldDirty

Kayıt kümesinin alan veri üyesini değiştirilmiş veya değişmemiş olarak işaretlemek için bu üye işlevini çağırın.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Kayıt kümesinde veya NULL'da bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL veritabanı terminolojisinde Null ile aynı değildir, yani "değeri yoktur.")

*bKirli*<br/>
Alan veri üyesi "kirli" (değiştirildi) olarak işaretlenecekse DOĞRU. Aksi takdirde alan veri üyesi "temiz" (değişmeden) olarak işaretlenecekse FALSE.

### <a name="remarks"></a>Açıklamalar

Alanları değişmemiş olarak işaretleme, alanın güncelleştirilmemesini sağlar.

Çerçeve işaretleri, DAO kayıt alanı değişimi (DFX) mekanizması tarafından veri kaynağına yazılmasını sağlamak için alan veri üyelerini değiştirdi. Bir alanın değerini değiştirmek genellikle alanı otomatik olarak kirli ayarlar, bu `SetFieldDirty` nedenle nadiren kendinizi aramanız gerekir, ancak bazen alan veri üyesinin değeri ne olursa olsun sütunların açıkça güncelleştirildiğinden veya eklenmediğinden emin olmak isteyebilirsiniz. DFX mekanizması da PSEUDONULL kullanımını kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation.](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)

Çift arabelleğe alma mekanizması kullanılmıyorsa, alanın değerini değiştirmek alanı otomatik olarak kirli olarak ayarlamaz. Bu durumda, açıkça kirli olarak alan ayarlamak için gerekli olacaktır. [m_bCheckCacheForDirtyFields'da](#m_bcheckcachefordirtyfields) bulunan bayrak bu otomatik alan denetimini kontrol eder.

> [!NOTE]
> Bu üye işlevini yalnızca [Edit](#edit) veya [AddNew'ı](#addnew)aradıktan sonra arayın.

İşlevin ilk bağımsız değişkeni için NULL'u kullanmak işlevi `outputColumn` tüm `CDaoFieldExchange`alanlara uygular, **param** alanlarına değil. Örneğin, arama

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

yalnızca `outputColumn` alanları NULL olarak ayarlar; **param** alanları etkilenmez.

Bir **param**üzerinde çalışmak için, üzerinde çalışmak istediğiniz tek tek **paramın** gerçek adresini sağlamanız gerekir:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Bu, `outputColumn` tüm **param** alanlarını, alanlar ile yapabildiğiniz gibi NULL'a ayarlayamayacağınız anlamına gelir.

`SetFieldDirty`üzerinden `DoFieldExchange`uygulanır.

## <a name="cdaorecordsetsetfieldnull"></a><a name="setfieldnull"></a>CDaoRecordset::SetFieldNull

Kayıt kümesinin alan veri üyesini Null (özellikle değeri olmayan) veya Null olmayan olarak işaretlemek için bu üye işlevini çağırın.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parametreler

*Pv*<br/>
Kayıt kümesinde veya NULL'da bir alan veri üyesinin adresini içerir. NULL ise, kayıt kümesindeki tüm alan veri üyeleri işaretlenir. (C++ NULL veritabanı terminolojisinde Null ile aynı değildir, yani "değeri yoktur.")

*bNull*<br/>
Alan veri üyesi hiçbir değeri (Null) olarak işaretlenecekise Nonzero. Aksi takdirde alan veri üyesi null olmayan olarak işaretlenecekse 0.

### <a name="remarks"></a>Açıklamalar

`SetFieldNull`mekanizmaya `DoFieldExchange` bağlı alanlar için kullanılır.

Bir kayıt kümesine yeni bir kayıt eklediğinizde, tüm alan veri üyeleri başlangıçta Null değerine ayarlanır ve "kirli" (değiştirildi) olarak işaretlenir. Bir veri kaynağından bir kayıt aldığınızda, sütunlarının zaten değerleri vardır veya Null'dadır. Bir alanı Null yapmak uygun değilse, [cdaoException](../../mfc/reference/cdaoexception-class.md) atılır.

Çift arabelleğe alma mekanizmasını kullanıyorsanız, örneğin, geçerli kaydın bir alanını özellikle bir değere `SetFieldNull` sahip olmayan olarak belirlemek istiyorsanız, null olarak işaretlemek için TRUE olarak ayarlanmış *bNull'u* arayın. Bir alan daha önce Null olarak işaretlenmişse ve şimdi ona bir değer vermek istiyorsanız, yeni değerini ayarlamanız yeterlidir. Null bayrağını `SetFieldNull`' la kaldırmanız gerekmez. Alanın Null olup olmadığını belirlemek için [IsFieldNullable'ı](#isfieldnullable)arayın.

Çift arabelleğe alma mekanizmasını kullanmıyorsanız, alanın değerini değiştirmek alanı otomatik olarak kirli ve Null olmayan olarak ayarlamaz. Özellikle kirli ve null olmayan alanları ayarlamanız gerekir. [m_bCheckCacheForDirtyFields'da](#m_bcheckcachefordirtyfields) bulunan bayrak bu otomatik alan denetimini kontrol eder.

DFX mekanizması PSEUDONULL kullanımını kullanır. Daha fazla bilgi için [CDaoFieldExchange::m_nOperation.](../../mfc/reference/cdaofieldexchange-class.md#m_noperation)

> [!NOTE]
> Bu üye işlevini yalnızca [Edit](#edit) veya [AddNew'ı](#addnew)aradıktan sonra arayın.

İşlevin ilk bağımsız değişkeni için NULL'u kullanmak işlevi yalnızca alanlara `outputColumn` uygular, 'deki **param** alanlarına `CDaoFieldExchange`değil. Örneğin, arama

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

yalnızca `outputColumn` alanları NULL olarak ayarlar; **param** alanları etkilenmez.

## <a name="cdaorecordsetsetfieldvalue"></a><a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue

Bir alanın değerini ordinal konuma göre veya dize değerini değiştirerek ayarlamak için bu üye işlevi çağırın.

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

*Lpszname*<br/>
Bir alanın adını içeren bir dize için bir işaretçi.

*varValue*<br/>
Alanın içeriğinin değerini içeren bir [COleVariant](../../mfc/reference/colevariant-class.md) nesnesine başvuru.

*Nındex*<br/>
Kayıt kümesinin Alanlar koleksiyonundaki (sıfır tabanlı) alanın ordinal konumunu temsil eden bir karşıcı.

*lpszValue*<br/>
Alanın içeriğinin değerini içeren bir dize için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

DoFieldExchange mekanizmasını kullanarak statik olarak bağlama sütunları yerine alanları çalışma zamanında dinamik olarak bağlamak için kullanın `SetFieldValue` ve [GetFieldValue'](#getfieldvalue) i kullanın. [DoFieldExchange](#dofieldexchange)

UNICODE kayıt kümesi oluşturmuyorsanız, parametre içermeyen bir `SetFieldValue` `COleVariant` form kullanmanız veya nesnenin `COleVariant` açıkça ANSI olarak bildirilmesi gerektiğini unutmayın. Bu [COleVariant kullanılarak yapılabilir::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlanmış `VT_BSTRT` yapıcı formu (ANSI) veya `COleVariant` işlev [SetString](../../mfc/reference/colevariant-class.md#setstring)kullanılarak *(lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlayın `VT_BSTRT`.**(**

İlgili bilgiler için DAO Yardım'daki "Alan Nesnesi" ve "Değer Özelliği" konularına bakın.

## <a name="cdaorecordsetsetfieldvaluenull"></a><a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull

Alanı Null değerine ayarlamak için bu üye işlevi arayın.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Sıfır tabanlı dizin tarafından arama için, kayıt kümesinde alan dizin.

*Lpszname*<br/>
Kayıt kümesindeki alanın adı, ada göre arama için.

### <a name="remarks"></a>Açıklamalar

C++ NULL, veritabanı terminolojisinde "değeri olmayan" anlamına gelen Null ile aynı değildir.

İlgili bilgiler için DAO Yardım'daki "Alan Nesnesi" ve "Değer Özelliği" konularına bakın.

## <a name="cdaorecordsetsetlockingmode"></a><a name="setlockingmode"></a>CDaoRecordset::SetLockingMode

Kayıt kümesi için kilitleme türünü ayarlamak için bu üye işlevi arayın.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Parametreler

*bPessimistic*<br/>
Kilitleme türünü gösteren bir bayrak.

### <a name="remarks"></a>Açıklamalar

Kötümser kilitleme etkin olduğunda, düzenlediğiniz kaydı içeren 2K `Edit` sayfa, üye işlevi çağırır çağırmaz kilitlenir. Sayfanın kilidi, üye işlevini `Update` `Close` veya Taşı veya Bul işlemlerinden herhangi birini aradığınızda açılır.

İyimser kilitleme etkin olduğunda, kaydı içeren 2K sayfa yalnızca `Update` kayıt üye işlevle güncelleştirilirken kilitlenir.

Bir sayfa kilitliyse, başka hiçbir kullanıcı aynı sayfadaki kayıtları kaldır. Sıfır olmayan `SetLockingMode` bir değeri arayıp geçerseniz ve başka bir kullanıcı sayfayı zaten `Edit`kilitliyse, aradığınızda bir özel durum atılır. Diğer kullanıcılar kilitli sayfalardan verileri okuyabilir.

Sayfa başka `SetLockingMode` bir kullanıcı tarafından `Update` kilitlenirken sıfır değeriyle arar ve daha sonra ararsanız, bir özel durum oluşur. Başka bir kullanıcı tarafından kaydınızda yapılan değişiklikleri görmek (ve `SetBookmark` değişikliklerinizi kaybetmek), geçerli kaydın yer imi değeriyle üye işlevini arayın.

ODBC veri kaynakları ile çalışırken, kilitleme modu her zaman iyimserdir.

## <a name="cdaorecordsetsetparamvalue"></a><a name="setparamvalue"></a>CDaoRecordset::SetParamValue

Çalışma zamanında kayıt kümesindeki bir parametrenin değerini ayarlamak için bu üye işlevi arayın.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Querydef'in Parametreler koleksiyonundaki parametrenin sayısal konumu.

*var*<br/>
Ayarlanan değer; bkz. Açıklamalar.

*Lpszname*<br/>
Değerini ayarlamak istediğiniz parametrenin adı.

### <a name="remarks"></a>Açıklamalar

Parametre, kayıt kümesinin SQL dizesinin bir parçası olarak zaten kurulmuş olmalıdır. Parametreye ada göre veya koleksiyondaki dizin konumuna göre erişebilirsiniz.

`COleVariant` Nesne olarak ayarlanın değeri belirtin. Nesnenizde `COleVariant` istenen değeri ve türü ayarlama hakkında bilgi için [COleVariant sınıfına](../../mfc/reference/colevariant-class.md)bakın. UNICODE kayıt kümesi oluşturmuyorsanız, nesnenin `COleVariant` açıkça ANSI olarak bildirilmesi gerektiğini unutmayın. Bu [COleVariant kullanılarak yapılabilir::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlanmış `VT_BSTRT` yapıcı formu (ANSI) veya `COleVariant` işlev [SetString](../../mfc/reference/colevariant-class.md#setstring)kullanılarak *(lpszSrc* **,** *vtSrc* **)** *vtSrc* ayarlayın `VT_BSTRT`.**(**

## <a name="cdaorecordsetsetparamvaluenull"></a><a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull

Parametreyi Null değerine ayarlamak için bu üye işlevi arayın.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Sıfır tabanlı dizin tarafından arama için, kayıt kümesinde alan dizin.

*Lpszname*<br/>
Kayıt kümesindeki alanın adı, ada göre arama için.

### <a name="remarks"></a>Açıklamalar

C++ NULL, veritabanı terminolojisinde "değeri olmayan" anlamına gelen Null ile aynı değildir.

## <a name="cdaorecordsetsetpercentposition"></a><a name="setpercentposition"></a>CDaoRecordset::SetPercentPosition

Kayıt kümesindeki kayıtların yüzdesini temel alan kayıt kümesi nesnesindeki geçerli kaydın yaklaşık konumunu değiştiren bir değer ayarlamak için bu üye işlevi çağırın.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Parametreler

*fPosition*<br/>
0 ile 100 arasında bir sayı.

### <a name="remarks"></a>Açıklamalar

Dynaset tipi veya anlık görüntü tipi kayıt kümesiyle çalışırken, önce aramadan `SetPercentPosition`önce son kayda geçerek kayıt kümesini doldur. Kayıt kümesini tam olarak doldurmadan önce ararsanız, `SetPercentPosition` hareket miktarı [GetRecordCount](#getrecordcount)değeri ile belirtildiği gibi erişilen kayıt sayısına göredir. Son kayda geçerek `MoveLast`.

Bir kez, bu değere karşılık gelen yaklaşık konumda kayıt geçerli olur. `SetPercentPosition`

> [!NOTE]
> Geçerli `SetPercentPosition` kaydı bir kayıt kümesinde belirli bir kayda taşımak için çağrı yapmak önerilmez. Bunun yerine [SetBookmark](#setbookmark) üye işlevini arayın.

İlgili bilgiler için DAO Yardım'daki "PercentPosition Özelliği" konusuna bakın.

## <a name="cdaorecordsetupdate"></a><a name="update"></a>CDaoRecordset::Güncelleme

Bu üye işlevini, üye `AddNew` `Edit` işlevine yapılan bir çağrıdan sonra çağırın.

```
virtual void Update();
```

### <a name="remarks"></a>Açıklamalar

Bu çağrının `AddNew` veya `Edit` işlemi tamamlamak için gerekli olması gerekir.

Her `AddNew` `Edit` ikisi de ve eklenen veya düzenlenen verilerin veri kaynağına kaydedilmesi için yerleştirildiği bir düzenleme arabelleği hazırlayın. `Update`verileri kaydeder. Yalnızca değiştirilme olarak işaretlenmiş veya algılanan alanlar güncelleştirilir.

Veri kaynağı hareketleri destekliyorsa, `Update` aramayı (ve `AddNew` karşılık `Edit` gelen veya aramasını) bir hareketin parçası yapabilirsiniz.

> [!CAUTION]
> Eğer ilk `Update` ya `AddNew` da `Edit`aramadan ararsanız, `Update` bir `CDaoException`atar . [MoveNext'i](#movenext) aramadan `Update` önce aramanız `AddNew` veya `Edit`aramanız gerekir veya kayıt kümesini veya veri kaynağı bağlantısını kapatmalısınız. Aksi takdirde, değişiklikleriniz bildirim yapılmadan kaybolur.

Kayıt kümesi nesnesi çok kullanıcılı bir ortamda kötümser bir şekilde `Edit` kilitlendiğinde, güncelleştirme tamamlanana kadar kayıt kullanılan andan itibaren kilitli kalır. Kayıt kümesi iyimser bir şekilde kilitlenirse, kayıt kilitlenir ve veritabanında güncelleştirilmeden hemen önce önceden düzenlenmiş kayıtla karşılaştırılır. Aradığından `Edit`beri kayıt değiştiyse, `Update` işlem başarısız olur ve MFC bir özel durum oluşturur. Kilitleme modunu `SetLockingMode`' ile değiştirebilirsiniz.

> [!NOTE]
> İyimser kilitleme her zaman ODBC ve yüklenebilir ISAM gibi dış veritabanı biçimlerinde kullanılır.

İlgili bilgiler için DAO Help'de "Yeni Yöntem Ekle", "CancelUpdate Yöntemi", "Silme Yöntemi", "LastModified Özellik", "Güncelleme Yöntemi" ve "EditMode Özelliği" konularına bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace Sınıf](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
