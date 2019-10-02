---
title: Visual Studio 'da CMake projeleri
ms.date: 10/01/2019
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 52ca34ef8522ada1881e2f7f5df212167c64c919
ms.sourcegitcommit: 4517932a67bbf2db16cfb122d3bef57a43696242
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/02/2019
ms.locfileid: "71816466"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio 'da CMake projeleri

CMake, birden çok platformda çalışan derleme işlemlerinin tanımlanması için platformlar arası, açık kaynaklı bir araçtır. Bu makalede CMake hakkında bilgi sahibi olduğunuz varsayılır. Geliştirme sırasında [, CMake Ile yazılımınızı test etme, test etme ve paketleme](https://cmake.org/)hakkında daha fazla bilgi edinebilirsiniz. 

> [!NOTE]
> CMake, son birkaç sürüm üzerinde Visual Studio ile daha fazla ve daha tümleştirilmiştir. Kullanmakta olduğunuz sürüm için doğru bilgileri görmek üzere, bu sayfanın sol üst kısmındaki sürüm seçicinin doğru ayarlandığından emin olun. 

::: moniker range="vs-2019"

**C++ Windows için CMake araçları** bileşeni, CMake proje dosyalarını (cmakelists. txt gibi) doğrudan IntelliSense ve gözatma amacıyla kullanmak için [klasörü aç](https://docs.microsoft.com/en-us/cpp/build/open-folder-projects-cpp?view=vs-2019) özelliğini kullanır. Hem Dokja hem de Visual Studio oluşturucuları desteklenir. Visual Studio Oluşturucusu kullanıyorsanız, geçici bir proje dosyası oluşturulup MSBuild. exe ' ye geçirilir, ancak IntelliSense veya gözatma amacıyla hiçbir şekilde yüklenmez. Ayrıca var olan bir CMake önbelleğini içeri aktarabilirsiniz.

## <a name="installation"></a>Yükleme

Windows için CMake araçları, iş yüküyle **Masaüstü geliştirmenin C++**  bir parçası olarak ve iş yükü  **C++ ile Linux geliştirmenin** bir parçası olarak varsayılan olarak yüklenir. **C++** Daha fazla bilgi için bkz. [platformlar arası CMake projeleri](../linux/cmake-linux-project.md) .

![C++ Masaüstü Iş yükünde CMake bileşeni](media/cmake-install-2019.png)

Daha fazla bilgi için bkz. [Visual C++ Studio 'da Linux iş yükünü yüklemeyi](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE tümleştirmesi

Bir CMakeLists. txt dosyası içeren bir klasörü açmak için **dosya > aç > klasörünü** seçtiğinizde, şunlar meydana gelir:

- Visual Studio, CMake komut dosyalarını görüntüleme ve düzenlemeyle ilgili komutlarla, **CMake** öğelerini **Proje** menüsüne ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio, CMake. exe ' yi çalıştırır ve x64 hata ayıklaması olan varsayılan *yapılandırma*Için CMake önbelleği oluşturur. CMake komut satırı, CMake 'in ek çıktılarıyla birlikte **Çıkış penceresi**görüntülenir.

- Arka planda, Visual Studio IntelliSense, gözatma bilgileri, yeniden düzenleme vb. etkinleştirmek için kaynak dosyaların dizinini oluşturup başlatır. Çalışmanız sırasında, Visual Studio düzenleyicideki değişiklikleri ve kaynakları kaynaklarla eşitlenmiş halde tutmak için diskte da izler.

İstediğiniz sayıda CMake projesini içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "kök" CMakeLists. txt dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama) ve C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok kökle CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, projelerinizi mantıksal olarak hedefe göre düzenlenmiş şekilde görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğunda açılan listeden **hedefler görünümünü** seçin:

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png)

Visual Studio, CMake. exe için ortam değişkenlerini veya komut satırı seçeneklerini depolamak üzere **Cmakesettings. JSON** adlı bir dosya kullanır. **Cmakesettings. JSON** Ayrıca birden çok CMake derleme yapılandırması tanımlamanıza ve depolamanıza olanak sağlar ve IDE 'de bunlarla kolayca geçiş yapmanızı sağlar. Visual Studio 2019 ' de **CMake ayarları Düzenleyicisi** , ayarlarınızı düzenlemek için kullanışlı bir yol sağlar. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md) .

