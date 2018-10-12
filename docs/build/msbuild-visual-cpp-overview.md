---
title: MSBuild (Visual C++) genel bakış | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c337ec94f863e6c19851bcf962db61f277491cf
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163250"
---
# <a name="msbuild-visual-c-overview"></a>MSBuild (Visual C++) Genel Bakış

Derleme sistemidir Visual C++ projeleri için MSBuild olur. Visual Studio tümleşik geliştirme ortamında (IDE) proje oluşturduğunuzda, msbuild.exe aracını, XML tabanlı proje dosyasını ve isteğe bağlı ayar dosyalarını kullanır. Msbuild.exe ve komut satırında bir proje dosyası kullanabilmenize rağmen IDE bir kullanıcı arabirimi sağlar, böylece daha kolay ayarlarını yapılandırmak ve bir proje oluşturun. Bu genel bakış, Visual C++'ın MSBuild sistemini nasıl kullandığını açıklar.

## <a name="prerequisites"></a>Önkoşullar

MSBuild hakkında aşağıdaki belgeleri okuyun.

- [MSBuild](/visualstudio/msbuild/msbuild) genel bakış, MSBuild kavramları.

- [MSBuild başvurusu](/visualstudio/msbuild/msbuild-reference) MSBuild sistemi ilgili başvuru bilgileri.

