---
title: Visual Studio 'da Linux CMake projesi yapılandırma
description: Visual Studio 'da Linux CMake ayarlarını yapılandırma
ms.date: 08/08/2020
ms.openlocfilehash: d39423b803b66d6bdf55cc67d488e74ccb682323
ms.sourcegitcommit: 2034f8e744a8b36cff8b15e9a5cfe684afebadfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2020
ms.locfileid: "88048193"
---
# <a name="configure-a-linux-cmake-project-in-visual-studio"></a>Visual Studio 'da Linux CMake projesi yapılandırma

::: moniker range="vs-2015"
Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu sürümlerin belgelerini görmek için, içindekiler tablosunun üstünde bulunan **Sürüm** açılan listesini **Visual Studio 2017** veya **Visual Studio 2019**olarak ayarlayın.
::: moniker-end

::: moniker range=">=vs-2017"
Bu konuda, bir CMake projesine, Linux için uzak bir Linux sistemi veya Linux (WSL) için Windows alt sistemi hedefleyen bir Linux yapılandırmasının nasıl ekleneceği açıklanmaktadır. [Visual Studio 'Da Linux CMake projesi oluşturma](cmake-linux-project.md)ile başlayan seriye devam eder. Bunun yerine MSBuild kullanıyorsanız, bkz. [Visual Studio 'Da Linux MSBuild projesi yapılandırma](configure-a-linux-project.md)

## <a name="add-a-linux-configuration"></a>Linux yapılandırması ekleme

Bir yapılandırma, aynı kaynak kodlu farklı platformları (Windows, WSL, uzak sistem) hedeflemek için kullanılabilir. Ayrıca, derleyicilerini ayarlamak, ortam değişkenlerini geçirmek ve CMake 'in nasıl çağrılacağını özelleştirmek için de bir yapılandırma kullanılır. Dosya *CMakeSettings.js* , [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)bölümünde listelenen özelliklerin bazılarını veya tümünü ve uzak Linux makinesindeki derleme ayarlarını denetleyen ek özellikleri belirtir.
::: moniker-end

::: moniker range="vs-2017"
Visual Studio 2017 ' de varsayılan CMake ayarlarını değiştirmek için, ana menüden **CMake**  >  **değişiklik CMake ayarlarını**  >  **CMakeLists.txt** seçin. Ya da **Çözüm Gezgini** *CMakeLists.txt* sağ tıklayıp **CMake ayarlarını değiştir**' i seçin. Daha sonra Visual Studio, kök proje klasörünüzde dosya üzerinde yeni bir *CMakeSettings.js* oluşturur. Değişiklik yapmak için dosyayı açın ve doğrudan değiştirin. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

Visual Studio 2017 ' de Linux-Debug için varsayılan yapılandırma (ve Visual Studio 2019 sürüm 16,0) şuna benzer:

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
Visual Studio 2019 ' de varsayılan CMake ayarlarını değiştirmek için, ana araç çubuğundan **yapılandırma** açılan listesini açın ve **yapılandırmaları Yönet**' i seçin.

![CMake yönetme yapılandırması](../build/media/vs2019-cmake-manage-configurations.png "CMake yapılandırma açılır")

Bu komut, kök proje klasörünüzdeki dosyadaki *CMakeSettings.js* düzenlemek Için kullanabileceğiniz **CMake ayarları düzenleyicisini**açar. Ayrıca, düzenleyicide **JSON Düzenle** düğmesine TıKLAYARAK dosyayı JSON Düzenleyicisi ile açabilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md).

Visual Studio 2019 sürüm 16,1 ' de varsayılan Linux-hata ayıklama yapılandırması ve sonraki sürümler şöyle görünür:

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

Visual Studio 2019 sürüm 16,6 veya sonraki sürümlerde, Dokja, uzak bir sistemi veya WSL 'yi hedefleyen yapılandırmalara yönelik varsayılan oluşturucu olur. Daha fazla bilgi için bkz. [C++ ekip blogu](https://devblogs.microsoft.com/cppblog/linux-development-with-visual-studio-first-class-support-for-gdbserver-improved-build-times-with-ninja-and-updates-to-the-connection-manager/)üzerinde bu gönderi.

::: moniker-end
::: moniker range=">=vs-2017"
Bu ayarlar hakkında daha fazla bilgi için bkz. [CMakeSettings.jsbaşvurusu](../build/cmakesettings-reference.md).

