---
title: Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
ms.openlocfilehash: 3d516f7923144f0e24bda676147ed529546def25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213768"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma

Normal bir MFC DLL 'den MFC uzantı DLL 'si kullanılırken, MFC uzantı DLL 'SI normal MFC DLL 'nin **CDynLinkLibrary** nesne zincirine bağlanmadıysanız bir veya daha fazla ilgili sorun kümesiyle karşılaşabilirsiniz. MFC veritabanı, OLE ve yuva desteği dll 'lerinin hata ayıklama sürümleri MFC uzantı dll 'leri olarak uygulandığından, kendi MFC uzantı dll 'lerinizi açıkça kullanmadığınız halde bu MFC özelliklerini kullanıyorsanız benzer sorunlar görebilirsiniz. Bazı belirtiler şunlardır:

- MFC uzantı DLL 'sinde tanımlı bir sınıf türünün bir nesnesinin serisini kaldırmaya çalışırken, "Uyarı: CYourClass from Arşiv ' e yüklenemez. Sınıf tanımlı değil. " Izleme hata ayıklama penceresinde görünür ve nesne seri hale getirilemez.

- Hatalı sınıfı gösteren bir özel durum ortaya çıkabilir.

- MFC uzantı DLL 'sinde depolanan kaynaklar, `AfxFindResourceHandle` **null** veya yanlış kaynak tanıtıcısı döndürdüğünden yüklenemedi.

- `DllGetClassObject`, `DllCanUnloadNow` , ve,, `UpdateRegistry` ve ' nin,,, `Revoke` `RevokeAll` ve `RegisterAll` üye işlevleri, `COleObjectFactory` MFC uzantı dll 'de tanımlanan bir sınıf fabrikasını bulamıyor.

- `AfxDoForAllClasses`MFC uzantı DLL dosyasındaki herhangi bir sınıf için çalışmaz.

- Standart MFC veritabanı, yuvalar veya OLE kaynakları yüklemede başarısız olur. Örneğin, **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**), normal MFC DLL MFC veritabanı sınıflarını doğru şekilde kullanırken bile boş bir dize döndürür.

Bu sorunlara yönelik çözüm, bir **CDynLinkLibrary** NESNESI oluşturan MFC uzantı dll 'sinde bir başlatma işlevi oluşturmaktır ve dışarı aktarmasıdır. Bu başlatma işlevini MFC uzantısı DLL kullanan her normal MFC DLL 'den tam olarak bir kez çağırın.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC veritabanı (veya DAO) veya MFC Yuvaları desteği

MFC OLE, MFC veritabanı (veya DAO) veya normal MFC DLL 'inizdeki MFC Yuvaları desteğini kullanıyorsanız, MFC hata ayıklama MFC uzantı dll 'Leri MFCOxxD.dll, MFCDxxD.dll ve MFCNxxD.dll (xx sürüm numarasıdır) otomatik olarak bağlanır. Kullanmakta olduğunuz bu DLL 'lerin her biri için önceden tanımlanmış bir başlatma işlevi çağırmanız gerekir.

Veritabanı desteği için, `AfxDbInitModule` normal MFC DLL 'inizin işlevine bir çağrı ekleyin `CWinApp::InitInstance` . Bu çağrının herhangi bir temel sınıf çağrısından veya MFCDxxD.dll erişen eklenen bir koddan önce olduğundan emin olun. Bu işlev hiçbir parametre alır ve void döndürür.

OLE desteği için `AfxOleInitModule` normal MFC DLL 'lerinizin öğesine bir çağrı ekleyin `CWinApp::InitInstance` . **Cotacontrolmodule InitInstance** işlevinin zaten çağırdığına `AfxOleInitModule` ve bir OLE denetimi oluşturuyorsanız ve kullanıyorsanız `COleControlModule` , bu çağrıyı öğesine eklememelisiniz `AfxOleInitModule` .

Yuva desteği için `AfxNetInitModule` normal MFC DLL 'lerinizin öğesine bir çağrı ekleyin `CWinApp::InitInstance` .

MFC DLL 'Lerinin ve uygulamalarının yayın derlemelerinin veritabanı, yuvalar veya OLE desteği için ayrı dll 'Ler kullanmadığını unutmayın. Ancak, bu başlatma işlevlerini yayın modunda çağırmak güvenlidir.

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary nesneleri

Bu konunun başlangıcında bahsedilen her bir işlem sırasında, MFC 'nin istenen bir değeri veya nesneyi araması gerekir. Örneğin, seri durumdan çıkarma sırasında, arşivdeki nesneleri uygun çalışma zamanı sınıfıyla eşleştirmek için MFC 'nin şu anda kullanılabilir olan tüm çalışma zamanı sınıflarını aramasını gerekir.

