---
title: "TN054: MFC DAO sınıflarını kullanırken DAO 'YU doğrudan çağırma"
ms.date: 09/17/2019
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
ms.openlocfilehash: cef9852f762a64579e11fe4b0d8606bfc9d36709
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095971"
---
# <a name="tn054-calling-dao-directly-while-using-mfc-dao-classes"></a>TN054: MFC DAO sınıflarını kullanırken DAO 'YU doğrudan çağırma

> [!NOTE]
> DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. Visual C++ ortamı ve sihirbazları DAO 'yu desteklemez (DAO sınıfları dahil edilir ancak yine de kullanabilirsiniz). Microsoft, yeni projeler için [OLE DB şablonlarını](../data/oledb/ole-db-templates.md) veya [ODBC 'yi ve MFC 'yi](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

MFC DAO veritabanı sınıfları kullanılırken, doğrudan DAO kullanılması gereken durumlar olabilir. Genellikle bu durum olmayacaktır, ancak MFC doğrudan DAO çağrılarıyla MFC sınıflarının kullanımını birleştirirken doğrudan DAO çağrılarını kolaylaştırmak için bazı yardımcı mekanizmalar sağlamıştır. MFC tarafından yönetilen bir DAO nesnesinin yöntemlerine doğrudan DAO çağrıları yapmak için yalnızca birkaç satır kod gerekir. MFC *tarafından yönetilmeyen DAO* nesneleri oluşturmanız ve kullanmanız gerekiyorsa, aslında nesneyi çağırarak `Release` biraz daha iş yapmanız gerekecektir. Bu teknik notta, DAO 'YU doğrudan çağırmak isteyebileceğiniz, MFC yardımcıların size yardımcı olmak için neler olabileceği ve DAO OLE arabirimlerinin nasıl kullanılacağı açıklanmaktadır. Son olarak, bu notta DAO güvenlik özellikleri için doğrudan DAO çağrısının nasıl çağrılacağını gösteren bazı örnek işlevler sağlanmaktadır.

## <a name="when-to-make-direct-dao-calls"></a>Doğrudan DAO çağrıları ne zaman yapılır?

Doğrudan DAO çağrıları yapmanın en yaygın durumları, koleksiyonların yenilenmesi gerektiğinde veya MFC tarafından sarmalanmamış Özellikler uyguladığınızda oluşur. MFC tarafından açığa çıkarılan en önemli özellik güvenlik ' dir. Güvenlik özelliklerini uygulamak istiyorsanız, doğrudan DAO kullanıcıları ve grupları nesnelerini kullanmanız gerekir. Güvenliğin yanı sıra, MFC tarafından desteklenmeyen başka bir DAO özelliği de vardır. Bunlar, kayıt kümesi kopyalama ve veritabanı çoğaltma özelliklerinin yanı sıra, DAO için birkaç geç ekleme içerir.

## <a name="a-brief-overview-of-dao-and-mfcs-implementation"></a>DAO ve MFC 'nin uygulamasına kısa bir genel bakış

MFC 'nin DAO sarmalanması, pek çok ayrıntıyı işleyerek DAO kullanımını daha kolay hale getirir, böylece çok az şey konusunda endişelenmenize gerek kalmaz. Bu, OLE başlatma, DAO nesnelerinin oluşturulması ve yönetimi (özellikle koleksiyon nesneleri), hata denetimi ve kesin belirlenmiş, daha basit bir arabirim ( **değişken** veya `BSTR` bağımsız değişken olmadan) sağlama içerir. Doğrudan DAO çağrıları yapabilir ve yine de bu özelliklerden yararlanabilirsiniz. Tüm kodunuzun doğrudan DAO çağrıları tarafından oluşturulan `Release` herhangi bir nesne için çağrı yapması gerekir ve MFC 'nin dahili olarak güvenebileceherhangi bir arabirim işaretçilerinden *hiçbirini değiştirmez.* Örneğin, *Tüm* iç sonuçları anlamadığınız müddetçe açık `CDaoRecordset` bir nesnenin m_pDAORecordset üyesini değiştirmeyin. Ancak, alanlar koleksiyonunu almak için doğrudan DAO çağırmak için *m_pDAORecordset* arabirimini kullanabilirsiniz. Bu durumda *m_pDAORecordset* üyesi değiştirilmez. Nesne ile işiniz bittiğinde alanlar `Release` koleksiyonu nesnesini çağırmanız yeterlidir.

