---
title: Yaygın MSBuild komutları ve Özellikler makroları
ms.date: 03/20/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- $(FrameworkSDKDir) macro
- ProjectName macro $(ProjectName)
- DevEnvDir macro $(DevEnvDir)
- $(DevEnvDir) macro
- TargetPath macro $(TargetPath)
- VSInstallDir macro $(VSInstallDir)
- $(InputFileName) macro
- $(SolutionFileName) macro
- macros [C++], build macros
- InputFileName macro $(InputFileName)
- $(VCInstallDir) macro
- $(IntDir) macro
- $(ConfigurationName) macro
- SolutionDir macro $(SolutionDir)
- $(TargetPath) macro
- $(Inherit) macro
- $(SolutionPath) macro
- WebDeployRoot macro $(WebDeployRoot)
- WebDeployPath macro $(WebDeployPath)
- StopEvaluating macro $(StopEvaluating)
- $(RootNamespace) macro
- $(WebDeployRoot) macro
- ProjectPath macro $(ProjectPath)
- $(ProjectPath) macro
- $(InputDir) macro
- SolutionName macro $(SolutionName)
- ProjectExt macro $(ProjectExt)
- $(TargetExt) macro
- $(ProjectFileName) macro
- TargetName macro $(TargetName)
- $(References) macro
- References macro $(References)
- TargetExt macro $(TargetExt)
- ProjectDir macro $(ProjectDir)
- $(TargetDir) macro
- SolutionExt macro $(SolutionExt)
- $(SolutionDir) macro
- ProjectFileName macro $(ProjectFileName)
- VCInstallDir macro $(VCInstallDir)
- $(InputExt) macro
- $(TargetFileName) macro
- $(SolutionExt) macro
- PlatformName macro $(PlatformName)
- IntDir macro $(IntDir)
- $(FrameworkVersion) macro
- $(ProjectDir) macro
- build macros [C++]
- InputPath macro $(InputPath)
- $(VSInstallDir) macro
- $(WebDeployPath) macro
- TargetFileName macro $(TargetFileName)
- NoInherit macro $(NoInherit)
- ConfigurationName macro $(ConfigurationName)
- $(ProjectExt) macro
- TargetDir macro $(TargetDir)
- InputName macro $(InputName)
- $(ProjectName) macro
- FrameworkSDKDir macro $(FrameworkSDKDir)
- $(ParentName) macro
- InputExt macro $(InputExt)
- $(SafeRootNamespace) macro
- InputDir macro $(InputDir)
- $(FxCopDir) macro
- $(RemoteMachine) macro
- Inherit macro $(Inherit)
- FrameworkVersion macro $(FrameworkVersion)
- $(StopEvaluating) macro
- $(OutDir) macro
- FrameworkDir macro $(FrameworkDir)
- SolutionFileName macro $(SolutionFileName)
- $(NoInherit) macro
- RemoteMachine macro $(RemoteMachine)
- properties [C++], build property macros
- $(TargetName) macro
- $(SolutionName) macro
- $(InputPath) macro
- ParentName macro $(ParentName)
- OutDir macro $(OutDir)
- SafeRootNamespace macro $(SafeRootNamespace)
- FxCopDir macro $(FxCopDir)
- $(InputName) macro
- RootNamespace macro $(RootNamespace)
- builds [C++], macros
- $(FrameworkDir) macro
- $(PlatformName) macro
- $(PlatformShortName) macro
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
ms.openlocfilehash: 46fdd5e356ded96388a154ff459ef4cc3c02267f
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58327685"
---
# <a name="common-macros-for-msbuild-commands-and-properties"></a>Yaygın MSBuild komutları ve Özellikler makroları