- [Proje dosyası şema başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference) özelliklerini ve üst ve alt öğeleri ile birlikte MSBuild XML şema öğelerini listeler. Özellikle dikkat edin [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [hedef](/visualstudio/msbuild/target-element-msbuild), ve [görev](/visualstudio/msbuild/task-element-msbuild) öğeleri.

- [Komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) komut satırı bağımsız değişkenlerini ve msbuild.exe ile kullanabileceğiniz seçenekleri açıklar.

- [Görev başvurusu](/visualstudio/msbuild/msbuild-task-reference) açıklar MSBuild görevleri. Özellikle, Visual C++'a özel görevlere dikkat edin: [BscMake görevi](/visualstudio/msbuild/bscmake-task), [CL görevi](/visualstudio/msbuild/cl-task), [CPPClean görevi](/visualstudio/msbuild/cppclean-task), [LIB görevi](/visualstudio/msbuild/lib-task), [Bağlantı görev](/visualstudio/msbuild/link-task), [MIDL görevi](/visualstudio/msbuild/midl-task), [MT görevi](/visualstudio/msbuild/mt-task), [RC görevi](/visualstudio/msbuild/rc-task), [SetEnv görevi](/visualstudio/msbuild/setenv-task), [ VCMessage görevi](/visualstudio/msbuild/vcmessage-task), [XDCMake görevi](/visualstudio/msbuild/xdcmake-task), [XSD görevi](/visualstudio/msbuild/xsd-task).

## <a name="msbuild-on-the-command-line"></a>Komut satırında MSBuild

Aşağıdaki ifade [MSBuild komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) msbuild.exe aracının kapalı veya açık aldığını gösterir *project_file* bağımsız değişkeni (Visual C++ projeleri için bir .vcxproj dosyası) ve sıfır veya daha fazla komut satırı *seçenekleri* bağımsız değişkenler.

> **MSBuild.exe** [ *project_file* ] [ *seçenekleri* ]

Kullanım **/target** (veya **/t**) ve **/Property** (veya **/p**) belirli özelliklerine ve olan hedefleri geçersiz kılmak için komut satırı seçenekleri Proje dosyasında belirtilen.

Proje dosyasının asıl işlevi belirtmek için olan bir *hedef*, projenizin ve girişlere ve çıkışlara bu işlemi gerçekleştirmek için gereken uygulanacak belirli bir işlem olduğu. Bir proje dosyası, varsayılan hedefin içerebileceği bir veya daha fazla hedefleri belirtebilirsiniz.

Her hedef bir veya daha fazla bir dizi oluşur *görevleri*. Her görev bir yürütülebilir komut içeren bir .NET Framework sınıfı tarafından temsil edilir. Örneğin, [CL görevi](/visualstudio/msbuild/cl-task) içeren [cl.exe](../build/reference/compiling-a-c-cpp-program.md) komutu.

A *görev parametresi* sınıf görevi özelliğidir ve genellikle yürütülebilir komutun komut satırı seçeneğini temsil eder. Örneğin, `FavorSizeOrSpeed` parametresinin `CL` görev karşılık gelen **/Os** ve **/Ot** derleyici seçenekleri.

Ek görev parametreleri MSBuild altyapısını destekler. Örneğin, `Sources` görev parametresi, diğer görevler tarafından tüketilebilecek bir görevler kümesini belirtir. Msbuil görevleri hakkında daha fazla bilgi için bkz. [görev başvurusu](/visualstudio/msbuild/msbuild-task-reference).

Çoğu görevler, girdileri ve çıktıları, dosya adları, yollar ve dize, sayısal ya da Boole parametreleri gibi gerektirir. Örneğin, ortak bir giriş derlenecek bir .cpp kaynak dosyasının adıdır. Önemli girdi parametresi yapı yapılandırması ve platformu, örneğin, belirten bir dizedir "hata ayıklama\|Win32". Giriş ve çıkışları bir veya daha fazla kullanıcı tarafından tanımlanan XML tarafından belirtilen `Item` içindeki öğe bir `ItemGroup` öğesi.

Kullanıcı tanımlı bir proje dosyası da belirtebilirsiniz *özellikleri* ve `ItemDefinitionGroup` *öğeleri*. Özellikler ve öğeler yapıda değişkenler olarak kullanılabilen ad/değer çiftlerini oluşturur. Bir çiftin ad bileşeni tanımlayan bir *makrosu*, ve değer bileşeni bildirir *makro değerini*. Özellik makrosuna $ kullanılarak erişilen (*adı*) gösterimi yanı sıra, öğe makrosu erişilen kullanarak %(*adı*) gösterimi.

Project dosyasındaki diğer XML öğeleri makroları test ve daha sonra koşullu olarak herhangi bir makronun değerini ayarlayabilir veya yapının yürütülmesini denetleme. Makro adları ve değişmez değer dizeleri, yol ve dosya adı gibi yapılar oluşturmak için birleştirilebilir. Komut satırında **/Property** seçeneği ayarlar ya da proje özelliğini geçersiz kılar. Öğeleri, komut satırında başvurulamaz.

Önce veya sonra başka bir hedef, MSBuild sistemi bir hedefi koşullu olarak yürütebilir. Ayrıca, sistem hedefin kullandığı dosyaların yaydığı dosyalardan daha yeni olup şirket tabanlı bir hedef oluşturabilir.

## <a name="msbuild-in-the-ide"></a>IDE içindeki MSBuild

IDE'de proje özelliklerini ayarlayın ve projeyi kaydettiğinizde, Visual C++ proje ayarlarını proje dosyanıza yazar. Proje dosyası projenize özgü ayarları içerir, ancak projenizi oluşturmak için gereken tüm ayarları içermiyor. Proje dosyasını içeren `Import` içeren ek bir ağ öğelerini *destek dosyaları.* Destek dosyaları geri kalan özellikleri, hedefleri ve projeyi oluşturmak için gerekli ayarları içerir.

Çoğu hedef ve Destek dosyalarını özellikler yalnızca yapı sistemini uygulamak için mevcut. Aşağıdaki bölümde, bazı yararlı hedefler ve MSBuild komut satırında belirtebileceğiniz özellikler açıklanmaktadır. Daha fazla hedef ve özellik keşfetmek için destek dosyası dizinlerindeki dosyaları inceleyin.

### <a name="support-file-directories"></a>Destek dosyası dizinleri

Varsayılan olarak birincil Visual C++ destek dosyaları aşağıdaki dizinlerde bulunur. Microsoft Visual Studio dizinlerde MSBuild altındaki dizinleri Visual Studio 2015 ve önceki sürümleri tarafından kullanılan Visual Studio 2017 ve sonraki sürümler tarafından kullanılabilir.

|Dizin|Açıklama|
|---------------|-----------------|
|*Sürücü*: \Program dosyaları *(x86)* \Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*Sürücü*: \Program dosyaları *(x86)* \MSBuild\Microsoft.Cpp (x86) \v4.0\\*sürümü*\ |Birincil hedef dosyalarını (.targets) içerir ve hedefler tarafından kullanılan özellik dosyalarını (.props). Varsayılan olarak $(VCTargetsPath) makro bu dizine başvurur.|
|*Sürücü*: \Program dosyaları *(x86)* \Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ Platformları\\*platformu*\ <br /><br />*Sürücü*: \Program dosyaları *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*sürüm*\Platforms\\*platformu*\ |Hedefleri ve özellikleri üst dizinindeki geçersiz kılma platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, içindeki hedefler tarafından kullanılan görevleri tanımlayan bir DLL de içerir.<br /><br /> *Platform* yer tutucusu, ARM, Win32 veya x64 gösterir alt.|
|*Sürücü*: \Program dosyaları *(x86)* \Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ Platformları\\*platform*\PlatformToolsets\\*araç takımı*\ <br /><br />*Sürücü*: \Program dosyaları *(x86)* \MSBuild\Microsoft.Cpp\v4.0\\*sürüm*\Platforms\\*platform*\ PlatformToolsets\\*araç takımı*\ <br /><br />*Sürücü*: \Program dosyaları *(x86)* \MSBuild\Microsoft.Cpp\v4.0\Platforms\\*platform*\PlatformToolsets\\*araç takımı*\ |Belirtilen kullanarak Visual C++ uygulamalarını oluşturmasını sağlayan dizinleri içerir *araç takımı*.<br /><br /> *Yıl* ve *edition* yer tutucuları, Visual Studio 2017 ve sonraki sürümleri tarafından kullanılır. *Sürüm* V110 Visual Studio 2012 için Visual Studio 2013 için V120 veya V140 Visual Studio 2015 için yer tutucu. *Platform* yer tutucusu, ARM, Win32 veya x64 gösterir alt. *Araç takımı* yer tutucusu v120_xp Windows XP için v110_wp80 veya Visual Studio 2013 araç takımı kullanarak oluşturmak için Visual Studio 2015 Araç Takımı'nı kullanarak Windows uygulamaları oluşturmaya yönelik örnek v140 araç kümesi alt dizinini temsil eder Visual Studio 2012 araç setini kullanarak Windows Phone 8.0 uygulamaları oluşturun.<br /><br />Visual C++ 2008 veya Visual C++ 2010 uygulamaları oluşturmasını sağlayan dizinleri içeren yolu içermez *sürüm*ve *platform* yer tutucusu temsil eder Itanium Win32 veya x64 alt. *Araç takımı* yer tutucusu v90 veya v100 araç kümesi alt dizinini temsil eder.|

### <a name="support-files"></a>Destek dosyaları

Dizinlere ilişkin destek Aşağıdaki uzantılara sahip dosyaları içerir:

|Uzantı|Açıklama|
|---------------|-----------------|
|.targets|İçeren `Target` hedefe göre yürütülen görevleri belirleyen XML öğeleri. Ayrıca içerebilir `PropertyGroup`, `ItemGroup`, `ItemDefinitionGroup`ve kullanıcı tanımlı `Item` görev parametrelerine dosyalar ve komut satırı seçenekleri atamak için kullanılan öğeleri.<br /><br /> Daha fazla bilgi için [hedef öğe (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|
|.props|İçeren `Property Group` ve kullanıcı tanımlı `Property` bir yapı sırasında kullanılan dosya ve parametre ayarlarını belirleyen XML öğeleri.<br /><br /> Ayrıca içerebilir `ItemDefinitionGroup` ve kullanıcı tanımlı `Item` ek ayarları belirtmek XML öğeleri. Bir öğe tanım grubu içinde tanımlanan öğeler özelliklere benzer ancak komut satırından erişilemez. Visual C++ proje dosyalarını sık kullandığı öğeleri özelliklerin yerine ayarları göstermek için.<br /><br /> Daha fazla bilgi için [ItemGroup öğesi (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [Itemdefinitiongroup öğesi (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), ve [öğe unsuru (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|
|.XML|Özellik bölümleri ve özellik sayfaları ve metin kutusu ve liste kutusu denetimleri gibi IDE kullanıcı arabirimi öğelerini bildirilip XML öğelerini içerir.<br /><br /> .Xml dosyaları doğrudan IDE'yi destekler, Msbuild'i değil. Ancak IDE özelliklerinin değerleri yapı özelliklerine ve öğelerine atanır.<br /><br /> Çoğu .xml dosyası bir yerel ayara özgü alt dizinde bulunur. Örneğin, ABD İngilizce bölgesinin dosyaları $(VCTargetsPath) \1033 içinde olan\\.|

## <a name="user-targets-and-properties"></a>Kullanıcı hedefleri ve özellikleri

MSBuild komut satırında en etkili bir şekilde kullanmak için hangi özelliklerin ve hedeflerin kullanışlı ve uygun olduğunu öğrenmenize yardımcı olur. Çoğu özellikleri ve hedefler Visual C++ yapı sistemini uygulamaya yardımcı olur ve sonuç olarak kullanıcıyla ilgili değildir. Bu bölümde, bazı faydalı kullanıcı-özellikler ve hedefler açıklanmaktadır.

### <a name="platformtoolset-property"></a>PlatformToolset özelliği

`PlatformToolset` Özelliği, yapıda kullanılan Visual C++ Araç Takımı'nı hangi uygulamada belirler. Varsayılan olarak, geçerli araç kümesi kullanılır. Bu özelliği ayarlandığında, özelliğin değerini belirli bir platform için bir proje oluşturmak için gereken özellik ve hedef dosyalarını içeren bir dizinin yolunu oluşturmak için hazır bilgi dizeleri ile birleştirilir. Bu platform araç kümesi sürümünü kullanarak oluşturmak için platform araç takımını yüklenmesi gerekir.

Örneğin, `PlatformToolset` özelliğini `v140` uygulamanızı oluşturmak için Visual C++ 2015 araçları ve kitaplıklarını kullanmak için:

`msbuild myProject.vcxproj /p:PlatformToolset=v140`

### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture özelliği

`PreferredToolArchitecture` Özelliği, yapıda 32-bit veya 64 bit derleyici ve araçların kullanılıp kullanılmayacağını belirler. Bu özellik, çıkış platformu mimarisi veya yapılandırmasını etkilemez. Varsayılan olarak MSBuild x86 kullanır. Bu özellik ayarlanmamışsa araçları ve derleyici sürümü.

Örneğin, `PreferredToolArchitecture` özelliğini `x64` uygulamanızı oluşturmak üzere 64 bit derleyici ve Araçları'nı kullanmak için:

`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`

### <a name="useenv-property"></a>UseEnv özelliği

Varsayılan olarak, geçerli proje için platforma özgü ayarlar PATH, INCLUDE, LIB, LIBPATH, yapılandırma ve PLATFORM ortam değişkenlerini geçersiz kılar. Ayarlama `UseEnv` özelliğini **true** ortam değişkenlerinin geçersiz kılınmadığını güvence altına almak için.

`msbuild myProject.vcxproj /p:UseEnv=true`

### <a name="targets"></a>Hedefler

Hedefler Visual C++ Destek dosyalarında yüzlerce vardır. Ancak, çoğu kullanıcının yok sayabileceği sistem odaklı hedefleri ' dir. Çoğu Sistem hedefleri, bir alt çizgi (_) öneki veya "" Hesapla", Hazırla ile", "Önce", "Ön" veya "Post" "Sonra" başlayan bir ada sahip.

Aşağıdaki tabloda, kullanıcıya yönelik bazı yararlı hedefler listeler.

|Hedef|Açıklama|
|------------|-----------------|
|BscMake|Yürütür Microsoft gözatma bilgisi bakım Yardımcısı aracı bscmake.exe'yi.|
|Derleme|Projeyi oluşturur.<br /><br /> Bu proje için varsayılan hedeftir.|
|ClCompile|Visual C++ Derleyici aracı yürütür cl.exe.|
|Temizleme|Yapı dosyalarını siler geçici ve Ara.|
|lib|Microsoft 32-Bit Kitaplık Yöneticisi Aracı yürütür lib.exe.|
|Bağlantı|Visual C++ bağlayıcı aracı yürütür link.exe.|
|ManifestResourceCompile|Bir bildirimden kaynakların listesini ayıklar ve ardından Microsoft Windows Kaynak Derleyicisi aracı yürütür rc.exe.|
|MIDL|Yürütür Microsoft arabirim tanımı dili (MIDL) derleyici aracı midl.exe'yi.|
|Yeniden oluşturma|Temizler ve ardından, projeyi oluşturur.|
|ResourceCompile|Yürütür Microsoft Windows Kaynak Derleyicisi aracı RC.exe'yi.|
|XdcMake|Yürütür XML belgelendirme aracı xdcmake.exe'yi.|
|XSD|XML şema tanımı aracı yürütür XSD.exe'nin. *Aşağıdaki nota bakın.*|

> [!NOTE]
> Visual Studio 2017'de C++ proje desteği **xsd** dosyaları kullanım dışı bırakılmıştır. Kullanmaya devam edebilirsiniz **Microsoft.VisualC.CppCodeProvider** ekleyerek **CppCodeProvider.dll** GAC için el ile.

## <a name="see-also"></a>Ayrıca Bkz.

[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
