---
title: Visual Studio'da CMake hata ayıklama oturumlarını yapılandırın
description: CMake hata ayıklama ayarlarını yapılandırmak için Visual Studio'nun nasıl kullanılacağını açıklar.
ms.date: 04/02/2020
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 8364e5b3dd3316a4ed7e754a104a14373040aa6e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328835"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake hata ayıklama oturumlarını yapılandırma

::: moniker range="vs-2015"

Yerel CMake desteği Visual Studio 2017 ve sonraki yıllarda mevcuttur. Bu sürümlere ait belgeleri görmek için, bu makalenin Visual Studio **Sürüm** seçici denetimini Visual Studio 2017 veya Visual Studio 2019 olarak ayarlayın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker-end

::: moniker range=">=vs-2017"

Tüm çalıştırılabilir CMake **hedefleri, Genel** araç çubuğundaki **Başlangıç Öğesi** açılır açılır yerinde gösterilir. Hata ayıklama oturumunu başlatmak ve hata ayıklama başlatın.

![CMake başlangıç öğesi açılır](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılır")

Çözüm Gezgini'nden bir hata ayıklama oturumu da başlatabilirsiniz. İlk olarak, **Çözüm Gezgini** penceresinde **CMake Targets View'a** geçin.

![CMake hedefleri görünüm düğmesi](media/cmake-targets-view.png  "CMake Hedefleri Görünüm menü öğesi")

Ardından, çalıştırılabilir bir sağ tıklatın ve **Hata Ayıklama**seçin. Bu komut, etkin yapılandırmanıza göre seçili hedefin hata ayıklamaya otomatik olarak başlar.

## <a name="customize-debugger-settings"></a>Hata ayıklama ayarlarını özelleştirme

Projenizdeki herhangi bir çalıştırılabilir CMake hedefi için hata ayıklama ayarlarını özelleştirebilirsiniz. Proje kökünüzdeki bir *`.vs`* klasörde bulunan *launch.vs.json*adlı bir yapılandırma dosyasında bulunurlar. Başlatma yapılandırma dosyası, hata ayıklama kurulum ayrıntılarınızı yapılandırıp kaydedebilirsiniz, çünkü çoğu hata ayıklama senaryosunda yararlıdır. Bu dosyanın üç giriş noktası vardır:

- **Hata Ayıklama Menüsü:** Etkin hata ayıklama hedefinize özgü hata ayıklama yapılandırmasını özelleştirmek için ana menüden **${activeDebugTarget} için Hata** Ayıklama > ve Başlatma Ayarları'nı seçin. Seçili bir hata ayıklama hedefiniz yoksa, bu seçenek gri renktedir.

![Hata ayıklama menü giriş noktası](media/cmake-debug-menu.png "Hata ayıklama menü giriş noktası")

- **Hedef Görünümü:** Çözüm Gezgini'nde **Hedef Görünümü'ne** gidin. Ardından, hata ayıklama hedefine sağ tıklayın ve seçili hedefe özgü hata ayıklama yapılandırmasını özelleştirmek için **Hata Ayıklama Yapılandırması Ekle'yi** seçin.

![Hedefler bakış giriş noktası](media/cmake-targets-add-debug-configuration.png "Hedefler bakış giriş noktası")

- **Kök CMakeLists.txt:** Bir kök *CMakeLists.txt'ye* sağ tıklayın ve Hata **Ayıklama** iletişim kutusunu seç'i açmak için **Hata Ayıklama Yapılandırması Ekle'yi** seçin. İletişim *kutusu, her* tür hata ayıklama yapılandırması eklemenize olanak sağlar, ancak `projectTarget` özellik üzerinden çağırmak için CMake hedefini el ile belirtmeniz gerekir.

![Hata ayıklama iletişim kutusu seçin](media/cmake-select-a-debugger.png "Hata ayıklama iletişim kutusu seçin")

Herhangi bir sayıda CMake hedefi için hata ayıklama yapılandırmaları oluşturmak için *launch.vs.json* dosyasını düzenleyebilirsiniz. Dosyayı kaydettiğinizde, Visual Studio **Başlangıç Öğesi** açılır açılır dosyasındaki her yeni yapılandırma için bir giriş oluşturur.

## <a name="reference-keys-in-cmakesettingsjson"></a>CMakeSettings.json'daki başvuru tuşları

*CMakeSettings.json* dosyasındaki herhangi bir `cmake.` anahtara başvurmak için *launch.vs.json'da*bu anahtara hazırlayın. Aşağıdaki örnek, şu anda seçili yapılandırma için *CMakeSettings.json* dosyasındaki `remoteCopySources` anahtarın değerini çeken basit bir *launch.vs.json* dosyasını gösterir:

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

*CMakeSettings.json'da* tanımlanan ortam `${env.VARIABLE_NAME}` **değişkenleri** sözdizimi kullanılarak launch.vs.json'da da kullanılabilir. Visual Studio 2019 sürüm 16.4 ve sonraki sürümlerinde hata ayıklama hedefleri *CMakeSettings.json'da*belirttiğiniz ortam kullanılarak otomatik olarak başlatılır. Bir ortam değişkenini **null**olarak ayarlayarak ayarlayabilirsiniz.

## <a name="launchvsjson-reference"></a>Launch.vs.json referans

Tüm hata ayıklama senaryolarınızı destekleyen birçok *launch.vs.json* özelliği vardır. Aşağıdaki özellikler, hem uzak hem de yerel tüm hata ayıklama yapılandırmaları için ortaktur:

- `projectTarget`: Projeyi kurarken çağırmak için CMake hedefini belirtir. Visual **Studio, Hata Ayıklama Menüsünden** veya **Hedef Görünümü'nden** *launch.vs.json* girerseniz bu özelliği otomatik olarak otomatik olarak doldurur. Bu değer, **Başlangıç Öğesi** açılır listesinde listelenen varolan bir hata ayıklama hedefinin adı ile eşleşmelidir.

- `env`: Sözdizimini kullanarak eklenecek ek ortam değişkenleri:

  ```json
  "env": {
        "DEBUG_LOGGING_LEVEL": "trace;info",
        "ENABLE_TRACING": "true"
      }
  ```

- `args`: Komut satırı bağımsız değişkenleri hata ayıklamak için programa geçti.

## <a name="launchvsjson-reference-for-remote-projects-and-wsl"></a>Uzak projeler ve WSL için Launch.vs.json referans

Visual Studio 2019 sürüm 16.6'da, uzak `type: cppgdb` sistemlerde ve WSL'de hata ayıklamayı kolaylaştırmak için yeni bir hata ayıklama yapılandırması ekledik. Eski hata ayıklama `type: cppdbg` yapılandırmaları hala desteklenir.

### <a name="configuration-type-cppgdb"></a>Yapılandırma türü`cppgdb`

- `name`: **Başlangıç Öğesi** açılır düşüşündeki yapılandırmayı tanımlamak için uygun bir ad.
- `project`: Proje dosyasına göreli yolu belirtir. Normalde, bir CMake projesini hata ayıklarken bu yolu değiştirmeniz gerekmez.
- `projectTarget`: Projeyi kurarken çağırmak için CMake hedefini belirtir. Visual **Studio, Hata Ayıklama Menüsünden** veya **Hedef Görünümü'nden** *launch.vs.json* girerseniz bu özelliği otomatik olarak otomatik olarak doldurur. Bu hedef değer, **Başlangıç Öğesi** açılır listesinde listelenen varolan bir hata ayıklama hedefinin adı ile eşleşmelidir.
- `debuggerConfiguration`: Kullanılacak hata ayıklama varsayılan değerleri kümesini gösterir. Visual Studio 2019 sürüm 16.6'da `gdb`tek geçerli seçenek . Önceki sürümler `gdbserver`de destekler.
- `args`: Komut satırı bağımsız değişkenleri, başlangıç tarihinde debugged olan programa geçti.
- `env`: Programa aktarılan ek ortam değişkenleri debugged ediliyor. Örneğin, `{"DISPLAY": "0.0"}`.
- `processID`: Linux işlem kimliği eklemek için. Yalnızca uzak bir işleme bağlanırken kullanılır. Daha fazla bilgi için [GDB kullanarak işlemlere iliştirilen Sorun Giderme'ye](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)bakın.

#### <a name="additional-options-for-the-gdb-configuration"></a>`gdb` Yapılandırma için ek seçenekler

- `program`: Varsayılan `"${debugInfo.fullTargetPath}"`değer. Hata ayıklama uygulamasına Unix yolu. Yalnızca yapı veya dağıtım konumunda yürütülebilir hedeften farklıysa gereklidir.
- `remoteMachineName`: Varsayılan `"${debugInfo.remoteMachineName}"`değer. Hata ayıklamak için programı barındıran uzak sistemin adı. Yalnızca yapı sisteminden farklıysa gereklidir. [Bağlantı Yöneticisi'nde](../linux/connect-to-your-remote-linux-computer.md)varolan bir giriş olmalıdır. Varolan tüm uzak bağlantıların listesini görüntülemek için **Ctrl+Space** tuşuna basın.
- `cwd`: Varsayılan `"${debugInfo.defaultWorkingDirectory}"`değer. Çalıştırılabildiği uzak sistemdeki `program` dizine Unix yolu. Dizinin var olması gerekir.
- `gdbpath`: Varsayılan `/usr/bin/gdb`değer. Hata ayıklamak için `gdb` kullanılan tam Unix yolu. Yalnızca `gdb`özel bir sürümünü kullanıyorsanız gereklidir.
- `preDebugCommand`: Bir Linux komutu hemen `gdb`önce çağıran çalıştırmak için . `gdb`komut tamamlanana kadar başlamaz. Yürütmeden önce bir komut dosyası çalıştırmak `gdb`için seçeneği kullanabilirsiniz.

#### <a name="deployment-options"></a>Dağıtım seçenekleri

Yapı makinenizi (CMakeSettings.json'da tanımlanan) uzaktan hata ayıklama makinenizden ayırmak için aşağıdaki seçenekleri kullanın.

- `remoteMachineName`: Uzaktan hata ayıklama makinesi. Yalnızca yapı makinesinden farklıysa gereklidir. [Bağlantı Yöneticisi'nde](../linux/connect-to-your-remote-linux-computer.md)varolan bir giriş olmalıdır. Varolan tüm uzak bağlantıların listesini görüntülemek için **Ctrl+Space** tuşuna basın.
- `disableDeploy`: Varsayılan `false`değer. Yapı/hata ayıklama ayırmanın devre dışı bırakıldığını gösterir. Ne `false`zaman , bu seçenek yapı ve hata ayıklama iki ayrı makinelerde oluşmasını sağlar.
- `deployDirectory`: Tam Unix yolu üzerinde `remoteMachineName` dizin üzerinde yürütülebilir kopyalanır alır.
- `deploy`: Bir dizi gelişmiş dağıtım ayarı. Bu ayarları yalnızca dağıtım işlemi üzerinde daha ayrıntılı denetim istediğinizde yapılandırmanız gerekir. Varsayılan olarak, yalnızca işlemin hata ayıklama için gerekli dosyaları uzak hata ayıklama makinesine dağıtıldı.
  - `sourceMachine`: Dosya nın veya dizinin kopyalandığı makine. Bağlantı Yöneticisi'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl+Space** tuşuna basın. YEREL olarak WSL'de bina yaparken, bu seçenek yoksayılır.
  - `targetMachine`: Dosya nın veya dizinin kopyalandığı makine. Bağlantı Yöneticisi'nde depolanan tüm uzak bağlantıların listesini görüntülemek için **Ctrl+Space** tuşuna basın.
  - `sourcePath`: Dosya veya dizin `sourceMachine`konumu.
  - `targetPath`: Dosya veya dizin `targetMachine`konumu.
  - `deploymentType`: Dağıtım türünün açıklaması. `LocalRemote`ve `RemoteRemote` desteklenir. `LocalRemote``remoteMachineName` *başlat.vs.json'da*belirtilen uzak sisteme yerel dosya sisteminden kopyalama anlamına gelir. `RemoteRemote`*CMakeSettings.json'da* belirtilen uzaktan yapı sisteminden *launch.vs.json'da*belirtilen farklı uzak sisteme kopyalama anlamına gelir.
  - `executable`: Dağıtılan dosyanın yürütülebilir olup olmadığını gösterir.

### <a name="execute-custom-gdb-commands"></a>Özel `gdb` komutları yürütme

Visual Studio, altta `gdb` yatan hata ayıklama yla doğrudan etkileşimde kalmak için özel komutların yürütülmesini destekler. Daha fazla bilgi için [ `gdb` bkz.](https://github.com/microsoft/MIEngine/wiki/Executing-custom-gdb-lldb-commands)

### <a name="enable-logging"></a>Günlü kaydını etkinleştir

Hangi komutların gönderildiğini, hangi çıktının `gdb` `gdb` döndüğünü ve her komutun ne kadar sürdüğünü görmek için MIEngine günlüğe kaydetmeyi etkinleştirin. [Daha fazlasını öğrenin](https://github.com/microsoft/MIEngine/wiki/Logging)

### <a name="configuration-type-cppdbg"></a>Yapılandırma türü`cppdbg`

Aşağıdaki seçenekler, `cppdbg` yapılandırma türünü kullanarak uzak bir sistemde veya WSL'de hata ayıklama yaparken kullanılabilir. Visual Studio 2019 sürüm 16.6 veya `cppgdb` sonraki sürümde yapılandırma türü önerilir.

- `name`: **Başlangıç Öğesi** açılır düşüşündeki yapılandırmayı tanımlamak için uygun bir ad.

- `project`: Proje dosyasına göreli yolu belirtir. Normalde, bir CMake projesini hata ayıklarken bu değeri değiştirmeniz gerekmez.

- `projectTarget`: Projeyi kurarken çağırmak için CMake hedefini belirtir. Visual **Studio, Hata Ayıklama Menüsünden** veya **Hedef Görünümü'nden** *launch.vs.json* girerseniz bu özelliği otomatik olarak otomatik olarak doldurur. Bu değer, **Başlangıç Öğesi** açılır listesinde listelenen varolan bir hata ayıklama hedefinin adı ile eşleşmelidir.

- `args`: Komut satırı bağımsız değişkenleri, başlangıç tarihinde debugged olan programa geçti.

- `processID`: Linux işlem kimliği eklemek için. Yalnızca uzak bir işleme bağlanırken kullanılır. Daha fazla bilgi için [GDB kullanarak işlemlere iliştirilen Sorun Giderme'ye](https://github.com/Microsoft/MIEngine/wiki/Troubleshoot-attaching-to-processes-using-GDB)bakın.

- `program`: Varsayılan `"${debugInfo.fullTargetPath}"`değer. Hata ayıklama uygulamasına Unix yolu. Yalnızca yapı veya dağıtım konumunda yürütülebilir hedeften farklıysa gereklidir.

- `remoteMachineName`: Varsayılan `"${debugInfo.remoteMachineName}"`değer. Hata ayıklamak için programı barındıran uzak sistemin adı. Yalnızca yapı sisteminden farklıysa gereklidir. [Bağlantı Yöneticisi'nde](../linux/connect-to-your-remote-linux-computer.md)varolan bir giriş olmalıdır. Varolan tüm uzak bağlantıların listesini görüntülemek için **Ctrl+Space** tuşuna basın.

- `cwd`: Varsayılan `"${debugInfo.defaultWorkingDirectory}"`değer. Çalıştırılanın uzak `program` sistemde dizine tam Unix yolu. Dizinin var olması gerekir.

- `environment`: Programa aktarılan ek ortam değişkenleri debugged ediliyor. Örneğin,

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

- `pipeArgs`: Bağlantıyı yapılandırmak için boru programına geçirilen bir dizi komut satırı bağımsız değişkeni. Boru programı Visual Studio ve `gdb`. CMake projelerini hata ayıklarken bu dizinin çoğunun **özelleştirilmesi gerekmez.** Bunun `${debuggerCommand}`istisnası, uzak `gdb` sistemde başlatılan durumdur. Şu şekilde değiştirilebilir:

  - Linux sisteminizde ortam değişkeni DISPLAY değerini dışa aktarın. Aşağıdaki örnekte, bu `:1`değer .

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

  - Yürütmeden önce bir `gdb`komut dosyası çalıştırın. Yürütme izinlerinin komut dosyanızda ayarlandığından emin olun.

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

- `stopOnEntry`: İşlem başlatılır başlatılır başlatmaz kırılıp kırılmayacağını belirten bir boolean. Varsayılan değer false.

- `visualizerFile`: Bu işlemi hata ayıklarken kullanılacak [bir .natvis dosyası.](/visualstudio/debugger/create-custom-views-of-native-objects) Bu seçenek, güzel `gdb` yazdırma ile uyumsuzdur. Bu `showDisplayString` özelliği ayarladığınızda da ayarlayın.

- `showDisplayString`: A belirtildiğinde ekran dizesini `visualizerFile` etkinleştiren bir boolean. Bu seçeneği `true` hata ayıklama sırasında daha yavaş performansa neden olacak şekilde ayarlamak.

- `setupCommands`: Bir `gdb` veya daha fazla komut(lar) yürütmek için, altta yatan hata ayıklayıcı kurmak için.

- `miDebuggerPath`: Tam yol `gdb`. Belirtilmemiş olduğunda, Visual Studio hata ayıklama için önce PATH'i arar.

- Son olarak, yapılandırma türü için `cppgdb` tanımlanan dağıtım seçeneklerinin `cppdbg` tümü yapılandırma türüne göre de kullanılabilir.

### <a name="debug-using-gdbserver"></a>Hata ayıklama kullanarak`gdbserver`

Yapılandırmayı `cppdbg` hata ayıklamak için `gdbserver`yapılandırabilirsiniz. Daha fazla ayrıntı ve Microsoft C++ Team Blog yazısı [ile `gdbserver`Linux CMake Projeleri Debugging ](https://devblogs.microsoft.com/cppblog/debugging-linux-cmake-projects-with-gdbserver/)bir örnek başlatma yapılandırma bulabilirsiniz.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da CMake projeleri](cmake-projects-in-visual-studio.md)\
[Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanın](../linux/connect-to-your-remote-linux-computer.md)\
[CMake yapı ayarlarını özelleştirin](customize-cmake-settings.md)\
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
[Linux projenizi dağıtma, çalıştırma ve hata ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)

::: moniker-end