## <a name="description-of-helpers-to-make-dao-calls-easier"></a>DAO çağrılarını daha kolay hale getirmek için yardımcıların açıklaması

Bir DAO 'YU çağırmak için belirtilen yardımcılar, MFC DAO veritabanı sınıflarında dahili olarak kullanılan yardımcılardır. Bu yardımcılar, doğrudan bir DAO çağrısı yaparken, hata ayıklama çıkışını günlüğe kaydederken, beklenen hataları denetleyerek ve gerekirse uygun özel durumlar oluşturarak dönüş kodlarını denetlemek için kullanılır. İki temel yardımcı işlev ve bu iki yardımcıdan biriyle eşlenen dört makro vardır. En iyi açıklama yalnızca kodu okumak olacaktır. Bkz. AFXDAO 'da **DAO_CHECK**, **DAO_CHECK_ERROR**, **DAO_CHECK_MEM**ve **DAO_TRACE** . Ve makroları görmek için **AfxDaoCheck** ve **AfxDaoTrace** daocore. CPP.

## <a name="using-the-dao-ole-interfaces"></a>DAO OLE arabirimlerini kullanma

DAO nesne hiyerarşisindeki her nesnenin OLE arabirimleri, DBDAOINT başlık dosyasında tanımlanmıştır. \Program Files\Microsoft Visual Studio .NET 2003 \ VC7\include dizininde bulunan H. Bu arabirimler, tüm DAO hiyerarşisini değiştirmenize olanak tanıyan yöntemler sağlar.

