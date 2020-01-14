---
title: Visual Studio 'da CMake hata ayıklama oturumlarını yapılandırma
description: CMake hata ayıklayıcı ayarlarını yapılandırmak için Visual Studio 'Nun nasıl kullanılacağını açıklar
ms.date: 01/13/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: ff1de8241c2489e675f82f469f1cf697a72f5034
ms.sourcegitcommit: 275b71219d2a8bd5d78f87e21dd909e9968c2f44
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75946806"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake hata ayıklama oturumlarını yapılandırma

::: moniker range="vs-2015"

Yerel CMake desteği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Tüm yürütülebilir CMake hedefleri, **genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde gösterilir. Bir hata ayıklama oturumu başlatmak için yalnızca birini seçip hata ayıklayıcıyı başlatın.

![CMake başlangıç öğesi açılan kutusu](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılan kutusu")

Ayrıca, Çözüm Gezgini bir hata ayıklama oturumu başlatabilirsiniz. İlk olarak, **Çözüm Gezgini** penceresinde **CMake hedeflerini göster görünümü** ' ne geçin.

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png  "CMake hedefleri görünümü menü öğesi")

Ardından, herhangi bir yürütülebilir dosyaya sağ tıklayın ve **Hata Ayıkla** veya **Hata Ayıkla ve başlatma ayarları**' nı seçin. **Hata ayıklama** , etkin yapılandırmanıza bağlı olarak seçili hedefte hata ayıklamayı otomatik olarak başlatır. **Hata ayıklama ve başlatma ayarları** , *Launch. vs. JSON* dosyasını açar ve seçili hedef için yeni bir hata ayıklama yapılandırması ekler.

## <a name="customize-debugger-settings"></a>Hata ayıklayıcı ayarlarını özelleştirme

Projenizdeki herhangi bir çalıştırılabilir CMake hedefi için hata ayıklayıcı ayarlarını *Launch. vs. JSON*adlı dosyada özelleştirebilirsiniz. Bu dosyaya üç giriş noktası vardır:

- Etkin hata ayıklama hedefine özgü hata ayıklama yapılandırmasını düzenlemek için ana menüden hata **ayıkla > hata ayıklama ve başlatma ayarları '** nı seçin. Etkin bir hedefi seçili değilse, bu seçenek gri olur.

- Çözüm Gezgini 'de **hedefler görünümüne** gidin. Sonra, bir hata ayıklama hedefine sağ tıklayıp hata ayıkla **ve başlatma ayarları** ' nı seçerek seçtiğiniz hedefe özgü hata ayıklama yapılandırmasını düzenleyin.

- Bir kök CMakeLists. txt dosyasına sağ tıklayın ve **hata ayıklama ve başlatma ayarları** ' nı seçerek **hata ayıklayıcı Seç** iletişim kutusunu açın. İletişim kutusu herhangi bir hata ayıklama yapılandırması eklemenize olanak tanır, ancak `projectTarget` özelliği aracılığıyla çağırmak için CMake hedefini el ile belirtmeniz gerekir.

