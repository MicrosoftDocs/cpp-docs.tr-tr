---
title: 'Nasıl yapılır: Mevcut C++ kodunu Evrensel Windows Platformu uygulamasında kullanma'
description: Evrensel Windows Platformu uygulamalarda mevcut kod uygulamalarınızı ve kitaplıklarınızı kullanmanın yolları.
ms.date: 09/04/2020
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 1e946d588f1a14018ebb11a60b319c2d54658f25
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609126"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Nasıl yapılır: Mevcut C++ kodunu Evrensel Windows Platformu uygulamasında kullanma

Evrensel Windows Platformu (UWP) projelerinde mevcut C++ kodunu kullanmanın çeşitli yolları vardır. Bazı yollarla kodun bileşen uzantıları (C++/CX) etkin (yani `/ZW` seçeneğiyle) ve bazı yöntemlerle yeniden derlenmesi gerekmez. Kodu standart C++ ' da tutmanız veya bazı kodlar için klasik bir Win32 derleme ortamını korumanız gerekebilir. Uygun mimari seçenekleriyle yine de yapabilirsiniz. UWP Kullanıcı arabirimi ve C#, Visual Basic ve JavaScript çağıranları tarafından sunulan türler içeren tüm kodunuzu göz önünde bulundurun. Bu kodun Windows uygulama projelerinde ve Windows Çalışma Zamanı bileşen projelerinde olması gerekir. Yalnızca C++ ' dan (C++/CX dahil) çağırdığınız kod, `/ZW` seçenek veya standart C++ projesiyle derlenen bir projede olabilir. İzin verilmeyen API 'Leri kullanmayan salt BINARY kodu, ' ın statik kitaplık olarak bağlanması ile kullanılabilir. Ya da uygulamayı içerik olarak paketleyebilir ve DLL 'ye yükleyebilirsiniz.

Masaüstü programınızı UWP ortamında çalışan bir şekilde almanın en kolay yolu masaüstü Köprüsü teknolojilerini kullanmaktır. Mevcut uygulamanızı kod değişikliği gerekmeden UWP uygulaması olarak paketleyip masaüstü uygulaması dönüştürücüsünü içerirler. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