DAO arabirimlerinin birçok yöntemi için, bir `BSTR` nesneyi (OLE Otomasyonu 'nda kullanılan length-önekli dize) değiştirmeniz gerekecektir. Nesnesi genellikle değişken veri türü içinde kapsüllenir. `BSTR` MFC sınıfının `COleVariant` kendisi **değişken** veri türünden devralır. Projenizi ANSI veya Unicode için oluşturup yapılandırdığınıza bağlı olarak, DAO arabirimleri ANSI veya Unicode `BSTR`s döndürür. İki makro, V_BSTR ve V_BSTRT, DAO arabiriminin beklenen türden `BSTR` birini aldığından emin olmak için yararlıdır.

V_BSTR, öğesinin `COleVariant` *bstrVal* üyesini ayıklar. Bu makro genellikle bir DAO arabiriminin bir yöntemine bir `COleVariant` öğesine geçiş yapmanız gerektiğinde kullanılır. Aşağıdaki kod parçası, V_BSTR makrodan faydalanan DAO DAOUser arabiriminin iki yöntemi için bildirimleri ve gerçek kullanımı gösterir:

```cpp
COleVariant varOldName;
COleVariant varNewName(_T("NewUser"), VT_BSTRT);

// Code to assign pUser to a valid value omitted DAO 3.6 is the final version and it is considered obsolete.User *pUser = NULL;

// These method declarations were taken from DBDAOINT.H
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;
DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->get_Name(&V_BSTR (&varOldName))); DAO 3.6 is the final version and it is considered obsolete._CHECK(pUser->put_Name(V_BSTR (&varNewName)));
```

`BSTR` `BSTR` `COleVariant` Yukarıdaki oluşturucuda belirtilen `VT_BSTRT` `COleVariant` bağımsız değişkenin, uygulamanız için bir ANSI sürümü ve bir Unicode sürümü için Unicode sürümü oluşturuyorsanız içinde bir ANSI olacağını unutmayın. uygulamanız. Bu, DAO 'nun beklediği şeydir.

Diğer makro olan `COleVariant` V_BSTRT, derleme türüne (ANSI veya Unicode) bağlı olarak bir ANSI veya Unicode *bstrVal* üyesini ayıklar. Aşağıdaki kod, ' `BSTR` `COleVariant` dan `CString`' a değerin ' a nasıl ayıklanacağını göstermektedir.

```cpp
COleVariant varName(_T("MyName"), VT_BSTRT);
CString str = V_BSTRT(&varName);
```

V_bstrt makrosu, içinde `COleVariant`depolanan diğer türleri açmaya yönelik diğer tekniklerle birlikte DAOVIEW örneğinde gösterilmiştir. Özellikle, bu çeviri `CCrack::strVARIANT` yönteminde gerçekleştirilir. Mümkün olduğunda bu yöntem değerini bir `COleVariant` `CString`örneğine çevirir.

## <a name="simple-example-of-a-direct-call-to-dao"></a>DAO 'ya doğrudan çağrının basit örneği

Temel alınan DAO koleksiyon nesnelerinin yenilenmesi gerektiğinde durumlar ortaya çıkabilir. Normalde, bu gerekli değildir, ancak gerekirse basit bir yordamdır. Bir koleksiyonun yenilenmesi gerekebilen bir örnek, birden çok kullanıcı yeni TableDefs oluşturma ile çok kullanıcılı bir ortamda çalışırken. Bu durumda, TableDefs koleksiyonunuz eski hale gelebilir. Koleksiyonu yenilemek için, yalnızca belirli bir koleksiyon nesnesinin `Refresh` yöntemini çağırmanız ve hataları kontrol etmeniz gerekir:

```cpp DAO 3.6 is the final version and it is considered obsolete._CHECK(pMyDaoDatabase->m_pDAOTableDefs->Refresh());
```

Şu anda tüm DAO koleksiyon nesne arabirimlerinin, MFC DAO veritabanı sınıflarının belgelenmemiş uygulama ayrıntıları olduğunu unutmayın.

## <a name="using-dao-directly-for-dao-security-features"></a>DAO güvenlik özellikleri için doğrudan DAO kullanma

MFC DAO veritabanı sınıfları, DAO güvenlik özelliklerini sarmaz. Bazı DAO güvenlik özelliklerini kullanmak için DAO arabirimlerinin yöntemlerini çağırmanız gerekir. Aşağıdaki işlev sistem veritabanını ayarlar ve sonra kullanıcının parolasını değiştirir. Bu işlev, daha sonra tanımlanan üç diğer işlevi çağırır.

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

Sonraki dört örnekte nasıl yapılacağı gösterilmektedir:

- Sistem DAO veritabanını ayarlayın (. MDW dosyası).

- Varsayılan Kullanıcı ve parolayı ayarlayın.

- Kullanıcının parolasını değiştirin.

- Parolasını değiştirin. MDB dosyası.

### <a name="setting-the-system-database"></a>Sistem veritabanını ayarlama

Bir uygulama tarafından kullanılacak sistem veritabanını ayarlamak için örnek bir işlev aşağıda verilmiştir. Diğer herhangi bir DAO çağrısı yapılmadan önce bu işlevin çağrılması gerekir.

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

### <a name="setting-the-default-user-and-password"></a>Varsayılan Kullanıcı ve Parolayı ayarlama

Bir sistem veritabanının varsayılan kullanıcı ve parolasını ayarlamak için aşağıdaki işlevi kullanın:

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

### <a name="changing-a-users-password"></a>Kullanıcının parolasını değiştirme

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

### <a name="changing-the-password-of-an-mdb-file"></a>Parolasını değiştirme. MDB dosyası

Parolasını değiştirmek için. MDB dosyası, aşağıdaki işlevi kullanın:

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
