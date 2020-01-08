---
title: Bağlayıcı Araçları Hatası LNK1104
description: Microsoft C ve C++ (MSVC) BAĞLAYıCı hatası LNK1104, nedenleri ve olası çözümleri açıklanmaktadır.
ms.date: 12/13/2019
f1_keywords:
- LNK1104
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
ms.openlocfilehash: 8878db1b0829703b22b2f7863eb7955d17ad3096
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301788"
---
# <a name="linker-tools-error-lnk1104"></a>Bağlayıcı Araçları Hatası LNK1104

> '*filename*' dosyası açılamıyor

Bu hata, bağlayıcı dosyayı okumak ya da yazmak için bir dosya açamazsa raporlanır. Sorunun en yaygın iki nedeni şunlardır:

- programınız zaten çalışıyor veya hata ayıklayıcıya yüklendi ve

- Kitaplık yollarınız yanlış veya çift tırnaklı şekilde sarmalanmamış.

Bu hatanın birçok nedeni olabilir. Onları daraltmak için, önce dosya *Dosya adının* ne tür olduğunu kontrol edin. Ardından, belirli bir sorunu belirlemenize ve gidermeye yardımcı olması için aşağıdaki bölümleri kullanın.

## <a name="cant-open-your-app-or-its-pdb-file"></a>Uygulamanızı veya. pdb dosyasını açamıyor

### <a name="your-app-is-running-or-its-loaded-in-the-debugger"></a>Uygulamanız çalışıyor veya hata ayıklayıcıda yüklendi

*Dosya adı* , yürütülebilir dosyanın adı ya da ilişkili bir. pdb dosyası olduğunda, uygulamanızın zaten çalışır durumda olup olmadığını görün. Sonra bir hata ayıklayıcıda yüklenip yüklenmediğini kontrol edin. Bu sorunu giderecek şekilde yeniden oluşturmadan önce programı durdurun ve hata ayıklayıcı 'dan kaldırın. Uygulama, kaynak Düzenleyicisi gibi başka bir programda açıksa kapatın. Programınız yanıt vermezse, işlemi sonlandırmak için Görev Yöneticisi 'ni kullanmanız gerekebilir. Ayrıca, Visual Studio 'Yu kapatıp yeniden başlatmanız gerekebilir.

### <a name="your-app-is-locked-by-an-antivirus-scan"></a>Uygulamanız bir virüsten koruma taraması tarafından kilitlenmiş

Virüsten koruma programları genellikle yeni oluşturulan dosyalara, özellikle. exe ve. dll yürütülebilir dosyalarına erişimi geçici olarak engeller. Bu sorunu onarmak için, proje yapı dizinlerinizi virüsten koruma tarayıcısı 'ndan dışlanmasını deneyin.

## <a name="cant-open-a-microsoft-library-file"></a>Microsoft kitaplık dosyası açılamıyor

### <a name="windows-libraries-such-as-kernel32lib"></a>Kernel32. lib gibi Windows kitaplıkları

Açılamadığı dosya Microsoft tarafından sunulan standart kitaplık dosyalarından biri olan *Kernel32. lib*gibi bir proje yapılandırma hatası veya yükleme hatası olabilir. Windows SDK yüklendiğini doğrulayın. Projeniz MFC gibi başka Microsoft kitaplıkları gerektiriyorsa, MFC bileşenlerinin Visual Studio yükleyicisi tarafından da yüklendiğinden emin olun. Dilediğiniz zaman isteğe bağlı bileşenler eklemek için yükleyiciyi yeniden çalıştırabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 'Yu değiştirme](/visualstudio/install/modify-visual-studio). Belirli kitaplıkları ve SDK 'Ları seçmek için yükleyicideki **bireysel bileşenler** sekmesini kullanın.

### <a name="versioned-vcruntime-libraries"></a>Sürümlü vcruntime kitaplıkları

Hata iletisinde *Msvcr120. lib*gibi sürümlenmiş bir Microsoft kitaplığı varsa, bu derleyici sürümü için platform araç takımı yüklü olmayabilir. Bu sorunu onarmak için iki seçeneğiniz vardır: projeyi geçerli platform araç takımını kullanmak üzere yükseltin veya eski araç takımını yükleyip projeyi değiştirilmemiş olarak derleyin. Daha fazla bilgi için bkz. [Visual C++ Studio 'nun önceki sürümlerinden projeleri yükseltme](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) ve [Eski projeler oluşturmak için Visual Studio 'da yerel çoklu](../../porting/use-native-multi-targeting.md)sürüm desteği kullanma.

### <a name="retail-debug-or-platform-specific-libraries"></a>Perakende, hata ayıklama veya platforma özgü kitaplıklar

