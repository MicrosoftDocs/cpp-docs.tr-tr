---
title: C++'da Windows Programlamasına Genel Bakış
ms.date: 09/17/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 8ab7fbf7c955b1c828ef583aa639eda7409cf167
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359940"
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

C++ ile oluşturabileceğiniz birkaç geniş Windows uygulaması kategorisi vardır. Her birinin kendi programlama modeli ve Windows'a özgü kitaplıklar kümesi vardır, ancak C++ standart kitaplığı ve üçüncü taraf C++ kitaplıkları bunlardan herhangi birinde kullanılabilir.

Bu bölümde, Windows programları oluşturmak için Visual Studio ve MFC/ATL sarıcı kitaplıklarının nasıl kullanılacağı açıklanmıştır. Windows platformunun kendisiyle ilgili belgeler için [Windows belgelerine](/windows/index)bakın.

## <a name="command-line-console-applications"></a>Komut satırı (konsol) uygulamaları

C++ konsol uygulamaları bir konsol penceresinde komut satırından çalışır ve yalnızca metin çıktısını görüntüleyebilir. Daha fazla bilgi için [bkz: C++ konsol uygulaması projesi oluştur.](../get-started/tutorial-console-cpp.md)

## <a name="native-desktop-client-applications"></a>Yerel masaüstü istemci uygulamaları

*Yerel masaüstü istemci uygulaması,* işletim sistemine erişmek için özgün ana windows c [API'lerini veya Bileşen Nesne Modeli (COM) API'lerini](/windows/win32/apiindex/windows-api-list) kullanan C veya C++ pencereli bir uygulamadır. Bu API'ler çoğunlukla C olarak yazılır. Yerel bir masaüstü uygulaması oluşturmanın birden fazla yolu vardır: İşletim sistemi olaylarını işleyen C tarzı ileti döngüsü kullanarak Win32 API'lerini doğrudan kullanarak programlayabilirsiniz. Veya, Win32'yi saran hafif nesne yönelimli bir C++ kitaplığı olan *Microsoft Foundation Classes'ı* (MFC) kullanarak programlayabilirsiniz. Her iki yaklaşım evrensel Windows Platformu (UWP) ile karşılaştırıldığında "modern" olarak kabul edilir, ancak her ikisi de hala tam olarak desteklenir ve bugün dünyada çalışan kod satırları milyonlarca var. Bir pencerede çalışan Win32 uygulaması, geliştiricinin Windows yordam işlevi içinde Windows iletileriyle açık bir şekilde çalışmasını gerektirir. Adına rağmen, win32 uygulaması 32 bit (x86) veya 64-bit (x64) ikili olarak derlenebilir. Visual Studio IDE'de x86 ve Win32 terimleri eş anlamlıdır.

Geleneksel Windows C++ programlamaya başlamak için [Win32 ve C++ ile Başlayın'a](/windows/win32/LearnWin32/learn-to-program-for-windows)bakın. Win32'yi biraz anladıktan sonra, [MFC Masaüstü Uygulamaları](../mfc/mfc-desktop-applications.md)hakkında bilgi edinmek daha kolay olacaktır. Gelişmiş grafikler kullanan geleneksel bir C++ masaüstü uygulaması örneği [için](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)bkz.

### <a name="c-or-net"></a>C++ veya .NET?

Genel olarak, C#'daki .NET programlama sı daha az karmaşık, daha az hata yatkındır ve Win32 veya MFC'den daha modern nesne yönelimli API'ye sahiptir. Çoğu durumda, performansı yeterli daha fazladır. .NET, zengin grafikler için Windows Presentation Foundation 'a (WPF) sahiptir ve hem Win32 hem de modern Windows Runtime API'sını tüketebilirsiniz. Genel bir kural olarak, masaüstü uygulamaları için C++'ı şunları istediğinizde kullanmanızı öneririz:

- bellek kullanımı üzerinde hassas kontrol
- güç tüketiminde en üst düzeyde ekonomi
- genel bilgi işlem için GPU kullanımı
- DirectX'e erişim
- standart C++ kitaplıklarının ağır kullanımı

C++'ın gücünü ve verimliliğini .NET programlama ile birleştirmek de mümkündür. C#'da bir kullanıcı arabirimi oluşturabilir ve uygulamanın yerel C++ kitaplıklarını tüketmesini sağlamak için C++/CLI'yi kullanabilirsiniz. Daha fazla bilgi için [C++/CLI ile .NET Programlama'ya](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)bakın.

## <a name="com-components"></a>COM Bileşenleri

[Bileşen Nesne Modeli (COM),](/windows/win32/com/the-component-object-model) farklı dillerde yazılmış programların birbirleriyle iletişim kurmasını sağlayan bir belirtimdir. Birçok Windows bileşeni COM nesneleri olarak uygulanır ve nesne oluşturma, arabirim bulma ve nesne imha için standart COM kurallarına uyar.  C++ masaüstü uygulamalarından COM nesnelerini kullanmak nispeten kolaydır, ancak kendi COM nesnenizi yazmak daha gelişmiştir. [Etkin Şablon Kitaplığı (ATL),](../atl/atl-com-desktop-components.md) COM geliştirmeyi basitleştiren makrolar ve yardımcı işlevler sağlar. Daha fazla bilgi için [ATL COM masaüstü bileşenlerine](../atl/atl-com-desktop-components.md)bakın.

