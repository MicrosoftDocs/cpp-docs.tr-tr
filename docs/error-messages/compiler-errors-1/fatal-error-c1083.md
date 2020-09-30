---
title: Önemli hata C1083
ms.date: 09/01/2017
f1_keywords:
- C1083
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
ms.openlocfilehash: 57ae8f2d0b7f02732032151f86617498e5201c61
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509745"
---
# <a name="fatal-error-c1083"></a>Önemli hata C1083

> Dosya *türü* açılamıyor: '*Dosya*': *ileti*

Derleyici, gerektirdiği bir dosyayı bulamadığında bir C1083 hatası oluşturur. Bu hatanın birçok olası nedeni vardır. Yanlış bir içerme arama yolu veya eksik ya da yanlış adlandırılmış üst bilgi dosyaları en yaygın nedenlerdir, ancak diğer dosya türleri ve sorunlar da C1083 neden olabilir. Derleyicinin bu hatayı üretmesinin bazı yaygın nedenlerinden bazıları aşağıda verilmiştir.

## <a name="the-specified-file-name-is-wrong"></a>Belirtilen dosya adı yanlış

Dosyanın adı yanlış yazılmış olabilir. Örneğin,

`#include <algorithm.h>`

istediğiniz dosyayı bulamayabilirsiniz. Çoğu C++ standart kitaplığı üstbilgi dosyası. h dosya adı uzantısına sahip değildir. \<algorithm>Üst bilgi bu `#include` yönergeyle bulunamamıştır. Bu sorunu gidermek için, aşağıdaki örnekte olduğu gibi doğru dosya adının girildiğinden emin olun:

`#include <algorithm>`

Belirli C Çalışma Zamanı Kitaplığı üstbilgileri , standart ekleme dizininin alt dizininde yer alır. Örneğin, dahil etmek için *`sys/types.h`* *`sys`* yönergede alt dizin adını dahil etmeniz gerekir `#include` :

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>Dosya, içerme arama yoluna dahil değildir

Derleyici, veya yönergesi tarafından belirtilen arama kurallarını kullanarak dosyayı bulamaz `#include` `#import` . Örneğin, bir üst bilgi dosyası adı tırnak işaretleri içine alınır

`#include "myincludefile.h"`

Bu, derleyicinin dosyayı önce kaynak dosyayı içeren aynı dizinde bakmasını ve ardından yapı ortamı tarafından belirtilen diğer konumlara bakmasını söyler. Tırnak işaretleri içinde mutlak bir yol varsa, derleyici dosyayı yalnızca ilgili konumda arar. Tırnak işaretleri içinde göreli bir konum varsa, derleyici, dosyayı kaynak dizine göreli olan dizinde arar.

Ad açılı parantezlerle çevrelenise,

`#include <stdio.h>`

