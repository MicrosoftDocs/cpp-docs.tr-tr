---
title: Visual Studio Visual Studio projelerinde Clang/LLVM desteği
ms.date: 08/30/2019
ms.description: Configure a Visual Studio MSBuild project to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ MSBuild projects
ms.openlocfilehash: 819f96bf2fd949f80ae72ca878ba7eb9cb1bffcc
ms.sourcegitcommit: c3283062ce4e382aec7f11626d358a37caf8cdbb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/13/2020
ms.locfileid: "75914359"
---
# <a name="clangllvm-support-in-visual-studio-projects"></a>Visual Studio projelerinde Clang/LLVM desteği

::: moniker range="<=vs-2017"

CMake ve MSBuild projelerinin her ikisi için de Clang desteği Visual Studio 2019 'de bulunabilir.

::: moniker-end

::: moniker range="vs-2019"

Windows veya Linux 'u hedefleyen Visual Studio projelerini (MSBuild) düzenlemek, derlemek ve hatalarını ayıklamak C++ Için visual Studio 2019 sürüm 16,2 Ile Clang kullanabilirsiniz.

## <a name="install"></a>yükleme

Visual Studio 'da en iyi IDE desteği için, Windows için en son Clang derleyicisi araçlarını kullanmanızı öneririz. Henüz yoksa, Visual Studio yükleyicisi açarak ve isteğe bağlı bileşenlerle **masaüstü geliştirme C++**  altında  **C++ Windows için Clang araçları** ' nı seçerek yükleyebilirsiniz. Makinenizde var olan bir Clang yüklemesini kullanmayı tercih ediyorsanız,  **C++ v142 derleme araçları için Clang-CL ' yi seçin.** isteğe bağlı bileşen. Microsoft C++ standart kitaplığı şu anda en az Clang 8.0.0 gerektirir. Standart kitaplığın Microsoft uygulamasındaki güncelleştirmelerle güncel kalmak için Clang 'nin paketlenmiş sürümü otomatik olarak güncelleştirilir. 

![Clang bileşeni yüklemesi](media/clang-install-vs2019.png)

## <a name="configure-a-windows-project-to-use-clang-tools"></a>Clang araçlarını kullanmak için bir Windows projesi yapılandırma

Bir Visual Studio projesini Clang kullanacak şekilde yapılandırmak için, **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. Genellikle, ilk olarak iletişim kutusunun en üstündeki **tüm yapılandırma** ' yı seçmeniz gerekir. Ardından, **genel** > **platform araç takımı**altında **LLVM (Clang-CL)** öğesini seçin ve ardından **Tamam**' ı seçin.

![Clang bileşeni yüklemesi](media/clang-msbuild-prop-page.png)

Visual Studio ile paketlenmiş Clang araçlarını kullanıyorsanız ek bir adım gerekmez. Windows projeleri için, Visual Studio varsayılan olarak Clang [-CL](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modunda Clang 'Yi ve standart kitaplığın Microsoft uygulamasını içeren bağlantıları çağırır. Varsayılan olarak, **Clang-CL. exe** `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`' de bulunur.

Özel bir Clang yüklemesi kullanıyorsanız, ilk dizin olarak özel Clang yükleme kökünü ekleyerek veya `LLVMInstallDir` özelliğinin değerini değiştirerek, **proje** > **özellikleri** > **VC + + dizinleri** > **yapılandırma özellikleri** > **çalıştırılabilir dizinler** ' i değiştirebilirsiniz. Daha fazla bilgi için bkz. [özel LLVM konumu ayarlama](#custom_llvm_location) .

## <a name="configure-a-linux-project-to-use-clang-tools"></a>Clang araçlarını kullanmak için bir Linux projesi yapılandırma

Linux projeleri için, Visual Studio Clang GCC ile uyumlu ön uç 'yi kullanır. Proje özellikleri ve neredeyse tüm derleyici bayrakları aynıdır

Bir Visual Studio Linux projesini Clang kullanacak şekilde yapılandırmak için:

1. **Çözüm Gezgini** ' de proje düğümüne sağ tıklayın ve **Özellikler**' i seçin. 
1. Genellikle, ilk olarak iletişim kutusunun en üstündeki **tüm yapılandırma** ' yı seçmeniz gerekir. 
1. **Genel** > **platform araç takımı**altında, Linux için Windows alt sistemi kullanıyorsanız veya uzak bır makine ya da VM kullanıyorsanız **Remote_Clang_1_0** **WSL_Clang_1_0** seçin.
1. Tuşuna **Tamam**.

![Clang bileşeni yüklemesi](media/clang-msbuild-prop-page.png)

Linux 'ta, Visual Studio varsayılan olarak PATH Environment özelliğinde karşılaştığı ilk Clang konumunu kullanır. Özel bir Clang yüklemesi kullanıyorsanız, `LLVMInstallDir` özelliğinin değerini değiştirmeniz veya **Project** > **Properties** > **VC + + dizinleri** > **yapılandırma özellikleri** > **çalıştırılabilir dizinler**altında bir yol yerine konacak olması gerekir. Daha fazla bilgi için bkz. [özel LLVM konumu ayarlama](#custom_llvm_location) .

## <a name="custom_llvm_location"></a>Özel bir LLVM konumu ayarlama

Bir veya daha fazla proje için, bir *Dizin. Build. props* dosyası oluşturarak ve bu dosyayı herhangi bir projenin kök klasörüne ekleyerek LLVM için özel bir yol ayarlayabilirsiniz. Bunu Çözümdeki tüm projelere uygulamak için kök çözüm klasörüne ekleyebilirsiniz. Dosya şuna benzemelidir (ancak gerçek yolunu yerine koyun):

```xml
<Project>
  <PropertyGroup>
    <LLVMInstallDir>c:\MyLLVMRootDir</LLVMInstallDir>
  </PropertyGroup>
</Project>
```

## <a name="set-additional-properties-edit-build-and-debug"></a>Ek özellikler ayarlama, düzenleme, derleme ve hata ayıklama

Bir Clang yapılandırması ayarladıktan sonra proje düğümünde tekrar sağ tıklayın ve **projeyi yeniden yükle**' yi seçin. Artık Clang araçlarını kullanarak projeyi derleyebilir ve hata ayıklayabilirsiniz. Visual Studio, Clang derleyicisini kullandığınızı algılar ve IntelliSense, vurgulama, gezinme ve diğer düzen özelliklerini sağlar. Hatalar ve uyarılar **Çıkış penceresi**görüntülenir. Clang yapılandırması için proje özellik sayfaları, MSVC için bunlara benzerdir, ancak Düzenle ve devam et gibi bazı derleyiciye bağımlı özellikler Clang yapılandırmaları için kullanılamaz. Özellik sayfalarında kullanılamayan bir Clang derleyicisini veya bağlayıcı seçeneğini ayarlamak için, **yapılandırma özellikleri** altındaki özellik sayfalarına > **C/C++ (veya bağlayıcı)**  > **komut satırı** > **ek seçenekler**' e el ile ekleyebilirsiniz.

Hata ayıklama sırasında kesme noktaları, bellek ve veri görselleştirme ve diğer birçok hata ayıklama özelliği kullanabilirsiniz.  

![Clang hata ayıklaması](media/clang-debug-msbuild.png)

::: moniker-end
