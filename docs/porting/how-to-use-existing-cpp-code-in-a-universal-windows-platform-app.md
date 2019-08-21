---
title: 'Nasıl yapılır: Evrensel Windows Platformu uygulamasında C++ mevcut kodu kullanma'
ms.date: 04/08/2019
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 5050a9773eea55549958195efa624743f44ed031
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630433"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Nasıl yapılır: Evrensel Windows Platformu uygulamasında C++ mevcut kodu kullanma

Masaüstü programınızı Evrensel Windows Platformu (UWP) ortamında çalışan bir şekilde almanın en kolay yolu masaüstü Köprüsü teknolojilerini kullanmaktır. Bunlar, mevcut uygulamanızı kod değişikliği gerekmeden UWP uygulaması olarak paketlenecek masaüstü uygulaması dönüştürücüsünü içerir. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

Bu konunun geri kalanında, bağlantı noktası C++ kitaplıklarının (dll 'leri ve statik kitaplıklar) Evrensel Windows platformu nasıl yapılacağı açıklanmaktadır. Çekirdek C++ mantığınızın bırden çok UWP uygulamalarıyla kullanılabilmesi için bunu yapmak isteyebilirsiniz.

UWP uygulamaları korumalı bir ortamda çalışır ve sonuç olarak, platformun güvenliğine zarar verebilecek çok sayıda Win32, COM ve CRT API çağrısı yapılmasına izin verilmez. Derleyici bu tür çağrıları algılayabilir ve `/ZW` seçenek kullanılırsa bir hata oluşturur. Yasak API 'Leri çağıran kodu algılamak için uygulamanızdaki uygulama sertifikasyon kitini kullanabilirsiniz. Daha fazla bilgi için bkz. [Windows uygulama Sertifikalama seti](/windows/uwp/debug-test-perf/windows-app-certification-kit).

Kitaplık için kaynak kodu kullanılabiliyorsa yasak API çağrılarını ortadan kaldırabiliyor olabilirsiniz. İzin verilen veya yasak API 'lerin listesini içeren ayrıntılar için bkz. [UWP uygulamaları Için Win32 ve com API 'leri](/uwp/win32-and-com/win32-and-com-for-uwp-apps) ve [Evrensel Windows platformu uygulamalarda desteklenmeyen crt işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md). [UWP uygulamalarında Windows API 'Lerinin alternatifleri bölümünde](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)bazı alternatifler bulabilirsiniz.

Bir Evrensel Windows projesinden klasik masaüstü kitaplığına bir başvuru eklemeye çalışırsanız, kitaplığın uyumlu olmadığını belirten bir hata iletisi alırsınız. Statik bir kitaplık söz konusu olduğunda, kitaplığı (. lib dosyası) yalnızca klasik bir Win32 uygulamasında olduğu gibi bağlayıcı girdisine ekleyerek kitaplığınıza bağlayabilirsiniz. Yalnızca bir ikilinin kullanılabildiği kitaplıklar için bu tek seçenektir. Statik bir kitaplık, uygulamanızın yürütülebilir dosyasına bağlanır, ancak UWP uygulamasında kullandığınız bir Win32 DLL, projeye eklenerek ve Içerik olarak işaretlenerek uygulamaya paketlenmesi gerekir. Bir UWP uygulamasında Win32 DLL yüklemek için, `LoadLibrary` ya `LoadLibraryEx`da yerine [loadpackagedlibrary](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary) çağrısı yapmanız gerekir.

DLL veya statik kitaplık için kaynak kodunuz varsa, UWP projesi olarak ile `/ZW` yeniden derleyebilirsiniz. Bunu yaparsanız, **Çözüm Gezgini**kullanarak bir başvuru ekleyebilir ve bunu C++ UWP uygulamalarında kullanabilirsiniz. DLL söz konusu olduğunda, dışa aktarma kitaplığıyla bağlantı oluşturursunuz.

Diğer dillerdeki arayanlara işlevselliği göstermek için, kitaplığı bir Windows Çalışma Zamanı bileşenine dönüştürebilirsiniz. Windows Çalışma Zamanı bileşenler, verileri .NET ve JavaScript tüketicilerinin gerektirdiği bir şekilde açıklayan. winmd dosyaları biçiminde meta verileri dahil ettikleri sıradan dll 'lerden farklıdır. API öğelerini diğer dillere göstermek için, başvuru sınıfları gibi/CX C++yapıları ekleyebilir ve bunları ortak hale getirebilir ya da [Windows çalışma zamanı C++ şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanabilirsiniz.  Windows 10 ve üzeri sürümlerde, [ C++/wınrt kütüphanesini](https://github.com/microsoft/cppwinrt) C++/cxyerine kullanabilirsiniz.

Önceki tartışma, farklı şekilde işlenmesi gereken COM bileşenleri için de geçerlidir. Bir EXE veya DLL 'de bir COM sunucunuz varsa, bunu bir Evrensel Windows projesinde, [kayıtsız BIR com bileşeni](/windows/win32/sbscs/creating-registration-free-com-objects)olarak paketleyip bunu projenize bir içerik dosyası olarak ekleyerek ve [CoCreateInstanceFromApp](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp)kullanarak örnekleyebilirsiniz. Daha fazla bilgi için bkz. [Windows Mağazası C++ PROJESINDE ücretsiz com dll kullanma](https://blogs.msdn.microsoft.com/win8devsupport/2013/05/19/using-free-com-dll-in-windows-store-c-project/).

UWP 'e bağlantı noktası eklemek istediğiniz mevcut bir COM kitaplığınız varsa, bunu [Windows çalışma zamanı C++ şablon kitaplığı (wrl)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanarak Windows çalışma zamanı bir bileşene dönüştürebilirsiniz. WRL, ATL ve OLE 'nin tüm özelliklerini desteklemez. bu nedenle, bu tür bir bağlantı noktasının uygun olup olmadığı, COM kodunuzun ne kadar com, ATL ve OLE 'nin gerekli özelliklerine bağlı olduğuna bağlıdır.

Bunlar, UWP projelerinde mevcut C++ kodu kullanmanın çeşitli yollarıdır. Bazı yollarla kod, bileşen uzantıları (C++/CX) etkin (yani, `/ZW` seçeneğiyle) ve bazıları C++için de klasik bir Win32 derleme ortamı için yeniden derlenmesi gerekmez. kod, uygun mimari seçenekleriyle bunu yapabilirsiniz. Örneğin, UWP Kullanıcı arabirimini ve C#, Visual Basic ve JavaScript çağıranlarını gösteren türleri içeren tüm kodunuz Windows uygulama projelerinde ve Windows çalışma zamanı bileşen projelerinde olmalıdır. Yalnızca içinde C++ tüketilmesi gereken kod (/CX dahil C++) kodu, `/WX` seçeneği veya standart C++ bir proje ile derlenen bir projede olabilir. Yalnızca ikili kod, bir statik kitaplık olarak bağlantı kurarak veya uygulamayla birlikte paketlenmiş ve yalnızca yasak API 'Leri kullanmıyorsa bir DLL 'ye yüklenmiş olarak kullanılabilir.

Seçtiğiniz geliştirme senaryolarından bağımsız olarak, kodunuzu hem klasik masaüstü hem de UWP kapsamında derlemek için kodunuzda kullanabileceğiniz bazı makro tanımlarından haberdar olmanız gerekir.

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

Bu deyimler sırasıyla UWP uygulamalarına, Windows Phone mağaza uygulamalarına, her ikisine de veya hiçbirine (yalnızca Klasik Win32 Masaüstü) uygulanır. Bu makrolar yalnızca Windows SDK 8,1 ve üzeri sürümlerde kullanılabilir. bu nedenle, kodunuzun önceki Windows SDK veya Windows 'un diğer platformları ile derlenmesi gerekiyorsa, bunların hiçbirinin tanımlanmaması durumunda da göz önünde bulundurmanız gerekir.

Bu konu aşağıdaki yordamları içerir:

- [UWP uygulamasında Win32 DLL kullanma](#BK_Win32DLL)

- [UWP uygulamasında yerel C++ bir statik kitaplık kullanma](#BK_StaticLib)

- [C++ Kitaplığı bir Windows çalışma zamanı bileşenine taşıma](#BK_WinRTComponent)

##  <a name="BK_Win32DLL"></a>UWP uygulamasında Win32 DLL kullanma

Daha iyi güvenlik ve güvenilirlik için, Evrensel Windows uygulamaları kısıtlı bir çalışma zamanı ortamında çalışır, bu nedenle yalnızca klasik bir Windows masaüstü uygulamasında yaptığınız şekilde herhangi bir yerel DLL kullanamazsınız. Bir DLL için kaynak kodunuz varsa, UWP üzerinde çalışacak şekilde kodu bağlantı noktası oluşturabilirsiniz. Projeyi UWP projesi olarak tanımlamak için birkaç proje ayarını ve proje dosyası meta verilerini değiştirerek başlayın. ,/Cx' i sağlayan `/ZW` C++seçeneğini kullanarak kitaplık kodunu derlemeniz gerekir. Bu ortamla ilişkili daha sıkı denetimler nedeniyle UWP uygulamalarında belirli API çağrılarına izin verilmez. [UWP uygulamaları için bkz. Win32 ve com API 'leri](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

Aşağıdaki yordam, kullanarak `__declspec(dllexport)`işlevleri kullanıma sunan bir yerel dll 'nin bulunduğu durumlar için geçerlidir.

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>Yeni bir proje oluşturmadan UWP 'e yerel DLL 'ye bağlantı noktası oluşturma

1. Kullanarak `__declspec(dllexport)`işlevleri dışarı aktaran bir yerel DLL varsa, bir UWP projesi olarak DLL 'yi yeniden derleyerek bu işlevleri UWP uygulamasından çağırabilirsiniz. Örneğin, aşağıdaki üstbilgi dosyası gibi bir kod ile birkaç sınıfı ve yöntemlerini veren bir DLL olduğunu varsayalım:

    ```cpp
    // giraffe.h
    #pragma once

    #ifdef _DLL
    #define GIRAFFE_API __declspec(dllexport)
    #else
    #define GIRAFFE_API
    #endif

    GIRAFFE_API int giraffeFunction();

    class Giraffe
    {
        int id;
            Giraffe(int id_in);
        friend class GiraffeFactory;

    public:
        GIRAFFE_API int GetID();
    };

    class GiraffeFactory
    {
        static int nextID;

    public:
        GIRAFFE_API GiraffeFactory();
        GIRAFFE_API static int GetNextID();
        GIRAFFE_API static Giraffe* Create();
    };
    ```

   Ve aşağıdaki kod dosyası:

    ```cpp
    // giraffe.cpp
    #include "stdafx.h"
    #include "giraffe.h"

    Giraffe::Giraffe(int id_in) : id(id_in)
    {
    }

    int Giraffe::GetID()
    {
      return id;
    }

    int GiraffeFactory::nextID = 0;

    GiraffeFactory::GiraffeFactory()
    {
        nextID = 0;
    }

    int GiraffeFactory::GetNextID()
    {
        return nextID;
    }

    Giraffe* GiraffeFactory::Create()
    {
        return new Giraffe(nextID++);
    }

    int giraffeFunction();
    ```

   Projedeki diğer her şey (stbafx. h, DllMain. cpp), standart Win32 Proje şablonunun bir parçasıdır. Birlikte izlemek isterseniz, ancak bu adımlarla kendi DLL 'nizi kullanmak istemiyorsanız, bir Win32 projesi oluşturmayı deneyin, proje sihirbazında DLL ' yi seçin ve ardından Giraffe. h ve kod dosyası Giraffe. cpp adlı bir üstbilgi dosyası ekleyin ve içeriği bu adımdaki koddan uygulamaya kopyalayın dosyaları boşaltın.

   Kod, tanımlandığında `GIRAFFE_API` `__declspec(dllexport)` olarak çözümlenen makroyu tanımlar (yani, proje DLL olarak yapılandırıldığında). `_DLL`

2. DLL projesi için **Proje özelliklerini** açın ve **yapılandırmayı** **tüm yapılandırmalar**olarak ayarlayın.

3. **Proje özellikleri**' nde, >  **C/C++** **genel** sekmesinde, kullan **Windows çalışma zamanı uzantısını** **Evet (/ZW)** olarak ayarlayın. Bu, bileşen uzantıları 'nıC++(/CX) sunar.

4. **Çözüm Gezgini**, proje düğümünü seçin, kısayol menüsünü açın ve **Projeyi Kaldır**' ı seçin. Ardından, yüklenmeyen proje düğümünde kısayol menüsünü açın ve proje dosyasını düzenlemeyi seçin. `WindowsTargetPlatformVersion` Öğesini bulun ve aşağıdaki öğelerle değiştirin.

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   . Vcxproj dosyasını kapatın, kısayol menüsünü yeniden açın ve **projeyi yeniden yükle**' yi seçin.

   **Çözüm Gezgini** artık projeyi bir Evrensel Windows projesi olarak tanımlıyor.

5. Önceden derlenmiş üst bilgi dosyası adınızın doğru olduğundan emin olun. **Ön derlenmiş üstbilgiler** bölümünde, **ön derlenmiş üstbilgi dosyasını** *pch. h* iken *stbafx. h*olarak değiştirin. Bunu yapmazsanız, aşağıdaki hatayı görürsünüz.

   > hata C2857:/Ycpch.h komut satırı seçeneğiyle belirtilen ' #include ' ifadesiyle kaynak dosyada bulunamadı

   Bu sorun, Evrensel Windows projelerinin ön derlenmiş üstbilgi dosyası için farklı bir adlandırma kuralı kullanmasına neden olur.

6. Projeyi oluşturun. Uyumsuz komut satırı seçenekleri hakkında bazı hatalar alabilirsiniz. Örneğin, artık kullanım dışı bırakılmış ancak sık kullanılan seçenek **en az sayıda yeniden derlemeyi etkinleştir (/GI)** , daha eski C++ projelerde varsayılan olarak ayarlanır ve ile `/ZW`uyumsuzdur.

   Evrensel Windows Platformu için derlerken bazı işlevler kullanılamaz. Herhangi bir sorun hakkında derleyici hataları görürsünüz. Temiz bir derleme yapana kadar bu bunları ele edin.

7. DLL 'yi aynı çözümde bir UWP uygulamasında kullanmak için, UWP proje düğümünün kısayol menüsünü açın ve**başvuru** **Ekle** > ' yi seçin.

   **Projeler** > **çözümü**altında dll projesinin yanındaki onay kutusunu işaretleyin ve **Tamam** düğmesini seçin.

8. Kitaplığın üst bilgi dosyalarını UWP uygulamanızın *pch. h* dosyasına ekleyin.

    ```cpp
    #include "..\MyNativeDLL\giraffe.h"
    ```

9. İşlevleri çağırmak ve DLL 'den türler oluşturmak için UWP projesinde her zamanki gibi kod ekleyin.

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

##  <a name="BK_StaticLib"></a>UWP uygulamasında yerel C++ bir statik kitaplık kullanma

UWP projesinde yerel C++ bir statik kitaplık kullanabilirsiniz, ancak farkında olacak bazı kısıtlamalar ve sınırlamalar vardır. [/CX içindeki C++statik kitaplıklar](../cppcx/static-libraries-c-cx.md)hakkında okumaya başlayın. UWP uygulamanızdan statik kitaplığınızdaki yerel koda erişebilirsiniz, ancak bu tür bir statik kitaplıkta ortak başvuru türleri oluşturulması önerilmez. `/ZW` Seçeneğiyle bir statik kitaplık derlerseniz, kütüphaneian (aslında gizleyen bağlayıcı) sizi uyarır:

> LNK4264:/ZW ile derlenen nesne dosyasını statik bir kitaplığa arşivleme; Windows Çalışma Zamanı türler yazarken Windows Çalışma Zamanı meta verileri içeren bir statik kitaplıkla bağlantı önerildiğine unutmayın

Ancak, bir UWP içindeki statik bir kitaplığı, ile `/ZW`yeniden derlemeden kullanabilirsiniz. Herhangi bir başvuru türü bildiremezsiniz veya/CX yapılarını kullanamazsınız C++, ancak amacınıza yalnızca yerel kod kitaplığı kullanmak istiyorsanız, bu adımları takip edebilirsiniz.

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP projesinde yerel C++ bir statik kitaplık kullanmak için

1. UWP projesinin proje özellikleri ' nde, sol bölmedeki **yapılandırma özellikleri** > **bağlayıcı** > **girişi** ' ni seçin. Sağ bölmede, **ek bağımlılıklar** özelliğindeki kitaplığa yolu ekleyin. Örneğin, projedeki çıktısını *SolutionFolder*\Debug\mynativelibrary\mynativelibrary.exe dizinine yerleştiren bir kitaplık için göreli yolu `Debug\MyNativeLibrary\MyNativeLibrary.lib`ekleyin.

2. Üstbilgi dosyasını *pch. h* dosyanıza (varsa) veya gerektiği gibi herhangi bir. cpp dosyasına başvuracak bir Include ifadesini ekleyin ve kitaplığı kullanan kodu eklemeye başlayın.

   ```cpp
   #include "..\MyNativeLibrary\giraffe.h"
   ```

   **Çözüm Gezgini** **Başvurular** düğümüne başvuru eklemeyin. Bu mekanizma yalnızca Windows Çalışma Zamanı bileşenleri için geçerlidir.

##  <a name="BK_WinRTComponent"></a>C++ Kitaplığı bir Windows çalışma zamanı bileşenine taşıma

Yerel API 'Leri UWP uygulamasından bir statik kitaplıkta kullanmak istiyorsanız ve yerel kitaplık için kaynak koduna sahipseniz, kodun Windows Çalışma Zamanı bir bileşende bağlantı noktası oluşturabilirsiniz. Artık bir statik kitaplık olmayacak, bu bir DLL olacaktır. Bunu herhangi bir C++ UWP uygulamasında kullanabilirsiniz, ancak statik kitaplık çalışmasının aksine, dilden bağımsız olarak HERHANGI bir UWP uygulama kodundaki istemciler için kullanılabilir C++olan başvuru türlerini ve diğer/CX yapılarını ekleyebilirsiniz. Bu nedenle, bu türlere, Visual Basic veya C#JavaScript 'ten erişebilirsiniz.  Temel yordam, bir Windows çalışma zamanı bileşen projesi oluşturmaktır, statik kitaplığınızın kodunu buna kopyalamak ve kodu standart C++ bir derlemeden `/ZW` derlemeye taşımadan kaynaklanan tüm hataları ele maktır.

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>Bir Windows Çalışma Zamanı bileşeni C++ için kitaplık bağlantı noktası oluşturma

1. Windows Çalışma Zamanı bileşen projesi oluşturun.

2. Projeyi kapatın.

3. **Windows Dosya Gezgini**'nde projeyi bulun. Varsayılan olarak, Visual Studio belgeler klasörünüzdeki Visual Studio 2017 \ Projects klasörünü kullanır. Bağlantı noktası C++ yapmak istediğiniz kodu içeren kitaplık projesini bulun. C++ Kitaplık projenizden kaynak dosyalarını (üst bilgi dosyalarını, kod dosyalarını ve alt dizinler dahil diğer tüm kaynakları) kopyalayın ve proje klasörüne yapıştırarak aynı klasör yapısını koruduğunuzdan emin olun.

4. Windows çalışma zamanı bileşen projesini yeniden açın ve **Çözüm Gezgini**içindeki proje düğümünün kısayol menüsünü açın ve**var olan öğeyi** **Ekle** > ' yi seçin.

5. Özgün projenizden eklenecek tüm dosyaları seçin ve **Tamam**' ı seçin. Alt klasörler için gerekliyse tekrarlayın.

6. Artık yinelenen bir kodunuz olabilir. Birden fazla önceden derlenmiş üst bilgi ( *stbafx. h* ve *pch. h*) varsa, saklanacak bir tane seçin. Include deyimlerini gibi gerekli kodu, koruduğunuz birine kopyalayın. Ardından, diğerini silin ve proje özelliklerinde, **önceden derlenmiş üstbilgiler**altında, üstbilgi dosyasının adının doğru olduğundan emin olun.

   Önceden derlenmiş üst bilgi olarak kullanılacak dosyayı değiştirdiyseniz, ön derlenmiş üstbilgi seçeneklerinin her dosya için doğru olduğundan emin olun. Sırasıyla her bir. cpp dosyasını seçin, Özellikler penceresini açın ve istenen önceden derlenmiş üst bilgi dışında (/i) **oluşturulacak**şekilde ayarlananların tümünün **(/Yu)** olarak ayarlandığından emin olun.

7. Projeyi derleyin ve hataları çözün. Bu hatalar, `/ZW` seçeneği kullanılarak veya Windows SDK yeni bir sürümlerinden kaynaklanmış olabilir ya da kitaplığınızın bağlı olduğu üstbilgi dosyaları ya da eskileri arasındaki proje ayarlarındaki farklılıklar gibi bağımlılıkları yansıtabilir. Proje ve yeni bir tane.

8. Projenize ortak başvuru türleri ekleyin veya giriş noktalarını UWP uygulamalarından çağırmak istediğiniz işlevselliğe göstermek için normal türleri ref türlerine dönüştürün.

9. Bir UWP uygulama projesinden buna bir başvuru ekleyerek bileşeni test edin ve oluşturduğunuz ortak API 'Leri çağırmak için kod ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Evrensel Windows Platformu taşıma](../porting/porting-to-the-universal-windows-platform-cpp.md)
