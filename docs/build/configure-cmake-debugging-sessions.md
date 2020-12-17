---
title: Visual Studio 'da CMake hata ayıklama oturumlarını yapılandırma
description: CMake hata ayıklayıcı ayarlarını yapılandırmak için Visual Studio 'Nun nasıl kullanılacağını açıklar.
ms.date: 12/16/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 36a4d64b987c1468caa06ed8670dfaf7d44abad3
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645112"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake hata ayıklama oturumlarını yapılandırma

::: moniker range="msvc-140"

Yerel CMake desteği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu sürümlerin belgelerini görmek için, bu makalenin Visual Studio **Sürüm** Seçicisi denetimini visual Studio 2017 veya visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=msvc-150"

Tüm yürütülebilir CMake hedefleri, araç çubuğundaki **Başlangıç öğesi** açılır listesinde gösterilir. Bir hata ayıklama oturumu başlatmak ve hata ayıklayıcıyı başlatmak için bir tane seçin.

![CMake başlangıç öğesi açılan kutusu](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılan kutusu")

Ayrıca, Çözüm Gezgini bir hata ayıklama oturumu başlatabilirsiniz. İlk olarak, **Çözüm Gezgini** penceresinde **CMake hedeflerini göster görünümü** ' ne geçin.

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png  "CMake hedefleri görünümü menü öğesi")

Ardından, bir yürütülebilir dosyaya sağ tıklayın ve **Hata Ayıkla**' yı seçin. Bu komut, etkin yapılandırmanıza bağlı olarak seçili hedefte hata ayıklamaya otomatik olarak başlar.

## <a name="customize-debugger-settings"></a>Hata ayıklayıcı ayarlarını özelleştirme

Projenizdeki herhangi bir çalıştırılabilir CMake hedefi için hata ayıklayıcı ayarlarını özelleştirebilirsiniz. Bunlar, proje kökündeki bir klasörde bulunan *launch.vs.json* adlı bir yapılandırma dosyasında bulunur *`.vs`* . Hata ayıklama kurulum ayrıntılarınızı yapılandırıp kaydedebildiğinden, bir başlatma yapılandırma dosyası çoğu hata ayıklama senaryosunda yararlıdır. Bu dosyaya üç giriş noktası vardır:

- **Hata ayıklama menüsü:** Etkin hata ayıklama hedefine özgü hata ayıklama yapılandırmasını özelleştirmek için ana menüden hata **ayıkla > hata ayıklama ve başlatma ayarları '** nı seçin. Seçili bir hata ayıklama hedefi yoksa, bu seçenek gri renkte olur.

![Hata ayıklama menüsü giriş noktası](media/cmake-debug-menu.png "Hata ayıklama menüsü giriş noktası")

- **Hedef görünümü:** Çözüm Gezgini 'de **hedefler görünümüne** gidin. Ardından, bir hata ayıklama hedefine sağ tıklayıp, seçilen hedefe özgü hata ayıklama yapılandırmasını özelleştirmek için **hata ayıklama yapılandırması Ekle** ' yi seçin.

![Hedef görünümü giriş noktası](media/cmake-targets-add-debug-configuration.png "Hedef görünümü giriş noktası")

- **Kök CMakeLists.txt:** Bir kök *CMakeLists.txt* sağ tıklayıp **hata ayıklama yapılandırması Ekle** ' yi seçerek **bir hata ayıklayıcı Seç** iletişim kutusunu açın. İletişim kutusu *herhangi bir* tür hata ayıklama yapılandırması eklemenize olanak tanır, ancak özelliği aracılığıyla çağırmak Için CMake hedefini el ile belirtmeniz gerekir `projectTarget` .

![Bir hata ayıklayıcı iletişim kutusu seçin](media/cmake-select-a-debugger.png "Bir hata ayıklayıcı iletişim kutusu seçin")

Herhangi bir sayıda CMake hedefi için hata ayıklama yapılandırması oluşturmak üzere dosya *launch.vs.js* düzenleyebilirsiniz. Dosyayı kaydettiğinizde, Visual Studio **Başlangıç öğesi** açılan menüsünde her yeni yapılandırma için bir giriş oluşturur.