Bu makalenin geri kalanında, C++ kitaplıklarının (dll 'Ler ve statik kitaplıklar) Evrensel Windows Platformu bağlantı noktası oluşturma konusu açıklanmaktadır. Temel C++ mantığınızın birden çok UWP uygulaması ile kullanılabilmesi için kodunuzun bağlantı noktası almak isteyebilirsiniz.

UWP uygulamaları korumalı bir ortamda çalışır. Sonuç olarak, platform güvenliğinin tehlikeye atabilecek birçok Win32, COM ve CRT API çağrısı yapılmasına izin verilmez. `/ZW`Derleyici seçeneği bu tür çağrıları algılayabilir ve bir hata oluşturur. İzin verilmeyen API 'Leri çağıran kodu algılamak için uygulamanızdaki uygulama sertifikasyon kitini kullanabilirsiniz. Daha fazla bilgi için bkz. [Windows uygulama Sertifikalama seti](/windows/uwp/debug-test-perf/windows-app-certification-kit).

Kitaplık için kaynak kodu kullanılabiliyorsa izin verilmeyen API çağrılarını ortadan kaldırmaya çalışırsınız. İzin verilmeyen API 'lerin listesi için, bkz. [Evrensel Windows platformu uygulamalarda desteklenmeyen](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) [UWP uygulamaları IÇIN Win32 ve com API 'leri](/uwp/win32-and-com/win32-and-com-for-uwp-apps) ve CRT işlevleri. [UWP uygulamalarında Windows API 'Lerinin alternatifleri bölümünde](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)bazı alternatifler bulabilirsiniz.

Bir Evrensel Windows projesinden klasik masaüstü kitaplığına bir başvuru eklemeye çalışırsanız, kitaplığın uyumlu olmadığını belirten bir hata iletisi alırsınız. Bu bir statik kitaplık ise, bir *`.lib`* Klasik Win32 uygulamasında yaptığınız şekilde bağlayıcı girişine kitaplık (dosya) ekleyerek kitaplığınıza bağlanabilirsiniz. Yalnızca bir ikili kitaplık varsa, tek seçenektir. Statik bir kitaplık, uygulamanızın yürütülebilir dosyasına bağlanır. Ancak, UWP uygulamasında kullandığınız bir Win32 DLL, projeye dahil ederek ve Içerik olarak işaretleyerek uygulamaya paketlenmesi gerekir. Bir UWP uygulamasında bir Win32 DLL yüklemek için, ya da yerine çağırmanız gerekir [`LoadPackagedLibrary`](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary) `LoadLibrary` `LoadLibraryEx` .

DLL veya statik kitaplık için kaynak kodunuz varsa, derleyici seçeneğini kullanarak onu UWP projesi olarak yeniden derleyebilirsiniz `/ZW` . Daha sonra, **Çözüm Gezgini**kullanarak buna bir başvuru ekleyebilir ve bunu C++ UWP uygulamalarında kullanabilirsiniz. Dışarı aktarma kitaplığını kullanarak DLL 'yi bağlayın.

Diğer dillerdeki arayanlara işlevselliği göstermek için, kitaplığı bir Windows Çalışma Zamanı bileşenine dönüştürebilirsiniz. Windows Çalışma Zamanı bileşenler *`.winmd`* , içeriği .net ve JavaScript tüketicilerinin gerektirdiği bir şekilde tanımlayan dosyalar biçiminde meta verileri dahil ettikleri sıradan dll 'lerden farklıdır.  API öğelerini diğer dillere göstermek için, ref sınıfları gibi C++/CX yapıları ekleyebilir ve bunları herkese açık hale getirebilirsiniz. Windows 10 ve üzeri sürümlerde c++/cxyerine [c++/Wınrt kitaplığını](https://github.com/microsoft/cppwinrt) öneririz.

Önceki tartışma, farklı şekilde işlenmesi gereken COM bileşenlerine uygulanmaz. Bir EXE veya DLL 'de bir COM sunucunuz varsa, bunu bir Evrensel Windows projesinde kullanabilirsiniz. Bunu, kayıtsız bir [com bileşeni](/windows/win32/sbscs/creating-registration-free-com-objects)olarak paketleyin, projenize bir içerik dosyası olarak ekleyin ve kullanarak örneğini oluşturun [`CoCreateInstanceFromApp`](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp) . Daha fazla bilgi için bkz. [Windows Mağazası C++ projesinde ÜCRETSIZ com dll kullanma](/archive/blogs/win8devsupport/using-free-com-dll-in-windows-store-c-project).

UWP 'ye mevcut bir COM kitaplığını bağlantı noktası eklemek istiyorsanız, bunu bir Windows Çalışma Zamanı bileşenine dönüştürmek de mümkündür. Bu tür bağlantı noktaları için C++/Wınrt kitaplığı önerilir, ancak [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)kullanmak da mümkündür. WRL kullanım dışıdır ve ATL ve OLE 'nin tüm özelliklerini desteklemez. Böyle bir bağlantı noktasının uygulanabilir olup olmadığı, bileşeninizin gerektirdiği COM, ATL ve OLE özelliklerine bağlıdır.

Seçtiğiniz geliştirme senaryolarında, bazı makro tanımlarından haberdar olmanız gerekir. Kodu hem klasik masaüstü Win32 hem de UWP altında koşullu olarak derlemek için kodunuzda bu makroları kullanabilirsiniz.

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

Bu deyimler sırasıyla UWP uygulamalarına, Windows Phone mağaza uygulamalarına, her ikisine de veya hiçbirine (yalnızca Klasik Win32 Masaüstü) uygulanır. Bu makrolar yalnızca Windows SDK 8,1 ve üzeri sürümlerde kullanılabilir.

Bu makale aşağıdaki yordamları içerir:

- [UWP uygulamasında Win32 DLL kullanma](#BK_Win32DLL)

- [UWP uygulamasında yerel C++ statik kitaplığı kullanma](#BK_StaticLib)

- [C++ Kitaplığı Windows Çalışma Zamanı bileşenine taşıma](#BK_WinRTComponent)

## <a name="using-a-win32-dll-in-a-uwp-app"></a><a name="BK_Win32DLL"></a> UWP uygulamasında Win32 DLL kullanma

Daha iyi güvenlik ve güvenilirlik için, Evrensel Windows uygulamaları kısıtlı bir çalışma zamanı ortamında çalışır. Yalnızca klasik bir Windows masaüstü uygulamasında yaptığınız şekilde herhangi bir yerel DLL kullanamazsınız. Bir DLL için kaynak kodunuz varsa, UWP üzerinde çalışacak şekilde kodu bağlantı noktası oluşturabilirsiniz. Projeyi UWP projesi olarak tanımlamak için birkaç proje ayarını ve proje dosyası meta verilerini değiştirerek başlayın. `/ZW`C++/CX' i sağlayan seçeneğini kullanarak kitaplık kodunu yeniden derleyeceksiniz. Bu ortamla ilişkili daha sıkı denetimler olduğundan UWP uygulamalarında belirli API çağrılarına izin verilmez. Daha fazla bilgi için bkz. [UWP uygulamaları Için Win32 ve com API 'leri](/uwp/win32-and-com/win32-and-com-for-uwp-apps).

Kullanarak işlevleri dışarı aktaran bir yerel DLL varsa, bir UWP `__declspec(dllexport)` projesi olarak DLL 'yi yeniden derleyerek bu IŞLEVLERI UWP uygulamasından çağırabilirsiniz. Örneğin, *Giraffe* adlı BIR Win32 DLL projem olduğunu varsayalım. Bu, aşağıdaki üstbilgi dosyası gibi kodla birlikte birkaç sınıfı ve kendi yöntemlerini dışarı aktardık:

```cpp
// giraffe.h
// Define GIRAFFE_EXPORTS when building this DLL
#pragma once

#ifdef GIRAFFE_EXPORTS
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
#include "pch.h"
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

Projedeki diğer her şey ( *`pch.h`* , *`dllmain.cpp`* ) standart Win32 Proje şablonunun bir parçasıdır. Kod, `GIRAFFE_API` `__declspec(dllexport)` ne zaman tanımlandığına çözümlenen makroyu tanımlar `GIRAFFE_EXPORTS` . Diğer bir deyişle, proje DLL olarak oluşturulduğunda tanımlanır, ancak bir istemci üstbilgiyi kullandığında değildir *`giraffe.h`* . Bu DLL, kaynak kodu değiştirmeden UWP projesinde kullanılabilir. Yalnızca bazı proje ayarlarının ve özelliklerinin değiştirilmesi gerekir.

Aşağıdaki yordam, kullanarak işlevleri kullanıma sunan bir yerel DLL olduğunda geçerlidir `__declspec(dllexport)` .

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>Yeni bir proje oluşturmadan UWP 'e yerel DLL 'ye bağlantı noktası oluşturma

1. Visual Studio 'da DLL projenizi açın.

1. DLL projesi için **Proje özelliklerini** açın ve **yapılandırmayı** **tüm yapılandırmalar**olarak ayarlayın.

1. **Proje özellikleri**' nde, **C/C++**  >  **genel** sekmesinde, kullanım **Windows çalışma zamanı uzantısını** **Evet (/ZW)** olarak ayarlayın. Bu özellik bileşen uzantılarına (C++/CX) izin vermez.

1. **Çözüm Gezgini**, proje düğümünü seçin, kısayol menüsünü açın ve **Projeyi Kaldır**' ı seçin. Ardından, yüklenmeyen proje düğümünde kısayol menüsünü açın ve proje dosyasını düzenlemeyi seçin. Öğesini bulun `WindowsTargetPlatformVersion` ve aşağıdaki öğelerle değiştirin.

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   Dosyayı kapatın *`.vcxproj`* , kısayol menüsünü yeniden açın ve **projeyi yeniden yükle**' yi seçin.

   **Çözüm Gezgini** artık projeyi bir Evrensel Windows projesi olarak tanımlıyor.

1. Önceden derlenmiş üst bilgi dosyası adınızın doğru olduğundan emin olun. **Önceden derlenmiş üstbilgiler** bölümünde, aşağıdaki gibi bir hata görürseniz, **önceden derlenmiş üst bilgi dosyasını** ' dan ' *`pch.h`* e *`stdafx.h`* veya başka bir yolla değiştirmeniz gerekebilir:

   > hata C2857: komut satırı seçeneğiyle belirtilen ' #include ' ifadesiyle **`/Ycpch.h`** kaynak dosyada bulunamadı

   Bu sorun eski proje şablonlarının ön derlenmiş üstbilgi dosyası için farklı bir adlandırma kuralı kullanmasına yöneliktir. Visual Studio 2019 ve sonraki projeler kullanır *`pch.h`* .

1. Projeyi derleyin. Uyumsuz komut satırı seçenekleri hakkında bazı hatalar alabilirsiniz. Örneğin, artık kullanım dışı olan ancak sık kullanılan seçenek **en az sayıda yeniden derlemeyi etkinleştir (/GD)** seçeneği, daha eski C++ projelerinde varsayılan olarak ayarlanır ve ile uyumlu değildir `/ZW` .

   Evrensel Windows Platformu için derlerken bazı işlevler kullanılamaz. Herhangi bir sorun hakkında derleyici hataları görürsünüz. Temiz bir yapıya sahip olana kadar bu hataları çözün.

1. DLL 'yi aynı çözümde bir UWP uygulamasında kullanmak için, UWP proje düğümünün kısayol menüsünü açın ve başvuru **Ekle**' yi seçin  >  **Reference**.

   **Projeler**  >  **çözümü**altında dll projesinin yanındaki onay kutusunu işaretleyin ve **Tamam** düğmesini seçin.

1. Kitaplığın üst bilgi dosyalarını UWP uygulamanızın *`pch.h`* dosyasına ekleyin.

    ```cpp
    #include "..\Giraffe\giraffe.h"
    ```

1. İşlevleri çağırmak ve DLL 'den türler oluşturmak için UWP projesinde her zamanki gibi kod ekleyin.

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

## <a name="using-a-native-c-static-library-in-a-uwp-app"></a><a name="BK_StaticLib"></a> UWP uygulamasında yerel C++ statik kitaplığı kullanma

UWP projesinde yerel C++ statik kitaplığını kullanabilirsiniz, ancak farkında olacak bazı kısıtlamalar ve sınırlamalar vardır. [C++/CX ' te statik kitaplıklar](../cppcx/static-libraries-c-cx.md)hakkında okumaya başlayın. UWP uygulamanızdan statik kitaplığınızdaki yerel koda erişebilirsiniz, ancak bu tür bir statik kitaplıkta ortak başvuru türleri oluşturulması önerilmez. Seçeneğiyle bir statik kitaplık derlerseniz `/ZW` , kütüphaneian (aslında gizleyen bağlayıcı) sizi uyarır:

> LNK4264:/ZW ile derlenen nesne dosyasını statik bir kitaplığa arşivleme; Windows Çalışma Zamanı türler yazarken Windows Çalışma Zamanı meta verileri içeren bir statik kitaplıkla bağlantı önerildiğine unutmayın

Ancak, bir UWP uygulamasındaki statik bir kitaplığı, ile yeniden derlemeden kullanabilirsiniz `/ZW` . Kitaplığınız herhangi bir başvuru türü bildiremeyebilir veya C++/CX yapılarını kullanamaz. Ancak, amacınıza yalnızca yerel kod kitaplığı kullanmak istiyorsanız, bu adımları izleyerek bunu yapabilirsiniz.

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP projesinde yerel C++ statik kitaplığını kullanmak için

1. UWP projesinin proje özellikleri ' nde, sol bölmedeki **yapılandırma özellikleri**  >  **bağlayıcı**  >  **girişi** ' ni seçin. Sağ bölmede, **ek bağımlılıklar** özelliğindeki kitaplığa yolu ekleyin. Örneğin, projedeki çıktısını yerleştiren bir kitaplık için *`<SolutionFolder>\Debug\MyNativeLibrary\MyNativeLibrary.lib`* göreli yolu ekleyin *`Debug\MyNativeLibrary\MyNativeLibrary.lib`* .

1. Üstbilgi dosyasını *`pch.h`* dosyanıza (varsa) veya gerekirse herhangi bir dosyaya başvurmak için bir include ifadesini ekleyin *`.cpp`* ve kitaplığı kullanan kodu eklemeye başlayın.

   ```cpp
   #include "..\MyNativeLibrary\MyNativeLibrary.h"
   ```

   **Çözüm Gezgini** **Başvurular** düğümüne başvuru eklemeyin. Bu mekanizma yalnızca Windows Çalışma Zamanı bileşenleri için geçerlidir.

## <a name="porting-a-c-library-to-a-windows-runtime-component"></a><a name="BK_WinRTComponent"></a> C++ Kitaplığı Windows Çalışma Zamanı bileşenine taşıma

UWP uygulamasından bir statik kitaplıkta yerel API 'Leri kullanmak istediğinizi varsayalım. Yerel kitaplık için kaynak kodunuz varsa, kodun Windows Çalışma Zamanı bir bileşende bağlantı noktası oluşturabilirsiniz. Artık bir statik kitaplık olmayacaktır; Bunu, herhangi bir C++ UWP uygulamasında kullanabileceğiniz bir DLL 'e dönüştürebilirsiniz. Bu yordamda, C++/CX uzantıları kullanan yeni bir Windows Çalışma Zamanı bileşenin nasıl oluşturulacağı açıklanmaktadır. Bunun yerine C++/Wınrt kullanan bir bileşen oluşturma hakkında daha fazla bilgi için bkz. [c++/wınrt ile Windows çalışma zamanı bileşenleri](/windows/uwp/winrt-components/create-a-windows-runtime-component-in-cppwinrt).

C++/CX kullandığınızda, her UWP uygulama kodundaki istemciler için kullanılabilir olan başvuru türlerini ve diğer C++/CX yapılarını ekleyebilirsiniz. Bu türlere C#, Visual Basic veya JavaScript üzerinden erişebilirsiniz. Temel yordam:

- Windows Çalışma Zamanı bileşeni (Evrensel Windows) projesi oluşturun,
- statik kitaplığınızın kodunu içine kopyalayın ve
- Derleyicinin hata nedeniyle oluşan tüm hataları çözün `/ZW` .

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>Bir C++ kitaplığının Windows Çalışma Zamanı bileşenine bağlantı noktası oluşturma

1. Windows Çalışma Zamanı bileşeni (Evrensel Windows) projesi oluşturun.

1. Projeyi kapatın.

1. **Windows Dosya Gezgini**'nde yeni projeyi bulun. Ardından, bağlantı noktası yapmak istediğiniz kodu içeren C++ Kitaplığı projesini bulun. C++ Kitaplığı projenizden kaynak dosyalarını (üst bilgi dosyalarını, kod dosyalarını ve alt dizinler dahil diğer tüm kaynakları) kopyalayın. Yeni proje klasörüne yapıştırarak aynı klasör yapısını koruduğunuzdan emin olun.

1. Windows Çalışma Zamanı bileşen projesini yeniden açın. **Çözüm Gezgini**' de proje düğümü için kısayol menüsünü açın ve **Add**  >  **var olan öğeyi**Ekle ' yi seçin.

1. Özgün projenizden eklenecek tüm dosyaları seçin ve **Tamam**' ı seçin. Alt klasörler için gerekliyse tekrarlayın.

1. Artık yinelenen bir kodunuz olabilir. Birden çok önceden derlenmiş üst bilgi (her ikisi de) varsa *`stdafx.h`* *`pch.h`* , saklanacak bir tane seçin. Include deyimlerini gibi gerekli kodu, koruduğunuz birine kopyalayın. Ardından, diğerini silin ve proje özelliklerinde, **önceden derlenmiş üstbilgiler**altında, üstbilgi dosyasının adının doğru olduğundan emin olun.

   Önceden derlenmiş üst bilgi olarak kullanılacak dosyayı değiştirdiyseniz, ön derlenmiş üstbilgi seçeneklerinin her dosya için doğru olduğundan emin olun. Her bir *`.cpp`* dosyayı sırayla seçin, Özellikler penceresini açın ve önceden derlenmiş üst bilgi dışında **,** **Create (/rivc)** olarak ayarlanmalıdır.

1. Projeyi derleyin ve hataları çözün. Bu hatalar, `/ZW` seçeneği kullanılarak veya Windows SDK yeni bir sürümü nedeniyle kaynaklanmış olabilir. Ya da, kitaplığınızın bağımlı olduğu üst bilgi dosyaları gibi bağımlılıkları veya eski projeniz ile yeni bir proje ayarları arasındaki farkları yansıtabilirler.

1. Projenize ortak başvuru türleri ekleyin veya normal türleri ref türlerine dönüştürün. UWP uygulamalarından çağırmak istediğiniz işlevselliğe giriş noktalarını göstermek için bu türleri kullanın.

1. Bir UWP uygulama projesinden buna bir başvuru ekleyerek bileşeni test edin ve oluşturduğunuz ortak API 'Leri çağırmak için kod ekleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Evrensel Windows Platformu taşıma](../porting/porting-to-the-universal-windows-platform-cpp.md)
