---
title: Visual Studio 'da CMake projeleri
description: Visual Studio 'da CMake kullanarak C++ projeleri oluşturma ve derleme.
ms.date: 01/08/2020
helpviewer_keywords:
- CMake in Visual C++
ms.assetid: 444d50df-215e-4d31-933a-b41841f186f8
ms.openlocfilehash: 693179c6da368fa84a5ccb0ffaf2b1b1596972b8
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922335"
---
# <a name="cmake-projects-in-visual-studio"></a>Visual Studio 'da CMake projeleri

CMake, birden çok platformda çalışan derleme işlemlerinin tanımlanması için platformlar arası, açık kaynaklı bir araçtır. Bu makalede CMake hakkında bilgi sahibi olduğunuz varsayılır. Geliştirme sırasında [, CMake Ile yazılımınızı test etme, test etme ve paketleme](https://cmake.org/)hakkında daha fazla bilgi edinebilirsiniz.

> [!NOTE]
> CMake, son birkaç sürüm üzerinde Visual Studio ile daha fazla ve daha tümleştirilmiştir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="msvc-160"

**Windows için C++ CMake araçları** bileşeni, IntelliSense ve gözatma amaçları doğrultusunda CMake proje dosyalarını ( *CMakeLists.txt* gibi) doğrudan kullanmak için [klasörü aç](open-folder-projects-cpp.md) özelliğini kullanır. Hem Dokja hem de Visual Studio oluşturucuları desteklenir. Visual Studio Oluşturucusu kullanıyorsanız, geçici bir proje dosyası oluşturur ve bunu msbuild.exe geçirir. Ancak proje, IntelliSense veya gözatma amacıyla hiçbir şekilde yüklenmez. Ayrıca var olan bir CMake önbelleğini içeri aktarabilirsiniz.

## <a name="installation"></a>Yükleme

C++ **CMake araçları** , c++ iş yükleri ile C++ ve **Linux geliştirme** **ile masaüstü geliştirme** 'nin bir parçası olarak yüklenir. Daha fazla bilgi için bkz. [platformlar arası CMake projeleri](../linux/cmake-linux-project.md).

![C Plus Plus açılır listesi seçiliyken masaüstü geliştirme ve c Plus Plus C, Windows için Araçlar seçeneği olarak adlandırılan ekran görüntüsü.](media/cmake-install-2019.png)

Daha fazla bilgi için bkz. [Visual Studio 'Da C++ Linux iş yükünü yüklemeyi](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE tümleştirmesi

**Dosya > > klasörünü** seçtiğinizde bir *CMakeLists.txt* dosyası içeren bir klasörü açmak için aşağıdaki işlemler gerçekleşir:

- Visual Studio, CMake komut dosyalarını görüntüleme ve düzenlemeyle ilgili komutlarla, **CMake** öğelerini **Proje** menüsüne ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio cmake.exe çalıştırır ve varsayılan (x64 hata ayıklama) yapılandırması için CMake önbellek dosyası ( *CMakeCache.txt* ) oluşturur. CMake komut satırı, CMake 'in ek çıktılarıyla birlikte **Çıkış penceresi** görüntülenir.

- Arka planda, Visual Studio IntelliSense, gözatma bilgileri, yeniden düzenleme vb. etkinleştirmek için kaynak dosyaların dizinini oluşturup başlatır. Çalışmanız sırasında, Visual Studio düzenleyicideki değişiklikleri ve kaynakları kaynaklarla eşitlenmiş halde tutmak için diskte da izler.

İstediğiniz sayıda CMake projesini içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "root" *CMakeLists.txt* dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama), C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok kökle CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, projelerinizi mantıksal olarak hedefe göre düzenlenmiş şekilde görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğunda açılan listeden **hedefler görünümünü** seçin:

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png)

*Out/Build/ \<config>* klasörlerdeki tüm CMake tarafından oluşturulan çıktıyı görmek Için **Çözüm Gezgini** üstündeki **tüm dosyaları göster** düğmesine tıklayın.

