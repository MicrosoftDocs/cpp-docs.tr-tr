---
title: Visual Studio'da bir Linux CMake projesi yapılandırma | Microsoft Docs
description: Visual Studio'da bir Linux CMake projesi yapılandırma
ms.custom: ''
ms.date: 07/20/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: bbc19b4c8e698c520be2283376ac5297cdae33df
ms.sourcegitcommit: f923f667065cd6c4203d10ca9520600ee40e5f84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/24/2018
ms.locfileid: "42900518"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake projesi yapılandırma

**Visual Studio 2017 sürüm 15.4 ve üzeri**  
Linux CMake desteği, Visual Studio için Linux C++ iş yükünü yüklediğinizde varsayılan olarak seçilidir. Artık CMake için Visual Studio projesi dönüştürmek zorunda kalmadan kullanan mevcut kod tabanınız üzerinde çalışabilirsiniz. Kod tabanınız platformlar arası ise, hem Windows hem de Visual Studio içinden Linux'u hedefleyebilirsiniz.

Bu konuda, Visual Studio'da CMake desteği temel olarak bilindiğini sahip olduğunuz varsayılır. Daha fazla bilgi için [Visual C++ için CMake araçlarını](../ide/cmake-tools-for-visual-cpp.md). CMake kendisi hakkında daha fazla bilgi için bkz: [derleme, Test ve paket Your yazılım CMake ile](https://cmake.org/).

> [!NOTE]  
> Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Destekleyen bir Microsoft tarafından sağlanan CMake değişken için [CMake hedefleri görünümü](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) bölmesinde Visual Studio, en son önceden oluşturulmuş ikili karşıdan [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases). Paket Yöneticisi'ni CMake 3.8 daha eski bir sürüm sağlıyorsa, geçici bir çözüm olarak çalışabilir [kaynağından CMake oluşturma](#build-a-supported-cmake-release-from-source), veya standart CMake kullanmayı tercih, resmi indirebilirsiniz [CMake indirme sayfası](https://cmake.org/download/). 

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

**Visual Studio 2017 sürüm 15.7 ve üzeri:**  
Uzak üst bilgiler için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için [uzak üst bilgiler için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Proje hata ayıklama

Uzak sistem üzerindeki kodunuzdaki hataları ayıklamak için bir kesme noktası ayarlayın, CMake hedef proje ayarın yanındaki araç çubuğu menüsü başlangıç öğesi olarak seçin ve seçin  **&#x23f5; Başlat** araç çubuğu veya F5 tuşuna basın.

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu açılır veya, programınız hakkındaki bilgileri içeren bir launch.vs.json yapılandırma dosyası oluşturur. Ek bağımsız değişkenlerini belirtmek için bunları eklemek `args` JSON dizisi. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](https://docs.microsoft.com/en-us/cpp/ide/non-msbuild-projects).

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

## <a name="build-a-supported-cmake-release-from-source"></a>Desteklenen bir CMake sürüm kaynağından alınan derleme

CMake en düşük sürümü, makine 3.8 ve sunucu modu desteklemelidir, Linux üzerinde gerekli. Bu komutu çalıştırarak bunu doğrulamak için:

```cmd
cmake --version
```

Bu sunucu modu etkin doğrulamak için şunu çalıştırın:

```cmd
cmake -E capabilities
```

Çıkışta, Aranan **"serverMode": true**. Hatta kaynağından CMake, açıklandığı gibi derleme yaptığınızda işiniz bittiğinde özellikleri denetlemelisiniz unutmayın. Linux sisteminiz sunucu modu etkinleştirilmesini engelleyen kısıtlamalar olabilir.

CMake Linux sisteminizin shell'de kaynağından oluşturmaya başlamak için Paket Yöneticisi güncel olduğundan ve git ve cmake kullanılabilir olduğundan emin olun.

İlk olarak, CMake kaynaklardan kopyalama [Microsoft CMake depo](https://github.com/Microsoft/CMake) Visual Studio'nun CMake desteği için bir Çatal burada sunuyoruz:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

Ardından, derleme ve /usr/local/bin için CMake'nin geçerli sürümünü yüklemek için şu komutları çalıştırın:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Ardından, sürüm doğrulamak için bu komutu çalıştırın > = 3.8 ve sunucu modu etkin:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)  
[Visual C++ için CMake araçları](../ide/cmake-tools-for-visual-cpp.md)  
