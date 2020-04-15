---
title: CMakeSettings.json şema referans
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: f9c864b66df86165090b7d6d6fc9c4fc51d65a5e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328888"
---
# <a name="cmakesettingsjson-schema-reference"></a>CMakeSettings.json şema referans

::: moniker range="vs-2015"

CMake projeleri Visual Studio 2017 ve sonrası desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

**CMakeSettings.json** dosyası Visual Studio IntelliSense için kullandığı bilgileri içerir ve belirli bir *yapılandırma* ve derleyici *ortamı*için cmake.exe geçer komut satırı bağımsız değişkenleri oluşturmak için . Yapılandırma, belirli bir platforma ve yapı türüne uygulanan özellikleri `x86-Debug` `Linux-Release`belirtir, örneğin. Her yapılandırma, msvc, GCC veya Clang gibi derleyici araç kümesi hakkında bilgi içeren bir ortam belirtir. CMake, *cMakeCache.txt* kökünü ve projeiçin diğer proje dosyalarını yeniden oluşturmak için komut satırı bağımsız değişkenlerini kullanır. Değerler *CMakeLists.txt* dosyalarında geçersiz kılınabilir.

IDE'ye yapılandırmalar ekleyebilir veya kaldırabilir ve ardından doğrudan JSON dosyasında dinleyebilir veya **CMake Ayarları düzenleyicisini** (Visual Studio 2019 ve sonrası) kullanabilirsiniz. Çeşitli proje dosyalarını oluşturmak için IDE'deki yapılandırmalar arasında kolayca geçiş yapabilirsiniz. Daha fazla bilgi için [Visual Studio'daki CMake yapı ayarlarını özelleştir'e](customize-cmake-settings.md) bakın.

## <a name="configurations"></a>Yapılandırmalar

Dizi, `configurations` bir CMake projesinin tüm yapılandırmalarını içerir. Önceden tanımlanmış yapılandırmalar hakkında daha fazla bilgi için [CMake önceden tanımlanmış yapılandırma başvurusuna](cmake-predefined-configuration-reference.md) bakın. Dosyaya önceden tanımlanmış veya özel yapılandırmalar herhangi bir sayıda ekleyebilirsiniz.

A `configuration` şu özelliklere sahiptir:

- `addressSanitizerEnabled`: `true` programı Address Sanitizer (Windows'da Deneysel) ile derlerse. Linux'ta, en iyi sonuçlar için -fno-omit-frame işaretçisi ve derleyici optimizasyon düzeyi -Os veya -Oo ile derle.
- `addressSanitizerRuntimeFlags`: ASAN_OPTIONS ortam değişkeni üzerinden AddressSanitizer'a geçirilen runtime bayrakları. Biçim: flag1=value:flag2=value2.
- `buildCommandArgs`: cmake'e geçtikten sonra cmake'ye geçen yerli yapı anahtarlarını belirtir -- inşa --. Örneğin, Ninja jeneratörü kullanırken -v'yi geçmek Ninja'yı komut satırlarına doğru iter. Ninja komutları hakkında daha fazla bilgi için [Ninja komut satırı bağımsız değişkenlerine](#ninja) bakın.
- `buildRoot`: CMake'in seçilen jeneratör için komut dosyası oluşturmasını oluşturduğu dizini belirtir.  -DCMAKE_BINARY_DIR **-DCMAKE_BINARY_DIR** için haritalar geçiş ve *CMakeCache.txt* oluşturulacak nerede belirtir. Klasör yoksa, oluşturulur. Desteklenen makrolar, `${workspaceRoot}` `${workspaceHash}`, `${projectFile}` `${projectDir}`, `${thisFile}` `${thisFileDir}`, `${name}` `${generator}`, `${env.VARIABLE}`, , .
- `cacheGenerationCommand`: önbelleği oluşturmak için örneğin *gencache.bat hata ayıklama* gibi bir komut satırı aracı ve bağımsız değişkenleri belirtir. Komut, kullanıcı açıkça yenilenme isteğinde bulunan yapılandırma için belirtilen ortamdaki kabuktan çalıştırılır veya cmakelists.txt veya CMakeSettings.json dosyası değiştirilir.
- `cacheRoot`: CMake önbelleğine giden yolu belirtir. Bu dizin varolan bir *CMakeCache.txt* dosyaiçermelidir.
- `clangTidyChecks`: virgülden ayrılmış, clang-tidy'ye geçirilecek uyarıların listesi; joker karakterlere izin verilir ve '-' öneki denetimleri kaldırır.
- `cmakeCommandArgs`: proje dosyalarını oluşturmak için çağrıldığınızda CMake'e geçirilen ek komut satırı seçeneklerini belirtir.
- `cmakeToolchain`: araç zinciri dosyasını belirtir. Bu CMake için -DCMAKE_TOOLCHAIN_FILE kullanılarak geçirilir."
- `codeAnalysisRuleset`: kod çözümlemesi çalıştırırken kullanılacak kural kümesini belirtir. Bu tam bir yol veya Visual Studio tarafından yüklenen bir kural kümesi dosyasının dosya adı olabilir.
- `configurationType`: seçili jeneratör için yapı türü yapılandırmasını belirtir. Bunlardan biri olabilir:

  - Hata ayıklama
  - Yayınla
  - MinSizeRel
  - RelWithDebInfo
  
- `ctestCommandArgs`: testleri çalıştırırken CTest'e geçirilen ek komut satırı seçeneklerini belirtir."
- `description`: menülerde görünecek olan bu yapılandırmanın açıklaması.
- `enableClangTidyCodeAnalysis`: kod analizi için Clang-Tidy kullanın.
- `enableMicrosoftCodeAnalysis`: kod analizi için Microsoft kod analizi araçlarını kullanın.
- `generator`: bu yapılandırma için kullanılacak CMake jeneratörbelirtir. Bunlardan biri olabilir:
  
  **Yalnızca Visual Studio 2019:**
  - Görsel Stüdyo 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 ve sonrası:**
  - Görsel Stüdyo 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Görsel Stüdyo 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - Unix Makefiles
  - Ninja

Ninja esneklik ve fonksiyon yerine hızlı yapı hızları için tasarlanmış olduğundan, varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri doğru Ninja kullanarak inşa etmek mümkün olmayabilir. Bu durumda, CMake'e Visual Studio projeleri oluşturması için talimat verebilirsiniz.

Visual Studio 2017'de Visual Studio jeneratörü belirlemek için **CMake | CMake Ayarlarını Değiştir.** "Ninja"yı silin ve "V" yazın. Bu, Istediğiniz jeneratörü seçmenize olanak tanıyan IntelliSense'i etkinleştirir.

Visual Studio 2019'da Visual Studio jeneratörü belirlemek için **Solution Explorer'daki** *CMakeLists.txt* dosyasına sağ tıklayın ve Project > Show Advanced Settings **CMake Generator**için **CMake** **Ayarlarını** > seçin.

Etkin yapılandırma bir Visual Studio jeneratörü belirttiğinde, varsayılan olarak MSBuild.exe bağımsız değişkenlerle `-m -v:minimal` çağrılır. *CMakeSettings.json* dosyasının içinde yapıyı özelleştirmek için, `buildCommandArgs` özellik üzerinden yapı sistemine geçirilecek ek [MSBuild komut satırı bağımsız değişkenlerini](../build/reference/msbuild-visual-cpp-overview.md) belirtebilirsiniz:

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: CMake'in seçilen jeneratör için yükleme hedefleri oluşturduğu dizini belirtir. Desteklenen makrolar, `${workspaceRoot}` `${workspaceHash}`, `${projectFile}` `${projectDir}`, `${thisFile}` `${thisFileDir}`, `${name}` `${generator}`, `${env.VARIABLE}`, , .
- `inheritEnvironments`: bu yapılandırmanın bağlı olduğu bir veya daha fazla derleyici ortamını belirtir. Herhangi bir özel ortam veya önceden tanımlanmış ortamlardan biri olabilir. Daha fazla bilgi için [Ortamlar'a](#environments)bakın.
- `intelliSenseMode`: intellisense bilgi hesaplamak için kullanılan modu belirtir". Bunlardan biri olabilir:

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
  - linux-gcc-kol"

- `name`: yapılandırmayı adlandırır.  Önceden tanımlanmış yapılandırmalar hakkında daha fazla bilgi için [CMake önceden tanımlanmış yapılandırma başvurusuna](cmake-predefined-configuration-reference.md) bakın.
- `wslPath`: Linux için Windows Alt Sistemi bir örneğin başlatıcısı için yol.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux projeleri için ek ayarlar

- `remoteMachineName`: CMake, builds ve hata ayıklama barındıran uzak Linux makinesinin adını belirtir. Yeni Linux makineleri eklemek için Bağlantı Yöneticisi'ni kullanın. Desteklenen makrolar `${defaultRemoteMachineName}`içerir.
- `remoteCopySourcesOutputVerbosity`: kaynak kopyalama işleminin ayrıntılı düzeyini uzak makineye belirtir. "Normal", "Verbose" veya "Diagnostic" olabilir.
- `remoteCopySourcesConcurrentCopies`: kaynakların uzak makineye senkronizasyonu sırasında kullanılan eşzamanlı kopya sayısını belirtir (yalnızca sftp).
- `remoteCopySourcesMethod`: dosyaları uzak makineye kopyalama yöntemini belirtir. "Rsync" veya "sftp" olabilir.
- `remoteCMakeListsRoot`: CMake projesini içeren uzak makinedeki dizini belirtir. Desteklenen makrolar, `${workspaceRoot}` `${workspaceHash}`, `${projectFile}` `${projectDir}`, `${thisFile}` `${thisFileDir}`, `${name}` `${generator}`, `${env.VARIABLE}`, , .
- `remoteBuildRoot`: CMake'in seçilen jeneratör için komut dosyası oluşturduğu uzak makinedeki dizin belirtir. Desteklenen makrolar, `${workspaceRoot}` `${workspaceHash}`, `${projectFile}` `${projectDir}`, `${thisFile}` `${thisFileDir}`, `${name}` `${generator}`, `${env.VARIABLE}`, , .
- `remoteInstallRoot`: CMake'in seçilen jeneratör için yükleme hedefleri oluşturduğu uzak makinedeki dizin belirtir. Desteklenen makrolar, `${workspaceRoot}` `${workspaceHash}`, `${projectFile}` `${projectDir}`, `${thisFile}` `${thisFileDir}`, `${name}` `${generator}`, `${env.VARIABLE}` , `VARIABLE` , , ve nerede sistem, kullanıcı veya oturum düzeyinde tanımlanmış bir ortam değişkenidir.
- `remoteCopySources`: `boolean` Visual Studio'nun kaynak dosyalarını uzak makineye kopyalaması gerekip gerekmediğini belirten bir belgedir. Varsayılan değer doğrudur. Dosya eşitlemasını kendiniz yönetiyorsanız false olarak ayarlayın.
- `remoteCopyBuildOutput`: `boolean` Uzak sistemden yapı çıktılarının kopyalanıp kopyalanmayacağını belirten bir.
- `remoteCopyAdditionalIncludeDirectories`: IntelliSense'i desteklemek için uzak makineden kopyalanacak dizinler ektir. "/path1;/path2..." olarak biçimlendirin.
- `remoteCopyExcludeDirectories`: Uzak makineden kopyalamak için dizinler ekle. "/path1;/path2..." olarak biçimlendirin.
- `remoteCopyUseCompilerDefaults`: Derleyicinin varsayılan tanımlarını kullanıp kullanmayacağını ve IntelliSense yollarını içereceğini belirtir. Yalnızca gcc stili bağımsız değişkenlerini desteklememek için kullanılan derleyiciler yanlış olmalıdır.
- `rsyncCommandArgs`: rsync'e geçirilen bir dizi ek komut satırı seçeneği belirtir.
- `remoteCopySourcesExclusionList`: `array` Kaynak dosyaları kopyalarken dışlanacak yolların listesini belirten bir yol': bir yol bir dosyanın/dizinin adı veya kopyanın köküne göre bir yol olabilir. Joker \\ \" * \\ karakterler \" ve? \\ \" \\ glob desen eşleştirme için \" kullanılabilir.
- `cmakeExecutable`: dosya adı ve uzantısı da dahil olmak üzere, cmake programı yürütülebilir tam yol belirtir.
- `remotePreGenerateCommand`: *CMakeLists.txt* dosyasını ayrıştmak için CMake'i çalıştırmadan önce çalıştırmak için gereken komutu belirtir.
- `remotePrebuildCommand`: oluşturmadan önce uzak makinede çalıştırmak için komut belirtir.
- `remotePostbuildCommand`: bina yı kaldıktan sonra uzak makinede çalıştırmak için komut belirtir.
- `variables`: CMake'e **-D** * _ad_=değeri* olarak geçecek cmake değişkenlerinin ad değeri çiftini içerir. CMake proje oluşturma yönergeleriniz herhangi bir değişkenin doğrudan *CMakeCache.txt* dosyasına eklenmesini belirtiyorsa, bunları buraya eklemeniz önerilir. Aşağıdaki örnekte, 14.14.26428 MSVC araç kümesinin ad değeri çiftleri nasıl belirtilir:

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

Eğer , `"type"` `"STRING"` türü varsayılan olarak kabul edilecektir tanımlamazsanız unutmayın.

- `remoteCopyOptimizations`: **Visual Studio 2019 sürüm 16.5 veya daha sonraki** özellikleri uzak hedefe kaynak kopyasını kontrol etmek için. Optimizasyonlar varsayılan olarak etkinleştirilir. Içerir `remoteCopyUseOptimizations` `rsyncSingleDirectoryCommandArgs`, `remoteCopySourcesMaxSmallChange`ve .

## <a name="environments"></a><a name="environments"></a>Ortam

*Ortam,* Visual Studio'nun cmake.exe'yi çağırmak için kullandığı işlemde ayarlanan ortam değişkenlerini kapsüller. MSVC projeleri için değişkenler, belirli bir platform için geliştirici [komut isteminde](building-on-the-command-line.md) ayarlanan değişkenlerdir. `msvc_x64_x64` Örneğin, ortam **VS 2017 için Geliştirici Komut Komut Istem'ini** veya VS **2019 için Geliştirici Komut Komut Istem'ini** **-arch=amd64 -host_arch=amd64** bağımsız değişkenleriyle çalıştırmakla aynıdır. `env.{<variable_name>}` *CMakeSettings.json'daki* sözdizimini, örneğin klasörlere giden yollar oluşturmak için tek tek ortam değişkenlerine başvurmak için kullanabilirsiniz.  Önceden tanımlanmış aşağıdaki ortamlar sağlanır:

- linux_arm: Hedef ARM Linux uzaktan.
- linux_x64: Hedef x64 Linux uzaktan.
- linux_x86: Hedef x86 Linux uzaktan.
- msvc_arm: MSVC derleyicisi ile ARM Windows'u hedefleyin.
- msvc_arm_x64: 64 bit MSVC derleyicili ARM Windows'u hedefleyin.
- msvc_arm64: MSVC derleyicisi ile ARM64 Windows hedef.
- msvc_arm64_x64: 64 bit MSVC derleyicisi ile ARM64 Windows'u hedefleyin.
- msvc_x64: MSVC derleyicisi ile x64 Windows'u hedefleyin.
- msvc_x64_x64: 64 bit MSVC derleyicisi ile x64 Windows'u hedefleyin.
- msvc_x86: MSVC derleyicisi ile x86 Windows'u hedefleyin.
- msvc_x86_x64: 64 bit MSVC derleyicisi ile x86 Windows'u hedefleyin.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>CMakeLists.txt'den çevre değişkenlerine erişim

CMakeLists.txt dosyasından, tüm ortam değişkenleri sözdizimi `$ENV{variable_name}`tarafından başvurulur. Bir ortam için kullanılabilir değişkenleri görmek için, ilgili `SET`komut istemini açın ve yazın. Çevre değişkenleri bazı bilgiler de CMake sistemi içgözlem değişkenleri aracılığıyla kullanılabilir, ancak çevre değişkeni kullanmak için daha uygun bulabilirsiniz. Örneğin, MSVC derleyici sürümü veya Windows SDK sürümü ortam değişkenleri aracılığıyla kolayca alınabilir.

### <a name="custom-environment-variables"></a>Özel ortam değişkenleri

' `CMakeSettings.json`de, `environments` dizide genel olarak veya yapılandırma başına özel ortam değişkenleri tanımlayabilirsiniz. Özel ortam, önceden tanımlanmış bir ortam yerine kullanabileceğiniz özellikler kümesini gruplandırmak veya önceden tanımlanmış bir ortamı genişletmek veya değiştirmek için kullanışlı bir yoldur. Dizideki `environments` her öğe aşağıdakilerden oluşur:

- `namespace`: değişkenlerinin formdaki `namespace.variable`bir yapılandırmadan başvurulabilmesi için ortamı adlandırır. Varsayılan ortam nesnesi çağrılır `env` ve 'de `%USERPROFILE%`dahil olmak üzere belirli sistem ortamı değişkenleri ile doldurulur.
- `environment`: bu değişken grubunu benzersiz olarak tanımlar. Grubun daha sonra bir `inheritEnvironments` girişte devralınmasına izin verir.
- `groupPriority`: Bu değişkenleri değerlendirirken önceliğini belirten bir karşısayı. Önce daha yüksek sayı öğeleri değerlendirilir.
- `inheritEnvironments`: Bu grup tarafından devralınan ortamkümesini belirten bir dizi değer. Bu özellik, varsayılan ortamları devralmanızı ve çalıştığında CMake.exe'ye geçirilen özel ortam değişkenleri oluşturmanıza olanak tanır.

**Visual Studio 2019 sürüm 16.4 ve sonrası:** Hata ayıklama hedefleri *CMakeSettings.json'da*belirttiğiniz ortamla otomatik olarak başlatılır. [Launch.vs.json](launch-vs-schema-reference-cpp.md) ve [tasks.vs.json'da](tasks-vs-json-schema-reference-cpp.md)hedef başına veya görev başına olarak ortam değişkenlerini geçersiz kılabilir veya ekleyebilirsiniz.

Aşağıdaki örnek, hem x86-Hata Ayıklama hem de x64-Hata Ayıklama yapılandırmalarında devralınan bir global değişken olan **BuildDir'ı**tanımlar. Her yapılandırma, bu yapılandırma için **buildRoot** özelliğinin değerini belirtmek için değişkeni kullanır. Her yapılandırmanın yalnızca bu yapılandırmaya uygulanan bir değişkeni belirtmek için **devralan Ortamlar** özelliğini nasıl kullandığına da dikkat edin.

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

Sonraki örnekte, x86-Hata Ayıklama **yapılandırması BuildDir** özelliği için kendi değerini tanımlar. Bu değer, global **BuildDir** özelliği tarafından ayarlanan değeri geçersiz `D:\custom-builddir\x86-Debug`kılar, böylece **BuildRoot'un** değerini .'ye göre değerlendirir.

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
      // Since this configuration doesn't modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="macros"></a>Makrolar

Aşağıdaki makrolar *CMakeSettings.json*kullanılabilir:

- `${workspaceRoot}`– çalışma alanı klasörünün tam yolu
- `${workspaceHash}`– çalışma alanı konumu karma; geçerli çalışma alanı için benzersiz bir tanımlayıcı oluşturmak için yararlıdır (örneğin, klasör yollarında kullanmak için)
- `${projectFile}`– kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}`– kök CMakeLists.txt dosyasının klasörünün tam yolu
- `${thisFile}`– dosyanın `CMakeSettings.json` tam yolu
- `${name}`– yapılandırmanın adı
- `${generator}`– Bu yapılandırmada kullanılan CMake jeneratörünün adı

*CMakeSettings.json'daki* makrolara ve ortam değişkenlerine yapılan tüm başvurular cmake.exe komut satırına geçirilmeden önce genişletilir.

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a>Ninja komut satırı bağımsız değişkenleri

Hedefler belirtilmemişse, 'varsayılan' hedef oluşturur.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --sürüm  | print ninja sürümü ("1.7.1")|
|   -C DIR   | başka bir şey yapmadan önce DIR'e değiştirin|
|   -f DOSYA  | giriş oluşturma dosyası belirtin (default=build.ninja)|
|   -j N     | n işleri paralel olarak çalıştırın (varsayılan=14, CPU'lardan türetilmiş)|
|   -k N     | N işleri başarısız olana kadar devam edin (varsayılan=1)|
|   -l N     | yük ortalaması N'den büyükse yeni işlere başlama|
|   -n       | kuru çalıştırın (komutları çalıştırmayın ama başarılı gibi hareket)|
|   -v       | inşa ederken tüm komut satırlarını göster|
|   -d MODU  | hata ayıklamayı etkinleştirme (liste kipleri için -d listesini kullan)|
|   -t ARAÇ  | bir alt araç çalıştırın (alt alt araçları listelemek için -t listesini kullanın). üst düzey seçenekleri sona erdirir; daha fazla bayrak araca geçirilir|
|   -w BAYRAK  | uyarıları ayarlama (uyarıları listelemek için -w listesini kullanın)|

::: moniker-end
