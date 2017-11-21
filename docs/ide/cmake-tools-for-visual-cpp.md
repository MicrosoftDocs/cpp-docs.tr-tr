---
title: Visual C++ projelerinde CMake | Microsoft Docs
ms.custom: 
ms.date: 08/08/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 770b7f70e52859b1489b984d8aef3c3876a9ca83
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="cmake-projects-in-visual-c"></a>Visual C++ projelerinde CMake
Bu makale, CMake, birden fazla platformda çalışacak derleme işlemi tanımlamak için platformlar arası, açık kaynaklı bir aracı aşina olduğunuzu varsayar.  

Yakın zamanda kadar Visual Studio kullanıcılarına CMake IDE sonra için IntelliSense tüketilen, MSBuild proje dosyalarını oluşturmak için kullanabilir gözatma ve derleme. Visual Studio 2017 ' Başlangıç **CMake için Visual C++ Araçları** bileşen "Klasör Aç" özelliği doğrudan amacıyla IntelliSense ve tarama CMake proje dosyalarını (örneğin, CMakeLists.txt) kullanmak IDE etkinleştirmek için kullanır. Visual Studio Oluşturucu kullanırsanız, bir geçici proje dosyası oluşturulur ve msbuild.exe için geçirilen ancak hiçbir zaman IntelliSense veya gözatma amaçları için yüklenir. 

**Visual Studio 2017 sürüm 15.3**: Destek Ninja ve Visual Studio oluşturucuları için sağlanır.

**Visual Studio 2017 sürüm 15.4**: Linux'ta CMake için destek eklendi. Daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma](../linux/cmake-linux-project.md).

## <a name="installing"></a>Yükleme
Visual C++ Araçları CMake için varsayılan C++ iş yükü ile masaüstü geliştirme bir parçası olarak yüklenir.

![C++ Masaüstü iş yükü CMake bileşeni](media/cmake-install.png)
 
## <a name="ide-integration"></a>IDE tümleştirme
Seçtiğinizde **dosya | Açık | Klasör** CMakeLists.txt dosyasını içeren klasörü açmak için aşağıdakiler gerçekleşir:
- Visual Studio ekler bir **CMake** menü komutları görüntüleme ve düzenleme CMake komut dosyaları için ana menü öğesine. 
- **Çözüm Gezgini** dosya ve klasör yapısını görüntüler. 
- Visual Studio CMake.exe çalışır ve varsayılan CMake önbelleğine oluşturur *yapılandırma*, x86 olduğu hata ayıklama. CMake komut satırı görüntülenir **çıktı penceresi**, CMake ek çıktısını yanı sıra.
- Arka planda gözatma bilgilerinin, yeniden düzenleme, IntelliSense etkinleştirmek için kaynak dosyalarını dizini oluşturmak ve benzeri Visual Studio başlatır. Çalışırken, Visual Studio düzenleyicisinde ve ayrıca dizinini kaynakları ile eşitlenmiş tutmak için disk üzerinde yapılan değişiklikleri izler. Herhangi bir sayıda CMake projeleri içeren klasörleri açabilirsiniz. Visual Studio algılar ve tüm "root" CMakeLists.txt dosyaları çalışma alanınızda yapılandırır. CMake işlemleri (yapılandırma, yapı, hata ayıklama) yanı sıra C++ IntelliSense ve göz atma, tüm CMake projeleri çalışma alanınızdaki kullanılabilir.

![Birden çok kök CMake projeyle](media/cmake-multiple-roots.png) 

## <a name="building-cmake-projects"></a>CMake proje oluşturma
CMake proje oluşturmak için bu seçeneğiniz vardır:
1. Hata ayıklama açılır ve tuşuna hedef seçin **F5** veya "Çalıştır" düğmesini tıklatın. Proje otomatik olarak ayarlanır yapı ilk olarak, Visual Studio çözümleriyle olduğu gibi.
2.  Üzerinde CMakeLists.txt sağ tıklatın ve bağlam menüsünden yapı seçin. Birden çok hedef klasörü yapısı içinde varsa, tüm ya da tek bir belirli hedef yapı seçebilirsiniz veya
  
