---
title: Visual Studio'da bir Linux CMake projesi oluşturun ve yapılandırıyor
description: Visual Studio'da bir Linux CMake projesi oluşturma, yapılandırma, düzenlemesi ve derlemesi
ms.date: 10/04/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 63c1f7953682e4d491660a18bedfa3d0ca4305ae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364382"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Linux CMake projesi oluşturma ve yapılandırma

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019'da yeni bir Linux CMake projesi oluşturmak için:

1. Visual **Studio'da Dosya > Yeni Proje'yi** seçin veya **Ctrl + Shift + N**tuşuna basın.
1. **Dili** **C++** olarak ayarlayın ve "CMake" aramasını yapın. Sonra **İleri'yi**seçin. **Ad** ve **Konum**girin ve **Oluştur'u**seçin.

Visual Studio, yalnızca çalıştırılabilir adı ve gerekli minimum CMake sürümü ile en az CMakeLists.txt dosyası oluşturur. Bu dosyayı istediğiniz gibi el ile edinebilirsiniz; Visual Studio asla değişikliklerinizin üzerine yazmaz. **Solution Explorer'daki** kök CMakeLists.txt dosyasına sağ tıklayarak ve **proje için CMake ayarlarını**seçerek CMake komut satırı bağımsız değişkenlerini ve ortam değişkenlerini belirtebilirsiniz. Hata ayıklama seçeneklerini belirtmek için proje düğümüne sağ tıklayın ve **Hata Ayıklama ve başlatma ayarlarını**seçin.

::: moniker-end

Varolan bir CMake projesini içeren bir klasörü açtığınızda, Visual Studio IntelliSense'i yapılandırmak için CMake önbelleğindeki değişkenleri kullanır ve otomatik olarak oluşturur. Yerel yapılandırma ve hata ayıklama ayarları, isteğe bağlı olarak Visual Studio kullanan diğer kişilerle paylaşılabilen JSON dosyalarında depolanır.

Visual Studio CMakeLists.txt dosyalarını değiştirmez, böylece aynı projede çalışan diğer kişiler zaten kullandıkları araçları kullanmaya devam edebilirler. Visual Studio, cmakelists.txt veya bazı durumlarda CMakeSettings.json için edinimi kaydettiğinizde önbelleği yeniden oluşturur. Ancak **Varolan Önbellek** yapılandırması kullanıyorsanız, Visual Studio önbelleği değiştirmez.

