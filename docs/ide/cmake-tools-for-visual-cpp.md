---
title: Visual C++'da CMake projeleri | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93cfa14e943e277b5255eeb486491c831eba0da3
ms.sourcegitcommit: 8c2de32e96c84d0147af3cce1e89e4f28707ff12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/26/2018
ms.locfileid: "50143737"
---
# <a name="cmake-projects-in-visual-c"></a>Visual C++'da CMake projeleri

Bu makalede, CMake, birden çok platformda çalışacak yapı işlemlerini tanımlamak için bir platformlar arası, açık kaynaklı araç aşina olduğunuzu varsayar.

Visual Studio 2015'te, Visual Studio kullanıcılarına kullanabileceğiniz bir [CMake Oluşturucu](https://cmake.org/cmake/help/v3.9/manual/cmake-generators.7.html) IDE için IntelliSense ardından tüketir, MSBuild proje dosyaları oluşturmak için göz atma ve derleme.

Visual Studio 2017'den itibaren **CMake için Visual C++ Araçları** bileşen **Klasör Aç** IDE CMake proje dosyaları (örneğin, CMakeLists.txt) doğrudan amaçları için kullanmak üzere etkinleştirmek için özelliği IntelliSense ve gözatma. Visual Studio Oluşturucu kullanırsanız, geçici bir proje dosyası oluşturulur ve msbuild.exe için geçirilen ancak hiçbir zaman IntelliSense ya amaçları için yüklenir.

**Visual Studio 2017 sürüm 15.3**: Ninja hem de Visual Studio oluşturucuları için destek sağlanır.

**Visual Studio 2017 sürüm 15.4**: Linux'ta CMake için destek eklendi. Daha fazla bilgi için [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

**Visual Studio 2017 sürüm 15.5**: Destek, var olan bir CMake önbelleğe almak için eklenir. Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve önceden doldurulmuş bir CMakeSettings.json dosyasına oluşturur.

**Visual Studio 2017 sürüm 15.7**: otomatik önbellek oluşturma, hedefleri Görünümü'nde devre dışı bırakmak için destek eklendiğinde **Çözüm Gezgini**ve tek dosyalı derleme.

## <a name="installation"></a>Yükleme

**CMake için Visual C++ Araçları** varsayılan olarak, bir parçası olarak yüklenen **C++ ile masaüstü geliştirme** iş yükü.

![C++ Masaüstü iş yükünde CMake bileşeni](media/cmake-install.png)

## <a name="ide-integration"></a>IDE tümleştirme

Seçeneğini belirlediğinizde **dosya | Açık | Klasör** CMakeLists.txt dosyasını içeren klasör Aç için aşağıdakiler gerçekleşir:

- Visual Studio ekler bir **CMake** görüntülemeyi ve düzenlemeyi CMake betikleri için komutlarla ana menüsüne menü öğesi.
- **Çözüm Gezgini** dosya ve klasör yapısını görüntüler.
- Visual Studio CMake.exe çalıştırır ve CMake önbelleği için varsayılan oluşturur *yapılandırma*, x86 olan hata ayıklama. CMake komut satırında görüntülenen **çıkış penceresine**, birlikte CMake ek çıktısı.  **Visual Studio 2017 sürüm 15.7 ve üzeri**: otomatik önbellek oluşturma devre dışı bırakılabilir içinde **araçları | Seçenekleri | CMake | Genel** iletişim.
- Arka planda gözatma bilgilerinin, yeniden düzenleme, IntelliSense, etkinleştirmek için kaynak dosyaları dizini oluşturmak ve benzeri Visual Studio başlatılır. Çalışırken, Visual Studio Düzenleyicisi'nde ve ayrıca disk dizinini kaynakları ile eşitlenmiş tutmak için değişiklikleri izler.

Herhangi bir sayıda CMake projelerini içeren klasörleri açabilirsiniz. Visual Studio algılar ve çalışma alanınızdaki tüm "Kök" CMakeLists.txt dosyaları yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama) yanı sıra C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projelerini kullanılabilir.

