---
title: CDaoTableDef sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a943374731785ecadd13f89ee5c1b760acfb46d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064868"
---
# <a name="cdaotabledef-class"></a>CDaoTableDef sınıfı

Temel tablonun veya eklenen tablonun saklı tanımını temsil eder.

## <a name="syntax"></a>Sözdizimi

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Oluşturur bir `CDaoTableDef` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef::Append](#append)|Yeni Tablo veritabanına ekler.|
|[CDaoTableDef::CanUpdate](#canupdate)|Tablo güncelleştirilebilir, sıfır döndürür (alanlar veya tablo özelliklerini tanımını değiştirebilirsiniz).|
|[CDaoTableDef::Close](#close)|Bir açık tabledef kapatır.|
|[CDaoTableDef::Create](#create)|Kullanarak veritabanına eklenen bir tablo oluşturur [ekleme](#append).|
|[CDaoTableDef::CreateField](#createfield)|Bir tablo için bir alan oluşturmak üzere çağrılır.|
|[CDaoTableDef::CreateIndex](#createindex)|Bir tablo için dizin oluşturma için çağrılır.|
|[CDaoTableDef::DeleteField](#deletefield)|Bir tablodan alan silmek için çağrılır.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|Tablodan bir dizini silmek için çağrılır.|
|[CDaoTableDef::GetAttributes](#getattributes)|Bir veya daha fazla özelliklerini gösteren bir değer döndüren bir `CDaoTableDef` nesne.|
|[CDaoTableDef::GetConnect](#getconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer döndürür.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Temel tablo temel tarihi ve saati döndürür. bir `CDaoTableDef` nesnesi oluşturuldu.|
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Temel tablo tasarımı için yapılan en son değiştirme saati ve tarihi döndürür.|
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Tabloda alanların sayısını temsil eden bir değer döndürür.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Tablodaki belirli tür alanları hakkında bilgileri döndürür.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|Dizin tablosu için sayısını döndürür.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Belirli tür tablosu için dizinler hakkında bilgileri döndürür.|
|[CDaoTableDef::GetName](#getname)|Kullanıcı tanımlı tablo adını döndürür.|
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Tablodaki kayıt sayısını döndürür.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Kaynak veritabanına ekli tablo adını belirten bir değeri döndürür.|
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Bir alandaki verileri değiştirildi veya tabloya eklenen doğrulayan bir değer döndürür.|
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Bir alan nesnesinin değerini belirtilen doğrulama kuralı karşılamaz, uygulamanızın görüntülediği iletisinin metni belirten bir değeri döndürür.|
|[CDaoTableDef::IsOpen](#isopen)|Tablo ise sıfır olmayan döndürür açın.|
|[CDaoTableDef::Open](#open)|Kullanıcının TableDef'ın koleksiyonu veritabanında varolan bir tabledef depolanan açar.|
|[CDaoTableDef::RefreshLink](#refreshlink)|Ekli bir tablo için bağlantı bilgilerini güncelleştirir.|
|[CDaoTableDef::SetAttributes](#setattributes)|Bir veya daha fazla özelliklerini gösteren bir değer ayarlar bir `CDaoTableDef` nesne.|
|[CDaoTableDef::SetConnect](#setconnect)|Bir tablonun kaynağı hakkında bilgi sağlayan bir değer ayarlar.|
|[CDaoTableDef::SetName](#setname)|Tablonun adını ayarlar.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Kaynak veritabanına ekli bir tablo adını belirten bir değeri ayarlar.|
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Bir alandaki verileri değiştirildi veya tabloya eklenen doğrulayan bir değer ayarlar.|
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Bir alan nesnesinin değerini belirtilen doğrulama kuralı karşılamaz, uygulamanızın görüntülediği iletisinin metni belirten bir değeri ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Tabledef nesnesi temel DAO arabirim işaretçisi.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Bu tablo için kaynak veritabanı.|

## <a name="remarks"></a>Açıklamalar

Her DAO veritabanı nesnesi tüm kaydedilmiş DAO tabledef nesneleri içeren TableDefs adlı bir koleksiyon tutar.

Kullanarak bir tablo tanımı düzenleme bir `CDaoTableDef` nesne. Örneğin, şunları yapabilirsiniz:

- Herhangi bir veritabanında yerel, eklenen veya dış tablo alanı ve dizin yapısını inceleyin.

- Çağrı `SetConnect` ve `SetSourceTableName` bağlı tablolar ve kullanmak için üye işlevleri `RefreshLink` bağlantılarını güncelleştirmek için üye işlevi bağlı tablolar.

- Çağrı `CanUpdate` tablosundaki alan tanımları düzenleyip düzenleyemeyeceğini belirlemek için üye işlevi.

- Alınacak veya ayarlanacak kullanarak doğrulama koşullar `GetValidationRule` ve `SetValidationRule`ve `GetValidationText` ve `SetValidationText` üye işlevleri.

- Kullanım `Open` üye işlevi bir tablo, dinamik veya anlık görüntü türü oluşturmak için `CDaoRecordset` nesne.

    > [!NOTE]
    >  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. Hala DAO sınıfları ile ODBC veri kaynaklarına erişim de kullanabilirsiniz. DAO sınıfları, genellikle Microsoft Jet veritabanı altyapısına özgü olduğundan üstün özellikler sunar.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>TableDef nesneleri veya varolan bir tablo ile çalışmak için yeni bir tablo oluşturmak için kullanılacak

1. Her durumda, ilk oluşturmak bir `CDaoTableDef` nesne, işaretçi sağlayan bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) tabloya ait olduğu nesne.

1. Ardından istediğinize bağlı olarak aşağıdakileri yapın:

   - Mevcut bir tablosu kaydedildi kullanmak için tabledef nesnenin çağrı [açık](#open) üye işlevi, kaydedilmiş tablonun adını belirtin.

   - Yeni bir tablo oluşturmak için tabledef nesnenin çağrı [Oluştur](#create) üye işlevi, tablo adını belirtin. Çağrı [CreateField](#createfield) ve [CreateIndex](#createindex) alanlarını ve dizinleri tabloya eklenecek.

   - Çağrı [ekleme](#append) veritabanının TableDefs koleksiyonu için ekleyerek tabloyu kaydetmek için. `Create` tabledef açık bir duruma koyar arama sonra bunu `Create` çağrılmayan `Open`.

        > [!TIP]
        >  Kaydedilen tablolar oluşturmak için en kolay yolu, bunları oluşturabilir ve bunları Microsoft Access kullanarak veritabanınızda depolamak sağlamaktır. Ardından açın ve bunları MFC kodunuzda kullanın.

Açılamıyor veya oluşturulan tabledef nesnesi kullanmak için oluşturma ve açık bir `CDaoRecordset` nesnesi ile tabledef adını belirten bir `dbOpenTable` değerini *nOpenType* parametresi.

Tabledef nesnesi oluşturmak için kullanılacak bir `CDaoRecordset` nesnesi, genellikle oluşturmak veya değer özelliği yukarıda açıklandığı şekilde açın ve ardından çağırdığınızda tabledef nesneniz için bir işaretçi işleve bir kayıt kümesi nesnesi oluşturmak [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Geçirdiğiniz tabledef açık durumda olması gerekir. Daha fazla bilgi için bkz. [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Tabledef nesneyi kullanmayı bitirdikten sonra arama, [Kapat](../../mfc/reference/cdaorecordset-class.md#close) üye işlev; ardından tabledef nesnesi yok.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="append"></a>  CDaoTableDef::Append

Çağırdıktan sonra bu üye işlevi çağrısı [Oluştur](#create) tabledef veritabanına kaydetmek için yeni bir tabledef nesne oluşturmak için.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

İşlev nesnesi için veritabanının TableDefs koleksiyonu ekler. Bunu ekleyerek değil tanımlarken tabledef geçici bir nesne olarak kullanabilirsiniz, ancak kaydetmek ve kullanmak istiyorsanız, çağırmalıdır `Append`.

> [!NOTE]
>  (Null veya boş bir dize içeren) bir adlandırılmamış tabledef eklenecek çalışırsanız, MFC özel durum oluşturur.

İlgili bilgiler için DAO Yardımı'nda "yöntemi ekleme" konusuna bakın.

##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate

Belirlemek için bu üye işlevi çağrısı olup olmadığını temel tablo tanımı bir `CDaoTableDef` nesnesi değiştirilebilir.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Dönüş Değeri

Tablo yapısı (şema) değiştirilebilir olursa sıfır dışı (ekler veya alanlarını ve dizinleri silme), aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, yeni oluşturulan tabloyu temel alınan bir `CDaoTableDef` nesne güncelleştirilebilir ve bir ekli tablo arka plandaki bir `CDaoTableDef` Nesne güncelleştirilemiyor. A `CDaoTableDef` elde edilen kayıt güncelleştirilebilir olmasa bile nesne güncelleştirilebilir, olabilir.

İlgili bilgiler için DAO Yardımı'nda "güncelleştirilebilir özelliği" konusuna bakın.

##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef

Oluşturur bir `CDaoTableDef` nesne.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Parametreler

*pDatabase*<br/>
Bir işaretçi bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Nesne oluşturduktan sonra çağırmanız gerekir [Oluştur](#create) veya [açık](#open) üye işlevi. Nesne ile işiniz bittiğinde, çağırmalıdır kendi [Kapat](#close) üye işlevi ve yok et `CDaoTableDef` nesne.

##  <a name="close"></a>  CDaoTableDef::Close

Kapat ve tabledef nesneyi serbest bırakmak için bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Arama sonra genellikle `Close`, ile ayırdığınızda tabledef nesneyi silmek **yeni**.

Çağırabilirsiniz [açık](#open) arama sonra yeniden `Close`. Bu, yeniden tabledef nesnesi sağlar.

İlgili bilgiler için "Kapat yöntemi" DAO Yardım konusuna bakın.

##  <a name="create"></a>  CDaoTableDef::Create

Yeni kaydedilen bir tablo oluşturmak için bu üye işlevini çağırın.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Tablonun adını içeren bir dize işaretçisi.

*lAttributes*<br/>
Tabledef nesnesiyle temsil edilen tablo özelliklerini karşılık gelen bir değer. Aşağıdaki sabitler hiçbirini birleştirmek için bit düzeyinde OR kullanabilirsiniz:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan eklenen tablonun gösterilir.|
|`dbAttachSavePWD`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı Kimliğini ve parolasını eklenen tablonun bağlantı bilgileriyle birlikte kaydedilir gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo gösterir.|

*lpszSrcTable*<br/>
Kaynak tablo adını içeren bir dize işaretçisi. Varsayılan olarak bu değeri NULL olarak başlatılır.

*lpszConnect*<br/>
Varsayılan bağlantı dizesi içeren bir dize işaretçisi. Varsayılan olarak bu değeri NULL olarak başlatılır.

### <a name="remarks"></a>Açıklamalar

Ardından tabledef adlandırdığınız sonra çağırabilirsiniz [ekleme](#append) tabledef veritabanının TableDefs koleksiyonu kaydedilecek. Arama sonra `Append`tabledef açık durumda ve oluşturmak için kullanmak bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne.

İlgili bilgiler için DAO Yardımı'nda "CreateTableDef Yöntemi" konusuna bakın.

##  <a name="createfield"></a>  CDaoTableDef::CreateField

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

*lpszName*<br/>
Bu alanın adını belirten bir dize ifadesi için bir işaretçi.

*nTür*<br/>
Alanın veri türünü belirten bir değer. Ayar şu değerlerden biri olabilir:

|Tür|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|Para birimi ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|çift|
|`dbDate`|8|Tarih/saat ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Uzun İkili (OLE nesne) [CLongBinary](../../mfc/reference/clongbinary-class.md) veya [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|Not ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize*<br/>
Metin içeren bir alanın bayt cinsinden en büyük boyutu veya sabit metin veya sayısal değerleri içeren bir alan boyutunu belirten bir değer. *LSize* parametresi tüm metin alanları için yoksayılır.

*lAttributes*<br/>
Bit düzeyinde OR kullanarak alan ve özelliklerle karşılık gelen bir değer birleştirilebilir.

|Sabit|Açıklama|
|--------------|-----------------|
|`dbFixedField`|Alan boyutu (sayısal alanlar için varsayılan değer) sabit.|
|`dbVariableField`|Alan boyutu (yalnızca metin alanları) değişkendir.|
|`dbAutoIncrField`|Yeni kayıtlar için alan değeri otomatik olarak değiştirilemez bir benzersiz uzun tamsayı olarak artırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.|
|`dbUpdatableField`|Alan değeri değiştirilebilir.|
|`dbDescending`|Alan azalan düzende sıralanır (Z - A veya 100 0) (yalnızca bir alan nesnesinde bir alanlar koleksiyonu dizin nesnesi için geçerlidir). Bu sabitin atlarsanız, alanın artan düzende sıralanır (A - Z veya 0 - 100) order (varsayılan).|

*FieldInfo*<br/>
Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.

### <a name="remarks"></a>Açıklamalar

A `DAOField` (OLE) nesnesi oluşturulur ve alanlar koleksiyonuna eklenmiş `DAOTableDef` (OLE) nesne. Nesne özellikleri incelemek için kullanımı yanı sıra, ayrıca kullanabilirsiniz `CDaoFieldInfo` değer özelliği yeni alanlar oluşturmak için bir giriş parametresi oluşturmak için. Ürününün ilk sürümünü `CreateField` kullanmak daha basittir, ancak daha hassas bir denetim istiyorsanız, ikinci sürümü kullanabilirsiniz `CreateField`, hangi alır bir `CDaoFieldInfo` parametresi.

Sürümünü kullanıyorsanız `CreateField` almayan bir `CDaoFieldInfo` parametresi, dikkatli bir şekilde ayarlamanız gerekir her biri aşağıdaki üyeleri `CDaoFieldInfo` yapısı:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Kalan üyeleri `CDaoFieldInfo` ayarlanmalıdır **0**, FALSE veya üye için uygun olarak boş bir dize veya bir `CDaoException` ortaya çıkabilir.

İlgili bilgiler için DAO Yardımı'nda "CreateField yöntemi" konusuna bakın.

##  <a name="createindex"></a>  CDaoTableDef::CreateIndex

Bir tabloya bir dizin eklemek için bu işlevi çağırın.

```
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Parametreler

*indexinfo*<br/>
Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.

### <a name="remarks"></a>Açıklamalar

Dizinler veritabanı tablolarını ve yinelenen kayıtları kabul edilmez erişilen kaydı sırasını belirtin. Dizinler, ayrıca veri verimli erişim sağlar.

Tablolar için dizin oluşturmanız gerekmez, ancak büyük, dizinden çıkarılmış tablolarda, belirli bir kayda erişmek veya bir kayıt kümesi oluşturma uzun zaman alabilir. Diğer taraftan, çok fazla dizinler oluşturma güncelleştirmesini yavaşlatan, ekleme ve silme işlemleri gibi tüm dizinleri otomatik olarak güncelleştirilir. Hangi dizin oluşturmaya karar verdiğinde aşağıdaki faktörleri göz önünde bulundurun.

Aşağıdaki üyeleri `CDaoIndexInfo` yapısı ayarlanmalıdır:

- `m_strName` Bir ad sağlanmalıdır.

- `m_pFieldInfos` Bir dizi için işaret etmelidir `CDaoIndexFieldInfo` yapıları.

- `m_nFields` Dizi alanların sayısını belirtmelisiniz `CDaoFieldInfo` yapıları.

Kalan üyeleri yoksayılan ise FALSE olarak ayarlanır. Ayrıca, `m_lDistinctCount` üye dizini oluşturma sırasında yok sayılır.

##  <a name="deletefield"></a>  CDaoTableDef::DeleteField

Bir alanı kaldırmak ve erişilemez kolaylaştırmak için bu üye işlevini çağırın.

```
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Varolan bir alanın adı bir dize ifadesi için bir işaretçi.

*nIndex*<br/>
Tablonun sıfır tabanlı alanlar koleksiyonu için dizine göre arama alanı dizini.

### <a name="remarks"></a>Açıklamalar

Veritabanına eklenmemiş yeni bir nesne üzerinde bu üye işlevi kullanabilirsiniz veya [CanUpdate](#canupdate) sıfır döndürür.

İlgili bilgiler için "Delete yöntemini" DAO Yardım konusuna bakın.

##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex

Temel alınan tabloda bir dizini silmek için bu üye işlevini çağırın.

```
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Var olan bir dizin adı bir dize ifadesi için bir işaretçi.

*nIndex*<br/>
Veritabanının sıfır tabanlı TableDefs koleksiyonu için arama dizini tarafından dizin nesnenin dizi dizini.

### <a name="remarks"></a>Açıklamalar

Veritabanına eklenmemiş yeni bir nesne üzerinde bu üye işlevi kullanabilirsiniz veya [CanUpdate](#canupdate) sıfır döndürür.

İlgili bilgiler için "Delete yöntemini" DAO Yardım konusuna bakın.

##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes

İçin bir `CDaoTableDef` nesne, dönüş değeri tarafından temsil edilen tablo özelliklerini belirtir `CDaoTableDef` nesne ve bu sabiti toplamı olabilir:

```
long GetAttributes();
```

### <a name="return-value"></a>Dönüş Değeri

Bir veya daha fazla özelliklerini gösteren bir değer döndüren bir `CDaoTableDef` nesne.

### <a name="remarks"></a>Açıklamalar

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan eklenen tablonun gösterilir.|
|`dbAttachSavePWD`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı Kimliğini ve parolasını eklenen tablonun bağlantı bilgileriyle birlikte kaydedilir gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo gösterir.|
|`dbAttachedTable`|Tablo Paradox veritabanı gibi bir ODBC olmayan veritabanına ekli bir tablodan olduğunu gösterir.|
|`dbAttachedODBC`|Ekli bir Microsoft SQL Server gibi bir ODBC veritabanı tablosundan tablo olduğunu gösterir.|

Bir sistem tablosu, çeşitli iç bilgileri içerecek şekilde Microsoft Jet veritabanı altyapısı tarafından oluşturulan bir tablodur.

Geçici Kullanım için Microsoft Jet veritabanı altyapısı tarafından oluşturulan bir tablo gizli bir tablodur.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getconnect"></a>  CDaoTableDef::GetConnect

Bir veri kaynağı için bağlantı dizesini almak için bu üye işlevini çağırın.

```
CString GetConnect();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` tablo için yolu ve veritabanı türünü içeren nesne.

### <a name="remarks"></a>Açıklamalar

İçin bir `CDaoTableDef` ekli bir tablo temsil eden nesne `CString` nesne (bir veritabanı türü belirticisi ve veritabanı için bir yol) bir veya iki bölümden oluşur.

Aşağıdaki tabloda gösterildiği gibi yolu veritabanı dosyalarını içeren dizinin tam yolu ve tanımlayıcısı tarafından gelmelidir "veritabanı =". Bazı durumlarda (Microsoft Jet ve Microsoft Excel ile veritabanlarında olduğu gibi), belirli bir dosya adı veritabanı yol bağımsız değişkeninde dahildir.

Tablodaki [CDaoTableDef::SetConnect](#setconnect) olası veritabanı türleri ve karşılık gelen veritabanı tanımlayıcıları ve yolları gösterir:

Microsoft Jet veritabanı temel tablolar için tanımlayıcısı boş bir dizedir ("").

Parola gerekli ancak sağlanmadı, ODBC sürücüsü bir tablo erişilen bir oturum açma iletişim kutusu ilk zaman görüntüler ve tekrar, bağlantı kapatılıp yeniden. Eklenen tablonun varsa `dbAttachSavePWD` özniteliği, oturum açma istemi tablo yeniden açıldığında görünmez.

İlgili bilgiler için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.

##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated

Temel tablo saat ve tarihi belirlemek için bu işlevi çağırın `CDaoTableDef` nesnesi oluşturuldu.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel alınan tablo oluşturma saat ve tarihi içeren bir değeri `CDaoTableDef` nesne.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları üzerinde temel tablo oluşturulduğu veya en son güncelleştirilen bilgisayardan türetilir. Çok kullanıcılı bir ortamda kullanıcılar, bu ayarları Tutarsızlıklardan kaçınmak için doğrudan dosya sunucusundan almalısınız; diğer bir deyişle, tüm istemciler, "standart" bir zaman kaynağı kullanmanız gerekir; belki de bir sunucudan.

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated

Temel tablo saat ve tarihi belirlemek için bu işlevi çağırın `CDaoTableDef` nesne son güncelleştirildi.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Dönüş Değeri

Temel tablo, tarih ve saat içeren bir değer `CDaoTableDef` nesne son güncelleştirildi.

### <a name="remarks"></a>Açıklamalar

Tarih ve saat ayarları üzerinde temel tablo oluşturulduğu veya en son güncelleştirilen bilgisayardan türetilir. Çok kullanıcılı bir ortamda kullanıcılar, bu ayarları Tutarsızlıklardan kaçınmak için doğrudan dosya sunucusundan almalısınız; diğer bir deyişle, tüm istemciler, "standart" bir zaman kaynağı kullanmanız gerekir; belki de bir sunucudan.

İlgili bilgiler için DAO Yardımı'ndaki "Notes LastUpdated Özellikler" bölümüne bakın.

##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount

Tabloda tanımlanan alanların sayısını almak için bu üye işlevini çağırın.

```
short GetFieldCount();
```

### <a name="return-value"></a>Dönüş Değeri

Alan sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda hiçbir nesne olmadığını.

İlgili bilgiler için DAO Yardımı'nda "Count özelliğini" konusuna bakın.

##  <a name="getfieldinfo"></a>  CDaoTableDef::GetFieldInfo

Çeşitli tabledef içinde tanımlı bir alan hakkında bilgi edinmek için bu üye işlevini çağırın.

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
Alan nesne koleksiyonundaki tablonun sıfır tabanlı alanlar için arama dizini tarafından dizin.

*FieldInfo*<br/>
Bir başvuru bir [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı.

*dwInfoOptions*<br/>
Hangi bilgilerin alınacağı alan hakkında belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların döndüren işlev neden yanı sıra aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` (Varsayılan) Adı, türü, boyut öznitelikleri. Hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: sıra gerekli, konum, sıfır uzunluk harmanlama sırası, yabancı adı, kaynak alan kaynak tablosunda izin ver

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: doğrulama kuralı, doğrulama metin, varsayılan değer

*lpszName*<br/>
Ada göre arama için alan nesne adını bir işaretçi. Benzersiz alan adları en fazla 64 karakter dizesiyle addır.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümünü bir alanından dizine göre aramak olanak sağlar. Başka bir sürüm bir alan adına göre aramak olanak sağlar.

Döndürülen bilgileri açıklaması için bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediğinizde de önceki tüm düzeylerde hakkında bilgi alın.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount

Bir tablo için dizin numarasını almak için bu üye işlevini çağırın.

```
short GetIndexCount();
```

### <a name="return-value"></a>Dönüş Değeri

Dizin tablosu için sayısı.

### <a name="remarks"></a>Açıklamalar

Değeri 0 ise, koleksiyonda dizin vardır.

İlgili bilgiler için DAO Yardımı'nda "Count özelliğini" konusuna bakın.

##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo

Çeşitli tabledef içinde tanımlanan dizin hakkında bilgi edinmek için bu üye işlevini çağırın.

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
Koleksiyondaki tablonun sıfır tabanlı dizin, koleksiyondaki konumuna göre arama için dizin nesnesi sayısal dizini.

*indexinfo*<br/>
Bir başvuru bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı.

*dwInfoOptions*<br/>
Seçenekler hangi bilgilerini almak için dizini belirtin. Kullanılabilir seçenekler, hangi kullanıcıların döndüren işlev neden yanı sıra aşağıda listelenmiştir:

- `AFX_DAO_PRIMARY_INFO` Ad alanı bilgi alanları. Hızlı performans için bu seçeneği kullanın.

- `AFX_DAO_SECONDARY_INFO` Birincil bilgilerin yanı sıra: birincil, benzersiz, kümelenmiş, Yoksay gerekli, null değerlere, yabancı

- `AFX_DAO_ALL_INFO` Birincil ve ikincil bilgileri, artı: ayrı sayım

*lpszName*<br/>
Ada göre arama için dizin nesnesi adı için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümünü, koleksiyon içindeki konumuna göre bir dizini arayın sağlar. Başka bir sürüm dizini adına göre aramak olanak sağlar.

Döndürülen bilgileri açıklaması için bkz: [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediğinizde de önceki tüm düzeylerde hakkında bilgi alın.

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="getname"></a>  CDaoTableDef::GetName

Temel alınan tabloda kullanıcı tanımlı adını almak için bu üye işlevini çağırın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı tanımlı adı için bir tablo.

### <a name="remarks"></a>Açıklamalar

Bu ad bir harf ile başlayan ve en fazla 64 karakter içerebilir. Sayılar içerebilir ve alt çizgi karakterleri, ancak noktalama işaretleri veya boşluk içeremez.

İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount

İçinde kaç tane kaydın olduğunu öğrenmek için bu üye işlevi çağrısı bir `CDaoTableDef` nesne.

```
long GetRecordCount();
```

### <a name="return-value"></a>Dönüş Değeri

Tabledef nesnesinde erişilen kayıt sayısı.

### <a name="remarks"></a>Açıklamalar

Çağırma `GetRecordCount` bir tablo türü için `CDaoTableDef` nesne yaklaşık tablosundaki kayıt sayısını yansıtır ve tablo kayıtlarını eklenen ve Silinen hemen etkilenir. İşlem, çağırana kadar kayıt sayısı bir parçası olarak görünür geri [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). A `CDaoTableDef` nesnesi ile hiçbir kayıt 0 kayıt sayısı özelliği ayarı vardır. Bağlı tablolar veya ODBC veritabanlarının ile çalışırken `GetRecordCount` her zaman -1 döndürür.

İlgili bilgiler için DAO Yardımı'nda "RecordCount özelliği" konusuna bakın.

##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName

Kaynak veritabanında eklenen tablonun adını almak için bu üye işlevini çağırın.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` nesnesini bir yerel veri tablo ekli bir tablo ya da boş bir dize kaynağı adını belirtir.

### <a name="remarks"></a>Açıklamalar

Eklenen tablonun Microsoft Jet veritabanına bağlı başka bir veritabanındaki bir tablodur. Bağlı tablolar için veriler, burada diğer uygulamalar tarafından yönetilebilir dış veritabanında kalır.

İlgili bilgiler için DAO Yardımı'nda "SourceTableName özelliği" konusuna bakın.

##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule

Değer özelliği için doğrulama kuralı almak için bu üye işlevini çağırın.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` değiştirildi veya tabloya eklenen bir alandaki veri doğrulama nesnesi.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları güncelleştirme işlemleri bağlantılı olarak kullanılır. Değer özelliği bir doğrulama kuralı varsa, verileri değiştirilmeden önce bu tabledef güncelleştirmeler belirlenmiş ölçütlerini karşılamalıdır. Değişiklik değerini içeren bir özel durum ölçütlerle eşleşmezse [GetValidationText](#getvalidationtext) oluşturulur. İçin bir `CDaoTableDef` nesnesi, bu `CString` salt okunur bir ekli tablo ve okuma/yazma için bir temel tablo.

İlgili bilgiler için DAO Yardımı'nda "ValidationRule özelliğini" konusuna bakın.

##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText

Kullanıcı doğrulama kuralı eşleşmeyen veri girdiğinde görüntülenecek dizeyi almak için bu işlevi çağırın.

```
CString GetValidationText();
```

### <a name="return-value"></a>Dönüş Değeri

A `CString` nesnesini kullanıcı doğrulama kuralı eşleşmeyen veri girerse görüntülenen metni belirtir.

### <a name="remarks"></a>Açıklamalar

İçin bir `CDaoTableDef` nesnesi, bu `CString` salt okunur bir ekli tablo ve okuma/yazma için bir temel tablo.

İlgili bilgiler için DAO Yardımı'nda "ValidationText özelliği" konusuna bakın.

##  <a name="isopen"></a>  CDaoTableDef::IsOpen

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDaoTableDef` nesne şu anda açık değil.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Gösterimiyse `CDaoTableDef` nesnedir açın; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase

Bir işaretçi içeren [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Bu tablo için nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef

DAO tabledef nesne temel OLE arabirimi için bir işaretçi içeren `CDaoTableDef` nesne.

### <a name="remarks"></a>Açıklamalar

DAO arabirimi doğrudan erişim gerekiyorsa, bu işaretçi kullanın.

##  <a name="open"></a>  CDaoTableDef::Open

Değer özelliği açmak için bu üye işlevi, daha önce bir veritabanında kayıtlı arama TableDef'ın koleksiyonu güçlendirin.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Tablo adı belirten bir dize işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink

Ekli bir tablo için bağlantı bilgilerini güncelleştirmek için bu üye işlevini çağırın.

```
void RefreshLink();
```

### <a name="remarks"></a>Açıklamalar

Çağırarak ekli bir tablo için bağlantı bilgilerini değiştirdiğiniz [SetConnect](#setconnect) buna karşılık gelen `CDaoTableDef` nesnesi ve ardından kullanarak `RefreshLink` bilgileri güncelleştirmek için üye işlevi. Çağırdığınızda `RefreshLink`, eklenen tablonun özellikleri değiştirilmez.

Zorlamak için değiştirilmiş, açık olan tüm etkili olması için bağlantı bilgilerini [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneler üzerinde bu tabledef göre kapalı.

İlgili bilgiler için DAO Yardımı'nda "RefreshLink yöntemi" konusuna bakın.

##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes

Bir veya daha fazla özelliklerini gösteren bir değer ayarlar bir `CDaoTableDef` nesne.

```
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Parametreler

*lAttributes*<br/>
Tarafından temsil edilen tablo özelliklerini `CDaoTableDef` nesne ve bu sabiti toplamı olabilir:

|Sabit|Açıklama|
|--------------|-----------------|
|`dbAttachExclusive`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için tablo özel kullanım için açılan eklenen tablonun gösterilir.|
|`dbAttachSavePWD`|Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için kullanıcı Kimliğini ve parolasını eklenen tablonun bağlantı bilgileriyle birlikte kaydedilir gösterir.|
|`dbSystemObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan bir sistem tablosu olduğunu gösterir.|
|`dbHiddenObject`|Tablonun Microsoft Jet veritabanı altyapısı tarafından sağlanan gizli bir tablo gösterir.|

### <a name="remarks"></a>Açıklamalar

Birden çok öznitelik ayarlarken, bit düzeyinde OR işlecini kullanarak uygun sabitleri toplayarak birleştirebilirsiniz. Ayar `dbAttachExclusive` iliştirilmemiş tablosunda bir özel durum oluşturur. Aşağıdaki değerleri, ayrıca özel durum bir üretim birleştirme:

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

İlgili bilgiler için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

##  <a name="setconnect"></a>  CDaoTableDef::SetConnect

İçin bir `CDaoTableDef` (bir veritabanı türü belirticisi ve veritabanı için bir yol) bir veya iki bölümden oluşur, dize nesnesine eklenen tablonun temsil eden nesne.

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Parametreler

*lpszConnect*<br/>
ODBC ya da yüklenebilir ISAM sürücüleri geçirilecek ek parametreler belirten bir dize ifadesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki tabloda gösterildiği gibi yolu veritabanı dosyalarını içeren dizinin tam yolu ve tanımlayıcısı tarafından gelmelidir "veritabanı =". Bazı durumlarda (Microsoft Jet ve Microsoft Excel ile veritabanlarında olduğu gibi), belirli bir dosya adı veritabanı yol bağımsız değişkeninde dahildir.

> [!NOTE]
>  Eşittir işareti çevresinde boşluk formun yolu deyimlerinde içermez "veritabanı = sürücü:\\\path". Bu, oluşturulan bir özel durum ve bağlantının başarısız olmasıyla sonuçlanır.

Aşağıdaki tabloda, olası veritabanı türleri ve karşılık gelen veritabanı tanımlayıcıları ve yolları gösterilmektedir:

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
|HTML içeri aktarma|"HTML alma;"|" `drive`:\\\ *yolu*\ *filename*"|
|HTML dışarı aktarma|"HTML dışarı aktarma;"|" `drive`:\\\ *yolu*"|
|Metin|"Metin"|"sürücü:\\\path"|
|ODBC|"ODBC; Veritabanı = `database`; UID = *kullanıcı*; PWD = *parola*; DSN = *datasourcename;* LOGINTIMEOUT = *saniye;*" (Bu tüm sunucular için bir tam bağlantı dizesi olmayabilir; yalnızca örnek olarak verilmiştir. Parametreleri arasında boşluk olmayan çok önemlidir.)|Yok.|
|Exchange|"Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &AMP;#124; 1};]<br /><br /> [PROFİL = *profili*;]<br /><br /> [PWD = *parola*;]<br /><br /> [VERİTABANI = `database`;] "|*"sürücü*:\\\ *yolu*\\\ *filename*. MDB"|

> [!NOTE]
>  Btrieve DAO 3.5 itibarıyla artık desteklenmiyor.

Çift ters eğik çizgi kullanmanız gerekir (\\\\) bağlantı dizelerindeki. Kullanarak mevcut bir bağlantı özelliklerini değiştirdiğiniz varsa `SetConnect`, sonradan çağırmalıdır [RefreshLink](#refreshlink). Bağlantı özelliklerini kullanarak başlatırken bunu `SetConnect`, ihtiyacınız olmayan çağrı `RefreshLink`, ancak tercih Bunu yapmak, önce tabledef ekleyin.

Parola gerekli ancak sağlanmadı, ODBC sürücüsü bir tablo erişilen bir oturum açma iletişim kutusu ilk zaman görüntüler ve tekrar, bağlantı kapatılıp yeniden.

Bağlantı dizesi için ayarlayabileceğiniz bir `CDaoTableDef` nesnesi bir kaynağı bağımsız değişkenine sağlayarak `Create` üye işlevi. Ayar türü, yol, kullanıcı kimliği, parola veya veritabanının ODBC veri kaynağını belirlemek için kontrol edebilirsiniz. Daha fazla bilgi için belirli bir sürücü için belgelere bakın.

İlgili bilgiler için DAO Yardımı'nda "özelliği Bağlan" konusuna bakın.

##  <a name="setname"></a>  CDaoTableDef::SetName

Bir tablo için bir kullanıcı tanımlı ad ayarlamak için bu üye işlevini çağırın.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Tablo adını belirten bir dize ifadesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Ad bir harf ile başlamalı ve en fazla 64 karakter içerebilir. Sayılar içerebilir ve alt çizgi karakterleri, ancak noktalama işaretleri veya boşluk içeremez.

İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName

Eklenen tablonun adını veya temel tablo adını üzerinde belirtmek için bu üye işlevi çağrısı `CDaoTableDef` nesne dayanır, verilerin özgün kaynakta mevcut olduğundan.

```
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Parametreler

*lpszSrcTableName*<br/>
Dış veritabanında bir tablo adı belirten bir dize ifadesi için bir işaretçi. Temel tablo için ayarı boş bir dizedir ("").

### <a name="remarks"></a>Açıklamalar

Ardından çağırmalıdır [RefreshLink](#refreshlink). Bu özellik ayarı bir temel tablo ve ekli bir tablo veya bir koleksiyonuna eklenmemiş bir nesne için okuma/yazma için boştur.

İlgili bilgiler için DAO Yardımı'nda "SourceTableName özelliği" konusuna bakın.

##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule

Değer özelliği için bir doğrulama kuralı ayarlamak için bu üye işlevini çağırın.

```
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Parametreler

*lpszValidationRule*<br/>
Bir işlem doğrulayan bir dize ifadesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Doğrulama kuralları güncelleştirme işlemleri bağlantılı olarak kullanılır. Değer özelliği bir doğrulama kuralı varsa, verileri değiştirilmeden önce bu tabledef güncelleştirmeler belirlenmiş ölçütlerini karşılamalıdır. Değişiklik metnini içeren bir özel durum ölçütlerle eşleşmezse [GetValidationText](#getvalidationtext) görüntülenir.

Doğrulama, yalnızca Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için desteklenir. İfade, kullanıcı tarafından tanımlanan İşlevler, etki alanı toplama işlevleri, SQL toplama işlevleri veya sorguları başvuruda bulunamaz. Bir doğrulama kuralı için bir `CDaoTableDef` nesneyi o nesnenin içinde birden çok alan başvurabilir.

Örneğin, adlandırılmış alanlar için *hire_date* ve *termination_date*, bir doğrulama kuralı olabilir:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

İlgili bilgiler için DAO Yardımı'nda "ValidationRule özelliğini" konusuna bakın.

##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText

Bir doğrulama kuralı için özel durum metni ayarlamak için bu üye işlevi çağrısı bir `CDaoTableDef` Microsoft Jet veritabanı altyapısı tarafından desteklenen bağlantılı bir temel tablo nesnesi.

```
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Parametreler

*lpszValidationText*<br/>
Bir işaretçi veri girdiyseniz görüntülenen metni belirtir bir dize ifadesi geçersiz.

### <a name="remarks"></a>Açıklamalar

Eklenen tablonun doğrulama metni olarak ayarlanamıyor.

İlgili bilgiler için DAO Yardımı'nda "ValidationText özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
