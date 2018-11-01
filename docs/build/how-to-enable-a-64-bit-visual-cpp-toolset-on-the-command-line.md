---
title: 'Nasıl yapılır: Komut Satırında 64 Bit Visual C++ Araç Takımını Etkinleştirme'
ms.date: 03/29/2018
helpviewer_keywords:
- x64 [C++]
- 64-bit compiler [C++], command line usage
- 64-bit compiler [C++], toolset enabling at command line
- command line [C++], 64-bit compiler
- Itanium [C++], command-line compiler
- IPF
- Itanium [C++]
- IPF, command-line compiler
- x64 [C++], command-line compiler
ms.assetid: 4da93a19-e20d-4778-902a-5eee9a6a90b5
ms.openlocfilehash: 5c5fe144fe81fcc0fb1194c57dec7fa7556101f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572373"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>Nasıl yapılır: 64 Bit etkinleştirmek için Visual C++ araç takımı komut satırında x64 barındırılan

Visual C++ Derleyicileri, linkers ve 32-bit, 64-bit veya ARM tabanlı Windows işletim sistemlerinde çalışan, uygulamaları platforma özgü sürümlerini oluşturmak için kullanabileceğiniz diğer araçlar içerir. İsteğe bağlı diğer Visual Studio iş yükleri, iOS, Android ve Linux gibi diğer platformlarda hedeflemek için C++ Araçları'nı kullanmanıza izin verir. Varsayılan yapı mimarisi, 32-bit, x86 yerel Windows kod oluşturmak için 32-bit, x86 barındırılan araçları kullanır. Ancak büyük olasılıkla bir 64 bit bilgisayar vardır. İşlemci ve bellek alanı 64-bit kod için kullanılabilir x86, x64 ya da ARM işlemcileri için kod oluşturma sırasında 64 bit, x64 barındırılan bir araç takımı kullanarak yararlanabilirsiniz.

> [!NOTE]
> Her Visual C++ sürüm ile birlikte gelen belirli araçları hakkında daha fazla bilgi için bkz: [Visual C++ Araçları ve özellikleri Visual Studio sürümlerinde](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Visual Studio IDE 64 bit uygulamalar oluşturmak için nasıl kullanılacağı hakkında daha fazla bilgi için bkz [nasıl yapılır: Visual C++ projeleri hedef 64-Bit, x64 yapılandırma platformları](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Visual Studio Yükleyicisi'nde bir C++ iş yükünü yüklediğinizde, 32-bit x86 barındırılan, yerel ve çapraz derleyici araçları x86 ve x64 Kodu derlemek için daima yüklenir. Evrensel Windows platformu iş yükü dahil ederseniz, ARM kodu oluşturmak için çapraz derleyici x86 barındırılan Araçlar de yükler. Bu iş yükleri üzerinde bir 64 bit x64 yüklerseniz işlemci de 64 bit yerel almanıza ve yapı x86, x 64 ve ARM çapraz Araçlar derleyici kodu. 32 bit ve 64 bit Araçlar aynı kodu oluşturur, ancak önceden derlenmiş üstbilgi sembolleri ve tüm Program iyileştirmesi için 64 bit Araçlar daha fazla bellek destekler ([/GL](../build/reference/gl-whole-program-optimization.md) ve [/LTCG](../build/reference/ltcg-link-time-code-generation.md)) seçenekleri. 32 bit araçları kullanırken bellek sorunu yaşarsanız çalıştırırsanız, 64-bit araçları deneyebilirsiniz.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Bir 64-bit barındırılan Geliştirici komut istemi kısayolunun kullanın

Ek Geliştirici komut istemi kısayolları 64-bit, x64 barındırılan yerel ve çapraz derleyiciler, Visual Studio 64-bit Windows işletim sisteminde yüklü olduğunda kullanılabilir. Üzerinde Windows 10, bu komut istemlerine erişmek için **Başlat** menüsünde, Visual Studio sürümünüz için örneğin yapıtlarını **Visual Studio 2017**, yerel veya çapraz araç x64 birini seçin Geliştirici komut istemleri. Üzerinde Windows 8'de, bu komut istemlerine erişmek için **Başlat** ekran açık **tüm uygulamalar**. Visual Studio'nın yüklü sürümü başlığı altında açık **Visual Studio** klasörü (Visual Studio'nun eski sürümleri adlandırılabilir **Visual Studio Araçları**). Önceki Windows sürümlerinde seçin **Başlat**, genişletme **tüm programlar**, sürümünüz için klasör **Visual Studio** (ve Visual Studio'nun daha eski sürümlerindeki  **Visual Studio Araçları**). Daha fazla bilgi için [Geliştirici komut istemi kısayolları](../build/building-on-the-command-line.md#developer-command-prompt-shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Bir 64-bit barındırılan yapı mimarisi için Vcvarsall.bat kullanın

Herhangi bir yerel veya çapraz derleyici araçları vcvarsall.bat çalıştırarak komut satırında derleme yapılandırmaları kullanılabilir dosya komutu. Bu komut dosyası yolunu yapılandırır ve var olan bir komut istemi penceresinde mimarisi sağlayan belirli bir ortam değişkenleri oluşturun. Ayrıntılı yönergeler için bkz: [Geliştirici komut dosyaları ve konumları](../build/building-on-the-command-line.md#developer-command-files-and-locations).

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++’ı 64 bit, x64 hedefler için yapılandırma](../build/configuring-programs-for-64-bit-visual-cpp.md)<br/>
