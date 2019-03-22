---
title: Visual Studio'da CMake derleme ayarlarını özelleştirme
ms.date: 03/05/2019
helpviewer_keywords:
- CMake build settings
ms.openlocfilehash: dd34fbefcbc89c7c4aa93105ae5bad31ae4d5f01
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328304"
---
# <a name="customize-cmake-build-settings"></a>CMake derleme ayarlarını özelleştirme

Visual Studio CMake.exe belirtilen proje için CMake önbelleği oluşturmak için nasıl çağrılan tanımlayan çeşitli CMake yapılandırmaları sağlar. Yeni bir yapılandırma eklemek için araç çubuğundaki açılan Yapılandırması'nı tıklatın ve seçin **yapılandırmaları yönetme**:

   ![CMake yapılandırmaları yönetme](media/cmake-manage-configurations.png)

Önceden tanımlanmış yapılandırmaları listesinden seçim yapabilirsiniz:

   ![Önceden tanımlanmış CMake yapılandırmaları](media/cmake-configurations.png)

İlk kez bir yapılandırma seçin, Visual Studio oluşturur bir `CMakeSettings.json` , projenin kök klasöründeki dosya. Bu dosya CMake önbellek dosyası, örneğin sonra yeniden oluşturmak için kullanılan bir **temiz** işlemi. 

Ek bir yapılandırma eklemek için sağ tıklayın `CMakeSettings.json` ve **Yapılandırması Ekle**. 

   ![CMake ekleme Yapılandırması](media/cmake-add-configuration.png "CMake Yapılandırması Ekle")

JSON IntelliSense düzenlemenize yardımcı olan `CMakeSettings.json` dosyası:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Kullanarak dosyayı düzenleyebilirsiniz **CMake ayarları Düzenleyicisi**. Sağ tıklayın `CMakeSettings.json` içinde **Çözüm Gezgini** ve **CMake ayarlarını Düzenle**. Ya da seçin **yapılandırmaları yönetme** Düzenleyicisi penceresinin üst kısmındaki açılan yapılandırmasından. 

Doğrudan düzenleyebilirsiniz `CMakeSettings.json` aşağıdaki örnekte özel yapılandırmaları oluşturmak için başlangıç noktası olarak kullanabileceğiniz bir örnek yapılandırması gösterilmektedir:

```json
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "installRoot": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\install\\${name}",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "-v",
      "ctestCommandArgs": ""
    },

```

- **ad**: C++ yapılandırma açılan menüde görünen adı. `${name}` Makrosu yolları gibi diğer özellik değerlerini oluştururken bu değeri kullanmanıza olanak sağlar. Bir örnek için bkz. **buildRoot** tanımında `CMakeSettings.json`.

- **Oluşturucu**: eşler için CMake **- G** geçin ve kullanılacak Oluşturucu belirtir. Bu özellik, bir makro ayrıca kullanılabilir `${generator}`, diğer özellik değerlerini oluştururken. Visual Studio şu anda aşağıdaki CMake oluşturucuları destekler:

  - "Ninja"
  - "Visual Studio 14 2015"
  - "Visual Studio 14 2015 ARM"
  - "Visual Studio 14 2015 Win64"
  - "Visual Studio 15 2017"
  - "Visual Studio 15 2017 ARM"
  - "Visual Studio 15 2017 Win64"

  Ninja, esneklik ve işlevi yerine hızlı derleme hızı için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projelerini Ninja kullanarak doğru şekilde derlenmesi olabilir. Bu meydana gelirse, bunun yerine Visual Studio projesi oluşturmak için CMake bildirebilirsiniz.

  Visual Studio Oluşturucu belirtmek için açık `CMakeSettings.json` seçerek ana menüden **CMake | CMake ayarlarını değiştir**. "Ninja" silin ve "V" yazın. Bu, istediğiniz Oluşturucu seçmenize olanak sağlayan IntelliSense etkinleştirir.

  Etkin yapılandırma bir Visual Studio oluşturucuyu belirttiğinde, varsayılan olarak MSBuild.exe ile çağrılan `-m -v:minimal` bağımsız değişkenler. Derleme içinde özelleştirmek için `CMakeSettings.json` , belirtebileceğiniz ek dosya [MSBuild komut satırı bağımsız değişkenleri](../build/reference/msbuild-visual-cpp-overview.md) yapı sistemi geçirilecek `buildCommandArgs` özelliği:
    
    ```json
    "buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
    ```