Aksi takdirde, **Cmakelists. txt** dosyasını herhangi bir CMake projesinde kaynak dosyaları belirtme, kitaplık bulma, derleyici ve bağlayıcı seçeneklerini ayarlama ve diğer derleme sistemiyle ilgili bilgileri belirtme gibi kullanın.

Hata ayıklama sırasında bir yürütülebilir dosyaya bağımsız değişkenler geçirmeniz gerekiyorsa, **Başlat. vs. JSON**adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda, Visual Studio bu dosyaları otomatik olarak oluşturur; bunları el ile düzenleyebilirsiniz. Dosyayı kendiniz de oluşturabilirsiniz.

> [!NOTE]
> Diğer açık klasör projesi türleri için, iki ek JSON dosyası kullanılır: **Cppproperties. JSON** ve **Tasks. vs. JSON**. Bunlardan hiçbiri CMake projelerine uygun değildir.

## <a name="import-an-existing-cache"></a>Var olan bir önbelleği içeri aktar

Var olan bir CMakeCache. txt dosyasını içeri aktardığınızda, Visual Studio özelleştirilmiş değişkenleri otomatik olarak ayıklar ve bunlara göre önceden doldurulmuş bir **Cmakesettings. JSON** dosyası oluşturur. Özgün önbellek herhangi bir şekilde değiştirilmez ve komut satırından veya onu oluşturmak için kullanılan herhangi bir araçla ya da IDE ile kullanılmaya devam edilebilir. Yeni **Cmakesettings. JSON** dosyası projenin kök CMakeLists. txt dosyasının yanına yerleştirilir. Visual Studio, ayarlar dosyasını temel alarak yeni bir önbellek oluşturur. **Araçlar > seçenekleri > CMake > genel** iletişim kutusunda otomatik önbellek oluşturmayı geçersiz kılabilirsiniz.

Önbellekteki her şey içeri aktarılmaz. Oluşturucu ve derleyicilerin konumu gibi özellikler, IDE ile birlikte çalışmak üzere bilinen varsayılanlar ile değiştirilmiştir.

## <a name="open-an-existing-cache"></a>Var olan bir önbelleği aç

Var olan bir CMake önbelleğini açtığınızda, Visual Studio sizin için önbelleğinizi ve derleme ağacınızı yönetmeyi denemez. Bu, özel veya tercih ettiğiniz araçlarınızın projenizi nasıl yapılandırdığından emin olmanızı sağlar. Visual Studio 'da dosya aracılığıyla var olan bir önbelleği açabilirsiniz **> CMake > açın** ve var olan bir CMakeCache. txt dosyasına gidin. Alternatif olarak, projeyi Visual Studio 'da zaten açtıysanız, yeni bir yapılandırma ekleyeceğiniz şekilde var olan bir önbelleği buna ekleyebilirsiniz. Daha fazla bilgi için, [Visual Studio 'da var olan bir önbelleği açmak](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)için blog gönderimize bakın.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

CMake projesi oluşturmak için şu seçimlere sahipsiniz:

1. Genel araç çubuğunda, **Konfigürasyonlar** açılan listesini bulun. Büyük olasılıkla "x64-Debug" varsayılan olarak gösterilir. İstenen yapılandırmayı seçin ve **F5**tuşuna basın ya da araç çubuğunda **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje, yalnızca bir Visual Studio çözümü gibi otomatik olarak ilk olarak oluşturulur.

1. CMakeLists. txt dosyasına sağ tıklayın ve bağlam menüsünden **Oluştur** ' u seçin. Klasör yapınız içinde birden çok hedef varsa, tümünü veya yalnızca bir hedefi derlemeyi seçebilirsiniz.

1. Ana menüden **oluştur > tümünü oluştur** ' u seçin (**F7** veya **Ctrl + Shift + B**). **Genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde bir CMake hedefinin zaten seçili olduğundan emin olun.

![CMake oluştur menü komutu](media/cmake-build-menu.png "CMake oluştur komut menüsü")

**CMake ayarları düzenleyicisini**kullanarak CMakeLists. txt dosyasını değiştirmeden derleme yapılandırması, ortam değişkenleri, komut satırı bağımsız değişkenleri ve diğer ayarları özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).

