---
title: 'İzlenecek yol: Visual C++ projesi oluşturmak için MSBuild kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.walkthrough.createproject
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), walkthrough: create a project'
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2c5c3f7001a98572129baaf3ee35bb02b6458fd
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37041217"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma

Bu kılavuz, bir komut isteminde Visual C++ projesi oluşturmak için MSBuild kullanma gösterilmiştir. C++ kaynak dosyaları ve bir Visual C++ konsol uygulaması için bir XML tabanlı proje dosyası nasıl oluşturulacağını öğreneceksiniz. Proje oluşturduktan sonra yapı işlemini nasıl özelleştireceğinizi öğreneceksiniz.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Projeniz için C++ kaynak dosyaları oluşturuluyor.

- XML MSBuild proje dosyası oluşturma.

- Projenizi derleme için MSBuild kullanma.

- Projenizi özelleştirmek için MSBuild kullanma.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdakiler gerekir:

- Visual Studio ile bir kopyasını **C++ ile masaüstü geliştirme** yüklü iş yükü.

- MSBuild sistem genel bir anlayış.

> [!NOTE]
> Visual Studio IDE kullanarak proje dosyası daha sonra düzenlemek istiyorsanız, bu yaklaşım kullanmayın. .Vcxproj dosyasını elle oluşturursanız, özellikle proje proje öğelerinde joker karakterler kullanıyorsa, Visual Studio IDE düzenlemek ya da, yük olmayabilir.

> [!NOTE]
> En düşük düzey yapı yönergeleri içerdiği **.targets** ve **.props** özellikte depolanan VCTargets dizininde tanımlanan dosyaları `$(VCTargetsPath)`. Visual Studio 2017 Enterprise Edition'da bu dosyaları için varsayılan yolu C: olduğu\\Program Files (x86)\\Microsoft Visual Studio\\2017\\Kurumsal\\Common7\\IDE\\ VC\\VCTargets\\.

## <a name="creating-the-c-source-files"></a>C++ kaynak dosyalar oluşturma

Bu kılavuzda bir kaynak dosya ve üstbilgi dosyası sahip bir proje oluşturur. Kaynak dosya main.cpp konsol uygulamasının main işlevi içerir. Üstbilgi dosyası main.h iostream üst bilgi dosyasını dahil kodunu içerir. Visual Studio Code gibi Düzenleyicisi Visual Studio ya da bir metin kullanarak bu C++ dosyaları oluşturabilirsiniz.

### <a name="to-create-the-c-source-files-for-your-project"></a>Projeniz için C++ kaynak dosyaları oluşturmak için

1. Projeniz için bir dizin oluşturun.

2. Main.cpp adlı bir dosya oluşturun ve bu dosyayı aşağıdaki kodu ekleyin:

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

3. Main.h adlı bir dosya oluşturun ve bu dosyayı aşağıdaki kodu ekleyin:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild proje dosyası oluşturma

MSBuild proje dosyası proje kök öğesi içeren bir XML dosyasıdır (\<Proje >). Aşağıdaki örnek projesinde \<Proje > öğesi yedi alt öğeleri içerir:

- Grup etiketleri öğe üç (\<ItemGroup >) proje yapılandırması ve platformu, kaynak dosya adı ve üstbilgi dosyası adı belirtin.

- Üç alma etiketler (\<alma >) Microsoft Visual C++ ayarları konumunu belirtin.

- Bir özellik Grup etiketi (\<PropertyGroup >) proje ayarları belirtir.

### <a name="to-create-the-msbuild-project-file"></a>MSBuild proje dosyası oluşturmak için

1. Adlı bir proje dosyası oluşturmak için bir metin düzenleyicisi kullanın `myproject.vcxproj`ve ardından aşağıdaki kök ekleyin \<Proje > öğesi. Aşağıdaki yordamdaki adımları kök arasında öğeleri eklemek \<Proje > etiketleri:

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

2. Aşağıdaki iki eklemek \<ProjectConfiguration > alt öğelerini bir \<ItemGroup > öğesi. Hata ayıklama alt öğesi belirtir ve yayın yapılandırmaları bir 32 bit Windows işletim sistemi için:

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

3. Aşağıdakileri ekleyin \<alma / > Bu proje için varsayılan C++ ayarlarını yolunu belirtir öğe:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

4. Aşağıdaki özellik Grup öğesine ekleyin (\<PropertyGroup >) belirleyen iki proje özellikleri:

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

5. Aşağıdakileri ekleyin \<alma / > Bu proje için geçerli C++ ayarlarını yolunu belirtir öğe:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

6. Aşağıdakileri ekleyin \<ClCompile > alt öğe bir \<ItemGroup > öğesi. Alt öğe derlemek için C/C++ kaynak dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > \<ClCompile > olan bir *hedef yapı* ve içinde tanımlanan **VCTargets** dizini.

7. Aşağıdakileri ekleyin \<ClInclude > alt öğe bir \<ItemGroup > öğesi. Alt öğe C/C++ kaynak dosya için üstbilgi dosyası adını belirtir:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

