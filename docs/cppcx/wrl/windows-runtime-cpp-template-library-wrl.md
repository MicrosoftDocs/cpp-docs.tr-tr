---
title: Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)
ms.date: 11/04/2016
ms.topic: overview
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 41b8b45f89e94b8de2ddcb9c87bfd72122db8e1a
ms.sourcegitcommit: 27d9db019f6d84c94de9e6aff0170d918cee6738
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/06/2020
ms.locfileid: "75676944"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)

Windows Çalışma Zamanı C++ şablon kitaplığı (WRL), Windows çalışma zamanı bileşenleri yazmak ve kullanmak için alt düzey bir yol sağlayan bir şablon kitaplığıdır.

> [!NOTE]
> WRL 'nin artık Windows Çalışma Zamanı API C++'leri için standart bir c++ 17 dil projeksiyonu olan/wınrt tarafından değiştirildi. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır.
>
> /Wınrt ile C++, standartlara uyumlu c++ 17 derleyicisini kullanarak Windows çalışma zamanı API 'leri hem tüketin hem de yazabilirsiniz. C++/Wınrt genellikle daha iyi gerçekleştirir ve Windows Çalışma Zamanı diğer dil seçeneklerinden daha küçük ikili dosyalar üretir. /CX ve WRL 'yi C++desteklemeye devam edeceğiz, ancak yeni uygulamaların/Winrtı kullanmasını C++önemle tavsiye ederiz. Daha fazla bilgi için bkz [ C++./wınrt](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).

## <a name="benefits"></a>Yararları

Windows Çalışma Zamanı C++ şablon kitaplığı, bileşen nesne MODELI (com) bileşenlerini daha kolay bir şekilde uygulamanıza ve kullanmanıza olanak sağlar. Bu, nesnelerin ömrünü yönetmek ve bir işlemin başarılı veya başarısız olup olmadığını anlamak üzere HRESULT değerlerini test etmek için başvuru sayımı gibi temizlik tekniklerini sağlar. Windows Çalışma Zamanı C++ şablonu kitaplığını başarıyla kullanmak için bu kuralları ve teknikleri dikkatle izlemeniz gerekir.

C++/CX Windows çalışma zamanı bileşenleri kullanmanın yüksek düzey, dil tabanlı bir yoludur. Hem Windows Çalışma Zamanı C++ şablon kitaplığı hem C++de/CX, sizin adınıza otomatik olarak görevleri gerçekleştirerek Windows çalışma zamanı kod yazmayı basitleştirir.

Windows Çalışma Zamanı C++ şablon kitaplığı ve C++/CX farklı avantajlar sağlar. Aşağıda, C++ C++/CX yerine Windows çalışma zamanı şablon kitaplığını kullanmak isteyebileceğiniz bazı nedenler verilmiştir:

- Windows Çalışma Zamanı C++ şablon kitaplığı, Windows çalışma zamanı uygulama ikili ARABIRIMINE (ABI) kısa soyutlama ekler ve bu sayede, Windows çalışma zamanı API 'leri daha iyi oluşturmak veya kullanmak için temel kodu denetlemenize olanak tanır.

- C++/CX, COM HRESULT değerlerini özel durumlar olarak temsil eder. COM kullanan veya özel durum kullanmayan bir kod tabanı devraldıysanız, özel durumları kullanmak zorunda olmadığınızdan Windows Çalışma Zamanı C++ şablon kitaplığının Windows çalışma zamanı ile çalışması için daha doğal bir yol olduğunu fark edebilirsiniz.

   > [!NOTE]
   > Windows Çalışma Zamanı C++ şablon kitaplığı HRESULT değerlerini kullanır ve özel durum oluşturmaz. Ayrıca, Windows Çalışma Zamanı C++ şablon kitaplığı, uygulama kodunuz bir özel durum oluşturduğunda nesnelerin doğru şekilde yok edilmesinin sağlanmasına yardımcı olması için akıllı işaretçiler ve rampaya da caii modelini kullanır. Akıllı işaretçiler ve Rat 'lar hakkında daha fazla bilgi için bkz. [Smart işaretçiler](../../cpp/smart-pointers-modern-cpp.md) ve [nesneler (çii)](../../cpp/objects-own-resources-raii.md).

- Windows Çalışma Zamanı C++ şablon kitaplığının amacı ve TASARıMı, com nesnelerinin programlamasını basitleştiren bir şablon tabanlı C++ sınıflar kümesi olan ETKIN şablon kitaplığı (ATL) tarafından ilham olarak gelir. Windows Çalışma Zamanı C++ şablon kitaplığı Windows çalışma zamanı sarmak için C++ standart kullandığından, daha kolay bağlantı kurabilir ve ATL 'de WINDOWS çalışma zamanı yazılan birçok mevcut com bileşeni ile etkileşim kurabilirsiniz. Zaten ATL 'yi biliyorsanız Windows Çalışma Zamanı C++ şablon kitaplığı programlamanın daha kolay olduğunu fark edebilirsiniz.

