---
title: "MSBuild (Visual C++) genel bakış | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MSBuild overview
ms.assetid: dd258f6f-ab51-48d9-b274-f7ba911d05ca
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f250443e0e5da2cf399282f19a5fde58c4c4b089
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="msbuild-visual-c-overview"></a>MSBuild (Visual C++) Genel Bakış  
  
MSBuild standart sistemi için Visual C++ projeleri derleme ' dir. Visual Studio tümleşik geliştirme ortamı (IDE) projede derlerken msbuild.exe aracı, bir XML tabanlı proje dosyası ve isteğe bağlı ayarlar dosyalarını kullanır. Msbuild.exe ve bir proje dosyası komut satırında kullanabilmenize karşın, böylece daha kolay ayarlarını yapılandırmak ve bir projeyi derleme IDE bir kullanıcı arabirimi sağlar. Bu genel bakışta, Visual C++ MSBuild sistem nasıl kullandığını açıklar.  
  
## <a name="prerequisites"></a>Önkoşullar  
  
MSBuild hakkında aşağıdaki belgeleri okuyun.  
  
- [MSBuild](/visualstudio/msbuild/msbuild)  
 MSBuild kavramları genel bakış.  
  
- [MSBuild Başvurusu](/visualstudio/msbuild/msbuild-reference)  
 MSBuild sistem hakkında başvuru bilgileri.  
  
- [Proje dosyası şema başvurusu](/visualstudio/msbuild/msbuild-project-file-schema-reference)  
 MSBuild XML şema öğeleri, öznitelikleri ve üst ve alt öğelerini birlikte listeler. Özellikle dikkat edin [ItemGroup](/visualstudio/msbuild/itemgroup-element-msbuild), [PropertyGroup](/visualstudio/msbuild/propertygroup-element-msbuild), [hedef](/visualstudio/msbuild/target-element-msbuild), ve [görev](/visualstudio/msbuild/task-element-msbuild) öğeleri.  
  
- [Komut Satırı Başvurusu](/visualstudio/msbuild/msbuild-command-line-reference)  
 Komut satırı bağımsız değişkenleri ve msbuild.exe ile kullanabileceğiniz seçenekleri açıklar.  
  
- [Görev başvurusu](/visualstudio/msbuild/msbuild-task-reference)  
 MSBuild görevleri açıklar. Visual C++'ye özgü bu görevleri özellikle dikkat edin: [BscMake görevi](/visualstudio/msbuild/bscmake-task), [CL görevi](/visualstudio/msbuild/cl-task), [CPPClean görevi](/visualstudio/msbuild/cppclean-task), [LIB görevi](/visualstudio/msbuild/lib-task), [Bağlantı görev](/visualstudio/msbuild/link-task), [MIDL görevi](/visualstudio/msbuild/midl-task), [MT görevi](/visualstudio/msbuild/mt-task), [RC görevi](/visualstudio/msbuild/rc-task), [SetEnv görevi](/visualstudio/msbuild/setenv-task), [ VCMessage görevi](/visualstudio/msbuild/vcmessage-task), [XDCMake görevi](/visualstudio/msbuild/xdcmake-task), [XSD görevi](/visualstudio/msbuild/xsd-task).  
  
## <a name="msbuild-on-the-command-line"></a>MSBuild komut satırında  
  
Aşağıdaki deyiminden [MSBuild komut satırı başvurusu](/visualstudio/msbuild/msbuild-command-line-reference) msbuild.exe aracı örtük veya açık aldığını gösterir *project_file* bağımsız değişkeni (Visual C++ projeleri için .vcxproj dosyası) ve sıfır veya daha fazla komut satırı *seçenekleri* bağımsız değişkenler.  
  
> **MSBuild.exe** [ *project_file* ] [ *seçenekleri* ]  
  
Kullanım **/target** (veya **/t**) ve **/property** (veya **/p**) belirli özellikler ve olan hedefleri geçersiz kılmak için komut satırı seçenekleri Proje dosyasında belirtilen.  
  
Proje dosyası önemli bir işlevinin belirtmektir bir *hedef*, projenizin ve girişlere ve çıkışlara bu işlemi gerçekleştirmek için gerekli uygulanan belirli bir işlem olduğu. Proje dosyası varsayılan hedef içerebilir, bir veya daha fazla hedefleri belirtebilirsiniz.  
  
Bir veya daha fazla bir dizi her hedef oluşur *görevleri*. Her görev, bir yürütülebilir komut içeren bir .NET Framework sınıf tarafından temsil edilir. Örneğin, [CL görevi](/visualstudio/msbuild/cl-task) içeren [cl.exe](../build/reference/compiling-a-c-cpp-program.md) komutu.  
  
