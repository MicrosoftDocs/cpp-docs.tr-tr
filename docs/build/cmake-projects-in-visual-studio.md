---
title: Visual Studio'da CMake projeleri
ms.date: 03/05/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: b055a1e3ca1d43cc0a1633401c1a08a3d54c1a31
ms.sourcegitcommit: 90817d9d78fbaed8ffacde63f3add334842e596f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/20/2019
ms.locfileid: "58278456"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio'da CMake projeleri

CMake, birden çok platformda çalışacak yapı işlemlerini tanımlamak için platformlar arası, açık kaynaklı bir araçtır. Bu makalede, CMake ile ilgili bilgi sahibi olduğunuz varsayılır. Adresinden hakkında daha fazla bilgi [derleme, Test ve paket Your yazılım CMake ile](https://cmake.org/).

Visual Studio 2015'te, Visual Studio kullanıcılarına kullanabileceğiniz bir [CMake Oluşturucu](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) IDE için IntelliSense ardından tüketir, MSBuild proje dosyaları oluşturmak için göz atma ve derleme.

Visual Studio 2017'yi tanıtır, CMake için zengin destek de dahil olmak üzere [platformlar arası CMake projelerini](../linux/cmake-linux-project.md). **CMake için Visual C++ Araçları** bileşen **Klasör Aç** IntelliSense ve gözatma amacıyla doğrudan IDE CMake proje dosyaları (örneğin, CMakeLists.txt) kullanmak üzere etkinleştirmek için özellik. Ninja hem de Visual Studio oluşturucuları desteklenir. Visual Studio Oluşturucu kullanırsanız, geçici bir proje dosyası oluşturulur ve msbuild.exe için geçirilen ancak hiçbir zaman IntelliSense ya amaçları için yüklenir. Mevcut bir CMake önbelleği içeri aktarabilirsiniz; Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve önceden doldurulmuş oluşturur `CMakeSettings.json` dosya. 

## <a name="installation"></a>Yükleme

**CMake için Visual C++ Araçları** varsayılan olarak, bir parçası olarak yüklenen **C++ ile masaüstü geliştirme** iş yükü ve bir parçası olarak **C++ ile Linux geliştirme** iş yükü.

![C++ Masaüstü iş yükünde CMake bileşeni](media/cmake-install.png)

Daha fazla bilgi için [Visual Studio'da C++ Linux iş yükünü yükleyin](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE tümleştirme

Seçeneğini belirlediğinizde **dosya | Açık | Klasör** CMakeLists.txt dosyasını içeren klasör Aç için aşağıdakiler gerçekleşir:

- Visual Studio ekler bir **CMake** görüntülemeyi ve düzenlemeyi CMake betikleri için komutlarla ana menüsüne menü öğesi.

- **Çözüm Gezgini** dosya ve klasör yapısını görüntüler.

- Visual Studio CMake.exe çalışır ve isteğe bağlı olarak CMake önbelleği için varsayılan oluşturur *yapılandırma*, x86 olan hata ayıklama. CMake komut satırında görüntülenen **çıkış penceresine**, birlikte CMake ek çıktısı.

- Arka planda gözatma bilgilerinin, yeniden düzenleme, IntelliSense, etkinleştirmek için kaynak dosyaları dizini oluşturmak ve benzeri Visual Studio başlatılır. Çalışırken, Visual Studio Düzenleyicisi'nde ve ayrıca disk dizinini kaynakları ile eşitlenmiş tutmak için değişiklikleri izler.

Herhangi bir sayıda CMake projelerini içeren klasörleri açabilirsiniz. Visual Studio algılar ve çalışma alanınızdaki tüm "Kök" CMakeLists.txt dosyaları yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama) yanı sıra C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projelerini kullanılabilir.

![Birden çok kök ile CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, mantıksal olarak hedefler tarafından düzenlenen projelerinizi görüntüleyebilirsiniz. Seçin **hedefleyen görünümü** açılır listeden **Çözüm Gezgini** araç çubuğu:

![CMake hedefleri görüntüle düğmesi](media/cmake-targets-view.png)

Visual Studio kullanan adlı bir dosya `CMakeSettings.json` ortam değişkenlerini veya komut satırı seçeneklerini Cmake.exe depolamak için. `CMakeSettings.json` Ayrıca etkinleştirir, tanımlamak ve birden çok CMake depolamak için derleme yapılandırmaları ve IDE'de bunlar arasında kolayca geçiş. 

Aksi takdirde kullanın `CMakeLists.txt` gibi kaynak dosyaları belirtme, kitaplıkları bulma, derleyici ve bağlayıcı seçenekleri ve diğer yapı sistemini belirtmek için bir CMake projesini ilgili bilgileri.

Hata ayıklama zaman bir yürütülebilir dosya için bağımsız değişkenleri geçirmek gerekiyorsa, adlı başka bir dosya kullanabilirsiniz `launch.vs.json`. Bazı senaryolarda, Visual Studio, bu dosyaları otomatik olarak oluşturur; bunları el ile düzenleyebilirsiniz. Ayrıca kendiniz dosyası oluşturabilirsiniz.

> [!NOTE]
> Klasör Aç projelerinin diğer türleri için iki ek JSON dosyaları kullanılır: `CppProperties.json` ve `tasks.vs.json`. Hiçbirini CMake projeleri için uygundur.

## <a name="import-an-existing-cache"></a>Mevcut bir önbelleğe alma

Mevcut bir CMakeCache.txt dosyasını içe aktardığınızda, Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve önceden doldurulmuş oluşturur [ `CMakeSettings.json` ](#cmake_settings) dosya tabanlı bunlar üzerinde. Özgün önbellek herhangi bir şekilde değiştirilmez ve hala komut satırından veya oluşturmak için kullanılan herhangi bir aracı veya IDE ile kullanılabilir. Yeni `CMakeSettings.json` dosyası, projenin kök CMakeLists.txt yanı sıra yerleştirilir. Visual Studio oluşturur, yeni bir önbellek temel ayarları dosyası. Otomatik önbellek oluşturma işleminde geçersiz kılabilirsiniz **araçları | Seçenekleri | CMake | Genel** iletişim.

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

1. Genel araç çubuğunda Bul **yapılandırmaları** açılır; bu büyük olasılıkla "Linux-hata ayıklama" veya "x64-Debug" varsayılan olarak göstermez. İstenen yapılandırma seçip ENTER tuşuna **F5**, veya **çalıştırmak** araç çubuğunda (yeşil üçgeni). Projeyi ilk olarak, yalnızca Visual Studio çözümü gibi otomatik olarak oluşturur.

1. Sağ tıklayın CMakeLists.txt ve select **derleme** bağlam menüsünden. Birden çok hedef klasör yapınız varsa, tüm veya tek bir belirli hedef oluşturmayı seçebilirsiniz.

1. Ana menüden **yapı | Çözüm yapı** (**F7** veya **Ctrl + Shift + B**). İçinde bir CMake hedef zaten seçili olduğundan emin olun **başlangıç öğesi** açılır menüde **genel** araç çubuğu.

![CMake derleme menü komutu](media/cmake-build-menu.png "CMake derleme komutu menüsü")

CMakeLists.txt dosyasıyla kullanarak değiştirmeden derleme yapılandırmaları, ortam değişkenleri, komut satırı bağımsız değişkenleri ve diğer ayarları özelleştirebilirsiniz `CMakeSettings.json` dosya. Daha fazla bilgi için [CMake özelleştirme ayarları](customize-cmake-settings.md).

Beklediğiniz gibi yapı sonuçlarını gösterilen **çıkış penceresine** ve **hata listesi**.

![CMake derleme hatalarını](media/cmake-build-errors.png "CMake derleme hataları")

Seçebileceğiniz birden çok derleme hedefi bir klasörde **derleme** üzerinde öğesi **CMake** menüsü veya **CMakeLists.txt** oluşturmak için hangi CMake hedef belirtmek için bağlam menüsü. Tuşuna basarak **Ctrl + Shift + B** bir CMake proje geçerli etkin belgeyi oluşturur.

## <a name="debugging-cmake-projects"></a>CMake projelerini hata ayıklama

CMake projesi hata ayıklamak için tuşuna basın ve istenen yapılandırmayı seçin **F5**, veya basın **çalıştırma** araç çubuğu düğmesi. Varsa **çalıştırma** düğmesi "Başlangıç öğesi seçin" ifadesini içeren, açılan oku seçin ve çalıştırmak istediğiniz bir hedef seçin. ("Geçerli belgede" bir CMake projesini içinde seçenektir yalnızca .cpp dosyaları için geçerli.)

![CMake Çalıştır düğmesini](media/cmake-run-button.png "CMake çalıştırma düğmesine")

**Çalıştırma** veya **F5** komutları son derlemeden sonra değişiklikler yapılıp yapılmadığını proje önce oluşturun.

Hata ayıklama oturumu özellikleri ayarlayarak bir CMake özelleştirebilirsiniz `launch.vs.json` dosya. Daha fazla bilgi için [hata ayıklama oturumları CMake yapılandırma](configure-cmake-debugging-sessions.md).


## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme

CMakeLists.txt dosyasını düzenlemek için sağ dosyasında tıklayın **Çözüm Gezgini** ve **açık**. Dosyaya değişiklik yaparsanız, sarı durum çubuğu görünür ve IntelliSense güncelleştirir ve güncelleştirme işlemi iptal etme fırsatı veren bildirir. CMakeLists.txt hakkında daha fazla bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   ![CMakeLists.txt dosyasını düzenleyerek](media/cmake-cmakelists.png "CMakeLists.txt dosyasını düzenleme")

Dosyayı kaydettikten hemen sonra yapılandırma adımını otomatik olarak yeniden çalıştırır ve bilgilerini görüntüler **çıkış** penceresi. Hatalar ve uyarılar gösterilir **hata listesi** veya **çıkış** penceresi. Hataya çift **hata listesi** CMakeLists.txt sorunlu satıra gidin.

   ![CMakeLists.txt dosyası hatalarını](media/cmake-cmakelists-error.png "CMakeLists.txt dosyası hataları")


## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

Ne zaman önemli değişiklikler yapıldıysa `CMakeSettings.json` veya CMakeLists.txt dosyasına Visual Studio otomatik olarak CMake yeniden çalıştırır adım yapılandırın. Yapılandırma adımı hatasız tamamlanırsa toplanan bilgileri de derlemede C++ IntelliSense ve dil hizmetlerini kullanılabilir ve hata ayıklama işlemleri.

Birden çok CMake projeleri aynı CMake yapılandırma adı (örneğin, x86-Debug) kullandığınızda, bunların tümünün yapılandırılan ve oluşturulan (, kendi yapı kök klasöründe) Bu yapılandırma seçildiğinde. Tüm bu CMake yapılandırmasında katılan CMake projeleri hedeflerden ayıklayabilirsiniz.

   ![CMake yalnızca derleme menü öğesi](media/cmake-build-only.png "CMake yalnızca derleme menü öğesi")

Yapıları sınırlamak ve projelerin çalışma alanında bir alt kümesini oturumları hata ayıklama için benzersiz bir adla yeni bir yapılandırma oluşturun `CMakeSettings.json` dosya ve yalnızca bu projeler için geçerlidir. Bu yapılandırma seçildiğinde, IntelliSense ve derleme ve hata ayıklama komutları yalnızca belirtilen desteklediği projeleri için etkinleştirilir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbellek hatalarında sorun giderme

Bir sorunu tanılamak için CMake önbelleğini durumu hakkında daha fazla bilgiye ihtiyacınız varsa, açık **CMake** ana menü veya **CMakeLists.txt** bağlam menüsünde **Çözüm Gezgini**şu komutları çalıştırmak için:

- **Önbellek görüntülemek** CMakeCache.txt dosyasını derleme kök klasörden Düzenleyicisi'nde açılır. (Önbelleğini temizlemek, CMakeCache.txt için burada yaptığınız tüm düzenlemeleri temizlendiğinde. Önbelleği temizledikten sonra kalıcı değişiklikler yapmak için bkz: [CMake ayarları ve özel yapılandırmalar](#cmake_settings) bu makalenin üst kısmındaki.)

- **Önbellek klasörü açın** derleme kök klasörü için bir Gezgin penceresi açılır.

- **Önbelleğini temizlemek** temiz önbellek'dan başlar adım böylece sonraki CMake yapılandırma derleme kök klasörü siler.

- **Önbelleği oluşturması** bile Visual Studio ortamı güncel dikkate oluşturma adım zorlar.

Otomatik önbellek oluşturma devre dışı bırakılabilir içinde **araçları | Seçenekleri | CMake | Genel** iletişim.

## <a name="single-file-compilation"></a>Tek Dosyalı derleme

Tek bir dosya içinde bir CMake projesini oluşturmak için dosyada sağ **Çözüm Gezgini** ve **derleme**. Ayrıca, düzenleyicide açık olan ana CMake menüsünü kullanarak dosyayı oluşturabilirsiniz:

![CMake tek dosyalı derleme](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>CMake komut satırından çalıştırma

CMake Visual Studio Yükleyicisi'nden yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Bkz: [komut satırında derleme](building-on-the-command-line.md) daha fazla bilgi için.

1. Çıkış klasörüne geçin.

1. CMake derleme/Uygulamanızı yapılandırmak için çalıştırın.
  
## <a name="see-also"></a>Ayrıca Bkz.

[Öğretici: Visual Studio’da platformlar arası C++ projeleri oluşturma](get-started-linux-cmake.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/>
[CMakeSettings.json başvurusu](cmakesettings-reference.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[Önceden tanımlanmış CMake yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>