Bu aramaların bir parçası olarak MFC, bir **CDynLinkLibrary** nesneleri zinciri yürüyerek kullanılan tüm MFC uzantı dll 'lerini tarar. **CDynLinkLibrary** nesneleri, oluşturma sırasında bir zincire otomatik olarak eklenir ve başlatma sırasında SıRAYLA her MFC uzantı dll tarafından oluşturulur. Ayrıca, her modülün (uygulama veya normal MFC DLL) kendi **CDynLinkLibrary** nesneleri zinciri vardır.

Bir MFC uzantısı DLL 'sinin bir **CDynLinkLibrary** zincirine kablolu olması için MFC uzantı dll 'sini kullanan her modülün bağlamında bir **CDynLinkLibrary** nesnesi oluşturması gerekir. Bu nedenle, bir MFC uzantı DLL 'SI normal MFC DLL 'lerden kullanılacaksa, bir **CDynLinkLibrary** nesnesi oluşturan bir içe aktarılmış başlatma işlevi sağlamalıdır. MFC uzantısı DLL kullanan her normal MFC DLL 'nin, aktarılmış başlatma işlevini çağırması gerekir.

MFC uzantı DLL 'SI yalnızca bir MFC uygulamasından (. exe) kullanılacaksa ve hiçbir şekilde normal MFC DLL 'den kullanılacaksa, bu durumda, MFC uzantı DLL 'sinde **CDynLinkLibrary** nesnesini oluşturmak yeterlidir `DllMain` . MFC DLL Sihirbazı MFC uzantı DLL kodunun yaptığı şeydir. MFC uzantı DLL 'sini örtülü olarak yüklerken `DllMain` uygulama başlamadan önce yükler ve yürütülür. Herhangi bir **CDynLinkLibrary** oluşturma, MFC DLL bir MFC uygulaması için ayrılmış bir varsayılan zincire bağlanır.

Özellikle MFC uzantı DLL 'sinin bellekten dinamik olarak kaldırılacaksa, tek bir zincirde bir MFC uzantı DLL 'sinden birden fazla **CDynLinkLibrary** nesnesine sahip olması kötü bir fikir olduğunu unutmayın. Başlatma işlevini herhangi bir modülden birden çok kez çağırmayın.

## <a name="sample-code"></a>Örnek Kod

Bu örnek kod, normal MFC DLL 'inin MFC uzantı DLL 'sine örtük olarak bağlandığını varsayar. Bu, normal MFC DLL 'SI oluşturulurken MFC uzantı DLL 'inin içeri aktarma kitaplığına (. lib) bağlanılarak gerçekleştirilir.

Aşağıdaki satırlar, MFC uzantı DLL 'sinin kaynağında olmalıdır:

```
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    if (dwReason == DLL_PROCESS_ATTACH)
    {
        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(extensionDLL, hInstance))
           return 0;
    }
    return 1;   // ok
}

// Exported DLL initialization is run in context of
// application or regular MFC DLL
extern "C" void WINAPI InitYourExtDLL()
{
    // create a new CDynLinkLibrary for this app
    new CDynLinkLibrary(extensionDLL);

    // add other initialization here
}
```

**InitYourExtDLL** işlevini dışarı aktardığınızdan emin olun. Bu, **`__declspec(dllexport)`** DLL 'nin. def dosyasında veya kullanılarak şu şekilde yapılabilir:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

`InitInstance` `CWinApp` MFC uzantı dll 'ini kullanarak her normal MFC DLL 'de türetilen nesnenin üyesine bir çağrı ekleyin:

```
// YourRegularDLL.cpp:

class CYourRegularDLL : public CWinApp
{
public:
    virtual BOOL InitInstance(); // Initialization
    virtual int ExitInstance();  // Termination

    // nothing special for the constructor
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }
};

BOOL CYourRegularDLL::InitInstance()
{
    // any DLL initialization goes here
    TRACE0("YOUR regular MFC DLL initializing\n");

    // wire any MFC extension DLLs into CDynLinkLibrary chain
    InitYourExtDLL();

    return TRUE;
}
```

### <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [MFC uzantı DLL 'sini başlatma](run-time-library-behavior.md#initializing-extension-dlls)

- [Normal MFC DLL 'Leri başlatma](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC uzantısı DLL’leri](extension-dlls.md)

- [MFC 'ye statik olarak bağlı normal MFC DLL 'Leri](regular-dlls-statically-linked-to-mfc.md)

- [MFC 'ye dinamik olarak bağlı normal MFC DLL 'Leri](regular-dlls-dynamically-linked-to-mfc.md)

- [DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [MFC 'nin DLL sürümü](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC uzantısı DLL’leri](extension-dlls.md)
