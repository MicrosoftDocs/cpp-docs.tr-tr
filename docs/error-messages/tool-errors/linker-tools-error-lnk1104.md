---
title: Bağlayıcı Araçları Hatası LNK1104
ms.date: 09/06/2019
f1_keywords:
- LNK1104
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
ms.openlocfilehash: f3effd9054954a90f69c5b18d8f099e6d705d9a3
ms.sourcegitcommit: 7babce70714242cf498ca811eec3695fad3abd03
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2019
ms.locfileid: "70808843"
---
# <a name="linker-tools-error-lnk1104"></a>Bağlayıcı Araçları Hatası LNK1104

> '*filename*' dosyası açılamıyor

Bağlayıcı belirtilen dosyayı açamadı. Bu sorunun en yaygın nedenleri, dosyanın kullanımda olması veya başka bir işlem tarafından kilitlenip kilitlenmesinden kaynaklanabilir. Ayrıca dosya yok olabilir veya bağlayıcının aradığı dizinlerden birinde bulunamaz. Ya da dosyaya erişmek için yeterli izniniz olmayabilir. Daha az yaygın olarak, disk alanınız tükenmiş olabilirsiniz, dosya çok büyük olabilir veya dosya yolu çok uzun olabilir.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bu hata, bağlayıcı okuma veya yazma için bir dosyayı açmaya çalıştığında ortaya çıkabilir. Olası nedenleri daraltmak için öncelikle ne tür bir dosya olduğunu kontrol edin. Ardından, belirli bir sorunu belirlemenize ve gidermeye yardımcı olması için aşağıdaki bölümleri kullanın.

### <a name="cant-open-your-app-or-its-pdb-file"></a>Uygulamanızı veya. pdb dosyasını açamıyor

Dosya adı, proje yapılarınız veya ilişkili bir. pdb dosyası ise, en yaygın nedeni, yeniden oluşturmaya çalıştığınızda uygulamanızın zaten çalışıyor olması veya bir hata ayıklayıcıda yüklenmiş olması olabilir. Bu sorunu giderecek şekilde yeniden oluşturmadan önce programı durdurun ve hata ayıklayıcı 'dan kaldırın. Uygulama, kaynak Düzenleyicisi gibi başka bir programda açıksa kapatın. Olağanüstü durumlarda, işlemi sonlandırmak için Görev Yöneticisi 'ni kullanmanız veya Visual Studio 'Yu durdurup yeniden başlatmanız gerekebilir.

Virüsten koruma programları genellikle yeni oluşturulan dosyalara, özellikle. exe ve. dll yürütülebilir dosyalarına erişimi geçici olarak engeller. Bu sorunu onarmak için, proje yapı dizinlerinizi virüsten koruma tarayıcısı 'ndan dışlanmasını deneyin.

### <a name="cant-open-a-microsoft-library-file"></a>Microsoft kitaplık dosyası açılamıyor

Açılamadığı dosya Microsoft tarafından sunulan standart kitaplık dosyalarından biri olan Kernel32. lib gibi bir proje yapılandırma hatası veya yükleme hatası olabilir. Windows SDK yüklendiğini doğrulayın ve projeniz MFC gibi başka Microsoft kitaplıklarını gerektiriyorsa, MFC bileşenlerinin Visual Studio yükleyicisi tarafından da yüklendiğinden emin olun. Dilediğiniz zaman isteğe bağlı bileşenler eklemek için yükleyiciyi yeniden çalıştırabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'Yu değiştirme](/visualstudio/install/modify-visual-studio). Belirli kitaplıkları ve SDK 'Ları seçmek için yükleyicideki bireysel bileşenler sekmesini kullanın.

Evrensel Windows (UWP) uygulamaları veya bileşenleri için Spectre ile hafiflemesiz kitaplıklar yoktur. Hata raporu *vccorlib. lib* dosyasından BAHSETMEDIĞINDE, UWP projesinde [/Qspectre](../../build/reference/qspectre.md) 'i etkinleştirmiş olabilirsiniz. Bu sorunu onarmak için **/Qspectre** derleyici seçeneğini devre dışı bırakın. Visual Studio 'da, proje **Özellik sayfaları** iletişim kutusunun >  **C/C++** **kod üretimi** sayfasında bulunan **Spectre risk azaltma** özelliğini değiştirin.

