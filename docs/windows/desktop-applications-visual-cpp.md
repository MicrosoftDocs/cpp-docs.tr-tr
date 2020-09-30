---
title: Masaüstü Uygulamaları (Visual C++)
ms.date: 07/28/2019
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
ms.topic: overview
ms.openlocfilehash: 26448ca65b3162e2adfe6988dfd8c9e85432429c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504446"
---
# <a name="desktop-applications-visual-c"></a>Masaüstü Uygulamaları (Visual C++)

C++ ' daki bir *Masaüstü uygulaması* , Windows API 'lerinin tam kümesine erişebilen ve bir pencerede veya sistem konsolunda çalışan bir yerel uygulamadır. C++ ' daki masaüstü uygulamaları Windows 10 ' dan Windows 10 ' da çalıştırılabilir (ancak Windows XP artık resmi olarak desteklenmese de, bu tarihten sonra sunulan birçok Windows API 'si mevcuttur).

Masaüstü uygulaması, Windows 10 çalıştıran bilgisayarlarda ve ayrıca XBox, Windows Phone, Surface Hub ve diğer cihazlarda çalışabilen Evrensel Windows Platformu (UWP) uygulamasından farklıdır. Masaüstü ile UWP uygulamaları hakkında daha fazla bilgi için bkz. [teknolojinizi seçme](/windows/win32/choose-your-technology).

## <a name="desktop-bridge"></a>Masaüstü Köprüsü

Windows 10 ' da, mevcut masaüstü uygulamanızı veya COM nesnesini UWP uygulaması olarak paketleyebilir, dokunmatik gibi UWP özellikleri ekleyebilir veya modern Windows API kümesinden API 'Ler çağırabilirsiniz. Ayrıca, Visual Studio 'da bir masaüstü çözümüne UWP uygulaması ekleyebilir ve bunları tek bir pakette paketleyebilir ve Windows API 'Lerini kullanarak onlarla iletişim kurabilirsiniz.

Visual Studio 2017 sürüm 15,4 ve sonraki sürümlerde, mevcut masaüstü uygulamanızı paketleme işini büyük ölçüde basitleştirmek için bir Windows uygulama paketi projesi oluşturabilirsiniz. Masaüstü uygulamanızın kullandığı kayıt defteri çağrılarının veya API 'lerle ilgili olarak birkaç kısıtlama geçerlidir, ancak çoğu durumda, uygulama paketinde çalışırken benzer işlevlere ulaşmak için alternatif kod yolları oluşturabilirsiniz. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

## <a name="terminology"></a>Terminoloji

- Bir *Win32* uygulaması, C++ ' da yerel [Windows C API 'leri ve/veya com API 'Leri](/windows/win32/apiindex/windows-api-list) ve standart kitaplık API 'lerini ve 3. taraf kitaplıklarını kullanan bir Windows masaüstü uygulamasıdır. Bir pencerede çalışan bir Win32 uygulaması, geliştiricinin bir Windows yordamı işlevi içinde Windows iletileriyle açık bir şekilde çalışmasını gerektirir. Ada karşın, bir Win32 uygulaması 32 bitlik (x86) veya 64 bit (x64) ikili olarak derlenebilir. Visual Studio IDE 'de, x86 ve Win32 terimleri eşanlamlı olarak anlamlıdır.

- [Bileşen nesne modeli (com)](/windows/win32/com/the-component-object-model) , farklı dillerde yazılmış programların birbirleriyle iletişim kurmasına olanak tanıyan bir belirtimdir. Birçok Windows bileşeni COM nesneleri olarak uygulanır ve nesne oluşturma, arabirim bulma ve nesne yok etme için standart COM kurallarını izler.  C++ Masaüstü uygulamalarından COM nesnelerinin kullanılması nispeten basittir, ancak kendi COM nesneniz yazmak daha gelişmiş bir işlemdir. [Etkin Şablon kitaplığı (ATL)](../atl/atl-com-desktop-components.md) , com geliştirmeyi kolaylaştıran makrolar ve yardımcı işlevler sağlar.

- MFC uygulaması, Kullanıcı arabirimini oluşturmak için [Microsoft Foundation sınıfları](../mfc/mfc-desktop-applications.md) kullanan bir Windows masaüstü uygulamasıdır. Bir MFC uygulaması Ayrıca, COM bileşenlerini ve CRT ve standart kitaplık API 'Lerini de kullanabilir. MFC, pencere ileti döngüsü ve Windows API 'Leri üzerinde ince C++ nesne odaklı bir sarmalayıcı sağlar. MFC, çok sayıda kullanıcı arabirimi denetimi veya özel kullanıcı denetimi olan uygulamalar için varsayılan seçenektir (özellikle kurumsal tür uygulamalar). MFC, pencere yönetimi, serileştirme, metin işleme, yazdırma ve şerit gibi modern Kullanıcı arabirimi öğeleri için kullanışlı yardımcı sınıflar sağlar. MFC ile etkili olması için Win32 ile ilgili bilgi sahibi olmanız gerekir.

