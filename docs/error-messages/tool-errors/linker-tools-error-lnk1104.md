---
title: Bağlayıcı Araçları Hatası LNK1104
ms.date: 05/17/2017
f1_keywords:
- LNK1104
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
ms.openlocfilehash: fcd3c06ae2db5c43aacbf781800870a83d2d77c1
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451139"
---
# <a name="linker-tools-error-lnk1104"></a>Bağlayıcı Araçları Hatası LNK1104

> Dosya açılamıyor '*filename*'

Bağlayıcı, belirtilen dosya açılamadı. Bu sorunun en yaygın nedenleri şunlardır: dosya kullanımda veya başka bir işlem tarafından kilitli, yok, bağlayıcı arama dizinlerinin birinde bulunamıyor emin veya dosyaya erişmek için yeterli izne sahip değil. Daha az yaygın olarak, disk alanı yetersiz çalıştırın, dosya çok büyük olabilir veya dosya yolu çok uzun olabilir.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bağlayıcı için okuma veya yazma için bir dosyayı açmaya çalıştığında bu hata oluşabilir. Olası nedenler daraltmak için önce ne tür bir dosya denetleyin ve tanımlamak ve belirli sorun gidermek için aşağıdaki bölümleri kullanın.

### <a name="cannot-open-your-app-or-its-pdb-file"></a>Uygulamanızı veya kendi .pdb dosyası açılamıyor

Yürütülebilir dosya adı ise projeniz derlenir, ya bir ilgili .pdb dosyası, en yaygın nedeni uygulamanızı yeniden oluşturmak deneyin ya da bir hata ayıklayıcıda yüklendiği zaten çalışıyor. Bu sorunu gidermek için programı durdurun ve yeniden oluşturmadan önce hata ayıklayıcı'dan kaldırın. Kaynak Düzenleyicisi gibi uygulama başka bir programda açık ise kapatın. Aşırı durumlarda işlemi sonlandırmak veya durdurun ve Visual Studio'yu yeniden başlatmanız Görev Yöneticisi'ni kullanmanız gerekebilir.

Virüsten koruma programları genellikle geçici olarak yeni oluşturulan dosyalar için özellikle .exe ve .dll yürütülebilir dosyalar erişimi engelleme. Bu sorunu gidermek için Proje yapı dizinlerinizi virüsten koruma tarayıcıdan hariç deneyin.

### <a name="cannot-open-a-microsoft-library-file"></a>Bir Microsoft Library dosyası açılamıyor

Açılamıyor dosya bu kernel32.lib gibi Microsoft tarafından sağlanan standart kitaplık dosyalarını biri, bir proje yapılandırması hatası veya bir yükleme hatası olabilir. Windows SDK'sı yüklendiğini doğrulayın ve projeniz MFC gibi diğer Microsoft kitaplıkları gerektiriyorsa, MFC bileşenlerini de Visual Studio yükleyicisi tarafından yüklendiğinden emin olun. İsteğe bağlı bileşenler herhangi bir zamanda yeniden eklemek için yükleyici çalıştırabilirsiniz. Daha fazla bilgi için [değiştirme Visual Studio](/visualstudio/install/modify-visual-studio). Bağımsız bileşenler sekmesinde yükleyicide belirli kitaplıklarına ve Sdk'lara seçmek için kullanın.

