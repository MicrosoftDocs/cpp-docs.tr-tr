---
title: Visual Studio'da CMake projeleri
description: Visual Studio'da CMake'i kullanarak C++ projeleri oluşturma ve oluşturma.
ms.date: 01/08/2020
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 49ba53eaa8ac075ab6d3b2a66f33160c5c3ec410
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329168"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio'da CMake projeleri

CMake, birden çok platformda çalışan yapı işlemlerini tanımlamak için çapraz platformlu, açık kaynak kodlu bir araçtır. Bu makalede CMake aşina olduğunuzu varsayar. Bu konuda daha fazla bilgi için [Build, Test ve Paketi Yazılımınızı CMake ile](https://cmake.org/)öğrenebilirsiniz.

> [!NOTE]
> CMake son birkaç sürümlerinde Visual Studio ile daha entegre hale gelmiştir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

Windows bileşeni **için C++ CMake araçları,** CMake proje dosyalarını *(CMakeLists.txt*gibi) doğrudan IntelliSense ve tarama amacıyla kullanmak için [Açık Klasör](open-folder-projects-cpp.md) özelliğini kullanır. Hem Ninja hem de Visual Studio jeneratörleri desteklenir. Visual Studio jeneratörü kullanıyorsanız, geçici bir proje dosyası oluşturur ve msbuild.exe'ye aktarılır. Ancak, proje IntelliSense veya tarama amacıyla yüklenmez. Varolan bir CMake önbelleğini de içe aktarabilirsiniz.

## <a name="installation"></a>Yükleme

**Windows için C++ CMake araçları,** **C++** iş yüklerine sahip C++ ve Linux Geliştirme **ile Masaüstü geliştirmenin** bir parçası olarak yüklenir. Daha fazla bilgi için [çapraz platform CMake projelerine](../linux/cmake-linux-project.md)bakın.

![C++ Masaüstü iş yükünde CMake bileşeni](media/cmake-install-2019.png)

Daha fazla bilgi için [Bkz. Visual Studio'da C++ Linux iş yükünü yükleyin.](../linux/download-install-and-setup-the-linux-development-workload.md)

## <a name="ide-integration"></a>IDE Tümleştirme

*CMakeLists.txt* dosyasını içeren bir klasörü açmak için **Dosya > Aç > Klasörünü** seçtiğinizde, aşağıdaki şeyler olur:

- Visual Studio, CMake komutlarını görüntülemek ve düzenlemek için komutlarla **Proje** menüsüne **CMake** öğeleri ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio cmake.exe çalışır ve varsayılan (x64 Hata Ayıklama) yapılandırması için CMake önbellek dosyası *(CMakeCache.txt)* oluşturur. CMake komut **satırı,** CMake'in ek çıktısıyla birlikte Çıkış Penceresinde görüntülenir.

- Arka planda Visual Studio, IntelliSense'i etkinleştirmek için kaynak dosyalarını dizine eklemeye, bilgilere göz atma, yeniden düzenleme ve benzeri bilgileri eklemeye başlar. Siz çalışırken Visual Studio, dizinini kaynaklarla eşit tutmak için düzenleyicideki ve diskteki değişiklikleri izler.

İstediğiniz sayıda CMake projesi içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "root" *CMakeLists.txt* dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, oluşturma, hata ayıklama), C++ IntelliSense ve tarama çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok köklü CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, hedeflere göre mantıksal olarak düzenlenen projelerinizi de görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğundaki açılır görünümden **Hedefler görünümünü** seçin:

![CMake hedefleri görünüm düğmesi](media/cmake-targets-view.png)

Tüm CMake tarafından oluşturulan çıktıyı *dış/yapı/config\<>* klasörlerinde görmek için **Solution Explorer'ın** üst kısmındaki Tüm **Dosyaları Göster** düğmesini tıklatın.

Visual Studio **CMakeSettings.json**adlı bir yapılandırma dosyası kullanır. Bu dosya, birden çok yapı yapılandırması tanımlamanızı ve depolamanızı ve IDE'de bunlar arasında kolayca geçiş yapmanızı sağlar. *Yapılandırma,* belirli bir yapı türüne özgü ayarları kapsülleyen bir Visual Studio yapısıdır. Ayarlar, Visual Studio'nun cmake.exe'ye geçtiği varsayılan komut satırı seçeneklerini yapılandırmak için kullanılır. Ayrıca burada ek CMake seçenekleri belirtebilir ve istediğiniz ek değişkenleri tanımlayabilirsiniz. Tüm seçenekler CMake önbelleğine dahili veya harici değişkenler olarak yazılır. Visual Studio 2019'da **CMake Ayarlar Düzenleyicisi** ayarlarınızı değiştirmenin kullanışlı bir yolunu sunar. Daha fazla bilgi için [CMake ayarlarını özelleştir'e](customize-cmake-settings.md)bakın.

Bir ayar, `intelliSenseMode` CMake geçirilir değil, ancak Visual Studio tarafından kullanılır.

**CMakeLists.txt** dosyasını her proje klasöründe, herhangi bir CMake projesinde olduğu gibi kullanın. Kaynak dosyaları belirtebilir, kitaplıkları bulabilir, derleyici ve bağlayıcı seçeneklerini ayarlayabilir ve sistemle ilgili diğer bilgileri belirtebilirsiniz.

Bağımsız değişkenleri hata ayıklama zamanında yürütülebilir bir dosyaya geçirmek için **launch.vs.json**adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda Visual Studio bu dosyaları otomatik olarak oluşturur. Bunları el ile dinleyebilir, hatta dosyayı kendiniz oluşturabilirsiniz.

> [!NOTE]
> Açık Klasör projelerinin diğer türleri için iki ek JSON dosyası kullanılır: **CppProperties.json** ve **tasks.vs.json**. Bunların hiçbiri CMake projeleri için ilgili değildir.

## <a name="open-an-existing-cache"></a>Varolan bir önbelleği açma

Varolan bir CMake önbellek dosyasını *(CMakeCache.txt)* açtığınızda, Visual Studio önbelleğinizi yönetmeye ve sizin için ağaç oluşturmaya çalışmaz. Özel veya tercih edilen araçlarınız, CMake'in projenizi nasıl yapılandırdığını tam olarak kontrol eder. Visual Studio'da varolan bir önbelleği açmak için **Dosya > Açık > CMake'i**seçin. Ardından, varolan bir *CMakeCache.txt* dosyasına gidin.

Açık bir projeye varolan bir CMake önbelleği ekleyebilirsiniz. Yeni bir yapılandırma eklediğiniz şekilde yapılır. Daha fazla bilgi için Visual [Studio'da mevcut bir önbellek açma](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)hakkındaki blog yazımıza bakın.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

Bir CMake projesi oluşturmak için şu seçeneklere sahipsiniz:

1. Genel araç çubuğunda, **Configurations** açılır düşüşünü bulun. Muhtemelen varsayılan olarak "x64-Hata Ayıklama" gösterir. Tercih edilen yapılandırmayı seçin ve **F5**tuşuna basın veya araç çubuğundaki **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje otomatik olarak ilk oluşturur, bir Visual Studio çözüm gibi.

1. *CMakeLists.txt'ye* sağ tıklayın ve bağlam menüsünden **Oluştur'u** seçin. Klasör yapınızda birden çok hedefiniz varsa, tümünü veya yalnızca belirli bir hedefi oluşturmayı seçebilirsiniz.

1. Ana menüden **Yapı > Tümünü Oluştur** **(F7** veya **Ctrl+Shift+B)** seçeneğini belirleyin. **Genel** araç çubuğundaki **Başlangıç Öğesi** açılır düşüşünde bir CMake hedefinin zaten seçildiğinden emin olun.

![CMake build menü komutu](media/cmake-build-menu.png "CMake build komut menüsü")

Beklediğiniz gibi, yapı sonuçları **Çıktı Penceresi** ve **Hata Listesinde**gösterilir.

![CYapı hataları oluşturma](media/cmake-build-errors.png "CYapı hataları oluşturma")

Birden çok yapı hedefi olan bir klasörde, hangi CMake hedefini oluştureceğini belirtebilirsiniz: Hedefi belirtmek için **CMake** menüsünde Veya *CMakeLists.txt* bağlam menüsünde **Yapı** öğesini seçin. CMake projesine **Ctrl+Shift+B** girerseniz, geçerli etkin belgeyi oluşturur.

## <a name="debugging-cmake-projects"></a>Hata ayıklama CMake projeleri

CMake projesini hata ayıklamak için tercih edilen yapılandırmayı seçin ve **F5**tuşuna basın veya araç çubuğundaki **Çalıştır** düğmesine basın. **Çalıştır** düğmesinde "Başlangıç Öğesini Seç" yazıyorsa, açılır ok'u seçin. Çalıştırmak istediğiniz hedefi seçin. (CMake projesinde "Geçerli belge" seçeneği yalnızca .cpp dosyaları için geçerlidir.)

![CÇalıştır düğmesi yap](media/cmake-run-button.png "CÇalıştır düğmesi yap")

Önceki yapıdan bu yana değişiklikler **yapıldıysa, önce Çalıştır** veya **F5** komutları projeyi oluşturur. *CMakeSettings.json'da* yapılan değişiklikler CMake önbelleğinin yeniden oluşturulmasına neden olur.

**Launch.vs.json** dosyasındaki özellikleri ayarlayarak cmake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için [CMake hata ayıklama oturumlarını yapılandırın.](configure-cmake-debugging-sessions.md)

## <a name="just-my-code-for-cmake-projects"></a>CMake projeleri için Sadece Kodum

MSVC derleyicisini kullanarak Windows için oluşturduğunuzda, CMake projeleri Just My Code hata ayıklama desteğine sahiptir. Yalnızca Kodum ayarını değiştirmek **için,** > **Genel**Hata**Ayıklama** > Araçları**Seçenekleri'ne** > gidin.

## <a name="vcpkg-integration"></a>Vcpkg entegrasyonu

[VCPKG](vcpkg.md)yüklü varsa, Visual Studio'da açılan CMake projeleri vcpkg araç zinciri dosyasını otomatik olarak entegre edin. Bu, CMake projelerinizle vcpkg kullanmak için ek yapılandırma gerekolmadığı anlamına gelir. Bu destek, hedeflediğiniz uzak sistemlerdeki hem yerel vcpkg yüklemeleri hem de vcpkg yüklemeleri için çalışır. CMake Ayarları yapılandırmanızda başka bir araç zinciri belirttiğinizde bu davranış otomatik olarak devre dışı bırakılır.

## <a name="customize-configuration-feedback"></a>Yapılandırma geri bildirimini özelleştirme

Varsayılan olarak, bir hata olmadığı sürece yapılandırma iletilerinin çoğu bastırılır. **Araçlar** > **Seçenekleri** > **CMake**bu özelliği etkinleştirerek tüm iletileri görebilirsiniz.

   ![CMake tanı lama seçeneklerini yapılandırma](media/vs2019-cmake-configure-options.png "CTanılama seçeneklerini yapın")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme

*CMakeLists.txt* dosyasını düzeltmek için **Solution Explorer'daki** dosyaya sağ tıklayın ve **Aç'ı**seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görüntülenir ve IntelliSense'in güncelleştireceğini bildirir. Güncelleştirme işlemini iptal etme şansı verir. *CMakeLists.txt*hakkında bilgi için, [CMake belgelerine](https://cmake.org/documentation/)bakın.

   ![CMakeLists.txt dosya düzenleme](media/cmake-cmakelists.png "CMakeLists.txt dosya düzenleme")

Dosyayı kaydedin en kısa sürede yapılandırma adımı otomatik olarak yeniden çalışır ve **Çıktı** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **Hata Listesi** veya **Çıktı** penceresinde gösterilir. *CMakeLists.txt'deki*rahatsız edici satıra gitmek için **Hata Listesi'ndeki** bir hataya çift tıklayın.

   ![CMakeLists.txt dosya hataları](media/cmake-cmakelists-error.png "CMakeLists.txt dosya hataları")

## <a name="cmake-configure-step"></a>CYapı yapı adımı

*CMakeSettings.json* veya *CMakeLists.txt* dosyalarında önemli değişiklikler yaptığınızda, Visual Studio CMake yapılandırma adımını otomatik olarak yeniden çalıştırır. Yapılandırma adımı hatasız biterse, toplanan bilgiler C++ IntelliSense ve dil hizmetlerinde kullanılabilir. Yapı ve hata ayıklama işlemlerinde de kullanılır.

## <a name="troubleshooting-cmake-cache-errors"></a>Sorun giderme CMake önbellek hataları

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, aşağıdaki komutlardan birini çalıştırmak için **Çözüm Gezgini'nde** **Project** ana menüsünü veya *CMakeLists.txt* bağlam menüsünü açın:

- **Önbellek'i görüntüle,** düzenleyicideki yapı kökü klasöründen *CMakeCache.txt* dosyasını açar. *(CMakeCache.txt* için burada yaptığınız herhangi bir edeç, önbelleği temizlerseniz silinir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için Bkz. [CMake ayarlarını Özelleştir](customize-cmake-settings.md):))

- **Önbellek Klasörünü Aç,** yapı kökü klasörüne bir Explorer penceresi açar.

- **Temiz Önbellek,** yapı kök klasörünü siler, böylece bir sonraki CMake yapılandırma adımı temiz bir önbellekten başlar.

- Visual Studio ortamı güncel olarak kabul etse bile, **Önbellek** oluşturma adımının çalışmasına neden olur.

CMake > Genel iletişim **kutusunda, Araçlar > Seçenekleri > otomatik** önbellek oluşturma devre dışı >.

## <a name="run-cmake-from-the-command-line"></a>Komut satırından CMake çalıştırın

Visual Studio Installer'dan CMake yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Daha fazla bilgi için [bkz: Komut Satırındaki Bina.](building-on-the-command-line.md)

1. Çıktı klasörünüze geçin.

1. Uygulamanızı oluşturmak/yapılandırmak için CMake'i çalıştırın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017, [platformlar arası CMake projeleri](../linux/cmake-linux-project.md)de dahil olmak üzere CMake için zengin bir desteğe sahiptir. CMake bileşeni **için Visual C++ Araçları,** IDE'nin CMake proje dosyalarını *(CMakeLists.txt*gibi) doğrudan IntelliSense ve tarama amacıyla tüketmesini sağlamak için **Açık Klasör** özelliğini kullanır. Hem Ninja hem de Visual Studio jeneratörleri desteklenir. Visual Studio jeneratörü kullanıyorsanız, geçici bir proje dosyası oluşturur ve msbuild.exe'ye aktarılır. Ancak, proje IntelliSense veya tarama amacıyla yüklenmez. Ayrıca varolan bir CMake önbelleğini de içe aktarabilirsiniz.

## <a name="installation"></a>Yükleme

**CMake için Visual C++ Tools,** **C++** iş yüklerine sahip C++ ve Linux Geliştirme **ile Masaüstü geliştirmenin** bir parçası olarak yüklenir.

![C++ Masaüstü iş yükünde CMake bileşeni](media/cmake-install.png)

Daha fazla bilgi için [Bkz. Visual Studio'da C++ Linux iş yükünü yükleyin.](../linux/download-install-and-setup-the-linux-development-workload.md)

## <a name="ide-integration"></a>IDE entegrasyonu

*CMakeLists.txt* dosyasını içeren bir klasörü açmak için **Dosya > Aç > Klasörünü** seçtiğinizde, aşağıdaki şeyler olur:

- Visual Studio, CMake komutlarını görüntülemek ve düzenlemek için komutları içeren ana menüye bir **CMake** menü öğesi ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio CMake.exe çalışır ve isteğe bağlı olarak varsayılan *yapılandırma*için CMake önbelleği oluşturur , hangi x86 Hata Ayıklama. CMake komut **satırı,** CMake'in ek çıktısıyla birlikte Çıkış Penceresinde görüntülenir.

- Arka planda Visual Studio, IntelliSense'i etkinleştirmek için kaynak dosyalarını dizine eklemeye, bilgilere göz atma, yeniden düzenleme ve benzeri bilgileri eklemeye başlar. Siz çalışırken Visual Studio, dizinini kaynaklarla eşit tutmak için düzenleyicideki ve diskteki değişiklikleri izler.

İstediğiniz sayıda CMake projesi içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "root" *CMakeLists.txt* dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, oluşturma, hata ayıklama), C++ IntelliSense ve tarama çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok köklü CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, hedeflere göre mantıksal olarak düzenlenen projelerinizi de görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğundaki açılır görünümden **Hedefler görünümünü** seçin:

![CMake hedefleri görünüm düğmesi](media/cmake-targets-view.png)

Visual Studio cmake.exe için ortam değişkenlerini veya komut satırı seçeneklerini depolamak için *CMakeSettings.json* adlı bir dosya kullanır. *CMakeSettings.json* ayrıca birden çok CMake yapı yapılandırmasını tanımlamanızı ve depolamanızı sağlar. IDE'de aralarında rahatlıkla geçiş yapabilirsiniz.

Aksi takdirde, kaynak dosyaları belirtmek, kitaplıklar bulmak, derleyici ve bağlayıcı seçenekleri ayarlamak ve sistemle ilgili diğer bilgileri belirtmek için herhangi bir CMake projesinde olduğu gibi *CMakeLists.txt'yi* kullanın.

Bağımsız değişkenleri hata ayıklama zamanında yürütülebilir bir dosyaya geçirmeniz gerekiyorsa, **launch.vs.json**adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda Visual Studio bu dosyaları otomatik olarak oluşturur. Bunları el ile dinleyebilir, hatta dosyayı kendiniz oluşturabilirsiniz.

> [!NOTE]
> Açık Klasör projelerinin diğer türleri için iki ek JSON dosyası kullanılır: **CppProperties.json** ve **tasks.vs.json**. Bunların hiçbiri CMake projeleri için ilgili değildir.

## <a name="import-an-existing-cache"></a>Varolan bir önbelleği alma

Varolan bir *CMakeCache.txt* dosyayı içe aktardığınızda, Visual Studio otomatik olarak özelleştirilmiş değişkenleri ayıklar ve bunlara dayalı önceden doldurulmuş bir *CMakeSettings.json* dosyası oluşturur. Özgün önbellek hiçbir şekilde değiştirilmez. Yine de komut satırından veya oluşturmak için kullanılan her türlü araç veya IDE ile kullanılabilir. Yeni *CMakeSettings.json* dosyası projenin kök *CMakeLists.txt*yanında yerleştirilir. Visual Studio ayarlar dosyasına dayalı yeni bir önbellek oluşturur. CMake > Genel iletişim **kutusunda, Araçlar > Seçenekleri > Otomatik** önbellek oluşturmayı geçersiz kılabilirsiniz.

Önbellekteki her şey içe aktarılmaz.  Jeneratör ve derleyicilerin konumu gibi özellikler, IDE ile iyi çalıştığı bilinen varsayılanlarla değiştirilir.

### <a name="to-import-an-existing-cache"></a>Varolan bir önbelleği almak için

1. Ana menüden **Dosya > Açık > CMake'i**seçin:

   ![CMake'i Aç](media/cmake-file-open.png "Dosya, Aç, CMake")

   Bu **komut, Önbellek sihirbazından CMake Alma'yı** getirir.

2. Almak istediğiniz *CMakeCache.txt* dosyasına gidin ve ardından **Tamam'ı**tıklatın. **Önbellek sihirbazından CMake Projesi alma** görüntülenir:

   ![CMake önbelleği alma](media/cmake-import-wizard.png "CMake alma önbellek sihirbazı açma")

   Sihirbaz tamamlandığında, **Çözüm Gezgini'nde** yeni *CMakeCache.txt* dosyasını projenizdeki kök *CMakeLists.txt* dosyasının yanında görebilirsiniz.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

Bir CMake projesi oluşturmak için şu seçeneklere sahipsiniz:

1. Genel araç çubuğunda, **Configurations** açılır düşüşünü bulun. Muhtemelen varsayılan olarak "Linux-Debug" veya "x64-Debug" gösteriyor. Tercih edilen yapılandırmayı seçin ve **F5**tuşuna basın veya araç çubuğundaki **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje otomatik olarak ilk oluşturur, bir Visual Studio çözüm gibi.

1. *CMakeLists.txt'ye* sağ tıklayın ve bağlam menüsünden **Oluştur'u** seçin. Klasör yapınızda birden çok hedefiniz varsa, tümünü veya yalnızca belirli bir hedefi oluşturmayı seçebilirsiniz.

1. Ana menüden **Yapı > Çözüm** **(F7** veya **Ctrl+Shift+B)** seçeneğini belirleyin. **Genel** araç çubuğundaki **Başlangıç Öğesi** açılır düşüşünde bir CMake hedefinin zaten seçildiğinden emin olun.

![CMake build menü komutu](media/cmake-build-menu.png "CMake build komut menüsü")

*CMakeSettings.json* dosyasındaki yapı yapılandırmalarını, ortam değişkenlerini, komut satırı bağımsız değişkenlerini ve diğer ayarları özelleştirebilirsiniz. *CMakeLists.txt* dosyasını değiştirmeden değişiklik yapmanızı sağlar. Daha fazla bilgi için [CMake ayarlarını özelleştir'e](customize-cmake-settings.md)bakın.

Beklediğiniz gibi, yapı sonuçları **Çıktı Penceresi** ve **Hata Listesinde**gösterilir.

![CYapı hataları oluşturma](media/cmake-build-errors.png "CYapı hataları oluşturma")

Birden çok yapı hedefi olan bir klasörde, hangi CMake hedefini oluştureceğini belirtebilirsiniz: Hedefi belirtmek için **CMake** menüsünde Veya *CMakeLists.txt* bağlam menüsünde **Yapı** öğesini seçin. CMake projesine **Ctrl+Shift+B** girerseniz, geçerli etkin belgeyi oluşturur.

## <a name="debugging-cmake-projects"></a>Hata ayıklama CMake projeleri

CMake projesini hata ayıklamak için tercih edilen yapılandırmayı seçin ve **F5 tuşuna**basın. Veya araç çubuğundaki **Çalıştır** düğmesine basın. **Çalıştır** düğmesinde "Başlangıç Öğesini Seç" yazıyorsa, açılır ok'u seçin ve çalıştırmak istediğiniz hedefi seçin. (CMake projesinde "Geçerli belge" seçeneği yalnızca .cpp dosyaları için geçerlidir.)

![CÇalıştır düğmesi yap](media/cmake-run-button.png "CÇalıştır düğmesi yap")

Önceki yapıdan bu yana değişiklikler **yapıldıysa, önce Çalıştır** veya **F5** komutları projeyi oluşturur.

**Launch.vs.json** dosyasındaki özellikleri ayarlayarak cmake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için [CMake hata ayıklama oturumlarını yapılandırın.](configure-cmake-debugging-sessions.md)

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyalarını düzenleme

*CMakeLists.txt* dosyasını düzeltmek için **Solution Explorer'daki** dosyaya sağ tıklayın ve **Aç'ı**seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görüntülenir ve IntelliSense'in güncelleştireceğini bildirir. Güncelleştirme işlemini iptal etme şansı verir. *CMakeLists.txt*hakkında bilgi için, [CMake belgelerine](https://cmake.org/documentation/)bakın.

   ![CMakeLists.txt dosya düzenleme](media/cmake-cmakelists.png "CMakeLists.txt dosya düzenleme")

Dosyayı kaydedin en kısa sürede yapılandırma adımı otomatik olarak yeniden çalışır ve **Çıktı** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **Hata Listesi** veya **Çıktı** penceresinde gösterilir. *CMakeLists.txt'deki*rahatsız edici satıra gitmek için **Hata Listesi'ndeki** bir hataya çift tıklayın.

   ![CMakeLists.txt dosya hataları](media/cmake-cmakelists-error.png "CMakeLists.txt dosya hataları")

## <a name="cmake-configure-step"></a>CYapı yapı adımı

*CMakeSettings.json* veya *CMakeLists.txt* dosyalarında önemli değişiklikler yapıldığında, Visual Studio CMake yapılandırma adımını otomatik olarak yeniden çalıştırır. Yapılandırma adımı hatasız biterse, toplanan bilgiler C++ IntelliSense ve dil hizmetlerinde kullanılabilir. Yapı ve hata ayıklama işlemlerinde de kullanılır.

Birden çok CMake projesi aynı CMake yapılandırma adını kullanabilir (örneğin, x86-Hata Ayıklama). Bu yapılandırma seçildiğinde hepsi yapılandırılır ve (kendi yapı kökü klasöründe) oluşturulur. Bu CMake yapılandırmasında yer alan tüm CMake projelerinin hedeflerini ayıklayabilirsiniz.

   ![CMake Yalnızca Ekle menü öğesi](media/cmake-build-only.png "CMake Yalnızca Ekle menü öğesi")

Yapı ve hata ayıklama oturumlarını çalışma alanındaki projelerin bir alt kümesiyle sınırlandırabilirsiniz. *CMakeSettings.json* dosyasında benzersiz bir ada sahip yeni bir yapılandırma oluşturun. Ardından, yapılandırmayı yalnızca bu projelere uygulayın. Bu yapılandırma seçildiğinde, IntelliSense ve yapı ve hata ayıklama komutları yalnızca belirtilen projeler için geçerlidir.

## <a name="troubleshooting-cmake-cache-errors"></a>Sorun giderme CMake önbellek hataları

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, bu komutlardan birini çalıştırmak için **Solution Explorer'daki** **CMake** ana menüsünü veya *CMakeLists.txt* bağlam menüsünü açın:

- **Önbellek'i görüntüle,** düzenleyicideki yapı kökü klasöründen *CMakeCache.txt* dosyasını açar. *(CMakeCache.txt* için burada yaptığınız herhangi bir edeç, önbelleği temizlerseniz silinir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için Bkz. [CMake ayarlarını Özelleştir](customize-cmake-settings.md):))

- **Önbellek Klasörünü Aç,** yapı kökü klasörüne bir Explorer penceresi açar.

- **Temiz Önbellek,** yapı kök klasörünü siler, böylece bir sonraki CMake yapılandırma adımı temiz bir önbellekten başlar.

- Visual Studio ortamı güncel olarak kabul etse bile, **Önbellek** oluşturma adımının çalışmasına neden olur.

CMake > Genel iletişim **kutusunda, Araçlar > Seçenekleri > otomatik** önbellek oluşturma devre dışı >.

## <a name="single-file-compilation"></a>Tek dosya derlemesi

CMake projesinde tek bir dosya oluşturmak için Solution **Explorer'daki**dosyaya sağ tıklayın. Açılan menüden **Derle'yi** seçin. Ana **CMake** menüsünü kullanarak düzenleyicide şu anda açık olan dosyayı da oluşturabilirsiniz:

![CMake tek dosya derleme](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>Komut satırından CMake çalıştırın

Visual Studio Installer'dan CMake yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Daha fazla bilgi için [komut satırındaki Bina'ya](building-on-the-command-line.md) bakın.

1. Çıktı klasörünüze geçin.

1. Uygulamanızı oluşturmak/yapılandırmak için CMake'i çalıştırın.

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015'te Visual Studio kullanıcıları, IDE'nin IntelliSense, tarama ve derleme için tükettiği MSBuild proje dosyalarını oluşturmak için bir [CMake jeneratörü](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) kullanabilir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: Visual Studio'da C++ platform ötesi projeler oluşturun](get-started-linux-cmake.md)\
[Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanın](../linux/connect-to-your-remote-linux-computer.md)\
[CMake yapı ayarlarını özelleştirin](customize-cmake-settings.md)\
[CMakeSettings.json şema referans](cmakesettings-reference.md)\
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
[Linux projenizi dağıtma, çalıştırma ve hata ayıklama](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
