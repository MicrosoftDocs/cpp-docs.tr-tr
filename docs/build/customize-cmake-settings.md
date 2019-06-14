---
title: Visual Studio'da CMake derleme ayarlarını özelleştirme
ms.date: 05/16/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: a00b18f163758be0238a05c4d2af3195014d79b0
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042544"
---
# <a name="customize-cmake-build-settings"></a>CMake derleme ayarlarını özelleştirme

::: moniker range="vs-2019"

Visual Studio 2019 ve sonraki sürümlerinde, yapılandırmaları ekleyebilir ve ayarlarını kullanarak özelleştirebileceğiniz **CMake ayarları Düzenleyicisi**. Düzenleyici daha basit bir CMakeSettings.json dosyayı elle düzenlemeye alternatif olması beklenir, ancak dosyayı doğrudan düzenlemek isterseniz, tıklayabilirsiniz **Düzenle JSON** bağlantıyı sağ üst kısmındaki Düzenleyici. 

Düzenleyicisi'ni açmak için tıklayın **yapılandırma** seçin ve açılır ana araç çubuğunda **yapılandırmaları yönetme**.

![CMake yapılandırmaları açılır](media/vs2019-cmake-manage-configurations.png)

Şimdi, gördüğünüz **ayarları Düzenleyicisi** soldaki yüklenmiş yapılandırmaya sahip. 

![CMake ayarları Düzenleyicisi](media/cmake-settings-editor.png)

Visual Studio, varsayılan olarak iki yapılandırmaları sunar: `x64-Debug` ve `x86-Debug`. Ek yapılandırmalar yeşil artı işaretine tıklayarak ekleyebilirsiniz. Düzenleyici'de gördüğünüz ayarları yapılandırması seçili olan bağlı olarak değişebilir.

Düzenleyici'de seçtiğiniz seçenekler CMakeSettings.json adlı bir dosyaya yazılır. Bu dosya, komut satırı bağımsız değişkenleri ve projeler derlerken Cmake'e geçirilen ortam değişkenleri sağlar. Visual Studio CMakeLists.txt hiçbir zaman otomatik olarak değiştirir; CMakeSettings.json kullanarak ekibinizdeki kullandıkları ne olursa olsun araçlarıyla kullanabilir, böylece CMake proje dosyaları dokunulmadan bırakarak Visual Studio ile derleme özelleştirebilirsiniz.

## <a name="cmake-general-settings"></a>CMake genel ayarlar

Aşağıdaki ayarlar altında kullanılabilir **genel** başlığı:

### <a name="configuration-name"></a>Yapılandırma adı

Karşılık gelen **adı** ayarı. Bu görünen addır C++ yapılandırma açılır. Kullanabileceğiniz `${name}` makrosu yolları gibi diğer özellik değerleri oluşturmak için.


### <a name="configuration-type"></a>Yapılandırma türü

Karşılık gelen **configurationType** ayarı. Seçili Oluşturucu için derleme yapılandırması türü tanımlar. Şu anda desteklenen değerler şunlardır: "Debug", "MinSizeRel", "Sürüm" ve "RelWithDebInfo".

### <a name="toolset"></a>Araç Takımı

Karşılık gelen **inheritedEnvironments** ayarı. Seçili yapılandırma oluşturmak için kullanılacak derleme ortamı tanımlar. Desteklenen değerler yapılandırma türüne bağlıdır. Özel bir ortam oluşturmak için tıklayın **Düzenle JSON** bağlantı ayarları Düzenleyicisi sağ üst köşesinde ve CMakeSettings.json dosyasına doğrudan düzenleyebilirsiniz.

### <a name="cmake-toolchain-file"></a>CMake araç zinciri dosyası

CMake araç zinciri dosyasının yolu. Cmake'e geçirilen "-DCMAKE_TOOLCHAIN_FILE = \<DosyaYolu >".

### <a name="build-root"></a>Kök derleme