Visual Studio'nun daha eski bir sürümü kullanılarak oluşturulmuş bir proje oluşturuyorsanız, platform araç takımı ve kitaplıklar bu sürümü yüklü olmayabilir. Hata iletisi msvcr100.lib gibi bir tutulan kitaplık adı için oluşursa bunun neden olabilir. Bu sorunu çözmek için iki seçeneğiniz vardır: projeyi yüklediğiniz geçerli platform araç takımını kullanacak şekilde yükseltebilir veya eski Araç Takımı'nı yükleyebilir ve değişmeden projeyi derleyin. Daha fazla bilgi için [önceki sürümleri, Visual C++ projeleri yükseltme](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) ve [yerel çoklu sürüm desteğinin Visual Studio'da eski projeleri oluşturmak için kullanmak](../../porting/use-native-multi-targeting.md).

Yeni Hedef platform veya yapılandırma için oluştururken bu hatayı görürseniz, bu proje yapılandırmasını veya platform araç takımını kitaplıkları yüklü olmayabilir. Doğrulayın **Platform araç takımını** ve **Windows SDK sürümü** belirtilen [genel özellik sayfası](../../build/reference/general-property-page-project.md) projeniz için yüklü olduğunu ve doğrulayın gerekli kitaplıkları kullanılabilir **kitaplık dizinleri** belirtilen [VC ++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) yapılandırma ayarlarınızı için. Hata ayıklama için ayrı ayarlar vardır ve perakende yapılandırmaları yanı sıra 32 bit ve 64-bit yapılandırmaları, bu nedenle bir derleme çalışır, ancak başka bir hataya neden ayarlarının doğru olduğundan emin olun ve için gerekli araçları ve kitaplıkları yüklü her oluşturduğunuz yapılandırma.

Başka bir bilgisayardan kopyalanan bir projeyi derlemek için Visual Studio IDE kullanıyorsanız, kitaplıkları için yükleme konumlarını farklı olabilir. Denetleme **kitaplık dizinleri** özelliği [VC ++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) projenin ve gerekirse güncelleştirin. Aşağı açılan denetim için bakın ve IDE içinde ayarlamak geçerli kitaplık yollarını düzenlemek için seçin **kitaplık dizinleri** özelliği ve **Düzenle**. **Değeri Hesaplandı** bölümünü **kitaplık dizinleri** iletişim kitaplığı dosyaları için Aranan geçerli yollarını listeler.

Bu hata, Windows SDK yolunu güncel olduğunda da meydana gelebilir. Visual Studio sürümünden daha yeni olan Windows SDK'sı sürümünü yüklediyseniz, yolları olarak belirttiğinizden emin olun. [VC ++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md) yeni SDK'sı eşleşecek şekilde güncelleştirilir. Geliştirici Komut İstemi'ni kullanırsanız, ortam değişkenleri başlatır toplu iş dosyasını yeni SDK yollarını güncelleştirildiğinden emin olun. Bu sorun, güncelleştirilmiş bir SDK'larını yüklemek için Visual Studio yükleyicisi kullanılarak önlenebilir.

### <a name="cannot-open-a-third-party-library-file"></a>Bir üçüncü taraf kitaplık dosyası açılamıyor

Bu sorunu bazı yaygın nedenleri şunlardır:

- Kitaplık dosyanızın yolu yanlış olabilir veya bağlayıcıya belirttikten değil.

- Kitaplığı 32-bit bir sürümünü yüklemiş olabilirsiniz, ancak 64-bit ya da tam tersi için oluşturuyorsunuz.

- Kitaplık bağımlılıkları yüklü olmayan diğer kitaplıkları olabilir.

Bir yol sorunu düzeltmek için LIB ortam değişkeni ayarlanır ve oluşturduğunuz her yapılandırma için kullanmak kitaplıkları için tüm dizinleri içeren doğrulayın. IDE içinde LIB değişkeni ayarlamak **kitaplık dizinleri** özelliği [VC ++ Directories Property Page](../../build/reference/vcpp-directories-property-page.md). İhtiyacınız olan kitaplıkları içeren tüm dizinleri oluşturduğunuz her yapılandırma için burada listelenen emin olun.

Kitaplık dizinine sağlamanız gerekiyorsa, standart kitaplık dizinini geçersiz kılar, kullanabileceğiniz [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği komut satırında veya IDE'de kullanabileceğiniz **ek kitaplık dizinleri** bir özellik **yapılandırma özellikleri > bağlayıcı > Genel** projeniz için özellik sayfası.

Derleme yapılandırmaları için gereksinim duyduğunuz kitaplığının her sürümünü yüklediğinizden emin olun. Kullanmayı [vcpkg](../../vcpkg.md) paketini yükleme ve kurulum için birçok ortak kitaplıkları otomatik hale getirmek için yönetim yardımcı programı. Mümkün olduğunda kitaplıkları gerektirir ve projeniz gibi aynı yapılandırmaları için oluşturulan tüm yerel bağımlılıkları bulunduğundan emin olacak şekilde, üçüncü taraf kitaplıklar, kendi kopyalarını oluşturmak idealdir.

### <a name="cannot-open-a-file-built-by-your-project"></a>Projeniz tarafından oluşturulmuş bir dosya açılamıyor

Bu hatayı görebilirsiniz dosya *filename* çözümünüz tarafından oluşturulmuş, ancak bağlayıcı bunu erişmeyi denediğinde henüz mevcut değil. Başka bir projeye bir proje bağlıdır, ancak projelerin doğru sırada yerleşik olarak bulunmaz, bu durum ortaya çıkabilir. Bu sorunu gidermek için projenizin başvurularına geçmesi gereken, eksik dosyayı oluşturulmuştur, dosyayı kullanan projede ayarlandığından emin olun. Daha fazla bilgi için [Visual Studio'daki başvurularının eklenmesi C++ projeleri](../../build/adding-references-in-visual-cpp-projects.md) ve [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>Dosya açılamıyor ' C:\\Program.obj'

Bu hata ya da bir beklenmeyen .obj dosyası, sürücünün kökünde içeren benzer bir hata görürseniz, olasılıkla çift tırnak içine sarmalanmamış bir kitaplık yolu bir sorundur.

Komut satırı derlemeleri için bu sorunu gidermek için denetleme [/Libpath](../../build/reference/libpath-additional-libpath.md) seçenek parametreleri, kitaplığı ortam değişkeni içinde belirtilen yolların ve komut satırında belirtilen yolların ve çift-tüm yolları tırnak kullandığınızdan emin olun boşluk içeren.

IDE içinde bu sorunu gidermek için işaretleyin **kitaplık dizinleri** özelliği [yapılandırma özellikleri > VC ++ dizinleri](../../build/reference/vcpp-directories-property-page.md) özellik sayfası **ek kitaplık dizinleri** özelliğinde **yapılandırma özellikleri > bağlayıcı > Genel** özellik sayfası ve **ek bağımlılıklar** özelliğinde **yapılandırma Özellikler > bağlayıcı > giriş** projeniz için özellik sayfası. İhtiyacınız olan kitaplıkları içeren dizin yolları, gerekirse çift tırnak içine sarmalanır ve emin olun.

### <a name="other-common-issues"></a>Diğer ortak sorunları

Bağlayıcı komut satırında veya kitaplığı dosya adı veya yolu belirtildiği zaman, bu hata oluşabilir bir [#pragma yorum (LIB, "library_name")](../../preprocessor/comment-c-cpp.md) yönergesi, yanlış veya yol geçersiz sürücü belirtimi. Yazım denetimi ve dosya uzantısı denetleyin ve dosyanın belirtilen konumda var olduğunu doğrulayın.

Dosyayı başka bir program olabilir ve bağlayıcı yazamaz. Virüsten koruma programları genellikle geçici olarak yeni oluşturulan dosyalara erişimi engelleyin. Bu sorunu gidermek için Proje yapı dizinlerinizi virüsten koruma tarayıcıdan hariç deneyin.

Paralel derleme seçeneği kullanıyorsanız, Visual Studio dosya başka bir iş parçacığı üzerinde kilitledi mümkündür. Bu sorunu gidermek için aynı kod nesnesi veya birden çok proje kitaplıkta derlenmiyor ve yerleşik projenizde ikililerinin alınacağı derleme bağımlılıkları veya proje başvuruları kullanmanız doğrulayın.

Tek tek kitaplıklarda belirttiğinizde **ek bağımlılıklar** özelliği doğrudan alanları kitaplık adlarını, değil virgül veya noktalı ayırmak için virgül kullanın. Kullanırsanız **Düzenle** açmak için menü öğesi **ek bağımlılıklar** iletişim kutusu, adları, değil virgül, noktalı virgül veya boşluk ayırmak için kullanım satır başı. Satır başı kitaplık yollarını belirttiğinizde de **kitaplık dizinleri** ve **ek kitaplık dizinleri** iletişim kutuları.

Bu hatayı görebilirsiniz, yolunu *filename* için 260 karakterden genişletir. Adlarını değiştirme veya gerekli dosyalara olan yolları kısaltmak için gerekirse dizin yapınızı yeniden düzenleyin.

Dosya çok büyük olduğundan, bu hata oluşabilir. Daha fazla bir gigabayt boyutunda 32-bit bağlayıcı için sorunlara neden olabilir, kitaplıkları veya nesne dosyaları. Bu sorunun olası bir düzeltme 64-bit araç takımı kullanmaktır. Komut satırında nasıl yapılacağı hakkında daha fazla bilgi için bkz. [nasıl yapılır: Bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirme](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). IDE içinde bunun hakkında daha fazla bilgi için bkz: [64 bit derleyici ve araçlarla MSBuild kullanma](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) ve Stack Overflow yazıya: [Visual Studio yerel amd64 araç zincirini kullanın yapma](https://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

Yeterli dosya erişim iznine sahip değilse bu hata oluşabilir *filename*. Bu kitaplık dosyaları korumalı sistem dizinlerde erişmek için bir normal bir kullanıcı hesabı ve girişim kullanın veya kendi özgün izinleri olan diğer kullanıcıların kopyalanan dosya halinde gerçekleşebilir ayarlayın. Bu sorunu gidermek için dosyayı bir yazılabilir proje dizinine taşıyın. Dosya yazılabilir bir dizinde ancak erişilemez izinleri varsa bir yönetici komut istemi kullanın ve dosya sahipliğini takeown.exe komutu çalıştırın.

Yeterli disk alanı yoksa hata oluşabilir. Bağlayıcı, bazı durumlarda geçici dosyaları kullanır. Yeterli disk alanına sahip olsanız bile, çok büyük bir bağlantı deplete veya parçalara kullanılabilir disk alanı. Kullanmayı [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md) seçeneği; geçişli COMDAT eleme okuma tüm nesne dosyaları birden çok kez yaparsanız.

Varsa *filename* LNK adlı*nnn*, geçici bir dosya için bağlayıcı tarafından oluşturulan bir dosya adı olan, TMP ortam değişkeninde belirtilen dizin yok veya birden fazla dizin olabilir için TMP ortam değişkenini belirtilen. Yalnızca bir dizin yolu için TMP ortam değişkenini belirtilmelidir.