Bekleneceğiniz gibi, yapı sonuçları **Çıkış penceresi** ve **hata listesi**gösterilir.

![CMake derleme hataları](media/cmake-build-errors.png "CMake derleme hataları")

Birden çok derleme hedefi olan bir klasörde, hangi CMake hedefini derlemek istediğinizi belirtmek için **CMake** menüsünde veya **cmakelists. txt** bağlam menüsündeki **Build** öğesini seçebilirsiniz. CMake projesinde **CTRL + SHIFT + B** tuşlarına basıldığında geçerli etkin belge oluşturulur.

## <a name="debugging-cmake-projects"></a>CMake projelerinde hata ayıklama

CMake projesinde hata ayıklamak için, istenen yapılandırmayı seçin ve **F5**tuşuna basın ya da araç çubuğunda **Çalıştır** düğmesine basın. **Çalıştır** düğmesi "başlangıç öğesi Seç" diyorsa, açılan oku seçin ve çalıştırmak istediğiniz hedefi seçin. (CMake projesinde, "geçerli belge" seçeneği yalnızca. cpp dosyaları için geçerlidir.)

![CMake Çalıştır düğmesi](media/cmake-run-button.png "CMake Çalıştır düğmesi")

Önceki derlemeden bu yana değişiklikler yapılmışsa, **Run** veya **F5** komutları ilk olarak projeyi oluşturur.

**Launch. vs. JSON** dosyasındaki özellikleri ayarlayarak CMake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md).

## <a name="just-my-code-for-cmake-projects"></a>CMake projeleri için Yalnızca kendi kodum

MSVC derleyicisini kullanarak Windows için derleme yaptığınızda CMake projeleriniz, Visual Studio 'da seçeneği etkinleştirilirse derleyicinin ve bağlayıcının yalnızca kendi kodumun hata ayıklamasını destekler. Ayarı değiştirmek için **araçlar** > **Seçenekler** > **hata ayıklama** > **genel**' e gidin.

## <a name="vcpkg-integration"></a>Vcpkg tümleştirmesi

[Vcpkg](vcpkg.md)yüklediyseniz, Visual Studio 'da açık olan CMake projeleri vcpkg araç zinciri dosyasını otomatik olarak tümleştirir. Bu, CMake projelerinizle vcpkg kullanmak için ek bir yapılandırma gerekmediği anlamına gelir. Bu destek, hedeflediğiniz uzak sistemlerde hem yerel vcpkg yüklemeleri hem de vcpkg yüklemeleri için geçerlidir. CMake ayarları yapılandırmanızda başka bir araç zinciri belirttiğinizde bu davranış otomatik olarak devre dışıdır.

## <a name="customize-configuration-feedback"></a>Yapılandırma geri bildirimini özelleştirme

Varsayılan olarak, çoğu yapılandırma iletisi bir hata olmadığı takdirde bastırılır. **Araçlar** > **seçenekleri** > **CMake**' de bu özelliği etkinleştirerek tüm iletileri görebilirsiniz.

   ![CMake tanılama seçeneklerini yapılandırma](media/vs2019-cmake-configure-options.png "CMake tanılama seçenekleri")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists. txt dosyalarını Düzenle

Bir CMakeLists. txt dosyasını düzenlemek için, **Çözüm Gezgini** dosya üzerinde sağ tıklayın ve **Aç**' ı seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görünür ve IntelliSense 'in güncelleşmekte olduğunu bildirir ve güncelleştirme işlemini iptal etmek için size bir fırsat sağlar. CMakeLists. txt hakkında daha fazla bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   Cmakelists. txt dosyasını ![düzenleyen Cmakelists. txt dosyasını Düzenle](media/cmake-cmakelists.png "")