Visual Studio, **üzerindeCMakeSettings.js** adlı bir yapılandırma dosyası kullanır. Bu dosya, birden çok derleme yapılandırması tanımlamanıza ve depolamanıza olanak tanır ve IDE 'de bunlarla kolayca geçiş yapmanızı sağlar. *Yapılandırma* , belirli bir yapı türüne özgü ayarları kapsülleyen bir Visual Studio yapısıdır. Ayarlar, Visual Studio 'Nun cmake.exe 'e geçirdiği varsayılan komut satırı seçeneklerini yapılandırmak için kullanılır. Ayrıca, burada ek CMake seçenekleri belirtebilir ve istediğiniz ek değişkenleri tanımlayabilirsiniz. Tüm seçenekler, CMake önbelleğine iç veya dış değişkenler olarak yazılır. Visual Studio 2019 ' de **CMake ayarları Düzenleyicisi** , ayarlarınızı düzenlemek için kullanışlı bir yol sağlar. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).

Tek bir ayar `intelliSenseMode` CMake 'e geçirilmez, ancak yalnızca Visual Studio tarafından kullanılır.

Her proje klasöründeki **CMakeLists.txt** dosyasını, tıpkı herhangi bir CMake projesinde olduğu gibi kullanın. Kaynak dosyaları belirtebilir, kitaplıkları bulabilir, derleyici ve bağlayıcı seçeneklerini ayarlayabilir ve diğer derleme sistemiyle ilgili bilgileri belirtebilirsiniz.

Bağımsız değişkenleri hata ayıklama zamanında bir yürütülebilir dosyaya geçirmek için, **üzerindelaunch.vs.js** adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda, Visual Studio otomatik olarak bu dosyaları oluşturur. Bunları el ile düzenleyebilir, hatta dosyayı kendiniz oluşturabilirsiniz.

> [!NOTE]
> Diğer açık klasör projesi türleri için, iki ek JSON dosyası kullanılır: **üzerindeCppProperties.js** ve **tasks.vs.js** . Bunlardan hiçbiri CMake projelerine uygun değildir.

## <a name="open-an-existing-cache"></a>Var olan bir önbelleği aç

Var olan bir CMake önbellek dosyasını ( *CMakeCache.txt* ) açtığınızda, Visual Studio sizin için önbelleğinizi ve derleme ağacınızı yönetmeyi denemez. Özel veya tercih ettiğiniz araçlarınız, CMake 'in projenizi nasıl yapılandırdığından emin olun. Visual Studio 'da var olan bir önbelleği açmak için **dosya > > CMake aç** ' ı seçin. Ardından, var olan bir *CMakeCache.txt* dosyasına gidin.

Mevcut bir CMake önbelleğini açık bir projeye ekleyebilirsiniz. Yeni bir yapılandırma ekleyeceğiniz şekilde yapılır. Daha fazla bilgi için, [Visual Studio 'da var olan bir önbelleği açmak](https://devblogs.microsoft.com/cppblog/open-existing-cmake-caches-in-visual-studio/)için blog gönderimize bakın.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

CMake projesi oluşturmak için şu seçimlere sahipsiniz:

1. Genel araç çubuğunda, **Konfigürasyonlar** açılan listesini bulun. Büyük olasılıkla "x64-Debug" varsayılan olarak gösterilir. Tercih edilen yapılandırmayı seçin ve **F5** tuşuna basın ya da araç çubuğunda **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje, yalnızca bir Visual Studio çözümü gibi otomatik olarak ilk olarak oluşturulur.

1. *CMakeLists.txt* sağ tıklayın ve bağlam menüsünden **Oluştur** ' u seçin. Klasör yapınız içinde birden çok hedef varsa, tümünü veya yalnızca bir hedefi derlemeyi seçebilirsiniz.

1. Ana menüden **oluştur > tümünü oluştur** ' u seçin ( **F7** veya **Ctrl + Shift + B** ). **Genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde bir CMake hedefinin zaten seçili olduğundan emin olun.

![CMake oluştur menü komutu](media/cmake-build-menu.png "CMake derlemesi komut menüsü")

Bekleneceğiniz gibi, yapı sonuçları **Çıkış penceresi** ve **hata listesi** gösterilir.

![CMake derleme hataları](media/cmake-build-errors.png "CMake derleme hataları")

Birden çok derleme hedefi olan bir klasörde, hangi CMake hedefinin derlenmeyeceğini belirtebilirsiniz: **CMake** menüsünde **derleme** öğesini seçin veya hedefi belirtmek Için *CMakeLists.txt* bağlam menüsünü seçin. CMake projesinde **CTRL + SHIFT + B** tuşlarına girerseniz, geçerli etkin belgeyi oluşturur.

## <a name="debugging-cmake-projects"></a>CMake projelerinde hata ayıklama

CMake projesinde hata ayıklamak için tercih edilen yapılandırmayı seçin ve **F5** tuşuna basın ya da araç çubuğunda **Çalıştır** düğmesine basın. **Çalıştır** düğmesi "başlangıç öğesi Seç" diyorsa, açılan oku seçin. Çalıştırmak istediğiniz hedefi seçin. (CMake projesinde, "geçerli belge" seçeneği yalnızca. cpp dosyaları için geçerlidir.)

![CMake Çalıştır düğmesi](media/cmake-run-button.png "CMake Çalıştır düğmesi")

Önceki derlemeden bu yana değişiklikler yapılmışsa, **Run** veya **F5** komutları ilk olarak projeyi oluşturur. *CMakeSettings.js* yapılan değişiklikler CMake önbelleğinin yeniden oluşturulmasına neden olur.

Dosyadaki **launch.vs.js** özelliklerini ayarlayarak CMake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md).

