---
title: C++'ta Windows programlamasına genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a8705f6c1ed1030f1beeb7c2302f0d629c5d17d
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012199"
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

Bir Windows server, Bulut veya Xbox üzerinde birçok türde bir Windows PC (x 86, x64 veya ARM) üzerinde çalışan programları yazmak için Visual C++ kullanabilirsiniz. İyi yazılmış C++ programları şu niteliklere sahip:
- verimli bellek gereksinimleri
- güç tüketiminde ekonomiktir 
- birden fazla çekirdekli ve çok çekirdekli cihazlar tam olarak yararlanmak kullanabilirsiniz
- Genel üzerindeki grafik işlemci birimi (GPGPU) bilgi işlem yapmak kullanabilirsiniz   
- Donanım diğer son gelişmelerden yararlanmak kullanabilirsiniz.

Visual C++ ile geliştirdiğiniz Windows uygulamaları birkaç kategoriden vardır. Bu kategoriler, farklı programlama modelleri veya yıllar içinde kullanıma sunulan uygulama modelleri sahip. Her model, pencereler ve iletişim kutuları gibi kullanıcı arabirimleri oluşturun ve platforma erişim sağlamak için farklı kitaplıklarını ve API'lerini kullanır. C++ Standart Kitaplığı yanı sıra üçüncü taraf kitaplıkların UWP için bazı kısıtlamalar ile aşağıdaki kategorilerden herhangi birine içinde kullanılabilir.

