---
title: Visual Studio'da C++ yapı sistemler için açık klasör desteği
ms.date: 03/21/2019
helpviewer_keywords:
- Open Folder Projects in Visual C++
ms.assetid: abd1985e-3717-4338-9e80-869db5435175
ms.openlocfilehash: 2dedd56759b6bb49260221e22218da6f4300a970
ms.sourcegitcommit: 42e65c171aaa17a15c20b155d22e3378e27b4642
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58356094"
---
# <a name="open-folder-projects-for-c"></a>C++ için klasör Proje Aç

Visual Studio 2017 ve sonraki sürümlerinde, "Klasör Aç" özelliği, bir kaynak dosya klasörü açın ve hemen desteğiyle tarama, yeniden düzenleme, hata ayıklama, IntelliSense, kod yazmaya başlayın ve benzeri sağlar. Hiçbir .sln veya .vcxproj dosyaları yüklenir; Gerekirse, özel görevleri oluşturmak ve parametreler aracılığıyla basit .json dosyaları başlatma olarak belirtebilirsiniz. Klasör Aç hakkında genel bilgi için bkz: [kod Visual Studio'da projeler veya çözümler olmadan geliştirme](/visualstudio/ide/develop-code-in-visual-studio-without-projects-or-solutions).

CMake, Visual Studio, C++ Masaüstü iş yükünde bir bileşeni CMake araçları Visual Studio IDE'de tümleşiktir. Daha fazla bilgi için [Visual Studio'daki CMake projeleri](cmake-projects-in-visual-studio.md). Diğer yapı sistemi için klasörü aç özelliğini kullanabilirsiniz. Klasör Aç, Kod Düzenleyicisi, hata ayıklayıcı ve derleme sistemi ve derleyici araç takımı Çözümleyicileri etkili bir şekilde ayırır. Zengin IntelliSense özelliklerini, kod Çözümleyicileri ve CMake Ninja, QMake (Qt projelerde), gyp, SCons, Gradle, Buck, oluşturma ve gibi neredeyse tüm derleme sistemi, Visual Studio hata ayıklayıcı ile C++ Kod Düzenleyicisi'ni kullanabilirsiniz. Hatta tek bir dosyayı veya dosyaları derleme sistemi gevşek koleksiyonu ile çalışır.

Klasör Aç'ı kullanmak için ana menüden seçin **dosya | Açık | Klasör** veya basın **Ctrl + Shift + Alt + O**. Çözüm Gezgini, hemen klasördeki tüm dosyaları görüntüler. Düzenlemeye başlamak için herhangi bir dosyaya tıklayabilirsiniz. Arka planda, dosyaları, IntelliSense, gezinti ve yeniden düzenleme özellikleri etkinleştirmek için Visual Studio başlatılır. Düzenleme, oluşturma, taşıma veya dosyaları silmek gibi Visual Studio değişiklikleri otomatik olarak izler ve IntelliSense dizinini sürekli olarak güncelleştirir. 

## <a name="qmake-projects-that-target-the-qt-framework"></a>QMake Qt Framework'ü hedefleyen projeleri