Karşılık gelen **buildRoot**. Eşlendiği **-DCMAKE_BINARY_DIR** geçin ve CMake önbelleği oluşturulacağı belirtir. Klasör mevcut değilse oluşturulur.

## <a name="command-arguments"></a>Komut bağımsız değişkenleri

Aşağıdaki ayarlar altında kullanılabilir **komut bağımsız değişkenleri** başlığı:

### <a name="cmake-command-arguments"></a>CMake komut bağımsız değişkenleri

Karşılık gelen **cmakeCommandArgs**. CMake.exe için geçirmek istediğiniz herhangi bir ek anahtarlar belirtir.

### <a name="build-command-arguments"></a>Komut satırı bağımsız değişkenlerini yapı

Karşılık gelen **buildCommandArgs**: temel alınan geçirilecek ek anahtarlar derleme sistemi belirtir. Örneğin, Ninja oluşturucusunu kullanırken - v geçirme komut satırları çıkış Ninja zorlar.


### <a name="ctest-command-arguments"></a>CTest komut bağımsız değişkenleri

Karşılık gelen**ctestCommandArgs**: testler çalıştırıldığında Ctest'e geçirilecek ek anahtarları belirtir.

## <a name="general-settings-for-remote-builds"></a>Uzak derlemeler için genel ayarları

Uzak derlemeleri kullanan yapılandırmalar için Linux gibi aşağıdaki ayarları da kullanılabilir:

### <a name="rsync-command-arguments"></a>rsync komut bağımsız değişkenleri

Rsync metoduna geçirilecek herhangi bir komut bağımsız değişkenleri sağlayın. 

## <a name="cmake-variables-and-cache"></a>CMake değişkenleri ve önbellek

Bu ayarlar CMake değişkenleri ayarlamak ve bunları CMakeSettings.json dosyanızdaki kaydetmenize olanak sağlar. Bunlar, oluşturma zamanında Cmake'e geçirilen ve hangi değerleri CMakeLists.txt dosyasına olabilir geçersiz kılar. Bu bölümde CMakeGUI düzenlemek kullanılabilir tüm CMake değişkenlerinin bir listesini görüntülemek için kullanıyor olabileceğiniz aynı şekilde kullanabilirsiniz. Tıklayın **kaydedin ve önbellek Oluştur** düzenlemek kullanılabilir tüm CMake değişkenlerinin bir listesini görüntülemek için Gelişmiş değişkenleri (başına CMakeGUI) dahil olmak üzere düğme. Listenin değişkenleri adına göre filtre uygulayabilirsiniz. 

Karşılık gelen **değişkenleri**: bir ad-değer çifti olarak geçirilen CMake değişkenlerinin içeren **-D** *_adı_ =  _değer_* CMake için. CMake projesi derleme Yönergeleriniz eklenmesi hiçbir değişkene doğrudan CMake önbellek dosyası belirtirseniz, bunları burada yerine eklemeniz önerilir.

## <a name="advanced-settings"></a>Gelişmiş ayarlar

### <a name="cmake-generator"></a>CMake Oluşturucu

Karşılık gelen **Oluşturucu**: eşler için CMake **- G** geçin ve kullanılacak Oluşturucu belirtir. Bu özellik, bir makro ayrıca kullanılabilir `${generator}`, diğer özellik değerlerini oluştururken. Visual Studio şu anda aşağıdaki CMake oluşturucuları destekler:

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
  
  Ninja, esneklik ve işlevi yerine hızlı derleme hızı için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projelerini Ninja kullanarak doğru şekilde derlenmesi olabilir. Bu meydana gelirse, bunun yerine Visual Studio projesi oluşturmak için CMake bildirebilirsiniz.

### <a name="intellisense-mode"></a>IntelliSense modu

Doğru IntelliSense ve projeniz için uygun değere ayarlayın.

### <a name="install-directory"></a>Yükleme dizini

CMake hedefleri yapıların yükleyen dizin.

### <a name="cmake-executable"></a>CMake çalıştırılabilir

