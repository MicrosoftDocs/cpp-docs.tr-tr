---
title: Visual Studio 'da C++ projeleri için MSBuild iç işlevleri
ms.date: 02/26/2020
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: e100913cf4f0d84eac0e5891edb053918aec67f4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87190500"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ projeleri için MSBuild iç işlevleri

IDE 'deki proje özelliklerini ayarlayıp projeyi kaydettiğinizde, Visual Studio proje ayarlarını proje dosyanıza yazar. Proje dosyası, projenize özgü olan ayarları içerir. Ancak, projenizi derlemek için gereken tüm ayarları içermez. Proje dosyası, `Import` ek *destek dosyalarının* bir ağını içeren öğeleri içerir. Destek dosyaları, projeyi derlemek için gereken kalan özellikleri, hedefleri ve ayarları içerir.

Destek dosyalarındaki birçok hedef ve özellik yalnızca derleme sistemini uygulamak için mevcuttur. Bu makalede, MSBuild komut satırında belirtebileceğiniz yararlı hedefler ve özellikler açıklanmaktadır. Daha fazla hedef ve özellik bulmayı sağlamak için destek dosya dizinlerindeki dosyaları keşfetme.

## <a name="support-file-directories"></a>Dosya dizinlerini destekleme

Varsayılan olarak, birincil Visual Studio destek dosyaları aşağıdaki dizinlerde bulunur. Bu bilgiler sürüme özgüdür.

### <a name="visual-studio-2019"></a>Visual Studio 2019

- % VSıNSTALLDIR% MSBuild \\ Microsoft \\ VC \\ *sürümü* \\ vctargets\\

  Hedefler tarafından kullanılan birincil hedef dosyaları (. targets) ve özellik dosyalarını (. props) içerir. Varsayılan olarak, $ (VCTargetsPath) makrosu bu dizine başvurur. *Sürüm* yer tutucusu Visual Studio Sürüm: V160 for visual Studio 2019, V150 for visual Studio 2017 için geçerlidir.

- % VSıNSTALLDIR% MSBuild \\ Microsoft \\ VC \\ *sürümü* \\ vctargets \\ platformları \\ *platformu*\\

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder.

- % VSıNSTALLDIR% MSBuild \\ Microsoft \\ VC \\ *sürümü* \\ vctargets \\ platformları \\ *Platform* \\ platformtoolsets \\ *araç takımı*\\

  Belirtilen *araç takımını*kullanarak, derlemeyi C++ uygulamaları oluşturmaya olanak sağlayan dizinleri içerir. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder. *Araç kümesi* yer tutucusu araç kümesi alt dizinini temsil eder.

### <a name="visual-studio-2017"></a>Visual Studio 2017

- % VSıNSTALLDIR% Common7 \\ IDE \\ VC \\ vctargets\\

  Hedefler tarafından kullanılan birincil hedef dosyaları (. targets) ve özellik dosyalarını (. props) içerir. Varsayılan olarak, $ (VCTargetsPath) makrosu bu dizine başvurur.

- % VSıNSTALLDIR% Common7 \\ IDE \\ VC \\ vctargets \\ platformları \\ *platformu*\\

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder.

- % VSıNSTALLDIR% Common7 \\ IDE \\ VC \\ vctargets \\ platformları \\ *Platform* \\ platformtoolsets \\ *araç takımı*\\

  Belirtilen *araç takımını*kullanarak, derlemeyi C++ uygulamaları oluşturmaya olanak sağlayan dizinleri içerir. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder. *Araç kümesi* yer tutucusu araç kümesi alt dizinini temsil eder.

### <a name="visual-studio-2015-and-earlier"></a>Visual Studio 2015 ve öncesi

- *sürücü*: \\ Program Files *(x86)* \\ MSBuild \\ Microsoft. cpp (x86) \\ v 4.0 \\ *sürümü*\\

  Hedefler tarafından kullanılan birincil hedef dosyaları (. targets) ve özellik dosyalarını (. props) içerir. Varsayılan olarak, $ (VCTargetsPath) makrosu bu dizine başvurur.

