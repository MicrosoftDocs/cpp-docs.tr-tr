---
title: 'İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma'
ms.date: 05/16/2019
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
ms.openlocfilehash: c93867f3be3b17f703c549aa5c05f3d327934c26
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417189"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma

Bu izlenecek yol, bir komut isteminde Visual Studio C++ projesi oluşturmak için MSBuild 'in nasıl kullanılacağını gösterir. C++ kaynak dosyalarını ve bir Visual C++ konsol uygulaması için XML tabanlı bir proje dosyasını oluşturmayı öğreneceksiniz. Projeyi oluşturduktan sonra, yapı sürecini özelleştirmeyi öğreneceksiniz.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Projeniz için C++ kaynak dosyaları oluşturma.

- XML MSBuild proje dosyası oluşturuluyor.

- Projenizi derlemek için MSBuild 'i kullanma.

- Projenizi özelleştirmek için MSBuild 'i kullanma.

## <a name="prerequisites"></a>Ön koşullar

Bu yönergeyi tamamlamak için aşağıdakilere ihtiyacınız vardır:

- C++ iş yükünün yüklü olduğu **masaüstü geliştirme** Ile Visual Studio 'nun bir kopyası.

- MSBuild sisteminin genel olarak anlaşılmasıdır.

> [!NOTE]
> Daha sonra Visual Studio IDE 'yi kullanarak proje dosyasını düzenlemek istiyorsanız bu yaklaşımı kullanmayın. . Vcxproj dosyasını el ile oluşturursanız, özellikle proje proje öğelerinde joker karakterler kullanıyorsa, Visual Studio IDE bu dosyayı düzenleyemeyebilir veya yükleyemeyebilir.

> [!NOTE]
> Alt düzey derleme yönergelerinin çoğu, özelliğinde `$(VCTargetsPath)`depolanan vctargets dizininde tanımlanan **. targets** ve **. props** dosyalarında yer alır. Visual Studio 2019 Enterprise Edition 'da bu dosyalar için varsayılan yol C:\Program Files (x86) \Microsoft Visual Studio\2019\Enterprise\MSBuild\Microsoft\VC\v160\Microsoft.Cpp.Common.props.

## <a name="creating-the-c-source-files"></a>C++ kaynak dosyalarını oluşturma

Bu kılavuzda, kaynak dosyasına ve başlık dosyasına sahip bir proje oluşturacaksınız. Main. cpp kaynak dosyası konsol uygulaması için Main işlevini içerir. Ana. h üstbilgi dosyası iostream üstbilgi dosyasını içerecek kodu içerir. Bu C++ dosyalarını, Visual Studio veya Visual Studio Code gibi bir metin düzenleyicisi kullanarak oluşturabilirsiniz.

### <a name="to-create-the-c-source-files-for-your-project"></a>Projeniz için C++ kaynak dosyalarını oluşturmak için

1. Projeniz için bir dizin oluşturun.

1. Main. cpp adlı bir dosya oluşturun ve bu dosyaya aşağıdaki kodu ekleyin:

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

1. Main. h adlı bir dosya oluşturun ve bu dosyaya aşağıdaki kodu ekleyin:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild proje dosyası oluşturuluyor

MSBuild proje dosyası, bir proje kök öğesi (`<Project>`) IÇEREN bir XML dosyasıdır. Aşağıdaki örnek projede, `<Project>` öğesi yedi alt öğe içerir:

- Proje yapılandırmasını ve platformunu,`<ItemGroup>`kaynak dosya adını ve üstbilgi dosyası adını belirten üç öğe grubu etiketi ().

- Microsoft Visual C++ ayarlarının konumunu belirten`<Import>`üç içeri aktarma etiketi ().

- Proje ayarlarını belirten bir özellik`<PropertyGroup>`grubu etiketi ().

### <a name="to-create-the-msbuild-project-file"></a>MSBuild proje dosyası oluşturmak için

1. Adlı `myproject.vcxproj`bir proje dosyası oluşturmak için bir metin düzenleyicisi kullanın ve ardından aşağıdaki kök `<Project>` öğeyi ekleyin. Kök `<Project>` Etiketler arasındaki aşağıdaki yordam adımlarında öğeleri ekleyin. (Visual Studio 2019 kullanıyorsanız, Visual Studio 2017 veya araçları sürümü = "16.0" kullanıyorsanız, araçları sürümü = "15.0" kullanın.)

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="16.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

1. Aşağıdaki iki `<ProjectConfiguration>` alt öğeyi bir `<ItemGroup>` öğesine ekleyin. Alt öğe, 32 bitlik bir Windows işletim sistemi için hata ayıklama ve sürüm yapılandırması belirtir:

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

1. Bu proje için `<Import>` varsayılan C++ ayarlarının yolunu belirten aşağıdaki öğeyi ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

