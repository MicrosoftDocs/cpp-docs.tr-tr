---
title: Önemli hata C1083
ms.date: 09/01/2017
f1_keywords:
- C1083
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
ms.openlocfilehash: ae4c6a9f6c41d94aa1e36ba4a79226b49df08b49
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628013"
---
# <a name="fatal-error-c1083"></a>Önemli hata C1083

> Açılamıyor *filetype* dosya: '*dosya*': *iletisi*

Derleyici, gerektiren bir dosyayı bulamadığında C1083 hatasını oluşturur. Bu hata birçok olası nedeni vardır. Yanlış INCLUDE arama yolu veya üst bilgi dosyaları eksik veya misnamed en yaygın nedenlerini, ancak diğer dosya türleri ve sorunları C1083 da neden olabilir. Bazı neden derleyicinin bu hatayı oluşturmasının yaygın nedenlerine aşağıda verilmiştir.

## <a name="the-specified-file-name-is-wrong"></a>Belirtilen dosya adı yanlış

Dosyanın adı yanlış yazılmış olabilir. Örneğin,

`#include <algorithm.h>`

istediğiniz dosyayı bulamayabilirsiniz. Çoğu C++ Standart Kitaplığı üst bilgi dosyaları .h dosya adı uzantısına sahip değilsiniz. \<Algoritma > üst bilgi bulunamadı Bu `#include` yönergesi. Bu sorunu gidermek için doğru dosya adı, bu örnekte olduğu gibi girildiğinden emin olun:

`#include <algorithm>`

Belirli C Çalışma Zamanı Kitaplığı üstbilgileri , standart ekleme dizininin alt dizininde yer alır. Örneğin, sys/types.h dahil etmek için sistem alt dizin adını içermelidir `#include` yönergesi:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>Dosya içinde arama yoluna eklenmemiş

Derleyici tarafından belirtilen arama kurallarını kullanarak dosyayı bulamıyor bir `#include` veya `#import` yönergesi. Örneğin, ne zaman bir üst bilgi dosyası adını tırnak işaretleri içine alınır,

`#include "myincludefile.h"`

Bu, kaynak dosyasını içeren aynı dizinde dosyasını arayın ve sonra yapı ortamı tarafından belirtilen diğer konumlarda aramak için derleyiciye bildirir. Tırnak işaretleri içinde mutlak bir yol varsa, derleyici dosyayı yalnızca ilgili konumda arar. Tırnak işaretleri içinde göreli bir konum varsa, derleyici, dosyayı kaynak dizine göreli olan dizinde arar.

Ad, açılı parantezlerle ise

`#include <stdio.h>`

