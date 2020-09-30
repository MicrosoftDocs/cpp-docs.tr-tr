---
title: Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)
ms.date: 11/04/2016
ms.topic: overview
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
ms.openlocfilehash: 12bda00d6687340fbddfb8f81bbb83b6c2bd98a6
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509800"
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)

Windows Çalışma Zamanı C++ Şablon kitaplığı (WRL), Windows Çalışma Zamanı bileşenleri yazmak ve kullanmak için düşük düzey bir yol sağlayan bir şablon kitaplığıdır.

> [!NOTE]
> WRL 'nin artık Windows Çalışma Zamanı API 'Leri için standart bir C++ 17 dil projeksiyonu olan C++/Wınrt tarafından değiştirildi. C++/Wınrt, sürüm 1803 ' den Windows 10 SDK ' da kullanılabilir. C++/Wınrt tamamen başlık dosyalarında uygulanır ve modern Windows API 'sine ilk sınıf erişim sağlamak için tasarlanmıştır.
>
> C++/Wınrt ile, standartlara uyumlu C++ 17 derleyicisini kullanarak Windows Çalışma Zamanı API 'Leri hem tüketin hem de yazabilirsiniz. C++/Wınrt genellikle daha iyi çalışır ve Windows Çalışma Zamanı için diğer dil seçeneklerinden daha küçük ikili dosyalar üretir. C++/CX ve WRL 'yi desteklemeye devam edeceğiz, ancak yeni uygulamaların C++/Wınrtrtı kullanmasını önemle öneririz. Daha fazla bilgi için bkz. [C++/Wınrt](/windows/uwp/cpp-and-winrt-apis/index).

## <a name="benefits"></a>Yararları

Windows Çalışma Zamanı C++ Şablon kitaplığı, bileşen nesne modeli (COM) bileşenlerini daha kolay bir şekilde uygulamanıza ve kullanmanıza olanak sağlar. Bu, nesnelerin ömrünü yönetmek ve bir işlemin başarılı veya başarısız olup olmadığını anlamak üzere HRESULT değerlerini test etmek için başvuru sayımı gibi temizlik tekniklerini sağlar. Windows Çalışma Zamanı C++ şablon kitaplığını başarıyla kullanmak için bu kuralları ve teknikleri dikkatle izlemeniz gerekir.

C++/CX Windows Çalışma Zamanı bileşenleri kullanmanın yüksek düzey, dil tabanlı bir yoludur. Windows Çalışma Zamanı C++ Şablon kitaplığı ve C++/CX her ikisi de, sizin adınıza otomatik olarak görevleri gerçekleştirerek Windows Çalışma Zamanı kod yazmayı basitleştirir.

Windows Çalışma Zamanı C++ Şablon kitaplığı ve C++/CX farklı avantajlar sağlar. C++/CX yerine Windows Çalışma Zamanı C++ şablon kitaplığını kullanmak isteyebileceğiniz bazı nedenler şunlardır:

- Windows Çalışma Zamanı C++ Şablon kitaplığı, Windows Çalışma Zamanı uygulama Ikili arabirimine (ABı) kısa soyutlama ekler ve bu sayede, Windows Çalışma Zamanı API 'Leri daha iyi oluşturmak veya kullanmak için temel kodu denetlemenize olanak sağlar.

- C++/CX, COM HRESULT değerlerini özel durumlar olarak temsil eder. COM kullanan veya özel durum kullanmayan bir kod tabanı devraldıysanız, özel durumları kullanmak zorunda olmadığınızdan Windows Çalışma Zamanı C++ şablonu kitaplığının Windows Çalışma Zamanı ile çalışması için daha doğal bir yol olduğunu fark edebilirsiniz.

   > [!NOTE]
   > Windows Çalışma Zamanı C++ Şablon kitaplığı HRESULT değerlerini kullanır ve özel durum oluşturmaz. Ayrıca, Windows Çalışma Zamanı C++ Şablon kitaplığı, uygulama kodunuz bir özel durum oluşturduğunda nesnelerin doğru şekilde yok edildiğini garantilemeye yardımcı olması için akıllı işaretçiler ve rampaya da caii modelini kullanır. Akıllı işaretçiler ve Rat 'lar hakkında daha fazla bilgi için bkz. [Smart işaretçiler](../../cpp/smart-pointers-modern-cpp.md) ve [nesneler (çii)](../../cpp/object-lifetime-and-resource-management-modern-cpp.md).