A *görev parametresi* sınıfı görev bir özelliktir ve genellikle bir komut satırı seçeneği yürütülebilir komutu temsil eder. Örneğin, `FavorSizeOrSpeed` parametresinin `CL` görev karşılık gelen **/Os** ve **/Ot** derleyici seçenekleri.  
  
Ek görevi parametreleri MSBuild altyapısını destekler. Örneğin, `Sources` görev parametresi, bir dizi diğer görevler tarafından kullanılabilecek görevi belirtir. MSBuild görevleri hakkında daha fazla bilgi için bkz: [görev başvurusu](/visualstudio/msbuild/msbuild-task-reference).  
  
Çoğu görevleri girişleri ve çıkışları dosya adları, yolları ve dize, sayısal ya da Boole parametreleri gibi gerektirir. Örneğin, ortak bir giriş derlemek için .cpp kaynak dosyasının adıdır. Önemli bir giriş parametresi yapı yapılandırması ve platformu, belirtir, örneğin, bir dizedir "hata ayıklama\|Win32". Girişleri ve çıkışları bir veya daha fazla kullanıcı tanımlı XML tarafından belirtilen `Item` içindeki öğe bir `ItemGroup` öğesi.  
  
Kullanıcı tanımlı bir proje dosyası da belirtebilirsiniz *özellikleri* ve `ItemDefinitionGroup` *öğeleri*. Yapı değişkenleri olarak kullanılan ad/değer çiftleri, özellikleri ve öğeleri oluşturur. Çiftinin adı bileşeni tanımlayan bir *makrosu*, ve değerini bileşenini bildirir *makrosu değeri*. Bir özellik makrosu $ kullanılarak erişilir (*adı*) gösterimi ve bir öğe makrosu erişildiğinde kullanarak %(*adı*) gösterimi.  
  
Bir proje dosyasındaki diğer XML öğeleri makroları, test ve ardından Koşullu herhangi makrosu değerini ayarlayabilir veya yapı yürütülmesi denetim. Makro adları ve değişmez değer dizeleri yapıları gibi bir yol ve dosya adı oluşturmak için art arda eklenebilir. Komut satırında **/property** seçeneği ayarlar ya da bir proje özelliğini geçersiz kılar. Komut satırında öğeleri başvurulamaz.  
  
MSBuild sistem koşullu önce veya sonra başka bir hedef hedef yürütebilir. Ayrıca, sistem olup hedef tüketir dosyaları, yayar dosyalardan daha yeni olan bağlı olarak bir hedef oluşturabilirsiniz.  
  
## <a name="msbuild-in-the-ide"></a>IDE içinde MSBuild  
  
IDE içinde proje özelliklerini ayarlama ve projeyi kaydedin, Visual C++ proje ayarlarını proje dosyasına yazar. Proje dosyası projenize benzersiz ayarları içerir, ancak projenizi derleme için gerekli tüm ayarları içermiyor. Proje dosyasını içeren `Import` ek ağı içeren öğelerini *destek dosyaları.* Destek dosyalarını kalan özellikleri, hedefler ve projeyi oluşturmak için gereken ayarları içerir.  
  
Çoğu hedefleri ve Destek dosyalarını özelliklerinde güvenmeyin build sistem uygulamak için mevcut. Aşağıdaki bölümde, bazı yararlı hedefleri ve MSBuild komut satırında belirttiğiniz özellikler açıklanmaktadır. Daha fazla hedefleri ve özellikleri bulmak için destek dosya dizinleri dosyalarında keşfedin.  
  
### <a name="support-file-directories"></a>Dosya dizinleri desteği  
  
Varsayılan olarak, birincil Visual C++ Destek dosyalarının aşağıdaki dizinlerindeki bulunur. MSBuild altındaki dizinleri Visual Studio 2015 ve önceki sürümleri tarafından kullanılırken Microsoft Visual Studio altındaki dizinleri Visual Studio 2017 ve sonraki sürümler tarafından kullanılır.  
  
