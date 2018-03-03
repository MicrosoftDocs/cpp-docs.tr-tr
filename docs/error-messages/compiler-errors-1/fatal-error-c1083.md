---
title: "Önemli hata C1083 | Microsoft Docs"
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1083
dev_langs:
- C++
helpviewer_keywords:
- C1083
ms.assetid: 97e52df3-e79c-4f85-8f1e-bbd1057d55e7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd929403afc86beabf185d099a79bfab5578482a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1083"></a>Önemli hata C1083

> Açılamıyor *dosya türü* dosya: '*dosya*': *iletisi*

Bir dosya gerektiriyorsa bulamadığında derleyici C1083 hata oluşturur. Bu hatanın birçok olası nedenleri vardır. Yanlış INCLUDE arama yolu veya eksik ya da misnamed üstbilgi dosyaları en yaygın nedenlerinden, ancak diğer dosya türleri ve sorunları C1083 da neden olabilir. Bu hata neden derleyici oluşturur ortak nedenlerinden bazıları aşağıda verilmiştir.

## <a name="the-specified-file-name-is-wrong"></a>Belirtilen dosya adı yanlış

Dosyanın adı yanlış yazılmış olabilir. Örneğin,

`#include <algorithm.h>`

istediğiniz dosyayı bulamayabilirsiniz. Çoğu C++ standart kitaplık üstbilgi dosyaları bir .h dosya adı uzantısına sahip değil. \<Algoritması > üstbilgi bulunamadı Bu tarafından `#include` yönergesi. Bu sorunu gidermek için doğru dosya adı, bu örnekteki girildiğinden emin olun:

`#include <algorithm>`

Belirli C Çalışma Zamanı Kitaplığı üstbilgileri , standart ekleme dizininin alt dizininde yer alır. Örneğin, sys/types.h dahil etmek sys alt adını içermelidir `#include` yönergesi:

`#include <sys/types.h>`

## <a name="the-file-is-not-included-in-the-include-search-path"></a>Dosya Ekle arama yolunda bulunmaz

Derleyici tarafından belirtilen arama kurallarını kullanarak dosyayı bulamıyor bir `#include` veya `#import` yönergesi. Örneğin, ne zaman üstbilgi dosyası adı tırnak işaretleri içine alınır,

`#include "myincludefile.h"`

Bu kaynak dosyasını içeren aynı dizinde dosyasını arayın ve yapı ortamı tarafından belirtilen diğer konumlarda aramak için derleyici bildirir. Tırnak işaretleri içinde mutlak bir yol varsa, derleyici dosyayı yalnızca ilgili konumda arar. Tırnak işaretleri içinde göreli bir konum varsa, derleyici, dosyayı kaynak dizine göreli olan dizinde arar.

Adı açılı ayraç içine alınırsa

`#include <stdio.h>`