## <a name="just-my-code-for-cmake-projects"></a>CMake projeleri için Yalnızca kendi kodum

MSVC derleyicisini kullanarak Windows için derleme yaparken CMake projelerinde Yalnızca kendi kodum hata ayıklama desteği vardır. Yalnızca kendi kodum ayarını değiştirmek için, **Araçlar**  >  **Seçenekler**  >  **hata ayıklama**  >  **genel** ' e gidin.

## <a name="vcpkg-integration"></a>Vcpkg tümleştirmesi

[Vcpkg](vcpkg.md)yüklediyseniz, Visual Studio 'da açık olan CMake projeleri vcpkg araç zinciri dosyasını otomatik olarak tümleştirin. Diğer bir deyişle, CMake projelerinizle vcpkg kullanmak için ek bir yapılandırma gerekmez. Bu destek, hedeflediğiniz uzak sistemlerde hem yerel vcpkg yüklemeleri hem de vcpkg yüklemeleri için geçerlidir. CMake ayarları yapılandırmanızda başka bir araç zinciri belirttiğinizde bu davranış otomatik olarak devre dışıdır.

## <a name="customize-configuration-feedback"></a>Yapılandırma geri bildirimini özelleştirme

Varsayılan olarak, çoğu yapılandırma iletisi bir hata olmadığı takdirde bastırılır. **Araçlar**  >  **Seçenekler**  >  **CMake** ' de bu özelliği etkinleştirerek tüm iletileri görebilirsiniz.

   ![CMake tanılama seçeneklerini yapılandırma](media/vs2019-cmake-configure-options.png "CMake tanılama seçenekleri")

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyaları düzenleniyor

Bir *CMakeLists.txt* dosyayı düzenlemek için, **Çözüm Gezgini** dosyasında dosyaya sağ tıklayın ve **Aç** ' ı seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görünür ve IntelliSense 'in güncelleşmekte olduğunu bildirir. Güncelleştirme işlemini iptal etmek için size bir şans sağlar. *CMakeLists.txt* hakkında bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   ![CMakeLists.txt dosya düzenlemesi](media/cmake-cmakelists.png "CMakeLists.txt dosya düzenlemesi")

Dosyayı kaydettikten hemen sonra yapılandırma adımı otomatik olarak çalışır ve **Çıkış** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **hata listesi** veya **Çıkış** penceresinde gösterilir. *CMakeLists.txt* sorunlu satıra gitmek için **hata listesi** bir hataya çift tıklayın.

   ![CMakeLists.txt dosyası hataları](media/cmake-cmakelists-error.png "CMakeLists.txt dosyası hataları")

## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

*CMakeLists.txt* dosya *üzerindeCMakeSettings.js* önemli değişiklikler yaptığınızda, Visual Studio otomatik olarak CMake yapılandırma adımını yeniden çalıştırır. Yapılandırma adımı hatasız tamamlandığında, toplanan bilgiler C++ IntelliSense ve dil Hizmetleri ' nde kullanılabilir. Derleme ve hata ayıklama işlemlerinde de kullanılır.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbelleği hatalarıyla ilgili sorunları giderme

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, aşağıdaki komutlardan birini çalıştırmak için **Proje** ana menüsünü veya Çözüm Gezgini *CMakeLists.txt* bağlam menüsünü açın **Solution Explorer** :