Visual Studio 'nun daha eski bir sürümü kullanılarak oluşturulmuş bir proje oluşturuyorsanız, bu sürüme ait platform araç takımı ve kitaplıkları yüklenmemiş olabilir. Hata iletisi, Msvcr100. lib gibi sürümlü bir kitaplık adı için oluşursa, bu durum büyük olasılıkla gerçekleşir. Bu sorunu onarmak için iki seçeneğiniz vardır: projeyi yüklediğiniz geçerli platform araç takımını kullanmak üzere yükseltebilir veya eski araç takımını yükleyebilir ve projeyi değiştirilmemiş olarak oluşturabilirsiniz. Daha fazla bilgi için bkz. [Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) ve [Eski projeler oluşturmak için Visual Studio 'da yerel çoklu](../../porting/use-native-multi-targeting.md)sürüm desteği kullanma.

Yeni bir hedef platform veya yapılandırma için derleme yaparken bu hatayı görürseniz, bu proje yapılandırması veya platform araç takımı için kitaplıklar yüklenmemiş olabilir. Projenizin [genel özellik sayfasında](../../build/reference/general-property-page-project.md) belirtilen **platform araç takımı** ve **Windows SDK sürümünün** yüklü olduğundan emin olun ve gerekli kitaplıkların, içinde belirtilen **kitaplık dizinlerinde** kullanılabilir olduğunu doğrulayın. yapılandırma ayarlarınıza yönelik [VC + + dizinleri Özellik sayfası](../../build/reference/vcpp-directories-property-page.md) . Hata ayıklama ve perakende yapılandırmalarının yanı sıra 32-bit ve 64 bit yapılandırmalarda ayrı ayarlar vardır. bu nedenle, bir derleme çalışıyorsa ancak başka bir hataya neden oluyorsa, ayarların doğru olduğundan ve gerekli araçların ve kitaplıkların her biri için yüklü olduğundan emin olun. derleme yaptığınız yapılandırma.

Başka bir bilgisayardan kopyalanmış bir proje oluşturmak için Visual Studio IDE kullanıyorsanız, kitaplıklar için yükleme konumları farklı olabilir. Projenin [VC + + dizinleri Özellik sayfasında](../../build/reference/vcpp-directories-property-page.md) bulunan **kitaplık dizinleri** özelliğini denetleyin ve gerekirse güncelleştirin. IDE 'de ayarlanmış geçerli kitaplık yollarını görmek ve düzenlemek için, **kitaplık dizinleri** özelliği için açılan denetimi seçin ve **Düzenle**' yi seçin. **Kitaplık dizinleri** Iletişim kutusunun **değerlendirilen değer** bölümü, kitaplık dosyaları için aranan geçerli yolları listeler.

Bu hata, Windows SDK yolu güncel olmadığında da oluşabilir. Windows SDK sürümünü Visual Studio sürümünüz sürümünden daha yeni yüklediyseniz, [VC + + dizinleri Özellik sayfasında](../../build/reference/vcpp-directories-property-page.md) belirtilen YOLLARıN yeni SDK ile eşleşecek şekilde güncelleştirildiğinden emin olun. Geliştirici Komut İstemi kullanıyorsanız, yeni SDK yolları için ortam değişkenlerini Başlatan toplu iş dosyasının güncelleştirildiğinden emin olun. Bu sorun, güncelleştirilmiş SDK 'Ları yüklemek için Visual Studio yükleyicisi kullanılarak kaçınılabilir.

### <a name="cannot-open-a-third-party-library-file"></a>Üçüncü taraf kitaplık dosyası açılamıyor

Bu sorunun birkaç yaygın nedeni vardır:

- Kitaplık dosyanızın yolu yanlış olabilir veya onu bağlayıcıya belirtmeyebilirsiniz.

- Kitaplığın 32 bitlik bir sürümünü yüklemiş olabilirsiniz, ancak 64 bit ya da tam tersi için derleme yapıyorsanız.

- Kitaplıkta yüklü olmayan diğer kitaplıkların bağımlılıkları olabilir.