## <a name="getting-started"></a>Başlarken

Windows Çalışma Zamanı C++ şablon kitaplığı ile hemen çalışmaya başlamanıza yardımcı olabilecek bazı kaynaklar aşağıda verilmiştir.

[Windows Çalışma Zamanı Kitaplığı (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
Bu Channel 9 videosunda Windows Çalışma Zamanı C++ şablon kitaplığının, evrensel WINDOWS platformu (UWP) uygulamaları yazmanıza ve Windows çalışma zamanı bileşenleri yazıp tüketmenize nasıl yardımcı olduğu hakkında daha fazla bilgi edinin.

[Nasıl yapılır: Windows Çalışma Zamanı bileşenini etkinleştirme ve kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Windows Çalışma Zamanı başlatmak ve Windows Çalışma Zamanı bileşenini etkinleştirmek C++ ve kullanmak için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

[Nasıl yapılır: zaman uyumsuz Işlemleri tamamlar](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Zaman uyumsuz işlemleri başlatmak ve işlemler C++ tamamlandığında iş gerçekleştirmek için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

[Nasıl yapılır: olayları Işleme](how-to-handle-events-using-wrl.md)<br/>
Bir Windows Çalışma Zamanı nesnesinin olaylarına abone olmak C++ ve olayları işlemek için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

[İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
[Microsoft medya altyapısı](/windows/win32/medfound/microsoft-media-foundation-sdk)kullanan bir UWP uygulaması oluşturmayı öğrenin.

[Nasıl yapılır: klasik bir COM bileşeni oluşturma](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Temel bir COM bileşeni oluşturmak için C++ Windows çalışma zamanı şablon kitaplığının ve bir masaüstü uygulamasından com bileşenini kaydetmek ve kullanmak için temel bir yol gösterir.

[Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma](how-to-instantiate-wrl-components-directly.md)<br/>
[Microsoft:: WRL:: Make](make-function.md) ve [Microsoft:: wrl::D Euçlar:: makeanınvoınitialize](makeandinitialize-function.md) işlevlerini kullanarak onu tanımlayan modülden bir bileşen örneğini oluşturmayı öğrenin.

[Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
. Winmd meta verilerinden bir IDL dosyası oluşturarak WRL 'den özel Windows Çalışma Zamanı bileşenlerini nasıl kullanacağınızı gösterir.

[İzlenecek Yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
UWP uygulamasındaki bir Web hizmetine HTTP GET ve POST istekleri göndermek için [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimlerinin görevlerle birlikte nasıl kullanılacağını gösterir.

[Bing Haritalar seyahat Iyileştirici örneği](https://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)<br/>
, [Izlenecek yol: görevleri ve XML http Isteklerini kullanarak](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) BIR bütün UWP uygulaması bağlamında tanımlanan `HttpRequest` sınıfını kullanır.

[C++ ÖRNEKLE Windows çalışma zamanı dll bileşeni oluşturma](https://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)<br/>
İşlem içi DLL bileşeni oluşturmak ve C++ bunu C++/CX, JavaScript ve ile C#kullanmak için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

[DirectX mermer Maze oyun örneği](https://docs.microsoft.com/samples/microsoft/windows-appsample-marble-maze/directx-marble-maze-game-sample/)<br/>
DirectX gibi COM bileşenlerinin ömrünü yönetmek C++ ve tam 3-b oyun bağlamında Medya Altyapısı için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

[Masaüstü uygulamaları örneğinden bildirimler gönderme](https://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)<br/>
Bir masaüstü uygulamasından bildirim bildirimleri ile C++ çalışmak için Windows çalışma zamanı şablon kitaplığının nasıl kullanılacağını gösterir.

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>ATL C++ ile karşılaştırıldığında şablon kitaplığı Windows çalışma zamanı

Windows Çalışma Zamanı C++ şablon kitaplığı, küçük ve hızlı com nesneleri oluşturmak Için kullanabileceğiniz etkin şablon KITAPLıĞıNA (ATL) benzer. Windows Çalışma Zamanı C++ şablon KITAPLıĞı ve ATL, modüller içindeki nesnelerin tanımı, açık arabirimlerin kaydı ve fabrika kullanarak nesne oluşturma gibi kavramları de paylaşır. ATL hakkında bilginiz varsa Windows Çalışma Zamanı C++ şablon kitaplığı ile rahat bir şekilde karşılaşabilirsiniz.

Windows Çalışma Zamanı C++ şablon KITAPLıĞı, UWP uygulamaları IÇIN gerekli com işlevlerini destekler. Bu nedenle, ATL 'den farklıdır çünkü şu şekilde COM özellikleri için doğrudan desteği atlar:

- toplama

- hisse senedi uygulamaları

- Çift arabirimler (`IDispatch`)

- Standart Numaralandırıcı arabirimleri

- bağlantı noktaları

- yırma arabirimleri

- OLE katıştırma

- ActiveX denetimleri

- COM+

## <a name="concepts"></a>Kavramlar

Windows Çalışma Zamanı C++ şablon kitaplığı, birkaç temel kavramı temsil eden türler sağlar. Aşağıdaki bölümlerde bu türler açıklanır.

### <a name="comptr"></a>ComPtr

[ComPtr](comptr-class.md) , şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türüdür. Arabiriminden türetilmiş bir nesnenin üyelerine erişebilen bir değişken bildirmek için `ComPtr` kullanın. `ComPtr`, temel alınan arabirim işaretçisi için otomatik olarak bir başvuru sayısı tutar ve başvuru sayısı sıfıra gittiğinde arabirimi yayınlar.

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](runtimeclass-class.md) , belirtilen arabirimlerin kümesini devralan bir örneklenmiş sınıfı temsil eder. Bir `RuntimeClass` nesnesi, bir veya daha fazla Windows Çalışma Zamanı COM arabirimine yönelik destek bileşimini veya bir bileşene zayıf bir başvuruyu sağlayabilir.

### <a name="module"></a>Modülü

[Modül](module-class.md) bir ilişkili nesneler koleksiyonunu temsil eder. Bir `Module` nesnesi, diğer uygulamaların bir nesne kullanmasına olanak tanıyan nesne ve kayıt oluşturan sınıf fabrikalarını yönetir.

### <a name="callback"></a>Callback

[Geri çağırma](callback-function-wrl.md) işlevi, üye işlevi bir olay işleyicisi (bir geri çağırma yöntemi) olan bir nesne oluşturur. Zaman uyumsuz işlemler yazmak için `Callback` işlevini kullanın.

### <a name="eventsource"></a>EventSource

[EventSource](eventsource-class.md) , *temsilci* olay işleyicilerini yönetmek için kullanılır. Bir temsilci C++ uygulamak için Windows çalışma zamanı Şablon kitaplığı kullanın ve temsilcileri eklemek, kaldırmak ve çağırmak için `EventSource` kullanın.

### <a name="asyncbase"></a>AsyncBase

[AsyncBase](asyncbase-class.md) Windows çalışma zamanı zaman uyumsuz programlama modelini temsil eden sanal yöntemler sağlar. Zaman uyumsuz bir işlemin ilerlemesini Başlatan, durduran veya denetleyen özel bir sınıf oluşturmak için bu sınıftaki üyeleri geçersiz kılın.

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) , serbest iş parçacıklı Sıralayıcı nesnesini temsil eder. `FtmBase`, genel bir arabirim tablosu (GIT) oluşturur ve sıralama ve proxy nesnelerinin yönetilmesine yardımcı olur.

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) , erişilebilir olabilecek veya erişilemeyen bir nesneye başvuran *zayıf bir başvuruyu*temsil eden bir akıllı işaretçi türüdür. `WeakRef` nesnesi, klasik COM tarafından değil yalnızca Windows Çalışma Zamanı tarafından kullanılabilir.

`WeakRef` nesnesi genellikle varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil eder. Örneğin, bir `WeakRef` nesnesi bir dosya nesnesine başvurabilir. Dosya açıkken `WeakRef` geçerli olur ve başvurulan dosya erişilebilir olur. Ancak dosya kapalıyken `WeakRef` geçersiz olur ve dosyaya erişilemez.

## <a name="related-topics"></a>İlgili Konular

|||
|-|-|
|[Kategoriye göre anahtar API 'Leri](key-wrl-apis-by-category.md)|Birincil Windows Çalışma Zamanı C++ şablon kitaplık türlerini, işlevleri ve makroları vurgular.|
|[Başvuru](wrl-reference.md)|Windows Çalışma Zamanı C++ şablon kitaplığı için başvuru bilgilerini içerir.|
|[Hızlı Başvuru (C++/CX)](../../cppcx/quick-reference-c-cx.md)|Windows Çalışma Zamanı destekleyen C++/CX özelliklerini kısaca açıklar.|
|[Windows Çalışma Zamanı bileşenlerini görsel olarak kullanmaC++](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)|Temel bir Windows Çalışma Zamanı bileşeni C++oluşturmak için/CX 'in nasıl kullanılacağını gösterir.|
