---
title: "Visual c++'ta klasörü projeleri Aç | Microsoft Docs"
ms.custom: 
ms.date: 08/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 72106bd363987d39fb11c9ec1a6d3fd0ceb5665d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="open-folder-projects-in-visual-c"></a>Visual C++'ta açık klasörü projeler
Visual Studio 2017, kaynak dosyaları klasörünü açın ve hemen kodlama gözatma, yeniden düzenleme, hata ayıklama, IntelliSense desteği ile başlayın ve benzeri olanak tanıyan "Klasörünü aç" özelliği sunmaktadır. Hiçbir .sln veya .vcxproj dosyalar yüklenir; Gerekirse, özel görevler oluşturun ve parametreleri basit .json dosyalar ile başlatma olarak belirtebilirsiniz. Klasör Aç gücü, yalnızca dosyaların kaybolmasını koleksiyonları, ancak de ayrıca neredeyse tüm yapı sistem, CMake Ninja, QMake (Qt projelerde), gyp, SCons, Gradle, Buck, marka ve çok çeşitli şimdi Visual C++ destekleyebilir. 

Klasör Aç kullanmak için ana menüden seçin *dosya | Açık | Klasör* veya basın *Ctrl + Shift + Alt + O*. Çözüm Gezgini, klasördeki tüm dosyaları hemen görüntüler. Düzenlemeye başlamak için herhangi bir dosya tıklatabilirsiniz. Arka planda, IntelliSense, gezinme ve düzenleme özellikleri etkinleştirmek için dosyaların dizinini Visual Studio başlatır. Düzenleme, oluşturma, taşıma veya dosyaları sil gibi Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir. 
  
## <a name="cmake-projects"></a>CMake projeleri
CMake Visual Studio IDE içinde Visual C++, C++ Masaüstü iş yükü bileşeninin CMake araçlar olarak tümleşiktir. Daha fazla bilgi için bkz: [CMake araçları Visual C++ için](cmake-tools-for-visual-cpp.md).
 
## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake Qt framework hedefleyen projeler
CMake araçlarını Visual C++ için hedef Qt Qt projeleri oluşturmak üzere kullanabileceğiniz veya Qt Visual Studio uzantısı kullanabilirsiniz. Not: İtibariyle Ağustos 2017 [Visual Studio 2017 Qt Visual Studio Uzantısı desteği](https://download.qt.io/development_releases/vsaddin/) beta sürümü olarak kullanılabilir.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, simgeler, SCons, Buck, vb.
Visual C++'da herhangi bir yapı sistemini kullanın ve hala avantajlarını Visual C++ IDE ve hata ayıklayıcı keyfini çıkarın. Projenizin kök klasörünü açın, Visual C++ kaynak dosyaları için IntelliSense ve Tarama için dizini için buluşsal yöntemler kullanır. CppProperties.json dosyasını düzenleyerek kodunuzu yapısı hakkında ipuçları sağlayabilir. Benzer şekilde, launch.vs.json dosyasını düzenleyerek yapı programınızı yapılandırabilirsiniz. 

## <a name="configuring-open-folder-projects"></a>Klasör Aç projeleri yapılandırma
Üç JSON dosyalar ile klasörü aç projesinde özelleştirebilirsiniz:
|||
|-|-|
|CppProperties.json|Tarama için özel yapılandırma bilgilerini belirtin. Bu dosya, gerekirse, kök proje klasörünüzde oluşturun.|
|Launch.vs.JSON|Komut satırı bağımsız değişkenleri belirtin. Üzerinden erişilen **Çözüm Gezgini** bağlam menüsü öğesini **hata ayıklama ve başlatma ayarları**.|
|Tasks.vs.JSON|Özel derleme komutları ve derleyici anahtarları belirtin. Üzerinden erişilen **Çözüm Gezgini** bağlam menüsü öğesini **yapılandırma görevleri**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>IntelliSense CppProperties.json ile yapılandırma
IntelliSense ve göz atma davranışlarına kısmen tanımlar etkin yapı yapılandırmasına bağlıdır # yolları, derleyici anahtarları ve diğer parametreleri include. Varsayılan olarak, Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar. Bazı projeler için IntelliSense ve göz atma özellikleri tam olarak kodunuzu kavrama sırayla özel yapılandırma oluşturmak gerekebilir. Yeni bir yapılandırma tanımlamak için kök klasöründe CppProperties.json adlı bir dosya oluşturun. Aşağıda bir örnek verilmiştir:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Bir yapılandırma aşağıdaki özelliklerden herhangi biri olabilir:

|||  
|-|-| 
|`name`|C++ yapılandırma açılır listede görünür yapılandırma adı|
|`includePath`|(çoğu derleyicileri için /I için maps) INCLUDE yolu belirtilmelidir klasörlerin listesi|
|`defines`|tanımlı (maps /d çoğu derleyicileri için) olmalıdır makroları listesi|
|`compilerSwitches`|IntelliSense davranışını etkilemek bir veya daha fazla ek anahtarlar|
|`forcedInclude`|Her derleme biriminde otomatik olarak eklenecek üstbilgi (eşler için /FI için MSVC veya - clang için dahil)|
|`undefines`|Tanımsız (maps) MSVC /U için olacak şekilde makroları listesi|
|`intelliSenseMode`|kullanılacak IntelliSense altyapısı. Mimari belirli çeşitleri MSVC, gcc veya Clang belirtebilirsiniz:
- MSVC x86 (varsayılan)
- MSVC x64
- MSVC arm
- Windows clang x86
- Windows clang x64
- Windows clang arm
- Linux x64
- Linux x86
- Linux arm
- gccarm

CppProperties.json destekler ortam değişkeni genişletmesini yolları ve diğer özellik değerlerini içerir. Sözdizimi `${env.FOODIR}` bir ortam değişkeni genişletmek için `%FOODIR%`.

Ayrıca bu dosya içinde aşağıdaki yerleşik makroları erişim sahibi:
|||
|-|-|
|`${workspaceRoot}`| çalışma klasörü tam yolu|
|`${projectRoot}`| CppProperties.json yerleştirildiği klasörün tam yolunu|
|`${vsInstallDir}`| VS 2017 çalışan örneği yüklendiği klasörün tam yolunu|

Örneğin, projenizin bir klasör ekle varsa ve aynı zamanda windows.h ve Windows SDK'sını diğer yaygın üstbilgileri içerir, bu yapılandırma dosyasını içerir, CppProperties.json güncelleştirmek isteyebilirsiniz:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\ucrt",
        "${env.NETFXSDKDir}\\include\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\um",
        "${env.WindowsSdkDir}include\\${env.WindowsSDKVersion}\\shared",
        "${env.VCToolsInstallDir}include"
      ]
    }
  ]
}
```

**Not:** `%WindowsSdkDir%` ve `%VCToolsInstallDir%` genel ortam değişkenleri böylece "Geliştirici komut isteminden bu değişkenleri tanımlayan VS 2017 için" devenv.exe başlattığınız emin olun olarak ayarlı değil.

IntelliSense sorunlarını giderme hataları nedeni eksik yolları eklenecek açmak **hata listesi** çıktısını "Yalnızca IntelliSense" için filtre ve hata kodu E1696 "kaynak dosyayı açamıyor...". 

Herhangi bir sayıda yapılandırmaları CppProperties.json oluşturabilirsiniz. Her yapılandırma açılır listede görüntülenir:

```json
{
  "configurations": [
    {
      "name": "Windows",
      ...
    },
    {
      "name": "with EXTERNAL_CODECS",
      ...
    }
  ]
}
```
### <a name="define-tasks-with-tasksvsjson"></a>Tasks.vs.json görevlerle tanımlayın
Yapı komut dosyaları veya diğer dış işlemleri doğrudan IDE'de görevler olarak çalıştırarak geçerli çalışma alanınızda sahip dosyalar üzerinde otomatik hale getirebilirsiniz. Bir dosya veya klasöre sağ tıklayıp seçerek yeni bir görev yapılandırabilirsiniz **yapılandırma görevleri**. 

![Klasör Aç yapılandırma görevleri](media/open-folder-config-tasks.png)

Bu oluşturur (veya açar) `tasks.vs.json` Visual Studio, kök proje klasöründe oluşturan .vs klasördeki dosya. Bu dosyada herhangi bir rastgele görev tanımlayın ve ondan çağırma **Çözüm Gezgini** bağlam menüsü. Aşağıdaki örnek, tek bir görev tanımlayan bir tasks.vs.json dosyası gösterir. `taskName`görünen adı bağlam menüsünde tanımlar. `appliesTo`komut gerçekleştirilebilir hangi dosyaların tanımlar. `command` Özelliği (cmd.exe Windows) konsol yolunu tanımlar COMSPEC ortam değişkeni anlamına gelmektedir. `args` Özelliği çağrılacak komut satırını belirtir. `${file}` Makrosu alır seçili dosyasında **Çözüm Gezgini**. Aşağıdaki örnek şu anda seçili .cpp dosyasının dosya adını görüntüler.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```
Tasks.vs.JSON kaydedildikten sonra klasördeki tüm .cpp dosyasına sağ tıklayın, seçin **Yankı filename** bağlam menüsünden ve dosya adı çıktı penceresinde görüntülenen bakın.