Yükleme seçenekleri bağlı olarak, Visual Studio Makroları yüzlerce kullanılabilir size (Msbuild'i temel alan) Visual Studio projesi içinde yapabilirsiniz. Bunlar varsayılan olarak veya .props veya .targets dosyalarında veya proje ayarlarınızda ayarlanır MSBuild özellikleri karşılık gelir. Bu makrolar bir projesinin her yerde kullanabilirsiniz **özellik sayfaları** iletişim kutusu burada dizeleri kabul edilir. Bu makrolar, büyük/küçük harfe duyarlı değildir.

## <a name="view-the-current-properties-and-macros"></a>Makroları ve geçerli özelliklerini görüntüleyin

Tüm kullanılabilir makroları görüntülemek için **özellik sayfaları** iletişim altında **VC ++ dizinleri**, özellik satırın sonundaki aşağı açılır oku seçin. Tıklayarak **Düzenle** Düzenle iletişim kutusunda seçin **makroları** düğmesi. Özellikler ve makrolar Visual Studio'da görünür geçerli kümesini geçerli değerin yanı sıra her biri için listelenir. Daha fazla bilgi için **Specifying User-Defined değerleri** bölümünü [C++ projesi özellik Sayfa başvurusu](property-pages-visual-cpp.md).

![VC ++ makroları düğmesi](../media/vcppdir_libdir_macros.png "makroları menüsü")

## <a name="list-of-common-macros"></a>Genel makro listesi

Bu tablo, uygun makroları yaygın olarak kullanılan bir alt kümesi açıklar; Çoğu burada listelenmeyen daha vardır. Git **makroları** tüm özelliklerini ve geçerli değerlerini, projenizdeki görmek için iletişim. MSBuild özellik tanımları nasıl oluşturulduğunu ve .props ve .targets .vcxproj dosyaları içindeki makrolar olarak kullanılan hakkında daha fazla bilgi için bkz [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$(Configuration)**|Geçerli proje yapılandırması, örneğin "Debug" adı.|
|**$(DevEnvDir)**|(Sürücü + yolu tanımlanan); Visual Studio yükleme dizini sondaki ters eğik çizgi içerir '\\'.|
|**$(FrameworkDir)**|.NET Framework yüklendiği dizin.|
|**$(FrameworkSDKDir)**|.NET Framework yüklü dizin. .NET Framework, Visual Studio'nun veya ayrı ayrı bir parçası olarak yüklenmiş.|
|**$(FrameworkVersion)**|Visual Studio tarafından kullanılan .NET Framework sürümü. Birlikte **$(FrameworkDir)**, .NET Framework kullanarak Visual Studio sürümünü tam yolu.|
|**$(FxCopDir)**|Fxcop.cmd dosyanın yolu. Tüm Visual C++ sürümleriyle fxcop.cmd dosyası yüklü değil.|
|**$(Intdir)**|Ara dosyaları için belirtilen dizin yolu. Bu göreli bir yol ise, Ara dosyaları proje dizinine eklenen bu yoluna gidin. Bu yolu bir eğik çizgiyle olması gerekir. Bu değeri çözümler **Ara dizin** özelliği. Kullanmayın **$(OutDir)** bu özelliği tanımlamak için.|
|**$(OutDir)**|Çıkış dosyası dizinine yolu. Bu göreli bir yol ise, çıktı dosyalarının proje dizinine eklenir bu yoluna gidin. Bu yolu bir eğik çizgiyle olması gerekir. Bu değeri çözümler **çıkış dizinine** özelliği. Kullanmayın **$(ıntdir)** bu özelliği tanımlamak için.|
|**$(Platform)**|Geçerli proje platformu, örneğin, "Win32" adı.|
|**$(PlatformShortName)**|Örneğin, "x86" veya "x64" geçerli mimariye kısa adı.|
|**$(ProjectDir)**|(Sürücü + yolu tanımlanan); proje dizini sondaki ters eğik çizgi içerir '\\'.|
|**$(ProjectExt)**|Projenin dosya uzantısı. İçerdiğinden '.' dosya uzantısı önce.|
|**$(ProjectFileName)**|(Temel adı + dosya uzantısı tanımlanan) proje dosya adı.|
|**$(ProjectName)**|Temel projenin adı.|
|**$(ProjectPath)**|(Sürücü yolu + temel adı + dosya uzantısı tanımlanır) projenin mutlak yol adı.|
|**$(RemoteMachine)**|Değerine ayarlanmasından **uzak makine** hata ayıklama özellik sayfasından özelliği. Bkz: [C/C++ hata ayıklama yapılandırması proje ayarları değiştirme](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) daha fazla bilgi için.|
|**$(RootNameSpace)**|Ad alanı varsa uygulamayı içeren.|
|**$(SolutionDir)**|(Sürücü + yolu tanımlanan); çözüm dizini sondaki ters eğik çizgi içerir '\\'. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionExt)**|Çözüm öğesinin dosya uzantısı. İçerdiğinden '.' dosya uzantısı önce. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionFileName)**|(Temel adı + dosya uzantısı tanımlanan) çözüm dosya adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionName)**|Çözümün temel adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionPath)**|(Sürücü yolu + temel adı + dosya uzantısı tanımlanır) çözümü mutlak yol adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(TargetDir)**|(Sürücü + yolu tanımlanan); derleme için birincil çıkış dosyasının dizini sondaki ters eğik çizgi içerir '\\'.|
|**$(TargetExt)**|Derleme için birincil çıkış dosyasının dosya uzantısı. İçerdiğinden '.' dosya uzantısı önce.|
|**$(TargetFileName)**|(Temel adı + dosya uzantısı tanımlanan) yapı için birincil çıkış dosyasının dosya adı.|
|**$(TargetName)**|Derleme için birincil çıkış dosyasının temel adı.|
|**$(TargetPath)**|Mutlak yol (sürücü yolu + temel adı + dosya uzantısı tanımlanır) yapı için birincil çıkış dosyasının adı.|
|**$(Vcınstalldir)**|Visual Studio yüklemenizin C++ içeriği içeren dizin. Bu özellik farklı olabilir hedeflenen Visual C++ araç takımı sürümünü içerir, Visual Studio ana bilgisayar. Örneğin, ile derleme yaparken `$(PlatformToolset) = v140`, **$(vcınstalldir)** Visual C++ 2015 yükleme yolunu içerir.|
|**$(Vsınstalldir)**|Visual Studio yüklü dizin. Bu özellik farklı olabilir hedeflenen Visual Studio araç takımı sürümünü içerir, Visual Studio ana bilgisayar. Örneğin, ile derleme yaparken `$(PlatformToolset) = v110`, **$(vsınstalldir)** Visual Studio 2012 yükleme yolunu içerir.|
|**$(WebDeployPath)**|Burada proje çıkışı için web dağıtım kök klasöründen göreli yolu ait. Aynı değeri döndürür <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|
|**$(WebDeployRoot)**|Konumunu mutlak yolu  **\<localhost >**. Örneğin, c:\inetpub\wwwroot.|

