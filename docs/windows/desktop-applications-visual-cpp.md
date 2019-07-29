---
title: Masaüstü uygulamaları (görsel C++)
ms.date: 07/28/2019
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
ms.openlocfilehash: a1e302a29e079545f6d12ad544eab4f43e2bd445
ms.sourcegitcommit: 720b74dddb1cdf4e570d55103158304ee1df81f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68606518"
---
# <a name="desktop-applications-visual-c"></a>Masaüstü uygulamaları (görsel C++)

İçindeki C++ bir *Masaüstü uygulaması* , Windows API 'lerinin tamamına erişebilen ve bir pencerede ya da sistem konsolunda çalışan yerel bir uygulamadır. İçindeki C++ masaüstü uygulamaları Windows 10 ' da Windows 10 ' da çalıştırılabilir (ancak Windows XP artık resmi olarak desteklenmese de, bu tarihten sonra sunulan birçok Windows API 'si mevcuttur). 

Masaüstü uygulaması, Windows 10 çalıştıran bilgisayarlarda ve ayrıca XBox, Windows Phone, Surface Hub ve diğer cihazlarda çalışabilen Evrensel Windows Platformu (UWP) uygulamasından farklıdır. Masaüstü ile ilgili daha fazla bilgi için UWP uygulamaları, bkz. [teknolojinizi seçme](/windows/desktop/choose-your-technology).

### <a name="desktop-bridge"></a>Masaüstü Köprüsü

Windows 10 ' da, mevcut masaüstü uygulamanızı veya COM nesnesini UWP uygulaması olarak paketleyebilir, dokunmatik gibi UWP özellikleri ekleyebilir veya modern Windows API kümesinden API 'Ler çağırabilirsiniz. Ayrıca, Visual Studio 'da bir masaüstü çözümüne UWP uygulaması ekleyebilir ve bunları tek bir pakette paketleyebilir ve Windows API 'Lerini kullanarak onlarla iletişim kurabilirsiniz.

Visual Studio 2017 sürüm 15,4 ve sonraki sürümlerde, mevcut masaüstü uygulamanızı paketleme işini büyük ölçüde basitleştirmek için bir Windows uygulama paketi projesi oluşturabilirsiniz. Masaüstü uygulamanızın kullandığı kayıt defteri çağrılarının veya API 'lerle ilgili olarak birkaç kısıtlama geçerlidir, ancak çoğu durumda, uygulama paketinde çalışırken benzer işlevlere ulaşmak için alternatif kod yolları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

### <a name="terminology"></a>Terminoloji

- Bir *Win32* uygulaması, yerel C++ [Windows C API 'Leri ve/veya com API 'leri](/windows/desktop/apiindex/windows-api-list) ve standart kitaplık API 'leri ve 3. taraf kitaplıklarını kullanarak, içindeki bir Windows masaüstü uygulamasıdır. Bir pencerede çalışan bir Win32 uygulaması, geliştiricinin bir Windows yordamı işlevi içinde Windows iletileriyle açık bir şekilde çalışmasını gerektirir. Ada karşın, bir Win32 uygulaması 32 bitlik (x86) veya 64 bit (x64) ikili olarak derlenebilir. Visual Studio IDE 'de, x86 ve Win32 terimleri eşanlamlı olarak anlamlıdır.

- [Bileşen nesne modeli (com)](/windows/desktop/com/the-component-object-model) , farklı dillerde yazılmış programların birbirleriyle iletişim kurmasına olanak tanıyan bir belirtimdir. Birçok Windows bileşeni COM nesneleri olarak uygulanır ve nesne oluşturma, arabirim bulma ve nesne yok etme için standart COM kurallarını izler.  C++ Masaüstü uygulamalarından com nesnelerinin kullanılması nispeten basittir, ancak kendi com nesneniz yazmak daha gelişmiş bir işlemdir. [Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md) , com geliştirmeyi kolaylaştıran makrolar ve yardımcı işlevler sağlar.

