---
title: Oluşturma ve Visual Studio'da bir Linux CMake projesi yapılandırma
description: Oluşturma, yapılandırma, düzenlemek ve bir Linux CMake projesini Visual Studio'da derleyin
ms.date: 06/12/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: d70ffe593cc014bca40a447a9cdb1c1c96a40e3f
ms.sourcegitcommit: fde637f823494532314790602c2819f889706ff6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/13/2019
ms.locfileid: "67042650"
---
# <a name="create-and-configure-a-linux-cmake-project"></a>Linux CMake projesi oluşturun ve yapılandırın

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio 2019 içinde yeni bir Linux CMake projesi oluşturmak için:

1. Seçin **Dosya > Yeni proje** Visual Studio'da ya da tuşuna **Ctrl + Shift + N**.
1. Ayarlama **dil** için **C++** ve "CMake" arayın. Ardından **sonraki**. Girin bir **adı** ve **konumu**ve **Oluştur**.

Visual Studio yalnızca adıyla yürütülebilir ve gereken en düşük CMake sürümü en az bir CMakeLists.txt dosyası oluşturur. Ancak, istediğiniz bu dosyayı el ile düzenleyebilirsiniz; Visual Studio, hiçbir zaman değişikliklerinizi üzerine yazar. CMakeLists.txt dosyasına sağ tıklayarak CMake komut satırı bağımsız değişkenleri ve ortam değişkenlerini belirtebilirsiniz **Çözüm Gezgini** seçip **CMake proje ayarlarını**. Hata ayıklama seçeneklerini belirtmek için proje düğümüne sağ tıklayın ve seçin **hata ayıklama ve başlatma ayarları**.

::: moniker-end

Mevcut bir CMake projesini içeren bir klasörü açtığınızda Visual Studio CMake IntelliSense yapılandırılacağı ve otomatik olarak oluşturur meta verileri kullanır. Yerel yapılandırma ve hata ayıklama ayarları, Visual Studio kullanan, isteğe bağlı olarak diğer kullanıcılarla paylaşılabilir JSON dosyalarında depolanır. 

Başkalarının aynı proje üzerinde çalışmaya zaten kullandıkları ne olursa olsun araçları kullanmaya devam edebilmeniz için visual Studio CMakeLists.txt dosyaları değiştirmez. Visual Studio düzenlemeleri CMakeLists.txt veya bazı durumlarda için CMakeSettings.json yaptığınızda önbelleği yeniden oluşturun. Ancak kullanıyorsanız bir **mevcut önbellek** yapılandırma ve ardından Visual Studio, önbellek değiştirmez.