Dosyayı kaydettikten hemen sonra yapılandırma adımı otomatik olarak çalışır ve **Çıkış** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **hata listesi** veya **Çıkış** penceresinde gösterilir. CMakeLists. txt dosyasındaki sorunlu satıra gitmek için **hata listesi** bir hataya çift tıklayın.

   ![Cmakelists. txt dosya hataları](media/cmake-cmakelists-error.png "cmakelists. txt dosya hataları")


## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

**Cmakesettings. JSON** veya CMakeLists. txt dosyalarında önemli değişiklikler yapıldığında, Visual Studio otomatik olarak CMake yapılandırma adımını yeniden çalıştırır. Yapılandırma adımı hatasız tamamlandığında, toplanan bilgiler C++ IntelliSense ve Language hizmetlerinde ve ayrıca derleme ve hata ayıklama işlemlerinde kullanılabilir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbelleği hatalarıyla ilgili sorunları giderme

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, bu komutlardan birini çalıştırmak için **Çözüm Gezgini** içindeki **Proje** ana menüsünü veya **cmakelists. txt** bağlam menüsünü açın:

- **Görüntüleme önbelleği** , düzenleyicideki derleme kökü klasöründen CMakeCache. txt dosyasını açar. (Burada, CMakeCache. txt ' de yaptığınız herhangi bir düzenleme, Önbelleği temizledikten sonra temizlenir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).)

- **Önbellek klasörünü aç** , derleme kök klasörü Için bir Gezgin penceresi açar.

- **Temiz önbellek** , sonraki CMake Yapılandır adımının temiz bir önbellekten başlaması için derleme kök klasörünü siler.

- **Önbellek oluşturma** , Visual Studio ortamı güncel kabul etse bile oluşturma adımını çalıştırmaya zorlar.

Otomatik önbellek oluşturma, **araçlar > seçeneklerinde > CMake > genel** iletişim kutusunda devre dışı bırakılabilir.

## <a name="run-cmake-from-the-command-line"></a>CMake 'i komut satırından Çalıştır

CMake 'i Visual Studio Yükleyicisi yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd. bat (x86/x64) öğesini çalıştırın. Daha fazla bilgi için bkz. [komut satırı üzerinde oluşturma](building-on-the-command-line.md) .

1. Çıkış klasörünüze geçin.

1. Uygulamanızı derlemek/yapılandırmak için CMake 'i çalıştırın.

::: moniker-end

::: moniker range="vs-2017"

Visual Studio 2017, [platformlar arası CMake projeleri](../linux/cmake-linux-project.md)de dahil olmak üzere CMake için zengin desteğe sahiptir. **CMake C++ bileşeni için görsel araçlar** , IDE 'nin CMake proje dosyalarını (cmakelists. txt gibi) doğrudan IntelliSense ve gözatma amaçlarıyla kullanmasını sağlamak için **klasörü aç** özelliğini kullanır. Hem Dokja hem de Visual Studio oluşturucuları desteklenir. Visual Studio Oluşturucusu kullanıyorsanız, geçici bir proje dosyası oluşturulup MSBuild. exe ' ye geçirilir, ancak IntelliSense veya gözatma amacıyla hiçbir şekilde yüklenmez. Ayrıca, var olan bir CMake önbelleğini içeri aktarabilirsiniz. 

## <a name="installation"></a>Yükleme

**CMake için görsel C++ araçlar** , iş yüküyle **Masaüstü geliştirmenin C++**  bir parçası olarak ve iş yükü **ile C++ Linux geliştirmenin** bir parçası olarak varsayılan olarak yüklenir.

![C++ Masaüstü Iş yükünde CMake bileşeni](media/cmake-install.png)

Daha fazla bilgi için bkz. [Visual C++ Studio 'da Linux iş yükünü yüklemeyi](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE tümleştirmesi

Bir CMakeLists. txt dosyası içeren bir klasörü açmak için **dosya > aç > klasörünü** seçtiğinizde, şunlar meydana gelir:

- Visual Studio, CMake komut dosyalarını görüntüleme ve düzenlemeyle ilgili komutlarla, ana menüye bir **CMake** menü öğesi ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio, CMake. exe ' yi çalıştırır ve isteğe bağlı olarak, x86 hata ayıklaması olan varsayılan *yapılandırma*Için CMake önbelleği oluşturur. CMake komut satırı, CMake 'in ek çıktılarıyla birlikte **Çıkış penceresi**görüntülenir.

- Arka planda, Visual Studio IntelliSense, gözatma bilgileri, yeniden düzenleme vb. etkinleştirmek için kaynak dosyaların dizinini oluşturup başlatır. Çalışmanız sırasında, Visual Studio düzenleyicideki değişiklikleri ve kaynakları kaynaklarla eşitlenmiş halde tutmak için diskte da izler.

İstediğiniz sayıda CMake projesini içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "kök" CMakeLists. txt dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama) ve C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok kökle CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, projelerinizi mantıksal olarak hedefe göre düzenlenmiş şekilde görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğunda açılan listeden **hedefler görünümünü** seçin:

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png)