## <a name="universal-windows-platform-apps"></a>Evrensel Windows Platformu uygulamaları

Evrensel Windows Platformu (UWP) modern Windows API'sidir. UWP uygulamaları herhangi bir Windows 10 aygıtında çalışır, kullanıcı arabirimi için XAML kullanır ve tamamen dokunma özelliğine sahiptir. UWP hakkında daha fazla bilgi için Evrensel [Windows Platformu (UWP) uygulaması nedir?](/windows/uwp/get-started/whats-a-uwp) ve [Windows Evrensel Uygulamalar Kılavuzu'na](/windows/uwp/get-started/universal-application-platform-guide)bakın.

UWP için orijinal C++ desteği, sözdizimi uzantıları olan C++'ın bir lehçesi olan (1) C++/CX veya (2) standart C++ ve COM'a dayanan Windows Runtime Library'den (WRL) oluşuyordu. Hem C++/CX hem de WRL hala desteklenir. Yeni projeler için, tamamen standart C++'a dayalı ve daha hızlı performans sağlayan [C++/WinRT'yi](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)öneriyoruz.

## <a name="desktop-bridge"></a>Masaüstü Köprü

Windows 10'da, varolan masaüstü uygulamanızı veya COM nesnenizi UWP uygulaması olarak paketleyebilir ve dokunma gibi UWP özelliklerini ekleyebilir veya modern Windows API kümesinden API'leri arayabilirsiniz. Ayrıca Visual Studio'daki bir masaüstü çözümüne bir UWP uygulaması ekleyebilir ve bunları tek bir pakette paketleyebilir ve aralarında iletişim kurmak için Windows API'lerini kullanabilirsiniz.

Visual Studio 2017 sürüm 15.4 ve daha sonra mevcut masaüstü uygulamanızı paketleme işini büyük ölçüde basitleştirmek için bir Windows Uygulama Paketi Projesi oluşturmanıza olanak tanır. Kayıt defteri aramaları veya masaüstü uygulamanızın kullanabileceği API'ler için birkaç kısıtlama uygulanır. Ancak, çoğu durumda, bir uygulama paketinde çalışırken benzer işlevselliği elde etmek için alternatif kod yolları oluşturabilirsiniz. Daha fazla bilgi için [Desktop Bridge'e](/windows/uwp/porting/desktop-to-uwp-root)bakın.

## <a name="games"></a>Oyunlar

DirectX oyunları PC'de veya Xbox'ta kullanılabilir. Daha fazla bilgi için [DirectX Graphics and Gaming'e](/windows/win32/directx)bakın.

## <a name="sql-server-database-clients"></a>SQL Server veritabanı istemcileri

SQL Server veritabanlarına yerel koddan erişmek için ODBC veya OLE DB'yi kullanın. Daha fazla bilgi için [SQL Server Native Client'a](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc)bakın.

## <a name="windows-device-drivers"></a>Windows cihaz sürücüleri

