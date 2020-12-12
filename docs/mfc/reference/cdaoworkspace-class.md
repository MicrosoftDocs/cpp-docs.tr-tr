---
description: 'Daha fazla bilgi edinin: CDaoWorkspace sınıfı'
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
ms.openlocfilehash: 73236019db3ecf4a79ef93e19a55d909e6e0d61d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248007"
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace sınıfı

Bir adlandırılmış, parola korumalı veritabanı oturumunu, oturum açmak için, tek bir kullanıcı tarafından yönetir. DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Syntax

```
class CDaoWorkspace : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace:: Cdaoçalışma alanı](#cdaoworkspace)|Bir çalışma alanı nesnesi oluşturur. Daha sonra, `Create` veya öğesini çağırın `Open` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace:: Append](#append)|Yeni oluşturulan bir çalışma alanını veritabanı altyapısının çalışma alanları koleksiyonuna ekler.|
|[CDaoWorkspace:: BeginTrans](#begintrans)|Çalışma alanında açık olan tüm veritabanları için geçerli olan yeni bir işlem başlatır.|
|[CDaoWorkspace:: Close](#close)|Çalışma alanını ve içerdiği tüm nesneleri kapatır. Bekleyen işlemler geri alınır.|
|[CDaoWorkspace:: CommitTrans](#committrans)|Geçerli işlemi tamamlar ve değişiklikleri kaydeder.|
|[CDaoWorkspace:: CompactDatabase](#compactdatabase)|Bir veritabanını sıkıştırır (veya çoğaltır).|
|[CDaoWorkspace:: Create](#create)|Yeni bir DAO çalışma alanı nesnesi oluşturur.|
|[CDaoWorkspace:: GetDatabaseCount](#getdatabasecount)|Çalışma alanının veritabanları koleksiyonundaki DAO veritabanı nesnelerinin sayısını döndürür.|
|[CDaoWorkspace:: GetDatabaseInfo](#getdatabaseinfo)|Çalışma alanının veritabanları koleksiyonunda tanımlanan, belirtilen bir DAO veritabanı hakkındaki bilgileri döndürür.|
|[CDaoWorkspace:: Getınıpath](#getinipath)|Windows kayıt defterindeki Microsoft Jet veritabanı altyapısının başlatma ayarlarının konumunu döndürür.|
|[CDaoWorkspace:: Getısolateodbctrans](#getisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlemin, veri kaynağına zorlanan birden çok bağlantı aracılığıyla yalıtılmış olup olmadığını gösteren bir değer döndürür.|
|[CDaoWorkspace:: GetLoginTimeout](#getlogintimeout)|Kullanıcı bir ODBC veritabanında oturum açmaya çalıştığında bir hata oluştuktan önceki saniye sayısını döndürür.|
|[CDaoWorkspace:: GetName](#getname)|Çalışma alanı nesnesi için Kullanıcı tanımlı adı döndürür.|
|[CDaoWorkspace:: GetUserName](#getusername)|Çalışma alanı oluşturulduğunda belirtilen kullanıcı adını döndürür. Bu, çalışma alanı sahibinin adıdır.|
|[CDaoWorkspace:: GetVersion](#getversion)|Çalışma alanıyla ilişkili veritabanı altyapısının sürümünü içeren bir dize döndürür.|
|[CDaoWorkspace:: Getıworkspace sayısı](#getworkspacecount)|Veritabanı altyapısının çalışma alanları koleksiyonundaki DAO çalışma alanı nesnelerinin sayısını döndürür.|
|[CDaoWorkspace:: Getıworkspace bilgileri](#getworkspaceinfo)|Veritabanı altyapısının çalışma alanları koleksiyonunda tanımlanan, belirtilen bir DAO çalışma alanıyla ilgili bilgileri döndürür.|
|[CDaoWorkspace:: Idle](#idle)|Veritabanı altyapısının arka plan görevleri gerçekleştirmesini sağlar.|
|[CDaoWorkspace:: IsOpen](#isopen)|Çalışma alanı açıksa sıfır olmayan bir değer döndürür.|
|[CDaoWorkspace:: Open](#open)|DAO 'nun varsayılan çalışma alanıyla ilişkili bir çalışma alanı nesnesini açık olarak açar.|
|[CDaoWorkspace:: RepairDatabase](#repairdatabase)|Hasarlı bir veritabanını onarmaya çalışır.|
|[CDaoWorkspace:: Rollback](#rollback)|Geçerli işlemi sonlandırır ve değişiklikleri kaydetmez.|
|[CDaoWorkspace:: SetDefaultPassword](#setdefaultpassword)|Belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı parolayı ayarlar.|
|[CDaoWorkspace:: SetDefaultUser](#setdefaultuser)|Belirli bir Kullanıcı adı olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı kullanıcı adını ayarlar.|
|[CDaoWorkspace:: Setınpath](#setinipath)|Windows kayıt defterindeki Microsoft Jet veritabanı altyapısının başlatma ayarlarının konumunu ayarlar.|
|[CDaoWorkspace:: SetIsolateODBCTrans](#setisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlemin, veri kaynağına birden çok bağlantı zorlanarak yalıtılıp yalıtımadığını belirtir.|
|[CDaoWorkspace:: SetLoginTimeout](#setlogintimeout)|Kullanıcı bir ODBC veri kaynağında oturum açmaya çalıştığında bir hata oluştuktan önceki saniye sayısını ayarlar.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoWorkspace:: m_pDAOWorkspace](#m_pdaoworkspace)|Temel alınan DAO çalışma alanı nesnesine işaret eder.|

## <a name="remarks"></a>Açıklamalar

Çoğu durumda, birden fazla çalışma alanına ihtiyacınız olmayacaktır ve açık çalışma alanı nesneleri oluşturmanız gerekmez; veritabanı ve kayıt kümesi nesnelerini açtığınızda, DAO 'nun varsayılan çalışma alanını kullanır. Ancak, gerekirse, ek çalışma alanı nesneleri oluşturarak tek seferde birden çok oturum çalıştırabilirsiniz. Her çalışma alanı nesnesi, kendi veritabanı koleksiyonunda birden çok açık veritabanı nesnesi içerebilir. MFC 'de, bir çalışma alanı birincil olarak bir işlem yöneticisidir ve aynı "işlem alanında" bir açık veritabanı kümesi belirtilerek.

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında bir "CDao" öneki vardır. Genel olarak, DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıflarından daha yetenekli değildir. DAO tabanlı sınıflar, ODBC sürücüleri dahil olmak üzere Microsoft Jet veritabanı altyapısı aracılığıyla verilere erişir. Ayrıca, DAO 'YU doğrudan çağırmaya gerek kalmadan veritabanları oluşturma ve sınıflar aracılığıyla tablo ve alan ekleme gibi veri tanımlama dili (DDL) işlemlerini de destekler.

## <a name="capabilities"></a>Özellikler

Sınıfı `CDaoWorkspace` aşağıdakileri sağlar:

- Gerekirse, varsayılan bir çalışma alanına, veritabanı altyapısı başlatılarak bir açık erişim. Genellikle, veritabanı ve kayıt kümesi nesneleri oluşturarak DAO 'nun varsayılan çalışma alanını örtülü olarak kullanırsınız.

- Çalışma alanında açık olan tüm veritabanları için hareketlerin uygulandığı bir işlem alanı. Ayrı işlem alanlarını yönetmek için ek çalışma alanları oluşturabilirsiniz.

- Temel alınan Microsoft Jet veritabanı altyapısının birçok özelliklerine yönelik arabirim (bkz. statik üye işlevleri). Bir çalışma alanı açmak veya oluşturmak ya da açılmadan veya oluşturmadan önce statik üye işlevini çağırmak, veritabanı altyapısını başlatır.

- Kendisine eklenmiş olan tüm etkin çalışma alanlarını depolayan veritabanı altyapısının çalışma alanları koleksiyonuna erişim. Ayrıca, çalışma alanlarını koleksiyona eklemeden de oluşturabilir ve bunlarla çalışabilirsiniz.

## <a name="security"></a>Güvenlik

MFC, güvenlik denetimi için kullanılan, DAO 'daki kullanıcılar ve gruplar koleksiyonlarını uygulamaz. DAO 'nun bu yönlerine ihtiyaç duyuyorsanız, DAO arabirimlerine doğrudan çağrılar aracılığıyla bunları kendiniz programlayabilirsiniz. Bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="usage"></a>Kullanım

Sınıfını kullanarak şunları yapabilirsiniz `CDaoWorkspace` :

- Varsayılan çalışma alanını açık olarak açın.

   Yeni [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri açtığınızda, genellikle varsayılan çalışma alanı kullanımı açıktır. Ancak, veritabanına doğrudan erişmeniz gerekebilir — Örneğin, veritabanı motoru özelliklerine veya çalışma alanları koleksiyonuna erişim için. Aşağıdaki "varsayılan çalışma alanının örtük kullanımı" bölümüne bakın.

- Yeni çalışma alanları oluşturun. Çalışma alanları koleksiyonuna eklemek istiyorsanız [append](#append) öğesini çağırın.

- Çalışma alanları koleksiyonunda var olan bir çalışma alanını açın.

Çalışma alanları koleksiyonunda zaten bulunmayan yeni bir çalışma alanı oluşturmak, üye [Oluştur](#create) işlevi altında açıklanmıştır. Datababase Engine oturumları arasında herhangi bir şekilde çalışma alanı nesneleri kalıcı olmaz. Uygulamanız MFC 'yi statik olarak bağlantılarsa, uygulamayı sonlandırmak veritabanı altyapısını geri başlatır. Uygulamanız MFC ile dinamik olarak bağlanıyorsa, MFC DLL kaldırıldığında veritabanı altyapısı başlatılmamış olur.

Varsayılan çalışma alanını açıkça açmak veya çalışma alanları koleksiyonunda var olan bir çalışma alanını açmak, [Open](#open) member işlevinin altında açıklanmıştır.

[Kapalı](#close) üye işleviyle çalışma alanını kapatarak bir çalışma alanı oturumunu sonlandırın. `Close` daha önce kapatılmayan veritabanlarını kapatır ve kaydedilmemiş işlemleri geri alabilirsiniz.

## <a name="transactions"></a>İşlemler

DAO çalışma alanı düzeyindeki işlemleri yönetir; Bu nedenle, birden çok açık veritabanına sahip çalışma alanındaki işlemler tüm veritabanlarına uygulanır. Örneğin, iki veritabanında işlenmemiş güncelleştirmeler varsa ve [CommitTrans](#committrans)' ı çağırırsanız, tüm güncelleştirmeler işlenir. İşlemleri tek bir veritabanıyla sınırlandırmak istiyorsanız, için ayrı bir çalışma alanı nesnesi gerekir.

## <a name="implicit-use-of-the-default-workspace"></a>Varsayılan çalışma alanının örtük kullanımı

MFC, DAO 'nun varsayılan çalışma alanını aşağıdaki koşullarda örtülü olarak kullanır:

- Yeni bir `CDaoDatabase` nesne oluşturur ancak bunu mevcut bir nesne aracılığıyla yapmazsanız `CDaoWorkspace` , MFC sizin IÇIN, DAO 'nun varsayılan çalışma alanına karşılık gelen geçici bir çalışma alanı nesnesi oluşturur. Bunu birden çok veritabanı için yaparsanız, tüm veritabanı nesneleri varsayılan çalışma alanıyla ilişkilendirilir. Bir veri üyesi aracılığıyla bir veritabanının çalışma alanına erişebilirsiniz `CDaoDatabase` .

- Benzer şekilde, bir nesneye `CDaoRecordset` işaretçi sağlamadan bir nesne oluşturursanız `CDaoDatabase` , MFC geçici bir veritabanı nesnesi ve uzantıya göre geçici bir çalışma alanı nesnesi oluşturur. Bir veri üyesi aracılığıyla bir kayıt kümesinin veritabanına ve dolaylı olarak çalışma alanına erişebilirsiniz `CDaoRecordset` .

## <a name="other-operations"></a>Diğer Işlemler

Bozuk bir veritabanını onarma veya bir veritabanını düzenleme gibi diğer veritabanı işlemleri de sağlanır.

DAO 'YU doğrudan çağırma ve DAO güvenliği hakkında daha fazla bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CDaoWorkspace`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaoworkspaceappend"></a><a name="append"></a> CDaoWorkspace:: Append

