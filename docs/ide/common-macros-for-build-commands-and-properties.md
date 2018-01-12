---
title: "Derleme komutları ve özellikler için ortak makrolar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs: C++
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
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f96e403516d6f85804fa798d7a0c28575482ff43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="common-macros-for-build-commands-and-properties"></a>Derleme komutları ve özellikler için ortak makroları
Yükleme seçenekleri bağlı olarak, Visual Studio Makroları yüzlerce size sunabilirsiniz. Bunlar varsayılan olarak, veya .props veya .targets dosyaları veya proje ayarlarınızı ayarlanır MSBuild özellikleri karşılık gelir. Bu makroları bir projesinin yerde kullanabilir **özellik sayfaları** iletişim kutusu burada dizeleri kabul edilir. Bu makrolar büyük küçük harfe duyarlı değildir.  
  
 Bir özellik adı sağına sütun şu anda kullanılabilir makroları görüntülemek için açılan oku tıklatın. Varsa **Düzenle** kullanılabilir tıklatın ve ardından Düzenle iletişim kutusunda **makroları**. Daha fazla bilgi için bkz: **Specifying User-Defined değerleri** bölümünü [özellik sayfaları](../ide/property-pages-visual-cpp.md).  
  
 "Kullanım dışı" olarak işaretlenmiş makroları artık kullanılmamaktadır veya eşdeğer bir tarafından değiştirilen [öğe meta veri makrosu](/visualstudio/msbuild/itemmetadata-element-msbuild) (**%(***adı***)**) . "Kullanım dışı; olarak işaretlenmiş makroları geçirilen"de kullanım dışı bırakılmıştır. Ve makrosu içeren projesini Visual Studio 2008'den geçirdiyseniz, Visual Studio eşdeğer geçerli makrosu için makro ek olarak, dönüştürür.  
  
 Aşağıdaki tabloda kullanılabilir makroları yaygın olarak kullanılan bir kısmı açıklanmaktadır. Bu liste geniş kapsamlı değildir. MSBuild özelliği tanımları nasıl oluşturulduğunu ve .props .targets dosyaları ve .vcxproj makroları olarak kullanılan ile ilgili ayrıntılar için bkz: [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).  
  
