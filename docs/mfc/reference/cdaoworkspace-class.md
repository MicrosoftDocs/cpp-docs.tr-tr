---
title: "CDaoWorkspace sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 96cc8325ce8084d62f05283b424ead222bc55dd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace sınıfı
Bir adlandırılmış, parola korumalı veritabanı oturum kapatmaya, tek bir kullanıcı oturumu açma yönetir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Bir çalışma alanı nesnesi oluşturur. Daha sonra arama **oluşturma** veya **açık**.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|Yeni oluşturulan bir çalışma alanı veritabanı altyapısının çalışma alanları koleksiyonuna ekler.|  
|[CDaoWorkspace::BeginTrans](#begintrans)|Tüm veritabanları açık çalışma alanında uygulandığı yeni bir işlem başlatır.|  
|[CDaoWorkspace::Close](#close)|Çalışma alanı ve içerdiği nesnelerin tümünü kapatır. İşlemler geri alınacak.|  
|[CDaoWorkspace::CommitTrans](#committrans)|Geçerli işlem tamamlandıktan ve değişiklikleri kaydeder.|  
|[CDaoWorkspace::CompactDatabase](#compactdatabase)|Bir veritabanı sıkıştırır (veya yineleme).|  
|[CDaoWorkspace::Create](#create)|Yeni bir DAO çalışma nesnesi oluşturur.|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|DAO veritabanı nesnelerinin Workspace'in veritabanları koleksiyonunda döndürür.|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Çalışma Alanı'nın veritabanları koleksiyonunda tanımlanan belirtilen bir DAO veritabanı hakkında bilgi verir.|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Microsoft Jet veritabanı konumunu altyapısı başlatma ayarlarını Windows Kayıt Defteri'nde döndürür.|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Veri kaynağı için birden çok bağlantı zorla aynı ODBC veri kaynağını içeren birden çok işlem aracılığıyla yalıtılmış olup olmadığını belirten bir değer döndürür.|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Kullanıcı bir ODBC veritabanı oturum açmayı denediğinde bir hata gerçekleşmeden önce saniye sayısını döndürür.|  
|[CDaoWorkspace::GetName](#getname)|Çalışma alanı nesnesi kullanıcı tanımlı adını döndürür.|  
|[CDaoWorkspace::GetUserName](#getusername)|Belirtilen kullanıcı adı çalışma oluşturulduğu döndürür. Çalışma alanı sahibi adıdır.|  
|[CDaoWorkspace::GetVersion](#getversion)|Çalışma alanıyla ilişkili veritabanı altyapısı sürümünü içeren bir dize döndürür.|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|DAO çalışma nesne sayısı veritabanı altyapısının çalışma alanları koleksiyonu döndürür.|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Veritabanı altyapısının çalışma alanları koleksiyonu içinde tanımlanan belirtilen bir DAO çalışma alanı hakkında bilgi verir.|  
|[CDaoWorkspace::Idle](#idle)|Arka plan görevleri gerçekleştirmek veritabanı altyapısı sağlar.|  
|[CDaoWorkspace::IsOpen](#isopen)|Çalışma alanı ise, sıfır olmayan döndürür açın.|  
|[CDaoWorkspace::Open](#open)|Açıkça DAO'ın varsayılan çalışma alanıyla ilişkilendirilmiş bir çalışma alanı nesnesini açar.|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Bozuk bir veritabanını onarmak çalışır.|  
|[CDaoWorkspace::Rollback](#rollback)|Geçerli işlemi sonlandırır ve değişiklikleri kaydetmez.|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Veritabanı altyapısı belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda kullandığı parolayı ayarlar.|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Belirli bir kullanıcı adı bir çalışma alanı nesnesi oluşturulduğunda, veritabanı altyapısı kullandığı kullanıcı adını ayarlar.|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Microsoft Jet veritabanı konumunu altyapısı başlatma ayarlarını Windows Kayıt Defteri'nde ayarlar.|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Aynı ODBC veri kaynağını içeren birden çok işlem veri kaynağı için birden çok bağlantı zorlayarak yalıtılmış olup olmadığını belirtir.|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Kullanıcı bir ODBC veri kaynağında oturum denediğinde bir hata gerçekleşmeden önce saniye sayısını ayarlar.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|DAO çalışma nesnesini noktalarına.|  
  
## <a name="remarks"></a>Açıklamalar  
 Çoğu durumda, birden çok çalışma gerekmez ve açık çalışma nesneleri oluşturma gerekmez; Veritabanı ve kayıt kümesi nesneleri açtığınızda, bunlar DAO'ın varsayılan çalışma alanını kullanın. Ancak, gerekirse, birden çok oturumu aynı anda ek workspace nesneleri oluşturarak çalıştırabilirsiniz. Her çalışma nesne kendi veritabanlarını koleksiyonundaki birden fazla açık veritabanı nesnelerini içerebilir. MFC'de, öncelikle bir işlem yöneticisi, açık bir veritabanları kümesi tüm aynı "işlem alanı" belirten bir çalışma alanı olan  
  
> [!NOTE]
>  DAO veritabanı sınıfları açık veritabanı bağlantısı (ODBC) üzerinde tabanlı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekine sahip. Genel olarak, üzerinde DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıfları'den fazla özelliğine sahiptir. DAO tabanlı sınıflar ODBC sürücüleri dahil olmak üzere Microsoft Jet veritabanı altyapısı verilere erişir. Bunlar ayrıca veritabanları oluşturma ve tabloları ve alanları sınıfları aracılığıyla doğrudan çağırmak zorunda kalmadan ekleme gibi veri tanımlama dili (DDL) işlemleri desteklemez.  
  
## <a name="capabilities"></a>Özellikler  
 Sınıf `CDaoWorkspace` şunları sağlar:  
  
-   Gerekirse veritabanı motoru başlatma tarafından oluşturulan bir varsayılan çalışma alanı için açık erişim. Genellikle, DAO'ın varsayılan çalışma alanını örtük olarak veritabanı ve kayıt kümesi nesnelerini oluşturarak kullanın.  
  
-   İşlemler tüm veritabanları için geçerli bir işlem alanı çalışma alanında açın. Ayrı işlem alanları yönetmek için ek çalışma alanları oluşturabilirsiniz.  
  
-   Temel alınan Microsoft Jet Veritabanı Altyapısı'nın birçok özelliği için bir arabirim (statik üye işlevleri bakın). Açma veya bir çalışma alanı oluşturma ya da önce statik üye işlevi çağırma açmak veya oluşturmak, veritabanı altyapısı başlatır.  
  
-   Kendisine eklenmiş tüm etkin çalışma depolar veritabanı altyapısının çalışma alanları koleksiyonu erişim. Ayrıca, oluşturabilir ve koleksiyona ekleme olmadan bunlarda çalışma.  
  
## <a name="security"></a>Güvenlik  
 MFC kullanıcılar ve gruplar koleksiyonlar için güvenlik denetimi kullanılan DAO uygulamıyor. DAO yönlerini ihtiyacınız varsa, bunları kendiniz DAO arabirimleri doğrudan çağrıları aracılığıyla program gerekir. Bilgi için bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="usage"></a>Kullanım  
 Sınıf kullanabilirsiniz `CDaoWorkspace` için:  
  
-   Açıkça varsayılan çalışma alanını açın.  
  
     Genellikle, varsayılan çalışma alanı örtük kullanılmasıdır — yeni açtığınızda [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesneleri. Ancak, açıkça erişim gerekebilir — örneğin, access veritabanı altyapısı özellikleri veya çalışma alanları koleksiyonu için. Aşağıda "Varsayılan çalışma alanı örtülü kullanımı" konusuna bakın.  
  
-   Yeni çalışma alanı oluşturun. Çağrı [Append](#append) çalışma alanları koleksiyonu eklemek istiyorsanız.  
  
-   Çalışma alanları koleksiyonu varolan bir çalışma alanını açın.  
  
 Yeni bir çalışma alanı oluşturma zaten yok koleksiyonudur altında açıklanan çalışma alanlarında [oluşturma](#create) üye işlevi. Çalışma alanı nesnelerini datababase altyapısı oturumları arasında herhangi bir şekilde devam etmez. Uygulamanızı MFC statik olarak bağlanıyorsa, uygulama bitiş veritabanı altyapısı uninitializes. MFC DLL kaldırıldığında, uygulamanızın MFC ile dinamik olarak bağlanıyorsa, veritabanı altyapısı başlatılmadı.  
  
 Açıkça varsayılan çalışma alanını açmak veya çalışma alanları koleksiyonu içinde varolan bir çalışma alanı açılırken açıklanmaktadır altında [açık](#open) üye işlevi.  
  
 Çalışma alanıyla kapatarak çalışma sona erdirmek [Kapat](#close) üye işlevi. **Kapat** olmayan kapattığınız daha önce kaydedilmemiş işlemler geri veritabanları kapatır.  
  
## <a name="transactions"></a>İşlemler  
 DAO çalışma düzeyinde işlemler yönetir; Bu nedenle, bir çalışma alanında birden çok açık veritabanlarıyla işlemleri tüm veritabanları için geçerlidir. Örneğin, iki veritabanları sahip kaydedilmemiş güncelleştirmeleri ve çağırır [CommitTrans](#committrans), tüm güncelleştirmeler uygulanır. Tek bir veritabanı için işlemler sınırlamak istiyorsanız, ayrı çalışma nesne için ihtiyacınız.  
  
## <a name="implicit-use-of-the-default-workspace"></a>Varsayılan çalışma alanı örtülü kullanımı  
 MFC DAO'ın varsayılan çalışma alanı aşağıdaki koşullarda örtük olarak kullanır:  
  
-   Yeni bir oluşturursanız `CDaoDatabase` nesne ancak bunu varolan aracılığıyla yapmayın `CDaoWorkspace` MFC bir geçici çalışma nesnesi oluşturur, DAO'ın varsayılan çalışma alanı için karşılık gelen nesne. Birden çok veritabanı için bunu yaparsanız, tüm veritabanı nesnelerinin varsayılan çalışma alanıyla ilişkilendirilir. Bir veritabanının çalışma alanını kullanarak erişebileceğiniz bir `CDaoDatabase` veri üyesi.  
  
-   Benzer şekilde, oluşturursanız, bir `CDaoRecordset` gösteren bir işaretçi sağladığını olmadan nesnesi bir `CDaoDatabase` nesnesi, MFC bir geçici veritabanı nesnesi oluşturur ve uzantılarının, bir geçici çalışma nesnesi. Bir kayıt kümesinin veritabanı ve dolaylı olarak, çalışma alanı üzerinden erişebilirsiniz bir `CDaoRecordset` veri üyesi.  
  
## <a name="other-operations"></a>Diğer işlemleri  
 Bozuk bir veritabanını onararak veya bir veritabanı sıkıştırılmasını gibi diğer veritabanı işlemleri de sağlanır.  
  
 DAO güvenlik ve DAO'yu doğrudan çağırma hakkında bilgi için bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
##  <a name="append"></a>CDaoWorkspace::Append  
 Çağırdıktan sonra bu üye işlevini çağırın [oluşturma](#create).  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Açıklamalar  
 **Append** veritabanı altyapısının çalışma alanları koleksiyonu için yeni oluşturulan çalışma nesnesi ekler. Çalışma alanı veritabanı altyapısı oturumları arasında kalmaz; bellek, disk üzerinde değil, yalnızca depolanır. Bir çalışma alanı eklemek zorunda değildir; Bunu yapmazsanız, onu kullanmaya devam edebilirsiniz.  
  
 Çağrısı tamamlanana kadar eklenmiş bir çalışma alanı çalışma alanları koleksiyonu etkin bir açık durumda kalır, [Kapat](#close) üye işlevi.  
  
 İlgili bilgi için DAO Yardımı'ndaki "yöntemi ekleme" konusuna bakın.  
  
##  <a name="begintrans"></a>CDaoWorkspace::BeginTrans  
 Bir işlemi başlatmak için bu üye işlevini çağırın.  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırdıktan sonra **BeginTrans**, işlem yaparsanız, verileri veya veritabanı yapısına yaptığınız güncelleştirmeler etkili. Çalışma tek işlem alanı tanımladığından, işlem çalışma alanındaki tüm açık veritabanları için geçerlidir. İşlemi tamamlamak için iki yolu vardır:  
  
-   Çağrı [CommitTrans](#committrans) hareketi ve veri kaynağına değişiklikleri kaydetmek için üye işlevi.  
  
-   Veya arama [geri alma](#rollback) işlem iptal etmek için üye işlevi.  
  
 Bir işlem beklemedeyken workspace nesnesi veya bir veritabanı nesnesi kapatarak tüm bekleyen işlemleri geri alır.  
  
 Başka bir ODBC veri kaynağı üzerinde olanlardan bir ODBC veri kaynağında işlemleri yalıtmak gerekiyorsa, bkz: [SetIsolateODBCTrans](#setisolateodbctrans) üye işlevi.  
  
##  <a name="cdaoworkspace"></a>CDaoWorkspace::CDaoWorkspace  
 Oluşturan bir `CDaoWorkspace` nesnesi.  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>Açıklamalar  
 C++ nesnesini oluşturduktan sonra iki seçeneğiniz vardır:  
  
-   Nesnenin çağrı [açmak](#open) üye işlevi varsayılan çalışma alanını açın veya varolan bir nesne içinde çalışma alanları koleksiyonu açmak için.  
  
-   Veya nesnenin çağrısı [oluşturma](#create) yeni bir DAO çalışma nesnesi oluşturmak için üye işlevi. Bu açıkça aracılığıyla başvurabilirsiniz yeni bir çalışma alanı oturumu başlatır `CDaoWorkspace` nesnesi. Çağırdıktan sonra **oluşturma**, çağırabilirsiniz [Append](#append) çalışma alanı veritabanı altyapısının çalışma alanları koleksiyonu eklemek istiyorsanız.  
  
 Sınıfına genel bakış için bkz: [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) açıkça oluşturmak gerektiğinde hakkında bilgi için bir `CDaoWorkspace` nesnesi. Açtığınızda örtük olarak oluşturulmuş çalışma alanları genellikle, kullandığınız bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesi açtığınızda veya bir çalışma alanı belirtmeden bir [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) bir veritabanı nesnesi belirtmeden nesnesi. Bu yolla oluşturulan MFC DAO nesneler oluşturulduktan sonra ve yeniden DAO'ın varsayılan çalışma alanını kullanın.  
  
 Bir çalışma alanı ve içerdiği nesneler serbest bırakmak için çalışma alanı nesnenin çağrısı [Kapat](#close) üye işlevi.  
  
##  <a name="close"></a>CDaoWorkspace::Close  
 Çalışma alanı nesnesi kapatmak için bu üye işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bir açık çalışma nesne kapatma DAO nesnesini serbest bırakır ve çalışma alanı çalışma alanları koleksiyonu üyesiyse koleksiyondan kaldırır. Çağırma **Kapat** uygulama programlama iyidir.  
  
> [!CAUTION]
>  Bir çalışma alanı nesnesi kapatma çalışma alanında açık bir veritabanınız kapatır. Bu da kapatılan veritabanlarındaki tüm kayıt kümeleri Aç sonuçlanır ve herhangi bir bekleyen düzenlemeler veya güncelleştirmeleri geri alındı. İlgili bilgi için bkz: [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), ve [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) üye işlevleri.  
  
 Çalışma alanı nesneleri kalıcı değildir; Bunlar yalnızca bunları başvurular varken mevcut. Bu, veritabanı altyapısı oturumu sona erdiğinde, çalışma alanı ve veritabanı koleksiyonu devam etmeyen olduğunu anlamına gelir. Bunları bir sonraki oturumu için yeniden çalışma ve veritabanları açarak yeniden oluşturmanız gerekir.  
  
 İlgili bilgiler için "Kapat yönteminde" DAO Yardım konusuna bakın.  
  
##  <a name="committrans"></a>CDaoWorkspace::CommitTrans  
 Bir işlem gerçekleştirmeyi bu üye işlevini çağırın — çalışma alanında bir veya daha fazla veritabanı için bir grup düzenlemeleri ve güncelleştirmeleri kaydedin.  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanı verileri veya bir çağrı itibaren yapısını değişiklikler dizisini bir işlem oluşan [BeginTrans](#begintrans). İşlem tamamlandığında veya geri alma ya da Yürüt (değişiklikleri iptal et) ile [geri alma](#rollback). Varsayılan olarak, işlemler, olmadan kayıtları güncelleştirmeleri hemen kabul edilir. Çağırma **BeginTrans** çağırmanız kadar Gecikmeli taahhüt güncelleştirmelerin neden **CommitTrans**.  
  
> [!CAUTION]
>  Bir çalışma alanı içindeki işlemler her zaman için çalışma alanına genel ve yalnızca bir veritabanı veya kayıt kümesi sınırlı değildir. Birden fazla veritabanı veya bir çalışma alanı işlem içinde kayıt kümesi gerçekleştirirseniz **CommitTrans** tüm bekleyen güncelleştirmeleri, yürütme ve **geri alma** bu veritabanlarını tüm işlemler geri yükler ve kayıt kümeleri.  
  
 Bir veritabanı veya bekleyen işlemler çalışma alanıyla kapattığınızda, işlemler tümü geri alınır.  
  
> [!NOTE]
>  Bu iki aşamalı yürütme mekanizması değildir. Kaydetmek bir güncelleştirme başarısız olursa, diğerleri hala yürütme.  
  
##  <a name="compactdatabase"></a>CDaoWorkspace::CompactDatabase  
 Belirtilen Microsoft Jet sıkıştırmak için bu üye işlevini çağırın (. MDB) veritabanı.  
  
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
 `lpszSrcName`  
 Var olan ad veritabanı kapatıldı. Bu tam yolunu ve dosya adı, aşağıdaki gibi olabilir "C:\\\MYDB. MDB". Dosya adı uzantısına sahip değilse, belirtmeniz gerekir. Ağınız Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, aynı zamanda bir ağ yolu gibi belirtebilirsiniz "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi olduğundan yolu dizelerde gerekli "\\" C++ kaçış karakteri.)  
  
 `lpszDestName`  
 Oluşturmakta olduğunuz sıkıştırılmış veritabanı tam yolu. İle bir ağ yolu da belirtebilirsiniz `lpszSrcName`. Kullanamazsınız `lpszDestName` bağımsız olarak aynı veritabanı dosyasını belirtmek için `lpszSrcName`.  
  
 `lpszPassword`  
 Parola korumalı bir veritabanını istediğinizde kullanılan bir parola. Sürümünü kullanıyorsanız, Not `CompactDatabase` parola alan, tüm parametreler sağlamanız gerekir. Bu bağlantı parametresi olduğundan, ayrıca, özel, aşağıdaki gibi biçimlendirme gerekiyor:; PWD = `lpszPassword`. Örneğin:; PWD = "Mutlu". (Başında noktalı virgül gereklidir.)  
  
 `lpszLocale`  
 Oluşturma için harmanlama sırası belirtmek için kullanılan bir dize ifadesi `lpszDestName`. Bu bağımsız değişkeni, ihmal varsayılan değerini kabul ederek **dbLangGeneral** (aşağıya bakın), yeni bir veritabanı yerel eski veritabanının aynıdır. Olası değerler şunlardır:  
  
- **dbLangGeneral** İngilizce, Almanca, Fransızca, Portekizce, İtalyanca ve Modern İspanyolca  
  
- **dbLangArabic** Arapça  
  
- **dbLangCyrillic** Rusça  
  
- **dbLangCzech** Çekçe  
  
- **dbLangDutch** Hollanda dili  
  
- **dbLangGreek** Yunanca  
  
- **dbLangHebrew** İbranice  
  
- **dbLangHungarian** Macarca  
  
- **dbLangIcelandic** İzlanda  
  
- **dbLangNordic** Kuzey Dilleri (yalnızca Microsoft Jet veritabanı altyapısı sürüm 1.0)  
  
- **dbLangNorwdan** Norveççe ve Danca  
  
- **dbLangPolish** Lehçe  
  
- **dbLangSpanish** geleneksel İspanyolca  
  
- **dbLangSwedfin** İsveççe ve Fince  
  
- **dbLangTurkish** Türkçe  
  
 `nOptions`  
 Hedef veritabanı için bir veya daha fazla seçenekleri gösterir `lpszDestName`. Varsayılan değer kabul ederek bu bağımsız değişken atlarsanız `lpszDestName` aynı şifreleme ve aynı sürüme sahip `lpszSrcName`. Birleştirebilirsiniz **dbEncrypt** veya **dbDecrypt** Bitsel veya işlecini kullanarak sürüm seçeneklerden birini seçeneğiyle. Bir veritabanı altyapısı sürümünü değil, veritabanı bir biçim belirtin olası değerler şunlardır:  
  
- **dbEncrypt** sıkıştırma sırasında veritabanı şifreleyin.  
  
- **dbDecrypt** sıkıştırma sırasında veritabanı şifresini.  
  
- **dbVersion10** sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.0 kullanan bir veritabanı oluşturun.  
  
- **dbVersion11** sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 1.1 kullanan bir veritabanı oluşturun.  
  
- **dbVersion20** sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 2.0 kullanan bir veritabanı oluşturun.  
  
- **dbVersion30** sıkıştırma sırasında Microsoft Jet veritabanı altyapısı sürüm 3.0 kullanan bir veritabanı oluşturun.  
  
 Kullanabileceğiniz **dbEncrypt** veya **dbDecrypt** şifrelemek mi, yoksa sıkıştırıldıktan gibi veritabanı şifresini çözmek için belirtmek için Seçenekler bağımsız. Bir şifreleme sabiti atlarsanız veya her ikisi de dahil ederseniz **dbDecrypt** ve **dbEncrypt**, `lpszDestName` aynı şifrelemeye sahip `lpszSrcName`. Sıkıştırılmış veritabanı için veri biçimi sürümü belirtmek için Seçenekler bağımsız değişkeninde sürüm sabitleri birini kullanabilirsiniz. Yalnızca veri biçimi sürümü bu sabiti etkiler `lpszDestName`. Yalnızca bir sürümü sabiti belirtebilirsiniz. Sürüm sabiti atlarsanız `lpszDestName` aynı sürüme sahip `lpszSrcName`. Sıkıştırabilirsiniz `lpszDestName` aynı olan bir sürüme veya daha sonraki bir sürümü `lpszSrcName`.  
  
> [!CAUTION]
>  Bir veritabanı şifrelenmezse, doğrudan veritabanı oluşturduğunu ikili disk dosyası okumak için kullanıcı/parola güvenlik uygulamak olsa bile, mümkündür.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanındaki verileri değiştirme gibi veritabanı dosyası parçalanabilir ve gerekirse daha fazla disk alanı kullanın. Düzenli aralıklarla, veritabanı dosyasını birleştirmek üzere veritabanınızı sıkıştırmanız gerekir. Sıkıştırılmış veritabanı genellikle daha küçüktür. Harmanlama sırası, şifreleme veya veri biçimi sürümü kopyalamak ve veritabanını değiştirmek seçebilirsiniz.  
  
> [!CAUTION]
>  `CompactDatabase` Üye işlevi tarafından değil doğru dönüştürülür tam bir Microsoft Access veritabanına bir sürümünden diğerine. Yalnızca veri biçimi dönüştürülür. Microsoft Access tanımlanan nesneleri, formlar ve raporlar gibi dönüştürülmez. Ancak, verileri doğru dönüştürülür.  
  
> [!TIP]
>  Aynı zamanda `CompactDatabase` bir veritabanı dosyası kopyalanamadı.  
  
 Sıkıştırma veritabanları hakkında daha fazla bilgi için DAO Yardımı'ndaki "CompactDatabase yöntemi" konusuna bakın.  
  
##  <a name="create"></a>CDaoWorkspace::Create  
 Yeni bir DAO workspace nesnesini oluşturmak ve MFC ile ilişkilendirmek için bu üye işlevini çağırın `CDaoWorkspace` nesnesi.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Yeni çalışma nesnesini benzersiz olarak adlandıran bir dizeyle 14 karaktere kadar. Bir ad girmeniz gerekir. İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 *lpszUserName*  
 Çalışma Alanı'nın sahibi kullanıcı adı. Gereksinimleri için bkz `lpszDefaultUser` parametresi [SetDefaultUser](#setdefaultuser) üye işlevi. İlgili bilgi için DAO Yardımı'ndaki "UserName özelliği" konusuna bakın.  
  
 `lpszPassword`  
 Yeni çalışma nesne parolası. Parola 14 karakterden uzun olamaz ve ASCII 0 (boş) dışında herhangi bir karakter içermelidir. Parolalar büyük/küçük harfe duyarlıdır. İlgili bilgi için "Parola özelliğinde" DAO Yardım konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Genel oluşturma işlemi şöyledir:  
  
1.  Oluşturmak bir [CDaoWorkspace](#cdaoworkspace) nesnesi.  
  
2.  Nesnenin çağrı **oluşturma** temel DAO çalışma alanı oluşturmak için üye işlevi. Bir çalışma alanı adı belirtmeniz gerekir.  
  
3.  İsteğe bağlı olarak çağrı [Append](#append) çalışma alanı veritabanı altyapısının çalışma alanları koleksiyonu eklemek istiyorsanız. Sonuna ekleme olmadan çalışma alanıyla çalışabilir.  
  
 Sonra **oluşturma** çağrısı, çalışma alanı nesnedir kullanıma hazır bir açık durumda. Arama **açık** sonra **oluşturma**. Arama **oluşturma** çalışma çalışma alanları koleksiyonu içinde zaten varsa. **Oluşturma** , zaten uygulamanız için başlatılmadı, veritabanı altyapısı başlatır.  
  
##  <a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount  
 DAO veritabanı nesnelerini Workspace'in veritabanları koleksiyonundaki sayısını almak için bu üye işlevini çağırın — çalışma alanında açık veritabanı sayısı.  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışma alanında açık veritabanı sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetDatabaseCount`Çalışma Alanı'nın veritabanları koleksiyonundaki tüm tanımlı veritabanları döngü gerektiğinde kullanışlı olur. Koleksiyonda verilen bir veritabanı hakkında bilgi edinmek için bkz: [GetDatabaseInfo](#getdatabaseinfo). Tipik kullanım çağırmaktır `GetDatabaseCount` açık veritabanı sayısı için ardından bu sayıyı döngü dizini olarak yinelenen çağrılar için kullanmak `GetDatabaseInfo`.  
  
##  <a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo  
 Çeşitli veritabanı açık çalışma hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 `nIndex`  
 Çalışma Alanı'nın veritabanları koleksiyondaki, dizine göre arama veritabanı nesnesinin sıfır tabanlı dizini.  
  
 `dbinfo`  
 Bir başvuru bir [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için veritabanını belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Ad, güncelleştirilebilir, işlemleri  
  
- `AFX_DAO_SECONDARY_INFO`Birincil bilgileri artı: sürüm, harmanlama sırası, sorgu zaman aşımı  
  
- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgi artı: bağlanma  
  
 `lpszName`  
 Ada göre arama veritabanı nesnesinin adı. Yeni çalışma nesne adlandıran 14 karaktere kadar bir dizeyle adıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlevi bir sürümü, bir veritabanı dizini tarafından ara olanak tanır. Başka bir sürüm bir veritabanını adına göre aramak olanak sağlar.  
  
 Döndürülen bilgi açıklaması `dbinfo`, bkz: [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istemek için de önceki tüm düzeylerde bilgi alın.  
  
##  <a name="getinipath"></a>CDaoWorkspace::GetIniPath  
 Microsoft Jet veritabanı konumunu altyapısı başlatma ayarlarını Windows kayıt defterinde almak için bu üye işlevini çağırın.  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) içeren kayıt defteri konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Veritabanı Altyapısı için ayarları hakkında bilgi edinmek için konumu kullanabilirsiniz. Döndürülen bilgi gerçekte bir kayıt defteri alt anahtarı adıdır.  
  
 İlgili bilgi için "IniPath özelliği" ve "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konularına bakın.  
  
##  <a name="getisolateodbctrans"></a>CDaoWorkspace::GetIsolateODBCTrans  
 DAO IsolateODBCTrans özelliğinin geçerli değeri için çalışma almak için bu üye işlevini çağırın.  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ODBC işlemleri yalıtılmış olması durumunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bazı durumlarda, bekleyen birden çok eşzamanlı işlem aynı ODBC veritabanı üzerinde olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma kendi ODBC bağlantısı veritabanına sahip olabilirsiniz, ancak bu sistem performansını yavaşlatır göz önünde bulundurun. ODBC bağlantıları aynı kullanıcı tarafından açılmış birden çok çalışma alanı nesnelerinden işlem yalıtım normalde gerekli olmadığından, varsayılan olarak paylaşılır.  
  
 Microsoft SQL Server gibi bazı ODBC sunucuları tek bir bağlantı üzerinde eşzamanlı işlemlere izin vermez. Bu tür bir veritabanında bir seferde birden fazla işlem değiştirilmesi gerekiyorsa, IsolateODBCTrans özelliğini ayarlamak **TRUE** açmadan hemen her çalışma alanında. Bu, her çalışma alanı için ayrı bir ODBC bağlantı zorlar.  
  
 İlgili bilgi için DAO Yardımı'ndaki "IsolateODBCTrans özelliği" konusuna bakın.  
  
##  <a name="getlogintimeout"></a>CDaoWorkspace::GetLoginTimeout  
 DAO LoginTimeout özelliğinin geçerli değeri için çalışma almak için bu üye işlevini çağırın.  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir ODBC veritabanı oturum açmayı denediğinizde bir hata gerçekleşmeden önce saniye sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer bir ODBC veritabanı oturum açmayı denediğinizde bir hata gerçekleşmeden önce saniye sayısını temsil eder. Varsayılan LoginTimeout 20 saniye ayardır. LoginTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı gerçekleşir ve veri kaynağı ile iletişimi yanıt vermeyebilir.  
  
 Microsoft SQL Server gibi bir ODBC veritabanı oturum çalışılırken bağlantı ağ hataları nedeniyle başarısız olabilir veya Sunucu çalışmadığı için. Bağlanmak için 20 saniye için varsayılan beklemek yerine bir hata üretir önce veritabanı altyapısı ne kadar bekleyeceğini belirtebilirsiniz. Sunucuya oturum açmayı örtük olarak bir dış sunucu veritabanında bir sorgu çalıştırılarak gibi farklı olay sayısı'nın bir parçası olarak gerçekleşir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "LoginTimeout özelliği" konusuna bakın.  
  
##  <a name="getname"></a>CDaoWorkspace::GetName  
 DAO çalışma nesnesinin altındaki kullanıcı tanımlı adı almak için bu üye işlevini çağırın `CDaoWorkspace` nesnesi.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) DAO workspace nesnesi kullanıcı tanımlı adını içeren.  
  
### <a name="remarks"></a>Açıklamalar  
 Adı, veritabanı altyapısının çalışma alanları koleksiyonu DAO çalışma nesnesinde adıyla erişmek için yararlıdır.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
##  <a name="getusername"></a>CDaoWorkspace::GetUserName  
 Çalışma alanının sahibinin adını almak için bu üye işlevini çağırın.  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) çalışma nesnenin sahibi temsil eden.  
  
### <a name="remarks"></a>Açıklamalar  
 Almak veya çalışma alanı sahibi izinlerini ayarlamak için doğrudan izinleri özellik ayarını denetlemek için çağırmak; Bu izinleri belirler kullanıcının sahip. İzinler ile çalışmak için bir sistem gerekir. MDA dosyası.  
  
 Doğrudan çağırma DAO hakkında bilgi için bkz [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). İlgili bilgi için DAO Yardımı'ndaki "UserName özelliği" konusuna bakın.  
  
##  <a name="getversion"></a>CDaoWorkspace::GetVersion  
 Microsoft Jet veritabanı altyapısı kullanımda sürümünü belirlemek için bu üye işlevini çağırın.  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) nesnesiyle ilişkili veritabanı altyapısı sürümünü gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer "major.minor"; formunda sürüm numarasını temsil eder Örneğin, "3.0". Ürün sürüm numarası (örneğin, 3.0) sürüm numarası (3), nokta ve sürüm numarasını (0) oluşur.  
  
 İlgili bilgi için DAO Yardımı'ndaki "Version özelliği" konusuna bakın.  
  
##  <a name="getworkspacecount"></a>CDaoWorkspace::GetWorkspaceCount  
 Veritabanı altyapısının çalışma alanları koleksiyonu DAO çalışma nesnelerin sayısı almak için bu üye işlevini çağırın.  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışma alanları koleksiyonu açık çalışma alanlarının sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sayı koleksiyona eklenmemiş açık çalışma alanları içermez. `GetWorkspaceCount`çalışma alanları koleksiyonu içinde tanımlanan tüm çalışma alanları arasında döngü gerektiğinde kullanışlı olur. Bir koleksiyondaki belirli bir çalışma alanı hakkında bilgi edinmek için bkz: [GetWorkspaceInfo](#getworkspaceinfo). Tipik kullanım çağırmaktır `GetWorkspaceCount` sayıda açık çalışma alanları için sonra bu sayıyı döngü dizini olarak yinelenen çağrılar için kullanmak `GetWorkspaceInfo`.  
  
##  <a name="getworkspaceinfo"></a>CDaoWorkspace::GetWorkspaceInfo  
 Çeşitli oturumunda çalışma açma hakkında bilgi edinmek için bu üye işlevini çağırın.  
  
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
 `nIndex`  
 Dizine göre arama için çalışma alanları koleksiyonu veritabanı nesnesinde sıfır tabanlı dizini.  
  
 `wkspcinfo`  
 Bir başvuru bir [Cdaoworkspaceınfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) istenen bilgileri döndürür nesnesi.  
  
 `dwInfoOptions`  
 Hangi bilgilerini almak için çalışma belirtin seçenekleri. Kullanılabilir seçenekler, hangi kullanıcıların işlevi döndürecek şekilde neden birlikte aşağıda listelenmiştir:  
  
- `AFX_DAO_PRIMARY_INFO`(Varsayılan) Adı  
  
- `AFX_DAO_SECONDARY_INFO`Artı birincil bilgileri: kullanıcı adı  
  
- `AFX_DAO_ALL_INFO`Birincil ve ikincil bilgi artı: yalıtmak ODBCTrans  
  
 `lpszName`  
 Ada göre arama workspace nesnesinin adı. Yeni çalışma nesne adlandıran 14 karaktere kadar bir dizeyle adıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen bilgi açıklaması `wkspcinfo`, bkz: [Cdaoworkspaceınfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) yapısı. Bu yapı bilgileri açıklaması, yukarıda listelenen öğelerin karşılık üyeler içeriyor `dwInfoOptions`. Bir düzeyde bilgi istediklerinde, önceki düzeyler için bilgi alın.  
  
##  <a name="idle"></a>CDaoWorkspace::Idle  
 Çağrı **boşta** veritabanı altyapısı nedeniyle yoğun veri işleme güncel olmayabilir arka plan görevleri gerçekleştirme olanağı sağlamak için.  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>Parametreler  
 `nAction`  
 Boşta işleme sırasında gerçekleştirilecek bir eylem. Şu anda yalnızca geçerli bir bölüm eylemdir **dbFreeLocks**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu genellikle olduğu olmayan bir kayıt kümesindeki tüm kayıtlar güncel tutmak için yeterli arka plan işleme zamanı çok kullanıcılı, Çoklu ortamlarda geçerlidir.  
  
> [!NOTE]
>  Çağırma **boşta** Microsoft Jet veritabanı altyapısı 3.0 sürümü ile oluşturulan veritabanları ile gerekli değildir. Kullanım **boşta** yalnızca daha önceki sürümleriyle oluşturulan veritabanları için.  
  
 Genellikle, okuma kilitleri kaldırılır ve yerel dynaset türündeki kayıt kümesi nesneleri verileri güncelleştirilir (fare hareketleri dahil) herhangi bir eylem yalnızca yaşanan olduğunda. Düzenli aralıklarla çağırırsanız **boşta**, arka plan görevleri bırakarak işlemleri Yakala süresiyle veritabanı altyapısı kilitleri okuma sağlayın. Belirtme **dbFreeLocks** sabit bir bağımsız değişken olarak gecikmeler tüm okuma kilitler serbest bırakılana kadar işleme.  
  
 Bir uygulama birden çok örneğini çalıştırmadığınız sürece bu üye işlevi tek kullanıcı ortamlarda gerekli değildir. **Boşta** bellek kilitler serbest diske verileri temizlemek için veritabanı altyapısı zorladığından, üye işlevi çok kullanıcılı ortamda performansını artırmak. Bir işlemin parçası işlemleri yaparak, okuma kilitleri serbest bırakabilirsiniz.  
  
 İlgili bilgi için DAO Yardımı'ndaki "yöntemi boşta" konusuna bakın.  
  
##  <a name="isopen"></a>CDaoWorkspace::IsOpen  
 Belirlemek için bu üye işlevini çağırın olup olmadığını `CDaoWorkspace` nesnesidir açık — diğer bir deyişle, olup MFC nesne için bir çağrı tarafından başlatıldı [açmak](#open) veya yapılan bir çağrı [oluşturma](#create).  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Çalışma alanı nesne açıksa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Herhangi bir üyenin bir açık durumda bir çalışma alanının işlevleri çağırabilir.  
  
##  <a name="m_pdaoworkspace"></a>CDaoWorkspace::m_pDAOWorkspace  
 DAO çalışma nesnesini bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 DAO nesnesini erişimi doğrudan, bu veri üyesi kullanın. Bu işaretçinin DAO nesnenin arabirimlerde çağırabilirsiniz.  
  
 DAO nesneleri doğrudan erişme hakkında daha fazla bilgi için bkz: [Teknik Not 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="open"></a>CDaoWorkspace::Open  
 Açıkça DAO'ın varsayılan çalışma alanıyla ilişkilendirilmiş bir çalışma alanı nesnesini açar.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Açmak için DAO çalışma nesnesinin adı — çalışma adlandıran bir dizeyle 14 karaktere kadar. Varsayılan değeri kabul **NULL** açıkça varsayılan çalışma alanını açın. Adlandırma gereksinimlerini bkz `lpszName` parametresi için [oluşturma](#create). İlgili bilgi için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturma sonrasında bir `CDaoWorkspace` nesne, aşağıdakilerden birini yapmak için bu üye işlevini çağırın:  
  
-   Açıkça varsayılan çalışma alanını açın. Geçirmek **NULL** için `lpszName`.  
  
-   Mevcut bir açık `CDaoWorkspace` nesnesi, ada göre çalışma alanları koleksiyonu üyesi. Varolan bir çalışma alanı nesnesi için geçerli bir ad verin.  
  
 **Açık** workspace nesnesi açık bir duruma koyar ve onu zaten uygulamanız için başlatılmadı, veritabanı altyapısı da başlatır.  
  
 Ancak birçok `CDaoWorkspace` işlevleri yalnızca çalışma açıldıktan sonra çağrılabilir üye veritabanı altyapısı üzerinde çalışan aşağıdaki üye işlevleri kullanılabilir yapım C++ nesnesinin ancak yapılan bir çağrı önce sonra **Aç** :  
  
||||  
|-|-|-|  
|[Oluşturma](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[Boşta](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="repairdatabase"></a>CDaoWorkspace::RepairDatabase  
 Microsoft Jet veritabanı altyapısı erişen bozuk bir veritabanı onarmayı gerekiyorsa bu üye işlevini çağırın.  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszName`  
 Bir Microsoft Jet altyapısı veritabanı dosyası için dosya adı ve yolu. Yolun atlarsanız, yalnızca geçerli dizin aranır. Sisteminiz Tekdüzen Adlandırma Kuralı (UNC) destekliyorsa, aynı zamanda bir ağ yolu gibi belirtebilirsiniz: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Çift ters eğik çizgi, yol dizesi gereklidir, çünkü "\\" C++ kaçış karakteri.)  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen veritabanı kapatmalısınız `lpszName` onu onarmak önce. Çok kullanıcılı bir ortamda, diğer kullanıcıların olamaz `lpszName` onarma sırada açın. Varsa `lpszName` kapalı veya bir hata oluştuğunda özel kullanım için kullanılabilir değil.  
  
 Bu üye işlevi tamamlanmamış yazma işlemi tarafından bozuk olarak işaretlenmiş bir veritabanını onarmak çalışır. Microsoft Jet veritabanı altyapısı kullanarak bir uygulama bir güç kesintisi veya bilgisayarın donanım sorunu nedeniyle beklenmedik şekilde kapatılmışsa, bu durum oluşabilir. İşlem ve çağrı tamamlarsanız [Kapat](../../mfc/reference/cdaodatabase-class.md#close) üye işlevi veya normal bir şekilde uygulama çıkın, veritabanı bozuk olarak işaretlenmez.  
  
> [!NOTE]
>  Bir veritabanını onararak sonra onu da kullanarak sıkıştırmak için iyi bir fikirdir [CompactDatabase](#compactdatabase) üye işlevi dosya birleştirme ve disk alanını kurtarmak için.  
  
 Veritabanları onarma hakkında daha fazla bilgi için DAO Yardımı'ndaki "RepairDatabase yöntemi" konusuna bakın.  
  
##  <a name="rollback"></a>CDaoWorkspace::Rollback  
 Geçerli işlem sonlandırmak ve işlem başladığı önce çalışma alanındaki tüm veritabanlarını kendi durumuna geri yüklemek için bu üye işlevini çağırın.  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!CAUTION]
>  Bir çalışma alanı nesnedeki işlemler her zaman için çalışma alanına genel ve yalnızca bir veritabanı veya kayıt kümesi sınırlı değildir. Birden fazla veritabanı veya bir çalışma alanı işlem içinde kayıt kümesi gerçekleştirirseniz **geri alma** tüm bu veritabanlarını ve kayıt kümeleri tüm işlemler geri yükler.  
  
 Bir çalışma alanı nesnesi kaydetmeden veya bekleyen işlemler geri kapatırsanız, işlemleri otomatik olarak geri alınır. Çağırırsanız [CommitTrans](#committrans) veya **geri alma** ilk çağırmadan [BeginTrans](#begintrans), bir hata oluşur.  
  
> [!NOTE]
>  Bir işlem başladığınızda, veritabanı altyapısı işlemlerini iş istasyonunda TEMP ortam değişkeni tarafından belirtilen dizininde tutulan dosyasına kaydeder. İşlem günlüğü dosyasını TEMP diskinizde kullanılabilir depolama alanı aşarsa, veritabanı altyapısı throw MFC neden olacak bir `CDaoException` (DAO hata 2004). Çağırırsanız bu noktada **CommitTrans**belirsiz sayıda işlem uygulanır, ancak kalan tamamlanmamış işlemler kaybolur ve işlemi yeniden başlatılması gerekiyor. Çağırma **geri alma** işlem günlüğü serbest bırakır ve tüm işlemler işlem geri alınır.  
  
##  <a name="setdefaultpassword"></a>CDaoWorkspace::SetDefaultPassword  
 Belirli bir parola olmadan bir çalışma alanı nesnesi oluşturulduğunda, veritabanı altyapısı kullanan varsayılan parolayı ayarlamak için bu üye işlevini çağırın.  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszPassword`  
 Varsayılan parola. Parola 14 karakterden uzun olamaz ve ASCII 0 (boş) dışında herhangi bir karakter içermelidir. Parolalar büyük/küçük harfe duyarlıdır.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrısından sonra oluşturduğunuz yeni çalışma alanları için ayarladığınız varsayılan parola geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, bir parola belirtmeniz gerekmez [oluşturma](#create) çağırın.  
  
 Bu üye işlevini kullanmak için:  
  
1.  Oluşturmak bir `CDaoWorkspace` nesne ancak çağırmayın **oluşturma**.  
  
2.  Çağrı `SetDefaultPassword` ve isterseniz, [SetDefaultUser](#setdefaultuser).  
  
3.  Çağrı **oluşturma** bu çalışma nesne veya sonraki olanlar için bir parola belirtilmeden.  
  
 Varsayılan olarak, DefaultUser özelliği "Yönetici"'ye ayarlanır ve DefaultPassword özelliği boş bir dize ("").  
  
 Güvenlik hakkında daha fazla bilgi için DAO Yardımı'ndaki "izinleri özellik" konusuna bakın. İlgili bilgi için "DefaultPassword özelliği" ve "DefaultUser özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="setdefaultuser"></a>CDaoWorkspace::SetDefaultUser  
 Belirli bir kullanıcı adı bir çalışma alanı nesnesi oluşturulduğunda, veritabanı altyapısı kullandığı varsayılan kullanıcı adını ayarlamak için bu üye işlevini çağırın.  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszDefaultUser`  
 Varsayılan kullanıcı adı. Bir kullanıcı adı 1-20 karakter uzunluğunda olmalı ve alfasayısal karakterler, aksanlı karakterler, sayılar, alanları ve simgeleri dışında içerir: "(tırnak işaretleri) / (eğik çizgi), \ (ters eğik çizgi) \[ \] (köşeli ayraç): (iki nokta üst üste), &#124; (kanal) \< (daha az-oturum daha), > (büyük-oturum daha), + (artı işareti) = (eşittir işareti), (noktalı), (virgül) (soru işareti) * (, boşluk ve denetim karakterleri (ASCII 00 ile ASCII 31) yol yıldız işareti). İlgili bilgi için DAO Yardımı'ndaki "UserName özelliği" konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrısından sonra oluşturduğunuz yeni çalışma alanları için ayarladığınız varsayılan kullanıcı adı geçerlidir. Sonraki çalışma alanları oluşturduğunuzda, bir kullanıcı adı belirtmeniz gerekmez [oluşturma](#create) çağırın.  
  
 Bu üye işlevini kullanmak için:  
  
1.  Oluşturmak bir `CDaoWorkspace` nesne ancak çağırmayın **oluşturma**.  
  
2.  Çağrı `SetDefaultUser` ve isterseniz, [SetDefaultPassword](#setdefaultpassword).  
  
3.  Çağrı **oluşturma** bu çalışma nesne veya sonraki olanlar için bir kullanıcı adı belirtilmeden.  
  
 Varsayılan olarak, DefaultUser özelliği "Yönetici"'ye ayarlanır ve DefaultPassword özelliği boş bir dize ("").  
  
 İlgili bilgi için "DefaultUser özelliği" ve "DefaultPassword özelliğinde" DAO Yardım konularına bakın.  
  
##  <a name="setinipath"></a>CDaoWorkspace::SetIniPath  
 Microsoft Jet veritabanı altyapısı için Windows kayıt defteri ayarları konumunu belirtmek için bu üye işlevini çağırın.  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszRegistrySubkey*  
 Microsoft Jet veritabanı altyapısı ayarları ya da yüklenebilir ISAM veritabanları için gerekli parametreleri konumu için bir Windows kayıt defteri alt anahtarı adını içeren dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı `SetIniPath` yalnızca özel ayarlar belirtmeniz gerekiyorsa. Daha fazla bilgi için DAO Yardımı'ndaki "IniPath özelliği" konusuna bakın.  
  
> [!NOTE]
>  Çağrı `SetIniPath` uygulama yüklemesi sırasında olmayan uygulama çalıştırıldığında. `SetIniPath`Tüm çalışma alanları, veritabanları veya kayıt kümeleri açmadan önce çağrılmalıdır; Aksi takdirde, MFC özel durum oluşturur.  
  
 Veritabanı altyapısı ile kullanıcı tarafından sağlanan kayıt defteri ayarlarını yapılandırmak için bu düzenek kullanabilirsiniz. Bu öznitelik kapsamı uygulamanıza sınırlıdır ve uygulamanızı yeniden başlatmanıza gerek kalmadan değiştirilemez.  
  
##  <a name="setisolateodbctrans"></a>CDaoWorkspace::SetIsolateODBCTrans  
 Çalışma alanı için DAO IsolateODBCTrans özelliğinin değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>Parametreler  
 *bIsolateODBCTrans*  
 Geçirmek **TRUE** ODBC işlemleri yalıtma başlamak istiyorsanız. Geçirmek **FALSE** ODBC işlemleri yalıtma durdurmak istiyorsanız.  
  
### <a name="remarks"></a>Açıklamalar  
 Bazı durumlarda, bekleyen birden çok eşzamanlı işlem aynı ODBC veritabanı üzerinde olması gerekebilir. Bunu yapmak için her işlem için ayrı bir çalışma alanı açmanız gerekir. Her çalışma kendi ODBC bağlantısı veritabanına sahip olabilirsiniz, ancak bu sistem performansını yavaşlatır. ODBC bağlantıları aynı kullanıcı tarafından açılmış birden çok çalışma alanı nesnelerinden işlem yalıtım normalde gerekli olmadığından, varsayılan olarak paylaşılır.  
  
 Microsoft SQL Server gibi bazı ODBC sunucuları tek bir bağlantı üzerinde eşzamanlı işlemlere izin vermez. Bu tür bir veritabanında bir seferde birden fazla işlem değiştirilmesi gerekiyorsa, IsolateODBCTrans özelliğini ayarlamak **TRUE** açmadan hemen her çalışma alanında. Bu, her çalışma alanı için ayrı bir ODBC bağlantı zorlar.  
  
##  <a name="setlogintimeout"></a>CDaoWorkspace::SetLoginTimeout  
 Çalışma alanı için DAO LoginTimeout özelliğinin değeri ayarlamak için bu üye işlevini çağırın.  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parametreler  
 `nSeconds`  
 Bir ODBC veritabanı oturum açmayı denediğinizde bir hata gerçekleşmeden önce saniye sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu değer bir ODBC veritabanı oturum açmayı denediğinizde bir hata gerçekleşmeden önce saniye sayısını temsil eder. Varsayılan LoginTimeout 20 saniye ayardır. LoginTimeout 0 olarak ayarlandığında, hiçbir zaman aşımı gerçekleşir ve veri kaynağı ile iletişimi yanıt vermeyebilir.  
  
 Microsoft SQL Server gibi bir ODBC veritabanı oturum çalışılırken bağlantı ağ hataları nedeniyle başarısız olabilir veya Sunucu çalışmadığı için. Bağlanmak için 20 saniye için varsayılan beklemek yerine bir hata üretir önce veritabanı altyapısı ne kadar bekleyeceğini belirtebilirsiniz. Sunucuda oturum açmak örtük olarak bir dış sunucu veritabanında bir sorgu çalıştırılarak gibi farklı olay sayısı'nın bir parçası olarak gerçekleşir. Zaman aşımı değeri LoginTimeout özelliği geçerli ayarı tarafından belirlenir.  
  
 İlgili bilgi için DAO Yardımı'ndaki "LoginTimeout özelliği" konusuna bakın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase sınıfı](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef sınıfı](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException Sınıfı](../../mfc/reference/cdaoexception-class.md)
