---
description: 'Hakkında daha fazla bilgi edinin: CMakeSettings.jsşema başvurusu'
title: Şema başvurusunda CMakeSettings.js
ms.date: 11/22/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 2be5edb616764d56e7c08a51be19aab11a62f227
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156911"
---
# <a name="cmakesettingsjson-schema-reference"></a>Şema başvurusunda CMakeSettings.js

::: moniker range="msvc-140"

CMake projeleri Visual Studio 2017 ve üzeri sürümlerde desteklenir.

::: moniker-end

::: moniker range=">=msvc-150"

**CMakeSettings.jsdosyadaki** , Visual Studio 'nun IntelliSense için kullandığı ve belirtilen bir *yapılandırma* ve derleyici *ortamı* için cmake.exe aktardığı komut satırı bağımsız değişkenlerini oluşturmak için gereken bilgileri içerir. Bir yapılandırma belirli bir platforma ve derleme türüne (örneğin,) uygulanan özellikleri belirtir `x86-Debug` `Linux-Release` . Her yapılandırma, örneğin MSVC, GCC veya Clang gibi derleyici araç takımı hakkındaki bilgileri kapsülleyen bir ortam belirtir. CMake, kök *CMakeCache.txt* dosyasını ve projenin diğer proje dosyalarını yeniden oluşturmak için komut satırı bağımsız değişkenlerini kullanır. Değerler *CMakeLists.txt* dosyalarında geçersiz kılınabilir.

IDE 'ye yapılandırma ekleyebilir veya kaldırabilir ve ardından bunları doğrudan JSON dosyasında düzenleyebilir veya **CMake ayarları düzenleyicisini** (Visual Studio 2019 ve üzeri) kullanabilirsiniz. Çeşitli proje dosyalarını oluşturmak için IDE 'de kolayca yapılandırma arasında geçiş yapabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md) .

## <a name="configurations"></a>Yapılandırmalar

`configurations`Dizi bir CMake projesi için tüm konfigürasyonları içerir. Önceden tanımlanmış yapılandırmalar hakkında daha fazla bilgi için bkz: [CMake önceden tanımlı yapılandırma başvurusu](cmake-predefined-configuration-reference.md) . Dosyaya önceden tanımlanmış veya özel yapılandırmaların sayısını ekleyebilirsiniz.

`configuration`, Şu özelliklere sahiptir:

- `addressSanitizerEnabled`: **`true`** Program, adres Temizleme (Windows üzerinde deneysel) ile derleniyorsa. Linux 'ta, en iyi sonuçlar için-FNO-yoksay-Frame-pointer ve derleyici iyileştirme düzeyi-OS veya-Oo ile derleyin.
- `addressSanitizerRuntimeFlags`: ASAN_OPTIONS ortam değişkeni aracılığıyla Addresstemizleme işlevine geçirilen çalışma zamanı bayrakları. Biçim: FLAG1 = değer: flag2 = değer2.
- `buildCommandArgs`: CMake sonrasında--Build--. geçirilen yerel derleme anahtarlarını belirtir Örneğin, Dokja Oluşturucu kullanıldığında-v ' d e geçiş, komut satırlarını çıktı olarak zorlar. Dokja komutları hakkında daha fazla bilgi için bkz. [dokja komut satırı bağımsız değişkenleri](#ninja) .
- `buildRoot`: CMake 'in seçili Oluşturucu için derleme betikleri oluşturduğu dizini belirtir.  **-DCMAKE_BINARY_DIR** anahtarına eşlenir ve *CMakeCache.txt* nerede oluşturulacağını belirtir. Klasör yoksa, oluşturulur. Desteklenen makrolar şunlardır,,,,, `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` , `${name}` , `${generator}` , `${env.VARIABLE}` .
- `cacheGenerationCommand`: bir komut satırı aracı ve bağımsız değişkenler belirtir, örneğin *gencache.bat hata ayıklama* önbelleği oluşturur. Kullanıcı açık olarak yeniden oluşturma isteğinde bulunduğunda veya bir CMakeLists.txt ya da CMakeSettings.jsbir dosya değiştirildiğinde, komut belirtilen ortamdaki kabuktan çalıştırılır.
- `cacheRoot`: CMake önbelleğinin yolunu belirtir. Bu dizin mevcut bir *CMakeCache.txt* dosyası içermelidir.
- `clangTidyChecks`: Clang-Tidy 'a geçirilecek uyarıların virgülle ayrılmış listesi; Joker karakterlere izin verilir ve '-' öneki denetimleri kaldırır.
- `cmakeCommandArgs`: proje dosyalarını oluşturmak için çağrıldığında CMake 'e geçirilen ek komut satırı seçeneklerini belirtir.
- `cmakeToolchain`: araç zinciri dosyasını belirtir. Bu, CMake kullanılarak-DCMAKE_TOOLCHAIN_FILE geçirilir. "
- `codeAnalysisRuleset`: Kod analizini çalıştırırken kullanılacak RuleSet öğesini belirtir. Bu, Visual Studio tarafından yüklenen bir RuleSet dosyasının tam yolu veya dosya adı olabilir.
- `configurationType`: seçili Oluşturucu için derleme türü yapılandırmasını belirtir. Aşağıdakilerden biri olabilir:

  - Hata ayıklama
  - Yayınla
  - MinSizeRel
  - Relwithdeınfo
  
