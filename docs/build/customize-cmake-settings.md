---
title: Visual Studio'da CMake yapı ayarlarını özelleştirin
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: c6bd1404799ccc9ad6b689646cd066849d48fca8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328686"
---
# <a name="customize-cmake-build-settings"></a>CMake derleme ayarlarını özelleştirme

::: moniker range="vs-2019"

Visual Studio 2019 ve sonraki durumlarda, **CMake ayarları düzenleyicisini**kullanarak yapılandırmalar ekleyebilir ve ayarlarını özelleştirebilirsiniz. Düzenleyici, *CMakeSettings.json* dosyasını el ile düzenlemek için daha basit bir alternatif olarak tasarlanmıştır, ancak dosyayı doğrudan düzenlemeyi tercih ederseniz, editörün sağ üst kısmındaki **JSON'u düzenle** bağlantısını tıklatabilirsiniz.

Düzenleyiciyi açmak için, ana araç çubuğundaki **Yapılandırma** açılır düğmesine tıklayın ve **Yapılandırmaları Yönet'i**seçin.

![CMake yapılandırmaları açılır](media/vs2019-cmake-manage-configurations.png)

Şimdi solda yüklü yapılandırmaları olan Ayarlar Düzenleyicisi'ni görüyorsunuz. **Settings Editor**

![CMake ayarları düzenleyicisi](media/cmake-settings-editor.png)

Visual Studio `x64-Debug` varsayılan olarak bir yapılandırma sağlar. Yeşil artı işaretini tıklatarak ek yapılandırmalar ekleyebilirsiniz. Düzenleyicide gördüğünüz ayarlar, hangi yapılandırmanın seçildiğine bağlı olarak değişebilir.

Editörde seçtiğiniz seçenekler *CMakeSettings.json*adlı bir dosyaya yazılır. Bu dosya, projeleri oluştururken CMake'e geçirilen komut satırı bağımsız değişkenleri ve ortam değişkenleri sağlar. Visual Studio *cmakelists.txt* otomatik olarak değiştirir asla; *CMakeSettings.json'ı* kullanarak, CMake proje dosyalarını el değmemiş halde bırakırken, ekibinizdeki diğer kişiler tarafından kullanılan araçlarla tüketebilmeleri için yapıyı Visual Studio aracılığıyla özelleştirebilirsiniz.

## <a name="cmake-general-settings"></a>CMake Genel Ayarları

Genel **başlık** altında aşağıdaki ayarlar mevcuttur:

### <a name="configuration-name"></a>Yapılandırma adı

**Ad** ayarına karşılık gelir. Bu ad C++ yapılandırma açılır açılır açılır durumda görünür. Makroyu, `${name}` yollar gibi diğer özellik değerlerini oluşturmak için kullanabilirsiniz.

### <a name="configuration-type"></a>Yapılandırma türü

**ConfigurationType** ayarına karşılık gelir. Seçili jeneratör için yapı yapılandırma türünü tanımlar. Şu anda desteklenen değerler "Hata Ayıklama", "MinSizeRel", "Release" ve "RelWithDebInfo"dur. [Bu CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html)için haritalar .

### <a name="toolset"></a>Araç Takımı

**Devralınan Ortamlar** ayarına karşılık gelir. Seçili yapılandırmayı oluşturmak için kullanılan derleyici ortamını tanımlar. Desteklenen değerler yapılandırma türüne bağlıdır. Özel bir ortam oluşturmak için Ayarlar düzenleyicisinin sağ üst köşesindeki **JSON'u edit** bağlantısını seçin ve *CMakeSettings.json* dosyasını doğrudan düzeltin.

### <a name="cmake-toolchain-file"></a>CMake araç zinciri dosyası

[CMake araç zinciri dosyasına](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html)giden yol. Bu yol CMake'e "-DCMAKE_TOOLCHAIN_FILE \<= filepath>" olarak geçirilir. Araç zinciri dosyaları derleyicilerin ve araç zinciri yardımcı programlarının konumlarını ve diğer hedef platformu ve derleyiciyle ilgili bilgileri belirtir. Varsayılan olarak, Visual Studio bu ayar belirtilmemişse [vcpkg araç zinciri dosyasını](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake) kullanır.

### <a name="build-root"></a>Kök oluşturma