![Birden çok kök ile CMake projesi](media/cmake-multiple-roots.png)

**Visual Studio 2017 sürüm 15.7 ve üzeri**: mantıksal olarak hedefler tarafından düzenlenen projelerinizi da görüntüleyebilirsiniz. Seçin **hedefleyen görünümü** açılır listeden **Çözüm Gezgini** araç çubuğu:

![CMake hedefleri görüntüle düğmesi](media/cmake-targets-view.png)

## <a name="import-an-existing-cache"></a>Mevcut bir önbelleğe alma

Mevcut bir CMakeCache.txt dosyasını içe aktardığınızda, Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve önceden doldurulmuş oluşturur [CMakeSettings.json](#cmake_settings) dosya tabanlı bunlar üzerinde. Özgün önbellek herhangi bir şekilde değiştirilmez ve hala komut satırından veya oluşturmak için kullanılan herhangi bir aracı veya IDE ile kullanılabilir. Projenin kök CMakeLists.txt yanı sıra yeni bir CMakeSettings.json dosyasına yerleştirilir. Visual Studio oluşturur, yeni bir önbellek temel ayarları dosyası.

**Visual Studio 2017 sürüm 15.7 ve üzeri**: otomatik önbellek oluşturma işleminde geçersiz kılabilirsiniz **araçları | Seçenekleri | CMake | Genel** iletişim.

Her şey önbelleğinde aktarılır.  Oluşturucu ve derleyiciler konumu gibi özellikleri de IDE ile çalışacak şekilde bilinen varsayılan değerleri ile değiştirilir.

### <a name="to-import-an-existing-cache"></a>Mevcut bir önbellek içeri aktarmak için

1. Ana menüden **dosya | Açık | CMake**:

   ![CMake açın](media/cmake-file-open.png "dosya, açık, CMake")

   Bu işlem sonrasında **önbellekten içeri aktarma CMake** Sihirbazı.

2. İçeri aktarmak istediğiniz CMakeCache.txt dosyasına gidin ve ardından **Tamam**. **Önbellekten CMake projesini içeri aktarma** Sihirbazı görünür:

   ![CMake önbellek alma](media/cmake-import-wizard.png "CMake önbelleği Sihirbazı içeri aktarma")

   Sihirbaz tamamlandığında, yeni CMakeCache.txt dosyasında gördüğünüz **Çözüm Gezgini** kök CMakeLists.txt dosyasını projenize yanında.

## <a name="building-cmake-projects"></a>CMake proje oluşturma

CMake projesi oluşturmak için bu seçeneğiniz vardır:

1. Hedef seçin **hata ayıklama** açılan basın **F5**, veya **çalıştırmak** (yeşil üçgeni) düğmesini. Projeyi ilk olarak, yalnızca Visual Studio çözümü gibi otomatik olarak oluşturur.
1. Sağ tıklayın CMakeLists.txt ve select **derleme** bağlam menüsünden. Birden çok hedef klasör yapınız varsa, tüm veya tek bir belirli hedef oluşturmayı seçebilirsiniz.
1. Ana menüden **yapı | Çözüm yapı** (**F7** veya **Ctrl + Shift + B**). İçinde bir CMake hedef zaten seçili olduğundan emin olun **başlangıç öğesi** açılır menüde **genel** araç çubuğu.

![CMake derleme menü komutu](media/cmake-build-menu.png "CMake derleme komutu menüsü")

Etkin yapılandırma için bir Visual Studio oluşturucuyu seçildiğinde, MSBuild.exe ile çağrılan `-m -v:minimal` bağımsız değişkenler. Bir CMakeSettings.json dosyasına içinde derleme özelleştirmek için yapı sistemine geçirilecek ek komut satırı bağımsız değişkenleri belirtebilirsiniz `buildCommandArgs` özelliği:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

Beklediğiniz gibi yapı sonuçlarını gösterilen **çıkış penceresine** ve **hata listesi**.

![CMake derleme hatalarını](media/cmake-build-errors.png "CMake derleme hataları")

Seçebileceğiniz birden çok derleme hedefi bir klasörde **derleme** üzerinde öğesi **CMake** menüsü veya **CMakeLists.txt** oluşturmak için hangi CMake hedef belirtmek için bağlam menüsü. Tuşuna basarak **Ctrl + Shift + B** bir CMake proje geçerli etkin belgeyi oluşturur.

## <a name="debug-the-project"></a>Proje hata ayıklama

CMake projesi hata ayıklamak için tuşuna basın ve istenen yapılandırmayı seçin **F5**, veya basın **çalıştırma** araç çubuğu düğmesi. Varsa **çalıştırma** düğmesi "Başlangıç öğesi seçin" ifadesini içeren, açılan oku seçin ve çalıştırmak istediğiniz bir hedef seçin. ("Geçerli belgede" bir CMake projesini içinde seçenektir yalnızca .cpp dosyaları için geçerli.)

![CMake Çalıştır düğmesini](media/cmake-run-button.png "CMake çalıştırma düğmesine")

**Çalıştırma** veya **F5** komutları son derlemeden sonra değişiklikler yapılıp yapılmadığını proje önce oluşturun.

## <a name="configure-cmake-debugging-sessions"></a>Hata ayıklama oturumları CMake yapılandırma

Tüm yürütülebilir CMake hedefleri gösterilen **başlangıç öğesi** açılır menüde **genel** araç çubuğu. Hata ayıklama oturumu başlatmak için birini seçin ve hata ayıklayıcıyı başlatın.

![CMake başlangıç öğesi açılan](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılır")

CMake menülerden bir hata ayıklama oturumu da başlatabilirsiniz.

Herhangi bir yürütülebilir CMake hedef projesinde hata ayıklayıcısı ayarlarını özelleştirmek için belirli CMakeLists.txt dosyasını sağ tıklatın ve seçin **hata ayıklama ve başlatma ayarları**. CMake hedef alt menüde seçtiğinizde, launch.vs.json adlı bir dosya oluşturulur. Bu dosya seçtiğiniz CMake hedef ilgili bilgilerle önceden doldurulur ve program bağımsız değişkenleri veya hata ayıklayıcı türü gibi ek parametreleri belirtmenizi sağlar. Herhangi bir tuşa bir CMakeSettings.json dosyasına başvurmak için "CMake" ile başlayın Launch.vs.JSON içinde. Aşağıdaki örnek çeken bir basit launch.vs.json dosyası şu anda seçili yapılandırma için CMakeSettings.json dosyasındaki "remoteCopySources" anahtarının değerini gösterir:

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

Launch.vs.json dosyası kaydedildiğinde bir giriş oluşturulan **başlangıç öğesi** Yeni adla açılır. Launch.vs.json dosyasını düzenleyerek CMake hedefleri herhangi bir sayıda için istediğiniz sayıda hata ayıklama yapılandırması gibi oluşturabilirsiniz.

**Visual Studio 2017 sürüm 15.4**: Launch.vs.json (aşağıya bakın) CMakeSettings.json dosyanızdaki bildirilir ve şu anda seçili yapılandırmanın geçerli değişkenleri destekler. Ayrıca, geçerli dizin başlatan uygulamanın ayarlar "currentDir" adlı bir anahtar vardır:

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

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme

CMakeLists.txt dosyasını düzenlemek için sağ dosyasında tıklayın **Çözüm Gezgini** ve **açık**. Dosyaya değişiklik yaparsanız, sarı durum çubuğu görünür ve IntelliSense güncelleştirir ve güncelleştirme işlemi iptal etme fırsatı veren bildirir. CMakeLists.txt hakkında daha fazla bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   ![CMakeLists.txt dosyasını düzenleyerek](media/cmake-cmakelists.png "CMakeLists.txt dosyasını düzenleme")

Dosyayı kaydettikten hemen sonra yapılandırma adımını otomatik olarak yeniden çalıştırır ve bilgilerini görüntüler **çıkış** penceresi. Hatalar ve uyarılar gösterilir **hata listesi** veya **çıkış** penceresi. Hataya çift **hata listesi** CMakeLists.txt sorunlu satıra gidin.

   ![CMakeLists.txt dosyası hatalarını](media/cmake-cmakelists-error.png "CMakeLists.txt dosyası hataları")

## <a name="cmake_settings"></a> CMake ayarları ve özel yapılandırmalar

Varsayılan olarak, Visual Studio altı varsayılan CMake yapılandırmaları ("x86-Debug", "sürüm x86", "x64-Debug", "x64 yayın", "Linux-Debug" ve "Linux-sürüm") sağlar. Bu yapılandırmaları nasıl CMake.exe belirtilen proje için CMake önbelleği oluşturmak için çağrılan tanımlar. Bu yapılandırmaları değiştirmeniz veya yeni özel yapılandırma oluşturmak için seçin **CMake | CMake ayarlarını değiştir**, ayarlarının uygulanacağı CMakeLists.txt dosyasını seçin. **CMake ayarlarını değiştir** komut dosyanın bağlam menüsünde kullanılabilir ayrıca **Çözüm Gezgini**. Bu komut, proje klasöründe bir CMakeSettings.json dosyasına oluşturur. Bu dosya CMake önbellek dosyası, örneğin sonra yeniden oluşturmak için kullanılan bir **temiz** işlemi.

   ![CMake ana menü komutunu değiştirme ayarları](media/cmake-change-settings.png)

JSON IntelliSense CMakeSettings.json dosyasına düzenlemenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Aşağıdaki örnek, başlangıç noktası olarak kendi CMakeSettings.json oluşturmak için kullanabileceğiniz örnek yapılandırması gösterilmektedir:

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

1. **ad**: C++ yapılandırma açılan menüde görünen adı. Bu özellik değeri, bir makro ayrıca kullanılabilir `${name}`diğer özellik değerlerini belirtmek için. Bir örnek için bkz. **buildRoot** CMakeSettings.json tanımında.

1. **Oluşturucu**: eşlendiği **- G** geçin ve kullanılacak Oluşturucu belirtir. Bu özellik, bir makro ayrıca kullanılabilir `${generator}`, diğer özellik değerlerini belirtin yardımcı olmak için. Visual Studio şu anda aşağıdaki CMake oluşturucuları destekler:

    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 2015 14 ARM"
    - "Visual Studio 2015 14 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Ninja, esneklik ve işlevi yerine hızlı derleme hızı için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projelerini Ninja kullanarak doğru şekilde derlenmesi olabilir. Bu meydana gelirse, bunun yerine Visual Studio projesi oluşturmak için CMake bildirebilirsiniz.

Visual Studio Oluşturucu CMakeSettings.json ana menüden seçerek açın **CMake | CMake ayarlarını değiştir**. "Ninja" silin ve "V" yazın. Bu, istediğiniz Oluşturucu seçmenize olanak sağlayan IntelliSense etkinleştirir.

1. **buildRoot**: eşlendiği **-DCMAKE_BINARY_DIR** geçin ve CMake önbelleği oluşturulacağı belirtir. Klasör mevcut değilse oluşturulur.

1. **değişkenleri**: bir ad-değer çifti olarak geçirilen CMake değişkenlerinin içeren **-D** *_adı_=_değer_* CMake için. CMake projesi derleme Yönergeleriniz eklenmesi hiçbir değişkene doğrudan CMake önbellek dosyası belirtirseniz, bunları burada yerine eklemeniz önerilir. Aşağıdaki örnek, ad-değer çiftlerini belirtin gösterilmektedir:

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

1. **cmakeCommandArgs**: istediğiniz CMake.exe için geçirilecek herhangi ek anahtarlar belirtir.

2. **configurationType**: Seçili Oluşturucu için derleme yapılandırması türü tanımlar. Şu anda desteklenen değerler şunlardır: "Debug", "MinSizeRel", "Sürüm" ve "RelWithDebInfo".

3. **ctestCommandArgs**: testler çalıştırıldığında Ctest'e geçirilecek ek anahtarları belirtir.

4. **buildCommandArgs**: temel alınan geçirilecek ek anahtarlar derleme sistemi belirtir. Örneğin, Ninja oluşturucusunu kullanırken - v geçirme komut satırları çıkış Ninja zorlar.

### <a name="environment-variables"></a>Ortam değişkenleri

CMakeSettings.json alıcı ortam değişkenlerini yukarıdaki özelliklerinden herhangi birini de da destekler. Kullanılacak söz dizimi `${env.FOO}` % ortam değişkeni % FOO genişletin.
Ayrıca yerleşik makroları içinde bu dosyayı erişebilirsiniz:

- `${workspaceRoot}` – Çalışma klasörün tam yolunu sağlar.
- `${workspaceHash}` – Çalışma alanı konumu; karması Geçerli çalışma alanına (örneğin, klasör yollarında kullanılacak) için benzersiz bir tanımlayıcı oluşturmak için yararlı
- `${projectFile}` – kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}` – kök CMakeLists.txt dosyasını klasörün tam yolu
- `${thisFile}` – CMakeSettings.json dosyasının tam yolu
- `${name}` – yapılandırmasının adı
- `${generator}` – Bu yapılandırmasında kullanılan CMake oluşturucu adı

### <a name="ninja-command-line-arguments"></a>Ninja komut satırı bağımsız değişkenleri

'Default' hedef hedefleri belirtilmemişse oluşturur (kılavuza bakın).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --sürümü  | Yazdırma ninja sürümü ("1.7.1")|
|   -C DİZİNİ   | başka bir şey yapmadan önce DIR değiştirme|
|   -f dosyası  | Giriş derleme dosyası (default=build.ninja) belirtin|
|   -j N     | N işleri paralel olarak çalıştırma (varsayılan = 14, CPU kullanılabilir türetilmiş)|
|   -k N     | N başarısız işleri kadar kullanmaya devam edin (varsayılan = 1)|
|   N -m     | Yük ortalama N büyükse, yeni iş başlatma|
|   -n       | kuru çalıştırın (ancak bunlar başarılı gibi davranmasına komutlarını çalıştırma)|
|   -v       | yapı sırasında tüm komut satırları göster|
|   -d modu  | (-d listesini modları kullanın) hata ayıklamayı etkinleştir|
|   -t aracı  | bir subtool (kullanın -t listesini alt araçları) çalıştırın. TopLevel seçenekleri sonlandırır; Daha fazla bayrakları araç geçirilir|
|   -w BAYRAĞI  | Uyarılar (kullanın -w listesini uyarılar) ayarlama|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>Devralınmış ortamların (Visual Studio 2017 sürüm 15.5)

CMakeSettings.json devralınmış ortamların artık desteklemektedir. Bu özellik, (1) varsayılan ortamları devralır ve (2) çalıştığında CMake.exe için geçirilen özel ortam değişkenleri oluşturmanıza olanak sağlar.

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

CMakeSettings.json dosyanızda, özel ortam değişkenleri genel tanımlayabileceğiniz veya başına yapılandırmada **ortamları** özelliği. Aşağıdaki örnek bir genel değişken tanımlar **BuildDir**, x86 hata ayıklama ve x64 hata ayıklama yapılandırmaları devralınır. Her yapılandırma değişkeni değeri belirtmek için kullanır. **buildRoot** bu yapılandırma için özellik. Her yapılandırma nasıl kullandığını da unutmayın **inheritEnvironments** özelliği yalnızca o yapılandırmanız için geçerli bir değişken belirtin.

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

Sonraki örnekte, kendi değerini x86 hata ayıklama yapılandırmasını tanımlar **BuildDir** özelliği ve bu değeri geçersiz kılar, genel tarafından ayarlanan değer **BuildDir** özelliği böylece  **BuildRoot** değerlendiren `D:\custom-builddir\x86-Debug`.

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

## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

Önemli değişiklikler CMakeSettings.json veya CMakeLists.txt dosyaları, Visual Studio otomatik olarak yapıldığında tekrar bölümlerini CMake adım yapılandırın. Yapılandırma adımı hatasız tamamlanırsa toplanan bilgileri de derlemede C++ IntelliSense ve dil hizmetlerini kullanılabilir ve hata ayıklama işlemleri.

Birden çok CMake projeleri aynı CMake yapılandırma adı (örneğin, x86-Debug) kullandığınızda, bunların tümünün yapılandırılan ve oluşturulan (, kendi yapı kök klasöründe) Bu yapılandırma seçildiğinde. Tüm bu CMake yapılandırmasında katılan CMake projeleri hedeflerden ayıklayabilirsiniz.

   ![CMake yalnızca derleme menü öğesi](media/cmake-build-only.png "CMake yalnızca derleme menü öğesi")

Yapıları sınırlamak ve projelerin çalışma alanında bir alt kümesini oturumları hata ayıklama için CMakeSettings.json dosyasındaki benzersiz bir adla yeni bir yapılandırma oluşturmak ve yalnızca bu projeler için geçerlidir. Bu yapılandırma seçildiğinde, IntelliSense ve derleme ve hata ayıklama komutları yalnızca belirtilen desteklediği projeleri için etkinleştirilir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbellek hatalarında sorun giderme

Bir sorunu tanılamak için CMake önbelleğini durumu hakkında daha fazla bilgiye ihtiyacınız varsa, açık **CMake** ana menü veya **CMakeLists.txt** bağlam menüsünde **Çözüm Gezgini**şu komutları çalıştırmak için:

- **Önbellek görüntülemek** CMakeCache.txt dosyasını derleme kök klasörden Düzenleyicisi'nde açılır. (Önbelleğini temizlemek, CMakeCache.txt için burada yaptığınız tüm düzenlemeleri temizlendiğinde. Önbelleği temizledikten sonra kalıcı değişiklikler yapmak için bkz: [CMake ayarları ve özel yapılandırmalar](#cmake_settings) bu makalenin üst kısmındaki.)

- **Önbellek klasörü açın** derleme kök klasörü için bir Gezgin penceresi açılır.

- **Önbelleğini temizlemek** temiz önbellek'dan başlar adım böylece sonraki CMake yapılandırma derleme kök klasörü siler.

- **Önbelleği oluşturması** bile Visual Studio ortamı güncel dikkate oluşturma adım zorlar.

**Visual Studio 2017 sürüm 15.7 ve üzeri**: otomatik önbellek oluşturma devre dışı bırakılabilir içinde **araçları | Seçenekleri | CMake | Genel** iletişim.

## <a name="single-file-compilation"></a>Tek Dosyalı derleme

**Visual Studio 2017 sürüm 15.7 ve üzeri**: tek bir dosya içinde bir CMake projesini oluşturmak için dosyada sağ **Çözüm Gezgini** ve **derleme**. Ayrıca, düzenleyicide açık olan ana CMake menüsünü kullanarak dosyayı oluşturabilirsiniz:

![CMake tek dosyalı derleme](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>CMake komut satırından çalıştırma
CMake Visual Studio Yükleyicisi'nden yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Bkz: [komut satırında derleme](../build/building-on-the-command-line.md) daha fazla bilgi için.
1. Çıkış klasörüne geçin.
1. CMake derleme/Uygulamanızı yapılandırmak için çalıştırın.