- **Görüntüleme önbelleği** , düzenleyicide yapı kök klasöründen *CMakeCache.txt* dosyasını açar. ( *CMakeCache.txt* burada yaptığınız herhangi bir düzenleme, önbelleği temizleyene kadar temizlenir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).)

- **Önbellek klasörünü aç** , derleme kök klasörü Için bir Gezgin penceresi açar.

- **Temiz önbellek** , sonraki CMake Yapılandır adımının temiz bir önbellekten başlaması için derleme kök klasörünü siler.

- **Önbellek oluşturma** , Visual Studio ortamı güncel kabul etse bile oluşturma adımını çalıştırmaya zorlar.

Otomatik önbellek oluşturma, **araçlar > seçeneklerinde > CMake > Genel** iletişim kutusunda devre dışı bırakılabilir.

## <a name="run-cmake-from-the-command-line"></a>CMake 'i komut satırından Çalıştır

CMake 'i Visual Studio Yükleyicisi yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Daha fazla bilgi için, bkz. [komut satırı üzerinde oluşturma](building-on-the-command-line.md).

1. Çıkış klasörünüze geçin.

1. Uygulamanızı derlemek/yapılandırmak için CMake 'i çalıştırın.

::: moniker-end

::: moniker range="msvc-150"

Visual Studio 2017, [platformlar arası CMake projeleri](../linux/cmake-linux-project.md)de dahil olmak üzere CMake için zengin desteğe sahiptir. **CMake bileşeni için Visual C++ araçları** , IDE 'Nin CMake proje dosyalarını ( *CMakeLists.txt* gibi) doğrudan IntelliSense ve göz atma amaçlarıyla kullanmasını sağlamak için **klasörü aç** özelliğini kullanır. Hem Dokja hem de Visual Studio oluşturucuları desteklenir. Visual Studio Oluşturucusu kullanıyorsanız, geçici bir proje dosyası oluşturur ve bunu msbuild.exe geçirir. Ancak proje, IntelliSense veya gözatma amacıyla hiçbir şekilde yüklenmez. Ayrıca, var olan bir CMake önbelleğini içeri aktarabilirsiniz.

## <a name="installation"></a>Yükleme

C++ iş yükleri ile C++ ve **Linux geliştirme** **ile masaüstü geliştirme** kapsamında, **CMake için Visual C++ araçları** yüklenir.

![Visual C Plus ve C Make için Araçlar seçeneği olarak adlandırılan tek tek bileşenler sekmesinin ekran görüntüsü.](media/cmake-install.png)