- Windows Çalışma Zamanı C++ şablon kitaplığının amacı ve tasarımı, COM nesnelerinin programlamasını basitleştiren bir şablon tabanlı C++ sınıfları kümesi olan etkin şablon kitaplığı (ATL) tarafından ilham olarak belirlenir. Windows Çalışma Zamanı C++ Şablon kitaplığı Windows Çalışma Zamanı kaydırmak için standart C++ kullandığından, daha kolay bağlantı kurabilir ve ATL 'de Windows Çalışma Zamanı yazılan birçok mevcut COM bileşeni ile etkileşim kurabilirsiniz. Zaten ATL 'yi biliyorsanız Windows Çalışma Zamanı C++ Şablon kitaplığı programlamanın daha kolay olduğunu fark edebilirsiniz.

## <a name="getting-started"></a>Başlarken

Windows Çalışma Zamanı C++ Şablon kitaplığı ile hemen çalışmaya başlamanıza yardımcı olabilecek bazı kaynaklar aşağıda verilmiştir.

[Windows Çalışma Zamanı Kitaplığı (WRL)](https://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)<br/>
Bu Channel 9 videosunda Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın Evrensel Windows Platformu (UWP) uygulamaları yazmanıza ve Windows Çalışma Zamanı bileşenleri nasıl yazıp tükettireceğinizi nasıl yardımcı olduğunu öğrenin.

[Nasıl yapılır: Windows Çalışma Zamanı bileşenini etkinleştirme ve kullanma](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)<br/>
Windows Çalışma Zamanı başlatmak ve Windows Çalışma Zamanı bileşenini etkinleştirmek ve kullanmak için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağını gösterir.

[Nasıl yapılır: zaman uyumsuz Işlemleri tamamlar](how-to-complete-asynchronous-operations-using-wrl.md)<br/>
Zaman uyumsuz işlemleri başlatmak ve işlemler tamamlandığında iş gerçekleştirmek için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağını gösterir.

[Nasıl yapılır: olayları Işleme](how-to-handle-events-using-wrl.md)<br/>
Bir Windows Çalışma Zamanı nesnesinin olaylarına abone olmak ve olayları işlemek için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağını gösterir.

[İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma](walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)<br/>
[Microsoft medya altyapısı](/windows/win32/medfound/microsoft-media-foundation-sdk)kullanan bir UWP uygulaması oluşturmayı öğrenin.

[Nasıl yapılır: klasik bir COM bileşeni oluşturma](how-to-create-a-classic-com-component-using-wrl.md)<br/>
Temel bir COM bileşeni oluşturmak için Windows Çalışma Zamanı C++ şablon kitaplığının nasıl kullanılacağını ve COM bileşenini bir masaüstü uygulamasından kaydetmek ve kullanmak için temel bir yol gösterir.

[Nasıl yapılır: doğrudan WRL bileşenleri örneği oluşturma](how-to-instantiate-wrl-components-directly.md)<br/>
[Microsoft:: WRL:: Make](make-function.md) ve [Microsoft:: wrl::D Euçlar:: makeanınvoınitialize](makeandinitialize-function.md) işlevlerini kullanarak onu tanımlayan modülden bir bileşen örneğini oluşturmayı öğrenin.

[Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma](use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)<br/>
. Winmd meta verilerinden bir IDL dosyası oluşturarak WRL 'den özel Windows Çalışma Zamanı bileşenlerini nasıl kullanacağınızı gösterir.

[İzlenecek yol: görevleri ve XML HTTP Isteklerini kullanarak bağlanma](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)<br/>
UWP uygulamasındaki bir Web hizmetine HTTP GET ve POST istekleri göndermek için [IXMLHTTPRequest2](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2) ve [IXMLHTTPRequest2Callback](/windows/win32/api/msxml6/nn-msxml6-ixmlhttprequest2callback) arabirimlerinin görevlerle birlikte nasıl kullanılacağını gösterir.

[Bing Haritalar seyahat Iyileştirici örneği](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples)<br/>
`HttpRequest` [İzlenecek yol: GÖREVLERI ve XML http isteklerini kullanarak](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) bir bütün UWP uygulaması bağlamında tanımlanan sınıfı kullanır.

[C++ örneği ile Windows Çalışma Zamanı DLL bileşeni oluşturma](https://github.com/Microsoft/VCSamples/tree/master/VC2012Samples/Windows%208%20samples/C%2B%2B/Windows%208%20app%20samples)<br/>
İşlem içi DLL bileşeni oluşturmak ve C++/CX, JavaScript ve C# ' den kullanmak için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağını gösterir.

[DirectX mermer Maze oyun örneği](/samples/microsoft/windows-appsample-marble-maze/directx-marble-maze-game-sample/)<br/>
DirectX ve tam 3-b oyun bağlamında Medya Altyapısı COM bileşenlerinin ömrünü yönetmek için Windows Çalışma Zamanı C++ Şablon kitaplığı 'nın nasıl kullanılacağını gösterir.

[Masaüstü uygulamalarından bildirim bildirimleri](/windows/uwp/design/shell/tiles-and-notifications/toast-desktop-apps)<br/>
Bir masaüstü uygulamasından nasıl bildirim gönderileceğini gösterir.

## <a name="windows-runtime-c-template-library-compared-to-atl"></a>ATL ile karşılaştırıldığında C++ Şablon kitaplığı Windows Çalışma Zamanı

Windows Çalışma Zamanı C++ Şablon kitaplığı, küçük ve hızlı COM nesneleri oluşturmak için kullanabileceğiniz etkin şablon kitaplığına (ATL) benzer. Windows Çalışma Zamanı C++ Şablon kitaplığı ve ATL, modüller içindeki nesnelerin tanımı, açık arabirimlerin kaydı ve fabrika kullanarak nesne oluşturma gibi kavramları de paylaşır. ATL hakkında bilginiz varsa Windows Çalışma Zamanı C++ Şablon kitaplığı ile rahat bir şekilde karşılaşabilirsiniz.

Windows Çalışma Zamanı C++ Şablon kitaplığı, UWP uygulamaları için gerekli COM işlevlerini destekler. Bu nedenle, ATL 'den farklıdır çünkü şu şekilde COM özellikleri için doğrudan desteği atlar:

- toplama

- hisse senedi uygulamaları

- Çift arabirimler ( `IDispatch` )

- Standart Numaralandırıcı arabirimleri

- bağlantı noktaları

- yırma arabirimleri

- OLE katıştırma

- ActiveX denetimleri

- COM+

## <a name="concepts"></a>Kavramlar

Windows Çalışma Zamanı C++ Şablon kitaplığı, birkaç temel kavramı temsil eden türler sağlar. Aşağıdaki bölümlerde bu türler açıklanır.

### <a name="comptr"></a>ComPtr

[ComPtr](comptr-class.md) , şablon parametresi tarafından belirtilen arabirimi temsil eden *akıllı bir işaretçi* türüdür. `ComPtr`Arabiriminden türetilmiş bir nesnenin üyelerine erişebilen bir değişken bildirmek için kullanın. `ComPtr` , temel alınan arabirim işaretçisi için bir başvuru sayısını otomatik olarak tutar ve başvuru sayısı sıfıra gittiğinde arabirimi serbest bırakır.

### <a name="runtimeclass"></a>RuntimeClass

[RuntimeClass](runtimeclass-class.md) , belirtilen arabirimlerin kümesini devralan bir örneklenmiş sınıfı temsil eder. Bir `RuntimeClass` nesne, bir veya daha fazla WINDOWS çalışma zamanı com arabirimi veya bir bileşene zayıf bir başvuru için destek bileşimini sağlayabilir.

### <a name="module"></a>Modül

[Modül](module-class.md) bir ilişkili nesneler koleksiyonunu temsil eder. `Module`Nesne, diğer uygulamaların bir nesne kullanmasına olanak sağlayan sınıf fabrikalarını, nesneleri ve kaydı oluşturan bir yönetir.

### <a name="callback"></a>Callback

[Geri çağırma](callback-function-wrl.md) işlevi, üye işlevi bir olay işleyicisi (bir geri çağırma yöntemi) olan bir nesne oluşturur. `Callback`Zaman uyumsuz işlemler yazmak için işlevini kullanın.

### <a name="eventsource"></a>EventSource

[EventSource](eventsource-class.md) , *temsilci* olay işleyicilerini yönetmek için kullanılır. Bir temsilciyi uygulamak ve `EventSource` temsilcileri eklemek, kaldırmak ve çağırmak için kullanmak üzere Windows çalışma zamanı C++ Şablon kitaplığı kullanın.

### <a name="asyncbase"></a>AsyncBase

[AsyncBase](asyncbase-class.md) Windows çalışma zamanı zaman uyumsuz programlama modelini temsil eden sanal yöntemler sağlar. Zaman uyumsuz bir işlemin ilerlemesini Başlatan, durduran veya denetleyen özel bir sınıf oluşturmak için bu sınıftaki üyeleri geçersiz kılın.

### <a name="ftmbase"></a>FtmBase

[FtmBase](ftmbase-class.md) , serbest iş parçacıklı Sıralayıcı nesnesini temsil eder. `FtmBase` genel bir arabirim tablosu (GIT) oluşturur ve sıralama ve proxy nesnelerinin yönetilmesine yardımcı olur.

### <a name="weakref"></a>WeakRef

[WeakRef](weakref-class.md) , erişilebilir olabilecek veya erişilemeyen bir nesneye başvuran *zayıf bir başvuruyu*temsil eden bir akıllı işaretçi türüdür. Bir `WeakRef` nesne, klasık com tarafından değil yalnızca Windows çalışma zamanı tarafından kullanılabilir.

Bir `WeakRef` nesne, genellikle varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil eder. Örneğin, bir `WeakRef` nesnesi bir dosya nesnesine başvurabilir. Dosya açıkken, `WeakRef` geçerli olur ve başvurulan dosya erişilebilir olur. Ancak dosya kapatıldığında, `WeakRef` geçersizdir ve dosyaya erişilemez.

## <a name="related-topics"></a>İlgili Konular

[Kategoriye göre anahtar API 'Leri](key-wrl-apis-by-category.md)\
Birincil Windows Çalışma Zamanı C++ şablon kitaplık türlerini, işlevleri ve makroları vurgular.

[Başvurunun](wrl-reference.md)\
Windows Çalışma Zamanı C++ Şablon kitaplığı için başvuru bilgilerini içerir.

[Hızlı başvuru (C++/CX)](../../cppcx/quick-reference-c-cx.md)\
Windows Çalışma Zamanı destekleyen C++/CX özelliklerini kısaca açıklar.

[Visual C++ Windows Çalışma Zamanı bileşenleri kullanma](/windows/uwp/winrt-components/walkthrough-creating-a-basic-windows-runtime-component-in-cpp-and-calling-it-from-javascript-or-csharp)\
C++/CX 'in temel bir Windows Çalışma Zamanı bileşeni oluşturmak için nasıl kullanılacağını gösterir.
