---
title: Derleme komutları ve özellikler için ortak makroları
ms.custom: ''
ms.date: 05/29/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
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
- SolutionPath macro $(SolutionPath)
ms.assetid: 239bd708-2ea9-4687-b264-043f1febf98b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 278cb34a49650d88b9e7de9efd8456ff430aca63
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34569933"
---
# <a name="common-macros-for-build-commands-and-properties"></a>Derleme komutları ve özellikler için ortak makroları

Yükleme seçenekleri bağlı olarak, Visual Studio Makroları yüzlerce size sunabilirsiniz. Bunlar varsayılan olarak, veya .props veya .targets dosyaları veya proje ayarlarınızı ayarlanır MSBuild özellikleri karşılık gelir. Bu makroları bir projesinin yerde kullanabilir **özellik sayfaları** iletişim kutusu burada dizeleri kabul edilir. Bu makrolar büyük küçük harfe duyarlı değildir.

## <a name="view-the-current-properties-and-macros"></a>Makrolar ve geçerli özelliklerini görüntüleyin

Şu anda kullanılabilir makroları hiçbir özellik sayfasını görüntülemek için **özellik sayfaları** iletişim kutusunda, bir özellik satırın sonunda aşağı açılan okunu seçin. Varsa **Düzenle** kullanılabilir, onu seçin ve ardından Düzenle iletişim kutusunda **makroları** düğmesi. Özellikleri ve makrolar Visual Studio'ya görünür geçerli kümesini her biri için geçerli değeri ile birlikte listelenir. Daha fazla bilgi için bkz: **Specifying User-Defined değerleri** bölümünü [özellik sayfaları](../ide/property-pages-visual-cpp.md).

## <a name="list-of-common-macros"></a>Ortak makroları listesi

Bu tabloda kullanılabilir makroları yaygın olarak kullanılan bir kısmı açıklanmıştır. Bu liste geniş kapsamlı gölgeden uzak olan. MSBuild özelliği tanımları nasıl oluşturulduğunu ve .props .targets dosyaları ve .vcxproj makroları olarak kullanılan ile ilgili ayrıntılar için bkz: [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$(Configuration)**|Geçerli proje yapılandırması, örneğin, "Hata ayıklama" adı.|
|**$(DevEnvDir)**|Yükleme dizini, Visual Studio'nun (sürücü + yolu tanımlanan); eğik içeren '\\'.|
|**$(FrameworkDir)**|.NET Framework yüklendiği dizin.|
|**$(FrameworkSDKDir)**|.NET Framework yüklü dizin. .NET Framework Visual Studio veya ayrı ayrı bir parçası yüklenmiş.|
|**$(FrameworkVersion)**|Visual Studio tarafından kullanılan .NET Framework sürümü. Birlikte **$(FrameworkDir)**, Visual Studio .NET Framework kullanarak sürümü tam yolu.|
|**$(FxCopDir)**|Fxcop.cmd dosyasının yolu. Fxcop.cmd dosya ile tüm Visual C++ sürümleri yüklü değil.|
|**$(Intdir)**|Ara dosyaları için belirtilen dizin yolu. Bu göreli bir yol ise, Ara dosyaları proje dizinine eklenmiş bu yoluna gidin. Bu yolu bir eğik çizgiyle içermelidir. Bu değeri çözümler **Ara dizin** özelliği. Kullanmayın **$(OutDir)** bu özellik tanımlamak için.|
|**$(OutDir)**|Çıkış dosyası dizin yolu. Bu göreli bir yol ise, çıktı dosyalarını proje dizinine eklenmiş bu yoluna gidin. Bu yolu bir eğik çizgiyle içermelidir. Bu değeri çözümler **çıktı dizini** özelliği. Kullanmayın **$(ıntdir)** bu özellik tanımlamak için.|
|**$(Platform)**|Örneğin, "Win32" bir geçerli proje platform adı.|
|**$(ProjectDir)**|(Sürücü + yolu tanımlanan); projenin dizini eğik içeren '\\'.|
|**$(ProjectExt)**|Projenin dosya uzantısı. İçerdiği '.' önce dosya uzantısı.|
|**$(ProjectFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) proje dosya adı.|
|**$(ProjectName)**|Projenin temel adı.|
|**$(ProjectPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) projenin mutlak bir yol adı.|
|**$(RemoteMachine)**|Değerine ayarlanmış **uzak makine** hata ayıklama özellik sayfası özelliği. Bkz: [bir C/C++ hata ayıklama yapılandırması proje ayarları değiştirme](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) daha fazla bilgi için.|
|**$(RootNameSpace)**|Ad alanı, varsa, uygulamayı içeren.|
|**$(SolutionDir)**|(Sürücü + yolu tanımlanan); çözüm dizini eğik içeren '\\'. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionExt)**|Çözüm dosya uzantısı. İçerdiği '.' önce dosya uzantısı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) çözüm dosya adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionName)**|Çözümün temel adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(SolutionPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) çözümü mutlak bir yol adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|
|**$(TargetDir)**|(Sürücü + yolu tanımlanan); derleme için birincil çıkış dosyasının dizin eğik içeren '\\'.|
|**$(TargetExt)**|Derleme için birincil çıkış dosyasının dosya uzantısı. İçerdiği '.' önce dosya uzantısı.|
|**$(TargetFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) derleme için birincil çıkış dosyasının dosya adı.|
|**$(TargetName)**|Derleme için birincil çıkış dosyasının temel adı.|
|**$(TargetPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) derleme için birincil çıkış dosyasının mutlak bir yol adı.|
|**$(Vcınstalldir)**|Visual Studio yüklemenizin C++ içeriğin bulunduğu dizin. Bu özellik, farklı olabilir hedeflenen Visual C++ araç takımını sürümünü içerir, Visual Studio ana bilgisayar. Örneğin, ile oluştururken `$(PlatformToolset) = v140`, **$(vcınstalldir)** Visual C++ 2015 yükleme yolunu içerir.|
|**$(Vsınstalldir)**|Visual Studio yüklü dizin. Bu özellik, farklı olabilir hedeflenen Visual Studio araç takımı sürümünü içerir, Visual Studio ana bilgisayar. Örneğin, ile oluştururken `$(PlatformToolset) = v110`, **$(vsınstalldir)** Visual Studio 2012 yükleme yolunu içerir.|
|**$(WebDeployPath)**|Burada proje çıkarır göreli yolu web dağıtımı kök ait. Aynı değeri döndürür <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|
|**$(WebDeployRoot)**|Konumu mutlak yolu  **\<localhost >**. Örneğin, c:\inetpub\wwwroot.|

