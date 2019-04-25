---
title: MFC DLL sık sorulan sorular
ms.date: 11/04/2016
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
ms.openlocfilehash: 33a0c9dd1abbfb9375ce1aef53fd152a521ac97d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274124"
---
# <a name="dll-frequently-asked-questions"></a>Sıkça Sorulan DLL Soruları

Aşağıda, DLL'leri hakkında bazı sık sorulan sorular (SSS) istenir.

- [MFC DLL çoklu iş parçacığı oluşturabilir miyim?](#mfc_multithreaded_1)

- [Çok iş parçacıklı uygulamada farklı iş parçacıkları MFC DLL'ine erişebilir mi?](#mfc_multithreaded_2)

- [MFC sınıfları veya bir MFC DLL'inde kullanılamayan işlevleri var mıdır?](#mfc_prohibited_classes)

- [Yüklenirken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](#mfc_optimization)

- [My Normal MFC DLL içinde bir bellek sızıntısı vardır, ancak kodum doğru görünüyor. Bellek sızıntısının yerini nasıl bulabilirim?](#memory_leak)

## <a name="mfc_multithreaded_1"></a> MFC DLL çoklu iş parçacığı oluşturabilir miyim?

Win32 iş parçacığı yerel depolama (TLS) işlevleri gibi kullandığı sürece başlatma sırasında bir MFC DLL güvenli bir şekilde birden çok iş parçacığı oluşturabilirsiniz dışında **TlsAlloc** iş parçacığı yerel depolama alanı ayrılamadı. Ancak, MFC DLL kullanıyorsa **gt;__declspec(thread)** iş parçacığında yerel depolama ayırmak için istemci uygulaması örtük olarak DLL'ye bağlanmalıdır. İstemci uygulaması açıkça DLL çağrısı bağlar, **LoadLibrary** başarıyla DLL yüklenmez. DLL'lerde thread-local değişkenleri hakkında daha fazla bilgi için bkz. [iş parçacığı](../cpp/thread.md).

Başlatma sırasında yeni bir MFC iş parçacığı oluşturan bir MFC DLL, bir uygulama tarafından yüklendiğinde yanıt vermeyi durdurur. Her bir iş parçacığı çağırarak oluşturulduğunda bu içerir `AfxBeginThread` veya `CWinThread::CreateThread` içinde:

- `InitInstance` , Bir `CWinApp`-Normal MFC DLL'SİNİN türetilmiş.

- Sağlanan `DllMain` veya **RawDllMain** Normal MFC DLL'SİNİN işlevi.

- Sağlanan `DllMain` veya **RawDllMain** bir MFC uzantılı DLL işlevi.

## <a name="mfc_multithreaded_2"></a> Çok iş parçacıklı uygulamada farklı iş parçacıkları MFC DLL'ine erişebilir mi?

Çok iş parçacıklı uygulamalar farklı iş parçacıklarından dinamik olarak MFC'ye bağlanan normal MFC DLL'leri ve MFC uzantısı DLL'leri erişebilirsiniz. Ve Visual C++ 4.2 sürümü itibarıyla uygulamada oluşturulmuş birden çok iş parçacığından MFC DLL'lerine Normal MFC DLL'leri uygulamaya erişebilir.

4.2 sürümü önce statik olarak MFC'ye bağlı normal MFC DLL'SİNİN için yalnızca bir dış iş parçacığı paylaşılmasıdır.

USRDLL terimi artık Visual C++ belgelerinde kullanılan unutmayın. Statik olarak MFC'ye bağlı normal MFC DLL'SİNİN önceki USRDLL ile aynı özelliklere sahiptir.

## <a name="mfc_prohibited_classes"></a> MFC sınıfları veya bir MFC DLL'inde kullanılamayan işlevleri var mıdır?

Uzantı DLL'leri kullanma `CWinApp`-derived class istemci uygulaması. Bunlar, kendi olmamalıdır `CWinApp`-türetilmiş sınıf.

Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne gibi bir MFC uygulaması. Farklı `CWinApp` uygulama nesnesinin `CWinApp` DLL nesnesinin bir ana ileti pompası sahip değil.

Dikkat edin çünkü `CWinApp::Run` mekanizması, bir DLL için geçerli değildir, uygulamanın ana ileti göndericisi. DLL kalıcı olmayan iletişim kutuları açılır ya da kendi ana penceresi varsa, uygulamanın ana ileti pompası sırayla çağırır DLL tarafından dışarı aktarılan bir yordam çağırmalıdır `CWinApp::PreTranslateMessage` DLL'nin uygulama nesnesinin üye işlevi.

## <a name="mfc_optimization"></a> Hangi iyileştirme tekniklerini istemci uygulaması geliştirmek için kullanmalıyım&#39;yüklenirken s performans?

DLL'niz MFC normal değiştirilmesi, statik olarak bağlı normal MFC DLL'SİNİN ise dinamik olarak MFC'ye bağlı bir MFC DLL dosyasının boyutunu azaltır.

DLL'de dışa aktarılan işlevleri çok sayıda varsa işlevleri dışarı aktarmak için bir .def dosyası kullanmanıza (kullanmak yerine **__declspec(dllexport)**) ve .def dosyası kullanmanıza [NONAME özniteliği](exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) her işlevi dışa. NONAME özniteliği yalnızca sıralı değerlerine ve dosya boyutunu azaltır DLL'nin dışa aktarma tablosunda, depolanacak işlevi adı değil neden olur.

Uygulama yüklendiğinde uygulama dolaylı olarak bağlantılı DLL'ler yüklenir. Yüklenirken performansını artırmak için farklı DLL'lere DLL bölmeyi deneyin. Bir DLL'e hemen sonra çağıran uygulamanız için gereken tüm işlevleri koyun ve bu DLL'ye örtük olarak bağlama çağıran uygulamanızı oluşturdunuz. Çağıran uygulama hemen gerekmeyen diğer işlevleri başka bir DLL içine yerleştirin ve sahip uygulamayı açıkça bağlanmak için bu DLL. Daha fazla bilgi için [çalıştırılabilir bir DLL'ye bağlandığı](linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use).

## <a name="memory_leak"></a> Orada&#39;s my Normal MFC DLL'SİNİN ancak kodum bir bellek sızıntısı iyi görünüyor. Bellek sızıntısının yerini nasıl bulabilirim?

Olası bir nedeni de bellek sızıntısı MFC ileti işleyicisi işlevler içinde kullanılan geçici nesneler oluşturmasıdır. MFC uygulamalarında, bu geçici nesneler otomatik olarak temizlenir `CWinApp::OnIdle()` iletilerini işleme arasında çağrılan işlev. Ancak, MFC dinamik bağlantı kitaplıklarını (DLL'ler) içinde `OnIdle()` işlevi otomatik olarak çağrılmaz. Sonuç olarak, geçici nesneler otomatik olarak temizlenir değil. Geçici nesneleri temizlemek için DLL'i açıkça çağırmalıdır `OnIdle(1)` düzenli aralıklarla.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)