- `ctestCommandArgs`: testler çalıştırılırken CTest 'e geçirilen ek komut satırı seçeneklerini belirtir. "
- `description`: menülerde görünecek bu yapılandırmanın açıklaması.
- `enableClangTidyCodeAnalysis`: kod analizi için Clang-Tidy kullanın.
- `enableMicrosoftCodeAnalysis`: kod analizi için Microsoft kod analizi araçları 'nı kullanın.
- `generator`: Bu yapılandırma için kullanılacak CMake oluşturucuyu belirtir. Aşağıdakilerden biri olabilir:
  
  **Yalnızca Visual Studio 2019:**
  - Visual Studio 16 2019
  - Visual Studio 16 2019 Win64
  - Visual Studio 16 2019 ARM

  **Visual Studio 2017 ve üzeri:**
  - Visual Studio 15 2017
  - Visual Studio 15 2017 Win64
  - Visual Studio 15 2017 ARM
  - Visual Studio 14 2015
  - Visual Studio 14 2015 Win64
  - Visual Studio 14 2015 ARM
  - UNIX makefiles
  - Ninja

Dokja esneklik ve işlev yerine hızlı derleme hızları için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri Dokja kullanarak doğru şekilde derlemeyebilir. Böyle bir durumla karşılaşırsanız, CMake 'in bunun yerine Visual Studio projeleri oluşturmasını sağlayabilirsiniz.

Visual Studio 2017 ' de bir Visual Studio üreteci belirtmek için CMake ' i seçerek ana menüden Ayarlar düzenleyicisini açın. **CMake ayarlarını değiştirin**. "Dokja" ve "V" yazın. Bu, istediğiniz oluşturucuyu seçmenizi sağlayan IntelliSense 'i etkinleştirir.

Visual Studio 2019 ' de bir Visual Studio Oluşturucusu belirtmek için, **Çözüm Gezgini** *CMakeLists.txt* dosyasına sağ tıklayın ve **CMake ayarları proje için CMake ayarlarını** seçin >  > **CMake oluşturucuyu** göster ' i seçin.

Etkin yapılandırma bir Visual Studio Oluşturucusu belirttiğinde, varsayılan olarak MSBuild.exe `-m -v:minimal` bağımsız değişkenlerle çağrılır. Derlemeyi özelleştirmek için, dosyadaki  *CMakeSettings.js* içinde, özelliği aracılığıyla yapı sistemine geçirilecek ek [MSBuild komut satırı bağımsız değişkenleri](../build/reference/msbuild-visual-cpp-overview.md) belirtebilirsiniz `buildCommandArgs` :

   ```json
   "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
   ```

