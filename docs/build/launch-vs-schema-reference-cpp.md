---
title: Launch. vs. JSON şema başvurusu (C++)
ms.date: 08/20/2019
helpviewer_keywords:
- launch.vs.json file [C++]
ms.openlocfilehash: 49b4f4e6c4359837e820684c29b0e102a08c3fd5
ms.sourcegitcommit: 6c1960089b92d007fc28c32af1e4bef0f85fdf0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/31/2019
ms.locfileid: "75556649"
---
# <a name="launchvsjson-schema-reference-c"></a>Launch. vs. JSON şema başvurusu (C++)

Hata ayıklama parametrelerini yapılandırmak için *Launch. vs. JSON* dosyasını kullanın. Dosyasını oluşturun. **Çözüm Gezgini** bir çalıştırılabilir dosyaya sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. Projenizle en yakından eşleşen seçeneği seçin ve ardından yapılandırmayı gerektiği şekilde değiştirmek için aşağıdaki özellikleri kullanın:

## <a name="default-properties"></a>Varsayılan Özellikler

||||
|-|-|-|
|**Özellik**|**Türü**|**Açıklama**|
|`name`|dize|Hata ayıklama hedefi açılan menüsünde girdinin adını belirtir.|
|`type`|dize|Projenin bir dll veya. exe olup olmadığını belirtir (varsayılan olarak. exe)|
|`project`|dize|Proje dosyasının göreli yolunu belirtir.|
|`projectTarget`|dize|`project`oluşturulurken çağrılan isteğe bağlı hedefi belirtir. Bu `projectTarget` zaten mevcut olmalı ve **hata ayıklama hedefi** açılan menüsünde adıyla eşleşmelidir.|
|`debugType`|dize|Kod türüne göre hata ayıklama modunu belirtir (yerel, yönetilen veya karma). Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır. İzin verilen değerler: "Native", "Managed", "mixed".|
|`inheritEnvironments`|dizi|Birden çok kaynaktan devralınan bir ortam değişkenleri kümesini belirtir. *Cmakesettings. JSON* veya *cppproperties. JSON* gibi dosyalarda bazı değişkenler tanımlayabilir ve bunları hata ayıklama bağlamı için kullanılabilir hale getirebilirsiniz.  **Visual Studio 16,4:** : `env.VARIABLE_NAME` sözdizimini kullanarak her hedef için ortam değişkenlerini belirtin. Bir değişkeni kaldırmak için, "null" olarak ayarlayın.|
|`args`|dizi|Başlatılan programa geçirilen komut satırı bağımsız değişkenlerini belirtir.|
|`currentDir`|dize|Derleme hedefinin tam dizin yolunu belirtir. Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır.|
|`noDebug`|Boole değeri|Başlatılan programda hata ayıklama yapılıp yapılmayacağını belirtir. Bu parametre için varsayılan değer belirtilmezse `false`.|
|`stopOnEntry`|Boole değeri|İşlem başlatıldığında ve hata ayıklayıcı iliştirip bu işlemin ne kadar kesmeyeceğini belirtir. Bu parametre için varsayılan değer `false`.|
|`remoteMachine`|dize|Programın başlatıldığı uzak makinenin adını belirtir.|
|`env`|dizi| Özel ortam değişkenlerinin anahtar-değer listesini belirtir. env: {"myEnv": "myVal"}.|
|`portName`|dize|Çalışan bir işleme eklenirken bağlantı noktasının adını belirtir.|
|`buildConfigurations`|dizi| Yapılandırmaların uygulanacağı yapı modunun adını belirten bir anahtar-değer çifti. Örneğin, `Debug` veya `Release` ve seçilen derleme moduna göre kullanılacak yapılandırma.

## <a name="c-linux-properties"></a>C++Linux özellikleri

