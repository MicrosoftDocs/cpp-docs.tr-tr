---
title: 'Nasıl yapılır: Mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma'
ms.date: 04/08/2019
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 3aeef205effe072a25fc0b3dabb9145245461d45
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424202"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Nasıl yapılır: Mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma

Belki de en kolay yolu Evrensel Windows Platformu (UWP) ortamında çalışan masaüstü programınızın Masaüstü köprüsü teknolojileri kullanmaktır. Mevcut uygulamanızı olmadan bir UWP uygulaması olarak paketleme masaüstü uygulaması dönüştürücü bunlar kod değişikliği gerekir. Daha fazla bilgi için [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

Bu konunun geri kalanında, bağlantı noktasına anlatılmaktadır C++ Evrensel Windows platformu için kitaplıkları (DLL'ler ve statik kitaplıklar). C++ mantıksal çekirdek ile birden çok UWP uygulamaları kullanılabilir, böylece bunu yapmak isteyebilirsiniz.

Korumalı bir ortamda UWP uygulamaları çalıştırma ve sonuç olarak, platform güvenliğinin tehlikeye atabilir birçok Win32 ve COM CRT API çağrıları izin verilmemektedir. Derleyici böyle çağrılar algılayabilir ve bir hata oluşturur `/ZW` seçeneği kullanılır. Yasaklanmış API çağıran kod algılamak için uygulama uygulama onay Seti kullanabilirsiniz. Daha fazla bilgi için [Windows uygulama Sertifikalama Seti](/windows/uwp/debug-test-perf/windows-app-certification-kit).

Kitaplık için kaynak kodu varsa, yasaklanmış API çağrıları ortadan kaldırmak mümkün olabilir. İzin verilen veya Yasak API'lerin bir listesi dahil olmak üzere ayrıntılı bilgi için bkz. [Win32 ve COM API UWP uygulamaları için](/uwp/win32-and-com/win32-and-com-for-uwp-apps) ve [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md). Bazı alternatifleri şu yolda bulunabilir: [UWP uygulamalarında Windows API'lere alternatifler](/uwp/win32-and-com/alternatives-to-windows-apis-uwp).

Yalnızca bir evrensel Windows projesi Klasik Masaüstü kitaplığına bir başvuru eklemek çalışırsanız, kitaplığın uyumlu olmayan bildiren bir hata iletisi alırsınız. Statik kitaplık söz konusu olduğunda, bir Klasik Win32 uygulamasında yaptığınız gibi kitaplık (.lib dosyası) yalnızca bağlayıcı girişinizi ekleyerek kitaplığınıza bağlayabilirsiniz. Yalnızca bir ikili kullanılabilir olduğu kitaplıkları için tek seçenek budur. Statik kitaplık, uygulamanızın yürütülebilir dosyanın içine bağlandı, ancak bir UWP uygulamasında tükettiğiniz bir Win32 DLL içeriği olarak işaretleme ve projeye dahil olmak üzere uygulamaya paketlenmesi gerekir. Bir UWP uygulamasında bir Win32 DLL yüklenecek çağırmak ' iniz de [LoadPackagedLibrary](/windows/desktop/api/winbase/nf-winbase-loadpackagedlibrary) yerine `LoadLibrary` veya `LoadLibraryEx`.

DLL veya statik kitaplığı için kaynak kodu varsa, ile derleyebilirsiniz `/ZW` bir UWP projesi olarak. Bunu yaparsanız, kullanarak bir başvuru ekleyebilirsiniz **Çözüm Gezgini**ve C++ UWP uygulamalarında kullanın. Bir DLL söz konusu olduğunda dışarı aktarma kitaplığı ile bağlayın.

Diğer dillerdeki arayanlara işlevselliği göstermek için kitaplık bir Windows çalışma zamanı bileşeni dönüştürebilirsiniz. Windows çalışma zamanı bileşenleri tanımlayan içeriği, .NET ve JavaScript tüketiciler gerektiren bir yolla .winmd dosyaları biçiminde meta verileri içermesi durumunda Normal DLL'leri farklıdır. Diğer diller için API öğeleri kullanıma sunmak için C + ekleyebileceğiniz +/ CX, başvuru sınıfları gibi oluşturur ve genel hale getirmek ya da kullanmak [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  Windows 10 ve sonraki sürümlerinde, kullanabileceğiniz [ C++/WinRT Kitaplığı](https://github.com/microsoft/cppwinrt) yerine C++/CX.

Yukarıdaki açıklama farklı işlenmesi gereken COM bileşenlerinin durumu için geçerli değildir. Bir EXE veya DLL bir COM sunucusu varsa, olarak paketini sürece, bir evrensel Windows projesi içinde kullanabileceğiniz bir [kayıt gerektirmeyen COM bileşeni](/windows/desktop/sbscs/creating-registration-free-com-objects), projenize bir içerik dosyası olarak ekleyin ve örneği kullanarak [ CoCreateInstanceFromApp](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstancefromapp). Daha fazla bilgi için [kullanarak ücretsiz COM DLL Windows Store C++ projesinde](https://blogs.msdn.microsoft.com/win8devsupport/2013/05/19/using-free-com-dll-in-windows-store-c-project/).

UWP taşımak istediğiniz mevcut bir COM kitaplığı varsa, kullanarak bir Windows çalışma zamanı bileşeni dönüştürebilir olabilir [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md). WRL ATL'ın tüm özelliklerini desteklemez ve OLE, bu nedenle bu tür bir bağlantı noktası uygun olup COM kodunuzu com, ATL, hangi özelliklere ne kadar bağımlı bağlıdır ve OLE bileşeniniz gerektirir.

UWP projelerinde mevcut C++ kodunu kullanabileceğiniz çeşitli yollar şunlardır. Bazı açılardan bileşen uzantıları ile derlenmesi için kod gerektirmeyen (C++/CX) etkin (diğer bir deyişle, ile `/ZW` seçeneği), ve kod standart çalışır durumda bulundurmanıza gerek bazı yapın, dolayısıyla C++, veya bir Klasik Win32 derleme ortamı bazıları için koru kod, uygun mimari seçim ile bunu yapabilirsiniz. Örneğin, tüm UWP UI içeren kod ve C#, Visual Basic ve JavaScript çağrı yapanlara sağlamak türlere Windows uygulaması projeleri ve Windows çalışma zamanı bileşeni projelerinde olması gerekir. Yalnızca kullanılması gereken kod C++ (dahil olmak üzere C++/CX) kod ile derleyen bir projede olabilir ya da `/WX` seçeneği veya bir standart C++ proje. Yalnızca ikili kod içinde statik bir kitaplık olarak bağlama tarafından kullanılan veya içerik olarak uygulamasıyla paketlenmiş ve yalnızca Yasak API'leri kullanmıyorsa DLL yükleniyor.

Seçtiğiniz bu geliştirme senaryolarını hangisinin bağımsız olarak kodunuzda kullanabilirsiniz ve böylece kodu Klasik Masaüstü Win32 ve UWP altında koşullu olarak derleyebilirsiniz makro tanımları sayısı haberdar olmanız gerekir.

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

Bu deyimler, uygulamalar, her iki ya da hiçbiri (Klasik Win32 yalnızca Masaüstü) UWP uygulamaları, Windows Phone Store sırasıyla uygulanır. Bu makrolar yalnızca Windows 8.1 SDK ve daha sonra durum, bunların hiçbiri göz önünde bulundurabileceğiniz sonra kodunuzu önceki sürümleriyle Windows SDK'yı veya Windows, yanı sıra diğer platformlar için derleme gerekiyorsa tanımlanan şekilde kullanılabilir.

Bu konu aşağıdaki yordamları içerir:

- [Bir Win32 kullanarak bir UWP uygulamasında DLL](#BK_Win32DLL)

- [C++ yerel bir statik kitaplık bir UWP uygulamasında kullanma](#BK_StaticLib)

- [Bir C++ Kitaplığı'na bir Windows çalışma zamanı bileşeni taşıma](#BK_WinRTComponent)

##  <a name="BK_Win32DLL"></a> Bir Win32 kullanarak bir UWP uygulamasında DLL

Bir Klasik Windows masaüstü uygulamasında olduğu gibi yalnızca herhangi bir yerel DLL kullanamazlar daha iyi güvenlik ve güvenilirlik için evrensel Windows uygulamaları bir kısıtlı çalışma zamanı ortamında çalıştırın. Bir DLL için kaynak kodu varsa, UWP üzerinde çalışır, böylece kod bağlantı noktası. Birkaç proje ayarları ve proje dosya meta verilerini projeyi bir UWP projesi olarak tanımlamak için değiştirerek başlayın. Kod kitaplığı kullanarak derlemek gereken `/ZW` seçeneğini aktarmasını C++/CX. Daha sıkı denetimler, ortamla ilişkilendirilmiş nedeniyle UWP uygulamalarında belirli API çağrılarına izin verilmiyor. Bkz: [Win32 ve COM API UWP uygulamaları için](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

Aşağıdaki yordamı kullanarak işlevleri sunan yerel bir DLL sahip olduğu durum için geçerli `__declspec(dllexport)`.

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>Bağlantı noktası için yeni bir proje oluşturmadan UWP yerel bir DLL

1. İşlevleri kullanarak dışa yerel bir DLL olup olmadığını `__declspec(dllexport)`, DLL olarak UWP projesini derleyerek bir UWP uygulaması bu işlevleri çağırabilir. Örneğin, birkaç sınıflarını ve yöntemlerini, aşağıdaki üst bilgi dosyası gibi bir kod ile dışarı aktaran bir DLL sahibiz varsayalım:

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

   (Stdafx.h, dllmain.cpp) projesinde bir şey standart Win32 Proje şablonu bir parçasıdır. Örneği takip etmek istiyorsanız, ancak kendi DLL henüz bu adımlarla kullanmak istemiyorsanız, Win32 projesi oluşturmayı deneyin, DLL projesi Sihirbazı'nda seçin ve ardından bir üstbilgi dosyası giraffe.h ve kod dosyası giraffe.cpp ekleyin ve bu adımı uygulamasına kodda içeriğini kopyalayın ropriate dosyaları.

   Makro kod tanımlar `GIRAFFE_API` çözümler için `__declspec(dllexport)` olduğunda `_DLL` (diğer bir deyişle, proje DLL olarak yapılandırıldığında) tanımlanır.

2. Açık **proje özellikleri** DLL projesi ve küme için **yapılandırma** için **yapılandırmalarında**.

3. İçinde **proje özellikleri**altında **C/C++** > **genel** sekmesinde, belirleyin **Windows çalışma zamanı uzantısını kullanma** için **Evet (/ZW)**. Bu bileşen uzantıları sağlar (C++/CX).

4. İçinde **Çözüm Gezgini**, proje düğümünü seçin, kısayol menüsünü açın ve seçin **projeyi**. Ardından, yüklenmemiş proje düğümünün kısayol menüsünde açın ve proje dosyasını düzenlemek seçin. Bulun `WindowsTargetPlatformVersion` öğesi şu öğeleri ile değiştirin.

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   .Vcxproj dosyasını kapatın, yeniden kısayol menüsünü açın ve seçin **projeyi**.

   **Çözüm Gezgini** şimdi projeyi bir evrensel Windows projesi olarak tanımlar.

5. Önceden derlenmiş üst bilgi dosyası adının doğru olduğundan emin olun. İçinde **önceden derlenmiş üst bilgiler** bölümünde **önceden derlenmiş üst bilgi dosyası** Stdafx.H'ye pch.h öğesinden. Bunu yapmazsanız, aşağıdaki hatayı görürsünüz.

   > hatası C2857: ' #include ' /Ycpch.h komut satırı seçeneği ile belirtilen deyim kaynak dosyasında bulunamadı

   Evrensel Windows projeleri için önceden derlenmiş üst bilgi dosyası farklı bir adlandırma kuralı kullanmak sorunudur.

6. Projeyi oluşturun. Uyumsuz komut satırı seçenekleri hakkında bazı hatalar alabilirsiniz. Örneğin, artık kullanım dışı ancak sık kullanılan seçeneği **en az yeniden derlemeyi etkinleştir (/ Gm)** eski birçok varsayılan olarak ayarlanmış C++ projeleri ve ile uyumlu değil `/ZW`.

   Evrensel Windows platformu için derleme yaparken bazı işlevler kullanılamaz. Derleyici hataları sorunlarla ilgili görürsünüz. Temiz yapı bulunana kadar bu adresi.

7. Aynı çözümdeki bir UWP uygulamasında DLL kullanmak için UWP proje düğümü için kısayol menüsünü açın ve seçin **Ekle** > **başvuru**.

   Altında **projeleri** > **çözüm**, DLL projesi yanındaki onay kutusunu seçin ve seçme **Tamam** düğmesi.

8. Kitaplık üstbilgi dosyaları UWP uygulamanızın pch.h dosyasına ekleyin.

    ```cpp
    #include "..\MyNativeDLL\giraffe.h"
    ```

9. Kod zamanki işlevleri çağırmak ve DLL türleri oluşturmak için UWP projesi ekleyin.

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

##  <a name="BK_StaticLib"></a> C++ yerel bir statik kitaplık bir UWP uygulamasında kullanma

Bir UWP projesi yerel C++ statik kitaplıkta kullanabilirsiniz, ancak bazı sınırlamalar ve dikkat edilmesi gereken sınırlamalar vardır. Okumayı Start [statik kitaplıklarda C++/CX](../cppcx/static-libraries-c-cx.md). Yerel kod, statik kitaplıkta UWP uygulamanızdan erişebilirsiniz, ancak ortak başvuru türleri statik kitaplık oluşturmak için önermedi. Statik bir kitaplıkla derlerseniz `/ZW` seçeneği, kitaplıkçı (aslında gizlenmiş bağlayıcı) uyarır:

> LNK4264: bir statik kitaplığa /ZW ile derlenen nesne dosyası arşivleme; Windows çalışma zamanı türleri yazılırken, Windows çalışma zamanı meta verileri içeren statik bir kitaplıkla bağlamak için önerilmediğini unutmayın

İle yeniden derlemeden bir UWP statik kitaplıkta ancak kullanabilirsiniz `/ZW`. Herhangi bir başvuru türü bildirmek veya C + kullanmayı mümkün olmayacaktır +/ CX oluşturur, sonra da bunu aşağıdaki adımları izleyerek yapabilirsiniz ancak amacınıza yalnızca yerel kod, kitaplığı kullanmak için uygun olup olmadığını.

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>Bir UWP projesi yerel C++ statik kitaplıkta kullanmak için

1. UWP projesi için proje özelliklerinde içinde **bağlayıcı** bölümünde, yolu kitaplığa eklemek **giriş** özelliği. Örneğin, bir kitaplık, çıktısını yerleştirir projedeki *SolutionFolder*\Debug\MyNativeLibrary\MyNativeLibrary.lib, göreli yol ekleme `Debug\MyNativeLibrary\MyNativeLibrary.lib`.

2. UWP projesi içinde pch.h üstbilgi dosyasına başvurmak ve kitaplığı kullanan kod ekleme başlatmak için bir ekleme deyimi ekleyin.

   ```cpp
   #include "..\MyNativeLibrary\giraffe.h"
   ```

   Başvuru eklemeyin **başvuruları** düğümünde **Çözüm Gezgini**. Bu mekanizma, yalnızca Windows çalışma zamanı bileşenleri için çalışır.

##  <a name="BK_WinRTComponent"></a> Bir C++ Kitaplığı'na bir Windows çalışma zamanı bileşeni taşıma

Statik kitaplıkta bir UWP uygulamasında yerel API'lerin kullanmasını istediğiniz ve yerel kitaplık için kaynak kodu varsa, bir Windows çalışma zamanı bileşeni koda bağlantı noktası. Statik kitaplık artık olmaz, bir DLL olacaktır. Herhangi bir C++ UWP uygulamasında kullanabilirsiniz, ancak statik kitaplık durumunu, başvuru türleri ve diğer C + ekleyebilirsiniz +/ CX yapıları, bir dil bağımsız olarak tüm UWP uygulama kodunda istemciler için kullanılabilir. Bu nedenle, bu tür C#, Visual Basic veya JavaScript erişebilirsiniz.  Temel bir Windows çalışma zamanı bileşeni projesi oluşturun, içine, statik kitaplık kodu kopyalayın ve kodu taşımak için standart bir C++ derlemeden ortaya çıkan hatalar adres oluşan bir yordamdır bir `/ZW` derleme.

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>Bir C++ Kitaplığı bir Windows çalışma zamanı bileşeni için bağlantı noktası

1. Bir Windows çalışma zamanı bileşeni projesi oluşturun.

2. Projeyi kapatın.

3. İçinde **Windows dosya Gezgini**, proje bulun. Varsayılan olarak, Visual Studio, Visual Studio 2017\Projects klasörünü Belgeler klasörünüzde kullanır. Taşımak istediğiniz kodu içeren C++ kitaplık projesi bulun. Kaynak dosyaları (üst bilgi dosyaları, kod dosyaları ve alt dizinlerinde dahil olmak üzere başka bir kaynak) C++ Kitaplığı projenize kopyalayın ve bunları aynı klasör yapısında korumak sağlamaktan proje klasörüne yapıştırın.

4. Windows çalışma zamanı bileşeni projesi yeniden açın ve proje düğümü için kısayol menüsünü açın **Çözüm Gezgini**ve **Ekle** > **var olan öğe**.

5. Orijinal projenize ekleyin ve tüm dosyaları seçin **Tamam**. Gerekirse, alt klasörleri için yineleyin.

6. Şimdi bazı kod Çoğalttığınız. Birden fazla önceden derlenmiş üst bilgi (örneğin stdafx.h ve pch.h) varsa tutmayı seçin. Tüm gerekli kodu kopyalayın, gibi açıklamaalarını tutma bir içerir. Ardından, projedeki diğer ve Özellikler altında Sil **önceden derlenmiş üst bilgiler**, üst bilgi dosyasının adının doğru olduğundan emin olun.

   Önceden derlenmiş üst bilgi kullanılacak dosyasını değiştirdiyseniz, önceden derlenmiş üst bilgi seçeneklerini her dosya için doğru olduğundan emin olun. Sırayla her .cpp dosyası seçin, kendi özellikleri penceresini açın ve tüm ayarlandığından emin olun **kullan (/Yu)**, istenen Ön derlenmiş üstbilgi dışında ayarlanması **oluştur (/Yc)**.

7. Projeyi oluşturmak ve tüm hataları çözümleyin. Bu hataları kullanarak kaynaklanabilir `/ZW` seçeneği veya Windows SDK'sı, yeni bir sürümü ile bunun veya bağımlılıkları kitaplığınızı bağlı başlık dosyaları ya da proje ayarlarında eski arasındaki farklar gibi olmanızdan kaynaklanabilir Proje ve yeni bir tane.

8. Genel başvuru türlerinde projenize ekleyin veya sıradan türleri giriş noktaları UWP uygulamaları aramak istediğiniz işlevi içinde kullanıma sunmak için başvuru türlerine dönüştürme.

9. UWP uygulama projesinden buna bir başvuru ekleyerek bileşeni test etmek ve oluşturduğunuz genel API'leri çağırmak için kod ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Evrensel Windows Platformu’na bağlantı noktası oluşturma](../porting/porting-to-the-universal-windows-platform-cpp.md)