## <a name="reference-keys-in-cmakesettingsjson"></a>CMakeSettings.jsiçindeki başvuru anahtarları

Dosyadaki bir *CMakeSettings.js* herhangi bir anahtara başvurmak için, `cmake.` *launch.vs.jsüzerine* sonuna ekleyin. Aşağıdaki örnek,  `remoteCopySources` Şu anda seçili olan yapılandırma için *CMakeSettings.json* dosyasındaki anahtarın değerini gösteren basit birlaunch.vs.jsdosyası gösterir:

```json
{
  "version": "0.2.1",
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

*CMakeSettings.jsüzerinde* tanımlanan **ortam değişkenleri** , sözdizimi kullanılarak launch.vs.jsde kullanılabilir `${env.VARIABLE_NAME}` . Visual Studio 2019 sürüm 16,4 ve sonraki sürümlerinde, hata ayıklama hedefleri *üzerindeCMakeSettings.js* belirttiğiniz ortam kullanılarak otomatik olarak başlatılır. Bir ortam değişkenini **null** olarak ayarlayarak ayarı yapabilirsiniz.

## <a name="launchvsjson-reference"></a>Başvuruya Launch.vs.js

Tüm hata ayıklama senaryolarınızı desteklemek için özelliklerde birçok *launch.vs.js* vardır. Aşağıdaki özellikler, uzak ve yerel tüm hata ayıklama yapılandırmalarında ortaktır:

- `projectTarget`: Proje oluşturulurken çağrılacak CMake hedefini belirtir. **Hata Ayıkla menüsünde** veya **hedefler görünümünden** *launch.vs.js* girerseniz, Visual Studio oto bu özelliği doldurur. Bu değer, **Başlangıç öğesi** açılan listesinde listelenen mevcut bir hata ayıklama hedefinin adıyla eşleşmelidir.

- `env`: Sözdizimi kullanılarak eklenecek ek ortam değişkenleri:

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`: Hata ayıklamak için programa geçirilen komut satırı bağımsız değişkenleri.

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>Uzak projeler ve WSL için başvuru Launch.vs.js

Visual Studio 2019 sürüm 16,6 ' de, `type: cppgdb` uzak sistemlerde ve WSL 'de hata ayıklamayı basitleştirmek için yeni bir hata ayıklama yapılandırması ekledik. Eski hata ayıklama yapılandırmalarının `type: cppdbg` desteklenmeye devam ediyor.

### <a name="configuration-type-cppgdb"></a>Yapılandırma türü `cppgdb`

