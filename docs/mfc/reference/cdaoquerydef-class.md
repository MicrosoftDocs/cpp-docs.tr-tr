---
title: "CDaoQueryDef sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
dev_langs: C++
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e619cbc049e64c25325ab8327ec6dd9d16e071be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdaoquerydef-class"></a>CDaoQueryDef sınıfı
Sorgu tanımı ya da "querydef" genellikle bir veritabanında kaydedilmiş temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoQueryDef : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Oluşturan bir **CDaoQueryDef** nesnesi. Sonraki çağrı **açık** veya **oluşturma**gereksinimlerinize bağlı olarak.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoQueryDef::Append](#append)|Querydef veritabanının QueryDefs koleksiyonu kayıtlı bir sorguyu olarak ekler.|  
|[CDaoQueryDef::CanUpdate](#canupdate)|Veritabanını güncelleştirme sorgusu, sıfır olmayan döndürür.|  
|[CDaoQueryDef::Close](#close)|QueryDefs kapatır. Tamamladığınızda, kendisiyle C++ nesne yok.|  
|[CDaoQueryDef::Create](#create)|DAO querydef nesnesini oluşturur. Bir geçici sorgu veya çağrı querydef kullanmak **Append** veritabanına kaydetmek için.|  
|[CDaoQueryDef::Execute](#execute)|Querydef nesnesi tarafından tanımlanan sorgusunu çalıştırır.|  
|[CDaoQueryDef::GetConnect](#getconnect)|Querydef ile ilişkili bağlantı dizesi döndürür. Veri kaynağı bağlantı dizesini tanımlar. (SQL için doğrudan yalnızca; Aksi halde boş bir dize sorgular.)|  
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Kaydedilmiş sorguyu oluşturulduğu tarihi döndürür.|  
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Kayıtlı sorgunun son güncelleştirildiği tarihi döndürür.|  
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Querydef tarafından tanımlanan alan sayısını döndürür.|  
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Sorguda tanımlanan belirtilen bir alan hakkında bilgi döndürür.|  
|[CDaoQueryDef::GetName](#getname)|Querydef adını döndürür.|  
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|(ODBC sorgu için) ODBC tarafından kullanılan zaman aşımı değeri döndürür querydef yürütülürse ne zaman. Bu sorgunun eylemi tamamlamak izin vermek ne kadar süreyle belirler.|  
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Sorgu için tanımlanan parametre sayısını döndürür.|  
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Belirtilen parametre hakkında bilgi için sorgu döndürür.|  
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Belirtilen parametre değerini sorguya döndürür.|  
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Bir eylem sorgu tarafından etkilenen kayıtların sayısı döndürür.|  
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Querydef tarafından tanımlanan sorgu kayıt döndürürse sıfır olmayan bir değer döndürür.|  
|[CDaoQueryDef::GetSQL](#getsql)|Querydef tarafından tanımlanan sorgusu belirtir SQL dizesi döndürür.|  
|[CDaoQueryDef::GetType](#gettype)|Sorgu türü döndürür: silerseniz, güncelleştirme, ekleme, tablo yapma ve benzeri.|  
|[CDaoQueryDef::IsOpen](#isopen)|Querydef açıksa ve yürütülebilir sıfır olmayan bir değer döndürür.|  
|[CDaoQueryDef::Open](#open)|Veritabanının QueryDefs koleksiyonu içinde depolanan var olan bir querydef açar.|  
|[CDaoQueryDef::SetConnect](#setconnect)|Bir ODBC veri kaynağında bir SQL doğrudan sorgusu için bağlantı dizesini ayarlar.|  
|[CDaoQueryDef::SetName](#setname)|Querydef oluşturulduğu sırada kullanımda adını değiştirerek kayıtlı sorgunun adını ayarlar.|  
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|(ODBC sorgu için) ODBC tarafından kullanılan zaman aşımı değeri ayarlar querydef yürütülürse ne zaman.|  
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Belirtilen parametre değerini sorguya ayarlar.|  
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Querydef kayıt döndürüp döndürmediğini belirtir. Bu öznitelik ayarını **doğru** yalnızca SQL geçiş sorguları için geçerlidir.|  
|[CDaoQueryDef::SetSQL](#setsql)|Querydef tarafından tanımlanan sorgusu belirtir SQL dizesini ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|DAO querydef nesnesini OLE arabirimi için bir işaretçi.|  
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Bir işaretçi `CDaoDatabase` querydef olduğu ilişkili nesne. Querydef veritabanında veya kaydedilmiş olabilir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sorgu ve "Oluşturulma tarihi" ve "ODBC zaman aşımı." gibi özelliklerini açıklayan SQL deyimi içeren bir veri erişim nesnesi bir querydef olan Kaydetmeden geçici querydef nesneleri oluşturabilirsiniz, ancak uygun olan — ve çok daha verimli — yaygın olarak kaydetmek için bir veritabanı sorguları yeniden kullanılabilir. A [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne kaydedilmiş querydefs içeren QueryDefs koleksiyonu adlı bir koleksiyon korur.  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile erişim ODBC veri kaynakları hala kullanabilirsiniz. Genel olarak, üzerinde DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıfları daha yetenekli; DAO tabanlı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri üzerinden de dahil olmak üzere, verilere erişebilir. DAO tabanlı sınıflar da tabloları sınıfları aracılığıyla doğrudan çağırmak zorunda kalmadan ekleme gibi veri tanımlama dili (DDL) işlemleri desteklemez.  
  
## <a name="usage"></a>Kullanım  
 QueryDef nesneleri ya da bir sorgu kaydedilen var olan iş için veya yeni bir sorgu veya geçici sorgu kaydedilen kullanın:  
  
1.  Her durumda, ilk oluşturmak bir `CDaoQueryDef` gösteren bir işaretçi sağladığını nesne [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) sorgunun ait olduğu nesne.  
  
2.  Ardından istediğinize bağlı olarak aşağıdakileri yapın:  
  
    -   Varolan bir sorgu kaydedilen kullanmak için querydef nesnesinin çağrısı [açık](#open) üye işlevi, kayıtlı sorgunun adını belirtin.  
  
    -   Yeni kaydedilen bir sorgu oluşturmak için querydef nesnesinin çağrısı [oluşturma](#create) üye işlevi, sorgunun adını belirtin. ' I çağırın [Append](#append) veritabanının QueryDefs koleksiyonu ekleyerek sorguyu kaydetmek için. **Create** querydef açık bir duruma koyar çağırdıktan sonra bunu **oluşturma** çağrılmayan **açmak**.  
  
    -   Geçici bir querydef oluşturmak için çağrı **oluşturma**. Sorgu adı boş bir dize geçirin. Çağırmayın **Append**.  
  
 QueryDefs kullanmayı bitirdiğinizde, çağrı kendi [Kapat](#close) üye işlev; querydef nesnesi yok.  
  
> [!TIP]
>  Kaydedilmiş sorguları oluşturmak için kolay bunları oluşturmak ve bunları Microsoft Access kullanarak veritabanınızda depolamak için yoludur. Ardından açın ve MFC kodunuzda kullanabilirsiniz.  
  
## <a name="purposes"></a>Amaçları  
 QueryDefs herhangi aşağıdaki amaçlar için kullanabilirsiniz:  
  
-   Oluşturmak için bir `CDaoRecordset` nesnesi  
  
-   Nesnenin çağırmak için **yürütme** doğrudan eylem sorgusu veya SQL doğrudan bir sorguyu yürütmek için üye işlevi  
  
 QueryDefs sorgu seçin, eylem, çapraz, silme, güncelleştirme dahil olmak üzere, her tür için kullanmak, ekleme, tablo oluşturma, veri tanımı, SQL doğrudan, UNION ve sorguları toplu. Sorgunun türü sağladığınız SQL deyimini içerik tarafından belirlenir. Sorgu türleri hakkında daha fazla bilgi için bkz: **yürütme** ve [GetType](#gettype) üye işlevleri. Kayıt kümeleri, satır döndürmek için yaygın olarak kullanılır, genellikle bu kullanarak sorgular **seçin... GELEN** anahtar sözcükler. **Yürütme** toplu işlemleri için en yaygın olarak kullanılır. Daha fazla bilgi için bkz: [yürütme](#execute) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
## <a name="querydefs-and-recordsets"></a>QueryDefs ve kayıt kümeleri  
 QueryDefs oluşturmak için kullanılacak bir `CDaoRecordset` nesne, genellikle oluşturun veya bir querydef yukarıda açıklandığı gibi açın. Çağırdığınızda, querydef nesnesine bir işaretçi geçirme bir kayıt kümesi nesnesi oluşturmak [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Geçirdiğiniz querydef açık durumda olması gerekir. Daha fazla bilgi için bkz [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Bir querydef açık durumda olmadığı sürece kayıt kümesi (en yaygın kullanımı bir querydef için) oluşturmak için kullanamazsınız. Querydef bir açık ya da çağırarak duruma **açmak** veya **oluşturma**.  
  
## <a name="external-databases"></a>Dış veritabanlarını  
 QueryDef nesneleri bir dış veritabanı altyapısı'nın özgün SQL dialect kullanmak için tercih edilen yöntemdir. Örneğin, (Microsoft SQL Server üzerinde kullanılan gibi) bir Transact SQL sorgusu oluşturun ve bir querydef nesnesinde saklayabilirsiniz. Microsoft Jet veritabanı altyapısını temel olmayan bir SQL sorgusu kullanmanız gerektiğinde, dış veri kaynağı için bir bağlantı dizesi belirtmeniz gerekir. Geçerli bağlantı dizeleri sorgularıyla veritabanı altyapısı atlayabilir ve işleme için dış veritabanı sunucusu için doğrudan sorgu geçirin.  
  
> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen bir Microsoft Jet eklenecek yoldur (. MDB) veritabanı.  
  
 İlgili bilgi için "QueryDefs", "QueryDefs koleksiyonu" ve "CdbDatabase nesnesinde" DAO SDK konularına bakın.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoQueryDef`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="append"></a>CDaoQueryDef::Append  
 Çağırdıktan sonra bu üye işlevini çağırın [oluşturma](#create) yeni bir querydef nesnesi oluşturmak için.  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Açıklamalar  
 **Append** querydef veritabanının QueryDefs koleksiyonu nesne eklenerek veritabanına kaydeder. Sonuna ekleme olmadan querydef geçici bir nesne kullanabilirsiniz, ancak kalıcı hale getirmek istiyorsanız, çağırmalısınız **Append**.  
  
 Geçici QueryDefs append çalışırsanız, MFC türünde bir özel durum atar [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="canupdate"></a>CDaoQueryDef::CanUpdate  
 Querydef değişiklik olup olmadığını belirlemek için bu üye işlevini çağırın — adını veya SQL dizesi değiştirme gibi.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Querydef değiştirmeye izin veriyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa querydef değiştirebilirsiniz:  
  
-   Bu salt okunur açık bir veritabanını temel alan değil.  
  
-   Veritabanı için güncelleştirme izinlerine sahip.  
  
     Bu güvenlik özellikleri olup uyguladık üzerinde bağlıdır. MFC desteği için güvenlik sağlamaz; kendiniz DAO'yu doğrudan çağırma veya Microsoft Access kullanarak uyguladıktan gerekir. DAO Yardımı'ndaki "izinleri özellik" konusuna bakın.  
  
##  <a name="cdaoquerydef"></a>CDaoQueryDef::CDaoQueryDef  
 Oluşturan bir **CDaoQueryDef** nesnesi.  
  
```  
CDaoQueryDef(CDaoDatabase* pDatabase);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDatabase`  
 Açık bir işaretçi [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne veritabanının QueryDefs koleksiyonu, koleksiyonda depolanması için yeni bir sorgu veya değil depolanması için geçici bir sorgu depolanan var olan bir querydef temsil edebilir. Sonraki adımınız querydef türüne bağlıdır:  
  
-   Varolan bir querydef nesneyi temsil ediyorsa, nesnenin çağrısı [açık](#open) başlatmak üzere üye işlevi.  
  
-   Nesne kaydedilmesi için yeni bir querydef temsil ediyorsa, nesnenin çağrısı [oluşturma](#create) üye işlevi. Bu nesne veritabanının QueryDefs koleksiyonuna ekler. ' I çağırın `CDaoQueryDef` üye işlevleri nesnenin özniteliklerini ayarlayın. Son olarak, arama [Append](#append).  
  
-   Geçici bir querydef (veritabanında kaydedilecek değil) nesneyi temsil ediyorsa, çağrı **oluşturma**, sorgunun adı boş bir dize geçirme. Çağırdıktan sonra **oluşturma**, querydef doğrudan özniteliklerini başlatırsınız. Çağırmayın **Append**.  
  
 Querydef özniteliklerini ayarlamak için kullanabileceğiniz [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)ve [SetReturnsRecords](#setreturnsrecords) üye işlevleri.  
  
 QueryDefs ile işiniz bittiğinde, çağrı kendi [Kapat](#close) üye işlevi. Querydef gösteren bir işaretçi varsa, **silmek** işleci C++ nesnesini yok.  
  
##  <a name="close"></a>CDaoQueryDef::Close  
 QueryDefs kullanarak tamamladığınızda bu üye işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 DAO nesnesini serbest ancak kaydedilmiş DAO querydef nesnesi ya da C++ silmiyor querydef kapatma `CDaoQueryDef` nesnesi. Bu aynı değil [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), hangi siler querydef koleksiyonundan veritabanının QueryDefs DAO (geçici bir querydef değilse).  
  
##  <a name="create"></a>CDaoQueryDef::Create  
 Yeni kaydedilen bir sorgu veya yeni bir geçici sorgu oluşturmak için bu üye işlevini çağırın.  
  
```  
virtual void Create(
    LPCTSTR lpszName = NULL,  
    LPCTSTR lpszSQL = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Veritabanında kayıtlı sorgunun benzersiz adı. Dize hakkında daha fazla ayrıntı için DAO Yardımı'ndaki "CreateQueryDef yöntemi" konusuna bakın. Varsayılan değer, boş bir dize kabul ederseniz, geçici bir querydef oluşturulur. Böyle bir sorguyu QueryDefs koleksiyonu kaydedilmez.  
  
 `lpszSQL`  
 Sorguyu tanımlayan SQL dizesi. Varsayılan değerini kabul ederseniz **NULL**, daha sonra çağırmalısınız [SetSQL](#setsql) dizesi ayarlanacak. O zamana kadar sorgu tanımlanmamıştır. Ancak, bir kayıt kümesi açmak için tanımsız sorgu kullanabilirsiniz; Açıklamalar için bkz. QueryDefs koleksiyonu querydef eklemeden önce SQL deyimini tanımlanması gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir ad geçirirseniz `lpszName`, ardından çağırabilirsiniz [Append](#append) veritabanının QueryDefs koleksiyonu querydef kaydetmek için. Aksi takdirde nesnesi geçici bir querydef ve kaydedilmez. Her iki durumda da querydef açık durumda olan ve ya da onu oluşturmak için kullanabileceğiniz bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesne veya querydef's çağrısı [yürütme](#execute) üye işlevi.  
  
 Bir SQL deyiminde belirtmezseniz `lpszSQL`, sorgu ile çalıştırılamıyor **yürütme** ancak bir kayıt kümesi oluşturmak için kullanın. Bu durumda, MFC kayıt kümesinin varsayılan SQL deyimini kullanır.  
  
##  <a name="execute"></a>CDaoQueryDef::Execute  
 Querydef nesnesi tarafından tanımlanan sorguyu çalıştırmak için bu üye işlevini çağırın.  
  
```  
virtual void Execute(int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Parametreler  
 `nOptions`  
 Sorgu özelliklerini belirleyen bir tamsayı. İlgili bilgi için DAO Yardımı'ndaki "yöntemi Çalıştır" konusuna bakın. Bit düzeyinde OR işleci kullanabilirsiniz ( **&#124;**) bu bağımsız değişken için aşağıdaki sabitleri birleştirmek için:  
  
- **dbDenyWrite** diğer kullanıcılara reddetme yazma izni.  
  
- **dbInconsistent** tutarsız güncelleştirmeler.  
  
- **dbConsistent** tutarlı güncelleştirmeler.  
  
- **dbSQLPassThrough** SQL doğrudan. Bir ODBC veritabanı işlenmek üzere geçirilmesi için SQL deyimini neden olur.  
  
- **dbFailOnError** varsayılan değer. Bir hata oluşursa, güncelleştirmeleri ve hata raporu kullanıcıya geri.  
  
- **dbSeeChanges** başka bir kullanıcı düzenlemekte verileri değiştirme, bir çalışma zamanı hatası oluşturur.  
  
> [!NOTE]
>  Koşulları bir açıklaması için "tutarsız" ve "tutarlı," DAO Yardımı'ndaki "yöntemi Çalıştır" konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu şekilde yürütmek için kullanılan Querydef nesneleri aşağıdaki sorgu türlerinden birini temsil edebilir:  
  
-   Eylem sorguları  
  
-   SQL doğrudan sorguları  
  
 **Yürütme** select sorguları gibi kayıtları döndüren sorgular için çalışmaz. **Yürütme** toplu işlemi sorgularında gibi yaygın olarak kullanılan **güncelleştirme**, **Ekle**, veya **SELECT INTO**, veya veri tanımlama dili (DDL) işlemler.  
  
> [!TIP]
>  ODBC veri kaynakları ile çalışmak için tercih edilen yol için bir Microsoft Jet tabloları eklemektir (. MDB) veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.  
  
 Çağrı [GetRecordsAffected](#getrecordsaffected) üye işlevi tarafından en son etkilenen kayıtların sayısı belirlemek için querydef nesnesinin **yürütme** çağırın. Örneğin, `GetRecordsAffected` silinmiş, güncelleştirilmiş veya eylem sorgusu yürütürken eklenen kayıt sayısı hakkında bilgi döndürür. Döndürülen sayı cascade güncelleştirir veya sildiğinde ilgili tablolarda değişiklikleri etkindir yansıtmaz.  
  
 Her ikisi de dahil ederseniz **dbInconsistent** ve **dbConsistent** veya hiçbiri eklerseniz, sonuç varsayılan **dbInconsistent**.  
  
 **Yürütme** bir kayıt kümesi döndürmüyor. Kullanarak **yürütme** türünde bir özel durum throw MFC kayıtları seçen bir sorgu neden [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
##  <a name="getconnect"></a>CDaoQueryDef::GetConnect  
 Querydef ait veri kaynağı ile ilişkili bağlantı dizesini almak için bu üye işlevini çağırın.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) querydef için bağlantı dizesini içeren.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev yalnızca ODBC veri kaynakları ve belirli ISAM sürücüleri ile kullanılır. Microsoft Jet ile kullanılmıyor (. MDB) veritabanları; Bu durumda, `GetConnect` boş bir dize döndürür. Daha fazla bilgi için bkz: [SetConnect](#setconnect).  
  
> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen iliştirdiğiniz yoldur bir. MDB Veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.  
  
 Bağlantı dizeleri hakkında daha fazla bilgi için DAO Yardımı'nda "özellik Bağlan" konusuna bakın.  
  
##  <a name="getdatecreated"></a>CDaoQueryDef::GetDateCreated  
 QueryDefs oluşturulduğu tarihi almak için bu üye işlevini çağırın.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) querydef oluşturulduğu saat ve tarihi içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getdatelastupdated"></a>CDaoQueryDef::GetDateLastUpdated  
 QueryDefs tarih almak için bu üye işlevi en son güncelleştirilen çağrı — zaman özelliklerinden birini değiştirildi, adını, kendi SQL dizesi veya bağlantı dizesi gibi.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) querydef en son güncelleştirilen saat ve tarihi içeren bir nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlgili bilgiler için DAO Yardımı'ndaki "Notes, LastUpdated özellikleri" konusuna bakın.  
  
##  <a name="getfieldcount"></a>CDaoQueryDef::GetFieldCount  
 Sorguda alan sayısını almak için bu üye işlevini çağırın.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sorguda tanımlanan alanların sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetFieldCount`querydef tüm alanlarda döngü için yararlıdır. Bu amaçla `GetFieldCount` birlikte [GetFieldInfo](#getfieldinfo).  
  
##  <a name="getfieldinfo"></a>CDaoQueryDef::GetFieldInfo  
 Çeşitli querydef tanımlı bir alan hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 Dizine göre arama için querydef's alanlar koleksiyonu istenen alanında sıfır tabanlı dizini.  
  
 `fieldinfo`  
 Bir başvuru bir `CDaoFieldInfo` istenen bilgileri döndürür nesnesi.  
  
 `dwInfoOptions`  
 Hangi bilgilerin alınacağı alan hakkında belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, tür, boyut öznitelikleri  
  
- `AFX_DAO_SECONDARY_INFO`Birincil bilgileri artı: gerekli sıralı konumu, sıfır uzunluk izni, kaynak alanı, yabancı adı, kaynak tablo, harmanlama sırası  
  
- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgi artı: varsayılan değer, doğrulama metin doğrulama kuralı  
  
 `lpszName`  
 Ada göre arama istenen alanın adını içeren dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen bilgi açıklaması `fieldinfo`, bkz: [Cdaofieldınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Bu yapı açıklayıcı bilgileri altında karşılık üyeler içeriyor `dwInfoOptions` üstünde. Bir düzey bilgilerin isterse bilgilerini de önceki tüm düzeylerini alın.  
  
##  <a name="getname"></a>CDaoQueryDef::GetName  
 Querydef tarafından temsil edilen sorgunun adını almak için bu üye işlevini çağırın.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sorgu adı.  
  
### <a name="remarks"></a>Açıklamalar  
 QueryDef adları benzersiz kullanıcı tanımlı adlarıdır. Querydef adları hakkında daha fazla bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
##  <a name="getodbctimeout"></a>CDaoQueryDef::GetODBCTimeout  
 Bir ODBC veri kaynağı sorgusu zaman aşımına uğramadan önce geçerli zaman sınırı almak için bu üye işlevini çağırın.  
  
```  
short GetODBCTimeout();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir sorgu önce saniye sayısını zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu zaman sınırı hakkında daha fazla bilgi için DAO Yardımı'ndaki "ODBCTimeout özelliği" konusuna bakın.  
  
> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen bir Microsoft Jet eklenecek yoldur (. MDB) veritabanı. Daha fazla bilgi için "Erişim dış veritabanları ile DAO'da" DAO Yardım konusuna bakın.  
  
##  <a name="getparametercount"></a>CDaoQueryDef::GetParameterCount  
 Kaydedilen sorguda parametreler sayısını almak üzere bu üye işlevini çağırın.  
  
```  
short GetParameterCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sorguda tanımlanan parametrelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetParameterCount`Tüm parametrelerinde querydef döngü için yararlıdır. Bu amaçla `GetParameterCount` birlikte [Getparameterınfo](#getparameterinfo).  
  
 İlgili bilgi için "Parametre nesnesi", "Parametreleri toplama" ve "parametre bildirimi (SQL)" DAO Yardımı'nda konularına bakın.  
  
##  <a name="getparameterinfo"></a>CDaoQueryDef::GetParameterInfo  
 Querydef tanımlanmış bir parametre hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
```  
void GetParameterInfo(
    int nIndex,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetParameterInfo(
    LPCTSTR lpszName,  
    CDaoParameterInfo& paraminfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dizine göre arama için querydef ait parametreler koleksiyonu istenen parametresinde sıfır tabanlı dizini.  
  
 `paraminfo`  
 Bir başvuru bir [Cdaoparameterınfo](../../mfc/reference/cdaoparameterinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için parametre belirtin seçenekleri. Kullanılabilir bir seçenek ne işlevi döndürecek şekilde neden birlikte burada listelenir:  
  
- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Adı, türü  
  
 `lpszName`  
 Ada göre arama için istenen parametre adını içeren dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen bilgi açıklaması `paraminfo`, bkz: [Cdaoparameterınfo](../../mfc/reference/cdaoparameterinfo-structure.md) yapısı. Bu yapı açıklayıcı bilgileri altında karşılık üyeler içeriyor `dwInfoOptions` üstünde.  
  
 İlgili bilgiler için "PARAMETRELER bildirimi (SQL)" DAO Yardım konusuna bakın.  
  
##  <a name="getparamvalue"></a>CDaoQueryDef::GetParamValue  
 Belirtilen parametre querydef's parametreleri koleksiyonda depolanan geçerli değerini almak için bu üye işlevini çağırın.  
  
```  
virtual COleVariant GetParamValue(LPCTSTR lpszName);  
virtual COleVariant GetParamValue(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Değer ada göre arama için istediğiniz parametresinin adı.  
  
 `nIndex`  
 Dizine göre arama için querydef ait parametre koleksiyonuna parametre sıfır tabanlı dizini. Bu değeri çağrıları ile elde edebilirsiniz [GetParameterCount](#getparametercount) ve [Getparameterınfo](#getparameterinfo).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sınıfın bir nesnesi [COleVariant](../../mfc/reference/colevariant-class.md) parametrenin değeri içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre adı veya koleksiyon içindeki sıralı konumuna göre erişebilirsiniz.  
  
 İlgili bilgiler için "PARAMETRELER bildirimi (SQL)" DAO Yardım konusuna bakın.  
  
##  <a name="getrecordsaffected"></a>CDaoQueryDef::GetRecordsAffected  
 Kaç tane kayıtları son çağrı tarafından etkilendiğini belirlemek için bu üye işlevini çağırın [yürütme](#execute).  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Etkilenen kayıtların sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen sayı cascade güncelleştirir veya sildiğinde ilgili tablolarda değişiklikleri etkindir yansıtmaz.  
  
 İlgili bilgiler için DAO Yardımı'ndaki "RecordsAffected özelliği" konusuna bakın.  
  
##  <a name="getreturnsrecords"></a>CDaoQueryDef::GetReturnsRecords  
 Querydef kayıtları döndüren bir sorguya dayalı olup olmadığını belirlemek için bu üye işlevini çağırın.  
  
```  
BOOL GetReturnsRecords();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıtları döndürür querydef bir sorguyu temel alıyorsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca SQL doğrudan sorguları için kullanılır. SQL sorguları hakkında daha fazla bilgi için bkz: [yürütme](#execute) üye işlevi. SQL doğrudan sorguları ile çalışma hakkında daha fazla bilgi için bkz: [SetReturnsRecords](#setreturnsrecords) üye işlevi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "ReturnsRecords özelliğini" konusuna bakın.  
  
##  <a name="getsql"></a>CDaoQueryDef::GetSQL  
 Querydef dayandığı sorguyu tanımlayan SQL deyimini almak için bu üye işlevini çağırın.  
  
```  
CString GetSQL();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Querydef dayandığı sorguyu tanımlayan SQL deyimi.  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtar sözcükler, tablo adları ve benzeri dizesi büyük olasılıkla ayrıştırma.  
  
 İlgili bilgi için "SQL özellik", "Karşılaştırma, Microsoft Jet veritabanı altyapısı SQL ve ANSI SQL" ve "Sorgulama bir veritabanı ile SQL, kodda" DAO Yardım konularına bakın.  
  
##  <a name="gettype"></a>CDaoQueryDef::GetType  
 Querydef sorgu türünü belirlemek için bu üye işlevini çağırın.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Querydef tarafından tanımlanan sorgu türü. Açıklamalar değerleri için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Sorgu türü querydef oluşturduğunuzda veya mevcut bir querydef's çağrısı ne querydef's SQL dizesi içinde belirttiğiniz tarafından ayarlanır [SetSQL](#setsql) üye işlevi. Bu işlev tarafından döndürülen sorgu türü aşağıdaki değerlerden biri olabilir:  
  
- **dbQSelect** seçin  
  
- **dbQAction** eylem  
  
- **dbQCrosstab** çapraz  
  
- **dbQDelete** Sil  
  
- **dbQUpdate** güncelleştirme  
  
- **dbQAppend** ekleme  
  
- **dbQMakeTable** tablo yapma  
  
- **dbQDDL** veri tanımlama  
  
- **dbQSQLPassThrough** geçiş  
  
- **dbQSetOperation** birleşim  
  
- **dbQSPTBulk** ile kullanılan **dbQSQLPassThrough** kayıtları döndürmeyen bir sorgu belirtmek için.  
  
> [!NOTE]
>  SQL doğrudan sorgu oluşturmak için ayarlamazsanız **dbSQLPassThrough** sabit. QueryDefs oluşturmak ve bağlantı dizesini ayarladığınızda, bu Microsoft Jet veritabanı altyapısı tarafından otomatik olarak ayarlanır.  
  
 SQL dizeleri hakkında daha fazla bilgi için bkz: [GetSQL](#getsql). Sorgu türleri hakkında daha fazla bilgi için bkz: [yürütme](#execute).  
  
##  <a name="isopen"></a>CDaoQueryDef::IsOpen  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDaoQueryDef` nesne şu anda açık.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sıfır olmayan IF `CDaoQueryDef` nesne şu anda açık; Aksi halde 0 değil.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrılacak kullanmadan önce bir querydef açık durumda olmalıdır [yürütme](#execute) veya oluşturmak için bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi. Ya da bir querydef açık durumda çağrısı yerleştirilecek [oluşturma](#create) (için yeni bir querydef) veya [açmak](#open) (için varolan bir querydef).  
  
##  <a name="m_pdatabase"></a>CDaoQueryDef::m_pDatabase  
 Bir işaretçi içeriyor [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) querydef nesneyle ilişkili nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanına doğrudan erişmeniz gerekiyorsa bu işaretçinin kullanın — örneğin, diğer querydef veya kayıt kümesi işaretçileri almak için nesneleri veritabanının koleksiyonlarda.  
  
##  <a name="m_pdaoquerydef"></a>CDaoQueryDef::m_pDAOQueryDef  
 DAO querydef nesnesini OLE arabirimi için bir işaretçi içeriyor.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işaretçinin bütünlük ve diğer sınıflar ile tutarlılık sağlanır. MFC DAO querydefs yerine tam olarak yalıtır olduğundan, ancak, bu gereksinim düşüktür. Onu kullanmıyorsa dikkatli bunu — yapmakta olduğunuz bilmiyorsanız işaretçinin değeri özellikle, değiştirmeyin.  
  
##  <a name="open"></a>CDaoQueryDef::Open  
 Veritabanının QueryDefs koleksiyonu içinde daha önce kaydedilmiş bir querydef açmak için bu üye işlevini çağırın.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Açmak için kaydedilmiş querydef adını içeren dize. Kullanabileceğiniz bir [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Açıklamalar  
 Querydef açık olduğunda çağırabilirsiniz kendi [yürütme](#execute) üye işlevini veya kullanım querydef oluşturmak için bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi.  
  
##  <a name="setconnect"></a>CDaoQueryDef::SetConnect  
 Querydef nesnesinin bağlantı dizesini ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetConnect(LPCTSTR lpszConnect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszConnect`  
 İlişkili bir bağlantı dizesi içeren bir dize [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağlantı dizesi ODBC ve belirli ISAM sürücüleri gerektiği gibi ek bilgileri geçirmek için kullanılır. Microsoft Jet için kullanılmayan (. MDB) veritabanları.  
  
> [!TIP]
>  ODBC tabloları ile çalışmak için tercih edilen iliştirdiğiniz yoldur bir. MDB Veritabanı.  
  
 SQL doğrudan sorgu için ODBC veri kaynağını temsil eden bir querydef yürütmeden önce bağlantı dizesi ile ayarlamanız `SetConnect` ve arama [SetReturnsRecords](#setreturnsrecords) sorgu kayıtları döndürüp döndürmediğini belirtmek için.  
  
 Bağlantı dizesinin yapısı ve bağlantı dizesi bileşenlerinin örnekleri hakkında daha fazla bilgi için DAO Yardımı'nda "özellik Bağlan" konusuna bakın.  
  
##  <a name="setname"></a>CDaoQueryDef::SetName  
 Geçici olmayan bir querydef adı değiştirmek istiyorsanız, bu üye işlevini çağırın.  
  
```  
void SetName(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Kalıcı sorguda ilişkili yeni adını içeren bir dize [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 QueryDef adları benzersiz, kullanıcı tanımlı adlarıdır. Çağırabilirsiniz `SetName` önce querydef nesnesi QueryDefs koleksiyonu eklenir.  
  
##  <a name="setodbctimeout"></a>CDaoQueryDef::SetODBCTimeout  
 Bir ODBC veri kaynağı sorgusu zaman aşımına uğramadan önce zaman sınırı ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetODBCTimeout(short nODBCTimeout);
```  
  
### <a name="parameters"></a>Parametreler  
 *nODBCTimeout*  
 Bir sorgu önce saniye sayısını zaman aşımına uğradı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi bağlı veri kaynağında "zaman aşımına uğradı." sonraki işlemleri önce varsayılan saniyeyi geçersiz kılmanıza olanak tanır Bir işlem ağ erişim sorunları, aşırı sorgu işleme süresini ve benzeri nedeniyle zaman. Çağrı `SetODBCTimeout` sorgu zaman aşımı değeri değiştirmek istiyorsanız bu querydef ile bir sorguyu çalıştırmadan önce. (ODBC bağlantıları yeniden kullanır, zaman aşımı değeri aynı bağlantı üzerinde tüm istemciler için aynıdır.)  
  
 Sorgu zaman aşımı için varsayılan değer 60 saniyedir.  
  
##  <a name="setparamvalue"></a>CDaoQueryDef::SetParamValue  
 Çalışma zamanında querydef bir parametrenin değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
virtual void SetParamValue(
    LPCTSTR lpszName,  
    const COleVariant& varValue);

 
virtual void SetParamValue(
    int nIndex,  
    const COleVariant& varValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Değer ayarlamak istediğiniz parametresinin adı.  
  
 `varValue`  
 Ayarlanacak değer; Açıklamalar bakın.  
  
 `nIndex`  
 Sıralı konumu parametresi querydef ait parametreler koleksiyonu. Bu değeri çağrıları ile elde edebilirsiniz [GetParameterCount](#getparametercount) ve [Getparameterınfo](#getparameterinfo).  
  
### <a name="remarks"></a>Açıklamalar  
 Parametre zaten querydef's SQL dizesi bir parçası olarak kurulmuş gerekir. Parametre adı veya koleksiyon içindeki sıralı konumuna göre erişebilirsiniz.  
  
 Olarak ayarlanacak değer belirtmek bir `COleVariant` nesnesi. İstenen değeri ve türü ayarlama hakkında bilgi için `COleVariant` nesne, sınıfına bakın [COleVariant](../../mfc/reference/colevariant-class.md).  
  
##  <a name="setreturnsrecords"></a>CDaoQueryDef::SetReturnsRecords  
 Dış veritabanı için SQL doğrudan sorgu ayarlama işleminin bir parçası olarak bu üye işlevini çağırın.  
  
```  
void SetReturnsRecords(BOOL bReturnsRecords);
```  
  
### <a name="parameters"></a>Parametreler  
 *bReturnsRecords*  
 Geçirmek **TRUE** dış veritabanı üzerindeki sorgu kayıtları; döndürürse, aksi takdirde, **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Böyle bir durumda querydef oluşturmalı ve diğer kullanarak özelliklerini ayarlamak `CDaoQueryDef` üye işlevleri. Dış veritabanlarını açıklaması için bkz: [SetConnect](#setconnect).  
  
##  <a name="setsql"></a>CDaoQueryDef::SetSQL  
 Querydef yürüten SQL deyimini ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszSQL`  
 Yürütme için uygun, tam bir SQL deyimi içeren bir dize. Bu dizesinin söz dizimi üzerinde DBMS bağlıdır, sorgu hedefler. Microsoft Jet Veritabanı Altyapısı'nda kullanılan sözdizimi bir tartışma için "Yapı SQL deyimleri içinde kodu" DAO Yardım konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Tipik bir kullanımını `SetSQL` QueryDefs SQL doğrudan sorgu kullanmak için yukarı ayardır. (SQL doğrudan sorguları, hedefte DBMS sözdizimi, DBMS belgelerine bakın.)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoException sınıfı](../../mfc/reference/cdaoexception-class.md)
