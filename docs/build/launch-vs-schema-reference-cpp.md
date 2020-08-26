---
title: Şema başvurusunda launch.vs.js(C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: 1161e8fa8ac3751ca8cc2b96ec063cd6063bb245
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88841993"
---
# <a name="launchvsjson-schema-reference-c"></a>Şema başvurusunda launch.vs.js(C++)

Hata ayıklama parametrelerini yapılandırmak için *launch.vs.js* dosyasını kullanın. Dosyasını oluşturun. **Çözüm Gezgini** bir çalıştırılabilir dosyaya sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. Projenizle en yakından eşleşen seçeneği seçin ve ardından yapılandırmayı gerektiği şekilde değiştirmek için aşağıdaki özellikleri kullanın. CMake projelerinde hata ayıklama hakkında daha fazla bilgi için bkz. [CMake hata ayıklama oturumlarını yapılandırma](/cpp/build/configure-cmake-debugging-sessions).

## <a name="default-properties"></a>Varsayılan Özellikler

|Özellik|Tür|Description|
|-|-|-|
|`name`|dize|Hata ayıklama hedefi açılan menüsünde girdinin adını belirtir.|
|`type`|string|Projenin bir dll veya. exe olup olmadığını belirtir (varsayılan olarak. exe)|
|`project`|string|Proje dosyasının göreli yolunu belirtir.|
|`projectTarget`|string|Oluşturma sırasında çağrılan isteğe bağlı hedefi belirtir `project` . Bu `projectTarget` zaten mevcut olmalı ve **hata ayıklama hedefi** açılan menüsünde adıyla eşleşmelidir.|
|`debugType`|string|Kod türüne göre hata ayıklama modunu belirtir (yerel, yönetilen veya karma). Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır. İzin verilen değerler: "Native", "Managed", "mixed".|
|`inheritEnvironments`|array|Birden çok kaynaktan devralınan bir ortam değişkenleri kümesini belirtir. Dosyalarda *CMakeSettings.js* veya *CppProperties.js* gibi bazı değişkenler tanımlayabilir ve bunları hata ayıklama bağlamı için kullanılabilir hale getirebilirsiniz.  **Visual Studio 16,4:**: söz dizimini kullanarak hedef başına temelinde ortam değişkenlerini belirtin `env.VARIABLE_NAME` . Bir değişkeni kaldırmak için, "null" olarak ayarlayın.|
|`args`|array|Başlatılan programa geçirilen komut satırı bağımsız değişkenlerini belirtir.|
|`currentDir`|string|Derleme hedefinin tam dizin yolunu belirtir. Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır.|
|`noDebug`|boolean|Başlatılan programda hata ayıklama yapılıp yapılmayacağını belirtir. Bu parametre için varsayılan değer **`false`** belirtilmemişse.|
|`stopOnEntry`|boolean|İşlem başlatıldığında ve hata ayıklayıcı iliştirip bu işlemin ne kadar kesmeyeceğini belirtir. Bu parametre için varsayılan değer **`false`** .|
|`remoteMachine`|string|Programın başlatıldığı uzak makinenin adını belirtir.|
|`env`|array| Özel ortam değişkenlerinin anahtar-değer listesini belirtir. env: {"myEnv": "myVal"}.|
|`portName`|string|Çalışan bir işleme eklenirken bağlantı noktasının adını belirtir.|
|`buildConfigurations`|array| Yapılandırmaların uygulanacağı yapı modunun adını belirten bir anahtar-değer çifti. Örneğin, `Debug` veya `Release` ve seçili yapı moduna göre kullanılacak yapılandırma.

## <a name="c-linux-properties"></a>C++ Linux özellikleri

|Özellik|Tür|Description|
|-|-|-|
|`program`|dize|Uzak makinedeki program yürütülebilirinin tam yolu. CMake kullanılırken, makro `${debugInfo.fullTargetPath}` Bu alanın değeri olarak kullanılabilir.|
|`processId`|integer|Hata ayıklayıcıyı iliştirmek için isteğe bağlı işlem KIMLIĞI.|
|`sourceFileMap`|object|Hata ayıklama altyapısına geçirilen isteğe bağlı kaynak dosya eşlemeleri. Biçim: `{ "\<Compiler source location>": "\<Editor source location>" }` veya `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }` . Örnek: `{ "/home/user/foo": "C:\\foo" }` veya `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. Bkz. [kaynak dosya haritası seçenekleri](#source_file_map_options).|
|`additionalProperties`|string|SourceFileMapOptions biri. (Aşağıya bakın.)|
|`MIMode`|string|MIDebugEngine 'in bağlanacağı mı özellikli konsol hata ayıklayıcısı türünü gösterir. İzin verilen değerler "gdb", "lldb" dir.|
|`args`|array|Programa geçirilen komut satırı bağımsız değişkenleri.|
|`environment`|array|Program için ortama eklenecek ortam değişkenleri. Örnek: [{"Name": "SQUID", "Value": "Clad"}].|
|`targetArchitecture`|string|Hata ayıklanan mimarisi. Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır. İzin verilen değerler x86, ARM, arm64, MIPS, x64, AMD64, x86_64.|
|`visualizerFile`|string|Bu işlemde hata ayıklanırken kullanılacak. natvis dosyası. Bu seçenek, GDB düzgün yazdırma ile uyumlu değildir. Bu ayar kullanılıyorsa "showDisplayString" başlığına bakın.|
|`showDisplayString`|boolean|Bir Visualizerdosyası belirtildiğinde, showDisplayString Görüntüleme dizesini etkinleştirir. Bu seçeneği açmak hata ayıklama sırasında daha yavaş performans oluşmasına neden olabilir.|
|`remoteMachineName`|string|GDB 'yi barındıran uzak Linux makinesi ve hata ayıklamak için program. Yeni Linux makineleri eklemek için bağlantı yöneticisini kullanın. CMake kullanılırken, makro `${debugInfo.remoteMachineName}` Bu alanın değeri olarak kullanılabilir.|
|`cwd`|string|Uzak makinedeki hedefin çalışma dizini. CMake kullanılırken, makro `${debugInfo.defaultWorkingDirectory}` Bu alanın değeri olarak kullanılabilir. *CMakeLists.txt* dosyasında geçersiz kılınmadığı müddetçe, varsayılan değer uzak çalışma alanı köküdür.|
|`miDebuggerPath`|string|Mı özellikli hata ayıklayıcının (gdb gibi) yolu. Belirtilmediğinde, ilk olarak hata ayıklayıcı için yol arar.|
|`miDebuggerServerAddress`|string|Bağlanılacak mı özellikli hata ayıklayıcı sunucusunun ağ adresi. Örnek: localhost: 1234.|
|`setupCommands`|array|Temel alınan hata ayıklayıcıyı ayarlamak için yürütülecek bir veya daha fazla GDB/LLDB komutu. Örnek: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`. Bkz. [Kurulum komutlarını başlatma](#launch_setup_commands).|
|`customLaunchSetupCommands`|array|Sağlanmışsa, bu, bir hedefi diğer komutlarla başlatmak için kullanılan varsayılan komutları değiştirir. Örneğin, bir hedef işleme iliştirmek için bu "-target-Attach" olabilir. Boş bir komut listesi, başlatma komutlarının hata ayıklayıcıda komut satırı seçenekleri olarak sağlanmakta olduğu durumlarda yararlı olabilecek hiçbir şey ile birlikte değiştirilir. Örnek: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`.|
|`launchCompleteCommand`|string|Hata ayıklayıcı, hedef işlemin çalışmasına neden olacak şekilde tamamen ayarlandıktan sonra yürütülecek komut. İzin verilen değerler şunlardır "exec-Run", "exec-Continue", "none". Varsayılan değer "exec-Run" değeridir.|
|`debugServerPath`|string|Başlatılacak sunucuda hata ayıklama için isteğe bağlı tam yol. Varsayılan olarak null değerini alır.|
|`debugServerArgs`|string|İsteğe bağlı hata ayıklama sunucusu bağımsız değişkenleri. Varsayılan olarak null değerini alır.|
|`filterStderr`|boolean|Sunucu tarafından başlatılan model için stderr akışında arama yapın ve hata ayıklama çıkışı için günlük stderr. Varsayılan olarak olur **`false`** .|
|`coreDumpPath`|string|Belirtilen program için bir çekirdek döküm dosyasının isteğe bağlı tam yolu. Varsayılan olarak null değerini alır.|
externalConsole|boolean|True ise hata ayıklanan için bir konsol başlatılır. Varsa **`false`** , hiçbir konsol başlatılmaz. Varsayılan olarak olur **`false`** . NOTE: Bu seçenek, bazı durumlarda teknik nedenlerden dolayı yok sayılır.|
|`pipeTransport`|string|Mevcut olduğunda, hata ayıklayıcıya, Visual Studio ile mı etkin hata ayıklayıcı (gdb gibi) arasında standart giriş/çıkış geçişi yapan bir kanal olarak başka bir yürütülebilir dosyayı kullanarak uzak bir bilgisayara bağlanmasını söyler. İzin verilen değerler: bir veya daha fazla [kanal taşıma seçeneği](#pipe_transport_options).|

## <a name="launch-setup-commands"></a><a name="launch_setup_commands"></a> Kurulum komutlarını Başlat

Özelliği ile kullanılır `setupCommands` :

|Özellik|Tür|Description|
|-|-|-|
|`text`|dize|Yürütülecek hata ayıklayıcı komutu.|
|`description`|string|Komut için isteğe bağlı açıklama.|
|`ignoreFailures`|boolean|Doğru ise, komuttan gelen hataların yok sayılacak olması gerekir. Varsayılan olarak olur **`false`** .|

## <a name="pipe-transport-options"></a><a name = "pipe_transport_options"></a> Kanal taşıma seçenekleri

Özelliği ile kullanılır `pipeTransport` :

|Özellik|Tür|Description|
|-|-|-|
|`pipeCwd`|dize|Kanal programı için çalışma dizininin tam yolu.|
|`pipeProgram`|string|Yürütülecek tam kanal komutu.|
|`pipeArgs`|array|Bağlantıyı yapılandırmak için kanal programına geçirilen komut satırı bağımsız değişkenleri.|
|`debuggerPath`|string|Hedef makinedeki hata ayıklayıcının tam yolu; Örneğin,/usr/bin/gdb.|
|`pipeEnv`|object|Kanal programına geçirilen ortam değişkenleri.|
|`quoteArgs`|boolean|Bağımsız değişkenler tek tek karakterler içeriyorsa (boşluk veya sekmeler gibi) tırnak içine alınmalıdır mi? İse **`false`** , hata ayıklayıcı komutu artık otomatik olarak tırnak içine alınmaz. Varsayılan değer **`true`** .|

## <a name="source-file-map-options"></a><a name="source_file_map_options"></a> Kaynak dosya eşleme seçenekleri

Özelliği ile kullanın `sourceFileMap` :

|Özellik|Tür|Description|
|-|-|-|
|`editorPath`|dize|Bulacak düzenleyicinin kaynak kodunun konumu.|
|`useForBreakpoints`|boolean|Kesme noktaları ayarlanırken, bu kaynak eşlemesinin kullanılması gerekir. İse **`false`** , kesme noktalarını ayarlamak için yalnızca dosya adı ve satır numarası kullanılır. İse **`true`** , kesme noktaları dosyanın tam yolu ve yalnızca bu kaynak eşleme kullanıldığında satır numarası ile ayarlanır. Aksi takdirde, kesme noktaları ayarlanırken yalnızca dosya adı ve satır numarası kullanılacaktır. Varsayılan değer **`true`** .|