**BuildRoot'a**karşılık gelir. [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)eşler ve CMake önbelleğinin nerede oluşturulacağını belirtir. Belirtilen klasör yoksa oluşturulur.

## <a name="command-arguments"></a>Komut bağımsız değişkenleri

Aşağıdaki ayarlar **Komut bağımsız değişkenleri** başlığı altında kullanılabilir:

### <a name="cmake-command-arguments"></a>CMake komut bağımsız değişkenleri

**CmakeCommandArgs'a**karşılık gelir. CMake.exe'ye geçirilen ek [komut satırı seçeneklerini](https://cmake.org/cmake/help/latest/manual/cmake.1.html) belirtir.

### <a name="build-command-arguments"></a>Komut bağımsız değişkenleri oluşturma

**CommandArgs'ı oluşturmaya**karşılık gelir. Temel yapı sistemine geçmek için ek anahtarlar belirtir. Örneğin, Ninja `-v` jeneratör kullanırken geçen ninja komut hatları çıkış için Ninja kuvvetleri.

### <a name="ctest-command-arguments"></a>CTest komut bağımsız değişkenleri

**ctestCommandArgs'a**karşılık gelir. Testleri çalıştırırken CTest'e geçmek için ek [komut satırı seçeneklerini](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html) belirtir.

## <a name="general-settings-for-remote-builds"></a>Uzaktan yapılar için genel ayarlar

Uzaktan yapılar kullanan Linux gibi yapılandırmalar için aşağıdaki ayarlar da kullanılabilir:

### <a name="rsync-command-arguments"></a>rsync komut bağımsız değişkenleri

Ek komut satırı seçenekleri [rsync](https://download.samba.org/pub/rsync/rsync.html)geçti , hızlı ve çok yönlü bir dosya kopyalama aracı.

## <a name="cmake-variables-and-cache"></a>CMake değişkenleri ve önbellek

Bu ayarlar CMake değişkenlerini ayarlamanızı ve *Bunları CMakeSettings.json'a kaydetmenizi*sağlar. Bunlar oluşturma zamanında CMake'e aktarılır ve *CMakeLists.txt* dosyasında bulunan değerleri geçersiz kılar. Bu bölümü, düzenlendirilebilecek tüm CMake değişkenlerinin listesini görüntülemek için CMakeGUI'yi kullanabileceğiniz şekilde kullanabilirsiniz. Gelişmiş değişkenler (CMakeGUI başına) dahil olmak üzere, değiştirilebilecek tüm CMake değişkenlerinin listesini görüntülemek için **Kaydet ve önbellek oluşturma** düğmesini tıklatın. Listeyi değişken adına göre filtreleyebilirsiniz.

**Değişkenlere**karşılık gelir. CMake'e **-D** * _ad_=değeri* olarak geçen CMake değişkenlerinin ad değeri çiftini içerir. CMake proje oluşturma yönergeleriniz herhangi bir değişkenin doğrudan CMake önbellek dosyasına eklenmesini belirtiyorsa, bunları buraya eklemenizi öneririz.

## <a name="advanced-settings"></a>Gelişmiş ayarlar

### <a name="cmake-generator"></a>CMake jeneratör

**Jeneratöre**karşılık gelir. CMake **-G** anahtarına eşler ve [cmake jeneratörü](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) kullanmak için belirtir. Bu özellik, `${generator}`diğer özellik değerleri oluştururken makro olarak da kullanılabilir. Visual Studio şu anda aşağıdaki CMake jeneratörleri destekler:

- "Ninja"
- "Unix Makefiles"
- "Visual Studio 16 2019"
- "Visual Studio 16 2019 Win64"
- "Visual Studio 16 2019 ARM"
- "Visual Studio 15 2017"
- "Visual Studio 15 2017 Win64"
- "Visual Studio 15 2017 ARM"
- "Visual Studio 14 2015"
- "Visual Studio 14 2015 Win64"
- "Visual Studio 14 2015 ARM"
  
Ninja esneklik ve fonksiyon yerine hızlı yapı hızları için tasarlandığıniçin varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri doğru Ninja kullanarak inşa etmek mümkün olmayabilir. Bu durumda, CMake'e bunun yerine bir Visual Studio projesi oluşturması için talimat verebilirsiniz.

### <a name="intellisense-mode"></a>IntelliSense modu

IntelliSense motoru tarafından kullanılan IntelliSense modu. Mod seçili değilse, Visual Studio belirtilen araç kümesinden devralır.  

### <a name="install-directory"></a>Dizin yükle

CMake'in hedefleri yüklü olduğu dizin. Haritalar [CMAKE_INSTALL_PREFIX.](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)

### <a name="cmake-executable"></a>CÇalıştırılabilir olun

Dosya adı ve uzantısı da dahil olmak üzere CMake programına tam yol çalıştırılabilir. Bu Visual Studio ile CMake özel bir sürümünü kullanmanıza olanak sağlar. Uzaktan yapılar için uzak makinedeki CMake konumunu belirtin.

Uzaktan yapılar kullanan Linux gibi yapılandırmalar için aşağıdaki ayarlar da kullanılabilir:

### <a name="remote-cmakeliststxt-root"></a>Uzak CMakeLists.txt kök

Kök *CMakeLists.txt* dosyasını içeren uzak makinedeki dizin.

### <a name="remote-install-root"></a>Uzaktan yükleme kökü

CMake'in hedefleri yüklü olduğu uzak makinedeki dizin. Haritalar [CMAKE_INSTALL_PREFIX.](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)

### <a name="remote-copy-sources"></a>Uzak kopyalama kaynakları

Kaynak dosyaları uzak makineye kopyalayıp kopyalamayacağınızı belirtir ve rsync veya sftp kullanıp kullanmayacağını belirtmenizi sağlar.

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.json'u doğrudan değiştirin

Ayrıca, özel yapılandırmalar oluşturmak için *CMakeSettings.json'u* doğrudan edinebilirsiniz. **Ayarlar** Düzenleyicisi'nin sağ üst kısmında düzenleme için dosyayı açan bir **Düzenle JSON** düğmesi vardır.

Aşağıdaki örnek, başlangıç noktası olarak kullanabileceğiniz örnek yapılandırmayı gösterir:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense, *CMakeSettings.json* dosyasını değiştirmenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

JSON düzenleyicisi, uyumsuz ayarları seçtiğinizde de sizi bilgilendirir.

Dosyadaki özelliklerin her biri hakkında daha fazla bilgi için [CMakeSettings.json şema referansına](cmakesettings-reference.md)bakın.

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017, CMake.exe'nin belirli bir proje için CMake önbelleğini oluşturmak için nasıl çağrıldığını tanımlayan birkaç CMake yapılandırması sağlar. Yeni bir yapılandırma eklemek için araç çubuğundaki yapılandırma açılır masını tıklatın ve **Yapılandırmaları Yönet'i**seçin:

   ![CMake yapılandırmaları yönetir](media/cmake-manage-configurations.png)

Önceden tanımlanmış yapılandırmalar listesinden seçim yapabilirsiniz:

   ![CMake önceden tanımlanmış yapılandırmaları](media/cmake-configurations.png)

İlk yapılandırmayı seçtiğinizde Visual Studio, projenizin kök klasöründe bir *CMakeSettings.json* dosyası oluşturur. Bu dosya, örneğin **Temiz** bir işlemden sonra CMake önbellek dosyasını yeniden oluşturmak için kullanılır.

Ek yapılandırma eklemek için *CMakeSettings.json'a* sağ tıklayın ve **Yapılandırma Ekle'yi**seçin.

   ![CMake Ekle yapılandırması](media/cmake-add-configuration.png "CMake Ekle Yapılandırması")

Ayrıca **CMake Ayarları**Düzenleyicisi'ni kullanarak dosyayı da değiştirebilirsiniz. **Solution Explorer'da** *CMakeSettings.json'a* sağ tıklayın ve **CMake Ayarlarını Edit'i**seçin. Veya, düzenleyici penceresinin üst kısmındaki yapılandırma açılır penceresinden **Yapılandırmaları Yönet'i** seçin.

Ayrıca, özel yapılandırmalar oluşturmak için *CMakeSettings.json'u* doğrudan edinebilirsiniz. Aşağıdaki örnek, başlangıç noktası olarak kullanabileceğiniz örnek yapılandırmayı gösterir:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },
```

JSON IntelliSense, *CMakeSettings.json* dosyasını değiştirmenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Dosyadaki özelliklerin her biri hakkında daha fazla bilgi için [CMakeSettings.json şema referansına](cmakesettings-reference.md)bakın.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da CMake Projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
