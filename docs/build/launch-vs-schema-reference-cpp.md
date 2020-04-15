---
title: launch.vs.json şema referansı (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: ff4713642ab95a9bbc31f1a06236de459e53f9c3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323049"
---
# <a name="launchvsjson-schema-reference-c"></a>launch.vs.json şema referansı (C++)

Hata ayıklama parametrelerini yapılandırmak için *launch.vs.json* dosyasını kullanın. Dosyayı oluşturmak için. **Solution Explorer'da** çalıştırılabilir bir dosyaya sağ tıklayın ve **Hata Ayıklama ve Başlatma Ayarları'nı**seçin. Projenize en yakın eşleşen seçeneği seçin ve ardından yapılandırmayı gerektiği gibi değiştirmek için aşağıdaki özellikleri kullanın. CMake projelerinin hata ayıklama hakkında daha fazla bilgi için Bkz. [CMake hata ayıklama oturumlarını yapılandırın.](/cpp/build/configure-cmake-debugging-sessions)

## <a name="default-properties"></a>Varsayılan özellikler

||||
|-|-|-|
|**Özellik**|**Tür**|**Açıklama**|
|`name`|string|Hata Ayıklama hedef açılır düşüşündeki girişin adını belirtir.|
|`type`|string|Projenin dll veya .exe olup olmadığını belirtir (Varsayılan olarak .exe)|
|`project`|string|Proje dosyasına göreli yolu belirtir.|
|`projectTarget`|string|Bina inşa `project`ederken çağrılan isteğe bağlı hedefi belirtir. Bu `projectTarget` zaten var olmalı ve **Hata Ayıklama Hedef** açılır durumdaki adı eşleştirmelidir.|
|`debugType`|string|Hata ayıklama modunu kod türüne (yerel, yönetilen veya karışık) göre belirtir. Bu parametre ayarlanmadıkça bu otomatik olarak algılanır. İzin verilen değerler: "yerel", "yönetilen", "karışık".|
|`inheritEnvironments`|array|Birden çok kaynaktan devralınan bir ortam değişkenleri kümesini belirtir. *CMakeSettings.json* veya *CppProperties.json* gibi dosyalarda bazı değişkenleri tanımlayabilir ve bunları hata ayıklama bağlamında kullanılabilir hale getirebilirsiniz.  **Visual Studio 16.4:**: `env.VARIABLE_NAME` Sözdizimini kullanarak ortam değişkenlerini hedef başına belirtin. Bir değişkeni ayarlamak için "null" olarak ayarlayın.|
|`args`|array|Başlatılan programa geçirilen komut satırı bağımsız değişkenlerini belirtir.|
|`currentDir`|string|Hedef Oluştur'a giden tam dizin yolunu belirtir. Bu parametre ayarlanmadıkça bu otomatik olarak algılanır.|
|`noDebug`|boole|Başlatılan programın hata ayıklanıp ayıklanmayacağını belirtir. Bu parametrenin varsayılan `false` değeri belirtilmemişse.|
|`stopOnEntry`|boole|İşlem başlatılır başlatılır ve hata ayıklama takılır kısa bir süre içinde kırılıp kırılmayacağını belirtir. Bu parametrenin varsayılan `false`değeri .|
|`remoteMachine`|string|Programın başlatıldığı uzak makinenin adını belirtir.|
|`env`|array| Özel ortam değişkenlerinin anahtar değer listesini belirtir. env:{"myEnv":"myVal"}.|
|`portName`|string|Çalışan bir işleme iliştirirken bağlantı noktasının adını belirtir.|
|`buildConfigurations`|array| Yapılandırmaları uygulamak için yapı modunun adını belirten anahtar değer çifti. Örneğin, `Debug` veya `Release` ve seçili yapı moduna göre kullanılacak yapılandırmalar.

## <a name="c-linux-properties"></a>C++ Linux özellikleri

||||
|-|-|-|
|**Özellik**|**Tür**|**Açıklama**|
|`program`|string|Uzak makinede çalıştırılabilir programa tam yol. CMake kullanırken, `${debugInfo.fullTargetPath}` makro bu alanın değeri olarak kullanılabilir.|
|`processId`|integer|Hata ayıklamayı eklemek için isteğe bağlı işlem kimliği.|
|`sourceFileMap`|object|İsteğe bağlı kaynak dosya eşlemeleri hata ayıklama altyapısına geçti. `{ "\<Compiler source location>": "\<Editor source location>" }` Biçimlendirme: `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`veya . Örnek: `{ "/home/user/foo": "C:\\foo" }` veya `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. [Bkz. Kaynak dosya eşlemi seçenekleri.](#source_file_map_options)|
|`additionalProperties`|string|KaynakFileMapOptions biri. (Aşağıya bakın.)|
|`MIMode`|string|MIDebugEngine'in bağlanacak MI özellikli konsol hata ayıklama türünü gösterir. İzin verilen değerler "gdb", "lldb"dir.|
|`args`|array|Komut satırı bağımsız değişkenleri programa geçti.|
|`environment`|array|Program için ortama eklemek için ortam değişkenleri. Örnek: [ { "isim": "kalamar", "değer": "istiridye" } }.|
|`targetArchitecture`|string|Hata ayıklamanın mimarisi. Bu parametre ayarlanmadıkça bu otomatik olarak algılanır. İzin verilen değerler x86, kol, arm64, mips, x64, amd64, x86_64.|
|`visualizerFile`|string|.natvis dosyası bu işlemi hata ayıklarken kullanılacaktır. Bu seçenek GDB güzel baskı ile uyumlu değildir. Bu ayarı kullanıyorsanız "showDisplayString" adlı bakın.|
|`showDisplayString`|boole|VisualizerFile belirtildiğinde, showDisplayString ekran dizesini etkinleştirecektir. Bu seçeneğin açıkça çıkırılışhata hatası sırasında daha düşü|
|`remoteMachineName`|string|Hata ayıklamak için gdb ve program barındıran uzak Linux makinesi. Yeni Linux makineleri eklemek için Bağlantı Yöneticisi'ni kullanın. CMake kullanırken, `${debugInfo.remoteMachineName}` makro bu alanın değeri olarak kullanılabilir.|
|`cwd`|string|Uzak makinedeki hedefin çalışma dizini. CMake kullanırken, `${debugInfo.defaultWorkingDirectory}` makro bu alanın değeri olarak kullanılabilir. Varsayılan değer, *CMakeLists.txt* dosyasında geçersiz kılınmadığı sürece uzak çalışma alanı köküdür.|
|`miDebuggerPath`|string|MI etkin hata ayıklama (gdb gibi) yolu. Belirtilmemiş olduğunda, hata ayıklama için önce PATH'i arar.|
|`miDebuggerServerAddress`|string|Bağlanmak için MI etkin hata ayıklama sunucusunun ağ adresi. Örnek: localhost:1234.|
|`setupCommands`|array|Altta yatan hata ayıklayıcıyı ayarlamak için yürütülmesi gereken bir veya daha fazla GDB/LLDB komutu. Örnek: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`. Bkz. [Başlat kurulum komutları.](#launch_setup_commands)|
|`customLaunchSetupCommands`|array|Sağlanan, bu diğer bazı komutları ile bir hedef başlatmak için kullanılan varsayılan komutları değiştirir. Örneğin, bu bir hedef işlemine eklemek için "hedef ekleme" olabilir. Boş bir komut listesi, başlatma komutlarının yerini hiçbir şey olmadan alır ve hata ayıklama komut satırı seçenekleri olarak başlatma seçenekleri sağlanıyorsa yararlı olabilir. Örnek: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`.|
|`launchCompleteCommand`|string|Hata ayıklama tamamen ayarlandıktan sonra yürütülecek komut, hedef işlemin çalışmasına neden olmak için. İzin verilen değerler "exec-run", "exec-continue", "None" dır. Varsayılan değer "exec-run"dır.|
|`debugServerPath`|string|Başlatılan sunucu hata ayıklama için isteğe bağlı tam yol. Varsayılan olarak null.|
|`debugServerArgs`|string|İsteğe bağlı hata ayıklama sunucusu args. Varsayılan olarak null.|
|`filterStderr`|boole|Sunucu tarafından başlatılan desen için stderr akışını arayın ve çıktıyı hata ayıklamak için stderr'ı günlüğe kaydedin. Varsayılan `false`değer.|
|`coreDumpPath`|string|Belirtilen program için bir çekirdek dökümü dosyasına isteğe bağlı tam yol. Varsayılan olarak null.|
hariciKonsol|boole|Doğruysa, hata ayıklama için bir konsol başlatılır. Eğer `false`, hiçbir konsol başlatılır. Varsayılan `false`değer. NOT: Bu seçenek bazı durumlarda teknik nedenlerle yoksayılır.|
|`pipeTransport`|string|Bu, hata ayıklama cıvık bir kullanıcıya Visual Studio ile MI özellikli hata ayıklama (gdb gibi) arasında standart giriş/çıkışı aktaracak bir boru olarak çalıştırılabilir başka bir çalıştırıcı kullanarak uzak bir bilgisayara bağlanmasını söyler. İzin verilen değerler: bir veya daha fazla [Boru Taşıma Seçeneği.](#pipe_transport_options)|

## <a name="launch-setup-commands"></a><a name="launch_setup_commands"></a>Başlatma kurulum komutları

`setupCommands` Özellik ile birlikte kullanılır:

||||
|-|-|-|
|`text`|string|Yürütmeiçin hata ayıklama komutu.|
|`description`|string|Komut için isteğe bağlı açıklama.|
|`ignoreFailures`|boole|Doğruysa, komuttaki hatalar yoksayılmalıdır. Varsayılan `false`değer.|

## <a name="pipe-transport-options"></a><a name = "pipe_transport_options"></a>Boru taşıma seçenekleri

`pipeTransport` Özellik ile birlikte kullanılır:

||||
|-|-|-|
|`pipeCwd`|string|Boru programı için çalışma dizinine tam nitelikli yol.|
|`pipeProgram`|string|Yürütmek için tam nitelikli boru komutu.|
|`pipeArgs`|array|Bağlantıyı yapılandırmak için boru programına geçirilen komut satırı bağımsız değişkenleri.|
|`debuggerPath`|string|Hedef makinedeki hata ayıklayıcıya giden tam yol, örneğin /usr/bin/gdb.|
|`pipeEnv`|object|Çevre değişkenleri boru programına geçti.|
|`quoteArgs`|boole|Tek tek bağımsız değişkenler karakterler içeriyorsa (boşluklar veya sekmeler gibi), alıntı yapılmalı mıdır? Eğer `false`, hata ayıklama komutu artık otomatik olarak alıntı olacaktır. `true` varsayılan değerdir.|

## <a name="source-file-map-options"></a><a name="source_file_map_options"></a>Kaynak dosya eşlemi seçenekleri

`sourceFileMap` Özellik ile kullanın:

||||
|-|-|-|
|`editorPath`|string|Düzenleyicinin bulması için kaynak kodun konumu.|
|`useForBreakpoints`|boole|Kesme noktaları ayarı yaparken, bu kaynak eşleme kullanılmalıdır. Kesme `false`noktalarını ayarlamak için yalnızca dosya adı ve satır numarası kullanılırsa. Eğer, `true`kesme noktaları yalnızca bu kaynak eşlemi kullanıldığında dosya ve satır numarasına tam yol ile ayarlanır. Aksi takdirde, kesme noktaları ayarlanırken sadece dosya adı ve satır numarası kullanılır. `true` varsayılan değerdir.|
