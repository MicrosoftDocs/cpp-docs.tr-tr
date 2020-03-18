---
title: Visual Studio 'da Linux CMake projesi oluşturma ve yapılandırma
description: Visual Studio 'da bir Linux CMake projesi oluşturma, yapılandırma, düzenleme ve derleme
ms.date: 10/04/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: a0b98e1d0e9ca5e68f5fd12c458fe29b9835b65c
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446859"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Linux CMake projesi oluşturma ve yapılandırma

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 'de yeni bir Linux CMake projesi oluşturmak için:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Dili** olarak **C++** ayarlayın ve "CMake" araması yapın. Ardından **İleri**' yi seçin. Bir **ad** ve **konum**girin ve **Oluştur**' u seçin.

Visual Studio yalnızca yürütülebilir dosya adı ve gereken en düşük CMake sürümü ile en az bir CMakeLists. txt dosyası oluşturur. Bu dosyayı dilediğiniz gibi el ile düzenleyebilirsiniz; Visual Studio, değişikliklerinizin üzerine hiçbir değişiklik yazmaz. CMake komut satırı bağımsız değişkenlerini ve ortam değişkenlerini **Çözüm Gezgini** ' de kök CMakeLists. txt dosyasına sağ tıklayıp, **proje için CMake ayarları**' nı seçerek belirtebilirsiniz. Hata ayıklama seçeneklerini belirtmek için, proje düğümüne sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin.

::: moniker-end

Var olan bir CMake projesi içeren bir klasörü açtığınızda, Visual Studio IntelliSense ve derlemeleri otomatik olarak yapılandırmak için CMake önbelleğindeki değişkenleri kullanır. Yerel yapılandırma ve hata ayıklama ayarları, isteğe bağlı olarak, Visual Studio kullanan diğer kullanıcılarla paylaşılabilen JSON dosyalarında depolanır.

Visual Studio, CMakeLists. txt dosyalarını değiştirmez, böylece aynı proje üzerinde çalışan diğerleri zaten kullanmakta oldukları araçları kullanmaya devam edebilir. CMakeLists. txt ' ye yapılan düzenlemeleri kaydettiğinizde veya bazı durumlarda CMakeSettings. JSON için Visual Studio önbelleği yeniden üretin. Ancak, **var olan bir önbellek** yapılandırması kullanıyorsanız, Visual Studio önbelleği değiştirmez.

