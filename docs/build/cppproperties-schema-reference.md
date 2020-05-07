---
title: CppProperties. JSON başvurusu
ms.date: 08/09/2019
helpviewer_keywords:
- CppProperties.json file [C++]
ms.openlocfilehash: be6db52e1e62244e9f44db8ac86238242ab50ca0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328727"
---
# <a name="cpppropertiesjson-reference"></a>CppProperties. JSON başvurusu

CMake kullanmayan açık klasör projeleri, bir *Cppproperties. JSON* dosyasında IntelliSense için proje yapılandırma ayarlarını saklayabilir. (CMake projeleri bir [Cmakesettings. JSON](customize-cmake-settings.md) dosyası kullanır.) Bir yapılandırma ad/değer çiftlerinden oluşur ve #include yollar, derleyici anahtarları ve diğer parametreleri tanımlar. Açık bir klasör projesinde yapılandırmaların nasıl ekleneceği hakkında daha fazla bilgi için bkz. [C++ Için açık klasör projeleri](open-folder-projects-cpp.md) . Aşağıdaki bölümler çeşitli ayarları özetler. Şemanın tam bir açıklaması için, *Cppproperties. JSON* açık olduğunda, kod düzenleyicisinin en üstünde tam yol verilen *CppProperties_schema. JSON*' a gidin.

## <a name="configuration-properties"></a>Yapılandırma özellikleri

Bir yapılandırma aşağıdaki özelliklerden herhangi birine sahip olabilir:

|||
|-|-|
|`inheritEnvironments`| Bu yapılandırma için hangi ortamların uygulanacağını belirtir.|
|`name`|C++ yapılandırma açılan menüsünde görünecek yapılandırma adı|
|`includePath`|İçerme yolunda belirtilmesi gereken klasörlerin virgülle ayrılmış listesi (Çoğu derleyiciler için/ı 'ye eşlenir)|
|`defines`|Tanımlanması gereken makroların listesi (Çoğu derleyiciler için/D ile eşlenir)|
|`compilerSwitches`|IntelliSense davranışını etkileyebilecek bir veya daha fazla ek anahtar|
|`forcedInclude`|Her derleme birimine otomatik olarak dahil edilecek üst bilgi (MSVC veya Clang için-include için/FI 'e eşlenir)|
|`undefines`|Tanımsız olacak makroların listesi (MSVC için/U ile eşlenir)|
|`intelliSenseMode`|Kullanılacak IntelliSense altyapısı. MSVC, GCC veya Clang için önceden tanımlanmış mimariye özgü çeşitlerden birini belirtebilirsiniz.|
|`environments`|Bir komut isteminde ortam değişkenleri gibi davranan ve $ {env ile erişilen değişkenlerin Kullanıcı tanımlı kümesi.\<>} makrosu DEĞIŞKENI.|

### <a name="intellisensemode-values"></a>ıntellisensemode değerleri

Kod Düzenleyicisi, şunu yaza başladığınızda kullanılabilir seçenekleri gösterir:

![Açık klasör IntelliSense](media/open-folder-intellisense-mode.png "Açık klasör IntelliSense")

Desteklenen değerler şunlardır:

- Windows-MSVC-x86
- Windows-MSVC-x64
- Windows-MSVC-ARM
- Windows-MSVC-arm64
- Android-Clang-x86
- Android-Clang-x64
- Android-Clang-ARM
- Android-Clang-arm64
- iOS-Clang-x86
- iOS-Clang-x64
- iOS-Clang-ARM
- iOS-Clang-arm64
- Windows-Clang-x86
- Windows-Clang-x64
- Windows-Clang-ARM
- Windows-Clang-arm64
- Linux-GCC-x86
- Linux-GCC-x64
- Linux-GCC-ARM

Note: değerler `msvc-x86` ve `msvc-x64` yalnızca eski nedenlerden dolayı desteklenir. Bunun yerine `windows-msvc-*` türevlerini kullanın.

## <a name="pre-defined-environments"></a>Önceden tanımlı ortamlar

Visual Studio, karşılık gelen Geliştirici Komut İstemi eşlenen Microsoft C++ için önceden tanımlanmış aşağıdaki ortamları sağlar. Bu ortamlarından birini dağıttığınızda, şu makro söz dizimine sahip genel özelliği `env` kullanarak ortam değişkenlerinden herhangi birine başvurabilirsiniz: $ {env.\<>} DEĞIŞKENI.

|Değişken Adı|Açıklama|
|-----------|-----------------|
|vsdev|Varsayılan Visual Studio ortamı|
|msvc_x86|X86 araçlarını kullanarak x86 için derleme|
|msvc_x64|64 bit araçları kullanarak AMD64 için derleme|
|msvc_arm|X86 araçlarını kullanarak ARM için derleme|
|msvc_arm64|X86 araçlarını kullanarak ARM64 için derleme|
|msvc_x86_x64|X86 araçlarını kullanarak AMD64 için derleme|
|msvc_arm_x64|64 bit araçları kullanarak ARM için derleme|
|msvc_arm64_x64|64 bit araçları kullanarak ARM64 için derleme|

Linux iş yükü yüklendiğinde, Linux ve WSL 'yi uzaktan hedeflemek için aşağıdaki ortamlar mevcuttur:

|Değişken Adı|Açıklama|
|-----------|-----------------|
|linux_x86|X86 Linux 'u uzaktan hedefleyin|
|linux_x64|X64 Linux 'u uzaktan hedefleyin|
|linux_arm|ARM Linux 'u uzaktan hedefleyin|

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a>Kullanıcı tanımlı ortamlar

İsteğe bağlı olarak, `environments` *cppproperties. JSON* içindeki değişken kümelerini tanımlamak için ya da genel olarak veya yapılandırma başına özelliğini kullanabilirsiniz. Bu değişkenler, açık bir klasör projesi bağlamında ortam değişkenleri gibi davranır ve $ {env. ile erişilebilir.\< *Tasks. vs. JSON* ve *Launch. vs. JSON* 'dan sonra, burada tanımlandıklarında değişken>} sözdizimi. Ancak, Visual Studio 'Nun dahili olarak kullandığı herhangi bir komut isteminde gerçek ortam değişkenleri olarak ayarlanmaları gerekmez.

**Visual Studio 2019 sürüm 16,4 ve üzeri:** *Cppproperties. JSON* içinde tanımlanan yapılandırmaya özgü değişkenler, hata ayıklama hedefleri ve görevleri tarafından ayarlanması `inheritEnvironments`gerekmeden otomatik olarak alınır. Hata ayıklama hedefleri, *Cppproperties. JSON*içinde belirttiğiniz ortam ile otomatik olarak başlatılır.

**Visual Studio 2019 sürüm 16,3 ve öncesi:** Bir ortamı tükettiğinizde, ortam aynı yapılandırmanın bir parçası olarak tanımlansa bile `inheritsEnvironments` özelliği özelliğinde belirtmeniz gerekir; `environment` özelliği, ortamın adını belirtir. Aşağıdaki örnekte, MSYS2 yüklemesinde GCC için IntelliSense 'i etkinleştirmek üzere örnek bir yapılandırma gösterilmektedir. Yapılandırmanın `mingw_64` ortamı nasıl tanımlayıp devraldığını ve `includePath` özelliğin `INCLUDE` değişkene nasıl erişebileceğini aklınızda bulabilirsiniz.

```json
"configurations": [
    {

      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath ,": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**",
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR};",
          "environment": "mingw_64"
        }
      ]
    }
  ]
```

Bir yapılandırma içinde bir **ortamlar** özelliği tanımladığınızda, aynı ada sahip tüm genel değişkenleri geçersiz kılar.

## <a name="built-in-macros"></a>Yerleşik makrolar

*Cppproperties. JSON*içinde aşağıdaki yerleşik makrolara erişebilirsiniz:

|||
|-|-|
|`${workspaceRoot}`| Çalışma alanı klasörünün tam yolu|
|`${projectRoot}`| *Cppproperties. JSON* ' ın yerleştirildiği klasörün tam yolu|
|`${env.vsInstallDir}`| Visual Studio 'nun çalışan örneğinin yüklü olduğu klasörün tam yolu|

### <a name="example"></a>Örnek

Projenizde bir içerme klasörü varsa ve ayrıca Windows SDK *Windows. h* ve diğer yaygın üstbilgileri Içeriyorsa, *cppproperties. JSON* yapılandırma dosyanızı aşağıdakiler dahil olmak üzere güncelleştirmek isteyebilirsiniz:

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
> `%WindowsSdkDir%`ve `%VCToolsInstallDir%` genel ortam değişkenleri olarak ayarlanmamış, bu nedenle devenv. exe ' yi bu değişkenleri tanımlayan bir geliştirici komut istemi başlattığınızdan emin olun. (Windows Başlat menüsünde "Geliştirici" yazın.)

## <a name="troubleshoot-intellisense-errors"></a>IntelliSense hatalarında sorun giderme

İstediğiniz IntelliSense 'i görmüyorsanız, **Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > **C/C++** > **Gelişmiş** ' e giderek ve **günlük kaydını** **true**olarak ayarlayarak sorun gidermeye devam edebilirsiniz. İle başlamak için **günlük kaydı düzeyini** 5 olarak ayarlamayı ve filtreleri 8 ' e **kaydetmeyi** deneyin.

![Tanılama günlüğüne kaydetme](media/diagnostic-logging.png)

Çıkış **Çıkış penceresi** gönderilir ve **çıktıyı göster: Visual C++ log**' u seçtiğinizde görünür. Çıktı, diğer şeyler yanında, IntelliSense 'in kullanmaya çalıştığı gerçek ekleme yollarının listesini içerir. Yollar *Cppproperties. JSON*içindeki olanlarla eşleşmiyorsa, klasörü kapatmayı ve önbelleğe alınmış tarama verilerini içeren *. vs* alt klasörünü silmeyi deneyin.

Eksik içerme yollarının neden olduğu IntelliSense hatalarını gidermek için **hata listesi** açın ve çıktısını "yalnızca IntelliSense" olarak filtreleyin ve hata kodu E1696 "kaynak dosyası açılamıyor...".
