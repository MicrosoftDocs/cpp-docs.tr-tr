---
title: "Bağlayıcı araçları hatası LNK1104 | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1104
dev_langs: C++
helpviewer_keywords: LNK1104
ms.assetid: 9ca6f929-0efc-4055-8354-3cf5b4e636dc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebc0b23a7d92c94373b9ae5be01a0ef50476e433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1104"></a>Bağlayıcı Araçları Hatası LNK1104
Dosya açılamıyor '*filename*'  
  
Bağlayıcı, belirtilen dosya açılamadı.  
  
## <a name="possible-causes-and-solutions"></a>Olası nedenler ve çözümler
  
Bağlayıcı için okuma veya yazma için bir dosyayı açmaya çalıştığında bu hata oluşabilir. Bu sorunu en sık karşılaşılan nedenleri şunlardır: dosya yok, dizinleri birinde bağlayıcı bulunamıyor arar, veya kullanımda ve başka bir işlem tarafından kilitlenmiş. Daha az yaygın olarak, disk alanı yetersiz çalışabilir dosya çok büyük olabilir dosyasının yolu çok uzun olabilir veya dosyaya erişim izniniz olmayabilir.  

Bu ortak sorunları biri için denetleyin:  

-   Bunu yeniden denediğinizde, uygulamanızın zaten çalışıyor. Açılamıyor dosyası yürütülebilir dosya veya bir .pdb gibi hata ayıklama dosyası ise, ortak bir nedeni budur. Bu sorunu gidermek için program durdurun ve yeniden oluşturmadan önce hata ayıklayıcı'dan kaldırın.  
  
-   Dosya *filename* çözümünüz tarafından oluşturulmuş ancak bağlayıcı erişmeye çalıştığında henüz yok. Bu dosyayı oluşturmak için başka bir projeye bir proje bağlıdır, ancak projeleri doğru sırada oluşturulan değil Bu durum oluşabilir. Bu sorunu gidermek için proje başvuruları gerekmeden önce eksik dosya yerleşik böylece dosyayı kullanan projede ayarlandığından emin olun. Daha fazla bilgi için bkz: [Visual C++ projelerine başvuru ekleme](../../ide/adding-references-in-visual-cpp-projects.md) ve [bir projedeki başvuruları yönetme](/visualstudio/ide/managing-references-in-a-project).  
  
-   Dosya adı veya yolu komut satırında veya #pragma lib yönergesinde belirtilen yanlış veya yolun bir Geçersiz sürücü belirtimi içeriyor. Yazım denetimi yapın ve dosyanın belirtilen konumda var olduğunu doğrulayın.  
  
-   Başka bir bilgisayardan kopyaladığınız bir proje oluşturmak için Visual Studio IDE kullanıyorsanız, kitaplıkları için yükleme konumlarını farklı olabilir. Kitaplık dizinleri özelliğini kontrol [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) ve gerekirse güncelleştirin. Bakın ve IDE içinde ayarlama geçerli kitaplık yolları düzenlemek için kitaplık dizinleri özelliği için aşağı açılır denetimin seçin ve Seç **Düzenle**. **Değeri hesaplanan** kitaplık dizinleri iletişim bölümünü kitaplık dosyaları için arama geçerli yolları listeler.  
  
-   Visual Studio'nun daha eski bir sürümü kullanılarak oluşturulmuş bir proje oluşturuyorsanız, bu sürüm için kitaplıkları ve platform araç takımı değil yüklenmemiş olabilir. Bu sorunu gidermek için iki seçeneğiniz vardır: yüklü olan geçerli platform araç takımı kullanmak için proje yükseltebilir veya daha eski araç takımı yükleyebilir ve değişmeden projeyi oluşturun. Daha fazla bilgi için bkz: [önceki sürümleri, Visual C++ projeleri yükseltme](../../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md) ve [yerel çoklu sürüm desteği eski projeler derlemek için Visual Studio'da kullanın](../../porting/use-native-multi-targeting.md).
  
-   Geçerli proje yapılandırması veya platform araç takımı için kitaplıkları yüklü değil. Windows SDK ve platform araç takımı içinde belirttiğinizi doğrulayın [genel özellik sayfası](../../ide/general-property-page-project.md) projeniz için yüklü olduğundan ve gerekli kitaplıkları Belirtilen kitaplık dizinleri kullanılabilir olduğundan emin olun [ VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) yapılandırma ayarlarınızı için. Hata ayıklama ve perakende yapılandırmaları için ayrı ayarlar vardır, bir derleme çalışır, ancak başka bir hataya neden olur, böylece ayarlarının doğru olduğundan ve her iki yapılandırma için gereken Araçlar ve kitaplıkları yüklü emin olun.  
  
