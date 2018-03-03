---
title: "Bağlayıcı araçları hatası LNK1104 | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1104
dev_langs:
- C++
helpviewer_keywords:
- LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c91853fe3310d8e577ac884545f86d1f4e1d4521
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1104"></a>Bağlayıcı Araçları Hatası LNK1104

> Dosya açılamıyor '*filename*'

Bağlayıcı, belirtilen dosya açılamadı. Bu sorunun en yaygın nedenleri arasında dosya kullanımda veya başka bir işlem tarafından kilitlendiğinden, yok, bağlayıcı arar dizinlerden biri bulunamıyor olduğunu veya dosyaya erişmek için yeterli izne sahip değil. Daha az yaygın olarak, disk alanı yetersiz çalışabilir, dosya çok büyük olabilir veya dosya yolu çok uzun olabilir.

## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler

Bağlayıcı okuma veya yazma için bir dosyayı açmaya çalıştığında bu hata oluşabilir. Olası nedenleri daraltmak için önce dosya türlerini denetleyin ve tanımlamak ve belirli sorun gidermek için aşağıdaki bölümleri kullanın.

### <a name="cannot-open-your-app-or-its-pdb-file"></a>Uygulamanızı veya kendi .pdb dosyasını açamıyor

Dosya adı yürütülebilir yazılmışsa projenizi oluşturur, ya bir ilişkili .pdb dosyasını en yaygın nedeni, uygulamanızın, yeniden deneyin veya Hata Ayıklayıcısı'ndaki yüklü olduğunda zaten çalışıyor. Bu sorunu gidermek için program durdurun ve yeniden oluşturmadan önce hata ayıklayıcı'dan kaldırın. Kaynak Düzenleyici gibi uygulama başka bir programda açık ise kapatın. Olağanüstü durumlarda işlemi sonlandırmamız veya durdurun ve Visual Studio yeniden Görev Yöneticisi'ni kullanmanız gerekebilir.

Virüsten koruma programları genellikle geçici olarak yeni oluşturulan dosyalar için özellikle .exe ve .dll yürütülebilir dosyalar erişimi engelleme. Bu sorunu gidermek için virüsten koruma tarayıcıdan proje derleme dizinlerinizi hariç deneyin.

### <a name="cannot-open-a-microsoft-library-file"></a>Bir Microsoft Library dosyası açılamıyor

Açılamıyor dosya kernel32.lib gibi Microsoft tarafından sağlanan standart kitaplık dosyalarından biri ise bir proje yapılandırma hatası veya bir yükleme hatası olabilir. Windows SDK'sı yüklendiğini doğrulayın ve projenizin MFC gibi diğer Microsoft kitaplıkları gerektiriyorsa, MFC bileşenlerini de Visual Studio yükleyicisi tarafından yüklenen emin olun. İsteğe bağlı bileşenleri herhangi bir zamanda yeniden eklemek için yükleyici çalıştırabilirsiniz. Daha fazla bilgi için bkz: [değiştirmek Visual Studio](/visualstudio/install/modify-visual-studio). Bileşenleri tek tek sekmesini yükleyicisinde belirli kitaplıkları ve SDK'ları seçmek için kullanın.

Visual Studio'nun daha eski bir sürümü kullanılarak oluşturulmuş bir proje oluşturuyorsanız, bu sürüm için kitaplıkları ve platform araç takımı yüklenmemiş olabilir. Hata iletisi msvcr100.lib gibi bir sürümü tutulan kitaplık adı için oluşursa bunun neden olabilir. Bu sorunu gidermek için iki seçeneğiniz vardır: yüklü olan geçerli platform araç takımı kullanmak için proje yükseltebilir veya daha eski araç takımı yükleyebilir ve değişmeden projeyi oluşturun. Daha fazla bilgi için bkz: [önceki sürümleri, Visual C++ projeleri yükseltme](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) ve [yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın](../../porting/use-native-multi-targeting.md).

Yeni hedef platformu ve yapılandırması için oluştururken bu hatayı görürseniz, bu proje yapılandırması veya platform araç takımı kitaplıkları yüklenmemiş. Doğrulayın **Platform araç takımı** ve **Windows SDK sürümü** belirtilen [genel özellik sayfası](../../ide/general-property-page-project.md) projeniz için yüklenir ve doğrulayın gerekli kitaplıkları kullanılabilir **kitaplık dizinleri** belirtilen [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) yapılandırma ayarlarınızı için. Hata ayıklama için ayrı ayarlar vardır ve perakende yapılandırmaları yanı sıra 32 bit ve 64-bit yapılandırmaları, bu nedenle bir yapı çalışır, ancak başka bir hataya neden olur ayarlarının doğru olduğundan emin olun ve için gereken Araçlar ve kitaplıkların yüklü her yapı yapılandırması.