## <a name="obsolete-macros"></a>Artık kullanılmayan makroları

Derleme Sistemi C++ için Visual Studio 2010 ve Visual Studio 2008 arasında önemli ölçüde değiştirildi. Önceki proje türlerinde kullanılan birçok makroları yenilerini için değiştirilmiştir. Bu makrolar artık kullanılmayan veya bir veya daha fazla eşdeğer özellikleri tarafından değiştirilmiş veya [öğe meta veri makrosu](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(**_adı_**)**) değerler. "Geçirilen" olarak işaretlenmiş makroları proje geçiş aracı tarafından güncelleştirilebilir. Makro içeren projesini Visual Studio 2008 veya daha önceki Visual Studio 2010 geçirilirse, Visual Studio makrosu eşdeğer geçerli makrosu dönüştürür. Visual Studio sonraki sürümlerini projeleri, Visual Studio 2008 ve daha önce yeni proje türüne dönüştürülemiyor. Bu iki adımı projelerde dönüştürmeniz gerekir; bunları Visual Studio 2010 dönüştürmeniz ve ardından sonucu, Visual Studio'nun daha yeni sürüme dönüştürebilirsiniz. Daha fazla bilgi için bkz: [olası yükseltme sorunlarını genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$(Inputdir)**|(Geçirildi.) (Sürücü + yolu tanımlanan); giriş dosyası dizini eğik içeren '\\'. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectDir)**.|
|**$(Inputext)**|(Geçirildi.) Giriş dosyasının dosya uzantısı. İçerdiği '.' önce dosya uzantısı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectExt)**. Kaynak dosyaları için budur **%(Extension)**.|
|**$(Inputfilename)**|(Geçirildi.) (Temel adı + dosya uzantısı olarak tanımlanan) giriş dosyasının dosya adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectFileName)**. Kaynak dosyaları için budur **%(Identity)**.|
|**$(Inputname)**|(Geçirildi.) Giriş dosyası temel adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectName)**. Kaynak dosyaları için budur **%(Filename)**.|
|**$(Inputpath)**|(Geçirildi.) Giriş dosyası (sürücü + yolu + temel ad + dosya uzantısı tanımlı) mutlak bir yol adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectPath)**. Kaynak dosyaları için budur **%(FullPath)**.|
|**$(ParentName)**|Bu proje öğesi içeren öğenin adı. Bu üst klasör adı ya da proje adı olacaktır.|
|**$(SafeInputName)**|Geçerli bir sınıf adı, dosya uzantısı eksi olarak dosyasının adı. Bu özellik, tam bir eşdeğeri yok.|
|**$(SafeParentName)**|Geçerli ad biçimi hemen üst adı. Örneğin, bir üst .resx dosyası biçimidir. Bu özellik, tam bir eşdeğeri yok.|
|**$(SafeRootNamespace)**|Ad alanı adı proje sihirbazları kod ekleyeceksiniz. Bu ad alanı adı yalnızca geçerli bir C++ tanımlayıcı izin karakter içerir. Bu özellik, tam bir eşdeğeri yok.|

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio'da C++ Projeleri Derleme](../ide/building-cpp-projects-in-visual-studio.md)
- [Visual C++ taşıma ve yükseltme Kılavuzu](../porting/visual-cpp-porting-and-upgrading-guide.md)
- [Olası yükseltme sorunlarını genel bakış](../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
