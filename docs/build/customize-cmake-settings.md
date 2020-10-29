---
title: Visual Studio 'da CMake derleme ayarlarını özelleştirme
ms.date: 08/20/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: 9fa1a21b26088482fb64441d0ccf0ad968bd480f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92919273"
---
# <a name="customize-cmake-build-settings"></a>CMake derleme ayarlarını özelleştirme

::: moniker range="msvc-160"

Visual Studio 2019 ve üzeri sürümlerde, **CMake ayarları düzenleyicisini** kullanarak yapılandırma ekleyebilir ve ayarlarını özelleştirebilirsiniz. Düzenleyicinin dosyada *CMakeSettings.js* el ile düzenlenmesi için daha basit bir alternatif olması amaçlanmıştır, ancak dosyayı doğrudan düzenlemek isterseniz, düzenleyicinin sağ üst köşesindeki **JSON bağlantısını Düzenle** ' ye tıklayabilirsiniz.

Düzenleyiciyi açmak için ana araç çubuğunda **yapılandırma** açılan düğmesine tıklayın ve **yapılandırmaları Yönet** ' i seçin.

![CMake yapılandırma açılır](media/vs2019-cmake-manage-configurations.png)

Artık **Ayarlar düzenleyicisini** sol taraftaki yüklü yapılandırmalara görürsünüz.

![CMake ayarları Düzenleyicisi](media/cmake-settings-editor.png)

Visual Studio `x64-Debug` Varsayılan olarak bir yapılandırma sağlar. Yeşil artı işaretine tıklayarak daha fazla yapılandırma ekleyebilirsiniz. Düzenleyicide gördüğünüz ayarlar hangi yapılandırmanın seçili olduğuna bağlı olarak değişiklik gösterebilir.

Düzenleyicide seçtiğiniz seçenekler *üzerindeCMakeSettings.js* adlı bir dosyaya yazılır. Bu dosya, projeleri oluştururken CMake 'e geçirilen komut satırı bağımsız değişkenleri ve ortam değişkenleri sağlar. Visual Studio *CMakeLists.txt* otomatik olarak değiştirmez; *CMakeSettings.js* kullanarak, derlemeyi Visual Studio aracılığıyla özelleştirebilir, böylece ekibinizdeki diğer kişilerin kullandıkları araçlarla onları kullanabilmesi Için CMake proje dosyalarını dokunmadan özelleştirebilirsiniz.

## <a name="cmake-general-settings"></a>CMake genel ayarları

**Genel** başlık altında aşağıdaki ayarlar kullanılabilir:

### <a name="configuration-name"></a>Yapılandırma adı

**Ad** ayarına karşılık gelir. Bu ad, C++ yapılandırma açılan listesinde görünür. `${name}`Yollar gibi diğer özellik değerlerini oluşturmak için makrosunu kullanabilirsiniz.

### <a name="configuration-type"></a>Yapılandırma türü

