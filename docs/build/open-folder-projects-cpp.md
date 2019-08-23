---
title: Visual Studio 'da derleme C++ sistemleri için klasör desteğini açma
ms.date: 08/20/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 78b1c00b07423e9d02f585c707156a1c843bea6f
ms.sourcegitcommit: ace42fa67e704d56d03c03745b0b17d2a5afeba4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69975994"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio 'da derleme C++ sistemleri için klasör desteğini açma

::: moniker range="vs-2015"

Klasör aç özelliği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio 2017 ve sonraki sürümlerde, "klasör aç" özelliği, kaynak dosyalarının bir klasörünü açmanıza ve IntelliSense, gözatma, yeniden düzenleme, hata ayıklama, vb. desteğiyle kodlamaya hemen başlayabilmenizi sağlar. Düzenleme, oluşturma, taşıma veya dosyaları silmek gibi Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir. . Sln veya. vcxproj dosyaları yüklü değil; gerekirse, özel görevleri belirtebilir ve basit. JSON dosyaları aracılığıyla parametreleri oluşturup başlatabilirsiniz. Bu özellik, herhangi bir üçüncü taraf derleme sistemini Visual Studio ile tümleştirmenize olanak sağlar. Açık klasör hakkında genel bilgi için bkz. [projeler veya çözümler olmadan Visual Studio 'da kod geliştirme](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions).

## <a name="cmake-and-qt"></a>CMake ve QT

CMake, C++ masaüstü iş yükünün bir bileşeni olarak VISUAL Studio IDE 'de tümleşiktir. CMake iş akışı, bu makalede açıklanan iş akışıyla aynı değildir. CMake kullanıyorsanız bkz. [Visual Studio 'Da CMake projeleri](cmake-projects-in-visual-studio.md). Ayrıca, CMake 'i de QT projeleri oluşturmak için kullanabilir veya Visual Studio 2015 ya da Visual Studio 2017 için [QT Visual Studio uzantısı](https://download.qt.io/development_releases/vsaddin/) ' nı kullanabilirsiniz.

## <a name="other-build-systems"></a>Diğer derleme sistemleri

Visual Studio IDE 'yi, ana menüden doğrudan desteklenmeyen bir yapı sistemi veya derleyici araç takımı ile kullanmak için **Dosya Seç | Açık |** Veya **CTRL + SHIFT + alt + O**tuşlarına basın. Kaynak kodu dosyalarınızı içeren klasöre gidin. Projeyi derlemek, IntelliSense 'i yapılandırmak ve hata ayıklama parametrelerini ayarlamak için üç JSON dosyası eklersiniz:

| | |
|-|-|
|CppProperties.json|Göz atmak için özel yapılandırma bilgilerini belirtin. Gerekirse, kök proje klasörünüzde bu dosyayı oluşturun. (CMake projelerinde kullanılmaz.)|
|Tasks. vs. JSON|Özel derleme komutlarını belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **yapılandırma görevleri**.|
|Launch. vs. JSON|Hata ayıklayıcı için komut satırı bağımsız değişkenlerini belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **hata ayıklama ve başlatma ayarları**.|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>CppProperties. JSON ile kod gezintisini yapılandırma

**Tanıma Git** gibi IntelliSense ve gözatma davranışlarının doğru şekilde çalışması Için, Visual Studio 'nun hangi derleyicisini kullandığınızı, sistem üstbilgilerinin nerede olduğunu ve doğrudan açtığınız klasör (çalışma alanı klasörü). Bir yapılandırma belirtmek için ana araç çubuğunda açılan listeden **yapılandırmaları Yönet** ' i seçebilirsiniz:

![Yapılandırmaların yönetme açılan menüsü](media/manage-configurations-dropdown.png)

Şu anda Visual Studio, tümü Microsoft C++ derleyicisi için dört varsayılan yapılandırma sunmaktadır:

![Varsayılan yapılandırma](media/default-configurations.png)

