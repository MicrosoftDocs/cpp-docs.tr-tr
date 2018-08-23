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
ms.openlocfilehash: a8bb957f0ab1dd2ea7d05151257aee0e15561e8a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609705"
---
# <a name="walkthrough-using-msbuild-to-create-a-visual-c-project"></a>İzlenecek yol: Visual C++ Projesi Oluşturmak için MSBuild Kullanma

Bu izlenecek yol MSBuild komut isteminde Visual C++ projesi oluşturmak için nasıl kullanılacağını gösterir. C++ kaynak dosyaları ve bir Visual C++ konsol uygulaması için bir XML tabanlı proje dosyasını nasıl oluşturulacağını öğreneceksiniz. Projeyi oluşturduktan sonra yapı işleminin nasıl özelleştirileceğini öğreneceksiniz.

Bu izlenecek yol aşağıdaki görevleri gösterir:

- Projeniz için C++ kaynak dosyaları oluşturma.

- XML MSBuild proje dosyası oluşturuluyor.

- Projenizi oluşturmak için MSBuild kullanma.

- Projenizi özelleştirmek için MSBuild kullanma.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için aşağıdakiler gerekir:

- Visual Studio ile bir kopyasını **C++ ile masaüstü geliştirme** iş yükü yüklenmiş.

- MSBuild sistemi ilişkin genel yaklaşım.

> [!NOTE]
> Visual Studio IDE kullanarak daha sonra projeyi dosyasını düzenlemek istiyorsanız, bu yaklaşım kullanmayın. .Vcxproj dosyasını el ile oluşturursanız, özellikle projeyi joker karakterler proje öğelerinde kullanıyorsa, Visual Studio IDE düzenlemek veya, yüklemek mümkün olmayabilir.

> [!NOTE]
> Alt düzey derleme yönergeleri çoğu içerdiği **.targets** ve **.props** için özellik içinde saklanan VCTargets dizinde tanımlanan dosyaları `$(VCTargetsPath)`. Visual Studio 2017 Enterprise sürümünde bu dosyalar için varsayılan yolu şöyledir\\Program dosyaları (x86)\\Microsoft Visual Studio\\2017\\Kurumsal\\Common7\\IDE\\ VC\\VCTargets\\.

## <a name="creating-the-c-source-files"></a>C++ kaynak dosyaları oluşturma

Bu izlenecek yolda kaynak dosyası ve üstbilgi dosyası içeren bir proje oluşturur. Kaynak dosyasının Main.cpp öğesi konsol uygulamasının ana işlevini içerir. Üstbilgi dosyası main.h, iostream üstbilgi dosyasını eklemek için kod içerir. Visual Studio Code gibi Düzenleyicisi Visual Studio veya metin kullanarak bu C++ dosyaları oluşturabilirsiniz.

### <a name="to-create-the-c-source-files-for-your-project"></a>Projeniz için C++ kaynak dosyaları oluşturmak için

1. Projeniz için bir dizin oluşturun.

2. Main.cpp olarak adlandırılan bir dosya oluşturun ve bu dosyaya aşağıdaki kodu ekleyin:

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

3. Main.h olarak adlandırılan bir dosya oluşturun ve bu dosyaya aşağıdaki kodu ekleyin:

    ```cpp
    // main.h: the application header code.
    /* Additional source code to include. */
    ```

## <a name="creating-the-xml-msbuild-project-file"></a>XML MSBuild proje dosyası oluşturma

Bir MSBuild proje dosyası proje kök öğesi içeren bir XML dosyasıdır (\<Proje >). Aşağıdaki örnek projesinde \<Proje > öğesi yedi alt öğeleri içerir:

- Üç öğe grubu etiketleri (\<ItemGroup >) proje yapılandırması ve platformu, kaynak dosya adı ve üst bilgi dosyası adını belirtin.

- Etiketleri üç içe aktarma (\<İçeri Aktar >) Microsoft Visual C++ ayarları konumunu belirtin.

- Özellik grubu etiketi (\<PropertyGroup >) proje ayarlarını belirtir.