Başka bir bilgisayardan kopyaladığınız bir proje oluşturmak için Visual Studio IDE kullanıyorsanız, kitaplıkları için yükleme konumlarını farklı olabilir. Denetleme **kitaplık dizinleri** özelliği [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) projesi için ve gerekirse güncelleştirin. Bakın ve IDE içinde ayarlama geçerli kitaplık yolları düzenlemek için aşağı açılır denetimin seçin **kitaplık dizinleri** özelliği ve **Düzenle**. **Değeri hesaplanan** bölümünü **kitaplık dizinleri** iletişim için kitaplık dosyalarını aranır geçerli yolları listeler.

Bu hata, Windows SDK yolunu güncel olduğunda da oluşabilir. Visual Studio sürümünüz yeni olan Windows SDK'sı sürümünü yüklediyseniz, yolları içinde belirttiğinizden emin olun. [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) yeni SDK eşleşecek şekilde güncelleştirilir. Geliştirici komut istemi kullanırsanız, ortam değişkenleri başlatır toplu iş dosyasını yeni SDK yollar için güncelleştirildiğinden emin olun. Bu sorun, güncelleştirilmiş SDK yüklemek için Visual Studio yükleyicisi kullanılarak önlenebilir.

### <a name="cannot-open-a-third-party-library-file"></a>Bir üçüncü taraf kitaplık dosyası açılamıyor

Bu sorunu birçok yaygın nedenleri şunlardır:

- Kitaplık dosyanızın yolu yanlış olabilir veya bağlayıcıya belirttikten değil.

- Kitaplık 32-bit sürümü yüklü, ancak 64-bit ya da tam tersini için oluşturma.

- Kitaplık bağımlılıkları yüklü olmayan diğer kitaplıkları olabilir.

Yol sorunu düzeltmek için LIB ortam değişkeni ayarlanır ve, yapı her yapılandırması için kullanmak kitaplıkları için tüm dizinleri içerdiğini doğrulayın. IDE içinde LIB değişkenini ayarla **kitaplık dizinleri** özelliği [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md). İhtiyacınız kitaplıklarını içeren tüm dizinleri, yapı her yapılandırması için burada listelenen emin olun.