1. İki proje özelliği belirten aşağıdaki özellik grubu`<PropertyGroup>`öğesini () ekleyin. (Visual Studio 2019 kullanıyorsanız, Visual Studio 2017 veya v142 kullanıyorsanız v141 kullanın.)

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v142</PlatformToolset>
    </PropertyGroup>
    ```

1. Bu proje için `<Import>` geçerli C++ ayarlarının yolunu belirten aşağıdaki öğeyi ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

1. Aşağıdaki `<ClCompile>` alt öğeyi bir `<ItemGroup>` öğesine ekleyin. Alt öğe, Derlenecek C/C++ kaynak dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > `<ClCompile>`, bir *derleme hedefidir* ve **vctargets** dizininde tanımlanmıştır.

1. Aşağıdaki `<ClInclude>` alt öğeyi bir `<ItemGroup>` öğesine ekleyin. Alt öğesi C/C++ kaynak dosyası için üst bilgi dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

1. Bu proje için `<Import>` hedefi tanımlayan dosyanın yolunu belirten aşağıdaki öğeyi ekleyin:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Proje dosyasını doldurun

Aşağıdaki kod, önceki yordamda oluşturduğunuz tüm proje dosyalarını gösterir. (Visual Studio 2017 için, araçları sürümü = "15.0" kullanın.)

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

Konsol uygulamanızı derlemek için komut istemine aşağıdaki komutu yazın:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild, çıkış dosyaları için bir dizin oluşturur ve ardından projenizi derleyen ve MyProject. exe programını oluşturacak şekilde bağlar. Oluşturma işlemi bittikten sonra, hata ayıklama klasöründen uygulamayı çalıştırmak için aşağıdaki komutu kullanın:

`myproject`

Uygulamanın "Merhaba, MSBuild!" görüntülemesi gerekir Konsol penceresinde.

## <a name="customizing-your-project"></a>Projenizi özelleştirme

MSBuild, önceden tanımlanmış derleme hedeflerini çalıştırmanızı, Kullanıcı tanımlı özellikleri uygulamanızı ve özel araçları, olayları ve derleme adımlarını kullanmanızı sağlar. Bu bölüm aşağıdaki görevleri gösterir:

- Yapı hedefleri ile MSBuild 'i kullanma.

- Yapı özellikleriyle MSBuild 'i kullanma.

- 64 bitlik derleyici ve araçlarla MSBuild 'i kullanma.

- Farklı araç kümeleriyle MSBuild 'i kullanma.

- MSBuild özelleştirmeleri ekleniyor.

### <a name="using-msbuild-with-build-targets"></a>Yapı hedefleri ile MSBuild kullanma

*Yapı hedefi* , derleme sırasında yürütülebilecek, önceden tanımlanmış veya Kullanıcı tanımlı komutların adlandırılmış bir kümesidir. Bir yapı hedefi belirtmek için target komut satırı`/t`seçeneğini () kullanın. `myproject` Örnek proje için, önceden tanımlanmış **Temizleme** hedefi hata ayıklama klasöründeki tüm dosyaları siler ve yeni bir günlük dosyası oluşturur.

Komut isteminde, temizlemek `myproject`için aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Yapı özellikleriyle MSBuild kullanma

Özellik komut satırı seçeneği (`/p`), proje derleme dosyanızdaki bir özelliği geçersiz kılmanıza olanak sağlar. `myproject` Örnek projede, yayın veya hata ayıklama derleme yapılandırması, `Configuration` özelliği tarafından belirtilir. Ve oluşturulan uygulamayı çalıştırmak için tasarlanan işletim sistemi, `Platform` özelliği tarafından belirtilir.

Komut isteminde, 32 bit Windows üzerinde çalışması amaçlanan `myproject` uygulamanın hata ayıklama derlemesini oluşturmak için aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

`myproject` Örnek projenin 64 bitlik pencereler için de bir yapılandırma ve adlı `myplatform`özel bir işletim sistemi için başka bir yapılandırma tanımladığını varsayın.

Komut isteminde, 64 bit Windows üzerinde çalışan bir yayın derlemesi oluşturmak için aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

Komut isteminde, için `myplatform`bir yayın derlemesi oluşturmak üzere aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 bitlik derleyici ve araçlarla MSBuild kullanma

Visual Studio 'Yu 64 bit Windows üzerinde yüklediyseniz, varsayılan olarak 64 bit x64 yerel ve çapraz araçlar yüklenir. MSBuild 'i, `PreferredToolArchitecture` özelliği ayarlayarak uygulamanızı derlemek için 64 bit derleyicisini ve araçları kullanacak şekilde yapılandırabilirsiniz. Bu özellik proje yapılandırma veya platform özelliklerini etkilemez. Varsayılan olarak, araçların 32 bit sürümü kullanılır. Derleyicinin ve araçların 64 bitlik sürümünü belirtmek için, `Microsoft.Cpp.default.props` \<Import/> öğesinden sonra MyProject. vcxproj proje dosyasına aşağıdaki özellik grubu öğesini ekleyin:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Komut isteminde, uygulamanızı derlemek için 64 bitlik araçları kullanmak üzere aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Farklı bir araç kümesiyle MSBuild kullanma

Visual C++ diğer sürümleri için araç kümeleri ve kitaplıklar varsa, MSBuild, geçerli Visual C++ sürümü veya diğer yüklü sürümler için uygulama oluşturabilir. Örneğin, Visual Studio 2012 ' i yüklediyseniz, Windows XP için Visual C++ 11,0 araç takımını belirtmek üzere, `Microsoft.Cpp.props` \<Import/> öğesinden sonra MyProject. vcxproj proje dosyasına aşağıdaki özellik grubu öğesini ekleyin:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Projenizi Visual C++ 11,0 Windows XP araç takımı ile yeniden derlemek için aşağıdaki komutları yazın:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild özelleştirmeleri ekleme

MSBuild, yapı işleminizi özelleştirmek için çeşitli yollar sağlar. Aşağıdaki konularda, MSBuild projenize özel derleme adımlarının, araçların ve olayların nasıl ekleneceği gösterilmektedir:

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](how-to-use-build-events-in-msbuild-projects.md)