Derleyici yapı ortamı tarafından tanımlanan arama yolunu izler **/I** derleyici seçeneği **/X** derleyici seçeneği ve **INCLUDE** ortam değişkeni. Bir dosyayı bulmak için kullanılan arama düzeni hakkındaki özel ayrıntılar dahil olmak üzere daha fazla bilgi için bkz. [#include yönergesi (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) ve [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Dahil etme dosyaları başka bir dizindeki, kaynak dizine göreli olan ve bir göreli yol kullanın, yönergelerinde, açılı ayraçlar yerine çift tırnak işareti kullanmanız gerekir. Örneğin, üst bilgi dosyası myheader.h proje kaynaklarınız üstbilgileri adlı bir alt dizinde, ardından bu örnek dosyayı bulmak başarısız olur ve C1083 neden olur:

`#include <headers\myheader.h>`

Ancak bu örnek çalışır:

`#include "headers\myheader.h"`

Göreli yollar ekleme kodu arama yolunu dizinleri ile de kullanılabilir. Bir dizine eklerseniz **INCLUDE** ortam değişkeni veya, **ekleme dizinleri** yolu Visual Studio'da da ekleme yolunun parçası içerme yönergeleri. Örneğin, üst bilgi \path\example\headers\myheader.h bulunur ve \path\example\headers\ için ekleme, **ekleme dizinleri** yolu Visual Studio'da ancak, `#include` dosyası olarak başvurduğu yönergesi

`#include <headers\myheader.h>`

ardından dosya bulunamadı. Ekleme kodu arama yolunu içinde belirtilen dizine göreli doğru yol kullanın. Bu örnekte, \path\example için ekleme kodu arama yolunu değiştirebilirsiniz\, veya headers\ yolu segmentten `#include` yönergesi.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bu hatayı görürseniz, bir üçüncü taraf kitaplığı yapınızın bir parçası olarak yapılandırılmaya çalışılırken kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paketi yükleyip kitaplığı derleme Yöneticisi. Vcpkg destekleyen çok ve artan [üçüncü taraf kitaplıkların listesini](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derleme için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için bkz. ilgili [Visual C++ blogu](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>Projenizi, ancak ekleme kodu arama yolunu dosyasıdır

Bile, üst bilgi dosyaları içinde listelenen **Çözüm Gezgini** tarafından bunlar için listelense projenin bir parçası, dosyaları yalnızca derleyici tarafından bulunan bir `#include` veya `#import` yönerge bir kaynak dosya ve bulunan bir arama yolu içerir. Farklı türde yapılar farklı arama yolları kullanabilir. **/X** derleyici seçeneği, INCLUDE arama yolundan dizinleri dışlamak için kullanılabilir. Bu, farklı yapıların aynı ada sahip farklı ekleme dosyalarını kullanmasına, fakat farklı dizinlerde tutulmasına olanak tanır. Bu, önişlemci komutlarını kullanarak koşullu derlemeye alternatiftir. Hakkında daha fazla bilgi için **/X** derleyici seçeneği bkz [/X (Ignore Standard INCLUDE Paths)](../../build/reference/x-ignore-standard-include-paths.md).

Bu sorunu gidermek için, eklenen veya içeri aktarılan dosyayı aramak üzere derleyici tarafından kullanılan yolu düzeltin. Yeni bir proje kullanan varsayılan arama yollarını içerir. Projeniz için bir dizin eklemek için ekleme kodu arama yolunu değiştirmeniz gerekebilir. Komut satırında derleme yapıyorsanız yola ekleyin **INCLUDE** ortam değişkeni veya **/I** derleyici seçeneğini dosya yolunu belirtin.

Visual Studio'da ekleme dizini yolunu ayarlamak için projenin açın **özellik sayfaları** iletişim kutusu. Seçin **VC ++ dizinleri** altında **yapılandırma özellikleri** düzenleyin ve sol bölmedeki **ekleme dizinleri** özelliği. Visual Studio'da derleyici tarafından aranan kullanıcı başına ve her proje dizinleri hakkında daha fazla bilgi için bkz: [VC ++ Directories Property Page](../../ide/vcpp-directories-property-page.md). Hakkında daha fazla bilgi için **/I** derleyici seçeneği bkz [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md).

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>Komut satırı dahil etme veya LIB ortam ayarlanmadı

Derleyici komut satırı üzerinde çağrıldığında, ortam değişkenleri genellikle arama yollarını belirtmek için kullanılır. Tarafından açıklanan arama yolu varsa **INCLUDE** veya **LIB** ortam değişkeninin doğru şekilde ayarlanmamışsa, C1083 hatası oluşturulur. Komut satırı için temel ortamı için geliştirici komut istemi kısayolunun derlemeleri kesinlikle öneririz. Daha fazla bilgi için [derleme C/C++ komut satırında](../../build/building-on-the-command-line.md). Ortam değişkenlerini kullanma hakkında daha fazla bilgi için bkz. [nasıl yapılır: Use Environment Variables'bir derlemedeki](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).

## <a name="the-file-may-be-locked-or-in-use"></a>Dosya kilitli olabilir veya kullanımda

Düzenlemek veya dosyaya erişmek için başka bir program kullanıyorsanız, dosya kilitli olabilir. Diğer program dosyasında kapatmayı deneyin. Bazen paralel derleme seçenekleri kullanıyorsanız, diğer program Visual Studio'nun kendisine olabilir. Bu sorun ise paralel derleme seçeneğini kapatma olursa, uzaklaşıyor hata sağlar. Diğer paralel yapı sistemi, bu sorun da olabilir. Derleme sırası doğru Bu nedenle, dosya ve proje bağımlılıkları ayarlamak dikkatli olun. Bazı durumlarda, birden fazla proje tarafından oluşturulan bir ortak dosyası için derleme bağımlılık sırası zorlamak için bir ara projesi oluşturmayı düşünün. Bazen virüsten koruma programları taramak için kısa bir süre önce değiştirilen dosyalar geçici olarak kilitler. Mümkünse, Proje yapı dizinlerinizi virüsten koruma tarayıcıdan dışlamayı göz önünde bulundurun.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>Dosya adının yanlış versiyonu eklendi

C1083 hatası, dosyanın yanlış versiyonunun eklendiğini de belirtebilir. Örneğin, bir derleme olan bir dosyanın yanlış sürümünü içerebilir bir `#include` bu yapı için hazırlanmamış bir üstbilgi dosyası yönergesi. Örneğin, belirli dosyaları için x86 yalnızca uygulanabilir yapılar veya hata ayıklama yapıları için. Üstbilgi dosyası bulunamazsa derleyici C1083 hatasını oluşturur. Bu sorunu gidermek için doğru dosyayı kullanın ve yapıya üstbilgi dosyasını veya dizinini eklemeyin.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>Önceden derlenmiş üstbilgiler henüz önceden derlenmiş değil

Bir proje, önceden derlenmiş üstbilgileri kullanmak üzere yapılandırıldığında, üstbilgi içeriğini kullanan dosyaların derlenebilmesi için ilgili .pch dosyalarının oluşturulması gerekir. Örneğin, stdafx.cpp dosyası, yeni projeler için proje dizininde otomatik olarak oluşturulur. Önceden derlenmiş üstbilgi dosyalarını oluşturmak için öncelikle bu dosyayı derleyin. Tipik yapı işlemi tasarımında, bu otomatik olarak gerçekleştirilir. Daha fazla bilgi için [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md).

## <a name="additional-causes"></a>Ek nedenler

- Bir SDK ya da üçüncü taraf kitaplığı yüklediyseniz, ancak sonra SDK'ın yeni bir geliştirici komut istemi penceresi açmadıysanız veya kitaplığı yüklenir. SDK'sı veya kitaplık dosyalarına eklerse **INCLUDE** yolu, bu ortam değişkeni değişikliklerini yeni bir geliştirici komut istemi penceresi açın gerekebilir.

- Ancak derleyici seçeneği, yönetilen kod dosyasını kullanan **/CLR** belirtilmedi. Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

- Dosyayı farklı bir kullanılarak derlenmiş **/ analyze** üstbilgileri önceden derlemek için kullanılan derleyici seçeneği ayarıyla. Bir projenin üstbilgileri önceden derlenmiş, aynı tüm kullanması gereken **/ analyze** ayarları. Daha fazla bilgi için [/ analyze (kod çözümleme)](../../build/reference/analyze-code-analysis.md).

- Dosya veya dizin Linux için Windows alt sistemi tarafından oluşturulmuş, dizin başına büyük/küçük harfe duyarlılık etkin ve belirtilen durumunun bir yol veya dosya yolu veya dosyanın disk üzerinde çalışması eşleşmiyor.

- Dosya, dizin veya disk salt okunur durumdadır.

- Visual Studio veya komut satırı araçları, dosya veya dizin okumak için yeterli izinlere sahip değil. Proje dosyalarını Visual Studio veya komut satırı araçlarını çalışan işlemi daha farklı sahiplik olduğunda bu, örneğin, oluşabilir. Bazen bu sorun, Visual Studio veya Geliştirici komut istemini yönetici olarak çalıştırarak düzeltilebilir.

- Yeterli dosya tanıtıcısı yoktur. Bazı uygulamaları kapatın ve sonra yeniden derleyin. Bu normal koşullar altında olağandışı bir durumdur. Fiziksel belleğin sınırlı olduğu bir bilgisayarda büyük projeler oluşturulduğunda meydana gelebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C1083 hatasını oluşturur, üst bilgi dosyası `"test.h"` kaynak dizini veya ekleme kodu arama yolunu yok.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

IDE veya komut satırında C/C++ projeleri oluşturma hakkında daha fazla bilgi ve ortam değişkenlerini ayarlama hakkında bilgi için bkz. [C/C++ programları oluşturma](../../build/building-c-cpp-programs.md).

## <a name="see-also"></a>Ayrıca bkz.

- [MSBuild Özellikleri](/visualstudio/msbuild/msbuild-properties)
