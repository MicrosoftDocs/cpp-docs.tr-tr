---
description: Visual Studio projelerinde Clang/LLVM desteği hakkında daha fazla bilgi edinin
title: Visual Studio projelerinde Clang/LLVM desteği
ms.date: 02/05/2021
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 7492d2c75e458fb4a8a94e009f40b49edf1a8204
ms.sourcegitcommit: 77235bff6a7b2621c501938e30d93cb15f5733cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2021
ms.locfileid: "100006054"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio projelerinde Clang/LLVM desteği

::: moniker range="<=msvc-150"

CMake ve MSBuild projelerinin her ikisi için de Clang desteği Visual Studio 2019 'de bulunabilir.

::: moniker-end

::: moniker range="msvc-160"

Windows veya Linux 'u hedefleyen C++ Visual Studio projelerini (MSBuild) düzenlemek, derlemek ve hatalarını ayıklamak için Visual Studio 2019 sürüm 16,2 ile Clang kullanabilirsiniz.

## <a name="install"></a>Yükleme

Visual Studio 'da en iyi IDE desteği için, Windows için en son Clang derleyicisi araçlarını kullanmanızı öneririz. Zaten araçlar yoksa, Visual Studio Yükleyicisi açarak ve C++ isteğe bağlı bileşenleriyle **masaüstü geliştirme** altında **Windows Için c++ Clang araçları** ' nı seçerek yükleyebilirsiniz. Makinenizde var olan bir Clang yüklemesini kullanmayı tercih edebilirsiniz; Bu durumda, **v142 derleme araçları için C++ Clang-CL** ' yi seçin. isteğe bağlı bileşen.

Microsoft C++ standart kitaplığı şu anda en az Clang 8.0.0 gerektirir. Clang 'nin paketlenmiş sürümü, standart kitaplığın Microsoft uygulamasındaki güncelleştirmelerle güncel kalmak için otomatik olarak güncelleştirilir.