Dosya adı ve uzantısıyla birlikte CMake yürütülebilir dosyanın tam yolu. Uzak derlemeler için uzak makinede CMake konumu belirtin.

Uzak derlemeleri kullanan yapılandırmalar için Linux gibi aşağıdaki ayarları da kullanılabilir:

### <a name="remote-cmakeliststxt-root"></a>Uzak CMakeLists.txt kök

Uzak makinede kök CMakeLists.txt dosyasını içeren dizin.

### <a name="remote-install-root"></a>Uzaktan Yükleme kök

Uzak makinede CMake hedefleri yükleyen dizin.

### <a name="remote-copy-sources"></a>Uzaktan Kopyala kaynakları

Kaynak dosyalar uzak makineye kopyalanıp kopyalanmayacağını belirtir ve, rsync veya sftp kullanılıp kullanılmayacağını belirlemenize olanak tanır. 

## <a name="directly-edit-cmakesettingsjson"></a>Doğrudan CMakeSettings.json Düzenle

Doğrudan düzenleyebilirsiniz `CMakeSettings.json` özel yapılandırmaları oluşturmak için. **Ayarları Düzenleyicisi** sahip bir **Düzenle JSON** dosyasını düzenleme için açar sağ üst köşedeki düğmesi. 

Aşağıdaki örnek, bir başlangıç noktası olarak kullanabileceğiniz bir örnek yapılandırması gösterilmektedir:

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

JSON IntelliSense düzenlemenize yardımcı olan `CMakeSettings.json` dosyası:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

JSON düzenleyicisini ayrıca uyumsuz ayarları seçtiğinizde bilgilendirecektir.

Her dosyanın özellikler hakkında daha fazla bilgi için bkz. [CMakeSettings.json şema başvurusu](cmakesettings-reference.md).

::: moniker-end

::: moniker range="<=vs-2017"

Visual Studio 2017 CMake.exe belirtilen proje için CMake önbelleği oluşturmak için nasıl çağrılan tanımlayan çeşitli CMake yapılandırmaları sağlar. Yeni bir yapılandırma eklemek için araç çubuğundaki açılan Yapılandırması'nı tıklatın ve seçin **yapılandırmaları yönetme**:

   ![CMake yapılandırmaları yönetme](media/cmake-manage-configurations.png)

Önceden tanımlanmış yapılandırmaları listesinden seçim yapabilirsiniz:

   ![Önceden tanımlanmış CMake yapılandırmaları](media/cmake-configurations.png)

İlk kez bir yapılandırma seçin, Visual Studio oluşturur bir `CMakeSettings.json` , projenin kök klasöründeki dosya. Bu dosya CMake önbellek dosyası, örneğin sonra yeniden oluşturmak için kullanılan bir **temiz** işlemi. 

Ek bir yapılandırma eklemek için sağ tıklayın `CMakeSettings.json` ve **Yapılandırması Ekle**. 

   ![CMake ekleme Yapılandırması](media/cmake-add-configuration.png "CMake Yapılandırması Ekle")

Kullanarak dosyayı düzenleyebilirsiniz **CMake ayarları Düzenleyicisi**. Sağ tıklayın `CMakeSettings.json` içinde **Çözüm Gezgini** ve **CMake ayarlarını Düzenle**. Ya da seçin **yapılandırmaları yönetme** Düzenleyicisi penceresinin üst kısmındaki açılan yapılandırmasından. 

Doğrudan düzenleyebilirsiniz `CMakeSettings.json` aşağıdaki örnekte özel yapılandırmaları oluşturmak için başlangıç noktası olarak kullanabileceğiniz bir örnek yapılandırması gösterilmektedir:

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

JSON IntelliSense düzenlemenize yardımcı olan `CMakeSettings.json` dosyası:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Her dosyanın özellikler hakkında daha fazla bilgi için bkz. [CMakeSettings.json şema başvurusu](cmakesettings-reference.md).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>