||||
|-|-|-|
|**Özellik**|**Türü**|**Açıklama**|
|`program`|dize|Uzak makinedeki program yürütülebilirinin tam yolu. CMake kullanılırken makro `${debugInfo.fullTargetPath}` bu alanın değeri olarak kullanılabilir.|
|`processId`|tamsayı|Hata ayıklayıcıyı iliştirmek için isteğe bağlı işlem KIMLIĞI.|
|`sourceFileMap`|nesnesi|Hata ayıklama altyapısına geçirilen isteğe bağlı kaynak dosya eşlemeleri. Biçim: `{ "\<Compiler source location>": "\<Editor source location>" }` veya `{ "\<Compiler source location>": { "editorPath": "\<Editor source location>", "useForBreakpoints": true } }`. Örnek: `{ "/home/user/foo": "C:\\foo" }` veya `{ "/home/user/foo": { "editorPath": "c:\\foo", "useForBreakpoints": true } }`. Bkz. [kaynak dosya haritası seçenekleri](#source_file_map_options).|
|`additionalProperties`|dize|SourceFileMapOptions biri. (Aşağıya bakın.)|
|`MIMode`|dize|MIDebugEngine 'in bağlanacağı mı özellikli konsol hata ayıklayıcısı türünü gösterir. İzin verilen değerler "gdb", "lldb" dir.|
|`args`|dizi|Programa geçirilen komut satırı bağımsız değişkenleri.|
|`environment`|dizi|Program için ortama eklenecek ortam değişkenleri. Örnek: [{"Name": "SQUID", "Value": "Clad"}].|
|`targetArchitecture`|dize|Hata ayıklanan mimarisi. Bu parametre ayarlanmadığı takdirde bu otomatik olarak algılanır. İzin verilen değerler x86, ARM, arm64, MIPS, x64, AMD64, x86_64.|
|`visualizerFile`|dize|Bu işlemde hata ayıklanırken kullanılacak. natvis dosyası. Bu seçenek, GDB düzgün yazdırma ile uyumlu değildir. Bu ayar kullanılıyorsa "showDisplayString" başlığına bakın.|
|`showDisplayString`|Boole değeri|Bir Visualizerdosyası belirtildiğinde, showDisplayString Görüntüleme dizesini etkinleştirir. Bu seçeneği açmak hata ayıklama sırasında daha yavaş performans oluşmasına neden olabilir.|
|`remoteMachineName`|dize|GDB 'yi barındıran uzak Linux makinesi ve hata ayıklamak için program. Yeni Linux makineleri eklemek için bağlantı yöneticisini kullanın. CMake kullanılırken makro `${debugInfo.remoteMachineName}` bu alanın değeri olarak kullanılabilir.|
|`cwd`|dize|Uzak makinedeki hedefin çalışma dizini. CMake kullanılırken makro `${debugInfo.defaultWorkingDirectory}` bu alanın değeri olarak kullanılabilir. *Cmakelists. txt* dosyasında geçersiz kılınmadığı müddetçe, varsayılan değer uzak çalışma alanı köküdür.|
|`miDebuggerPath`|dize|Mı özellikli hata ayıklayıcının (gdb gibi) yolu. Belirtilmediğinde, ilk olarak hata ayıklayıcı için yol arar.|
|`miDebuggerServerAddress`|dize|Bağlanılacak mı özellikli hata ayıklayıcı sunucusunun ağ adresi. Örnek: localhost: 1234.|
|`setupCommands`|dizi|Temel alınan hata ayıklayıcıyı ayarlamak için yürütülecek bir veya daha fazla GDB/LLDB komutu. Örnek: `"setupCommands": [ { "text": "-enable-pretty-printing", "description": "Enable GDB pretty printing", "ignoreFailures": true }]`. Bkz. [Kurulum komutlarını başlatma](#launch_setup_commands).|
|`customLaunchSetupCommands`|dizi|Sağlanmışsa, bu, bir hedefi diğer komutlarla başlatmak için kullanılan varsayılan komutları değiştirir. Örneğin, bir hedef işleme iliştirmek için bu "-target-Attach" olabilir. Boş bir komut listesi, başlatma komutlarının hata ayıklayıcıda komut satırı seçenekleri olarak sağlanmakta olduğu durumlarda yararlı olabilecek hiçbir şey ile birlikte değiştirilir. Örnek: `"customLaunchSetupCommands": [ { "text": "target-run", "description": "run target", "ignoreFailures": false }]`.|
|`launchCompleteCommand`|dize|Hata ayıklayıcı, hedef işlemin çalışmasına neden olacak şekilde tamamen ayarlandıktan sonra yürütülecek komut. İzin verilen değerler şunlardır "exec-Run", "exec-Continue", "none". Varsayılan değer "exec-Run" değeridir.|
|`debugServerPath`|dize|Başlatılacak sunucuda hata ayıklama için isteğe bağlı tam yol. Varsayılan olarak null değerini alır.|
|`debugServerArgs`|dize|İsteğe bağlı hata ayıklama sunucusu bağımsız değişkenleri. Varsayılan olarak null değerini alır.|
|`filterStderr`|Boole değeri|Sunucu tarafından başlatılan model için stderr akışında arama yapın ve hata ayıklama çıkışı için günlük stderr. `false` değerini varsayılan olarak alır.|
|`coreDumpPath`|dize|Belirtilen program için bir çekirdek döküm dosyasının isteğe bağlı tam yolu. Varsayılan olarak null değerini alır.|
externalConsole|Boole değeri|True ise hata ayıklanan için bir konsol başlatılır. `false`, hiçbir konsol başlatılmaz. `false` değerini varsayılan olarak alır. NOTE: Bu seçenek, bazı durumlarda teknik nedenlerden dolayı yok sayılır.|
|`pipeTransport`|dize|Mevcut olduğunda, hata ayıklayıcıya, Visual Studio ile mı etkin hata ayıklayıcı (gdb gibi) arasında standart giriş/çıkış geçişi yapan bir kanal olarak başka bir yürütülebilir dosyayı kullanarak uzak bir bilgisayara bağlanmasını söyler. İzin verilen değerler: bir veya daha fazla [kanal taşıma seçeneği](#pipe_transport_options).|


## <a name="launch_setup_commands"></a>Kurulum komutlarını Başlat

`setupCommands` özelliği ile kullanılır:

||||
|-|-|-|
|`text`|dize|Yürütülecek hata ayıklayıcı komutu.|
|`description`|dize|Komut için isteğe bağlı açıklama.|
|`ignoreFailures`|Boole değeri|Doğru ise, komuttan gelen hataların yok sayılacak olması gerekir. `false` değerini varsayılan olarak alır.|

## <a name = "pipe_transport_options"></a>Kanal taşıma seçenekleri

`pipeTransport` özelliği ile kullanılır:

||||
|-|-|-|
|`pipeCwd`|dize|Kanal programı için çalışma dizininin tam yolu.|
|`pipeProgram`|dize|Yürütülecek tam kanal komutu.|
|`pipeArgs`|dizi|Bağlantıyı yapılandırmak için kanal programına geçirilen komut satırı bağımsız değişkenleri.|
|`debuggerPath`|dize|Hedef makinedeki hata ayıklayıcının tam yolu; Örneğin,/usr/bin/gdb.|
|`pipeEnv`|nesnesi|Kanal programına geçirilen ortam değişkenleri.|
|`quoteArgs`|Boole değeri|Bağımsız değişkenler tek tek karakterler içeriyorsa (boşluk veya sekmeler gibi) tırnak içine alınmalıdır mi? `false`, hata ayıklayıcı komutu artık otomatik olarak tırnak içine alınmaz. Varsayılan değer `true`.|

## <a name="source_file_map_options"></a>Kaynak dosya eşleme seçenekleri

`sourceFileMap` özelliği ile kullanın:

||||
|-|-|-|
|`editorPath`|dize|Bulacak düzenleyicinin kaynak kodunun konumu.|
|`useForBreakpoints`|Boole değeri|Kesme noktaları ayarlanırken, bu kaynak eşlemesinin kullanılması gerekir. `false`, kesme noktaları ayarlamak için yalnızca dosya adı ve satır numarası kullanılır. `true`, kesme noktaları dosyanın tam yolu ve yalnızca bu kaynak eşleme kullanıldığında satır numarası ile ayarlanır. Aksi takdirde, kesme noktaları ayarlanırken yalnızca dosya adı ve satır numarası kullanılacaktır. Varsayılan değer `true`.|
