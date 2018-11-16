---
title: C++'da Windows Programlamasına Genel Bakış
ms.date: 11/15/2018
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: b33236df6e4c7f679ff1dd9f9f8bc409c86e011a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693870"
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

Windows uygulamalarının C++ ile oluşturabileceğiniz çeşitli geniş kategorisi vardır. Her biri kendi programlama modeli ve Windows özgü kitaplıklar kümesi vardır, ancak üçüncü taraf C++ kitaplıklarının yanı sıra C++ Standart Kitaplığı herhangi biri kullanılabilir. 

## <a name="command-line-console-applications"></a>Komut satırı (konsol) uygulamaları

C++ konsol uygulamaları, konsol penceresinde komut satırından çalıştırın ve yalnızca metin çıktısı görüntüleyebilirsiniz. Daha fazla bilgi için [konsol uygulamaları](console-applications-in-visual-cpp.md).
 
## <a name="native-desktop-client-applications"></a>Yerel masaüstü istemci uygulamaları

Terim *yerel masaüstü istemcisi uygulama* işletim sistemi erişmek için özgün Windows Win32 API kullanan bir C veya C++ pencereli uygulamaya başvurur. Bu API'leri kendilerini çoğunlukla c dilinde yazılmış olan Bu tür bir uygulama oluştururken, işletim sistemi olayları işleyen doğrudan bir C tarzı ileti döngüsü karşı programlama veya kullanma seçeneğiniz *Microsoft Foundation sınıfları* (MFC) Win32 sarmalayan bir C++ Kitaplığı biraz nesne yönelimli bir biçimde. Her iki yaklaşım "modern" Evrensel Windows Platformu (aşağıya bakın) kıyasla, ancak her ikisi de yine de tamamen desteklenen ve dünyanın hemen çalıştırma kod satırlarını milyonlarca sahip olarak kabul edilir.

Geleneksel Windows programlama C++ ile çalışmaya başlamak için bkz. [Win32 ve C++ ile çalışmaya başlama](/windows/desktop/LearnWin32/learn-to-program-for-windows). Win32'in bazı anlamak sonra hakkında bilgi edinmek daha kolay olacak [MFC Masaüstü uygulamaları](/mfc/mfc-desktop-applications). Gelişmiş grafik kullanan geleneksel C++ masaüstü uygulaması örneği için bkz: [Hilo: için C++ uygulamaları Windows geliştirme](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx).

### <a name="c-or-net"></a>C++ veya .NET? 

En Masaüstü uygulama senaryoları için (diğer bir deyişle, değil hedefleme UWP) kullanmayı C# ve .NET. .NET programlama genellikle daha az karmaşık, daha az hata yapmaya açık ve nesne yönelimli daha modern API Win32 veya MFC sahip olmasıdır. Çoğu durumda, kendi performans birden fazla yeterlidir. .NET zengin grafik Windows Presentation Foundation (WPF) özellikleri ve Win32 yanı sıra (UWP aşağıya bakın) modern Windows Runtime API'ı kullanabilir. Genel kural olarak, gerektirdiğinde, Masaüstü uygulamaları için C++ kullanmanızı öneririz:

- bellek kullanımı üzerinde kesin denetim
- güç tüketiminde hayati ekonomi
- genel bilgi işlem için GPU kullanımı
- DirectX erişim
- Standart C++ kitaplıklarını ağır kullanımı

## <a name="com-components"></a>COM bileşenleri

Windows işletim sistemi pek çok bölümünün üzerinde Bileşen Nesne Modeli (herhangi bir bilgisayar dilinde yazılmış istemci uygulamalarından Tüketilecek bileşeni sağlayan bir ikili standart tanımlayan COM) temel alır. C++'da, kendi COM bileşenleri oluşturma işini kolaylaştırmak için Etkin Şablon kitaplığı (ATL) kullanabilirsiniz. Daha fazla bilgi için [Bileşen Nesne Modeli (COM)](/windows/desktop/com/component-object-model--com--portal) ve [ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

## <a name="windows-universal-apps"></a>Evrensel Windows uygulamaları

Evrensel Windows Platformu (UWP) modern Windows API'dir. UWP uygulamaları, tüm Windows 10 cihazlarda çalıştırmak, XAML için kullanıcı arabirimini kullanın ve tam olarak dokunmatik. UWP hakkında daha fazla bilgi için bkz: [bir evrensel Windows Platformu (UWP) uygulaması nedir?](/windows/uwp/get-started/whats-a-uwp) ve [Evrensel Windows uygulamaları Kılavuzu](/windows/uwp/get-started/universal-application-platform-guide).

