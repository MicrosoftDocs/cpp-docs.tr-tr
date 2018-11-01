---
title: "TN054: MFC DAO Sınıflarını Kullanırken DAO'yu Doğrudan Çağırma"
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.dao
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
ms.openlocfilehash: 938381f55b598911b69bb25bf7af576dfdfb2e4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505748"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: MFC DAO Sınıflarını Kullanırken DAO'yu Doğrudan Çağırma

> [!NOTE]
> Sihirbazlar ve Visual C++ ortamına DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

MFC DAO veritabanı sınıfları kullanırken DAO doğrudan kullanmak için gerekli olduğu durumlar olabilir. Genellikle bu durum olmaz, ancak MFC yapmayı doğrudan DAO çağrıları basit MFC sınıflarını kullanımını doğrudan DAO çağrıları ile birleştirilirken kolaylaştırmak için bazı yardımcı mekanizmaları sağlamıştır. MFC yönetilen DAO nesnenin yöntemlere yapılan çağrılar doğrudan DAO yaparak yalnızca birkaç satır kod istemeniz gerekir. DAO nesneleri oluşturup kullanacağınızı ihtiyacınız varsa *değil* MFC tarafından yönetilen, aslında çağırarak biraz daha fazla iş yapmanız gerekecek `Release` nesne üzerinde. Bu teknik Not, ne zaman DAO doğrudan çağırmak isteyebilirsiniz, MFC Yardımcıları yardımcı olması için neler yapabileceğinizi ve DAO OLE arabirimleri kullanmayı açıklar. Son olarak, bu not, doğrudan DAO güvenlik özellikleri DAO çağırma gösteren bazı örnek işlevleri sağlar.

## <a name="when-to-make-direct-dao-calls"></a>DAO doğrudan çağrı yapmak ne zaman

Koleksiyonları yenilenmesi gerektiğinde doğrudan DAO çağrıları yapmak için en yaygın durumlar ortaya ya da MFC tarafından Sarmalanan değil özellikleri ne zaman uyguluyor. MFC tarafından sunulmadığından en önemli güvenlik özelliğidir. Güvenlik özellikleri uygulamak istiyorsanız, DAO kullanıcılar ve gruplar nesneleri doğrudan kullanmanız gerekir. Güvenlik yanı sıra MFC tarafından desteklenmeyen yalnızca birkaç diğer DAO özellikleri vardır. Bunlar, kayıt kopyalama ve veritabanı çoğaltma özellikleri yanı sıra birkaç geç DAO eklemeleri içerir.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO ve MFC'nin uygulaması kısa bir genel bakış

MFC'nin kaydırma, çok az şey hakkında endişelenmeniz gerekmez için pek çok detayından işleyerek DAO daha kolay kullanarak DAO yapar. Bu OLE, oluşturulmasını ve yönetimini (koleksiyon nesnelerini özellikle) hata denetleme ve kesin türü belirtilmiş ve daha basit bir arabirim sağlayan DAO nesnelerin başlatılması içerir (hiçbir **değişken** veya `BSTR` bağımsız değişkenler). Doğrudan DAO aramaları yapmak ve yine de bu özelliklerden yararlanabilirsiniz. Tüm kodunuzu gerçekleştirmelisiniz olan çağrı `Release` doğrudan DAO tarafından oluşturulan nesneler için çağırır ve *değil* MFC üzerinde dahili ihtiyaç duyabilir arabirim işaretçilerini düzenleyin. Örneğin, değiştirmeyin *m_pDAORecordset* açık bir üye `CDaoRecordset` sürece, nesne *tüm* iç sonuçları. Ancak, kullandığınız olabilir *m_pDAORecordset* doğrudan alanlar koleksiyonu almak için DAO çağırmak için arabirim. Bu durumda *m_pDAORecordset* üye değiştirilemiyor. Yalnızca çağırmak zorunda `Release` nesneyle tamamladığınızda, alanlar koleksiyonu nesne üzerinde.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>DAO yapmak Yardımcıları açıklamasını daha kolay çağırır