Bir yol sorununu onarmak için, LıB ortam değişkeninin ayarlandığını ve oluşturduğunuz her yapılandırma için kullandığınız kitaplıkların tüm dizinlerini içerdiğini doğrulayın. IDE 'de LIB değişkeni, [VC + + dizinleri özellik sayfasındaki](../../build/reference/vcpp-directories-property-page.md) **kitaplık dizinleri** özelliği tarafından ayarlanır. Oluşturduğunuz her yapılandırma için, ihtiyacınız olan kitaplıkları içeren tüm dizinlerin burada listelendiğinden emin olun.

Standart Kitaplık dizinini geçersiz kılan bir kitaplık dizini sağlamanız gerekiyorsa, komut satırında [/LIBPATH](../../build/reference/libpath-additional-libpath.md) seçeneğini KULLANABILIR veya IDE 'de yapılandırma özelliklerindeki **Ek kitaplık dizinleri** özelliğini kullanabilirsiniz  **Projeniz için > bağlayıcı > Genel** Özellik sayfası.

Oluşturduğunuz yapılandırmaların her bir kitaplığı için ihtiyaç duyduğunuz her sürümü yüklediğinizden emin olun. Yükleme ve kurulum işlemlerini otomatik hale getirmek için [vcpkg](../../vcpkg.md) paket yönetimi yardımcı programını kullanmayı göz önünde bulundurun. Mümkün olduğunca, üçüncü taraf kitaplıklarının kopyalarını oluşturmak en iyisidir. bu nedenle, kitaplıkların gerektirdiği tüm yerel bağımlılıklara sahip olduğunuzdan emin olun ve bunlar projenizle aynı yapılandırmalara göre oluşturulmazlar.

### <a name="cannot-open-a-file-built-by-your-project"></a>Projeniz tarafından oluşturulan bir dosya açılamaz

