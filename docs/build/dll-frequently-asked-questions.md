---
title: MFC DLL sıkça sorulan sorular
ms.date: 05/06/2019
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 9108aaf3fcface847b0391455a2aecd4d45658c4
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417350"
---
# <a name="dll-frequently-asked-questions"></a>Sıkça Sorulan DLL Soruları

Aşağıda, dll 'Ler hakkında sık sorulan bazı sorular (SSS) verilmiştir.

- [Bir MFC DLL birden çok iş parçacığı oluşturabilir mi?](#mfc_multithreaded_1)

- [Çok iş parçacıklı bir uygulama farklı iş parçacıklarında bir MFC DLL 'sine erişebilmi?](#mfc_multithreaded_2)

- [MFC DLL 'de kullanılamayan MFC sınıfları veya işlevleri var mı?](#mfc_prohibited_classes)

- [Yükleme sırasında istemci uygulamasının performansını iyileştirmek için hangi iyileştirme tekniklerini kullanmalıyım?](#mfc_optimization)

- [Normal MFC DLL 'imde bellek sızıntısı var, ancak kodum iyi görünüyor. Bellek sızıntısını nasıl bulabilirim?](#memory_leak)

## <a name="can-an-mfc-dll-create-multiple-threads"></a><a name="mfc_multithreaded_1"></a>Bir MFC DLL birden çok iş parçacığı oluşturabilir mi?

Başlatma işlemi haricinde, bir MFC DLL, iş parçacığı yerel depolama alanı ayırmak için **TlsAlloc** gibi Win32 iş parçacığı yerel depolama (TLS) işlevlerini kullandığı sürece güvenli bir şekilde birden çok iş parçacığı oluşturabilir. Ancak, bir MFC DLL iş parçacığı yerel depolama alanı ayırmak için **__declspec (iş parçacığı)** kullanıyorsa, ISTEMCI uygulamanın DLL 'ye örtük olarak bağlanması gerekir. İstemci uygulaması açıkça DLL 'ye bağlanıyorsa, **LoadLibrary** 'e YAPıLAN çağrı dll 'yi başarıyla yüklemez. Dll 'Lerdeki iş parçacığı yerel değişkenleri hakkında daha fazla bilgi için bkz. [thread](../cpp/thread.md).

Başlangıç sırasında yeni bir MFC iş parçacığı oluşturan MFC DLL 'SI, bir uygulama tarafından yüklendiğinde yanıt vermeyi durdurur. Bu, çağırarak `AfxBeginThread` veya `CWinThread::CreateThread` içinde bir iş parçacığının oluşturulduğu her seferinde şunları içerir:

- `InitInstance` Normal mfc dll `CWinApp`içindeki bir türetilmiş nesne.

- Normal bir `DllMain` MFC DLL 'de sağlanan veya **RawDllMain** işlevi.

- Bir MFC `DllMain` uzantı dll dosyasında sağlanan veya **RawDllMain** işlevi.

## <a name="can-a-multithreaded-application-access-an-mfc-dll-in-different-threads"></a><a name="mfc_multithreaded_2"></a>Çok iş parçacıklı bir uygulama farklı iş parçacıklarında bir MFC DLL 'sine erişebilmi?

Çok iş parçacıklı uygulamalar, farklı iş parçacıklarından MFC ve MFC uzantı dll 'Lerine dinamik olarak bağlanan normal MFC DLL 'Lerine erişebilir. Uygulama, uygulamada oluşturulan birden çok iş parçacığından MFC 'ye statik olarak bağlanan normal MFC DLL 'Lerine erişebilir.

## <a name="are-there-any-mfc-classes-or-functions-that-cannot-be-used-in-an-mfc-dll"></a><a name="mfc_prohibited_classes"></a>MFC DLL 'de kullanılamayan MFC sınıfları veya işlevleri var mı?

Uzantı dll 'Leri, `CWinApp`istemci uygulamasının türetilmiş sınıfını kullanır. Kendi kendine `CWinApp`türetilmiş sınıfına sahip olmaması gerekir.

MFC uygulaması gibi normal MFC dll `CWinApp`'lerinin türetilmiş bir sınıfı ve bu uygulama sınıfının tek bir nesnesi olmalıdır. Uygulamanın `CWinApp` nesnesinin aksıne, dll `CWinApp` nesnesinin, ana ileti göndericisi yok.

`CWinApp::Run` MEKANIZMANıN dll 'ye uygulanmadığından, uygulamanın ana ileti göndericisinin sahibi olduğundan emin olmak. DLL kalıcı olmayan iletişim kutuları açarsa veya kendi ana çerçeve penceresine sahipse, uygulamanın ana ileti göndericisinin DLL tarafından dışarıya aktarılmış bir yordamı çağırması gerekir ve bu da DLL 'nin uygulama nesnesinin `CWinApp::PreTranslateMessage` üye işlevini çağırır.

## <a name="what-optimization-techniques-should-i-use-to-improve-the-client-application39s-performance-when-loading"></a><a name="mfc_optimization"></a>Yükleme sırasında istemci uygulamasını&#39;s performansını iyileştirmek için hangi iyileştirme tekniklerini kullanmalıyım?

DLL 'niz MFC 'ye statik olarak bağlanan normal bir MFC DLL ise, bunu MFC 'ye dinamik olarak bağlanan normal bir MFC DLL ile değiştirmek dosya boyutunu azaltır.

DLL 'de çok sayıda dışarı aktarılmış işlev varsa, işlevleri dışarı aktarmak için bir. def dosyası kullanın ( **__declspec (dllexport)** kullanmak yerine) ve her dışa aktarılmış işlevde. def dosya [noname özniteliğini](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) kullanın. NONAME özniteliği, işlev adının DLL 'nin dışarı aktarma tablosunda depolanmasına ve dosya boyutunu azaltacak şekilde değil, yalnızca sıralı değer oluşmasına neden olur.

Uygulamaya örtük olarak bağlı olan DLL 'Ler, uygulama yüklendiğinde yüklenir. Yükleme sırasında performansı artırmak için DLL 'yi farklı dll 'Lere bölmek için deneyin. Çağıran uygulamanın bir DLL 'ye yükledikten hemen sonra ihtiyacı olan tüm işlevleri yerleştirin ve çağıran uygulamanın bu DLL 'ye örtülü olarak bağlantısını yapın. Çağıran uygulamanın başka bir DLL 'ye hemen gerek duymadığından diğer işlevleri ekleyin ve uygulamanın bu DLL 'ye açık bir şekilde bağlantı altına alın. Daha fazla bilgi için bkz. bir [yürütülebilir dosyayı dll 'ye bağlama](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use).

## <a name="there39s-a-memory-leak-in-my-regular-mfc-dll-but-my-code-looks-fine-how-can-i-find-the-memory-leak"></a><a name="memory_leak"></a>Normal MFC DLL 'imde bellek sızıntısı&#39;, ancak kodum iyi görünüyor. Bellek sızıntısını nasıl bulabilirim?

Bellek sızıntısının olası nedenlerinden biri, MFC 'nin ileti işleyici işlevleri içinde kullanılan geçici nesneler oluşturmasıdır. MFC uygulamalarında bu geçici nesneler, işleme iletileri arasında çağrılan `CWinApp::OnIdle()` işlevde otomatik olarak temizlenir. Ancak, MFC dinamik bağlantı kitaplıkları (dll 'Ler) içinde, `OnIdle()` işlev otomatik olarak çağrılmaz. Sonuç olarak, geçici nesneler otomatik olarak temizlenmez. Geçici nesneleri temizlemek için DLL 'nin belirli aralıklarla düzenli olarak çağrılması `OnIdle(1)` gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