DAO daha kolay bir şekilde arama yapmak için sağlanan Yardımcıları MFC DAO veritabanı sınıfları dahili olarak kullanılan aynı yardımcılardır. Bu Yardımcıları, hata ayıklama çıkışını günlüğe kaydetme beklenen hatalarını denetleme ve gerekirse uygun özel durumları atma dönüş kodları doğrudan bir DAO arama yaparken denetlemek için kullanılır. Temel alınan iki yardımcı işlev ve bu iki Yardımcıları birine harita dört makroları vardır. En iyi bir açıklama, kodun okunmasını olacaktır. Bkz: **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**, ve **DAO_TRACE** AFXDAO içinde. Makroları bakın ve görmek için H **AfxDaoCheck** ve **AfxDaoTrace** DAOCORE içinde. CPP.

## <a name="using-the-dao-ole-interfaces"></a>DAO OLE arabirimleri kullanarak

DAO nesne hiyerarşisinde her nesne için OLE arabirimleri DBDAOINT üstbilgi dosyasında tanımlanır. H \Program Visual Studio .NET 2003\VC7\include dizinde bulunamadı. Bu arabirimlerin tüm DAO hiyerarşi yönetmenize olanak tanıyan yöntemler sağlar.

Birçok DAO arabirimleri yöntemlere yönetmek ihtiyacınız olacak bir `BSTR` nesne (OLE Otomasyonu nesnesi etkin kullanılan bir ön eki uzunluğu dize). `BSTR` Nesne genellikle saklanmış olduğu içinde **değişken** veri türü. MFC sınıfı `COleVariant` kendisini devraldığı **değişken** veri türü. Olup ANSI veya Unicode için projenizi bağlı olarak, ANSI veya Unicode DAO arabirimleri döndüreceği `BSTR`s. DAO arabirimi sağlayan alır için V_BSTR ve V_BSTRT, iki makro yararlı `BSTR` beklenen türde.

V_BSTR ayıklamak *bstrVal* üyesi bir `COleVariant`. İçeriği geçirmeniz gerektiğinde bu makroyu genellikle kullanılan bir `COleVariant` DAO arabirim yöntemi için. Aşağıdaki kod parçası, bildirimler ve gerçek kullanım için V_BSTR makrosu yararlanan iki DAO DAOUser arabirimin yöntemlerini gösterir:

```cpp
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

Unutmayın `VT_BSTRT` belirtilen bağımsız değişken `COleVariant` Oluşturucusu yukarıdaki sağlar bir ANSI olacaktır `BSTR` içinde `COleVariant` uygulamanız ve bir Unicode ANSI sürümü'derleme `BSTR` Unicode sürümü Uygulamanızı. DAO neleri bekliyor budur.

Diğer makro V_BSTRT, ANSI veya Unicode ayıklayacaktır *bstrVal* üyesi `COleVariant` (ANSI veya Unicode) yapı türüne bağlıdır. Aşağıdaki kod nasıl ayıklanacağını gösterir `BSTR` değerini bir `COleVariant` içine bir `CString`:

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

Depolanan diğer türleri açmak için diğer tekniklerle birlikte V_BSTRT makrosu `COleVariant`, DAOVIEW örnekte gösterilmiştir. Bu çeviri özellikle gerçekleştirilir `CCrack::strVARIANT` yöntemi. Mümkünse, bu yöntem değeri çevirir bir `COleVariant` örneği `CString`.

## <a name="simple-example-of-a-direct-call-to-dao"></a>DAO doğrudan çağrı basit örneği

Temel alınan DAO koleksiyon nesnelerini yenilemek gerekli olduğunda durumlarda ortaya çıkabilir. Genellikle bu gerekli olmaz, ancak gerekirse, bir basit bir yordamdır. Ne zaman bir toplama yenilenmesi gerekebilir, çok kullanıcılı bir ortamda birden çok kullanıcının bulunduğu yeni tabledefs oluşturmaya çalışırken örneğidir. Bu durumda, tabledefs koleksiyonu eski hale gelebilir. Koleksiyon yenilemek için çağrı yeterlidir `Refresh` hatalar için belirli bir koleksiyon nesnesi ve onay yöntemi:

```cpp
DAO_CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Şu anda tüm DAO koleksiyon nesnesi arabirimleri MFC DAO veritabanı sınıfları belgelenmemiş uygulama ayrıntılarını olduğunu unutmayın.