Toplamda UWP özgün C++ desteği (1), C + +/ CX kapsamında, SQL diyalektiği C++ sözdizimi uzantılarını ile veya (2 Windows çalışma zamanı kitaplığı (Standart C++ ve COM dayalı WRL) Hem C + +/ CX ve WRL desteklenmeye devam eder. Yeni projeler için öneririz [C + +/ WinRT](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt) tamamen standart C++ temel alır ve daha hızlı performans sağlar. 

Windows 10 için mevcut C++ Masaüstü uygulamanızı olarak paketleyebilirsiniz-Microsoft Store aracılığıyla dağıtım içindir. Daha fazla bilgi için [Masaüstü uygulamaları (Masaüstü köprüsü) paketini](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="games"></a>Oyunlar

DirectX oyunları, PC veya Xbox üzerinde çalıştırabilirsiniz. Daha fazla bilgi için [DirectX grafik ve oyun](/windows/desktop/directx).

## <a name="net-wrappers-for-c-libraries"></a>C++ kitaplıkları için .NET sarmalayıcıları

Kullanabileceğiniz C + +/ CLI, .NET kodu yerel C++ kitaplıkları kullanmasını sağlayan bir birlikte çalışma katmanı oluşturmak için. Daha fazla bilgi için [.NET programlama ile C + +/ CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

## <a name="sql-server-database-clients"></a>SQL Server veritabanı istemcileri

SQL Server veritabanlarını yerel kod içinden erişmek için ODBC ve OLE DB kullanın. Daha fazla bilgi için [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

## <a name="windows-device-drivers"></a>Windows cihaz sürücüleri

Donanım cihazlardan gelen veriler uygulamalar tarafından erişilebilir kılın alt düzey bileşenleri ve diğer işletim sistemi bileşenleri sürücülerdir. Daha fazla bilgi için [Windows Sürücü Seti'nin (WDK)](/windows-hardware/drivers/index).

## <a name="windows-services"></a>Windows hizmetleri

Bir Windows *hizmet* çok az kayıpla veya hiç kullanıcı etkileşimi olmadan arka planda çalışan bir programdır. UNIX bunlar adlandırılır *Daemon'ları*. Daha fazla bilgi için [Hizmetleri](/windows/desktop/services/services).

## <a name="sdks-libraries-and-header-files"></a>SDK'lar, kitaplıklar ve üst bilgi dosyaları

Visual Studio C çalışma zamanı kitaplığı (CRT), C++ Standart Kitaplığı ve Microsoft'a özel diğer kitaplıkları içerir. Bu kitaplıklara ilişkin üst bilgi dosyaları içeren içerme klasörleri ya da Visual Studio yükleme dizininde \VC\ klasörünün altında ya da söz konusu olduğunda Windows SDK'sını yükleme klasöründeki CRT yer alır.

Kullanabileceğiniz [Vcpkg Paket Yöneticisi](../vcpkg.md) Windows için üçüncü taraf açık kaynak kitaplıkları yüzlerce rahatça yüklenecek.

Microsoft kitaplıkları şunları içerir:

- Microsoft Foundation Classes (MFC): Geleneksel Windows programları ve özellikle de düğmeler, liste kutuları, ağaç görünümleri ve diğer denetimleri barındıran zengin kullanıcı arabirimlerine sahip kurumsal uygulamalar oluşturmaya yönelik nesne yönelimli bir çerçevedir. Daha fazla bilgi için [MFC Masaüstü uygulamaları](../mfc/mfc-desktop-applications.md).

- Etkin Şablon Kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplık. Daha fazla bilgi için [ATL COM Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism): GPU üzerinde yüksek performanslı genel hesaplama işlerini etkinleştiren bir kitaplık. Daha fazla bilgi için [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Birden fazla çekirdekli ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama işini basitleştiren bir kitaplık. Daha fazla bilgi için [eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Varsayılan olarak, Visual Studio, Windows SDK'sı bir evrensel Windows uygulama geliştirmeyi sağlayan C++ Masaüstü iş yükü bileşeni olarak yükler. UWP uygulamaları geliştirme için Windows SDK'sının Windows 10 sürümü gerekir. Bilgi için [Windows 10 SDK'sı](https://dev.windows.com/downloads/windows-10-sdk). (Windows, önceki sürümler için Windows SDK'ları hakkında daha fazla bilgi için bkz. [Windows SDK arşivi](https://developer.microsoft.com/windows/downloads/sdk-archive)).

**Program dosyaları (x86) \Windows Setleri** yüklü olduğu Windows SDK'ın tüm sürümleri için varsayılan konumdur.

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için [Visual Studio ile geliştirmeye başlayın](/visualstudio/ide/get-started-developing-with-visual-studio), ve [geliştirme araçları ve IDE](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="in-this-section"></a>Bu bölümde
|Başlık|Açıklama|
|-----------|-----------------|
|[C++ içinde Windows Masaüstü Uygulamaları](desktop-applications-visual-cpp.md)| Geleneksel Masaüstü uygulamaları oluşturmayı öğrenin.|
|[Etkin Şablon Kitaplığı (ATL)](../atl/TOC.md)|ATL kitaplığı, C++ ile COM bileşenleri oluşturmak için kullanın.|
|[Microsoft Foundation Sınıfları (MFC)](../mfc/TOC.md)|MFC iletişim kutuları ve denetimleri ile büyük veya küçük Windows uygulamaları oluşturmak için kullanın|
|[ATL ve MFC Paylaşılan Sınıfları](../atl-mfc-shared/TOC.md)|ATL ve MFC paylaşılan sınıfları CString gibi kullanın.|
|[C++/CLI ile .NET Geliştirme](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET uygulamaları ve bileşenleri ile iletişimi etkinleştir yerel C++ kitaplıkları için sarmalayıcıları oluşturun.|
|[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)|C + tarafından paylaşılan söz dizimi öğeleri için başvuru +/ CX ve C + +/ CLI.|
|[Evrensel Windows Uygulamaları (C++)](universal-windows-apps-cpp.md)|Yazma UWP uygulamaları kullanarak C + +/ CX veya Windows çalışma zamanı Şablon kitaplığı (WRL).|
|[COM ve .NET için C++ Öznitelikleri](attributes/cpp-attributes-com-net.md)|Standart olmayan öznitelikler için .NET veya COM kullanarak yalnızca Windows programlama|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Visual C++ Geliştirici içeriği için üst konu.|
