---
title: Visual Studio Visual Studio projelerinde Clang/LLVM desteği
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 8d7d7fec979d3e7b8f665e56094ee1c309e3b686
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323116"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio projelerinde Clang/LLVM desteği

::: moniker range="<=vs-2017"

Hem CMake hem de MSBuild projeleri için Clang desteği Visual Studio 2019'da mevcuttur.

::: moniker-end

::: moniker range="vs-2019"

Windows veya Linux'u hedefleyen C++ Visual Studio projelerini (MSBuild) yeniden oluşturmak, oluşturmak ve hata ayıklamak için Clang ile Visual Studio 2019 sürüm 16.2'yi kullanabilirsiniz.

## <a name="install"></a>Yükleme

Visual Studio'da en iyi IDE desteği için, Windows için en son Clang derleyici araçlarını kullanmanızı öneririz. Bunlarzaten yoksa, Visual Studio Installer'ı açarak ve C++ isteğe bağlı **bileşenleriyle Masaüstü geliştirme** altında Windows için **C++ Clang araçlarını** seçerek bunları yükleyebilirsiniz. Makinenizde varolan bir Clang yüklemesini kullanmayı tercih ederseniz, **v142 yapı araçları için C++ Clang-cl'yi seçin.** isteğe bağlı bileşen. Microsoft C++ Standart Kitaplığı şu anda en az Clang 8.0.0 gerektirir; Clang'ın birlikte verilen sürümü, Standart Kitaplığın Microsoft uygulamasındaki güncelleştirmelerle güncel kalacak şekilde otomatik olarak güncelleştirilir.

![Clang bileşen kurulumu](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang araçlarını kullanacak şekilde bir Windows projesini yapılandırma

Clang'ı kullanacak bir Visual Studio projesini yapılandırmak için **Solution Explorer'daki** proje düğümüne sağ tıklayın ve **Özellikler'i**seçin. Genellikle, öncelikle iletişim kutusunun üst **kısmındaki Tüm yapılandırmaları** seçmeniz gerekir. Sonra, **Genel** > **Platform Araç Seti**altında, **LLVM (clang-cl) seçin** ve sonra **Tamam**.

![Clang bileşen kurulumu](media/clang-msbuild-prop-page.png)

Visual Studio ile birlikte verilen Clang araçlarını kullanıyorsanız, ek adımlar gerekmez. Windows projeleri için Visual Studio varsayılan olarak [Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modunda Clang'ı çağırır ve Standart Kitaplığın Microsoft uygulamasıyla bağlantı eder. Varsayılan olarak, **clang-cl.exe** `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`bulunur.

Özel bir Clang yüklemesi kullanıyorsanız, özel Clang yükleme kökünü buradaki ilk dizin olarak ekleyerek **Project** > **Properties** > **VC++ DIrectories** > Configuration**Properties** > **Executable Directories'i** değiştirebilir veya `LLVMInstallDir` özelliğin değerini değiştirebilirsiniz. Bkz. Daha fazla bilgi için [özel bir LLVM konumu ayarlama.](#custom_llvm_location)

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang araçlarını kullanacak bir Linux projesini yapılandırma

Visual Studio, Linux projeleri için Clang GCC uyumlu ön uç kullanır. Proje özellikleri ve hemen hemen tüm derleyici bayrakları aynıdır

Clang'ı kullanmak için visual studio Linux projesini yapılandırmak için:

1. **Çözüm Gezgini'ndeki** proje düğümüne sağ tıklayın ve **Özellikler'i**seçin.
1. Genellikle, öncelikle iletişim kutusunun üst **kısmındaki Tüm yapılandırmaları** seçmeniz gerekir.
1. **Genel** > **Platform Araç Seti**altında, Linux için Windows Alt Sistemi kullanıyorsanız **WSL_Clang_1_0** veya uzak bir makine veya VM kullanıyorsanız **Remote_Clang_1_0'yi** seçin.
1. **Tamam**'a basın.

![Clang bileşen kurulumu](media/clang-msbuild-prop-page.png)

Visual Studio, Linux'ta varsayılan olarak PATH ortamında karşılaştığı ilk Clang konumunu kullanır. Özel bir Clang yüklemesi `LLVMInstallDir` kullanıyorsanız, özelliğin değerini değiştirmeniz veya **Project** > **Properties** > **VC++ DIrectories** > Configuration**Properties** > **Executable Directories**altında bir yol değiştirmeniz gerekir. Bkz. Daha fazla bilgi için [özel bir LLVM konumu ayarlama.](#custom_llvm_location)

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a>Özel bir LLVM konumu ayarlama

*Bir Dizin.build.prop* dosyası oluşturarak ve bu dosyayı herhangi bir projenin kök klasörüne ekleyerek LLVM için bir veya daha fazla proje için özel bir yol ayarlayabilirsiniz. Çözümdeki tüm projelere uygulamak için kök çözüm klasörüne ekleyebilirsiniz. Dosya bu gibi görünmelidir (ancak gerçek yol unuzu değiştirin):

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>Ek özellikler ayarlama, ayarlama, oluşturma ve hata ayıklama

Bir Clang yapılandırması ayarladıktan sonra, proje düğümüne tekrar tıklayın ve **projeyi Yeniden Yükle'yi**seçin. Artık Clang araçlarını kullanarak projeyi oluşturabilir ve hata ayıklayabilirsiniz. Visual Studio, Clang derleyicisini kullandığınızı algılar ve IntelliSense, vurgulama, gezinme ve diğer düzenleme özellikleri sağlar. Hatalar ve uyarılar **Çıktı Penceresinde**görüntülenir. Clang yapılandırması için proje özelliği sayfaları, Düzenleme ve Devam gibi derleyiciye bağlı bazı özellikler Clang yapılandırmaları için kullanılamamasına rağmen, MSVC'ninkilere çok benzer. Özellik sayfalarında bulunmayan bir Clang derleyicisi veya bağlayıcı seçeneği ayarlamak için, **yapılandırma özellikleri** > **C/C++ (veya Bağlayıcı)** > Komut**Satırı** > Ek**Seçenekleri**altında özellik sayfalarında el ile ekleyebilirsiniz.

Hata ayıklama yaparken, kesme noktaları, bellek ve veri görselleştirme ve diğer çoğu hata ayıklama özelliklerini kullanabilirsiniz.  

![Clang hata ayıklama](media/clang-debug-msbuild.png)

::: moniker-end
