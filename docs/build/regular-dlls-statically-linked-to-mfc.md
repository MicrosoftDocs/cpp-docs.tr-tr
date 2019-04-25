---
title: Statik olarak MFC'ye bağlı normal MFC DLL'leri
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
ms.openlocfilehash: 1f05b5e3c268935cf3161fb7184e04b3e3ea1446
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314786"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>Statik olarak MFC'ye bağlı normal MFC DLL'leri

MFC DLL statik olarak MFC'ye bağlı normal MFC dahili olarak kullandığı bir DLL'dir ve DLL'de dışa aktarılan işlevleri MFC veya MFC olmayan yürütülebilir dosyaları tarafından çağrılabilir. Adı açıklandığı gibi bu tür bir DLL, MFC statik bağlantı kitaplığı sürümü kullanılarak oluşturulur. İşlevleri, genellikle bir Normal MFC DLL standart C arabirimini kullanarak dışarı aktarılır. Örnek Normal MFC DLL'SİNİN yazma, derleme ve ilişkin bir örnek için bkz. [ile ilgili](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap).

USRDLL terimi artık Visual C++ belgelerinde kullanılan unutmayın. Statik olarak MFC'ye bağlı normal MFC DLL'SİNİN önceki USRDLL ile aynı özelliklere sahiptir.

MFC'ye statik olarak bağlı normal MFC DLL'SİNİN, aşağıdaki özelliklere sahiptir:

- İstemci yürütülebilir, DLL'lerin (C, C++, Pascal, Visual Basic ve benzeri); kullanımını destekleyen herhangi bir dilde yazılabilir bir MFC uygulaması yok.

- DLL uygulamaları tarafından kullanılan MFC statik bağlantı kitaplıklarında bağlayabilirsiniz. Artık statik bağlantı kitaplıklarında DLL'ler için ayrı bir sürümü yoktur.

- MFC 4.0 sürümünden önce statik olarak MFC'ye bağlı normal MFC DLL'leri işlevi aynı türde USRDLL sağlanır. İtibarıyla Visual C++ sürüm 4.0 USRDLL terimi artık kullanılmıyor.

MFC'ye statik olarak bağlı normal MFC DLL'SİNİN, aşağıdaki gereksinimleri vardır:

- Bu tür bir DLL türetilen bir sınıf örneği oluşturmanız gerekir `CWinApp`.

- Bu tür bir DLL kullanan `DllMain` MFC tarafından sağlanan. Tüm özel DLL başlatma kodunda yerleştirin `InitInstance` üye işlevine ve sonlandırma kodu `ExitInstance` normal bir MFC uygulaması olduğu gibi.

- Terim USRDLL kullanılmıyor olsa da hala tanımlamalısınız "**_USRDLL**" derleyici komut satırında. Bu tanım, hangi bildirimlerin çekilmesini MFC üst bilgi dosyaları belirler.

Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne gibi bir MFC uygulaması. Ancak, `CWinApp` DLL'nin nesne gibi bir ana ileti pompası yok `CWinApp` uygulamanın nesne.

Unutmayın `CWinApp::Run` mekanizması uygulamanın ana ileti göndericisi çünkü bir DLL için uygulanmaz. DLL kalıcı olmayan iletişim kutuları açılır ya da kendi ana penceresi varsa, uygulamanın ana ileti pompası sırayla çağırır DLL tarafından dışarı aktarılan bir yordam çağırmalıdır `CWinApp::PreTranslateMessage` DLL'nin uygulama nesnesinin üye işlevi.

İle ilgili örnek bu işlev örneği için bkz.

Simgeler, genellikle bir Normal MFC DLL standart C arabirimini kullanarak dışarı aktarılır. Normal MFC DLL'den dışarı aktarılan bir işlevin bildirimi aşağıdaki gibi görünür:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Normal MFC DLL'SİNİN içindeki tüm bellek ayırmaları DLL kalmalı; DLL geçirin veya çağıran yürütülebilir dosyadan aşağıdakilerden herhangi birini alıyorsunuz gerekir:

- MFC nesne işaretçileri

- MFC tarafından ayrılan bellek işaretçisi

Yukarıdakilerden herhangi biri yapın veya çağıran yürütülebilir dosyayı ve DLL arasında MFC'den türetilmiş nesneler geçirmek ihtiyaç duyduğunuz ise bir MFC uzantılı DLL oluşturmanız gerekir.

Verilerin bir kopyasını yaparsanız işaretçileri ayrılan bellek için C çalışma zamanı kitaplıkları tarafından bir uygulama ve DLL arasında geçirmek güvenlidir. Değil silmeli veya bu işaretçileri yeniden boyutlandırmak veya bellek kopyalayarak olmadan kullanın.

MFC'ye statik olarak bağlanan bir DLL de dinamik olarak paylaşılan MFC DLL'lerine bağlanamıyor. Dinamik olarak MFC'ye statik olarak bağlanan bir DLL bir uygulama gibi başka bir DLL bağlıdır; uygulamalar için diğer DLL gibi bağlayın.

Standart MFC statik bağlantı kitaplıklarında açıklanan kurallara göre adlandırılır [MFC DLL'leri için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions). Ancak, MFC sürüm 3.0 ve üstü ile artık bağlayıcıya bağlı olarak istediğiniz MFC kitaplık sürümünü el ile belirtmek gereklidir. Bunun yerine, MFC başlık dosyaları otomatik olarak gibi MFC Kitaplığı içinde göre önişlemci bağlamak için doğru sürümünü tanımlayan belirlemek  **\_hata ayıklama** veya **_UNICODE**. MFC üstbilgi dosyalarındaki MFC Kitaplığı belirli bir sürümüne bağlamak için DEFAULTLIB ekleyin.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Normal MFC DLL'leri Başlat](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Bir DLL'in bir parçası MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Normal MFC DLL'lerinde Veritabanı, OLE ve Yuva MFC uzantısı DLL'leri Kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)

- [Dinamik Olarak MFC'ye Bağlı Normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)