**ConfigurationType** ayarına karşılık gelir. Seçili Oluşturucu için derleme yapılandırma türünü tanımlar. Şu anda desteklenen değerler şunlardır "Debug", "MinSizeRel", "Release" ve "Relwithdeınfo". [CMAKE_BUILD_TYPE](https://cmake.org/cmake/help/latest/variable/CMAKE_BUILD_TYPE.html)eşlenir.

### <a name="toolset"></a>Araç Takımı

**Inheritedenvironments** ayarına karşılık gelir. Seçilen yapılandırmayı oluşturmak için kullanılan derleyici ortamını tanımlar. Desteklenen değerler yapılandırma türüne bağlıdır. Özel bir ortam oluşturmak için, ayarlar düzenleyicisinin sağ üst köşesindeki **JSON 'U Düzenle** bağlantısını seçin ve dosyadaki *CMakeSettings.js* doğrudan düzenleyin.

### <a name="cmake-toolchain-file"></a>CMake araç zinciri dosyası

[CMake araç zinciri dosyasının](https://cmake.org/cmake/help/latest/variable/CMAKE_TOOLCHAIN_FILE.html)yolu. Bu yol CMake "-DCMAKE_TOOLCHAIN_FILE =" olarak geçirilir \<filepath> . Araç zinciri dosyaları, derleyicilerin ve araç zinciri yardımcı programlarının ve diğer hedef platformun ve derleyicinin ilgili bilgilerinin konumlarını belirtir. Varsayılan olarak, bu ayar belirtilmemişse Visual Studio [vcpkg toolzincirde dosyasını](https://github.com/microsoft/vcpkg/blob/master/docs/examples/installing-and-using-packages.md#cmake) kullanır.

### <a name="build-root"></a>Derleme kökü

**Buildroot** öğesine karşılık gelir. [CMAKE_BINARY_DIR](https://cmake.org/cmake/help/v3.15/variable/CMAKE_BINARY_DIR.html)eşlenir ve CMake önbelleğinin nerede oluşturulacağını belirtir. Belirtilen klasör mevcut değilse oluşturulur.

## <a name="command-arguments"></a>Komut bağımsız değişkenleri

Aşağıdaki ayarlar **komut bağımsız değişkenleri** başlığı altında bulunur:

### <a name="cmake-command-arguments"></a>CMake komut bağımsız değişkenleri

**Cmakecommandargs** öğesine karşılık gelir. CMake.exe gönderilen ek [komut satırı seçeneklerini](https://cmake.org/cmake/help/latest/manual/cmake.1.html) belirtir.

### <a name="build-command-arguments"></a>Derleme komutu bağımsız değişkenleri

**Buildcommandargs** öğesine karşılık gelir. Temel yapı sistemine geçirilecek ek anahtarlar belirtir. Örneğin, `-v` dokja oluşturucusunu kullanmanın ne zaman geçirilmesi, komut satırları çıktısını almak Için dokja zorlar.

### <a name="ctest-command-arguments"></a>CTest komut bağımsız değişkenleri

**Ctestcommandargs** öğesine karşılık gelir. Testleri çalıştırırken CTest 'e geçirilecek ek [komut satırı seçeneklerini](https://cmake.org/cmake/help/v3.15/manual/ctest.1.html) belirtir.

## <a name="general-settings-for-remote-builds"></a>Uzak derlemeler için genel ayarlar

Uzak derlemeleri kullanan Linux gibi yapılandırmalar için aşağıdaki ayarlar da kullanılabilir:

### <a name="rsync-command-arguments"></a>rsync komut bağımsız değişkenleri

Hızlı ve çok yönlü bir dosya kopyalama aracı olan [rsync](https://download.samba.org/pub/rsync/rsync.html)'e geçirilen ek komut satırı seçenekleri.

## <a name="cmake-variables-and-cache"></a>CMake değişkenleri ve önbelleği

Bu ayarlar, CMake değişkenlerini ayarlamanıza ve *üzerindeCMakeSettings.js* kaydetmenizi sağlar. Derleme zamanında CMake 'e geçirilir ve *CMakeLists.txt* dosyasında hangi değerlerin olduğunu geçersiz kılar. Bu bölümü, düzenlenecek tüm CMake değişkenlerinin listesini görüntülemek için Cmakeguı 'yi kullandığınız şekilde kullanabilirsiniz. Gelişmiş değişkenler de dahil olmak üzere, düzenleme için kullanılabilen tüm CMake değişkenlerinin listesini görüntülemek için **önbelleği Kaydet ve oluştur** düğmesine tıklayın (Cmakeguı başına). Listeyi değişken adına göre filtreleyebilirsiniz.

**Değişkenlere** karşılık gelir. **-D** *_ad_ = _değeri_* CMake olarak geçirilen bir ad-değer çifti değişkeni içerir. CMake proje derleme yönergelerinizi herhangi bir değişkenin eklenmesini doğrudan CMake önbellek dosyasına belirtiyorsanız, bunun yerine bunları buraya eklemenizi öneririz.

## <a name="advanced-settings"></a>Gelişmiş ayarlar

### <a name="cmake-generator"></a>CMake Oluşturucusu

**Oluşturucuya** karşılık gelir. CMake **-G** anahtarına eşlenir ve kullanılacak [CMake oluşturucuyu](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) belirtir. Bu özellik `${generator}` , diğer özellik değerlerini oluştururken makro olarak da kullanılabilir. Visual Studio şu anda aşağıdaki CMake Kurucularını desteklemektedir:

- Ninja
- "Unix makefiles"
- "Visual Studio 16 2019"
- "Visual Studio 16 2019 Win64"
- "Visual Studio 16 2019 ARM"
- "Visual Studio 15 2017"
- "Visual Studio 15 2017 Win64"
- "Visual Studio 15 2017 ARM"
- "Visual Studio 14 2015"
- "Visual Studio 14 2015 Win64"
- "Visual Studio 14 2015 ARM"
  
Dokja esneklik ve işlev yerine hızlı derleme hızları için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri Dokja kullanarak doğru şekilde derlemeyebilir. Böyle bir durumla karşılaşırsanız, CMake 'in bunun yerine bir Visual Studio projesi oluşturmasını sağlayabilirsiniz.

### <a name="intellisense-mode"></a>IntelliSense modu

IntelliSense altyapısı tarafından kullanılan IntelliSense modu. Hiçbir mod seçilmezse, Visual Studio belirtilen araç kümesinden devralınır.  

### <a name="install-directory"></a>Dizin yüklemesi

CMake 'in hedefleri yüklediği dizin. [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)eşlenir.

### <a name="cmake-executable"></a>CMake yürütülebiliri

Dosya adı ve uzantısıyla birlikte CMake program yürütülebilirinin tam yolu. Visual Studio ile özel bir CMake sürümü kullanmanıza olanak sağlar. Uzak derlemeler için, uzak makinede CMake konumunu belirtin.

Uzak derlemeleri kullanan Linux gibi yapılandırmalar için aşağıdaki ayarlar da kullanılabilir:

### <a name="remote-cmakeliststxt-root"></a>Uzak CMakeLists.txt kökü

Uzak makinedeki kök *CMakeLists.txt* dosyasını içeren dizin.

### <a name="remote-install-root"></a>Uzaktan Install root

CMake 'in hedefleri yüklediği uzak makinedeki dizin. [CMAKE_INSTALL_PREFIX](https://cmake.org/cmake/help/latest/variable/CMAKE_INSTALL_PREFIX.html)eşlenir.

### <a name="remote-copy-sources"></a>Uzak kopya kaynakları

Kaynak dosyaların uzak makineye kopyalanıp kopyalanmayacağını belirtir ve rsync veya SFTP kullanıp kullanmayacağınızı belirtmenize izin verir.

## <a name="directly-edit-cmakesettingsjson"></a>CMakeSettings.jsdoğrudan düzenleme

Ayrıca, özel yapılandırma oluşturmak için *CMakeSettings.js* doğrudan düzenleyebilirsiniz. **Ayarlar Düzenleyicisi** 'nin sağ üst köşesinde dosyayı düzenleme için açan bir **JSON Düzenle** düğmesi vardır.

Aşağıdaki örnekte, bir başlangıç noktası olarak kullanabileceğiniz örnek bir yapılandırma gösterilmektedir:

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

JSON IntelliSense, dosyadaki *CMakeSettings.js* düzenlemenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Ayrıca, uyumsuz ayarları seçtiğinizde JSON Düzenleyicisi size bildirir.

Dosyadaki özelliklerin her biri hakkında daha fazla bilgi için bkz. [ şema başvurusundaCMakeSettings.js](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=msvc-150"

Visual Studio 2017, belirli bir proje için CMake önbelleğini oluşturmak üzere CMake.exe nasıl çağrılacağını tanımlayan birkaç CMake yapılandırması sunar. Yeni bir yapılandırma eklemek için, araç çubuğunda yapılandırma açılır listesini tıklatın ve **yapılandırmaları Yönet** ' i seçin:

   ![CMake yönetme yapılandırması](media/cmake-manage-configurations.png)

Önceden tanımlanmış yapılandırmaların listesinden seçim yapabilirsiniz:

   ![CMake önceden tanımlı yapılandırma](media/cmake-configurations.png)

İlk kez bir yapılandırma seçtiğinizde, Visual Studio projenizin kök klasöründe bir *CMakeSettings.js* dosya oluşturur. Bu dosya, CMake önbellek dosyasını yeniden oluşturmak için kullanılır, örneğin bir **Temizleme** işleminden sonra.

Ek bir yapılandırma eklemek için *CMakeSettings.jsüzerinde* sağ tıklayın ve **yapılandırma Ekle** ' yi seçin.

   ![CMake yapılandırma Ekle](media/cmake-add-configuration.png "CMake yapılandırma Ekle")

Ayrıca, **CMake ayarları düzenleyicisini** kullanarak dosyayı düzenleyebilirsiniz. **Çözüm Gezgini** *üzerindeCMakeSettings.js* sağ tıklayın ve **CMake ayarlarını Düzenle** ' yi seçin. Ya da düzenleyici penceresinin en üstündeki yapılandırma açılır listesinden **yapılandırmaları Yönet** ' i seçin.

Ayrıca, özel yapılandırma oluşturmak için *CMakeSettings.js* doğrudan düzenleyebilirsiniz. Aşağıdaki örnekte, bir başlangıç noktası olarak kullanabileceğiniz örnek bir yapılandırma gösterilmektedir:

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

JSON IntelliSense, dosyadaki *CMakeSettings.js* düzenlemenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Dosyadaki özelliklerin her biri hakkında daha fazla bilgi için bkz. [ şema başvurusundaCMakeSettings.js](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
