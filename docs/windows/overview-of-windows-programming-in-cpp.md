---
title: C++'da Windows Programlamasına Genel Bakış
ms.date: 07/28/2019
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
ms.openlocfilehash: 10ef9698e27099d5856c1ed5f8ed2f21cea72c24
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514799"
---
# <a name="overview-of-windows-programming-in-c"></a>C++'da Windows Programlamasına Genel Bakış

İle C++oluşturabileceğiniz çeşitli geniş Windows uygulamaları kategorileri vardır. Her birinin kendi programlama modeli ve Windows 'a özel kitaplıkları vardır, ancak C++ standart kitaplık ve üçüncü taraf C++ kitaplıkları bunlardan hiçbirinde kullanılabilir. 

Bu bölümde, Windows programları oluşturmak için Visual Studio ve MFC/ATL sarmalayıcı kitaplıklarının nasıl kullanılacağı açıklanmaktadır. Windows platformunun belgeleri için, bkz. [Windows belgeleri](/windows/index).

## <a name="command-line-console-applications"></a>Komut satırı (konsol) uygulamaları

C++Konsol uygulamaları konsol penceresinde komut satırından çalışır ve yalnızca metin çıktısını görüntüleyebilir. Daha fazla bilgi için bkz. [konsol uygulamaları](console-applications-in-visual-cpp.md).

## <a name="native-desktop-client-applications"></a>Yerel Masaüstü istemci uygulamaları

*Yerel Masaüstü istemci uygulaması* , işletim sistemine erişmek için C++ özgün yerel [Windows C API 'lerini veya bileşen nesne modeli (com) API 'lerini](/windows/win32/apiindex/windows-api-list) kullanan bir C veya pencereli uygulamadır. Bu API 'Ler çoğunlukla C içinde yazılır. Yerel masaüstü uygulaması oluşturmanın birden çok yolu vardır: İşletim sistemi olaylarını işleyen C stili bir ileti döngüsü kullanarak doğrudan Win32 API 'Leri kullanarak program yapabilirsiniz. Ya da, Win32 sarmalayan hafif bir nesne yönelimli C++ kitaplık olan Microsoft Foundation sınıfları (MFC) kullanarak program yapabilirsiniz. Hiçbir yaklaşım, Evrensel Windows Platformu (UWP) ile karşılaştırıldığında "modern" olarak kabul edilir, ancak her ikisi de tamamen desteklenmektedir ve dünyanın dört bir kısmında çalışan milyonlarca kod satırı vardır. Bir pencerede çalışan bir Win32 uygulaması, geliştiricinin bir Windows yordamı işlevi içinde Windows iletileriyle açık bir şekilde çalışmasını gerektirir. Ada karşın, bir Win32 uygulaması 32 bitlik (x86) veya 64 bit (x64) ikili olarak derlenebilir. Visual Studio IDE 'de, x86 ve Win32 terimleri eşanlamlı olarak anlamlıdır.

Geleneksel Windows C++ programlama ile çalışmaya başlamak için bkz. [Win32 ve C++ile çalışmaya ](/windows/win32/LearnWin32/learn-to-program-for-windows)başlama. Win32 hakkında biraz bilgi sahibi olduktan sonra [MFC masaüstü uygulamaları](../mfc/mfc-desktop-applications.md)hakkında daha fazla bilgi edinmek daha kolay olacaktır. Gelişmiş grafikler kullanan geleneksel C++ masaüstü uygulamasına bir örnek için bkz [. Tepo: C++ Windows](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)için uygulamalar geliştirme.

### <a name="c-or-net"></a>C++veya .NET?

Genel olarak, sürümünde C# .NET programlama daha az karmaşıktır, daha az hataya açıktır ve WIN32 veya MFC 'den daha modern bir nesne odaklı API içerir. Çoğu durumda, performansı yeterli değildir. .NET, zengin grafikler için Windows Presentation Foundation (WPF) özelliklerine sahiptir ve hem Win32 hem de modern Windows Çalışma Zamanı API 'sini kullanabilirsiniz. Genel bir kural olarak, ihtiyacınız olduğunda Masaüstü C++ uygulamaları için kullanmanızı öneririz:

- bellek kullanımı üzerinde kesin denetim
- güç tüketiminde en çok ekonomisi
- genel bilgi işlem için GPU kullanımı
- DirectX 'e erişim
- Standart C++ kitaplıkların ağır kullanımı

.NET programlama C++ ile gücünü ve verimliliğini de birleştirmek mümkündür. ' De bir kullanıcı arabirimi oluşturabilir ve C# uygulamayı yerel C++ C++ kitaplıkları kullanmasını sağlamak için/CLI ' yı kullanabilirsiniz. Daha fazla bilgi için bkz. [/CLI ile C++.NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

## <a name="com-components"></a>COM bileşenleri

[Bileşen nesne modeli (com)](/windows/win32/com/the-component-object-model) , farklı dillerde yazılmış programların birbirleriyle iletişim kurmasına olanak tanıyan bir belirtimdir. Birçok Windows bileşeni COM nesneleri olarak uygulanır ve nesne oluşturma, arabirim bulma ve nesne yok etme için standart COM kurallarını izler.  C++ Masaüstü uygulamalarından com nesnelerinin kullanılması nispeten basittir, ancak kendi com nesneniz yazmak daha gelişmiş bir işlemdir. [Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md) , com geliştirmeyi kolaylaştıran makrolar ve yardımcı işlevler sağlar. Daha fazla bilgi için bkz. [atl com Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

## <a name="universal-windows-platform-apps"></a>Evrensel Windows platformu uygulamaları

Evrensel Windows Platformu (UWP), modern Windows API 'sidir. UWP uygulamaları herhangi bir Windows 10 cihazında çalışır, Kullanıcı arabirimi için XAML kullanın ve tam dokunma etkindir. UWP hakkında daha fazla bilgi için bkz. [Evrensel Windows platformu (UWP) uygulaması nedir?](/windows/uwp/get-started/whats-a-uwp) ve [Windows Evrensel uygulamalarına yönelik kılavuz](/windows/uwp/get-started/universal-application-platform-guide).

UWP için C++ özgün destek (1) C++/CX, sözdizimi uzantılarına C++ sahip bir diyalekt veya (2) standart C++ ve com tabanlı Windows çalışma zamanı kitaplığı (WRL). Hem C++/CX hem de WRL destekleniyor. Yeni projelerde, tamamen standart C++ tabanlı olan ve daha hızlı performans sağlayan [ C++/wınrt](/windows/uwp/cpp-and-winrt-apis/intro-to-using-cpp-with-winrt)önerilir.

## <a name="desktop-bridge"></a>Masaüstü Köprüsü

Windows 10 ' da, mevcut masaüstü uygulamanızı veya COM nesnesini UWP uygulaması olarak paketleyebilir, dokunmatik gibi UWP özellikleri ekleyebilir veya modern Windows API kümesinden API 'Ler çağırabilirsiniz. Ayrıca, Visual Studio 'da bir masaüstü çözümüne UWP uygulaması ekleyebilir ve bunları tek bir pakette paketleyebilir ve Windows API 'Lerini kullanarak onlarla iletişim kurabilirsiniz.

Visual Studio 2017 sürüm 15,4 ve üzeri, mevcut masaüstü uygulamanızı paketleme işini önemli ölçüde basitleştirmek için bir Windows uygulama paketi projesi oluşturmanızı sağlar. Masaüstü uygulamanızın kullanabileceği kayıt defteri çağrıları veya API 'Leri için birkaç kısıtlama geçerlidir. Ancak çoğu durumda, bir uygulama paketinde çalışırken benzer işlevlere ulaşmak için alternatif kod yolları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="games"></a>Oynayabilir

DirectX oyunları PC veya Xbox üzerinde çalışabilir. Daha fazla bilgi için bkz. [DirectX grafik ve oyun](/windows/win32/directx).

## <a name="sql-server-database-clients"></a>SQL Server veritabanı istemcileri

Yerel koddan SQL Server veritabanlarına erişmek için ODBC veya OLE DB kullanın. Daha fazla bilgi için bkz. [SQL Server Native Client](/sql/relational-databases/native-client/odbc/sql-server-native-client-odbc).

## <a name="windows-device-drivers"></a>Windows cihaz sürücüleri

Sürücüler, donanım aygıtlarından uygulamalar ve diğer işletim sistemi bileşenleri tarafından erişilebilen verileri oluşturan alt düzey bileşenleridir. Daha fazla bilgi için bkz. [Windows Sürücü Seti (WDK)](/windows-hardware/drivers/index).

## <a name="windows-services"></a>Windows hizmetleri

Windows *hizmeti* , çok az kullanıcı etkileşimi ile arka planda çalışabilecek bir programdır. Bu programlara UNIX sistemlerinde *Daemon 'ları* adı verilir. Daha fazla bilgi için bkz. [Hizmetler](/windows/win32/services/services).

## <a name="sdks-libraries-and-header-files"></a>SDK 'lar, kitaplıklar ve üst bilgi dosyaları

Visual Studio, C çalışma zamanı kitaplığı (CRT), C++ standart kitaplığı ve Microsoft 'a özgü diğer kitaplıkları içerir. Bu kitaplıkların başlık dosyalarını içeren içerme klasörlerinin çoğu, \VC\ klasörü altındaki Visual Studio yükleme dizininde bulunur. Windows ve CRT üst bilgi dosyaları Windows SDK yükleme klasöründe bulunur.

[Vcpkg Paket Yöneticisi](../build/vcpkg.md) , Windows için yüzlerce üçüncü taraf açık kaynak kitaplıklarını rahat bir şekilde yüklemenize olanak sağlar.

Microsoft kitaplıkları şunları içerir:

- Microsoft Foundation Sınıfları (MFC): Özellik düğmeleri, liste kutuları, ağaç görünümleri ve diğer denetimler için zengin Kullanıcı arabirimleri olan geleneksel Windows programları (özellikle kurumsal uygulamalar) oluşturmaya yönelik nesne odaklı bir çerçeve. Daha fazla bilgi için bkz. [MFC masaüstü uygulamaları](../mfc/mfc-desktop-applications.md).

- Etkin Şablon kitaplığı (ATL): COM bileşenleri oluşturmak için güçlü bir yardımcı kitaplığı. Daha fazla bilgi için bkz. [atl com Masaüstü bileşenleri](../atl/atl-com-desktop-components.md).

- C++AMP (C++ hızlandırılmış geniş paralellik): GPU üzerinde yüksek performanslı genel hesaplama çalışmasına izin veren bir kitaplık. Daha fazla bilgi için bkz [ C++ . ampC++ (hızlandırılmış geniş paralellik)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Eşzamanlılık Çalışma Zamanı: Çoklu ve çok çekirdekli cihazlar için paralel ve zaman uyumsuz programlama çalışmasını kolaylaştıran bir kitaplık. Daha fazla bilgi için bkz. [Eşzamanlılık çalışma zamanı](../parallel/concrt/concurrency-runtime.md).

Birçok Windows programlama senaryosunda ayrıca, Windows işletim sistemi bileşenlerine erişimi etkinleştiren başlık dosyalarını içeren Windows SDK gerekir. Varsayılan olarak, Visual Studio Windows SDK, Evrensel Windows uygulamalarının geliştirilmesini sağlayan C++ masaüstü iş yükünün bir bileşeni olarak yüklenir. UWP uygulamaları geliştirmek için Windows SDK Windows 10 sürümü gerekir. Bilgi için bkz. [Windows 10 SDK](https://dev.windows.com/downloads/windows-10-sdk). (Windows 'un önceki sürümleri için Windows SDK 'Ları hakkında daha fazla bilgi için bkz. [Windows SDK Arşivi](https://developer.microsoft.com/windows/downloads/sdk-archive)).

**Program Files (x86) \Windows Kits** , yüklediğiniz tüm Windows SDK sürümleri için varsayılan konumdur.

Xbox ve Azure gibi diğer platformların kendi SDK'ları vardır ve bunları yüklemeniz gerekebilir. Daha fazla bilgi için bkz. DirectX Geliştirici Merkezi ve Azure Geliştirici Merkezi.

## <a name="development-tools"></a>Geliştirme Araçları

Visual Studio yerel kod, statik çözümleme araçları, grafik hata ayıklama araçları, tam özellikli bir kod düzenleyicisi, birim testleri için destek ve diğer birçok araç ve yardımcı program için güçlü bir hata ayıklayıcı içerir. Daha fazla bilgi için bkz. [Visual Studio ile geliştirmeye başlama](/visualstudio/ide/get-started-developing-with-visual-studio)ve [Visual Studio 'Da C++ geliştirmeye genel bakış](../overview/overview-of-cpp-development.md).

## <a name="in-this-section"></a>Bu bölümde
|Başlık|Açıklama|
|-----------|-----------------|
|[İzlenecek yol: Standart Bir C++ Programı Oluşturma](walkthrough-creating-a-standard-cpp-program-cpp.md)| Bir Windows konsol uygulaması oluşturun.|
|[İzlenecek yol: Windows Masaüstü Uygulaması Oluşturma (C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|Yerel bir Windows masaüstü uygulaması oluşturun.|
|[Windows Masaüstü Sihirbazı](windows-desktop-wizard.md)|Yeni Windows projeleri oluşturmak için Sihirbazı kullanın.|
|[Etkin Şablon Kitaplığı (ATL)](../atl/atl-com-desktop-components.md)|' De C++com bileşenleri oluşturmak için ATL kitaplığını kullanın.|
|[Microsoft Foundation Sınıfları (MFC)](../mfc/mfc-desktop-applications.md)|İletişim kutuları ve denetimlerle büyük veya küçük Windows uygulamaları oluşturmak için MFC 'yi kullanma|
|[ATL ve MFC Paylaşılan Sınıfları](../atl-mfc-shared/atl-mfc-shared-classes.md)|ATL ve MFC 'de paylaşılan CString gibi sınıfları kullanın.|
|[Veri Erişimi](../data/data-access-in-cpp.md)| OLE DB ve ODBC|
|[Metin ve Dizeler](../text/text-and-strings-in-visual-cpp.md)|Windows üzerinde çeşitli dize türleri.|
|[DirectX Kullanarak Oyun Oluşturmak için Kaynaklar](resources-for-creating-a-game-using-directx.md)
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows SDK|
|[Kaynak Dosyalarıyla Çalışma](working-with-resource-files.md)|Bir masaüstü uygulamasına görüntü, simge, dize tablosu ve diğer kaynakları ekleme.|
|[DirectX (C++) kullanarak oyun oluşturmak için kaynaklar](resources-for-creating-a-game-using-directx.md)|İçindeki C++oyunları oluşturmak için içerik bağlantıları.|
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK kullanarak derlemek için projenizi ayarlama adımlarını içerir.|
|[Yerel Masaüstü Uygulamaları Dağıtma](deploying-native-desktop-applications-visual-cpp.md)|Windows üzerinde yerel uygulamalar dağıtın.|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)|Görsel C++ geliştirici içeriği için üst konu.|
[C++/CLI ile .NET Geliştirme](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)|.NET uygulamaları ve bileşenleriyle C++ iletişim kurmasını sağlayan yerel kitaplıklar için sarmalayıcılar oluşturun.|
|[.NET ve UWP İçin Bileşen Uzantıları](../extensions/component-extensions-for-runtime-platforms.md)|/CX ve C++ C++/clientarafından paylaşılan sözdizimi öğelerine yönelik başvuru.|
|[Evrensel Windows Uygulamaları (C++)](../cppcx/universal-windows-apps-cpp.md)|/CX veya Windows Çalışma Zamanı şablon C++kitaplığı (WRL) kullanarak UWP uygulamaları yazın.|
|[COM ve .NET için C++ Öznitelikleri](attributes/cpp-attributes-com-net.md)|Yalnızca Windows 'un .NET veya COM kullanan programlama için standart olmayan öznitelikler.|