3. Ana menüden seçin **yapı | Çözümü derlemek** (**F7** veya **Ctrl + Shift + B**) (bir CMake hedefi olarak zaten seçildiğinden emin olun **başlangıç öğesi** açılır**Genel** araç).

![CMake derleme menü komutu](media/cmake-build-menu.png) 
 
Visual Studio Oluşturucu için etkin yapılandırma seçildiğinde MSBuild.exe çağrılıyor `-m -v:minimal` bağımsız değişkenler. CMakeSettings.json dosyası içindeki yapı özelleştirmek için derleme sistem geçirilmesi ek komut satırı bağımsız değişkenleri belirtebilirsiniz `buildCommandArgs` özelliği:

```json
"buildCommandArgs": "-m:8 -v:minimal -p:PreferredToolArchitecture=x64"
```
Beklediğiniz gibi yapı sonuçları gösterilmektedir **çıktı penceresi** ve **hata listesi**.
 
![CMake derleme hataları](media/cmake-build-errors.png)

Birden çok derleme hedefi bir klasörde CMake menü veya oluşturmak için hangi CMake hedef belirtmek için CMakeLists.txt bağlam menüsü üzerinde yapı öğesini seçebilirsiniz. Tuşuna basarak **Ctrl + Shift + B** bir CMake projeyi geçerli etkin belgeyi oluşturur. 

## <a name="debugging-the-project"></a>Projeyi hata ayıklama
CMake projede hataları ayıklamak için tuşuna basın ve istenen yapılandırma tercih **F5**, veya araç çubuğunda Çalıştır düğmesine basın. Çalıştır düğmesini diyorsa "Başlangıç öğesi seçin", bulunan aşağı oka tıklayın ve çalıştırmak istediğiniz bir hedef seçin. (CMake projesinde, "geçerli belgede" seçeneği geçerli yalnızca .cpp dosyaları için.) 

 ![Çalıştırma CMake düğmesi](media/cmake-run-button.png)

 Tuşuna basarak **F5** önceki yapıdan sonra yapılan değişiklikler, ilk derleme projesi olur.

## <a name="configuring-cmake-debugging-sessions"></a>Hata ayıklama oturumları CMake yapılandırma
Tüm yürütülebilir CMake hedefleri başlangıç öğesi açılır genel araç çubuğunda gösterilir. Hata ayıklama oturumu başlatmak için birini seçin ve hata ayıklayıcısı başlatın.

 ![CMake başlangıç öğesi açılır](media/cmake-startup-item-dropdown.png)

Ayrıca, bir hata ayıklama oturumu CMake menülerden başlatabilirsiniz.

Projenizdeki yürütülebilir herhangi CMake hedefi için hata ayıklayıcı ayarları özelleştirmek için belirli CMakeLists.txt dosyasını sağ tıklatın ve seçin **hata ayıklama ve başlatma ayarları**, bir CMake hedef alt menüsünde, adlı bir dosya seçin Launch.vs.JSON oluşturulur. Bu dosya, seçtiğiniz CMake hedef hakkındaki bilgilerle önceden doldurulmuştur ve program bağımsız değişken veya hata ayıklayıcı türü gibi ek parametreler belirtmenizi sağlar. Herhangi bir tuşa CMakeSettings.json dosyasına başvurmak için "cmake" ile yazdığınızdan Launch.vs.JSON içinde. Aşağıdaki örnek çeken bir basit launch.vs.json dosyası şu anda seçili yapılandırma CMakeSettings.json dosyasında "remoteCopySources" anahtar değeri gösterir:

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
Launch.vs.json dosyası kaydedildiğinde bir giriş başlangıç öğesi açılan yeni adıyla oluşturulur. Launch.vs.json dosyasını düzenleyerek CMake hedefleri herhangi bir sayı için istediğiniz gibi birçok hata ayıklama yapılandırmaları gibi oluşturabilirsiniz.

