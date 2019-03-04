---
title: CDaoWorkspace sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
ms.openlocfilehash: 6aa404c5eb543db198043dba68d55a4b925739c8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57263461"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace sınıfı

Adlandırılmış, parola korumalı veritabanı oturumunu, tek bir kullanıcı tarafından oturum kapatma için oturum açma işlemi yönetir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Bir çalışma nesnesi oluşturur. Daha sonra arama `Create` veya `Open`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace::Append](#append)|Yeni oluşturulan bir çalışma alanı veritabanı altyapısının çalışma alanları koleksiyonuna ekler.|
|[CDaoWorkspace::BeginTrans](#begintrans)|Tüm veritabanlarının açık çalışma öğesine uygulanan yeni bir işlem başlar.|
|[CDaoWorkspace::Close](#close)|Çalışma alanı ve içerdiği nesnelerin tümünü kapatır. İşlemler geri alınacak.|
|[CDaoWorkspace::CommitTrans](#committrans)|Geçerli işlem tamamlanır ve değişiklikleri kaydeder.|
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|Bir veritabanı sıkıştırır (veya yineleme).|
|[CDaoWorkspace::Create](#create)|Yeni bir DAO çalışma nesnesi oluşturur.|
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Çalışma alanınızın veritabanları koleksiyondaki DAO veritabanı nesne sayısını döndürür.|
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Çalışma alanınızın veritabanları koleksiyonunda tanımlı belirtilen bir DAO veritabanı hakkındaki bilgileri döndürür.|
|[CDaoWorkspace::GetIniPath](#getinipath)|Microsoft Jet veritabanı konumunu Windows kayıt defterinde altyapısının başlatma ayarlarını döndürür.|
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Veri kaynağı için birden çok bağlantı zorla aynı ODBC veri kaynağını içeren birden çok işlem aracılığıyla yalıtılmış olup olmadığını gösteren bir değer döndürür.|
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Kullanıcı bir ODBC veritabanı için oturum açma girişiminde bulunduğunda bir hata gerçekleşmeden önce saniye sayısını döndürür.|
|[CDaoWorkspace::GetName](#getname)|Çalışma alanı nesnesi kullanıcı tanımlı adını döndürür.|
|[CDaoWorkspace::GetUserName](#getusername)|Çalışma alanı oluşturulduğu zaman belirtilen kullanıcı adı döndürür. Bu çalışma alanı sahibi adıdır.|
|[CDaoWorkspace::GetVersion](#getversion)|Çalışma alanı ile ilişkili veritabanı altyapısı sürümünü içeren bir dize döndürür.|
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|DAO çalışma nesnelerin sayısı, veritabanı altyapısının içinde çalışma alanları koleksiyonu döndürür.|
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Veritabanı altyapısının çalışma alanları koleksiyonunda tanımlı belirtilen bir DAO çalışma alanı hakkında bilgi döndürür.|
|[CDaoWorkspace::Idle](#idle)|Arka plan görevleri gerçekleştirmek veritabanı altyapısı sağlar.|
|[CDaoWorkspace::IsOpen](#isopen)|Çalışma alanı ise sıfır olmayan döndürür açın.|
|[CDaoWorkspace::Open](#open)|Açıkça DAO'ın varsayılan çalışma alanı ile ilişkili bir çalışma alanı nesnesini açar.|
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Bozuk bir veritabanı onarmaya çalışır.|
|[CDaoWorkspace::Rollback](#rollback)|Geçerli işlemi sonlandırır ve değişiklikleri kaydetmez.|
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Veritabanı altyapısı belirli bir parola bir çalışma nesnesi oluşturulduğunda kullandığı parolayı ayarlar.|
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Belirli bir kullanıcı adı bir çalışma nesnesi oluşturulduğunda, veritabanı motorunu kullanır kullanıcı adını ayarlar.|
|[CDaoWorkspace::SetIniPath](#setinipath)|Microsoft Jet veritabanı konumunu Windows kayıt defterinde altyapısının başlatma ayarları ayarlar.|
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlem birden fazla veri kaynağı bağlantı zorlayarak yalıtılmış olup olmadığını belirtir.|
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Kullanıcı bir ODBC veri kaynağında oturum çalıştığında bir hata gerçekleşmeden önce saniye sayısını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|DAO çalışma alanı nesnesini işaret eder.|

## <a name="remarks"></a>Açıklamalar

Çoğu durumda, birden çok çalışma alanı gerekli değildir ve açık bir çalışma alanı nesneleri oluşturma gerekmez; Veritabanı ve kayıt nesneleri açtığınızda, bunlar DAO'ın varsayılan çalışma alanı kullanır. Ancak, gerekirse, birden çok oturumu aynı anda ek çalışma alanı nesnelerini oluşturarak çalıştırabilirsiniz. Her çalışma alanı nesnesi, kendi veritabanı koleksiyonu içindeki birden çok açık veritabanı nesnelerini içerebilir. MFC'de, öncelikle bir işlem yöneticisi, açık bir veritabanları kümesi tümü aynı "işlem alanı" belirten bir çalışma alanıdır.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekine sahiptir. Genel olarak, üzerinde DAO göre MFC ODBC tabanlı MFC sınıfları daha yetenekli sınıflardır. DAO dayalı sınıflar ODBC sürücüleri dahil olmak üzere Microsoft Jet veritabanı altyapısı verilere sahiptir. Bunlar ayrıca veritabanları oluşturma ve DAO doğrudan çağırmak zorunda kalmadan, tablolar ve alanlar aracılığıyla sınıfları ekleme gibi veri tanımlama dili (DDL) işlemleri destekler.

## <a name="capabilities"></a>Özellikler

Sınıf `CDaoWorkspace` şunları sağlar:

- Gerekirse veritabanı motoru başlatma tarafından oluşturulan bir varsayılan çalışma alanına açık erişim. Genellikle, DAO'ın varsayılan çalışma alanını örtük olarak veritabanı ve kayıt nesneleri oluşturarak kullanın.

- İşlem tüm veritabanları için geçerli bir işlem alanı çalışma alanında açın. Ayrı bir işlem alanları yönetmek için ek bir çalışma alanı oluşturabilirsiniz.

- Temel alınan Microsoft Jet Veritabanı Altyapısı'nın birçok özelliği için bir arabirim (statik üye işlevleri bakın). Açma veya bir çalışma alanı oluşturma veya önce bir statik üye işlevini çağırarak açın veya oluşturun, Veritabanı Altyapısı'nı başlatır.

- Erişim için eklenmiş tüm etkin çalışma alanlarını depolar veritabanı altyapısının çalışma alanları koleksiyonu. Ayrıca, oluşturabilir ve koleksiyona ekleme olmadan çalışma alanlarıyla çalışma.

## <a name="security"></a>Güvenlik

MFC kullanıcılar ve gruplar koleksiyonlar için güvenlik denetimi tarafından kullanılan DAO uygulamıyor. DAO yönlerini gerekirse bunları kendiniz DAO arabirimleri doğrudan çağrılar aracılığıyla program gerekir. Bilgi için [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="usage"></a>Kullanım

Sınıf kullanabileceğiniz `CDaoWorkspace` için:

- Açıkça varsayılan çalışma alanını açın.

   Varsayılan çalışma alanı kullanımınızı genellikle örtük olarak — yeni açtığınızda [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri. Ancak açıkça erişim gerekebilir; örneğin, access veritabanı altyapısı özellikleri veya çalışma alanı koleksiyonu için. Aşağıdaki "Örtülü varsayılan çalışma alanı kullanımı" bölümüne bakın.

- Yeni çalışma alanları oluşturun. Çağrı [ekleme](#append) çalışma alanları koleksiyona eklemek istiyorsanız.

- Çalışma alanları koleksiyonunda mevcut bir çalışma alanını açın.

Yeni bir çalışma alanı oluşturma zaten varolmadığından koleksiyondur altında açıklandığı gibi çalışma alanlarında [Oluştur](#create) üye işlevi. Çalışma alanı nesnelerini datababase altyapısı oturumları arasında herhangi bir şekilde devam etmez. Uygulamanız MFC statik olarak bağlanıyorsa, veritabanı altyapısı uygulama bitiş başlamasını iptal eder. Uygulamanız MFC ile dinamik olarak bağlanıyorsa, MFC DLL kaldırıldığında, veritabanı altyapısı başlatılmamış.

Açıkça varsayılan çalışma alanını açma veya çalışma alanları koleksiyonunda mevcut bir çalışma alanını açma altında açıklanmıştır [açık](#open) üye işlevi.

Çalışma alanı ile kapatarak bir çalışma alanı oturumunu [Kapat](#close) üye işlevi. `Close` tüm veritabanları, daha önce kaydedilmemiş işlemler geri kapatılmamış kapatır.

## <a name="transactions"></a>İşlemler

DAO çalışma alanı düzeyinde işlemler yönetir; Bu nedenle, işlem bir çalışma alanında açık olan birden fazla veritabanıyla tüm veritabanları için geçerlidir. Örneğin, iki veritabanları olan kaydedilmemiş güncelleştirmeleri ve çağırmaya [CommitTrans](#committrans), tüm güncelleştirmeleri kararlıyız. Tek bir veritabanı işlemleri sınırlandırmak istiyorsanız, ayrı bir çalışma nesnesi için ihtiyacınız.

## <a name="implicit-use-of-the-default-workspace"></a>Örtülü varsayılan çalışma alanı kullanımı

MFC DAO'ın varsayılan çalışma alanı aşağıdaki koşullarda örtük olarak kullanır:

- Yeni bir oluşturursanız `CDaoDatabase` nesnesi ancak bunu varolan aracılığıyla yapmayın `CDaoWorkspace` MFC oluşturur bir geçici çalışma alanı nesnesi, DAO'ın varsayılan çalışma alanına karşılık gelen nesne. Birden fazla veritabanı için bunu yaparsanız, tüm veritabanı nesnelerinin varsayılan çalışma alanıyla ilişkilendirilir. Bir veritabanının çalışma alanını kullanarak erişebileceğiniz bir `CDaoDatabase` veri üyesi.

- Benzer şekilde, oluşturursanız, bir `CDaoRecordset` nesne işaretçisi sağlama olmadan bir `CDaoDatabase` nesnesi, MFC, bir geçici veritabanı nesnesi oluşturur ve uzantısı, bir geçici çalışma alanı nesnesi. Bir kayıt kümesinin veritabanı ve dolaylı olarak kendi çalışma alanı üzerinden erişebilirsiniz bir `CDaoRecordset` veri üyesi.

## <a name="other-operations"></a>Diğer işlemler

Bozuk bir veritabanını onararak veya bir veritabanı sıkıştırma gibi diğer veritabanı işlemleri de sağlanır.

Ve DAO güvenlik DAO'yu doğrudan çağırma hakkında bilgi için bkz [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="append"></a>  CDaoWorkspace::Append

Çağırdıktan sonra bu üye işlevi çağrısı [Oluştur](#create).

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append` Yeni oluşturulan çalışma nesnesi veritabanı altyapısının çalışma alanları koleksiyonuna ekler. Çalışma alanı veritabanı altyapısı oturumları arasında kalmaz; Bunlar, bellek, disk üzerinde değil, yalnızca depolanır. Bir çalışma alanı eklemek izniniz yok; Bunu yapmazsanız, yine de kullanabilirsiniz.

Açık duruma çağırmanızı kadar çalışma alanları koleksiyonundaki etkin bir eklenmiş bir çalışma alanında kalır, [Kapat](#close) üye işlevi.

İlgili bilgiler için DAO Yardımı'nda "yöntemi ekleme" konusuna bakın.

##  <a name="begintrans"></a>  CDaoWorkspace::BeginTrans

Bir işlem başlatmak için bu üye işlevini çağırın.

```
void BeginTrans();
```

### <a name="remarks"></a>Açıklamalar

Çağırdıktan sonra `BeginTrans`, işlem taahhüt verdiğinizde, verileri veya veritabanı yapısına yaptığınız güncelleştirmeler etkili. Çalışma alanı tek bir işlem alanı tanımladığından, işlem çalışma alanındaki tüm açık veritabanları için geçerlidir. İşlemi tamamlamak için iki yolu vardır:

- Çağrı [CommitTrans](#committrans) hareketi tamamlamak ve değişiklikleri veri kaynağına kaydetmek için üye işlevi.

- Veya çağrı [geri alma](#rollback) işlemi iptal üye işlevi.

Çalışma alanı nesnesi veya bir veritabanı nesnesi bir işlem beklenirken Kapatma tüm bekleyen işlemleri geri alır.

İşlemler bu başka bir ODBC veri kaynağı bir ODBC veri kaynağında yalıtmanız gerekiyorsa, bkz. [SetIsolateODBCTrans](#setisolateodbctrans) üye işlevi.

##  <a name="cdaoworkspace"></a>  CDaoWorkspace::CDaoWorkspace

Oluşturur bir `CDaoWorkspace` nesne.

```
CDaoWorkspace();
```

### <a name="remarks"></a>Açıklamalar

C++ nesnesini oluşturduktan sonra iki seçeneğiniz vardır:

- Nesnenin [açın](#open) üye işlevini varsayılan çalışma alanını açın veya varolan bir nesneye çalışma alanı koleksiyonu.

- Veya nesnenin [Oluştur](#create) DAO yeni bir çalışma alanı nesnesi oluşturmak için üye işlevi. Bu açıkça aracılığıyla başvurabilirsiniz yeni bir çalışma alanı oturumu başlatır `CDaoWorkspace` nesne. Arama sonra `Create`, çağırabilirsiniz [ekleme](#append) çalışma alanı veritabanı altyapısının çalışma alanları koleksiyona eklemek istiyorsanız.

Sınıfına genel bakış için bkz. [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) açıkça oluşturmanız gerektiğinde hakkında bilgi için bir `CDaoWorkspace` nesne. Açtığınızda örtük olarak oluşturulan çalışma alanları genellikle, kullandığınız bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne açtığınızda veya bir çalışma alanı belirtmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) bir veritabanı nesnesi belirtmeden nesne. Bu şekilde oluşturulan MFC DAO nesneler oluşturulduktan ve yeniden DAO'ın varsayılan çalışma kullanın.

Bir çalışma alanı ve içerdiği nesneler serbest bırakmak için çalışma alanı nesnenin çağrı [Kapat](#close) üye işlevi.

##  <a name="close"></a>  CDaoWorkspace::Close

Çalışma alanı nesnesi kapatmak için bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Bir açık çalışma nesnesi kapatma DAO nesnesini serbest bırakır ve çalışma alanının çalışma alanı koleksiyonunun bir üyesi ise koleksiyondan kaldırır. Çağırma `Close` alışkanlıktır.

> [!CAUTION]
>  Bir çalışma nesnesi kapatma çalışma alanında açık herhangi bir veritabanına kapatır. Hiçbir kayıt kümeleri açık de kapalı veritabanlarındaki sonuçlanır ve herhangi bir bekleyen düzenlemeler veya güncelleştirmeleri geri alınır. İlgili bilgiler için bkz. [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), ve [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) üye işlevleri.

Çalışma alanı nesnelerini kalıcı değildir; bunların yalnızca başvuruları bunları varken mevcut. Bu, veritabanı altyapısı oturumu sona erdiğinde, çalışma ve kendi veritabanı koleksiyonu kalıcı olduğunu anlamına gelir. Bunları sonraki oturum için çalışma alanı ve veritabanları yeniden açarak yeniden oluşturmanız gerekir.

İlgili bilgiler için "Kapat yöntemi" DAO Yardım konusuna bakın.

##  <a name="committrans"></a>  CDaoWorkspace::CommitTrans

Bir hareketi tamamlamak için bu üye işlevini çağırın; bir grubu düzenleme ve güncelleştirmeleri çalışma alanında bir veya daha fazla veritabanı kaydedin.

```
void CommitTrans();
```

### <a name="remarks"></a>Açıklamalar

Veritabanı veri veya çağrı başlayarak yapısını değişiklikleri bir dizi işlem oluşan [BeginTrans](#begintrans). İşlem tamamlandığında veya geri alma ya da işleme (değişiklikleri iptal et) ile [geri alma](#rollback). Varsayılan olarak, işlem olmadan kayıtlara güncelleştirmeleri hemen kararlıyız. Çağırma `BeginTrans` , çağırana kadar Gecikmeli taahhüdünün güncelleştirmelerin neden `CommitTrans`.

> [!CAUTION]
>  Bir çalışma alanındaki işlemler her zaman çalışma alanına genel ve yalnızca bir veritabanı ya da kayıt sınırlı değildir. Birden fazla veritabanı ya da bir çalışma alanı işlem içinde kayıt işlemleri gerçekleştirirseniz `CommitTrans` tüm bekleyen güncelleştirmeleri, işlemeler ve `Rollback` bu veritabanları ve kayıt kümeleri üzerindeki tüm işlemler geri yükler.

İşlemler veritabanı veya bekleyen işlemler çalışma alanıyla kapattığınızda, tüm geri alınır.

> [!NOTE]
>  Bu iki aşamalı tamamlama mekanizması değildir. Kaydetmek bir güncelleştirme başarısız olursa, diğerleri hala işleme.

##  <a name="compactdatabase"></a>  CDaoWorkspace::CompactDatabase

Belirtilen bir Microsoft Jet sıkıştırmak için bu üye işlevini çağırın (. MDB) veritabanı.

```
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale = dbLangGeneral,
    int nOptions = 0);

static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,
    LPCTSTR lpszDestName,
    LPCTSTR lpszLocale,
    int nOptions,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszSrcName*<br/>
Mevcut bir adı, veritabanı kapalı. Bu tam yol ve dosya, aşağıdaki gibi olabilir "C:\\\MYDB. MDB". Dosya adı uzantısı varsa, bunu belirtmeniz gerekir. Ağınızı Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, yol dizelerde gereklidir, çünkü "\\" C++ kaçış karakteri olan.)

*lpszDestName*<br/>
Oluşturmakta olduğunuz sıkıştırılmış veritabanı tam yolu. İle bir ağ yolu olarak belirtebilirsiniz *lpszSrcName*. Kullanamazsınız *lpszDestName* bağımsız olarak aynı veritabanı dosyasını belirtmek için *lpszSrcName*.

*lpszPassword*<br/>
Parola korumalı bir veritabanını istediğinizde kullanılan parola. Sürümünü kullanıyorsanız, Not `CompactDatabase` almayan bir parola, tüm parametreleri sağlamanız gerekir. Bu bağlantı parametresi olduğundan, ayrıca, özel, aşağıdaki şekilde biçimlendirme gerektiriyor:; PWD = *lpszPassword*. Örneğin:; PWD "Mutlu" =. (Başında noktalı virgül gereklidir.)

*lpszLocale*<br/>
Oluşturmak için harmanlama sırası belirtmek için kullanılan bir dize ifadesi *lpszDestName*. Bu bağımsız değişken varsayılan değerini kabul ederek atlarsanız, `dbLangGeneral` (aşağıya bakın), yeni veritabanının yerel eski veritabanının aynıdır. Olası değerler şunlardır:

- `dbLangGeneral` İspanyolca, İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern

- `dbLangArabic` Arapça

- `dbLangCyrillic` Rusça

- `dbLangCzech` Çekçe

- `dbLangDutch` Hollanda dili

- `dbLangGreek` Yunanca

- `dbLangHebrew` İbranice

- `dbLangHungarian` Macarca

- `dbLangIcelandic` İzlanda dili

- `dbLangNordic` Kuzey Dilleri (yalnızca Microsoft Jet veritabanı motoru sürüm 1.0)

- `dbLangNorwdan` Norveççe ve Danca

- `dbLangPolish` Lehçe

- `dbLangSpanish` Geleneksel İspanyolca

- `dbLangSwedfin` İsveç dili ve Fince

- `dbLangTurkish` Türkçe

*nOptions*<br/>
Hedef veritabanı için bir veya daha fazla seçeneklerini gösteren *lpszDestName*. Bu bağımsız değişken atlarsanız varsayılan değeri kabul ederek *lpszDestName* aynı şifreleme ve aynı sürüme *lpszSrcName*. Birleştirebilirsiniz `dbEncrypt` veya `dbDecrypt` bit düzeyinde OR işlecini kullanarak sürüm seçeneklerden biriyle seçeneği. Bir veritabanı altyapısı sürümünü değil, bir veritabanı biçimi belirtin. olası değerler şunlardır:

- `dbEncrypt` Sıkıştırma sırasında veritabanı şifreleyin.

- `dbDecrypt` Veritabanı sıkıştırılırken şifresini çözemez.

- `dbVersion10` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.0 kullanan bir veritabanı oluşturun.

- `dbVersion11` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.1 kullanan bir veritabanı oluşturun.

- `dbVersion20` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 2.0 kullanan bir veritabanı oluşturun.

- `dbVersion30` Sıkıştırma sırasında Microsoft Jet veritabanı motoru sürüm 3.0 kullanan bir veritabanı oluşturun.

Kullanabileceğiniz `dbEncrypt` veya `dbDecrypt` seçenekleri değişkenindeki şifrelemek veya düzenlenmiş gibi veritabanı şifresini çözmek için etkinleştirilip etkinleştirilmeyeceğini belirtin. Bir şifreleme sabiti atlarsanız veya her ikisi de dahil ederseniz `dbDecrypt` ve `dbEncrypt`, *lpszDestName* aynı şifrelemeye olacaktır *lpszSrcName*. Sıkıştırılmış veritabanı için veri biçimi sürümü belirtmek için Seçenekler bağımsız değişkeninde sürüm sabitlerinden birini kullanabilirsiniz. Yalnızca veri biçimi sürümü bu sabiti etkiler *lpszDestName*. Yalnızca bir sürümü sabiti belirtebilirsiniz. Bir sürüm sabit atlarsanız *lpszDestName* aynı sürüme sahip olur *lpszSrcName*. Sıkıştırma *lpszDestName* aynı olan bir sürüme veya daha yeni *lpszSrcName*.

> [!CAUTION]
>  Bir veritabanı şifreli değilse, kullanıcı/parola güvenlik, doğrudan veritabanı oluşturan ikili disk dosyası okuma için bile uygularsanız, mümkündür.

### <a name="remarks"></a>Açıklamalar

Veritabanı içindeki veriler değiştikçe, veritabanı dosyası parçalanabilir ve gerekirse daha fazla disk alanı kullanın. Düzenli olarak veritabanınızın veritabanı dosyasını birleştirmek üzere sıkıştırmanız gerekir. Sıkıştırılmış veritabanı genellikle daha küçüktür. Harmanlama sırası, şifreleme veya veri biçimi sürümü kopyalayın ve veritabanını değiştirmek seçebilirsiniz.

> [!CAUTION]
>  `CompactDatabase` Üye işlevi tarafından değil doğru şekilde dönüştürülür tam bir Microsoft Access veritabanına bir sürümden diğerine. Yalnızca veri biçimi dönüştürülür. Microsoft Access tanımlı nesneler, formlar ve raporlar gibi dönüştürülmez. Ancak, verileri doğru şekilde dönüştürülür.

> [!TIP]
>  Ayrıca `CompactDatabase` veritabanı dosyasını kopyalamak için.

Sıkıştırma veritabanları hakkında daha fazla bilgi için DAO Yardımı'nda "CompactDatabase yöntemi" konusuna bakın.

##  <a name="create"></a>  CDaoWorkspace::Create

Yeni bir DAO çalışma nesnesi oluşturun ve MFC ile ilişkilendirmek için bu üye işlevini çağırın `CDaoWorkspace` nesne.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Yeni çalışma alanı nesnesi adlandıran 14 adede kadar karakter içeren bir dize. Bir ad sağlamanız gerekir. İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

*lpszUserName*<br/>
Çalışma alanının sahibi kullanıcı adı. Gereksinimleri için bkz *lpszDefaultUser* parametresi [SetDefaultUser](#setdefaultuser) üye işlevi. İlgili bilgiler için DAO Yardımı'nda "UserName özelliği" konusuna bakın.

*lpszPassword*<br/>
Yeni çalışma alanı nesnesi parolası. Parola 14 adede kadar karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içermelidir. Parolalar büyük/küçük harfe duyarlıdır. İlgili bilgiler için DAO Yardımı'nda "Password özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Genel oluşturma işlemi şöyledir:

1. Oluşturmak bir [CDaoWorkspace](#cdaoworkspace) nesne.

1. Nesnenin `Create` temel DAO çalışma alanı oluşturmak için üye işlevi. Bir çalışma alanı adı belirtmeniz gerekir.

1. İsteğe bağlı olarak çağrı [ekleme](#append) çalışma alanı veritabanı altyapısının çalışma alanları koleksiyona eklemek istiyorsanız. Ekleme olmadan, çalışma alanı ile çalışabilirsiniz.

Sonra `Create` , çalışma alanı nesnesi çağrıdır kullanıma hazır bir açık durumda. Çağrılmayan `Open` sonra `Create`. Çağrılmayan `Create` çalışma alanının çalışma alanı koleksiyonda zaten varsa. `Create` Bunu zaten uygulamanız için başlatılmadı, veritabanı altyapısı başlatır.

##  <a name="getdatabasecount"></a>  CDaoWorkspace::GetDatabaseCount

Çalışma alanınızın veritabanı koleksiyonu içindeki DAO veritabanı nesne sayısını almak için bu üye işlevi çağrısı — açık veritabanı çalışma sayısı.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanında açık veritabanı sayısı.

### <a name="remarks"></a>Açıklamalar

`GetDatabaseCount` Çalışma alanınızın veritabanı koleksiyonu içindeki tüm tanımlı veritabanlarına döngü istiyorsanız kullanışlıdır. Bir koleksiyondaki belirli bir veritabanı hakkında bilgi edinmek için bkz: [GetDatabaseInfo](#getdatabaseinfo). Tipik kullanım çağırmaktır `GetDatabaseCount` açık veritabanı için ardından bu sayıyı bir döngü dizini yinelenen çağrılar için kullanma `GetDatabaseInfo`.

##  <a name="getdatabaseinfo"></a>  CDaoWorkspace::GetDatabaseInfo

Çeşitli türlerdeki bir veritabanı açık çalışma hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetDatabaseInfo(
    int nIndex,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetDatabaseInfo(
    LPCTSTR lpszName,
    CDaoDatabaseInfo& dbinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizine göre arama için çalışma alanınızın veritabanları koleksiyonunun veritabanı nesnesi sıfır tabanlı dizini.

*dbinfo*<br/>
Bir başvuru bir [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Alınacak veritabanıyla ilgili bilgileri belirtmenize seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların döndüren işlev neden yanı sıra aşağıda listelenmiştir:

- (Varsayılan) AFX_DAO_PRIMARY_INFO adı, güncelleştirilebilir, işlemleri

- Artı AFX_DAO_SECONDARY_INFO birincil bilgileri: Sorgu zaman aşımı harmanlama sırası, sürüm

- AFX_DAO_ALL_INFO birincil ve ikincil bilgi artı: Bağlanma

*lpszName*<br/>
Ada göre arama veritabanı nesnesinin adı. Yeni çalışma alanı nesnesi adlandıran bir 14 adede kadar karakter dizesiyle addır.

### <a name="remarks"></a>Açıklamalar

Bir veritabanını dizine göre ara işlevin bir sürümünü sağlar. Başka bir sürüm, bir veritabanı adına göre aramak sağlar.

Döndürülen bilgilerin açıklamasını *dbinfo*, bkz: [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediğinizde de önceki tüm düzeylerde hakkında bilgi alın.

##  <a name="getinipath"></a>  CDaoWorkspace::GetIniPath

Windows kayıt defterinde altyapısının başlatma ayarları Microsoft Jet veritabanı konumunu almak için bu üye işlevini çağırın.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) içeren kayıt defteri konumu.

### <a name="remarks"></a>Açıklamalar

Veritabanı Altyapısı için ayarları hakkında bilgi edinmek için konumu kullanabilirsiniz. Döndürülen bilgileri aslında bir kayıt defteri alt anahtarı adıdır.

İlgili bilgiler için "Özelliğini Registry'nin" ve "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konularına bakın.

##  <a name="getisolateodbctrans"></a>  CDaoWorkspace::GetIsolateODBCTrans

Çalışma alanı için DAO IsolateODBCTrans özelliğinin geçerli değeri almak için bu üye işlevini çağırın.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC işlemleri yalıtılmış olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Her bir çalışma alanı veritabanı kendi ODBC bağlantısı olabilse de, bu sistem performansı yavaşlattığını göz önünde bulundurun. İşlem yalıtım normalde gerekli olmadığından, aynı kullanıcı tarafından açıldığında birden çok çalışma alanı nesnelerden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları tek bir bağlantı üzerinde eşzamanlı işlemlere izin vermez. Böyle bir veritabanında bir zamanda birden fazla işlem değiştirilmesi gerekiyorsa, açıldıktan hemen sonra IsolateODBCTrans özelliği her bir çalışma alanı true. Bu, her çalışma alanı için ayrı bir ODBC bağlantı zorlar.

İlgili bilgiler için DAO Yardımı'nda "IsolateODBCTrans özelliği" konusuna bakın.

##  <a name="getlogintimeout"></a>  CDaoWorkspace::GetLoginTimeout

Çalışma alanı için DAO LoginTimeout özelliğinin geçerli değeri almak için bu üye işlevini çağırın.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ODBC Veritabanı'nda oturum açmaya çalıştığında bir hata gerçekleşmeden önce saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer bir ODBC Veritabanı'nda oturum açmaya çalıştığında bir hata gerçekleşmeden önce saniye sayısını temsil eder. Varsayılan LoginTimeout 20 saniyedir. LoginTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı oluşur ve veri kaynağı ile iletişimi yanıt vermeyebilir.

Oturumu açmak için Microsoft SQL Server gibi bir ODBC veritabanı çalışırken bağlantı, ağ hataları nedeniyle başarısız olabilir veya sunucusu çalışmıyor. Bağlanmak için 20 saniye için varsayılan beklemek yerine bir hata oluşturur önce veritabanı altyapısı bekleyeceği süreyi belirtebilirsiniz. Sunucuda oturum açmayı örtük olarak bir dış sunucu veritabanında sorgu çalıştırma gibi farklı olayların bir sayının parçası olarak gerçekleşir.

İlgili bilgiler için DAO Yardımı'nda "LoginTimeout özelliği" konusuna bakın.

##  <a name="getname"></a>  CDaoWorkspace::GetName

DAO çalışma temel nesne kullanıcı tanımlı adını almak için bu üye işlevi çağrısı `CDaoWorkspace` nesne.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO çalışma alanı nesnesi kullanıcı tanımlı adını içeren.

### <a name="remarks"></a>Açıklamalar

Adı, veritabanı altyapısının çalışma alanları koleksiyonu DAO çalışma nesnesinde adıyla erişmek için yararlıdır.

İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

##  <a name="getusername"></a>  CDaoWorkspace::GetUserName

Çalışma alanının sahibinin adını almak için bu üye işlevini çağırın.

```
CString GetUserName();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) çalışma nesnenin sahibi, temsil eder.

### <a name="remarks"></a>Açıklamalar

Almak veya çalışma alanı sahibi izinlerini ayarlamak için doğrudan izinleri özelliği ayarı denetlemek için DAO çağırın. Bu izinleri belirler, kullanıcının sahip. İzinleri ile çalışmak için bir sistem gerekir. MDA dosyası.

DAO çağırma hakkında bilgi için doğrudan bkz [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). İlgili bilgiler için DAO Yardımı'nda "UserName özelliği" konusuna bakın.

##  <a name="getversion"></a>  CDaoWorkspace::GetVersion

Kullanımdaki Microsoft Jet veritabanı altyapısı sürümünü belirlemek için bu üye işlevini çağırın.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesneyle ilişkili veritabanı altyapısı sürümünü gösterir.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer "AnaSürüm.altsürüm"; biçiminde sürüm numarasını temsil eder. Örneğin, "3.0". Ürün sürüm numarasını (örneğin, 3.0), sürüm numarası (3), nokta ve sürüm numarasını (0) oluşur.

İlgili bilgiler için DAO Yardımı'nda "Version özelliği" konusuna bakın.

##  <a name="getworkspacecount"></a>  CDaoWorkspace::GetWorkspaceCount

DAO veritabanı altyapısının çalışma alanları koleksiyonu çalışma alanı nesneleri sayısını almak için bu üye işlevini çağırın.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı koleksiyonu içindeki açık çalışma alanlarının sayısını.

### <a name="remarks"></a>Açıklamalar

Bu sayı, koleksiyona eklenmemiş açık çalışma alanları içermez. `GetWorkspaceCount` çalışma alanları koleksiyonunda tanımlanan tüm çalışma alanları arasında döngü istiyorsanız kullanışlıdır. Bir koleksiyondaki belirli bir çalışma alanı hakkında bilgi edinmek için bkz: [GetWorkspaceInfo](#getworkspaceinfo). Tipik kullanım çağırmaktır `GetWorkspaceCount` açık çalışma alanı sayısı için ardından bu sayıyı bir döngü dizini yinelenen çağrılar için kullanmak `GetWorkspaceInfo`.

##  <a name="getworkspaceinfo"></a>  CDaoWorkspace::GetWorkspaceInfo

Çeşitli oturumunda bir çalışma alanı açık hakkında bilgi edinmek için bu üye işlevini çağırın.

```
void GetWorkspaceInfo(
    int nIndex,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetWorkspaceInfo(
    LPCTSTR lpszName,
    CDaoWorkspaceInfo& wkspcinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Dizine göre arama, çalışma alanları koleksiyondaki veritabanı nesnesi sıfır tabanlı dizini.

*wkspcinfo*<br/>
Bir başvuru bir [Cdaoworkspaceınfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) nesnesini istenen bilgileri döndürür.

*dwInfoOptions*<br/>
Seçenekler hangi almak için çalışma alanı bilgilerini belirtin. Kullanılabilir seçenekler, hangi kullanıcıların döndüren işlev neden yanı sıra aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) adı

- Artı AFX_DAO_SECONDARY_INFO birincil bilgileri: Kullanıcı adı

- AFX_DAO_ALL_INFO birincil ve ikincil bilgi artı: ODBCTrans Ayır

*lpszName*<br/>
Ada göre arama çalışma nesnesinin adı. Yeni çalışma alanı nesnesi adlandıran bir 14 adede kadar karakter dizesiyle addır.

### <a name="remarks"></a>Açıklamalar

Döndürülen bilgilerin açıklamasını *wkspcinfo*, bkz: [Cdaoworkspaceınfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) yapısı. Bilgi açıklamasındaki yukarıda listelenen öğelerin karşılık gelen üyeleri bu yapıya sahip *dwInfoOptions*. Bir düzeyde bilgi istediklerinde, önceki düzeyler hakkında bilgi alın.

##  <a name="idle"></a>  CDaoWorkspace::Idle

Çağrı `Idle` veritabanı altyapısı nedeniyle yoğun veri işleme, güncel olmayabilir arka plan görevleri gerçekleştirme olanağı sağlamak için.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>Parametreler

*nEylem*<br/>
Boşta işleme sırasında gerçekleştirilecek bir eylem. Şu anda yalnızca geçerli eylem ise `dbFreeLocks`.

### <a name="remarks"></a>Açıklamalar

Bu genellikle olduğu olmayan bir kayıt kümesindeki tüm kayıtlar güncel tutmak için yeterli arka plan işleme süresi çok kullanıcılı, çoklu ortamlarında true olur.

> [!NOTE]
>  Çağırma `Idle` Microsoft Jet veritabanı altyapısı 3.0 sürümü ile oluşturulan veritabanları ile gerekli değildir. Kullanım `Idle` yalnızca önceki sürümleriyle oluşturulan veritabanları için.

Genellikle okuma kilitlerini kaldırılır ve yerel değişken küme türündeki kayıt kümesi nesnelerdeki verilere güncelleştirilir (fare hareketlerini dahil) herhangi bir eylem yalnızca oluşan olduğunda. Düzenli aralıklarla çağırırsanız `Idle`, arka planda işleme görevlerini bırakarak Kaçırdığınız süresiyle veritabanı altyapısı kilitleri okumak sağlayın. Belirtme `dbFreeLocks` sabit bağımsız değişken olarak, tüm okuma kilitler serbest bırakılana kadar işleme geciktirir.

Bu üye işlevi bir uygulamanın birden çok örneği çalıştırmıyorsanız tek kullanıcı ortamlarında gerekli değildir. `Idle` Üye işlevi, çok kullanıcılı bir ortamda performans artırabileceği, diske, bellek kilitleri serbest verileri temizleyemedi. veritabanı altyapısı zorladığından. Bir işlemin parçası işlemleri yaparak, salt okunur kilitleri serbest bırakabilirsiniz.

İlgili bilgiler için DAO Yardımı'nda "yöntemi boşta" konusuna bakın.

##  <a name="isopen"></a>  CDaoWorkspace::IsOpen

Belirlemek için bu üye işlevi çağrısı olup olmadığını `CDaoWorkspace` nesnedir açık — diğer bir deyişle, olup MFC nesne için bir çağrı tarafından başlatılmış [açın](#open) veya çağrı [Oluştur](#create).

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı nesnesi açıksa sıfır; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Herhangi bir açık durumda olan bir çalışma alanının işlevleri çağırabilir.

##  <a name="m_pdaoworkspace"></a>  CDaoWorkspace::m_pDAOWorkspace

DAO çalışma alanı nesnesini bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Doğrudan DAO nesnesini erişim, bu veri üyesi kullanın. DAO nesnenin arabirimlerinin this işaretçisi aracılığıyla çağırabilirsiniz.

DAO nesneleri doğrudan erişme hakkında daha fazla bilgi için bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

##  <a name="open"></a>  CDaoWorkspace::Open

Açıkça DAO'ın varsayılan çalışma alanı ile ilişkili bir çalışma alanı nesnesini açar.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Açmak için DAO çalışma nesnesinin adını — çalışma adlandıran 14 adede kadar karakter içeren bir dize. Açıkça varsayılan çalışma alanını açmak için NULL varsayılan değeri kabul edin. Adlandırma gereksinimlerini bkz *lpszName* parametresi için [Oluştur](#create). İlgili bilgiler için DAO Yardımı'nda "Name özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Oluşturma sonrasında bir `CDaoWorkspace` nesne, aşağıdakilerden birini yapmak için bu üye işlevini çağırın:

- Açıkça varsayılan çalışma alanını açın. NULL geçirmek *lpszName*.

- Mevcut bir açık `CDaoWorkspace` nesnesi, ada göre çalışma alanı koleksiyonunun bir üyesi. Mevcut bir çalışma alanı nesnesi için geçerli bir ad verin.

`Open` Çalışma alanı nesnesi açık olmayan bir duruma getirir ve bunu zaten uygulamanız için başlatılmadı, veritabanı altyapısı da başlatır.

Ancak birçok `CDaoWorkspace` üye işlevleri, yalnızca çalışma açıldıktan sonra çağrılabilir, veritabanı altyapısında çalışan aşağıdaki üye işlevleri kullanılabilir yapı C++ nesnesinin ancak bir çağrı önce sonra `Open`:

||||
|-|-|-|
|[Oluşturma](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|
|[GetIniPath](#getinipath)|[Boşta](#idle)|[SetIniPath](#setinipath)|
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|

##  <a name="repairdatabase"></a>  CDaoWorkspace::RepairDatabase

Microsoft Jet veritabanı altyapısı erişen bozuk bir veritabanını onarmayı denemek gerekiyorsa, bu üye işlevini çağırın.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Mevcut bir Microsoft Jet motoru veritabanı dosyası için dosya adı ve yolu. Yolun atlarsanız, yalnızca geçerli dizin aranır. Sisteminiz Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, bir ağ yolu gibi belirtebilirsiniz: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, yol dizesi gereklidir, çünkü "\\" C++ kaçış karakteri olan.)

### <a name="remarks"></a>Açıklamalar

Tarafından belirtilen veritabanı kapatmalısınız *lpszName* önce onu onarın. Çok kullanıcılı bir ortamda, diğer kullanıcıların olamaz *lpszName* onarma sırada açın. Varsa *lpszName* kapalı veya hata oluşursa özel kullanım için kullanılabilir değil.

Bu üye işlevi, bir eksik yazma işlemiyle bozuk olarak işaretlenmiş bir veritabanını onarın dener. Microsoft Jet Veritabanı Altyapısı'nı kullanarak bir uygulama beklenmedik bir güç kesintisi veya bilgisayarın donanım sorunu nedeniyle kapalı ise bu durum oluşabilir. Çağrı ve işlemi tamamlarsınız [Kapat](../../mfc/reference/cdaodatabase-class.md#close) üye işlevini veya normal bir şekilde uygulama çıkın, veritabanı bozuk olarak işaretlenmez.

> [!NOTE]
>  Bir veritabanını onararak sonra bu da kullanarak sıkıştırmak için iyi bir fikirdir [CompactDatabase](#compactdatabase) dosyasını birleştirmek ve disk alanını kurtarmak için üye işlevi.

Veritabanları onarma hakkında daha fazla bilgi için DAO Yardımı'nda "RepairDatabase yöntemi" konusuna bakın.

##  <a name="rollback"></a>  CDaoWorkspace::Rollback

Geçerli işlem ve çalışma alanındaki tüm veritabanları, işlemin başladığı önce kendi durumuna geri yüklemek için bu üye işlevini çağırın.

```
void Rollback();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
>  Bir çalışma nesnesi içerisinde işlemler her zaman çalışma alanına genel ve yalnızca bir veritabanı ya da kayıt sınırlı değildir. Birden fazla veritabanı ya da bir çalışma alanı işlem içinde kayıt işlemleri gerçekleştirirseniz `Rollback` veritabanları ve kayıt kümelerini tümüne ilişkin tüm işlemleri geri yükler.

Bir çalışma nesnesi kaydetme veya bekleyen tüm işlemleri geri kapatırsanız, işlemleri otomatik olarak geri alınır. Eğer [CommitTrans](#committrans) veya `Rollback` ilk çağırmadan [BeginTrans](#begintrans), bir hata oluşur.

> [!NOTE]
>  Bir işlem başladığınızda, veritabanı altyapısı işlemlerini iş istasyonunda TEMP ortam değişkeni tarafından belirtilen dizindeki tutulan bir dosyaya kaydeder. İşlem günlüğü dosyaları kullanılabilir depolama alanına TEMP sürücünüzde aşarsa, veritabanı altyapısı oluşturmak MFC neden olacak bir `CDaoException` (DAO hata 2004). Eğer bu noktada `CommitTrans`belirsiz sayıda işlem taahhüt ancak kalan tamamlanmamış işlemleri kaybolur ve işlemi yeniden başlatılması gerekir. Çağırma `Rollback` işlem günlüğü serbest bırakır ve tüm işlemleri geri alır.

##  <a name="setdefaultpassword"></a>  CDaoWorkspace::SetDefaultPassword

Belirli bir parola bir çalışma nesnesi oluşturulduğunda veritabanı motorunu kullanır varsayılan parolayı ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszPassword*<br/>
Varsayılan parolası. Parola 14 adede kadar karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içermelidir. Parolalar büyük/küçük harfe duyarlıdır.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan parola çağrısından sonra oluşturduğunuz yeni çalışma alanlarında geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, bir parola belirtmeniz gerekmez [Oluştur](#create) çağırın.

Bu üye işlevi kullanmak için:

1. Oluşturmak bir `CDaoWorkspace` nesnesi ancak çağırmayın `Create`.

1. Çağrı `SetDefaultPassword` ve isterseniz [SetDefaultUser](#setdefaultuser).

1. Çağrı `Create` bu çalışma alanı nesnesi veya sonraki yorumlar için bir parola belirtilmeden.

Varsayılan olarak "admin" DefaultUser özelliği ayarlanır ve DefaultPassword özelliği için boş bir dize ("").

Güvenlik hakkında daha fazla bilgi için Yardım DAO "izinleri özelliği" konusuna bakın. İlgili bilgiler için "DefaultPassword özelliği" ve DAO Yardımı'nda "DefaultUser özelliği" konularına bakın.

##  <a name="setdefaultuser"></a>  CDaoWorkspace::SetDefaultUser

Belirli bir kullanıcı adı bir çalışma nesnesi oluşturulduğunda, veritabanı altyapısı kullanan varsayılan kullanıcı adı ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>Parametreler

*lpszDefaultUser*<br/>
Varsayılan kullanıcı adı. Bir kullanıcı adı 1-20 karakter uzunluğunda olmalıdır ve alfabetik karakterler, aksanlı karakterler, sayılar, boşluk ve semboller dışında şunlardır: "(tırnak işaretleri) / (eğik çizgi), \ (ters eğik çizgi) \[ \] (köşeli ayraç): (virgül) &#124; ( Kanal) \< (az-işareti), > (büyük-işareti), + (artı) = (eşittir işareti), (virgül), (ayrılmış) (soru işareti) \* (, alanları ve denetim karakterlerine (ASCII 00 ile 31 ASCII) baştaki yıldız işareti). İlgili bilgiler için DAO Yardımı'nda "UserName özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan kullanıcı adı ve çağrının ardından oluşturduğunuz yeni çalışma alanlarında geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, bir kullanıcı adı belirtmeniz gerekmez [Oluştur](#create) çağırın.

Bu üye işlevi kullanmak için:

1. Oluşturmak bir `CDaoWorkspace` nesnesi ancak çağırmayın `Create`.

1. Çağrı `SetDefaultUser` ve isterseniz [SetDefaultPassword](#setdefaultpassword).

1. Çağrı `Create` bu çalışma alanı nesnesi veya sonraki yorumlar için bir kullanıcı adı belirtilmeden.

Varsayılan olarak "admin" DefaultUser özelliği ayarlanır ve DefaultPassword özelliği için boş bir dize ("").

İlgili bilgiler için "DefaultUser özelliği" ve DAO Yardımı'nda "DefaultPassword özelliği" konularına bakın.

##  <a name="setinipath"></a>  CDaoWorkspace::SetIniPath

Microsoft Jet veritabanı altyapısı için Windows kayıt defteri ayarları konumunu belirtmek için bu üye işlevini çağırın.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistrySubkey*<br/>
Microsoft Jet veritabanı altyapısı ayarları ya da yüklenebilir ISAM veritabanları için gereken parametreleri konumu için bir Windows kayıt defteri alt anahtarı adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Çağrı `SetIniPath` yalnızca özel ayarlar belirtmeniz gerekiyorsa. Daha fazla bilgi için DAO Yardımı'nda "INIPath özelliği" konusuna bakın.

> [!NOTE]
>  Çağrı `SetIniPath` uygulama yüklemesi sırasında değil, uygulama çalışır. `SetIniPath` Tüm çalışma alanları, veritabanları ya da kayıt kümeleri açmadan önce çağrılmalıdır; Aksi takdirde, MFC özel durum oluşturur.

Bu mekanizma, bir veritabanı altyapısı, kullanıcı tarafından sağlanan kayıt defteri ayarlarını yapılandırmak için kullanabilirsiniz. Bu öznitelik kapsamı uygulamanıza sınırlıdır ve uygulamanızı yeniden başlatmadan değiştirilemez.

##  <a name="setisolateodbctrans"></a>  CDaoWorkspace::SetIsolateODBCTrans

Çalışma alanı için DAO IsolateODBCTrans özelliğinin değeri ayarlamak için bu üye işlevini çağırın.

```
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>Parametreler

*bIsolateODBCTrans*<br/>
ODBC işlemleri yalıtma başlamak istiyorsanız TRUE geçirin. ODBC işlemleri yalıtma durdurmak istiyorsanız FALSE geçirin.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Bu, her bir çalışma alanı veritabanı kendi ODBC bağlantısı olabilse de, sistem performansı yavaşlatır. İşlem yalıtım normalde gerekli olmadığından, aynı kullanıcı tarafından açıldığında birden çok çalışma alanı nesnelerden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları tek bir bağlantı üzerinde eşzamanlı işlemlere izin vermez. Böyle bir veritabanında bir zamanda birden fazla işlem değiştirilmesi gerekiyorsa, açıldıktan hemen sonra IsolateODBCTrans özelliği her bir çalışma alanı true. Bu, her çalışma alanı için ayrı bir ODBC bağlantı zorlar.

##  <a name="setlogintimeout"></a>  CDaoWorkspace::SetLoginTimeout

Çalışma alanı için DAO LoginTimeout özelliğinin değeri ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSeconds*<br/>
Bir ODBC Veritabanı'nda oturum açmaya çalıştığında bir hata gerçekleşmeden önce saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer bir ODBC Veritabanı'nda oturum açmaya çalıştığında bir hata gerçekleşmeden önce saniye sayısını temsil eder. Varsayılan LoginTimeout 20 saniyedir. LoginTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı oluşur ve veri kaynağı ile iletişimi yanıt vermeyebilir.

Oturumu açmak için Microsoft SQL Server gibi bir ODBC veritabanı çalışırken bağlantı, ağ hataları nedeniyle başarısız olabilir veya sunucusu çalışmıyor. Bağlanmak için 20 saniye için varsayılan beklemek yerine bir hata oluşturur önce veritabanı altyapısı bekleyeceği süreyi belirtebilirsiniz. Sunucuda oturum açmak, bir dış sunucu veritabanında sorgu çalıştırma gibi farklı olayların bir sayının parçası olarak örtülü olarak gerçekleşir. Zaman aşımı değeri LoginTimeout özelliğinin geçerli ayarı tarafından belirlenir.

İlgili bilgiler için DAO Yardımı'nda "LoginTimeout özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