Visual Studio 'da CMake desteği hakkında genel bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md). Devam etmeden önce bunu okuyun.

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, CMake bileşeni de dahil olmak üzere iş yükünün yüklü **olduğu C++ Linux geliştirdiğinizden** emin olun. Bkz. [Visual C++ Studio 'da Linux iş yükünü yüklemeyi](download-install-and-setup-the-linux-development-workload.md). 

Linux sisteminde aşağıdakilerin yüklü olduğundan emin olun: 

- GCC
- GDB
- rsync
- zip 

::: moniker range="vs-2019"

CMake projeleri için Linux desteği, hedef makinede CMake 'in son sürümünün yüklü olmasını gerektirir. Genellikle, bir dağıtımın varsayılan paket yöneticisi tarafından sunulan sürüm, Visual Studio için gereken tüm özellikleri desteklemeye yetecek kadar güncel değildir. Visual Studio 2019, Linux sisteminde bir CMake son sürümünün yüklü olup olmadığını algılar. Hiçbiri bulunmazsa, Visual Studio düzenleyici bölmesinin üst kısmında [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases), sizin için yüklemenizi sağlayan bir bilgi çubuğu gösterir.

Visual Studio 'da CMake desteği, CMake 3,8 ' de tanıtılan sunucu modu desteğini gerektirir. Visual Studio 2019 ' de, sürüm 3,14 veya üzeri önerilir.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 'da CMake desteği, CMake 3,8 ' de tanıtılan sunucu modu desteğini gerektirir. Microsoft tarafından sağlanmış bir CMake değişkeni için [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases)adresinden en son önceden oluşturulmuş ikilileri indirin.

İkililer `~/.vs/cmake`yüklenecek. İkili dosyaları dağıttıktan sonra, projeniz otomatik olarak yeniden oluşturulur. `CMakeSettings.json` `cmakeExecutable` alanının belirttiği CMake geçersiz olduğunu (yoksa veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş ikili dosyaların mevcut olduğunu, Visual Studio 'Nun `cmakeExecutable` yoksayyacağını ve önceden oluşturulmuş ikililerin kullanılacağını unutmayın.

:::moniker-end

## <a name="open-a-folder"></a>Bir klasörü açın

Başlamak için, ana menüden **dosya** > **Aç** > **klasörünü** seçin veya komut satırına `devenv.exe <foldername>` yazın. Açtığınız klasörün, kaynak kodunuzla birlikte bu dosyada bir CMakeLists. txt dosyası olması gerekir.
Aşağıdaki örnekte bir basit CMakeLists. txt dosyası ve. cpp dosyası gösterilmektedir:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

CMakeLists. txt:

```cmd
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux hedefi seçin

Klasörü açtığınızda, Visual Studio CMakeLists. txt dosyasını ayrıştırır ve **x86-Debug**' ın bir Windows hedefini belirtir. Uzak bir Linux sistemini hedeflemek için, proje ayarlarını **Linux-Debug** veya **Linux-Release**olarak değiştirin. (Bkz. [Linux Için CMake ayarlarını yapılandırma](#configure_cmake_linux) .)

::: moniker range="vs-2019"

Linux için Windows alt sistemini hedeflemek için ana araç çubuğundaki yapılandırma açılan kutusunda bulunan **yapılandırmaları Yönet** ' e tıklayın. Ardından **yapılandırma Ekle** düğmesine basın ve CLANG/LLVM araç takımını kullanıyorsanız, GCC veya Clang türevlerini kullanıyorsanız **WSL-Debug** veya **WSL-Release** ' i seçin. 

**Visual Studio 2019 sürüm 16,1** WSL 'yi hedeflerken, Linux üzerindeki derleyicinin kaynak dosyalarınızın bulunduğu Windows dosya sistemine doğrudan erişimi olduğundan, kaynak veya üst bilgilerin kopyalanması gerekmez. (Windows sürüm 1903 ve üzeri sürümlerde, Windows uygulamaları Linux üst bilgi dosyalarına doğrudan erişebilir, ancak Visual Studio henüz bu özellikten yararlanamaz).

::: moniker-end

Uzak hedefler için, Visual Studio varsayılan olarak **araçlar** >  > **Seçenekler** altındaki listedeki Ilk uzak sistemi, **platformlar arası** > **Bağlantı Yöneticisi**' ni seçer. Uzak bağlantı bulunamazsa, bir tane oluşturmanız istenir. Daha fazla bilgi için bkz. [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

Uzak bir Linux hedefi belirtirseniz, kaynağınız uzak sisteme kopyalanır.

Bir hedef seçtikten sonra CMake, projenizin CMake önbelleğini oluşturmak için Linux sisteminde otomatik olarak çalışır. 

![Linux 'ta CMake önbelleği oluşturma](media/cmake-linux-1.png "Linux 'ta CMake önbelleğini oluşturma")

Uzak Linux sistemlerindeki üst bilgiler için IntelliSense desteği sağlamak üzere, Visual Studio bunları otomatik olarak Linux makinesinden yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için bkz. [uzak üstbilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug_cmake_project"></a>CMake projesinde hata ayıklama

Belirtilen hata ayıklama hedef sisteminde kodunuzun hatalarını ayıklamak için, bir kesme noktası ayarlayın, proje ayarının yanındaki araç çubuğu menüsünde bulunan başlangıç öğesi olarak CMake hedefini seçin ve araç çubuğundan  **&#x23f5; Başlat** ' ı seçin veya F5 tuşuna basın.

Programınızın komut satırı bağımsız değişkenlerini özelleştirmek için **Çözüm Gezgini** üst kısmındaki **hedefleri Değiştir** düğmesine basın ve ardından **hedefler görünümü**' ne tıklayın. Ardından, hedefe sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. Bu, programınız hakkında bilgi içeren bir Launch. vs. JSON yapılandırma dosyası açar veya oluşturur. Kaynak dosyalarının konumunu belirtmek için, aşağıdaki örnekte gösterildiği gibi, dosyasına bir **Sourcefilemap** özelliği ekleyin:

```json
"MIMode": "gdb",
"externalConsole": true,
"sourceFileMap": {
"c/Users/USER/source/repos/CMAKEPROJECTNAME": "C:\\Users\\USER\\source\\repos\\CMAKEPROJECTNAME"
},
"remoteMachineName": "${debugInfo.remoteMachineName}",
```

Ek bağımsız değişkenler belirtmek için, `args` JSON dizisine ekleyin. Daha fazla bilgi için bkz. [klasör C++ projelerini açma](../build/open-folder-projects-cpp.md) ve [CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md).

## <a name="configure_cmake_linux"></a>Linux için CMake ayarlarını yapılandırma

CMake Linux projesindeki bir CMakeSettings. JSON dosyası, [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)bölümünde listelenen tüm özellikleri ve uzak Linux makinesindeki derleme ayarlarını denetleyen ek özellikleri belirtebilir. 

::: moniker range="vs-2019"

Visual Studio 2019 ' de varsayılan CMake ayarlarını değiştirmek için, ana araç çubuğundan **yapılandırma** açılan çubuğunu açın ve **yapılandırmaları Yönet**' i seçin. 

![CMake yönetme yapılandırması](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırma açılır")

Bu, kök proje klasörünüzdeki `CMakeSettings.json` dosyasını düzenlemek için kullanabileceğiniz **CMake ayarları düzenleyicisini** getirir. Ayrıca, düzenleyicide **JSON Düzenle** düğmesine tıklayarak dosyayı doğrudan açabilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017 ' de varsayılan CMake ayarlarını değiştirmek için CMake ' i seçin.  **CMake ayarlarını değiştir | CMakeLists. txt** ana menüden veya **Çözüm Gezgini** ' de cmakesettings. txt öğesine sağ tıklayıp **CMake ayarlarını değiştir**' i seçin. Daha sonra Visual Studio, kök proje klasörünüzde yeni bir `CMakeSettings.json` dosyası oluşturur. **CMake ayarları** düzenleyicisini kullanarak dosyayı açabilir veya dosyayı doğrudan değiştirebilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

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

::: moniker range="vs-2019"

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

Bu ayarlar hakkında daha fazla bilgi için bkz. [Cmakesettings. JSON başvurusu](../build/cmakesettings-reference.md).


## <a name="optional-settings"></a>İsteğe Bağlı Ayarlar

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
[CMake önceden tanımlanmış yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)<br/>