Örneğin, **x64-Debug**' ı seçerseniz, Visual Studio kök proje klasörünüzde *cppproperties. JSON* adlı bir dosya oluşturur ve bunu şöyle doldurur:

```json
{
  "configurations": [
    {
      "inheritEnvironments": [
        "msvc_x64"
      ],
      "name": "x64-Debug",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "defines": [
        "WIN32",
        "_DEBUG",
        "UNICODE",
        "_UNICODE"
      ],
      "intelliSenseMode": "windows-msvc-x64"
    }
  ]
}
```

Bu yapılandırma, Visual Studio [x64 Geliştirici komut istemi](building-on-the-command-line.md)ortam değişkenlerini devralır. Bu değişkenlerden biri, `INCLUDE` `${env.INCLUDE}` makroyu kullanarak buraya başvurabilirsiniz. Özelliği `includePath` , Visual Studio 'ya IntelliSense için gereken tüm kaynakları nerede bakacağını söyler. Bu durumda, "ıNCLUDE ortam değişkeni tarafından belirtilen tüm dizinlere ve ayrıca geçerli çalışma klasörü ağacındaki tüm dizinlere bak" diyor. `name` Özelliği, açılan menüde görünecek addır ve istediğiniz herhangi bir şey olabilir. Özelliği `defines` , koşullu derleme blokları ile karşılaştığında IntelliSense 'e ipuçları sağlar. `intelliSenseMode` Özelliği, derleyici türüne göre bazı ek ipuçları sağlar. MSVC, GCC ve Clang için çeşitli seçenekler mevcuttur.

## <a name="example-configuration-for-gcc"></a>GCC için örnek yapılandırma

Microsoft C++dışında bir derleyici kullanıyorsanız, *cppproperties. JSON*içinde özel bir yapılandırma ve ortam oluşturmanız gerekir. Aşağıdaki örnek, MSYS2 yüklemesinde GCC 'yi kullanmak için tek bir özel yapılandırmaya sahip olan tüm *Cppproperties. JSON* dosyasını göstermektedir:

```json
{
  "configurations": [
   {
      "inheritEnvironments": [
        "mingw_64"
      ],
      "name": "Mingw64",
      "includePath": [
        "${env.INCLUDE}",
        "${workspaceRoot}\\**"
      ],
      "intelliSenseMode": "linux-gcc-x64",
      "environments": [
        {
          "MINGW64_ROOT": "C:\\msys64\\mingw64",
          "BIN_ROOT": "${env.MINGW64_ROOT}\\bin",
          "FLAVOR": "x86_64-w64-mingw32",
          "TOOLSET_VERSION": "8.3.0",
          "PATH": "${env.MINGW64_ROOT}\\bin;${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR}",
          "environment": "mingw_64"
        }
      ]
   }
}
```

`environments` Bloğa göz önünde edin. Bu, ortam değişkenleri gibi davranan ve yalnızca *Cppproperties. JSON* dosyasında değil, diğer yapılandırma dosyaları *görev. vs. JSON* ve *Launch. vs. JSON*içinde de bulunan özellikleri tanımlar. Yapılandırma ortamı devralır ve değerini`includePath`belirtmek için özelliğinikullanır.`INCLUDE` `mingw_w64` `Mingw64` Gerektiğinde bu dizi özelliğine başka yollar ekleyebilirsiniz. '

> [!WARNING]
> Şu anda ' de `INCLUDE` `environments` belirtilen değerin `includePath` özelliğine doğru şekilde geçirilmediği bilinen bir sorun var. Tüm değişmez değer `includePath` dizisini diziye ekleyerek soruna geçici bir çözüm bulabilirsiniz.

`intelliSenseMode` Özelliği gcc için uygun bir değere ayarlanır. Tüm bu özellikler hakkında daha fazla bilgi için bkz. [Cppproperties şema başvurusu](cppproperties-schema-reference.md).