|Makrosu|Açıklama|  
|-----------|-----------------|  
|**$(RemoteMachine)**|Değerine ayarlanmış **uzak makine** hata ayıklama özellik sayfası özelliği. Bkz: [bir C/C++ hata ayıklama yapılandırması proje ayarları değiştirme](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) daha fazla bilgi için.|  
|**$(Configuration)**|Geçerli proje yapılandırması, örneğin, "Hata ayıklama" adı.|  
|**$(Platform)**|Örneğin, "Win32" bir geçerli proje platform adı.|  
|**$(ParentName)**|(Kullanım dışı). Bu proje öğesi içeren öğenin adı. Bu üst klasör adı ya da proje adı olacaktır.|  
|**$(RootNameSpace)**|Ad alanı, varsa, uygulamayı içeren.|  
|**$(Intdir)**|Ara dosyaları için belirtilen dizin yolu. Bu göreli bir yol ise, Ara dosyaları proje dizinine eklenmiş bu yoluna gidin. Bu yolu bir eğik çizgiyle içermelidir. Bu değeri çözümler **Ara dizin** özelliği. Kullanmayın **$(OutDir)** bu özellik tanımlamak için.|  
|**$(OutDir)**|Çıkış dosyası dizin yolu. Bu göreli bir yol ise, çıktı dosyalarını proje dizinine eklenmiş bu yoluna gidin. Bu yolu bir eğik çizgiyle içermelidir. Bu değeri çözümler **çıktı dizini** özelliği. Kullanmayın **$(ıntdir)** bu özellik tanımlamak için.|  
|**$(DevEnvDir)**|Yükleme dizini, Visual Studio'nun (sürücü + yolu tanımlanan); eğik içeren '\\'.|  
|**$(Inputdir)**|(Kullanım dışı; geçirilen.) (Sürücü + yolu tanımlanan); giriş dosyası dizini eğik içeren '\\'. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectDir)**.|  
|**$(Inputpath)**|(Kullanım dışı; geçirilen.) Giriş dosyası (sürücü + yolu + temel ad + dosya uzantısı tanımlı) mutlak bir yol adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectPath)**.|  
|**$(Inputname)**|(Kullanım dışı; geçirilen.) Giriş dosyası temel adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectName)**.|  
|**$(Inputfilename)**|(Kullanım dışı; geçirilen.) (Temel adı + dosya uzantısı olarak tanımlanan) giriş dosyasının dosya adı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectFileName)**.|  
|**$(Inputext)**|(Kullanım dışı; geçirilen.) Giriş dosyasının dosya uzantısı. İçerdiği '.' önce dosya uzantısı. Giriş projedir sonra bu makrosu eşdeğerdir **$(ProjectExt)**.|  
|**$(ProjectDir)**|(Sürücü + yolu tanımlanan); projenin dizini eğik içeren '\\'.|  
|**$(ProjectPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) projenin mutlak bir yol adı.|  
|**$(ProjectName)**|Projenin temel adı.|  
|**$(ProjectFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) proje dosya adı.|  
|**$(ProjectExt)**|Projenin dosya uzantısı. İçerdiği '.' önce dosya uzantısı.|  
|**$(SolutionDir)**|(Sürücü + yolu tanımlanan); çözüm dizini eğik içeren '\\'. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|  
|**$(SolutionPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) çözümü mutlak bir yol adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|  
|**$(SolutionName)**|Çözümün temel adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|  
|**$(SolutionFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) çözüm dosya adı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|  
|**$(SolutionExt)**|Çözüm dosya uzantısı. İçerdiği '.' önce dosya uzantısı. Yalnızca IDE'de bir çözüm oluşturulurken tanımlanır.|  
|**$(TargetDir)**|(Sürücü + yolu tanımlanan); derleme için birincil çıkış dosyasının dizin eğik içeren '\\'.|  
|**$(TargetPath)**|(Sürücü + yolu + temel ad + dosya uzantısı tanımlanan) derleme için birincil çıkış dosyasının mutlak bir yol adı.|  
|**$(TargetName)**|Derleme için birincil çıkış dosyasının temel adı.|  
|**$(TargetFileName)**|(Temel adı + dosya uzantısı olarak tanımlanan) derleme için birincil çıkış dosyasının dosya adı.|  
|**$(TargetExt)**|Derleme için birincil çıkış dosyasının dosya uzantısı. İçerdiği '.' önce dosya uzantısı.|  
|**$(Vsınstalldir)**|Visual Studio yüklü dizin.<br /><br /> Bu özellik hedeflenen Visual Studio'nun sürümü, hangi farklı olabilir, içerir, Visual Studio ana bilgisayar. Örneğin, ile oluştururken `$(PlatformToolset) = v110`, **$(vsınstalldir)** Visual Studio 2012 yükleme yolunu içerir.|  
|**$(Vcınstalldir)**|Visual C++ yüklü dizin.<br /><br /> Bu özellik hedeflenen Visual C++ sürümlerinden biri, farklı olabilir, içerir, Visual Studio ana bilgisayar. Örneğin, ile oluştururken `$(PlatformToolset) = v140`, **$(vcınstalldir)** Visual C++ 2015 yükleme yolunu içerir.|  
|**$(FrameworkDir)**|.NET Framework yüklendiği dizin.|  
|**$(FrameworkVersion)**|Visual Studio tarafından kullanılan .NET Framework sürümü. Birlikte **$(FrameworkDir)**, Visual Studio .NET Framework kullanarak sürümü tam yolu.|  
|**$(FrameworkSDKDir)**|.NET Framework yüklü dizin. .NET Framework Visual Studio veya ayrı ayrı bir parçası yüklenmiş.|  
|**$(WebDeployPath)**|Burada proje çıkarır göreli yolu web dağıtımı kök ait. Aynı değeri döndürür <xref:Microsoft.VisualStudio.VCProjectEngine.VCWebDeploymentTool.RelativePath%2A>.|  
|**$(WebDeployRoot)**|Konumu mutlak yolu  **\<localhost >**. Örneğin, c:\inetpub\wwwroot.|  
|**$(SafeParentName)**|(Kullanım dışı). Geçerli ad biçimi hemen üst adı. Örneğin, bir üst .resx dosyası biçimidir.|  
|**$(SafeInputName)**|(Kullanım dışı). Geçerli bir sınıf adı, dosya uzantısı eksi olarak dosyasının adı.|  
|**$(SafeRootNamespace)**|(Kullanım dışı). Ad alanı adı proje sihirbazları kod ekleyeceksiniz. Bu ad alanı adı yalnızca geçerli bir C++ tanımlayıcı izin karakter içerir.|  
|**$(FxCopDir)**|Fxcop.cmd dosyasının yolu. Fxcop.cmd dosya ile tüm Visual C++ sürümleri yüklü değil.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual Studio'da C++ Projeleri Derleme](../ide/building-cpp-projects-in-visual-studio.md)