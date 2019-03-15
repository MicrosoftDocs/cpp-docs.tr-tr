---
title: Hata ayıklama oturumları Visual Studio'da CMake yapılandırma
ms.date: 03/05/2019
helpviewer_keywords:
- CMake debugging
ms.openlocfilehash: 9a4dd009544a4590c336697ba2162eec45718869
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57824123"
---
# <a name="configure-cmake-debugging-sessions"></a>Hata ayıklama oturumları CMake yapılandırma

Tüm yürütülebilir CMake hedefleri gösterilen **başlangıç öğesi** açılır menüde **genel** araç çubuğu. Hata ayıklama oturumu başlatmak için birini seçin ve hata ayıklayıcıyı başlatın.

![CMake başlangıç öğesi açılan](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılır")

CMake menülerden bir hata ayıklama oturumu da başlatabilirsiniz.

## <a name="customize-debugger-settings"></a>Hata ayıklayıcı ayarları özelleştirme

Herhangi bir yürütülebilir CMake hedef projesinde hata ayıklayıcısı ayarlarını özelleştirmek için belirli CMakeLists.txt dosyasını sağ tıklatın ve seçin **hata ayıklama ve başlatma ayarları**. CMake hedef alt menüde seçtiğinizde, bir dosya olarak adlandırılan `launch.vs.json` oluşturulur. Bu dosya seçtiğiniz CMake hedef ilgili bilgilerle önceden doldurulur ve program bağımsız değişkenleri veya hata ayıklayıcı türü gibi ek parametreleri belirtmenizi sağlar. Herhangi bir tuşa başvurmak için bir `CMakeSettings.json` dosya, kendisiyle yazdığınızdan `cmake.` içinde `launch.vs.json`. Aşağıdaki örnek, basit bir gösterir `launch.vs.json` değerinde çeker dosya `remoteCopySources` anahtarını `CMakeSettings.json` şu anda seçili yapılandırma dosyası:

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

Kaydettiğiniz hemen sonra `launch.vs.json` dosyasının, bir giriş oluşturulduğunu **başlangıç öğesi** Yeni adla açılır. Düzenleyerek `launch.vs.json` dosya, CMake hedefleri herhangi bir sayıda için istediğiniz sayıda hata ayıklama yapılandırması gibi oluşturabilirsiniz.

## <a name="support-for-cmakesettings-variables"></a>CMakeSettings değişkenleri için destek

 `Launch.vs.json` bildirilen değişkenleri destekleyen `CMakeSettings.json` (aşağıya bakın) ve şu anda seçili yapılandırma için geçerli. Ayrıca adlı bir anahtar sahip `currentDir`, geçerli dizin başlatan uygulamanın ayarlar:

```json
{
  "type": "default",
  "project": "CMakeLists.txt",
  "projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
  "currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Değerini uygulamayı çalıştırdığınızda `currentDir` benzer bir şeydir

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>