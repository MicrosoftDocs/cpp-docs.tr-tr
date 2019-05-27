---
title: Visual Studio'da bir Linux CMake projesi yapılandırma
description: Yapılandırma, düzenlemek ve bir Linux CMake projesini Visual Studio'da derleyin
ms.date: 05/21/2019
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: e2cda5e9b942342cca035c48054aadb5425b69cf
ms.sourcegitcommit: bde3279f70432f819018df74923a8bb895636f81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66174775"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake projesi yapılandırma

Visual Studio, bir CMake projesini içeren bir klasörü açtığınızda, CMake IntelliSense yapılandırılacağı ve otomatik olarak oluşturur meta verileri kullanır. Yerel yapılandırma ve hata ayıklama ayarları, Visual Studio kullanan, isteğe bağlı olarak diğer kullanıcılarla paylaşılabilir JSON dosyalarında depolanır. 

Başkalarının aynı proje üzerinde çalışmaya zaten kullandıkları ne olursa olsun araçları kullanmaya devam edebilmeniz için visual Studio CMakeLists.txt dosyalar ya da özgün CMake önbelleği değiştirmez.

Visual Studio'da CMake desteği hakkında genel bilgi için bkz: [Visual Studio için CMake araçlarını](../build/cmake-projects-in-visual-studio.md). Bu burada devam etmeden önce okuyun.

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, sahip olduğunuzdan emin olun **C++ ile Linux geliştirme** CMake bileşen dahil olmak üzere iş yükü yüklenmiş,. Bkz: [Visual Studio'da C++ Linux iş yükünü yükleyin](download-install-and-setup-the-linux-development-workload.md). 

Linux makinesinde aşağıdaki yüklendiğinden emin olun: 

- gcc
- GDB
- rsync
- zip 

::: moniker range="vs-2019"

CMake projeleri için Linux desteği, en güncel sürümünü CMake hedef makinede yüklü olmasını gerektirir. Genellikle, bir dağıtım'ın varsayılan Paket Yöneticisi tarafından sunulan sürüm IDE'nin tüm özellikleri desteklemek için yeterince yeni değil. Visual Studio 2019 CMake kullanıcı yerel kopyasını yeni bir sürümü yüklü CMake olmayan uzak Linux makineleri otomatik olarak geri yükleyebilirsiniz. CMake uyumlu bir sürümünün ilk kez algılanırsa değil, projenizi, CMake yüklemek sunan bir bilgi çubuğu görürsünüz.

İkili dosyaların şekilde yüklenecek `~/.vs/cmake`. İkili dosyaları dağıttıktan sonra projeniz otomatik olarak yeniden neden. Tarafından belirtilen CMake unutmayın `cmakeExecutable` alanındaki `CMakeSettings.json` geçersiz (mevcut değil veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş ikili dosyalar mevcut Visual Studio yoksayar `cmakeExecutable` ve önceden oluşturulmuş ikili dosyaları kullanın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

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
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Bir Linux hedef seçin

Klasörü açın hemen sonra Visual Studio CMakeLists.txt dosyasını ayrıştırır ve Windows hedefi belirtir **x86 hata ayıklama**. Linux hedeflemek için proje ayarlarını **Linux hata ayıklama** veya **Linux sürüm**.

Varsayılan olarak, Visual Studio altındaki listede ilk uzak sistem seçer **Araçları** > **seçenekleri** > **Çoklu Platform**  >  **Bağlantı Yöneticisi**. Uzak bağlantılar bulunursa oluşturmanız istenir. Daha fazla bilgi için [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

Bir Linux hedef belirttikten sonra kaynak Linux makinenizi kopyalanır. Daha sonra CMake projeniz için CMake önbelleği oluşturması için Linux makine üzerinde çalıştırın.

![Linux üzerinde CMake önbelleğini oluşturun](media/cmake-linux-1.png "Linux'ta CMake önbelleğini oluşturun")

Uzak üst bilgiler için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları Linux makineden yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için [uzak üst bilgiler için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Proje hata ayıklama

Uzak sistem üzerindeki kodunuzdaki hataları ayıklamak için bir kesme noktası ayarlayın, CMake hedef proje ayarın yanındaki araç çubuğu menüsü başlangıç öğesi olarak seçin ve seçin  **&#x23f5; Başlat** araç çubuğu veya F5 tuşuna basın.

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu açılır veya, programınız hakkındaki bilgileri içeren bir launch.vs.json yapılandırma dosyası oluşturur. Ek bağımsız değişkenlerini belirtmek için bunları eklemek `args` JSON dizisi. Daha fazla bilgi için [C++ açık klasörü projelerde](../build/open-folder-projects-cpp.md) ve [hata ayıklama oturumları CMake yapılandırma](../build/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a>Linux CMake ayarlarını yapılandırma

Bir CMakeSettings.json dosyasına CMake Linux projesi içinde listelenen tüm özellikleri belirtebilirsiniz [CMake özelleştirme ayarları](../build/customize-cmake-settings.md), ayrıca uzak Linux makine üzerinde derleme ayarlarını denetleyen ek özellikler. 

::: moniker range="vs-2019"

Ana araç çubuğundan Visual Studio 2019 varsayılan CMake ayarlarını değiştirmek için **yapılandırma** seçin ve açılan menü **yapılandırmaları yönetme**. 

   ![CMake yapılandırmaları yönetme](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırmaları açılır")

Bu işlem sonrasında **CMake ayarları Düzenleyicisi** düzenlemek için kullanabileceğiniz `CMakeSettings.json` kök proje klasörünüzdeki dosya. Doğrudan tıklayarak dosyasını da açabilirsiniz **Düzenle JSON** Düzenleyicisi'nde düğmesi. Daha fazla bilgi için [CMake ayarlarını Özelleştir](../build/customize-cmake-settings.md).

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017'de varsayılan CMake ayarlarını değiştirmek için seçin **CMake | CMake ayarlarını değiştir | CMakeLists.txt** ana menüsünden veya sağ tıklama CMakeSettings.txt içinde **Çözüm Gezgini** ve **CMake ayarlarını değiştir**. Visual Studio ardından oluşturur Yeni `CMakeSettings.json` kök proje klasörünüzdeki dosya. Kullanarak dosyayı açın **CMake ayarlarını** Düzenleyicisi veya dosyasını doğrudan değiştirebilirsiniz. Daha fazla bilgi için [CMake özelleştirme ayarları](../build/customize-cmake-settings.md).

::: moniker-end

Aşağıdaki örnek, Linux hata ayıklama için varsayılan yapılandırma, önceki kod örneği temel alarak gösterir:

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
Aşağıdaki tabloda ayarları özetlemektedir:

|Ayar|Açıklama|
|-----------|-----------------|
|`name`|Bu değer, dilediğiniz olabilir.|
|`remoteMachineName`|Birden fazla olması durumunda, hedef, hangi uzak sisteme belirtir. IntelliSense doğru sistemi seçmenize yardımcı olması Bu alan için etkinleştirilir.|
|`remoteCMakeListsRoot`|Proje kaynaklarınız için Uzak sistemde kopyalanacağı belirtir.|
|`remoteBuildRoot`|Derleme çıktısında, uzak sistemde oluşturulacağı belirtir. Çıkış da yerel olarak tarafından belirtilen konuma kopyalanır `buildRoot`.|
|`remoteInstallRoot` ve `installRoot`| Benzer şekilde `remoteBuildRoot` ve `buildRoot`, bir CMake yüklemesi yapılırken geçerlidir.|
|`remoteCopySources`|Yerel, kaynakları uzak makineye kopyalanıp olup olmadığını belirtir. Bunu false olarak çok sayıda dosya varsa ve zaten kaynakları kendinize eşitleniyor ayarlayabilirsiniz.|
|`remoteCopyOutputVerbosity`| Hataları tanılamak gerektiği durumlarda kopyalama adımı, ayrıntı düzeyini belirtir.|
|`remoteCopySourcesConcurrentCopies`| Kaç tane işlemleri kopyalamayı yapmak için kökenli belirtir.|
|`remoteCopySourcesMethod`| Olabilir `rsync` veya `sftp`.|
|`remoteCopySourcesExclusionList`| Uzak makineye kopyalanmasını istemediğiniz dosyaları belirtir.|
|`rsyncCommandArgs`|Rsync kopyalama yöntemini denetler.|
|`remoteCopyBuildOutput`| Uzak derleme çıktı, yerel yapı klasörüne kopyalandığını olup olmadığını denetler.|

Bu isteğe bağlı ayarlar daha fazla denetim için kullanabilirsiniz:

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

Bu seçenekler uzak sistemde, önce ve sonra yapı ve CMake oluşturma önce komutları çalıştırmanıza olanak sağlar. Değerler, uzak sistemde geçerli herhangi bir komutu olabilir. Çıktı, Visual Studio'ya dönün cmdlet'iyle yönetilir.

::: moniker range="vs-2019"

Visual Studio 2019 içinde tüm bu ayarları düzenleyebileceğiniz **CMake ayarları Düzenleyicisi**.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](../build/working-with-project-properties.md)<br/>
[Visual Studio'da CMake projeleri](../build/cmake-projects-in-visual-studio.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)<br/>
[CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)<br/>