Derleyici, derleme ortamı, **`/I`** derleyici seçeneği, **`/X`** derleyici seçeneği ve **Include** ortam değişkeni tarafından tanımlanan bir arama yolunu izler. Dosya bulmak için kullanılan arama sırasına ilişkin belirli ayrıntılar dahil olmak üzere daha fazla bilgi için, bkz. [#include yönergesi (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) ve [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

İçerme dosyalarınız, kaynak dizininizle ilişkili başka bir dizinde yer alıyorsa ve dahil etme yönergelerinden göreli bir yol kullanıyorsanız, açılı ayraçlar yerine çift tırnak işareti kullanmanız gerekir. Örneğin, üst bilgi dosyanız, *`myheader.h`* üst bilgiler adlı proje kaynaklarınızın bir alt dizinindeyse, bu örnek dosyayı bulamaz ve C1083 neden olur:

`#include <headers\myheader.h>`

Ancak bu örnek şu şekilde geçerlidir:

`#include "headers\myheader.h"`

Göreli yollar Ayrıca, ekleme arama yolundaki dizinlerle birlikte kullanılabilir. **Include** ortam değişkenine veya Visual Studio 'Daki **içerme dizinleri** yolunuza bir dizin eklerseniz, yolun bir parçasını dahil etme yönergelerine de eklemeyin. Örneğin, üstbilgileriniz adresinde bulunuyorsa *`\path\example\headers\myheader.h`* ve *`\path\example\headers\`* Visual Studio 'Da **içerme dizinleri** yolunuza eklerseniz, `#include` yönerggeniz dosyayı şu şekilde gösterir:

`#include <headers\myheader.h>`

Dosya bulunamadı. Ekleme arama yolunda belirtilen dizine göre doğru yolu kullanın. Bu örnekte, arama yolunu Ekle *`\path\example\`* ' yi değiştirebilir veya *`headers\`* yönergeden yol kesimini kaldırabilirsiniz `#include` .

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve vcpkg

Derlemenizi bir parçası olarak bir üçüncü taraf kitaplığı yapılandırmaya çalışırken bu hatayı görürseniz, [`vcpkg`](../../build/vcpkg.md) kitaplığı yüklemek ve derlemek için bir C++ paket yöneticisi kullanmayı düşünün. vcpkg, [üçüncü taraf kitaplıkların](https://github.com/Microsoft/vcpkg/tree/master/ports)büyük ve artan bir listesini destekler ve projenizin bir parçası olarak başarılı derlemeler için gereken tüm yapılandırma özelliklerini ve bağımlılıklarını ayarlar.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>Dosya projenizde, ancak içerme arama yolu değil

Üst bilgi dosyaları bir projenin parçası olarak **Çözüm Gezgini** listelendiğinde bile, dosyalar yalnızca derleyici tarafından `#include` `#import` kaynak dosyadaki bir veya yönergeyle başvurulduğu zaman ve ekleme arama yolunda yer alır. Farklı türde yapılar farklı arama yolları kullanabilir. **`/X`** Derleyici seçeneği, dizinleri içerme arama yolundan dışlamak için kullanılabilir. Bu, farklı yapıların aynı ada sahip farklı ekleme dosyalarını kullanmasına, fakat farklı dizinlerde tutulmasına olanak tanır. Bu, önişlemci komutlarını kullanarak koşullu derlemeye alternatiftir. Derleyici seçeneği hakkında daha fazla bilgi için **`/X`** bkz. [ `/X` (Standart içerme yollarını yoksay)](../../build/reference/x-ignore-standard-include-paths.md).

Bu sorunu gidermek için, eklenen veya içeri aktarılan dosyayı aramak üzere derleyici tarafından kullanılan yolu düzeltin. Yeni bir proje varsayılan içerme arama yollarını kullanır. Projeniz için bir dizin eklemek üzere ekleme arama yolunu değiştirmeniz gerekebilir. Komut satırında derleme yapıyorsanız, dosyanın yolunu belirtmek için yolu **Include** ortam değişkenine veya **`/I`** derleyici seçeneğine ekleyin.

Visual Studio 'da içerme dizin yolunu ayarlamak için projenin **Özellik sayfaları** iletişim kutusunu açın. Sol bölmedeki **yapılandırma özellikleri** altında **VC + + dizinleri** ' ni seçin ve ardından **dizinleri dahil et** özelliğini düzenleyin. Visual Studio 'da derleyici tarafından aranan Kullanıcı başına ve proje başına dizinler hakkında daha fazla bilgi için bkz. [VC + + dizinleri Özellik sayfası](../../build/reference/vcpp-directories-property-page.md). Derleyici seçeneği hakkında daha fazla bilgi için **`/I`** bkz. [ `/I` (ek ekleme dizinleri)](../../build/reference/i-additional-include-directories.md).

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>Komut satırı IÇERME veya LıB ortamı ayarlanmadı

Derleyici komut satırı üzerinde çağrıldığında, ortam değişkenleri genellikle arama yollarını belirtmek için kullanılır. **Include** veya **LIB** ortam değişkeni tarafından tanımlanan arama yolu doğru ayarlanmamışsa, bir C1083 hatası oluşturulabilir. Komut satırı yapıları için temel ortamı ayarlamak üzere bir geliştirici komut istemi kısayolunun kullanılması önemle önerilir. Daha fazla bilgi için, bkz. [komut satırında C/C++ oluşturma](../../build/building-on-the-command-line.md). Ortam değişkenlerinin nasıl kullanılacağı hakkında daha fazla bilgi için bkz. [nasıl yapılır: bir derlemede ortam değişkenlerini kullanma](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).

## <a name="the-file-may-be-locked-or-in-use"></a>Dosya kilitli veya kullanımda olabilir

Dosyayı düzenlemek veya dosyaya erişmek için başka bir program kullanıyorsanız, dosya kilitli olabilir. Diğer programdaki dosyayı kapatmayı deneyin. Bazen paralel derleme seçenekleri kullanıyorsanız diğer program Visual Studio 'Nun kendisi olabilir. Paralel derleme seçeneğini devre dışı bırakırsanız, hata kaybolur ve bu sorun bu soruna neden olur. Diğer paralel derleme sistemleri de bu soruna sahip olabilir. Derleme sırasının doğru olması için dosya ve Proje bağımlılıklarını ayarlamaya dikkat edin. Bazı durumlarda, birden çok proje tarafından derlenen ortak bir dosya için derleme bağımlılığı sıralamasını zorlamak üzere bir ara proje oluşturmayı düşünün. Bazen virüsten koruma programları, son değiştirilen dosyaları tarama için geçici olarak kilitler. Mümkünse, proje yapı dizinlerinizi virüsten koruma tarayıcısı dışında bırakmayı göz önünde bulundurun.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>Dosya adının yanlış versiyonu eklendi

C1083 hatası, dosyanın yanlış versiyonunun eklendiğini de belirtebilir. Örneğin, bir derleme, `#include` Bu derleme için tasarlanmamış bir üst bilgi dosyası için bir yönergesine sahip bir dosyanın yanlış sürümünü içerebilir. Örneğin, belirli dosyalar yalnızca x86 yapılarına uygulanabilir veya derlemelerde hata ayıklaması yapılabilir. Üstbilgi dosyası bulunamazsa derleyici C1083 hatasını oluşturur. Bu sorunu gidermek için doğru dosyayı kullanın ve yapıya üstbilgi dosyasını veya dizinini eklemeyin.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>Önceden derlenmiş üstbilgiler henüz önceden derlenmiş değil

Bir proje önceden derlenmiş üstbilgileri kullanacak şekilde yapılandırıldığında, *`.pch`* üst bilgi içeriğini kullanan dosyaların derlenebilecek şekilde ilgili dosyaların oluşturulması gerekir. Örneğin, *`pch.cpp`* dosya ( *`stdafx.cpp`* Visual Studio 2017 ve önceki sürümlerde) yeni projeler için proje dizininde otomatik olarak oluşturulur. Önceden derlenmiş üstbilgi dosyalarını oluşturmak için öncelikle bu dosyayı derleyin. Tipik derleme işlemi tasarımında, bu otomatik olarak yapılır. Daha fazla bilgi için bkz. [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/creating-precompiled-header-files.md).

## <a name="additional-causes"></a>Ek nedenler

- Bir SDK veya üçüncü taraf kitaplığı yüklediniz, ancak SDK veya kitaplık yüklendikten sonra yeni bir geliştirici komut istemi penceresi açmadı. SDK veya kitaplık, **ekleme** yoluna dosya eklerse, bu ortam değişkeni değişikliklerini almak için yeni bir geliştirici komut istemi penceresi açmanız gerekebilir.

- Dosya yönetilen kodu kullanıyor, ancak derleyici seçeneği **`/clr`** belirtilmedi. Daha fazla bilgi için bkz. [ `/clr` (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

- Dosya, **`/analyze`** üstbilgileri önceden derlemek için kullanılandan farklı bir derleyici seçenek ayarı kullanılarak derlenir. Bir projenin üst bilgileri önceden derlenmiş olduğunda, hepsi aynı **`/analyze`** ayarları kullanmalıdır. Daha fazla bilgi için bkz. [ `/analyze` (kod analizi)](../../build/reference/analyze-code-analysis.md).

- Dosya veya dizin, Linux için Windows alt sistemi tarafından oluşturulmuştur, dizin başına büyük/küçük harf duyarlılığı etkindir ve bir yol veya dosyanın belirtilen durumu diskteki yol veya dosya durumuyla eşleşmez.

- Dosya, dizin veya disk salt okunur durumdadır.

- Visual Studio veya komut satırı araçları, dosyayı veya dizini okumak için yeterli izinlere sahip değil. Bu, örneğin, proje dosyalarının Visual Studio veya komut satırı araçlarının çalıştırıldığı işlemden farklı sahiplikleri olduğunda meydana gelebilir. Bazen bu sorun, Visual Studio veya geliştirici komut istemi yönetici olarak çalıştırılarak düzeltilebilir.

- Yeterli dosya tanıtıcısı yoktur. Bazı uygulamaları kapatın ve sonra yeniden derleyin. Bu normal koşullar altında olağandışı bir durumdur. Fiziksel belleğin sınırlı olduğu bir bilgisayarda büyük projeler oluşturulduğunda meydana gelebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, üstbilgi dosyası `"test.h"` kaynak dizinde yoksa veya içerme arama yolunda yoksa bir C1083 hatası oluşturur.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

IDE 'de veya komut satırında C/C++ projelerinin nasıl oluşturulacağı hakkında bilgi edinmek ve ortam değişkenlerini ayarlama hakkında bilgi için bkz. [Projeler ve derleme sistemleri](../../build/projects-and-build-systems-cpp.md).

## <a name="see-also"></a>Ayrıca bkz.

- [MSBuild özellikleri](/visualstudio/msbuild/msbuild-properties)
