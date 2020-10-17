---
title: 'İzlenecek yol: Visual Studio C++ projesi oluşturmak için MSBuild kullanma'
description: Sıfırdan bir komut satırı MSBuild C++. vcxproj projesinin nasıl oluşturulacağını gösteren bir izlenecek yol.
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), walkthrough: create a project'
ms.openlocfilehash: 4f17cd8c4f5f48d8be5cd7cb25940db87029e111
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099738"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma

Bu izlenecek yol, bir Visual Studio C++ projesi oluşturmak için bir komut isteminde MSBuild 'in nasıl kullanılacağını gösterir. *`.vcxproj`* Bir Visual C++ konsol uygulaması IÇIN XML tabanlı proje dosyası oluşturmayı öğreneceksiniz. Projeyi oluşturduktan sonra, yapı sürecini özelleştirmeyi öğreneceksiniz.

> [!IMPORTANT]
> Daha sonra Visual Studio IDE 'yi kullanarak proje dosyasını düzenlemek istiyorsanız bu yaklaşımı kullanmayın. Bir *`.vcxproj`* dosyayı el ile oluşturursanız, özellikle proje proje öğelerinde joker karakter kullanıyorsa, Visual STUDIO IDE onu düzenleyemeyebilir veya yükleyemeyebilir. Daha fazla bilgi için bkz. [ `.vcxproj` ve `.props` dosya yapısı](./reference/vcxproj-file-structure.md) ve [ `.vcxproj` Dosyalar ve joker karakterler](./reference/vcxproj-files-and-wildcards.md).

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Projeniz için C++ kaynak dosyaları oluşturma.

- XML MSBuild proje dosyası oluşturuluyor.

- Projenizi derlemek için MSBuild 'i kullanma.

- Projenizi özelleştirmek için MSBuild 'i kullanma.

## <a name="prerequisites"></a>Ön koşullar

Bu yönergeyi tamamlamak için şu önkoşullara ihtiyacınız vardır:

- C++ iş yükünün yüklü olduğu **masaüstü geliştirme** Ile Visual Studio 'nun bir kopyası.

- MSBuild sisteminin genel olarak anlaşılmasıdır.

::: moniker range="vs-2015"

> [!NOTE]
> Alt düzey derleme yönergelerinin çoğu, *`.targets`* *`.props`* özelliğinde depolanan varsayılan hedefler klasörü altında tanımlanan ve dosyalarında bulunur `$(VCTargetsPath)` . Gibi dosyaları burada bulabilirsiniz *`Microsoft.Cpp.Common.props`* . Visual Studio 2015 ve önceki sürümlerde bu dosyalar için varsayılan yol altındadır *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

::: moniker range="vs-2017"

> [!NOTE]
> Alt düzey derleme yönergelerinin çoğu, *`.targets`* *`.props`* özelliğinde depolanan varsayılan hedefler klasörü altında tanımlanan ve dosyalarında bulunur `$(VCTargetsPath)` . Gibi dosyaları burada bulabilirsiniz *`Microsoft.Cpp.Common.props`* . Bu dosyalar için varsayılan yol, Visual Studio 2017 ' de bulunur *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* . Visual Studio 2015 ve önceki sürümleri, altında depolanır *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

::: moniker range=">=vs-2019"