- *sürücü*: \\ Program Files *(x86)* \\ MSBuild \\ Microsoft. cpp \\ v 4.0 \\ *Sürüm* \\ platformları \\ *platformu*\\

  Üst dizinindeki hedefleri ve özellikleri geçersiz kılan platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder.

- *sürücü*: \\ Program Files *(x86)* \\ MSBuild \\ Microsoft. cpp \\ v 4.0 \\ *Sürüm* \\ platformları \\ *Platform* \\ platformtoolsets \\ *araç takımı*\\

  Belirtilen *araç takımını*kullanarak, derlemeyi C++ uygulamaları oluşturmaya olanak sağlayan dizinleri içerir. *Sürüm* yer tutucusu, visual Studio 2012 için V110, Visual Studio 2013 için v120 ve visual Studio 2015 için v140. *Platform* yer tutucusu ARM, Win32 veya x64 alt dizinini temsil eder. *Araç kümesi* yer tutucusu araç kümesi alt dizinini temsil eder. Örneğin, Visual Studio 2015 araç takımını kullanarak Windows uygulamaları oluşturmak için v140. Veya, Visual Studio 2013 araç takımını kullanarak Windows XP için derleme v120_xp.

- *sürücü*: \\ Program Files *(x86)* \\ MSBuild \\ Microsoft. cpp \\ v 4.0 \\ platformları \\ *Platform* \\ platformtoolsets \\ *araç takımı*\\

  Derlemeyi, Visual Studio 2008 ya da Visual Studio 2010 uygulamaları oluşturmak için etkinleştiren yollar *sürümü*içermez. Bu sürümlerde, *Platform* yer tutucusu Itanium, Win32 veya x64 alt dizinini temsil eder. *Araç kümesi* yer tutucusu V90 veya V100 araç kümesi alt dizinini temsil eder.

## <a name="support-files"></a>Destek dosyaları

Destek dosya dizinleri, bu uzantılara sahip dosyaları içerir:

| Uzantı | Açıklama |
| --------- | ----------- |
| . targets | `Target`Hedef tarafından yürütülen görevleri belirten xml öğeleri içerir. Ayrıca `PropertyGroup` , `ItemGroup` `ItemDefinitionGroup` `Item` görev parametrelerine dosya ve komut satırı seçenekleri atamak için kullanılan,, ve Kullanıcı tanımlı öğeleri içerebilir.<br /><br /> Daha fazla bilgi için bkz. [target öğesi (MSBuild)](/visualstudio/msbuild/target-element-msbuild). |
| . props | `Property Group`, Ve `Property` derleme sırasında kullanılan dosya ve parametre ayarlarını belirten Kullanıcı tanımlı XML öğelerini içerir.<br /><br /> Ayrıca, `ItemDefinitionGroup` `Item` ek ayarları belirten Kullanıcı tanımlı xml öğeleri de içerebilir. Öğe tanımı grubunda tanımlanan öğeler özelliklere benzer ancak komut satırından erişilemez. Visual Studio proje dosyaları, ayarları temsil etmek için genellikle özellikler yerine öğeleri kullanır.<br /><br /> Daha fazla bilgi için bkz. [ItemGroup öğesi (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [ItemDefinitionGroup öğesi (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild)ve [öğe öğesi (MSBuild)](/visualstudio/msbuild/item-element-msbuild). |
| .xml | IDE Kullanıcı arabirimi öğelerini bildiren ve başlatacak XML öğeleri içerir. Örneğin, özellik sayfaları, özellik sayfaları, TextBox denetimleri ve ListBox denetimleri.<br /><br /> . Xml dosyaları MSBuild değil doğrudan IDE 'yi destekler. Ancak IDE özelliklerinin değerleri yapı özelliklerine ve öğelerine atanır.<br /><br /> Çoğu. xml dosyası yerel ayara özgü bir alt dizinde bulunur. Örneğin, Ingilizce-US bölgesi dosyaları $ (VCTargetsPath) 1033 ' dir \\ \\ . |

## <a name="user-targets-and-properties"></a>Kullanıcı hedefleri ve özellikleri

MSBuild 'i etkin bir şekilde kullanmak için hangi özelliklerin ve hedeflerin yararlı ve alakalı olduğunu öğrenmenize yardımcı olur. Çoğu özellik ve hedef, Visual Studio derleme sisteminin uygulamaya yardımcı olur ve sonuç olarak kullanıcıyla ilgili değildir. Bu bölümde, konusunda bilinmesi gereken kullanıcı odaklı özellikler ve hedefler açıklanmaktadır.

### <a name="platformtoolset-property"></a>Platformaraç takımı özelliği

`PlatformToolset`Özelliği, derlemede HANGI MSVC araç takımının kullanıldığını belirler. Varsayılan olarak, geçerli araç kümesi kullanılır. Bu özellik ayarlandığında, yolu oluşturmak için değeri değişmez dizeler ile birleştirilir. Bu, belirli bir platform için bir proje oluşturmak için gereken özelliği ve hedef dosyaları içeren dizindir. Platform araç takımı, bu platform araç kümesi sürümünü kullanarak derlemek için yüklenmelidir.

Örneğin, `PlatformToolset` `v140` uygulamanızı derlemek için özelliğini, Visual Studio 2015 araçlarını ve kitaplıklarını kullanacak şekilde ayarlayın:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture özelliği

`PreferredToolArchitecture`Özelliği, derlemede 32-bit veya 64 bit derleyicisinin ve araçların kullanılıp kullanılmadığını belirler. Bu özellik, çıkış platformu mimarisini veya yapılandırmasını etkilemez. Varsayılan olarak, MSBuild, bu özellik ayarlanmamışsa derleyicinin x86 sürümünü ve araçlarını kullanır.

Örneğin, `PreferredToolArchitecture` özelliğini, `x64` uygulamanızı derlemek için 64 bitlik derleyici ve araçları kullanacak şekilde ayarlayın:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv özelliği

Varsayılan olarak, geçerli proje için platforma özgü ayarlar yolu, ıNCLUDE, LIB, LıBPATH, yapılandırma ve PLATFORM ortam değişkenlerini geçersiz kılar. `UseEnv` **`true`** Ortam değişkenlerinin geçersiz kılınmadığını güvence altına almak için özelliğini olarak ayarlayın.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Targets

Visual Studio destek dosyalarında yüzlerce hedef vardır. Ancak, çoğu kullanıcının yoksayması için sistem odaklı hedeflerdir. Çoğu sistem hedefi bir alt çizgi () tarafından ön yüklenir `_` veya "PrepareFor", "COMPUTE", "Before", "After", "Pre" veya "Post" ile başlayan bir ada sahiptir.

Aşağıdaki tabloda, çok sayıda kullanışlı Kullanıcı yönelimli hedef listelenmiştir.

| Hedef | Açıklama |
| ------ | ----------- |
| BscMake | , Microsoft 'A ait bilgi Bakımı yardımcı programı aracı bscmake.exe yürütülür. |
| Yapı | Projeyi oluşturur.<br /><br /> Bu hedef, bir proje için varsayılandır. |
| ClCompile | cl.exe MSVC derleyici aracını yürütür. |
| Temizle | Geçici ve ara derleme dosyalarını siler. |
| LIB | Microsoft 32-bit kitaplık Yöneticisi aracını yürütür lib.exe. |
| Bağlantı | link.exe MSVC bağlayıcı aracını yürütür. |
| ManifestResourceCompile | Bir bildirimden kaynak listesini ayıklar ve sonra Microsoft Windows Kaynak derleyicisi aracı rc.exe yürütülür. |
| MIDL | , midl.exe Microsoft Arabirim Tanımlama Dili (MıDL) derleyici aracını yürütür. |
| Yeniden derleme | Projenizi temizler ve sonra oluşturur. |
| ResourceCompile | rc.exe Microsoft Windows Kaynak derleyicisi aracı 'nı yürütür. |
| XdcMake | , xdcmake.exe XML belge aracını yürütür. |
| Yapamadı | , xsd.exe XML şema tanımı aracını yürütür. *Aşağıdaki nota bakın.* |

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