Qt projeleri derlemek için Qt hedeflemek için Visual Studio için CMake araçlarını kullanabilir veya kullanabileceğiniz [Qt Visual Studio Uzantısı](https://download.qt.io/development_releases/vsaddin/) Visual Studio 2015 veya Visual Studio 2017 için.

## <a name="gyp-cons-scons-buck-etc"></a>gyp, simgeler, SCons, Buck, vb.

Visual Studio'da herhangi bir derleme sistemini kullanın ve C++ IDE ve hata ayıklayıcı avantajları hala keyfini çıkarın. Projenizin kök klasörüne açtığınızda, C++ Kod Düzenleyicisi IntelliSense ve gözatma için kaynak dosyaları dizini oluşturmak için buluşsal yöntemler kullanır. CppProperties.json dosyasını düzenleyerek, kodunuzun yapısı hakkında ipuçları sağlayabilir. Benzer şekilde, yapılandırma ve yapı programınızı launch.vs.json dosyasını düzenleyerek çağırma.

## <a name="configuring-open-folder-projects"></a>Klasör Aç projeleri yapılandırma

Klasör Aç projesinde üç JSON dosyalarıyla özelleştirebilirsiniz:

| | |
|-|-|
|CppProperties.json|Gözatma için özel yapılandırma bilgilerini belirtin. Bu dosya, kök proje klasörünüzdeki gerekirse oluşturun. ('da CMake projeleri kullanılmıyor.)|
|Tasks.vs.JSON|Özel derleme komutları ve derleyici anahtarları belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **yapılandırma görevleri**.|
|launch.vs.json|Hata ayıklayıcının komut satırı bağımsız değişkenlerini belirtin. Aracılığıyla erişilen **Çözüm Gezgini** bağlam menüsü öğesi **hata ayıklama ve başlatma ayarları**.|

### <a name="configure-intellisense-and-browsing-hints-with-cpppropertiesjson"></a>IntelliSense ve ipuçlarıyla CppProperties.json gözatma yapılandırın

IntelliSense ve göz atma davranışlarına kısmen bağlıdır tanımlayan etkin yapı yapılandırmasını # yolları, derleyici anahtarlarını ve diğer parametreler include. Varsayılan olarak, Visual Studio hata ayıklama ve yayın yapılandırmaları sağlar. CMake projeleri, bu amaçla CMakeSettings.json dosyasına ve CMakeLists.txt dosyaları kullanın. Klasör Aç projelerinin diğer türleri için tam kod kavrama için IntelliSense ve gözatma özellikler için sırayla özel yapılandırma oluşturmak gerekebilir. Yeni bir yapılandırmasını tanımlamak için kök klasörde CppProperties.json adlı bir dosya oluşturun. Aşağıda bir örnek verilmiştir:

```json
{
  "configurations": [
    {
      "name": "Windows x64",
      "includePath": [ "include" ],
      "defines": [ "_DEBUG" ],
      "compilerSwitches": "/std:c++17",
      "intelliSenseMode": "windows-msvc-x64",
      "forcedInclude": [ "pch.h" ],
      "undefines": []
    }
  ]
}
```
Daha fazla bilgi için [CppProperties şema başvurusu](cppproperties-schema-reference.md).

### <a name="define-build-tasks-with-tasksvsjson"></a>Tasks.vs.json ile derleme görevleri tanımlama

Derleme betikleri veya geçerli çalışma alanınızda doğrudan IDE'de görev olarak çalıştırarak olması dosyalarda dış diğer işlemleri otomatik hale getirebilirsiniz. Bir dosya veya klasörü sağ tıklatıp seçerek yeni bir görev yapılandırabileceğiniz **yapılandırma görevleri**.

![Klasör Aç yapılandırma görevleri](media/open-folder-config-tasks.png)

Oluşturur (veya açılır) **tasks.vs.json** Visual Studio kök proje klasörünüzdeki oluşturan .vs klasöründeki dosya. Bu dosyayı herhangi bir rastgele görev tanımlayın ve ondan çağırma **Çözüm Gezgini** bağlam menüsü. Aşağıdaki örnek, tek bir görevi tanımlayan bir tasks.vs.json dosyası gösterir. `taskName` bağlam menüsünde görünen adını tanımlar. `appliesTo` hangi dosyaların komutu gerçekleştirilebilir tanımlar. `command` Özelliği başvurur (Windows cmd.exe'de) konsol yolunu tanımlar COMSPEC ortam değişkenine. CppProperties.json veya CMakeSettings.json bildirilen ortam değişkenlerini de başvurabilirsiniz. `args` Özellik çağrılacak komut satırını belirtir. `${file}` Makrosu alır seçili dosyasında **Çözüm Gezgini**. Aşağıdaki örnek şu anda seçili .cpp dosyasının dosya adını görüntüler.

```json
{
  "version": "0.2.1",
  "tasks": [
    {
      "taskName": "Echo filename",
      "appliesTo": "*.cpp",
      "type": "command",
      "command": "${env.COMSPEC}",
      "args": ["echo ${file}"]
    }
  ]
}
```

Tasks.vs.JSON kaydettikten sonra herhangi bir .cpp dosyası klasörüne sağ tıklayın, seçin **Yankı filename** bağlam menüsü ve dosya adı çıktı penceresinde görüntülenen bakın.

Daha fazla bilgi için [Tasks.vs.json şema başvurusu](tasks-vs-json-schema-reference-cpp.md).

### <a name="configure-debugging-parameters-with-launchvsjson"></a>Launch.vs.json ile hata ayıklama parametreleri Yapılandır

Program komut satırı bağımsız değişkenleri özelleştirmek için yürütülebilir dosya çubuğunda sağ **Çözüm Gezgini** seçip **hata ayıklama ve başlatma ayarları**. Bu varolan açar **launch.vs.json** dosyası veya yoksa, seçtiğiniz program hakkında bilgileri önceden doldurulmuş yeni bir dosya oluşturur.

Ek bağımsız değişkenlerini belirtmek için bunları eklemeniz yeterlidir `args` aşağıdaki örnekte gösterildiği gibi JSON dizisi:

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

Bu dosyayı kaydettiğinizde, yeni yapılandırmayı hata ayıklama hedefi açılır menüde görünür ve hata ayıklayıcıyı başlatmak için bunu seçebilirsiniz. Dilediğiniz sayıda yürütülebilir dosyalar için birçok hata ayıklama yapılandırması oluşturabilirsiniz. Basarsanız **F5** hata ayıklayıcısı artık, başlar ve zaten ayarladığınız bir kesme noktasına ulaşırsınız. Tüm alıştığınız hata ayıklayıcı pencereleri ve işlevleri artık kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.


