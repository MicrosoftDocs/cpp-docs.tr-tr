---
title: C++'da Windows programlamasına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0e00159c828a87eba58920f90b6cd73d1b216232
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2018
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

Windows Server'da, bulutta ya da Xbox birçok türde (x 86, x64 veya ARM), bir Windows bilgisayarında çalışan programları yazmak için Visual C++ kullanabilirsiniz. İyi yazılmış C++ programları bu niteliklerini vardır:
- verimli bellek gereksinimleri
- güç tüketiminde ekonomik 
- çok çekirdekli ve çok çekirdekli aygıtların tam anlamıyla yararlanabilmek için
- Grafik işlem birimi (GPGPU'yu) hakkında genel bilgi işlem yapmak için   
- Donanım son diğer geliştirmeleri avantajlarından yararlanmak kullanabilirsiniz.

Visual C++ ile geliştirebilirsiniz Windows uygulamaları birkaç geniş kategorisi vardır. Bu kategoriler farklı programlama modelleri ya da yıllar içinde sunulan uygulama modelleri vardır. Her model platform erişim sağlar ve windows ve iletişim kutuları gibi kullanıcı arabirimleri oluşturmak için farklı kitaplıklarını ve API'lerini kullanır. C++ Standart Kitaplığı yanı sıra üçüncü taraf kitaplıklar, herhangi bir UWP için bazı kısıtlamalar ile Bu kategoriler kullanılabilir.

- [Windows Evrensel uygulamaları](#BK_WindowsUniversal). Windows uygulamaları üçüncü kategorisini Windows 8 ile sunulan ve uygulamaların bu kategori için destek Windows 10'da devam eder. Bu uygulamaları sık "Windows uygulamalar" olarak adlandırılır ve çeşitli aygıtlardan hedef Masaüstü ve mobil uygulamaları içerir. Bu uygulamaları C + yazabileceğiniz +/ CX, Windows çalışma zamanı geliştirme ya da Windows çalışma zamanı kitaplığı (WRL) kullanarak COM ile standart c++ desteğiyle C++ diyalekti. Bu uygulamaları, ilk olarak Windows 10 masaüstü penceresinde çalıştırma seçeneğini kullanıcınız rağmen tam ekran çalıştırmak için tasarlanmıştır. Bu uygulamaları dokunmalı, ancak kullanıcıların tercih ederseniz veya dokunmatik ekran kullanılamıyorsa çalışmak üzere fareyi kullanmasını kolaydır. Bu uygulamalar, "Depo" uygulamaları çağrılan bunları sonuçlanan bir olgu Microsoft Store aracılığıyla dağıtılır.

UWP uygulamaları tabletleri ve telefonları gibi tüm Windows 10 cihazlarda yanı sıra masaüstünde çalıştırabilir. Masaüstü bir pencere olarak çalıştırılabilmesi için masaüstünde yerine her zaman tam ekran çalışıyor. Bu uygulamalar, Xbox ve gelecekteki aygıtlarda de çalıştırabilirsiniz.  Kullanıcı arabirimi öğeleri, hizmetleri ve Windows'da desteklenen farklı donanım aygıtları için bir arabirim sağlayan Windows Runtime UWP uygulamaları çalıştırın.  

UWP uygulamaları C + yazabileceğiniz +/ CX, C++, diyalekti kullanabileceğiniz [C + +/ WinRT Kitaplığı](https://moderncpp.com/)bazı senaryolar için. UWP uygulamaları için yerel kodu derleme ve XAML kullanıcı arabirimi olan ya da DirectX kullanın. Yerel kodda diğer dillerde yazılmış UWP uygulamaları tüketebileceği yazılır Windows çalışma zamanı bileşenleri. Daha fazla bilgi için bkz: [C++'da bir evrensel Windows Platform uygulaması oluşturma](http://go.microsoft.com/fwlink/?LinkID=534976), [DirectX kullanarak ilk UWP oyununuzu oluşturma](http://go.microsoft.com/fwlink/p/?LinkId=244656), ve [oluşturma Windows çalışma zamanı bileşenleri c++](http://go.microsoft.com/fwlink/p/?LinkId=244658).

   Bu kategori, çekirdek bileşenleri ve sunucu ve bulut programlama bağlamındaki hesaplama kodu C++ kullanarak de içerir. Bazen bir sunucu veya Bulut uygulaması'nın performansı yoğun kodu C++'da performansı en üst düzeye çıkarmak için yazılır. Bir DLL'e böyle Kodu derlemek ve C# veya Visual Basic kullanın.

- **.NET framework uygulamaları**. Çoğu .NET Framework uygulamaları C# veya Visual Basic ile yazılmış, ancak aşağıdakileri de yapabilirsiniz C + +/ CLI (Visual c++/CLR derleyici seçeneği). Öneririz kullanarak C + +/ CLI yönetilen ve yerel kodu içeren daha büyük bir uygulamanın en az bir birlikte çalışma katmanda için.

##  <a name="BK_WindowsUniversal"></a> Windows Evrensel uygulamaları

Windows 10 ile uygulamaları tabletleri ve telefonları gibi tüm Windows 10 cihazlarda yanı sıra masaüstünde çalıştırabilir. Masaüstü bir pencere olarak çalıştırılabilmesi için masaüstünde yerine her zaman tam ekran çalışıyor. Bu uygulamalar, Xbox ve gelecekteki aygıtlarda de çalıştırabilirsiniz.  İki tür uygulamaları için programlama modelini Win32 Masaüstü uygulamalardan farklıdır. Bu Windows uygulamaları Windows kullanıcı arabirimi öğeleri, bu uygulamalar için temel hizmetleri sağlayan ve sağlar, çalışma zamanı ve bir arabirim desteklenen farklı donanım aygıtları için çalışır. Bu uygulamaları için yerel kodu derleme ve XAML kullanıcı arabirimi olan ya da DirectX kullanın. Windows çalışma zamanı bileşenleri diğer Windows uygulamalarını tüketebileceği yerel kodda yazabilirsiniz — bunlar, C#, Visual Basic veya JavaScript içinde yazılmış uygulamalar içerir. Daha fazla bilgi için bkz: [C++'da bir UWP "Hello world" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp), [DirectX ile basit UWP oyun oluşturmak](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game), ve [oluşturma Windows çalışma zamanı bileşenleri c++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

> [!TIP]
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için varolan Masaüstü uygulamanız paketlemek için masaüstü uygulaması dönüştürücü kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Evrensel Windows platformu örnekler için bkz: [github'da Windows Evrensel örnekleri](https://github.com/Microsoft/Windows-universal-samples)

Var olan bir Windows 8.1 proje ve istediğiniz Windows 10 için bağlantı noktası varsa, bkz: [Evrensel Windows Platformu'na bağlantı noktası oluşturma](../porting/porting-to-the-universal-windows-platform-cpp.md). Varolan Klasik Win32 Masaüstü kitaplıkları varsa ve bu kod, istediğiniz bir UWP uygulamanıza tümleştirmek için bkz: [nasıl yapılır: kullanım mevcut C++ kodunu Evrensel Windows platformu uygulamasında](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

Genel olarak, UWP hakkında daha fazla bilgi için bkz [bir evrensel Windows Platformu (UWP) uygulaması nedir?](/windows/uwp/get-started/whats-a-uwp).

Tüm bu kavramları daha fazla bilgi için bkz: [Windows Evrensel uygulamaları için kılavuz](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Masaüstü ve sunucu uygulamaları

Masaüstü için Windows istemci uygulamaları yazma temel bilgileri öğrenmek için bkz: [Windows uygulamalarında geliştirme C++](http://msdn.microsoft.com/vstudio//hh304489) ve [Windows programlama c++ giriş](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx).

Windows 10 Masaüstü programları birçok türde oluşturmak için Visual C++ kullanabilirsiniz:

- Komut satırı uygulamaları ve yardımcı programları. Daha fazla bilgi için bkz: [konsol uygulamaları](../windows/console-applications-in-visual-cpp.md).

- Gelişmiş grafik kullanıcı arabirimleri olan tüketici uygulamaları. Daha fazla bilgi için bkz: [Hilo: için C++ uygulamaları Windows geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=256417)

- .NET Framework üzerinde çalışan Enterprise ve business satır uygulamalar. Çoğu .NET Framework uygulamaları, C# veya Visual Basic yazılır. Kullanabileceğiniz C + +/ CLI yerel C++ kitaplıkları kullanmak .NET kodunun etkinleştirmek birlikte çalışma katmanlar oluşturun. Daha fazla bilgi için bkz: [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- Yerel kod halinde çalışan SQL veritabanı istemcileri. Daha fazla bilgi için bkz: [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

- Microsoft Office uygulamaları için eklentiler. Daha fazla bilgi için bkz: [Outlook 2010 bir C++ eklentisi oluşturma](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Aygıt sürücüleri. Daha fazla bilgi için bkz: [Windows Sürücü Seti (WDK)](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Windows hizmetleri. Daha fazla bilgi için bkz: [Windows hizmet uygulamalarına giriş](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

C++ uygulamaları veya diğer dillerde (örneğin, C# veya Visual Basic) yazılmış uygulamalar tarafından kullanılabilen Win32 DLL'leri veya COM DLL'leri içindeki özel yüksek performanslı işlevselliğin hemen her türünü paketlemek için Visual C++ kullanabilirsiniz. WIn32 DLL'leri hakkında daha fazla bilgi için bkz: [DLL'leri Visual C++'ta](../build/dlls-in-visual-cpp.md). COM geliştirme hakkında daha fazla bilgi için bkz: [Bileşen Nesne Modeli (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="games"></a>Oyunlar

DirectX oyunlar PC veya Xbox çalıştırabilirsiniz. Daha fazla bilgi için bkz: [DirectX Geliştirici Merkezi](http://go.microsoft.com/fwlink/p/?LinkId=256418).

## <a name="sdks-libraries-and-header-files"></a>SDK'lar, kitaplıklar ve başlık dosyaları

Visual C++ C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı ve diğer Microsoft özgü kitaplıkları içerir. Bu kitaplıklar için üstbilgi dosyaları içeren INCLUDE klasörlerin ya da Visual Studio yükleme dizininde \VC\ klasörü altında ya da Windows SDK yükleme klasöründeki CRT durumunda yer alır.   

Kullanabileceğiniz [Vcpkg Paket Yöneticisi](../vcpkg.md) rahat Windows için üçüncü taraf açık kaynak kitaplıkları yüzlerce yüklemek için.

Microsoft kitaplıkları içerir:

- Microsoft Foundation Classes (MFC): Geleneksel Windows programları ve özellikle de düğmeler, liste kutuları, ağaç görünümleri ve diğer denetimleri barındıran zengin kullanıcı arabirimlerine sahip kurumsal uygulamalar oluşturmaya yönelik nesne yönelimli bir çerçevedir. Daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md).

- Etkin Şablon Kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplık. Daha fazla bilgi için bkz: [ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): GPU üzerinde yüksek performanslı genel hesaplama işlerini etkinleştiren bir kitaplık. Daha fazla bilgi için bkz: [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Birden fazla çekirdekli ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama işini basitleştiren bir kitaplık. Daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Varsayılan olarak, Visual Studio Windows SDK'sı bir evrensel Windows uygulamaları geliştirmeye olanak tanır C++ Masaüstü iş yükü bileşeni olarak yüklenir. UWP uygulamaları geliştirmek için Windows SDK'sı Windows 10 sürümü gerekir. Bilgi için bkz: [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk). (Daha önceki Windows sürümleri için Windows SDK'ları hakkında daha fazla bilgi için bkz: [Windows SDK arşiv](https://developer.microsoft.com/windows/downloads/sdk-archive)). 

**Program dosyaları (x86) \Windows Setleri** yüklü olan Windows SDK'sı tüm sürümleri için varsayılan konumu.

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için bkz: [Visual Studio ile geliştirmeye başlamak](/visualstudio/ide/get-started-developing-with-visual-studio), ve [IDE ve geliştirme araçları](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C++ Geliştirici içerik için üst konu.|