### <a name="to-create-the-msbuild-project-file"></a>MSBuild proje dosyası oluşturmak için

1. Adlı bir proje dosyası oluşturmak için bir metin düzenleyicisi kullanın `myproject.vcxproj`ve ardından aşağıdaki kök ekleyin \<Proje > öğesi. Aşağıdaki yordam adımlarının kök öğeleri eklemek \<Project > etiketleri:

    ```xml
    <Project DefaultTargets="Build" ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
    </Project>
    ```

2. Aşağıdaki iki ekleme \<ProjectConfiguration > alt öğe bir \<ItemGroup > öğesi. Hata ayıklama alt öğe belirtir ve sürüm yapılandırmalarını 32-bit Windows işletim sistemi:

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

3. Aşağıdaki \<İçeri Aktar / > Bu proje için varsayılan C++ ayarları yolunu belirleyen öğesi:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />
    ```

4. Aşağıdaki özellik grubu öğesini ekleyin (\<PropertyGroup >) iki proje özellikleri belirtir:

    ```xml
    <PropertyGroup>
      <ConfigurationType>Application</ConfigurationType>
      <PlatformToolset>v141</PlatformToolset>
    </PropertyGroup>
    ```

5. Aşağıdaki \<İçeri Aktar / > Bu proje için geçerli C++ ayarları yolunu belirleyen öğesi:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
    ```

6. Aşağıdaki \<ClCompile > alt öğede bir \<ItemGroup > öğesi. Alt öğe, derlenecek C/C++ kaynak dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClCompile Include="main.cpp" />
    </ItemGroup>
    ```

   > [!NOTE]
   > \<ClCompile > olan bir *derleme hedefi* ve tanımlanan **VCTargets** dizin.

7. Aşağıdaki \<Clınclude > alt öğede bir \<ItemGroup > öğesi. Alt öğe, C/C++ kaynak dosyası için üstbilgi dosyasının adını belirtir:

    ```xml
    <ItemGroup>
      <ClInclude Include="main.h" />
    </ItemGroup>
    ```

8. Aşağıdaki \<alma > Bu proje için hedef tanımlayan dosyasının yolunu belirtir öğesi:

    ```xml
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />
    ```

### <a name="complete-project-file"></a>Tam proje dosyası

Aşağıdaki kod, önceki yordamda oluşturduğunuz proje dosyasının gösterir.

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

Konsol uygulamanızı oluşturmak için komut isteminde aşağıdaki komutu yazın:

`msbuild myproject.vcxproj /p:configuration=debug`

MSBuild çıkış dosyaları için bir dizini derler ve projenize Myproject.exe programını oluşturmak için bağlantı. Yapı işlemi tamamlandıktan sonra uygulamayı çalıştırmak için aşağıdaki komutu kullanın:

`myproject`

Uygulama "Msbuild'dan,!" görüntülemelidir. Konsol penceresinde.

## <a name="customizing-your-project"></a>Projenizi özelleştirme

MSBuild, önceden tanımlanmış bir yapı hedefleri yürütmenizi, kullanıcı tanımlı özellikler uygulamanızı ve olayları, özel araçlarını kullanın ve derleme adımları sağlar. Bu bölüm aşağıdaki görevleri gösterir:

- Yapı hedefleriyle MSBuild kullanma.

- Yapı özellikleriyle MSBuild kullanma.

- 64 bit derleyici ve araçlarla MSBuild kullanma.

- MSBuild ile farklı araç takımları kullanma.

- MSBuild özelleştirmeleri ekleme.

### <a name="using-msbuild-with-build-targets"></a>Yapı hedefleriyle MSBuild kullanma

A *derleme hedefi* derleme sırasında yürütülebilecek önceden tanımlı veya kullanıcı tanımlı komut adlandırılmış kümesidir. Hedef komut satırı seçeneğini kullanın (**/t**) yapı hedefi belirtmek için. Durumunda, `myproject` örnek proje, önceden tanımlanmış **temiz** hedef hata ayıklama klasöründeki tüm dosyaları siler ve yeni bir günlük dosyası oluşturur.

Komut isteminde temizlemek için aşağıdaki komutu yazın `myproject`.

`msbuild myproject.vcxproj /t:clean`

### <a name="using-msbuild-with-build-properties"></a>Yapı özellikleriyle MSBuild kullanma

Özellik komut satırı seçeneği (**/p**), Proje yapı dosyanızda bir özelliği geçersiz kılmanıza olanak sağlar. İçinde `myproject` örnek proje, yayınlama veya hata ayıklama derleme yapılandırması tarafından belirtilen `Configuration` özelliği. Ve oluşturulan uygulamayı çalıştırmayı amaçlayan işletim sistemi tarafından belirtilen `Platform` özelliği.

Hata Ayıklama yapısını oluşturmak için aşağıdaki komutu komut istemine yazın `myproject` 32-bit Windows üzerinde çalışma üzere tasarlanan bir uygulama.

`msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`

Varsayımında `myproject` proje de tanımlayan bir yapılandırma adlı özel bir işletim sistemi için başka bir yapılandırmayı yanı sıra 64-bit Windows için örnek `myplatform`.

Komut isteminde sürüm yapılandırması oluşturmak için aşağıdaki komutu yazın, 64 bit Windows üzerinde çalışır.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`