Dosya *dosya adı* çözümünüz tarafından derlense ancak bağlayıcı buna erişmeye çalıştığında henüz yoksa, bu hatayı görebilirsiniz. Bu, bir proje başka bir projeye bağlı olduğunda gerçekleşebilir, ancak projeler doğru sırada derlenmez. Bu sorunu onarmak için, proje başvurularınızın dosyayı kullanan projede ayarlandığından emin olun. bu nedenle, eksik dosya istenmeden önce oluşturulur. Daha fazla bilgi için bkz. [Visual Studio C++ projelerinde başvuruları ekleme](../../build/adding-references-in-visual-cpp-projects.md) ve [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>' C:\\program. obj ' dosyası açılamıyor

Bu hatayı veya sürücünüzün kökündeki beklenmeyen bir. obj dosyasını içeren benzer bir hatayı görürseniz, sorun neredeyse tamamen çift tırnak içine sarılan bir kitaplık yoludur.

Komut satırı yapılarına yönelik bu sorunu gidermek için [/libpath](../../build/reference/libpath-additional-libpath.md) seçenek PARAMETRELERINI, LIB ortam değişkeninde belirtilen yolları ve komut satırında belirtilen yolları denetleyin ve boşluk içeren tüm yollar etrafında çift tırnak işareti kullandığınızdan emin olun.

IDE 'de bu sorunu onarmak için yapılandırma özellikleri [> VC + + dizinleri](../../build/reference/vcpp-directories-property-page.md) Özellik sayfasında, yapılandırma özellikleri > bağlayıcı ' da **Ek kitaplık dizinleri** özelliği olan **kitaplık dizinleri** özelliğini kontrol edin.  **> Genel** Özellik sayfası ve yapılandırma özelliklerindeki **ek bağımlılıklar** özelliği, projeniz için **> bağlayıcı > giriş** Özellik sayfasında. İhtiyaç duyduğunuz kitaplıkları içeren tüm dizin yollarının gerekirse çift tırnaklara sarmalanmış olduğundan emin olun.

### <a name="other-common-issues"></a>Diğer yaygın sorunlar

Bu hata, komut satırında veya bir [#pragma yorumu (lib, "library_name")](../../preprocessor/comment-c-cpp.md) yönergesinde bağlayıcıya belirtilen kitaplık dosya adı veya yolu yanlış olduğunda ya da yolun geçersiz bir sürücü belirtimine sahip olması durumunda ortaya çıkabilir. Yazımınızı ve dosya uzantısını denetleyip dosyanın belirtilen konumda var olduğunu doğrulayın.

Başka bir program dosyayı açık olabilir ve bağlayıcı buna yazamıyor. Virüsten koruma programları genellikle yeni oluşturulan dosyalara erişimi geçici olarak engeller. Bu sorunu onarmak için, proje yapı dizinlerinizi virüsten koruma tarayıcısı 'ndan dışlanmasını deneyin.

Paralel derleme seçeneği kullanıyorsanız, Visual Studio 'nun dosyayı başka bir iş parçacığında kilitlediği olasıdır. Bu sorunu onarmak için, birden çok projede aynı kod nesnesini veya kitaplığı yapılandırmayın ve projenizde oluşturulan ikili dosyaları çekmek için derleme bağımlılıklarını veya proje başvurularını kullandığınızı doğrulayın.

**Ek bağımlılıklar** özelliğinde tek tek kitaplıkları belirttiğinizde, virgül veya noktalı virgül değil, kitaplık adlarını ayırmak için boşluk kullanın. **Ek bağımlılıklar** iletişim kutusunu açmak için **Düzenle** menü öğesini kullanırsanız, adları virgül, noktalı virgül veya boşluk değil olarak ayırmak için newlines kullanın. Ayrıca, **kitaplık dizinleri** ve **Ek kitaplık dizinleri** iletişim kutularında kitaplık yollarını belirttiğinizde newlines ' i kullanın.

*Dosya adı* için yol 260 karakterden fazlasına genişlediğinde bu hatayı görebilirsiniz. Gerekli dosyaların yollarını kısaltmak için gerekirse adları değiştirin veya dizin yapınızı yeniden düzenleyin.

Dosya çok büyük olduğu için bu hata ortaya çıkabilir. Boyutlu bir gigabayt 'tan daha fazla kitaplık veya nesne dosyası 32 bitlik bağlayıcı için sorunlara neden olabilir. Bu sorun için olası bir çözüm 64 bit araç takımını kullanmaktır. Komut satırında bunun nasıl yapılacağı hakkında daha fazla bilgi için bkz [. nasıl yapılır: Komut satırında C++ ](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)64 bitlik görsel araç takımını etkinleştirin. Bunun IDE 'de nasıl yapılacağı hakkında bilgi için bkz. [64 bit derleyici ve araçlarla MSBuild kullanma](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) ve bu Stack Overflow Gönderi: [Visual Studio 'nun yerel AMD64 araç zincirini kullanma şekli](https://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

Bu hata, dosya *adına*erişmek için yeterli dosya izinleriniz yoksa oluşabilir. Bu durum sıradan bir kullanıcı hesabı kullanıyorsanız ve korunan sistem dizinlerindeki kitaplık dosyalarına erişmeyi denerseniz veya özgün izinlerinin ayarlandığı diğer kullanıcılardan kopyalanan dosyaları kullanabilirsiniz. Bu sorunu onarmak için dosyayı yazılabilir bir proje dizinine taşıyın. Dosya yazılabilir bir dizinde ve erişim izni varsa, bir yönetici komut istemi kullanabilir ve dosyanın sahipliğini almak için takeown. exe komutunu çalıştırabilirsiniz.

Yeterli disk alanınız olmadığında hata oluşabilir. Bağlayıcı, birkaç durumda geçici dosyaları kullanır. Yeterli disk alanınız olsa bile, çok büyük bir bağlantı kullanılabilir disk alanını tükeniyor veya parçalara ayırın. [/Opt (iyileştirmeler)](../../build/reference/opt-optimizations.md) seçeneğini kullanmayı düşünün; geçişli COMDAT eleme, tüm nesne dosyalarını birden çok kez okur.

*Dosya adı* , geçici bir dosya için bağlayıcı tarafından oluşturulan bir dosya adı olan lnk*nnn*olarak adlandırılmışsa, TMP ortam değişkeninde belirtilen DIZIN mevcut olmayabilir veya TMP ortam değişkeni için birden fazla dizin belirtilebilir. TMP ortam değişkeni için yalnızca bir dizin yolu belirtilmelidir.