Yeni bir hedef platform veya bir yapılandırma (perakende ya da ARM64 gibi) için ilk derleme yaptığınızda hata ortaya çıkabilir. IDE 'de, [genel özellik sayfasında](../../build/reference/general-property-page-project.md) belirtilen **platform araç** takımının ve **Windows SDK sürümünün** yüklü olduğundan emin olun. Ayrıca, gerekli kitaplıkların [VC + + dizinleri Özellik sayfasında](../../build/reference/vcpp-directories-property-page.md)belirtilen **kitaplık dizinlerinde** kullanılabilir olduğunu doğrulayın. Hata ayıklama, perakende, x86 veya ARM64 gibi her yapılandırma için özellikleri denetleyin. Bir derleme çalışırsa ancak başka bir değilse, her ikisi için de ayarları karşılaştırın. Eksik gerekli araçları ve kitaplıkları yükler.

### <a name="the-vccorliblib-library"></a>Vccorlib. lib kitaplığı

Evrensel Windows (UWP) uygulamaları veya bileşenleri için Spectre ile hafiflemesiz kitaplıklar yoktur. Hata iletisi *vccorlib. lib*IÇERIYORSA, UWP projesinde [/Qspectre](../../build/reference/qspectre.md) 'i etkinleştirmiş olabilirsiniz. Bu sorunu onarmak için **/Qspectre** derleyici seçeneğini devre dışı bırakın. Visual Studio 'da **Spectre azaltma** özelliğini değiştirin. Proje **Özellik sayfaları** iletişim kutusunun **C/C++**  > **kod üretimi** sayfasında bulunur.

### <a name="libraries-in-projects-from-online-or-other-sources"></a>Çevrimiçi veya diğer kaynaklardan gelen projelerde kitaplıklar

Başka bir bilgisayardan kopyalanmış bir proje oluşturursanız, kitaplık yükleme konumları farklı olabilir. Komut satırı derlemeleri için, LıB ortam değişkeninin ve kitaplık yollarının derleme için doğru şekilde ayarlandığını doğrulayın. Visual Studio 'da, projenizin özellik sayfalarında ayarlanmış geçerli kitaplık yollarını görebilir ve düzenleyebilirsiniz. **VC + + dizinleri** sayfasında, **kitaplık dizinleri** özelliği için açılan denetimi seçin ve ardından **Düzenle**' yi seçin. **Kitaplık dizinleri** Iletişim kutusunun **değerlendirilen değer** bölümü, kitaplık dosyaları için aranan geçerli yolları listeler. Bu yolları yerel kitaplıklarınıza işaret etmek için güncelleştirin.

### <a name="updated-windows-sdk-libraries"></a>Windows SDK kitaplıkları güncelleştirildi

Bu hata, Windows SDK Visual Studio yolu güncel olmadığında ortaya çıkabilir. Visual Studio yükleyicisinden bağımsız olarak daha yeni bir Windows SDK yüklerseniz bu durum oluşabilir. IDE 'de onarmak için, [VC + + dizinleri Özellik sayfasında](../../build/reference/vcpp-directories-property-page.md)belirtilen yolları güncelleştirin. Yoldaki sürümü yeni SDK ile eşleşecek şekilde ayarlayın. Geliştirici Komut İstemi kullanıyorsanız, ortam değişkenlerini Başlatan toplu iş dosyasını yeni SDK yollarıyla güncelleştirin. Bu sorun, güncelleştirilmiş SDK 'Ları yüklemek için Visual Studio yükleyicisi kullanılarak kaçınılabilir.

## <a name="cant-open-a-third-party-library-file"></a>Üçüncü taraf kitaplık dosyası açılamıyor

Bu sorunun birkaç yaygın nedeni vardır:

- Kitaplık dosyanızın yolu yanlış veya çift tırnaklı şekilde sarmalanmamış olabilir. Ya da, bunu bağlayıcıya belirtmeyebilirsiniz.

- Kitaplığın 32 bitlik bir sürümünü yüklemiş olabilirsiniz ancak 64 bit için derleme yapıyorsanız veya başka bir şekilde.

- Kitaplıkta yüklü olmayan diğer kitaplıkların bağımlılıkları olabilir.

Komut satırı Derlemeleriyle ilgili bir yol sorununu onarmak için, LıB ortam değişkeninin ayarlandığını doğrulayın. Kullandığınız tüm kitaplıkların ve oluşturduğunuz her yapılandırma için yol içerdiğinden emin olun. IDE 'de, kitaplık yolları **VC + + dizinleri** > **kitaplık dizinleri** özelliği tarafından ayarlanır. Oluşturduğunuz her yapılandırma için, ihtiyacınız olan kitaplıkları içeren tüm dizinlerin burada listelendiğinden emin olun.

