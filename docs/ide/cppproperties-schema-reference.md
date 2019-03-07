---
title: CppProperties.json schema reference
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.openlocfilehash: fd655de3313dd95eb3fcefaeba21e703d32e860a
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/07/2019
ms.locfileid: "57566925"
---
# <a name="cpppropertiesjson-schema-reference"></a>CppProperties.json schema reference

CMake kullanmayan klasör Proje Aç projesi yapılandırma ayarlarında depolayabileceğiniz bir `CppProperties.json` dosya. (Kullanım CMake projeleri bir [CMakeSettings.json](customize-cmake-settings.md) dosyası.) Visual Studio IDE kullanan `CppProperties.json` için IntelliSense ve kod gezintisi. Bir yapılandırmayı, ad/değer çiftlerinden oluşur ve tanımlar # yolları, derleyici anahtarlarını ve diğer parametreler include. 


## <a name="default-configurations"></a>Varsayılan yapılandırmaları

Visual Studio, önceden tanımlanmış yapılandırmaları sunar x86 ve x64 hata ayıklama ve yayın. Varsayılan olarak, projenizin bir x86 hata ayıklama yapılandırması vardır `CppProperties.json`. Yeni bir yapılandırma eklemek için sağ tıklayın `CppProperties.json` dosyası **Çözüm Gezgini** ve **Yapılandırması Ekle**:

![Açık klasör ekleme Yapılandırması](media/open-folder-add-config.png "Klasör Aç, yeni yapılandırma Ekle")

Varsayılan yapılandırmaları burada gösterilir:

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x86"
      ],
      "name": "x86-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x86"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    },
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Release",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "NDEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```
Yazmaya başladığınızda, izin verilen bir dizi taşıyan özellikler için Kod Düzenleyicisi mevcut seçenekler gösterilmektedir:

![Açık klasör IntelliSense](media/open-folder-intellisense-mode.png "açık klasör IntelliSense")



## <a name="configuration-properties"></a>Yapılandırma özellikleri

Bir yapılandırma aşağıdaki özelliklerinden herhangi birini içerebilir:

|||
|-|-|
|`name`|C++ yapılandırma açılan menüde görüntülenen yapılandırma adı|
|`includePath`|ekleme yoluna (/I eşlenir derleyicilerin çoğu için) belirtilmelidir klasörlerin listesi|
|`defines`|olmalıdır makroları listesinde tanımlanan (/D eşlenir derleyicilerin çoğu için)|
|`compilerSwitches`|IntelliSense davranışını etkileyen bir veya daha fazla ek anahtarlar|
|`forcedInclude`|Her derleme biriminde otomatik olarak eklenecek üstbilgi (/FI için MSVC için eşler veya - clang için dahil)|
|`undefines`|Tanımsız (maps) MSVC için /U için olmasını makroları listesi|
|`intelliSenseMode`|kullanılacak IntelliSense altyapısı. Mimari belirli çeşitleri MSVC, gcc veya Clang belirtebilirsiniz:<br/><br/>-msvc-x86 (varsayılan)<br/>- msvc-x64<br/>- msvc-arm<br/>- windows-clang-x86<br/>- windows-clang-x64<br/>- windows-clang-arm<br/>- Linux-x64<br/>- Linux-x86<br/>-Linux-arm<br/>-gccarm|

## <a name="custom-configurations"></a>Özel yapılandırmalar


Herhangi bir varsayılan configuations özelleştirebileceğiniz `CppProperties.json`, ya da yeni yapılandırmalar oluşturun. Her yapılandırma açılan listede görünür:

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

## <a name="system-environment-variables"></a>Sistem ortam değişkenleri 

 `CppProperties.json` destekleyen sistem ortam değişkeni genişletmesini yollarını ve diğer özellik değerlerini içerir. Söz dizimi `${env.FOODIR}` bir ortam değişkeni genişletin `%FOODIR%`. Aşağıdaki sistem tanımlı değişkenleri de desteklenir:

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

## <a name="custom-environment-variables"></a>Özel ortam değişkenleri

Tanımlayabileceğiniz özel ortam değişkenleri `CppProperties.json` ya da genel olarak veya başına yapılandırma. Aşağıdaki örnek nasıl varsayılan ve özel ortam değişkenleri bildirilen kaldırılabilir ve gösterir. Genel **ortamları** özellik adında bir değişken bildirir **INCLUDE** tarafından herhangi bir yapılandırma kullanılabilir:

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
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
## <a name="per-configuration-environment-variables"></a>Yapılandırma ortam değişkenleri

Ayrıca tanımlayabilirsiniz bir **ortamları** özelliği içinde bir yapılandırması olan yalnızca bu yapılandırma için geçerlidir ve herhangi bir genel değişkenler aynı ada sahip geçersiz kılar. Aşağıdaki örnekte, x64 yapılandırmasını tanımlayan bir yerel **INCLUDE** genel değerini geçersiz kılar değişkeni:

```json
{
  "environments": [
    {
      "INCLUDE": "${workspaceRoot}\src\includes"
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
          "INCLUDE": "${env.INCLUDE};${workspaceRoot}\src\includes64"
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

Tüm özel ve varsayılan ortam değişkenlerini de kullanılabilir `tasks.vs.json` ve `launch.vs.json`.

#### <a name="build-in-macros"></a>Derleme içinde makroları

İçinde aşağıdaki yerleşik makroları erişiminiz `CppProperties.json`:

|||
|-|-|
|`${workspaceRoot}`| Çalışma alanı klasörün tam yolu|
|`${projectRoot}`| klasörün tam yolu burada `CppProperties.json` yerleştirilir|
|`${vsInstallDir}`| çalışan örneği VS 2017'in yüklendiği klasörün tam yolu|

Örneğin, projeniz bir dahil etme klasörü varsa, ve ayrıca windows.h ve diğer ortak üst bilgileri Windows SDK içerir güncelleştirmek isteyebilirsiniz, `CppProperties.json` bu yapılandırma dosyası içerir:

```json
{
  "configurations": [
    {
      "name": "Windows",
      "includePath": [
        // local include folder
        "${workspaceRoot}\include",
        // Windows SDK and CRT headers
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\ucrt",
        "${env.NETFXSDKDir}\include\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\um",
        "${env.WindowsSdkDir}\include\${env.WindowsSDKVersion}\shared",
        "${env.VCToolsInstallDir}\include"
      ]
    }
  ]
}
```

> [!Note]
> `%WindowsSdkDir%` ve `%VCToolsInstallDir%` genel ortam değişkenleri bu nedenle "Geliştirici komut isteminden bu değişkenleri tanımlayan VS 2017 için" devenv.exe başlattığınız emin olun olarak ayarlı değil.

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense sorunlarını giderme

IntelliSense sorunlarını gidermek için yol, hataları nedeni eksik eklemeyi açın **hata listesi** hata kodu E1696 "kaynak dosyayı açamıyor..." ve "Yalnızca IntelliSense" çıktısını Filtrele.



