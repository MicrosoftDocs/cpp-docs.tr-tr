---
title: Visual Studio 'da CMake hata ayıklama oturumlarını yapılandırma
ms.date: 03/21/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 41f53c0c3ea46a8a1aa11215968aaee6c13c2dea
ms.sourcegitcommit: e33126222c418daf977533ea9e2819d99e0d7b8d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72534109"
---
# <a name="configure-cmake-debugging-sessions"></a>CMake hata ayıklama oturumlarını yapılandırma

Tüm yürütülebilir CMake hedefleri, **genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde gösterilir. Bir hata ayıklama oturumu başlatmak için yalnızca birini seçip hata ayıklayıcıyı başlatın.

![CMake başlangıç öğesi açılan kutusu](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılan kutusu")

Ayrıca, Çözüm Gezgini bir hata ayıklama oturumu başlatabilirsiniz. İlk olarak, **Çözüm Gezgini** penceresinde **CMake hedeflerini göster görünümü** ' ne geçin.

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png  "CMake hedefleri görünümü menü öğesi")

Ardından, herhangi bir yürütülebilir dosyaya sağ tıklayın ve **Hata Ayıkla** veya **Hata Ayıkla ve başlatma ayarları**' nı seçin. **Hata ayıklama** , etkin yapılandırmanıza bağlı olarak seçili hedefte hata ayıklamayı otomatik olarak başlatır. **Hata ayıklama ve başlatma ayarları** , *Launch. vs. JSON* dosyasını açar ve seçili hedef için yeni bir hata ayıklama yapılandırması ekler.

## <a name="customize-debugger-settings"></a>Hata ayıklayıcı ayarlarını özelleştirme

Projenizdeki herhangi bir çalıştırılabilir CMake hedefi için hata ayıklayıcı ayarlarını özelleştirmek için, belirli CMakeLists. txt dosyasına sağ tıklayın ve **Hata Ayıkla ve başlatma ayarları**' nı seçin. (Veya **Çözüm Gezgini**Içinde **hedefler görünümünde** bir hedef seçin.) Alt menüde CMake hedefini seçtiğinizde, **Launch. vs. JSON** adlı bir dosya oluşturulur. Bu dosya, seçtiğiniz CMake hedefi hakkındaki bilgilerle önceden doldurulmuştur ve program bağımsız değişkenleri veya hata ayıklayıcı türü gibi ek parametreler belirtmenize olanak sağlar. **Cmakesettings. JSON** dosyasındaki herhangi bir anahtara başvurmak için, bunu **Launch. vs. JSON**içinde `cmake.` ön yüz. Aşağıdaki örnek, şu anda seçili olan yapılandırma için **Cmakesettings. JSON** dosyasında `remoteCopySources` anahtarının değerini alan basit bir **Launch. vs. JSON** dosyasını gösterir:

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

**Launch. vs. JSON** dosyasını kaydettikten hemen sonra, **Başlangıç öğesi** açılan listesinde yeni adla bir giriş oluşturulur. **Launch. vs. JSON** dosyasını düzenleyerek, Istediğiniz sayıda CMake hedefi için dilediğiniz sayıda hata ayıklama yapılandırması oluşturabilirsiniz.

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings değişkenleri için destek

 **Launch. vs. JSON** , **cmakesettings. JSON** dosyasında belirtilen değişkenleri destekler (aşağıda görebilirsiniz) ve şu anda seçili yapılandırma için geçerlidir. Ayrıca, yerel bir proje için Başlatan uygulamanın geçerli dizinini ayarlayan `currentDir` adlı bir anahtara sahiptir:

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Uygulamayı çalıştırdığınızda `currentDir` değeri şuna benzer bir şeydir

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

' CWD ' anahtarı, uzak bir proje için Başlatan uygulamanın geçerli dizinini ayarlar. Varsayılan değer ' $ {DebugInfo. defaultWorkingDirectory} ' olarak değerlendirilir 

```cmd
/var/tmp/src/bfc6f7f4-4f0f-8b35-80d7-9198fa973fb9/Linux-Debug
```

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>