[Oluşturma](#create)çağrısından sonra bu üye işlevini çağırın.

```
virtual void Append();
```

### <a name="remarks"></a>Açıklamalar

`Append` Yeni oluşturulan bir çalışma alanı nesnesini veritabanı altyapısının çalışma alanları koleksiyonuna ekler. Çalışma alanları, veritabanı altyapısı oturumları arasında devam etmez; diskler diskte değil yalnızca bellekte depolanır. Çalışma alanı eklemeniz gerekmez; Bunu yapmazsanız, kullanmaya devam edebilirsiniz.

Eklenmiş bir çalışma alanı, [Close](#close) üye işlevini çağırana kadar, etkin ve açık durumda olan çalışma alanları koleksiyonunda kalır.

İlgili bilgiler için, DAO yardımı 'nda "ekleme yöntemi" konusuna bakın.

## <a name="cdaoworkspacebegintrans"></a><a name="begintrans"></a> CDaoWorkspace:: BeginTrans

Bir işlem başlatmak için bu üye işlevini çağırın.

```cpp
void BeginTrans();
```

### <a name="remarks"></a>Açıklamalar

' İ çağırdıktan sonra `BeginTrans` , veri veya veritabanı yapınıza yaptığınız güncelleştirmeler işlemi gerçekleştirdiğinizde etkili olur. Çalışma alanı tek bir işlem alanını tanımladığından, işlem çalışma alanındaki tüm açık veritabanlarına uygulanır. İşlemi tamamlamaya yönelik iki yol vardır:

- İşlemi yürütmek ve veri kaynağına değişiklikleri kaydetmek için [CommitTrans](#committrans) üye işlevini çağırın.

- Veya işlemi iptal etmek için [Rollback](#rollback) üye işlevini çağırın.

Çalışma alanı nesnesini veya bir veritabanı nesnesini kapatmak, bir işlem beklerken bekleyen tüm işlemleri geri kaydeder.

Bir ODBC veri kaynağındaki işlemleri başka bir ODBC veri kaynağından yalıtmanız gerekiyorsa, bkz. [Setisolateodbctrans](#setisolateodbctrans) üye işlevi.

## <a name="cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a> CDaoWorkspace:: Cdaoçalışma alanı

Bir `CDaoWorkspace` nesnesi oluşturur.

```
CDaoWorkspace();
```

### <a name="remarks"></a>Açıklamalar

C++ nesnesi oluşturulduktan sonra iki seçeneğiniz vardır:

- Varsayılan çalışma alanını açmak veya çalışma alanları koleksiyonunda var olan bir nesneyi açmak için nesnenin [Açık](#open) üye işlevini çağırın.

- Veya yeni bir DAO çalışma alanı nesnesi oluşturmak için nesnenin üye [Oluştur](#create) işlevini çağırın. Bu, açıkça bir nesne aracılığıyla başvurabileceğiniz yeni bir çalışma alanı oturumu başlatır `CDaoWorkspace` . Öğesini çağırdıktan sonra `Create` , çalışma alanını veritabanı altyapısının çalışma alanları koleksiyonuna eklemek Istiyorsanız [append](#append) ' i çağırabilirsiniz.

Açıkça bir nesne oluşturmanız gerektiğinde ilgili bilgi için, [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) için sınıfa genel bakış bölümüne bakın `CDaoWorkspace` . Genellikle, bir çalışma alanı belirtmeden bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi açtığınızda veya bir veritabanı nesnesi belirtmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi açtığınızda örtük olarak oluşturulan çalışma alanlarını kullanırsınız. Bu şekilde oluşturulan MFC DAO nesneleri, bir kez oluşturulan ve yeniden kullanılan, DAO 'nun varsayılan çalışma alanını kullanır.

Bir çalışma alanını ve içerdiği nesneleri serbest bırakmak için, Workspace nesnesinin [Close](#close) üye işlevini çağırın.

## <a name="cdaoworkspaceclose"></a><a name="close"></a> CDaoWorkspace:: Close

Çalışma alanı nesnesini kapatmak için bu üye işlevini çağırın.

```
virtual void Close();
```

### <a name="remarks"></a>Açıklamalar

Açık çalışma alanı nesnesini kapatmak, temel alınan DAO nesnesini serbest bırakır ve çalışma alanı bir çalışma alanları koleksiyonunun üyesiyse, onu koleksiyondan kaldırır. Çağırma `Close` işlemi iyi bir programlama uygulamasıdır.

> [!CAUTION]
> Çalışma alanı nesnesini kapatmak çalışma alanındaki açık veritabanlarını kapatır. Bu, tüm kayıt kümelerinin kapanmakta olan veritabanlarında açık olması ve bekleyen tüm düzenlemeler ya da güncelleştirmelerin geri alınması sonucunu verir. İlgili bilgiler için, bkz. [CDaoDatabase:: Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset:: Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef:: Close](../../mfc/reference/cdaotabledef-class.md#close)ve [CDaoQueryDef:: Close](../../mfc/reference/cdaoquerydef-class.md#close) üye işlevleri.

Çalışma alanı nesneleri kalıcı değil; Bunlar yalnızca başvuruları vardır. Bu, veritabanı motoru oturumu sona erdiğinde, çalışma alanının ve veritabanları koleksiyonunun kalıcı olmayacağı anlamına gelir. Çalışma alanınızı ve veritabanınızı yeniden açarak bir sonraki oturum için bunları yeniden oluşturmanız gerekir.

İlgili bilgiler için, DAO yardımı 'nda "Yöntem kapatma" konusuna bakın.

## <a name="cdaoworkspacecommittrans"></a><a name="committrans"></a> CDaoWorkspace:: CommitTrans

Bir işlemi yürütmek için bu üye işlevini çağırın — çalışma alanındaki bir veya daha fazla veritabanında düzenleme ve güncelleştirme grubunu kaydedin.

```cpp
void CommitTrans();
```

### <a name="remarks"></a>Açıklamalar

Bir işlem, bir [BeginTrans](#begintrans)çağrısıyla başlayan veritabanının verilerinde veya yapısında bir dizi değişiklikle oluşur. İşlemi tamamladığınızda, uygulamayı yürütün veya geri [alma](#rollback)ile geri alın (değişiklikleri iptal edin). Varsayılan olarak, işlem olmadan kayıt güncelleştirmeleri hemen kaydedilir. Çağırma `BeginTrans` , çağrı yapana kadar güncelleştirmelerin gecikmesine neden olur `CommitTrans` .

> [!CAUTION]
> Bir çalışma alanı içinde, işlemler her zaman çalışma alanına geneldir ve yalnızca bir veritabanı ya da kayıt kümesiyle sınırlı değildir. Bir çalışma alanı işlemi içinde birden fazla veritabanı veya kayıt kümesi üzerinde işlem gerçekleştirirseniz, `CommitTrans` bekleyen tüm güncelleştirmeleri kaydeder ve `Rollback` bu veritabanlarına ve kayıt kümelerine tüm işlemleri geri yükler.

Bekleyen işlemleri olan bir veritabanını veya çalışma alanını kapattığınızda, işlemler geri alınır.

> [!NOTE]
> Bu, iki aşamalı bir tamamlama mekanizması değildir. Bir güncelleştirme işlemezse, diğerleri yine de devam edecektir.

## <a name="cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a> CDaoWorkspace:: CompactDatabase

Belirtilen bir Microsoft Jet 'i sıkıştırmak için bu üye işlevi çağırın (. MDB) veritabanı.

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
Mevcut, kapalı bir veritabanının adı. "C: \Mydb" gibi tam bir yol ve dosya adı olabilir \\ . MDB ". Dosya adının bir uzantısı varsa, onu belirtmeniz gerekir. Ağınız Tekdüzen adlandırma kuralını (UNC) destekliyorsa, " \\ \\ \\ \sunucum \\ \ myshare \\ \ mydizinim \\ \ mydbgibi bir ağ yolu da belirtebilirsiniz. MDB ". ("" C++ kaçış karakteri olduğundan, yol dizelerinde çift ters eğik çizgiler gereklidir \\ .)

*lpszDestName*<br/>
Oluşturmakta olduğunuz sıkıştırılan veritabanının tam yolu. Ayrıca, *lpszSrcName* ile olduğu gibi bir ağ yolu da belirtebilirsiniz. *LpszDestName* bağımsız değişkenini, *lpszSrcName* ile aynı veritabanı dosyasını belirtmek için kullanamazsınız.

*lpszPassword*<br/>
Parola korumalı bir veritabanını sıkıştırmak istediğinizde kullanılan parola. `CompactDatabase`Bir parola alan sürümünü kullanıyorsanız, tüm parametreleri sağlamanız gerektiğini unutmayın. Ayrıca, bu bir Connect parametresi olduğundan şu şekilde özel biçimlendirme gerektirir:; PWD = *lpszPassword*. Örneğin:; PWD = "mutlu". (Baştaki noktalı virgül gereklidir.)

*lpszLocale*<br/>
*LpszDestName* oluşturmak için harmanlama sırasını belirtmek için kullanılan bir dize ifadesi. Varsayılan değerini (aşağıya bakın) kabul ederek bu bağımsız değişkeni atlarsanız `dbLangGeneral` , yeni veritabanının yerel ayarı eski veritabanıyla aynı olur. Olası değerler şunlardır:

- `dbLangGeneral` İngilizce, Almanca, Fransızca, Portekizce, Italyanca ve modern Ispanyolca

- `dbLangArabic` Arapça

- `dbLangCyrillic` Rusça

- `dbLangCzech` Çekçe

- `dbLangDutch` Hollanda dili

- `dbLangGreek` Yunanca

- `dbLangHebrew` İbranice

- `dbLangHungarian` Macarca

- `dbLangIcelandic` İzlanda dili

- `dbLangNordic` İskandinav dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürüm 1,0)

- `dbLangNorwdan` Norveççe ve Danca

- `dbLangPolish` Lehçe

- `dbLangSpanish` Geleneksel Ispanyolca

- `dbLangSwedfin` İsveççe ve Fince

- `dbLangTurkish` Türkçe

*Önemli seçenekler*<br/>
Hedef veritabanı için bir veya daha fazla seçeneği gösterir, *lpszDestName*. Bu bağımsız değişkeni varsayılan değeri kabul ederek atlarsanız, *lpszDestName* aynı şifrelemeye ve *lpszSrcName* ile aynı sürüme sahip olur. Ya da seçeneğini, `dbEncrypt` `dbDecrypt` BIT düzeyinde OR işlecini kullanarak sürüm seçeneklerinden biriyle birleştirebilirsiniz. Veritabanı biçimi olarak değil, veritabanı biçimini belirten olası değerler şunlardır:

- `dbEncrypt` Sıkıştırma sırasında veritabanını şifreleyin.

- `dbDecrypt` Sıkıştırma sırasında veritabanının şifresini çözün.

- `dbVersion10` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı 1,0 sürümünü kullanan bir veritabanı oluşturun.

- `dbVersion11` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı 1,1 sürümünü kullanan bir veritabanı oluşturun.

- `dbVersion20` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı 2,0 sürümünü kullanan bir veritabanı oluşturun.

- `dbVersion30` Sıkıştırma sırasında Microsoft Jet veritabanı altyapısı 3,0 sürümünü kullanan bir veritabanı oluşturun.

`dbEncrypt` `dbDecrypt` Sıkıştırılmış veritabanının şifrelenip şifrelenmeyeceğini veya şifresinin çözülmesi gerekip gerekmediğini belirtmek için seçenekler bağımsız değişkeninde veya kullanabilirsiniz. Bir şifreleme sabitini atlarsanız veya hem hem de eklerseniz `dbDecrypt` `dbEncrypt` , *lpszDestName* aynı şifrelemeye sahip olur.  Sıkıştırılan veritabanının veri biçiminin sürümünü belirtmek için, Seçenekler bağımsız değişkenindeki sürüm sabitlerinden birini kullanabilirsiniz. Bu sabit yalnızca *lpszDestName* veri biçiminin sürümünü etkiler. Yalnızca bir sürüm sabiti belirtebilirsiniz. Bir sürüm sabitini atlarsanız, *lpszDestName* aynı sürüme sahip olacaktır *lpszSrcName*. *LpszDestName* yalnızca *lpszSrcName* ile aynı veya sonraki bir sürüme sıkıştırabilirsiniz.

> [!CAUTION]
> Bir veritabanı şifrelenmemişse, veritabanını oluşturan ikili disk dosyasını doğrudan okumak için Kullanıcı/parola güvenliği uygulasanız bile mümkündür.

### <a name="remarks"></a>Açıklamalar

Veritabanındaki verileri değiştirirken veritabanı dosyası parçalanabilir ve gerekenden daha fazla disk alanı kullanabilir. Veritabanı dosyasını birleştirmek için düzenli aralıklarla veritabanınızı sıkıştırmanız gerekir. Sıkıştırılan veritabanı genellikle küçüktür. Ayrıca veritabanını kopyalayıp sıkıştırırken harmanlama sırasını, şifrelemeyi veya veri biçiminin sürümünü değiştirmeyi de seçebilirsiniz.

> [!CAUTION]
> `CompactDatabase`Üye işlevi, tüm Microsoft Access veritabanını bir sürümden diğerine doğru dönüştürmeyecektir. Yalnızca veri biçimi dönüştürülür. Form ve raporlar gibi Microsoft Access tarafından tanımlanan nesneler dönüştürülmez. Ancak, veriler doğru şekilde dönüştürülür.

> [!TIP]
> Ayrıca, `CompactDatabase` bir veritabanı dosyasını kopyalamak için kullanabilirsiniz.

Veritabanları sıkıştırılıyor hakkında daha fazla bilgi için, DAO yardımı 'nda "CompactDatabase yöntemi" konusuna bakın.

## <a name="cdaoworkspacecreate"></a><a name="create"></a> CDaoWorkspace:: Create

Yeni bir DAO çalışma alanı nesnesi oluşturmak ve bunu MFC nesnesiyle ilişkilendirmek için bu üye işlevini çağırın `CDaoWorkspace` .

```
virtual void Create(
    LPCTSTR lpszName,
    LPCTSTR lpszUserName,
    LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Yeni çalışma alanı nesnesini benzersiz şekilde adlandıran en fazla 14 karakter içeren bir dize. Bir ad belirtmeniz gerekir. İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*lpszUserName*<br/>
Çalışma alanının sahibinin Kullanıcı adı. Gereksinimler için bkz. [SetDefaultUser](#setdefaultuser) üye işlevine *lpszDefaultUser* parametresi. İlgili bilgiler için, DAO yardımı 'nda "Kullanıcı adı özelliği" konusuna bakın.

*lpszPassword*<br/>
Yeni çalışma alanı nesnesinin parolası. Parola, en fazla 14 karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içerebilir. Parolalar büyük/küçük harfe duyarlıdır. İlgili bilgiler için, DAO yardımı 'nda "parola özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Genel oluşturma işlemi şu şekilde yapılır:

1. Bir [CDaoWorkspace](#cdaoworkspace) nesnesi oluşturun.

1. `Create`Temel ALıNAN DAO çalışma alanını oluşturmak için nesnenin üye işlevini çağırın. Bir çalışma alanı adı belirtmelisiniz.

1. Çalışma alanını veritabanı altyapısının çalışma alanları koleksiyonuna eklemek istiyorsanız, isteğe bağlı olarak [append](#append) çağrısı yapın. Çalışma alanıyla birlikte eklemeden çalışabilirsiniz.

Çağrıdan sonra `Create` çalışma alanı nesnesi açık durumda ve kullanıma hazırdır. Öğesinden sonra çağırmayın `Open` `Create` . `Create`Çalışma alanı koleksiyonunda zaten varsa, ' i çağırmayın. `Create` , uygulamanız için zaten başlatılmamış olan veritabanı altyapısını başlatır.

## <a name="cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a> CDaoWorkspace:: GetDatabaseCount

Çalışma alanının veritabanları koleksiyonundaki DAO veritabanı nesnelerinin sayısını (çalışma alanındaki açık veritabanlarının sayısı) almak için bu üye işlevini çağırın.

```
short GetDatabaseCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanındaki açık veritabanlarının sayısı.

### <a name="remarks"></a>Açıklamalar

`GetDatabaseCount` çalışma alanının veritabanları koleksiyonundaki tüm tanımlı veritabanları arasında döngü uygulamanız gerekiyorsa yararlıdır. Koleksiyonda belirli bir veritabanı hakkında bilgi edinmek için bkz. [GetDatabaseInfo](#getdatabaseinfo). Tipik kullanım, `GetDatabaseCount` Açık veritabanlarının sayısını çağırmak ve ardından bu numarayı, yinelenen çağrılar için bir döngü dizini olarak kullanmaktır `GetDatabaseInfo` .

## <a name="cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a> CDaoWorkspace:: GetDatabaseInfo

Çalışma alanında açık bir veritabanı hakkında çeşitli bilgileri almak için bu üye işlevi çağırın.

```cpp
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

*nDizin*<br/>
Dizine göre arama için, çalışma alanının veritabanları koleksiyonundaki veritabanı nesnesinin sıfır tabanlı dizini.

*dınfo 'lar*<br/>
İstenen bilgileri döndüren bir [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak veritabanı ile ilgili hangi bilgilerin alındığını belirleyen seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad, güncelleştirilebilir, Işlemler

- AFX_DAO_SECONDARY_INFO birincil bilgileri Plus: sürüm, harmanlama sırası, sorgu zaman aşımı

- Birincil ve ikincil bilgileri AFX_DAO_ALL_INFO ve: Bağlan

*lpszName*<br/>
Ada göre arama için veritabanı nesnesinin adı. Ad, yeni çalışma alanı nesnesini benzersiz şekilde adlandıran en fazla 14 karakter içeren bir dizedir.

### <a name="remarks"></a>Açıklamalar

İşlevin bir sürümü, dizine göre bir veritabanını arama olanağı sağlar. Diğer sürüm, bir veritabanını adına göre arama yapmanızı sağlar.

*Dınfo*'da döndürülen bilgilerin açıklaması Için, [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki tüm düzeyler için de bilgi alırsınız.

## <a name="cdaoworkspacegetinipath"></a><a name="getinipath"></a> CDaoWorkspace:: Getınıpath

Windows kayıt defterinde Microsoft Jet veritabanı altyapısının başlatma ayarlarının konumunu almak için bu üye işlevi çağırın.

```
static CString PASCAL GetIniPath();
```

### <a name="return-value"></a>Dönüş Değeri

Kayıt defteri konumunu içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Veritabanı altyapısının ayarları hakkında bilgi edinmek için konumunu kullanabilirsiniz. Döndürülen bilgiler aslında bir kayıt defteri alt anahtarının adıdır.

İlgili bilgiler için, DAO yardımı 'nda "INIPath özelliği" ve "veri erişimi için Windows kayıt defteri ayarlarını özelleştirme" konularına bakın.

## <a name="cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a> CDaoWorkspace:: Getısolateodbctrans

Çalışma alanının DAO ısoteodbctrans özelliğinin geçerli değerini almak için bu üye işlevi çağırın.

```
BOOL GetIsolateODBCTrans();
```

### <a name="return-value"></a>Dönüş Değeri

ODBC işlemleri yalıtılmışsa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma alanının veritabanına kendi ODBC bağlantısı olmasına rağmen bu, sistem performansını yavaşlatır. İşlem yalıtımı normalde gerekli olmadığı için, aynı kullanıcı tarafından açılan birden çok çalışma alanı nesnesinden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları, tek bir bağlantıda eşzamanlı işlemlere izin vermez. Bu tür bir veritabanına karşı bekleyen bir zamanda birden fazla işlem olması gerekiyorsa, her bir çalışma alanında onu açtığınızda ısoteodbctrans özelliğini TRUE olarak ayarlayın. Bu, her çalışma alanı için ayrı bir ODBC bağlantısını zorlar.

İlgili bilgiler için, DAO yardımı 'nda "ısoteodbctrans özelliği" konusuna bakın.

## <a name="cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a> CDaoWorkspace:: GetLoginTimeout

Çalışma alanının DAO LoginTimeout özelliğinin geçerli değerini almak için bu üye işlevi çağırın.

```
static short PASCAL GetLoginTimeout();
```

### <a name="return-value"></a>Dönüş Değeri

Bir ODBC veritabanında oturum açmaya çalıştığınızda hata oluşması gereken saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, bir ODBC veritabanında oturum açmaya çalıştığınızda hata oluşması gereken saniye sayısını temsil eder. Varsayılan LoginTimeout ayarı 20 saniyedir. LoginTimeout 0 olarak ayarlandığında zaman aşımı oluşmaz ve veri kaynağıyla iletişim yanıt vermeyi durdurabilir.

Microsoft SQL Server gibi bir ODBC veritabanında oturum açmaya çalışırken, ağ hatalarının sonucu olarak veya sunucu çalışmadığından bağlantı başarısız olabilir. Bağlanmak için varsayılan 20 saniye beklemek yerine, veritabanı altyapısının bir hata üretmeden önce ne kadar bekleyeceğini belirtebilirsiniz. Sunucuda oturum açmak, bir dış sunucu veritabanında sorgu çalıştırma gibi bir dizi farklı olayın parçası olarak örtük olarak gerçekleşir.

İlgili bilgiler için, DAO yardımı 'nda "LoginTimeout Özelliği" konusuna bakın.

## <a name="cdaoworkspacegetname"></a><a name="getname"></a> CDaoWorkspace:: GetName

Nesneyi temel alan DAO çalışma alanı nesnesinin kullanıcı tanımlı adını almak için bu üye işlevini çağırın `CDaoWorkspace` .

```
CString GetName();
```

### <a name="return-value"></a>Dönüş Değeri

DAO çalışma alanı nesnesinin kullanıcı tanımlı adını içeren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Ad, veritabanı altyapısının çalışma alanları koleksiyonundaki ada göre DAO çalışma alanı nesnesine erişmek için yararlıdır.

İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

## <a name="cdaoworkspacegetusername"></a><a name="getusername"></a> CDaoWorkspace:: GetUserName

Çalışma alanının sahibinin adını almak için bu üye işlevi çağırın.

```
CString GetUserName();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı nesnesinin sahibini temsil eden bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Çalışma alanı sahibine ilişkin izinleri almak veya ayarlamak için, Izinler özellik ayarını denetlemek üzere DAO 'YU doğrudan çağırın; Bu, kullanıcının hangi izinleri olduğunu belirler. İzinlerle çalışmak için bir SISTEME ihtiyacınız vardır. MDA dosyası.

DAO 'YU doğrudan çağırma hakkında daha fazla bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). İlgili bilgiler için, DAO yardımı 'nda "Kullanıcı adı özelliği" konusuna bakın.

## <a name="cdaoworkspacegetversion"></a><a name="getversion"></a> CDaoWorkspace:: GetVersion

Kullanımdaki Microsoft Jet veritabanı altyapısının sürümünü öğrenmek için bu üye işlevi çağırın.

```
static CString PASCAL GetVersion();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnesiyle ilişkili veritabanı altyapısının sürümünü gösteren bir [CString](../../atl-mfc-shared/reference/cstringt-class.md) .

### <a name="remarks"></a>Açıklamalar

Döndürülen değer "ana. ikincil" biçiminde sürüm numarasını temsil eder; Örneğin, "3,0". Ürün sürüm numarası (örneğin, 3,0) sürüm numarasından (3), bir noktayla ve yayın numarasından (0) oluşur.

İlgili bilgiler için, DAO yardımı 'nda "sürüm özelliği" konusuna bakın.

## <a name="cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a> CDaoWorkspace:: Getıworkspace sayısı

Veritabanı altyapısının çalışma alanları koleksiyonundaki DAO çalışma alanı nesnelerinin sayısını almak için bu üye işlevi çağırın.

```
short GetWorkspaceCount();
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanları koleksiyonundaki açık çalışma alanlarının sayısı.

### <a name="remarks"></a>Açıklamalar

Bu sayı, koleksiyona eklenmemiş açık çalışma alanlarını içermez. `GetWorkspaceCount` Çalışma alanları koleksiyonundaki tüm tanımlı çalışma alanlarını döngüye almanız gerekiyorsa yararlıdır. Koleksiyonda belirli bir çalışma alanı hakkında bilgi edinmek için bkz. [Getıın Info](#getworkspaceinfo). Tipik kullanım, `GetWorkspaceCount` Açık çalışma alanlarının sayısını çağırmak ve sonra bu numarayı, yinelenen çağrılar için bir döngü dizini olarak kullanmaktır `GetWorkspaceInfo` .

## <a name="cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a> CDaoWorkspace:: Getıworkspace bilgileri

Oturumunda açık olan bir çalışma alanı hakkında çeşitli bilgiler almak için bu üye işlevini çağırın.

```cpp
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

*nDizin*<br/>
Dizine göre arama için, çalışma alanları koleksiyonundaki veritabanı nesnesinin sıfır tabanlı dizini.

*wkspcinfo*<br/>
İstenen bilgileri döndüren bir [CDaoWorkspace Info](../../mfc/reference/cdaoworkspaceinfo-structure.md) nesnesine başvuru.

*dwInfoOptions*<br/>
Alınacak çalışma alanıyla ilgili hangi bilgilerin bulunduğunu belirten seçenekler. Kullanılabilir seçenekler, işlevin döndürmesine neden olan özellikler ile birlikte aşağıda listelenmiştir:

- AFX_DAO_PRIMARY_INFO (varsayılan) ad

- AFX_DAO_SECONDARY_INFO birincil bilgileri Plus: Kullanıcı adı

- Birincil ve ikincil bilgileri AFX_DAO_ALL_INFO ve: ODBCTrans 'ı yalıtma

*lpszName*<br/>
Ada göre arama için çalışma alanı nesnesinin adı. Ad, yeni çalışma alanı nesnesini benzersiz şekilde adlandıran en fazla 14 karakter içeren bir dizedir.

### <a name="remarks"></a>Açıklamalar

*Wkspcinfo*' de döndürülen bilgilerin açıklaması Için, [Cdaoıgntionınfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) yapısına bakın. Bu yapının, *Dwinfooptions* açıklamasında yukarıda listelenen bilgi öğelerine karşılık gelen üyeleri vardır. Bir düzeyde bilgi istediğinizde, önceki düzeyler için de bilgi alırsınız.

## <a name="cdaoworkspaceidle"></a><a name="idle"></a> CDaoWorkspace:: Idle

`Idle`Veritabanı altyapısını, yoğun veri işleme nedeniyle güncel olmayan arka plan görevleri gerçekleştirme fırsatına sağlamak için çağırın.

```
static void PASCAL Idle(int nAction = dbFreeLocks);
```

### <a name="parameters"></a>Parametreler

*nEylem*<br/>
Boşta işleme sırasında gerçekleştirilecek bir eylem. Şu anda tek geçerli eylem `dbFreeLocks` .

### <a name="remarks"></a>Açıklamalar

Bu, genellikle bir kayıt kümesindeki tüm kayıtları tutmak için yeterli arka plan işleme süresi olmayan çok kullanıcılı, çoklu görev ortamlarında geçerlidir.

> [!NOTE]
> Çağırma `Idle` , Microsoft Jet veritabanı altyapısının 3,0 sürümü ile oluşturulan veritabanlarında gerekli değildir. `Idle`Yalnızca önceki sürümlerle oluşturulan veritabanları için kullanın.

Genellikle, okuma kilitleri kaldırılır ve yerel dinamik küme türü kayıt kümesi nesnelerindeki veriler yalnızca başka hiçbir eylem (fare hareketleri dahil) gerçekleşmemişse güncelleştirilir. Düzenli aralıklarla bir kez çağrı yaparsanız `Idle` , gereksiz okuma kilitlerini serbest bırakarak arka plan işleme görevlerini yakalamak için veritabanı altyapısı 'nı sağlarsınız. `dbFreeLocks`Sabit bir bağımsız değişken olarak belirtilmesi, tüm okuma kilitleri serbest bırakılana kadar işleme gecikmelidir.

Bu üye işlevi, bir uygulamanın birden çok örneği çalışmadığı müddetçe tek kullanıcı ortamlarında gerekli değildir. `Idle`Üye işlevi, veritabanı motorunu verileri diske boşaltmaya zorlediği ve bellekte kilitleri serbest bırakan bir çok kullanıcılı ortamda performansı artırabilir. Ayrıca işlemleri bir işlemin parçası yaparak okuma kilitlerini serbest bırakabilirsiniz.

İlgili bilgiler için, DAO yardımı 'nda "boşta yöntemi" konusuna bakın.

## <a name="cdaoworkspaceisopen"></a><a name="isopen"></a> CDaoWorkspace:: IsOpen

Nesnenin açık olup olmadığını öğrenmek için bu üye işlevi çağırın `CDaoWorkspace` — diğer bir deyişle, MFC nesnesinin [Açık](#open) veya [oluşturulacak](#create)bir çağrı ile başlatılmış olup olmadığı.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çalışma alanı nesnesi açıksa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Açık durumda olan bir çalışma alanının üye işlevlerinden herhangi birini çağırabilirsiniz.

## <a name="cdaoworkspacem_pdaoworkspace"></a><a name="m_pdaoworkspace"></a> CDaoWorkspace:: m_pDAOWorkspace

Temel alınan DAO çalışma alanı nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Temel alınan DAO nesnesine doğrudan erişmeniz gerekiyorsa bu veri üyesini kullanın. Bu işaretçi aracılığıyla DAO nesnesinin arabirimlerini çağırabilirsiniz.

DAO nesnelerine doğrudan erişme hakkında daha fazla bilgi için bkz. [teknik notta 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).

## <a name="cdaoworkspaceopen"></a><a name="open"></a> CDaoWorkspace:: Open

DAO 'nun varsayılan çalışma alanıyla ilişkili bir çalışma alanı nesnesini açık olarak açar.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Açılacak DAO çalışma alanı nesnesinin adı — en fazla 14 karakter içeren bir dize, çalışma alanını benzersiz olarak adlandırır. Varsayılan çalışma alanını açık olarak açmak için NULL varsayılan değerini kabul edin. Adlandırma gereksinimleri için, bkz. [Create](#create) *lpszName* parametresi. İlgili bilgiler için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturduktan sonra `CDaoWorkspace` , aşağıdakilerden birini yapmak için bu üye işlevi çağırın:

- Varsayılan çalışma alanını açık olarak açın. *LpszName* için null geçirin.

- `CDaoWorkspace`Çalışma alanları koleksiyonunun bir üyesi olan varolan bir nesneyi ada göre açın. Mevcut bir çalışma alanı nesnesi için geçerli bir ad geçirin.

`Open` çalışma alanı nesnesini açık duruma geçirir ve ayrıca, uygulamanız için zaten başlatılmamışsa, veritabanı altyapısını başlatır.

Birçok `CDaoWorkspace` üye işlevi yalnızca çalışma alanı açıldıktan sonra çağrılabilir ancak, veritabanı altyapısında çalışan aşağıdaki üye işlevleri, C++ nesnesi oluşturulduktan sonra ancak öğesine yapılan çağrıdan sonra kullanılabilir `Open` .

:::row:::
   :::column span="":::
      [Oluşturma](#create)\
      [Getınıpath](#getinipath)\
      [GetLoginTimeout](#getlogintimeout)
   :::column-end:::
   :::column span="":::
      [GetVersion](#getversion)\
      [Boş](#idle)
   :::column-end:::
   :::column span="":::
      [SetDefaultPassword](#setdefaultpassword)\
      [SetDefaultUser](#setdefaultuser)
   :::column-end:::
   :::column span="":::
      [Setınıpath](#setinipath)\
      [SetLoginTimeout](#setlogintimeout)
   :::column-end:::
:::row-end:::

## <a name="cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a> CDaoWorkspace:: RepairDatabase

Microsoft Jet veritabanı altyapısına erişen bozuk bir veritabanını onarmayı denemeniz gerekiyorsa bu üye işlevi çağırın.

```
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parametreler

*lpszName*<br/>
Mevcut bir Microsoft Jet Engine veritabanı dosyası için yol ve dosya adı. Yolu atlarsanız, yalnızca geçerli dizin aranır. Sisteminiz Tekdüzen adlandırma kuralını (UNC) destekliyorsa, şöyle bir ağ yolu belirtebilirsiniz: " \\ \\ \\ \sunucum \\ \ myshare \\ \mydizinim \\ \ MyDB. MDB ". ("" C++ kaçış karakteri olduğundan, yol dizesinde çift ters eğik çizgi gereklidir \\ .)

### <a name="remarks"></a>Açıklamalar

*LpszName* tarafından belirtilen veritabanını onarmadan önce kapatmanız gerekir. Çok kullanıcılı bir ortamda, diğer kullanıcıların *lpszName* açık olması gerekir. *LpszName* kapanmamış veya özel kullanım için kullanılabilir değilse bir hata oluşur.

Bu üye işlevi, tamamlanmamış bir yazma işlemi tarafından bozuk olarak işaretlenmiş bir veritabanını onarmaya çalışır. Bu durum, bir güç kesintisi veya bilgisayar donanımı sorunu nedeniyle Microsoft Jet veritabanı altyapısını kullanan bir uygulama beklenmedik şekilde kapatılırsa oluşabilir. İşlemi tamamlayıp [kapatma](../../mfc/reference/cdaodatabase-class.md#close) üye işlevini çağırırsanız veya uygulamadan her zamanki şekilde çıkarsanız, veritabanı muhtemelen bozuk olarak işaretlenmeyecektir.

> [!NOTE]
> Bir veritabanını onardıktan sonra, dosyayı birleştirmek ve disk alanını kurtarmak için [CompactDatabase](#compactdatabase) üye işlevini kullanarak bunu sıkıştırmak de iyi bir fikirdir.

Veritabanlarını onarma hakkında daha fazla bilgi için, DAO yardımı 'nda "RepairDatabase yöntemi" konusuna bakın.

## <a name="cdaoworkspacerollback"></a><a name="rollback"></a> CDaoWorkspace:: Rollback

Geçerli işlemi sonlandırmak ve çalışma alanındaki tüm veritabanlarını, işlem başlamadan önce durumuna geri yüklemek için bu üye işlevi çağırın.

```cpp
void Rollback();
```

### <a name="remarks"></a>Açıklamalar

> [!CAUTION]
> Bir çalışma alanı nesnesi içinde, işlemler her zaman çalışma alanına geneldir ve yalnızca bir veritabanı ya da kayıt kümesiyle sınırlı değildir. Bir çalışma alanı işlemi içinde birden fazla veritabanı veya kayıt kümesi üzerinde işlem gerçekleştirirseniz, `Rollback` Bu veritabanlarının ve kayıt kümelerinin tümünde tüm işlemleri geri yükler.

Bekleyen işlemleri kaydetmeden veya geri almadan bir çalışma alanı nesnesini kapatırsanız, işlemler otomatik olarak geri alınır. [CommitTrans](#committrans) 'yi çağırdıysanız veya `Rollback` ilk olarak [BeginTrans](#begintrans)'yi çağırmadan bir hata oluşur.

> [!NOTE]
> Bir işlem başlattığınızda, veritabanı altyapısı işlemlerini iş istasyonundaki TEMP ortam değişkeni tarafından belirtilen dizinde tutulan bir dosyaya kaydeder. İşlem günlüğü dosyası, GEÇICI sürücünüzdeki kullanılabilir depolamayı tükettarsa, veritabanı altyapısı MFC 'nin `CDaoException` (DAO hatası 2004) oluşturmasına neden olur. Bu noktada, öğesini çağırırsanız `CommitTrans` , belirsiz sayıda işlem gerçekleştirilir, ancak kalan tamamlanmamış işlemler kaybolur ve işlemin yeniden başlatılması gerekir. Çağırma `Rollback` işlemi, işlem günlüğünü yayınlar ve işlemdeki tüm işlemleri geri kaydeder.

## <a name="cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a> CDaoWorkspace:: SetDefaultPassword

Belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı varsayılan parolayı ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```

### <a name="parameters"></a>Parametreler

*lpszPassword*<br/>
Varsayılan parola. Parola, en fazla 14 karakter uzunluğunda olabilir ve ASCII 0 (null) dışında herhangi bir karakter içerebilir. Parolalar büyük/küçük harfe duyarlıdır.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan parola, çağrıdan sonra oluşturduğunuz yeni çalışma alanları için geçerlidir. Sonraki çalışma alanlarını oluştururken [Create](#create) çağrısında bir parola belirtmeniz gerekmez.

Bu üye işlevi kullanmak için:

1. Bir `CDaoWorkspace` nesne oluşturun ancak çağırmayın `Create` .

1. ' İ `SetDefaultPassword` ve Isterseniz [SetDefaultUser](#setdefaultuser)öğesini çağırın.

1. `Create`Bu çalışma alanı nesnesi veya sonraki bir parolayı, bir parola belirtmeden çağırın.

Varsayılan olarak, DefaultUser özelliği "admin" olarak ayarlanır ve DefaultPassword özelliği boş bir dize ("") olarak ayarlanır.

Güvenlik hakkında daha fazla bilgi için, DAO yardımı 'nda "Izinler özelliği" konusuna bakın. İlgili bilgiler için, DAO yardımı 'nda "DefaultPassword özelliği" ve "DefaultUser özelliği" konularına bakın.

## <a name="cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a> CDaoWorkspace:: SetDefaultUser

Belirli bir Kullanıcı adı olmadan bir çalışma alanı nesnesi oluşturulduğunda veritabanı altyapısının kullandığı varsayılan kullanıcı adını ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```

### <a name="parameters"></a>Parametreler

*lpszDefaultUser*<br/>
Varsayılan Kullanıcı adı. Bir Kullanıcı adı 1-20 karakter uzunluğunda olabilir ve alfasayısal karakterler, aksanlı karakterler, sayılar, boşluklar ve simgeler içerebilir: "(tırnak işaretleri),/(eğik çizgi), \ (ters eğik çizgi), \[ \] (köşeli ayraç),: (iki nokta üst üste), &#124; (dikey çizgi), \< (less-than sign), > (büyüktür işareti), + (artı işareti), = (eşittir işareti),; (noktalı virgül),, (virgül), (soru işareti), \* (yıldız işareti), baştaki boşluklar ve denetim karakterleri (ASCII 00-ASCII 31). İlgili bilgiler için, DAO yardımı 'nda "Kullanıcı adı özelliği" konusuna bakın.

### <a name="remarks"></a>Açıklamalar

Ayarladığınız varsayılan Kullanıcı adı, çağrıdan sonra oluşturduğunuz yeni çalışma alanları için geçerlidir. Sonraki çalışma alanlarını oluştururken [Create](#create) çağrısında bir Kullanıcı adı belirtmeniz gerekmez.

Bu üye işlevi kullanmak için:

1. Bir `CDaoWorkspace` nesne oluşturun ancak çağırmayın `Create` .

1. , `SetDefaultUser` Ve istiyorsanız, [SetDefaultPassword](#setdefaultpassword)öğesini çağırın.

1. `Create`Bu çalışma alanı nesnesi veya sonraki bir Kullanıcı adı belirtmeden çağrı yapın.

Varsayılan olarak, DefaultUser özelliği "admin" olarak ayarlanır ve DefaultPassword özelliği boş bir dize ("") olarak ayarlanır.

İlgili bilgiler için, DAO yardımı 'nda "DefaultUser özelliği" ve "DefaultPassword özelliği" konularına bakın.

## <a name="cdaoworkspacesetinipath"></a><a name="setinipath"></a> CDaoWorkspace:: Setınpath

Microsoft Jet veritabanı altyapısı için Windows kayıt defteri ayarlarının konumunu belirtmek için bu üye işlevini çağırın.

```
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```

### <a name="parameters"></a>Parametreler

*lpszRegistrySubkey*<br/>
Microsoft Jet veritabanı altyapısı ayarları veya yüklenebilir ISAM veritabanları için gereken parametrelerin konumu için Windows kayıt defteri alt anahtarının adını içeren bir dize.

### <a name="remarks"></a>Açıklamalar

`SetIniPath`Yalnızca özel ayarları belirtmeniz gerekiyorsa çağırın. Daha fazla bilgi için, DAO yardımı 'nda "INIPath özelliği" konusuna bakın.

> [!NOTE]
> Uygulama `SetIniPath` çalıştırıldığında değil, uygulama yükleme sırasında çağrı. `SetIniPath` herhangi bir çalışma alanını, veritabanlarını veya kayıt kümelerini açmadan önce çağrılmalıdır; Aksi halde MFC bir özel durum oluşturur.

Bu mekanizmayı, veritabanı altyapısını Kullanıcı tarafından sağlanmış kayıt defteri ayarlarıyla yapılandırmak için kullanabilirsiniz. Bu özniteliğin kapsamı uygulamanızla sınırlı olduğundan, uygulamanız yeniden başlatılmadan değiştirilemez.

## <a name="cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a> CDaoWorkspace:: SetIsolateODBCTrans

Çalışma alanının DAO ısoteodbctrans özelliğinin değerini ayarlamak için bu üye işlevini çağırın.

```cpp
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```

### <a name="parameters"></a>Parametreler

*Bısoteodbctrans*<br/>
ODBC işlemlerini yalıtmaya başlamak istiyorsanız TRUE geçirin. ODBC işlemlerini yalıtmayı durdurmak istiyorsanız FALSE geçirin.

### <a name="remarks"></a>Açıklamalar

Bazı durumlarda, aynı ODBC veritabanında bekleyen birden çok eşzamanlı işlem olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma alanının veritabanına kendi ODBC bağlantısı olabilir, ancak bu sistem performansını yavaşlatır. İşlem yalıtımı normalde gerekli olmadığı için, aynı kullanıcı tarafından açılan birden çok çalışma alanı nesnesinden ODBC bağlantıları varsayılan olarak paylaşılır.

Microsoft SQL Server gibi bazı ODBC sunucuları, tek bir bağlantıda eşzamanlı işlemlere izin vermez. Bu tür bir veritabanına karşı bekleyen bir zamanda birden fazla işlem olması gerekiyorsa, her bir çalışma alanında onu açtığınızda ısoteodbctrans özelliğini TRUE olarak ayarlayın. Bu, her çalışma alanı için ayrı bir ODBC bağlantısını zorlar.

## <a name="cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a> CDaoWorkspace:: SetLoginTimeout

Çalışma alanının DAO LoginTimeout özelliğinin değerini ayarlamak için bu üye işlevini çağırın.

```
static void PASCAL SetLoginTimeout(short nSeconds);
```

### <a name="parameters"></a>Parametreler

*nSaniye*<br/>
Bir ODBC veritabanında oturum açmaya çalıştığınızda hata oluşması gereken saniye sayısı.

### <a name="remarks"></a>Açıklamalar

Bu değer, bir ODBC veritabanında oturum açmaya çalıştığınızda hata oluşması gereken saniye sayısını temsil eder. Varsayılan LoginTimeout ayarı 20 saniyedir. LoginTimeout 0 olarak ayarlandığında zaman aşımı oluşmaz ve veri kaynağıyla iletişim yanıt vermeyi durdurabilir.

Microsoft SQL Server gibi bir ODBC veritabanında oturum açmaya çalışırken, ağ hatalarının sonucu olarak veya sunucu çalışmadığından bağlantı başarısız olabilir. Bağlanmak için varsayılan 20 saniye beklemek yerine, veritabanı altyapısının bir hata üretmeden önce ne kadar bekleyeceğini belirtebilirsiniz. Sunucuda oturum açmak, bir dış sunucu veritabanında sorgu çalıştırma gibi bir dizi farklı olayın parçası olarak örtük olarak gerçekleşir. Zaman aşımı değeri, LoginTimeout özelliğinin geçerli ayarıyla belirlenir.

İlgili bilgiler için, DAO yardımı 'nda "LoginTimeout Özelliği" konusuna bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)<br/>
[CDaoException sınıfı](../../mfc/reference/cdaoexception-class.md)