Her şey doğru şekilde çalıştığında, bir türün üzerine geldiğinizde GCC başlıklarından IntelliSense görürsünüz:

![GCC IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense tanılamayı etkinleştir

İstediğiniz IntelliSense 'i görmüyorsanız, **Araçlar** > **Seçenekler** > **metin Düzenleyicisi** > **C/C++**  > **Gelişmiş** ' e giderek sorun gidermeye devam edebilirsiniz ve **günlük kaydını** **doğru**olarak etkinleştir ayarı. İle başlamak için **günlük kaydı düzeyini** 5 olarak ayarlamayı ve filtreleri 8 ' e **kaydetmeyi** deneyin.

![Tanılama günlükleri](media/diagnostic-logging.png)

Çıkış **Çıkış penceresi** gönderilir ve **çıktıyı göster ' i seçtiğinizde görünür. Görsel C++ günlüğü*. Çıktı, diğer şeyler yanında, IntelliSense 'in kullanmaya çalıştığı gerçek ekleme yollarının listesini içerir. Yollar *Cppproperties. JSON*içindeki olanlarla eşleşmiyorsa, klasörü kapatmayı ve önbelleğe alınmış gözatma verilerini içeren *. vs* alt klasörünü silmeyi deneyin.

### <a name="define-build-tasks-with-tasksvsjson"></a>Görevler. vs. JSON ile derleme görevlerini tanımlama

Derleme betikleri veya geçerli çalışma alanınızda doğrudan IDE'de görev olarak çalıştırarak olması dosyalarda dış diğer işlemleri otomatik hale getirebilirsiniz. Bir dosya veya klasörü sağ tıklatıp seçerek yeni bir görev yapılandırabileceğiniz **yapılandırma görevleri**.

![Klasörü aç görevleri yapılandırma](media/configure-tasks.png)

Bu, Visual Studio 'Nun kök proje klasörünüzde oluşturduğu. vs klasöründeki *Tasks. vs. JSON* dosyasını oluşturur (veya açar). Bu dosyada herhangi bir rastgele görev tanımlayabilir ve ardından **Çözüm Gezgini** bağlam menüsünden çağırabilirsiniz. GCC örneğine devam etmek için aşağıdaki kod parçacığında, bir proje derlemek için *g + +. exe* ' yi çağıran tek bir görevle birlikte tamamlanmış bir *Görevler. vs. JSON* dosyası gösterilmektedir. Projenin *Hello. cpp*adlı tek bir dosya içerdiğini varsayın.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "build hello",
      "appliesTo": "/",
      "type": "default",
      "command": "g++",
      "args": [
        "-g",
        "-o",
        "hello",
        "hello.cpp"
      ]
    }
  ]
}