*Cmakesettings. JSON* dosyasındaki herhangi bir anahtara başvurmak için, bunu *Launch. vs. JSON*içinde `cmake.` ön yüz. Aşağıdaki örnek, şu anda seçili olan yapılandırma için *Cmakesettings. JSON* dosyasında `remoteCopySources` anahtarının değerini alan basit bir *Launch. vs. JSON* dosyasını gösterir:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "name": "CMakeHelloWorld.exe (Debug\\CMakeHelloWorld.exe)",
      "args": ["${cmake.remoteCopySources}"]
    }
  ]
}
```

*Launch. vs. JSON* dosyasını kaydettiğinizde, Visual Studio **Başlangıç öğesi** açılan menüsünde Yeni ad için bir giriş oluşturur. Herhangi bir sayıda CMake hedefi için, birden çok hata ayıklama yapılandırması oluşturmak üzere *Launch. vs. JSON* dosyasını düzenleyebilirsiniz.

## <a name="launchvsjson-reference"></a>Launch. vs. JSON başvurusu

Tüm hata ayıklama senaryolarınızı desteklemek için birçok *Launch. vs. JSON* özelliği vardır. Aşağıdaki özellikler, uzak ve yerel tüm hata ayıklama yapılandırmalarında ortaktır:

- `projectTarget`: proje derlerken çağrılacak CMake hedefini belirtir. Visual Studio, # **{activeDebugTarget} veya hedefler görünümü için debug > hata ayıklama ve başlatma ayarları '** ndan *Launch. vs. JSON* girerseniz,bu özelliği oto doldurur.

- `program`: uzak sistemdeki program yürütülebilirinin tam yolu. Makroyu burada `${debugInfo.fullTargetPath}` kullanabilirsiniz.

- `args`: hata ayıklamak için programa geçirilen komut satırı bağımsız değişkenleri.

## <a name="launchvsjson-reference-for-remote-linux-projects"></a>Uzak Linux projeleri için Launch. vs. JSON başvurusu

Aşağıdaki özellikler, **Uzaktan hata ayıklama yapılandırmalarına**özeldir. Ayrıca, [komutları doğrudan gdb 'ye gönderebilir](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands) ve [mıengine günlük kaydını etkinleştirebilirsiniz](https://github.com/microsoft/MIEngine/wiki/Logging). Bu özellikler, gdb 'ye hangi komutların gönderileceğini, gdb 'nin döndürdüğü çıktıyı ve her komutun ne kadar sürdüğünü görmenizi sağlar.

- `cwd`: uzak makinedeki bağımlılıkları ve diğer dosyaları bulmak için geçerli çalışma dizini. Makro `${debugInfo.defaultWorkingDirectory}` kullanılabilir. Varsayılan değer, *Cmakelists. txt*dosyasında geçersiz kılınmadıkça uzak çalışma alanı köküdür. Bu özellik yalnızca uzak yapılandırmalarda kullanılır; `currentDir`, yerel bir proje için Başlatan uygulamanın geçerli dizinini ayarlamak üzere kullanılır.

- `environment`: Bu söz dizimi ile program için ortama eklenecek ek ortam değişkenleri:

```json
  "environment": [
      {
        "name": "ENV1",
        "value": "envvalue1"
      },
      {
        "name": "ENV2",
        "value": "envvalue2"
      }
    ]