> [!NOTE]
> Alt düzey derleme yönergelerinin çoğu, *`.targets`* *`.props`* özelliğinde depolanan varsayılan hedefler klasörü altında tanımlanan ve dosyalarında bulunur `$(VCTargetsPath)` . Gibi dosyaları burada bulabilirsiniz *`Microsoft.Cpp.Common.props`* . Bu dosyalar için varsayılan yol altında bulunur *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`* . `<version>`Yol öğesi, Visual Studio 'nun sürümüne özgüdür. *`v160`* Visual Studio 2019 içindir. Visual Studio 2017, bu dosyaları altında saklı *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`* . Visual Studio 2015 ve önceki sürümleri, altında depolanır *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\`* .

::: moniker-end

## <a name="create-the-c-source-files"></a>C++ kaynak dosyalarını oluşturma

Bu kılavuzda, kaynak dosyasına ve başlık dosyasına sahip bir proje oluşturacaksınız. Kaynak dosya *`main.cpp`* `main` konsol uygulaması için işlevi içerir. Üst bilgi dosyası *`main.h`* başlık dosyasını içerecek kodu içerir *`<iostream>`* . Bu C++ dosyalarını, Visual Studio veya Visual Studio Code gibi bir metin düzenleyicisi kullanarak oluşturabilirsiniz.

### <a name="to-create-the-c-source-files-for-your-project"></a>Projeniz için C++ kaynak dosyalarını oluşturmak için

1. Projeniz için bir klasör oluşturun.

1. Adlı bir dosya oluşturun *`main.cpp`* ve bu kodu dosyaya ekleyin:

    ```cpp
    // main.cpp : the application source code.
    #include <iostream>
    #include "main.h"
    int main()
    {
       std::cout << "Hello, from MSBuild!\n";
       return 0;
    }
    ```

1. Adlı bir dosya oluşturun *`main.h`* ve bu kodu dosyaya ekleyin:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild proje dosyası oluşturuluyor

MSBuild proje dosyası, bir proje kök öğesi () içeren bir XML dosyasıdır `<Project>` . Oluşturacağınız örnek projede, `<Project>` öğe yedi alt öğe içerir:

- `<ItemGroup>`Proje yapılandırmasını ve platformunu, kaynak dosya adını ve üstbilgi dosyası adını belirten üç öğe grubu etiketi ().

- Microsoft Visual C++ ayarlarının konumunu belirten üç içeri aktarma etiketi ( `<Import>` ).

- Proje ayarlarını belirten bir özellik grubu etiketi ( `<PropertyGroup>` ).

### <a name="to-create-the-msbuild-project-file"></a>MSBuild proje dosyası oluşturmak için

1. Adlı bir proje dosyası oluşturmak için bir metin düzenleyicisi kullanın *`myproject.vcxproj`* ve ardından `<Project>` burada gösterilen kök öğeyi ekleyin. (Visual Studio 2015 kullanıyorsanız, Visual Studio `ToolsVersion="14.0"` 2017 kullanıyorsanız `ToolsVersion="15.0"` veya `ToolsVersion="16.0"` Visual Studio 2019 kullanıyorsanız kullanın.)

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

   Kök Etiketler arasındaki sonraki yordam adımlarındaki öğeleri ekleyin `<Project>` .

1. Bu iki `<ProjectConfiguration>` alt öğeyi bir öğesine ekleyin `<ItemGroup>` . Alt öğe, 32 bitlik bir Windows işletim sistemi için hata ayıklama ve sürüm yapılandırması belirtir:

    ```xml
    <ItemGroup>
      <ProjectConfiguration Include="Debug|Win32">
        <Configuration>Debug</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
      <ProjectConfiguration Include="Release|Win32">
        <Configuration>Release</Configuration>
        <Platform>Win32</Platform>
      </ProjectConfiguration>
    </ItemGroup>
    ```

1. `<Import>`Bu proje için varsayılan C++ ayarlarının yolunu belirten bir öğe ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. `<PropertyGroup>`İki proje özelliği ve ' ı belirten bir özellik grubu öğesi () `<ConfigurationType>` ekleyin `<PlatformToolset>` . (Visual Studio 2015 kullanıyorsanız, Visual Studio `v140` `<PlatformToolset>` 2017 kullanıyorsanız `v141` veya Visual Studio 2019 kullanıyorsanız, bu değeri olarak kullanın `v142` .)

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. `<Import>`Bu proje için geçerli C++ ayarlarının yolunu belirten bir öğe ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. `<ClCompile>`Bir öğeye alt öğe ekleyin `<ItemGroup>` . Alt öğe, Derlenecek C/C++ kaynak dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>` , bir *derleme hedefidir* ve varsayılan hedefler klasöründe tanımlanmıştır.

1. `<ClInclude>`Bir öğeye alt öğe ekleyin `<ItemGroup>` . Alt öğesi C/C++ kaynak dosyası için üst bilgi dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. `<Import>`Bu proje için hedefi tanımlayan dosyanın yolunu belirten bir öğe ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Proje dosyasını doldurun

Bu kod, önceki yordamda oluşturduğunuz tüm proje dosyasını gösterir. ( `ToolsVersion="15.0"` Visual studio 2017 için veya `ToolsVersion="14.0"` visual Studio 2015 için kullanın.)

```xml
<Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup>
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
  <PropertyGroup>
    <ConfigurationType>Application</ConfigurationType>
    <PlatformToolset>v142</PlatformToolset>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ItemGroup>
    <ClCompile Include="main.cpp" />
  </ItemGroup>
  <ItemGroup>
    <ClInclude Include="main.h" />
  </ItemGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
</Project>
```

## <a name="using-msbuild-to-build-your-project"></a>Projenizi derlemek için MSBuild 'i kullanma

Konsol uygulamanızı derlemek için komut isteminde şu komutu girin:

> `msbuild myproject.vcxproj /p:configuration=debug`

MSBuild, çıkış dosyaları için bir klasör oluşturur ve ardından projeyi derlemek ve bir program oluşturmak için bağlar *`Myproject.exe`* . Oluşturma işlemi bittikten sonra, uygulamayı hata ayıklama klasöründen çalıştırmak için bu komutu kullanın:

> `myproject`

Uygulamanın "Merhaba, MSBuild!" görüntülemesi gerekir Konsol penceresinde.

