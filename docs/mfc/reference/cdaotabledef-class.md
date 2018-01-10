---
title: "CDaoTableDef sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
dev_langs: C++
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b140d61689672f9d27b8078ad7d2eab732c1582
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaotabledef-class"></a>CDaoTableDef sınıfı
Temel tablo veya ekli bir tablo saklı tanımını temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoTableDef : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Oluşturan bir **CDaoTableDef** nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoTableDef::Append](#append)|Yeni bir tablo veritabanına ekler.|  
|[CDaoTableDef::CanUpdate](#canupdate)|Tablo güncelleştirilebilir değilse sıfır olmayan döndürür (alanları veya tablo özelliklerini tanımını değiştirebilirsiniz).|  
|[CDaoTableDef::Close](#close)|Açık bir tabledef kapatır.|  
|[CDaoTableDef::Create](#create)|Veritabanı kullanmaya eklenen bir tablo oluşturur [Append](#append).|  
|[CDaoTableDef::CreateField](#createfield)|Bir alan için bir tablo oluşturmak için çağrılır.|  
|[CDaoTableDef::CreateIndex](#createindex)|Bir tablo için bir dizin oluşturmak için çağrılır.|  
|[CDaoTableDef::DeleteField](#deletefield)|Bir tablodan alan silmek için çağrılır.|  
|[CDaoTableDef::DeleteIndex](#deleteindex)|Bir tablodan bir dizini silmek için çağrılır.|  
|[CDaoTableDef::GetAttributes](#getattributes)|Bir veya daha fazla özelliklerini belirten bir değer döndüren bir `CDaoTableDef` nesnesi.|  
|[CDaoTableDef::GetConnect](#getconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer döndürür.|  
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Temel tablo arka plandaki tarihi ve saati döndürür bir `CDaoTableDef` nesnesi oluşturuldu.|  
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Temel tablo tasarımı için yapılan en son değişikliğin saat ve tarihi döndürür.|  
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Tabloda yer alan sayısını temsil eden bir değer döndürür.|  
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Tablodaki belirli tür alanları hakkında bilgi döndürür.|  
|[CDaoTableDef::GetIndexCount](#getindexcount)|Tablosu için dizin numarasını döndürür.|  
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Belirli türdeki tablosu için dizinler hakkında bilgi döndürür.|  
|[CDaoTableDef::GetName](#getname)|Kullanıcı tanımlı tablo adını döndürür.|  
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Tablodaki kayıt sayısını döndürür.|  
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Kaynak veritabanında ekli tablo adı belirten bir değer döndürür.|  
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Bir alandaki veri değiştirilmiş veya tabloya eklenen doğrulayan bir değer döndürür.|  
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Bir alan nesnenin değerini belirtilen doğrulama kuralı karşılamadığı, uygulamanızın görüntülediği ileti metnini belirten bir değer döndürür.|  
|[CDaoTableDef::IsOpen](#isopen)|Tablo ise sıfır olmayan döndürür açın.|  
|[CDaoTableDef::Open](#open)|Kullanıcının TableDef'ın koleksiyonu veritabanında varolan bir tabledef depolanan açar.|  
|[CDaoTableDef::RefreshLink](#refreshlink)|Ekli bir tablo için bağlantı bilgilerini güncelleştirir.|  
|[CDaoTableDef::SetAttributes](#setattributes)|Bir veya daha fazla özelliklerini belirten bir değer ayarlar bir `CDaoTableDef` nesnesi.|  
|[CDaoTableDef::SetConnect](#setconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer ayarlar.|  
|[CDaoTableDef::SetName](#setname)|Tablonun adını ayarlar.|  
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Kaynak veritabanında ekli bir tablo adı belirten bir değer ayarlar.|  
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Bir alandaki veri değiştirilmiş veya tabloya eklenen doğrulayan bir değer ayarlar.|  
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Bir alan nesnenin değerini belirtilen doğrulama kuralı karşılamadığı, uygulamanızın görüntülediği ileti metnini belirten bir değer ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Tabledef nesnesi için temel alınan DAO arabirimi için bir işaretçi.|  
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Bu tablo için kaynak veritabanı.|  
  
## <a name="remarks"></a>Açıklamalar  
 Her DAO veritabanı nesnesinin tüm kaydedilmiş DAO tabledef nesneleri içeren TableDefs adlı bir koleksiyon tutar.  
  
 Tablo tanımı kullanılarak işlemek bir `CDaoTableDef` nesnesi. Örneğin, şunları yapabilirsiniz:  
  
-   Bir veritabanı herhangi bir yerel, ekli veya dış tabloda alan ve dizin yapısını inceleyin.  
  
-   Çağrı `SetConnect` ve `SetSourceTableName` iliştirilmiş tablolar ve kullanmak için üye işlevleri `RefreshLink` bağlantıları güncelleştirmek için üye işlevi bağlı tabloları.  
  
-   Çağrı `CanUpdate` üye işlevi tabloda yer alan tanımları düzenleyip düzenleyemeyeceğini belirler.  
  
-   Alınacak veya ayarlanacak kullanarak doğrulama koşullarını `GetValidationRule` ve `SetValidationRule`ve `GetValidationText` ve `SetValidationText` üye işlevleri.  
  
-   Kullanım **açık** bir tablo, dinamik küme veya anlık görüntü türü oluşturmak için üye işlevi `CDaoRecordset` nesnesi.  
  
    > [!NOTE]
    >  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala yapabilecekleriniz; Microsoft Jet veritabanı altyapısı için belirli olduklarından DAO sınıfları genellikle üstün yetenekleri sunar.  
  
### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Varolan bir tablo ile çalışma veya yeni bir tablo oluşturmak için TableDef nesneleri kullanmak için  
  
1.  Her durumda, ilk oluşturmak bir `CDaoTableDef` gösteren bir işaretçi sağladığını nesne, bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) tablo ait olduğu nesne.  
  
2.  Ardından istediğinize bağlı olarak aşağıdakileri yapın:  
  
    -   Varolan bir tablosu kaydedildi kullanmak için tabledef nesnesinin çağrısı [açık](#open) kaydedilmiş tablonun adını sağlayarak üye işlevi.  
  
    -   Yeni bir tablo oluşturmak için tabledef nesnesinin çağırın [oluşturma](#create) üye işlevi, tablo adını belirtin. Çağrı [CreateField](#createfield) ve [CreateIndex](#createindex) alanları ve dizinler tabloya eklemek için.  
  
    -   Çağrı [Append](#append) veritabanının TableDefs koleksiyonu ekleyerek tabloyu kaydetmek için. **Create** tabledef açık bir duruma koyar çağırdıktan sonra bunu **oluşturma** çağrılmayan **açmak**.  
  
        > [!TIP]
        >  Kaydedilen tablolar oluşturmak için kolay bunları oluşturmak ve bunları Microsoft Access kullanarak veritabanınızda depolamak için yoludur. Ardından açın ve MFC kodunuzda kullanabilirsiniz.  
  
 Açılamıyor veya oluşturulan tabledef nesnesi kullanmak için oluşturun ve açık bir `CDaoRecordset` nesnesi ile tabledef adını belirterek, bir **dbOpenTable** değeri `nOpenType` parametresi.  
  
 Tabledef nesnesi oluşturmak için kullanılacak bir `CDaoRecordset` nesnesi, genellikle oluşturmak veya bir tabledef yukarıda açıklandığı gibi açın ve ardından çağırdığınızda, tabledef nesnesine bir işaretçi geçirme bir kayıt kümesi nesnesi oluşturun [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Geçirdiğiniz tabledef açık durumda olması gerekir. Daha fazla bilgi için bkz [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Tabledef nesnesi kullanmayı bitirdiğinizde, çağrı kendi [Kapat](../../mfc/reference/cdaorecordset-class.md#close) üye işlev; tabledef nesnesi yok.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="append"></a>CDaoTableDef::Append  
 Çağırdıktan sonra bu üye işlevini çağırın [oluşturma](#create) tabledef veritabanına kaydetmek için yeni bir tabledef nesnesi oluşturmak için.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev nesnesi veritabanının TableDefs koleksiyonu ekler. Bunu ekleyerek değil tanımlarken tabledef geçici bir nesne kullanabilirsiniz, ancak kaydedin ve kullanmak istiyorsanız, çağırmalısınız **Append**.  
  
> [!NOTE]
>  (Null veya boş bir dizeyi içeren) bir adlandırılmamış tabledef append çalışırsanız, MFC özel durum oluşturur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "yöntemi ekleme" konusuna bakın.  
  
##  <a name="canupdate"></a>CDaoTableDef::CanUpdate  
 Belirlemek için bu üye işlevini çağırın olup olmadığını temel tablo tanımı bir `CDaoTableDef` nesne değiştirilebilir.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tablo yapısı (şema) değiştirilebilir, sıfır olmayan (ekleme veya alanlar ve dizinleri silme), aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, yeni oluşturulmuş bir tabloyu temel bir `CDaoTableDef` nesne güncelleştirilebilir ve ekli tablo temel bir `CDaoTableDef` Nesne güncelleştirilemiyor. A `CDaoTableDef` elde edilen kayıt kümesi güncelleştirilebilir değilse bile nesne güncelleştirilebilir, olabilir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "güncelleştirilebilir özellik" konusuna bakın.  
  
##  <a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef  
 Oluşturan bir **CDaoTableDef** nesnesi.  
  
```  
CDaoTableDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDatabase`  
 Bir işaretçi bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne oluşturma sonra çağırmalısınız [oluşturma](#create) veya [açık](#open) üye işlevi. Nesnesi ile işiniz bittiğinde, çağırmalısınız kendi [Kapat](#close) üye işlev ve destroy `CDaoTableDef` nesnesi.  
  
##  <a name="close"></a>CDaoTableDef::Close  
 Kapatmak ve tabledef nesnesi serbest bırakmak için bu üye işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Genellikle çağırdıktan sonra **Kapat**, ile ayırdığınızda tabledef nesnesi silme **yeni**.  
  
 Çağırabilirsiniz [açık](#open) çağırdıktan sonra yeniden **Kapat**. Bu, tabledef nesnesi yeniden kullanmanıza olanak sağlar.  
  
 İlgili bilgiler için "Kapat yönteminde" DAO Yardım konusuna bakın.  
  
##  <a name="create"></a>CDaoTableDef::Create  
 Yeni kaydedilen bir tablo oluşturmak için bu üye işlevini çağırın.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    long lAttributes = 0,  
    LPCTSTR lpszSrcTable = NULL,  
    LPCTSTR lpszConnect = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Tablonun adını içeren bir dize için bir işaretçi.  
  
 `lAttributes`  
 Tabledef nesnesinin temsil ettiği tablo özelliklerini karşılık gelen bir değer. Bit düzeyinde-OR aşağıdaki sabitlerden herhangi birisi birleştirmek için kullanabilirsiniz:  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan ekli bir tablo gösterir.|  
|**dbAttachSavePWD**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı kimliği ve parola ekli tablo için bağlantı bilgileriyle birlikte kaydedilir gösterir.|  
|**dbSystemObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu tablo olduğunu gösterir.|  
|**dbHiddenObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo tablo olduğunu gösterir.|  
  
 *lpszSrcTable*  
 Kaynak tablo adı içeren bir dize için bir işaretçi. Varsayılan olarak bu değer başlatılmadan **NULL**.  
  
 `lpszConnect`  
 Varsayılan bağlantı dizesini içeren bir dize için bir işaretçi. Varsayılan olarak bu değer başlatılmadan **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Tabledef adlı sonra ardından çağırabilirsiniz [Append](#append) veritabanının TableDefs koleksiyonu tabledef kaydetmek için. Çağırdıktan sonra **Append**tabledef açık bir durumda ve oluşturmak için kullanın bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "CreateTableDef Yöntemi" konusuna bakın.  
  
##  <a name="createfield"></a>CDaoTableDef::CreateField  
 Tabloya bir alan eklemek için bu üye işlevini çağırın.  
  
```  
void CreateField(
    LPCTSTR lpszName,  
    short nType,  
    long lSize,  
    long lAttributes = 0);  
  
void CreateField(CDaoFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Bu alanın adını belirten dize ifadesi için bir işaretçi.  
  
 `nType`  
 Alanın veri türünü belirten bir değer. Ayar şu değerlerden biri olabilir:  
  
|Tür|Boyut (bayt)|Açıklama|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 bayt|BOOL|  
|**dbByte**|1.|BYTE|  
|**dbInteger**|2|int|  
|**dbLong**|4|long|  
|**dbCurrency**|8|Para birimi ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|float|  
|**dbDouble**|8|çift|  
|**dbDate**|8|Tarih/saat ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Metin ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Uzun İkili (OLE nesnesi) [CLongBinary](../../mfc/reference/clongbinary-class.md) veya [CLongBinary](../../mfc/reference/cbytearray-class.md)|  
|**dbMemo**|0|Not ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
  
 `lSize`  
 Bir metin içeren bir alanın bayt cinsinden en büyük boyutu veya sabit boyutlu metin veya sayı değerlerini içeren bir alanın belirten bir değer. `lSize` Parametresi için metin alanları dışındaki tüm alanlar yoksayılır.  
  
 `lAttributes`  
 Alan ve özelliklerle karşılık gelen bir değer veya Bitsel kullanılarak birleştirilebilir.  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|**dbFixedField**|Alan boyutu (varsayılan sayısal alanlar için) sabittir.|  
|**dbVariableField**|Alan boyutu (yalnızca metin alanları) değişkenidir.|  
|**dbAutoIncrField**|Yeni kayıtlar için alan değeri değiştirilemez bir benzersiz uzun tamsayı olarak otomatik olarak yükseltilir. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.|  
|**dbUpdatableField**|Alan değeri değiştirilebilir.|  
|**dbDescending**|Alan azalan düzende sıralanır (Z - A veya 100-0) (yalnızca bir alanlar koleksiyonu dizin nesnenin alan nesnesinde için geçerlidir). Bu sabit atlarsanız, alan artan düzende sıralanır (A - Z veya 0 - 100) sipariş (varsayılan).|  
  
 `fieldinfo`  
 Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 A **DAOField** (OLE) nesnesi oluşturulur ve alanları koleksiyonuna eklenen **DAOTableDef** (OLE) nesnesi. Nesne özelliklerinin incelenmesi için kullanımı yanı sıra, kullanabilirsiniz `CDaoFieldInfo` bir tabledef yeni alanları oluşturmak için bir giriş parametresi oluşturulamadı. İlk sürümü `CreateField` kullanmak daha basittir ancak daha hassas denetim isterseniz, ikinci sürümü kullanabilirsiniz `CreateField`, hangi alır bir `CDaoFieldInfo` parametresi.  
  
 Sürümünü kullanıyorsanız `CreateField` alan bir `CDaoFieldInfo` parametresi dikkatli bir şekilde ayarlamanız gerekir her aşağıdaki üyeleri `CDaoFieldInfo` yapısı:  
  
- **m_strName**  
  
- `m_nType`  
  
- **m_lSize**  
  
- **m_lAttributes**  
  
- **m_bAllowZeroLength**  
  
 Kalan üyeleri `CDaoFieldInfo` ayarlanmalı **0**, **FALSE**, veya üye için uygun şekilde boş bir dize veya bir `CDaoException` ortaya çıkabilir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "CreateField yöntemi" konusuna bakın.  
  
##  <a name="createindex"></a>CDaoTableDef::CreateIndex  
 Bir tabloya bir dizin eklemek için bu işlevini çağırın.  
  
```  
void CreateIndex(CDaoIndexInfo& indexinfo);
```  
  
### <a name="parameters"></a>Parametreler  
 `indexinfo`  
 Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinleri veritabanı tablolarını yinelenen kayıtları kabul erişildiğini kayıtların sırasını belirtin. Dizinler ayrıca veri etkili erişim sağlar.  
  
 Tablolar için dizin oluşturmanız gerekmez, ancak büyük, dizinlenmemiş tablolarda, belirli bir kayda erişmek veya bir kayıt kümesi oluşturma uzun zaman alabilir. Diğer taraftan, çok fazla dizin oluşturma güncelleştirme yavaşlatır, ekleme ve tüm dizinleri otomatik olarak güncelleştirilen gibi silme işlemleri. Hangi dizin oluşturmak için karar gibi bu etmenleri dikkate alın.  
  
 Aşağıdaki üyeleri `CDaoIndexInfo` yapısı ayarlanmalıdır:  
  
- **m_strName** bir adı sağlanmalıdır.  
  
- `m_pFieldInfos`İçin bir dizi işaret etmelidir `CDaoIndexFieldInfo` yapıları.  
  
- `m_nFields`Dizi içinde alan sayısını belirtmelisiniz `CDaoFieldInfo` yapıları.  
  
 Üyeleri kalan yoksayılan IF ayarlanacak **FALSE**. Ayrıca, **m_lDistinctCount** üye dizini oluşturma sırasında göz ardı edilir.  
  
##  <a name="deletefield"></a>CDaoTableDef::DeleteField  
 Bir alanı kaldırmak ve erişilemez yapmak için bu üye işlevini çağırın.  
  
```  
void DeleteField(LPCTSTR lpszName);  
void DeleteField(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Varolan bir alan adı bir dize ifadesi için bir işaretçi.  
  
 `nIndex`  
 Tablonun sıfır tabanlı alanlar koleksiyonunda araması dizini tarafından için alan dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanına eklenmemiş yeni bir nesne üzerinde bu üye işlevini kullanabilirsiniz veya ne zaman [CanUpdate](#canupdate) sıfır olmayan bir değer döndürür.  
  
 İlgili bilgi için "Delete yöntemini" DAO Yardım konusuna bakın.  
  
##  <a name="deleteindex"></a>CDaoTableDef::DeleteIndex  
 Temel alınan tabloda bir dizini silmek için bu üye işlevini çağırın.  
  
```  
void DeleteIndex(LPCTSTR lpszName);  
void DeleteIndex(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Varolan bir dizin adı bir dize ifadesi için bir işaretçi.  
  
 `nIndex`  
 Veritabanının sıfır tabanlı TableDefs koleksiyonu, araması dizini tarafından dizin nesnesinde dizi dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanına eklenmemiş yeni bir nesne üzerinde bu üye işlevini kullanabilirsiniz veya ne zaman [CanUpdate](#canupdate) sıfır olmayan bir değer döndürür.  
  
 İlgili bilgi için "Delete yöntemini" DAO Yardım konusuna bakın.  
  
##  <a name="getattributes"></a>CDaoTableDef::GetAttributes  
 İçin bir `CDaoTableDef` nesnesi, dönüş değeri tarafından temsil edilen tablonun özelliklerini belirtir `CDaoTableDef` nesne ve bu sabitleri toplamını olabilir:  
  
```  
long GetAttributes();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir veya daha fazla özelliklerini belirten bir değer döndüren bir `CDaoTableDef` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan ekli bir tablo gösterir.|  
|**dbAttachSavePWD**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı kimliği ve parola ekli tablo için bağlantı bilgileriyle birlikte kaydedilir gösterir.|  
|**dbSystemObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu tablo olduğunu gösterir.|  
|**dbHiddenObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo tablo olduğunu gösterir.|  
|**dbAttachedTable**|Tablo Paradox veritabanı gibi bir ODBC olmayan veritabanı bağlı bir tablodan gösterir.|  
|**dbAttachedODBC**|Microsoft SQL Server gibi bir ODBC veritabanı bağlı bir tablodan tablo olduğunu gösterir.|  
  
 Bir sistem tablosu çeşitli iç bilgileri içerecek şekilde Microsoft Jet veritabanı altyapısı tarafından oluşturulan bir tablodur.  
  
 Gizli bir tablo geçici kullanım için Microsoft Jet veritabanı altyapısı tarafından oluşturulan bir tablodur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="getconnect"></a>CDaoTableDef::GetConnect  
 Bir veri kaynağına yönelik bağlantı dizesini almak için bu üye işlevini çağırın.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` tablo için yolu ve veritabanı türünü içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin bir `CDaoTableDef` ekli bir tablo temsil eden nesnesi `CString` nesne (bir veritabanı türü belirticisi ve bir veritabanı yolu) bir veya iki bölümden oluşur.  
  
 Aşağıdaki tabloda gösterildiği gibi yolunu veritabanı dosyalarını içeren dizini için tam yol ve tanımlayıcısıyla gelmelidir "veritabanı =". Bazı durumlarda (Microsoft Jet ve Microsoft Excel ile veritabanlarında olduğu gibi), belirli bir dosya adı veritabanı yolu bağımsız değişkeninde bulunur.  
  
 Tabloda [CDaoTableDef::SetConnect](#setconnect) olası veritabanı türlerini ve ilgili veritabanı belirticileri ve yolları gösterir:  
  
 Microsoft Jet veritabanı temel tablolar için tanımlayıcısı boş bir dizedir ("").  
  
 Bir parola gerekiyor ancak sağlanmadı ODBC sürücüsü tablo erişildiğinde bir oturum açma iletişim kutusu ilk zaman görüntüler ve yeniden bağlantı kapalı ve yeniden açılacak. Ekli bir tablo varsa **dbAttachSavePWD** öznitelik, oturum açma istemini Tablo açıldığında görünmez.  
  
 İlgili bilgi için DAO Yardımı'nda "özellik Bağlan" konusuna bakın.  
  
##  <a name="getdatecreated"></a>CDaoTableDef::GetDateCreated  
 Arka plandaki tabloda tarih ve saat belirlemek için bu işlevi çağırmak `CDaoTableDef` nesnesi oluşturuldu.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Temel tablo oluşturma saat ve tarihi içeren bir değer `CDaoTableDef` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarih ve saat ayarları üzerinde temel tablo oluşturulmuş veya son güncelleştirme bilgisayardan türetilir. Çok kullanıcılı bir ortamda, Tutarsızlıklardan kaçınmak için doğrudan dosya sunucusundan bu ayarlar kullanıcılar almanız gerekir; diğer bir deyişle, tüm istemcilerin "standart" zaman kaynağı kullanması gereken — belki de bir sunucudan.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated  
 Arka plandaki tabloda tarih ve saat belirlemek için bu işlevi çağırmak **CDaoTableDef** nesne son güncelleştirildi.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki tabloda tarih ve saati içeren bir değer **CDaoTableDef** nesne son güncelleştirildi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarih ve saat ayarları üzerinde temel tablo oluşturulmuş veya son güncelleştirme bilgisayardan türetilir. Çok kullanıcılı bir ortamda, Tutarsızlıklardan kaçınmak için doğrudan dosya sunucusundan bu ayarlar kullanıcılar almanız gerekir; diğer bir deyişle, tüm istemcilerin "standart" zaman kaynağı kullanması gereken — belki de bir sunucudan.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getfieldcount"></a>CDaoTableDef::GetFieldCount  
 Tablosunda tanımlanan alanların sayısını almak için bu üye işlevini çağırın.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tablodaki alanların sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri 0 ise, koleksiyonda nesne yok.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Count özelliğini" konusuna bakın.  
  
##  <a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo  
 Çeşitli tabledef tanımlı bir alan hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 Tablonun sıfır tabanlı alanlar koleksiyonu araması dizini tarafından için alan nesnesinde dizini.  
  
 `fieldinfo`  
 Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.  
  
 `dwInfoOptions`  
 Hangi bilgilerin alınacağı alan hakkında belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, tür, boyut öznitelikleri. Hızlı performans için bu seçeneği kullanın.  
  
- `AFX_DAO_SECONDARY_INFO`Birincil bilgilerin yanı sıra: gerekli, sıra konumu sıfır uzunluk, harmanlama sırası yabancı adı, kaynak alanı, kaynak tablo izin ver  
  
- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgileri, artı: doğrulama kuralı, doğrulama metin, varsayılan değer  
  
 `lpszName`  
 Ada göre arama alanı nesne adını gösteren bir işaretçi. Alan adlandıran bir dize en fazla 64 karakterden adıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevin bir sürüm dizini tarafından bir alanından aramak olanak sağlar. Başka bir sürüm bir alan adına göre aramak olanak sağlar.  
  
 Döndürülen bilgi açıklaması için bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istemek için de önceki tüm düzeylerde bilgi alın.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="getindexcount"></a>CDaoTableDef::GetIndexCount  
 Bir tablo için dizin numarasını almak için bu üye işlevini çağırın.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tablosu için dizin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri 0 ise, koleksiyonda dizin vardır.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Count özelliğini" konusuna bakın.  
  
##  <a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo  
 Çeşitli tabledef tanımlanan dizin hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 Koleksiyondaki tablonun sıfır tabanlı dizin, koleksiyondaki konumuna göre arama dizin nesnesi sayısal dizini.  
  
 `indexinfo`  
 Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için dizini belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO`Ad alanı bilgisi alanları. Hızlı performans için bu seçeneği kullanın.  
  
- `AFX_DAO_SECONDARY_INFO`Birincil bilgilerin yanı sıra: birincil, benzersiz, kümelenmiş, Yoksay gerekli, null değerlere, yabancı  
  
- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgileri, artı: ayrı sayım  
  
 `lpszName`  
 Ada göre arama dizini nesne adını gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi bir sürümü, bir dizin koleksiyondaki konumuyla aramak olanak tanır. Başka bir sürüm bir dizin oluşturan adına göre aramak olanak sağlar.  
  
 Döndürülen bilgi açıklaması için bkz: [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istemek için de önceki tüm düzeylerde bilgi alın.  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="getname"></a>CDaoTableDef::GetName  
 Temel tablo kullanıcı tanımlı adını almak için bu üye işlevini çağırın.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı tanımlı bir adı bir tablo için.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu ad bir harfle başlar ve en fazla 64 karakter içerebilir. Sayı içerebilir ve alt çizgi karakterleri ancak noktalama veya boşluk içeremez.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
##  <a name="getrecordcount"></a>CDaoTableDef::GetRecordCount  
 İçinde kaç kayıt olduğunu bulmak için bu üye işlevini çağırın bir `CDaoTableDef` nesnesi.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir tabledef nesnesinde erişilen kayıtların sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırma `GetRecordCount` tablo türü için `CDaoTableDef` nesne tablosundaki kayıt yaklaşık sayısını yansıtır ve tablo kayıtlarını eklenen ve Silinen hemen etkilenir. İşlemler, kayıt sayısı bir parçası olarak görünür, size çağrısı tamamlanana kadar geri [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). A `CDaoTableDef` hiçbir kayıt nesnesiyle 0 kayıt sayısı özelliği ayarı vardır. Bağlı tablolar veya ODBC veritabanları ile çalışırken `GetRecordCount` her zaman -1 döndürür.  
  
 İlgili bilgi için DAO Yardımı'ndaki "RecordCount özelliği" konusuna bakın.  
  
##  <a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName  
 Bir kaynak veritabanı bağlı bir tablonun adını almak için bu üye işlevini çağırın.  
  
```  
CString GetSourceTableName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` nesne yerel veri tablosu, ekli bir tablo ya da boş bir dize kaynak adını belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Microsoft Jet veritabanına bağlı başka bir veritabanı tablosunda bir ekli tablodur. Bağlı tablolar için verileri nerede diğer uygulamalar tarafından yönetilebilir dış veritabanında kalır.  
  
 İlgili bilgi için DAO Yardımı'ndaki "SourceTableName özellik" konusuna bakın.  
  
##  <a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule  
 Bir tabledef için doğrulama kuralı almak için bu üye işlevini çağırın.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **CString** değiştirilmiş veya tabloya eklenen bir alandaki verileri doğrular nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Doğrulama kuralları güncelleştirme işlemleri bağlantılı olarak kullanılır. Bir tabledef bir doğrulama kuralı içeriyorsa, veriler değiştirilmeden önce o tabledef güncelleştirmeleri belirlenmiş ölçütlerini karşılamalıdır. Değişiklik değerini içeren bir özel durum, ölçütleri eşleşmiyorsa [GetValidationText](#getvalidationtext) atılır. İçin bir `CDaoTableDef` nesnesi, bu `CString` salt okunur bir ekli tablo ve okuma/yazma için bir temel tablo.  
  
 İlgili bilgi için "ValidationRule özelliğinde" DAO Yardım konusuna bakın.  
  
##  <a name="getvalidationtext"></a>CDaoTableDef::GetValidationText  
 Kullanıcı doğrulama kuralı eşleşmiyor veri girdiğinde görüntülenecek dize almak için bu işlevini çağırın.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CString` nesne kullanıcı doğrulama kuralı eşleşmiyor veri girerse görüntülenen metni belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İçin bir `CDaoTableDef` nesnesi, bu `CString` salt okunur bir ekli tablo ve okuma/yazma için bir temel tablo.  
  
 İlgili bilgi için DAO Yardımı'ndaki "ValidationText özelliği" konusuna bakın.  
  
##  <a name="isopen"></a>CDaoTableDef::IsOpen  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDaoTableDef` nesne şu anda açık.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDaoTableDef` nesnesidir açık; Aksi halde 0.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase  
 Bir işaretçi içeriyor [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Bu tablo için nesne.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef  
 DAO tabledef nesnesinin altındaki için OLE arabirimi için bir işaretçi içeriyor `CDaoTableDef` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 DAO arabirimi doğrudan erişmeniz gerekiyorsa bu işaretçiyi kullanın.  
  
##  <a name="open"></a>CDaoTableDef::Open  
 Bir tabledef açmak için bu üye işlevi veritabanında önceden kaydedilmiş çağrısı TableDef'ın koleksiyonu kullanıcının.  
  
```  
virtual void Open(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Bir tablo adı belirten bir dize için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
  
##  <a name="refreshlink"></a>CDaoTableDef::RefreshLink  
 Ekli bir tablo için bağlantı bilgilerini güncelleştirmek için bu üye işlevini çağırın.  
  
```  
void RefreshLink();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak ekli bir tablo için bağlantı bilgilerini değiştirme [SetConnect](#setconnect) karşılık gelen üzerinde `CDaoTableDef` nesnesi ve ardından kullanarak `RefreshLink` bilgileri güncelleştirmek için üye işlevi. Çağırdığınızda `RefreshLink`, ekli tablonun özelliklerini değiştirilmez.  
  
 Zorlamak için değiştirilmiş tüm açık etkili olabilmesi için bağlantı bilgilerini [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneler üzerinde bu tabledef kapalı.  
  
 İlgili bilgi için DAO Yardımı'ndaki "RefreshLink yöntemi" konusuna bakın.  
  
##  <a name="setattributes"></a>CDaoTableDef::SetAttributes  
 Bir veya daha fazla özelliklerini belirten bir değer ayarlar bir `CDaoTableDef` nesnesi.  
  
```  
void SetAttributes(long lAttributes);
```  
  
### <a name="parameters"></a>Parametreler  
 `lAttributes`  
 Tarafından temsil edilen tablonun özelliklerini `CDaoTableDef` nesne ve bu sabitleri toplamını olabilir:  
  
|Sabit|Açıklama|  
|--------------|-----------------|  
|**dbAttachExclusive**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan ekli bir tablo gösterir.|  
|**dbAttachSavePWD**|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı kimliği ve parola ekli tablo için bağlantı bilgileriyle birlikte kaydedilir gösterir.|  
|**dbSystemObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu tablo olduğunu gösterir.|  
|**dbHiddenObject**|Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo tablo olduğunu gösterir.|  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok öznitelik ayarlarken Bitsel veya işlecini kullanarak uygun sabitleri toplayarak birleştirebilirsiniz. Ayarı **dbAttachExclusive** iliştirilmemiş bir tabloda bir özel durum oluşturur. Aşağıdaki değerleri de bir özel durumu ürettiği birleştirme:  
  
- **dbAttachExclusive &#124; dbAttachedODBC**  
  
- **dbAttachSavePWD &#124; dbAttachedTable**  
  
 İlgili bilgi için DAO Yardımı'ndaki "öznitelikler özelliği" konusuna bakın.  
  
##  <a name="setconnect"></a>CDaoTableDef::SetConnect  
 İçin bir `CDaoTableDef` temsil eden dize nesnesi ekli bir tablo nesnesi (bir veritabanı türü belirticisi ve bir veritabanı yolu) bir veya iki bölümden oluşur.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszConnect`  
 ODBC veya yüklenebilir ISAM sürücüleri için ek parametreleri belirten bir dize ifadesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda gösterildiği gibi yolunu veritabanı dosyalarını içeren dizini için tam yol ve tanımlayıcısıyla gelmelidir "veritabanı =". Bazı durumlarda (Microsoft Jet ve Microsoft Excel ile veritabanlarında olduğu gibi), belirli bir dosya adı veritabanı yolu bağımsız değişkeninde bulunur.  
  
> [!NOTE]
>  Eşittir işaretinden çevresine boşluk formun yol deyimlerinde içermez "veritabanı = sürücü:\\\path". Bu, oluşturulan bir özel durum ve bağlantı başarısız sonuçlanır.  
  
 Aşağıdaki tabloda, olası veritabanı türlerini ve ilgili veritabanı belirticileri ve yolları gösterilmektedir:  
  
|Veritabanı türü|Belirleyici|Yol|  
|-------------------|---------------|----------|  
|Jet veritabanı altyapısı kullanılarak veritabanı|"[ `database`];"|" `drive`:\\\ *yolu*\\\ *filename*. MDB"|  
|dBASE III|"dBASE III;"|" `drive`:\\\ *yolu*"|  
|dBASE IV|"dBASE IV;"|" `drive`:\\\ *yolu*"|  
|dBASE 5|"dBASE 5.0;"|" `drive`:\\\ *yolu*"|  
|Paradox 3.x|"Paradox 3.x;"|" `drive`:\\\ *yolu*"|  
|Paradox 4.x|"Paradox 4.x;"|" `drive`:\\\ *yolu*"|  
|Paradox 5.x|"Paradox 5.x;"|" `drive`:\\\ *yolu*"|  
|Excel 3.0|"Excel 3.0;"|" `drive`:\\\ *yolu*\\\ *filename*. XLS"|  
|Excel 4.0|"Excel 4.0;"|" `drive`:\\\ *yolu*\\\ *filename*. XLS"|  
|Excel 5.0 veya Excel 95|"Excel 5.0;"|" `drive`:\\\ *yolu*\\\ *filename*. XLS"|  
|Excel 97|"Excel 8.0;"|" `drive`:\\\ *yolu*\ *filename*. XLS"|  
|HTML alma|"HTML alma;"|" `drive`:\\\ *yolu*\ *filename*"|  
|HTML dışa aktarma|"HTML verme;"|" `drive`:\\\ *yolu*"|  
|Metin|"Metin;"|"sürücü:\\\path"|  
|ODBC|"ODBC; Veritabanı = `database`; UID = *kullanıcı*; PWD = *parola*; DSN = *datasourcename;* LOGINTIMEOUT = *saniye;*" (Bu tüm sunucular için tam bağlantı dizesi olmayabilir; bu yalnızca bir örnektir. Parametreleri arasında boşluk olmaması çok önemlidir.)|Yok.|  
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &#124; 1}]<br /><br /> [Profili = *profil*;]<br /><br /> [PWD = *parola*;]<br /><br /> [VERİTABANI = `database`;] "|*"sürücü*:\\\ *yolu*\\\ *filename*. MDB"|  
  
> [!NOTE]
>  Btrieve DAO 3.5 itibariyle artık desteklenmiyor.  
  
 Çift ters eğik çizgi kullanmanız gerekir (\\\\) bağlantı dizelerinde. Kullanarak varolan bir bağlantı özelliklerini değiştirdi, `SetConnect`, sonradan çağırmalısınız [RefreshLink](#refreshlink). Kullanarak bağlantı özelliklerini başlatma, `SetConnect`, değil çağrısı ihtiyacınız `RefreshLink`, ancak seçtiğiniz Bunu yapmak, önce tabledef ekleyin.  
  
 Bir parola gerekiyor ancak sağlanmadı ODBC sürücüsü tablo erişildiğinde bir oturum açma iletişim kutusu ilk zaman görüntüler ve yeniden bağlantı kapalı ve yeniden açılacak.  
  
 Bağlantı dizesi için ayarlayabileceğiniz bir `CDaoTableDef` bir kaynak bağımsız değişkeni sağlayarak nesne **oluşturma** üye işlevi. Tür, yol, kullanıcı kimliği, parola veya veritabanının ODBC veri kaynağını belirlemek için bu ayarı kontrol edebilirsiniz. Daha fazla bilgi için belirli bir sürücüyü belgelerine bakın.  
  
 İlgili bilgi için DAO Yardımı'nda "özellik Bağlan" konusuna bakın.  
  
##  <a name="setname"></a>CDaoTableDef::SetName  
 Bir tablo için bir kullanıcı tarafından tanımlanan ad ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Bir tablo için bir ad belirten bir dize ifadesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Adı bir harf ile başlamalı ve en fazla 64 karakter içerebilir. Sayı içerebilir ve alt çizgi karakterleri ancak noktalama veya boşluk içeremez.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
##  <a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName  
 Bağlı bir tablonun adı veya temel tablo adını üzerinde belirtmek için bu üye işlevini çağırın `CDaoTableDef` nesne dayanır, özgün veri kaynağında mevcut olduğundan.  
  
```  
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszSrcTableName*  
 Dış veritabanında bir tablo adı belirten bir dize ifadesi için bir işaretçi. Temel tablo için boş bir dize ayarıdır ("").  
  
### <a name="remarks"></a>Açıklamalar  
 Ardından çağırmalısınız [RefreshLink](#refreshlink). Bu özellik ayarı için bir temel tablo ve okuma/yazma ekli bir tablo veya bir koleksiyona eklenmemiş bir nesne için boştur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "SourceTableName özellik" konusuna bakın.  
  
##  <a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule  
 Bir tabledef için bir doğrulama kuralı ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetValidationRule(LPCTSTR lpszValidationRule);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszValidationRule*  
 Bir işlem doğrulayan bir dize ifadesi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Doğrulama kuralları güncelleştirme işlemleri bağlantılı olarak kullanılır. Bir tabledef bir doğrulama kuralı içeriyorsa, veriler değiştirilmeden önce o tabledef güncelleştirmeleri belirlenmiş ölçütlerini karşılamalıdır. Değişiklik metnini içeren bir özel durum, ölçütleri eşleşmiyorsa [GetValidationText](#getvalidationtext) görüntülenir.  
  
 Doğrulama Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için desteklenir. İfade, kullanıcı tanımlı işlevler, etki alanı toplama işlevleri, SQL toplama işlevleri veya sorgular için başvuruda bulunamaz. Bir doğrulama kuralı için bir `CDaoTableDef` nesnesi, söz konusu nesne birden çok alanlara başvurabilir.  
  
 Örneğin, adlandırılmış alanlar için `hire_date` ve `termination_date`, bir doğrulama kuralı olabilir:  
  
 [!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]  
  
 İlgili bilgi için "ValidationRule özelliğinde" DAO Yardım konusuna bakın.  
  
##  <a name="setvalidationtext"></a>CDaoTableDef::SetValidationText  
 Bir doğrulama kuralı için özel durum metni ayarlamak için bu üye işlevini çağırın bir `CDaoTableDef` Microsoft Jet veritabanı altyapısı tarafından desteklenen bir temel alınan temel tablo nesnesiyle.  
  
```  
void SetValidationText(LPCTSTR lpszValidationText);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszValidationText*  
 Bir işaretçi veri girdiyseniz görüntülenen metni belirten bir dize ifadesi geçersiz.  
  
### <a name="remarks"></a>Açıklamalar  
 Ekli bir tablo doğrulama metnin ayarlanamıyor.  
  
 İlgili bilgi için DAO Yardımı'ndaki "ValidationText özelliği" konusuna bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
