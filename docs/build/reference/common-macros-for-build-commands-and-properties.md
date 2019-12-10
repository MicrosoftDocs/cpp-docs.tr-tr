---
title: MSBuild komutları ve özellikleri için genel makrolar
ms.date: 08/02/2019
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
ms.openlocfilehash: e2c7fe6f2ea63f2cbd259e4114843fcfc28fcd84
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988333"
---
# <a name="common-macros-for-msbuild-commands-and-properties"></a>MSBuild komutları ve özellikleri için genel makrolar

Visual Studio, yükleme seçeneklerinize bağlı olarak, Visual Studio projesinde (MSBuild 'e göre) yüzlerce makro kullanabilir. Bunlar, varsayılan olarak veya. props veya. targets dosyalarında ya da proje ayarlarınızda ayarlanan MSBuild özelliklerine karşılık gelir. Bu makroları, dizelerin kabul edildiği bir projenin **Özellik sayfaları** iletişim kutusunda herhangi bir yerde kullanabilirsiniz. Bu makrolar büyük/küçük harfe duyarlı değildir.

## <a name="view-the-current-properties-and-macros"></a>Geçerli özellikleri ve makroları görüntüleme

Mevcut olan tüm makroları göstermek için, **Özellik sayfaları** iletişim kutusunda, **VC + + dizinleri**altında, bir özellik satırının sonundaki açılan oku seçin. **Düzenle** ' ye tıklayın ve ardından Düzenle Iletişim kutusunda **makrolar** düğmesini seçin. Visual Studio tarafından görülebilen geçerli özellikler ve makrolar kümesi, her biri için geçerli değer ile birlikte listelenir. Daha fazla bilgi için, [ C++ proje özellik sayfası başvurusunun](property-pages-visual-cpp.md) **Kullanıcı tanımlı değerler belirtme** bölümüne bakın.

![VC + + makroları düğmesi](../media/vcppdir_libdir_macros.png "Makrolar menüsü")

## <a name="list-of-common-macros"></a>Ortak makro listesi

Bu tabloda, kullanılabilir makroların yaygın olarak kullanılan bir alt kümesi açıklanmaktadır; Burada listelenen pek çok daha fazla bilgi vardır. Tüm özellikleri ve projenizdeki geçerli değerlerini görmek için **makrolar** iletişim kutusuna gidin. MSBuild özellik tanımlarının. props,. targets ve. vcxproj dosyalarında makro olarak nasıl oluşturulduğu ve kullanıldığı hakkında ayrıntılı bilgi için bkz. [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$ (Yapılandırma)**|Geçerli proje yapılandırmasının adı, örneğin "Debug".|
|**$ (DevEnvDir)**|Visual Studio yükleme dizini (sürücü + yol olarak tanımlanır); Sondaki ters eğik çizgi '\\' içerir.|
|**$ (FrameworkDir)**|.NET Framework yüklendiği dizin.|
|**$ (FrameworkSDKDir)**|.NET Framework yüklediğiniz dizin. .NET Framework, Visual Studio 'nun bir parçası olarak veya ayrı olarak yüklenmiş olabilir.|
|**$ (FrameworkVersion)**|Visual Studio tarafından kullanılan .NET Framework sürümü. **$ (FrameworkDir)** ile birlikte kullanıldığında, Visual Studio tarafından kullanılan .NET Framework sürümünün tam yoludur.|
|**$ (FxCopDir)**|FxCop. cmd dosyasının yolu. FxCop. cmd dosyası tüm Visual Studio sürümleriyle birlikte yüklenmez.|
|**$ (IntDir)**|Ara dosyalar için belirtilen dizinin yolu. Göreli bir yol ise, ara dosyalar proje dizinine eklenen bu yola gider. Bu yolun sonunda eğik çizgi olmalıdır. **Ara dizin** özelliği için değer olarak çözümlenir. Bu özelliği tanımlamak için **$ (OutDir)** kullanmayın.|
|**$ (OutDir)**|Çıkış dosyası dizininin yolu. Göreli bir yol ise, çıkış dosyaları proje dizinine eklenen bu yola gider. Bu yolun sonunda eğik çizgi olmalıdır. **Çıkış dizini** özelliğinin değerine çözümlenmektedir. Bu özelliği tanımlamak için **$ (IntDir)** kullanmayın.|
|**$ (Platform)**|Geçerli proje platformunun adı, örneğin "Win32".|
|**$ (PlatformShortName)**|Geçerli mimarinin kısa adı (örneğin, "x86" veya "x64").|
|**$ (ProjectDir)**|Projenin dizini (sürücü + yol olarak tanımlanır); Sondaki ters eğik çizgi '\\' içerir.|
|**$ (ProjectExt)**|Projenin dosya uzantısı. Dosya uzantısından önce '. ' içerir.|
|**$ (ProjectFileName)**|Projenin dosya adı (taban adı + dosya uzantısı olarak tanımlanır).|
|**$ (ProjectName)**|Projenin temel adı.|
|**$ (ProjectPath)**|Projenin mutlak yol adı (sürücü + yol + taban adı + dosya uzantısı olarak tanımlanır).|
|**$ (PublishDir)**|Yayımla hedefi için çıkış konumu; Sondaki ters eğik çizgi '\\' içerir. Varsayılan olarak **$ (OutDir) App. publish\\** klasörüdür.|
|**$ (RemoteMachine)**|Hata ayıklama özelliği sayfasında, **uzak makine** özelliğinin değerine ayarlanır. Daha fazla bilgi için bkz. [C/C++ Debug yapılandırması Için proje ayarlarını değiştirme](/visualstudio/debugger/project-settings-for-a-cpp-debug-configuration) .|
|**$ (RootNameSpace)**|Varsa, uygulamayı içeren ad alanı.|
|**$ (SolutionDir)**|Çözümün dizini (sürücü + yol olarak tanımlanır); Sondaki ters eğik çizgi '\\' içerir. Yalnızca IDE 'de bir çözüm oluşturulurken tanımlanır.|
|**$ (SolutionExt)**|Çözümün dosya uzantısı. Dosya uzantısından önce '. ' içerir. Yalnızca IDE 'de bir çözüm oluşturulurken tanımlanır.|
|**$ (SolutionFileName)**|Çözümün dosya adı (temel ad + dosya uzantısı olarak tanımlanır). Yalnızca IDE 'de bir çözüm oluşturulurken tanımlanır.|
|**$ (SolutionName)**|Çözümün temel adı. Yalnızca IDE 'de bir çözüm oluşturulurken tanımlanır.|
|**$ (SolutionPath)**|Çözümün mutlak yol adı (sürücü + yol + taban adı + dosya uzantısı olarak tanımlanır). Yalnızca IDE 'de bir çözüm oluşturulurken tanımlanır.|
|**$ (TARGETDIR)**|Derleme için birincil çıkış dosyasının dizini (sürücü + yol olarak tanımlanır); Sondaki ters eğik çizgi '\\' içerir.|
|**$ (TargetExt)**|Derleme için birincil çıkış dosyasının dosya uzantısı. Dosya uzantısından önce '. ' içerir.|
|**$ (TargetFileName)**|Derleme için birincil çıkış dosyasının dosya adı (temel ad + dosya uzantısı olarak tanımlanır).|
|**$ (TargetName)**|Derleme için birincil çıkış dosyasının temel adı.|
|**$ (TargetPath)**|Derleme için birincil çıkış dosyasının mutlak yol adı (sürücü + yol + taban adı + dosya uzantısı olarak tanımlanır).|
|**$ (VCInstallDir)**|Visual Studio yüklemenizin C++ içeriğini içeren dizin. Bu özellik hedeflenen Microsoft C++ (MSVC) araç takımının, Visual Studio 'nun barındırıcı farklı olabilen sürümünü içerir. Örneğin, `$(PlatformToolset) = v140`ile derlerken, **$ (VCInstallDir)** , Visual Studio 2015 yüklemesinin yolunu içerir.|
|**$ (VSInstallDir)**|Visual Studio 'Yu yüklediğiniz dizin. Bu özellik hedeflenen Visual Studio araç takımının sürümünü içerir ve bu, Visual Studio 'nun barındırıcı farklı olabilir. Örneğin, `$(PlatformToolset) = v110`ile derlerken, **$ (VSInstallDir)** , Visual Studio 2012 yüklemesinin yolunu içerir.|
|**$ (WebDeployPath)**|Web Dağıtım kökünden proje çıkışların ait olduğu yere göreli yol.|
|**$ (WebDeployRoot)**|**\<localhost >** konumunun mutlak yolu. Örneğin, c:\inetpub\wwwroot.|

## <a name="obsolete-macros"></a>Kullanılmayan makrolar

İçin C++ derleme sistemi, visual Studio 2008 Ile visual Studio 2010 arasında önemli ölçüde değiştirilmiştir. Daha önceki proje türlerinde kullanılan birçok makro yeni olanlarla değiştirilmiştir. Bu makrolar artık kullanılmıyor veya bir veya daha fazla eşdeğer özellik ya da [öğe meta veri makrosu](/visualstudio/msbuild/itemmetadata-element-msbuild) ( **%(** _ad_ **)** ) değeri tarafından değiştirildi. "Geçirilmiş" olarak işaretlenen makrolar, proje geçiş aracı tarafından güncelleştirilebilen olabilir. Makroyu içeren proje Visual Studio 2008 veya daha eski bir sürümden Visual Studio 2010 ' ye geçirilirse, Visual Studio makroyu eşdeğer geçerli makroya dönüştürür. Visual Studio 'nun sonraki sürümleri, projeleri Visual Studio 2008 ve önceki sürümlerden yeni proje türüne dönüştüremiyor. Bu projeleri iki adımda dönüştürmeniz gerekir; önce bunları Visual Studio 2010 ' e dönüştürün ve sonra sonucu Visual Studio 'nun daha yeni sürümüne dönüştürün. Daha fazla bilgi için bkz. [olası yükseltme sorunlarına genel bakış](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md).

|Makrosu|Açıklama|
|-----------|-----------------|
|**$ (InputDir)**|(Geçirilmiş.) Giriş dosyasının dizini (sürücü + yol olarak tanımlanır); Sondaki ters eğik çizgi '\\' içerir. Eğer proje giriş ise, bu makro **$ (ProjectDir)** ile eşdeğerdir.|
|**$ (InputExt)**|(Geçirilmiş.) Giriş dosyasının dosya uzantısı. Dosya uzantısından önce '. ' içerir. Eğer proje giriş ise, bu makro **$ (ProjectExt)** ile eşdeğerdir. Kaynak dosyaları için **% (uzantı)** .|
|**$ (Inputfilename)**|(Geçirilmiş.) Giriş dosyasının dosya adı (taban adı + dosya uzantısı olarak tanımlanır). Proje giriş ise, bu makro **$ (ProjectFileName)** ile eşdeğerdir. Kaynak dosyaları için bu değer **% (kimlik)** .|
|**$ (Inputname)**|(Geçirilmiş.) Giriş dosyasının temel adı. Eğer proje giriş ise, bu makro **$ (ProjectName)** ile eşdeğerdir. Kaynak dosyaları için **% (filename)** .|
|**$ (Inputpath)**|(Geçirilmiş.) Giriş dosyasının mutlak yol adı (sürücü + yol + taban adı + dosya uzantısı olarak tanımlanır). Eğer proje giriş ise, bu makro **$ (ProjectPath)** ile eşdeğerdir. Kaynak dosyaları için bu değer **% (FullPath)** .|
|**$ (ParentName)**|Bu proje öğesini içeren öğenin adı. Bu, üst klasör adı veya proje adı olacaktır.|
|**$ (Safeınputname)**|Dosyanın adı geçerli bir sınıf adı, eksi dosya uzantısı. Bu özelliğin tam bir eşdeğeri yoktur.|
|**$ (SafeParentName)**|Geçerli ad biçiminde hemen üst öğenin adı. Örneğin, bir form. resx dosyasının üst öğesidir. Bu özelliğin tam bir eşdeğeri yoktur.|
|**$ (SafeRootNamespace)**|Proje sihirbazlarının kod ekleneceği ad alanı adı. Bu ad alanı adı, yalnızca geçerli C++ bir tanımlayıcıda izin verilen karakterler içerir. Bu özelliğin tam bir eşdeğeri yoktur.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio projeleri- C++ ](../creating-and-managing-visual-cpp-projects.md)\
[Görsel C++ taşıma ve Yükseltme Kılavuzu](../../porting/visual-cpp-porting-and-upgrading-guide.md)\
[Olası yükseltme sorunlarına genel bakış](../../porting/overview-of-potential-upgrade-issues-visual-cpp.md)
