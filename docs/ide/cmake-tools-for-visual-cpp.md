---
title: Visual C++ projelerinde CMake | Microsoft Docs
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b9f00e511be43e5a6b77abae6394013e4e33a34
ms.sourcegitcommit: 2cca90d965f76ebf1d741ab901693a15d5b8a4df
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/24/2018
---
# <a name="cmake-projects-in-visual-c"></a>Visual C++ projelerinde CMake

Bu makale, CMake, birden fazla platformda çalışacak derleme işlemi tanımlamak için platformlar arası, açık kaynaklı bir aracı aşina olduğunuzu varsayar.

Yakın zamanda kadar Visual Studio kullanıcılarına CMake IDE sonra için IntelliSense tüketilen, MSBuild proje dosyalarını oluşturmak için kullanabilir gözatma ve derleme. Visual Studio 2017 ' Başlangıç **CMake için Visual C++ Araçları** bileşen **Klasör Aç** doğrudan amacıyla CMake proje dosyalarını (örneğin, CMakeLists.txt) kullanmak IDE etkinleştirmek için özellik IntelliSense ve tarama. Visual Studio Oluşturucu kullanırsanız, bir geçici proje dosyası oluşturulur ve msbuild.exe için geçirilen ancak hiçbir zaman IntelliSense veya gözatma amaçları için yüklenir. 

**Visual Studio 2017 sürüm 15.3**: Destek Ninja ve Visual Studio oluşturucuları için sağlanır.

**Visual Studio 2017 sürüm 15.4**: Linux'ta CMake için destek eklendi. Daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma](../linux/cmake-linux-project.md).

**Visual Studio 2017 sürüm 15,5**: varolan bir CMake önbelleğe almak için destek eklenir. Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve bir önceden doldurulmuş haldedir CMakeSettings.json dosyası oluşturur.


## <a name="installation"></a>Yükleme

**CMake için Visual C++ Araçları** varsayılan olarak bir parçası olarak yüklenen **C++ ile masaüstü geliştirme** iş yükü.

