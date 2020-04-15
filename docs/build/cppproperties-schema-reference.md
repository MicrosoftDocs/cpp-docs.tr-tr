---
title: CppProperties.json başvuru
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
# <a name="cpppropertiesjson-reference"></a>CppProperties.json başvuru

CMake kullanmayan Klasör'ü aç projeleri, IntelliSense için proje yapılandırma ayarlarını *CppProperties.json* dosyasında depolayabilir. (CMake projeleri [cmakesettings.json](customize-cmake-settings.md) dosyası kullanın.) Yapılandırma ad/değer çiftlerinden oluşur ve #include yolları, derleyici anahtarları ve diğer parametreleri tanımlar. Açık Klasör projesinde yapılandırma ların nasıl eklenöğretilenhakkında daha fazla bilgi için [C++ için Açık Klasör projelerine](open-folder-projects-cpp.md) bakın. Aşağıdaki bölümlerde çeşitli ayarlar özetlenir. Şema tam bir açıklama için, *CppProperties_schema.json*gidin , tam yol *CppProperties.json* açık olduğunda kod düzenleyicisinin üst kısmında verilir.

## <a name="configuration-properties"></a>Yapılandırma özellikleri

Yapılandırma aşağıdaki özelliklerden herhangi biri olabilir:

|||
|-|-|
|`inheritEnvironments`| Bu yapılandırmaiçin hangi ortamların geçerli olduğunu belirtir.|
|`name`|The configuration name that will appear in the C++ configuration dropdown|
|`includePath`|İçyol'da belirtilmesi gereken klasörlerin virgülle ayrılmış bir listesi (çoğu derleyici için /I'ye eşlemler)|
|`defines`|Tanımlanması gereken makroların listesi (çoğu derleyici için /D eşler)|
|`compilerSwitches`|IntelliSense davranışını etkileyebilen bir veya daha fazla ek anahtar|
|`forcedInclude`|Her derleme birimine otomatik olarak eklenecek üstbilgi (MSVC için /FI haritaları veya -clang için dahil)|
|`undefines`|Tanımlanmamış makroların listesi (MSVC için /U haritaları)|
|`intelliSenseMode`|Kullanılacak IntelliSense motoru. MSVC, gcc veya Clang için önceden tanımlanmış mimariye özgü türevlerinden birini belirtebilirsiniz.|
|`environments`|Komut isteminde ortam değişkenleri gibi görünen ve ${env ile erişilen kullanıcı\< tanımlı değişken kümeleri. DEĞIŞKEN>} makro.|

### <a name="intellisensemode-values"></a>intelliSenseMode değerleri

Kod düzenleyicisi, yazmaya başladığınızda kullanılabilir seçenekleri gösterir:

![Klasör Üle'yi Aç](media/open-folder-intellisense-mode.png "Klasör Üle'yi Aç")

Desteklenen değerler şunlardır:

- windows-msvc-x86
- windows-msvc-x64
- windows-msvc-kol
- windows-msvc-kol64
- android-clang-x86
- android-clang-x64
- android-clang-kol
- android-clang-arm64
- ios-clang-x86
- ios-clang-x64
- ios-clang-kol
- ios-clang-arm64
- windows-clang-x86
- windows-clang-x64
- windows-clang-kol
- windows-clang-kol64
- linux-gcc-x86
- linux-gcc-x64
- linux-gcc-kol

Not: Değerler `msvc-x86` `msvc-x64` ve yalnızca eski nedenlerle desteklenir. Bunun `windows-msvc-*` yerine varyantları kullanın.

## <a name="pre-defined-environments"></a>Önceden Tanımlanmış Ortamlar

Visual Studio, Microsoft C++ için aşağıdaki önceden tanımlanmış ortamları sağlar ve bu ortamlar ilgili Geliştirici Komut Komut Ustem'ine eş sağlar. Bu ortamlardan birini devraldığınızda, bu makro sözdizimi ile genel `env` özelliği kullanarak ortam değişkenlerinden herhangi\< birine başvurabilirsiniz: ${env. DEĞIŞKEN>}.

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

Linux iş yükü yüklendiğinde, Linux ve WSL'yi uzaktan hedeflemek için aşağıdaki ortamlar kullanılabilir:

|Değişken Adı|Açıklama|
|-----------|-----------------|
|linux_x86|Hedef x86 Linux uzaktan|
|linux_x64|Hedef x64 Linux uzaktan|
|linux_arm|Hedef ARM Linux uzaktan|

## <a name="user-defined-environments"></a><a name="user_defined_environments"></a>Kullanıcı tanımlı ortamlar

Özelliği isteğe bağlı `environments` *olarak, CppProperties.json'daki* değişken kümelerini genel olarak veya yapılandırma başına tanımlamak için kullanabilirsiniz. Bu değişkenler bir Açık Klasör projesi bağlamında ortam değişkenleri gibi davranılır ve ${env ile erişilebilir.\< VARIABLE>} *tasks.vs.json* ve *launch.vs.json* sözdizimi burada tanımlandıktan sonra. Ancak, Visual Studio'nun dahili olarak kullandığı herhangi bir komut isteminde gerçek ortam değişkenleri olarak ayarlanmaları gerekmez.

**Visual Studio 2019 sürüm 16.4 ve sonrası:** *CppProperties.json'da* tanımlanan yapılandırmaya özgü değişkenler, ayarlanmaya `inheritEnvironments`gerek kalmadan hata ayıklama hedefleri ve görevleri tarafından otomatik olarak alınır. Hata ayıklama hedefleri *CppProperties.json'da*belirttiğiniz ortamla otomatik olarak başlatılır.

**Visual Studio 2019 sürüm 16.3 ve önceki:** Bir ortamı tükettiğinızda, ortam aynı yapılandırmanın `inheritsEnvironments` bir parçası olarak tanımlanmış olsa bile, bu ortamı özellikte belirtmeniz gerekir; `environment` özellik çevrenin adını belirtir. Aşağıdaki örnek, MSYS2 yüklemesinde GCC için IntelliSense'i etkinleştirmek için örnek bir yapılandırmayı gösterir. Yapılandırmanın ortamı nasıl tanımladığını `mingw_64` ve devraldığına `includePath` ve özelliğin `INCLUDE` değişkene nasıl erişebileceğine dikkat edin.

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

Bir yapılandırma içinde bir **ortam** özelliği tanımladığınızda, aynı ada ait tüm genel değişkenleri geçersiz kılar.

## <a name="built-in-macros"></a>Yerleşik makrolar

*CppProperties.json*içinde aşağıdaki yerleşik makrolara erişebilirsiniz:

|||
|-|-|
|`${workspaceRoot}`| Çalışma alanı klasörüne tam yol|
|`${projectRoot}`| *CppProperties.json'Un* yerleştirildiği klasöre tam yol|
|`${env.vsInstallDir}`| Visual Studio'nun çalışan örneğinin yüklü olduğu klasöre tam yol|

### <a name="example"></a>Örnek

Projenizde bir include klasörü varsa ve Windows SDK'dan *windows.h* ve diğer ortak üstbilgileri de içeriyorsa, *CppProperties.json* yapılandırma dosyanızı aşağıdakilerle güncelleştirmek isteyebilirsiniz:

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
> `%WindowsSdkDir%`ve `%VCToolsInstallDir%` genel ortam değişkenleri olarak ayarlanmadığından, bu değişkenleri tanımlayan bir Geliştirici Komut Komut Ustem'den devenv.exe'yi başlattığınızdan emin olun. (Windows Başlat Menüsüne "geliştirici" yazın.)

## <a name="troubleshoot-intellisense-errors"></a>Sorun Giderme IntelliSense hataları

Beklediğiniz IntelliSense'i görmüyorsanız, **Tools** > **Options** > **Text Editor** > **C/C++** > **Advanced'e** giderek sorun giderebilirsiniz ve **Günlük'ü** **doğru**şekilde etkinleştir'i ayarlayabilirsiniz. Başlangıç olarak, **Günlük Düzeyi'ni** 5'e, **Günlük Filtrelerini** 8'e ayarlamayı deneyin.

![Tanılama günlüğüne kaydetme](media/diagnostic-logging.png)

Çıktı **Çıkış Penceresine** borulanır ve **Çıktıyı Göster'i**seçtiğinizde görünür: Visual C++ Log . Çıktı, diğer şeylerin yanı sıra, IntelliSense'in kullanmaya çalıştığı yolları içerir. Yollar *CppProperties.json'dakiyle*eşleşmiyorsa, klasörü kapatmayı ve önbelleğe alınmış tarama verilerini içeren *.vs* alt klasörünü silmeyi deneyin.

Eksik yolların neden olduğu IntelliSense hatalarını gidermek için, **hata listesini** açın ve çıktısını "Yalnızca IntelliSense" ve Hata Kodu E1696'ya filtreleyin "kaynak dosyasını açamazsınız...".
