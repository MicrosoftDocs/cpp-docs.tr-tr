---
title: Visual Studio 'da C++ projeleri için MSBuild iç işlevleri
description: Visual Studio C++ projeleri için MSBuild tarafından kullanılan destek dosyaları, Özellikler ve hedefler.
ms.date: 10/14/2020
helpviewer_keywords:
- MSBuild overview
ms.openlocfilehash: e99b9a428d9c6149debc06e1dfab7a69c3590196
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924385"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ projeleri için MSBuild iç işlevleri

IDE 'deki proje özelliklerini ayarlayıp projeyi kaydettiğinizde, Visual Studio proje ayarlarını proje dosyanıza yazar. Proje dosyası, projenize özgü olan ayarları içerir. Ancak, projenizi derlemek için gereken tüm ayarları içermez. Proje dosyası, `Import` ek *destek dosyalarının* bir ağını içeren öğeleri içerir. Destek dosyaları, projeyi derlemek için gereken kalan özellikleri, hedefleri ve ayarları içerir.

Destek dosyalarındaki birçok hedef ve özellik yalnızca derleme sistemini uygulamak için mevcuttur. Bu makalede, MSBuild komut satırında belirtebileceğiniz yararlı hedefler ve özellikler açıklanmaktadır. Daha fazla hedef ve özellik bulmayı sağlamak için destek dosya dizinlerindeki dosyaları keşfetme.

## <a name="support-file-directories"></a>Dosya dizinlerini destekleme

Varsayılan olarak, birincil Visual Studio destek dosyaları aşağıdaki dizinlerde bulunur. Bu bilgiler sürüme özgüdür.

::: moniker range=">=msvc-160"