- **buildRoot**: eşlendiği **-DCMAKE_BINARY_DIR** geçin ve CMake önbelleği oluşturulacağı belirtir. Klasör mevcut değilse oluşturulur.

- **değişkenleri**: bir ad-değer çifti olarak geçirilen CMake değişkenlerinin içeren **-D** *_adı_=_değer_* CMake için. CMake projesi derleme Yönergeleriniz eklenmesi hiçbir değişkene doğrudan CMake önbellek dosyası belirtirseniz, bunları burada yerine eklemeniz önerilir. Aşağıdaki örnek 14.14.26428 için ad-değer çiftlerini belirtin gösterilmiştir MSVC araç takımı:

```json
"variables": [
    {
      "name": "CMAKE_CXX_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    },
    {
      "name": "CMAKE_C_COMPILER",
      "value": "C:/Program Files (x86)/Microsoft Visual Studio/157/Enterprise/VC/Tools/MSVC/14.14.26428/bin/HostX86/x86/cl.exe"
    }
  ]
```

- **cmakeCommandArgs**: istediğiniz CMake.exe için geçirilecek herhangi ek anahtarlar belirtir.

- **configurationType**: Seçili Oluşturucu için derleme yapılandırması türü tanımlar. Şu anda desteklenen değerler şunlardır: "Debug", "MinSizeRel", "Sürüm" ve "RelWithDebInfo".

- **ctestCommandArgs**: testler çalıştırıldığında Ctest'e geçirilecek ek anahtarları belirtir.

- **buildCommandArgs**: temel alınan geçirilecek ek anahtarlar derleme sistemi belirtir. Örneğin, Ninja oluşturucusunu kullanırken - v geçirme komut satırları çıkış Ninja zorlar.

Ek ayarları CMake Linux projeleri için kullanılabilir. Bkz: [CMake Linux projesi yapılandırma](../linux/cmake-linux-project.md).

## <a name="environment-variables"></a>Ortam değişkenleri

 `CMakeSettings.json` Ayrıca, yukarıda belirtilen özelliklerinden herhangi birini kullanan ortam değişkenlerini destekler. Kullanılacak söz dizimi `${env.FOO}` % ortam değişkeni % FOO genişletin.
Ayrıca yerleşik makroları içinde bu dosyayı erişebilirsiniz:

