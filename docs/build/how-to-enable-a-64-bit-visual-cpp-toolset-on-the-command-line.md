---
title: 'Nasıl yapılır: Komut satırında 64 Bit MSVC araç takımını etkinleştirme'
ms.date: 05/16/2019
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
ms.openlocfilehash: 24dd6355578e8e9e00064ccfdf31bc51b7fd12ec
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65836983"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>Nasıl yapılır: 64 Bit etkinleştirmek için komut satırında MSVC araç takımı x64 barındırılan

Visual Studio C++ Derleyicileri, linkers ve 32-bit, 64-bit veya ARM tabanlı Windows işletim sistemlerinde çalışan, uygulamaları platforma özgü sürümlerini oluşturmak için kullanabileceğiniz diğer araçlar içerir. İsteğe bağlı diğer Visual Studio iş yükleri, iOS, Android ve Linux gibi diğer platformlarda hedeflemek için C++ Araçları'nı kullanmanıza izin verir. Varsayılan yapı mimarisi, 32-bit, x86 yerel Windows kod oluşturmak için 32-bit, x86 barındırılan araçları kullanır. Ancak büyük olasılıkla bir 64 bit bilgisayar vardır. İşlemci ve bellek alanı 64-bit kod için kullanılabilir x86, x64 ya da ARM işlemcileri için kod oluşturma sırasında 64 bit, x64 barındırılan bir araç takımı kullanarak yararlanabilirsiniz.

> [!NOTE]
> Her Visual Studio sürüm ile birlikte gelen belirli araçları hakkında daha fazla bilgi için bkz: [Visual C++ Araçları ve özellikleri Visual Studio sürümlerinde](../overview/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Visual Studio IDE 64 bit uygulamalar oluşturmak için nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [nasıl yapılır: 64-Bit, hedeflemek için Visual C++ projeleri x64 yapılandırma platformları](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

Visual Studio Yükleyicisi'nde bir C++ iş yükünü yüklediğinizde, 32-bit x86 barındırılan, yerel ve çapraz derleyici araçları x86 ve x64 Kodu derlemek için daima yüklenir. Evrensel Windows platformu iş yükü dahil ederseniz, ARM kodu oluşturmak için çapraz derleyici x86 barındırılan Araçlar de yükler. Bu iş yükleri üzerinde bir 64 bit x64 yüklerseniz işlemci de 64 bit yerel almanıza ve yapı x86, x 64 ve ARM çapraz Araçlar derleyici kodu. 32 bit ve 64 bit Araçlar aynı kodu oluşturur, ancak önceden derlenmiş üstbilgi sembolleri ve tüm Program iyileştirmesi için 64 bit Araçlar daha fazla bellek destekler ([/GL](reference/gl-whole-program-optimization.md) ve [/LTCG](reference/ltcg-link-time-code-generation.md)) seçenekleri. 32 bit araçları kullanırken bellek sorunu yaşarsanız çalıştırırsanız, 64-bit araçları deneyebilirsiniz.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Bir 64-bit barındırılan Geliştirici komut istemi kısayolunun kullanın

Ek Geliştirici komut istemi kısayolları 64-bit, x64 barındırılan yerel ve çapraz derleyiciler, Visual Studio 64-bit Windows işletim sisteminde yüklü olduğunda kullanılabilir. Üzerinde Windows 10, bu komut istemlerine erişmek için **Başlat** menüsünde, Visual Studio sürümünüz için örneğin yapıtlarını **Visual Studio 2019**, yerel veya çapraz araç x64 birini seçin Geliştirici komut istemleri. Üzerinde Windows 8'de, bu komut istemlerine erişmek için **Başlat** ekran açık **tüm uygulamalar**. Visual Studio'nın yüklü sürümü başlığı altında açık **Visual Studio** klasörü (Visual Studio'nun eski sürümleri adlandırılabilir **Visual Studio Araçları**). Önceki Windows sürümlerinde seçin **Başlat**, genişletme **tüm programlar**, sürümünüz için klasör **Visual Studio** (ve Visual Studio'nun daha eski sürümlerindeki  **Visual Studio Araçları**). Daha fazla bilgi için [Geliştirici komut istemi kısayolları](building-on-the-command-line.md#developer_command_prompt_shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Bir 64-bit barındırılan yapı mimarisi için Vcvarsall.bat kullanın

Herhangi bir yerel veya çapraz derleyici araçları vcvarsall.bat çalıştırarak komut satırında derleme yapılandırmaları kullanılabilir dosya komutu. Bu komut dosyası yolunu yapılandırır ve var olan bir komut istemi penceresinde mimarisi sağlayan belirli bir ortam değişkenleri oluşturun. Ayrıntılı yönergeler için bkz: [Geliştirici komut dosyası konumları](building-on-the-command-line.md#developer_command_file_locations).

## <a name="see-also"></a>Ayrıca bkz.

[C++ projeleri için 64 bit x64 yapılandırma hedefleri](configuring-programs-for-64-bit-visual-cpp.md)<br/>