8. Aşağıdakileri ekleyin \<alma > öğesi bu proje için hedef tanımlayan dosyasının yolunu belirtir:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Proje dosyası tamamlayın

Aşağıdaki kod önceki yordamda oluşturduğunuz tam proje dosyası gösterir.

```xml
<Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
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
    <PlatformToolset>v141</PlatformToolset>
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

## <a name="using-msbuild-to-build-your-project"></a>Projenizi oluşturmak için MSBuild kullanma

Konsol uygulamanızı yapılandırmak için komut isteminde aşağıdaki komutu yazın:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild çıkış dosyaları için bir dizini derler ve Myproject.exe programı oluşturmak için projenize bağlar. Derleme işlemi tamamlandıktan sonra uygulamayı çalıştırmak için aşağıdaki komutu kullanın:

`myproject`

Uygulama "Hello, MSBuild gelen!" görüntülenmelidir Konsol penceresinde.

## <a name="customizing-your-project"></a>Projenizi özelleştirme

MSBuild, önceden tanımlanmış yapı hedefleri yürütmek, kullanıcı tanımlı özellikler, uygulayın ve özel araçlar, olayları kullanın ve derleme adımları sağlar. Bu bölümde aşağıdaki görevler gösterilir:

- MSBuild ile derleme hedefleri kullanma.

- MSBuild ile derleme özelliklerini kullanma.

- MSBuild 64 bit derleyici ve araçlarla kullanma.

- MSBuild ile farklı toolsets kullanma.

- MSBuild özelleştirmeleri ekleniyor.

### <a name="using-msbuild-with-build-targets"></a>MSBuild ile derleme hedefleri kullanma

A *hedef yapı* komutların derleme sırasında yürütülen önceden tanımlanmış veya kullanıcı tanımlı adlandırılmış bir kümedir. Hedef komut satırı seçeneğini kullanın (**/t**) bir yapı hedef belirtmek için. Durumunda `myproject` örnek proje, önceden tanımlanmış **temiz** hedef hata ayıklama klasördeki tüm dosyaları siler ve yeni bir günlük dosyası oluşturur.

Komut isteminde temizlemek için aşağıdaki komutu yazın `myproject`.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>MSBuild ile derleme özellikleri kullanma

Özellik komut satırı seçeneği (**/p**) projesi derleme dosyanızı özelliğinde geçersiz kılmanıza olanak tanır. İçinde `myproject` örnek proje, yayın veya hata ayıklama yapı yapılandırması tarafından belirtilen `Configuration` özelliği. Ve yerleşik uygulamayı çalıştırmak için tasarlanmıştır işletim sistemi tarafından belirtilen `Platform` özelliği.

Komut isteminde, hata ayıklama derlemesi oluşturmak için aşağıdaki komutu yazın `myproject` 32-bit Windows üzerinde çalışmak üzere tasarlanmıştır uygulama.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Varsayımında `myproject` proje de tanımlayan bir yapılandırma 64-bit Windows ve adlı özel bir işletim sistemi için başka bir yapılandırma için örnek `myplatform`.

Komut isteminde bir sürüm oluşturmak için aşağıdaki komutu yapı türü 64-bit Windows sürümlerinde çalışır.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

Komut isteminde için yayın derlemesi oluşturma için aşağıdaki komutu `myplatform`.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 bit derleyici ve araçlarla MSBuild kullanma

Visual C++ 64-bit Windows sürümlerinde varsayılan olarak yüklü değilse, 64-bit x64 yerel ve Araçlar yüklenir. MSBuild ayarlayarak uygulamanızı oluşturmak için Araçlar ve 64 bit derleyici kullanmak için yapılandırabilirsiniz `PreferredToolArchitecture` özelliği. Bu özellik Proje yapılandırması veya platform özelliklerini etkilemez. Varsayılan olarak, Araçlar 32-bit sürümünü kullanılır. Derleyici ve araçları 64-bit sürümünü belirtmek için aşağıdaki özellik Grup öğesi Myproject.vcxproj proje dosyasına sonra ekleyin `Microsoft.Cpp.default.props` \<alma / > öğesi:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Komut isteminde uygulamanızı oluşturmak için 64-bit araçları kullanmak için aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Farklı bir araç takımı ile MSBuild kullanma

Visual C++ yüklü diğer sürümleri için kitaplıkları ve toolsets varsa, MSBuild geçerli Visual C++ sürümü veya diğer yüklü sürümleri için uygulamalar oluşturabilir. Örneğin, yüklediyseniz [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)], Windows XP için Visual C++ 11.0 araç takımı belirtin, sonra Microsoft.Cpp.props Myproject.vcxproj proje dosyasına aşağıdaki özellik Grup öğesi eklemek için `<Import />` öğe:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Visual C++ 11.0 Windows XP araç takımı ile projenizi yeniden oluşturmak için aşağıdaki komutlardan birini yazın:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

`msbuild myproject.vcxproj /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild özelleştirmeleri ekleme

MSBuild yapı işleminizin özelleştirmek için çeşitli yöntemler sağlar. Aşağıdaki konular özel derleme adımları, Araçlar ve olayları MSBuild projenize ekleme gösterir:

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)
