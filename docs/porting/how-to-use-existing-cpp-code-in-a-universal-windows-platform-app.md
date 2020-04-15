---
title: 'Nasıl yapılır: Mevcut C++ Kodunu Evrensel Windows Platformu Uygulamasında Kullanma'
ms.date: 04/08/2019
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: b1351a1c7858b00cffc454fa66831b3995aea804
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366423"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Nasıl yapılır: Mevcut C++ Kodunu Evrensel Windows Platformu Uygulamasında Kullanma

Masaüstü programınızı Evrensel Windows Platformu (UWP) ortamında çalıştırmanın belki de en kolay yolu Desktop Bridge teknolojilerini kullanmaktır. Bunlar arasında, mevcut uygulamanızı kod değişikliği gerektirmeden uwp uygulaması olarak paketleyecek olan Masaüstü Uygulama Dönüştürücüsü de yer alıyor. Daha fazla bilgi için [Desktop Bridge'e](/windows/uwp/porting/desktop-to-uwp-root)bakın.

Bu konunun geri kalanı, C++ kitaplıklarını (DL'ler ve statik kitaplıklar) Evrensel Windows Platformu'na nasıl bağlantı kurup kurabilirsiniz. Bunu, temel C++ mantığınızın birden çok UWP uygulamasıyla kullanılabilmesi için yapmak isteyebilirsiniz.

UWP Uygulamaları korumalı bir ortamda çalışır ve sonuç olarak platformun güvenliğini tehlikeye atabilecek birçok Win32, COM ve CRT API çağrısına izin verilmez. Derleyici bu tür çağrıları algılayabilir ve `/ZW` seçenek kullanılırsa bir hata oluşturabilir. Uygulamanızdaki Uygulama Sertifika Kiti'ni, yasak API'leri çağıran kodları algılamak için kullanabilirsiniz. Daha fazla bilgi için [Windows Uygulama Sertifika Kiti'ne](/windows/uwp/debug-test-perf/windows-app-certification-kit)bakın.

Kitaplık için kaynak kodu varsa, yasak API çağrılarını ortadan kaldırabilirsiniz. İzin verilen veya yasaklanmış API'lerin bir listesini içeren ayrıntılar için, [Evrensel Windows Platformu uygulamalarında desteklenmeyen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)UWP uygulamaları ve CRT işlevleri için Win32 ve COM [API'larına](/uwp/win32-and-com/win32-and-com-for-uwp-apps) bakın. Bazı alternatifler [UWP uygulamalarında Windows API'lerine Alternatifler'de](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)bulunabilir.

Evrensel Windows Projesi'nden klasik bir masaüstü kitaplığına bir başvuru eklemeye çalışırsanız, kitaplığın uyumlu olmadığını belirten bir hata iletisi alırsınız. Statik bir kitaplık söz konusu olduğunda, tıpkı klasik bir Win32 uygulamasında olduğu gibi, kitaplığınızı (.lib dosyası) bağlayıcı girişinize ekleyerek kitaplığınıza bağlayabilirsiniz. Yalnızca ikili kullanılabilen kitaplıklar için tek seçenek budur. Statik bir kitaplık uygulamanızın yürütülebilir içeriğine bağlıdır, ancak bir UWP uygulamasında tükettiğiniz Win32 DLL'nin projeye dahil edilerek ve İçerik olarak işaretlenerek uygulamaya paketlenmesi gerekir. Bir UWP uygulamasında Win32 DLL yüklemek için, [loadpackagedlibrary](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary) yerine `LoadLibrary` `LoadLibraryEx`veya .

DLL veya statik kitaplık için kaynak kodunuz varsa, `/ZW` UWP projesi olarak yeniden derleyebilirsiniz. Bunu yaparsanız, **Solution Explorer'ı**kullanarak bir başvuru ekleyebilir ve C++ UWP uygulamalarında kullanabilirsiniz. Bir DLL durumunda, dışa aktarma kitaplığı ile bağlantı.

İşlevselliği diğer dillerdeki arayanlara maruz bırakmak için kitaplığı Bir Windows Runtime Bileşenine dönüştürebilirsiniz. Windows Runtime Bileşenleri, .NET ve JavaScript tüketicilerinin ihtiyaç duyduğu şekilde içeriği açıklayan .winmd dosyaları biçiminde meta verileri içerdikleri için sıradan DL'lerden farklıdır. API öğelerini diğer dillere maruz bırakmak için, ref sınıfları gibi C++/CX yapıları ekleyebilir ve bunları herkese açık hale getirebilir veya [Windows Runtime C++ Şablon Kitaplığı'nı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanabilirsiniz.  Windows 10 ve sonraki durumlarda [C++/CX yerine C++/WinRT kitaplığını](https://github.com/microsoft/cppwinrt) kullanabilirsiniz.

Önceki tartışma, farklı şekilde ele alınması gereken COM bileşenleri için geçerli değildir. EXE veya DLL'de bir COM sunucunuz varsa, evrensel bir Windows Projesi'nde [kayıt gerektirmeyen](/windows/win32/sbscs/creating-registration-free-com-objects)bir COM bileşeni olarak paketlediğiniz, İçerik dosyası olarak projenize eklediğiniz ve [CoCreateInstanceFromApp](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp)kullanarak anlık olarak oluşturduğunuz sürece kullanabilirsiniz. Daha fazla bilgi için Windows [Mağazası C++ Projesi'nde Free-COM DLL kullanma'ya](https://blogs.msdn.microsoft.com/win8devsupport/2013/05/19/using-free-com-dll-in-windows-store-c-project/)bakın.

UWP'ye bağlantı sağlamak istediğiniz varolan bir COM kitaplığınız varsa, [Windows Runtime C++ Şablon Kitaplığı 'nı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanarak onu Windows Runtime Bileşenine dönüştürebilirsiniz. WRL, ATL ve OLE'nin tüm özelliklerini desteklemez, bu nedenle böyle bir bağlantı noktasının uygun olup olmadığı COM kodunuzcom, ATL ve OLE'nin bileşeninizin hangi özelliklerini gerektirdiğine bağlıdır.

Bunlar, UWP projelerinde varolan C++ kodunu kullanabileceğiniz çeşitli yollardır. Bazı yollarla kod bileşeni uzantıları (C++/CX) etkin (yani, `/ZW` seçenek ile) ile yeniden derlenecek gerektirmez, bu nedenle standart C++'da kod tutmanız veya bazı kodlar için klasik bir Win32 derleme ortamını korumanız gerekiyorsa, bunu uygun mimari seçenekleriyle yapabilirsiniz. Örneğin, UWP UI içeren tüm kodunuz ve C#, Visual Basic ve JavaScript arayanlara maruz kalınması gereken türleri Windows App projelerinde ve Windows Runtime Bileşeni projelerinde olmalıdır. Yalnızca C++'da (C++/CX dahil) tüketilmesi gereken kod, `/WX` seçenekle veya standart bir C++ projesiyle derlenen bir projede olabilir. Yalnızca ikili kod statik bir kitaplık olarak bağlayarak veya uygulamayla içerik olarak paketlenerek ve yalnızca yasak API'leri kullanmıyorsa DLL'ye yüklenerek kullanılabilir.

Bu geliştirme senaryolarından hangisini seçerseniz seçin, kodu hem klasik masaüstü Win32 hem de UWP altında koşullu olarak derleyebilmeniz için kodunuzda kullanabileceğiniz bir dizi makro tanımının farkında olmalısınız.

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

Bu ifadeler sırasıyla UWP uygulamaları, Windows Phone Mağazası uygulamaları, her ikisi veya ikisi için geçerlidir (yalnızca klasik Win32 masaüstü). Bu makrolar yalnızca Windows SDK 8.1 ve sonraki sürümlerinde kullanılabilir, bu nedenle kodunuzu Windows SDK'nın önceki sürümleriyle veya Windows dışındaki diğer platformlar için derlemek gerekiyorsa, bunların hiçbirinin tanımlanmadığını da göz önünde bulundurmanız gerekir.

Bu konu aşağıdaki yordamları içerir:

- [UWP Uygulamasında Win32 DLL kullanma](#BK_Win32DLL)

- [UWP Uygulamasında yerel C++ statik kitaplığı kullanma](#BK_StaticLib)

- [C++ Kitaplığı Windows Runtime Bileşenine Taşıma](#BK_WinRTComponent)

## <a name="using-a-win32-dll-in-a-uwp-app"></a><a name="BK_Win32DLL"></a>UWP Uygulamasında Win32 DLL kullanma

Daha iyi güvenlik ve güvenilirlik için, Universal Windows Apps sınırlı çalışma zamanı ortamında çalışır, böylece herhangi bir yerel DLL'yi klasik bir Windows masaüstü uygulamasında kullandığınız şekilde kullanamazsınız. Bir DLL için kaynak kodunuz varsa, kodu UWP'de çalışır şekilde işaretleyebilirsiniz. Projeyi UWP projesi olarak tanımlamak için birkaç proje ayarını ve proje dosyası meta verilerini değiştirerek başlarsınız. C++/CX sağlayan `/ZW` seçeneği kullanarak kitaplık kodunu derlemeniz gerekir. UWP uygulamalarında, bu ortamla ilişkili daha sıkı denetimler nedeniyle bazı API çağrılarına izin verilmez. [UWP uygulamaları için Win32 ve COM API'leri'ne](/uwp/win32-and-com/win32-and-com-for-uwp-apps)bakın.

Aşağıdaki yordam, kullanarak `__declspec(dllexport)`işlevleri ortaya çıkaran bir yerel DLL'ye sahip olduğunuz durum için de geçerlidir.

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>Yeni bir proje oluşturmadan yerel bir DLL'yi UWP'ye taşıma

1. Kullanarak işlevleri dışa dışa aktarma `__declspec(dllexport)`yapan bir yerel DLL'niz varsa, DLL'yi UWP projesi olarak yeniden derleyerek bu işlevleri bir UWP uygulamasından arayabilirsiniz. Örneğin, aşağıdaki üstbilgi dosyası gibi kodile birkaç sınıf ve yöntemleri dışa aktaran bir DLL'miz olduğunu varsayalım:

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

   Projedeki diğer her şey (stdafx.h, dllmain.cpp) standart Win32 proje şablonunun bir parçasıdır. Takip etmek istiyorsanız, ancak bu adımlarla henüz kendi DLL kullanmak istemiyorsanız, bir Win32 projesi oluşturmayı deneyin, proje sihirbazında DLL seçin ve sonra bir üstbilgi dosyası zürafa.h ve kod dosyası giraffe.cpp ekleyin ve uygun dosyalara bu adımda kod içeriğini kopyalayın.

   Kod, ne zaman `GIRAFFE_API` `_DLL` tanımlandığına `__declspec(dllexport)` (diğer bir şekilde, proje DLL olarak inşa edildiğinde) çözümleyen makroyu tanımlar.

2. DLL projesi için **Proje Özelliklerini** açın ve **Yapılandırmayı** **Tüm Yapılandırmalara**ayarlayın.

3. Project **Properties'te**, **C/C++** > **Genel** sekmesi altında, Windows Çalışma Süresi Uzantısını **Evet (/ZW)** olarak **ayarlayın.** Bu bileşen uzantıları (C++/CX) sağlar.

4. **Çözüm Gezgini'nde**proje düğümünü seçin, kısayol menüsünü açın ve **Project'i Boşalt'ı**seçin. Ardından, boşaltılmış proje düğümündeki kısayol menüsünü açın ve proje dosyasını düzenlemesini seçin. Öğeyi `WindowsTargetPlatformVersion` bulun ve aşağıdaki öğelerle değiştirin.

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   .vcxproj dosyasını kapatın, kısayol menüsünü yeniden açın ve **Project'i Yeniden Yükle'yi**seçin.

   **Solution Explorer** artık projeyi Evrensel Windows projesi olarak tanımlar.

5. Önceden derlenmiş üstbilgi dosya adınızın doğru olduğundan emin olun. Önceden **Derlenmiş Üstbilgi** bölümünde, **Önceden Derlenmiş Üstbilgi Dosyasını** *pch.h'den* *stdafx.h'ye*değiştirin. Bunu yapmazsanız, aşağıdaki hatayı görürsünüz.

   > hata C2857: /Ycpch.h komut satırı seçeneği ile belirtilen '#include' deyimi kaynak dosyada bulunamadı

   Sorun, Evrensel Windows projelerinin önceden derlenmiş üstbilgi dosyası için farklı bir adlandırma kuralı kullanmasıdır.

6. Projeyi derleyin. Uyumsuz komut satırı seçenekleri hakkında bazı hatalar alabilirsiniz. Örneğin, şimdi azalan ancak sık kullanılan seçenek **Enable Minimal Rebuild (/Gm)** varsayılan olarak birçok eski C++ `/ZW`projesinde ayarlanır ve .

   Evrensel Windows Platformu için derlediğinizde bazı işlevler kullanılamaz. Herhangi bir sorun hakkında derleyici hataları göreceksiniz. Temiz bir yapıya sahip olana kadar bunları ele alın.

7. Aynı çözümde bir UWP uygulamasında DLL kullanmak için, UWP proje düğümü için kısayol menüsünü açın ve**Başvuru** **Ekle'yi** > seçin.

   **Projeler** > **Çözümü**altında, DLL projesinin yanındaki onay kutusunu seçin ve **Tamam** düğmesini seçin.

8. UWP uygulamanızın *pch.h* dosyasına kitaplığın üstbilgi dosyasını(lar) ekleyin.

    ```cpp
    #include "..\MyNativeDLL\giraffe.h"
    ```

9. Işlevleri çağırmak ve DLL'den türler oluşturmak için UWP projesinde her zamanki gibi kod ekleyin.

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

## <a name="using-a-native-c-static-library-in-a-uwp-app"></a><a name="BK_StaticLib"></a>UWP Uygulamasında yerel C++ statik kitaplığı kullanma

UWP projesinde yerel c++ statik kitaplığını kullanabilirsiniz, ancak dikkat edilmesi gereken bazı kısıtlamalar ve sınırlamalar vardır. [C++/CX'teki statik kitaplıklar](../cppcx/static-libraries-c-cx.md)hakkında okuyarak başlayın. Statik kitaplığınızdaki yerel koda UWP uygulamanızdan erişebilirsiniz, ancak böyle bir statik kitaplıkta genel ref türleri oluşturmanız önerilmez. `/ZW` Bu seçenekle statik bir kitaplık derlerseniz, kütüphaneci (aslında kılık değiştirmiş bağlayıcı) şu uyarıda bulunur:

> LNK4264: /ZW ile derlenen nesne dosyasının statik bir kitaplığa arşivleme; Windows Runtime türleri yazarken Windows Runtime meta verileri içeren statik bir kitaplık ile bağlantı tavsiye edilmez unutmayın

Ancak, bir UWP ile yeniden derlemeden statik bir `/ZW`kitaplık kullanabilirsiniz. Herhangi bir ref türünü beyan edemez veya C++/CX yapılarını kullanamazsınız, ancak amacınız yalnızca yerel kod kitaplığını kullanmaksa, bunu aşağıdaki adımları izleyerek yapabilirsiniz.

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP projesinde yerel C++ statik kitaplığını kullanmak için

1. UWP projesinin proje özelliklerinde, sol bölmedeki **Configuration Properties** > **Linker** > **Girişi'ni** seçin. Sağ bölmede, **Ek Bağımlılıklar** özelliğindeki kitaplık yolunu ekleyin. Örneğin, çıktısını *SolutionFolder*\Debug\MyNativeLibrary\MyNativeLibrary.lib'e yerleştiren projedeki bir kitaplık için, göreli yolu `Debug\MyNativeLibrary\MyNativeLibrary.lib`ekleyin.

2. Üstbilgi *dosyanıza* (varsa) veya gerektiğinde herhangi bir .cpp dosyasına başvurmak için bir ek açıklama ekleyin ve kitaplığı kullanan kod eklemeye başlayın.

   ```cpp
   #include "..\MyNativeLibrary\giraffe.h"
   ```

   **Çözüm Gezgini'ndeki** **Başvuru** düğümüne bir başvuru eklemeyin. Bu mekanizma yalnızca Windows Runtime Bileşenleri için çalışır.

## <a name="porting-a-c-library-to-a-windows-runtime-component"></a><a name="BK_WinRTComponent"></a>C++ Kitaplığı Windows Runtime Bileşenine Taşıma

Bir UWP uygulamasından statik bir kitaplıkta yerel API'leri tüketmek istiyorsanız ve yerel kitaplığın kaynak koduna sahipseniz, kodu bir Windows Runtime Bileşenine taşınabilirsiniz. Artık statik bir kütüphane olmayacak, bir DLL olacak. Herhangi bir C++ UWP uygulamasında kullanabilirsiniz, ancak statik kitaplık durumundan farklı olarak, dilden bağımsız olarak herhangi bir UWP uygulama kodunda istemcilerin kullanabileceği ref türleri ve diğer C++/CX yapıları ekleyebilirsiniz. Bu nedenle, bu tür lere C#, Visual Basic veya JavaScript'ten erişebilirsiniz.  Temel yordam, bir Windows Runtime Bileşeni projesi oluşturmak, statik kitaplığınız için kodu kopyalamak ve kodu standart bir C++ `/ZW` derlemesinden derlemeye taşımaktan kaynaklanan hataları gidermektir.

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>C++ kitaplığını Windows Runtime Bileşenine taşıma

1. Bir Windows Runtime Bileşeni projesi oluşturun.

2. Projeyi kapatın.

3. Windows **Dosya Gezgini'nde**projeyi bulun. Varsayılan olarak Visual Studio, Belgeler klasörünüzdeki Visual Studio 2017\Projects klasörünü kullanır. Bağlantı noktasına gelmek istediğiniz kodu içeren C++ kitaplık projesini bulun. C++ kitaplık projenizden kaynak dosyaları (üstbilgi dosyaları, kod dosyaları ve alt dizinler de dahil olmak üzere diğer kaynaklar) kopyalayın ve aynı klasör yapısını koruduğunuzdan emin olmak için proje klasörüne yapıştırın.

4. Windows Runtime Bileşeni projesini yeniden açın ve **Solution Explorer'daki**proje düğümü için kısayol menüsünü açın ve**Varolan Öğe** **Ekle'yi** > seçin.

5. Özgün projenizden ekleyeceğiniz tüm dosyaları seçin ve **Tamam'ı**seçin. Alt klasörler için gerekirse yineleyin.

6. Şimdi bazı yinelenen kod olabilir. Birden fazla önceden derlenmiş üstbilginiz varsa *(stdafx.h* ve *pch.h)* tutmak için birini seçin. İçki ifadeleri gibi gerekli kodları tuttuğunuz koda kopyalayın. Daha sonra, diğerini silin ve proje özelliklerinde, **Önceden Derlenmiş Üstbilgi**altında, üstbilgi dosyasının adının doğru olduğundan emin olun.

   Dosyayı önceden derlenmiş üstbilgi olarak kullanmak üzere değiştirdiyseniz, önceden derlenmiş üstbilgi seçeneklerinin her dosya için doğru olduğundan emin olun. Sırayla her .cpp dosyasını seçin, özellikleri penceresini açın ve **create (/Yc)** olarak ayarlanmalıdır istenen önceden derlenmiş üstbilgi dışında tüm **Kullanım (/Yu)** olarak ayarlandıklarından emin olun.

7. Projeyi oluşturun ve hataları giderin. Bu hatalar `/ZW` seçeneğin kullanılmasından kaynaklanabilir veya Windows SDK'nın yeni bir sürümünden kaynaklanabilir veya kitaplığınızın bağlı olduğu üstbilgi dosyaları veya eski projeniz ile yeni proje ayarları arasındaki farklar gibi bağımlılıkları yansıtabilir.

8. UWP uygulamalarından aramak istediğiniz işlevselliğe giriş noktalarını ortaya çıkarmak için projenize genel ref türleri ekleyin veya normal türleri ref türlerine dönüştürün.

9. Bir UWP uygulama projesinden bir başvuru ekleyerek bileşeni sınayın ve oluşturduğunuz genel API'leri aramak için bazı kodlar ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Evrensel Windows Platformuna Taşıma](../porting/porting-to-the-universal-windows-platform-cpp.md)
