---
title: MFC 'ye dinamik olarak bağlı normal MFC DLL 'Leri
ms.date: 11/04/2016
helpviewer_keywords:
- regular MFC DLLs [C++], dynamically linked to MFC
- AFX_MANAGE_STATE macro
- DLLs [C++], regular
- shared DLL versions [C++]
- dynamically linked DLLs [C++]
ms.assetid: b4f7ab92-8723-42a5-890e-214f4e29dcd0
ms.openlocfilehash: 3bfed5f75dab4c501708950fdb99f53c40ec142c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315007"
---
# <a name="regular-mfc-dlls-dynamically-linked-to-mfc"></a>MFC 'ye dinamik olarak bağlı normal MFC DLL 'Leri

MFC 'ye dinamik olarak bağlı normal MFC DLL, MFC 'yi dahili olarak kullanan bir DLL 'dir ve DLL 'deki verilen işlevler MFC ya da MFC olmayan yürütülebilir dosyalar tarafından çağrılabilir. Adın açıkladığı gibi, bu tür DLL MFC 'nin dinamik bağlantı kitaplığı sürümü (MFC 'nin paylaşılan sürümü olarak da bilinir) kullanılarak oluşturulmuştur. İşlevler genellikle standart C arabirimi kullanılarak normal MFC DLL 'sinden içe aktarılabilir.

Geçerli modül durumunu DLL `AFX_MANAGE_STATE` için bir tane olarak ayarlamak üzere MFC 'ye dinamik olarak bağlanan normal MFC DLL 'lerinde tüm aktarılmış işlevlerin başlangıcında makroyu eklemeniz gerekir. Bu, DLL 'den aktarılmış işlevlerin başlangıcına aşağıdaki kod satırı eklenerek yapılır:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

MFC 'ye dinamik olarak bağlı normal MFC DLL 'SI aşağıdaki özelliklere sahiptir:

- Bu, Visual C++ 4,0 tarafından sunulan yeni bir DLL türüdür.

- İstemci yürütülebilir dosyası, dll 'lerin kullanımını destekleyen herhangi bir dilde yazılabilir (C, C++, Pascal, Visual Basic vb.); MFC uygulaması olması gerekmez.

- Statik olarak bağlanan normal MFC DLL 'inin aksine bu tür DLL, MFC DLL 'ye (paylaşılan MFC DLL olarak da bilinir) dinamik olarak bağlanır.

- Bu tür DLL 'ye bağlı MFC içeri aktarma kitaplığı, MFC uzantı dll 'Leri veya MFC DLL 'SI (MFCxx (D). lib kullanan uygulamalar için kullanılan bir kitaplıktır.

MFC 'ye dinamik olarak bağlı normal MFC DLL 'SI aşağıdaki gereksinimlere sahiptir:

- Bu dll 'Ler, MFC DLL 'sine dinamik olarak bağlanmış bir yürütülebilir gibi **_AFXDLL** tanımlanmış ile derlenir. Ancak, MFC 'ye statik olarak bağlanan normal bir MFC DLL gibi **_USRDLL** de tanımlanmıştır.

- Bu tür DLL, bir `CWinApp`türetilmiş sınıf örneği oluşturmalıdır.

- Bu tür DLL MFC tarafından `DllMain` sunulan öğesini kullanır. DLL 'e özgü tüm başlatma kodlarını `InitInstance` üye işlevine ve sonlandırma kodunu normal bir MFC uygulamasında `ExitInstance` olduğu gibi yerleştirin.

Bu tür bir DLL MFC 'nin dinamik bağlantı kitaplığı sürümünü kullandığından, geçerli modül durumunu DLL için bir tane olarak ayarlamanız gerekir. Bunu yapmak için, DLL 'den aktarılmış her işlevin başlangıcında [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) makrosunu kullanın.

MFC uygulaması gibi normal MFC dll `CWinApp`'lerinin türetilmiş bir sınıfı ve bu uygulama sınıfının tek bir nesnesi olmalıdır. Ancak, bir `CWinApp` uygulamanın `CWinApp` nesnesi gibi, dll nesnesinin bir ana ileti göndericisi yoktur.