![Visual Studio yükleyicisi 'nin ayrı bileşenler sekmesi seçili ve C Plus Plus Clang bileşenleri görünür ekran görüntüsü.](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang araçlarını kullanmak için bir Windows projesi yapılandırma

Bir Visual Studio projesini Clang kullanacak şekilde yapılandırmak için, **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. Genellikle, ilk olarak iletişim kutusunun en üstündeki **tüm yapılandırma** ' yı seçmeniz gerekir. Ardından, **genel**  >  **platform araç takımı** altında **LLVM (Clang-CL)** öğesini ve ardından **Tamam**' ı seçin.

![Yapılandırma özellikleri > genel seçili ve platform araç kümesi ve L L V M (Clang c l) seçenekleri vurgulanmış şekilde Özellik sayfaları iletişim kutusunun ekran görüntüsü.](media/clang-msbuild-prop-page.png)

Visual Studio ile paketlenmiş Clang araçlarını kullanıyorsanız ek bir adım gerekmez. Windows projeleri için, Visual Studio varsayılan olarak [Clang-CL](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modunda Clang 'i çağırır. Standart kitaplığın Microsoft uygulamasıyla bağlantı oluşur. Varsayılan olarak, **clang-cl.exe** *% VCInstallDir% \\ araçları \\ LLVM \\ \\ bin* ve *% VCInstallDir% \\ Tools \\ LLVM \\ x64 \\ bin \\* konumunda bulunur.

Özel bir Clang yüklemesi kullanıyorsanız,   >    >  ilk dizin olarak özel Clang yükleme kökünü ekleyerek veya özelliğin değerini değiştirerek Proje özellikleri **VC + + dizinlerin**  >  **yapılandırma özellikleri**  >  **yürütülebilir dizinlerini** değiştirebilirsiniz `LLVMInstallDir` . Daha fazla bilgi için bkz. [Özel BIR LLVM konumu ayarlama](#custom_llvm_location).

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang araçlarını kullanmak için bir Linux projesi yapılandırma

Linux projeleri için, Visual Studio Clang GCC ile uyumlu ön uç 'yi kullanır. Proje özellikleri ve neredeyse tüm derleyici bayrakları aynıdır

Bir Visual Studio Linux projesini Clang kullanacak şekilde yapılandırmak için:

1. **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin.
1. Genellikle, ilk olarak iletişim kutusunun en üstündeki **tüm yapılandırma** ' yı seçmeniz gerekir.
1.   >  Linux için Windows alt kümesi (WSL) kullanıyorsanız, genel **platform araç takımı** altında **WSL_Clang_1_0** öğesini seçin. Uzak makine veya VM kullanıyorsanız **Remote_Clang_1_0** seçin.
1. **Tamam**'a basın.

![Konsol uygulaması Clang Visual Studio 2019 Özellik sayfaları iletişim kutusunun yapılandırma özellikleri > genel seçili ve platform araç takımı ve L L V M (Clang c l) seçenekleri vurgulanmış ekran görüntüsü.](media/clang-msbuild-prop-page.png)

Linux 'ta, Visual Studio varsayılan olarak PATH Environment özelliğinde bulduğu ilk Clang konumunu kullanır. Özel bir Clang yüklemesi kullanıyorsanız, özelliğin değerini değiştirin `LLVMInstallDir` ya da **Proje**  >  **özellikleri**  >  **yapılandırma özellikleri**  >  **VC + + dizinleri**  >  **yürütülebilir dizinleri** altına bir yol girin. Daha fazla bilgi için bkz. [Özel BIR LLVM konumu ayarlama](#custom_llvm_location).

## <a name="set-a-custom-llvm-location"></a><a name="custom_llvm_location"></a> Özel bir LLVM konumu ayarlama

Bir veya daha fazla proje için, bir *Dizin. Build. props* dosyası oluşturarak LLVM 'ye özel bir yol ayarlayabilirsiniz. Ardından, bu dosyayı herhangi bir projenin kök klasörüne ekleyin. Bunu Çözümdeki tüm projelere uygulamak için kök çözüm klasörüne ekleyebilirsiniz. Dosya şuna benzemelidir (ancak gerçek LLVM yolunu kullanın):

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>C:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

Bu özelliği özel bir LLVM araç takımı sürümü ile birleştirebilirsiniz. Daha fazla bilgi için bkz. [özel LLVM araç takımı sürümü ayarlama](#custom_llvm_toolset).

## <a name="set-a-custom-llvm-toolset-version"></a><a name="custom_llvm_toolset"></a> Özel bir LLVM araç takımı sürümü ayarla

Visual Studio 2019 sürüm 16,9 ' den başlayarak, LLVM için özel bir araç takımı sürümü ayarlayabilirsiniz. Visual Studio 'da bir projede bu özelliği ayarlamak için:

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](./working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **genel** özellik sayfasını seçin.

1. **Platform araç takımı** özelliğini, zaten ayarlanmamışsa, *LLVM (Clang-CL)* olarak değiştirin.

1. **Yapılandırma özellikleri** > **Gelişmiş** özellik sayfasını seçin.

1. **LLVM araç takımı sürümü** özelliğini tercih ettiğiniz sürümle değiştirin ve ardından değişikliklerinizi kaydetmek için **Tamam** ' ı seçin.

**LLVM araç kümesi sürümü** özelliği yalnızca LLVM platform araç kümesi seçildiğinde görüntülenir.

Bir veya daha fazla projenin araç kümesi sürümünü bir *Dizin. Build. props* dosyası oluşturarak ayarlayabilirsiniz. Ardından, bu dosyayı herhangi bir projenin kök klasörüne ekleyin. Bunu Çözümdeki tüm projelere uygulamak için kök çözüm klasörüne ekleyin. Dosya şuna benzemelidir (ancak gerçek LLVM yolunu kullanın):

```xml
<Project>
  <PropertyGroup>
    <LLVMToolsVersion>11.0.0</LLVMToolsVersion>
  </PropertyGroup>
</Project>
```

Ayrıca, bu özelliği özel bir LLVM konumu ile birleştirebilirsiniz. Örneğin, *dizininiz. Build. props* dosyanız şu şekilde görünebilir:

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>C:\MyLLVMRootDir</LLVMInstallDir>
    <LLVMToolsVersion>11.0.0</LLVMToolsVersion>
  </PropertyGroup>
</Project>
```

Bir *Dizin. Build. props* dosyası eklediğinizde, ayarlar proje özellik sayfaları iletişim kutusunda varsayılan olarak görünür. Ancak, Visual Studio 'daki bu özelliklerde yapılan değişiklikler *Directory. Build. props* dosyasındaki ayarları geçersiz kılar.

## <a name="set-additional-properties-edit-build-and-debug"></a>Ek özellikler ayarlama, düzenleme, derleme ve hata ayıklama

Bir Clang yapılandırması ayarladıktan sonra proje düğümünde tekrar sağ tıklayın ve **projeyi yeniden yükle**' yi seçin. Artık Clang araçlarını kullanarak projeyi derleyebilir ve hata ayıklayabilirsiniz. Visual Studio, Clang derleyicisini kullandığınızı algılar ve IntelliSense, vurgulama, gezinme ve diğer düzen özelliklerini sağlar. Hatalar ve uyarılar **Çıkış penceresi** görüntülenir. Clang yapılandırması için proje özellik sayfaları, MSVC için olanlarla benzerdir. Ancak, Clang yapılandırmalarında Düzenle ve devam et gibi bazı derleyiciye bağımlı özellikler kullanılamaz. Özellik sayfalarında kullanılamayan bir Clang derleyicisi veya bağlayıcı seçeneği belirleyebilirsiniz. **Yapılandırma özellikleri**  >  **C/C++ (veya bağlayıcı)**  >  **komut satırı**  >  **ek seçenekleri** altındaki özellik sayfalarına el ile ekleyin.

Hata ayıklama sırasında kesme noktaları, bellek ve veri görselleştirme ve diğer birçok hata ayıklama özelliği kullanabilirsiniz.  

![Clang hata ayıklaması](media/clang-debug-msbuild.png)

::: moniker-end