Visual Studio'da CMake desteği hakkında genel bilgi için bkz: [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md). Bu burada devam etmeden önce okuyun.

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, sahip olduğunuzdan emin olun **C++ ile Linux geliştirme** CMake bileşen dahil olmak üzere iş yükü yüklenmiş,. Bkz: [Visual Studio'da C++ Linux iş yükünü yükleyin](download-install-and-setup-the-linux-development-workload.md). 

Linux sisteminde aşağıdaki yüklendiğinden emin olun: 

- gcc
- GDB
- rsync
- zip 

::: moniker range="vs-2019"

CMake projeleri için Linux desteği, en güncel sürümünü CMake hedef makinede yüklü olmasını gerektirir. Genellikle, bir dağıtım'ın varsayılan Paket Yöneticisi tarafından sunulan sürümü Visual Studio tarafından gerekli olan tüm özellikleri desteklemek için yeterince yeni değil. Visual Studio 2019 Linux sistemde CMake yeni bir sürümü yüklü olup olmadığını algılar. Bulunamazsa, Visual Studio için yüklemeyi teklif ediyor Düzenleyici bölmesinin üst bir bilgi çubuğu gösterir [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Visual Studio 2019 içinde 3.14 veya sonraki bir sürümü önerilir.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

İkili dosyaların şekilde yüklenecek `~/.vs/cmake`. İkili dosyaları dağıttıktan sonra projeniz otomatik olarak yeniden neden. Tarafından belirtilen CMake unutmayın `cmakeExecutable` alanındaki `CMakeSettings.json` geçersiz (mevcut değil veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş ikili dosyalar mevcut Visual Studio yoksayar `cmakeExecutable` ve önceden oluşturulmuş ikili dosyaları kullanın.

:::moniker-end

## <a name="open-a-folder"></a>Klasör Aç

Başlamak için seçin **dosya** > **açık** > **klasör** ana menü veya başka tür gelen `devenv.exe <foldername>` komut satırında. Açtığınız klasör içindeki CMakeLists.txt dosyasıyla birlikte kullanarak kaynak kodunuz olmalıdır.
Aşağıdaki örnek, bir basit bir CMakeLists.txt dosyası ve .cpp dosyası gösterir:

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

## <a name="choose-a-linux-target"></a>Bir Linux hedef seçin

Klasörü açın hemen sonra Visual Studio CMakeLists.txt dosyasını ayrıştırır ve Windows hedefi belirtir **x86 hata ayıklama**. Uzak Linux sistemi hedeflemek için proje ayarlarını **Linux hata ayıklama** veya **Linux sürüm**. (Bkz [Linux CMake yapılandırma ayarlarını](#configure_cmake_linux) aşağıda.)

::: moniker range="vs-2019"

Linux için Windows alt sistemi hedeflemek için tıklayın **yapılandırmaları yönetme** içinde yapılandırma açılır ana araç penceresinde. Tuşuna basarak **Yapılandırması Ekle** düğmesini tıklatın ve seçin **WSL hata ayıklama** veya **WSL yayın** GCC, Clang çeşitler Clang/LLVM araç takımı kullanıyorsanız kullanıyorsanız veya. 

**Visual Studio 2019 sürüm 16.1** Linux'ta derleyici, kaynak dosyalarının bulunduğu Windows dosya sistemine doğrudan erişimi olduğundan WSL hedeflerken, kaynaklarını veya üst bilgileri kopyalamaya gereklidir. (Windows sürümünde 1903 ve üzeri, Windows uygulamalarını aynı şekilde Linux üst bilgi dosyaları doğrudan erişebilir, ancak Visual Studio henüz bu özellikten faydalanmak değil).

::: moniker-end

Uzak hedefleri için varsayılan olarak Visual Studio altındaki listede ilk uzak sistem seçer **Araçları** > **seçenekleri** > **Çoklu Platform**  >  **Bağlantı Yöneticisi**. Uzak bağlantılar bulunursa oluşturmanız istenir. Daha fazla bilgi için [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

Uzak Linux hedef belirtirseniz, kaynak uzak sisteme kopyalanır.

Bir hedef seçin sonra CMake projeniz için CMake önbelleği oluşturması için Linux sisteminde otomatik olarak çalıştırır. 

![Linux üzerinde CMake önbelleğini oluşturun](media/cmake-linux-1.png "Linux'ta CMake önbelleğini oluşturun")

Uzak Linux sistemlerinde üst bilgiler için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları Linux makineden yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için [uzak üst bilgiler için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug_cmake_project"></a> CMake proje hata ayıklama

Belirtilen hata ayıklama hedef sistemde kodunuzdaki hataları ayıklamak için bir kesme noktası ayarlayın, CMake hedef proje ayarın yanındaki araç çubuğu menüsü başlangıç öğesi olarak seçin ve seçin  **&#x23f5; Başlat** araç çubuğu veya F5 tuşuna basın.

Program komut satırı bağımsız değişkenleri özelleştirmek için basın **anahtar hedefleri** üst kısmındaki düğmeye **Çözüm Gezgini** seçip **hedefleri görünümü**. Ardından sağ tıklatın ve hedef **hata ayıklama ve başlatma ayarları**. Bu açılır veya, programınız hakkındaki bilgileri içeren bir launch.vs.json yapılandırma dosyası oluşturur. Ek bağımsız değişkenlerini belirtmek için bunları eklemek `args` JSON dizisi. Daha fazla bilgi için [C++ açık klasörü projelerde](../build/open-folder-projects-cpp.md) ve [hata ayıklama oturumları CMake yapılandırma](../build/configure-cmake-debugging-sessions.md).

## <a name="configure_cmake_linux"></a> Linux CMake ayarlarını yapılandırma

Bir CMakeSettings.json dosyasına CMake Linux projesi içinde listelenen tüm özellikleri belirtebilirsiniz [CMake özelleştirme ayarları](../build/customize-cmake-settings.md), ayrıca uzak Linux makine üzerinde derleme ayarlarını denetleyen ek özellikler. 

::: moniker range="vs-2019"

Ana araç çubuğundan Visual Studio 2019 varsayılan CMake ayarlarını değiştirmek için **yapılandırma** seçin ve açılan menü **yapılandırmaları yönetme**. 

![CMake yapılandırmaları yönetme](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırmaları açılır")

Bu işlem sonrasında **CMake ayarları Düzenleyicisi** düzenlemek için kullanabileceğiniz `CMakeSettings.json` kök proje klasörünüzdeki dosya. Doğrudan tıklayarak dosyasını da açabilirsiniz **Düzenle JSON** Düzenleyicisi'nde düğmesi. Daha fazla bilgi için [CMake ayarlarını Özelleştir](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de varsayılan CMake ayarlarını değiştirmek için seçin **CMake | CMake ayarlarını değiştir | CMakeLists.txt** ana menüsünden veya sağ tıklama CMakeSettings.txt içinde **Çözüm Gezgini** ve **CMake ayarlarını değiştir**. Visual Studio ardından oluşturur Yeni `CMakeSettings.json` kök proje klasörünüzdeki dosya. Kullanarak dosyayı açın **CMake ayarlarını** Düzenleyicisi veya dosyasını doğrudan değiştirebilirsiniz. Daha fazla bilgi için [CMake özelleştirme ayarları](../build/customize-cmake-settings.md).

Aşağıdaki örnek, önceki kod örneği temel alarak Visual Studio 2017 (ve Visual Studio 2019 sürüm 16,0) Linux hata ayıklama için varsayılan yapılandırmayı gösterir:

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

 Visual Studio 2019 16.1 ve sonraki sürümleri varsayılan Linux hata ayıklama yapılandırmasında, burada gösterildiği gibi verilmiştir:

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

Bu ayarlar hakkında daha fazla bilgi için bkz. [CMakeSettings.json başvuru](../build/cmakesettings-reference.md).


## <a name="optional-settings"></a>İsteğe bağlı ayarlar

Daha fazla denetim için aşağıdaki isteğe bağlı ayarları kullanabilirsiniz:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Bu seçenekler önce ve sonra yapı ve CMake oluşturma önce Linux sisteminde komutları çalıştırmanıza olanak sağlar. Değerler, uzak sistemde geçerli herhangi bir komutu olabilir. Çıktı, Visual Studio'ya dönün cmdlet'iyle yönetilir.



## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](../build/working-with-project-properties.md)<br/>
[Visual Studio'da CMake projeleri](../build/cmake-projects-in-visual-studio.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)<br/>
[CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)<br/>
