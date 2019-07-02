---
title: CMakeSettings.json şema başvurusu
ms.date: 05/16/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: cc9b9a788f17e9257bed628024e3f65dfc89fb23
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67516374"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json şema başvurusu

**Cmakesettings.json** dosya Visual Studio'nun belirli bir platform için bir proje oluşturmak için CMake ile nasıl etkileşim kuracağını belirten bilgileri içerir. Dosya, ortam değişkenleri ya da cmake.exe ortam için bağımsız değişkenler gibi bilgileri depolar. Doğrudan düzenlemeniz veya kullanın **CMake ayarları Düzenleyicisi** (2019 ve daha sonra Visual Studio). Bkz: [özelleştirme CMake derleme ayarları Visual Studio'da](customize-cmake-settings.md) Düzenleyicisi hakkında daha fazla bilgi.

## <a name="environments"></a>Ortamlar

`environments` Dizi listesini içeren `items` türü `object` derleyici araç takımı "ortam" tanımlayın Bir ortam değişkenleri kümesi uygulamak için kullanılabilir bir `configuration`. Her öğe `environments` dizi oluşur:

- `namespace`: ortam değişkenlerini biçiminde bir yapılandırma başvurulabilir, böylece adları `namespace.variable`. Varsayılan ortam nesne adında `env` ve sistem ortam değişkenlerini de dahil olmak üzere belirli doldurulur `%USERPROFILE%`.
- `environment`: Bu değişken grubu benzersiz olarak tanımlar. Grubun daha sonra devralınmasını sağlar bir `inheritEnvironments` girişi.
- `groupPriority`: Önceliği bu değişkenlerin değerlendirilme sırasındaki belirten bir tamsayı. İlk olarak daha yüksek sayıya sahip öğeler değerlendirilir.
- `inheritEnvironments`: Bu grup tarafından devralınan ortamlar kümesi belirten değerleri dizisi. Bu özellik varsayılan ortamları devralır ve çalıştığında CMake.exe için geçirilen özel ortam değişkenleri oluşturmanıza olanak sağlar.

   ```json
   "inheritEnvironments": [ "msvc_x64_x64" ]
   ```

   Yukarıdaki örnekte çalışan aynıdır **VS 2017 için geliştirici komut istemi** veya **VS 2019 için geliştirici komut istemi** ile **-arch = amd64-host_arch amd64 =** bağımsız değişkenler. Önceden tanımlanmış bu ortamları veya herhangi bir özel ortama kullanılabilir:
 
  - linux_arm: ARM Linux'u uzaktan hedefleyin.
  - linux_x64: Hedef x64 Linux uzaktan.
  - linux_x86: Hedef x86 Linux uzaktan.
  - msvc_arm: MSVC derleyicisi ile ARM Windows hedef.
  - msvc_arm_x64: 64 bit MSVC derleyicisi ile ARM Windows hedef.
  - msvc_arm64: MSVC derleyicisi ile ARM64 Windows hedef.
  - msvc_arm64_x64: 64 bit MSVC derleyicisi ile ARM64 Windows hedef.
  - msvc_x64: MSVC derleyicisi ile hedef x64 Windows.
  - msvc_x64_x64: Hedef x64 Windows 64 bit MSVC derleyicisi ile.
  - msvc_x86: MSVC derleyicisi ile hedef x86 Windows.
  - msvc_x86_x64: Hedef x86 Windows 64 bit MSVC derleyicisi ile.

## <a name="configurations"></a>Yapılandırmalar

`configurations` Aynı klasördeki CMakeLists.txt dosyasına uygulanan CMake yapılandırmaları temsil eden nesneler dizisi oluşur. Bu nesneler, birden çok derleme yapılandırmalarını tanımlamak ve bunları IDE'de arasında kolayca geçiş için kullanabilirsiniz. 