- [Windows Evrensel uygulamaları](#BK_WindowsUniversal). Üçüncü kategori Windows uygulamalarını Windows 8 ile kullanıma sunulmuştur ve bu kategoriyi uygulama için destek Windows 10'da devam eder. Bu uygulamaları sık "Windows uygulamaları" olarak adlandırılır ve çeşitli cihazları hedefleyen Masaüstü ve mobil uygulamaları içerirler. Bu uygulamaları C + yazabileceğiniz +/ CX, bir Windows çalışma zamanı geliştirme veya standart C++ ile Windows çalışma zamanı kitaplığı (WRL) kullanarak COM desteği içeren C++ SQL diyalektiği. Bu uygulamaları Windows 10'da kullanıcılar bunları masaüstü penceresinde çalışan seçeneğiniz vardır. ancak tam ekran, çalıştırılacak üzere tasarlanmıştır. Bu uygulamalar, dokunma odaklı, ancak kullanıcıların tercih ederseniz veya dokunmatik ekran kullanılabilir değilse, çalışılacak fare kullanmak daha kolaydır. Bu uygulamalar Microsoft Store, bunları "Store" uygulamaları çağrılan sonuçlanan bir olgu üzerinden dağıtılır.

UWP uygulamaları, tabletler ve cep telefonları gibi tüm Windows 10 cihazlarında yanı sıra Masaüstü çalıştırabilir. Bir masaüstü pencere olarak çalıştırılabilmesi için masaüstünde yerine her zaman tam ekran çalışıyor. Bu uygulamalar, Xbox ve gelecekteki cihazlarda da çalıştırabilirsiniz.  UWP uygulamaları kullanıcı arabirimi öğeleri, hizmetleri ve Windows üzerinde desteklenen çeşitli donanım aygıtları için bir arabirim sağlayan Windows Runtime çalıştırın.  

UWP uygulamaları C + yazabileceğiniz +/ CX, C++, bir SQL diyalektiği kullanabileceğiniz [C + +/ WinRT Kitaplığı](https://moderncpp.com/)bazı senaryolar için. UWP uygulamaları için yerel kod derleme ve XAML kullanıcı arabirimine sahip ya da DirectX kullanın. UWP uygulamaları diğer dillerde yazılmış tüketebileceği yerel kod halinde yazılmış Windows çalışma zamanı bileşenleri. Daha fazla bilgi için [c++'ta bir evrensel Windows platformu uygulaması oluşturma](http://go.microsoft.com/fwlink/?LinkID=534976), [DirectX kullanarak ilk UWP oyununuzu oluşturun](http://go.microsoft.com/fwlink/p/?LinkId=244656), ve [C++'ta Windows çalışma zamanı oluşturma bileşenleri](http://go.microsoft.com/fwlink/p/?LinkId=244658).

   Bu kategori, C++ temel bileşenleri ve sunucu ve bulut programlama bağlamındaki hesaplama kodu kullanarak da içerir. Bazen yoğun performans kod merkezinde bulunan bir sunucu veya Bulut uygulama performansını en üst düzeye c++'ta yazılır. Bu kod bir DLL içine derleyin ve C# veya Visual Basic kullanın.

- **.NET framework uygulamaları**. Çoğu .NET Framework uygulamaları, C# veya Visual Basic'te yazılır, ancak ayrıca C + +/ CLI ( `/clr` Visual c++ derleyici seçeneği). Öneririz kullanarak C + +/ CLI yönetilen ve yerel kodu içeren büyük bir uygulamanın en az bir birlikte çalışma katmanı için.

##  <a name="BK_WindowsUniversal"></a> Evrensel Windows uygulamaları

Windows 10 ile uygulamaları, tabletler ve cep telefonları gibi tüm Windows 10 cihazlarında yanı sıra Masaüstü çalıştırabilir. Bir masaüstü pencere olarak çalıştırılabilmesi için masaüstünde yerine her zaman tam ekran çalışıyor. Bu uygulamalar, Xbox ve gelecekteki cihazlarda da çalıştırabilirsiniz.  İki tür uygulamaları için programlama modeli, Win32 Masaüstü uygulamalardan farklıdır. Bu Windows uygulamaları farklı donanım cihazlarının desteklenen Windows kullanıcı arabirimi öğeleri, bu uygulamalar için hayati hizmetler sağlayan ve sağlar, çalışma zamanı ve bir arabirim çalıştırın. Bu uygulamalar için yerel kod derleme ve XAML kullanıcı arabirimine sahip ya da DirectX kullanın. Windows çalışma zamanı bileşenleri diğer Windows uygulamaları kullanabileceği yerel kod halinde yazabilirsiniz; bunlar, C#, Visual Basic veya JavaScript içinde yazılmış uygulamalar içerir. Daha fazla bilgi için [C++ UWP "Hello world" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp), [DirectX ile basit bir UWP oyunu oluşturma](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game), ve [C++'ta Windows çalışma zamanı oluşturma bileşenleri](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

> [!TIP]
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için var olan masaüstü uygulamanızı paketlemek için Masaüstü uygulamasını dönüştürücüyü kullanabilirsiniz. Daha fazla bilgi için [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile masaüstü uygulamanızı taşıyın](https://msdn.microsoft.com/windows/uwp/porting/desktop-to-uwp-root).

Evrensel Windows platformu örnekleri için bkz [Windows Evrensel Samples github'da](https://github.com/Microsoft/Windows-universal-samples)

Var olan bir proje Windows 8.1 ve Windows 10'a bağlantı istiyorsanız, bkz: [Evrensel Windows Platformu'na](../porting/porting-to-the-universal-windows-platform-cpp.md). Çalıştırıyorsanız, varolan Klasik Win32 Masaüstü kitaplıkları ve bu kod, istediğiniz bir UWP uygulamasıyla tümleştirmek için bkz: [nasıl yapılır: mevcut C++ kodunu Evrensel Windows platformu uygulamasında kullanma](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

Genel olarak, UWP hakkında daha fazla bilgi için bkz [bir evrensel Windows Platformu (UWP) uygulaması nedir?](/windows/uwp/get-started/whats-a-uwp).

Tüm Bu kavramlar hakkında daha fazla bilgi almak için bkz. [Evrensel Windows uygulamaları Kılavuzu](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Masaüstü ve sunucu uygulamaları

Masaüstü için Windows istemci uygulamaları yazmanın temellerini öğrenmek için bkz. [C++'ta Windows uygulamaları geliştirme](http://msdn.microsoft.com/vstudio//hh304489) ve [C++'ta Windows programlamaya giriş](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx).

Windows 10'da, pek çok masaüstü programları oluşturmak için Visual C++ kullanabilirsiniz:

- Komut satırı uygulamaları ve yardımcı programları. Daha fazla bilgi için [konsol uygulamaları](../windows/console-applications-in-visual-cpp.md).

- Gelişmiş grafik kullanıcı arabirimleri olan tüketici uygulamaları. Daha fazla bilgi için [Hilo: için C++ uygulamaları Windows geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=256417)

- .NET Framework üzerinde çalışan Enterprise ve satır iş kolu uygulamaları. Çoğu .NET Framework uygulamaları, C# veya Visual Basic'te yazılır. Kullanabileceğiniz C + +/ CLI .NET kodu yerel C++ kitaplıkları kullanmasını sağlayan birlikte çalışma katmanı oluşturmak için. Daha fazla bilgi için [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- Yerel kod halinde çalışan SQL veritabanı istemcileri. Daha fazla bilgi için [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

- Microsoft Office uygulamaları için eklentiler. Daha fazla bilgi için [Outlook 2010 bir C++ eklentisi oluşturma](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Aygıt sürücüleri. Daha fazla bilgi için [Windows Sürücü Seti'nin (WDK)](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Windows hizmetleri. Daha fazla bilgi için [Windows hizmeti uygulamalarına giriş](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

C++ uygulamaları veya diğer dillerde (örneğin, C# veya Visual Basic) yazılmış uygulamalar tarafından kullanılabilen Win32 DLL'leri veya COM DLL'leri içindeki özel yüksek performanslı işlevselliğin hemen her türünü paketlemek için Visual C++ kullanabilirsiniz. WIn32 DLL'leri hakkında daha fazla bilgi için bkz: [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md). COM geliştirme hakkında daha fazla bilgi için bkz. [Bileşen Nesne Modeli (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="games"></a>Oyunlar

DirectX oyunları, PC veya Xbox üzerinde çalıştırabilirsiniz. Daha fazla bilgi için [DirectX Geliştirici Merkezi](http://go.microsoft.com/fwlink/p/?LinkId=256418).

## <a name="sdks-libraries-and-header-files"></a>SDK'lar, kitaplıklar ve üst bilgi dosyaları

Visual C++, C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı ve Microsoft'a özel diğer kitaplıkları içerir. Bu kitaplıklara ilişkin üst bilgi dosyaları içeren içerme klasörleri ya da Visual Studio yükleme dizininde \VC\ klasörünün altında ya da söz konusu olduğunda Windows SDK'sını yükleme klasöründeki CRT yer alır.   

Kullanabileceğiniz [Vcpkg Paket Yöneticisi](../vcpkg.md) Windows için üçüncü taraf açık kaynak kitaplıkları yüzlerce rahatça yüklenecek.

Microsoft kitaplıkları şunları içerir:

- Microsoft Foundation Classes (MFC): Geleneksel Windows programları ve özellikle de düğmeler, liste kutuları, ağaç görünümleri ve diğer denetimleri barındıran zengin kullanıcı arabirimlerine sahip kurumsal uygulamalar oluşturmaya yönelik nesne yönelimli bir çerçevedir. Daha fazla bilgi için [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md).

- Etkin Şablon Kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplık. Daha fazla bilgi için [ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): GPU üzerinde yüksek performanslı genel hesaplama işlerini etkinleştiren bir kitaplık. Daha fazla bilgi için [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Birden fazla çekirdekli ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama işini basitleştiren bir kitaplık. Daha fazla bilgi için [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Varsayılan olarak, Visual Studio, Windows SDK'sı bir evrensel Windows uygulama geliştirmeyi sağlayan C++ Masaüstü iş yükü bileşeni olarak yükler. UWP uygulamaları geliştirme için Windows SDK'sının Windows 10 sürümü gerekir. Bilgi için [Windows 10 SDK'sı](https://dev.windows.com/downloads/windows-10-sdk). (Windows, önceki sürümler için Windows SDK'ları hakkında daha fazla bilgi için bkz. [Windows SDK arşivi](https://developer.microsoft.com/windows/downloads/sdk-archive)). 

**Program dosyaları (x86) \Windows Setleri** yüklü olduğu Windows SDK'ın tüm sürümleri için varsayılan konum için.

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için [Visual Studio ile geliştirmeye başlayın](/visualstudio/ide/get-started-developing-with-visual-studio), ve [geliştirme araçları ve IDE](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C++ Geliştirici içeriği için üst konu.|