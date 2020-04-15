---
title: CDaoWorkspace Sınıf
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
ms.openlocfilehash: 52aaa4970ef483988194691eb6b870cbfe51f494
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377111"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace Sınıf

Adlandırılmış, parola korumalı bir veritabanı oturumunu oturum açmadan girişe kadar tek bir kullanıcı tarafından yönetir. DAO, Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDaoÇalışma Alanı::CDaoÇalışma Alanı](#cdaoworkspace)|Bir çalışma alanı nesnesi oluşturuyor. Daha sonra, arama `Create` veya `Open`.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoWorkspace::Ek](#append)|Veritabanı altyapısının Çalışma Alanları koleksiyonuna yeni oluşturulan bir çalışma alanı ekler.|
|[CDaoWorkspace::BeginTrans](#begintrans)|Çalışma alanında açık olan tüm veritabanları için geçerli olan yeni bir işlem başlatır.|
|[CDaoWorkspace::Kapat](#close)|Çalışma alanını ve içerdiği tüm nesneleri kapatır. Bekleyen hareketler geri alınır.|
|[CDaoWorkspace::CommitTrans](#committrans)|Geçerli hareketi tamamlar ve değişiklikleri kaydeder.|
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|Bir veritabanını sıkıştırır (veya yineler).|
|[CDaoWorkspace::Oluştur](#create)|Yeni bir DAO çalışma alanı nesnesi oluşturur.|
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Çalışma alanının Veritabanları koleksiyonundaki DAO veritabanı nesnelerinin sayısını verir.|
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Çalışma alanının Veritabanları koleksiyonunda tanımlanan belirli bir DAO veritabanı hakkındaki bilgileri verir.|
|[CDaoWorkspace::GetIniPath](#getinipath)|Windows kayıt defterinde Microsoft Jet veritabanı altyapısının başlatma ayarlarının konumunu döndürür.|
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlemin veri kaynağına zorunlu birden çok bağlantı yoluyla izole edilip edilmediğini gösteren bir değer verir.|
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Kullanıcı bir ODBC veritabanında oturum açmaya çalıştığında hata oluşmadan önceki saniye sayısını döndürür.|
|[CDaoWorkspace::GetName](#getname)|Çalışma alanı nesnesi için kullanıcı tanımlı adı döndürür.|
|[CDaoWorkspace::GetUserName](#getusername)|Çalışma alanı oluşturulduğunda belirtilen kullanıcı adını döndürür. Bu, çalışma alanı sahibinin adıdır.|
|[CDaoWorkspace::GetVersion](#getversion)|Çalışma alanıyla ilişkili veritabanı altyapısının sürümünü içeren bir dize döndürür.|
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|Veritabanı altyapısının Çalışma Alanları koleksiyonundaki DAO çalışma alanı nesnelerinin sayısını verir.|
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Veritabanı altyapısının Çalışma Alanları koleksiyonunda tanımlanan belirli bir DAO çalışma alanı hakkındaki bilgileri verir.|
|[CDaoWorkspace::Boşta](#idle)|Veritabanı altyapısının arka plan görevlerini gerçekleştirmesine olanak tanır.|
|[CDaoWorkspace::Açık](#isopen)|Çalışma alanı açıksa sıfırsız döndürür.|
|[CDaoWorkspace::Aç](#open)|DAO'nun varsayılan çalışma alanıyla ilişkili bir çalışma alanı nesnesi açıkça açılır.|
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Hasarlı bir veritabanını onarmaya çalışır.|
|[CDaoWorkspace::Geri alma](#rollback)|Geçerli hareketi sona erdirir ve değişiklikleri kaydetmez.|
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı parolayı ayarlar.|
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Belirli bir kullanıcı adı olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı kullanıcı adını ayarlar.|
|[CDaoÇalışma Alanı::SetIniPath](#setinipath)|Microsoft Jet veritabanı altyapısının Windows kayıt defterindeki başlatma ayarlarının konumunu ayarlar.|
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlemin veri kaynağına birden çok bağlantı zorlayarak yalıtılıp yalıtılmayacağını belirtir.|
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Kullanıcı bir ODBC veri kaynağında oturum açmaya çalıştığında hata oluşmadan saniye sayısını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoÇalışma Alanı::m_pDAOWorkspace](#m_pdaoworkspace)|Altta yatan DAO çalışma alanı nesnesine işaret edin.|

## <a name="remarks"></a>Açıklamalar

Çoğu durumda, birden çok çalışma alanına ihtiyacınız olmaz ve açık çalışma alanı nesneleri oluşturmanız gerekmez; veritabanını açtığınızda ve nesneleri kaydettiğinizde, DAO'nun varsayılan çalışma alanını kullanırlar. Ancak, gerekirse, ek çalışma alanı nesneleri oluşturarak aynı anda birden çok oturum çalıştırabilirsiniz. Her çalışma alanı nesnesi, kendi Veritabanları koleksiyonunda birden çok açık veritabanı nesnesi içerebilir. MFC'de, çalışma alanı öncelikle aynı "işlem alanında" açık veritabanları kümesini belirten bir işlem yöneticisidir.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adlarının bir "CDao" öneki vardır. Genel olarak, DAO'ya dayalı MFC sınıfları ODBC'ye dayalı MFC sınıflardan daha yeteneklidir. DAO tabanlı sınıflar, ODBC sürücüleri de dahil olmak üzere Microsoft Jet veritabanı altyapısı üzerinden verilere erişir. Ayrıca, DOĞRUDAN DAO'yu aramak zorunda kalmadan veritabanları oluşturma ve sınıflar üzerinden tablo ve alan ekleme gibi Veri Tanım Dili (DDL) işlemlerini de desteklerler.

## <a name="capabilities"></a>Özellikler

Sınıf `CDaoWorkspace` aşağıdakileri sağlar:

- Veritabanı altyapısının başlatılmasıyla oluşturulan varsayılan çalışma alanına açık erişim. Genellikle veritabanı ve kayıt kümesi nesneleri oluşturarak örtülü OLARAK DAO varsayılan çalışma alanı kullanın.

- Çalışma alanında açık olan tüm veritabanları için hareketlerin uygulandığı bir hareket alanı. Ayrı işlem alanlarını yönetmek için ek çalışma alanları oluşturabilirsiniz.

- Altta yatan Microsoft Jet veritabanı altyapısının birçok özelliğinin arabirimi (statik üye işlevlere bakın). Çalışma alanını açmak veya oluşturmak veya açmadan veya oluşturmadan önce statik bir üye işlevi çağırmak veritabanı altyapısını açar.

- Veritabanı altyapısının, eklenen tüm etkin çalışma alanlarını depolayan Çalışma Alanları koleksiyonuna erişim. Ayrıca, koleksiyona ekolmadan çalışma alanları oluşturabilir ve bunlarla çalışabilirsiniz.

## <a name="security"></a>Güvenlik

MFC, DAO'da güvenlik denetimi için kullanılan Kullanıcı ve Gruplar koleksiyonlarını uygulamaz. DAO bu yönlerini gerekiyorsa, DAO arayüzleri doğrudan aramalar yoluyla kendiniz programlamak gerekir. Daha fazla bilgi için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

## <a name="usage"></a>Kullanım

Sınıfı `CDaoWorkspace` şu şekilde kullanabilirsiniz:

- Varsayılan çalışma alanını açıkça açın.

   Genellikle varsayılan çalışma alanını kullanımınız örtülüdür — yeni [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri açtığınızda. Ancak veritabanı altyapısı özelliklerine veya Çalışma Alanları koleksiyonuna erişmek için açıkça erişmeniz gerekebilir. Aşağıdaki "Varsayılan Çalışma Alanının Örtülü Kullanımı" bölümüne bakın.

- Yeni çalışma alanları oluşturun. Çalışma Alanları koleksiyonuna eklemek istiyorsanız [Append'i](#append) arayın.

- Çalışma Alanları koleksiyonunda varolan bir çalışma alanı açın.

Çalışma Alanları koleksiyonunda zaten bulunmayan yeni bir çalışma alanı oluşturma, [Üye Oluştur](#create) işlevi altında açıklanır. Çalışma alanı nesneleri datababase altyapı oturumları arasında hiçbir şekilde devam etmez. Uygulamanız MFC'yi statik olarak bağlıyorsa, uygulamayı sonlandırmak veritabanı altyapısını başlatır. Uygulamanız MFC ile dinamik olarak bağlantı kursa, MFC DLL kaldırıldığında veritabanı altyapısı nın başlatılması nı sağlar.

Varsayılan çalışma alanını açıkça açmak veya Çalışma Alanları koleksiyonunda varolan bir çalışma alanını [açmak, Açık](#open) üye işlevi altında açıklanmıştır.

Çalışma alanını [Kapat](#close) üye işleviyle kapatarak çalışma alanı oturumunu sonlandırın. `Close`daha önce kapatmadığınız veritabanlarını kapatır ve kaydedilmemiş hareketleri geri alar.

## <a name="transactions"></a>İşlemler

DAO, çalışma alanı düzeyinde ki işlemleri yönetir; bu nedenle, birden çok açık veritabanları ile bir çalışma alanında hareketler tüm veritabanları için geçerlidir. Örneğin, iki veritabanında işlenmemiş güncelleştirmeler varsa ve [CommitTrans'ı](#committrans)ararsanız, güncelleştirmelerin tümü işlenir. Hareketleri tek bir veritabanıyla sınırlamak istiyorsanız, bunun için ayrı bir çalışma alanı nesnesi gerekir.

## <a name="implicit-use-of-the-default-workspace"></a>Varsayılan Çalışma Alanının Örtülü Kullanımı

MFC, DAO'nun varsayılan çalışma alanını aşağıdaki koşullar altında dolaylı olarak kullanır:

- Yeni `CDaoDatabase` bir nesne oluşturur, ancak varolan `CDaoWorkspace` bir nesne aracılığıyla bunu yapmazsanız, MFC sizin için DAO'nun varsayılan çalışma alanına karşılık gelen geçici bir çalışma alanı nesnesi oluşturur. Bunu birden çok veritabanı için yaparsanız, tüm veritabanı nesneleri varsayılan çalışma alanıyla ilişkilidir. Bir veritabanının çalışma alanına bir `CDaoDatabase` veri üyesi aracılığıyla erişebilirsiniz.

- Benzer şekilde, bir `CDaoRecordset` `CDaoDatabase` nesneye işaretçi sağlamadan bir nesne oluşturursanız, MFC geçici bir veritabanı nesnesi ve uzantısı olarak geçici bir çalışma alanı nesnesi oluşturur. Bir kayıt kümesinin veritabanına ve dolaylı olarak çalışma alanına `CDaoRecordset` bir veri üyesi aracılığıyla erişebilirsiniz.

## <a name="other-operations"></a>Diğer İşlemler

Bozuk bir veritabanını onarmak veya veritabanını sıkıştırmak gibi diğer veritabanı işlemleri de sağlanır.

DAO'ya doğrudan ve DAO güvenliği hakkında arama hakkında bilgi için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaoworkspaceappend"></a><a name="append"></a>CDaoWorkspace::Ek

Oluştur'u aradıktan sonra bu üye işlevini [çağırın.](#create)

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append`veritabanı altyapısının Çalışma Alanları koleksiyonuna yeni oluşturulan çalışma alanı nesnesini ekler. Çalışma alanları veritabanı altyapısı oturumları arasında kalıcı değildir; diskte değil, yalnızca bellekte depolanırlar. Bir çalışma alanı eklemek zorunda değilsin; yoksa, yine de kullanabilirsiniz.

Eklenen bir çalışma alanı, [siz Onun Yakın](#close) üye işlevini arayana kadar Çalışma Alanları koleksiyonunda etkin ve açık bir durumda kalır.

İlgili bilgiler için DAO Yardım'daki "Uygulama Yöntemi" konusuna bakın.

## <a name="cdaoworkspacebegintrans"></a><a name="begintrans"></a>CDaoWorkspace::BeginTrans

Bir işlem başlatmak için bu üye işlevi arayın.

```
void BeginTrans();
```

### <a name="remarks"></a>Açıklamalar

Aramadan `BeginTrans`sonra, işlemi yaptığınızda verilerinizde veya veritabanı yapınızda yaptığınız güncelleştirmeler etkili olur. Çalışma alanı tek bir işlem alanı tanımladığından, hareket çalışma alanındaki tüm açık veritabanları için geçerlidir. İşlemi tamamlamanın iki yolu vardır:

- İşlemi gerçekleştirmek ve verileri kaynağına kaydetmek için [CommitTrans](#committrans) üye işlevini arayın.

- Veya işlemi iptal etmek için [Rollback](#rollback) üye işlevini arayın.

İşlem beklerken çalışma alanı nesnesini veya veritabanı nesnesini kapatma bekleyen tüm hareketleri geri alır.

Bir ODBC veri kaynağındaki hareketleri başka bir ODBC veri kaynağındakilerden yalıtmanız gerekiyorsa, [SetIsolateODBCTrans](#setisolateodbctrans) üye işlevine bakın.

## <a name="cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a>CDaoÇalışma Alanı::CDaoÇalışma Alanı

Bir `CDaoWorkspace` nesne inşa eder.

```
CDaoWorkspace();
```

### <a name="remarks"></a>Açıklamalar

C++ nesnesini yaptıktan sonra iki seçeneğiniz vardır:

- Varsayılan çalışma alanını açmak veya Çalışma Alanları koleksiyonunda varolan bir nesneyi açmak için nesnenin [Açık](#open) üye işlevini çağırın.

- Veya yeni bir DAO çalışma alanı nesnesi oluşturmak için nesnenin [Oluştur](#create) üye işlevini çağırın. Bu, `CDaoWorkspace` nesne üzerinden başvurabileceğiniz yeni bir çalışma alanı oturumu başlatır. Aradıktan `Create`sonra, çalışma alanını veritabanı altyapısının Çalışma Alanları koleksiyonuna eklemek istiyorsanız [Append'i](#append) arayabilirsiniz.

Bir `CDaoWorkspace` nesneyi açıkça oluşturmanız gereken zaman hakkında bilgi almak için [CDaoWorkspace'e](../../mfc/reference/cdaoworkspace-class.md) sınıf genel bakışına bakın. Genellikle, bir çalışma alanı belirtmeden bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi açtığınızda veya bir veritabanı nesnesi belirtmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi açtığınızda örtülü olarak oluşturulan çalışma alanlarını kullanırsınız. Bu şekilde oluşturulan MFC DAO nesneleri, bir kez oluşturulan ve yeniden kullanılan DAO varsayılan çalışma alanı kullanır.

Çalışma alanını ve içerdiği nesneleri serbest bırakmak için çalışma alanı nesnesinin [Yakın](#close) üye işlevini arayın.

## <a name="cdaoworkspaceclose"></a><a name="close"></a>CDaoWorkspace::Kapat

Çalışma alanı nesnesini kapatmak için bu üye işlevi arayın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açık bir çalışma alanı nesnesini kapatmak, temel DAO nesnesini serbest bırakır ve çalışma alanı Çalışma Alanları koleksiyonunun bir üyesiyse, onu koleksiyondan kaldırır. Arama `Close` iyi programlama uygulamasıdır.

> [!CAUTION]
> Çalışma alanı nesnesini kapatmak, çalışma alanındaki tüm açık veritabanlarını kapatır. Bu, veritabanlarında da açık olan kayıt kümelerinin açılmasına ve bekleyen tüm güncelleştirmelerin veya güncelleştirmelerin geri aldansın. İlgili bilgiler için [CDaoDatabase::Close,](../../mfc/reference/cdaodatabase-class.md#close) [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close)ve [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) üye işlevlerini kapatın.

Çalışma alanı nesneleri kalıcı değildir; onlar sadece onlara referanslar var iken var. Bu, veritabanı altyapısı oturumu sona erdiğinde, çalışma alanı ve Veritabanları koleksiyonunun devam edilemeyeceğini anlamına gelir. Çalışma alanınızı ve veritabanı(lar)ınızı yeniden açarak bir sonraki oturum için bunları yeniden oluşturmanız gerekir.

İlgili bilgiler için DAO Yardım'daki "Yöntemi Kapat" konusuna bakın.

## <a name="cdaoworkspacecommittrans"></a><a name="committrans"></a>CDaoWorkspace::CommitTrans

Bir işlem gerçekleştirmek için bu üye işlevini çağırın — çalışma alanındaki bir veya daha fazla veritabanına bir dizi düzenlemeye ve güncelleştirmeye kaydedin.

```
void CommitTrans();
```

### <a name="remarks"></a>Açıklamalar

Bir hareket, [BeginTrans'a](#begintrans)yapılan bir çağrıyla başlayan veritabanının verilerinde veya yapısında yapılan bir dizi değişiklikten oluşur. İşlemi tamamladığınızda, [rollback](#rollback)ile ya gerçekleştirin ya da geri alabilirsiniz (değişiklikleri iptal edin). Varsayılan olarak, işlemler olmadan, kayıtlara güncelleştirmeler hemen işlenir. Arama, `BeginTrans` güncelleştirmelerin siz arayınana `CommitTrans`kadar geciktirilmesine neden olur.

> [!CAUTION]
> Bir çalışma alanı içinde, hareketler her zaman çalışma alanı için geneldir ve yalnızca bir veritabanı veya kayıt kümesiyle sınırlı değildir. Bir çalışma alanı hareketi içinde birden fazla veritabanı veya `CommitTrans` kayıt kümesinde işlem `Rollback` yaparsanız, bekleyen tüm güncelleştirmeleri işler ve bu veritabanları ve kayıt kümeleri üzerindeki tüm işlemleri geri yükler.

Bekleyen hareketlerle bir veritabanını veya çalışma alanını kapattığınızda, hareketlerin tümü geri alınır.

> [!NOTE]
> Bu iki aşamalı bir işleme mekanizması değildir. Bir güncelleştirme nin işlememesi durumunda, diğerleri yine de işlemeye devam eder.

## <a name="cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a>CDaoWorkspace::CompactDatabase

Belirli bir Microsoft Jet'i sıkıştırmak için bu üye işlevini arayın (. MDB) veritabanı.

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
Varolan, kapalı bir veritabanının adı. "C:\\\MYDB" gibi tam bir yol ve dosya adı olabilir. MDB". Dosya adının bir uzantısı varsa, belirtmeniz gerekir. Ağınız tek düzen adlandırma kuralını (UNC) destekliyorsa, "\\\\\\\MYSERVER \MYSHARE\\\\\\\MYDIR \MYDB gibi bir ağ yolu da belirtebilirsiniz. MDB". (" " C++\\kaçış karakteri olduğu için yol dizelerinde çift eğik çizgi gereklidir.)

*lpszDestName*<br/>
Oluşturduğunuz sıkıştırılmış veritabanının tam yolu. Ayrıca *lpszSrcName'de*olduğu gibi bir ağ yolu da belirtebilirsiniz. *LpszSrcName*ile aynı veritabanı dosyasını belirtmek için *lpszDestName* bağımsız değişkenini kullanamazsınız.

*lpszPassword*<br/>
Parola korumalı bir veritabanını sıkıştırmak istediğinizde kullanılan parola. `CompactDatabase` Bunun bir parola alır sürümünü kullanırsanız, tüm parametreleri sağlamanız gerektiğini unutmayın. Ayrıca, bu bir bağlantı parametresi olduğundan, aşağıdaki gibi özel biçimlendirme gerektirir: ; PWD= *lpszPassword*. Örneğin: ; PWD="Mutlu". (Önde gelen yarı kolon gereklidir.)

*lpszYerele*<br/>
*lpszDestName*oluşturmak için harmanlama sırasını belirtmek için kullanılan bir dize ifadesi. Bu bağımsız değişkeni varsayılan değerini kabul `dbLangGeneral` ederek atlarsanız (aşağıya bakın), yeni veritabanının yerel değeri eski veritabanınınkiyle aynıdır. Olası değerler şunlardır:

- `dbLangGeneral`İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern İspanyolca

- `dbLangArabic`Arapça

- `dbLangCyrillic`Rusça

- `dbLangCzech`Çekçe

- `dbLangDutch`Hollanda dili

- `dbLangGreek`Yunanca

- `dbLangHebrew`İbranice

- `dbLangHungarian`Macarca

- `dbLangIcelandic`İzlanda dili

- `dbLangNordic`İskandinav dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürümü 1.0)

- `dbLangNorwdan`Norveççe ve Danimarkaca

- `dbLangPolish`Lehçe

- `dbLangSpanish`Geleneksel İspanyolca

- `dbLangSwedfin`İsveççe ve Fince

- `dbLangTurkish`Türkçe

*nSeçenekler*<br/>
Hedef veritabanı için bir veya daha fazla seçenek gösterir, *lpszDestName*. Varsayılan değeri kabul ederek bu bağımsız değişkeni atlarsanız, *lpszDestName* aynı şifrelemeye ve *lpszSrcName*ile aynı sürüme sahip olacaktır. `dbEncrypt` Bitwise-OR `dbDecrypt` işleci kullanarak sürüm seçeneklerinden biriyle veya seçeneği birleştirebilirsiniz. Veritabanı altyapısı sürümü değil, veritabanı biçimi belirten olası değerler şunlardır:

- `dbEncrypt`Sıkıştırma sırasında veritabanını şifreleyin.

- `dbDecrypt`Sıkıştırma sırasında veritabanının şifresini çöz.

- `dbVersion10`Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.0 kullanan bir veritabanı oluşturun.

- `dbVersion11`Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.1'i kullanan bir veritabanı oluşturun.

- `dbVersion20`Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 2.0 kullanan bir veritabanı oluşturun.

- `dbVersion30`Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 3.0 kullanan bir veritabanı oluşturun.

Sıkıştırılmış `dbEncrypt` olarak `dbDecrypt` veritabanını şifreleyip şifrelemeyeceğiniz veya şifresini çözüp çözmeyin ilerler belirlemek için seçenekler bağımsız değişkenini kullanabilirsiniz. Bir şifreleme sabitini atlarsanız veya `dbDecrypt` `dbEncrypt`her ikisini de eklerseniz, *lpszDestName* *lpszSrcName*ile aynı şifrelemeye sahip olacaktır. Sıkıştırılmış veritabanı için veri biçiminin sürümünü belirtmek için seçenekler argümanındaki sürüm sabitlerinden birini kullanabilirsiniz. Bu sabit *lpszDestName*veri biçiminin yalnızca sürümünü etkiler. Yalnızca bir sürüm sabiti belirtebilirsiniz. Eğer bir sürüm sabiti atlarsanız, *lpszDestName* *lpszSrcName*ile aynı sürüme sahip olacaktır. *LpszDestName'yi* yalnızca *lpszSrcName*ile aynı veya daha sonra olan bir sürüme sıkıştırabilirsiniz.

> [!CAUTION]
> Bir veritabanı şifrelenmemişse, kullanıcı/parola güvenliğini uygulasanız bile veritabanını oluşturan ikili disk dosyasını doğrudan okumak mümkündür.

### <a name="remarks"></a>Açıklamalar

Veritabanındaki verileri değiştirin, veritabanı dosyası parçalanmış olabilir ve gerekenden daha fazla disk alanı kullanabilir. Düzenli aralıklarla, veritabanı dosyanızı parçalamak için veritabanınızı sıkıştırmanız gerekir. Sıkıştırılmış veritabanı genellikle daha küçüktür. Veritabanını kopyalayıp sıkıştırırken, harmanlama sırasını, şifrelemeyi veya veri biçiminin sürümünü değiştirmeyi de seçebilirsiniz.

> [!CAUTION]
> Üye `CompactDatabase` işlev, tam bir Microsoft Access veritabanını bir sürümden diğerine doğru şekilde dönüştürmez. Yalnızca veri biçimi dönüştürülür. Formlar ve raporlar gibi Microsoft Access tanımlı nesneler dönüştürülmez. Ancak, veriler doğru dönüştürülür.

> [!TIP]
> Veritabanı dosyasını `CompactDatabase` kopyalamak için de kullanabilirsiniz.

Sıkıştırma veritabanları hakkında daha fazla bilgi için DAO Yardım'da "CompactDatabase Method" konusuna bakın.

## <a name="cdaoworkspacecreate"></a><a name="create"></a>CDaoWorkspace::Oluştur

Yeni bir DAO çalışma alanı nesnesi oluşturmak ve MFC `CDaoWorkspace` nesnesi ile ilişkilendirmek için bu üye işlevi arayın.

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Yeni çalışma alanı nesnesini benzersiz olarak isimleyen en fazla 14 karaktere sahip bir dize. Bir isim vermelisin. İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

*lpszUserName*<br/>
Çalışma alanısahibinin kullanıcı adı. Gereksinimler için [SetDefaultUser](#setdefaultuser) üye işlevinin *lpszDefaultUser* parametresine bakın. İlgili bilgiler için DAO Help'deki "Kullanıcı Adı Özelliği" konusuna bakın.

*lpszPassword*<br/>
Yeni çalışma alanı nesnesinin parolası. Parola en fazla 14 karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içerebilir. Parolalar büyük/küçük harf duyarlıdır. İlgili bilgiler için DAO Yardım'daki "Parola Özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Genel oluşturma işlemi:

1. Bir [CDaoWorkspace nesnesi](#cdaoworkspace) oluştur.

1. Altta yatan DAO çalışma alanını oluşturmak için nesnenin `Create` üye işlevini çağırın. Bir çalışma alanı adı belirtmeniz gerekir.

1. Çalışma alanını veritabanı altyapısının Çalışma Alanları koleksiyonuna eklemek istiyorsanız isteğe bağlı olarak [Append'i](#append) arayın. Çalışma alanıyla ek olmadan çalışabilirsiniz.

Aramadan `Create` sonra, çalışma alanı nesnesi kullanıma hazır, açık bir durumdadır. Sonra `Open` `Create`aramayın. Çalışma alanı `Create` Çalışma Alanları koleksiyonunda zaten varsa aramazsınız. `Create`uygulamanız için daha önce başlatmışsa veritabanı altyapısını başlatir.

## <a name="cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount

Çalışma alanının Veritabanları koleksiyonundaki DAO veritabanı nesnelerinin sayısını almak için bu üye işlevi arayın - çalışma alanındaki açık veritabanlarının sayısı.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanındaki açık veritabanlarının sayısı.

### <a name="remarks"></a>Açıklamalar

`GetDatabaseCount`çalışma alanının Veritabanları koleksiyonundaki tüm tanımlı veritabanlarıarasında döngü oluşturmanız gerekiyorsa yararlıdır. Koleksiyondaki belirli bir veritabanı hakkında bilgi edinmek için [GetDatabaseInfo'ya](#getdatabaseinfo)bakın. Tipik kullanım, `GetDatabaseCount` açık veritabanlarının sayısını aramak, ardından bu sayıyı yinelenen aramalar `GetDatabaseInfo`için döngü dizini olarak kullanmaktır.

## <a name="cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo

Çalışma alanında açık bir veritabanı hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

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

*Nındex*<br/>
Çalışma alanının Veritabanları koleksiyonundaki veritabanı nesnesinin dizin le arama için sıfır tabanlı dizin.

*dbinfo*<br/>
İstenen bilgileri döndüren bir [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Veritabanı hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı, Güncel, İşlemler

- AFX_DAO_SECONDARY_INFO Birincil bilgi artı: Sürüm, Collating Order, Sorgu Zaman

- AFX_DAO_ALL_INFO Birincil ve ikincil bilgi artı: Bağlan

*Lpszname*<br/>
Veritabanı nesnesinin adı, ada göre arama için. Ad, yeni çalışma alanı nesnesini benzersiz olarak adlandıran en fazla 14 karaktere sahip bir dizedir.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, bir veritabanını dizin olarak aramanızı sağlar. Diğer sürüm, bir veritabanını ada göre aramanızı sağlar.

*DBinfo'da*döndürülen bilgilerin açıklaması için [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

## <a name="cdaoworkspacegetinipath"></a><a name="getinipath"></a>CDaoWorkspace::GetIniPath

Windows kayıt defterinde Microsoft Jet veritabanı altyapısının başlatma ayarlarının konumunu edinmek için bu üye işlevini arayın.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt defteri konumunu içeren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Veritabanı altyapısının ayarları hakkında bilgi almak için konumu kullanabilirsiniz. Döndürülen bilgiler aslında bir kayıt defteri alt anahtarının adıdır.

İlgili bilgiler için DAO Help'de "IniPath Property" ve "Veri Erişimi için Windows Kayıt Defteri Ayarlarını Özelleştirme" konularına bakın.

## <a name="cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a>CDaoWorkspace::GetIsolateODBCTrans

Çalışma alanı için DAO IsolateODBCTrans özelliğinin geçerli değerini almak için bu üye işlevi arayın.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC hareketleri yalıtılmışsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için, her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma alanının veritabanına kendi ODBC bağlantısına sahip olmasına rağmen, bunun sistem performansını yavaşlattığını unutmayın. İşlem yalıtımı normalde gerekli olmadığından, aynı kullanıcı tarafından açılan birden çok çalışma alanı nesnesinden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları, tek bir bağlantıda eşzamanlı işlemlere izin vermez. Böyle bir veritabanına karşı bekleyen bir anda birden fazla işlemin olması gerekiyorsa, açar açmaz her çalışma alanında IsolateODBCTrans özelliğini TRUE olarak ayarlayın. Bu, her çalışma alanı için ayrı bir ODBC bağlantısı zorlar.

İlgili bilgiler için DAO Yardım'daki "IsolateODBCTrans Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a>CDaoWorkspace::GetLoginTimeout

Çalışma alanı için DAO Giriş Zaman Dışarı özelliğinin geçerli değerini almak için bu üye işlevi arayın.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC veritabanında oturum açmaya çalıştığınızda hata oluşmadan önceki saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, bir ODBC veritabanında oturum açmaya çalıştığınızda bir hata oluşmadan önceki saniye sayısını gösterir. Varsayılan Giriş Zaman Çıkış ayarı 20 saniyedir. Giriş Zaman Dışarısı 0 olarak ayarlandığında, zaman ekme oluşmaz ve veri kaynağıyla iletişim yanıt vermeyi durdurabilir.

Microsoft SQL Server gibi bir ODBC veritabanında oturum açmaya çalışırken, ağ hataları veya sunucu çalışmadığı için bağlantı başarısız olabilir. Varsayılan 20 saniyenin bağlanmasını beklemek yerine, veritabanı altyapısının hata oluşturmadan önce ne kadar bekleyeceğini belirtebilirsiniz. Sunucuya giriş yapmak, dış sunucu veritabanında sorgu çalıştırmak gibi bir dizi farklı olayın parçası olarak örtülü olarak gerçekleşir.

İlgili bilgiler için DAO Yardım'daki "Giriş Zaman Çıkış Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetname"></a><a name="getname"></a>CDaoWorkspace::GetName

`CDaoWorkspace` Nesnenin altında yatan DAO çalışma alanı nesnesinin kullanıcı tanımlı adını almak için bu üye işlevi arayın.

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

DAO çalışma alanı nesnesinin kullanıcı tanımlı adını içeren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Ad, veritabanı altyapısının Çalışma Alanları koleksiyonundaki DAO çalışma alanı nesnesini ada göre erişmek için yararlıdır.

İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetusername"></a><a name="getusername"></a>CDaoWorkspace::GetUserName

Çalışma alanının sahibinin adını almak için bu üye işlevi arayın.

```
CString GetUserName();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı nesnesinin sahibini temsil eden bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Çalışma alanı sahibinin izinlerini almak veya ayarlamak için, İzinler özellik ayarını denetlemek için doğrudan DAO'yu arayın; bu, kullanıcının hangi izinlere sahip olduğunu belirler. İzinlerle çalışmak için bir SİsteM gerekir. MDA dosyası.

DOĞRUDAN DAO'u arama hakkında bilgi için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın. İlgili bilgiler için DAO Help'deki "Kullanıcı Adı Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetversion"></a><a name="getversion"></a>CDaoWorkspace::GetVersion

Microsoft Jet veritabanı altyapısının sürümünü belirlemek için bu üye işlevini arayın.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Nesneyle ilişkili veritabanı altyapısının sürümünü gösteren bir [CString.](../../atl-mfc-shared/reference/cstringt-class.md)

### <a name="remarks"></a>Açıklamalar

Döndürülen değer"major.minor" şeklindeki sürüm numarasını temsil eder; örneğin, "3.0". Ürün sürüm numarası (örneğin, 3.0) sürüm numarası (3), bir dönem ve sürüm numarasından (0) oluşur.

İlgili bilgiler için DAO Yardım'daki "Sürüm Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a>CDaoWorkspace::GetWorkspaceCount

Veritabanı altyapısının Çalışma Alanları koleksiyonundaki DAO çalışma alanı nesnelerinin sayısını almak için bu üye işlevi arayın.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma Alanları koleksiyonundaki açık çalışma alanlarının sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sayım, koleksiyona eklenmiş açık çalışma alanlarını içermez. `GetWorkspaceCount`Çalışma Alanları koleksiyonundaki tüm tanımlı çalışma alanlarını döngüye almanız gerekiyorsa yararlıdır. Koleksiyondaki belirli bir çalışma alanı hakkında bilgi edinmek için [GetWorkspaceInfo'ya](#getworkspaceinfo)bakın. Tipik kullanım, `GetWorkspaceCount` açık çalışma alanlarının sayısını aramak, ardından bu sayıyı yinelenen `GetWorkspaceInfo`aramalar için döngü dizini olarak kullanmaktır.

## <a name="cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a>CDaoWorkspace::GetWorkspaceInfo

Oturumda açık bir çalışma alanı hakkında çeşitli bilgiler elde etmek için bu üye işlevi arayın.

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

*Nındex*<br/>
Dizin tarafından arama için Çalışma Alanları koleksiyonundaki veritabanı nesnesinin sıfır tabanlı dizin.

*wkspcinfo*<br/>
İstenen bilgileri döndüren bir [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Çalışma alanı hakkında hangi bilgilerin alınaaçık olduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürülmesine neden oldukları yla birlikte burada listelenir:

- AFX_DAO_PRIMARY_INFO (Varsayılan) Adı

- AFX_DAO_SECONDARY_INFO Temel bilgi artı: Kullanıcı Adı

- AFX_DAO_ALL_INFO Birincil ve ikincil bilgi artı: ODBCTrans izole

*Lpszname*<br/>
Ada göre arama için çalışma alanı nesnesinin adı. Ad, yeni çalışma alanı nesnesini benzersiz olarak adlandıran en fazla 14 karaktere sahip bir dizedir.

### <a name="remarks"></a>Açıklamalar

*Wkspcinfo*döndürülen bilgilerin açıklaması için [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) yapısına bakın. Bu yapı, *dwInfoOptions*açıklamasında yukarıda listelenen bilgi öğeleri karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

## <a name="cdaoworkspaceidle"></a><a name="idle"></a>CDaoWorkspace::Boşta

Yoğun `Idle` veri işleme nedeniyle güncel olmayan arka plan görevlerini gerçekleştirme fırsatı yla veritabanı altyapısına ödeme yapın.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>Parametreler

*nEylem*<br/>
Boşta işleme sırasında yapılacak bir eylem. Şu anda tek `dbFreeLocks`geçerli eylem .

### <a name="remarks"></a>Açıklamalar

Bu genellikle, tüm kayıtları kayıt kümesi nde tutmak için yeterli arka plan işleme süresinin olmadığı çok kullanıcılı, çoklu görev ortamlarında geçerlidir.

> [!NOTE]
> Microsoft `Idle` Jet veritabanı altyapısının sürüm 3.0 ile oluşturulan veritabanları ile arama gerekli değildir. Yalnızca `Idle` önceki sürümlerle oluşturulan veritabanları için kullanın.

Genellikle, okuma kilitleri kaldırılır ve yerel dynaset türü kayıt kümesi nesnelerindeki veriler yalnızca başka bir eylem (fare hareketleri dahil) oluşmadığında güncelleştirilir. Düzenli olarak ararsanız, `Idle`gereksiz okuma kilitleri bırakarak arka plan işleme görevlerini yakalamak için veritabanı altyapısına zaman sağlarsınız. Bağımsız değişken `dbFreeLocks` olarak sabiti belirtme, tüm okuma kilitleri serbest bırakılıncaya kadar işlemeyi geciktirir.

Bir uygulamanın birden çok örneği çalışmadığı sürece, bu üye işlev tek kullanıcılı ortamlarda gerekli değildir. Üye `Idle` işlev, veritabanı altyapısını verileri diske yıkamaya zorladığı ve bellekte kilitler bırakması nedeniyle çok kullanıcılı bir ortamda performansı artırabilir. İşlemleri bir işlemin parçası haline getirerek okuma kilitlerini de serbest bırakabilirsiniz.

İlgili bilgiler için DAO Yardım'daki "Boşta Yöntemi" konusuna bakın.

## <a name="cdaoworkspaceisopen"></a><a name="isopen"></a>CDaoWorkspace::Açık

Nesnenin `CDaoWorkspace` açık olup olmadığını belirlemek için bu üye işlevi arayın - yani MFC nesnesinin [Aç'a](#open) yapılan bir çağrı yla mı yoksa [Oluşturma](#create)çağrısıyla mı baş harfe çevrilip açılmadığını.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı nesnesi açıksa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Açık durumda olan bir çalışma alanının üye işlevlerinden herhangi birini arayabilirsiniz.

## <a name="cdaoworkspacem_pdaoworkspace"></a><a name="m_pdaoworkspace"></a>CDaoÇalışma Alanı::m_pDAOWorkspace

Altta yatan DAO çalışma alanı nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Altta yatan DAO nesnesine doğrudan erişmeniz gerekiyorsa bu veri üyesini kullanın. Dao nesnesinin arabirimlerini bu işaretçi aracılığıyla arayabilirsiniz.

DAO nesnelerine doğrudan erişim hakkında bilgi için [Teknik Not 54'e](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)bakın.

## <a name="cdaoworkspaceopen"></a><a name="open"></a>CDaoWorkspace::Aç

DAO'nun varsayılan çalışma alanıyla ilişkili bir çalışma alanı nesnesi açıkça açılır.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Açılacak DAO çalışma alanı nesnesinin adı — çalışma alanını benzersiz olarak adlandıran en fazla 14 karaktere sahip bir dize. Varsayılan çalışma alanını açıkça açmak için varsayılan değer NULL'u kabul edin. Adlandırma gereksinimleri [için, Oluştur](#create)için *lpszName* parametreye bakın. İlgili bilgiler için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bir `CDaoWorkspace` nesne yaptıktan sonra, aşağıdakilerden birini yapmak için bu üye işlevi arayın:

- Varsayılan çalışma alanını açıkça açın. *LpszName*için NULL'u geç.

- Varolan `CDaoWorkspace` bir nesneyi, Çalışma Alanları koleksiyonunun bir üyesini ada göre açın. Varolan bir çalışma alanı nesnesi için geçerli bir ad geçirin.

`Open`çalışma alanı nesnesini açık bir duruma getirir ve uygulamanız için zaten başharfe çevrilmediyse veritabanı altyapısını başlatır.

Birçok `CDaoWorkspace` üye işlev yalnızca çalışma alanı açıldıktan sonra çağrılabilse de, veritabanı altyapısında çalışan aşağıdaki üye işlevler C++ nesnesinin yapımından sonra ancak çağrıdan önce `Open`kullanılabilir:

||||
|-|-|-|
|[Oluştur](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|
|[GetIniPath](#getinipath)|[Boş](#idle)|[SetIniPath](#setinipath)|
|[GetLoginTimeout](#getlogintimeout)|[Varsayılan Şifreyi Ayarla](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|

## <a name="cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a>CDaoWorkspace::RepairDatabase

Microsoft Jet veritabanı altyapısına erişen bozuk bir veritabanını onarmaya çalışmanız gerekiyorsa bu üye işlevi arayın.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*Lpszname*<br/>
Varolan bir Microsoft Jet altyapısı veritabanı dosyasının yolu ve dosya adı. Yolu atlarsanız, yalnızca geçerli dizin aranır. Sisteminiz tek düzen adlandırma\\\\\\kuralını (UNC) destekliyorsa, "\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB" gibi bir ağ yolu da belirtebilirsiniz. MDB". (" " C++\\kaçış karakteri olduğu için yol dizesinde çift eğik çizgi gereklidir.)

### <a name="remarks"></a>Açıklamalar

Onarmadan önce *lpszName* tarafından belirtilen veritabanını kapatmanız gerekir. Çok kullanıcılı bir ortamda, siz onu onarırken diğer kullanıcılar *lpszName'yi* açık layamaz. *LPSzName* kapalı değilse veya özel kullanım için kullanılamıyorsa bir hata oluşur.

Bu üye işlev, tamamlanmamış bir yazma işlemi tarafından bozuk olarak işaretlenmiş bir veritabanını onarmaya çalışır. Bu, Microsoft Jet veritabanı altyapısını kullanan bir uygulama, elektrik kesintisi veya bilgisayar donanımı sorunu nedeniyle beklenmedik şekilde kapatılırsa oluşabilir. İşlemi tamamlar ve [Kapat](../../mfc/reference/cdaodatabase-class.md#close) üye işlevini ararsanız veya uygulamayı olağan bir şekilde bırakırsanız, veritabanı bozuk olarak işaretlenmeyecek.

> [!NOTE]
> Bir veritabanını onardıktan sonra, dosyayı parçalamak ve disk alanını kurtarmak için [CompactDatabase](#compactdatabase) üye işlevini kullanarak sıkıştırmak da iyi bir fikirdir.

Veritabanlarını onarma hakkında daha fazla bilgi için DAO Help'deki "RepairDatabase Method" konusuna bakın.

## <a name="cdaoworkspacerollback"></a><a name="rollback"></a>CDaoWorkspace::Geri alma

Geçerli hareketi sona erdirmek ve çalışma alanındaki tüm veritabanlarını işlem başlamadan önce durumlarına geri yüklemek için bu üye işlevi arayın.

```
void Rollback();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bir çalışma alanı nesnesi içinde, hareketler her zaman çalışma alanı için geneldir ve yalnızca bir veritabanı veya kayıt kümesiyle sınırlı değildir. Bir çalışma alanı hareketi içinde birden fazla veritabanı veya `Rollback` kayıt kümesinde işlem yaparsanız, bu veritabanları ve kayıt kümelerinin tümünün tüm işlemlerini geri yükler.

Bekleyen hareketleri kaydetmeden veya geri almadan bir çalışma alanı nesnesini kapatırsanız, hareketler otomatik olarak geri alınır. [CommitTrans'ı](#committrans) ararsanız veya `Rollback` [BeginTrans'ı](#begintrans)ilk aramadan bir hata oluşur.

> [!NOTE]
> Bir hareketi başladığınızda, veritabanı altyapısı işlemlerini iş istasyonundaTEMP ortamı değişkeni tarafından belirtilen dizinde tutulan bir dosyada kaydeder. İşlem günlüğü dosyası TEMP sürücünüzdeki kullanılabilir depolama yıkılırsa, veritabanı altyapısı `CDaoException` MFC'nin (DAO hatası 2004) atmasını sağlar. Bu noktada, ararsanız, `CommitTrans`belirsiz sayıda işlem yapılır, ancak kalan tamamlanmamış işlemler kaybolur ve işlemin yeniden başlatılması gerekir. Arama, `Rollback` hareket günlüğünü serbest bırakır ve işlemdeki tüm işlemleri geri alır.

## <a name="cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a>CDaoWorkspace::SetDefaultPassword

Belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı varsayılan parolayı ayarlamak için bu üye işlevi arayın.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszPassword*<br/>
Varsayılan parola. Parola en fazla 14 karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içerebilir. Parolalar büyük/küçük harf duyarlıdır.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan parola, aramadan sonra oluşturduğunuz yeni çalışma alanları için geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, [Create](#create) çağrısında parola belirtmeniz gerekmez.

Bu üye işlevini kullanmak için:

1. Bir `CDaoWorkspace` nesne oluştur, `Create`ancak aramayın.

1. Arayın `SetDefaultPassword` ve isterseniz, [SetDefaultUser](#setdefaultuser).

1. Parola `Create` belirtmeden bu çalışma alanı nesnesi veya sonraki leri arayın.

Varsayılan olarak, DefaultUser özelliği "yönetici" olarak ayarlanır ve DefaultPassword özelliği boş bir dize ("") olarak ayarlanır.

Güvenlik hakkında daha fazla şey için DAO Yardım'daki "İzinler Özelliği" konusuna bakın. İlgili bilgiler için DAO Yardım'daki "DefaultPassword Property" ve "DefaultUser Property" konularına bakın.

## <a name="cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a>CDaoWorkspace::SetDefaultUser

Belirli bir kullanıcı adı olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı varsayılan kullanıcı adını ayarlamak için bu üye işlevi arayın.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>Parametreler

*lpszDefaultUser*<br/>
Varsayılan kullanıcı adı. Bir kullanıcı adı 1 - 20 karakter uzunluğunda olabilir ve alfabetik karakterler, aksanlı karakterler, sayılar, boşluklar ve semboller hariç: " \[ \] (tırnak işaretleri), / (ileri eğik çizgi), \ (ters eğik çizgi), (parantez), : (kolon), &#124; (boru), \< (daha az işaret), > (büyük işareti), + (artı işareti), = (eşit işaret), ; (semicolon), , (virgül), (soru işareti), \* (yıldız işareti), boşluk ve kontrol karakterleri (ASCII 00 - ASCII 31). İlgili bilgiler için DAO Help'deki "Kullanıcı Adı Özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan kullanıcı adı, aramadan sonra oluşturduğunuz yeni çalışma alanları için geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, [Create](#create) çağrısında bir kullanıcı adı belirtmeniz gerekmez.

Bu üye işlevini kullanmak için:

1. Bir `CDaoWorkspace` nesne oluştur, `Create`ancak aramayın.

1. Arama `SetDefaultUser` ve isterseniz, [SetDefaultPassword](#setdefaultpassword).

1. Bir `Create` kullanıcı adı belirtmeden bu çalışma alanı nesnesi veya sonraki nesneler için çağrıda deyin.

Varsayılan olarak, DefaultUser özelliği "yönetici" olarak ayarlanır ve DefaultPassword özelliği boş bir dize ("") olarak ayarlanır.

İlgili bilgiler için DAO Yardım'daki "DefaultUser Property" ve "DefaultPassword Property" konularına bakın.

## <a name="cdaoworkspacesetinipath"></a><a name="setinipath"></a>CDaoÇalışma Alanı::SetIniPath

Microsoft Jet veritabanı altyapısının Windows kayıt defteri ayarlarının konumunu belirtmek için bu üye işlevini arayın.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistrySubkey*<br/>
Microsoft Jet veritabanı altyapısı ayarlarının veya yüklenebilir ISAM veritabanları için gereken parametrelerin konumu için Windows kayıt defteri alt anahtarının adını içeren dize.

### <a name="remarks"></a>Açıklamalar

Yalnızca `SetIniPath` özel ayarlar belirtmeniz gerekiyorsa arayın. Daha fazla bilgi için DAO Yardım'daki "IniPath Property" konusuna bakın.

> [!NOTE]
> Uygulama `SetIniPath` nın çalıştırılması sırasında değil, uygulama yükleme sırasında arayın. `SetIniPath`çalışma alanlarını, veritabanlarını veya kayıt kümelerini açmadan önce çağrılmalıdır; aksi takdirde, MFC bir özel durum atar.

Veritabanı altyapısını kullanıcı tarafından sağlanan kayıt defteri ayarlarıyla yapılandırmak için bu mekanizmayı kullanabilirsiniz. Bu özniteliğin kapsamı uygulamanızla sınırlıdır ve uygulamanızı yeniden başlatmadan değiştirilemez.

## <a name="cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a>CDaoWorkspace::SetIsolateODBCTrans

Çalışma alanı için DAO IsolateODBCTrans özelliğinin değerini ayarlamak için bu üye işlevi arayın.

```
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>Parametreler

*bIsolateODBCTrans*<br/>
ODBC hareketlerini izole etmeye başlamak istiyorsanız TRUE'dan geçirin. ODBC hareketlerini yalıtmayı durdurmak istiyorsanız FALSE'u geçirin.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için, her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma alanı veritabanına kendi ODBC bağlantısına sahip olsa da, bu sistem performansını yavaşlatUr. İşlem yalıtımı normalde gerekli olmadığından, aynı kullanıcı tarafından açılan birden çok çalışma alanı nesnesinden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları, tek bir bağlantıda eşzamanlı işlemlere izin vermez. Böyle bir veritabanına karşı bekleyen bir anda birden fazla işlemin olması gerekiyorsa, açar açmaz her çalışma alanında IsolateODBCTrans özelliğini TRUE olarak ayarlayın. Bu, her çalışma alanı için ayrı bir ODBC bağlantısı zorlar.

## <a name="cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a>CDaoWorkspace::SetLoginTimeout

Çalışma alanı için DAO Giriş Timeout özelliğinin değerini ayarlamak için bu üye işlevi arayın.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSeconds*<br/>
ODBC veritabanında oturum açmaya çalıştığınızda hata oluşmadan önceki saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, bir ODBC veritabanında oturum açmaya çalıştığınızda bir hata oluşmadan önceki saniye sayısını gösterir. Varsayılan Giriş Zaman Çıkış ayarı 20 saniyedir. Giriş Zaman Dışarısı 0 olarak ayarlandığında, zaman ekme oluşmaz ve veri kaynağıyla iletişim yanıt vermeyi durdurabilir.

Microsoft SQL Server gibi bir ODBC veritabanında oturum açmaya çalışırken, ağ hataları veya sunucu çalışmadığı için bağlantı başarısız olabilir. Varsayılan 20 saniyenin bağlanmasını beklemek yerine, veritabanı altyapısının hata oluşturmadan önce ne kadar bekleyeceğini belirtebilirsiniz. Sunucuda oturum açmak, dış sunucu veritabanında sorgu çalıştırmak gibi bir dizi farklı olayın parçası olarak örtülü olarak gerçekleşir. Zaman ayarı değeri, LoginTimeout özelliğinin geçerli ayarına göre belirlenir.

İlgili bilgiler için DAO Yardım'daki "Giriş Zaman Çıkış Özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef Sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
