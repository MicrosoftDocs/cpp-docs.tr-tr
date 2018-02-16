---
title: "C++'da Windows programlamasına genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b204783e3b2c418e5e719ca5c6efcf9c2d31c6df
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

Bulut veya Xbox, Windows Server, Windows PC (x86, x64 veya ARM) üzerinde çalışan çeşitli programlar yazmak için Visual C++ kullanabilirsiniz. İyi yazılmış C++ programları, hızlıdır, verimlidir, güç tüketiminde ekonomiktir ve birden fazla çekirdekli ve çok çekirdekli cihazlardan, grafik işlemci birimine dayalı genel bilgiişlemden (GPGPU) ve donanımdaki diğer son gelişmelerden en iyi şekilde yararlanabilir.

Visual C++ ile geliştirebilirsiniz Windows uygulamaları birkaç geniş kategorisi vardır. Bu kategoriler farklı programlama modelleri ya da farklı kitaplıkları ve platform erişim sağlar ve kullanıcı arabirimi API'lerini kullandığını anlamına gelir uygulama modelleri vardır.

- [Windows Evrensel uygulamaları](#BK_WindowsUniversal). Windows uygulamaları üçüncü kategorisini Windows 8 ile sunulan ve uygulamaların bu kategori için destek Windows 10'da devam eder. Bu uygulamaları sık "Windows uygulamalar" olarak adlandırılır ve çeşitli aygıtlardan hedef Masaüstü ve mobil uygulamaları içerir. Bu uygulamaları C + yazabileceğiniz +/ CX, Windows çalışma zamanı geliştirme ya da Windows çalışma zamanı kitaplığı (WRL) kullanarak COM ile standart c++ desteğiyle C++ diyalekti. Bu uygulamaları, ilk olarak Windows 10 masaüstü penceresinde çalıştırma seçeneğini kullanıcınız rağmen tam ekran çalıştırmak için tasarlanmıştır. Bu uygulamaları dokunmalı, ancak kullanıcıların tercih ederseniz veya dokunmatik ekran kullanılamıyorsa çalışmak üzere fareyi kullanmasını kolaydır. Bu uygulamalar, "Depo" uygulamaları çağrılan bunları sonuçlanan bir olgu Microsoft Store aracılığıyla dağıtılır.

- [Masaüstü, sunucu ve bulut uygulamaları ve oyunları](#BK_Native). Bu kategorideki tüm Windows uygulamalarını olan, Windows Masaüstü uygulamaları, Win32 uygulamaları olarak da adlandırılan bu uygulamaları Win32 API önce Windows 8 kullanarak sonra bu kategorisi içerir. Bu kategorideki uygulamalar, bir kullanıcı arabirimi için MFC ve ATL COM nesneleri genellikle olan Windows bileşenleri ile etkileşim kurmak için kullanabilirsiniz.

   Uygulamalar, bileşenler veya standart C++ ile yazılmış kitaplıkları da bu kategoriye uygun.

   Bu kategori, çekirdek bileşenleri ve sunucu ve bulut programlama bağlamındaki hesaplama kodu C++ kullanarak de içerir. Bazen bir sunucu veya Bulut uygulaması'nın performansı yoğun kodu C++'da performansı en üst düzeye çıkarmak için yazılır. Bir DLL'e böyle Kodu derlemek ve C# veya Visual Basic kullanın.

- **.NET framework uygulamaları**. Çoğu .NET Framework uygulamaları C# veya Visual Basic ile yazılmış, ancak aşağıdakileri de yapabilirsiniz C + +/ CLI (Visual c++/CLR derleyici seçeneği). Öneririz kullanarak C + +/ CLI yönetilen ve yerel kodu içeren daha büyük bir uygulamanın en az bir birlikte çalışma katmanda için.

##  <a name="BK_WindowsUniversal"></a> Windows Evrensel uygulamaları

Windows 10 ile uygulamaları tabletleri ve telefonları gibi tüm Windows 10 cihazlarda yanı sıra masaüstünde çalıştırabilir. Masaüstü bir pencere olarak çalıştırılabilmesi için masaüstünde yerine her zaman tam ekran çalışıyor. Bu uygulamalar, Xbox ve gelecekteki aygıtlarda de çalıştırabilirsiniz.  İki tür uygulamaları için programlama modelini Win32 Masaüstü uygulamalardan farklıdır. Bu Windows uygulamaları Windows kullanıcı arabirimi öğeleri, bu uygulamalar için temel hizmetleri sağlayan ve sağlar, çalışma zamanı ve bir arabirim desteklenen farklı donanım aygıtları için çalışır. Bu uygulamaları için yerel kodu derleme ve XAML kullanıcı arabirimi olan ya da DirectX kullanın. Windows çalışma zamanı bileşenleri diğer Windows uygulamalarını tüketebileceği yerel kodda yazabilirsiniz — bunlar, C#, Visual Basic veya JavaScript içinde yazılmış uygulamalar içerir. Daha fazla bilgi için bkz: [C++'da bir UWP "Hello world" uygulaması oluşturma](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp), [DirectX ile basit UWP oyun oluşturmak](/windows/uwp/gaming/tutorial--create-your-first-uwp-directx-game), ve [oluşturma Windows çalışma zamanı bileşenleri c++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

> [!TIP]
> Windows 10 için Microsoft Store aracılığıyla dağıtımı için varolan Masaüstü uygulamanız paketlemek için masaüstü uygulaması dönüştürücü kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) ve [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Evrensel Windows platformu örnekler için bkz: [github'da Windows Evrensel örnekleri](https://github.com/Microsoft/Windows-universal-samples)

Var olan bir Windows 8.1 proje ve istediğiniz Windows 10 için bağlantı noktası varsa, bkz: [Evrensel Windows Platformu'na bağlantı noktası oluşturma](../porting/porting-to-the-universal-windows-platform-cpp.md). Varolan Klasik Win32 Masaüstü kitaplıkları varsa ve bu kod, istediğiniz bir UWP uygulamanıza tümleştirmek için bkz: [nasıl yapılır: kullanım mevcut C++ kodunu Evrensel Windows platformu uygulamasında](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

C + kullanmadan Evrensel Windows uygulamaları, oyun ve bileşenleri de yazabilirsiniz +/ CX; Bunun yerine, Windows çalışma zamanı C++ Şablon kitaplığı (Windows çalışma zamanı C++ Şablon kitaplığı) kullanabilirsiniz. Daha fazla bilgi için bkz: [Windows çalışma zamanı C++ Şablon kitaplığı (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

İle [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], Windows 10 Masaüstü ve mobil cihaz çalıştırmak Evrensel Windows uygulamaları geliştirebilirsiniz. Windows 8.1 uygulamaları ve Windows Phone 8.1 uygulamaları geliştirme yapabilirsiniz [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], ancak bunu yapmak için önce Visual Studio 2013 aynı bilgisayara yüklemeniz ve ardından projenizi kullanmak için yapılandırmanız gerekir **Visual Studio 2013 (v120)** araç takımı . Projenizde bu ayarı yapılandırmak için Proje Özellikleri'ni açın ve **genel** bölümünde, **Platform araç takımı** için **Visual Studio 2013 (v120)**.

Visual Studio kurulumunda Phone 8.0 araçlarını yüklüyorsanız, ayrıca Windows Phone 8.0 hedefleyebilirsiniz.

Windows API sözleşmeleri adlı 10'da sunulan yeni bir kavram, belirli Windows sürümlerini hedefleyen eski uygulama olarak değiştirir. Bunun yerine, uygulamanızın hangi API sözleşmelerinin seçebilirsiniz gereksinimleri ve bunu çalıştırır bu sözleşmeleri destekleyen herhangi bir Windows cihazda. Bir API sözleşme, platform veya cihazlar kaynağa erişim sağlayabildiği kararlı API kümesidir. API sözleşmeleri proje sistemde başvuru olarak dahil edilebilir. Belirli bir uzantı SDK başvuru eklerseniz, bir Visual Studio projesi uygun API sözleşmeleri sonra Visual Studio ekler.

Tüm bu kavramları daha fazla bilgi için bkz: [Windows Evrensel uygulamaları için kılavuz](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Masaüstü, sunucu ve bulut uygulamaları ve oyunları

Bulutta Azure yerel kod derlemeleri C++ ile yazma ve bunlara C# ' de oluşturulan Web rollerden çağırın. Daha fazla bilgi için bkz: [Azure SDK'sı](http://go.microsoft.com/fwlink/p/?LinkId=256416).

Masaüstü için Windows istemci uygulamaları yazma temel bilgileri öğrenmek için bkz: [Windows uygulamalarında geliştirme C++](http://msdn.microsoft.com/vstudio//hh304489) ve [Windows programlama c++ giriş](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx).

Windows 10'program birçok türleri oluşturmak için Visual C++ kullanabilirsiniz:

- Komut satırı uygulamaları ve yardımcı programları. Daha fazla bilgi için bkz: [konsol uygulamaları](../windows/console-applications-in-visual-cpp.md).

- PC veya Xbox üzerinde çalışan DirectX Oyunları. Daha fazla bilgi için bkz: [DirectX Geliştirici Merkezi](http://go.microsoft.com/fwlink/p/?LinkId=256418).

- Gelişmiş grafik kullanıcı arabirimleri olan tüketici uygulamaları. Daha fazla bilgi için bkz: [Hilo: için C++ uygulamaları Windows geliştirme](http://go.microsoft.com/fwlink/p/?LinkId=256417)

- .NET Framework üzerinde çalışan veya .NET Framework uygulamaları ile yerel kod halinde yazılmış uygulama ve bileşenler arasında bir köprü görevi gören kurumsal uygulamalar ve iş kolu uygulamaları. Daha fazla bilgi için bkz: [.NET programlama ile C + +/ CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- Yerel kod halinde çalışan SQL veritabanı istemcileri. Daha fazla bilgi için bkz: [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419).

- Microsoft Office uygulamaları için eklentiler. Daha fazla bilgi için bkz: [Outlook 2010 bir C++ eklentisi oluşturma](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Aygıt sürücüleri. Daha fazla bilgi için bkz: [Windows Sürücü Seti (WDK)](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Windows hizmetleri. Daha fazla bilgi için bkz: [Windows hizmet uygulamalarına giriş](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

C++ uygulamaları veya diğer dillerde (örneğin, C# veya Visual Basic) yazılmış uygulamalar tarafından kullanılabilen Win32 DLL'leri veya COM DLL'leri içindeki özel yüksek performanslı işlevselliğin hemen her türünü paketlemek için Visual C++ kullanabilirsiniz. WIn32 DLL'leri hakkında daha fazla bilgi için bkz: [DLL'leri Visual C++'ta](../build/dlls-in-visual-cpp.md). COM geliştirme hakkında daha fazla bilgi için bkz: [Bileşen Nesne Modeli (COM)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="sdks-and-header-files"></a>SDK'lar ve Üst Bilgi Dosyaları

Visual C++ C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı ve diğer Microsoft özgü kitaplıkları içerir. Bu kitaplıklar için üstbilgi dosyaları içeren Ekle ya da \VC\ klasörü altında veya CRT, Windows SDK yükleme klasörü, örneğin, Windows Kits\10 Program Files söz konusu olduğunda Visual Studio yükleme dizininde bulunan klasörlerdir Windows 10 SDK'sı için klasör.  Microsoft kitaplıkları içerir:

- Microsoft Foundation Classes (MFC): Geleneksel Windows programları ve özellikle de düğmeler, liste kutuları, ağaç görünümleri ve diğer denetimleri barındıran zengin kullanıcı arabirimlerine sahip kurumsal uygulamalar oluşturmaya yönelik nesne yönelimli bir çerçevedir. Daha fazla bilgi için bkz: [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md).

- Etkin Şablon Kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplık. Daha fazla bilgi için bkz: [ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): GPU üzerinde yüksek performanslı genel hesaplama işlerini etkinleştiren bir kitaplık. Daha fazla bilgi için bkz: [C++ AMP (C++ hızlandırılmış yoğun paralellik)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Birden fazla çekirdekli ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama işini basitleştiren bir kitaplık. Daha fazla bilgi için bkz: [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Varsayılan olarak, Evrensel Windows uygulamaları geliştirme sağlayan Windows SDK, Visual Studio yükler. Windows 10 için evrensel Windows uygulamaları geliştirmek için Windows SDK'sı Windows 10 sürümü gerekir. Windows 10 SDK'sı hakkında daha fazla bilgi için bkz: [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk). (Daha önceki Windows sürümleri için Windows SDK'ları hakkında daha fazla bilgi için bkz: [Windows SDK arşiv](https://developer.microsoft.com/windows/downloads/sdk-archive)).

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için bkz: [Visual Studio ile geliştirmeye başlamak](/visualstudio/ide/get-started-developing-with-visual-studio), ve [IDE ve geliştirme araçları](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C++ Geliştirici içerik için üst konu.|