Bir yapı gerçekleştirdiğinizde:
- Uzak bir sistemi hedefliyorsanız, Visual Studio **Tools** > **Options** > uzak hedefler için varsayılan olarak Araçlar Seçenekler **platformlar arası** > **Bağlantı Yöneticisi** altındaki listede bulunan ilk uzak sistemi seçer.
- Uzak bağlantı bulunamazsa, bir tane oluşturmanız istenir. Daha fazla bilgi için bkz. [uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md).

## <a name="choose-a-linux-target"></a>Linux hedefi seçin

CMake proje klasörünü açtığınızda, Visual Studio *CMakeLists.txt* dosyayı ayrıştırır ve **x86-Debug**' ı bir Windows hedefini belirtir. Uzak bir Linux sistemini hedeflemek için proje ayarlarını **Linux-Debug** veya **Linux-Release**olarak değiştirirsiniz.

Uzak bir Linux hedefi belirtirseniz, kaynağınız uzak sisteme kopyalanır.

Bir hedef seçtikten sonra CMake, projenizin CMake önbelleğini oluşturmak için Linux sisteminde otomatik olarak çalışır:

![Linux 'ta CMake önbelleği oluşturma](media/cmake-linux-1.png "Linux 'ta CMake önbelleğini oluşturma")

::: moniker-end
::: moniker range="vs-2019"

### <a name="target-windows-subsystem-for-linux"></a>Linux için Windows alt sistemini hedefleme

Linux için Windows alt sistemini (WSL) hedefliyorsanız, uzak bir bağlantı eklemeniz gerekmez.

WSL 'yi hedeflemek için ana araç çubuğunda yapılandırma açılan menüsünde **yapılandırmaları Yönet** ' i seçin. Ardından, **yapılandırma Ekle** düğmesine basın ve GCC kullanılıyorsa **WSL-Debug** veya **WSL-Release** ' i seçin. Clang/LLVM araç takımını kullanıyorsanız Clang türevlerini kullanın.

**Visual Studio 2019 sürüm 16,1** WSL 'yi hedeflediğinizde, Linux üzerindeki derleyicinin bağlı Windows dosya sisteminde kaynak dosyalarınıza doğrudan erişimi olduğundan, Visual Studio 'nun kaynak dosyalarını kopyalaması ve yapı ağacınızdaki iki zaman uyumlu kopyasını koruması gerekmez.
::: moniker-end
::: moniker range=">=vs-2017"

### <a name="intellisense"></a>IntelliSense

Doğru C++ IntelliSense, C++ kaynak dosyalarınızın başvurduğu C++ üst bilgilerine erişim gerektirir. Visual Studio, tam uygunlukta bir IntelliSense deneyimi sağlamak için Linux 'tan Windows 'a CMake projesi tarafından başvurulan üstbilgileri otomatik olarak kullanır. Daha fazla bilgi için bkz. [uzak üstbilgiler Için IntelliSense](configure-a-linux-project.md#remote_intellisense).

### <a name="locale-setting"></a>Yerel ayar ayarı

Visual Studio yüklü paketleri yönetmediğinden veya yapılandırmadığından, Visual Studio dil ayarları Linux hedeflerine yayılmaz. Derleme hataları gibi çıkış penceresinde gösterilen iletiler, Linux hedefinin dili ve yerel ayarı kullanılarak gösterilir. Linux hedeflerinizi istenen yerel ayar için yapılandırmanız gerekir.

## <a name="additional-settings"></a>Ek ayarlar

Oluşturmadan önce ve sonra ve CMake oluşturmadan önce Linux sisteminde komutları çalıştırmak için aşağıdaki ayarları kullanın. Değerler, uzak sistemde geçerli olan herhangi bir komut olabilir. Çıktı, Visual Studio 'ya geri gönderilir.

```json
{
      "remotePrebuildCommand": "",
      "remotePreGenerateCommand": "",
      "remotePostbuildCommand": "",
}
```

## <a name="next-steps"></a>Sonraki adımlar

[CMake hata ayıklama oturumlarını yapılandırma](../build/configure-cmake-debugging-sessions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Proje özellikleriyle çalışma](../build/working-with-project-properties.md)<br/>
[CMake ayarlarını özelleştirme](../build/customize-cmake-settings.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](../build/cmake-predefined-configuration-reference.md)

::: moniker-end