## <a name="using-dao-directly-for-dao-security-features"></a>DAO kullanarak doğrudan DAO güvenlik özellikleri

MFC DAO veritabanı sınıfları DAO güvenlik özellikleri kaydırılacak. Bazı DAO güvenlik özelliklerini kullanmayı DAO arabirimin yöntemlerini çağırmanız gerekir. Aşağıdaki işlev sistem veritabanı ayarlar ve ardından kullanıcının parolasını değiştirir. Bu işlev, sonradan tanımlanan üç diğer işlevleri çağırır.

```cpp
void ChangeUserPassword()
{
    // Specify path to the Microsoft Access *// system database
    CString strSystemDB =
        _T("c:\\Program Files\\MSOffice\\access\\System.mdw");

    // Set system database before MFC initilizes DAO
    // NOTE: An MFC module uses only one instance
    // of a DAO database engine object. If you have
    // called a DAO object in your application prior
    // to calling the function below, you must call
    // AfxDaoTerm to destroy the existing database
    // engine object. Otherwise, the database engine
    // object already in use will be reused, and setting
    // a system datbase will have no effect.
    //
    // If you have used a DAO object prior to calling
    // this function it is important that DAO be
    // terminated with AfxDaoTerm since an MFC
    // module only gets one copy of the database engine
    // and that engine will be reused if it hasn't been
    // terminated. In other words, if you do not call
    // AfxDaoTerm and there is currently a database
    // initialized, setting the system database will
    // have no effect.
    SetSystemDB(strSystemDB);

    // User name and password manually added
    // by using Microsoft Access
    CString strUserName = _T("NewUser");
    CString strOldPassword = _T("Password");
    CString strNewPassword = _T("NewPassword");

    // Set default user so that MFC will be able
    // to log in by default using the user name and
    // password from the system database
    SetDefaultUser(strUserName, strOldPassword);

    // Change the password. You should be able to
    // call this function from anywhere in your
    // MFC application
    ChangePassword(strUserName, strOldPassword, strNewPassword);

    // ...
}
```

Sonraki dört örnekler göstermektedir nasıl yapılır:

- Sistem DAO veritabanı kümesi (. MDW dosyası).

- Varsayılan kullanıcı adı ve parola ayarlayın.

- Bir kullanıcı parolasını değiştirin.

- Parolasını değiştirmek bir. Dosyayı MDB.

### <a name="setting-the-system-database"></a>Sistem veritabanı ayarlama

Bir uygulama tarafından kullanılan sistem veritabanı ayarlamak için bir örnek işlevi aşağıdadır. Bu işlev, diğer DAO çağrı yapılmadan önce çağrılmalıdır.

```cpp
// Set the system database that the
// DAO database engine will use

void SetSystemDB(CString& strSystemMDB)
{
    COleVariant varSystemDB(strSystemMDB, VT_BSTRT);

    // Initialize DAO for MFC
    AfxDaoInit();
    DAODBEngine* pDBEngine = AfxDaoGetEngine();

    ASSERT(pDBEngine != NULL);

    // Call put_SystemDB method to set the *// system database for DAO engine
    DAO_CHECK(pDBEngine->put_SystemDB(varSystemDB.bstrVal));
}
```