|Dizin|Açıklama|  
|---------------|-----------------|  
|*Sürücü*: \Program Files *(x86)*\Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ <br /><br />*Sürücü*: \Program Files *(x86)*\MSBuild\Microsoft.Cpp (x86) \v4.0\\*sürümü*\ |Birincil hedef dosyaları (.targets) içerir ve özellik dosyalarını (.props) hedefler tarafından kullanılır. Varsayılan olarak, bu dizin $(VCTargetsPath) makrosu başvurur.|  
|*Sürücü*: \Program Files *(x86)*\Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ Platformlar\\*platform*\ <br /><br />*Sürücü*: \Program Files *(x86)*\MSBuild\Microsoft.Cpp\v4.0\\*sürüm*\Platforms\\*platform*\ |Hedefleri ve kendi ana dizini özelliklerinde geçersiz kılma platforma özgü hedef ve özellik dosyalarını içerir. Bu dizin, bu dizinde hedefleri tarafından kullanılan görevleri tanımlayan bir DLL de içerir.<br /><br /> *Platform* yer tutucu ARM, Win32 ya da x64 temsil eden alt dizin.|  
|*Sürücü*: \Program Files *(x86)*\Microsoft Visual Studio\\*yıl*\\*edition*\Common7\IDE\VC\VCTargets\ Platformlar\\*platform*\PlatformToolsets\\*araç takımı*\ <br /><br />*Sürücü*: \Program Files *(x86)*\MSBuild\Microsoft.Cpp\v4.0\\*sürüm*\Platforms\\*platform*\ PlatformToolsets\\*araç takımı*\ <br /><br />*Sürücü*: \Program Files *(x86)*\MSBuild\Microsoft.Cpp\v4.0\Platforms\\*platform*\PlatformToolsets\\*araç takımı*\ |Belirtilen kullanarak Visual C++ uygulamaları oluşturmak yapı etkinleştirmek dizinleri içeren *araç takımı*.<br /><br /> *Yıl* ve *edition* yer tutucuları, Visual Studio 2017 ve sonraki sürümleri tarafından kullanılır. *Sürüm* tutucudur V110 Visual Studio 2012 için Visual Studio 2013 için V120 ya da Visual Studio 2015 için V140. *Platform* yer tutucu ARM, Win32 ya da x64 temsil eden alt dizin. *Araç takımı* yer tutucu araç takımı alt, örneğin, Visual Studio 2015 araç takımı, Visual Studio 2013 araç takımı veya v110_wp80 için kullanan Windows XP için yapı v120_xp kullanılarak Windows uygulamaları oluşturmaya yönelik v140 temsil eder Visual Studio 2012 araç setini kullanarak Windows Phone 8.0 uygulamalar oluşturun.<br /><br />Visual C++ 2008 veya Visual C++ 2010 uygulamaları oluşturmak yapı etkinleştirmek dizinleri içeren yolu içermeyen *sürüm*ve *platform* yer tutucusu temsil eder Itanium, Win32 ya da x64 alt dizin. *Araç takımı* yer tutucu v90 veya nı v100 araç takımı alt temsil eder.|  
  
### <a name="support-files"></a>Destek dosyaları  
  
Destek dosya dizinleri uzantılara sahip dosyaları içerir:  
  
|Uzantısı|Açıklama|  
|---------------|-----------------|  
|.targets|İçeren `Target` XML öğesi hedef tarafından yürütülen görevler belirten. Ayrıca içerebilir `PropertyGroup`, `ItemGroup`, `ItemDefinitionGroup`ve kullanıcı tanımlı `Item` dosyaları ve komut satırı seçenekleri görev parametrelerini atamak için kullanılan öğeleri.<br /><br /> Daha fazla bilgi için bkz: [hedef öğesi (MSBuild)](/visualstudio/msbuild/target-element-msbuild).|  
|.props|İçeren `Property Group` ve kullanıcı tanımlı `Property` derleme sırasında kullanılan dosya ve parametre ayarlarını belirtin XML öğeleri.<br /><br /> Ayrıca içerebilir `ItemDefinitionGroup` ve kullanıcı tanımlı `Item` ek ayarları belirtmek XML öğeleri. Bir öğe tanımı grubunda tanımlanan öğeleri özellikleri benzer, ancak komut satırından erişilemiyor. Visual C++ proje dosyalarını sık öğeleri özellikleri yerine ayarları temsil etmek için kullanır.<br /><br /> Daha fazla bilgi için bkz: [ItemGroup öğesi (MSBuild)](/visualstudio/msbuild/itemgroup-element-msbuild), [Itemdefinitiongroup öğesi (MSBuild)](/visualstudio/msbuild/itemdefinitiongroup-element-msbuild), ve [öğe unsuru (MSBuild)](/visualstudio/msbuild/item-element-msbuild).|  
|.XML|Özellik sayfaları ve özellik sayfaları ve metin kutusu ve liste kutusu denetimleri gibi IDE kullanıcı arabirimi öğeleri bildirilip XML öğeleri içerir.<br /><br /> .Xml dosyaları, IDE, değil MSBuild doğrudan destekler. Ancak, IDE özelliklerinin değerlerini, özellikler ve öğeler oluşturmak üzere atanır.<br /><br /> Çoğu .xml dosyaları yerel ayarlara özgü alt dizininde bulunur. Örneğin, İngilizce-ABD bölgesi için $(VCTargetsPath) \1033 dosyalarıdır\\.|  
  