- `installRoot`: CMake 'in seçili Oluşturucu için bir Install targets oluşturduğu dizini belirtir. Desteklenen makrolar şunlardır,,,,, `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` , `${name}` , `${generator}` , `${env.VARIABLE}` .
- `inheritEnvironments`: Bu yapılandırmanın bağımlı olduğu bir veya daha fazla derleyici ortamını belirtir. Özel bir ortam veya önceden tanımlanmış ortamların biri olabilir. Daha fazla bilgi için bkz. [ortamlar](#environments).
- `intelliSenseMode`: IntelliSense bilgilerini bilgi işlem için kullanılan modu belirtir. Aşağıdakilerden biri olabilir:

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
  - Linux-GCC-ARM "

- `name`: yapılandırmayı adlandırır.  Önceden tanımlanmış yapılandırmalar hakkında daha fazla bilgi için bkz: [CMake önceden tanımlı yapılandırma başvurusu](cmake-predefined-configuration-reference.md) .
- `wslPath`: Linux için Windows alt sistemi örneğinin Başlatıcı yolu.

### <a name="additional-settings-for-cmake-linux-projects"></a>CMake Linux projeleri için ek ayarlar

- `remoteMachineName`: CMake, derlemeler ve hata ayıklayıcıyı barındıran uzak Linux makinenin adını belirtir. Yeni Linux makineleri eklemek için bağlantı yöneticisini kullanın. Desteklenen makrolar şunlardır `${defaultRemoteMachineName}` .
- `remoteCopySourcesOutputVerbosity`: uzak makineye kaynak kopyalama işleminin ayrıntı düzeyini belirtir. "" Normal "," verbose "veya" Diagnostic "değerinden biri olabilir.
- `remoteCopySourcesConcurrentCopies`: kaynakların uzak makineye eşitlenmesi sırasında kullanılan eş zamanlı kopyaların sayısını belirtir (yalnızca SFTP).
- `remoteCopySourcesMethod`: uzak makineye dosya kopyalama yöntemini belirtir. "Rsync" veya "SFTP" olabilir.
- `remoteCMakeListsRoot`: CMake projesini içeren uzak makinedeki dizini belirtir. Desteklenen makrolar şunlardır,,,,, `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` , `${name}` , `${generator}` , `${env.VARIABLE}` .
- `remoteBuildRoot`: uzak makinedeki, CMake 'in seçili Oluşturucu için derleme betikleri oluşturduğu dizini belirtir. Desteklenen makrolar şunlardır,,,,, `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` , `${name}` , `${generator}` , `${env.VARIABLE}` .
- `remoteInstallRoot`: uzak makinedeki, CMake 'in seçili Oluşturucu için Install hedeflerini oluşturduğu dizini belirtir. Desteklenen makrolar,,,,,,, ve ' nin yanı sıra `${workspaceRoot}` `${workspaceHash}` `${projectFile}` `${projectDir}` `${thisFile}` `${thisFileDir}` `${name}` `${generator}` `${env.VARIABLE}` `VARIABLE` sistem, Kullanıcı veya oturum düzeyinde tanımlanmış bir ortam değişkenidir.
- `remoteCopySources`: `boolean` Visual Studio 'nun kaynak dosyaları uzak makineye kopyalamasını gerekip gerekmediğini belirten bir. Varsayılan değer true 'dur. Dosya eşitlemesini kendiniz yönetiyorsanız, false olarak ayarlayın.
- `remoteCopyBuildOutput`: `boolean` Derleme çıktılarının uzak sistemden kopyalanıp kopyalanmayacağını belirten bir.
- `remoteCopyAdditionalIncludeDirectories`: IntelliSense 'i desteklemek için uzak makineden kopyalanacak ek dizinler ekleyin. "/Path1;/path2,.exe" olarak biçimlendirin.
- `remoteCopyExcludeDirectories`: Uzak makineden kopyalanacak dizinleri dahil et. "/Path1;/path2,.exe" olarak biçimlendirin.
- `remoteCopyUseCompilerDefaults`: Derleyicinin varsayılan tanımlar ve IntelliSense için yolların dahil edilip edilmeyeceğini belirtir. Yalnızca, ' deki derleyiciler GCC stili bağımsız değişkenlerini desteklemediğinden yanlış olmalıdır.
- `rsyncCommandArgs`: rsync 'e geçirilen ek komut satırı seçenekleri kümesini belirtir.
- `remoteCopySourcesExclusionList`: `array` Kaynak dosyalarını kopyalarken dışlanacak yolların listesini belirten a: bir yol bir dosyanın/dizinin adı ya da kopyanın köküne göre bir yol olabilir. Joker karakterler \\ \" * \\ \" ve \\ \" ? \\ \" Glob düzeniyle eşleşen bir şekilde kullanılabilir.
- `cmakeExecutable`: dosya adı ve uzantısı dahil olmak üzere CMake program yürütülebilirinin tam yolunu belirtir.
- `remotePreGenerateCommand`: *CMakeLists.txt* dosyasını ayrıştırmak Için CMake 'i çalıştırmadan önce çalıştırılacak komutu belirtir.
- `remotePrebuildCommand`: derlemeden önce uzak makinede çalıştırılacak komutu belirtir.
- `remotePostbuildCommand`: derlemeden sonra uzak makinede çalıştırılacak komutu belirtir.
- `variables`: **-D** *_ad_ = _değeri_* CMake olarak geçirilecek CMake değişkenlerinin ad-değer çiftini içerir. CMake proje derleme yönergelerinizi herhangi bir değişkenin eklenmesini doğrudan *CMakeCache.txt* dosyasına belirtse, bunları buraya eklemeniz önerilir. Aşağıdaki örnek, 14.14.26428 MSVC araç takımı için ad-değer çiftlerinin nasıl kullanılacağını gösterir:

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

Öğesini tanımlamadıysanız, `"type"` `"STRING"` türün varsayılan olarak kabul edilir olduğunu unutmayın.

- `remoteCopyOptimizations`: Uzak hedefe kaynak kopyalamayı denetlemeye yönelik **Visual Studio 2019 sürüm 16,5 veya üzeri** Özellikler. İyileştirmeler varsayılan olarak etkindir. `remoteCopyUseOptimizations`, `rsyncSingleDirectoryCommandArgs` , Ve içerir `remoteCopySourcesMaxSmallChange` .

## <a name="environments"></a><a name="environments"></a> Lý

Bir *ortam* , Visual Studio 'nun cmake.exe çağırmak için kullandığı işlemde ayarlanan ortam değişkenlerini kapsüller. MSVC projeleri için, değişkenler belirli bir platform için [Geliştirici komut isteminde](building-on-the-command-line.md) ayarlanan olanlardır. Örneğin, `msvc_x64_x64` ortam **vs 2017 için geliştirici komut istemi** veya **-arch = AMD64-host_arch = amd64** bağımsız değişkenleriyle **vs 2019 için geliştirici komut istemi** ile aynıdır. `env.{<variable_name>}`Tek tek ortam değişkenlerine başvurmak için, örneğin, klasörlere yol oluşturmak için *CMakeSettings.jsüzerindeki* sözdizimini kullanabilirsiniz.  Aşağıdaki önceden tanımlı ortamlar verilmiştir:

- linux_arm: ARM Linux 'u uzaktan hedefleyin.
- linux_x64: x64 Linux 'u uzaktan hedefleyin.
- linux_x86: x86 Linux 'u uzaktan hedefleyin.
- msvc_arm: MSVC derleyicisi ile ARM pencerelerini hedefleyin.
- msvc_arm_x64:64-bit MSVC derleyicisi ile ARM pencerelerini hedefleyin.
- msvc_arm64: MSVC derleyicisi ile ARM64 Windows hedefleyin.
- msvc_arm64_x64:64-bit MSVC derleyicisi ile ARM64 Windows hedefleyin.
- msvc_x64: MSVC derleyicisi ile x64 Windows 'ı hedefleyin.
- msvc_x64_x64:64-bit MSVC derleyicisi ile x64 Windows 'ı hedefleyin.
- msvc_x86: MSVC derleyicisi ile x86 pencerelerini hedefleyin.
- msvc_x86_x64:64 bit MSVC derleyicisi ile x86 pencerelerini hedefleyin.

### <a name="accessing-environment-variables-from-cmakeliststxt"></a>CMakeLists.txt ortam değişkenlerine erişme

Bir CMakeLists.txt dosyasından, tüm ortam değişkenlerine sözdizimi tarafından başvurulur `$ENV{variable_name}` . Bir ortamın kullanılabilir değişkenlerini görmek için ilgili komut istemi ' ni açın ve yazın `SET` . Ortam değişkenlerinin bazı bilgileri CMake sistem iç denetim değişkenleri aracılığıyla da kullanılabilir, ancak ortam değişkenini kullanmayı daha uygun bulabilirsiniz. Örneğin, MSVC derleyici sürümü veya Windows SDK sürümü, ortam değişkenleri aracılığıyla kolayca alınır.

### <a name="custom-environment-variables"></a>Özel ortam değişkenleri

İçinde  `CMakeSettings.json` , dizide genel olarak veya yapılandırma başına özel ortam değişkenleri tanımlayabilirsiniz `environments` . Özel bir ortam, önceden tanımlanmış bir ortamın yerine kullanabileceğiniz bir özellik kümesini gruplamak veya önceden tanımlanmış bir ortamı genişletmek ya da değiştirmek için kullanışlı bir yoldur. Dizideki her öğe `environments` aşağıdakilerden oluşur:

- `namespace`: bir ortamı, değişkenlerini form içindeki bir yapılandırmadan başvurulabilmeleri için adlandırır `namespace.variable` . Varsayılan ortam nesnesi çağrılır `env` ve dahil olmak üzere belirli sistem ortam değişkenleriyle doldurulur `%USERPROFILE%` .
- `environment`: Bu değişken grubunu benzersiz bir şekilde tanımlar. Grubun daha sonra bir girişte devralınmasını sağlar `inheritEnvironments` .
- `groupPriority`: Bu değişkenlerin değerlendirmesi sırasında önceliğini belirten bir tamsayı. Daha yüksek sayıda öğe önce değerlendirilir.
- `inheritEnvironments`: Bu grup tarafından devralınan ortamlar kümesini belirten bir değerler dizisi. Bu özellik varsayılan ortamları devralmasını ve çalıştırıldığında CMake.exe geçirilen özel ortam değişkenleri oluşturmanızı sağlar.

**Visual Studio 2019 sürüm 16,4 ve üzeri:** Hata ayıklama hedefleri, *üzerindeCMakeSettings.js* belirttiğiniz ortamda otomatik olarak başlatılır. [Üzerindelaunch.vs.js](launch-vs-schema-reference-cpp.md) ve [tasks.vs.jsüzerinde](tasks-vs-json-schema-reference-cpp.md), ortam değişkenlerini, hedef başına veya görev başına temelinde geçersiz kılabilir veya ekleyebilirsiniz.

Aşağıdaki örnek, hem x86-hata ayıklama hem de x64-hata ayıklama yapılandırmalarında devralınan bir genel değişkeni ( **BuildDir**) tanımlar. Her yapılandırma, bu yapılandırma için **buildroot** özelliğinin değerini belirtmek için değişkenini kullanır. Ayrıca, her yapılandırmanın yalnızca bu yapılandırma için geçerli olan bir değişken belirtmek üzere **ınherenler** özelliğini nasıl kullandığını unutmayın.

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

Sonraki örnekte, x86-hata ayıklama yapılandırması **BuildDir** özelliği için kendi değerini tanımlar. Bu değer, genel **BuildDir** özelliği tarafından ayarlanan değeri geçersiz kılar, böylece **buildroot** olarak değerlendirilir `D:\custom-builddir\x86-Debug` .

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

Aşağıdaki makrolar *üzerindeCMakeSettings.js* kullanılabilir:

- `${workspaceRoot}` – çalışma alanı klasörünün tam yolu
- `${workspaceHash}` – çalışma alanı konumunun karması; geçerli çalışma alanı için benzersiz bir tanımlayıcı oluşturmak için kullanışlıdır (örneğin, klasör yollarında kullanmak için)
- `${projectFile}` – kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}` – kök CMakeLists.txt dosyasının klasörünün tam yolu
- `${thisFile}`– dosyanın tam yolu `CMakeSettings.json`
- `${name}` – yapılandırmanın adı
- `${generator}` – Bu yapılandırmada kullanılan CMake oluşturucusunun adı

*CMakeSettings.jsüzerindeki* makrolar ve ortam değişkenlerine yapılan tüm başvurular cmake.exe komut satırına geçirilmeden önce genişletilir.

## <a name="ninja-command-line-arguments"></a><a name="ninja"></a> Dokja komut satırı bağımsız değişkenleri

Hedefler belirtilmemişse, ' default ' hedefini oluşturur.

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --sürüm  | dokja sürümünü Yazdır ("1.7.1")|
|   -C DIR   | başka bir şey yapmadan önce DIR olarak değiştirin|
|   -f dosyası  | giriş derleme dosyasını belirtin (varsayılan = Build. dokja)|
|   -j N     | N işi paralel olarak çalıştır (varsayılan = 14, kullanılabilir CPU 'Larda türetilir)|
|   -k N     | N işleri başarısız olana kadar devam edin (varsayılan = 1)|
|   -l N     | Yük ortalaması N değerinden büyükse yeni işleri başlatma|
|   -n       | Kuru çalıştırma (komutları çalıştırmayın ancak başarılı oldukları gibi davranın)|
|   -v       | oluşturma sırasında tüm komut satırlarını göster|
|   -d modu  | hata ayıklamayı etkinleştir (modları listelemek için-d listesini kullanın)|
|   -t aracı  | bir alt araç çalıştırın (alt araçları listelemek için-t listesini kullanın). üst düzey seçenekleri sonlandırır; araca daha fazla bayrak geçirilir|
|   -w bayrağı  | uyarıları ayarlama (uyarıları listelemek için-w listesini kullanın)|

::: moniker-end