Uygulamanın ana ileti `CWinApp::Run` göndericisinin sahibi olduğu için MEKANIZMANıN dll 'ye uygulanmadığını unutmayın. DLL 'niz modsuz iletişim kutusu alıyorsa veya kendi ana çerçeve penceresine sahipse, uygulamanızın ana ileti göndericisi, çağıran `CWinApp::PreTranslateMessage`bir dll 'den aktarılmış yordam çağırmalıdır.

DLL 'e özgü tüm başlatma işlevlerini normal MFC `CWinApp::InitInstance` uygulamasındaki gibi üye işlevine yerleştirin. `CWinApp` Türetilmiş `CWinApp::ExitInstance` SıNıFıNıZıN üye işlevi, DLL kaldırılmadan önce MFC tarafından verilen `DllMain` işlevden çağrılır.

MFCx0. dll ve MSVCR * 0. dll (veya benzer dosyalar) paylaşılan DLL 'Lerini uygulamanızla dağıtmanız gerekir.

MFC 'ye dinamik olarak bağlı bir DLL de MFC 'ye statik olarak bağlanamaz. Uygulamalar, diğer tüm DLL gibi MFC 'ye dinamik olarak bağlı normal MFC DLL 'Lerine bağlanır.

Semboller genellikle standart C arabirimi kullanılarak normal MFC DLL 'sinden içe aktarılabilir. Normal MFC DLL 'den dışarıya aktarılmış bir işlevin bildirimi şuna benzer:

```
extern "C" __declspec(dllexport) MyExportedFunction( );
```

Normal bir MFC DLL içindeki tüm bellek ayırmaları DLL içinde kalacak; DLL 'nin, çağrıyı yapan bir yürütülebilir dosyadan geçmemelidir veya buradan alması gerekir:

- MFC nesnelerine işaretçiler

- MFC tarafından ayrılan bellek işaretçileri

Yukarıdakilerden birini yapmanız gerekiyorsa veya çağıran çalıştırılabilir ile DLL arasında MFC 'den türetilmiş nesneler geçirmeniz gerekiyorsa, bir MFC uzantı DLL oluşturmanız gerekir.

Yalnızca verilerin bir kopyasını yaparsanız, bir uygulama ve DLL arasında C çalışma zamanı kitaplıkları tarafından ayrılan belleğe işaretçiler geçirmek güvenlidir. Bu işaretçileri silmeyin veya yeniden boyutlandırmamalıdır ya da belleğin bir kopyasını oluşturmadan kullanmanız gerekir.

MFC 'ye dinamik olarak bağlanan normal bir MFC DLL 'SI oluştururken, MFC modül durumunu doğru bir şekilde değiştirmek için makro [AFX_MANAGE_STATE](../mfc/reference/extension-dll-macros.md#afx_manage_state) kullanmanız gerekir. Bu, DLL 'den aktarılmış işlevlerin başlangıcına aşağıdaki kod satırı eklenerek yapılır:

```
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))
```

**AFX_MANAGE_STATE** MAKROSU, MFC 'ye statik olarak veya MFC uzantı dll 'lerine statik olarak bağlanan normal MFC DLL 'lerinde kullanılmamalıdır. Daha fazla bilgi için bkz. [MFC modüllerinin durum verilerini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md).

Normal MFC DLL yazma, oluşturma ve kullanma hakkında bir örnek için bkz. örnek [DLLScreenCap](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/MFC/advanced/DllScreenCap). MFC 'ye dinamik olarak bağlanan normal MFC DLL 'Leri hakkında daha fazla bilgi için, örneğin özet içindeki "DLLScreenCap 'i MFC DLL ile dinamik olarak bağlama" başlıklı bölüme bakın.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [Normal MFC DLL 'Leri başlatma](run-time-library-behavior.md#initializing-regular-dlls)

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC 'ye dinamik olarak bağlı normal bir MFC DLL 'nin modül durumları](module-states-of-a-regular-dll-dynamically-linked-to-mfc.md)

- [MFC modüllerinin durum verisini yönetme](../mfc/managing-the-state-data-of-mfc-modules.md)

- [Normal MFC DLL 'Lerinde Database, OLE ve Sockets MFC uzantı dll 'Lerini kullanma](using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)

- [DLL 'nin bir parçası olarak MFC kullanma](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

## <a name="see-also"></a>Ayrıca bkz.

[DLL Türleri](kinds-of-dlls.md)
