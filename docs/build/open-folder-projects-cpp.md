---
title: Visual Studio 'da C++ derleme sistemleri için açık klasör desteği
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 03c6a07d19599958de81a604ca77e2772168d441
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924112"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio 'da C++ derleme sistemleri için açık klasör desteği

::: moniker range="msvc-140"

Klasör aç özelliği Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

Visual Studio 2017 ve sonraki sürümlerde, "klasör aç" özelliği, kaynak dosyalarının bir klasörünü açmanıza ve IntelliSense, gözatma, yeniden düzenleme, hata ayıklama, vb. desteğiyle kodlamaya hemen başlayabilmenizi sağlar. Dosyaları düzenlerken, oluştururken, taşırken veya silerken, Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir. . Sln veya. vcxproj dosyaları yüklü değil; gerekirse, özel görevleri belirtebilir ve basit. JSON dosyaları aracılığıyla parametreleri oluşturup başlatabilirsiniz. Bu özellik, herhangi bir üçüncü taraf derleme sistemini Visual Studio ile tümleştirmenize olanak sağlar. Açık klasör hakkında genel bilgi için bkz. [projeler veya çözümler olmadan Visual Studio 'da kod geliştirme](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions).

## <a name="cmake-and-qt"></a>CMake ve QT

CMake, C++ masaüstü iş yükünün bir bileşeni olarak Visual Studio IDE 'de tümleşiktir. CMake iş akışı, bu makalede açıklanan iş akışıyla aynı değildir. CMake kullanıyorsanız bkz. [Visual Studio 'Da CMake projeleri](cmake-projects-in-visual-studio.md). Ayrıca, CMake 'i de QT projeleri oluşturmak için kullanabilir veya Visual Studio 2015 ya da Visual Studio 2017 için [QT Visual Studio uzantısı](https://download.qt.io/development_releases/vsaddin/) ' nı kullanabilirsiniz.

## <a name="other-build-systems"></a>Diğer derleme sistemleri

Visual Studio IDE 'yi, ana menüden doğrudan desteklenmeyen bir yapı sistemi veya derleyici araç takımı ile kullanmak için **Dosya Seç | Açık | Veya** **CTRL + SHIFT + alt + O** tuşlarına basın. Kaynak kodu dosyalarınızı içeren klasöre gidin. Projeyi derlemek, IntelliSense 'i yapılandırmak ve hata ayıklama parametrelerini ayarlamak için üç JSON dosyası eklersiniz:

| Dosya | Açıklama |
|-|-|
|Üzerinde CppProperties.js|Göz atmak için özel yapılandırma bilgilerini belirtin. Gerekirse, kök proje klasörünüzde bu dosyayı oluşturun. (CMake projelerinde kullanılmaz.)|
|Üzerinde tasks.vs.js|Özel derleme komutlarını belirtin. **Çözüm Gezgini** bağlam menüsü öğesi aracılığıyla erişilen **görevleri yapılandırın** .|
|Üzerinde launch.vs.js|Hata ayıklayıcı için komut satırı bağımsız değişkenlerini belirtin. **Çözüm Gezgini** bağlam menüsü öğesi **hata ayıklama ve başlatma ayarları** aracılığıyla erişilir.|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>CppProperties.jsile kod gezintisini yapılandırma

**Tanıma Git** gibi IntelliSense ve gözatma davranışlarının doğru çalışması Için, Visual Studio 'nun hangi derleyicisini kullandığınızı, sistem üstbilgilerinin nerede olduğunu ve doğrudan açtığınız klasörde (çalışma alanı klasörü) değil ek içerme dosyalarının nerede bulunduğunu bilmesi gerekir. Bir yapılandırma belirtmek için ana araç çubuğunda açılan listeden **yapılandırmaları Yönet** ' i seçebilirsiniz:

![Yapılandırmaların yönetme açılan menüsü](media/manage-configurations-dropdown.png)

Visual Studio aşağıdaki varsayılan yapılandırmalara sahiptir:

![Varsayılan yapılandırma](media/default-configurations.png)

Örneğin, **x64-Debug** ' ı seçerseniz, Visual Studio kök proje klasörünüzde *CppProperties.js* adlı bir dosya oluşturur:

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