### <a name="visual-studio-2019"></a>Visual Studio 2019

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\`*

  Hedefler tarafından kullanılan birincil hedef dosyaları (. targets) ve özellik dosyalarını (. props) içerir. Varsayılan olarak, $ (VCTargetsPath) makrosu bu dizine başvurur. *`<version>`* Yer tutucu Visual Studio sürümü: V160 for Visual studio 2019, Visual studio 2017 için V150.

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\`*

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *`<platform>`* Yer tutucu ARM, ARM64, Win32 veya x64 alt dizinini temsil eder.

- *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Derlemeyi, belirtilen kullanılarak C++ uygulamaları oluşturmak için etkinleştiren dizinleri içerir *`<toolset>`* . *`<platform>`* Yer tutucu ARM, ARM64, Win32 veya x64 alt dizinini temsil eder. *`<toolset>`* Yer tutucu, araç kümesi alt dizinini temsil eder.

::: moniker-end

::: moniker range=">=msvc-150"

### <a name="visual-studio-2017"></a>Visual Studio 2017

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\`*

  Hedefler tarafından kullanılan birincil hedef dosyaları ( *`.targets`* ) ve özellik dosyalarını ( *`.props`* ) içerir. Varsayılan olarak, `$(VCTargetsPath)` makro bu dizine başvurur.

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\`*

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *`<platform>`* Yer tutucu ARM, ARM64, Win32 veya x64 alt dizinini temsil eder.

- *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Derlemeyi, belirtilen kullanılarak C++ uygulamaları oluşturmak için etkinleştiren dizinleri içerir *`<toolset>`* . *`<platform>`* Yer tutucu ARM, Win32 veya x64 alt dizinini temsil eder. *`<toolset>`* Yer tutucu, araç kümesi alt dizinini temsil eder.

::: moniker-end

### <a name="visual-studio-2015-and-earlier"></a>Visual Studio 2015 ve öncesi

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\`*

  Hedefler tarafından kullanılan birincil hedef dosyaları (. targets) ve özellik dosyalarını (. props) içerir. Varsayılan olarak, $ (VCTargetsPath) makrosu bu dizine başvurur.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\`*

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *`<platform>`* Yer tutucu ARM, Win32 veya x64 alt dizinini temsil eder.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\<version>\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Derlemeyi, belirtilen kullanılarak C++ uygulamaları oluşturmak için etkinleştiren dizinleri içerir *`<toolset>`* . *`<version>`* Yer tutucu, Visual studio 2012 Için v110, Visual Studio 2013 Için v120 ve Visual Studio 2015 Için v140. *`<platform>`* Yer tutucu ARM, Win32 veya x64 alt dizinini temsil eder. *`<toolset>`* Yer tutucu, araç kümesi alt dizinini temsil eder. Örneğin, Visual Studio 2015 araç takımını kullanarak Windows uygulamaları oluşturmak için v140. Veya, Visual Studio 2013 araç takımını kullanarak Windows XP için derleme v120_xp.

- *`<drive>:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\Platforms\<platform>\PlatformToolsets\<toolset>\`*

  Derlemeyi, Visual Studio 2008 ya da Visual Studio 2010 uygulamaları oluşturmak için etkinleştiren yollar, içermez *`<version>`* . Bu sürümlerde, *`<platform>`* yer tutucu Itanium, Win32 veya x64 alt dizinini temsil eder. *`<toolset>`* Yer tutucu V90 veya V100 araç kümesi alt dizinini temsil eder.

## <a name="support-files"></a>Destek dosyaları

Destek dosya dizinleri, bu uzantılara sahip dosyaları içerir:

| Uzantı | Açıklama |
| --------- | ----------- |
| *`.targets`* | `Target`Hedef tarafından yürütülen görevleri belirten xml öğeleri içerir. Ayrıca `PropertyGroup` , `ItemGroup` `ItemDefinitionGroup` `Item` görev parametrelerine dosya ve komut satırı seçenekleri atamak için kullanılan,, ve Kullanıcı tanımlı öğeleri içerebilir.<br /><br /> Daha fazla bilgi için bkz. [target öğesi (MSBuild)](/visualstudio/msbuild/target-element-msbuild). |
| *`.props`* | `Property Group`, Ve `Property` derleme sırasında kullanılan dosya ve parametre ayarlarını belirten Kullanıcı tanımlı XML öğelerini içerir.<br /><br /> Ayrıca, `ItemDefinitionGroup` `Item` ek ayarları belirten Kullanıcı tanımlı xml öğeleri de içerebilir. Öğe tanımı grubunda tanımlanan öğeler özelliklere benzer ancak komut satırından erişilemez. Visual Studio proje dosyaları, ayarları temsil etmek için genellikle özellikler yerine öğeleri kullanır.<br /><br /> Daha fazla bilgi için bkz. [ItemGroup öğesi (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [ItemDefinitionGroup öğesi (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)ve [öğe öğesi (MSBuild)](/visualstudio/msbuild/item-element-msbuild). |
| *`.xml`* | IDE Kullanıcı arabirimi öğelerini bildiren ve başlatacak XML öğeleri içerir. Örneğin, özellik sayfaları, özellik sayfaları, TextBox denetimleri ve ListBox denetimleri.<br /><br /> *`.xml`* Dosyalar MSBuild değil doğrudan IDE 'yi destekler. Ancak IDE özelliklerinin değerleri yapı özelliklerine ve öğelerine atanır.<br /><br /> Çoğu *`.xml`* dosya yerel ayara özgü bir alt dizinde bulunur. Örneğin, Ingilizce-US bölgesine ait dosyalar ' da bulunur `$(VCTargetsPath)\1033\` . |

## <a name="user-targets-and-properties"></a>Kullanıcı hedefleri ve özellikleri

MSBuild 'i etkin bir şekilde kullanmak için hangi özelliklerin ve hedeflerin yararlı ve alakalı olduğunu öğrenmenize yardımcı olur. Çoğu özellik ve hedef, Visual Studio derleme sisteminin uygulamaya yardımcı olur ve sonuç olarak kullanıcıyla ilgili değildir. Bu bölümde, konusunda bilinmesi gereken kullanıcı odaklı özellikler ve hedefler açıklanmaktadır.

### <a name="platformtoolset-property"></a>`PlatformToolset` özelliði

`PlatformToolset`Özelliği, derlemede HANGI MSVC araç takımının kullanıldığını belirler. Varsayılan olarak, geçerli araç kümesi kullanılır. Bu özellik ayarlandığında, yolu oluşturmak için değeri değişmez dizeler ile birleştirilir. Bu, belirli bir platform için bir proje oluşturmak için gereken özelliği ve hedef dosyaları içeren dizindir. Platform araç takımı, bu platform araç kümesi sürümünü kullanarak derlemek için yüklenmelidir.

Örneğin, `PlatformToolset` `v140` uygulamanızı derlemek için özelliğini, Visual Studio 2015 araçlarını ve kitaplıklarını kullanacak şekilde ayarlayın:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>`PreferredToolArchitecture` özelliði

`PreferredToolArchitecture`Özelliği, derlemede 32-bit veya 64 bit derleyicisinin ve araçların kullanılıp kullanılmadığını belirler. Bu özellik, çıkış platformu mimarisini veya yapılandırmasını etkilemez. Varsayılan olarak, MSBuild, bu özellik ayarlanmamışsa derleyicinin x86 sürümünü ve araçlarını kullanır.

Örneğin, `PreferredToolArchitecture` özelliğini, `x64` uygulamanızı derlemek için 64 bitlik derleyici ve araçları kullanacak şekilde ayarlayın:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>`UseEnv` özelliði

Varsayılan olarak, geçerli proje için platforma özgü ayarlar yolu, ıNCLUDE, LIB, LıBPATH, yapılandırma ve PLATFORM ortam değişkenlerini geçersiz kılar. `UseEnv` **`true`** Ortam değişkenlerinin geçersiz kılınmadığını güvence altına almak için özelliğini olarak ayarlayın.

> `msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Targets

