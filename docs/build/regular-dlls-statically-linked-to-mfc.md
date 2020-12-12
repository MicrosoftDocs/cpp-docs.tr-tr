---
description: "Daha fazla bilgi edinin: MFC 'ye statik olarak bağlı normal MFC DLL 'Leri"
title: MFC 'ye statik olarak bağlı normal MFC DLL 'Leri
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++]
- DLLs [C++], regular
- USRDLLs
- USRDLLs, statically linked to MFC
- statically linked DLLs [C++]
- regular MFC DLLs [C++], statically linked to MFC
ms.assetid: 2eed531c-726a-4b8a-b936-f721dc00a7fa
ms.openlocfilehash: b213be6bf076557fc57a5bcac62cbf9767587bd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273806"
---
# <a name="regular-mfc-dlls-statically-linked-to-mfc"></a>MFC 'ye statik olarak bağlı normal MFC DLL 'Leri

MFC 'ye statik olarak bağlanan normal bir MFC DLL, MFC 'yi dahili olarak kullanan bir DLL 'dir ve DLL 'deki verilen işlevler MFC ya da MFC olmayan yürütülebilir dosyalar tarafından çağrılabilir. Adın açıkladığı gibi, bu tür DLL MFC 'nin statik bağlantı kitaplığı sürümü kullanılarak oluşturulmuştur. İşlevler genellikle standart C arabirimi kullanılarak normal MFC DLL 'sinden içe aktarılabilir. Normal MFC DLL yazma, oluşturma ve kullanma hakkında bir örnek için bkz. örnek [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap).

USRDLL teriminin Visual C++ belgelerde artık kullanılmadığını unutmayın. MFC 'ye statik olarak bağlanan normal bir MFC DLL 'SI, eski USRDLL ile aynı özelliklere sahiptir.

Statik olarak MFC 'ye bağlı normal MFC DLL 'SI aşağıdaki özelliklere sahiptir:

- İstemci yürütülebilir dosyası, dll 'lerin kullanımını destekleyen herhangi bir dilde yazılabilir (C, C++, Pascal, Visual Basic vb.); MFC uygulaması olması gerekmez.

- DLL, uygulamalar tarafından kullanılan aynı MFC statik bağlantı kitaplıklarına bağlanabilir. Artık dll 'Ler için statik bağlantı kitaplıklarının ayrı bir sürümü yoktur.

- MFC 4,0 sürümünden önce, USRDLL 'ler MFC 'ye statik olarak bağlanan normal MFC DLL 'Leri ile aynı tür işlevselliği sağladı. Visual C++ sürüm 4,0 itibariyle, USRDLL terimi artık kullanılmıyor.

Statik olarak MFC 'ye bağlı normal MFC DLL 'SI aşağıdaki gereksinimlere sahiptir:

- Bu tür DLL, öğesinden türetilmiş bir sınıf örneği oluşturmalıdır `CWinApp` .

- Bu tür DLL `DllMain` MFC tarafından sunulan öğesini kullanır. DLL 'e özgü tüm başlatma kodlarını `InitInstance` üye işlevine ve sonlandırma kodunu `ExitInstance` normal bir MFC uygulamasında olduğu gibi yerleştirin.

- USRDLL terimi kullanılmıyor olsa da, derleyici komut satırında yine "**_USRDLL**" tanımlamanız gerekir. Bu tanım, MFC başlık dosyalarından hangi bildirimlerin çekilacağını belirler.

MFC uygulaması gibi normal MFC DLL 'Lerinin `CWinApp` türetilmiş bir sınıfı ve bu uygulama sınıfının tek bir nesnesi olmalıdır. Ancak, `CWinApp` bir uygulamanın nesnesi gibi, dll nesnesinin bir ana ileti göndericisi yoktur `CWinApp` .

`CWinApp::Run`Uygulamanın ana ileti göndericisinin sahibi olduğu için MEKANIZMANıN dll 'ye uygulanmadığını unutmayın. DLL engelleyici olmayan iletişim kutusu açarsa veya kendi ana çerçeve penceresine sahipse, uygulamanın ana ileti göndericisi dll tarafından, `CWinApp::PreTranslateMessage` DLL 'nin uygulama nesnesinin üye işlevini çağıran bir yordamı çağırmalıdır.

Bu işleve bir örnek için bkz. DLLScreenCap Sample.

Semboller genellikle standart C arabirimi kullanılarak normal MFC DLL 'sinden içe aktarılabilir. Normal MFC DLL 'den dışarıya aktarılmış bir işlevin bildirimi şuna benzer:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Normal bir MFC DLL içindeki tüm bellek ayırmaları DLL içinde kalacak; DLL 'nin, çağrıyı yapan bir yürütülebilir dosyadan geçmemelidir veya buradan alması gerekir:

- MFC nesnelerine işaretçiler

- MFC tarafından ayrılan bellek işaretçileri

Yukarıdakilerden herhangi birini yapmanız gerekiyorsa veya çağıran çalıştırılabilirle DLL arasında MFC 'den türetilmiş nesneler geçirmeniz gerekiyorsa, bir MFC uzantısı DLL oluşturmanız gerekir.

Yalnızca verilerin bir kopyasını yaparsanız, bir uygulama ve DLL arasında C çalışma zamanı kitaplıkları tarafından ayrılan belleğe işaretçiler geçirmek güvenlidir. Bu işaretçileri silmeyin veya yeniden boyutlandırmamalıdır ya da belleğin bir kopyasını oluşturmadan kullanmanız gerekir.

MFC 'ye statik olarak bağlı bir DLL Ayrıca paylaşılan MFC DLL 'Lerine dinamik olarak bağlanamaz. MFC 'ye statik olarak bağlı bir DLL, diğer tüm DLL gibi bir uygulamaya dinamik olarak bağlanır; uygulamalar, diğer herhangi bir DLL gibi buna bağlanır.

Standart MFC statik bağlantı kitaplıkları, [MFC DLL 'leri Için adlandırma kuralları](../mfc/mfc-library-versions.md#mfc-static-library-naming-conventions)bölümünde açıklanan kurala göre adlandırılır. Ancak, MFC sürüm 3,0 ve üzeri ile, bağlantılı olmasını istediğiniz MFC kitaplığının sürümünü bağlayıcıya el ile belirtmek artık gerekli değildir. Bunun yerine, MFC başlık dosyaları, **\_ hata ayıklama** veya **_UNICODE** gibi Önişlemci TANıMLARıNı temel alarak bağlamak üzere MFC kitaplığının doğru sürümünü otomatik olarak belirler. MFC üst bilgi dosyaları, MFC kitaplığının belirli bir sürümünde bağlantı için bağlayıcı arabirimini veren/DEFAULTLIB yönergeleri ekler.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Normal MFC DLL 'Leri başlatma](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [MFC DLL oluşturma](../mfc/reference/mfc-dll-wizard.md)

- [MFC 'ye dinamik olarak bağlı normal MFC DLL 'Leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)