Daha fazla bilgi için bkz. [Visual Studio 'Da C++ Linux iş yükünü yüklemeyi](../linux/download-install-and-setup-the-linux-development-workload.md).

## <a name="ide-integration"></a>IDE tümleştirmesi

**Dosya > > klasörünü** seçtiğinizde bir *CMakeLists.txt* dosyası içeren bir klasörü açmak için aşağıdaki işlemler gerçekleşir:

- Visual Studio, CMake komut dosyalarını görüntüleme ve düzenlemeyle ilgili komutlarla, ana menüye bir **CMake** menü öğesi ekler.

- **Çözüm Gezgini** klasör yapısını ve dosyalarını görüntüler.

- Visual Studio CMake.exe çalışır ve isteğe bağlı olarak, x86 hata ayıklaması olan varsayılan *yapılandırma* Için CMake önbelleği oluşturur. CMake komut satırı, CMake 'in ek çıktılarıyla birlikte **Çıkış penceresi** görüntülenir.

- Arka planda, Visual Studio IntelliSense, gözatma bilgileri, yeniden düzenleme vb. etkinleştirmek için kaynak dosyaların dizinini oluşturup başlatır. Çalışmanız sırasında, Visual Studio düzenleyicideki değişiklikleri ve kaynakları kaynaklarla eşitlenmiş halde tutmak için diskte da izler.

İstediğiniz sayıda CMake projesini içeren klasörleri açabilirsiniz. Visual Studio, çalışma alanınızdaki tüm "root" *CMakeLists.txt* dosyalarını algılar ve yapılandırır. CMake işlemleri (yapılandırma, derleme, hata ayıklama), C++ IntelliSense ve gözatma, çalışma alanınızdaki tüm CMake projeleri için kullanılabilir.

![Birden çok kökle CMake projesi](media/cmake-multiple-roots.png)

Ayrıca, projelerinizi mantıksal olarak hedefe göre düzenlenmiş şekilde görüntüleyebilirsiniz. **Çözüm Gezgini** araç çubuğunda açılan listeden **hedefler görünümünü** seçin:

![CMake hedefleri görünümü düğmesi](media/cmake-targets-view.png)

Visual Studio Cmake.exe için ortam değişkenlerini veya komut satırı seçeneklerini depolamak üzere *CMakeSettings.js* adlı bir dosya kullanır. *CMakeSettings.js* Ayrıca, birden çok CMake derleme yapılandırması tanımlamanıza ve depolamanıza olanak sağlar. IDE 'de bunlarla kolayca geçiş yapabilirsiniz.

Aksi takdirde, kaynak dosyaları belirtmek, kitaplıkları bulmak, derleyici ve bağlayıcı seçeneklerini ayarlamak ve diğer derleme sistemiyle ilgili bilgileri belirtmek için herhangi bir CMake projesinde olduğu gibi *CMakeLists.txt* kullanın.

Hata ayıklama zamanında bir yürütülebilir dosyaya bağımsız değişkenler geçirmeniz gerekiyorsa, **üzerindelaunch.vs.js** adlı başka bir dosya kullanabilirsiniz. Bazı senaryolarda, Visual Studio otomatik olarak bu dosyaları oluşturur. Bunları el ile düzenleyebilir, hatta dosyayı kendiniz oluşturabilirsiniz.

> [!NOTE]
> Diğer açık klasör projesi türleri için, iki ek JSON dosyası kullanılır: **üzerindeCppProperties.js** ve **tasks.vs.js** . Bunlardan hiçbiri CMake projelerine uygun değildir.

## <a name="import-an-existing-cache"></a>Var olan bir önbelleği içeri aktar

Mevcut bir *CMakeCache.txt* dosyasını içeri aktardığınızda, Visual Studio özelleştirilmiş değişkenleri otomatik olarak ayıklar ve bunlara göre dosya üzerinde önceden doldurulmuş bir *CMakeSettings.js* oluşturur. Özgün önbellek herhangi bir şekilde değiştirilmez. Bu, komut satırından veya onu oluşturmak için kullanılan herhangi bir araçla veya IDE ile kullanılabilir. Dosyadaki yeni  *CMakeSettings.js* , projenin kök *CMakeLists.txt* yanına yerleştirilir. Visual Studio, ayarlar dosyasını temel alarak yeni bir önbellek oluşturur. **Araçlar > seçenekleri > CMake > Genel** iletişim kutusunda otomatik önbellek oluşturmayı geçersiz kılabilirsiniz.

Önbellekteki her şey içeri aktarılmaz.  Oluşturucu ve derleyicilerin konumu gibi özellikler, IDE ile birlikte çalışmak üzere bilinen varsayılanlar ile değiştirilmiştir.

### <a name="to-import-an-existing-cache"></a>Var olan bir önbelleği içeri aktarmak için

1. Ana menüden **dosya > > CMake aç** ' ı seçin:

   ![CMake 'i aç](media/cmake-file-open.png "Dosya, açık, CMake")

   Bu komut, **önbellekten CMake Içeri aktarma** Sihirbazı 'nı getirir.

2. İçeri aktarmak istediğiniz *CMakeCache.txt* dosyasına gidin ve ardından **Tamam** ' a tıklayın. **Önbellekten CMake projesini Içeri aktarma** Sihirbazı görünür:

   ![CMake önbelleğini içeri aktarma](media/cmake-import-wizard.png "CMake içeri aktarma önbelleği Sihirbazı 'nı açın")

   Sihirbaz tamamlandığında, yeni *CMakeCache.txt* dosyasını projenizdeki kök *CMakeLists.txt* dosyasının yanına **Çözüm Gezgini** görebilirsiniz.

## <a name="building-cmake-projects"></a>CMake projeleri oluşturma

CMake projesi oluşturmak için şu seçimlere sahipsiniz:

1. Genel araç çubuğunda, **Konfigürasyonlar** açılan listesini bulun. Büyük olasılıkla "Linux-Debug" veya "x64-Debug" varsayılan olarak gösteriliyor. Tercih edilen yapılandırmayı seçin ve **F5** tuşuna basın ya da araç çubuğunda **Çalıştır** (yeşil üçgen) düğmesine tıklayın. Proje, yalnızca bir Visual Studio çözümü gibi otomatik olarak ilk olarak oluşturulur.

1. *CMakeLists.txt* sağ tıklayın ve bağlam menüsünden **Oluştur** ' u seçin. Klasör yapınız içinde birden çok hedef varsa, tümünü veya yalnızca bir hedefi derlemeyi seçebilirsiniz.

1. Ana menüden **derleme > Build Solution** ( **F7** veya **Ctrl + Shift + B** ) öğesini seçin. **Genel** araç çubuğundaki **Başlangıç öğesi** açılır listesinde bir CMake hedefinin zaten seçili olduğundan emin olun.

![CMake oluştur menü komutu](media/cmake-build-menu.png "CMake derlemesi komut menüsü")

Derleme konfigürasyonları, ortam değişkenleri, komut satırı bağımsız değişkenleri ve *CMakeSettings.js* dosyadaki diğer ayarları özelleştirebilirsiniz. *CMakeLists.txt* dosyasını değiştirmeden değişiklik yapmanızı sağlar. Daha fazla bilgi için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).

Bekleneceğiniz gibi, yapı sonuçları **Çıkış penceresi** ve **hata listesi** gösterilir.

![CMake derleme hataları](media/cmake-build-errors.png "CMake derleme hataları")

Birden çok derleme hedefi olan bir klasörde, hangi CMake hedefinin derlenmeyeceğini belirtebilirsiniz: **CMake** menüsünde **derleme** öğesini seçin veya hedefi belirtmek Için *CMakeLists.txt* bağlam menüsünü seçin. CMake projesinde **CTRL + SHIFT + B** tuşlarına girerseniz, geçerli etkin belgeyi oluşturur.

## <a name="debugging-cmake-projects"></a>CMake projelerinde hata ayıklama

CMake projesinde hata ayıklamak için tercih edilen yapılandırmayı seçin ve **F5** tuşuna basın. Ya da araç çubuğundaki **Çalıştır** düğmesine basın. **Çalıştır** düğmesi "başlangıç öğesi Seç" diyorsa, açılan oku seçin ve çalıştırmak istediğiniz hedefi seçin. (CMake projesinde, "geçerli belge" seçeneği yalnızca. cpp dosyaları için geçerlidir.)

![CMake Çalıştır düğmesi](media/cmake-run-button.png "CMake Çalıştır düğmesi")

Önceki derlemeden bu yana değişiklikler yapılmışsa, **Run** veya **F5** komutları ilk olarak projeyi oluşturur.

Dosyadaki **launch.vs.js** özelliklerini ayarlayarak CMake hata ayıklama oturumunu özelleştirebilirsiniz. Daha fazla bilgi için bkz. [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md).

## <a name="editing-cmakeliststxt-files"></a>CMakeLists.txt dosyaları düzenleniyor

Bir *CMakeLists.txt* dosyayı düzenlemek için, **Çözüm Gezgini** dosyasında dosyaya sağ tıklayın ve **Aç** ' ı seçin. Dosyada değişiklik yaparsanız, sarı bir durum çubuğu görünür ve IntelliSense 'in güncelleşmekte olduğunu bildirir. Güncelleştirme işlemini iptal etmek için size bir şans sağlar. *CMakeLists.txt* hakkında bilgi için bkz. [CMake belgeleri](https://cmake.org/documentation/).

   ![CMakeLists.txt dosya düzenlemesi](media/cmake-cmakelists.png "CMakeLists.txt dosya düzenlemesi")

Dosyayı kaydettikten hemen sonra yapılandırma adımı otomatik olarak çalışır ve **Çıkış** penceresinde bilgileri görüntüler. Hatalar ve uyarılar **hata listesi** veya **Çıkış** penceresinde gösterilir. *CMakeLists.txt* sorunlu satıra gitmek için **hata listesi** bir hataya çift tıklayın.

   ![CMakeLists.txt dosyası hataları](media/cmake-cmakelists-error.png "CMakeLists.txt dosyası hataları")

## <a name="cmake-configure-step"></a>CMake yapılandırma adımı

*CMakeSettings.jsüzerinde* veya *CMakeLists.txt* dosyalardaki önemli değişiklikler yapıldığında, Visual Studio otomatik olarak CMake yapılandırma adımını yeniden çalıştırır. Yapılandırma adımı hatasız tamamlandığında, toplanan bilgiler C++ IntelliSense ve dil Hizmetleri ' nde kullanılabilir. Derleme ve hata ayıklama işlemlerinde de kullanılır.

Birden çok CMake projesinde aynı CMake yapılandırma adı (örneğin, x86-hata ayıklama) kullanılabilir. Bu yapılandırma seçildiğinde, tümü yapılandırılır ve oluşturulur (kendi yapı kök klasöründe). Bu CMake yapılandırmasına katılan tüm CMake projelerinin hedeflerinde hata ayıklaması yapabilirsiniz.

   ![CMake yalnızca derleme menü öğesi](media/cmake-build-only.png "CMake yalnızca derleme menü öğesi")

Derlemeleri ve hata ayıklama oturumlarını çalışma alanındaki projelerin bir alt kümesiyle sınırlayabilirsiniz. Dosyasında  *CMakeSettings.js* benzersiz bir adla yeni bir yapılandırma oluşturun. Ardından, yapılandırmayı yalnızca bu projelere uygulayın. Bu yapılandırma seçildiğinde, IntelliSense ve derleme ve hata ayıklama komutları yalnızca belirtilen projeler için geçerlidir.

## <a name="troubleshooting-cmake-cache-errors"></a>CMake önbelleği hatalarıyla ilgili sorunları giderme

Bir sorunu tanılamak için CMake önbelleğinin durumu hakkında daha fazla bilgiye ihtiyacınız varsa, aşağıdaki komutlardan birini çalıştırmak için **CMake** ana menüsünü veya Çözüm Gezgini *CMakeLists.txt* bağlam menüsünü açın **Solution Explorer** :

- **Görüntüleme önbelleği** , düzenleyicide yapı kök klasöründen  *CMakeCache.txt* dosyasını açar. (  *CMakeCache.txt* burada yaptığınız herhangi bir düzenleme, önbelleği temizleyene kadar temizlenir. Önbellek temizlendikten sonra devam eden değişiklikler yapmak için bkz. [CMake ayarlarını özelleştirme](customize-cmake-settings.md).)

- **Önbellek klasörünü aç** , derleme kök klasörü Için bir Gezgin penceresi açar.

- **Temiz önbellek** , sonraki CMake Yapılandır adımının temiz bir önbellekten başlaması için derleme kök klasörünü siler.

- **Önbellek oluşturma** , Visual Studio ortamı güncel kabul etse bile oluşturma adımını çalıştırmaya zorlar.

Otomatik önbellek oluşturma, **araçlar > seçeneklerinde > CMake > Genel** iletişim kutusunda devre dışı bırakılabilir.

## <a name="single-file-compilation"></a>Tek dosya derleme

CMake projesinde tek bir dosya oluşturmak için **Çözüm Gezgini** dosyasında dosyaya sağ tıklayın. Açılır menüden **Derle** ' yi seçin. Ana **CMake** menüsünü kullanarak düzenleyicide Şu anda açık olan dosyayı da oluşturabilirsiniz:

![CMake tek dosya derlemesi](media/cmake-single-file-compile.png)

## <a name="run-cmake-from-the-command-line"></a>CMake 'i komut satırından Çalıştır

CMake 'i Visual Studio Yükleyicisi yüklediyseniz, aşağıdaki adımları izleyerek komut satırından çalıştırabilirsiniz:

1. Uygun vsdevcmd.bat (x86/x64) çalıştırın. Daha fazla bilgi için, bkz. [komut satırı üzerinde oluşturma](building-on-the-command-line.md) .

1. Çıkış klasörünüze geçin.

1. Uygulamanızı derlemek/yapılandırmak için CMake 'i çalıştırın.

::: moniker-end

::: moniker range="msvc-140"

Visual Studio 2015 ' de, Visual Studio kullanıcıları bir [CMake Oluşturucu](https://cmake.org/cmake/help/latest/manual/cmake-generators.7.html) kullanarak, IDE 'nin IntelliSense, gözatma ve derleme Için kullandığı MSBuild proje dosyaları oluşturabilir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Öğretici: Visual Studio 'da C++ platformlar arası projeleri oluşturma](get-started-linux-cmake.md)\
[Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md)\
[Uzak Linux bilgisayarınıza bağlanma](../linux/connect-to-your-remote-linux-computer.md)\
[CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)\
[ Şema başvurusundaCMakeSettings.js](cmakesettings-reference.md)\
[CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
[Linux projenizi dağıtın, çalıştırın ve hatalarını ayıklayın](../linux/deploy-run-and-debug-your-linux-project.md)\
[CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)
