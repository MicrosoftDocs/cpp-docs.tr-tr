---
title: Visual c++'ta açık klasör projelere | Microsoft Docs
ms.custom: ''
ms.date: 06/01/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5c7473cd7d6f2f07d81011eca0826b8066513d23
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50069262"
---
# <a name="open-folder-projects-in-visual-c"></a>Visual c++ açık klasörü projeler

Visual Studio 2017 ve sonraki sürümlerinde, "Klasör Aç" özelliği, bir kaynak dosya klasörü açın ve hemen desteğiyle tarama, yeniden düzenleme, hata ayıklama, IntelliSense, kod yazmaya başlayın ve benzeri sağlar. Hiçbir .sln veya .vcxproj dosyaları yüklenir; Gerekirse, özel görevleri oluşturmak ve parametreler aracılığıyla basit .json dosyaları başlatma olarak belirtebilirsiniz.
Klasör Aç tarafından desteklenen, Visual C++ artık yalnızca dosyaların kaybolmasını koleksiyonları ancak aynı zamanda neredeyse tüm yapı sistemi, CMake Ninja, QMake (Qt projelerde), gyp, SCons, Gradle, Buck, oluşturma ve gibi destekler.

Klasör Aç'ı kullanmak için ana menüden seçin *dosya | Açık | Klasör* veya basın *Ctrl + Shift + Alt + O*. Çözüm Gezgini, hemen klasördeki tüm dosyaları görüntüler. Düzenlemeye başlamak için herhangi bir dosyaya tıklayabilirsiniz. Arka planda, dosyaları, IntelliSense, gezinti ve yeniden düzenleme özellikleri etkinleştirmek için Visual Studio başlatılır. Düzenleme, oluşturma, taşıma veya dosyaları silmek gibi Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir.

## <a name="cmake-projects"></a>CMake projeleri

CMake, Visual C++, C++ Masaüstü iş yükünde bir bileşeni CMake araçları Visual Studio IDE'de tümleşiktir. Daha fazla bilgi için [Visual C++ için CMake araçlarını](cmake-tools-for-visual-cpp.md).

## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake Qt Framework'ü hedefleyen projeleri