## <a name="customizing-your-project"></a>Projenizi özelleştirme

MSBuild, önceden tanımlanmış derleme hedeflerini çalıştırmanızı, Kullanıcı tanımlı özellikleri uygulamanızı ve özel araçları, olayları ve derleme adımlarını kullanmanızı sağlar. Bu bölümde bu görevler gösterilmektedir:

- Yapı hedefleri ile MSBuild 'i kullanma.

- Yapı özellikleriyle MSBuild 'i kullanma.

- 64 bitlik derleyici ve araçlarla MSBuild 'i kullanma.

- Farklı araç kümeleriyle MSBuild 'i kullanma.

- MSBuild özelleştirmeleri ekleniyor.

### <a name="using-msbuild-with-build-targets"></a>Yapı hedefleri ile MSBuild kullanma

*Yapı hedefi* , derleme sırasında yürütülebilecek, önceden tanımlanmış veya Kullanıcı tanımlı komutların adlandırılmış bir kümesidir. **`/t`** Bir yapı hedefi belirtmek için target komut satırı seçeneğini () kullanın. `myproject`Örnek proje için, önceden tanımlanmış **`clean`** hedef, hata ayıklama klasöründeki tüm dosyaları siler ve yeni bir günlük dosyası oluşturur.

Komut isteminde, temizlemek için şu komutu girin `myproject` :

> `msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Yapı özellikleriyle MSBuild kullanma

Özellik komut satırı seçeneği (), `/p` proje derleme dosyanızdaki bir özelliği geçersiz kılmanıza olanak sağlar. `myproject`Örnek projede, yayın veya hata ayıklama derleme yapılandırması, özelliği tarafından belirtilir `Configuration` . Oluşturulan uygulamayı çalıştırmak için kullanacağınız işletim sistemi, özelliği tarafından belirtilir `Platform` .

Komut isteminde, `myproject` 32 bit Windows üzerinde çalıştırılacak uygulamanın hata ayıklama derlemesini oluşturmak için şu komutu girin:

> `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

`myproject`Örnek projenin 64 bitlik pencereler için de bir yapılandırma ve adlı özel bir işletim sistemi için başka bir yapılandırma tanımladığını varsayın `myplatform` .

Komut isteminde, 64 bit Windows üzerinde çalışan bir yayın derlemesi oluşturmak için şu komutu girin:

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

Komut isteminde, için bir yayın derlemesi oluşturmak üzere şu komutu girin `myplatform` :

> `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 bitlik derleyici ve araçlarla MSBuild kullanma

Visual Studio 'Yu 64 bit Windows üzerinde yüklediyseniz, 64 bit x64 yerel ve çapraz araçları varsayılan olarak yüklenir. MSBuild 'i, özelliği ayarlayarak uygulamanızı derlemek için 64 bit derleyicisini ve araçları kullanacak şekilde yapılandırabilirsiniz `PreferredToolArchitecture` . Bu özellik proje yapılandırma veya platform özelliklerini etkilemez. Varsayılan olarak, araçların 32 bit sürümü kullanılır. Derleyicinin ve araçların 64 bitlik sürümünü belirtmek için, dosya öğesinden sonra bu özellik grubu öğesini *`Myproject.vcxproj`* proje dosyasına ekleyin *`Microsoft.Cpp.default.props`* `<Import />` :

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Komut isteminde, uygulamanızı derlemek üzere 64 bitlik araçları kullanmak için şu komutu girin:

> `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Farklı bir araç kümesiyle MSBuild kullanma

Visual C++ diğer sürümleri için araç kümeleri ve kitaplıklar varsa, MSBuild, geçerli Visual C++ sürümü veya diğer yüklü sürümler için uygulama oluşturabilir. Örneğin, Visual Studio 2012 ' i yüklediyseniz, Windows XP için Visual C++ 11,0 araç takımını belirtmek üzere, bu özellik grubu öğesini *`Myproject.vcxproj`* Dosya öğesinden sonra proje dosyasına ekleyin *`Microsoft.Cpp.props`* `<Import />` :

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Projenizi Visual C++ 11,0 Windows XP araç takımı ile yeniden oluşturmak için şu komutu girin:

> `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild özelleştirmeleri ekleme

MSBuild, yapı işleminizi özelleştirmek için çeşitli yollar sağlar. Bu makalelerde, MSBuild projenize özel derleme adımları, Araçlar ve olayların nasıl ekleneceği gösterilmektedir:

- [Nasıl yapılır: MSBuild projelerine özel derleme adımı ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Nasıl yapılır: MSBuild projelerine özel derleme araçları ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Nasıl yapılır: MSBuild projelerinde derleme olaylarını kullanma](how-to-use-build-events-in-msbuild-projects.md)