A `configuration` şu özelliklere sahiptir:
- `name`: yapılandırma adları.
- `description`: menülerde görünür bu yapılandırma açıklaması.
- `generator`: Bu yapılandırma için kullanılacak CMake Oluşturucu belirtir. Aşağıdakilerden biri olabilir:
  
  **Yalnızca Visual Studio 2019:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 ve sonraki sürümleri:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 2015 14 ARM
  - UNIX derleme görevleri dosyası
  - Ninja

Ninja, esneklik ve işlevi yerine hızlı derleme hızı için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projelerini Ninja kullanarak doğru şekilde derlenmesi olabilir. Bu meydana gelirse, bunun yerine Visual Studio projesi oluşturmak için CMake bildirebilirsiniz.

Visual Studio 2017'de Visual Studio Oluşturucu belirtmek için açık `CMakeSettings.json` seçerek ana menüden **CMake | CMake ayarlarını değiştir**. "Ninja" silin ve "V" yazın. Bu, istediğiniz Oluşturucu seçmenize olanak sağlayan IntelliSense etkinleştirir.

Visual Studio oluşturucu içinde Visual Studio 2019 belirtmek için CMakeLists.txt dosyasına sağ **Çözüm Gezgini** ve **CMake proje ayarlarını** > **Göster Gelişmiş ayarlar** > **CMake Oluşturucu**.

Etkin yapılandırma bir Visual Studio oluşturucuyu belirttiğinde, varsayılan olarak MSBuild.exe ile çağrılan `-m -v:minimal` bağımsız değişkenler. Derleme içinde özelleştirmek için `CMakeSettings.json` , belirtebileceğiniz ek dosya [MSBuild komut satırı bağımsız değişkenleri](../build/reference/msbuild-visual-cpp-overview.md) yapı sistemi geçirilecek `buildCommandArgs` özelliği:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `configurationType`: Seçili Oluşturucu için derleme türü yapılandırmasını belirler. Aşağıdakilerden biri olabilir:
 
  - Hata ayıklama
  - Sürüm
  - MinSizeRel
  - RelWithDebInfo
 
- `inheritEnvironments`: Bu yapılandırmanın bağımlı olduğu bir veya daha fazla derleyici ortamları belirtir. Herhangi bir özel ortama veya önceden tanımlanmış ortamlar biri olabilir.
- `buildRoot`: cmake'in seçili Oluşturucu için derleme betikleri dizini belirtir.  Eşlendiği **-DCMAKE_BINARY_DIR** geçin ve CMake önbelleği oluşturulacağı belirtir. Klasör mevcut değilse oluşturulur. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `installRoot`: cmake'in seçili Oluşturucu için yükleme hedefleri dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `cmakeCommandArgs`: önbelleği oluşturması için çağrıldığında Cmake'e geçirilen ek komut satırı seçenekleri belirtir.
- `cmakeToolchain`: araç zinciri dosyasını belirtir. Bu Cmake'e geçirilen kullanma - DCMAKE_TOOLCHAIN_FILE. "
- `buildCommandArgs`: yerel derleme anahtarları--build--Cmake'e geçirilen belirtir. Örneğin, Ninja oluşturucusunu kullanırken - v geçirme komut satırları çıkış Ninja zorlar. Bkz: [Ninja komut satırı bağımsız değişkenleri](#ninja) Ninja komutlar hakkında daha fazla bilgi için.
- `ctestCommandArgs`: ek komut satırı seçenekleri, testler çalıştırıldığında Ctest'e geçirilen belirtir. "
- `codeAnalysisRuleset`: Kod Analizi çalıştırırken kullanılacak ruleset belirtir. Bu, bir tam yol veya Visual Studio tarafından yüklenmiş bir ruleset dosyasının dosya adı olabilir.
- `intelliSenseMode`: IntelliSense bilgilerinin hesaplanmasında kullanılan mod belirtir ". Aşağıdakilerden biri olabilir:
 
  - windows-msvc-x86
  - windows-msvc-x64
  - Windows msvc arm
  - Windows msvc arm64
  - Android clang x86
  - Android clang x64
  - Android-clang-arm
  - Android clang arm64
  - iOS clang x86
  - iOS clang x64
  - iOS-clang-arm
  - iOS clang arm64
  - Windows clang x86
  - windows-clang-x64
  - Windows-clang-arm
  - windows-clang-arm64
  - Linux gcc x86
  - Linux gcc x64
  - Linux-gcc-arm"

