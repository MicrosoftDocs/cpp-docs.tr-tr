---
title: "TN054: Doğrudan MFC DAO sınıflarını kullanırken DAO'yu çağırma | Microsoft Docs"
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.dao
dev_langs:
- C++
helpviewer_keywords:
- MFC, DAO and
- passwords [MFC], calling DAO
- security [MFC], DAO
- DAO (Data Access Objects), calling directly
- DAO (Data Access Objects), security
- security [MFC]
- TN054
- DAO (Data Access Objects), and MFC
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2acc0d6df4495ed38e7c5a6a34dcfd70108f34b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: MFC DAO Sınıflarını Kullanırken DAO'yu Doğrudan Çağırma
> [!NOTE]
>  Visual C++ ortamı ve sihirbazları DAO (DAO sınıfları dahil edilmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.  
  
 MFC DAO veritabanı sınıfları kullanırken DAO doğrudan kullanmak için gerekli olduğu durumlar olabilir. Genellikle, bu durumda olmayacak, ancak MFC yapmayı doğrudan DAO çağrıları basit MFC sınıfları kullanımını doğrudan DAO aramaları birleştirilirken kolaylaştırmak için bazı yardımcı mekanizmalar sağlamıştır. Bir MFC yönetilen DAO nesne yöntemlerinin çağrıları doğrudan DAO yapmadan yalnızca birkaç satır kod istemeniz gerekir. DAO nesneleri oluşturmak gereken *değil* MFC tarafından yönetilen, aslında çağırarak biraz daha fazla iş yapmanız gerekecek **sürüm** nesne üzerinde. Bu teknik Not zaman doğrudan çağırmak isteyebilirsiniz, MFC Yardımcıları yardımcı olması için yapabilirsiniz ve DAO OLE arabirimleri kullanmayı açıklar. Son olarak, bu Not DAO güvenlik özellikleri doğrudan çağırmak nasıl gösteren bazı örnek işlevleri sağlar.  
  
## <a name="when-to-make-direct-dao-calls"></a>Doğrudan DAO çağrıları yapma zamanı  
 Ne zaman MFC tarafından Sarmalanan değil özelliklerini uygulama veya koleksiyonlar yenilenmesi gerektiğinde doğrudan DAO çağrıları yapma için en yaygın durumlar oluşabilir. MFC tarafından gösterilmeyen en önemli güvenlik özelliğidir. Güvenlik özellikleri uygulamak istiyorsanız, DAO kullanıcıları ve grupları nesneleri doğrudan kullanmanız gerekir. Güvenlik yanı sıra, MFC tarafından desteklenmeyen yalnızca birkaç diğer DAO özellikleri vardır. Bunlar, DAO birkaç geç eklemeler yanı sıra kayıt kümesi kopyalama ve veritabanı çoğaltma özellikleri içerir.  
  
## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO ve MFC'nin uygulaması kısa bir genel bakış  
 MFC'nin kaydırma DAO bağlamak çok az şey hakkında endişelenmeniz gerekmez şekilde ayrıntılarına işleyerek DAO kullanarak daha kolay hale getirir. Bu OLE, oluşturulmasını ve yönetimini DAO nesneleri (özellikle koleksiyonu), hata denetleme ve kesin türü belirtilmiş, daha basit bir arabirim sağlayan başlatılması içerir (hiçbir **değişken** veya `BSTR` bağımsız değişkenler). Doğrudan DAO çağrıları yapma ve hala bu özelliklerden yararlanabilir. Kodunuzu gerçekleştirmelisiniz tümüdür çağrısı **sürüm** doğrudan DAO tarafından oluşturulan tüm nesneler için çağırır ve *değil* MFC üzerinde dahili olarak biçimlendirmenizi arabirim işaretçileri düzenleyin. Örneğin, değiştirmeyin **m_pDAORecordset** açık bir üyesi `CDaoRecordset` , anlamadan nesne *tüm* iç ayrımlar. Ancak, kullanabilirsiniz **m_pDAORecordset** doğrudan alanlar koleksiyonu almak için çağırmak için arabirim. Bu durumda **m_pDAORecordset** üyesi değişiklik. Yalnızca çağrı zorunda **sürüm** nesnesiyle bittiğinde alanlar koleksiyonu nesne üzerinde.  
  
## <a name="description-of-helpers-to-make-dao-calls-easier"></a>DAO yapmak için Yardımcıları açıklaması daha kolay çağırır  
 DAO çağırma daha kolay yapmak için sağlanan Yardımcıları MFC DAO veritabanı sınıfları dahili olarak kullanılan aynı yardımcılardır. Bu Yardımcıları beklenen hatalarını denetleme ve gerekirse uygun özel durumları atma hata ayıklama çıktısı günlüğü doğrudan bir DAO arama yaparken dönüş kodlarını denetlemek için kullanılır. İki temel yardımcı işlevleri ve bu iki Yardımcıları birine eşleme dört makroları vardır. En iyi açıklama kod okumaya olacaktır. Bkz: **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, ve **DAO_TRACE** AFXDAO içinde. Makroları bakın ve görmek için H **AfxDaoCheck** ve **AfxDaoTrace** DAOCORE içinde. CPP.  
  
## <a name="using-the-dao-ole-interfaces"></a>DAO OLE arabirimleri kullanarak  
 DAO nesne hiyerarşideki her nesne için OLE arabirimleri DBDAOINT üstbilgi dosyasında tanımlanır. H \Program Visual Studio .NET 2003\VC7\include dizininde bulunur. Bu arabirimleri DAO hiyerarşinin değiştirmenize izin veren yöntemler sağlar.  
  
 Çoğu DAO arabirimleri yöntemlere işlemek gerekecek bir `BSTR` nesne (OLE Otomasyon kullanılan bir uzunluk önek dizesi). `BSTR` Nesne genellikle kapsüllenmiş içinde **değişken** veri türü. MFC sınıf `COleVariant` kendisini devraldığı **değişken** veri türü. Olup, projenizin ANSI veya Unicode için yapı bağlı olarak, DAO arabirimleri ANSI veya Unicode döndürülecek `BSTR`s. İki makroları **V_BSTR** ve **V_BSTRT**, DAO arabirim sağlayan alır için yararlı olan `BSTR` beklenen türünün örneği.  
  
 **V_BSTR** ayıklanır **bstrVal** üyesi bir `COleVariant`. İçeriğini geçmesi gerektiğinde bu makrosu genelde kullanılan bir `COleVariant` bir yönteme DAO arabirimi. Aşağıdaki kod parçası bildirimler ve yararlanmak DAO DAOUser arabiriminin iki yöntem için gerçek kullanım gösterir **V_BSTR** makrosu:  
  
```  
COleVariant varOldName;  
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

 
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
 
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
 
DAO_CHECK(pUser->get_Name(&V_BSTR (&varOldName)));

DAO_CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```  
  
 Unutmayın `VT_BSTRT` belirtilen bağımsız değişken `COleVariant` Oluşturucusu yukarıdaki sağlar ANSI olacaktır `BSTR` içinde `COleVariant` uygulamanız ve bir Unicode ANSI sürümü yapı varsa `BSTR` Unicode sürümü için Uygulamanızı. Ne DAO bekliyor budur.  
  
 Diğer makro **V_BSTRT**, ANSI veya Unicode ayıklanır **bstrVal** üyesi `COleVariant` yapı (ANSI veya Unicode) türüne bağlı olarak. Aşağıdaki kodda ayıklamak gösterilmiştir `BSTR` değeri bir `COleVariant` içine bir `CString`:  
  
```  
COleVariant varName(_T("MyName"), VT_BSTRT);

CString str = V_BSTRT(&varName);
```  
  
 **V_BSTRT** depolanan diğer türleri açmak için başka teknikler birlikte makrosu `COleVariant`, DAOVIEW örnekte gösterilmiştir. Bu çevirme özellikle gerçekleştirilir **CCrack::strVARIANT** yöntemi. Bu yöntem, mümkün olduğunda, değerini çevirir bir `COleVariant` örneğine `CString`.  
  
## <a name="simple-example-of-a-direct-call-to-dao"></a>DAO doğrudan arama basit örneği  
 Arka plandaki DAO koleksiyonu nesneleri yenilemek gerekli olduğunda durumlar oluşabilir. Genellikle bu gerekli olmamalıdır, ancak gerekli değilse basit bir yordam değil. Çok kullanıcılı bir ortamda yeni tabledefs oluşturma birden fazla kullanıcı ile çalışırken bir koleksiyon yenilenmesi gerektiğinde, bir örnek verilmiştir. Bu durumda, tabledefs koleksiyonu eski hale gelebilir. Koleksiyon yenilemek için arama yeterlidir **yenileme** belirli koleksiyon nesnesi ve onay yöntemi hataları için:  
  
```  
DAO_CHECK(pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh());
```  
  
 Şu anda tüm DAO koleksiyon nesnesi arabirimleri MFC DAO veritabanı sınıfları belgelenmemiş uygulama ayrıntılarını olduğuna dikkat edin.  
  
## <a name="using-dao-directly-for-dao-security-features"></a>DAO doğrudan DAO güvenlik özellikleri kullanma  
 MFC DAO veritabanı sınıfları DAO güvenlik özellikleri kaydırılacak. Bazı DAO güvenlik özellikleri kullanmak için DAO arabirimleri yöntemlerini çağırmalıdır. Aşağıdaki işlevi sistem veritabanı ayarlar ve kullanıcının parolasını değiştirir. Bu işlev, sonradan tanımlanmış olan üç diğer işlevleri çağırır.  
  
```  
void ChangeUserPassword()  
{ *// Specify path to the Microsoft Access *// system database  
    CString strSystemDB = 
    _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

 *// Set system database before MFC initilizes DAO *// NOTE: An MFC module uses only one instance *// of a DAO database engine object. If you have *// called a DAO object in your application prior *// to calling the function below,
    you must call *// AfxDaoTerm to destroy the existing database *// engine object. Otherwise,
    the database engine *// object already in use will be reused,
    and setting *// a system datbase will have no effect. *// *// If you have used a DAO object prior to calling *// this function it is important that DAO be *// terminated with AfxDaoTerm since an MFC *// module only gets one copy of the database engine *// and that engine will be reused if it hasn't been *// terminated. In other words,
    if you do not call *// AfxDaoTerm and there is currently a database *// initialized,
    setting the system database will *// have no affect.  
 
    SetSystemDB(strSystemDB);

 *// User name and password manually added *// by using Microsoft Access  
    CString strUserName = _T("NewUser");

    CString strOldPassword = _T("Password");

    CString strNewPassword = _T("NewPassword");

 *// Set default user so that MFC will be able *// to log in by default using the user name and *// password from the system database  
    SetDefaultUser(strUserName,
    strOldPassword);

 *// Change the password. You should be able to *// call this function from anywhere in your *// MFC application  
    ChangePassword(strUserName,
    strOldPassword,   
    strNewPassword);

 
 .  
 .  
 .  
 
}  
```  
  
 Sonraki dört örnekler göstermektedir nasıl yapılır:  
  
-   Sistem DAO veritabanı ayarlayın (. MDW dosyası).  
  
-   Varsayılan kullanıcı adı ve parola ayarlayın.  
  
-   Bir kullanıcının parolasını değiştirin.  
  
-   Parolasını değiştirme bir. MDB dosyası.  
  
### <a name="setting-the-system-database"></a>Sistem veritabanı ayarlama  
 Bir uygulama tarafından kullanılan sistem veritabanını ayarlamak için bir örnek işlevi aşağıdadır. Bu işlev, diğer DAO çağrıları yapılmadan önce çağrılmalıdır.  
  
```  
// Set the system database that the   
// DAO database engine will use  
 
void SetSystemDB(CString& strSystemMDB)  
{  
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

 *// Initialize DAO for MFC  
    AfxDaoInit();
DAODBEngine* pDBEngine = AfxDaoGetEngine();

 
    ASSERT(pDBEngine != NULL);

 *// Call put_SystemDB method to set the *// system database for DAO engine  
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));

} 
```  
  
### <a name="setting-the-default-user-and-password"></a>Varsayılan kullanıcı adı ve parola ayarlama  
 Varsayılan kullanıcı ve bir sistem veritabanı parolasını ayarlamak için aşağıdaki işlevi kullanın:  
  
```  
void SetDefaultUser(CString& strUserName,
    CString& strPassword)  
{  
    COleVariant varUserName(strUserName,
    VT_BSTRT);

    COleVariant varPassword(strPassword,
    VT_BSTRT);

 
    DAODBEngine* pDBEngine = AfxDaoGetEngine();
ASSERT(pDBEngine != NULL);

 *// Set default user:  
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

 *// Set default password:  
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));

} 
```  
  
### <a name="changing-a-users-password"></a>Bir kullanıcının parolasını değiştirme  
 Bir kullanıcının parolasını değiştirmek için aşağıdaki işlevi kullanın:  
  
```  
void ChangePassword(CString &strUserName,   
    CString &strOldPassword,   
    CString &strNewPassword)  
{ *// Create (open) a workspace  
    CDaoWorkspace wsp;  
    CString strWspName = _T("Temp Workspace");

 
    wsp.Create(strWspName, strUserName,  
    strOldPassword);

 wsp.Append();

 *// Determine how many objects there are *// in the Users collection  
    short nUserCount;  
    short nCurrentUser;  
    DAOUser *pUser = NULL;  
    DAOUsers *pUsers = NULL;  
 *// Side-effect is implicit OLE AddRef() *// on DAOUser object:  
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

 *// Side-effect is implicit OLE AddRef() *// on DAOUsers object  
    DAO_CHECK(pUsers->getcount(&nUserCount));

 *// Traverse through the list of users *// and change password for the userid *// used to create/open the workspace  
    for(nCurrentUser = 0; nCurrentUser <nUserCount;  
    nCurrentUser++) 
 {  
    COleVariant varIndex(nCurrentUser, VT_I2);

    COleVariant varName;  
 *// Retrieve information for user nCurrentUser  
    DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

 *// Retrieve name for user nCurrentUser  
    DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

 
    CString strTemp = V_BSTRT(&varName);

 *// If there is a match, change the password  
    if(strTemp == strUserName)  
 {  
    COleVariant varOldPwd(strOldPassword,   
    VT_BSTRT);

 COleVariant  varNewPwd(strNewPassword,   
    VT_BSTRT);

 
    DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd), 
    V_BSTR(&varNewPwd)));

 
    TRACE("\t Password is changed\n");

 }  
 }  
 *// Clean up: decrement the usage count *// on the OLE objects  
    pUser->Release();
pUsers->Release();

 
    wsp.Close();

} 
```  
  
### <a name="changing-the-password-of-an-mdb-file"></a>Parolasını değiştirme bir. MDB dosyası  
 Parolasını değiştirmek için bir. MDB dosya, aşağıdaki işlev kullanın:  
  
```  
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)  
{  
    CDaoDatabase db;  
    CString strConnect(_T(";pwd="));

 *// the database must be opened as exclusive *// to set a password  
    db.Open(pDB,
    TRUE,
    FALSE,   
    strConnect + pszOldPassword);

 
    COleVariant NewPassword(pszNewPassword,
    VT_BSTRT),  
    OldPassword(pszOldPassword,
    VT_BSTRT);

 
    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword), 
    V_BSTR(&NewPassword)));

 
    db.Close();

} 
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