Bu yapılandırma, Visual Studio [x64 Geliştirici komut istemi](building-on-the-command-line.md)ortam değişkenlerini devralır. Bu değişkenlerden biri, `INCLUDE` makroyu kullanarak buraya başvurabilirsiniz `${env.INCLUDE}` . `includePath`Özelliği, Visual Studio 'Ya IntelliSense için gereken tüm kaynakları nerede bakacağını söyler. Bu durumda, "ıNCLUDE ortam değişkeni tarafından belirtilen tüm dizinlere ve ayrıca geçerli çalışma klasörü ağacındaki tüm dizinlere bak" diyor. `name`Özelliği, açılan menüde görünecek addır ve istediğiniz herhangi bir şey olabilir. `defines`Özelliği, koşullu derleme blokları ile karşılaştığında IntelliSense 'e ipuçları sağlar. `intelliSenseMode`Özelliği, derleyici türüne göre bazı ek ipuçları sağlar. MSVC, GCC ve Clang için çeşitli seçenekler mevcuttur.

> [!NOTE]
> Visual Studio *CppProperties.jsüzerindeki* ayarları yok saymış görünüyorsa, *. gitignore* dosyanıza şu şekilde bir özel durum eklemeyi deneyin: `!/CppProperties.json` .

## <a name="default-configuration-for-mingw-w64"></a>MinGW için varsayılan yapılandırma-W64

MinGW-W64 yapılandırmasını eklerseniz JSON şuna bakar:

```json
{
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
          "TOOLSET_VERSION": "9.1.0",
          "PATH": "${env.BIN_ROOT};${env.MINGW64_ROOT}\\..\\usr\\local\\bin;${env.MINGW64_ROOT}\\..\\usr\\bin;${env.MINGW64_ROOT}\\..\\bin;${env.PATH}",
          "INCLUDE": "${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION};${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\tr1;${env.MINGW64_ROOT}\\include\\c++\\${env.TOOLSET_VERSION}\\${env.FLAVOR}",
          "environment": "mingw_64"
        }
      ]
    }
}
```

Bloğa göz önünde edin `environments` . Ortam değişkenleri gibi davranan ve yalnızca dosyadaki *CppProperties.js* değil, diğer yapılandırma dosyalarında de *task.vs.js* ve *launch.vs.jsaçık* olan özellikleri tanımlar. `Mingw64`Yapılandırma `mingw_w64` ortamı devralır ve `INCLUDE` değerini belirtmek için özelliğini kullanır `includePath` . Gerektiğinde bu dizi özelliğine başka yollar ekleyebilirsiniz. '

`intelliSenseMode`Özelliği GCC için uygun bir değere ayarlanır. Tüm bu özellikler hakkında daha fazla bilgi için bkz. [Cppproperties şema başvurusu](cppproperties-schema-reference.md).

Her şey doğru şekilde çalıştığında, bir türün üzerine geldiğinizde GCC başlıklarından IntelliSense görürsünüz:

![GCC IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense tanılamayı etkinleştir

İstediğiniz IntelliSense 'i görmüyorsanız, **Araçlar**  >  **Seçenekler**  >  **metin Düzenleyicisi**  >  **C/C++**  >  **Gelişmiş** ' e giderek ve **günlüğü etkinleştir** **`true`** ' i ayarlayarak sorun giderebilirsiniz. İle başlamak için **günlük kaydı düzeyini** 5 olarak ayarlamayı ve filtreleri 8 ' e **kaydetmeyi** deneyin.

![Tanılama günlüğüne kaydetme](media/diagnostic-logging.png)

Çıkış **Çıkış penceresi** gönderilir ve * *çıktıyı göster: Visual C++ günlük* ' i seçtiğinizde görünür. Çıktı, diğer şeyler yanında, IntelliSense 'in kullanmaya çalıştığı gerçek ekleme yollarının listesini içerir. Yollar *CppProperties.js* ' deki olanlarla eşleşmiyorsa, klasörü kapatmayı ve önbelleğe alınmış gözatma verilerini içeren *. vs* alt klasörünü silmeyi deneyin.

### <a name="define-build-tasks-with-tasksvsjson"></a>Üzerinde tasks.vs.jsderleme görevleri tanımlayın

Mevcut çalışma alanınızda bulunan dosyalar üzerinde, derleme betikleri veya diğer dış işlemleri otomatikleştirebilir ve bunları doğrudan IDE 'de görevler olarak çalıştırabilirsiniz. Bir dosya veya klasöre sağ tıklayıp **görevleri Yapılandır** ' ı seçerek yeni bir görev yapılandırabilirsiniz.

![Klasörü aç görevleri yapılandırma](media/configure-tasks.png)

Bu, Visual Studio 'Nun kök proje klasörünüzde oluşturduğu. vs klasöründeki dosyasında *tasks.vs.js* oluşturur (veya açar). Bu dosyada herhangi bir rastgele görev tanımlayabilir ve ardından **Çözüm Gezgini** bağlam menüsünden çağırabilirsiniz. GCC örneğine devam etmek için aşağıdaki kod parçacığında, bir proje derlemek için *g + +. exe* ' yi çağıran tek bir görevle dosyadaki bir bütün *tasks.vs.js* gösterilmektedir. Projenin *Hello. cpp* adlı tek bir dosya içerdiğini varsayın.

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

JSON dosyası *. vs* alt klasörüne yerleştirilir. Bu klasörü görmek için **Çözüm Gezgini** üstündeki **tüm dosyaları göster** düğmesine tıklayın. Bu görevi, **Çözüm Gezgini** kök düğümüne sağ tıklayıp **Merhaba Build** ' i seçerek çalıştırabilirsiniz. Görev tamamlandığında, **Çözüm Gezgini** *hello.exe* yeni bir dosya görmeniz gerekir.

Birçok görev türü tanımlayabilirsiniz. Aşağıdaki örnekte, tek bir görevi tanımlayan bir *dosyatasks.vs.js* gösterilmektedir. `taskLabel` bağlam menüsünde görünen adı tanımlar. `appliesTo` komutun hangi dosyalara uygulanabilir olduğunu tanımlar. `command`Özelliği, konsol yolunu (Windows üzerinde *cmd.exe* ) tanımlayan ComSpec ortam değişkenine başvurur. Ayrıca, üzerinde veya CMakeSettings.jsüzerinde CppProperties.jsolarak belirtilen ortam değişkenlerine de başvurabilirsiniz. `args`Özelliği çağrılacak komut satırını belirtir. `${file}`Makro seçili dosyayı **Çözüm Gezgini** alır. Aşağıdaki örnek, seçili olan. cpp dosyasının dosya adını görüntüler.

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

*tasks.vs.js* kaydettikten sonra, klasördeki herhangi bir *. cpp* dosyasına sağ tıklayabilir, bağlam menüsünden **echo filename** ' i seçebilir ve çıkış penceresinde dosya adının görüntülenmesini sağlayabilirsiniz.

Daha fazla bilgi için bkz. [ şema başvurusundaTasks.vs.js](tasks-vs-json-schema-reference-cpp.md).

### <a name="configure-debugging-parameters-with-launchvsjson"></a>launch.vs.jshata ayıklama parametrelerini yapılandırma

Programınızın komut satırı bağımsız değişkenlerini ve hata ayıklama talimatlarını özelleştirmek için **Çözüm Gezgini** ' de çalıştırılabilir dosyaya sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları** ' nı seçin. Bu, dosya üzerinde var olan bir *launch.vs.js* açar veya yoksa, bir dizi minimum başlatma ayarı olan yeni bir dosya oluşturur. İlk olarak, ne tür bir hata ayıklama oturumu yapılandırmak istediğinizi tercih edersiniz. Bir MinGw-W64 projesinde hata ayıklamak için, **MinGW/Cygwin (GDB) için C/C++ başlatma** ' yı seçiyoruz. Bu, varsayılan değerler hakkında bazı eğitimleri tahmin etmek için *gdb.exe* kullanmaya yönelik bir başlatma yapılandırması oluşturur. Bu varsayılan değerlerden biri `MINGW_PREFIX` . Değişmez değer yolunu (aşağıda gösterildiği gibi) değiştirebilir veya `MINGW_PREFIX` *üzerindeCppProperties.js* bir özellik tanımlayabilirsiniz:

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

Daha fazla bilgi için bkz. [ şema başvurusundalaunch.vs.js](launch-vs-schema-reference-cpp.md).

## <a name="launching-other-executables"></a>Diğer yürütülebilir dosyalar başlatılıyor

Bilgisayarınızda çalıştırılabilir dosya için başlatma ayarları tanımlayabilirsiniz. Aşağıdaki örnek, *7za* 'yi başlatır ve JSON dizisine ekleyerek ek bağımsız değişkenleri belirtir `args` :

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