## <a name="user-targets-and-properties"></a>Kullanıcı hedefleri ve özellikleri  
  
MSBuild komut satırında en verimli şekilde kullanmak için hangi özellikler ve hedefleri faydalı ve ilgili bilmeniz yardımcı olabilir. Çoğu özellik ve hedefleri Visual C++ derleme sistem uygulamaya yardımcı olur ve sonuç olarak kullanıcıyla ilgili değildir. Bu bölümde bazı faydalı kullanıcı odaklı özellikleri ve hedefler açıklanmaktadır.  

### <a name="platformtoolset-property"></a>PlatformToolset özelliği  
  
`PlatformToolset` Özelliği, hangi Visual C++ araç takımını derlemede kullanılan belirler. Varsayılan olarak, geçerli araç takımı kullanılır. Bu özellik ayarladığınızda, özelliğin değerini belirli bir platform için bir proje oluşturmak için gerekli özellik ve hedef dosyaları içeren bir dizinin yolunu oluşturmak için değişmez değer dizeleri ile birleştirilir. Bu platform araç takımı sürümünü kullanarak oluşturmak için platform araç takımı yüklenmesi gerekir.  
  
Örneğin, `PlatformToolset` özelliğine `v140` uygulamanızı oluşturmak için Visual C++ 2015 Araçlar ve kitaplıkların kullanmak için:  
  
`msbuild myProject.vcxproj /p:PlatformToolset=v140`  
  
### <a name="preferredtoolarchitecture-property"></a>PreferredToolArchitecture özelliği  
  
`PreferredToolArchitecture` Özelliği, 32 bit veya 64 bit derleyici ve araçları derlemede kullanılıp kullanılmayacağını belirler. Bu özellik çıkış platform mimarisi veya yapılandırma etkilemez. Varsayılan olarak, MSBuild x86 kullanır derleyici ve bu özellik ayarlanmamışsa araçları sürümü.  
  
Örneğin, `PreferredToolArchitecture` özelliğine `x64` uygulamanızı oluşturmak için Araçlar ve 64 bit derleyici kullanmak için:  
  
`msbuild myProject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### <a name="useenv-property"></a>UseEnv özelliği  
  
Varsayılan olarak, yol, Ekle, LIB, LIBPATH, yapılandırma ve PLATFORM ortam değişkenleri geçerli proje için platforma özgü ayarları geçersiz kılar. Ayarlama `UseEnv` özelliğine `true` ortam değişkenleri değildir kılınır güvence altına almak için.  
  
`msbuild myProject.vcxproj /p:UseEnv=true`  
  
### <a name="targets"></a>Hedefler  
  
Visual C++ Destek dosyalarını hedeflerini yüzlerce vardır. Ancak, çoğu kullanıcı yoksayabilirsiniz sistem odaklı hedefleri değildir. Çoğu Sistem hedefler bir çizgiyle (_) önüne ya da "" İşlem"PrepareFor ile", "Önce", "Öncesi" veya "Post" "Sonra" başlayan bir ada sahip.  
  
Aşağıdaki tabloda, çeşitli yararlı kullanıcı odaklı hedefleri listeler.  
  
|Hedef|Açıklama|  
|------------|-----------------|  
|BscMake|Microsoft Gözat bilgileri bakım yardımcı programı aracı yürütür bscmake.exe.|  
|Derleme|Projeyi oluşturur.<br /><br /> Bir proje için varsayılan hedef budur.|  
|ClCompile|Visual C++ Derleyici aracı yürütür cl.exe.|  
|Temizleme|Siler geçici ve Ara dosya oluşturun.|  
|LIB|Microsoft 32 Bit Kitaplık Yöneticisi aracını yürütür lib.exe.|  
|Bağlantı|Visual C++ bağlayıcı aracı yürütür link.exe.|  
|ManifestResourceCompile|Bildirimden alınan kaynakların bir listesini ayıklar ve Microsoft Windows Kaynak Derleyicisi aracı yürütür rc.exe.|  
|MIDL|Microsoft arabirimi tanım dili (MIDL) derleyici aracı yürütür midl.exe.|  
|Yeniden oluşturma|Temizler ve projenizi oluşturur.|  
|ResourceCompile|Microsoft Windows Kaynak Derleyicisi aracı yürütür rc.exe.|  
|XdcMake|XML belgeleri aracı yürütür xdcmake.exe.|  
|XSD|XML şema tanımı aracı yürütür XSD.exe'nin.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