İçin sürüm yapılandırması oluşturmak için aşağıdaki komutu komut istemine yazın `myplatform`.

`msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`

### <a name="using-msbuild-with-the-64-bit-compiler-and-tools"></a>64 bit derleyici ve araçlarla MSBuild kullanma

Varsayılan olarak Visual C++ 64 bit Windows üzerinde yüklü değilse, 64-bit x64 yerel ve çapraz Araçlar yüklenir. MSBuild ayarlayarak uygulamanızı oluşturmak üzere 64 bit derleyici ve Araçları'nı kullanmak için yapılandırabilirsiniz `PreferredToolArchitecture` özelliği. Bu özellik, proje yapılandırmasını veya platform özelliklerini etkilemez. Varsayılan olarak araçların 32 bit sürümü kullanılır. Derleyici ve araçların 64-bit sürümünü belirtmek için aşağıdaki özellik grubu öğesini sonra Myproject.vcxproj proje dosyasına eklemek `Microsoft.Cpp.default.props` \<İçeri Aktar / > öğesi:

```xml
<PropertyGroup>
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>
</PropertyGroup>
```

Komut isteminde uygulamanızı oluşturmak üzere 64 bit Araçlar kullanmak için aşağıdaki komutu yazın.

`msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="using-msbuild-with-a-different-toolset"></a>Farklı araç takımıyla MSBuild kullanma

Araç kümeleri ve kitaplıklar için yüklü Visual C++'ın diğer sürümlerinin varsa, MSBuild geçerli Visual C++ sürümü veya diğer yüklü sürümler için uygulamalar oluşturabilirsiniz. Windows XP için Visual C++ 11.0 araç kümesini belirtmek için Visual Studio 2012, yüklediğiniz Örneğin, aşağıdaki özellik grubu öğesini Myproject.vcxproj proje dosyasına Microsoft.Cpp.props sonra ekleyin `<Import />` öğesi:

```xml
<PropertyGroup>
    <PlatformToolset>v110_xp</PlatformToolset>
</PropertyGroup>
```

Projenizi Visual C++ 11.0 Windows XP araç takımıyla yeniden oluşturmak için aşağıdaki komutlardan birini yazın:

`msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`

`msbuild myproject.vcxproj /t:rebuild`

### <a name="adding-msbuild-customizations"></a>MSBuild özelleştirmeleri ekleme

MSBuild, yapı işleminizi özelleştirmek için çeşitli yollar sağlar. Aşağıdaki konular, özel derleme adımları, araçları ve olaylarının MSBuild projenize ekleme gösterir:

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Adımı Ekleme](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerine Özel Derleme Araçları Ekleme](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)

- [Nasıl Yapılır: MSBuild Projelerinde Derleme Olaylarını Kullanma](../build/how-to-use-build-events-in-msbuild-projects.md)
