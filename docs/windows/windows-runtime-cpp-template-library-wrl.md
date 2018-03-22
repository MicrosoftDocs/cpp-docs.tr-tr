---
title: Windows çalışma zamanı C++ Şablon kitaplığı (WRL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d362fdde185f5d9345977ca58d7679a448976555
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="windows-runtime-c-template-library-wrl"></a>Windows Çalışma Zamanı C++ Şablon Kitaplığı (WRL)
Windows çalışma zamanı C++ Şablon kitaplığı (WRL) yazar ve Windows çalışma zamanı bileşenleri kullanmak için alt düzey bir yol sağlayan bir şablon kitaplıktır.

> [!NOTE]
> WRL şimdi kılınan tarafından C + +/ WinRT, bir standart C ++ 17 dil projeksiyon için Windows çalışma zamanı API'leri. C + +/ WinRT, Windows 10 SDK sürüm 1803 ileriye doğru kullanılabilir. C + +/ WinRT tamamen üstbilgi dosyalarında uygulanan ve modern Windows API ile birinci sınıf erişim sağlamak üzere tasarlanmıştır.

> İle C + +/ WinRT, size hem kullanabilir ve Windows çalışma zamanı herhangi standartlarıyla uyumlu C ++ 17 derleyici kullanarak API'leri yazar. C + +/ WinRT genellikle daha iyi gerçekleştirir ve Windows çalışma zamanı için başka bir dil seçeneği değerinden daha küçük ikili dosyaları üretir. C + desteklemek devam +/ CX ve WRL, ancak yüksek oranda yeni uygulamalar C + kullanmanızı öneririz +/ WinRT. Daha fazla bilgi için bkz: [C + +/ WinRT](https://docs.microsoft.com/windows/uwp/cpp-and-winrt-apis/index).   
  
## <a name="benefits"></a>Yararları  
 Windows çalışma zamanı C++ Şablon kitaplığı, daha kolay uygulama ve Bileşen Nesne Modeli (COM) bileşenlerini kullanmasına olanak sağlar. Nesneleri ve test ömrünü yönetmek için başvuru sayımı gibi temizlik teknikleri sağlar `HRESULT` bir işlem başarılı veya başarısız olup olmadığını belirlemek için değerleri. Windows çalışma zamanı C++ Şablon kitaplığı başarıyla kullanmak için dikkatle bu kuralları ve teknikleri izlemelisiniz.  
  
 C + +/ CX Windows çalışma zamanı bileşenleri kullanmak için bir yoldur üst düzey, dil tabanlı. Windows çalışma zamanı C++ Şablon Kitaplığı hem C + +/ CX kod yazma Windows çalışma zamanı için otomatik olarak sizin adınıza temizlik görevleri gerçekleştirerek basitleştirin.  
  
 Windows çalışma zamanı C++ Şablon kitaplığı ve C + +/ CX farklı avantajlar sağlar. Windows çalışma zamanı C++ Şablon kitaplığı C + yerine kullanmak isteyebilirsiniz bazı nedenler şunlardır +/ CX:  
  
-   Windows çalışma zamanı C++ Şablon kitaplığı Windows çalışma zamanı uygulama ikili arabirimi (ABI üzerinden) az soyutlama ekler, veren temeldeki kodu daha iyi denetleme olanağı oluşturabilir veya Windows çalışma zamanı API'larını kullanabilir.  
  
-   C + +/ CX temsil eden COM `HRESULT` özel durumlar olarak değerleri. COM ya da özel durumlar kullanmayan bir kullanan bir kod temeli devralınan, Windows çalışma zamanı C++ Şablon kitaplığı özel durumlar kullanmanız gerekmez çünkü Windows çalışma zamanı ile çalışmak için daha doğal şekilde olduğunu fark edebilirsiniz.  
  
    > [!NOTE]
    >  Windows çalışma zamanı C++ Şablon kitaplığı kullanır `HRESULT` değerleri ve özel durumlar oluşturmadığını. Ayrıca, Windows çalışma zamanı C++ Şablon kitaplığı akıllı işaretçiler ve RAII düzeni, uygulama kodunuzun bir özel durum oluşturduğunda nesneleri doğru yok olur sağlanmasına yardımcı olmak için kullanır. Akıllı işaretçiler ve RAII hakkında daha fazla bilgi için bkz: [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md) ve [nesneleri kendi kaynakları (RAII)](../cpp/objects-own-resources-raii.md).  
  
-   Amacı ve Windows çalışma zamanı C++ Şablon kitaplığı tasarımını neden olacak Etkin Şablon kitaplığı (ATL tarafından), hangi COM nesneleri programlama basitleştirmek şablona dayalı C++ sınıflar kümesidir. Windows çalışma zamanı C++ Şablon kitaplığı Windows çalışma zamanı sarmalamak için standart C++ kullandığından, daha kolay bağlantı noktası ve ATL içinde Windows çalışma zamanı için yazılan birçok mevcut COM bileşenleri ile etkileşim. ATL zaten biliyorsanız, Windows çalışma zamanı C++ Şablon kitaplığı programlama daha kolay olduğunu görebilirsiniz.  
  
## <a name="getting-started"></a>Başlarken  
 Windows çalışma zamanı C++ Şablon Kitaplığı'yla hemen çalışmaya alma yardımcı olacak bazı kaynaklar aşağıda verilmiştir.  
  
 [Windows çalışma zamanı kitaplığı (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 Bu kanal 9 videoda, Windows çalışma zamanı C++ Şablon Kitaplığı nasıl yardımcı olduğu hakkında Evrensel Windows Platformu (UWP) uygulamaları ve nasıl yazılacağını ve Windows çalışma zamanı bileşenlerini kullanacak yazma edinin.  
  
 [Nasıl yapılır: Windows çalışma zamanı bileşenini etkinleştirme ve kullanma](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Windows çalışma zamanı C++ Şablon kitaplığı Windows çalışma zamanı başlatmak ve etkinleştirmek ve bir Windows çalışma zamanı bileşeni kullanmak için nasıl kullanılacağını gösterir.  
  
 [Nasıl yapılır: zaman uyumsuz işlemleri tamamlama](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Windows çalışma zamanı C++ Şablon kitaplığı zaman uyumsuz işlemleri başlatmak ve işlemlerini tamamladıktan sonra iş gerçekleştirmek için nasıl kullanılacağını gösterir.  
  
 [Nasıl yapılır: olayları işleme](../windows/how-to-handle-events-using-wrl.md)  
 Windows çalışma zamanı C++ Şablon kitaplığı abone olma ve Windows çalışma zamanı nesne olayları işlemek için nasıl kullanılacağını gösterir.  
  
 [İzlenecek yol: WRL ve Medya Altyapısı kullanarak UWP uygulaması oluşturma](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 Kullanan bir UWP uygulaması oluşturmayı öğrenin [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 [Nasıl yapılır: klasik COM bileşeni oluşturma](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Windows çalışma zamanı C++ Şablon kitaplığı temel bir COM bileşeni ve kaydetme ve COM bileşeninin düzgün bir masaüstü uygulaması'ndan kullanmak için temel bir şekilde oluşturmak için nasıl kullanılacağını gösterir.  
  
 [Nasıl yapılır: Doğrudan WRL Bileşenlerinin Örneğini Oluşturma](../windows/how-to-instantiate-wrl-components-directly.md)  
 Nasıl kullanacağınızı öğrenin [Microsoft::WRL::Make](../windows/make-function.md) ve [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) tanımlayan modülden bir bileşen örneği oluşturmak için işlevleri.  
  
 [Nasıl yapılır: Windows meta verilerinden .h dosyaları oluşturmak için winmdidl.exe ve midlrt.exe programını kullanma](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 WRL özel Windows çalışma zamanı bileşenlerini .winmd meta verilerini bir IDL dosya oluşturarak kullanma gösterir.  
  
 [İzlenecek Yol: Görevleri ve XML HTTP İsteklerini Kullanarak Bağlanma](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Nasıl kullanılacağını gösterir [Ixmlhttprequest2](http://msdn.microsoft.com/en-us/bbc11c4a-aecf-4d6d-8275-3e852e309908) ve [Ixmlhttprequest2callback](http://msdn.microsoft.com/en-us/aa4b3f4c-6e28-458b-be25-6cce8865fc71) bir UWP uygulamasında bir web hizmeti için HTTP GET ve POST istekleri göndermek için görevler birlikte arabirimleri.  
  
 [Bing Haritalar seyahat iyileştirici örneği](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 Kullanan `HttpRequest` tanımlanan sınıfı [izlenecek yol: bağlanma kullanarak görevleri ve XML HTTP isteklerini](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) tam bir UWP uygulaması bağlamında.  
  
 [C++ örneği ile Windows çalışma zamanı DLL bileşeni oluşturma](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 Windows çalışma zamanı C++ Şablon kitaplığı bir işlemdeki DLL bileşen oluşturun ve onu C + seçeneğini kullanmak için nasıl kullanılacağını gösterir +/ CX, JavaScript ve C#.  
  
 [DirectX Mermer Labirent oyun örnek](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 Windows çalışma zamanı C++ Şablon kitaplığı tam 3-b oyun bağlamında DirectX ve Media Foundation gibi COM bileşenlerini ömrünü yönetmek için nasıl kullanılacağını gösterir.  
  
 [Masaüstü uygulamaları örnek alarak bildirimleri gönderme](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 Windows çalışma zamanı C++ Şablon kitaplığı Masaüstü uygulamasından bildirimleri göreceklerdir çalışmak için nasıl kullanılacağını gösterir.  
  
## <a name="windows-runtime-c-template-library-compared-to-atl"></a>ATL için karşılaştırıldığında Windows çalışma zamanı C++ Şablon Kitaplığı  
 Küçük, hızlı COM nesneleri oluşturmak için kullandığı için Windows çalışma zamanı C++ Şablon kitaplığı Etkin Şablon kitaplığı (ATL) benzer. Windows çalışma zamanı C++ Şablon kitaplığı ve ATL ayrıca modüllerdeki arabirimleri, açık kayıt nesnelerle tanımını gibi kavramları paylaşma ve nesneleri oluşturucuları kullanarak açın. ATL ile bilginiz varsa, Windows çalışma zamanı C++ Şablon kitaplığı ile rahat olabilir  
  
 Windows çalışma zamanı C++ Şablon kitaplığı UWP uygulamaları için gerekli olan COM işlevleri destekler. Bu nedenle, COM özellikleri doğrudan desteği gibi atladığından ATL farklılık gösterir:  
  
-   Toplama  
  
-   Stok uygulamaları  
  
-   çift arabirimler (`IDispatch`)  
  
-   Standart Numaralandırıcı arabirimleri  
  
-   bağlantı noktaları  
  
-   etiketleri arabirimleri  
  
-   OLE katıştırma  
  
-   ActiveX denetimleri  
  
-   COM+  
  
## <a name="concepts"></a>Kavramlar  
 Windows çalışma zamanı C++ Şablon kitaplığı birkaç temel kavramları temsil eden türler sağlar. Aşağıdaki bölümlerde bu türleri açıklanmaktadır.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) olan bir *akıllı işaretçi* şablon parametresi tarafından belirtilen arabirimi temsil eden tür. Kullanım `ComPtr` arabirimden türetilmiş bir nesnenin üyelerine erişmek için bir değişken bildirmek için. `ComPtr` otomatik olarak bir başvuru sayısı için temel arabirim işaretçisi tutar ve başvuru sayısı sıfır olarak gittiğinde arabirimi serbest bırakır.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) bir dizi belirtilen arabirimden devralan başlatılan bir sınıfı temsil eder. A `RuntimeClass` nesnesi bir veya daha fazla Windows çalışma zamanı COM arabirimleri veya bir bileşen zayıf başvurusu için destek bileşimini sağlayabilir.  
  
### <a name="module"></a>Modül  
 [Modül](../windows/module-class.md) ilgili nesneler koleksiyonunu temsil eder. A `Module` nesnesi nesneleri ve diğer uygulamaların bir nesne kullanmasını sağlar kayıt oluşturma sınıf oluşturucuları yönetir.  
  
### <a name="callback"></a>Geri çağırma  
 [Geri çağırma](../windows/callback-function-windows-runtime-cpp-template-library.md) işlevi olan üye işlevi bir olay işleyicisi (bir geri çağırma yöntemi) olan bir nesne oluşturur. Kullanım `Callback` yazma zaman uyumsuz işlemleri için işlev.  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md) yönetmek için kullanılan *temsilci* olay işleyicileri. Bir temsilci uygulamak ve kullanmak için Windows çalışma zamanı C++ Şablon kitaplığı kullanmak `EventSource` eklemek, kaldırmak ve temsilciler çağırma.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) Windows çalışma zamanı zaman uyumsuz programlama modeli temsil eden sanal yöntemler sağlar. Başlatma, durdurma veya zaman uyumsuz bir işlemin ilerleme durumunu denetlemek özel bir sınıf oluşturmak için üyeler bu sınıftaki geçersiz kılar.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) ücretsiz iş parçacıklı Sıralayıcı nesneyi temsil eder. `FtmBase` Genel arabirim tablosu (GIT) oluşturur ve sıralama ve proxy nesneleri yönetilmesine yardımcı olur.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) temsil eden bir akıllı işaretçi türü bir *zayıf başvuru*, olabilir ya da erişilebilir olmayabilir bir nesne başvuruyor. A `WeakRef` nesnesi, yalnızca Windows çalışma zamanı tarafından ve klasik COM tarafından kullanılabilir  
  
 A `WeakRef` nesnesi genellikle, varlığı bir dış iş parçacığı veya uygulama tarafından denetlenen bir nesneyi temsil eder. Örneğin, bir `WeakRef` nesnesi bir dosya nesnesine başvuru. Dosya açıkken `WeakRef` geçerlidir ve başvurulan dosyasının erişilebilir olduğunu. Ancak dosyayı kapattığınızda `WeakRef` geçersiz olduğunu ve dosyaya erişilemiyor.  
  
## <a name="related-topics"></a>İlgili Konular  
  
|||  
|-|-|  
|[Kategoriye göre başlıca API'ler](../windows/key-wrl-apis-by-category.md)|Birincil Windows çalışma zamanı C++ Şablon kitaplığı türleri, İşlevler ve makrolar vurgular.|  
|[Başvuru](../windows/wrl-reference.md)|Windows çalışma zamanı C++ Şablon kitaplığı için başvuru bilgileri içerir.|  
|[Hızlı Başvuru (Windows çalışma zamanı ve Visual C++)](http://go.microsoft.com/fwlink/p/?linkid=229180)|Kısaca açıklanmaktadır C + +/ Windows çalışma zamanı desteği CX özellikleri.|  
|[Visual C++'da Windows çalışma zamanı bileşenleri kullanma](http://go.microsoft.com/fwlink/p/?linkid=229155)|C + kullanmayı gösterir +/ CX temel Windows çalışma zamanı bileşeni oluşturma.|