Kitaplık dizinine sağlamanız gerekiyorsa, standart kitaplığı dizin geçersiz kılar, kullanabileceğiniz [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği komut satırında ya da IDE içinde kullanabileceğiniz **ek kitaplık dizinleri** bir özellik **yapılandırma özellikleri > bağlayıcı > Genel** projeniz için özellik sayfası.

Derleme yapılandırmaları için gereken kitaplığının her sürümü yüklediğinizden emin olun. Kullanmayı [vcpkg](../../vcpkg.md) paketi yükleme ve Kurulum birçok ortak kitaplıkları için otomatik hale getirmek için yönetim yardımcı programı. Şunları yapabilirsiniz, kitaplıkları gerektiren ve aynı yapılandırmaları projeniz olarak oluşturulmuş tüm yerel bağımlılıkları bulunduğundan emin olması için üçüncü taraf kitaplıkların kendi kopya oluşturmak en iyisidir.

### <a name="cannot-open-a-file-built-by-your-project"></a>Projeniz tarafından oluşturulmuş bir dosya açılamıyor

Bu hata olmadığını görebilirsiniz dosya *filename* çözümünüz tarafından oluşturulmuş ancak bağlayıcı erişmeye çalıştığında henüz yok. Bu bir proje başka bir projeye bağlıdır, ancak projeleri doğru sırada oluşturulan değil ortaya çıkar. Bu sorunu gidermek için proje başvuruları gerekmeden önce eksik dosya yerleşik böylece dosyayı kullanan projede ayarlandığından emin olun. Daha fazla bilgi için bkz: [Visual C++ projelerine başvuru ekleme](../../ide/adding-references-in-visual-cpp-projects.md) ve [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).

### <a name="cannot-open-file-cprogramobj"></a>Dosya açılamıyor ' C:\\Program.obj'

Bu hata veya sürücünüzün kökünü beklenmeyen .obj dosyasında içeren benzer bir hata görürseniz, hemen kesinlikle çift tırnak içine sarmalanmamış bir kitaplık yolu sorundur.

Komut satırı derlemeleri için bu sorunu gidermek için denetleme [/Libpath](../../build/reference/libpath-additional-libpath.md) seçenek parametreleri, LIB ortam değişkeninde belirtilen yolları ve komut satırında belirtilen yollarını ve tüm yollar etrafında çift tırnak kullandığınızdan emin olun boşluk içeren.

IDE içinde bu sorunu gidermek için denetleme **kitaplık dizinleri** özelliği [yapılandırma özellikleri > VC ++ dizinleri](../../ide/vcpp-directories-property-page.md) özellik sayfası, **ek kitaplık dizinleri** özelliğinde **yapılandırma özellikleri > bağlayıcı > Genel** özellik sayfası ve **ek bağımlılıklar** özelliğinde **yapılandırma Özellikler > bağlayıcı > giriş** projeniz için özellik sayfası. Gerekirse ihtiyacınız kitaplıklarını içeren tüm dizin yolları çift tırnak içine sarılır emin olun.

### <a name="other-common-issues"></a>Diğer ortak sorunlar

Bağlayıcı komut satırında veya kitaplık dosya adı veya yolu belirtildiği zaman bu hata oluşabilir bir [#pragma Açıklama (lib, "library_name")](../../preprocessor/comment-c-cpp.md) yönergesi hatalı olduğundan veya yol geçersiz sürücü belirtimi. Yazım denetimi ve dosya uzantısını denetleyin ve dosyanın belirtilen konumda var olduğunu doğrulayın.

Başka bir programda açık dosyayı olabilir ve bağlayıcı için yazılamıyor. Virüsten koruma programları geçici olarak genellikle yeni oluşturulan dosya erişimini engelleyin. Bu sorunu gidermek için virüsten koruma tarayıcıdan proje derleme dizinlerinizi hariç deneyin.

Paralel yapı seçeneği kullanıyorsanız, Visual Studio dosyanın başka bir iş parçacığında kilitledi mümkündür. Bu sorunu gidermek için aynı kod nesnesini veya birden çok proje kitaplığında yapı değil ve yerleşik ikili dosyalarını projenizde seçmek için yapı bağımlılıklar veya proje başvuruları kullanın doğrulayın.

Tek tek kitaplıklarda belirttiğinizde **ek bağımlılıklar** özelliği doğrudan alanları kitaplık adları, değil virgül veya noktalı ayırmak için kullanın. Kullanırsanız **Düzenle** açmak için menü öğesini **ek bağımlılıklar** iletişim kutusu, kullanım satır başı adları, değil virgül, noktalı virgül veya boşluk ayırın. Kitaplık yolları belirttiğinizde, satır başı de **kitaplık dizinleri** ve **ek kitaplık dizinleri** iletişim kutuları.

Bu hatayı görebilirsiniz zaman yolunu *filename* 260 karakterden genişletir. Gerekli dosyaları yollara kısaltmak için gerekirse, dizin yapısını yeniden veya adlarını değiştirebilirsiniz.

Dosya çok büyük olduğundan bu hata oluşabilir. Kitaplıkları veya nesne gigabayt boyutu 32-bit bağlayıcı için sorun yaratabilir fazlasını dosyaları. Bu sorunun olası bir düzeltme 64-bit araç takımı kullanmaktır. Komut satırında nasıl yapılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirmek](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). IDE içinde nasıl yapılacağı hakkında daha fazla bilgi için bkz: [kullanarak MSBuild 64 bit derleyici ve araçları ile](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) ve bu yığın taşması post: [Visual Studio yerel amd64 zincirinin kullanmak nasıl](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).

Yetersiz dosya erişim izni varsa, bu hata oluşabilir *filename*. Kitaplık dosyaları korumalı sistem dizinlerde erişmek için bir sıradan kullanıcı hesabı ve girişimi kullanın veya kendi özgün izinleri olan diğer kullanıcıların kopyalanan dosya kullanıyorsanız bu durum oluşabilir ayarlayın. Bu sorunu gidermek için dosyayı yazılabilir proje dizinine taşıyın. Dosyanın yazılabilir bir dizinde ancak erişilemez izinlerine sahip bir yönetici komut istemi kullanın ve dosya sahipliğini almak için takeown.exe komutunu çalıştırın.

Yeterli disk alanı yoksa hata oluşabilir. Bağlayıcı birkaç durumlarda geçici dosyaları kullanır. Yeterli disk alanına sahip olsa bile, çok büyük bir bağlantı deplete veya parçalara kullanılabilir disk alanı. Kullanmayı [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md) seçeneği; geçişli comdat'ı eleme okuma tüm nesne dosyaları birden çok kez bulunurken.

Varsa *filename* LNK adlı*nnn*, geçici bir dosya için bağlayıcı tarafından oluşturulan bir dosya adı olduğu, TMP ortam değişkeninde belirtilen dizin var olmayabilir, ya da birden fazla Dizin TMP ortam değişkeni için belirtilebilir. Yalnızca bir dizin yolu TMP ortam değişkeni belirtilmesi gerekir.
