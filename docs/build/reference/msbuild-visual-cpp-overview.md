---
title: Visual Studio'da MSBuild iç c++ projeleri
ms.date: 05/16/2019
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
ms.openlocfilehash: b3348320a1468fea03f39e43cc847f1085f3d319
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837225"
---
# <a name="msbuild-internals-for-c-projects"></a>C++ projeleri için MSBuild iç işlevleri

IDE'de proje özelliklerini ayarlayın ve projeyi kaydettiğinizde, Visual Studio Proje ayarlarını proje dosyanıza yazar. Proje dosyası projenize özgü ayarları içerir, ancak projenizi oluşturmak için gereken tüm ayarları içermiyor. Proje dosyasını içeren `Import` içeren ek bir ağ öğelerini *destek dosyaları.* Destek dosyaları geri kalan özellikleri, hedefleri ve projeyi oluşturmak için gerekli ayarları içerir.

Çoğu hedef ve Destek dosyalarını özellikler yalnızca yapı sistemini uygulamak için mevcut. Aşağıdaki bölümde, bazı yararlı hedefler ve MSBuild komut satırında belirtebileceğiniz özellikler açıklanmaktadır. Daha fazla hedef ve özellik keşfetmek için destek dosyası dizinlerindeki dosyaları inceleyin.

## <a name="support-file-directories"></a>Destek dosyası dizinleri

Varsayılan olarak birincil Visual Studio destek dosyaları aşağıdaki dizinlerde bulunur. Microsoft Visual Studio dizinlerde MSBuild altındaki dizinleri Visual Studio 2015 ve önceki sürümleri tarafından kullanılan Visual Studio 2017 ve sonraki sürümler tarafından kullanılabilir.

|Dizin|Açıklama|
|---------------|-----------------|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp (x86)\v4.0\\*version*\ |Birincil hedef dosyalarını (.targets) içerir ve hedefler tarafından kullanılan özellik dosyalarını (.props). Varsayılan olarak $(VCTargetsPath) makro bu dizine başvurur.|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*version*\Platforms\\*platform*\ |Hedefleri ve özellikleri üst dizinindeki geçersiz kılma platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, içindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir.<br /><br /> *Platform* yer tutucusu, ARM, Win32 veya x64 gösterir alt.|
|*drive*:\Program Files *(x86)* \Microsoft Visual Studio\\*year*\\*edition*\Common7\IDE\VC\VCTargets\Platforms\\*platform*\PlatformToolsets\\*toolset*\ <br /><br />*Sürücü*: \Program dosyaları *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*sürüm*\Platforms\\*platform*\ PlatformToolsets\\*araç takımı*\ <br /><br />*drive*:\Program Files *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*platform*\PlatformToolsets\\*toolset*\ |Belirtilen kullanarak C++ uygulamalarını oluşturmasını sağlayan dizinleri içerir *araç takımı*.<br /><br /> *Yıl* ve *edition* yer tutucuları, Visual Studio 2017 ve sonraki sürümleri tarafından kullanılır. *Sürüm* V110 Visual Studio 2012, Visual Studio 2013 için V120 V140 Visual Studio 2015, Visual Studio 2017 v141 ve Visual Studio 2019 için v142 için yer tutucudur. *Platform* yer tutucusu, ARM, Win32 veya x64 gösterir alt. *Araç takımı* yer tutucusu v120_xp Visual Studio 2013 Araç Takımı'nı kullanarak Windows XP için oluşturmak için Visual Studio 2015 Araç Takımı'nı kullanarak Windows uygulamaları oluşturmaya yönelik örnek v140 araç kümesi alt dizinini temsil eder.<br /><br />Visual Studio 2008 veya Visual Studio 2010 uygulamaları oluşturmasını sağlayan dizinleri içeren yolu içermez *sürüm*ve *platform* yer tutucu Itanium, Win32 veya x64 temsil eden alt. *Araç takımı* yer tutucusu v90 veya v100 araç kümesi alt dizinini temsil eder.|

## <a name="support-files"></a>Destek dosyaları

Dizinlere ilişkin destek Aşağıdaki uzantılara sahip dosyaları içerir:

|Dahili numara|Açıklama|
|---------------|-----------------|
|.targets|İçeren `Target` hedefe göre yürütülen görevleri belirleyen XML öğeleri. Ayrıca içerebilir `PropertyGroup`, `ItemGroup`, `ItemDefinitionGroup`ve kullanıcı tanımlı `Item` görev parametrelerine dosyalar ve komut satırı seçenekleri atamak için kullanılan öğeleri.<br /><br /> Daha fazla bilgi için [hedef öğe (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|
|.props|İçeren `Property Group` ve kullanıcı tanımlı `Property` bir yapı sırasında kullanılan dosya ve parametre ayarlarını belirleyen XML öğeleri.<br /><br /> Ayrıca içerebilir `ItemDefinitionGroup` ve kullanıcı tanımlı `Item` ek ayarları belirtmek XML öğeleri. Bir öğe tanım grubu içinde tanımlanan öğeler özelliklere benzer ancak komut satırından erişilemez. Visual Studio proje dosyaları yerine özellikleri öğeleri ayarları göstermek için sık kullanın.<br /><br /> Daha fazla bilgi için [ItemGroup öğesi (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), 
[Itemdefinitiongroup öğesi (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), ve [öğesi öğesi (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|
|.XML|Özellik bölümleri ve özellik sayfaları ve metin kutusu ve liste kutusu denetimleri gibi IDE kullanıcı arabirimi öğelerini bildirilip XML öğelerini içerir.<br /><br /> .Xml dosyaları doğrudan IDE'yi destekler, Msbuild'i değil. Ancak IDE özelliklerinin değerleri yapı özelliklerine ve öğelerine atanır.<br /><br /> Çoğu .xml dosyası bir yerel ayara özgü alt dizinde bulunur. Örneğin, ABD İngilizce bölgesinin dosyaları $(VCTargetsPath) \1033 içinde olan\\.|

## <a name="user-targets-and-properties"></a>Kullanıcı hedefleri ve özellikleri

MSBuild komut satırında en etkili bir şekilde kullanmak için hangi özelliklerin ve hedeflerin kullanışlı ve uygun olduğunu öğrenmenize yardımcı olur. Çoğu özellikleri ve hedefler Visual Studio yapı sistemini uygulamaya yardımcı olur ve sonuç olarak kullanıcıyla ilgili değildir. Bu bölümde, bazı faydalı kullanıcı-özellikler ve hedefler açıklanmaktadır.

### <a name="platformtoolset-property"></a>PlatformToolset özelliği

`PlatformToolset` Özelliği, yapıda kullanılan hangi MSVC araç takımı belirler. Varsayılan olarak, geçerli araç kümesi kullanılır. Bu özelliği ayarlandığında, özelliğin değerini belirli bir platform için bir proje oluşturmak için gereken özellik ve hedef dosyalarını içeren bir dizinin yolunu oluşturmak için hazır bilgi dizeleri ile birleştirilir. Bu platform araç kümesi sürümünü kullanarak oluşturmak için platform araç takımını yüklenmesi gerekir.

Örneğin, `PlatformToolset` özelliğini `v140` uygulamanızı oluşturmak için Visual Studio 2015 araçları ve kitaplıklarını kullanmak için:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture özelliği

`PreferredToolArchitecture` Özelliği, yapıda 32-bit veya 64 bit derleyici ve araçların kullanılıp kullanılmayacağını belirler. Bu özellik, çıkış platformu mimarisi veya yapılandırmasını etkilemez. Varsayılan olarak MSBuild x86 kullanır. Bu özellik ayarlanmamışsa araçları ve derleyici sürümü.

Örneğin, `PreferredToolArchitecture` özelliğini `x64` uygulamanızı oluşturmak üzere 64 bit derleyici ve Araçları'nı kullanmak için:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv özelliği

Varsayılan olarak, geçerli proje için platforma özgü ayarlar PATH, INCLUDE, LIB, LIBPATH, yapılandırma ve PLATFORM ortam değişkenlerini geçersiz kılar. Ayarlama `UseEnv` özelliğini **true** ortam değişkenlerinin geçersiz kılınmadığını güvence altına almak için.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Hedefler

Hedefler Visual Studio destek dosyalarında yüzlerce vardır. Ancak, çoğu kullanıcının yok sayabileceği sistem odaklı hedefleri ' dir. Çoğu Sistem hedefleri, bir alt çizgi (_) öneki veya "" Hesapla", Hazırla ile", "Önce", "Ön" veya "Post" "Sonra" başlayan bir ada sahip.

Aşağıdaki tabloda, kullanıcıya yönelik bazı yararlı hedefler listeler.

|Hedef|Açıklama|
|------------|-----------------|
|BscMake|Yürütür Microsoft gözatma bilgisi bakım Yardımcısı aracı bscmake.exe'yi.|
|Yapı|Projeyi oluşturur.<br /><br /> Bu proje için varsayılan hedeftir.|
|ClCompile|MSVC derleyici araç yürütür cl.exe.|
|Temizleme|Yapı dosyalarını siler geçici ve Ara.|
|lib|Microsoft 32-Bit Kitaplık Yöneticisi Aracı yürütür lib.exe.|
|Bağlantı|MSVC bağlayıcı aracı yürütür link.exe.|
|ManifestResourceCompile|Bir bildirimden kaynakların listesini ayıklar ve ardından Microsoft Windows Kaynak Derleyicisi aracı yürütür rc.exe.|
|MIDL|Yürütür Microsoft arabirim tanımı dili (MIDL) derleyici aracı midl.exe'yi.|
|Yeniden oluşturma|Temizler ve ardından, projeyi oluşturur.|
|ResourceCompile|Yürütür Microsoft Windows Kaynak Derleyicisi aracı RC.exe'yi.|
|XdcMake|Yürütür XML belgelendirme aracı xdcmake.exe'yi.|
|Xsd|XML şema tanımı aracı yürütür XSD.exe'nin. *Aşağıdaki nota bakın.*|

> [!NOTE]
> Visual Studio 2017 ve sonraki sürümlerinde, C++ proje desteği **xsd** dosyaları kullanım dışı bırakılmıştır. Kullanmaya devam edebilirsiniz **Microsoft.VisualC.CppCodeProvider** ekleyerek **CppCodeProvider.dll** GAC için el ile.

## <a name="see-also"></a>Ayrıca bkz.

[MSBuild Görev Başvurusu](/visualstudio/msbuild/msbuild-task-reference)<br/>
[BscMake Görevi](/visualstudio/msbuild/bscmake-task)<br/>
[CL Görevi](/visualstudio/msbuild/cl-task)<br/>
[CPPClean Görevi](/visualstudio/msbuild/cppclean-task)<br/>
[LIB Görevi](/visualstudio/msbuild/lib-task)<br/>
[Link Görevi](/visualstudio/msbuild/link-task)<br/>
[MIDL Görevi](/visualstudio/msbuild/midl-task)<br/>
[MT Görevi](/visualstudio/msbuild/mt-task)<br/>
[RC Görevi](/visualstudio/msbuild/rc-task)<br/>
[SetEnv Görevi](/visualstudio/msbuild/setenv-task)<br/>
[VCMessage Görevi](/visualstudio/msbuild/vcmessage-task)<br/>
[XDCMake Görevi](/visualstudio/msbuild/xdcmake-task)<br/>
