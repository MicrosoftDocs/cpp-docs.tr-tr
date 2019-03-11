---
title: Visual Studio'da bir Linux CMake projesi yapılandırma
description: Visual Studio'da bir Linux CMake projesi yapılandırma
ms.date: 11/01/2018
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: f2186c14fbe2eb1273fceb4a378b359564eae327
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750604"
---
# <a name="configure-a-linux-cmake-project"></a>Linux CMake projesi yapılandırma

Visual Studio, bir CMake projesini içeren bir klasörü açtığınızda, CMake IntelliSense yapılandırılacağı ve otomatik olarak oluşturur meta verileri kullanır. Yerel yapılandırma ve hata ayıklama ayarları, Visual Studio kullanan, isteğe bağlı olarak diğer kullanıcılarla paylaşılabilir JSON dosyalarında depolanır. 

Başkalarının aynı proje üzerinde çalışmaya zaten kullandıkları ne olursa olsun araçları kullanmaya devam edebilmeniz için visual Studio CMakeLists.txt dosyalar ya da özgün CMake önbelleği değiştirmez.  

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, sahip olduğunuzdan emin olun **C++ ile Linux geliştirme** CMake bileşen dahil olmak üzere iş yükü yüklenmiş,. Bkz: [Visual Studio'da C++ Linux iş yükünü yükleyin](download-install-and-setup-the-linux-development-workload.md). 

Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

Bu konuda okuduğunuz varsayılır [Visual Studio için CMake araçlarını](../ide/cmake-tools-for-visual-cpp.md). 

> [!NOTE]
> Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Bir Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases). Visual Studio 2019 önceden oluşturulmuş ikili dosyalar otomatik olarak dağıtılabilir (bkz [önceden oluşturulmuş CMake ikilileri indirmek](#download-prebuilt-cmake-binaries)).

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

**Visual Studio 2017 sürüm 15.7 ve üzeri:**<br/>
Uzak üst bilgiler için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları Linux makineden yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için [uzak üst bilgiler için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Proje hata ayıklama

Uzak sistem üzerindeki kodunuzdaki hataları ayıklamak için bir kesme noktası ayarlayın, CMake hedef proje ayarın yanındaki araç çubuğu menüsü başlangıç öğesi olarak seçin ve seçin  **&#x23f5; Başlat** araç çubuğu veya F5 tuşuna basın.

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu açılır veya, programınız hakkındaki bilgileri içeren bir launch.vs.json yapılandırma dosyası oluşturur. Ek bağımsız değişkenlerini belirtmek için bunları eklemek `args` JSON dizisi. Daha fazla bilgi için [Klasör Aç Visual C++ projelerinde](../ide/non-msbuild-projects.md) ve [hata ayıklama oturumları CMake yapılandırma](../ide/configure-cmake-debugging-sessions.md).

## <a name="configure-cmake-settings-for-linux"></a>Linux CMake ayarlarını yapılandırma

Bir CMakeSettings.json dosyasına CMake Linux projesi içinde listelenen tüm özellikleri belirtebilirsiniz [CMake özelleştirme ayarları](../ide/customize-cmake-settings.md), ayrıca uzak Linux makine üzerinde derleme ayarlarını denetleyen ek özellikler. Varsayılan CMake ayarlarını değiştirmek için seçin **CMake | CMake ayarlarını değiştir | CMakeLists.txt** ana menüsünden veya sağ tıklama CMakeSettings.txt içinde **Çözüm Gezgini** ve **CMake ayarlarını değiştir**. Visual Studio ardından oluşturur Yeni `CMakeSettings.json` kök proje klasörünüzdeki dosya. Kullanarak dosyayı açın **CMake ayarlarını** Düzenleyicisi veya dosyasını doğrudan değiştirebilirsiniz. 

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
      "remotePreBuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostBuildCommand": "",
}
```

Bu seçenekler uzak sistemde, önce ve sonra yapı ve CMake oluşturma önce komutları çalıştırmanıza olanak sağlar. Değerler, uzak sistemde geçerli herhangi bir komutu olabilir. Çıktı, Visual Studio'ya dönün cmdlet'iyle yönetilir.

## <a name="download-prebuilt-cmake-binaries"></a>Önceden oluşturulmuş CMake ikili dosyaları indirme

Kendi Linux distro CMake daha eski bir sürümü olabilir. Visual Studio'da CMake desteği, CMake 3.8 içinde sunulan sunucu modu desteği gerektirir. Microsoft tarafından sağlanan CMake değişken için en son önceden oluşturulmuş ikilileri indirmek [ https://github.com/Microsoft/CMake/releases ](https://github.com/Microsoft/CMake/releases).

**Visual Studio 2019**<br/>
Geçerli bir CMake uzak makinede bulunmazsa bir bilgi çubuğu görünür ve önceden oluşturulmuş CMake ikili dosyaları otomatik olarak dağıtmak için bir seçenek sağlar. İkili dosyaların şekilde yüklenecek `~/.vs/cmake`. İkili dosyaları dağıttıktan sonra projeniz otomatik olarak yeniden neden. Tarafından belirtilen CMake unutmayın `cmakeExecutable` alanındaki `CMakeSettings.json` geçersiz (mevcut değil veya desteklenmeyen bir sürüm) ve önceden oluşturulmuş ikili dosyalar mevcut Visual Studio yoksayar `cmakeExecutable` ve önceden oluşturulmuş ikili dosyaları kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)<br/>
[Visual C++ için CMake araçları](../ide/cmake-tools-for-visual-cpp.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md)<br/>
[CMake ayarlarını özelleştirme](../ide/customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](../ide/configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](../ide/cmake-predefined-configuration-reference.md)<br/>