- C++/CLı uygulaması veya bileşeni, .NET ve yerel C + + kodu arasında etkileşimi etkinleştirmek için C++ sözdizimi (C++ standardı tarafından izin verilen) uzantıları kullanır.  C++/CLı uygulaması, yerel olarak çalışan ve .NET temel sınıf kitaplığı erişimi olan .NET Framework çalışan parçalar içerebilir. C++/CLı, C# veya Visual Basic yazılmış kodla çalışması gereken yerel C++ kodunuz varsa tercih edilen seçenektir. Kullanıcı arabirimi kodu yerine .NET DLL 'lerde kullanılmak üzere tasarlanmıştır. Daha fazla bilgi için bkz. [C++/CLI ile .NET programlama (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

C++ ' daki herhangi bir masaüstü uygulaması C çalışma zamanı (CRT) ve standart kitaplık sınıfları ve işlevleri, COM nesneleri ve toplu olarak Windows API olarak bilinen genel Windows işlevlerini kullanabilir. C++ ' da Windows masaüstü uygulamalarına giriş için bkz. [Win32 ve C++ Ile çalışmaya başlama](/windows/win32/LearnWin32/learn-to-program-for-windows).

## <a name="in-this-section"></a>Bu bölümde

|Başlık|Açıklama|
|-----------|-----------------|
|[C++ içinde Windows Konsol Uygulamaları](./overview-of-windows-programming-in-cpp.md)|Konsol uygulamaları hakkında bilgi içerir. Bir Win32 (veya Win64) konsol uygulamasının kendi penceresi yok ve ileti döngüsü yok. Konsol penceresinde çalışır ve giriş ve çıkış komut satırı aracılığıyla işlenir.|
|[İzlenecek yol: Windows Masaüstü Uygulamaları Oluşturma (C++)](walkthrough-creating-windows-desktop-applications-cpp.md)|Basit bir Windows masaüstü uygulaması oluşturun.|
|[Boş Windows Masaüstü Uygulaması Oluşturma](./overview-of-windows-programming-in-cpp.md)|Varsayılan dosyaları olmayan bir Windows Masaüstü projesi oluşturma.|
|[Boş Win32 Uygulamalarına Dosya Ekleme](./overview-of-windows-programming-in-cpp.md)|Boş bir projeye dosya ekleme.|
|[Kaynak Dosyalarıyla Çalışma](working-with-resource-files.md)|Bir masaüstü uygulamasına görüntü, simge, dize tablosu ve diğer kaynakları ekleme.|
|[DirectX kullanarak oyun oluşturmak için kaynaklar (C++)](resources-for-creating-a-game-using-directx.md)|C++ ' da oyunlar oluşturmak için içerik bağlantıları.|
|[İzlenecek yol: statik kitaplık oluşturma ve kullanma](../build/walkthrough-creating-and-using-a-static-library-cpp.md)|. Lib ikili dosyası oluşturma.|
|[Nasıl yapılır: Windows 10 SDK 'Yı bir Windows masaüstü uygulamasında kullanma](how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Windows 10 SDK kullanarak derlemek için projenizi ayarlama adımlarını içerir.|

## <a name="related-articles"></a>İlgili Makaleler

|Başlık|Açıklama|
|-----------|-----------------|
|[Windows Geliştirme](/windows/win32/index)|Windows API ve COM hakkında bilgi içerir. (Bazı Windows API 'leri ve üçüncü taraf dll 'Ler COM nesneleri olarak uygulanır.)|
|[Tepo: Windows 7 için C++ uygulamaları geliştirme](/previous-versions/msdn10/ff708696(v=msdn.10))|Bir Carousel tabanlı kullanıcı arabirimi oluşturmak için Windows Animation ve Direct2D kullanan zengin istemci bir Windows masaüstü uygulamasının nasıl oluşturulduğunu açıklar.  Bu öğretici, Windows 7 ' den beri güncelleştirilmemiş, ancak yine de Win32 programlamaya kapsamlı bir giriş sağlıyor.|
|[C++ ' da Windows programlamaya genel bakış](overview-of-windows-programming-in-cpp.md)|C++ ' da Windows masaüstü programlama 'nin temel özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio’da C++](../overview/visual-cpp-in-visual-studio.md)
