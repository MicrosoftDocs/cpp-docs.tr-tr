---
description: "Şu konuda daha fazla bilgi edinin: nasıl yapılır: 64 bit, x64 'te barındırılan MSVC araç takımını komut satırında etkinleştirme"
title: 'Nasıl yapılır: komut satırında 64-bit MSVC araç takımını etkinleştirme'
ms.date: 07/24/2019
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
ms.openlocfilehash: d5e712802f420d425f4a0291d88220c22d4aeb62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97162735"
---
# <a name="how-to-enable-a-64-bit-x64-hosted-msvc-toolset-on-the-command-line"></a>Nasıl yapılır: komut satırında 64 bit, x64 içinde barındırılan MSVC araç takımını etkinleştirme

Visual Studio, 32 bit, 64 bit veya ARM tabanlı Windows işletim sistemlerinde çalışabilen uygulamalarınızın platforma özgü sürümlerini oluşturmak için kullanabileceğiniz C++ derleyicileri, linleri ve diğer araçları içerir. Diğer isteğe bağlı Visual Studio iş yükleri, iOS, Android ve Linux gibi diğer platformları hedeflemek için C++ araçları kullanmanıza olanak sağlar. Varsayılan derleme mimarisi, 32 bit, x86-yerel Windows kodu derlemek için 32 bit, x86 barındırılan araçları kullanır. Ancak büyük olasılıkla 64 bitlik bir bilgisayarınız vardır. Visual Studio, 64 bitlik bir Windows işletim sisteminde yüklü olduğunda, 64 bit, x64 'de barındırılan yerel ve çapraz derleyiciler için ek Geliştirici komut istemi kısayolları kullanılabilir. X86, x64 veya ARM işlemcileri için kod oluştururken, 64 bit, x64 tarafından barındırılan araç takımını kullanarak 64 bit kod için kullanılabilen işlemci ve bellek alanından yararlanabilirsiniz.

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>64 bitlik bir barındırılan Geliştirici komut istemi kısayolu kullanın

Windows 10 ' da bu komut istemlerini erişmek için, **Başlat** menüsünde, Visual Studio sürümünüz için klasörü açın, örneğin **Visual Studio 2019** ve ardından x64 yerel veya çapraz araç Geliştirici komut istemlerinin birini seçin.

![x64 Yerel Araçları Komut İstemi](media/x64-native-tools-command-prompt.png "Başlangıç menüsünde x64 yerel araçları")

Bu komut istemlerini Windows 8 ' de erişmek için, **Başlangıç** ekranında **tüm uygulamalar**' ı açın. Visual Studio 'nun yüklü sürümü için başlık altında, **Visual Studio** klasörünü açın (Visual Studio 'nun eski sürümlerinde, **Visual Studio Araçları** adlandırılmış olabilir). Windows 'un önceki sürümlerinde **Başlat**' ı, **tüm programlar**' ı, **Visual Studio** sürümünüz için klasörü (ve Visual Studio 'nun eski sürümlerinde **Visual Studio Araçları**) seçin. Daha fazla bilgi için bkz. [Geliştirici komut istemi kısayolları](building-on-the-command-line.md#developer_command_prompt_shortcuts).

## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>64 bitlik bir barındırılan derleme mimarisi ayarlamak için Vcvarsall.bat kullanma

Herhangi bir yerel veya çapraz derleyici araçları derleme yapılandırması, vcvarsall.bat komut dosyası çalıştırılarak komut satırında kullanılabilir. Bu komut dosyası, varolan bir komut istemi penceresinde belirli bir yapı mimarisini etkinleştiren yolu ve ortam değişkenlerini yapılandırır. Belirli yönergeler için bkz. [Geliştirici komut dosyası konumları](building-on-the-command-line.md#developer_command_file_locations).

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Her Visual Studio sürümüne dahil olan belirli araçlar hakkında daha fazla bilgi için bkz. [Visual Studio sürümlerindeki Visual C++ araçları ve özellikleri](../overview/visual-cpp-tools-and-features-in-visual-studio-editions.md).
>
> Visual Studio IDE 'nin 64 bitlik uygulamalar oluşturmak için nasıl kullanılacağı hakkında bilgi için bkz. [nasıl yapılır: yapılandırma Visual C++ projeleri 64 bit, x64 platformları hedefleyecek](how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)şekilde.

Visual Studio yükleyicisine bir C++ iş yükü yüklediğinizde, x86 ve x64 kodu oluşturmak için her zaman 32 bit, x86 barındırılan, yerel ve çapraz derleyici araçları yükler. Evrensel Windows Platformu iş yükünü eklerseniz, ARM kodu oluşturmak için x86 barındırılan çapraz derleyici araçları da yüklenir. Bu iş yüklerini 64 bit, x64 işlemciye yüklerseniz, x86, x64 ve ARM kodu oluşturmaya yönelik 64 bit yerel ve çapraz derleyici araçları da alırsınız. 32-bit ve 64 bit araçları aynı kodu oluşturur, ancak 64 bit araçları önceden derlenmiş üstbilgi sembolleri ve tüm program Iyileştirmesi ([/GL](reference/gl-whole-program-optimization.md) ve [/LTCG](reference/ltcg-link-time-code-generation.md)) seçenekleri için daha fazla bellek destekler. 32 bit araçları kullandığınızda bellek sınırlarında çalıştırırsanız, 64 bit araçları deneyin.

## <a name="see-also"></a>Ayrıca bkz.

[64 bit, x64 hedefleri için C++ projelerini yapılandırma](configuring-programs-for-64-bit-visual-cpp.md)<br/>