yapı ortamı tarafından tanımlanan bir arama yolu derleyici izleyen **/I** derleyici seçeneği **/X** derleyici seçeneği ve **INCLUDE** ortam değişkeni. Belirli bir dosyayı bulmak için kullanılan arama sırası ayrıntılarını dahil daha fazla bilgi için bkz: [#include yönergesi (C/C++)](../../preprocessor/hash-include-directive-c-cpp.md) ve [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Kaynak dizine göreli başka bir dizindeki dosyaları Ekle bulunan ve göreli bir yol kullanmak, yönergelerini, yerine köşeli çift tırnak işareti kullanın. Örneğin, üstbilgi dosyası myheader.h üstbilgileri adlı proje kaynaklarınızı alt dizininde ise, ardından bu örnek dosyayı bulmak başarısız olur ve C1083 neden olur:

`#include <headers\myheader.h>`

Ancak bu örnek çalışır:

`#include "headers\myheader.h"`

Göreli yollar ekleme arama yolu dizinleri ile de kullanılabilir. Bir dizine eklerseniz **INCLUDE** ortam değişkeni veya, **içerme dizinleri** Visual Studio'da yolu da ekleme yolun bir kısmı içerme yönergeleri. Örneğin, üstbilgi \path\example\headers\myheader.h bulunur ve \path\example\headers\ için eklerseniz, **içerme dizinleri** yol Visual Studio'da ancak, `#include` dosyası olarak başvurduğu yönergesi

`#include <headers\myheader.h>`

ardından dosyası bulunamadı. INCLUDE arama yolunda belirtilen dizine göreli doğru yol kullanın. Bu örnekte, \path\example için Include arama yolu değişebilir\, headers\ yol kesimi öğesinden Kaldır `#include` yönergesi.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bir üçüncü taraf kitaplık yapınızın bir parçası yapılandırmak çalışırken bu hatayı görürseniz, kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paket yüklemek ve kitaplık yapı yöneticisi,. Büyük ve artan Vcpkg desteklemektedir [üçüncü taraf kitaplıkların bir listesi](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derlemeler için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için ilgili bkz [Visual C++ Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="the-file-is-in-your-project-but-not-the-include-search-path"></a>Projeniz, ancak INCLUDE arama yolu dosyasıdır

Bile zaman üstbilgi dosyaları listelenen **Çözüm Gezgini** tarafından bunlar için adlandırılır olduğunda bir projenin bir parçası, dosyaları yalnızca derleyici tarafından bulunan bir `#include` veya `#import` kaynağındaki yönerge dosya ve bulunan bir arama yolu içerir. Farklı türde yapılar farklı arama yolları kullanabilir. **/X** derleyici seçeneği, dizinleri INCLUDE arama yolundan hariç tutmak için kullanılabilir. Bu, farklı yapıların aynı ada sahip farklı ekleme dosyalarını kullanmasına, fakat farklı dizinlerde tutulmasına olanak tanır. Bu, önişlemci komutlarını kullanarak koşullu derlemeye alternatiftir. Hakkında daha fazla bilgi için **/X** derleyici seçeneği bkz [/X (Yoksay standart yol eklemeyi)](../../build/reference/x-ignore-standard-include-paths.md).

Bu sorunu gidermek için, eklenen veya içeri aktarılan dosyayı aramak üzere derleyici tarafından kullanılan yolu düzeltin. Yeni bir proje kullandığı varsayılan arama yolları içerir. Projeniz için bir dizin eklemek için Ekle arama yolu değiştirmek zorunda kalabilirsiniz. Komut satırında derleme, yoluna ekleyin **Ekle** ortam değişkeni veya **/I** derleyici seçeneği dosyasının yolunu belirtin.

Visual Studio'da INCLUDE dizin yolu ayarlamak için projenin açmak **özellik sayfaları** iletişim kutusu. Seçin **VC ++ dizinleri** altında **yapılandırma özellikleri** sol bölmesinde ve ardından düzenleyin **içerme dizinleri** özelliği. Visual Studio'da derleyici tarafından aranan kullanıcı başına ve proje başına dizinleri hakkında daha fazla bilgi için bkz: [VC ++ dizinleri özellik sayfası](../../ide/vcpp-directories-property-page.md). Hakkında daha fazla bilgi için **/I** derleyici seçeneği bkz [/ı (ek içeren dizinler)](../../build/reference/i-additional-include-directories.md).

## <a name="the-command-line-include-or-lib-environment-is-not-set"></a>Komut satırı Ekle veya LIB ortam ayarlanmadı

Derleyici komut satırı üzerinde çağrıldığında, ortam değişkenleri genellikle arama yollarını belirtmek için kullanılır. Arama yolu tarafından açıklanan varsa **INCLUDE** veya **LIB** ortam değişkeni doğru ayarlanmadı, C1083 hata oluşturulabilir. Komut satırı temel ortamını ayarlamak için geliştirici komut istemi kısayolunu kullanarak yapılar önerilir. Daha fazla bilgi için bkz: [yapı C/C++ komut satırında](../../build/building-on-the-command-line.md). Ortam değişkenlerini kullanma hakkında daha fazla bilgi için bkz: [nasıl yapılır: bir derlemede ortam değişkenlerini kullanın](/visualstudio/msbuild/how-to-use-environment-variables-in-a-build).

## <a name="the-file-may-be-locked-or-in-use"></a>Dosyanın kilitli veya kullanımda

Düzenlemek veya dosyaya erişim için başka bir program kullanıyorsanız, dosyanın kilitli olabilir. Diğer program dosyasında kapatmayı deneyin. Bazen paralel derleme seçenekleri kullanıyorsanız, diğer program Visual Studio'nun kendisine olabilir. Sorunun bu olup sonra paralel yapı seçeneğini kapatma, azalttıktan hata yapar. Diğer paralel yapı sistemleri de bu sorun olabilir. Dosya ve proje bağımlılıkları derleme sırası doğru şekilde ayarlama konusunda dikkatli olun. Bazı durumlarda, birden çok proje tarafından oluşturulan ortak bir dosya için derleme bağımlılık sırası zorlamak için bir ara projesi oluşturmayı düşünün. Bazen virüsten koruma programları tarama için son değişen dosyaları geçici olarak kilitleyebilirsiniz. Mümkünse, proje derleme dizinlerinizi virüsten koruma tarayıcıdan hariç tutmayı düşünebilirsiniz.

## <a name="the-wrong-version-of-a-file-name-is-included"></a>Dosya adının yanlış versiyonu eklendi

C1083 hatası, dosyanın yanlış versiyonunun eklendiğini de belirtebilir. Örneğin, bir derleme sahip bir dosya yanlış sürümünü içerebilir bir `#include` değil kullanılmaya üstbilgi dosyası bu derleme için yönerge. Örneğin, belirli dosyaları x86 için yalnızca uygulanabilir yapılar veya hata ayıklama yapıları için. Üstbilgi dosyası bulunamazsa derleyici C1083 hatasını oluşturur. Bu sorunu gidermek için doğru dosyayı kullanın ve yapıya üstbilgi dosyasını veya dizinini eklemeyin.

## <a name="the-precompiled-headers-are-not-yet-precompiled"></a>Önceden derlenmiş üstbilgiler henüz önceden derlenmiş değil

Bir proje, önceden derlenmiş üstbilgileri kullanmak üzere yapılandırıldığında, üstbilgi içeriğini kullanan dosyaların derlenebilmesi için ilgili .pch dosyalarının oluşturulması gerekir. Örneğin, stdafx.cpp dosyası yeni projeler için proje dizininde otomatik olarak oluşturulur. Önceden derlenmiş üstbilgi dosyalarını oluşturmak için öncelikle bu dosyayı derleyin. Genel derleme işlemi tasarımında, bu otomatik olarak gerçekleştirilir. Daha fazla bilgi için bkz: [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md).

## <a name="additional-causes"></a>Ek nedenler

- Bir SDK veya üçüncü taraf kitaplık yüklediyseniz ancak SDK sonra yeni bir geliştirici komut istemi penceresi açmadıysanız veya kitaplığı yüklenir. SDK veya kitaplık dosyalarını eklerse **INCLUDE** yolu, bu ortam değişkeni değişiklikleri almak için yeni bir geliştirici komut istemi penceresi açın gerekebilir.

- Derleyici seçeneği ancak yönetilen kod dosyası kullanır **/CLR** belirtilmedi. Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

- Farklı bir kullanarak derlenmiş dosyası **/ analyze** üstbilgileri derleneceği halinden derleyici seçeneği ayarı. Bir proje için üstbilgileri önceden derlenmiş, tümü aynı kullanmalıdır **/ analyze** ayarlar. Daha fazla bilgi için bkz: [/ analyze (kod çözümleme)](../../build/reference/analyze-code-analysis.md).

- Dosya, dizin veya disk salt okunur durumdadır.

- Visual Studio ya da komut satırı araçlarını dosya veya dizin okumak için yeterli izinlere sahip değil. Proje dosyalarını Visual Studio veya komut satırı araçlarını çalışan işlem'den farklı sahipliğine Bu, örneğin, ortaya çıkar. Bazen Geliştirici komut istemi veya Visual Studio'yu yönetici olarak çalıştırarak bu sorun çözülebilir.

- Yeterli dosya tanıtıcısı yoktur. Bazı uygulamaları kapatın ve sonra yeniden derleyin. Bu normal koşullar altında olağandışı bir durumdur. Fiziksel belleğin sınırlı olduğu bir bilgisayarda büyük projeler oluşturulduğunda meydana gelebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir C1083 hatası oluşturur, üst bilgi dosyasını `"test.h"` kaynak dizin veya INCLUDE arama yolu yok.

```cpp
// C1083.cpp
// compile with: /c
#include "test.h"   // C1083 test.h does not exist
#include "stdio.h"  // OK
```

IDE veya komut satırında C/C++ projeleri oluşturma hakkında bilgi ve ortam değişkenlerini ayarlama hakkında daha fazla bilgi için bkz: [C/C++ programları oluşturma](../../build/building-c-cpp-programs.md).

## <a name="see-also"></a>Ayrıca bkz.

[MSBuild Özellikleri](/visualstudio/msbuild/msbuild-properties)