- `cacheRoot`: bir CMake önbelleği yolunu belirtir. Bu dizin mevcut bir CMakeCache.txt dosyasını içermesi gerekir.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux projeleri için ek ayarlar. 

- `remoteMachineName`: Cmake'i, derlemeleri ve hata ayıklayıcı barındıran uzak Linux makinesinin adını belirtir. Yeni Linux makineleri eklemek için Bağlantı Yöneticisi'ni kullanın. Desteklenen makrolar `${defaultRemoteMachineName}`.
- `remoteCopySourcesOutputVerbosity`: işlem uzak makineye kopyalanıyor kaynak ayrıntı düzeyini belirtir. "Yalnızca"Normal","Ayrıntılı"veya"Tanılama". olabilir
- `remoteCopySourcesConcurrentCopies`: kaynakları uzak makineye (yalnızca sftp) eşitleme sırasında kullanılan eş zamanlı kopyaların sayısını belirtir.
- `remoteCopySourcesMethod`: dosyalar uzak makineye kopyalamak için yöntemini belirtir. "Rsync" veya "sftp" olabilir.
- `remoteCMakeListsRoot`: uzak makinede CMake projesini içeren dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteBuildRoot`: cmake'in seçili Oluşturucu için derleme betikleri uzak bir makinede dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, `${env.VARIABLE}`.
- `remoteInstallRoot`: uzak makinede cmake'in seçili Oluşturucu için yükleme hedefleri dizini belirtir. Desteklenen makrolar `${workspaceRoot}`, `${workspaceHash}`, `${projectFile}`, `${projectDir}`, `${thisFile}`, `${thisFileDir}`, `${name}`, `${generator}`, ve `${env.VARIABLE}` burada `VARIABLE` sahip bir ortam değişkeni Sistem, kullanıcı veya oturum düzeyinde tanımlanmış.
- `remoteCopySources`: A `boolean` Visual Studio kaynak dosyaları uzak makineye kopyalayın olup olmadığını belirtir. Varsayılan değer True'dur. Dosya eşitlemesini kendiniz yönetiyorsanız false olarak ayarlayın.
- `remoteCopyBuildOutput`: A `boolean` yapı çıkışlarını Uzak sistemden kopyalanıp kopyalanmayacağını belirtir.
- `rsyncCommandArgs`: rsync metoduna geçirilen ek komut satırı seçeneklerini belirtir.
- `remoteCopySourcesExclusionList`: A `array` kaynak dosyaları kopyalarken hariç tutulacak yolları listesi belirten: bir yolu, dosya/dizin veya kopya köküne göreli bir yol adı olabilir. Joker karakterler \\ \" * \\ \" ve \\ \"?\\ \" glob deseni eşleştirmek için kullanılabilir.
- `cmakeExecutable`: dosya adı ve uzantısıyla birlikte CMake programı yürütülebilir tam yolunu belirtir.
- `remotePreGenerateCommand`: CMakeLists.txt dosyasını ayrıştırmak için Cmake'i çalıştırmadan önce çalıştırılacak komutu belirtir.
- `remotePrebuildCommand`: derlemeden önce uzak makinede çalıştırılacak komutu belirtir.
- `remotePostbuildCommand`: derlemeden sonra uzak makinede çalıştırılacak komutu belirtir.
- `variables`: bir ad-değer çifti olarak geçirilen CMake değişkenlerinin içeren **-D** *_adı_=_değer_* CMake için. CMake projesi derleme Yönergeleriniz eklenmesi hiçbir değişkene doğrudan CMake önbellek dosyası belirtirseniz, bunları burada yerine eklemeniz önerilir. Aşağıdaki örnek 14.14.26428 için ad-değer çiftlerini belirtin gösterilmiştir MSVC araç takımı:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe",
      "type": "FILEPATH"
    }
  ]
```