Visual Studio'da CMake desteği hakkında genel bilgi için [Visual Studio'daki CMake projelerine](../build/cmake-projects-in-visual-studio.md)bakın. Burada devam etmeden önce ilk okuyun.

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, CMake bileşeni de dahil olmak üzere C++ iş yükünün yüklü olduğu **Linux geliştirmesini** olduğundan emin olun. Bkz. [Visual Studio'da C++ Linux iş yükünü yükleyin.](download-install-and-setup-the-linux-development-workload.md)

Linux sisteminde, aşağıdakilerin yüklü olduğundan emin olun:

- Gcc
- Gdb
- Rsync
- Zip
- ninja yapı

::: moniker range="vs-2019"

CMake projeleri için Linux desteği, CMake'nin yeni bir sürümünün hedef makineye yüklenmesini gerektirir. Genellikle, bir dağıtımVarsayılan paket yöneticisi tarafından sunulan sürüm Visual Studio tarafından gerekli olan tüm özellikleri desteklemek için yeterince yeni değildir. Visual Studio 2019, CMake'nin yeni bir sürümünün Linux sistemine yüklenip yüklenmediğini algılar. Hiçbiri bulunmazsa, Visual Studio editör bölmesinin üst kısmında sizin için yüklemek için teklif [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)bir bilgi çubuğu gösterir.

Visual Studio'daki CMake desteği, CMake 3.8'de tanıtılan sunucu modu desteğini gerektirir. Visual Studio 2019'da sürüm 3.14 veya sonraki sürüm önerilir.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio'daki CMake desteği, CMake 3.8'de tanıtılan sunucu modu desteğini gerektirir. Microsoft tarafından sağlanan bir CMake varyantı için, [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)önceden oluşturulmuş en son ikilileri .'dan indirin.

İkili' ye `~/.vs/cmake`' İkili leri dağıttıktan sonra, projeniz otomatik olarak yeniden yenilenir. `cmakeExecutable` Alan tarafından belirtilen CMake `CMakeSettings.json` geçersizse (yok veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş ikililer varsa Visual Studio'nun önceden oluşturulmuş ikilileri yok sayacağını `cmakeExecutable` ve kullanacağını unutmayın.

:::moniker-end

## <a name="open-a-folder"></a>Klasör açma

Başlamak için ana menüden **Dosya** > **Aç** > **Klasörünü** seçin veya komut satırına başka bir yazı yazın. `devenv.exe <foldername>` Açtığınız klasörde kaynak kodunuzla birlikte bir CMakeLists.txt dosyası olmalıdır.
Aşağıdaki örnek basit bir CMakeLists.txt dosyasını ve .cpp dosyasını gösterir:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists.txt:

```cmd
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Bir Linux hedefi seçin

Klasörü açar açmaz Visual Studio CMakeLists.txt dosyasını ayrıştırır ve **x86-Hata**Ayıklama'nın Windows hedefini belirtir. Uzak bir Linux sistemini hedeflemek için proje ayarlarını **Linux-Hata Ayıklama** veya Linux Sürümü olarak **değiştirin.** (Aşağıdaki [Linux için CMake ayarlarını yapılandırın.)](#configure_cmake_linux)

::: moniker range="vs-2019"

Linux için Windows Alt Sistemi'ni hedeflemek için, ana araç çubuğundaki yapılandırma açılır penceresinde **ki Yapılandırmaları Yönet'e** tıklayın. Ardından **Yapılandırma Ekle** düğmesine basın ve GCC kullanıyorsanız **WSL-Hata Ayıklama** veya **WSL-Release'i** veya Clang/LLVM araç setini kullanıyorsanız Clang türevlerini seçin.

**Visual Studio 2019 sürüm 16.1** WSL'yi hedeflerken, Linux'taki derleyici kaynak dosyalarınızın bulunduğu Windows dosya sistemine doğrudan erişimi olduğundan kaynak veya üstbilgi kopyalamasına gerek yoktur. (Windows sürüm 1903 ve sonrası, Windows uygulamaları aynı şekilde doğrudan Linux üstbilgi dosyalarına erişebilirsiniz, ancak Visual Studio henüz bu özellikten yararlanamaz).

::: moniker-end

Uzak hedefler için Visual Studio varsayılan olarak **Araçlar** > **Seçenekleri** > **Çapraz Platform** > **Bağlantı Yöneticisi**altında listedeki ilk uzak sistemi seçer. Uzak bağlantı bulunmazsa, bir bağlantı oluşturmanız istenir. Daha fazla bilgi için, [uzak Linux bilgisayarınıza bağlan'a](connect-to-your-remote-linux-computer.md)bakın.

Uzak bir Linux hedefi belirtirseniz, kaynağınız uzak sisteme kopyalanır.

Bir hedef seçtikten sonra CMake, projeniz için CMake önbelleğini oluşturmak için Linux sisteminde otomatik olarak çalışır.

![Linux üzerinde CMake önbelleği oluşturun](media/cmake-linux-1.png "Linux üzerinde CMake önbelleği oluşturun")

Uzak Linux sistemlerindeki başlıklar için IntelliSense desteği sağlamak için Visual Studio bunları Linux makinesinden yerel Windows makinenizdeki bir dizine otomatik olarak kopyalar. Daha fazla bilgi [için uzak üstbilgiler için IntelliSense'e](configure-a-linux-project.md#remote_intellisense)bakın.

## <a name="debug-the-cmake-project"></a><a name="debug_cmake_project"></a>CMake projesini hata ayıklama

Belirtilen hata ayıklama hedef sisteminde kodunuzu hata ayıklamak için bir kesme noktası ayarlayın, proje ayarı yanındaki araç çubuğu menüsünde başlangıç öğesi olarak CMake hedefini seçin ve araç çubuğunda **Başlat&#x23f5;** seçin veya F5 tuşuna basın.

Programınızın komut satırı bağımsız değişkenlerini özelleştirmek **için, Çözüm Gezgini'nin** üst kısmındaki **Hedefleri Değiştir** düğmesine basın ve ardından **Hedef Görünümü'ni**seçin. Ardından hedefe sağ tıklayın ve **Hata Ayıklama ve Başlatma Ayarları'nı**seçin. Bu, programınız hakkında bilgi içeren bir launch.vs.json yapılandırma dosyanı açar veya oluşturur. Kaynak dosyaların konumunu belirtmek için, bu örnekte gösterildiği gibi dosyaya bir **sourceFileMap** özelliği ekleyin:

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

Ek bağımsız değişkenler belirtmek `args` için bunları JSON dizisine ekleyin. Daha fazla bilgi [için C++ için Açık Klasör projelerine](../build/open-folder-projects-cpp.md) bakın ve [CMake hata ayıklama oturumlarını yapılandırın.](../build/configure-cmake-debugging-sessions.md)

## <a name="configure-cmake-settings-for-linux"></a><a name="configure_cmake_linux"></a>Linux için CMake ayarlarını yapılandırın

Bir CMake Linux projesindeki Bir CMakeSettings.json dosyası, [CMake ayarlarını özelleştirmede](../build/customize-cmake-settings.md)listelenen tüm özellikleri ve uzak Linux makinesindeki yapı ayarlarını kontrol eden ek özellikleri belirtebilir.

::: moniker range="vs-2019"

Visual Studio 2019'daki varsayılan CMake ayarlarını ana araç çubuğundan değiştirmek için **Configuration** açılan ını açın ve **Yapılandırmaları Yönet'i**seçin.

![CMake Yapılandırmaları Yönet](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırmaları açılır")

Bu, kök proje klasörünüzdeki dosyayı `CMakeSettings.json` yeniden düzenleyen **CMake Ayarlar Düzenleyicisi'ni** getirir. Ayrıca, düzenleyicideki **JSON'u Edit** düğmesini tıklatarak dosyayı doğrudan açabilirsiniz. Daha fazla bilgi için [CMake Ayarlarını Özelleştir'e](../build/customize-cmake-settings.md)bakın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de varsayılan CMake ayarlarını değiştirmek için **CMake | CMake Ayarlarını Değiştir | Ana menüden CMakeLists.txt** veya **Solution Explorer'da** CMakeSettings.txt'ye sağ tıklayın ve **CMake Ayarlarını Değiştir'i**seçin. Visual Studio daha sonra `CMakeSettings.json` kök proje klasörünüzde yeni bir dosya oluşturur. **CMake Ayarları** düzenleyicisini kullanarak dosyayı açabilir veya dosyayı doğrudan değiştirebilirsiniz. Daha fazla bilgi için [CMake ayarlarını özelleştir'e](../build/customize-cmake-settings.md)bakın.

Aşağıdaki örnek, önceki kod örneğine göre Visual Studio 2017'de (ve Visual Studio 2019 sürüm 16.0)'da Linux Hata Ayıklama için varsayılan yapılandırmayı gösterir:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteInstallRoot": "/var/tmp/build/${workspaceHash}/install/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "remoteCopySourcesMethod": "rsync",
      "remoteCopySourcesExclusionList": [".vs", ".git"],
      "rsyncCommandArgs" : "-t --delete --delete-excluded",
      "remoteCopyBuildOutput" : "false",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 sürüm 16.1 ve sonrası varsayılan Linux-Hata Ayıklama yapılandırması burada gösterildiği gibi:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "configurationType": "Debug",
      "cmakeExecutable": "/usr/bin/cmake",
      "remoteCopySourcesExclusionList": [ ".vs", ".git", "out" ],
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux_x64" ],
      "remoteMachineName": "${defaultRemoteMachineName}",
      "remoteCMakeListsRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/src",
      "remoteBuildRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/build/${name}",
      "remoteInstallRoot": "$HOME/.vs/${projectDirName}/${workspaceHash}/out/install/${name}",
      "remoteCopySources": true,
      "rsyncCommandArgs": "-t --delete --delete-excluded",
      "remoteCopyBuildOutput": false,
      "remoteCopySourcesMethod": "rsync",
      "addressSanitizerRuntimeFlags": "detect_leaks=0",
      "variables": []
    }
  ]
}
```

::: moniker-end

Bu ayarlar hakkında daha fazla bilgi için [CMakeSettings.json referansına](../build/cmakesettings-reference.md)bakın.

## <a name="optional-settings"></a>İsteğe Bağlı Ayarlar

Daha fazla denetim için aşağıdaki isteğe bağlı ayarları kullanabilirsiniz:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Bu seçenekler, Linux sisteminde komutları oluşturmadan önce ve sonra ve CMake oluşturmadan önce çalıştırmanızı sağlar. Değerler uzak sistemde geçerli olan herhangi bir komut olabilir. Çıkış Visual Studio'ya geri iletilir.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](../build/working-with-project-properties.md)<br/>
[Visual Studio'da CMake Projeleri](../build/cmake-projects-in-visual-studio.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)<br/>
[CMake ayarlarını özelleştirin](../build/customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)<br/>