Visual Studio, CMake. exe için ortam değişkenlerini veya komut satırı seçeneklerini depolamak üzere **Cmakesettings. JSON** adlı bir dosya kullanır. **Cmakesettings. JSON** Ayrıca birden çok CMake derleme yapılandırması tanımlamanıza ve depolamanıza olanak sağlar ve IDE 'de bunlarla kolayca geçiş yapmanızı sağlar. 

Aksi takdirde, **Cmakelists. txt** dosyasını herhangi bir CMake projesinde yaptığınız gibi, kaynak dosyaları belirtme, kitaplıklar bulma, derleyici ve bağlayıcı seçeneklerini ayarlama ve diğer derleme sistemiyle ilgili bilgileri belirtme gibi kullanın.

Hata ayıklama sırasında bir yürütülebilir dosyaya bağımsız değişkenler geçirmeniz gerekiyorsa, **Başlat. vs. JSON**adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda, Visual Studio bu dosyaları otomatik olarak oluşturur; bunları el ile düzenleyebilirsiniz. Dosyayı kendiniz de oluşturabilirsiniz.

> [!NOTE]
> Diğer açık klasör projesi türleri için, iki ek JSON dosyası kullanılır: **Cppproperties. JSON** ve **Tasks. vs. JSON**. Bunlardan hiçbiri CMake projelerine uygun değildir.

## <a name="import-an-existing-cache"></a>Var olan bir önbelleği içeri aktar

Var olan bir CMakeCache. txt dosyasını içeri aktardığınızda, Visual Studio özelleştirilmiş değişkenleri otomatik olarak ayıklar ve bunlara göre önceden doldurulmuş bir **Cmakesettings. JSON** dosyası oluşturur. Özgün önbellek herhangi bir şekilde değiştirilmez ve komut satırından veya onu oluşturmak için kullanılan herhangi bir araçla ya da IDE ile kullanılmaya devam edilebilir. Yeni **Cmakesettings. JSON** dosyası projenin kök CMakeLists. txt dosyasının yanına yerleştirilir. Visual Studio, ayarlar dosyasını temel alarak yeni bir önbellek oluşturur. **Araçlar > seçenekleri > CMake > genel** iletişim kutusunda otomatik önbellek oluşturmayı geçersiz kılabilirsiniz.

Önbellekteki her şey içeri aktarılmaz.  Oluşturucu ve derleyicilerin konumu gibi özellikler, IDE ile birlikte çalışmak üzere bilinen varsayılanlar ile değiştirilmiştir.

### <a name="to-import-an-existing-cache"></a>Var olan bir önbelleği içeri aktarmak için

1. Ana menüden **dosya > > CMake aç**' ı seçin:

   ![CMake dosyasını açın](media/cmake-file-open.png ", açık, CMake")

   Bu, **önbellekten CMake Içeri aktarma** Sihirbazı 'nı getirir.