Tanımlamıyor gerçekleştiriyorsanız `"type"`, "Dize" türü varsayılan olarak varsayılacak.

## <a name="environment-variables"></a>Ortam değişkenleri

`CMakeSettings.json` Ayrıca alıcı ortam değişkenlerini yukarıdaki özelliklerinden birini destekler. Kullanılacak söz dizimi `${env.FOO}` % ortam değişkeni % FOO genişletin.

Ayrıca yerleşik makroları içinde bu dosyayı erişebilirsiniz:

- `${workspaceRoot}` – Çalışma klasörün tam yolunu sağlar.
- `${workspaceHash}` – Çalışma alanı konumu; karması Geçerli çalışma alanına (örneğin, klasör yollarında kullanılacak) için benzersiz bir tanımlayıcı oluşturmak için yararlı
- `${projectFile}` – kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}` – kök CMakeLists.txt dosyasını klasörün tam yolu
- `${thisFile}` – tam yolunu `CMakeSettings.json` dosyası
- `${name}` – yapılandırmasının adı
- `${generator}` – Bu yapılandırmasında kullanılan CMake oluşturucu adı


### <a name="custom-environment-variables"></a>Özel ortam değişkenleri

İçinde `CMakeSettings.json`, genel olarak özel ortam değişkenleri tanımlayabilir veya başına yapılandırmada **ortamları** özelliği. Aşağıdaki örnek bir genel değişken tanımlar **BuildDir**, x86 hata ayıklama ve x64 hata ayıklama yapılandırmaları devralınır. Her yapılandırma değişkeni değeri belirtmek için kullanır. **buildRoot** bu yapılandırma için özellik. Her yapılandırma nasıl kullandığını da unutmayın **inheritEnvironments** özelliği yalnızca o yapılandırmanız için geçerli bir değişken belirtin.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

Sonraki örnekte, kendi değerini x86 hata ayıklama yapılandırmasını tanımlar **BuildDir** özelliği. Bu değer, genel tarafından ayarlanan değer geçersiz kılar **BuildDir** özelliği böylece **BuildRoot** değerlendiren `D:\custom-builddir\x86-Debug`.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir"
          // This environment does not specify a namespace, hence by default "env" will be assumed.
          // "namespace" : "name" would require that this variable be referenced with "${name.BuildDir}".
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="ninja"></a> Ninja komut satırı bağımsız değişkenleri

'Default' hedef hedefleri belirtilmemişse oluşturur.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --version  | Yazdırma ninja sürümü ("1.7.1")|
|   -C DİZİNİ   | başka bir şey yapmadan önce DIR değiştirme|
|   -f dosyası  | Giriş derleme dosyası (default=build.ninja) belirtin|
|   -j N     | N işleri paralel olarak çalıştırma (varsayılan = 14, CPU kullanılabilir türetilmiş)|
|   -k N     | N başarısız işleri kadar kullanmaya devam edin (varsayılan = 1)|
|   N -m     | Yük ortalama N büyükse, yeni iş başlatma|
|   -n       | kuru çalıştırın (ancak bunlar başarılı gibi davranmasına komutlarını çalıştırma)|
|   -v       | yapı sırasında tüm komut satırları göster|
|   -d modu  | (-d listesini modları kullanın) hata ayıklamayı etkinleştir|
|   -t aracı  | bir subtool (kullanın -t listesini alt araçları) çalıştırın. üst düzey seçenekleri sonlandırır; Daha fazla bayrakları araç geçirilir|
|   -w BAYRAĞI  | Uyarılar (kullanın -w listesini uyarılar) ayarlama|