Qt projeleri derlemek için Qt hedeflemek için Visual C++ için CMake araçlarını kullanabilir veya kullanabileceğiniz [Qt Visual Studio Uzantısı](https://download.qt.io/development_releases/vsaddin/) Visual Studio 2015 veya Visual Studio 2017 için.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, simgeler, SCons, Buck, vb.

Visual c++'ta herhangi bir derleme sistemini kullanın ve yine de Visual C++ IDE ve hata ayıklayıcı avantajları keyfini çıkarın. Projenizin kök klasörü açın, Visual C++ kaynak dosyaları için IntelliSense ve gözatma dizini oluşturmak için buluşsal yöntemler kullanır. CppProperties.json dosyasını düzenleyerek, kodunuzun yapısı hakkında ipuçları sağlayabilir. Benzer şekilde, launch.vs.json dosyasını düzenleyerek derleme programınızı yapılandırabilirsiniz.

## <a name="configuring-open-folder-projects"></a>Klasör Aç projeleri yapılandırma

Klasör Aç projesinde üç JSON dosyalarıyla özelleştirebilirsiniz:
|||
|-|-|
|CppProperties.json|Gözatma için özel yapılandırma bilgilerini belirtin. Bu dosya, kök proje klasörünüzdeki gerekirse oluşturun.|
|Launch.vs.JSON|Komut satırı bağımsız değişkenlerini belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **hata ayıklama ve başlatma ayarları**.|
|Tasks.vs.JSON|Özel derleme komutları ve derleyici anahtarları belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **yapılandırma görevleri**.|

### <a name="configure-intellisense-with-cpppropertiesjson"></a>IntelliSense ile CppProperties.json yapılandırın

IntelliSense ve göz atma davranışlarına kısmen bağlıdır tanımlayan etkin yapı yapılandırmasını # yolları, derleyici anahtarlarını ve diğer parametreler include. Varsayılan olarak, Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar. Bazı projeler için tam kod kavrama için IntelliSense ve gözatma özellikler için sırayla özel yapılandırma oluşturmak gerekebilir. Yeni bir yapılandırmasını tanımlamak için kök klasörde CppProperties.json adlı bir dosya oluşturun. Aşağıda bir örnek verilmiştir:

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
Bir yapılandırma aşağıdaki özelliklerinden herhangi birini içerebilir:

|||
|-|-|
|`name`|C++ yapılandırma açılan menüde görüntülenen yapılandırma adı|
|`includePath`|ekleme yoluna (/I eşlenir derleyicilerin çoğu için) belirtilmelidir klasörlerin listesi|
|`defines`|olmalıdır makroları listesinde tanımlanan (/D eşlenir derleyicilerin çoğu için)|
|`compilerSwitches`|IntelliSense davranışını etkileyen bir veya daha fazla ek anahtarlar|
|`forcedInclude`|Her derleme biriminde otomatik olarak eklenecek üstbilgi (/FI için MSVC için eşler veya - clang için dahil)|
|`undefines`|Tanımsız (maps) MSVC için /U için olmasını makroları listesi|
|`intelliSenseMode`|kullanılacak IntelliSense altyapısı. Mimari belirli çeşitleri MSVC, gcc veya Clang belirtebilirsiniz:<br/><br/>-msvc-x86 (varsayılan)<br/>-msvc x64<br/>-msvc-arm<br/>-windows clang x86<br/>-windows clang x64<br/>-windows-clang-arm<br/>Linux-x64<br/>Linux-x86<br/>-Linux-arm<br/>-gccarm|

#### <a name="environment-variables"></a>Ortam değişkenleri

CppProperties.json destekler sistem ortam değişkeni genişletmesini yollarını ve diğer özellik değerlerini içerir. Söz dizimi `${env.FOODIR}` bir ortam değişkeni genişletin `%FOODIR%`. Aşağıdaki sistem tanımlı değişkenleri de desteklenir:

|Değişken adı|Açıklama|
|-----------|-----------------|
|vsdev|Varsayılan Visual Studio ortamı|
|msvc_x86|X86 kullanarak x86 için derleme araçları|
|msvc_arm|X86 kullanarak ARM için derleme araçları|
|msvc_arm64|ARM64 için x86 kullanarak derleme araçları|
|msvc_x86_x64|AMD64 için x86 kullanarak derleme araçları|
|msvc_x64_x64|AMD64 için 64-bit araçlarını kullanarak derleme|
|msvc_arm_x64|64-bit araçlarını kullanarak ARM için derleme|
|msvc_arm64_x64|ARM64 için 64-bit araçlarını kullanarak derleme|

Linux iş yükü yüklendiğinde, Linux ve WSL uzaktan hedeflemek için aşağıdaki ortamlarda kullanılabilir:

|Değişken adı|Açıklama|
|-----------|-----------------|
|linux_x86|Hedef x86 Linux uzaktan|
|linux_x64|Hedef x64 Linux uzaktan|
|linux_arm|ARM Linux'u uzaktan hedefleyin|

Özel ortam değişkenleri CppProperties.json ya da genel tanımlayabileceğiniz veya başına yapılandırma. Aşağıdaki örnek nasıl varsayılan ve özel ortam değişkenleri bildirilen kaldırılabilir ve gösterir. Genel **ortamları** özellik adında bir değişken bildirir **INCLUDE** tarafından herhangi bir yapılandırma kullanılabilir:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        // Inherit the MSVC 32-bit environment and toolchain.
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "inheritEnvironments": [
        // Inherit the MSVC 64-bit environment and toolchain.
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined above.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```
Ayrıca tanımlayabilirsiniz bir **ortamları** özelliği içinde bir yapılandırması olan yalnızca bu yapılandırma için geçerlidir ve herhangi bir genel değişkenler aynı ada sahip geçersiz kılar. Aşağıdaki örnekte, x64 yapılandırmasını tanımlayan bir yerel **INCLUDE** genel değerini geçersiz kılar değişkeni:

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\\src\\includes"
    }
  ],

  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86",
      "includePath": [
        // Use the include path defined in the global environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x86"
    },
    {
      "environments": [
        {
          // Append 64-bit specific include path to env.INCLUDE.
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\\src\\includes64"
        }
      ],

      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64",
      "includePath": [
        // Use the include path defined in the local environments property.
        "${env.INCLUDE}"
      ],
      "defines": [ "WIN32", "_DEBUG", "UNICODE", "_UNICODE" ],
      "intelliSenseMode": "msvc-x64"
    }
  ]
}
```

Tüm özel ve varsayılan ortam değişkenlerini de launch.vs.json ve tasks.vs.json ile kullanılabilir.

#### <a name="macros"></a>Makrolar

CppProperties.json içinde aşağıdaki yerleşik makroları erişebilirsiniz:
|||
|-|-|
|`${workspaceRoot}`| Çalışma alanı klasörün tam yolu|
|`${projectRoot}`| CppProperties.json yerleştirildiği klasörün tam yolu|
|`${vsInstallDir}`| çalışan örneği VS 2017'in yüklendiği klasörün tam yolu|

Örneğin, projenize bir dahil etme klasörü ve ayrıca windows.h ve diğer ortak üst bilgileri Windows SDK içerir, bu yapılandırma dosyası içerir, CppProperties.json güncelleştirmek isteyebilirsiniz:

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

> [!Note]
> `%WindowsSdkDir%` ve `%VCToolsInstallDir%` genel ortam değişkenleri bu nedenle "Geliştirici komut isteminden bu değişkenleri tanımlayan VS 2017 için" devenv.exe başlattığınız emin olun olarak ayarlı değil.

IntelliSense sorunlarını gidermek için yol, hataları nedeni eksik eklemeyi açın **hata listesi** hata kodu E1696 "kaynak dosyayı açamıyor..." ve "Yalnızca IntelliSense" çıktısını Filtrele.

CppProperties.json içinde herhangi bir sayıda yapılandırmaları oluşturabilirsiniz. Her yapılandırma açılan listede görünür:

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

### <a name="define-tasks-with-tasksvsjson"></a>Tasks.vs.json ile görevleri tanımlama

Derleme betikleri veya geçerli çalışma alanınızda doğrudan IDE'de görev olarak çalıştırarak olması dosyalarda dış diğer işlemleri otomatik hale getirebilirsiniz. Bir dosya veya klasörü sağ tıklatıp seçerek yeni bir görev yapılandırabileceğiniz **yapılandırma görevleri**.

![Klasör Aç yapılandırma görevleri](media/open-folder-config-tasks.png)

Oluşturur (veya açılır) `tasks.vs.json` Visual Studio kök proje klasörünüzdeki oluşturan .vs klasöründeki dosya. Bu dosyayı herhangi bir rastgele görev tanımlayın ve ondan çağırma **Çözüm Gezgini** bağlam menüsü. Aşağıdaki örnek, tek bir görevi tanımlayan bir tasks.vs.json dosyası gösterir. `taskName` bağlam menüsünde görünen adını tanımlar. `appliesTo` hangi dosyaların komutu gerçekleştirilebilir tanımlar. `command` Özelliği başvurur (Windows cmd.exe'de) konsol yolunu tanımlar COMSPEC ortam değişkenine. CppProperties.json veya CMakeSettings.json bildirilen ortam değişkenlerini de başvurabilirsiniz. `args` Özellik çağrılacak komut satırını belirtir. `${file}` Makrosu alır seçili dosyasında **Çözüm Gezgini**. Aşağıdaki örnek şu anda seçili .cpp dosyasının dosya adını görüntüler.

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
Tasks.vs.JSON kaydettikten sonra herhangi bir .cpp dosyası klasörüne sağ tıklayın, seçin **Yankı filename** bağlam menüsü ve dosya adı çıktı penceresinde görüntülenen bakın.

#### <a name="appliesto"></a>AppliesTo

Görevler için herhangi bir dosya veya klasör adını belirterek oluşturabileceğiniz `appliesTo` alan, örneğin `"appliesTo" : "hello.cpp"`. Aşağıdaki dosya maskesi değerleri kullanılabilir:
|||
|-|-|
|`"*"`| Görev tüm dosyaları ve klasörleri çalışma alanında kullanılabilir|
|`"*/"`| Görev, çalışma alanındaki tüm klasörler için kullanılabilir|
|`"*.cpp"`| Görev tüm dosyaları uzantı .cpp çalışma alanında kullanılabilir|
|`"/*.cpp"`| Görev, tüm çalışma alanı kökünde uzantısı .cpp dosyaları için kullanılabilir|
|`"src/*/"`| Görev "src =" klasörün tüm alt klasörleri için kullanılabilir|
|`"makefile"`| Görev, çalışma alanındaki tüm derleme görevleri dosyaları için kullanılabilir|
|`"/makefile"`| görev yalnızca çalışma alanının kök makefile kullanılabilir|

#### <a name="output"></a>çıktı

Kullanım `output` tuşuna bastığınızda, başlatılacak çalıştırılabilir dosyayı belirtmek için özellik **F5**. Örneğin:

```json
      "output": "${workspaceRoot}\\bin\\hellomake.exe"
```

#### <a name="macros-for-tasksvsjson"></a>Tasks.vs.json makroları

|||
|-|-|
|`${env.<VARIABLE>}`| herhangi bir ortam değişkeni (örneğin, ${env. belirtir YOL}, ${env.COMSPEC} vb.) için geliştirici komut istemi ayarlayın. Daha fazla bilgi için [Visual Studio için geliştirici komut istemi](/dotnet/framework/tools/developer-command-prompt-for-vs).|
|`${workspaceRoot}`| çalışma klasörü (örneğin, "C:\sources\hello") tam yolu|
|`${file}`| Dosya veya bu görevi (örneğin, "C:\sources\hello\src\hello.cpp") karşı çalıştırmak için Seçili klasörün tam yolu|
|`${relativeFile}`| göreli yol dosya veya klasör (örneğin, "src\hello.cpp")|
|`${fileBasename}`| yol ve uzantı (örneğin, "hello") olmadan dosyanın adı|
|`${fileDirname}`| Dosya adı (örneğin, "C:\sources\hello\src") dışında dosyasının tam yolu|
|`${fileExtname}`| Seçili dosya (örneğin, ".cpp") uzantısı|

#### <a name="custom-macros"></a>Özel makroları

Özel bir makro içinde tasks.vs.json tanımlamak için önce görev blokları ad: değer çifti ekleyin. Aşağıdaki örnek adlı bir makro tanımlar `outDir` içinde kullanılan `args` özelliği:

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

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Launch.vs.json ile hata ayıklama parametreleri Yapılandır

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu varolan açar `launch.vs.json` dosyası veya yoksa, seçtiğiniz program hakkında bilgileri önceden doldurulmuş yeni bir dosya oluşturur.

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

Bu dosyayı kaydettiğinizde, yeni yapılandırmayı hata ayıklama hedefi açılır menüde görünür ve hata ayıklayıcıyı başlatmak için bunu seçebilirsiniz. Dilediğiniz sayıda yürütülebilir dosyalar için birçok hata ayıklama yapılandırması oluşturabilirsiniz. Basarsanız **F5** hata ayıklayıcısı artık, başlar ve zaten ayarladığınız bir kesme noktasına ulaşırsınız. Tüm alıştığınız hata ayıklayıcı pencereleri ve işlevleri artık kullanılabilir.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Geliştirme Araçları ve IDE](ide-and-tools-for-visual-cpp-development.md)

