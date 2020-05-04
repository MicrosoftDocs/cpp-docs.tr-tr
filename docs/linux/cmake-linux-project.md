---
title: Visual Studio 'da Linux CMake projesi oluşturma ve yapılandırma
description: Visual Studio 'da bir Linux CMake projesi oluşturma, yapılandırma, düzenleme ve derleme
ms.date: 05/03/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: c12e32801c992f6ba3675327b9ae537890202a4c
ms.sourcegitcommit: 8a01ae145bc65f5bc90d6e47b4a1bdf47b073ee7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2020
ms.locfileid: "82765766"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Linux CMake projesi oluşturma ve yapılandırma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, CMake bileşeni dahil olmak üzere C++ iş yükünün yüklü **olduğu Linux geliştirdiğinizden** emin olun. Bkz. [Visual Studio 'Da C++ Linux iş yükünü yüklemeyi](download-install-and-setup-the-linux-development-workload.md).

Linux sisteminde aşağıdakilerin yüklü olduğundan emin olun:

- GCC
- GDB
- rsync
- zip
- dokja-derleme

::: moniker-end

::: moniker range="vs-2019"

CMake projeleri için Linux desteği hedef makinenin en son CMake sürümüne sahip olmasını gerektirir. Genellikle, bir dağıtımın varsayılan paket yöneticisi tarafından sunulan sürüm, Visual Studio için gereken tüm özellikleri desteklemeye yetecek kadar güncel değildir. Visual Studio 2019, Linux sisteminde bir CMake son sürümünün yüklü olup olmadığını algılar. Hiçbiri bulunmazsa, Visual Studio, düzenleyici bölmesinin üst kısmında bir bilgi çubuğu gösterir. Sizin için CMake 'i [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)yüklemenizi sağlar.

Visual Studio 'da CMake desteği, CMake 3,8 ' de tanıtılan sunucu modu desteğini gerektirir. Visual Studio 2019 ' de, sürüm 3,14 veya üzeri önerilir.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 'da CMake desteği, CMake 3,8 ' de tanıtılan sunucu modu desteğini gerektirir. Microsoft tarafından sağlanmış bir CMake değişkeni için, en son önceden oluşturulmuş ikilileri adresinden [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)indirin.

İkililer ' de `~/.vs/cmake`yüklenir. İkili dosyaları dağıttıktan sonra projeniz otomatik olarak yeniden oluşturur. `cmakeExecutable` *Cmakesettings. JSON* Içindeki alan tarafından belirtilen CMake geçersiz (yok veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş Ikili dosyalar varsa, Visual Studio önceden oluşturulmuş ikilileri yoksayar `cmakeExecutable` ve kullanır.

:::moniker-end

::: moniker range="vs-2019"

## <a name="create-a-new-linux-cmake-project"></a>Yeni bir Linux CMake projesi oluştur

Visual Studio 2019 'de yeni bir Linux CMake projesi oluşturmak için:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Dili** **C++** olarak ayarlayın ve "CMake" araması yapın. Ardından **İleri**' yi seçin. Bir **ad** ve **konum**girin ve **Oluştur**' u seçin.

Visual Studio yalnızca yürütülebilir dosya adı ve gereken en düşük CMake sürümü ile en az bir *Cmakelists. txt* dosyası oluşturur. Bu dosyayı dilediğiniz gibi el ile düzenleyebilirsiniz; Visual Studio, değişikliklerinizin üzerine hiçbir değişiklik yazmaz. CMake komut satırı bağımsız değişkenlerini ve ortam değişkenlerini bu dosyada belirtebilirsiniz. **Çözüm Gezgini** kök *cmakelists. txt* dosyasına sağ tıklayın ve **proje için CMake ayarları**' nı seçin. Hata ayıklama seçeneklerini belirtmek için, proje düğümüne sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="open-a-cmake-project-folder"></a>CMake proje klasörü aç

Var olan bir CMake projesi içeren bir klasörü açtığınızda, Visual Studio IntelliSense ve yapıları otomatik olarak yapılandırmak için CMake önbelleğindeki değişkenleri kullanır. Yerel yapılandırma ve hata ayıklama ayarları JSON dosyalarında depolanır. İsteğe bağlı olarak, bu dosyaları Visual Studio kullanan diğer kullanıcılarla paylaşabilirsiniz.

Visual Studio, *Cmakelists. txt* dosyalarını değiştirmez. Aynı proje üzerinde çalışan başkalarının mevcut araçlarını kullanmaya devam edebilmesi için tek başına kalır. *Cmakelists. txt* ' ye yapılan düzenlemeleri kaydettiğinizde veya bazı durumlarda *cmakesettings. JSON*için Visual Studio önbelleği yeniden üretin. Ancak **var olan bir önbellek** yapılandırması kullanıyorsanız, Visual Studio önbelleği değiştirmez.

Visual Studio 'da CMake desteği hakkında genel bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md). Devam etmeden önce bunu okuyun.

Başlamak için, ana menüden **Dosya** > **Aç** > **klasörünü** seçin veya bir [Geliştirici komut istemi](../build/building-on-the-command-line.md) penceresinde `devenv.exe <foldername>` yazın. Açtığınız klasörün, kaynak kodunuzla birlikte bu dosyada bir *Cmakelists. txt* dosyası olması gerekir.

Aşağıdaki örnekte bir basit *Cmakelists. txt* dosyası ve. cpp dosyası gösterilmektedir:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*Cmakelists. txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux hedefi seçin

Klasörü açtığınızda, Visual Studio *Cmakelists. txt* dosyasını ayrıştırır ve **x86-Debug**' ın bir Windows hedefini belirtir. Uzak bir Linux sistemini hedeflemek için, proje ayarlarını **Linux-Debug** veya **Linux-Release**olarak değiştirin. (Bkz. [Linux Için CMake ayarlarını yapılandırma](#configure_cmake_linux) .)

::: moniker-end

::: moniker range="vs-2019"

Linux için Windows alt sistemini hedeflemek için ana araç çubuğunda yapılandırma açılan menüsünde **yapılandırmaları Yönet** ' e tıklayın. Ardından, **yapılandırma Ekle** düğmesine basın ve GCC kullanılıyorsa **WSL-Debug** veya **WSL-Release** ' i seçin. Clang/LLVM araç takımını kullanıyorsanız Clang türevlerini kullanın.

**Visual Studio 2019 sürüm 16,1** WSL 'yi hedeflerken, kaynak veya üst bilgi kopyalama gerekli değildir. Bunun nedeni, Linux üzerinde derleyicinin Windows dosya sistemindeki kaynak dosyalarınıza doğrudan erişmesini sağlar. (Windows 10 sürüm 1903 ve üzeri sürümlerde, Windows uygulamaları da doğrudan Linux üstbilgi dosyalarına erişebilir. Visual Studio henüz bu özellikten yararlanamaz.)

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio, uzak hedefler için varsayılan olarak **Araçlar** > **Seçenekler** > **çapraz platform** > **Bağlantı Yöneticisi** altındaki listede bulunan ilk uzak sistemi seçer. Uzak bağlantı bulunamazsa, bir tane oluşturmanız istenir. Daha fazla bilgi için bkz. [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

Uzak bir Linux hedefi belirtirseniz, kaynağınız uzak sisteme kopyalanır.

Bir hedef seçtikten sonra CMake, projenizin CMake önbelleğini oluşturmak için Linux sisteminde otomatik olarak çalışır.

![Linux 'ta CMake önbelleği oluşturma](media/cmake-linux-1.png "Linux 'ta CMake önbelleğini oluşturma")

Uzak Linux sistemlerindeki üst bilgiler için IntelliSense desteği sağlamak üzere, Visual Studio bunları otomatik olarak Linux makinesinden yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için bkz. [uzak üstbilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-cmake-project"></a><a name="debug_cmake_project"></a>CMake projesinde hata ayıklama

Belirtilen hedef sistemde kodunuzun hatalarını ayıklamak için bir kesme noktası ayarlayın. Proje ayarının yanındaki araç çubuğu menüsündeki başlangıç öğesi olarak CMake hedefini seçin. Sonra araç çubuğunda **&#x23f5; Başlat** ' ı seçin veya **F5**tuşuna basın.

Programınızın komut satırı bağımsız değişkenlerini özelleştirmek için **Çözüm Gezgini** üst kısmındaki **hedefleri Değiştir** düğmesine basın ve ardından **hedefler görünümü**' ne tıklayın. Ardından, hedefe sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. Bu komut, programınız hakkında bilgi içeren bir *Launch. vs. JSON* yapılandırma dosyası açar veya oluşturur. Kaynak dosyalarının konumunu belirtmek için, aşağıdaki örnekte gösterildiği gibi, dosyasına bir **Sourcefilemap** özelliği ekleyin:

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

Ek bağımsız değişkenler belirtmek için bunları `args` JSON dizisine ekleyin. Daha fazla bilgi için bkz. [C++ Için klasör projelerini açma](../build/open-folder-projects-cpp.md) ve [CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a><a name="configure_cmake_linux"></a>Linux için CMake ayarlarını yapılandırma

CMake Linux projesindeki bir *Cmakesettings. JSON* dosyası, [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)bölümünde listelenen tüm özellikleri ve uzak Linux makinesindeki derleme ayarlarını denetleyen ek özellikleri belirtebilir.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 ' de varsayılan CMake ayarlarını değiştirmek için, ana araç çubuğundan **yapılandırma** açılan listesini açın ve **yapılandırmaları Yönet**' i seçin.

![CMake yönetme yapılandırması](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırma açılır")

Bu komut, kök proje klasörünüzdeki *Cmakesettings. JSON* dosyasını düzenlemek Için kullanabileceğiniz **CMake ayarları düzenleyicisini**getirir. Ayrıca, düzenleyicide **JSON Düzenle** düğmesine tıklayarak dosyayı doğrudan açabilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

Visual Studio 2019 sürüm 16,1 ve sonraki sürümlerde varsayılan Linux-Debug yapılandırması burada gösterilmektedir:

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

::: moniker range="vs-2017"

Visual Studio 2017 ' de varsayılan CMake ayarlarını değiştirmek için, ana menüden **CMake** > **değişiklik CMake ayarları** > **cmakelists. txt** ' yi seçin. Ya da **Çözüm Gezgini** Içinde *cmakesettings. txt* dosyasına sağ tıklayıp **CMake ayarlarını değiştir**' i seçin. Daha sonra Visual Studio, kök proje klasörünüzde yeni bir *Cmakesettings. JSON* dosyası oluşturur. **CMake ayarları** düzenleyicisini kullanarak dosyayı açabilir veya dosyayı doğrudan değiştirebilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

Aşağıdaki örnek, önceki kod örneğine göre Visual Studio 2017 (ve Visual Studio 2019 sürüm 16,0) içindeki Linux-Debug için varsayılan yapılandırmayı gösterir:

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

::: moniker range=">=vs-2017"

Bu ayarlar hakkında daha fazla bilgi için bkz. [Cmakesettings. JSON başvurusu](../build/cmakesettings-reference.md).

## <a name="optional-settings"></a>İsteğe bağlı ayarlar

Daha fazla denetim için aşağıdaki isteğe bağlı ayarları kullanabilirsiniz:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Bu seçenekler, Linux sisteminde oluşturmadan önce ve sonra ve CMake oluşturmadan önce komutları çalıştırmanızı sağlar. Değerler, uzak sistemde geçerli olan herhangi bir komut olabilir. Çıktı, Visual Studio 'ya geri gönderilir.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](../build/working-with-project-properties.md)<br/>
[Visual Studio 'da CMake projeleri](../build/cmake-projects-in-visual-studio.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)<br/>
[CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