-   Windows SDK yolunu güncel değil. Visual Studio sürümünüz yeni olan Windows SDK'sı sürümünü yüklediyseniz, yolları içinde belirttiğinizden emin olun. [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md) yeni SDK eşleşecek şekilde güncelleştirilir. Geliştirici komut istemi kullanırsanız, ortam değişkenleri başlatır toplu iş dosyasını yeni SDK yollar için güncelleştirildiğinden emin olun.  
  
-   Başka bir programda açık dosyayı olabilir ve bağlayıcı için yazılamıyor. Virüsten koruma programları geçici olarak genellikle yeni oluşturulan dosya erişimini engelleyin. Bu sorunu gidermek için virüsten koruma tarayıcıdan proje derleme dizinlerinizi hariç deneyin.  
  
-   Paralel yapı seçeneği kullanıyorsanız, Visual Studio dosyanın başka bir iş parçacığında kilitledi mümkündür. Bu sorunu gidermek için aynı kod nesnesini veya birden çok proje kitaplığında yapı değil ve yerleşik ikili dosyalarını projenizde seçmek için yapı bağımlılıklar veya proje başvuruları kullanın doğrulayın.  
  
-   Yanlış bir LIB ortam değişkeni var. Komut satırı derlemelerde LIB ortam değişkeni ayarlanır ve kullandığınız kitaplıkları için tüm dizinleri içerdiğini doğrulayın. IDE içinde LIB değişkeni kitaplık dizinleri özelliği tarafından ayarlanan [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md). Tüm ihtiyacınız kitaplıklarını içeren dizinleri burada listelenen olduğundan emin olun. Kitaplık dizinine sağlamanız gerekiyorsa, standart kitaplığı dizin geçersiz kılar, kullanabileceğiniz [/Libpath](../../build/reference/libpath-additional-libpath.md)) komut satırı veya projeniz için bağlayıcı özellik sayfası ek kitaplık dizinleri özelliğinde seçeneği.  
  
-   Tek tek kitaplıklarda bir projenin özellik sayfaları iletişim kutusunda belirtirken, kitaplık adları boşluklarla değil virgülle ayrılmış olması gerekir.  
  
-   Yolu *filename* 260 karakterden genişletir. Gerekli dosyaları yollara kısaltmak için gerekirse, dizin yapısını yeniden veya adlarını değiştirebilirsiniz.  
  
-   Dosya çok büyük. Kitaplıkları veya nesne gigabayt boyutu 32-bit bağlayıcı için sorun yaratabilir fazlasını dosyaları. Bu sorunun olası bir düzeltme 64-bit araç takımı kullanmaktır. Komut satırında nasıl yapılacağı hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir 64 Bit Visual C++ araç takımını komut satırında etkinleştirmek](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md). IDE içinde nasıl yapılacağı hakkında daha fazla bilgi için bkz: [kullanarak MSBuild 64 bit derleyici ve araçları ile](../../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md#using-msbuild-to-build-your-project) ve bu yığın taşması post: [Visual Studio yerel amd64 zincirinin kullanmak nasıl](http://stackoverflow.com/questions/19820718/how-to-make-visual-studio-use-the-native-amd64-toolchain/23793055).  
  
-   Yetersiz dosya erişim iznine sahip *filename*. Bu kitaplık dosyaları korumalı sistem dizinlerde erişmek veya kendi özgün izinleri olan diğer kullanıcıların kopyalanan dosya halinde gerçekleşebilir ayarlayın. Bu sorunu gidermek için dosyayı yazılabilir proje dizinine taşıyın. Dosyanın yazılabilir bir dizinde ancak erişilemez izinlerine sahip bir yönetici komut istemi kullanın ve dosya sahipliğini almak için takeown.exe komutunu çalıştırın.  
  
-   Yeterli disk alanı yok. Bağlayıcı birkaç durumlarda geçici dosyaları kullanır. Yeterli disk alanına sahip olsa bile, çok büyük bir bağlantı deplete veya parçalara kullanılabilir disk alanı. Kullanmayı [OPT (iyileştirmeler)](../../build/reference/opt-optimizations.md) seçeneği; geçişli comdat'ı eleme okuma tüm nesne dosyaları birden çok kez bulunurken.  
  
-   Varsa *filename* LNK adlı*n*, geçici bir dosya için bağlayıcı tarafından oluşturulan bir dosya adı olduğu, TMP ortam değişkeninde belirtilen dizin var olmayabilir, ya da birden fazla Dizin TMP ortam değişkeni için belirtilebilir. Yalnızca bir dizin yolu TMP ortam değişkeni belirtilmesi gerekir.  
  
-   Hata iletisi için bir kitaplık adı oluşur ve bir önceki Microsoft Visual C++ geliştirme sistemi .mak dosyasından son bağlantı noktası kurulmuş, kitaplık artık geçerli olmayabilir. Kitaplık adı doğru olduğundan ve hala belirtilen konumda bulunduğundan emin olun veya yeni bir konuma LIB yolunu güncelleştirin.  