- MFC uygulaması, Kullanıcı arabirimini oluşturmak için [Microsoft Foundation sınıfları](../mfc/mfc-desktop-applications.md) kullanan bir Windows masaüstü uygulamasıdır. Bir MFC uygulaması Ayrıca, COM bileşenlerini ve CRT ve standart kitaplık API 'Lerini de kullanabilir. MFC, pencere ileti C++ döngüsü ve Windows API 'leri üzerinde ince nesne odaklı bir sarmalayıcı sağlar. MFC, çok sayıda kullanıcı arabirimi denetimi veya özel kullanıcı denetimi olan uygulamalar için varsayılan seçenektir (özellikle kurumsal tür uygulamalar). MFC, pencere yönetimi, serileştirme, metin işleme, yazdırma ve şerit gibi modern Kullanıcı arabirimi öğeleri için kullanışlı yardımcı sınıflar sağlar. MFC ile etkili olması için Win32 ile ilgili bilgi sahibi olmanız gerekir.

- Bir C++/CLI uygulaması veya bileşeni, .net Ile C++ yerel C + + kodu arasında C++ etkileşimi etkinleştirmek için sözdizimi için uzantıları (Standart tarafından izin verilen olarak) kullanır.  Bir C++/CLI uygulaması, yerel olarak çalışan ve .net temel sınıf kitaplığı erişimi olan .NET Framework çalışan parçalar içerebilir. C++/CLı, C# veya Visual Basic yazılmış kodla çalışması gereken yerel C++ kodunuz varsa tercih edilen seçenektir. Kullanıcı arabirimi kodu yerine .NET DLL 'lerde kullanılmak üzere tasarlanmıştır. Daha fazla bilgi için bkz. [/CLI ( C++görsel C++) ile .NET programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

İçindeki C++ herhangi bir masaüstü uygulaması C çalışma zamanı (CRT) ve standart kitaplık sınıfları ve IŞLEVLERI, com nesneleri ve toplu olarak Windows API olarak bilinen genel Windows işlevlerini kullanabilir. İçindeki C++Windows masaüstü uygulamalarına giriş için bkz. [Win32 ve C++ile çalışmaya başlama ](/windows/desktop/LearnWin32/learn-to-program-for-windows).

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[C++ içinde Windows Konsol Uygulamaları](console-applications-in-visual-cpp.md)|Konsol uygulamaları hakkında bilgi içerir. Bir Win32 (veya Win64) konsol uygulamasının kendi penceresi yok ve ileti döngüsü yok. Konsol penceresinde çalışır ve giriş ve çıkış komut satırı aracılığıyla işlenir.|
|[İzlenecek yol: Windows Masaüstü Uygulaması Oluşturma (C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|Basit bir Windows masaüstü uygulaması oluşturun.|
|[Boş Windows Masaüstü Uygulaması Oluşturma](creating-an-empty-windows-desktop-application.md)|Varsayılan dosyaları olmayan bir Windows Masaüstü projesi oluşturma.|
|[Boş Win32 Uygulamalarına Dosya Ekleme](adding-files-to-an-empty-win32-applications.md)|Boş bir projeye dosya ekleme.|
|[Kaynak Dosyalarıyla Çalışma](working-with-resource-files.md)|Bir masaüstü uygulamasına görüntü, simge, dize tablosu ve diğer kaynakları ekleme.|
|[DirectX (C++) kullanarak oyun oluşturmak için kaynaklar](resources-for-creating-a-game-using-directx.md)|İçindeki C++oyunları oluşturmak için içerik bağlantıları.|
|[İzlenecek yol: Statik kitaplık oluşturma ve kullanma](walkthrough-creating-and-using-a-static-library-cpp.md)|. Lib ikili dosyası oluşturma.|
|[Nasıl yapılır: Windows 10 SDK’yı bir Windows Masaüstü Uygulamasında Kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK kullanarak derlemek için projenizi ayarlama adımlarını içerir.|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Windows Geliştirme](/windows/desktop/index)|Windows API ve COM hakkında bilgi içerir. (Bazı Windows API 'leri ve üçüncü taraf dll 'Ler COM nesneleri olarak uygulanır.)|
|[Hilo Windows C++ 7 için uygulama geliştirme](https://msdn.microsoft.com/library/windows/desktop/ff708696.aspx)|Bir Carousel tabanlı kullanıcı arabirimi oluşturmak için Windows Animation ve Direct2D kullanan zengin istemci bir Windows masaüstü uygulamasının nasıl oluşturulduğunu açıklar.  Bu öğretici, Windows 7 ' den beri güncelleştirilmemiş, ancak yine de Win32 programlamaya kapsamlı bir giriş sağlıyor.|
|[C++'ta Windows Programlamasına Genel Bakış](overview-of-windows-programming-in-cpp.md)|' De C++Windows masaüstü programlama 'nin temel özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)