- `name`: **Başlangıç öğesi** açılan menüsünde yapılandırmayı tanımlayacak kolay bir ad.
- `project`: Proje dosyasının göreli yolunu belirtir. Normal olarak, CMake projesinde hata ayıklarken bu yolu değiştirmeniz gerekmez.
- `projectTarget`: Proje oluşturulurken çağrılacak CMake hedefini belirtir. **Hata Ayıkla menüsünde** veya **hedefler görünümünden** *launch.vs.js* girerseniz, Visual Studio oto bu özelliği doldurur. Bu hedef değer, **Başlangıç öğesi** açılan listesinde listelenen mevcut bir hata ayıklama hedefinin adıyla eşleşmelidir.
- `debuggerConfiguration`: Hangi hata ayıklama varsayılan değerlerini kullanacağını gösterir. Visual Studio 2019 sürüm 16,6 ' de geçerli tek seçenek `gdb` . Visual Studio 2019 sürüm 16,7 veya üzeri de desteklenir `gdbserver` .
- `args`: Başlatma sırasında hata ayıklanan programa geçirilen komut satırı bağımsız değişkenleri.
- `env`: Hata ayıklamakta olan programa başka ortam değişkenleri geçirildi. Örneğin, `{"DISPLAY": "0.0"}`.
- `processID`: Eklenecek Linux işlem KIMLIĞI. Yalnızca uzak bir işleme eklenirken kullanılır. Daha fazla bilgi için bkz. [GDB kullanarak işlemlere ekleme sorunlarını giderme](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

#### <a name="additional-options-for-the-gdb-configuration"></a>Yapılandırma için ek seçenekler `gdb`

- `program`: Varsayılan olarak olur `"${debugInfo.fullTargetPath}"` . Hata ayıklaması yapılacak uygulamanın UNIX yolu. Yalnızca derleme veya dağıtım konumundaki hedef yürütülebilir dosyadan farklıysa gereklidir.
- `remoteMachineName`: Varsayılan olarak olur `"${debugInfo.remoteMachineName}"` . Hata ayıklama için programı barındıran uzak sistemin adı. Yalnızca yapı sisteminden farklıysa gereklidir. [Bağlantı yöneticisinde](../linux/connect-to-your-remote-linux-computer.md)mevcut bir giriş olmalıdır. Var olan tüm uzak bağlantıların listesini görüntülemek için **CTRL + boşluk** tuşlarına basın.
- `cwd`: Varsayılan olarak olur `"${debugInfo.defaultWorkingDirectory}"` . Çalıştıran uzak sistemdeki dizinin UNIX yolu `program` . Dizinin var olması gerekir.
- `gdbpath`: Varsayılan olarak olur `/usr/bin/gdb` . `gdb`Hata ayıklama için kullanılan tam UNIX yolu. Yalnızca özel bir sürümü kullanılıyorsa gereklidir `gdb` .
- `preDebugCommand`: Çağırma sonrasında hemen çalıştırılacak bir Linux komutu `gdb` . `gdb` Komut tamamlanana kadar başlatılmaz. Yürütmeden önce bir betiği çalıştırmak için seçeneğini kullanabilirsiniz `gdb` .

#### <a name="additional-options-allowed-with-the-gdbserver-configuration-167-or-later"></a>Yapılandırmaya izin verilen ek seçenekler `gdbserver` (16,7 veya üzeri)

- `program`: Varsayılan olarak olur `"${debugInfo.fullTargetPath}"` . Hata ayıklaması yapılacak uygulamanın UNIX yolu. Yalnızca derleme veya dağıtım konumundaki hedef yürütülebilir dosyadan farklıysa gereklidir.

  > [!TIP]
  > Dağıtım henüz yerel çapraz derleme senaryolarında desteklenmiyor. Windows üzerinde çapraz derleme yapıyorsanız (örneğin, Windows 'da bir Linux ARM yürütülebilir dosyası oluşturmak için bir çapraz derleyicisini kullanarak), `program` hata ayıklamadan önce, ikili dosyayı uzak ARM makinesinde belirtilen konuma el ile kopyalamanız gerekir.

- `remoteMachineName`: Varsayılan olarak olur `"${debugInfo.remoteMachineName}"` . Hata ayıklama için programı barındıran uzak sistemin adı. Yalnızca yapı sisteminden farklıysa gereklidir. [Bağlantı yöneticisinde](../linux/connect-to-your-remote-linux-computer.md)mevcut bir giriş olmalıdır. Var olan tüm uzak bağlantıların listesini görüntülemek için **CTRL + boşluk** tuşlarına basın.
- `cwd`: Varsayılan olarak olur `"${debugInfo.defaultWorkingDirectory}"` . Çalıştıran uzak sistemdeki dizinin tam UNIX yolu `program` . Dizinin var olması gerekir.
- `gdbPath`: Varsayılan olarak olur `${debugInfo.vsInstalledGdb}` . `gdb`Hata ayıklama için kullanılan tam Windows yolu. , `gdb` C/C++ iş yüküyle Linux geliştirmeyle birlikte yüklenir.
- `gdbserverPath`: Varsayılan olarak olur `usr/bin/gdbserver` . `gdbserver`Hata ayıklama için kullanılan tam UNIX yolu.
- `preDebugCommand`: Başlatmadan hemen önce çalıştırılacak bir Linux komutu `gdbserver` . `gdbserver` Komut tamamlanana kadar başlatılmaz.

#### <a name="deployment-options"></a>Dağıtım seçenekleri

Derleme makinenizi (CMakeSettings.jsüzerinde tanımlanmıştır) uzaktan hata ayıklama makinenizden ayırmak için aşağıdaki seçenekleri kullanın.

- `remoteMachineName`: Uzaktan hata ayıklama makinesi. Yalnızca derleme makinesinden farklıysa gereklidir. [Bağlantı yöneticisinde](../linux/connect-to-your-remote-linux-computer.md)mevcut bir giriş olmalıdır. Var olan tüm uzak bağlantıların listesini görüntülemek için **CTRL + boşluk** tuşlarına basın.
- `disableDeploy`: Varsayılan olarak olur **`false`** . Derleme/hata ayıklama ayrımı devre dışı olup olmadığını gösterir. Ne zaman **`false`** , bu seçenek derleme ve hata ayıklamanın iki ayrı makinede oluşmasına izin verir.
- `deployDirectory`: Yürütülebilir dosyanın kopyalandığı dizinin tam UNIX yolu `remoteMachineName` .
- `deploy`: Gelişmiş dağıtım ayarlarından oluşan bir dizi. Bu ayarları yalnızca dağıtım işlemi üzerinde daha ayrıntılı denetim sağlamak istediğinizde yapılandırmanız gerekir. Varsayılan olarak, yalnızca hata ayıklama işlemi için gereken dosyalar uzaktan hata ayıklama makinesine dağıtılır.
  - `sourceMachine`: Dosya veya dizinin kopyalandığı makine. Bağlantı Yöneticisi 'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl + Space** tuşlarına basın. WSL üzerinde yerel olarak oluşturulurken Bu seçenek yoksayılır.
  - `targetMachine`: Dosya veya dizinin kopyalandığı makine. Bağlantı Yöneticisi 'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl + Space** tuşlarına basın.
  - `sourcePath`: Üzerindeki dosya veya dizin konumu `sourceMachine` .
  - `targetPath`: Üzerindeki dosya veya dizin konumu `targetMachine` .
  - `deploymentType`: Dağıtım türünün açıklaması. `LocalRemote` ve `RemoteRemote` desteklenir. `LocalRemote` , yerel dosya sisteminden `remoteMachineName` *üzerindelaunch.vs.js* tarafından belirtilen uzak sisteme kopyalama anlamına gelir. `RemoteRemote`*CMakeSettings.js* ' de belirtilen uzak yapı sisteminden *launch.vs.jsüzerinde* belirtilen farklı uzak sisteme kopyalama anlamına gelir.
  - `executable`: Dağıtılan dosyanın yürütülebilir olup olmadığını gösterir.

### <a name="execute-custom-gdb-commands"></a>Özel `gdb` komutları yürütme

Visual Studio `gdb` temel alınan hata ayıklayıcıyla doğrudan etkileşimde bulunmak için özel komutların yürütülmesini destekler. Daha fazla bilgi için bkz. [özel `gdb` lldb komutlarını yürütme](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands).

### <a name="enable-logging"></a>Günlü kaydını etkinleştir

Hangi komutların gönderileceğini `gdb` , hangi çıktının `gdb` geri döndüğünü ve her komutun ne kadar sürdüğünü görmek Için mıengine günlüğünü etkinleştirin. [Daha fazla bilgi edinin](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>Yapılandırma türü `cppdbg`

Yapılandırma türü kullanılarak, uzak bir sistemde veya WSL 'de hata ayıklanırken aşağıdaki seçenekler kullanılabilir `cppdbg` . Visual Studio 2019 sürüm 16,6 veya sonraki sürümlerde yapılandırma türü `cppgdb` önerilir.

- `name`: **Başlangıç öğesi** açılan menüsünde yapılandırmayı tanımlayacak kolay bir ad.

- `project`: Proje dosyasının göreli yolunu belirtir. Normal olarak, CMake projesinde hata ayıklarken bu değeri değiştirmeniz gerekmez.

- `projectTarget`: Proje oluşturulurken çağrılacak CMake hedefini belirtir. **Hata Ayıkla menüsünde** veya **hedefler görünümünden** *launch.vs.js* girerseniz, Visual Studio oto bu özelliği doldurur. Bu değer, **Başlangıç öğesi** açılan listesinde listelenen mevcut bir hata ayıklama hedefinin adıyla eşleşmelidir.

- `args`: Başlatma sırasında hata ayıklanan programa geçirilen komut satırı bağımsız değişkenleri.

- `processID`: Eklenecek Linux işlem KIMLIĞI. Yalnızca uzak bir işleme eklenirken kullanılır. Daha fazla bilgi için bkz. [GDB kullanarak işlemlere ekleme sorunlarını giderme](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB).

- `program`: Varsayılan olarak olur `"${debugInfo.fullTargetPath}"` . Hata ayıklaması yapılacak uygulamanın UNIX yolu. Yalnızca derleme veya dağıtım konumundaki hedef yürütülebilir dosyadan farklıysa gereklidir.

- `remoteMachineName`: Varsayılan olarak olur `"${debugInfo.remoteMachineName}"` . Hata ayıklama için programı barındıran uzak sistemin adı. Yalnızca yapı sisteminden farklıysa gereklidir. [Bağlantı yöneticisinde](../linux/connect-to-your-remote-linux-computer.md)mevcut bir giriş olmalıdır. Var olan tüm uzak bağlantıların listesini görüntülemek için **CTRL + boşluk** tuşlarına basın.

- `cwd`: Varsayılan olarak olur `"${debugInfo.defaultWorkingDirectory}"` . Çalıştıran uzak sistemdeki dizinin tam UNIX yolu `program` . Dizinin var olması gerekir.

- `environment`: Hata ayıklamakta olan programa başka ortam değişkenleri geçirildi. Örneğin,

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

- `pipeArgs`: Bağlantıyı yapılandırmak için kanal programına geçirilen komut satırı bağımsız değişkenlerinin dizisi. Kanal programı, Visual Studio ve arasında standart giriş/çıkış geçişi için kullanılır `gdb` . CMake projelerinde hata ayıklanırken bu dizinin çoğu **özelleştirilmek zorunda değildir** . Özel durum, `${debuggerCommand}` uzak sistemde başlatılan ' dır `gdb` . Bu, şu şekilde değiştirilebilir:

  - Linux sisteminizde ortam değişkeni görüntüleme değerini dışarı aktarın. Aşağıdaki örnekte bu değer `:1` .

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

  - Yürütmeden önce bir komut dosyası çalıştırın `gdb` . Betikte yürütme izinlerinin ayarlandığından emin olun.

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

- `stopOnEntry`: İşlem başlatıldıktan hemen sonra kesmenin yapılıp yapılmayacağını belirten bir Boole değeri. Varsayılan değer false.

- `visualizerFile`: Bu işlemde hata ayıklanırken kullanılacak bir [. natvis dosyası](/visualstudio/debugger/create-custom-views-of-native-objects) . Bu seçenek, düzgün yazdırma ile uyumlu değildir `gdb` . `showDisplayString`Bu özelliği ayarladığınızda de ayarlanır.

- `showDisplayString`: Bir, belirtildiğinde, görüntüleme dizesini sağlayan bir Boole değeri `visualizerFile` . Bu seçeneğin ayarlanması **`true`** hata ayıklama sırasında daha yavaş performansa neden olabilir.

- `setupCommands`: `gdb` Temel alınan hata ayıklayıcıyı ayarlamak için yürütülecek bir veya daha fazla komut (ler).

- `miDebuggerPath`: Tam yolu `gdb` . Belirtilmediğinde, Visual Studio hata ayıklayıcı için önce yolu arar.

- Son olarak, yapılandırma türü için tanımlanan tüm dağıtım seçenekleri `cppgdb` `cppdbg` yapılandırma türü tarafından da kullanılabilir.

### <a name="debug-using-gdbserver"></a>Kullanarak hata ayıkla `gdbserver`

`cppdbg`Yapılandırmayı kullanarak hata ayıklama için yapılandırabilirsiniz `gdbserver` . Microsoft C++ Team blog postasında [hata ayıklama Linux CMake projelerinde `gdbserver` ](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)daha fazla ayrıntı ve örnek başlatma yapılandırması bulabilirsiniz.

::: moniker-end

::: moniker range=">=msvc-150"

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da CMake projeleri](cmake-projects-in-visual-studio.md)\
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)\
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)\
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
[Linux projenizi dağıtın, çalıştırın ve hatalarını ayıklayın](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)

::: moniker-end