**Visual Studio 2017 sürüm 15.4**: Launch.vs.json bildirilen değişkenler CMakeSettings.json (aşağıya bakın) destekler. Ayrıca, "başlatan uygulamanın geçerli dizin ayarlanan currentDir", bir kavramı vardır:

```json
{
"type": "default",
"project": "CMakeLists.txt",
"projectTarget": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"name": "CMakeHelloWorld1.exe (C:\\Users\\satyan\\CMakeBuilds\\Test\\Debug\\CMakeHelloWorld1.exe)",
"currentDir": "${env.USERPROFILE}\\CMakeBuilds\\${workspaceHash}"
}
```
Uygulama, değerini çalıştırdığınızda `currentDir` olduğu 

```cmd
C:\Users\satyan\7f14809a-2626-873e-952e-cdf038211175\
```
 

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme
CMakeLists.txt dosyayı düzenlemek için sağ dosyasında tıklayın **Çözüm Gezgini** ve **açık**. Dosyaya değişiklik yaparsanız, sarı durum çubuğu görüntülenir ve IntelliSense güncelleştirir ve güncelleştirme işlemi iptal fırsatı veren size bildirir. CMakeLists.txt hakkında daha fazla bilgi için bkz: [CMake belgelerine](https://cmake.org/documentation/).

  ![CMakeLists.txt dosya düzenleme](media/cmake-cmakelists.png)

Dosyayı kaydettikten hemen yapılandırma adımı otomatik olarak yeniden çalıştırın ve bilgi çıkış penceresinde görüntüle. Hataları ve uyarıları hata listesini veya çıktı penceresinde gösterilir. Hatayla CMakeLists.txt sorunlu satırda gitmek için hata listesine çift tıklayın.

  ![CMakeLists.txt dosya hataları](media/cmake-cmakelists-error.png)
 
## <a name="cmake_settings"></a>CMake ayarları ve özel yapılandırmalar
Varsayılan olarak, Visual Studio altı varsayılan CMake yapılandırmaları ("x86-Debug", "x86-sürüm", "x64-Debug", "x64-sürüm", "Linux-Debug" ve "Linux-sürüm") sağlar. Bu yapılandırmalar CMake.exe belirli bir projenin CMake önbelleği oluşturmak için nasıl çağrıldığını tanımlayın. Bu yapılandırmaları değiştirmeniz veya yeni bir özel yapılandırma oluşturmak için Seç **CMake | Değiştirme CMake ayarı**ve ardından ayarları uygulanır CMakeLists.txt dosyası seçin. Ayarları Değiştir CMake dosyanın bağlam menüsünde de kullanılabilir **Çözüm Gezgini**. Bu komutu proje klasöründe bir CMakeSettings.json dosyası oluşturur. Bu dosya CMake önbellek dosyası, örneğin "Temiz" işleminden sonra yeniden oluşturmak için kullanılır. 

  ![CMake ana menü komutu için ayarlarını değiştir](media/cmake-change-settings.png)
 
JSON IntelliSense CMakeSettings.json dosyasını düzenlemenize yardımcı olur:

   ![CMake JSON IntelliSense](media/cmake-json-intellisense.png)

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
1.  Ad: C++ yapılandırma açılır listede görünen adı. Bu özellik değeri makro olarak da kullanılabilir `${name}` diğer özellik değerleri belirtin. Örneğin, CMakeSettings.json "buildRoot" tanımında bakın.
2.  Oluşturucu: eşler -G geçin ve kullanılacak Oluşturucu belirtir. Bu özellik ayrıca makro olarak kullanılabilir `${generator}` diğer özellik değerlerini belirtin yardımcı olacak. Visual Studio şu anda aşağıdaki CMake oluşturucuları destekler:
    - "Ninja"
    - "Visual Studio 14 2015"
    - "Visual Studio 14 2015 ARM"
    - "Visual Studio 14 2015 Win64"
    - "Visual Studio 15 2017"
    - "Visual Studio 15 2017 ARM"
    - "Visual Studio 15 2017 Win64"
    - 
Ninja esneklik ve işlevi yerine hızlı derlemeleri hızları için tasarlandığından, varsayılan olarak ayarlanır. Ancak, bazı CMake projeleri düzgün Ninja kullanarak oluşturamadı olabilir. Bu gerçekleşirse, bunun yerine Visual Studio projesi oluşturmak için CMake söyleyebilirsiniz. 

Visual Studio Oluşturucu CMakeSettings.json ana menüden seçerek açın **CMake | CMake Ayarları Değiştir**. "Ninja" silin ve "V" yazın. İstediğiniz Oluşturucu seçmenize olanak tanıyan IntelliSense etkinleştirir.
3.  buildRoot: DCMAKE_BINARY_DIR anahtara - eşler ve CMake önbellek oluşturulacağı belirtir. Klasörün mevcut değilse oluşturulur.
4.  değişkenler: - Dname geçirilen CMake değişkenleri ad + değer çiftinden içeren CMake değerine =. CMake proje derleme yönergeleri değişkenlerin doğrudan CMake önbellek dosyası ekleme belirtirseniz, bunları burada yerine eklediğiniz önerilir.
5.  cmakeCommandArgs: CMake.exe için geçirmek istediğiniz bir ek anahtar belirtir.
6.  configurationType: Seçilen Oluşturucu yapı yapılandırma türü tanımlar. Şu anda desteklenen değerler "Hata ayıklama", "MinSizeRel", "Yayın" ve "RelWithDebInfo" dir.

### <a name="environment-variables"></a>Ortam değişkenleri
CMakeSettings.json tüketim ortam değişkenleri herhangi bir yukarıda belirtilen özellikleri de destekler. Kullanmak için söz dizimi `${env.FOO}` % % ortam değişkeniyle FOO genişletin.
Ayrıca bu dosya içinde yerleşik makroları erişim sahibi:
- `${workspaceRoot}`– Çalışma klasörün tam yolunu sağlar
- `${workspaceHash}`– karma çalışma konumunun; yararlı (örneğin, klasör yollarında kullanmak için) geçerli çalışma alanı için benzersiz bir tanımlayıcı oluşturmak için
- `${projectFile}`– kök CMakeLists.txt dosyasının tam yolu
- `${projectDir}`– klasörünün kök CMakeLists.txt dosyasının tam yolu
- `${thisFile}`– CMakeSettings.json dosyasının tam yolu
- `${name}`– yapılandırmasının adı
- `${generator}`– Bu yapılandırmada kullanılan CMake oluşturucu adı

### <a name="ninja-command-line-arguments"></a>Ninja komut satırı bağımsız değişkenleri

'Default' hedef hedefleri belirtilmemişse oluşturur (el ile bakın).

```cmd
C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise>ninja -?
ninja: invalid option -- `-?'
usage: ninja [options] [targets...]
```

|Seçenek|Açıklama|  
|--------------|------------|  
| --Sürüm  | Yazdırma ninja sürümü ("1.7.1")| 
|   -C DIR   | başka bir şey yapmadan önce DIR değiştirme| 
|   -f dosyası  | Giriş derleme dosyası [default=build.ninja] belirtin| 
|   -j N     | N işleri paralel olarak çalıştırma [varsayılan = CPU kullanılabilir türetilmiş 14]| 
|   -k N     | N başarısız işleri kadar gidiyor [varsayılan = 1]| 
|   -l N     | Yük ortalama N büyükse, yeni işleri başlatma| 
|   -n      | kuru çalıştırın (komutları çalıştırma ancak bunlar başarılı gibi hareket)| 
|   -v       | derleme sırasında tüm komut satırları göster| 
|   -d modu  | (kullanım -d listesini modları) hata ayıklamayı etkinleştir| 
|   -t aracı  | subtool (kullanın -t listesini alt araçları) çalıştırın. TopLevel seçenekleri sonlandırır; Daha fazla bayrakları araç geçirilir| 
|   -w BAYRAĞI  | Uyarılar (kullanın -w listesini uyarıları) ayarla| 


### <a name="inherited-environments-visual-studio-2017-version-155"></a>Devralınan ortamları (Visual Studio 2017 sürüm 15,5)

CmakeSettings.json artık inherted ortamları destekler. Bu özellik olanak sağlayan özel bir değişken oluşturabilirsiniz:

```json
  "inheritEnvironments": [ "msvc_x64_x64" ]
```

Bu alan çalıştırıldığında, CMake.exe için otomatik olarak geçirilir değişkenleri ayarlar. Yukarıdaki örnekte "Geliştirici komut istemi" VS 2017 için çalışan ile aynıdır `-arch=amd64 -host_arch=amd64` bağımsız değişkenler.

Aşağıdaki tabloda, desteklenen değerler ve komut satırı eşdeğerleri gösterilmektedir:

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


Önemli değişiklikler CMakeSettings.json veya CMakeLists.txt dosyalar, Visual Studio için otomatik olarak yapıldığında yeniden CMake'ı çalıştıran adım yapılandırın. Yapılandırma adımı hatasız tamamlanırsa, toplanan bilgileri C++ IntelliSense ve dil hizmetleri hem de yapı kullanılabilir ve hata ayıklama işlemleri.

Birden çok CMake projeleri aynı CMake yapılandırma adı (örneğin, x86-Debug) kullandığınızda, bunların tümünün yapılandırılır ve (kendi yapı kök klasöründe) yerleşik bu yapılandırma seçildiğinde. Tüm bu CMake yapılandırmasında katılmak CMake projeleri hedeflerden ayıklayabilirsiniz.

   ![CMake yalnızca derleme menü öğesi](media/cmake-build-only.png)

Yapıları sınırlamak ve projelerin çalışma alanında bir alt kümesini oturumlarını hata ayıklamak için CMakeSettings.json dosyasındaki benzersiz bir adla yeni bir yapılandırma oluşturmak ve yalnızca bu projeler için geçerlidir. Bu yapılandırma olduğunda, derleme, IntelliSense, seçili ve hata ayıklama etkinleştirilecek yalnızca bu projeleri belirtilen için.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbellek hatalarında sorun giderme
Bir sorunu tanılamak için CMake önbellek durumuyla ilgili daha fazla bilgiye ihtiyacınız varsa, CMake ana menü veya CMakeLists.txt bağlam menüsünden açmak **Çözüm Gezgini** aşağıdaki komutlardan birini çalıştırmak için:
- **Önbellek görüntülemek** Düzenleyicisi'nde yapı kök klasörden CMakeCache.txt dosyasını açar. (Önbelleğini temizlemek, burada CMakeCache.txt için yaptığınız düzenlemeler temizlenir. Önbellek temizlendikten sonra kalıcı değişiklikler yapmak için bkz: [CMake ayarları ve özel yapılandırmaları](#cmake_settings) bu makalenin önceki.)
- **Önbellek klasörü açın** yapı kök klasörüne Explorer penceresi açar.  
- **Önbelleği Temizle** sonraki CMake yapılandırma adımı başlatır temiz önbelleğinden böylece yapı kök klasörünü siler.
- **Önbellek oluşturmak** generate adım Visual Studio ortamında güncel göz önünde bulundurur olsa bile çalışmaya zorlar.

