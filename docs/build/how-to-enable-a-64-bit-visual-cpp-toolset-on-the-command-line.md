---
title: "Nasıl yapılır: bir 64 Bit Visual C++ araç komut satırında etkinleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "30"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7712bcf73881d02b5d28c8a7645609be1df5e489
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-a-64-bit-x64-hosted-visual-c-toolset-on-the-command-line"></a>Nasıl yapılır: 64 Bit etkinleştirmek için x64 Barındırılan Visual C++ araç takımını komut satırı

Visual C++ Derleyicileri, linkers ve platforma özgü sürümlerini 32-bit, 64-bit ya da ARM tabanlı Windows işletim sistemlerinde çalışan, uygulamalarınızı oluşturmak için kullanabileceğiniz diğer araçlar içerir. İsteğe bağlı diğer Visual Studio iş yükleri iOS, Android ve Linux gibi diğer platformlarda hedeflemek için C++ araçları kullanmanıza olanak tanır. 32-bit, x86 yerel Windows kod derleme için 32-bit, x86 barındırılan Araçlar Varsayılan yapı mimarisi kullanır. Ancak, muhtemelen bir 64-bit bilgisayarda vardır. 64 bit kodu kullanılabilir bellek alanı ve işlemci x86, x64 veya ARM işlemcileri için kod oluşturma sırasında 64-bit, x64 barındırılan araç takımı kullanarak yararlanabilirsiniz.
  
> [!NOTE]
>  Her Visual C++ edition ile birlikte belirli araçları hakkında daha fazla bilgi için bkz: [Visual C++ Araçları ve özelliklerinin Visual Studio sürümlerinde](../ide/visual-cpp-tools-and-features-in-visual-studio-editions.md).  
>   
>  64-bit uygulamaları oluşturmak için Visual Studio IDE kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: Visual C++ projeleri hedef 64-Bit, x64 yapılandırma platformları](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).  
  
Visual Studio yükleyicisinde C++ iş yükü yüklediğinizde, 32-bit, x86 barındırılan, yerel ve derleme araçları x86 hem x64 kodu oluşturmak için çapraz daima yüklenir. Evrensel Windows platformu iş yükü eklerseniz, ARM kodu oluşturmak için çapraz derleyici x86 barındırılan araçları da yüklenir. Bu iş yükleri üzerinde bir 64-bit, x64 yüklerseniz işlemci, aynı zamanda 64-bit yerel almak ve x 64, x86 oluşturun ve ARM derleyici araçları kod. Önceden derlenmiş üst bilgi simgeleri ve bütün Program iyileştirmesi için daha fazla bellek 64-bit araçları destek ancak aynı kodu 32 bit ve 64-bit araçları oluştur ([/GL](../build/reference/gl-whole-program-optimization.md) ve [/LTCG](../build/reference/ltcg-link-time-code-generation.md)) seçenekleri. 32 bit araçları kullandığınızda bellek sınırları çalıştırırsanız, 64-bit araçları deneyin.  

## <a name="use-a-64-bit-hosted-developer-command-prompt-shortcut"></a>Bir 64-bit barındırılan Geliştirici komut istemi kısayolunu kullanın
  
Ek Geliştirici komut istemi kısayolları 64-bit, x64 barındırılan yerel ve çapraz derleyiciler, Visual Studio bir 64-bit Windows işletim sisteminde yüklü olduğunda kullanılabilir. Bu komut istemlerine Windows 10'na erişmek için **Başlat** menüsünde, Visual Studio sürümünüze örneğin yapıtlarını **Visual Studio 2017**ve yerel veya çapraz aracı x64 birini seçin Geliştirici komut istemleri. Windows 8'de, bu komut istemlerine'na erişmek için **Başlat** ekran, açık **tüm uygulamalar**. Visual Studio yüklü sürümü başlığı altında açmak **Visual Studio** klasörü (Visual Studio'nun daha eski sürümleri adlandırılabilir **Visual Studio Araçları**). Önceki Windows sürümlerinde seçin **Başlat**, genişletin **tüm programlar**, sürümünüz için klasör **Visual Studio** (ve eski sürümleri, Visual Studio  **Visual Studio Araçları**). Daha fazla bilgi için bkz: [Geliştirici komut istemi kısayolları](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts).  
  
## <a name="use-vcvarsallbat-to-set-a-64-bit-hosted-build-architecture"></a>Bir 64-bit barındırılan yapı mimarisi ayarlamak için Vcvarsall.bat kullanın
  
Herhangi bir yerel veya vcvarsall.bat çalıştırarak komut satırında derleme yapılandırmaları kullanılabilir derleyici araçları Çapraz Dosya komutu. Bu komut dosyası yolu yapılandırır ve var olan bir komut istemi penceresinde mimarisi belirli bir etkinleştirme ortam değişkenleri oluşturun. Ayrıntılı yönergeler için bkz: [Geliştirici komut dosyaları ve konumları](../build/building-on-the-command-line.md#developer_command_files) .  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++’ı 64 bit, x64 hedefler için yapılandırma](../build/configuring-programs-for-64-bit-visual-cpp.md)