2. İçeri aktarmak istediğiniz CMakeCache. txt dosyasına gidin ve ardından **Tamam**' a tıklayın. **Önbellekten CMake projesini Içeri aktarma** Sihirbazı görünür:

   ![CMake önbelleğini Içeri aktarma](media/cmake-import-wizard.png "CMake alma önbelleği açma Sihirbazı")

   Sihirbaz tamamlandığında, projenizdeki kök CMakeLists. txt dosyasının yanındaki **Çözüm Gezgini** yeni CMakeCache. txt dosyasını görebilirsiniz.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

CMake projesi oluşturmak için şu seçimlere sahipsiniz:

1. Genel araç çubuğunda, **Konfigürasyonlar** açılan listesini bulun; büyük olasılıkla "Linux-Debug" veya "x64-Debug" varsayılan olarak gösteriliyor. İstenen yapılandırmayı seçin ve **F5**tuşuna basın ya da araç çubuğunda **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje, yalnızca bir Visual Studio çözümü gibi otomatik olarak ilk olarak oluşturulur.

1. CMakeLists. txt dosyasına sağ tıklayın ve bağlam menüsünden **Oluştur** ' u seçin. Klasör yapınız içinde birden çok hedef varsa, tümünü veya yalnızca bir hedefi derlemeyi seçebilirsiniz.

1. Ana menüden **derleme > Build Solution** (**F7** veya **Ctrl + Shift + B**) öğesini seçin. **Genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde bir CMake hedefinin zaten seçili olduğundan emin olun.

![CMake oluştur menü komutu](media/cmake-build-menu.png "CMake oluştur komut menüsü")

**Cmakesettings. JSON** dosyasını kullanarak CMakeLists. txt dosyasını değiştirmeden derleme yapılandırması, ortam değişkenleri, komut satırı bağımsız değişkenleri ve diğer ayarları özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).

Bekleneceğiniz gibi, yapı sonuçları **Çıkış penceresi** ve **hata listesi**gösterilir.

![CMake derleme hataları](media/cmake-build-errors.png "CMake derleme hataları")

Birden çok derleme hedefi olan bir klasörde, hangi CMake hedefini derlemek istediğinizi belirtmek için **CMake** menüsünde veya **cmakelists. txt** bağlam menüsündeki **Build** öğesini seçebilirsiniz. CMake projesinde **CTRL + SHIFT + B** tuşlarına basıldığında geçerli etkin belge oluşturulur.

## <a name="debugging-cmake-projects"></a>CMake projelerinde hata ayıklama

CMake projesinde hata ayıklamak için, istenen yapılandırmayı seçin ve **F5**tuşuna basın ya da araç çubuğunda **Çalıştır** düğmesine basın. **Çalıştır** düğmesi "başlangıç öğesi Seç" diyorsa, açılan oku seçin ve çalıştırmak istediğiniz hedefi seçin. (CMake projesinde, "geçerli belge" seçeneği yalnızca. cpp dosyaları için geçerlidir.)

![CMake Çalıştır düğmesi](media/cmake-run-button.png "CMake Çalıştır düğmesi")

Önceki derlemeden bu yana değişiklikler yapılmışsa, **Run** veya **F5** komutları ilk olarak projeyi oluşturur.

**Launch. vs. JSON** dosyasındaki özellikleri ayarlayarak CMake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md).


## <a name="editing-cmakeliststxt-files"></a>CMakeLists. txt dosyalarını Düzenle

Bir CMakeLists. txt dosyasını düzenlemek için, **Çözüm Gezgini** dosya üzerinde sağ tıklayın ve **Aç**' ı seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görünür ve IntelliSense 'in güncelleşmekte olduğunu bildirir ve güncelleştirme işlemini iptal etmek için size bir fırsat sağlar. CMakeLists. txt hakkında daha fazla bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   Cmakelists. txt dosyasını ![düzenleyen Cmakelists. txt dosyasını Düzenle](media/cmake-cmakelists.png "")

Dosyayı kaydettikten hemen sonra yapılandırma adımı otomatik olarak çalışır ve **Çıkış** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **hata listesi** veya **Çıkış** penceresinde gösterilir. CMakeLists. txt dosyasındaki sorunlu satıra gitmek için **hata listesi** bir hataya çift tıklayın.

   ![Cmakelists. txt dosya hataları](media/cmake-cmakelists-error.png "cmakelists. txt dosya hataları")


## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

**Cmakesettings. JSON** veya CMakeLists. txt dosyalarında önemli değişiklikler yapıldığında, Visual Studio otomatik olarak CMake yapılandırma adımını yeniden çalıştırır. Yapılandırma adımı hatasız tamamlandığında, toplanan bilgiler C++ IntelliSense ve Language hizmetlerinde ve ayrıca derleme ve hata ayıklama işlemlerinde kullanılabilir.

Birden çok CMake projesi aynı CMake yapılandırma adını (örneğin, x86-hata ayıklama) kullandıklarında, bu yapılandırma seçildiğinde bunların hepsi yapılandırılır ve oluşturulur (kendi yapı kök klasöründe). Bu CMake yapılandırmasına katılan tüm CMake projelerinin hedeflerinde hata ayıklaması yapabilirsiniz.

   ![CMake yalnızca yapı Oluştur menü öğesi](media/cmake-build-only.png "CMake yalnızca yapı Oluştur menü öğesi")

Derlemeleri ve hata ayıklama oturumlarını çalışma alanındaki projelerin bir alt kümesiyle sınırlamak için, **Cmakesettings. JSON** dosyasında benzersiz bir adla yeni bir yapılandırma oluşturun ve bunu yalnızca bu projelere uygulayın. Bu yapılandırma seçildiğinde, IntelliSense ve Build ve Debug komutları yalnızca belirtilen projeler için etkinleştirilir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbelleği hatalarıyla ilgili sorunları giderme

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, aşağıdaki komutlardan birini çalıştırmak için **CMake** ana menüsünü veya **Çözüm Gezgini** içindeki **cmakelists. txt** bağlam menüsünü açın:

- **Görüntüleme önbelleği** , düzenleyicideki derleme kökü klasöründen CMakeCache. txt dosyasını açar. (Burada, CMakeCache. txt ' de yaptığınız herhangi bir düzenleme, Önbelleği temizledikten sonra temizlenir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).)

- **Önbellek klasörünü aç** , derleme kök klasörü Için bir Gezgin penceresi açar.

- **Temiz önbellek** , sonraki CMake Yapılandır adımının temiz bir önbellekten başlaması için derleme kök klasörünü siler.

- **Önbellek oluşturma** , Visual Studio ortamı güncel kabul etse bile oluşturma adımını çalıştırmaya zorlar.

Otomatik önbellek oluşturma, **araçlar > seçeneklerinde > CMake > genel** iletişim kutusunda devre dışı bırakılabilir.

## <a name="single-file-compilation"></a>Tek dosya derleme

CMake projesinde tek bir dosya oluşturmak için, **Çözüm Gezgini** dosya üzerinde sağ tıklayın ve **Derle**' yi seçin. Ayrıca, ana CMake menüsünü kullanarak düzenleyicide açık olan dosyayı da oluşturabilirsiniz:

![CMake tek dosya derlemesi](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>CMake 'i komut satırından Çalıştır

CMake 'i Visual Studio Yükleyicisi yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd. bat (x86/x64) öğesini çalıştırın. Daha fazla bilgi için bkz. [komut satırı üzerinde oluşturma](building-on-the-command-line.md) .

1. Çıkış klasörünüze geçin.

1. Uygulamanızı derlemek/yapılandırmak için CMake 'i çalıştırın.

::: moniker-end

::: moniker range="vs-2015"

Visual Studio 2015 ' de, Visual Studio kullanıcıları bir [CMake Oluşturucu](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) kullanarak, IDE 'nin IntelliSense, gözatma ve derleme Için kullandığı MSBuild proje dosyaları oluşturabilir.

::: moniker-end


## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: Visual C++ Studio 'da platformlar arası projeler oluşturma](get-started-linux-cmake.md)<br/>
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)<br/>
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)<br/>
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)<br/>
[CMakeSettings. JSON başvurusu](cmakesettings-reference.md)<br/>
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)<br/>
[Linux projenizi dağıtın, çalıştırın ve hatalarını ayıklayın](../linux/deploy-run-and-debug-your-linux-project.md)<br/>
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)<br/>