Standart Kitaplık dizinini geçersiz kılan bir kitaplık dizini sağlamanız gerekebilir. Komut satırında [/LIBPATH](../../build/reference/libpath-additional-libpath.md) seçeneğini kullanın. IDE 'de, projeniz için **yapılandırma özellikleri > bağlayıcı > genel** Özellik sayfasında bulunan **Ek kitaplık dizinleri** özelliğini kullanın.

Oluşturduğunuz yapılandırmaların her birinde gerekli olan tüm kitaplık sürümlerini yüklediğinizden emin olun. Yükleme ve kurulum işlemlerini otomatik hale getirmek için [vcpkg](../../vcpkg.md) paket yönetimi yardımcı programını kullanmayı göz önünde bulundurun. Bunu yaptığınızda, üçüncü taraf kitaplıklarının kendi kopyalarını oluşturmak en iyisidir. Daha sonra, tüm kitaplıkların yerel bağımlılıklarını, projenizde aynı yapılandırmalara yönelik olarak oluşturulan tüm kitaplıklara sahip olduğunuzdan emin olursunuz.

## <a name="cant-open-a-file-built-by-your-project"></a>Projeniz tarafından oluşturulan bir dosyayı açamıyor

Bağlayıcı ona erişmeyi denediğinde *dosya adı* henüz yoksa bu hatayı görebilirsiniz. Bir proje çözümdeki başka bir projeye bağımlıysa, ancak projeler yanlış sırada derleniyorsa bu durum oluşabilir. Bu sorunu onarmak için, proje başvurularınızın dosyayı kullanan projede ayarlandığından emin olun. Daha sonra, eksik dosya, gerekli olmadan önce oluşturulmuştur. Daha fazla bilgi için bkz. [Visual Studio C++ projelerinde başvuruları ekleme](../../build/adding-references-in-visual-cpp-projects.md) ve [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

## <a name="cannot-open-file-cprogramobj"></a>' C:\\program. obj ' dosyası açılamıyor

Hata iletisinde *C:\\program. obj* dosya adını görürseniz, kitaplık yollarınızı çift tırnak içine sarın. Bu hata, *C:\\program dosyaları* ile başlayan sarmalanmamış bir yol bağlayıcıya geçirildiğinde oluşur. Sarmalanmamış yollar da benzer hatalara neden olabilir. Genellikle, sürücünüzün kökünde beklenmeyen bir. obj dosyası gösterir.

Bu sorunu komut satırı yapılarına yönelik olarak onarmak için [/libpath](../../build/reference/libpath-additional-libpath.md) seçenek parametrelerini denetleyin. Ayrıca, LıB ortam değişkeninde belirtilen yolları ve komut satırında belirtilen yolları kontrol edin. Boşluk içeren tüm yollar etrafında çift tırnak işareti kullandığınızdan emin olun.

IDE 'deki bu sorunu onarmak için, projeniz için aşağıdaki özelliklere gereken şekilde çift tırnak işareti ekleyin:

- [Yapılandırma özellikleri > VC + + dizinleri](../../build/reference/vcpp-directories-property-page.md) Özellik sayfasında bulunan **kitaplık dizinleri** özelliği

- **Yapılandırma özellikleri > bağlayıcı > genel** özellik sayfasındaki **Ek kitaplık dizinleri** özelliği

- **Yapılandırma özellikleri > bağlayıcı > giriş** özelliği sayfasında **ek bağımlılıklar** özelliği.

## <a name="other-common-issues"></a>Diğer yaygın sorunlar

### <a name="path-or-filename-issues"></a>Yol veya dosya adı sorunları

Bu hata, bağlayıcı için belirtilen kitaplık dosya adı veya yolu yanlış olduğunda meydana gelebilir. Ya da yol geçersiz bir sürücü belirtimine sahip olduğunda. Sorunlar için komut satırına veya herhangi bir [#pragma yorumu (lib, "library_name")](../../preprocessor/comment-c-cpp.md) yönergesine bakın. Yazımınızı ve dosya uzantısını denetleyip dosyanın belirtilen konumda var olduğunu doğrulayın.

### <a name="parallel-build-synchronization"></a>Paralel derleme eşitlemesi

Paralel bir yapı seçeneği kullanıyorsanız, Visual Studio dosyayı başka bir iş parçacığında kilitlemiş olabilir. Bu sorunu onarmak için, aynı kod nesnesinin veya kitaplığın birden çok projede derlenmediğinden emin olun. Projenizde oluşturulan ikili dosyaları seçmek için derleme bağımlılıklarını veya proje başvurularını kullanın.

### <a name="additional-dependencies-specified-in-the-ide"></a>IDE 'de belirtilen ek bağımlılıklar

**Ek bağımlılıklar** özelliğinde bağımsız kitaplıkları doğrudan belirttiğinizde, kitaplık adlarını ayırmak için boşluk kullanın. Virgül veya noktalı virgül kullanmayın. **Ek bağımlılıklar** iletişim kutusunu açmak için **Düzenle** menü öğesini kullanırsanız, adları virgül, noktalı virgül veya boşluk değil olarak ayırmak için newlines kullanın. Ayrıca, **kitaplık dizinleri** ve **Ek kitaplık dizinleri** iletişim kutularında kitaplık yollarını belirttiğinizde newlines ' i kullanın.

### <a name="paths-that-are-too-long"></a>Çok uzun olan yollar

*Dosya adı* için yol 260 karakterden fazlasına genişlediğinde bu hatayı görebilirsiniz. Gerekirse, dizin yapınızı yeniden düzenleyin veya yolları kısaltmak için klasör ve dosya adlarınızı kısaltın.

### <a name="files-that-are-too-large"></a>Çok büyük dosyalar

Dosya çok büyük olduğu için bu hata ortaya çıkabilir. Boyutlu bir gigabayt 'tan daha fazla kitaplık veya nesne dosyası 32 bitlik bağlayıcı için sorunlara neden olabilir. Bu sorun için olası bir çözüm 64 bit araç takımını kullanmaktır. Komut satırında 64 bit araç takımını kullanma hakkında daha fazla bilgi için, bkz. [nasıl yapılır: 64-bit görsel C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). IDE 'de 64 bit araç takımını kullanma hakkında daha fazla bilgi için bkz. MSBuild 'i [64 bit derleyici ve araçlarla kullanma](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project). Ayrıca bkz. bu Stack Overflow Post: [Visual Studio 'nun yerel AMD64 araç zincirini nasıl kullanmasını sağlama](https://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

### <a name="incorrect-file-permissions"></a>Yanlış dosya izinleri

Bu hata, dosya *adına*erişmek için yeterli dosya izinleriniz yoksa oluşabilir. Korumalı sistem dizinlerindeki kitaplık dosyalarına erişmek için sıradan bir kullanıcı hesabı kullanıyorsanız bu durum oluşabilir. Ya da hala özgün izinlerinin ayarlandığı diğer kullanıcılardan kopyalanan dosyaları kullanıyorsanız. Bu sorunu onarmak için dosyayı yazılabilir bir proje dizinine taşıyın. Taşınan dosyanın izinleri erişilemiyorsa, dosyanın sahipliğini almak için bir yönetici komut penceresinde takeown. exe komutunu çalıştırın.

### <a name="insufficient-disk-space"></a>Yetersiz disk alanı

Yeterli disk alanınız olmadığında hata oluşabilir. Bağlayıcı, birkaç durumda geçici dosyaları kullanır. Yeterli disk alanınız olsa bile, büyük bir bağlantı kullanılabilir disk alanını tükeniyor veya parçalara ayırın. [/Opt (iyileştirmeler)](../../build/reference/opt-optimizations.md) seçeneğini kullanmayı düşünün; geçişli COMDAT eleme, tüm nesne dosyalarını birden çok kez okur.

### <a name="problems-in-the-tmp-environment-variable"></a>TMP ortam değişkenindeki sorunlar

*Dosya adı* lnk*nnn*olarak adlandırılmışsa, geçici bir dosya için bağlayıcı tarafından oluşturulan bir dosya adıdır. TMP ortam değişkeninde belirtilen dizin mevcut olmayabilir. Ya da, TMP ortam değişkeni için birden fazla dizin belirtilebilir. TMP ortam değişkeni için yalnızca bir dizin yolu belirtilmelidir.

## <a name="help-my-issue-isnt-listed-here"></a>Yardım, sorunum burada listelenmedi!

Burada listelenen sorunlardan hiçbiri uygulanmadığı zaman, yardım için Visual Studio 'daki geri bildirim araçlarını kullanabilirsiniz. IDE 'de, menü çubuğuna gidin ve **sorun bildirmek > yardım > geri bildirim gönder**' i seçin. Ya da bir öneri göndermek **> yardım > geri bildirim gönder**' i kullanarak bir öneride bulunun. Visual Studio C++ [Geliştirici topluluğu](https://developercommunity.visualstudio.com/spaces/62/index.html)) Web sitesini de kullanabilirsiniz. Soruların yanıtlarını aramak ve yardım istemek için bunu kullanın. Daha fazla bilgi için bkz. [görsel C++ araç takımı veya belgelerde sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).

Bu makaleye eklememiz gereken bu sorunu çözmek için yeni bir yol tespit ediyorsanız bize bize izin verin. **Bu sayfa**için aşağıdaki düğmeyi kullanarak bize geri bildirim gönderebilirsiniz. Belge GitHub deposunda yeni bir sorun oluşturmak için bunu kullanın. [ C++ ](https://github.com/MicrosoftDocs/cpp-docs/issues) Teşekkürler!
