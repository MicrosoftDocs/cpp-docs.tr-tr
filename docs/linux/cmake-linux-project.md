---
title: Visual Studio'da bir Linux CMake projesi yapılandırma
description: Visual Studio'da bir Linux CMake projesi yapılandırma
ms.date: 07/20/2018
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 32d69e28c0991adc6117b7f9496eeb1022943ef2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585048"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake projesi yapılandırma

**Visual Studio 2017 sürüm 15.4 ve üzeri**<br/>
Linux CMake desteği, Visual Studio için Linux C++ iş yükünü yüklediğinizde varsayılan olarak seçilidir. Artık CMake için Visual Studio projesi dönüştürmek zorunda kalmadan kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, hem Windows hem de Visual Studio içinden Linux'u hedefleyebilirsiniz.

Bu konuda, Visual Studio'da CMake desteği temel olarak bilindiğini sahip olduğunuz varsayılır. Daha fazla bilgi için [Visual C++ için CMake araçlarını](../ide/cmake-tools-for-visual-cpp.md). CMake kendisi hakkında daha fazla bilgi için bkz: [derleme, Test ve paket Your yazılım CMake ile](https://cmake.org/).

> [!NOTE]
> Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Bir Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

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
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Bir Linux hedef seçin

Klasörü açın hemen sonra Visual Studio CMakeLists.txt dosyasını ayrıştırır ve Windows hedefi belirtir **x86 hata ayıklama**. Linux hedeflemek için proje ayarlarını **Linux hata ayıklama** veya **Linux sürüm**.

Varsayılan olarak, Visual Studio altındaki listede ilk uzak sistem seçer **Araçları** > **seçenekleri** > **Çoklu Platform**  >  **Bağlantı Yöneticisi**. Uzak bağlantılar bulunursa oluşturmanız istenir.

Bir Linux hedef belirttikten sonra kaynak Linux makinenizi kopyalanır. Daha sonra CMake projeniz için CMake önbelleği oluşturması için Linux makine üzerinde çalıştırın.

![Linux üzerinde CMake önbelleğini oluşturun](media/cmake-linux-1.png "Linux'ta CMake önbelleğini oluşturun")

**Visual Studio 2017 sürüm 15.7 ve üzeri:**<br/>
Uzak üst bilgiler için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için [uzak üst bilgiler için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Proje hata ayıklama

Uzak sistem üzerindeki kodunuzdaki hataları ayıklamak için bir kesme noktası ayarlayın, CMake hedef proje ayarın yanındaki araç çubuğu menüsü başlangıç öğesi olarak seçin ve seçin  **&#x23f5; Başlat** araç çubuğu veya F5 tuşuna basın.

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu açılır veya, programınız hakkındaki bilgileri içeren bir launch.vs.json yapılandırma dosyası oluşturur. Ek bağımsız değişkenlerini belirtmek için bunları eklemek `args` JSON dizisi. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](../ide/non-msbuild-projects.md).

## <a name="configure-cmake-settings-for-linux"></a>Linux CMake ayarlarını yapılandırma

Varsayılan CMake ayarlarını değiştirmek için seçin **CMake | CMake ayarlarını değiştir | CMakeLists.txt** ana menüsünden veya sağ tıklama CMakeSettings.txt içinde **Çözüm Gezgini** ve **CMake ayarlarını değiştir**. Visual Studio ardından adlı klasörünüze yeni bir dosya oluşturur `CMakeSettings.json` proje ayarları menü öğesi listelenen varsayılan yapılandırmaları ile doldurulur. Aşağıdaki örnek, Linux hata ayıklama için varsayılan yapılandırma, önceki kod örneği temel alarak gösterir:

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

`name` Dilediğiniz değeri olabilir. `remoteMachineName` Değer birden fazla olması durumunda hangi hedef, uzak sisteme belirtir. IntelliSense doğru sistemi seçmenize yardımcı olması Bu alan için etkinleştirilir. Alan `remoteCMakeListsRoot` proje kaynaklarınız için Uzak sistemde kopyalanacağı belirtir. Alan `remoteBuildRoot` , uzak sistemde yapı çıkışını oluşturulacağı olduğu. Çıkış da yerel olarak tarafından belirtilen konuma kopyalanır `buildRoot`. `remoteInstallRoot` Ve `installRoot` alanları için benzer `remoteBuildRoot` ve `buildRoot`, bir cmake yüklemesi yapılırken geçerlidir. `remoteCopySources` Giriş, yerel kaynakları uzak makineye kopyalanan olup olmadığını denetler. Bunu false olarak çok sayıda dosya varsa ve zaten kaynakları kendinize eşitleniyor ayarlayabilirsiniz. `remoteCopyOutputVerbosity` Değer hataları tanılamak gerektiği durumlarda kopyalama adımı, ayrıntı düzeyini denetler. `remoteCopySourcesConcurrentCopies` Giriş kaç işlemleri kopyalamayı yapmak için kökenli denetler. `remoteCopySourcesMethod` Değer rsync veya sftp biri olabilir. `remoteCopySourcesExclusionList` Alan uzak makineye kopyalandı denetlemenize olanak verir. `rsyncCommandArgs` Değeri kopyalama rsync yöntemi denetlemenize olanak tanır. `remoteCopyBuildOutput` Alan denetimleri olup olmadığı uzak derleme çıktı, yerel bir yapı klasörüne kopyalanır.

Daha fazla denetim için kullanabileceğiniz bazı isteğe bağlı ayarları vardır:

```json
{
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Bu seçenekler önce ve sonra yapı ve CMake oluşturma önce uzak çubuğundaki komutları çalıştırmanıza olanak sağlar. Herhangi bir geçerli komutu uzak kutusunda olabilirler. Çıkış, Visual Studio'ya dönün cmdlet'iyle yönetilir.

## <a name="download-prebuilt-cmake-binaries"></a>Önceden oluşturulmuş CMake ikili dosyaları indirme

Kendi Linux distro CMake daha eski bir sürümü olabilir. Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Bir Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)<br/>
[Visual C++ için CMake araçları](../ide/cmake-tools-for-visual-cpp.md)