- `${workspaceRoot}` – Çalışma klasörün tam yolunu sağlar.
- `${workspaceHash}` – Çalışma alanı konumu; karması Geçerli çalışma alanına (örneğin, klasör yollarında kullanılacak) için benzersiz bir tanımlayıcı oluşturmak için yararlı
- `${projectFile}` – kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}` – kök CMakeLists.txt dosyasını klasörün tam yolu
- `${thisFile}` – tam yolunu `CMakeSettings.json` dosyası
- `${name}` – yapılandırmasının adı
- `${generator}` – Bu yapılandırmasında kullanılan CMake oluşturucu adı

## <a name="ninja-command-line-arguments"></a>Ninja komut satırı bağımsız değişkenleri

'Default' hedef hedefleri belirtilmemişse oluşturur (kılavuza bakın).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --version  | Yazdırma ninja sürümü ("1.7.1")|
|   -C DİZİNİ   | başka bir şey yapmadan önce DIR değiştirme|
|   -f dosyası  | Giriş derleme dosyası (default=build.ninja) belirtin|
|   -j N     | N işleri paralel olarak çalıştırma (varsayılan = 14, CPU kullanılabilir türetilmiş)|
|   -k N     | N başarısız işleri kadar kullanmaya devam edin (varsayılan = 1)|
|   N -m     | Yük ortalama N büyükse, yeni iş başlatma|
|   -n       | kuru çalıştırın (ancak bunlar başarılı gibi davranmasına komutlarını çalıştırma)|
|   -v       | yapı sırasında tüm komut satırları göster|
|   -d modu  | (-d listesini modları kullanın) hata ayıklamayı etkinleştir|
|   -t aracı  | bir subtool (kullanın -t listesini alt araçları) çalıştırın. üst düzey seçenekleri sonlandırır; Daha fazla bayrakları araç geçirilir|
|   -w BAYRAĞI  | Uyarılar (kullanın -w listesini uyarılar) ayarlama|

## <a name="inherited-environments"></a>Devralınan ortamlar

 `CMakeSettings.json` ortamları destekler devralındı. Bu özellik, (1) varsayılan ortamları devralır ve (2) çalıştığında CMake.exe için geçirilen özel ortam değişkenleri oluşturmanıza olanak sağlar.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Yukarıdaki örnekte çalışan aynıdır **VS 2017 için geliştirici komut istemi** ile **-arch = amd64-host_arch amd64 =** bağımsız değişkenler.

Aşağıdaki tabloda, varsayılan değerleri gösterir:

|İçerik adı|Açıklama|
|-----------|-----------------|
|vsdev|Varsayılan Visual Studio ortamı|
|msvc_x86|X86 kullanarak x86 için derleme araçları|
|msvc_arm| X86 kullanarak ARM için derleme araçları|
|msvc_arm64|ARM64 için x86 kullanarak derleme araçları|
|msvc_x86_x64|AMD64 için x86 kullanarak derleme araçları|
|msvc_x64_x64|AMD64 için 64-bit araçlarını kullanarak derleme|
|msvc_arm_x64|64-bit araçlarını kullanarak ARM için derleme|
|msvc_arm64_x64|ARM64 için 64-bit araçlarını kullanarak derleme|

### <a name="custom-environment-variables"></a>Özel ortam değişkenleri

İçinde `CMakeSettings.json`, genel olarak özel ortam değişkenleri tanımlayabilir veya başına yapılandırmada **ortamları** özelliği. Aşağıdaki örnek bir genel değişken tanımlar **BuildDir**, x86 hata ayıklama ve x64 hata ayıklama yapılandırmaları devralınır. Her yapılandırma değişkeni değeri belirtmek için kullanır. **buildRoot** bu yapılandırma için özellik. Her yapılandırma nasıl kullandığını da unutmayın **inheritEnvironments** özelliği yalnızca o yapılandırmanız için geçerli bir değişken belirtin.

```json
{
  // The "environments" property is an array of key value pairs of the form
  // { "EnvVar1": "Value1", "EnvVar2": "Value2" }
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}\\build",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x86 compiler.
      "inheritEnvironments": [ "msvc_x86" ],
      "buildRoot": "${env.BuildDir}\\${name}"    },
    {
      "name": "x64-Debug",
      "generator": "Ninja",
      "configurationType": "Debug",
      // Inherit the defaults for using the MSVC x64 compiler.
      "inheritEnvironments": [ "msvc_x64" ],
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

Sonraki örnekte, kendi değerini x86 hata ayıklama yapılandırmasını tanımlar **BuildDir** özelliği. Bu değer, genel tarafından ayarlanan değer geçersiz kılar **BuildDir** özelliği böylece **BuildRoot** değerlendiren `D:\custom-builddir\x86-Debug`.

```json
{
  "environments": [
    {
      "BuildDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}",
    }
  ],

  "configurations": [
    {
      "name": "x86-Debug",

      // The syntax for this property is the same as the global one above.
      "environments": [
        {
          // Replace the global property entirely.
          "BuildDir": "D:\\custom-builddir",
        }
      ],

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x86" ],
      // Evaluates to "D:\custom-builddir\x86-Debug"
      "buildRoot": "${env.BuildDir}\\${name}"
    },
    {
      "name": "x64-Debug",

      "generator": "Ninja",
      "configurationType": "Debug",
      "inheritEnvironments": [ "msvc_x64" ],
      // Since this configuration doesn’t modify BuildDir, it inherits
      // from the one defined globally.
      "buildRoot": "${env.BuildDir}\\${name}"
    }
  ]
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Visual Studio'da CMake projeleri](cmake-projects-in-visual-studio.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>