```

JSON dosyası, **Çözüm Gezgini**en üstündeki **tüm dosyaları göster** düğmesine tıkladıysanız görebileceğiniz *. vs* alt klasörüne yerleştirilir. Bu görevi, **Çözüm Gezgini** kök düğümüne sağ tıklayıp **Merhaba Build**' i seçerek çalıştırabilirsiniz. Görev tamamlandığında **Çözüm Gezgini**yeni bir *Hello. exe* dosyası görmeniz gerekir.

Birçok görev türü tanımlayabilirsiniz. Aşağıdaki örnek, tek bir görevi tanımlayan *Tasks. vs. json dosyasını* gösterir. `taskLabel`bağlam menüsünde görünen adı tanımlar. `appliesTo`komutun hangi dosyalara uygulanabilir olduğunu tanımlar. Özelliği, konsolunun yolunu tanımlayan ComSpec ortam değişkenine başvurur (Windows üzerinde*cmd. exe* ). `command` Ayrıca, CppProperties. JSON veya CMakeSettings. JSON içinde belirtilen ortam değişkenlerine de başvurabilirsiniz. `args` Özelliği çağrılacak komut satırını belirtir. `${file}` Makrosu alır seçili dosyasında **Çözüm Gezgini**. Aşağıdaki örnek, seçili olan. cpp dosyasının dosya adını görüntüler.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskLabel": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

*Tasks. vs. JSON*dosyasını kaydettikten sonra, klasördeki herhangi bir *. cpp* dosyasına sağ tıklayabilir, bağlam menüsünden **echo filename** ' i seçebilir ve çıkış penceresinde görünen dosya adına bakabilirsiniz.

Daha fazla bilgi için bkz. [Tasks. vs. JSON şema başvurusu](tasks-vs-json-schema-reference-cpp.md).

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Launch. vs. JSON ile hata ayıklama parametrelerini yapılandırma

Programınızın komut satırı bağımsız değişkenlerini ve hata ayıklama talimatlarını özelleştirmek için **Çözüm Gezgini** ' de çalıştırılabilir dosyaya sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. Bu, var olan bir *Launch. vs. JSON* dosyasını açar veya yoksa, bir dizi minimum başlatma ayarı ile yeni bir dosya oluşturur. İlk olarak, ne tür bir hata ayıklama oturumu yapılandırmak istediğinizi tercih edersiniz. Bir MinGW-W64 projesinde hata ayıklamak için, **minggwC++ /Cygwin (GDB) için C/Launch**' ı seçtik. Bu, *gdb. exe* ' yi kullanmak için varsayılan değerler hakkında bazı eğitirüler içeren bir başlatma yapılandırması oluşturur. Bu varsayılan değerlerden `MINGW_PREFIX`biri. Değişmez değer yolunu (aşağıda gösterildiği gibi) değiştirebilir veya *cppproperties. JSON*içinde `MINGW_PREFIX` bir özellik tanımlayabilirsiniz:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "cppdbg",
      "name": "hello.exe",
      "project": "hello.exe",
      "cwd": "${workspaceRoot}",
      "program": "${debugInfo.target}",
      "MIMode": "gdb",
      "miDebuggerPath": "c:\\msys64\\usr\\bin\\gdb.exe",
      "externalConsole": true
    }
  ]
}

```

Hata ayıklamayı başlatmak için, hata ayıklama açılan menüsünde yürütülebilir dosyayı seçin, ardından yeşil oka tıklayın:

![Hata ayıklayıcıyı Başlat](media/launch-debugger-gdb.png)

**Hata ayıklayıcıyı başlatma** iletişim kutusunu ve ardından programınızı çalıştıran bir dış konsol penceresini görmeniz gerekir.

Daha fazla bilgi için bkz. [Launch. vs. JSON şema başvurusu](launch-vs-schema-reference-cpp.md).

## <a name="launching-other-executables"></a>Diğer yürütülebilir dosyalar başlatılıyor

Bilgisayarınızda çalıştırılabilir dosya için başlatma ayarları tanımlayabilirsiniz. Aşağıdaki örnek, *7za* 'yi başlatır ve `args` JSON dizisine ekleyerek ek bağımsız değişkenleri belirtir:

```json
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
      "type": "default",
      "project": "CPP\\7zip\\Bundles\\Alone\\O\\7za.exe",
      "name": "7za.exe list content of helloworld.zip",
      "args": [ "l", "d:\\sources\\helloworld.zip" ]
    }
  ]
}
```

Bu dosyayı kaydettiğinizde, yeni yapılandırma hata ayıklama hedefi açılır listesinde görünür ve hata ayıklayıcıyı başlatmak için bunu seçebilirsiniz. Dilediğiniz sayıda yürütülebilir dosya için dilediğiniz sayıda hata ayıklama yapılandırması oluşturabilirsiniz. Şimdi **F5** 'e basarsanız, hata ayıklayıcı daha önce ayarlamış olduğunuz herhangi bir kesme noktasına uyar ve bu noktaları vuracaktır. Tüm tanıdık hata ayıklayıcı pencereleri ve işlevleri artık kullanılabilir.

::: moniker-end