Sürücüler, donanım aygıtlarından gelen verileri uygulamalar ve diğer işletim sistemi bileşenleri için erişilebilir hale getiren düşük düzeyli bileşenlerdir. Daha fazla bilgi için [Windows Sürücü Kiti 'ne (WDK)](/windows-hardware/drivers/index)bakın.

## <a name="windows-services"></a>Windows hizmetleri

Windows *hizmeti,* arka planda çok az kullanıcı etkileşimi olan veya hiç kullanıcı etkileşimi olmadan çalıştırılabilen bir programdır. Bu programlar UNIX sistemlerinde *daemons* denir. Daha fazla bilgi için [Hizmetler'e](/windows/win32/services/services)bakın.

## <a name="sdks-libraries-and-header-files"></a>SDK'lar, kitaplıklar ve üstbilgi dosyaları

Visual Studio, C Runtime Kitaplığı (CRT), C++ Standart Kitaplığı ve Microsoft'a özgü diğer kitaplıkları içerir. Bu kitaplıklar için üstbilgi dosyaları içeren klasörlerin çoğu \VC\ klasörünün altındaki Visual Studio yükleme dizininde bulunur. Windows ve CRT üstbilgi dosyaları Windows SDK yükleme klasöründe bulunur.

[Vcpkg paket yöneticisi,](../build/vcpkg.md) Windows için yüzlerce üçüncü taraf açık kaynak kitaplığı kolayca yüklemenize olanak tanır.

Microsoft kitaplıkları şunlardır:

- Microsoft Foundation Classes (MFC): Geleneksel Windows programları ve özellikle de düğmeler, liste kutuları, ağaç görünümleri ve diğer denetimleri barındıran zengin kullanıcı arabirimlerine sahip kurumsal uygulamalar oluşturmaya yönelik nesne yönelimli bir çerçevedir. Daha fazla bilgi için [MFC Masaüstü Uygulamaları'na](../mfc/mfc-desktop-applications.md)bakın.

- Etkin Şablon Kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplık. Daha fazla bilgi için [ATL COM Masaüstü Bileşenleri'ne](../atl/atl-com-desktop-components.md)bakın.

- C++ AMP (C++ Accelerated Massive Parallelism): GPU üzerinde yüksek performanslı genel hesaplama işlerini etkinleştiren bir kitaplık. Daha fazla bilgi için [bkz: C++ AMP (C++ Hızlandırılmış Masif Paralelizm)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Birden fazla çekirdekli ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama işini basitleştiren bir kitaplık. Daha fazla bilgi için [Eşzamanlılık Çalışma Zamanı'na](../parallel/concrt/concurrency-runtime.md)bakın.

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Visual Studio varsayılan olarak, Windows SDK'yı Evrensel Windows uygulamalarının geliştirilmesini sağlayan C++ Masaüstü iş yükünün bir bileşeni olarak yükler. UWP uygulamaları geliştirmek için Windows SDK'nın Windows 10 sürümüne ihtiyacınız vardır. Daha fazla bilgi için [Windows 10 SDK'ya](https://dev.windows.com/downloads/windows-10-sdk)bakın. (Windows'un önceki sürümleri için Windows SDK'lar hakkında daha fazla bilgi için [Windows SDK arşivine](https://developer.microsoft.com/windows/downloads/sdk-archive)bakın).

**Program Dosyaları (x86)\Windows Kitleri,** yüklediğiniz Windows SDK'nın tüm sürümleri için varsayılan konumdur.

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için Visual [Studio ile geliştirmeye başlayın](/visualstudio/ide/get-started-developing-with-visual-studio)ve Visual [Studio'da C++ gelişimine Genel Bakış](../overview/overview-of-cpp-development.md)bölümü ne kadar önemli olduğunu görün.

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[Walkthrough: Standart C++ Programı Oluşturma](walkthrough-creating-a-standard-cpp-program-cpp.md)| Bir Windows konsol uygulaması oluşturun.|
|[İzlenecek yol: Windows Masaüstü Uygulamaları Oluşturma (C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|Yerel bir Windows masaüstü uygulaması oluşturun.|
|[Windows Masaüstü Sihirbazı](windows-desktop-wizard.md)|Yeni Windows projeleri oluşturmak için sihirbazı kullanın.|
|[Etkin Şablon Kitaplığı (ATL)](../atl/atl-com-desktop-components.md)|C++'da COM bileşenleri oluşturmak için ATL kitaplığını kullanın.|
|[Microsoft Foundation Sınıfları (MFC)](../mfc/mfc-desktop-applications.md)|İletişim ve denetimleri olan büyük veya küçük Windows uygulamaları oluşturmak için MFC'yi kullanın|
|[ATL ve MFC Paylaşılan Sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md)|ATL ve MFC'de paylaşılan CString gibi sınıfları kullanın.|
|[Veri Erişimi](../data/data-access-in-cpp.md)| OLE DB ve ODBC|
|[Metin ve Dizeleri](../text/text-and-strings-in-visual-cpp.md)|Windows'da çeşitli dize türleri.|
|[DirectX Kullanarak Oyun Oluşturmak için Kaynaklar](resources-for-creating-a-game-using-directx.md)
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK’sı|
|[Kaynak Dosyalarıyla Çalışma](working-with-resource-files.md)|Masaüstü uygulamasına resim, simge, dize tabloları ve diğer kaynaklar ekleme.|
|[DirectX (C++) Kullanarak Oyun Oluşturma Kaynakları](resources-for-creating-a-game-using-directx.md)|C++'da oyun oluşturmak için içeriğe bağlantılar.|
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK'yı kullanarak projenizi oluşturmak için ayarlama adımları içerir.|
|[Yerel Masaüstü Uygulamaları Dağıtma](deploying-native-desktop-applications-visual-cpp.md)|Windows'da yerel uygulamaları dağıtın.|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual Studio'da C++](../overview/visual-cpp-in-visual-studio.md)|Visual C++ geliştirici içeriği için ana konu.|
[C++/CLI ile .NET Geliştirme](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET uygulamaları ve bileşenleriyle iletişim kurmasını sağlayan yerel C++ kitaplıkları için sarmalayıcılar oluşturun.|
|[.NET ve UWP İçin Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)|C++/CX ve C++/CLI tarafından paylaşılan sözdizimi öğeleri için başvuru.|
|[Evrensel Windows Uygulamaları (C++)](../cppcx/universal-windows-apps-cpp.md)|C++/CX veya Windows Runtime Şablon Kitaplığı (WRL) kullanarak UWP uygulamaları yazın.|
|[COM ve .NET için C++ Öznitelikleri](attributes/cpp-attributes-com-net.md)|.NET veya COM kullanarak yalnızca Windows programlama için standart olmayan öznitelikler.|