Visual Studio destek dosyalarında yüzlerce hedef vardır. Ancak, çoğu kullanıcının yoksayması için sistem odaklı hedeflerdir. Çoğu sistem hedefi bir alt çizgi ( `_` ) veya,,,, veya ile başlayan bir ada `PrepareFor` sahiptir `Compute` `Before` `After` `Pre` `Post` .

Aşağıdaki tabloda, çok sayıda kullanışlı Kullanıcı yönelimli hedef listelenmiştir.

| Hedef | Açıklama |
| ------ | ----------- |
| BscMake | , Microsoft 'A ait bilgi Bakımı yardımcı programı aracı bscmake.exe yürütülür. |
| Oluşturma | Projeyi oluşturur.<br /><br /> Bu hedef, bir proje için varsayılandır. |
| ClCompile | cl.exe MSVC derleyici aracını yürütür. |
| Temizle | Geçici ve ara derleme dosyalarını siler. |
| LIB | Microsoft 32-bit kitaplık Yöneticisi aracını yürütür lib.exe. |
| Bağlantı | link.exe MSVC bağlayıcı aracını yürütür. |
| ManifestResourceCompile | Bir bildirimden kaynak listesini ayıklar ve sonra Microsoft Windows Kaynak derleyicisi aracı rc.exe yürütülür. |
| MIDL | , midl.exe Microsoft Arabirim Tanımlama Dili (MıDL) derleyici aracını yürütür. |
| Yeniden derleme | Projenizi temizler ve sonra oluşturur. |
| ResourceCompile | rc.exe Microsoft Windows Kaynak derleyicisi aracı 'nı yürütür. |
| XdcMake | , xdcmake.exe XML belge aracını yürütür. |
| Yapamadı | , xsd.exe XML şema tanımı aracını yürütür. *Bkz. Note.* |

> [!NOTE]
> Visual Studio 2017 ve üzeri sürümlerde, **XSD** dosyaları için C++ proje desteği kullanım dışıdır. GAC 'ye el ile **CppCodeProvider.dll** ekleyerek **Microsoft. VisualC. CppCodeProvider** kullanmaya devam edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[MSBuild görev başvurusu](/visualstudio/msbuild/msbuild-task-reference)\
[BscMake görevi](/visualstudio/msbuild/bscmake-task)\
[CL görevi](/visualstudio/msbuild/cl-task)\
[CPPClean görevi](/visualstudio/msbuild/cppclean-task)\
[LıB görevi](/visualstudio/msbuild/lib-task)\
[Bağlantı görevi](/visualstudio/msbuild/link-task)\
[MıDL görevi](/visualstudio/msbuild/midl-task)\
[MT görevi](/visualstudio/msbuild/mt-task)\
[RC görevi](/visualstudio/msbuild/rc-task)\
[SetEnv Görevi](/visualstudio/msbuild/setenv-task)\
[VCMessage görevi](/visualstudio/msbuild/vcmessage-task)\
[XDCMake görevi](/visualstudio/msbuild/xdcmake-task)