### <a name="setting-the-default-user-and-password"></a>Varsayılan kullanıcı adı ve parola ayarlama

Varsayılan kullanıcı ve bir sistem veritabanı parolasını ayarlamak için aşağıdaki işlevi kullanın:

```cpp
void SetDefaultUser(CString& strUserName,
    CString& strPassword)
{
    COleVariant varUserName(strUserName, VT_BSTRT);
    COleVariant varPassword(strPassword, VT_BSTRT);

    DAODBEngine* pDBEngine = AfxDaoGetEngine();
    ASSERT(pDBEngine != NULL);

    // Set default user:
    DAO_CHECK(pDBEngine->put_DefaultUser(varUserName.bstrVal));

    // Set default password:
    DAO_CHECK(pDBEngine->put_DefaultPassword(varPassword.bstrVal));
}
```

### <a name="changing-a-users-password"></a>Bir kullanıcının parolasını değiştirme

Bir kullanıcının parolasını değiştirmek için aşağıdaki işlevi kullanın:

```cpp
void ChangePassword(CString &strUserName,
    CString &strOldPassword,
    CString &strNewPassword)
{
    // Create (open) a workspace
    CDaoWorkspace wsp;
    CString strWspName = _T("Temp Workspace");

    wsp.Create(strWspName, strUserName, strOldPassword);
    wsp.Append();

    // Determine how many objects there are *// in the Users collection
    short nUserCount;
    short nCurrentUser;
    DAOUser *pUser = NULL;
    DAOUsers *pUsers = NULL;

    // Side-effect is implicit OLE AddRef()
    // on DAOUser object:
    DAO_CHECK(wsp.m_pDAOWorkspace->get_Users(&pUsers));

    // Side-effect is implicit OLE AddRef()
    // on DAOUsers object
    DAO_CHECK(pUsers->getcount(&nUserCount));

    // Traverse through the list of users
    // and change password for the userid
    // used to create/open the workspace
    for(nCurrentUser = 0; nCurrentUser <nUserCount; nCurrentUser++)
    {
        COleVariant varIndex(nCurrentUser, VT_I2);
        COleVariant varName;

        // Retrieve information for user nCurrentUser
        DAO_CHECK(pUsers->get_Item(varIndex, &pUser));

        // Retrieve name for user nCurrentUser
        DAO_CHECK(pUser->get_Name(&V_BSTR(&varName)));

        CString strTemp = V_BSTRT(&varName);

        // If there is a match, change the password
        if (strTemp == strUserName)
        {
            COleVariant varOldPwd(strOldPassword, VT_BSTRT);
            COleVariant varNewPwd(strNewPassword, VT_BSTRT);

            DAO_CHECK(pUser->NewPassword(V_BSTR(&varOldPwd),
                V_BSTR(&varNewPwd)));

            TRACE("\t Password is changed\n");
        }
    }
    // Clean up: decrement the usage count
    // on the OLE objects
    pUser->Release();
    pUsers->Release();
    wsp.Close();
}
```

### <a name="changing-the-password-of-an-mdb-file"></a>Parolasını değiştirme bir. Dosyayı MDB

Parolasını değiştirmek için bir. MDB dosyasında, aşağıdaki işlevini kullanın:

```cpp
void SetDBPassword(LPCTSTR pDB,
    LPCTSTR pszOldPassword,
    LPCTSTR pszNewPassword)
{
    CDaoDatabase db;
    CString strConnect(_T(";pwd="));

    // the database must be opened as exclusive
    // to set a password
    db.Open(pDB, TRUE, FALSE, strConnect + pszOldPassword);

    COleVariant NewPassword(pszNewPassword, VT_BSTRT),
                OldPassword(pszOldPassword, VT_BSTRT);

    DAO_CHECK(db.m_pDAODatabase->NewPassword(V_BSTR(&OldPassword),
        V_BSTR(&NewPassword)));

    db.Close();
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