## <a name="obsolete-macros"></a>Eski makroları

C++ için derleme sistemi, Visual Studio 2010 ve Visual Studio 2008 arasında önemli ölçüde değişti. Önceki proje türlerinde kullanılan birçok makroları yenilerini değiştirildi. Bu makrolar artık kullanılmayan veya eşdeğer bir veya daha fazla özellik tarafından değiştirilmiş veya [öğe meta verileri makrosu](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(**_adı_**)**) değerler. Proje geçiş aracı tarafından "geçirilen" olarak işaretlenmiş makroları güncelleştirilebilir. Makro içeren projeyi Visual Studio 2008 veya daha önceki Visual Studio 2010 geçirilirse, Visual Studio eşdeğer geçerli makrosu için makro dönüştürür. Visual Studio'nun sonraki sürümlerinde projeleri Visual Studio 2008 ve daha önce yeni bir proje türü dönüştürülemiyor. Bu iki adımı projelerinde dönüştürmeniz gerekir; ilk önce bunları Visual Studio 2010'a dönüştürmek ve ardından sonucu yeni Visual Studio sürümünüze dönüştürün. Daha fazla bilgi için [olası yükseltme sorunlarına genel bakış](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$(Inputdir)**|(Geçiş) Girdi dosyasının (sürücü + yolu tanımlanan); dizin sondaki ters eğik çizgi içerir '\\'. Giriş projedir sonra Bu makroyu eşdeğerdir **$(ProjectDir)**.|
|**$(Inputext)**|(Geçiş) Giriş dosyasının dosya uzantısı. İçerdiğinden '.' dosya uzantısı önce. Giriş projedir sonra Bu makroyu eşdeğerdir **$(ProjectExt)**. Bu kaynak dosyaları için **%(Extension)**.|
|**$(Inputfilename)**|(Geçiş) Dosya adı girdi dosyasının (temel adı + dosya uzantısı olarak tanımlanır). Giriş projedir sonra Bu makroyu eşdeğerdir **$(ProjectFileName)**. Bu kaynak dosyaları için **%(Identity)**.|
|**$(Inputname)**|(Geçiş) Giriş dosyası taban adı. Giriş projedir sonra Bu makroyu eşdeğerdir **$(ProjectName)**. Bu kaynak dosyaları için **%(Filename)**.|
|**$(Inputpath)**|(Geçiş) Mutlak yol adı girdi dosyasının (sürücü yolu + temel adı + dosya uzantısı tanımlanır). Giriş projedir sonra Bu makroyu eşdeğerdir **$(ProjectPath)**. Bu kaynak dosyaları için **%(FullPath)**.|
|**$(ParentName)**|Bu proje öğesi içeren bir öğesinin adı. Bu, üst klasör adı ya da proje adı olacaktır.|
|**$(SafeInputName)**|Geçerli sınıf adı, dosya uzantısı hariç dosya adı. Bu özellik, tam bir eşdeğeri yok.|
|**$(SafeParentName)**|Geçerli bir adı biçiminde ilk üst öğe adı. Örneğin, bir .resx dosyası üst biçimidir. Bu özellik, tam bir eşdeğeri yok.|
|**$(SafeRootNamespace)**|Ad alanı adı proje sihirbazları kod ekleyeceksiniz. Bu ad alanı adı yalnızca geçerli bir C++ tanımlayıcısı izin karakterleri içerir. Bu özellik, tam bir eşdeğeri yok.|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Projeleri - C++](../creating-and-managing-visual-cpp-projects.md)
- [Visual C++ taşıma ve yükseltme Kılavuzu](../../porting/visual-cpp-porting-and-upgrading-guide.md)
- [Olası yükseltme sorunlarına genel bakış](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
