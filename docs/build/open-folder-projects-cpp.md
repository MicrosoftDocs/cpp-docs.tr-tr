---
title: Visual Studio'da C++ yapı sistemleri için Klasör açma desteği
ms.date: 12/02/2019
helpviewer_keywords:
- Open Folder Projects in Visual Studio
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 9264aa4bf77de406bdde9042ef9ec4251763f721
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320956"
---
# <a name="open-folder-support-for-c-build-systems-in-visual-studio"></a>Visual Studio'da C++ yapı sistemleri için Klasör açma desteği

::: moniker range="vs-2015"

Açık Klasör özelliği Visual Studio 2017 ve sonraki yıllarda kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Visual Studio 2017 ve sonrası özellikleri, kaynak dosyaların bir klasörünü açmanızı ve IntelliSense desteği ile hemen kodlamaya başlamanızı sağlar, tarama, yeniden düzenleme, hata ayıklama, ve benzeri. Dosyaları düzenlediğinizde, oluşturdukça, taşırken veya silerken, Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak günceller. .sln veya .vcxproj dosyaları yüklenmez; gerekirse, özel görevler belirtebilir, ayrıca basit .json dosyaları aracılığıyla parametreler oluşturabilir ve başlatabilirsiniz. Bu özellik, herhangi bir üçüncü taraf yapı sistemini Visual Studio'ya entegre etmenizi sağlar. Açık Klasör hakkında genel bilgi için visual [studio'da proje veya çözüm olmadan kod geliştir'e](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions)bakın.

## <a name="cmake-and-qt"></a>CMake ve Qt

