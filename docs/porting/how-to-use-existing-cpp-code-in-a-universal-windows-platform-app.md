---
title: "Nasıl yapılır: mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 10b63f8e7bd7d23e75417e28b45d533832c8426e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>Nasıl yapılır: Mevcut C++ Kodunu Evrensel Windows Platformu Uygulamasında Kullanma
Belki de UWP ortamında çalışan masaüstü programınızı almak için en kolay yolu Masaüstü köprüsü teknolojileri kullanmaktır. Varolan uygulamanızı içermeyen bir UWP uygulaması olarak paketini masaüstü uygulaması dönüştürücü bunlar kodu gerekli değişiklikleri. Daha fazla bilgi için bkz: [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-root).

Bu konunun geri kalanında C++ kitaplıklarını (DLL'ler ve statik kitaplıklarından) bağlantı noktası Evrensel Windows Platformu (UWP) açıklanmaktadır. Böylece çekirdek C++ mantığı ile birden çok UWP uygulamaları kullanılabilir yapmak isteyebilirsiniz. 
  
 Korumalı bir ortamda UWP uygulamaları çalıştırabilir ve sonuç olarak, platform güvenliğini tehlikeye atabilir çoğu Win32 ve COM CRT API çağrıları izin verilmez. Derleyici tür çağrılar algılayabilir ve /ZW seçeneği kullanıldığında bir hata oluşturur. Yasaklanmış API çağıran kodu algılamak için uygulama sertifika kitiyle, uygulamanızda kullanabilirsiniz. Bkz: [uygulama sertifika kitiyle kullanarak](https://msdn.microsoft.com/library/windows/apps/hh694081.aspx).  
  
 Kitaplık için kaynak kodu varsa, yasaklanmış API çağrıları ortadan kaldırmak mümkün olabilir. İzin verilen veya Yasak API'lerin listesi dahil olmak üzere ayrıntılı bilgi için bkz: [Win32 ve Windows çalışma zamanı uygulamaları için COM ve evrensel Windows Platformu (UWP) uygulamaları](https://msdn.microsoft.com/library/windows/apps/br205762.aspx) ve [CRT işlevleri ile desteklenmez /ZW](https://msdn.microsoft.com/library/windows/apps/jj606124.aspx). Bazı alternatifleri bulunabilir [Windows çalışma zamanı uygulamaları ve evrensel Windows Platformu (UWP) uygulamaları Windows API'leri alternatifleri](https://msdn.microsoft.com/library/windows/apps/hh464945.aspx).  
  
 Yalnızca bir evrensel Windows projeden Klasik Masaüstü kitaplığına bir başvuru eklemeniz çalışırsanız, kitaplık uyumlu olmayan bildiren bir hata iletisi alırsınız. Bir statik kitaplık söz konusu olduğunda klasik bir Win32 uygulaması gibi kitaplığına (.lib dosyası), bağlayıcı girişi için basitçe ekleyerek kitaplığınıza bağlayabilirsiniz. Yalnızca bir ikili kullanılabilir olduğu kitaplıkları için tek seçenek budur. Bir statik kitaplık, uygulamanızın yürütülebilir bağlandı, ancak bir UWP uygulamasında kullanan Win32 DLL projesinde dahil ve içerik olarak işaretleme uygulamaya paketlenmesi gerekir. Win32 DLL bir evrensel Windows platformu uygulamasında yüklemek için çağırmak de [LoadPackagedLibrary](https://msdn.microsoft.com/library/windows/desktop/hh447159.aspx) LoadLibrary veya LoadLibraryEx yerine.  
  
 DLL veya statik kitaplık için kaynak kodu varsa, /ZW ile UWP projesi olarak derlenir. Bunu yaparsanız, Çözüm Gezgini'nde bir başvuru ekleyin ve C++ UWP uygulamalarında kullanın. DLL'den söz konusu olduğunda dışa aktarma kitaplığı ile bağlantı.  
  
 Diğer dillerde arayanlara işlevselliği kullanıma sunmak için kitaplık Windows çalışma zamanı bileşeni dönüştürebilirsiniz. Meta veri formunda içeriğini .NET ve JavaScript tüketicileri gerektiren bir şekilde tanımlayan .winmd dosyaların içerirler, Windows çalışma zamanı bileşenleri sıradan DLL'lerden farklılık gösterir. Diğer diller için API öğeleri göstermek için C + ekleyebileceğiniz +/ CX, ref sınıflar gibi oluşturur ve genel hale getirmek veya kullanmak [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).  Windows 10 ve sonraki sürümlerinde, kullanabileceğiniz [C + +/ WinRT Kitaplığı](https://github.com/microsoft/cppwinrt) yerine C + +/ CX. 
  
 Yukarıdaki açıklama farklı şekilde ele alınması COM bileşenlerini çalışması için geçerli değildir. Bir EXE ya da DLL COM sunucusu varsa, olarak paketini sürece, bir evrensel Windows projesi kullanabileceğiniz bir [Kayıtsız COM bileşeni](https://msdn.microsoft.com/library/dd408052.aspx), projenize bir içerik dosyası olarak ekleyin ve kullanarak örneği [ CoCreateInstanceFromApp](https://msdn.microsoft.com/library/windows/apps/hh404137.aspx). Bkz: [gerektirmeyen COM DLL Windows mağazası C++ projesi kullanarak](http://blogs.msdn.com/b/win8devsupport/archive/2013/05/20/using-free-com-dll-in-windows-store-c-project.aspx).  
  
 Evrensel Windows platformu bağlantı noktasına istediğiniz var olan bir COM kitaplık varsa, kullanarak Windows çalışma zamanı bileşeni dönüştürebilir olabilir [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md). WRL ATL tüm özelliklerini desteklemez ve OLE, bu nedenle bu tür bir bağlantı noktası uygun olup COM kodunuzu com, ATL, hangi özelliklere ne kadar bağımlı bağlıdır ve OLE bileşeniniz gerektirir.  
  
 Mevcut C++ kodunu Evrensel Windows platformu projelerinde kullanabileceğiniz çeşitli şekillerde bunlar. Bazı yollarını bileşen uzantılarıyla derlenmesi için kod gerektirmeyen (C + +/ CX) etkin (diğer bir deyişle, /ZW ile seçenek) ve bazı standart C++'da kod saklamak veya Klasik bir Win32 derleme ortamı için bazı kod korumak gerekiyorsa, bunu yapabilirsiniz, bunun , ilgili mimarinize seçenekleriyle. Örneğin, tüm evrensel Windows platformu UI içeren kodu ve C#, Visual Basic ve JavaScript arayanlara açığa çıkarılması türleri Windows uygulaması projeleri ve Windows çalışma zamanı bileşeni projeler gerekir. C++'da yalnızca tüketilmesi gereken kod (dahil C + +/ CX) kod /WX seçeneği ile derlenen bir proje veya standart C++ projesi ya da olabilir. Yalnızca ikili kod içinde bir statik kitaplık bağlama tarafından kullanılan veya uygulama içeriği olarak paketlenir ve yalnızca yasaklanmış API'leri kullanmıyorsa DLL yükleniyor.  
  
 Seçtiğiniz bu geliştirme senaryolarından hangisinin bağımsız olarak, kodunuzda kullanabilirsiniz ve böylece kodu Klasik Masaüstü Win32 ve evrensel Windows platformu altında koşullu derleme makro tanımları sayısı haberdar olmanız gerekir.  
  
```cpp  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)  
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)  
```  
  
 Bu deyimler sırasıyla Windows mağazası uygulamaları, Windows Phone mağazası uygulamaları, hem veya hiçbiri (Klasik Win32 yalnızca Masaüstü) geçerli. Bu makroları yalnızca Windows 8.1 SDK ve daha sonra de durum, bunların hiçbiri dikkate almalısınız sonra Windows SDK veya diğer platformlar yanı sıra Windows, önceki sürümleriyle derlemek kodunuzu gerekiyorsa tanımlanan şekilde kullanılabilir.  
  
 Bu konu aşağıdaki yordamları içerir.  
  
1.  [Win32 kullanarak bir evrensel Windows platformu uygulamasında DLL](#BK_Win32DLL)  
  
2.  [C++ yerel bir statik kitaplık bir UWP uygulamasında kullanma](#BK_StaticLib)  
  
3.  [Windows çalışma zamanı bileşeni C++ kitaplığına bağlantı noktası oluşturma](#BK_WinRTComponent)  
  
##  <a name="BK_Win32DLL"></a>Win32 kullanarak bir evrensel Windows platformu uygulamasında DLL  
 Klasik Windows masaüstü uygulamasında olduğu gibi yalnızca herhangi bir yerel DLL kullanamazlar daha iyi güvenlik ve güvenilirlik için evrensel Windows uygulamaları kısıtlı çalışma zamanı ortamında çalıştırın. Bir DLL için kaynak kodu varsa, böylece UWP üzerinde çalışan kod bağlantı noktası. Birkaç proje ayarları ve proje dosya meta verileri projesi olarak UWP projesini belirlemek için değiştirerek başlatın. C + etkinleştirir /ZW seçeneğini kullanarak kitaplık Kodu derlemek ihtiyacınız +/ CX. Bu ortam ile ilgili katı denetimleri nedeniyle UWP uygulamalarında belirli API çağrılarına izin verilmiyor. Bkz: [Win32 ve COM Windows çalışma zamanı için uygulamaları ve evrensel Windows Platformu (UWP) uygulamaları](https://msdn.microsoft.com/library/windows/apps/br205757.aspx).  
  
 Aşağıdaki yordam __declspec(dllexport) kullanarak işlevleri sunan yerel bir DLL sahip olduğu durum için geçerlidir.  
  
#### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>Bağlantı noktası için yeni bir proje oluşturmadan UWP yerel DLL'i  
  
1.  __Declspec(dllexport) kullanarak işlevlerini dışarı aktarıp yerel bir DLL varsa, bu işlevlerin bir UWP uygulamasını DLL UWP projesi olarak derleyerek çağırabilirsiniz. Örneğin, sınıflar ve onların yöntemleriyle kod aşağıdaki üstbilgi dosyası gibi çeşitli aktaran DLL sahibiz varsayın:  
  
    ```  
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
  
    ```  
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
  
     Proje (stdafx.h, DllMain.cpp'yi) bir şey standart Win32 Proje şablonu bir parçasıdır. İzlemek istediğiniz, ancak kendi DLL henüz bu adımlarla kullanmak istemiyorsanız, Win32 Proje oluşturmayı deneyin, DLL projesi Sihirbazı'nda seçin ve ardından bir üstbilgi dosyası giraffe.h ve kod dosyası giraffe.cpp ekleyin ve bu adımı uygulamada kodda içeriğini kopyalayın ropriate dosyaları.  
  
     Kod, __declspec(dllexport) için çözümlenen GIRAFFE_API makrosu tanımlar zaman _DLL tanımlanır (diğer bir deyişle, proje DLL olarak yapılandırıldığında).  
  
2.  DLL projesi için proje özelliklerini açın ve yapılandırmayı ayarlamak **tüm yapılandırmaları**.  
  
3.  Proje Özellikleri'nde altında **C/C++**, **genel** sekmesinde, ayarlamak **tüketen Windows çalışma zamanı uzantısı** için **Evet (/ZW)**. Bu bileşen uzantıları sağlar (C + +/ CX).  
  
4.  İçinde **Çözüm Gezgini**, proje düğümüne seçin, kısayol menüsünü açın ve belirtin **projeyi**. Ardından, bellekten proje düğümüne kısayol menüsünü açın ve proje dosyasını düzenlemek seçin. WindowsTargetPlatformVersion öğesini bulun ve aşağıdaki öğeleri ile değiştirin.  
  
    ```xml  
    <AppContainerApplication>true</AppContainerApplication>  
    <ApplicationType>Windows Store</ApplicationType>  
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>  
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>  
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>  
    ```  
  
     .Vcxproj dosyayı kapatın, kısayol menüsünün yeniden açın ve seçin **projeyi yeniden yükle**.  
  
     Çözüm Gezgini proje Evrensel Windows projesi olarak şimdi tanımlar.  
  
5.  Önceden derlenmiş üst bilgi dosya adının doğru olduğundan emin olun. Önceden derlenmiş üstbilgiler bölümünde önceden derlenmiş üstbilgi dosyası için stdafx.h pch.h değiştirin. Bunu yapmazsanız, aşağıdaki hatayı görürsünüz.  
  
    ```Output  
    error C2857: '#include' statement specified with the /Ycpch.h command-line option was not found in the source file  
    ```  
  
     Evrensel Windows projeleri için önceden derlenmiş üst bilgi dosyasını farklı bir adlandırma kuralı kullanmak sorunudur.  
  
6.  Projeyi oluşturun. Uyumsuz komut satırı seçenekleri hakkında bazı hatalar alabilirsiniz. Örneğin, sık kullanılan en az yeniden etkinleştirme seçeneği (/ Gm) birçok C++ projelerine varsayılan olarak ayarlanır ve /ZW ile uyumlu değil.  
  
     Evrensel Windows platformu için derleme yaparken bazı işlevler kullanılamaz. Derleyici hataları sorunlarla ilgili görürsünüz. Temiz bir yapı elde edene kadar bu adresi.  
  
7.  DLL aynı çözüme UWP uygulamasında kullanmak için UWP projesi düğümünü için kısayol menüsünü açın ve seçin **eklemek için başvuru**.  
  
     Altında **projeleri, çözüm**, DLL projesi yanındaki onay kutusunu seçin ve **Tamam** düğmesi.  
  
8.  Kitaplık üstbilgi dosyaları UWP uygulamanızın pch.h dosyasına ekleyin.  
  
    ```  
    #include "..\MyNativeDLL\giraffe.h"  
    ```  
  
9. Kodu her zamanki gibi işlevleri çağırmak ve DLL'den türleri oluşturmak için UWP projesi ekleyin.  
  
    ```  
    MainPage::MainPage()  
    {  
        InitializeComponent();  
        GiraffeFactory gf;  
        Giraffe* g = gf.Create();  
        int id = g->GetID();  
    }  
  
    ```  
  
##  <a name="BK_StaticLib"></a>C++ yerel bir statik kitaplık bir UWP uygulamasında kullanma  
 UWP projesini yerel C++ statik kitaplığa kullanabilirsiniz, ancak bazı kısıtlamalar ve dikkat edilmesi gereken sınırlamalar vardır. Başlat bu okuyarak [konu](https://msdn.microsoft.com/library/hh771041.aspx) hakkında statik kitaplıklarda C + +/ CX. Yerel kod UWP uygulamanızdan statik kitaplığınızda erişebilirsiniz, ancak bu ortak ref türler içinde statik kitaplık oluşturma önerilmez. Bir statik kitaplık /ZW seçeneğiyle derleme varsa, (gerçekten gizlenmiş bağlayıcı) kitaplığı sizi uyarır:  
  
```  
LNK4264: archiving object file compiled with /ZW into a static library; note that when authoring Windows Runtime types it is not recommended to link with a static library that contains Windows Runtime metadata  
```  
  
 Ancak, bir UWP statik kitaplığa /ZW ile derlemeden kullanabilirsiniz. Ref türlerinizi veya C + kullanan açamazsınız +/ CX oluşturur, sonra da aşağıdaki adımları izleyerek yapabilirsiniz ancak amacınıza yalnızca yerel kod kitaplığı kullanmak için olup olmadığını.  
  
#### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>UWP projesini yerel C++ statik kitaplığa kullanmak için  
  
1.  Bağlayıcı bölümünde, UWP projesi için Proje Özellikleri'nde giriş özellik kitaplığına yolunu ekleyin. Örneğin, kendi çıktısında yerleştirir proje kitaplığında *SolutionFolder*\Debug\MyNativeLibrary\MyNativeLibrary.lib, göreli yol eklemek `Debug\MyNativeLibrary\MyNativeLibrary.lib`.  
  
2.  UWP projesinde, pch.h üstbilgi dosyasına başvuru ve kitaplık kullanan kodu eklemeye başlamak için bir ekleme deyimi ekleyin.  
  
    ```  
    #include "..\MyNativeLibrary\giraffe.h"  
    ```  
  
     Başvuru eklemeyin **başvuruları** düğümünde **Çözüm Gezgini**. Bu mekanizma, yalnızca Windows çalışma zamanı bileşenleri için çalışır.  
  
##  <a name="BK_WinRTComponent"></a>Windows çalışma zamanı bileşeni C++ kitaplığına bağlantı noktası oluşturma  
 Bir UWP uygulaması statik bir kitaplıktan yerel API'leri kullanmak istediğiniz ve yerel kitaplığı için kaynak kodu varsa, Windows çalışma zamanı bileşeni koda bağlantı noktası. Bir statik kitaplık artık olmayacaktır, DLL olacaktır. Tüm C++ UWP uygulamasında kullanabilirsiniz, ancak statik kitaplık durumda, ref türleri ve diğer C + ekleyebilirsiniz +/ dil bağımsız olarak tüm UWP uygulama kodu istemciler için kullanılabilir olan CX yapıları. Bu nedenle, bu tür C#, Visual Basic veya JavaScript aracılığıyla erişebilirsiniz.  Temel Windows çalışma zamanı bileşeni projesi oluşturun, statik kitaplığınızın kodunu buraya kopyalayın ve kod /ZW derleme için standart bir C++ derlemeden taşınmasını ortaya çıkan hataları çözmek için bir yordamdır.  
  
#### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>Windows çalışma zamanı bileşeni C++ kitaplığına bağlantı noktası  
  
1.  Windows çalışma zamanı bileşeni projesi oluşturun.  
  
2.  Projeyi kapatın.  
  
3.  Windows dosya Gezgini'nde, proje bulun. Varsayılan olarak, Visual Studio, Visual Studio 2017\Projects klasörü Belgeler klasörünüzde kullanır. Bağlantı noktasına istediğiniz kodu içeren C++ Kitaplık projesinin bulun. C++ Kitaplık projenizden (üst bilgi dosyaları, kod dosyaları ve dizinlerde de dahil olmak üzere başka bir kaynağı) kaynak dosyaları kopyalayın ve bunları aynı klasör yapısını korumak emin proje klasörüne yapıştırın.  
  
4.  Windows çalışma zamanı bileşeni projeyi yeniden açın ve proje düğümünün kısayol menüsünü açın **Çözüm Gezgini**ve seçin **Ekle, var olan öğeyi**.  
  
5.  Özgün projenize eklemek için tüm dosyaları seçin ve Tamam'ı seçin. Gerekirse, alt klasörler için yineleyin.  
  
6.  Şimdi bazı kod Çoğalttığınız. Birden fazla önceden derlenmiş üst bilgi (deyin stdafx.h ve pch.h) varsa, tutmak için seçin. Gibi deyime tutma bir içeriyor, tüm gerekli kodu kopyalayın. Daha sonra diğer ve proje özelliklerini altında silin **önceden derlenmiş üstbilgiler**, üstbilgi dosyası adının doğru olduğundan emin olun.  
  
     Önceden derlenmiş üst bilgi kullanılacak dosyasını değiştirdiyseniz, önceden derlenmiş başlık seçeneklerini her dosya için doğru olduğundan emin olun. Her .cpp dosya sırayla seçin, Özellikler penceresini açın ve tüm ayarlandığından emin olun **kullanın (/Yu)**, istenen önceden derlenmiş üstbilgi dışında hangi ayarlanmalıdır **oluştur (/Yc)**.  
  
7.  Projeyi derlemek ve varsa hataları çözümleyin. /ZW seçeneğini kullanarak bu hatalarına neden veya Windows SDK'sı, yeni bir sürümü ile kaynaklanabilir veya kitaplığınızın bağlı başlık dosyaları veya eski projenizi ve yeni o arasındaki farklar proje ayarlarında gibi bağımlılıkları gösterebilir ne.  
  
8.  Ortak ref türleri projenize ekleyin veya ref türleri, UWP uygulamaları aramak istediğiniz işlevselliği içine giriş noktalarını göstermek için sıradan türleri Dönüştür.  
  
9. Bileşen bir UWP uygulaması projesi kendisine bir başvuru ekleyerek test ve oluşturduğunuz ortak API'leri çağırmak için bazı kod ekleyin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Evrensel Windows Platformu'na bağlantı noktası oluşturma](../porting/porting-to-the-universal-windows-platform-cpp.md)