![C++ Masaüstü iş yükü CMake bileşeni](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE tümleştirme

Seçtiğinizde **dosya | Açık | Klasör** CMakeLists.txt dosyasını içeren klasörü açmak için aşağıdakiler gerçekleşir:

- Visual Studio ekler bir **CMake** menü komutları görüntüleme ve düzenleme CMake komut dosyaları için ana menü öğesine.
- **Çözüm Gezgini** dosya ve klasör yapısını görüntüler.
- Visual Studio CMake.exe çalışır ve varsayılan CMake önbelleğine oluşturur *yapılandırma*, x86 olduğu hata ayıklama. CMake komut satırı görüntülenir **çıktı penceresi**, CMake ek çıktısını yanı sıra.
- Arka planda gözatma bilgilerinin, yeniden düzenleme, IntelliSense etkinleştirmek için kaynak dosyalarını dizini oluşturmak ve benzeri Visual Studio başlatır. Çalışırken, Visual Studio düzenleyicisinde ve ayrıca dizinini kaynakları ile eşitlenmiş tutmak için disk üzerinde yapılan değişiklikleri izler.
 
Herhangi bir sayıda CMake projeleri içeren klasörleri açabilirsiniz. Visual Studio algılar ve tüm "root" CMakeLists.txt dosyaları çalışma alanınızda yapılandırır. CMake işlemleri (yapılandırma, yapı, hata ayıklama) yanı sıra C++ IntelliSense ve göz atma, tüm CMake projeleri çalışma alanınızdaki kullanılabilir.

![Birden çok kök CMake projeyle](media/cmake-multiple-roots.png) 

## <a name="import-an-existing-cache"></a>Varolan bir önbelleğe alma

Var olan bir CMakeCache.txt dosyasını içe aktardığınızda, Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve bunlar üzerinde dayalı bir önceden doldurulmuş haldedir CMakeSettings.json dosyası oluşturur. Özgün önbellek herhangi bir şekilde değiştirilmez ve hala komut satırından veya herhangi bir aracı ya da IDE oluşturmak için kullanılan ile kullanılabilir. Yeni CMakeSettings.json dosyası, projenin kök CMakeLists.txt yerleştirilir. Visual Studio'nun oluşturduğu yeni bir önbellek temel ayarları dosyası. Her şeyin önbelleğinde alınır.  Oluşturucunun ve derleyicileri konum gibi özellikleri de IDE ile çalışmak için bilinen varsayılanları ile değiştirilir.

### <a name="to-import-an-existing-cache"></a>Varolan bir önbelleğe almak için

1. Ana menüden **dosya | Açık | CMake**:

   ![Açık CMake](media/cmake-file-open.png "dosya, Aç, CMake") 

   Bu işlem sonrasında **alma CMake önbelleğinden** Sihirbazı. 
   
2. İçeri aktarmak istediğiniz CMakeCache.txt dosyasına gidin ve ardından **Tamam**. **Önbelleğinden CMake projeyi içeri aktarma** Sihirbazı görünür:

   ![Bir CMake önbelleğe alma](media/cmake-import-wizard.png "CMake alma önbellek Sihirbazı'nı açın") 

   Sihirbaz tamamlandığında yeni CMakeCache.txt dosyasında görebilirsiniz **Çözüm Gezgini** projenizi kök CMakeLists.txt dosyasında yanındaki.


## <a name="building-cmake-projects"></a>CMake proje oluşturma

CMake proje oluşturmak için bu seçeneğiniz vardır:

1. Hedef seçin **hata ayıklama** açılır ve tuşuna basın **F5**, veya **çalıştırmak** (yeşil üçgenle) düğmesini. Proje ilk olarak, yalnızca Visual Studio çözümü gibi otomatik olarak oluşturur.
1. Sağ tıklayın CMakeLists.txt ve select **yapı** ve bağlam menüsünden. Birden çok hedef klasörü yapısı içinde varsa, tüm ya da tek bir belirli hedef yapı seçebilirsiniz veya
1. Ana menüden seçin **yapı | Çözümü derlemek** (**F7** veya **Ctrl + Shift + B**). İçinde bir CMake hedef zaten seçili olduğundan emin olun **başlangıç öğesi** açılır listede **genel** araç.

![CMake derleme menü komutu](media/cmake-build-menu.png "Cmake yapı komut menüsü") 

Visual Studio Oluşturucu için etkin yapılandırma seçildiğinde MSBuild.exe çağrılıyor `-m -v:minimal` bağımsız değişkenler. CMakeSettings.json dosyası içindeki yapı özelleştirmek için derleme sistem geçirilmesi ek komut satırı bağımsız değişkenleri belirtebilirsiniz `buildCommandArgs` özelliği:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```

Beklediğiniz gibi yapı sonuçları gösterilmektedir **çıktı penceresi** ve **hata listesi**.
 
![CMake derleme hataları](media/cmake-build-errors.png "CMake derleme hataları")

Birden çok derleme hedefi bir klasörde seçtiğiniz **yapı** üzerinde öğesi **CMake** menüsü veya **CMakeLists.txt** bağlam menüsü oluşturmak için hangi CMake hedef belirtin. Tuşuna basarak **Ctrl + Shift + B** bir CMake projeyi geçerli etkin belgeyi oluşturur.

## <a name="debug-the-project"></a>Projeyi hata ayıklama

CMake projede hataları ayıklamak için tuşuna basın ve istenen yapılandırma tercih **F5**, veya basın **çalıştırmak** araç çubuğu düğmesini. Varsa **çalıştırmak** düğmesi "Başlangıç öğesi seçin" diyor, açılan oku seçin ve çalıştırmak istediğiniz bir hedef seçin. (CMake projesinde, "geçerli belgede" seçeneği geçerli yalnızca .cpp dosyaları için.) 

![CMake Çalıştır düğmesini](media/cmake-run-button.png "çalıştırmak Cmake düğmesi")


**Çalıştırmak** veya **F5** komutları önceki yapıdan sonra yapılan değişiklikler, proje önce oluşturun.

## <a name="configure-cmake-debugging-sessions"></a>Hata ayıklama oturumları CMake yapılandırın

Tüm yürütülebilir CMake hedefleri gösterilen **başlangıç öğesi** açılır listede **genel** araç. Hata ayıklama oturumu başlatmak için birini seçin ve hata ayıklayıcısı başlatın.

![CMake başlangıç öğesi açılır](media/cmake-startup-item-dropdown.png "CMake başlangıç öğesi açılır")


Ayrıca, bir hata ayıklama oturumu CMake menülerden başlatabilirsiniz.

Projenizdeki yürütülebilir herhangi CMake hedefi için hata ayıklayıcı ayarları özelleştirmek için belirli CMakeLists.txt dosyasını sağ tıklatın ve seçin **hata ayıklama ve başlatma ayarları**. Alt menüde CMake hedef seçtiğinizde, launch.vs.json adlı bir dosya oluşturulur. Bu dosya, seçtiğiniz CMake hedef hakkındaki bilgilerle önceden doldurulmuştur ve program bağımsız değişken veya hata ayıklayıcı türü gibi ek parametreler belirtmenizi sağlar. Herhangi bir tuşa CMakeSettings.json dosyasına başvurmak için "cmake" ile yazdığınızdan in launch.vs.json. Aşağıdaki örnek çeken bir basit launch.vs.json dosyası şu anda seçili yapılandırma CMakeSettings.json dosyasında "remoteCopySources" anahtar değeri gösterir:

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

Launch.vs.json dosyası kaydedildiğinde bir giriş oluşturulan **başlangıç öğesi** yeni adıyla açılır. Launch.vs.json dosyasını düzenleyerek CMake hedefleri herhangi bir sayı için istediğiniz gibi birçok hata ayıklama yapılandırmaları gibi oluşturabilirsiniz.

**Visual Studio 2017 sürüm 15.4**: Launch.vs.json CMakeSettings.json (aşağıya bakın) bildirilir ve şu anda seçili yapılandırma için geçerli olan değişkenleri destekler. Ayrıca, geçerli dizin başlatan uygulamanın ayarlar "currentDir" adlı bir anahtar vardır:


```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```

Uygulama, değerini çalıştırdığınızda `currentDir` benzer bir şeyin

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme

CMakeLists.txt dosyayı düzenlemek için sağ dosyasında tıklayın **Çözüm Gezgini** ve **açık**. Dosyaya değişiklik yaparsanız, sarı durum çubuğu görüntülenir ve IntelliSense güncelleştirir ve güncelleştirme işlemi iptal fırsatı veren size bildirir. CMakeLists.txt hakkında daha fazla bilgi için bkz: [CMake belgelerine](https://cmake.org/documentation/).

   ![CMakeLists.txt dosyasını düzenleyerek](media/cmake-cmakelists.png "CMakeLists.txt dosya düzenleme")


Dosyayı kaydettikten hemen yapılandırma adımı otomatik olarak yeniden çalıştırır ve bilgileri görüntüler **çıkış** penceresi. Hatalar ve uyarılar içinde gösterilir **hata listesi** veya **çıkış** penceresi. Bir hata çift **hata listesi** CMakeLists.txt sorunlu satırına gidin.

   ![CMakeLists.txt dosya hataları](media/cmake-cmakelists-error.png "CMakeLists.txt dosya hataları")

## <a name="cmake_settings"></a> CMake ayarları ve özel yapılandırmalar

Varsayılan olarak, Visual Studio altı varsayılan CMake yapılandırmaları ("x86-Debug", "x86-sürüm", "x64-Debug", "x64-sürüm", "Linux-Debug" ve "Linux-sürüm") sağlar. Bu yapılandırmalar CMake.exe belirli bir projenin CMake önbelleği oluşturmak için nasıl çağrıldığını tanımlayın. Bu yapılandırmaları değiştirmeniz veya yeni bir özel yapılandırma oluşturmak için Seç **CMake | CMake Ayarları Değiştir**ve ardından ayarları uygulamak CMakeLists.txt dosyası seçin. **CMake ayarlarını değiştir** komutu dosyanın bağlam menüsünde kullanılabilir de **Çözüm Gezgini**. Bu komutu proje klasöründe bir CMakeSettings.json dosyası oluşturur. Bu dosya CMake önbellek dosyası örneğin sonra yeniden oluşturmak için kullanılan bir **temiz** işlemi. 

   ![CMake ana menü komutu için ayarlarını değiştir](media/cmake-change-settings.png)


JSON IntelliSense CMakeSettings.json dosyasını düzenlemenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png "CMake JSON IntelliSense")

Aşağıdaki örnek, başlangıç noktası olarak kendi CMakeSettings.json oluşturmak için kullanabileceğiniz örnek bir yapılandırma gösterir:

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

1. **ad**: C++ yapılandırma açılır listede görünen adı. Bu özellik değeri bir makro da kullanılabilir `${name}`, diğer özellik değerleri belirtin. Bir örnek için bkz: **buildRoot** CMakeSettings.json tanımında.
1. **Oluşturucu**: eşlendiği **- G** geçin ve kullanılacak Oluşturucu belirtir. Bu özellik ayrıca, bir makro kullanılabilir `${generator}`, diğer özellik değerlerini belirtin yardımcı olacak. Visual Studio şu anda aşağıdaki CMake oluşturucuları destekler:


    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"

Ninja esneklik ve işlevi yerine hızlı derlemeleri hızları için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri düzgün Ninja kullanarak oluşturamadı olabilir. Bu gerçekleşirse, bunun yerine Visual Studio projesi oluşturmak için CMake söyleyebilirsiniz.

Visual Studio Oluşturucu CMakeSettings.json ana menüden seçerek açın **CMake | CMake Ayarları Değiştir**. "Ninja" silin ve "V" yazın. İstediğiniz Oluşturucu seçmenize olanak tanıyan IntelliSense etkinleştirir.

1. **buildRoot**: eşlendiği **-DCMAKE_BINARY_DIR** geçin ve CMake önbellek oluşturulacağı belirtir. Klasörün mevcut değilse oluşturulur.
1. **değişkenleri**: ad-değer çifti olarak geçirilen CMake değişkenlerin içeren **-D**_adı_**=**_değeri_ CMake için. CMake proje derleme yönergeleri hiçbir değişkene doğrudan CMake önbellek dosyası eklenmesi belirtirseniz, bunları burada yerine eklediğiniz önerilir.
1. **cmakeCommandArgs**: CMake.exe için geçirmek istediğiniz bir ek anahtar belirtir.
1. **configurationType**: Seçilen Oluşturucu yapı yapılandırma türü tanımlar. Şu anda desteklenen değerler "Hata ayıklama", "MinSizeRel", "Yayın" ve "RelWithDebInfo" dir.

### <a name="environment-variables"></a>Ortam değişkenleri

CMakeSettings.json tüketim ortam değişkenleri herhangi bir yukarıda belirtilen özellikleri de destekler. Kullanmak için söz dizimi `${env.FOO}` % % ortam değişkeniyle FOO genişletin.
Ayrıca bu dosya içinde yerleşik makroları erişim sahibi:

- `${workspaceRoot}` – Çalışma klasörün tam yolunu sağlar
- `${workspaceHash}` – karma çalışma konumunun; yararlı (örneğin, klasör yollarında kullanmak için) geçerli çalışma alanı için benzersiz bir tanımlayıcı oluşturmak için
- `${projectFile}` – kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}` – klasörünün kök CMakeLists.txt dosyasının tam yolu
- `${thisFile}` – CMakeSettings.json dosyasının tam yolu
- `${name}` – yapılandırmasının adı
- `${generator}` – Bu yapılandırmada kullanılan CMake oluşturucu adı

### <a name="ninja-command-line-arguments"></a>Ninja komut satırı bağımsız değişkenleri

'Default' hedef hedefleri belirtilmemişse oluşturur (el ile bakın).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|
|--------------|------------|
| --version  | Yazdırma ninja sürümü ("1.7.1")|
|   -C DIR   | başka bir şey yapmadan önce DIR değiştirme|
|   -f dosyası  | Giriş derleme dosyası (default=build.ninja) belirtin|
|   -j N     | N işleri paralel olarak çalıştırma (varsayılan = CPU kullanılabilir türetilmiş 14)|
|   -k N     | N başarısız işleri kadar gidiyor (varsayılan = 1)|
|   -l N     | Yük ortalama N büyükse, yeni işleri başlatma|
|   -n      | kuru çalıştırın (komutları çalıştırma ancak bunlar başarılı gibi hareket)|
|   -v       | derleme sırasında tüm komut satırları göster|
|   -d modu  | (kullanım -d listesini modları) hata ayıklamayı etkinleştir|
|   -t aracı  | subtool (kullanın -t listesini alt araçları) çalıştırın. TopLevel seçenekleri sonlandırır; Daha fazla bayrakları araç geçirilir| 
|   -w FLAG  | Uyarılar (kullanın -w listesini uyarıları) ayarla|

### <a name="inherited-environments-visual-studio-2017-version-155"></a>Devralınan ortamları (Visual Studio 2017 sürüm 15,5)
CMakeSettings.json artık devralınan ortamları destekler. Bu özellik (1) varsayılan ortamları devralır ve (2) çalıştırıldığında CMake.exe için geçirilen özel ortam değişkenleri oluşturmanıza olanak sağlar.

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Yukarıdaki örnekte çalışan aynıdır **VS 2017 için geliştirici komut istemi** ile **-arch amd64 =-host_arch amd64 =** bağımsız değişkenler.

Aşağıdaki tabloda, varsayılan değerleri ve komut satırı eşdeğerleri gösterilmektedir:

|Bağlam adı|Açıklama|
|-----------|-----------------|
|vsdev|Varsayılan Visual Studio ortamı|
|msvc_x86|X86 kullanarak x86 için derleme araçları|
|msvc_arm| X86 kullanarak ARM için derleme araçları|
|msvc_arm64|X86 kullanarak derleme ARM64 için Araçlar|
|msvc_x86_x64|X86 kullanarak derleme AMD64 için Araçlar|
|msvc_x64_x64|AMD64 için 64-bit araçlarını kullanarak derleme|
|msvc_arm_x64|64-bit araçlarını kullanarak ARM için derleme|
|msvc_arm64_x64|Derleme ARM64 için 64-bit araçlarını kullanma|

### <a name="custom-environment-variables"></a>Özel ortam değişkenleri
CMakeSettings.json içinde özel ortam değişkenleri genel tanımlayabilirsiniz veya her yapılandırmada **ortamları** özelliği. Aşağıdaki örnek, bir genel değişkeni tanımlar **BuildDir**, x86 hata ayıklama ve x64-Debug yapılandırmalarını devralındı. Her yapılandırma değişkeni için değer belirtmek için kullanır. **buildRoot** bu yapılandırma için özellik. Ayrıca her yapılandırma nasıl kullandığını unutmayın **inheritEnvironments** özelliği yalnızca bu yapılandırma için geçerli bir değişken belirtin.

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

Sonraki örnekte kendi değerini x86 hata ayıklama yapılandırmasını tanımlayan **BuildDir** özellik ve bu değerin geçersiz kılmaları genel tarafından ayarlanan değer **BuildDir** özelliği böylece  **BuildRoot** değerlendiren `D:\custom-builddir\x86-Debug`.

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

Önemli değişiklikler CMakeSettings.json veya CMakeLists.txt dosyalar, Visual Studio için otomatik olarak yapıldığında yeniden CMake'ı çalıştıran adım yapılandırın. Yapılandırma adımı hatasız tamamlanırsa, toplanan bilgileri de yapı C++ IntelliSense ve dil Hizmetleri'nde kullanılabilir ve işlemleri hata ayıklama.

Birden çok CMake projeleri aynı CMake yapılandırma adı (örneğin, x86-Debug) kullandığınızda, bunların tümünün yapılandırılır ve (kendi yapı kök klasöründe) yerleşik bu yapılandırma seçildiğinde. Tüm bu CMake yapılandırmasında katılmak CMake projeleri hedeflerden ayıklayabilirsiniz.

   ![CMake yalnızca derleme menü öğesi](media/cmake-build-only.png "CMake yalnızca derleme menü öğesi")

Yapıları sınırlamak ve projelerin çalışma alanında bir alt kümesini oturumlarını hata ayıklamak için CMakeSettings.json dosyasındaki benzersiz bir adla yeni bir yapılandırma oluşturmak ve yalnızca bu projeler için geçerlidir. Bu yapılandırma seçildiğinde, IntelliSense, yapı ve hata ayıklama komutları yalnızca belirtilen bu projeleri için etkinleştirilir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbellek hatalarında sorun giderme

Bir sorunu tanılamak için CMake önbellek durumuyla ilgili daha fazla bilgiye ihtiyacınız varsa, açık **CMake** ana menü veya **CMakeLists.txt** bağlam menüsünde **Çözüm Gezgini**aşağıdaki komutlardan birini çalıştırmak için:

- **Önbellek görüntülemek** Düzenleyicisi'nde yapı kök klasörden CMakeCache.txt dosyasını açar. (Önbelleğini temizlemek, burada CMakeCache.txt için yaptığınız düzenlemeler temizlenir. Önbellek temizlendikten sonra kalıcı değişiklikler yapmak için bkz: [CMake ayarları ve özel yapılandırmaları](#cmake_settings) bu makalenin önceki.)
- **Önbellek klasörü açın** yapı kök klasörüne Explorer penceresi açar.  
- **Önbelleği Temizle** sonraki CMake yapılandırma adımı başlatır temiz önbelleğinden böylece yapı kök klasörünü siler.
- **Önbellek oluşturmak** generate adım Visual Studio ortamında güncel göz önünde bulundurur olsa bile çalışmaya zorlar.