CMake, Visual Studio IDE'ye C++ masaüstü iş yükünün bir bileşeni olarak entegre edilmiştir. CMake iş akışı bu makalede açıklanan iş akışıyla aynı değildir. CMake kullanıyorsanız, [Visual Studio CMake projelerine](cmake-projects-in-visual-studio.md)bakın. Qt projeleri oluşturmak için CMake'i de kullanabilir veya Visual Studio 2015 veya Visual Studio 2017 için [Qt Visual Studio Extension'ı](https://download.qt.io/development_releases/vsaddin/) kullanabilirsiniz.

## <a name="other-build-systems"></a>Diğer yapı sistemleri

Visual Studio IDE'yi ana menüden doğrudan desteklenmeyen bir yapı sistemi veya derleyici araç seti ile kullanmak için Dosya ' yı seçin **| Aç | Klasör** veya **Ctrl + Shift + Alt + O**tuşuna basın. Kaynak kod dosyalarınızı içeren klasöre gidin. Projeyi oluşturmak, IntelliSense'i yapılandırmak ve hata ayıklama parametrelerini ayarlamak için üç JSON dosyası eklersiniz:

| | |
|-|-|
|CppProperties.json|Tarama için özel yapılandırma bilgilerini belirtin. Gerekirse bu dosyayı kök proje klasörünüzde oluşturun. (CMake projelerinde kullanılmaz.)|
|görevler.vs.json|Özel yapı komutları belirtin. **Solution Explorer** bağlam menüsü öğesi üzerinden erişilen **Yapılandırma Görevleri**.|
|launch.vs.json|Hata ayıklama için komut satırı bağımsız değişkenlerini belirtin. **Solution Explorer** bağlam menü öğesi **Hata Ayıklama ve Başlatma Ayarları**üzerinden erişilir.|

## <a name="configure-code-navigation-with-cpppropertiesjson"></a>CppProperties.json ile kod gezintisini yapılandır

IntelliSense ve Doğru çalışması **için Tanıma Git** gibi tarama davranışı için Visual Studio'nun hangi derleyiciyi kullandığınızı, sistem üstbilgilerinin nerede olduğunu ve doğrudan açtığınız klasörde (çalışma alanı klasöründe) değilse ek dosyaların nerede bulunduğunu bilmesi gerekir. Yapılandırma belirtmek için, ana araç çubuğundaki açılır sayfadan **Yapılandırmaları Yönet'i** seçebilirsiniz:

![Yapılandırmaları yönetme açılır](media/manage-configurations-dropdown.png)

Visual Studio aşağıdaki varsayılan yapılandırmaları sunar:

![Varsayılan yapılandırmalar](media/default-configurations.png)

Örneğin, **x64-Debug'ı**seçerseniz, Visual Studio kök proje klasörünüzde *CppProperties.json* adlı bir dosya oluşturur:

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

Bu yapılandırma Visual Studio [x64 Developer Command Prompt'ın](building-on-the-command-line.md)ortam değişkenlerini devralır. Bu `INCLUDE` değişkenlerden biri ve `${env.INCLUDE}` makro kullanarak burada başvurabilirsiniz. Tesis `includePath` Visual Studio'ya IntelliSense için ihtiyaç duyduğu tüm kaynakları nerede arayacağını söyler. Bu durumda, "INCLUDE ortamı değişkeni tarafından belirtilen tüm dizinlere ve ayrıca geçerli çalışma klasörü ağacındaki tüm dizinlere bakın" diyor. Özellik `name` açılır açılır görünür adıdır ve istediğiniz herhangi bir şey olabilir. Özellik, `defines` koşullu derleme bloklarıyla karşılaştığında IntelliSense'e ipuçları sağlar. Özellik `intelliSenseMode` derleyici türüne göre bazı ek ipuçları sağlar. MSVC, GCC ve Clang için çeşitli seçenekler mevcuttur.

> [!NOTE]
> Visual Studio *CppProperties.json*ayarları göz ardı gibi görünüyorsa, bu gibi *.gitignore* dosyasına bir özel durum eklemeyi deneyin: `!/CppProperties.json`.

## <a name="default-configuration-for-mingw-w64"></a>MinGW-w64 için varsayılan yapılandırma

MinGW-W64 yapılandırmasını eklerseniz, JSON şuna bakar:

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

Engellemeye `environments` dikkat edin. Bu çevre değişkenleri gibi görünen özellikleri tanımlar ve *cppProperties.json* dosyasında sadece kullanılabilir, ama aynı zamanda diğer yapılandırma dosyaları *task.vs.json* ve *launch.vs.json*. Yapılandırma `Mingw64` `mingw_w64` ortamı devralır ve 'nin değerini belirtmek `includePath`için özelliğini `INCLUDE` kullanır. Gerektiğinde bu dizi özelliğine başka yollar ekleyebilirsiniz.'

Özellik, `intelliSenseMode` GCC için uygun bir değere ayarlanmıştır. Tüm bu özellikler hakkında daha fazla bilgi için [CppProperties şema başvurusuna](cppproperties-schema-reference.md)bakın.

Her şey doğru çalıştığında, bir tür üzerinde gezinmek zaman GCC başlıkları IntelliSense göreceksiniz:

![GCC IntelliSense](media/gcc-intellisense.png)

## <a name="enable-intellisense-diagnostics"></a>IntelliSense tanılamayı etkinleştirin

Beklediğiniz IntelliSense'i görmüyorsanız, **Tools** > **Options** > **Text Editor** > **C/C++** > **Advanced'e** giderek sorun giderebilirsiniz ve **Günlük'ü** **doğru**şekilde etkinleştir'i ayarlayabilirsiniz. Başlangıç olarak, **Günlük Düzeyi'ni** 5'e, **Günlük Filtrelerini** 8'e ayarlamayı deneyin.

![Tanılama günlüğüne kaydetme](media/diagnostic-logging.png)

**Çıktı Çıkış Penceresine** borulanır ve seçtiğinizde görünür **Çıkış Göster: Visual C++ Log*. Çıktı, diğer şeylerin yanı sıra, IntelliSense'in kullanmaya çalıştığı yolları içerir. Yollar *CppProperties.json'dakiyle*eşleşmiyorsa, klasörü kapatmayı ve önbelleğe alınmış tarama verilerini içeren *.vs* alt klasörünü silmeyi deneyin.

### <a name="define-build-tasks-with-tasksvsjson"></a>Görevlerle yapı görevlerini tanımlama.vs.json

Komut dosyalarını veya diğer dış işlemleri, geçerli çalışma alanınızdaki dosyalarda doğrudan IDE'de görev olarak çalıştırarak otomatikleştirebilirsiniz. Bir dosyaveya klasöre sağ tıklayarak ve **Görevleri Yapılandır'ı**seçerek yeni bir görevi yapılandırabilirsiniz.

![Klasör Yapılandırma Görevlerini Aç](media/configure-tasks.png)

Bu, Visual Studio'nun kök proje klasörünüzde oluşturduğu .vs klasöründe *görevler.vs.json* dosyasını oluşturur (veya açar). Bu dosyadaki herhangi bir rasgele görevi tanımlayabilir ve ardından **Çözüm Gezgini** bağlam menüsünden çağırabilirsiniz. GCC örneğine devam etmek için, aşağıdaki snippet tam bir *görevleri gösterir.vs.json* dosyası, bir proje oluşturmak için *g++.exe'yi* çağıran tek bir görev olarak. Projenin *hello.cpp*adlı tek bir dosya içerdiğini varsayalım.

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

JSON dosyası *.vs* alt klasörüne yerleştirilir. Bu klasörü görmek **için, Solution Explorer'ın**üst kısmındaki **Tüm Dosyaları Göster** düğmesini tıklatın. **Çözüm Gezgini'ndeki** kök düğümüne sağ tıklayarak ve merhaba **oluştur'u**seçerek bu görevi çalıştırabilirsiniz. Görev tamamlandığında **Çözüm Gezgini'nde** *hello.exe* yeni bir dosya görmeniz gerekir.

Birçok türde görev tanımlayabilirsiniz. Aşağıdaki örnek, tek bir görevi tanımlayan *bir görevler.vs.json dosyasını* gösterir. `taskLabel`bağlam menüsünde görünen adı tanımlar. `appliesTo`komutun hangi dosyalarüzerinde gerçekleştirilebileceğini tanımlar. Özellik, `command` konsolun (Windows'da*cmd.exe)* yolunu tanımlayan COMSPEC ortamı değişkenini ifade eder. CppProperties.json veya CMakeSettings.json'da bildirilen ortam değişkenlerine de başvuruyapabilirsiniz. Özellik, `args` çağrılacak komut satırını belirtir. `${file}` Makro, **Çözüm Gezgini'nde**seçili dosyayı alır. Aşağıdaki örnekte, şu anda seçili .cpp dosyasının dosya adı görüntülenir.

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

*tasks.vs.json'u*kurtardıktan sonra klasördeki herhangi bir *.cpp* dosyasına sağ tıklayabilir, bağlam menüsünden **Yankı dosya adını** seçebilir ve Çıktı penceresinde görüntülenen dosya adını görebilirsiniz.

Daha fazla bilgi için [Tasks.vs.json şema referansına](tasks-vs-json-schema-reference-cpp.md)bakın.

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Hata ayıklama parametrelerini launch.vs.json ile yapılandırın

Programınızın komut satırı bağımsız değişkenlerini ve hata ayıklama yönergelerini özelleştirmek **için, Solution Explorer'da** çalıştırılabilir'e sağ tıklayın ve **Hata Ayıklama ve Başlatma Ayarları'nı**seçin. Bu, varolan bir *launch.vs.json* dosyasini açar veya hiçbiri yoksa, en az başlatma ayarları kümesine sahip yeni bir dosya oluşturur. Önce yapılandırmak istediğiniz hata ayıklama oturumu tür bir seçim verilir. Bir MinGw-w64 projesinin hata ayıklanması **için, MinGW/Cygwin (gdb) için C/C++ Lansmanı'nı**seçiyoruz. Bu, varsayılan değerler hakkında bazı eğitimli tahminlerle *gdb.exe* kullanmak için bir başlatma yapılandırması oluşturur. Bu varsayılan değerlerden `MINGW_PREFIX`biri. Eğer edebi yol yerine (aşağıda gösterildiği gibi) veya `MINGW_PREFIX` *CppProperties.json*bir özellik tanımlayabilirsiniz:

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

Hata ayıklama yı başlatmak için hata ayıklama açılır durumda yürütülebilir'i seçin ve ardından yeşil oku tıklatın:

![Başlatma hata ayıklama](media/launch-debugger-gdb.png)

Başlangıç Hata **ayıklayıcı** iletişim kutusunu ve ardından programınızı çalıştıran harici bir konsol penceresini görmeniz gerekir.

Daha fazla bilgi için [launch.vs.json şema referansına](launch-vs-schema-reference-cpp.md)bakın.

## <a name="launching-other-executables"></a>Diğer çalıştırılabilir leri başlatma

Bilgisayarınızda çalıştırılabilir herhangi bir başlatma ayarlarını tanımlayabilirsiniz. Aşağıdaki örnek *7za* başlatıyor ve bunları JSON dizisine `args` ekleyerek ek bağımsız değişkenler belirtir:

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

Bu dosyayı kaydettiğinizde, hata ayıklama hedef açılır durumda yeni yapılandırma görünür ve hata ayıklama başlatmak için seçebilirsiniz. Herhangi bir sayıda yürütülebilir işlem için istediğiniz kadar hata ayıklama yapılandırması oluşturabilirsiniz. Şimdi **F5** tuşuna basarsanız, hata ayıklama başlatAcak ve önceden ayarlamış olabileceğiniz herhangi bir kesme noktasına çarpar. Tüm tanıdık hata ayıklama pencereleri ve işlevleri artık kullanılabilir.

::: moniker-end