#### <a name="appliesto"></a>appliesTo
Görevler için herhangi bir dosya veya klasör adını belirterek oluşturabileceğiniz `appliesTo` alan, örneğin `"appliesTo" : "hello.cpp"`. Aşağıdaki dosya maskeleri değerleri olarak kullanılabilir:
|||
|-|-|
|`"*"`| Görev tüm dosyalara ve klasörlere çalışma alanında kullanılabilir|
|`"*/"`| Görev çalışma alanındaki tüm klasörler için kullanılabilir|
|`"*.cpp"`| Görev çalışma alanında uzantısı .cpp sahip tüm dosyaları için kullanılabilir|
|`"/*.cpp"`| Görev çalışma kök uzantısı .cpp sahip tüm dosyaları için kullanılabilir|
|`"src/*/"`| Görev için "src" klasörünün tüm alt klasörleri kullanılabilir|
|`"makefile"`| Görev çalışma alanındaki tüm derleme görevleri dosyaları için kullanılabilir|
|`"/makefile"`| görev yalnızca çalışma kök derleme görevleri dosyası kullanılabilir|

#### <a name="output"></a>çıktı
Kullanım `output` bastığınızda başlatacak yürütülebilir dosyayı belirtmek üzere özelliğini **F5**. Örneğin:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe" 
```

#### <a name="macros-for-tasksvsjson"></a>Tasks.vs.json makroları

|||
|-|-|
|`${env.<VARIABLE>}`| herhangi bir ortam değişkeni (örneğin, ${env. belirtir YOL}, ${env.COMSPEC} vb.) için geliştirici komut istemi ayarlayın. Daha fazla bilgi için bkz: [Visual Studio için geliştirici komut istemi](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| çalışma klasörü (örneğin, "C:\sources\hello") için tam yolu|
|`${file}`| Dosya veya klasör (örneğin, "C:\sources\hello\src\hello.cpp") karşı bu görevi çalıştırmak için seçili tam yolu|
|`${relativeFile}`| göreli yol dosya veya klasöre (örneğin, "src\hello.cpp")|
|`${fileBasename}`| yolu ya da (örneğin, "hello") uzantısı olmadan dosya adı|
|`${fileDirname}`| Dosya adı (örneğin, "C:\sources\hello\src") hariç olmak üzere dosyanın tam yolu|
|`${fileExtname}`| Seçilen dosya (örneğin, ".cpp") uzantısı|

#### <a name="custom-macros"></a>Özel makroları
Özel bir makro içinde tasks.vs.json tanımlamak için bir ad: değer çifti görev blokları önce ekleyin. Aşağıdaki örnek, adlandırılmış bir makro tanımlar `outDir` içinde tüketilen `args` özelliği:

```json
{
"version": "0.2.1",
  "outDir": "${workspaceRoot}\\bin",
  "tasks": [
    {
      "taskName": "List outputs",
      "*",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": [
        "dir ${outDir}"
      ]
    }
  ]
```

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Hata ayıklama parametrelerini launch.vs.json ile yapılandırma
Yürütülebilir dosya, programın komut satırı bağımsız değişkenleri özelleştirmek için sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu var olan açar `launch.vs.json` dosyası veya hiçbiri yoksa, seçtiğiniz programı hakkında bilgi ile önceden doldurulmaz yeni bir dosya oluşturur. 

Ek bağımsız değişkenlerini belirtmek için bunları eklemeniz yeterlidir `args` aşağıdaki örnekte gösterildiği gibi JSON dizisi:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Bu dosyayı kaydettiğinizde, yeni yapılandırmayı hedef hata ayıklama açılır listede görünür ve hata ayıklayıcısı başlayacak şekilde seçebilirsiniz. Yürütülebilir dosyalar herhangi bir sayı için istediğiniz kadar çok hata ayıklama yapılandırmaları oluşturabilirsiniz. Basarsanız **F5** hata ayıklayıcı şimdi başlar ve zaten ayarladığınız herhangi kesme noktası isabet. Tüm bilinen hata ayıklayıcı pencerelerinin ve işlevleri kullanıma hazırdır.

## <a name="see-also"></a>Ayrıca Bkz.
[Visual C++ Geliştirme Araçları ve IDE](ide-and-tools-for-visual-cpp-development.md)