```

- `pipeArgs`: bağlantıyı yapılandırmak için kanal programına geçirilen komut satırı bağımsız değişkenleri. Kanal programı, Visual Studio ile gdb arasında standart giriş/çıkış geçişi için kullanılır. Komut `${debuggerCommand}` uzak sistemde gdb 'yi başlatır ve şu şekilde değiştirilebilir:

  - Linux sisteminizde ortam değişkeni görüntüleme değerini dışarı aktarın. Aşağıdaki örnekte, bu değer `:1`.

  ```json
  "pipeArgs": [
      "/s",
      "${debugInfo.remoteMachineId}",
      "/p",
      "${debugInfo.parentProcessId}",
      "/c",
      "export DISPLAY=:1;${debuggerCommand}",
      "--tty=${debugInfo.tty}"
    ],
  ```

  - GDB 'nin yürütülmesi için bir komut dosyası çalıştırın. Betikte yürütme izinlerinin ayarlandığından emin olun.

    ```json
    "pipeArgs": [
        "/s",
        "${debugInfo.remoteMachineId}",
        "/p",
        "${debugInfo.parentProcessId}",
        "/c",
        "/path/to/script.sh;${debuggerCommand}",
        "--tty=${debugInfo.tty}"
      ],
    ```

- `stopOnEntry`: işlem başlatıldıktan hemen sonra kesmenin yapılıp yapılmayacağını belirten bir Boole değeri. Varsayılan olarak yanlıştır.

- `visualizerFile`: Bu işlemde hata ayıklanırken kullanılacak [. natvis dosyası](/visualstudio/debugger/create-custom-views-of-native-objects) . Bu seçenek, gdb düzgün yazdırma ile uyumsuzdur. Ayrıca, bu özelliği ayarladığınızda `showDisplayString` ayarlayın.

- `showDisplayString`: bir `visualizerFile` belirtildiğinde görünen dizeyi sağlayan bir Boole değeri. Bu seçeneğin `true` ayarlanması, hata ayıklama sırasında daha yavaş performansa neden olabilir.

- `setupCommands`: temel alınan hata ayıklayıcıyı ayarlamak için yürütülecek bir veya daha fazla gdb komutu.

- `externalConsole`: hata ayıklanan için bir konsolun başlatılıp başlatılmayacağını belirten bir Boole değeri.

- `miDebuggerPath`: GDB 'nin tam yolu. Belirtilmediğinde, Visual Studio hata ayıklayıcı için önce yolu arar.

::: moniker-end

::: moniker range="vs-2017"

- `remoteMachineName`: GDB 'yi barındıran uzak Linux sistemi ve hata ayıklamak için program.

::: moniker-end

::: moniker range="vs-2019"

Aşağıdaki özellikler uzaktan **hata ayıklama sisteminizden** **uzak derleme sisteminizi** ayırmak için kullanılabilir. Daha fazla bilgi için bkz. [oluşturma ve hata ayıklama için farklı makineler belirtme](../linux/deploy-run-and-debug-your-linux-project.md#cmake-projects).

- `remoteMachineName`: GDB 'yi barındıran uzak Linux sistemi ve hata ayıklamak için program. Bu girişin *Cmakesettings. JSON*dosyasında belirtilen derleme için kullanılan uzak Linux sistemiyle eşleşmesi gerekmez. [Bağlantı Yöneticisi](../linux/connect-to-your-remote-linux-computer.md)'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **CTRL + boşluk** tuşlarına basın.

- `disableDeploy`: derleme/hata ayıklama ayrımı devre dışı olup olmadığını gösterir. Bu özellik etkinleştirildiğinde, derleme ve hata ayıklamanın iki ayrı makinede oluşmasına izin verir.

- `deployDirectory`: uzak hata ayıklama makinesindeki dizin (`remoteMachineName`tarafından belirtilen), yürütülebilir dosyanın kopyalanacağı yer.

- `deploy`: gelişmiş dağıtım ayarları dizisi. Bu ayarları yalnızca dağıtım işlemi üzerinde daha ayrıntılı denetim sağlamak istediğinizde yapılandırmanız gerekir. Varsayılan olarak, yalnızca hata ayıklama işlemi için gerekli olan dosyalar, uzaktan hata ayıklama makinesine dağıtılır.

  - `sourceMachine`: dosya veya dizinin kopyalanacağı makine. Bağlantı Yöneticisi 'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl + Space** tuşlarına basın.

  - `targetMachine`: dosya veya dizinin kopyalanacağı makine. Bağlantı Yöneticisi 'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl + Space** tuşlarına basın.

  - `sourcePath`: `sourceMachine`dosya veya dizin konumu.

  - `targetPath`: `targetMachine`dosya veya dizin konumu.

  - `deploymentType`: dağıtım türünün açıklaması. `LocalRemote` ve `RemoteRemote` desteklenir. `LocalRemote`, yerel dosya sisteminden *Launch. vs. JSON*içinde `remoteMachineName` tarafından belirtilen uzak sisteme kopyalanması anlamına gelir. `RemoteRemote`, *Cmakesettings. JSON* dosyasında belirtilen uzak derleme sisteminden *Launch. vs. JSON*içinde belirtilen farklı bir uzak sisteme kopyalanması anlamına gelir.

  - `executable`: dağıtılan dosyanın yürütülebilir olup olmadığını gösterir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="attach-to-a-remote-process"></a>Uzak bir işleme iliştirme

Hata ayıklayıcıyı iliştirmek için `processId` Işlem KIMLIĞINE ayarlayarak Linux sisteminizde çalışan bir işleme ekleyebilirsiniz. Daha fazla bilgi için bkz. [GDB kullanarak işlemlere ekleme sorunlarını giderme](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

::: moniker-end

::: moniker range="vs-2019"

## <a name="debug-on-linux-using-gdbserver"></a>Gdbserver kullanarak Linux 'ta hata ayıklama

Visual Studio 2019 sürüm 16,5 Preview 1 veya üzeri, gdbserver ile CMake projelerinin uzaktan hata ayıklamasını destekler. Daha fazla bilgi için bkz. [gdbserver Ile Linux CMake projelerinde hata ayıklama](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/).

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'Da CMake projeleri](cmake-projects-in-visual-studio.md)\
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanın](../linux/connect-to-your-remote-linux-computer.md)\
[CMake derleme ayarlarını özelleştirin](customize-cmake-settings.md)\
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
[Linux projenizi dağıtın, çalıştırın ve hata ayıklayın](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)

::: moniker-end
