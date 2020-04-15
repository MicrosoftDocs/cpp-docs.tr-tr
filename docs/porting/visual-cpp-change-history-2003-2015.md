---
title: Visual C++ değişiklik geçmişi 2003 - 2015
ms.date: 10/21/2019
helpviewer_keywords:
- breaking changes [C++]
ms.assetid: b38385a9-a483-4de9-99a6-797488bc5110
ms.openlocfilehash: a045b04e5a57e9963b2ad374fbdfdd533bde0a05
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374162"
---
# <a name="visual-c-change-history-2003---2015"></a>Visual C++ değişiklik geçmişi 2003 - 2015

Bu makalede Visual Studio 2015'ten Visual Studio 2003'e kadar olan tüm kırılma değişiklikleri açıklanmaktadır ve bu makalede "yeni davranış" veya "şimdi" terimleri Visual Studio 2015 ve sonrası terimlerini ifade eder. "Eski davranış" ve "önce" terimleri Visual Studio 2013 ve önceki sürümlere atıfta bulunur.

Visual Studio'nun en son sürümü hakkında bilgi için Visual [Studio'da Visual C++ için yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md) ve [Visual Studio'da Visual C++'da Uyumluluk Geliştirmeleri](../overview/cpp-conformance-improvements.md)bölümüne bakın.

> [!NOTE]
> Visual Studio 2015 ile Visual Studio 2017 arasında ikili kırılma yoktur.

Visual Studio'nun yeni bir sürümüne yükselttiğinde, daha önce derlenmiş ve doğru çalışan kodda derleme ve/veya çalışma zamanı hatalarıyla karşılaşabilirsiniz. Bu tür sorunlara neden olan yeni sürümdeki *değişiklikler, değişiklikleri kırma*olarak bilinir ve genellikle C++ dil standardında, işlev imzalarında veya bellekteki nesnelerin düzenindeki değişiklikler tarafından gereklidir.

Algılatılması ve tanısı zor olan çalışma zamanı hatalarını önlemek için, derleyicinin farklı bir sürümünü kullanarak derlenen ikililere hiçbir zaman statik olarak bağlanmamamanızı öneririz. Ayrıca, bir EXE veya DLL projesini yükseltirken, bağlantı verdiği kitaplıkları da yükselttiğinizden emin olun. Derleyicinin farklı sürümlerini kullanarak derlenen DL'ler de dahil olmak üzere ikililer arasında CRT (C Runtime) veya C++ Standart Kitaplığı (C++ Standart Kitaplığı) türlerini geçmeyin. Daha fazla bilgi için [bkz.](../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md)

COM arabirimi veya POD nesnesi olmayan bir nesne için belirli bir düzene bağlı kod asla yazmamalısınız. Bu tür bir kod yazarsanız, yükseltme sonrasında çalışmasını sağlamalısınız. Daha fazla bilgi için ABI [Sınırlarında Taşınabilirlik'e](../cpp/portability-at-abi-boundaries-modern-cpp.md)bakın.

Ayrıca, derleyici uygunluğu için devam eden geliştirmeler bazen derleyicinin varolan kaynak kodunuzu nasıl anladığını değiştirebilir. Örneğin, yapınız sırasında yeni veya farklı hatalar, hatta daha önce oluşturulmuş ve doğru şekilde çalışan koddaki davranış farklılıkları bulabilirsiniz. Bu geliştirmeler, bu belgede tartışılanlar gibi değişiklikleri kırmasa da, bu sorunları gidermek için kaynak kodunuzda değişiklik yapmanız gerekebilir:

- [C Çalışma Zamanı (CRT) Kitaplığı Son Kesme Değişiklikleri](#BK_CRT)

- [Standart C++ ve C++ Standart Kitaplık Son Dakika Değişiklikleri](#BK_STL)

- [MFC ve ATL Breaking Değişiklikler](#BK_MFC)

- [Eşzamanlılık Çalışma Zamanı Son Kesme Değişiklikleri](#BK_ConcRT)

## <a name="visual-studio-2015-conformance-changes"></a><a name="VC_2015"></a>Visual Studio 2015 Uygunluk Değişiklikleri

### <a name="c-runtime-library-crt"></a><a name="BK_CRT"></a>C Çalışma Zamanı Kitaplığı (CRT)

#### <a name="general-changes"></a>Genel Değişiklikler

- **Refactored ikili**

   CRT Kitaplığı iki farklı ikiliye dönüştürülür: standart işlevselliğin çoğunu içeren Evrensel CRT (ucrtbase) ve VC Çalışma Zamanı Kitaplığı (vcruntime). Vcruntime kitaplığı, özel durum işleme ve içsel lik gibi derleyiciyle ilgili işlevleri içerir. Varsayılan proje ayarlarını kullanıyorsanız, bağlayıcı yeni varsayılan kitaplıkları otomatik olarak kullanacağından bu değişiklik sizi etkilemez. Projenin **Bağlayıcı** özelliğini Tüm Varsayılan Kitaplıkları **Evet** **olarak yoksay'a** ayarladıysanız veya komut satırındaki `/NODEFAULTLIB` bağlayıcı seçeneğini kullanıyorsanız, kitaplık listenizi **(Ek Bağımlılıklar** özelliğinde) yeni, yeniden faktörlü kitaplıkları içerecek şekilde güncelleştirmeniz gerekir. Eski CRT kitaplığını (libcmt.lib, libcmtd.lib, msvcrt.lib, msvcrtd.lib) eşdeğer refactored kitaplıklarıyla değiştirin. Yeniden düzenleme yapılan iki kitaplıktan her biri için statik (.lib) ve dinamik (.dll) sürüm (sonek olmadan) ve hata ayıklama sürümleri ("d" soneki yle) vardır. Dinamik sürümler, bağlantı kurabileceğiniz bir alma kitaplığına sahiptir. İki refactored kütüphaneler Evrensel CRT, özellikle ucrtbase.dll veya ucrtbase.lib, ucrtbased.dll veya ucrtbased.lib ve VC runtime kütüphane, libvcruntime.lib, vcruntime*sürümü*.dll, libvcruntimed.lib ve vcruntimed*sürümü*.dll vardır . Visual Studio 2015 ve Visual Studio 2017 *sürümü* 140'tır. [Bkz. CRT Kitaplık Özellikleri.](../c-runtime-library/crt-library-features.md)

#### <a name="localeh"></a>\<locale.h>

- **localeconv**

   Locale.h'de bildirilen [localeconv](../c-runtime-library/reference/localeconv.md) işlevi, [iş parçacığı başına yerel etkinlik](../parallel/multithreading-and-locales.md) etkinleştirildiğinde artık doğru şekilde çalışır. Kitaplığın önceki sürümlerinde, bu işlev `lconv` iş parçacığının yerel değil, genel yerel aserin verilerini döndürecek.

   İş parçacığı başına yerel eşler kullanıyorsanız, `localeconv`''yi' kullanımınız kontrol etmelisiniz. Kodunuz döndürülen `lconv` verilerin genel yerel alan için olduğunu varsalarsa, bunu düzeltmeniz gerekir.

#### <a name="mathh"></a>\<math.h>

- **C++ matematik kitaplığı işlevlerinin aşırı yükleri**

   Önceki sürümlerde \<math.h>, C++'ın matematik kitaplığı işlevleri için aşırı yüklemelerinin bazılarını, ancak tümlerini tanımlamamıştır. Aşırı yüklerin geri kalanı \<cmath> başlığındaydı. Yalnızca \<math.h> içeren kod işlev aşırı yük çözümü ile ilgili sorunlar olabilir. C++ aşırı \<yükleri math.h> kaldırıldı ve yalnızca \<cmath> bulunur.

   Hataları gidermek için, \< \<math.h> kaldırılan işlevlerin bildirimleri almak için cmath> içerir. Bu işlevler taşındı:

  - `double abs(double)` ve `float abs(float)`

  - `double pow(double, int)`, `float pow(float, float)`, `float pow(float, int)`, `long double pow(long double, long double)`, `long double pow(long double, int)`

  - `float`ve `long double` yüzer nokta `acos`fonksiyonlarısürümleri `asinh`, `atan` `atanh`, `atan2` `cbrt` `ceil` `copysign` `cos` `cosh` `erf` `erfc` `exp` `exp2` `expm1` `fabs` `fdim` `floor` `fma`, `fmax`, , , `fmin` `fmod` `frexp` `hypot` `ilogb` `ldexp` `lgamma` `llrint` `llround` `log` `log10` `log1p` `log2` `lrint` `lround`, , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , `modf` `nearbyint` `nextafter` `nexttoward` `remainder` `remquo` `rint` `round` `scalbln` `scalbn` `sin` `sinh` `sqrt` `tan` `tanh` `tgamma` `asin` `acosh``trunc`

  Yalnızca \<math.h `abs`> üstbilgisini içeren kayan nokta türüyle kullanan kodunuz varsa, kayan nokta sürümleri artık kullanılamaz. Arama şimdi hata `abs(int)`üreten bir kayan nokta bağımsız değişkeni bile, giderir:

    ```Output
    warning C4244: 'argument' : conversion from 'float' to 'int', possible loss of data
    ```

  Bu uyarı için düzeltme, çift `abs` bağımsız `abs`değişken veya `fabs` `fabsf` float bağımsız değişkeni gibi kayan bir nokta sürümü \<ile arama değiştirmek veya `abs`cmath> üstbilgi dahil ve kullanmaya devam etmektir.

- **Kayan nokta uygunluğu**

   Matematik kitaplığında, NIn'ler ve sonsuzluklar gibi özel durum girdileri ile ilgili Olarak IEEE-754 ve C11 Ek F spesifikasyonlarına uygunluğu iyileştirmek için birçok değişiklik yapılmıştır. Örneğin, genellikle kitaplığın önceki sürümlerinde hata olarak kabul edilen sessiz NaN girişleri artık hata olarak kabul edilmez. [C11 Standardının](https://www.iso.org/standard/57853.html) [IEEE 754 Standardı](https://standards.ieee.org/standard/754-2008.html) ve Ek F'si bölümüne bakınız.

   Bu değişiklikler derleme zamanı hatalarına neden olmaz, ancak programların standarda göre daha farklı ve daha doğru davranmasına neden olabilir.

- **FLT_ROUNDS**

   Visual Studio 2013'te, FLT_ROUNDS makrosu sabit bir ifadeye genişledi, bu da hatalıydı çünkü yuvarlama modu çalışma zamanında ,örneğin fesetround'u arayarak yapılandırılabilir. FLT_ROUNDS makro su anda dinamiktir ve geçerli yuvarlama modunu doğru bir şekilde yansıtır.

#### <a name="new-and-newh"></a>\<yeni> \<ve new.h>

- **yeni ve silme**

   Kitaplığın önceki sürümlerinde, uygulama tanımlı işleç yeni ve silme işlevleri çalışma zamanı dll kitaplığından dışa aktarıldı (örneğin, msvcr120.dll). Bu işleç işlevleri artık çalışma zamanı kitaplığı DL'leri kullanırken bile ikililerinize statik olarak bağlanır.

   Bu, yerel veya karma kod için`/clr`bir son dakika değişikliği değildir ( ), ancak [/clr:pure](../build/reference/clr-common-language-runtime-compilation.md)olarak derlenen kod için, bu değişiklik kodunuzu derlemek için başarısız neden olabilir. Kodu olarak `/clr:pure`derlerseniz, bu değişiklik `#include <new>` `#include <new.h>` nedeniyle yapı hataları eklemeniz veya bunları çözmeniz gerekebilir. Bu`/clr:pure` seçenek Visual Studio 2015'te küçümser ve Visual Studio 2017'de desteklenmez. "Saf" olması gereken kod C#'a taşınabilir.

#### <a name="processh"></a>\<process.h>

- **_beginthread ve _beginthreadex**

   [_beginthread](../c-runtime-library/reference/beginthread-beginthreadex.md) ve [_beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md) işlevleri artık iş parçacığı yordamının iş parçacığı süresince tanımlandığı modüle bir başvuru tutar. Bu, bir iş parçacığı tamamlanana kadar modüllerin kaldırılmamasını sağlamaya yardımcı olur.

#### <a name="stdargh"></a>\<stdarg.h>

- **va_start ve başvuru türleri**

   C++ kodunu derlerken, [va_start](../c-runtime-library/reference/va-arg-va-copy-va-end-va-start.md) şimdi derleme zamanında bağımsız değişkenin başvuru türünden olmadığını doğrular. Başvuru türü bağımsız değişkenler C++ Standardı tarafından yasaklanır.

#### <a name="stdioh-and-conioh"></a><a name="stdio_and_conio"></a>\<stdio.h> \<ve conio.h>

- **Printf ve scanf işlev ailesi artık satır içi olarak tanımlanır.**

   Tüm `printf` ve `scanf` işlevlerin tanımları stdio.h \<>, \<conio.h> ve diğer CRT üstbilgilerine göre sıralı olarak taşınmıştır. Bu kesme değişikliği, uygun CRT üstbilgilerini dahil etmeden bu işlevleri yerel olarak bildiren programlar için bir bağlayıcı hatasına (LNK2019, çözülmemiş dış simge) yol açar. Mümkünse, kodu CRT üstbilgilerini (diğer bir deyişle `#include <stdio.h>`ekle) ve satır ara işlevlerini içerecek şekilde güncelleştirmeniz gerekir, ancak kodunuzu bu üstbilgi dosyalarını içerecek şekilde değiştirmek istemiyorsanız, alternatif bir çözüm bağlantı bağlayıcı girişinize ek bir kitaplık eklemektir, legacy_stdio_definitions.lib.

   Bu kitaplığı IDE'deki bağlayıcı girişinize eklemek için, proje düğümü için bağlam menüsünü açın, **Özellikler'i**seçin, ardından **Project Properties** iletişim kutusunda `legacy_stdio_definitions.lib` **Bağlayıcı'yı**seçin ve yarı nokta noktalı ayrılmış listeye eklemek için **Bağlayıcı Girişi'ni** edin.

   Projeniz Visual Studio'nun 2015'ten önce yayımlanmış bir sürümüyle derlenen statik kitaplıklarla bağlantı kurabilirse, bağlantı cı, çözümlenmemiş bir dış simge bildirebilir. Bu hatalar _imp_\*şeklinde `_iob`belirli `_iob_func` \<stdio.h> işlevleri için , veya ilgili içe alma için iç tanımlar referans olabilir. Microsoft, bir projeyi yükselttirirken tüm statik kitaplıkları C++ derleyicisinin ve kitaplıkların en son sürümüyle yeniden derlemenizi önerir. Kitaplık, kaynağın kullanılamadığı bir üçüncü taraf kitaplığıysa, üçüncü taraftan güncelleştirilmiş bir ikili istemeli veya bu kitaplığı kullanımınızı derleyici nin ve kitaplıkların eski sürümüyle derlediğiniz ayrı bir DLL'ye kapsüllemeniz gerekir.

    > [!WARNING]
    > Windows SDK 8.1 veya daha önce bağlantı kuruyorsanız, bu çözülmemiş dış simge hatalarıyla karşılaşabilirsiniz. Bu durumda, daha önce açıklandığı gibi bağlayıcı girişine legacy_stdio_definitions.lib ekleyerek hatayı gidermelisiniz.

   Çözülmemiş sembol hatalarını gidermek için, ikili olarak tanımlanan simgeleri incelemek için [dumpbin.exe'yi](../build/reference/dumpbin-reference.md) kullanmayı deneyebilirsiniz. Kitaplıkta tanımlanan simgeleri görüntülemek için aşağıdaki komut satırını deneyin.

    ```cpp
    dumpbin.exe /LINKERMEMBER somelibrary.lib
    ```

- **alır ve _getws**

   [Alır](../c-runtime-library/gets-getws.md) ve [_getws](../c-runtime-library/gets-getws.md) işlevleri kaldırıldı. Gets işlevi, güvenli bir şekilde kullanılamadığı için C11'deki C Standart Kitaplığı'ndan kaldırıldı. _getws işlevi alır eşdeğer ama geniş dizeleri için bir Microsoft uzantısı oldu. Bu fonksiyonlara alternatif olarak, [fgets,](../c-runtime-library/reference/fgets-fgetws.md) [fgetws,](../c-runtime-library/reference/fgets-fgetws.md) [gets_s](../c-runtime-library/reference/gets-s-getws-s.md)ve [_getws_s](../c-runtime-library/reference/gets-s-getws-s.md)kullanımını düşünün.

- **_cgets ve _cgetws**

   [_cgets](../c-runtime-library/cgets-cgetws.md) ve [_cgetws](../c-runtime-library/cgets-cgetws.md) işlevleri kaldırıldı. Bu fonksiyonlara alternatif olarak, [_cgets_s](../c-runtime-library/reference/cgets-s-cgetws-s.md) ve [_cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)kullanmayı düşünün.

- **Sonsuzluk ve NaN Biçimlendirme**

   Önceki sürümlerde, sonsuzluklar ve NAN'lar MSVC'ye özgü sentinel dizeleri kümesi kullanılarak biçimlendirilirdi.

  - Sonsuzluk: 1.#INF

  - Sessiz NaN: 1.#QNAN

  - Sinyal NaN: 1.#SNAN

  - Belirsiz NaN: 1.#IND

  Bu biçimlerden herhangi biri bir işaret tarafından önceden belirlenmiş olabilir ve alan genişliğine ve hassasiyete bağlı olarak biraz `printf("%.2f\n", INFINITY)` farklı biçimlendirilmiş olabilir (örneğin, #INF 2 basamaklı bir duyarlık için "yuvarlanmış" olacağı için 1,#J yazdırılır). C99, sonsuzlukların ve NN'lerin nasıl biçimlendirilen yeni gereksinimler getirmiştir. MSVC uygulaması artık bu gereksinimlere uygundur. Yeni dizeleri aşağıdaki gibidir:

  - Sonsuzluk: inf

  - Sessiz NaN: nan

  - Sinyal NaN: nan(snan)

  - Belirsiz NaN: nan(ind)

  Bunlardan herhangi biri bir işaret tarafından önceden belirlenmiş olabilir. Büyük harfli biçim belirteci kullanılırsa (%F yerine %f), dizeleri büyük`INF` harflerle (yerine) `inf`gerekirse yazdırılır.

  [Scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) işlevleri bu yeni dizeleri ayrışdırmak için değiştirilmiştir, bu `printf` yüzden `scanf`bu dizeleri şimdi gidiş-dönüş ve .

- **Kayan nokta biçimlendirme ve ayrışma**

   Doğruluğu iyileştirmek için yeni kayan nokta biçimlendirme ve ayrıştma algoritmaları tanıtıldı. Bu değişiklik, işlevlerin [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) ve [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) ailelerinin yanı sıra [strtod](../c-runtime-library/reference/strtod-strtod-l-wcstod-wcstod-l.md)gibi işlevleri de etkiler.

   Eski biçimlendirme algoritmaları yalnızca sınırlı sayıda basamak oluşturur, sonra kalan ondalık basamakları sıfırla doldurur. Genellikle orijinal kayan nokta değerine geri gidiş-dönüş olacak dizeleri oluşturabilir, ancak tam değeri (veya bunların en yakın ondalık gösterimi) istedim büyük değildi. Yeni biçimlendirme algoritmaları değeri temsil etmek (veya belirtilen kesinliği doldurmak için) gerektiği kadar basamak oluşturur. İyileştirmenin bir örneği olarak; iki büyük bir güç yazdırırken sonuçları göz önünde bulundurun:

    ```cpp
    printf("%.0f\n", pow(2.0, 80))
    ```

   Eski çıktı:

    ```Output
    1208925819614629200000000
    ```

   Yeni çıktı:

    ```Output
    1208925819614629174706176
    ```

   Eski ayrıştırma algoritmaları giriş dizesinden yalnızca en fazla 17 önemli basamak dikkate alır ve diğer basamakları atar. Bu yaklaşım, dize tarafından temsil edilen değerin yakın bir yaklaşımını oluşturmak için yeterlidir ve sonuç genellikle doğru yuvarlanmış sonuca çok yakındır. Yeni uygulama tüm mevcut basamakları dikkate alır ve tüm girişler için doğru yuvarlanmış sonucu üretir (uzunluğu 768 basamak kadar). Buna ek olarak, bu işlevler artık yuvarlama moduna saygı duyar (fesetround üzerinden kontrol edilebilir).  Bu işlevler farklı sonuçlar çıktı olabilir, çünkü bu büyük bir kesme davranış değişikliğidir. Yeni sonuçlar her zaman eski sonuçlardan daha doğrudur.

- **Hexadecimal ve sonsuzluk/NaN yüzer nokta ayrışma**

   Kayan nokta ayrıştırma algoritmaları şimdi hexadecimal kayan nokta dizeleri ayrıştıracak (% a ve % A printf biçimi belirteçleri tarafından oluşturulan `printf` olanlar gibi) ve tüm sonsuzluk ve NaN dizeleri işlevleri tarafından oluşturulan, yukarıda açıklandığı gibi.

- **%A ve %sıfır dolgu**

   %a ve %A biçimi, kayan nokta sayısını hexadecimal mantissa ve ikili üs olarak biçimlendirin. Önceki sürümlerde, `printf` işlevler yanlış sıfır pad dizeleri olur. Örneğin, `printf("%07.0a\n", 1.0)` 0x01p+0 yazdırılır, burada 0x01p+0 yazdırılır. Bu kusur düzeltildi.

- **%A ve %bir kesinlik**

   %A ve %bir biçim belirtimlerinin varsayılan kesinliği kitaplığın önceki sürümlerinde 6 idi. Varsayılan kesinlik, C Standardına uygunluk için şimdi 13'e sahiptir.

   Bu, %A veya %a ile biçim dizesi kullanan herhangi bir işlevin çıktısında bir çalışma zamanı davranış değişikliğidir. Eski davranışta, %A belirticisini kullanan çıktı "1.1A2B3Cp+111" olabilir. Şimdi aynı değer için çıkış "1.1A2B3C4D5E6F7p+111". Eski davranışı elde etmek için, örneğin %.6A hassasiyetini belirtebilirsiniz. Bkz. [Hassas Belirtim.](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md#precision)

- **%F belirtici**

   %F biçimi/dönüştürme belirtimi artık desteklenmektedir. Sonsuzlukların ve NN'lerin büyük harflerle biçimlendirilmesi dışında, işlevsel olarak %f biçimi belirticisine eşdeğerdir.

   Önceki sürümlerde, uygulama f ve N'yi uzunluk değiştiriciler olarak ayrışdırmak için kullanılır. Bu davranış, segmente edilmiş adres alanlarının yaşına kadar uzanır: Bu uzunluk değiştiriciler, sırasıyla %Fp veya %N'lerde olduğu gibi uzak ve yakın işaretçileri belirtmek için kullanılmıştır. Bu davranış kaldırıldı. %F ile karşılaşılırsa, artık %F biçimi belirticisi olarak kabul edilir; %N ile karşılaşılırsa, artık geçersiz bir parametre olarak kabul edilir.

- **Üslü biçimlendirme**

   %e ve %E biçimi belirteçleri kayan nokta sayısını ondalık mantissa ve üs olarak biçimlendirin. %g ve %G biçimi belirteçleri de bazı durumlarda bu formdaki sayıları biçimlendirin. Önceki sürümlerde, CRT her zaman üç basamaklı üslere sahip dizeleri oluşturur. Örneğin, `printf("%e\n", 1.0)` 1.000000e+000 yazdırılır, bu da yanlıştı. C, üs yalnızca bir veya iki basamak kullanılarak temsil edilebilirse, yalnızca iki basamak yazdırılmasını gerektirir.

   Visual Studio 2005'te küresel bir uyumluluk anahtarı eklendi: [_set_output_format.](../c-runtime-library/set-output-format.md) Bir program, uyumlu üsbaskıyı etkinleştirmek için bu işlevi _TWO_DIGIT_EXPONENT bağımsız değişkenle çağırabilir. Varsayılan davranış, standartlara uygun üssel yazdırma moduna değiştirildi.

- **Biçim dize doğrulaması**

   Önceki sürümlerde, `printf` `scanf` ve işlevler sessizce birçok geçersiz biçim dizeleri, bazen alışılmadık etkileri ile kabul eder. Örneğin, %hlhld %d olarak kabul edilir. Geçersiz biçim dizeleri artık geçersiz parametreler olarak kabul edilir.

- **fopen modu dize doğrulama**

   Önceki sürümlerde, `fopen` işlevler ailesi sessizce gibi bazı geçersiz mod `r+b+`dizeleri, kabul etti. Geçersiz mod dizeleri şimdi algılanır ve geçersiz parametreler olarak kabul edilir.

- **_O_U8TEXT modu**

   [_setmode](../c-runtime-library/reference/setmode.md) işlevi artık in_O_U8TEXT açılan akışlar için modu doğru şekilde bildirir. Kitaplığın önceki sürümlerinde, _O_WTEXT'da açılmış gibi akışlar bildirilir.

   Bu, kodlamanın UTF-8 olduğu akışlar için _O_WTEXT modunu yorumluyorsa, bu bir kırılma değişikliğidir. Uygulamanız UTF_8 desteklemiyorsa, giderek yaygınlaşan bu kodlama için destek eklemeyi düşünün.

- **snprintf ve vsnprintf**

   [Snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) ve [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) işlevleri artık uygulanmaktadır. Eski kod, CRT kitaplığı tarafından uygulanmadığından, bu işlevlerin tanımlarını genellikle makro sürümlerini sağlar, ancak artık yeni sürümlerde bunlara ihtiyaç duyulmamıştır. stdio.h>'ı da dahil etmeden \<önce [snprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) veya [vsnprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) makro olarak tanımlanırsa, derleme artık makronun tanımlandığı yeri gösteren bir hatayla başarısız olur.

   Normalde, bu sorunun düzeltmesi veya kullanıcı `snprintf` kodu `vsnprintf` herhangi bir bildirimleri silmektir.

- **tmpnam Kullanılabilir Dosya Adları Oluşturur**

   Önceki sürümlerde, `tmpnam` `tmpnam_s` sürücünün kökünde dosya adları ve işlevleri oluşturulur (\sd3c gibi).. Bu işlevler artık geçici bir dizinde kullanılabilir dosya adı yolları oluşturur.

- **DOSYA Kapsülleme**

   Önceki sürümlerde, tüm DOSYA türü \<stdio.h> genel olarak tanımlanmıştır, bu nedenle kullanıcı kodunun bir DOSYAya ulaşması ve iç lerini değiştirmesi mümkündür. Kitaplık, uygulama ayrıntılarını gizlemek için değiştirildi. Bu değişikliğin bir parçası olarak, \<STDio.h>'da tanımlandığı gibi DOSYA artık opak bir türdür ve üyelerine CRT'nin dışından erişilemez.

- **_outp ve _inp**

   [_outp](../c-runtime-library/outp-outpw-outpd.md), [_outpw](../c-runtime-library/outp-outpw-outpd.md), [_outpd](../c-runtime-library/outp-outpw-outpd.md), [_inp](../c-runtime-library/inp-inpw-inpd.md), [_inpw](../c-runtime-library/inp-inpw-inpd.md)ve [_inpd](../c-runtime-library/inp-inpw-inpd.md) işlevleri kaldırıldı.

#### <a name="stdlibh-malloch-and-sysstath"></a>\<stdlib.h>, \<malloc.h \<> ve sys/stat.h>

- **strtof ve wcstof**

   Ve `strtof` `wcstof` işlevler, `errno` değer float olarak temsil edilemediği zaman ERANGE'ye ayarlayamadı. Bu hata bu iki fonksiyona özgüydü; `strtod`, `wcstod`, `strtold`ve `wcstold` işlevler etkilenmedi. Bu sorun giderildi ve çalışma zamanı kesme değişikliğidir.

- **Hizalanmış ayırma işlevleri**

   Önceki sürümlerde, hizalanmış ayırma`_aligned_malloc` `_aligned_offset_malloc`işlevleri (, , vb) sessizce 0 hizalama ile bir blok isteklerini kabul eder. İstenen hizalama, sıfır için geçerli olmayan iki kişilik bir güç olmalıdır. İstenen 0 hizalaması artık geçersiz bir parametre olarak kabul edilir. Bu sorun giderildi ve çalışma zamanı kesme değişikliğidir.

- **Yığın fonksiyonları**

   , `_heapadd` `_heapset`ve `_heapused` işlevler kaldırıldı. CRT Windows yığınını kullanmak üzere güncelleştirildiberi bu işlevler işlevsel değildir.

- **smallheap**

   Bağlantı `smallheap` seçeneği kaldırıldı. [Bkz. Bağlantı Seçenekleri.](../c-runtime-library/link-options.md)

#### <a name="stringh"></a>\<string.h>

- **wcstok**

   İşlevin `wcstok` imzası C Standardı'nın gerektirdiği yle eşleşecek şekilde değiştirildi. Kitaplığın önceki sürümlerinde, bu işlevin imzası:

    ```cpp
    wchar_t* wcstok(wchar_t*, wchar_t const*)
    ```

   Bu, aramalar arasında durumu izlemek için dahili, iş `strtok`parçacığı başına bağlam ı kullandı, çünkü . İşlev şimdi imzaya `wchar_t* wcstok(wchar_t*, wchar_t const*, wchar_t**)`sahiptir ve arayanın işlevine üçüncü bir bağımsız değişken olarak bağlamı geçirmesini gerektirir.

   Taşımayı `_wcstok` kolaylaştırmak için eski imzayla birlikte yeni bir işlev eklendi. C++ kodunu derlerken, eski imzaya `wcstok` sahip satır satırlı aşırı yükleme de vardır. Bu aşırı yük amortismana ermiş olarak beyan edilir. C kodunda, `_wcstok` `wcstok`'nin yerine kullanılmasına neden define_CRT_NON_CONFORMING_WCSTOK olabilir.

#### <a name="timeh"></a>\<time.h>

- **saat**

   Önceki sürümlerde, [saat](../c-runtime-library/reference/clock.md) işlevi Windows API [GetSystemTimeAsFileTime](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getsystemtimeasfiletime)kullanılarak uygulanmıştır. Bu uygulama ile, saat fonksiyonu sistem zamanına duyarlıydı ve bu nedenle mutlaka monoton değildi. Saat işlevi [QueryPerformanceCounter](/windows/win32/api/profileapi/nf-profileapi-queryperformancecounter) açısından yeniden uygulanmıştır ve şimdi monoton.

- **fstat ve _utime**

   Önceki sürümlerde, [_stat](../c-runtime-library/reference/stat-functions.md), [fstat](../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)ve [_utime](../c-runtime-library/reference/utime-utime32-utime64-wutime-wutime32-wutime64.md) işlevleri yaz saati uygulamasını yanlış işler. Visual Studio 2013'den önce, tüm bu işlevler standart saat saatlerini gündüz vakti gibi yanlış ayarlanmıştı.

   Visual Studio 2013'te sorun **_stat** fonksiyon ailesinde giderildi, ancak **fstat** ve **_utime** işlevlerin ailelerindeki benzer sorunlar düzeltilmedi. Bu kısmi düzeltme, işlevler arasındaki tutarsızlık nedeniyle sorunlara yol açtı. **Fstat** ve **_utime** işlevleri aileleri artık sabit, bu nedenle tüm bu işlevleri niçin doğru ve tutarlı bir şekilde gün ışığından yararlanma zamanı işlemek.

- **asctime**

   Önceki sürümlerde, [asctime](../c-runtime-library/reference/asctime-wasctime.md) işlevi tek basamaklı günleri satır aralığı sıfırla, örneğin: `Fri Jun 06 08:00:00 2014`. Belirtim, bu tür günlerin bir satır aralığıyla dolgulu olmasını gerektirir. `Fri Jun  6 08:00:00 2014` Bu sorun düzeltilmiştir.

- **strftime ve wcsftime**

   Ve `strftime` `wcsftime` işlevler artık %C, %D, %e, %F, %g, %G, %h, %n, %r, %R, %t, %T, %u ve %V formatı belirteçlerini desteklememektedir. Ayrıca, E ve O değiştiriciler ayrıştı ancak yoksayılır.

   %c biçim belirtici geçerli yerel için "uygun tarih ve saat gösterimi" üreten olarak belirtilir. C yerel, bu gösterim aynı olması gerekir `%a %b %e %T %Y`, tarafından üretilen aynı `asctime`form . Önceki sürümlerde, %c biçimi `MM/DD/YY HH:MM:SS` bir gösterim kullanarak yanlış biçimlendirilmiş kez belirtir. Bu sorun düzeltilmiştir.

- **zaman spec ve TIME_UTC**

   time.h> üstbilgi şimdi `timespec` C11 `timespec_get` Standard'ın türünü ve işlevini tanımlar. \< Buna ek olarak, `timespec_get` TIME_UTC makro, işlev ile kullanılmak üzere, şimdi tanımlanır. Bu güncelleştirme, bu tanımlayıcılardan herhangi biri için çakışan bir tanımı olan kod için bir son verme değişikliğidir.

- **CLOCKS_PER_SEC**

   CLOCKS_PER_SEC makrosu artık C dilinin gerektirdiği `clock_t`şekilde bir tamsayıya genişletir.

#### <a name="c-standard-library"></a><a name="BK_STL"></a>C++ Standart Kitaplık

Yeni iyileştirmeleri ve hata ayıklama denetimlerini etkinleştirmek için, C++ Standart Kitaplığı'nın Visual Studio uygulaması bir sürümden sonraki bir sürüme ikili uyumluluğu kasıtlı olarak bozar. Bu nedenle, C++ Standart Kitaplığı kullanıldığında, farklı sürümlerin kullanımıyla derlenmiş nesne dosyaları ve statik kitaplıklar tek bir ikili dosya (EXE veya DLL) halinde karma yapılabilir ve C++ Standart Kitaplığı nesneleri, farklı sürümler kullanılarak derlenmiş ikili dosyalar arasında geçirilemez. Bu tür karmalar, _MSC_VER uyuşmazlıklarıyla ilgili bağlayıcı hataları verir. (_MSC_VER derleyicinin ana sürümünü içeren makrodur—örneğin Visual Studio 2013 için 1800.) Bu denetim DLL karıştırma algılayamadı ve Visual Studio 2008 veya daha önce içeren karıştırma algılayamıyor.

- **C++ Standart Kitaplığı dosyaları içerir**

   C++ Standart Kitaplık üstbilgisindeki dahil yapısında bazı değişiklikler yapılmıştır. C++ Standart Kitaplık üstbilgilerinin birbirini belirtilmeyen şekillerde eklemesine izin verilir. Genel olarak, kodunuzu C++ standardına göre ihtiyaç duyduğu tüm üstbilgiyi dikkatle içerecek şekilde yazmanız gerekir ve hangi C++ Standart Kitaplık üstbilgilerinin hangi C++ Standart Kitaplık üstbilgisini içerdiğine güvenmez. Bu, kodu sürümler ve platformlar arasında taşınabilir hale getirir. Visual Studio 2015'teki en az iki üstbilgi değişikliği kullanıcı kodunu etkiler. İlk \<olarak, string \<> artık> yineleyici içerir. İkinci \<olarak, tuple `std::array`> şimdi kod \<yapıları aşağıdaki birleşimi ile kod kırabilir dizi>, tüm dahil olmadan bildirir: kod "dizi" adlı bir değişken var ve bir kullanım yönergesi var \<"namespace std kullanarak;", ve bir C++ Standart Kütüphane üstbilgi (işlevsel> gibi) tuple> içeren \<bir , şimdi bildirir `std::array`.

- **steady_clock**

   steady_clock \<krono> [steady_clock](../standard-library/steady-clock-struct.md) uygulaması, c++ standart istikrar ve monotonluk gereksinimlerini karşılayacak şekilde değiştirildi. `steady_clock`şimdi [QueryPerformanceCounter](/windows/win32/api/profileapi/nf-profileapi-queryperformancecounter) dayanmaktadır `high_resolution_clock` ve şimdi bir `steady_clock`typedef için . Sonuç olarak, Visual `steady_clock::time_point` Studio şimdi bir `chrono::time_point<steady_clock>`typedef için ; ancak, bu mutlaka diğer uygulamalar için durum değildir.

- **ayırıcılar ve const**

   Şimdi her iki tarafta const argümanlar kabul etmek için ayırıcı eşitlik / eşitsizlik karşılaştırmalar gerektirir. Tahsisatçılarınız bu işleçleri bu şekilde tanımlıyorsa,

    ```cpp
    bool operator==(const MyAlloc& other)
    ```

   sonra bunları güncelleştirin ve const üye olarak bildirmelisiniz:

    ```cpp
    bool operator==(const MyAlloc& other) const
    ```

- **const elemanları**

   C++ standardı her zaman const elemanların kapsayıcılarını yasaklamıştır (vektör\<const T> veya const T>) gibi.\< Visual Studio 2013 ve daha önce bu tür konteynerler kabul etti. Geçerli sürümde, bu tür kapsayıcılar derlemek için başarısız.

- **std::allocator::deallocate**

   Visual Studio 2013 ve `std::allocator::deallocate(p, n)` daha önce, argüman *n*için geçti göz ardı .  C++ standardı her zaman *n'nin* `allocate` *döndürülen p*. Ancak, geçerli sürümde, *n* değeri denetlenir. *N* için bağımsız değişkenleri geçen ve standardın gerektirdiğinden farklı olan kod çalışma zamanında çökebilir.

- **hash_map ve hash_set**

   > ve \<hash_set> \<hash_map standart olmayan üstbilgi dosyaları Visual Studio 2015'te amortismana uğrama olur ve ileride yayınlanacaktır. Bunun \<yerine \<unordered_map> ve unordered_set> kullanın.

- **karşılaştırıcılar ve operatör()**

   Bağşdırıcı kapsayıcılar \<(harita> aile) artık karşılaştırıcılarının const-callable function çağrı işleçlerine sahip olmasını gerektirir. Karşılaştırıcı sınıf bildiriminde aşağıdaki kod şimdi derlemek için başarısız olur:

    ```cpp
    bool operator()(const X& a, const X& b)
    ```

   Bu hatayı gidermek için işlev bildirimini şu şekilde değiştirin:

    ```cpp
    bool operator()(const X& a, const X& b) const
    ```

- **tür özellikleri**

   C++ taslak standardının önceki bir sürümündeki tür özellikleriiçin eski adlar kaldırıldı. Bunlar C++11'de değiştirildi ve Visual Studio 2015'te C++11 değerlerine güncellendi. Aşağıdaki tabloda eski ve yeni adlar gösterilmektedir.

   |Eski ad|Yeni ad|
   |--------------|--------------|
   |add_reference|add_lvalue_reference|
   |has_default_constructor|is_default_constructible|
   |has_copy_constructor|is_copy_constructible|
   |has_move_constructor|is_move_constructible|
   |has_nothrow_constructor|is_nothrow_default_constructible|
   |has_nothrow_default_constructor|is_nothrow_default_constructible|
   |has_nothrow_copy|is_nothrow_copy_constructible|
   |has_nothrow_copy_constructor|is_nothrow_copy_constructible|
   |has_nothrow_move_constructor|is_nothrow_move_constructible|
   |has_nothrow_assign|is_nothrow_copy_assignable|
   |has_nothrow_copy_assign|is_nothrow_copy_assignable|
   |has_nothrow_move_assign|is_nothrow_move_assignable|
   |has_trivial_constructor|is_trivially_default_constructible|
   |has_trivial_default_constructor|is_trivially_default_constructible|
   |has_trivial_copy|is_trivially_copy_constructible|
   |has_trivial_move_constructor|is_trivially_move_constructible|
   |has_trivial_assign|is_trivially_copy_assignable|
   |has_trivial_move_assign|is_trivially_move_assignable|
   |has_trivial_destructor|is_trivially_destructible|

- **başlat::herhangi ve başlat::eşitleme ilkeleri**

   Standart `launch::any` dışı `launch::sync` ve ilkeler kaldırıldı. Bunun yerine, `launch::any` `launch:async | launch:deferred`için , kullanın . `launch::sync` için `launch::deferred`'i kullanın. Bkz. [fırlatma Numaralandırma.](../standard-library/future-enums.md#launch)

#### <a name="mfc-and-atl"></a><a name="BK_MFC"></a>MFC ve ATL

- **Microsoft Foundation Sınıfları (MFC)**

   büyük boyutu nedeniyle artık Visual Studio bir "Tipik" yüklemek dahil edilir. MFC'yi yüklemek için Visual Studio 2015 kurulumunda **Özel** yükleme seçeneğini seçin. Visual Studio 2015 yüklüyse, **Visual Studio** kurulumlarını yeniden çalıştırarak MFC'yi yükleyebilirsiniz. **Özel** yükleme seçeneğini seçin ve ardından **Microsoft Hazırlık Sınıfları'nı**seçin. **Visual Studio** kurulumunu **Denetim Masası** denetim **Programlarından ve Özelliklerinden**veya yükleme medyasından çalıştırabilirsiniz.

   Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.

#### <a name="concurrency-runtime"></a><a name="BK_ConcRT"></a>Eşzamanlı çalışma süresi

- **Eşzamanlılıkla çakışan Windows.h'den verim makrosu::Bağlam::Verim**

   Daha önce, Windows.h `#undef` h'de tanımlanan Verim makrosu ile işlev arasındaki çakışmaları `concurrency::Context::Yield` önlemek için Verim makrosu tanımını çıkarmak için kullanılan Eşzamanlı Çalışma Süresi. Bu `#undef` kaldırıldı ve yeni bir çakışmayan eşdeğer API çağrı [eşzamanlılık::Bağlam::YieldExecution](../parallel/concrt/reference/context-class.md#yieldexecution) eklendi. Verim ile çakışmaları çözmek için, aşağıdaki örnekte olduğu `YieldExecution` gibi, `Yield` işlevyerine çağırmak için kodunuzu güncelleştirebilirsiniz veya işlev adını çağrı sitelerinde parantezlerle çevreleyebilirsiniz:

    ```cpp
    (concurrency::Context::Yield)();
    ```

## <a name="compiler-conformance-improvements-in-visual-studio-2015"></a>Visual Studio 2015'te Derleyici Uygunluk Geliştirmeleri

Kodu önceki sürümlerden yükseltirken, Visual Studio 2015'te yapılan uyumluluk geliştirmelerinden kaynaklanan derleyici hatalarıyla da karşılaşabilirsiniz. Bu geliştirmeler Visual Studio'nun önceki sürümlerinden ikili uyumluluğu bozmaz, ancak daha önce hiç yayımlanmamış derleyici hataları üretebilir. Daha fazla bilgi için Visual [C++ What's New 2003 ile 2015](../porting/visual-cpp-what-s-new-2003-through-2015.md)'e bakın.

Visual Studio 2015'te, derleyici uygunluğuiçin devam eden iyileştirmeler bazen derleyicinin varolan kaynak kodunuzu nasıl anladığını değiştirebilir. Sonuç olarak, yapınız sırasında yeni veya farklı hatalarla, hatta daha önce oluşturulmuş ve doğru şekilde çalışan koddaki davranış farklılıklarıyla karşılaşabilirsiniz.

Neyse ki, bu farklılıkların kaynak kodlarınızın çoğu üzerinde çok az veya hiç etkisi yoktur. Bu farklılıkları gidermek için kaynak kodu veya diğer değişiklikler gerektiğinde, düzeltmeler küçük ve yalındır olma eğilimindedir. Daha önce değiştirilmesi *(önce)* olması gereken daha önce kabul edilebilir kaynak kodu ve bunları düzeltmek için düzeltmeler *(sonra)* birçok örnek ekledik.

Bu farklılıklar kaynak kodunuzu veya diğer yapı yapılarını etkilese de, Visual Studio sürümlerinde yapılan güncelleştirmeler arasındaki ikili uyumluluğu etkilemez. *Bir kesme değişikliği* daha şiddetlidir ve ikili uyumluluğu etkileyebilir, ancak bu tür ikili uyumluluk molaları yalnızca Visual Studio'nun ana sürümleri arasında(örneğin, Visual Studio 2013 ve Visual Studio 2015 arasında) oluşur. Visual Studio 2013 ve Visual Studio 2015 arasında gerçekleşen son dakika değişiklikleri hakkında daha fazla bilgi için [Visual Studio 2015 Uygunluk Değişiklikleri'ne](#VC_2015)bakın.

- [Visual Studio 2015'te Uygunluk Geliştirmeleri](#VS_RTM)

- [Güncelleme 1'deki Uygunluk Geliştirmeleri](#VS_Update1)

- [Güncelleme 2'deki Uygunluk Geliştirmeleri](#VS_Update2)

- [Güncelleme 3'te Uygunluk Geliştirmeleri](#VS_Update3)

### <a name="conformance-improvements-in-visual-studio-2015"></a><a name="VS_RTM"></a>Visual Studio 2015'te Uygunluk Geliştirmeleri

- /Zc:forScope- seçeneği

   Derleyici seçeneği `/Zc:forScope-` amortismana alınır ve ileride sürülecek şekilde kaldırılır.

    ```cpp
    Command line warning  D9035: option 'Zc:forScope-' has been deprecated and will be removed in a future release
    ```

   Genellikle, bu seçenek, standart göre, kapsam dışına gitmiş olması gereken noktadan sonra döngü değişkenleri kullanan standart dışı kod izin vermek için kullanılmıştır. Bu yalnızca `/Za` seçenekle derlediğinizde gerekliydi, `/Za`çünkü döngü nün bitiminden sonra for döngüsü değişkeninin kullanımına her zaman izin verilir. Standartlara uygunluğu önemsemiyorsanız (örneğin, kodunuz diğer derleyicilere taşınabilir değilse), `/Za` seçeneği kapatabilir (veya Devre Dışı BırakDil Uzantıları özelliğini **No**olarak **ayarlayabilirsiniz).** Taşınabilir, standartlara uygun kod yazmayı önemsiyorsanız, bu tür değişkenlerin bildirimini döngü dışında bir noktaya taşıyarak kodunuzu standarda uygun olacak şekilde yeniden yazmalısınız.

    ```cpp
    // C2065 expected
    int main() {
        // Uncomment the following line to resolve.
        // int i;
        for (int i = 0; i < 1; i++);
        i = 20;   // i has already gone out of scope under /Za
    }
    ```

- `/Zg`derleyici seçeneği

   `/Zg` Derleyici seçeneği (İşlev Prototipleri Oluştur) artık kullanılamıyor. Bu derleyici seçeneği daha önce küçümsüldü.

- C++/CLI ile birim testlerini artık mstest.exe ile komut satırından çalıştıramazsınız. Bunun yerine vstest.console.exe'yi kullanın. Bkz. [VSTest.Console.exe komut satırı seçenekleri.](/visualstudio/test/vstest-console-options)

- **mutable anahtar kelime**

   Daha önce hatasız derlendiği yerlerde **değişken** depolama sınıfı belirteci artık izin verilmez. Şimdi, derleyici hata C2071 (yasadışı depolama sınıfı) verir. Standarda göre, **mutable belirteç** yalnızca sınıf veri üyelerinin adlarına uygulanabilir ve const veya statik olarak bildirilen adlara uygulanamaz ve başvuru üyelerine uygulanamaz.

   Örneğin, aşağıdaki kodu göz önünde bulundurun:

    ```cpp
    struct S
    {
        mutable int &r;
    };
    ```

   Derleyicinin önceki sürümleri bunu kabul etti, ancak şimdi derleyici aşağıdaki hatayı verir:

    ```Output
    error C2071: 'S::r': illegal storage class
    ```

   Hatayı düzeltmek için, gereksiz **mutable** anahtar sözcüğü kaldırın.

- **char_16_t ve char32_t**

   Bu türler artık `char16_t` `char32_t` yerleşik olarak kabul edilir, çünkü artık bir **typedef**veya diğer adlar olarak kullanabilirsiniz. Kullanıcıların `char16_t` ve kitaplık yazarlarının `char32_t` `uint16_t` `uint32_t`sırasıyla diğer adları ve diğer adları tanımlaması yaygındı.

    ```cpp
    #include <cstdint>

    typedef uint16_t char16_t; //C2628
    typedef uint32_t char32_t; //C2628

    int main(int argc, char* argv[])
    {
        uint16_t x = 1; uint32_t y = 2;
        char16_t a = x;
        char32_t b = y;
        return 0;
    }
    ```

   Kodunuzu güncelleştirmek için **typedef** bildirimlerini kaldırın ve bu adlarla çarpışan diğer tanımlayıcıları yeniden adlandırın.

- **Türü olmayan şablon parametreleri**

   Tür dışı şablon parametrelerini içeren belirli kod, açık şablon bağımsız değişkenleri sağladığınızda tür uyumluluğu için doğru şekilde denetlenir. Örneğin, Visual Studio'nun önceki sürümlerinde hatasız olarak derlenen aşağıdaki kod.

    ```cpp
    struct S1
    {
        void f(int);
        void f(int, int);
    };

    struct S2
    {
        template <class C, void (C::*Function)(int) const> void f() {}
    };

    void f()
    {
        S2 s2;
        s2.f<S1, &S1::f>();
    }
    ```

   Şablon parametre türü şablon bağımsız değişkeniyle eşleşmediği için geçerli derleyici doğru bir hata verir (parametre const üyeiçin bir işaretçidir, ancak f işlevi const değildir):

    ```Output
    error C2893: Failed to specialize function template 'void S2::f(void)'note: With the following template arguments:note: 'C=S1'note: 'Function=S1::f'
    ```

   Kodunuzdaki bu hatayı gidermek için, kullandığınız şablon bağımsız değişkeninin türünün bildirilen şablon parametre türüyle eşleştiğinden emin olun.

- **__declspec(hizala)**

   Derleyici artık işlevleri `__declspec(align)` kabul etmez. Bu yapı her zaman yoksayılır, ancak şimdi bir derleyici hatası üretir.

    ```cpp
    error C3323: 'alignas' and '__declspec(align)' are not allowed on function declarations
    ```

   Bu sorunu gidermek `__declspec(align)` için işlev bildiriminden kaldırın. Hiçbir etkisi olmadığı için, çıkarmak hiçbir şeyi değiştirmez.

- **Özel durum işleme**

   Özel durum işlemede birkaç değişiklik vardır. İlk olarak, özel durum nesnelerinin kopyalanabilir veya taşınabilir olması gerekir. Visual Studio 2013'te derlenen ancak Visual Studio 2015'te derlenmeyen aşağıdaki kod:

    ```cpp
    struct S
    {
    public:
        S();
    private:
        S(const S &);
    };

    int main()
    {
        throw S(); // error
    }
    ```

   Sorun, kopya oluşturucu nun özel olmasıdır, bu nedenle nesne bir özel durumu işleme normal seyrinde olduğu gibi kopyalanamaz. Aynı durum, kopya oluşturucu **açık**olarak beyan edildiğinde de geçerlidir.

    ```cpp
    struct S
    {
        S();
        explicit S(const S &);
    };

    int main()
    {
        throw S(); // error
    }
    ```

   Kodunuzu güncelleştirmek için, özel durum nesnenizin kopya oluşturucusu **ortak** olduğundan ve **açık**olarak işaretlenmemiş olduğundan emin olun.

   Bir özel durum değerine göre yakalamak da özel durum nesnesinin kopyalanabilir olmasını gerektirir. Visual Studio 2013'te derlenen ancak Visual Studio 2015'te derlenmeyen aşağıdaki kod:

    ```cpp
    struct B
    {
    public:
        B();
    private:
        B(const B &);
    };

    struct D : public B {};

    int main()
    {
        try
        {
        }
        catch (D d) // error
        {
        }
    }
    ```

   **Catch** için parametre türünü bir başvuruyla değiştirerek bu sorunu giderebilirsiniz.

    ```cpp
    catch (D& d)
    {
    }
    ```

- **Dizeleri literals makrolar tarafından takip**

   Derleyici artık kullanıcı tanımlı literalleri destekler. Sonuç olarak, herhangi bir müdahale beyaz boşluk olmadan makrolar tarafından takip string literals hatalar veya beklenmeyen sonuçlar üretebilir kullanıcı tanımlı literals olarak yorumlanır. Örneğin, önceki derleyicilerde aşağıdaki kod başarıyla derlenmiştir:

    ```cpp
    #define _x "there"
    char* func() {
        return "hello"_x;
    }
    int main()
    {
        char * p = func();
        return 0;
    }
    ```

   Derleyici bu kodu bir dize olarak yorumladı "merhaba" bir makro ardından, hangi "orada" içine genişletilir ve daha sonra iki dize literals bir içine sıkıştırılmış edildi. Visual Studio 2015'te derleyici bu diziyi kullanıcı tanımlı bir edebi olarak yorumlar, ancak `_x` eşleşen kullanıcı tanımlı gerçek tanımlı olmadığından hata verir.

    ```Output
    error C3688: invalid literal suffix '_x'; literal operator or literal operator template 'operator ""_x' not found
    note: Did you forget a space between the string literal and the prefix of the following string literal?
    ```

   Bu sorunu gidermek için, dize literal ve makro arasında bir boşluk ekleyin.

- **Bitişik dize literals**

   Öncekine benzer şekilde, dize ayrıştırma ile ilgili değişiklikler nedeniyle, herhangi bir boşluk olmadan bitişik dize literals (ya geniş veya dar karakter dize literals) Visaul C++'ın önceki sürümlerinde tek bir concatenated dize olarak yorumlandı. Visual Studio 2015'te, artık iki dize arasına boşluk eklemeniz gerekir. Örneğin, aşağıdaki kodun değiştirilmesi gerekir:

    ```cpp
    char * str = "abc""def";
    ```

   Bu sorunu gidermek için, iki dize arasına bir boşluk ekleyin:

    ```cpp
    char * str = "abc" "def";
    ```

- **Yeni yerleştirme ve silme**

   C++14 standardına uygun hale getirmek için **silme** işlecinde bir değişiklik yapıldı. Standart değişikliğinin ayrıntıları [C++ Boyutlu Deallocation'da](https://isocpp.org/files/papers/n3778.html)bulunabilir. Değişiklikler, boyut **parametresi** alan genel silme işlecinin bir biçimini ekler. Kesme değişikliği, daha önce aynı imzayla bir operatör **silme** kullanıyorsanız **(yeni bir yerleşim** operatörüyle karşılık gelmek üzere), derleyicinin uygun eşleşen bir **silme** işlecini tanımlamaya çalıştığı koddaki konum olduğundan, yeni yerleşimin kullanıldığı noktada oluşan bir derleyici hatası (C2956) alırsınız.

   İşlev, `void operator delete(void *, size_t)` C++11'deki yerleşim `void * operator new(size_t, size_t)` **yeni** işlevine karşılık gelen bir yerleşim **silme** işleciydi. C++14 boyutlu deallocation ile bu silme işlevi artık olağan bir *ayırma işlevidir* (global **delete** işleci). Standart, bir yerleşim yeni kullanımı karşılık gelen bir silme işlevi arar ve her zamanki bir deallocation işlevi bulursa, program kötü biçimlendirilmiş olması gerektirir.

   Örneğin, kodunuzun hem yeni bir **yerleşim** hem de **bir yerleşim silme**tanımladığını varsayalım:

    ```cpp
    void * operator new(std::size_t, std::size_t);
    void operator delete(void*, std::size_t) noexcept;
    ```

   Sorun, tanımladığınız bir **yerleşim silme** işleci ile yeni genel boyutlu **silme** işleci arasındaki işlev imzalarında eşleşme nedeniyle oluşur. Herhangi bir **yerleşim yeni** ve `size_t` **silme** işleçleri için farklı bir tür kullanabilirsiniz olup olmadığını düşünün. `size_t` **Typedef** türü derleyiciye bağlıdır; MSVC'de **imzasız int** için bir **typedef's.** İyi bir çözüm, bu gibi numaralandırılmış bir tür kullanmaktır:

    ```cpp
    enum class my_type : size_t {};
    ```

   Daha sonra, **yeni yerleşim** tanımınızı değiştirin ve bu tür yerine ikinci bağımsız değişken olarak kullanmak için `size_t` **sil.** Ayrıca, yeni türü geçmek için yeni yerleşim çağrılarını güncelleştirmeniz (örneğin, tamsayı değerinden dönüştürmeyi kullanarak) `static_cast<my_type>` ve tamsayı türüne geri döküm yapmak için **yeni** ve **silme** tanımını güncelleştirmeniz gerekir. Bunun için **enum** kullanmanızgerekmez; bir üye ile `size_t` bir sınıf türü de çalışacak.

   Alternatif bir çözüm, **yerleşim yeni** tamamen ortadan kaldırmak mümkün olabilir. Kodunuz, yerleşim bağımsız değişkeninin ayrılan veya silinen nesnenin boyutu olduğu bir bellek havuzu uygulamak için **yeni yerleşim** kullanıyorsa, boyutlandırma özelliği kendi özel bellek havuzu kodunuzu değiştirmek için uygun olabilir ve yerleşim işlevlerinden kurtulabilir ve yerleşim işlevleri yerine kendi iki bağımsız değişken **silme** işlecinizi kullanabilirsiniz.

   Kodunuzu hemen güncelleştirmek istemiyorsanız, derleyici seçeneğini `/Zc:sizedDealloc-`kullanarak eski davranışa geri dönebilirsiniz. Bu seçeneği kullanırsanız, iki bağımsız değişken silme işlevleri yok ve **yerleşim silme** operatörünüzle bir çakışma neden olmaz.

- **Birlik veri üyeleri**

   Birliş veri üyeleri artık başvuru türlerine sahip olamaz. Aşağıdaki kod Visual Studio 2013'te başarıyla derlenmiştir, ancak Visual Studio 2015'te bir hata üretir.

    ```cpp
    union U1
    {
        const int i;
    };
    union U2
    {
        int & i;
    };
    union U3
    {
        struct { int & i; };
    };
    ```

   Önceki kod aşağıdaki hataları üretir:

    ```Output
    test.cpp(67): error C2625: 'U2::i': illegal union member; type 'int &' is reference type
    test.cpp(70): error C2625: 'U3::i': illegal union member; type 'int &' is reference type
    ```

   Bu sorunu gidermek için başvuru türlerini bir işaretçi veya değer olarak değiştirin. Türü işaretçiye değiştirmek, birleşim alanını kullanan kodda değişiklikler gerektirir. Kodu bir değere değiştirmek, birleşim türlerindeki alanlar aynı belleği paylaştığından diğer alanları etkileyen birleşimde depolanan verileri değiştirir. Değerin boyutuna bağlı olarak, birlikteliğin boyutunu da değiştirebilir.

- Anonim sendikalar artık standarda daha uygun. Derleyicinin önceki sürümleri, anonim sendikalar için açık bir yapıcı ve yıkıcı oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu oluşturucu yut. Derleyici tarafından oluşturulan bu işlevler Visual Studio 2015'te silinir.

    ```cpp
    struct S
    {
        S();
    };

    union
    {
        struct
        {
            S s;
        };
    } u; // C2280
    ```

   Önceki kod Visual Studio 2015'te aşağıdaki hatayı oluşturur:

    ```cpp
    error C2280: '<unnamed-type-u>::<unnamed-type-u>(void)': attempting to reference a deleted function
    note: compiler has generated '<unnamed-type-u>::<unnamed-type-u>' here
    ```

   Bu sorunu çözmek için, yapıcı ve / veya yıkıcı kendi tanımlarını sağlayın.

    ```cpp
    struct S
    {
        // Provide a default constructor by adding an empty function body.
        S() {}
    };

    union
    {
        struct
        {
            S s;
        };
    } u;
    ```

- **Anonim yapılı sendikalar**

   Standarda uymak için, sendikalardaki anonim yapıların üyeleri için çalışma zamanı davranışı değişti. Bir sendikadaki anonim yapı üyelerinin oluşturucusu, böyle bir birlik oluşturulduğunda artık örtülü olarak çağrılmaz. Ayrıca, bir sendikadaki anonim yapı üyelerinin imha edicisi, sendika kapsam dışına çıktığında artık örtülü olarak çağrılmaz. Bir birlik U'nun, yıkıcısı olan adlandırılmış üye yapısı S'yi içeren anonim bir yapı içerdiği aşağıdaki kodu göz önünde bulundurun.

    ```cpp
    #include <stdio.h>
    struct S
    {
        S() { printf("Creating S\n"); }
        ~S() { printf("Destroying S\n"); }
    };
    union U
    {
        struct {
            S s;
        };
        U() {}
        ~U() {}
    };

    void f()
    {
        U u;
        // Destructor implicitly called here.
    }

    int main()
    {
        f();

        char s[1024];
        printf("Press any key.\n");
        gets_s(s);
        return 0;
    }
    ```

   Visual Studio 2013'te, birliktelik oluşturulduğunda S'nin oluşturucusu çağrılır ve işlev f yığını temizlendiğinde S için yıkıcı çağrılır. Ancak Visual Studio 2015'te yapıcı ve yıkıcı çağrılmadı. Derleyici bu davranış değişikliği hakkında bir uyarı verir.

    ```Output
    warning C4587: 'U::s': behavior change: constructor is no longer implicitly calledwarning C4588: 'U::s': behavior change: destructor is no longer implicitly called
    ```

   Özgün davranışı geri yüklemek için anonim yapıya bir ad verin. Anonim olmayan yapıların çalışma zamanı davranışı, derleyici sürümünden bağımsız olarak aynıdır.

    ```cpp
    #include <stdio.h>

    struct S
    {
        S() { printf("Creating S.\n"); }
        ~S() { printf("Destroying S\n"); }
    };
    union U
    {
        struct
        {
            S s;
        } namedStruct;
        U() {}
        ~U() {}
    };

    void f()
    {
        U u;
    }

    int main()
    {
        f();

        char s[1024];
        printf("Press any key.\n");
        gets_s(s);
        return 0;
    }
    ```

   Alternatif olarak, oluşturucu ve yıkıcı kodu yeni işlevlere taşımayı deneyin ve bu işlevlere birleşim için oluşturucu ve yıkıcıdan çağrılar ekleyin.

    ```cpp
    #include <stdio.h>

    struct S
    {
        void Create() { printf("Creating S.\n"); }
        void Destroy() { printf("Destroying S\n"); }
    };
    union U
    {
        struct
        {
            S s;
        };
        U() { s.Create(); }
        ~U() { s.Destroy(); }
    };

    void f()
    {
        U u;
    }

    int main()
    {
        f();

        char s[1024];
        printf("Press any key.\n");
        gets_s(s);
        return 0;
    }
    ```

- **Şablon çözünürlüğü**

   Şablonlar için ad çözümlemesi için değişiklikler yapıldı. C++'da, bir ismin çözümü için adayları değerlendirirken, olası eşleşmeler olarak düşünülen bir veya daha fazla ad geçersiz bir şablon anlık oluşturma sağlar. Bu geçersiz anlık hatalar normalde derleyici hatalarına neden olmaz, SFINAE (Değiştirme Hatası Hata Değildir) olarak bilinen bir ilkedir.

   Şimdi, SFINAE derleyicinin bir sınıf şablonunun uzmanlığını anında ani hale getirilmesini gerektiriyorsa, bu işlem sırasında oluşan hatalar derleyici hatalarıdır. Önceki sürümlerde, derleyici bu tür hataları yoksardı. Örneğin, aşağıdaki kodu göz önünde bulundurun:

    ```cpp
    #include <type_traits>

    template< typename T>
    struct S
    {
        S() = default;
        S(const S&);
        S(S& &);

        template< typename U, typename = typename std::enable_if< std::is_base_of< T, U> ::value> ::type>
        S(S< U> & &);
    };

    struct D;

    void f1()
    {
        S< D> s1;
        S< D> s2(s1);
    }

    struct B
    {
    };

    struct D : public B
    {
    };

    void f2()
    {
        S< D> s1;
        S< D> s2(s1);
    }
    ```

   Geçerli derleyiciyle derlerseniz, aşağıdaki hatayı alırsınız:

    ```Output
    type_traits(1110): error C2139: 'D': an undefined class is not allowed as an argument to compiler intrinsic type trait '__is_base_of'
    ..\t331.cpp(14): note: see declaration of 'D'
    ..\t331.cpp(10): note: see reference to class template instantiation 'std::is_base_of<T,U>' being compiled
    with
    [
        T=D,
        U=D
    ]
    ```

   Bunun nedeni, is_base_of ilk çağrı noktasında sınıfın `D` henüz tanımlanmamış olmasıdır.

   Bu durumda, düzeltme sınıf tanımlanana kadar bu tür özellikleri kullanmamaktır. Tanımları kod dosyasının `B` `D` başına ve tanımına taşırsanız, hata çözülür. Tanımlar üstbilgi dosyalarındaysa, sorunlu şablonlar kullanılmadan önce sınıf tanımlarının derlenmiş olduğundan emin olmak için üstbilgi dosyalarıiçin ekstrelerin sırasını denetleyin.

- **Kopya yapıcılar**

   Hem Visual Studio 2013 hem de Visual Studio 2015'te derleyici, bu sınıfın kullanıcı tanımlı bir hareket oluşturucusu varsa ancak kullanıcı tanımlı kopya oluşturucusu yoksa bir sınıf için bir kopya oluşturucu oluşturur. Dev14'te, bu örtülü olarak oluşturulan kopya oluşturucusu da "= delete" olarak işaretlenir.

<!--From here to VS_Update1 added 04/21/2017-->

- **ana extern "C" olarak ilan şimdi bir dönüş türü gerektirir.**

   Aşağıdaki kod şimdi C4430 üretir.

    ```cpp
    extern "C" __cdecl main(){} // C4430
    ```

   Hatayı düzeltmek için iade türünü ekleyin:

    ```cpp
    extern "C" int __cdecl main(){} // OK
    ```

- **bir üye baş harfinde yazı adı izin verilmez**

   Aşağıdaki kod şimdi C2059 üretir:

    ```cpp
    template<typename T>
    struct S1 : public T::type
    {
        S1() : typename T::type() // C2059
        {
        }
    };

    struct S2 {
        typedef S2 type;
    };

    S1<S2> s;
    ```

   Hatayı gidermek için, `typename` baş harflerinden kaldırın:

    ```cpp
    S1() : T::type() // OK
    ...
    ```

- **Açık uzmanlıklar üzerinde depolama sınıfı yoksayılır.**

   Aşağıdaki kodda, statik depolama sınıf belirtimi

    ```cpp
    template <typename T>
    void myfunc(T h)
    {
    }

    template<>
    static void myfunc(double h) // static is ignored
    {
    }
    ```

- **Sınıf şablonu içindeki bir static_assert kullanılan bir sabit her zaman başarısız olur.**

   Aşağıdaki kod her `static_assert` zaman başarısız neden olur:

    ```cpp
    template <size_t some_value>
    struct S1
    {
        static_assert(false, "default not valid"); // always invoked

    };

    //other partial specializations here
    ```

   Bu sorunu çözmek için değeri bir **yapıya**sarın:

    ```cpp
    template <size_t some_value>
    struct constant_false {
        static const bool value = false;
    };

    template <size_t some_value>
    struct S1
    {
        static_assert(constant_false<some_value>::value, "default not valid");
    };

    //other partial specializations here
    ```

- **İletme bildirimleri için uygulanan kurallar. (Sadece C için geçerlidir.)**

   Aşağıdaki kod şimdi C2065 üretir:

    ```cpp
    struct token_s;
    typedef int BOOL;
    typedef int INT;

    typedef int(*PFNTERM)(PTOKEN, BOOL, INT); // C2065: 'PTOKEN' : undeclared identifier
    ```

   Bu sorunu gidermek için, uygun iletme bildirimlerini ekleyin:

    ```cpp
    struct token_s;
    typedef int BOOL;
    typedef int INT;

    // forward declarations:
    typedef struct token_s TOKEN;
    typedef TOKEN *PTOKEN;

    typedef int(*PFNTERM)(PTOKEN, BOOL, INT);
    ```

- **İşlev işaretçisi türlerinin daha tutarlı uygulanması**

   Aşağıdaki kod şimdi C2197 üretir:

    ```cpp
    typedef int(*F1)(int);
    typedef int(*F2)(int, int);

    void func(F1 f, int v1, int v2)
    {
        f(v1, v2); // C2197
    }
    ```

- **Aşırı yüklü işlevlere belirsiz çağrılar**

   Aşağıdaki kod şimdi C266 üretir: 'N::bind': aşırı yüklü işleve belirsiz çağrı

    ```cpp
    template<typename R, typename T, typename T1, typename A1>
    void bind(R(T::*)(T1), A1&&);

    namespace N
    {
        template <typename T, typename R, typename ... Tx>
        void bind(R(T::*)(Tx...), T* ptr);
    }

    using namespace N;

    class Manager
    {
    public:
        void func(bool initializing);

        void mf()
        {
            bind(&Manager::func, this); //C2668
        }
    };
    ```

   Hatayı düzeltmek için, `bind: N::bind(...)`aramayı tam olarak 'ye uygun olarak nitelendirebilirsiniz. Ancak, bu değişiklik bildirilmemiş bir tanımlayıcı (C2065) aracılığıyla ortaya çıkarsa, bunun yerine bir **kullanma** bildirimi ile bunu düzeltmek uygun olabilir.

   Bu desen, `Microsoft::WRL` ad alanındaki ComPtr ve diğer türlerde sık sık olur.

- **Yanlış adresi düzeltme**

   Aşağıdaki kod artık C2440 üretir: '=': 'type *' ile 'type' arasında dönüştüremez. Hatayı düzeltmek için, &(tür) (tür) ve (&f()) ile (f()) olarak değiştirin.

    ```cpp
    // C
    typedef void (*type)(void);

    void f(int i, type p);
    void g(int);
    void h(void)
    {
        f(0, &(type)g);
    }

    // C++
    typedef void(*type)(void);

    type f();

    void g(type);

    void h()
    {
        g(&f());
    }
    ```

- **String literal sabit bir dizidir**

   Aşağıdaki kod şimdi C2664 üretir: 'void f(void *)': 'const char (*)[2]' den 'void *' için bağımsız değişken 1 dönüştüremezsiniz

    ```cpp
    void f(void *);

    void h(void)
    {
        f(&__FUNCTION__);
        void *p = &"";
    }
    ```

   Hatayı düzeltmek için işlev parametre türünü `const void*`değiştirin veya gövdeyi `h` aşağıdaki örneğe benzer şekilde değiştirin:

    ```cpp
    void h(void)
    {
        char name[] = __FUNCTION__;
        f( name);
        void *p = &"";
    }
    ```

- **C++11 UDL dizeleri**

   Aşağıdaki kod şimdi hata C3688 üretir: geçersiz literal sonek 'L'; literal işleç veya literal işleç şablonu 'operatör ""L' bulunamadı

    ```cpp
    #define MACRO

    #define STRCAT(x, y) x\#\#y

    int main(){

        auto *val1 = L"string"MACRO;
        auto *val2 = L"hello "L"world";

        std::cout << STRCAT(L"hi ", L"there");
    }
    ```

   Hatayı düzeltmek için, alan eklemek için kodu değiştirin:

    ```cpp
    #define MACRO

    // Remove ##. Strings are automatically
    // concatenated so they aren't needed
    #define STRCAT(x, y) x y

    int main(){
        //Add space after closing quote
        auto *val1 = L"string" MACRO;
        auto *val2 = L"hello " L"world";

        std::cout << STRCAT(L"hi ", L"there");
    }
    ```

   Yukarıdaki örnekte, `MACRO` artık iki belirteç (bir dize ve ardından bir makro) olarak ayrıştırılır. Şimdi tek bir belirteç UDL olarak ayrıştı. Aynı durum daha önce L"" ve L" olarak ayrıştırılan l""L"""", şimdi L""L ve "" olarak ayrıştırıldı.

   Dize concatenation kuralları da standart, yani L"a" "b" L"ab eşdeğerdir uyumlu hale getirildi. Visual Studio'nun önceki sürümleri, farklı karakter genişliğine sahip dizelerin biraraya getiringenliğini kabul etmiyor.

- **C++11 boş karakter kaldırıldı**

   Aşağıdaki kod şimdi hata C2137 üretir: boş karakter sabiti

    ```cpp
    bool check(wchar_t c){
        return c == L''; //implicit null character
    }
    ```

   Hatayı düzeltmek için, null'u açık yapmak için kodu değiştirin:

    ```cpp
    bool check(wchar_t c){
        return c == L'\0';
    }
    ```

- **MFC özel durumları kopyalanabildiği için değere göre yakalanamaz**

   Bir MFC uygulamasındaki aşağıdaki kod artık C2316 hatasına neden olur: 'D': yıkıcı ve/veya kopya oluşturucu erişilemez veya silinemediği için yakalanamaz

    ```cpp
    struct B {
    public:
        B();
    private:
        B(const B &);
    };

    struct D : public B {
    };

    int main()
    {
        try
        {
        }
        catch (D) // C2316
        {
        }
    }
    ```

   Kodu düzeltmek için `catch (const D &)` catch bloğunu değiştirebilirsiniz, ancak daha iyi çözüm genellikle MFC TRY/CATCH makrolarını kullanmaktır.

- **alignof artık bir anahtar kelime**

   Aşağıdaki kod şimdi hata C2332 üretir: 'sınıf': eksik etiket adı. Kodu düzeltmek için sınıfı yeniden adlandırmanız veya sınıf **alignof**ile aynı işi gerçekleştiriyorsa, sınıfı yeni anahtar sözcükle değiştirmeniz gerekir.

    ```cpp
    class alignof{}
    ```

- **constexpr artık bir anahtar kelime**

   Aşağıdaki kod şimdi hata C2059 üretir: sözdizimi hatası: ')'. Kodu düzeltmek için, "constexpr" olarak adlandırılan herhangi bir işlev veya değişken adlarını yeniden adlandırmanız gerekir.

    ```cpp
    int constexpr() {return 1;}
    ```

- **Hareketli türler const olamaz**

   Bir işlev taşınması amaçlanan bir tür döndürdüğünde, geri dönüş türü **const**olmamalıdır.

- **Silinmiş kopya oluşturucuları**

   Aşağıdaki kod artık C2280 'S::S(S &&)': silinmiş bir işleve başvurmaya çalışmak üzere üretir:

    ```cpp
    struct S{
        S(int, int);
        S(const S&) = delete;
        S(S&&) = delete;
    };

    S s2 = S(2, 3); //C2280
    ```

   Hatayı düzeltmek için aşağıdakiler için `S2`doğrudan başlatma kullanın:

    ```cpp
    struct S{
        S(int, int);
        S(const S&) = delete;
        S(S&&) = delete;
    };

    S s2 = {2,3}; //OK
    ```

- **İşlev işaretçisine dönüştürme yalnızca lambda yakalama olmadığında oluşturulur**

   Aşağıdaki kod Visual Studio 2015'te C2664'u üretir.

    ```cpp
    void func(int(*)(int)) {}

    int main() {

        func([=](int val) { return val; });
    }
    ```

   Hatayı düzeltmek için, `=` yakalama listesinden kaldırın.

- **Dönüşüm işleçlerini içeren belirsiz aramalar**

   Aşağıdaki kod artık C2440 hatası üretir: 'tür döküm': 'S2'den 'S1'e dönüştüremez:

    ```cpp
    struct S1 {
        S1(int);
    };

    struct S2 {
        operator S1();
        operator int();
    };

    void f(S2 s2)
    {
        (S1)s2;
    }
    ```

   Hatayı düzeltmek için dönüşüm işleciyi açıkça arayın:

    ```cpp
    void f(S2 s2)
    {
        //Explicitly call the conversion operator
        s2.operator S1();
        // Or
        S1((int)s2);
    }
    ```

   Aşağıdaki kod şimdi hata C2593 üretir: 'işleç =' belirsizdir:

    ```cpp
    struct S1 {};

    struct S2 {
        operator S1&();
        operator S1() const;
    };

    void f(S1 *p, S2 s)
    {
        *p = s;
    }
    ```

   Hatayı düzeltmek için dönüşüm işleciyi açıkça arayın:

    ```cpp
    void f(S1 *p, S2 s)
    {
        *p = s.operator S1&();
    }
    ```

- **Statik olmayan veri üyesi başlatmada (NSDMI) geçersiz kopya başlatmayı düzeltme**

   Aşağıdaki kod şimdi hata C2664 üretir: 'S1::S1(S1 &&)': 'bool' den 'const S1 &' için bağımsız değişken 1 dönüştüremezsiniz:

    ```cpp
    struct S1 {
        explicit S1(bool);
    };

    struct S2 {
        S1 s2 = true; // error
    };
    ```

   Hatayı gidermek için doğrudan başlatma yı kullanın:

    ```cpp
    struct S2 {
    S1 s1{true}; // OK
    };
    ```

- **Decltype deyimleri içindeki kuruculara erişim**

   Aşağıdaki kod şimdi C2248 üretir: 'S::S': sınıf 'S' olarak bildirilen özel üye erişemez:

    ```cpp
    class S {
        S();
    public:
        int i;
    };

    class S2 {
        auto f() -> decltype(S().i);
    };
    ```

   Hatayı düzeltmek için, bir arkadaş `S2` `S`bildirimi eklemek için:

    ```cpp
    class S {
        S();
        friend class S2; // Make S2 a friend
    public:
        int i;
    };
    ```

- **lambda varsayılan ctor örtülü olarak silinir**

   Aşağıdaki kod şimdi hata C3497 üretir: bir lambda örneği oluşturamazsınız:

    ```cpp
    void func(){
        auto lambda = [](){};

        decltype(lambda) other;
    }
    ```

   Hatayı gidermek için varsayılan oluşturucunun çağrılması gereksinimini kaldırın. Lambda bir şey yakalayamazsa, bir işlev işaretçisine atılabilir.

- **Silinmiş atama işleci ile Lambdas**

   Aşağıdaki kod şimdi hata C2280 üretir:

    ```cpp
    #include <memory>
    #include <type_traits>

    template <typename T, typename D>
    std::unique_ptr<T, typename std::remove_reference<D &&>::type> wrap_unique(T *p, D &&d);

    void f(int i)
    {
        auto encodedMsg = wrap_unique<unsigned char>(nullptr, [i](unsigned char *p) {
        });
        encodedMsg = std::move(encodedMsg);
    }
    ```

   Hatayı düzeltmek için lambda'yı bir functor sınıfıyla değiştirin veya atama işlecinin kullanılması gereksinimini ortadan kaldırın.

- **Silinmiş kopya oluşturucusu yla nesneyi taşımaya çalışma**

   Aşağıdaki kod şimdi hata C2280 üretir: 'moveable::moveable(const moveable &)': silinmiş bir işleve başvurmaya çalışmak

    ```cpp
    struct moveable {

        moveable() = default;
        moveable(moveable&&) = default;
        moveable(const moveable&) = delete;
    };

    struct S {
        S(moveable && m) :
            m_m(m)//copy constructor deleted
        {}
        moveable m_m;
    };
    ```

   Hatayı düzeltmek için `std::move` aşağıdakileri kullanın:

    ```cpp
    S(moveable && m) :
        m_m(std::move(m))
    ```

- **Yerel sınıf, daha sonra aynı işlevde tanımlanan diğer yerel sınıfa başvuru yapamaz**

   Aşağıdaki kod şimdi hata C2079 üretir: 's' tanımlanmamış yapı 'main kullanır::S2'

    ```cpp
    int main()
    {
        struct S2;
        struct S1 {
            void f() {
                S2 s;
            }
        };
        struct S2 {};
    }
    ```

   Hatayı düzeltmek için aşağıdakilerin tanımını `S2`yukarı taşıyın:

    ```cpp
    int main()
    {
        struct S2 { //moved up
        };

    struct S1 {
        void f() {
            S2 s;
            }
        };
    }
    ```

- **Türetilmiş ctor'un gövdesinde korunan bir baz ctor'u çağıramaz.**

   Aşağıdaki kod şimdi hata C2248 üretir: 'S1::S1': 'S1' sınıfında bildirilen korumalı üyeerişemiyorum

    ```cpp
    struct S1 {
    protected:
        S1();
    };

    struct S2 : public S1 {
        S2() {
            S1();
        }
    };
    ```

   Hatayı düzeltmek için, `S2` `S1()` çağrıyı oluşturucudan kaldırın ve gerekirse başka bir işleve koyun.

- **{}işaretçiye dönüştürülmesini önler**

   Aşağıdaki kod şimdi C2439 'S::p'i üretir: üye baş harfe getirilemedi

    ```cpp
    struct S {
        S() : p({ 0 }) {}
        void *p;
    };
    ```

   Hatayı düzeltmek için, parantezleri çevredekilerden `0` kaldırın veya bu örnekte gösterildiği gibi **yerine nullptr** kullanın:

    ```cpp
    struct S {
        S() : p(nullptr) {}
        void *p;
    };
    ```

- **Parantez içinde yanlış makro tanımı ve kullanımı**

   Aşağıdaki örnek şimdi hata C2008 üretir: ';': makro tanımında beklenmeyen

    ```cpp
    #define A; //cause of error

    struct S {
        A(); // error
    };
    ```

   Sorunu gidermek için, üst satırı`#define A();`

   Aşağıdaki kod C2059 hata üretir: sözdizimi hatası: ')'

    ```cpp
    //notice the space after 'A'
    #define A () ;

    struct S {
        A();
    };
    ```

   Kodu düzeltmek için, A ile () arasındaki boşluğu kaldırın.

   Aşağıdaki kod C2091 hata üretir: işlev döndürür işlevi:

    ```cpp
    #define DECLARE void f()

    struct S {
        DECLARE();
    };
    ```

   Hatayı düzeltmek için, S'de DECLARE'dan `DECLARE;`sonra parantezleri kaldırın: .

   Aşağıdaki kod C2062 hatası üretir: 'int' beklenmeyen yazın

    ```cpp
    #define A (int)

    struct S {
        A a;
    };
    ```

   Sorunu gidermek için `A` aşağıdaki gibi tanımlayın:

    ```cpp
    #define A int
    ```

- **Beyannamelerde ekstra parenler**

   Aşağıdaki kod C2062 hatası üretir: 'int' beklenmeyen yazın

    ```cpp
    struct S {
        int i;
        (int)j;
    };
    ```

   Hatayı gidermek için, çevresindeki `j`parantezleri kaldırın. Netlik için parantez gerekiyorsa, **bir typedef**kullanın.

- **Derleyici tarafından oluşturulan yapıcılar ve __declspec(novtable)**

   Visual Studio 2015'te, sanal temel sınıflara sahip soyut sınıfların derleyici tarafından oluşturulan satır `__declspec(novtable)` içi oluşturucularının `__declspec(dllimport)`, 'ile birlikte kullanıldığında yanlış kullanımını ortaya çıkarma olasılığı artmıştır.

- **otomatik doğrudan liste-başlatma tek bir ifade gerektirir**

   Aşağıdaki kod şimdi hata C3518 üretir: 'testPositions': doğrudan liste-başlatma bağlamında 'otomatik' türü yalnızca tek bir baş harfi ifadeden çıkarılabilir

    ```cpp
    auto testPositions{
        std::tuple<int, int>{13, 33},
        std::tuple<int, int>{-23, -48},
        std::tuple<int, int>{38, -12},
        std::tuple<int, int>{-21, 17}
    };
    ```

   Hatayı düzeltmek için, bir olasılık `testPositions` aşağıdaki gibi baş harfe başlatmadır:

    ```cpp
    std::tuple<int, int> testPositions[]{
        std::tuple<int, int>{13, 33},
        std::tuple<int, int>{-23, -48},
        std::tuple<int, int>{38, -12},
        std::tuple<int, int>{-21, 17}
    };
    ```

- **is_convertible için türleri ve işaretçileri türleri denetleme**

   Aşağıdaki kod artık statik sürünçin başarısız olması için neden olur.

    ```cpp
    struct B1 {
    private:
        B1(const B1 &);
    };
    struct B2 : public B1 {};
    struct D : public B2 {};

    static_assert(std::is_convertible<D, B2>::value, "fail");
    ```

   Hatayı düzeltmek için, `static_assert` işaretçileri karşılaştırır `D` ve: `B2`

    ```cpp
    static_assert(std::is_convertible<D*, B2*>::value, "fail");
    ```

- **__declspec(novtable) beyannameleri tutarlı olmalıdır**

   `__declspec`bildirimler tüm kitaplıklar arasında tutarlı olmalıdır. Aşağıdaki kod artık tek tanımlı bir kural (ODR) ihlali üretecektir:

    ```cpp
    //a.cpp
    class __declspec(dllexport)
        A {
    public:
        A();
        A(const A&);
        virtual ~A();
    private:
        int i;
    };

    A::A() {}
    A::~A() {}
    A::A(const A&) {}

    //b.cpp
    // compile with cl.exe /nologo /LD /EHsc /Osx b.cpp
    #pragma comment(lib, "A")
    class __declspec(dllimport) A
    {
    public: A();
            A(const A&);
            virtual ~A();
    private:
        int i;
    };

    struct __declspec(novtable) __declspec(dllexport) B
        : virtual public A {
        virtual void f() = 0;
    };

    //c.cpp
    #pragma comment(lib, "A")
    #pragma comment(lib, "B")
    class __declspec(dllimport) A
    {
    public:
        A();
        A(const A&);
        virtual ~A();
    private:
        int i;
    };
    struct  /* __declspec(novtable) */ __declspec(dllimport) B // Error. B needs to be novtable here also.
        : virtual public A
    {
        virtual void f() = 0;
    };

    struct C : virtual B
    {
        virtual void f();
    };

    void C::f() {}
    C c;
    ```

### <a name="conformance-improvements-in-update-1"></a><a name="VS_Update1"></a>Güncelleme 1'deki Uygunluk Geliştirmeleri

- **Özel sanal temel sınıflar ve dolaylı kalıtım**

   Derleyicinin önceki sürümleri, türetilmiş bir sınıfın dolaylı `private virtual` olarak türetilmiş taban sınıflarının üye işlevlerini aramasına izin verdi. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve sonuç olarak derleyici hatası C2280'i sorun.

    ```Output
    error C2280: 'void *S3::__delDtor(unsigned int)': attempting to reference a deleted function
    ```

   Örnek (daha önce)

    ```cpp
    class base
    {
    protected:
        base();
        ~base();
    };

    class middle : private virtual base {}; class top : public virtual middle {};

    void destroy(top *p)
    {
        delete p;  //
    }
    ```

   Örnek (sonra)

    ```cpp
    class base;  // as above

    class middle : protected virtual base {};
    class top : public virtual middle {};

    void destroy(top *p)
    {
        delete p;
    }
    ```

   \-veya -

    ```cpp
    class base;  // as above

    class middle : private virtual base {};
    class top : public virtual middle, private virtual bottom {};

    void destroy(top *p)
    {
        delete p;
    }
    ```

- **Aşırı yüklenmiş operatör yeni ve operatör silme**

   Derleyicinin önceki sürümleri, üye olmayan **operatör silmenin** statik olarak bildirilmesine ve genel ad alanı dışındaki ad alanlarında beyan edilmesine olanak sağladı. **operator delete**  Bu eski davranış, programın programcının amaçladığı **yeni** veya silme operatör uygulamasını aramaması veya **silmemesi** riski oluşturarak sessiz kötü çalışma zamanı davranışına neden oldu. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2323 sorunları.

    ```Output
    error C2323: 'operator new': non-member operator new or delete functions may not be declared static or in a namespace other than the global namespace.
    ```

   Örnek (daha önce)

    ```cpp
    static inline void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // error C2323
    ```

   Örnek (sonra)

    ```cpp
    void * __cdecl operator new(size_t cb, const std::nothrow_t&)  // removed 'static inline'
    ```

   Ayrıca, derleyici belirli bir tanı vermese de, satır içi işleç **yeni** kötü biçimli olarak kabul edilir.

- **Sınıf dışı türlerde 'operatör *türü*()' (kullanıcı tanımlı dönüştürme) çağrısı**

   Derleyicinin önceki sürümlerinde 'işleç *türü*()' sınıf dışı türlerde çağrılmasına izin verilirken sessizce yok sayılabilir. Bu eski davranış, öngörülemeyen çalışma zamanı davranışıile sonuçlanan sessiz kötü kod oluşturma riski yarattı. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C2228 sorunları.

    ```Output
    error C2228: left of '.operator type' must have class/struct/union
    ```

   Örnek (daha önce)

    ```cpp
    typedef int index_t;
    void bounds_check(index_t index);
    void login(int column)
    {
        bounds_check(column.operator index_t());  // error C2228
    }
    ```

   Örnek (sonra)

    ```cpp
    typedef int index_t;
    void bounds_check(index_t index);
    void login(int column)
    {
        bounds_check(column);  // removed cast to 'index_t', 'index_t' is an alias of 'int'
    }
    ```

- **Ayrıntılı tür belirteciler içinde gereksiz yazı adı**

   Derleyicinin önceki sürümleri ayrıntılı bir tür belirtiminde **yazı adına** izin verebiliyor, ancak bu şekilde yazılmış kod anlamsal olarak yanlıştır. Derleyici artık bu şekilde yazılmış kodu kabul etmez ve bunun yerine derleyici hatası C3406'yı sorun.

    ```Output
    error C3406: 'typename' cannot be used in an elaborated type specifier
    ```

   Örnek (daha önce)

    ```cpp
    template <typename class T>
    class container;
    ```

   Örnek (sonra)

    ```cpp
    template <class T>  // alternatively, could be 'template <typename T>'; 'typename' is not elaborating a type specifier in this case
    class container;
    ```

- **Bir baş harf listesinden dizilerin dizilerin tümdengelimi yazma**

   Derleyicinin önceki sürümleri, bir baş harf listesinden dizilerin tür tümdengelimini desteklemedi. Derleyici şimdi bu tür tümdengelimi biçimini destekler ve sonuç olarak, baş harflistelerini kullanarak işlev şablonlarına yapılan çağrılar artık belirsiz olabilir veya derleyicinin önceki sürümlerinden farklı bir aşırı yükleme seçilebilir. Bu sorunları gidermek için, programın artık programcının amaçladığı aşırı yükü açıkça belirtmesi gerekir.

   Bu yeni davranış, aşırı yük çözümlemesi, tarihi aday kadar iyi olan ek bir adayı dikkate almaya neden olduğunda, çağrı belirsiz hale gelir ve derleyici sorunları derleme hatası C2668 sonucu olarak.

    ```Output
    error C2668: 'function' : ambiguous call to overloaded function.
    ```

   Örnek 1: Aşırı yüklü işleve belirsiz çağrı (önce)

    ```cpp
    // In previous versions of the compiler, code written in this way would unambiguously call f(int, Args...)
    template < typename... Args>
    void f(int, Args...);  //

    template < int N, typename... Args>
    void f(const int(&)[N], Args...);

    int main()
    {
        // The compiler now considers this call ambiguous, and issues a compiler error
         f({ 3 });   error C2668 : 'f' ambiguous call to overloaded function
    }
    ```

   Örnek 1: aşırı yüklü işleve belirsiz çağrı (sonra)

    ```cpp
    template < typename... Args>
    void f(int, Args...);  //

    template < int N, typename... Args>
    void f(const int(&)[N], Args...);

    int main()
    {
        // To call f(int, Args...) when there is just one expression in the initializer list, remove the braces from it.
        f(3);
    }
    ```

   Bu yeni davranış, aşırı yükleme çözümünü, tarihi adaydan daha iyi eşleşen ek bir adayı dikkate almak için neden olduğunda, çağrı yeni adaya açık bir şekilde çözümlenir ve programcının amaçladığından farklı program davranışında bir değişikliğe neden olur.

   Örnek 2: aşırı yük çözünürlüğünde değişiklik (önce)

    ```cpp
    // In previous versions of the compiler, code written in this way would unambiguously call f(S, Args...)
    struct S
    {
        int i;
        int j;
    };

    template < typename... Args>
    void f(S, Args...);

    template < int N, typename... Args>
    void f(const int *&)[N], Args...);

    int main()
    {
        // The compiler now resolves this call to f(const int (&)[N], Args...) instead
         f({ 1, 2 });
    }
    ```

   Örnek 2: aşırı yük çözünürlüğünde değişiklik (sonra)

    ```cpp
    struct S;  // as before

    template < typename... Args>
    void f(S, Args...);

    template < int N, typename... Args>
    void f(const int *&)[N], Args...);

    int main()
    {
        // To call f(S, Args...), perform an explicit cast to S on the initializer list.
        f(S{ 1, 2 });
    }
    ```

- **Anahtar bildirimi uyarılarının restorasyonu**

   Derleyicinin önceki bir **sürümü, geçiş** ifadeleriile ilgili bazı uyarıları kaldırmış; bu uyarılar artık geri yüklendi. Derleyici artık geri yüklenen uyarıları yayınlar ve belirli servis talepleriyle ilgili uyarılar (varsayılan durum dahil) artık anahtar deyiminin son satırıyerine kusurlu örneği içeren satırda verilir. Bu uyarıların geçmişteolduğundan farklı satırlarda verilmesisonucunda, daha önce kullanılarak `#pragma warning(disable:####)` bastırılan uyarılar artık beklendiği gibi bastırılamayabilir. Bu uyarıları beklendiği gibi bastırmak için, yönergeyi `#pragma warning(disable:####)` ilk kusurlu durumun üzerinde bir satıra taşımak gerekebilir. Geri yüklenen uyarılar şunlardır:

    ```Output
    warning C4060: switch statement contains no 'case' or 'default' labels
    ```

    ```Output
    warning C4061: enumerator 'bit1' in switch of enum 'flags' is not explicitly handled by a case label
    ```

    ```Output
    warning C4062: enumerator 'bit1' in switch of enum 'flags' is not handled
    ```

    ```Output
    warning C4063: case 'bit32' is not a valid value for switch of enum 'flags'
    ```

    ```Output
    warning C4064: switch of incomplete enum 'flags'
    ```

    ```Output
    warning C4065: switch statement contains 'default' but no 'case' labels
    ```

    ```Output
    warning C4808: case 'value' is not a valid value for switch condition of type 'bool'
    ```

    ```Output
    Warning C4809: switch statement has redundant 'default' label; all possible 'case' labels are given
    ```

   C4063 örneği (daha önce)

    ```cpp
    class settings
    {
    public:
        enum flags
        {
            bit0 = 0x1,
            bit1 = 0x2,
            ...
        };
        ...
    };

    int main()
    {
        auto val = settings::bit1;

        switch (val)
        {
        case settings::bit0:
            break;

        case settings::bit1:
            break;

             case settings::bit0 | settings::bit1:  // warning C4063
                break;
        }
    };
    ```

   C4063 örneği (sonra)

    ```cpp
    class settings { ... };  // as above
    int main()
    {
        // since C++11, use std::underlying_type to determine the underlying type of an enum
        typedef std::underlying_type< settings::flags> ::type flags_t;

            auto val = settings::bit1;

        switch (static_cast< flags_t> (val))
        {
        case settings::bit0:
            break;

        case settings::bit1:
            break;

        case settings::bit0 | settings::bit1:  // ok
            break;
        }
    };
    ```

   Geri yüklenen diğer uyarılara örnekler belgelerinde verilmiştir.

- **#include: yol adında '..' üst dizin belirtici** nin `/Wall` `/WX`kullanımı (yalnızca etkiler)

   Derleyicinin önceki sürümlerinde üst dizin belirtici '..' kullanımını algılamadı. direktiflerin `#include` yol adında. Bu şekilde yazılan kod genellikle proje göreli yolları yanlış kullanarak proje dışında var olan üstbilgi eklemek için tasarlanmıştır. Bu eski davranış, programın programcının amaçladığından farklı bir kaynak dosyası ekleyerek derlenebileceği veya bu göreli yolların diğer yapı ortamlarına taşınabilir olmaması riski oluşturmıştır. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinleştirilirse isteğe bağlı derleyici uyarısı C4464'ü yayınlar.

    ```Output
    warning C4464: relative include path contains '..'
    ```

   Örnek (daha önce)

    ```cpp
    #include "..\headers\C4426.h"  // emits warning C4464
    ```

   Örnek (sonra)

    ```cpp
    #include "C4426.h"  // add absolute path to 'headers\' to your project's include directories
    ```

   Ayrıca, derleyici belirli bir tanılama vermese de, üst dizinin ".." belirticinin projenizin dahil dizinlerini belirtmek için kullanılmamasını da öneririz.

- **#pragma en iyi duruma getirme() üstbilgi dosyasının son ucunu genişletir** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümlerinde, çeviri birimi içinde bulunan bir üstbilgi dosyasından kaçan en iyi duruma getirilmesi bayrak ayarlarında yapılan değişiklikler algılanmadı. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve `#include`etkinse, rahatsız ın bulunduğu yerde isteğe bağlı bir derleyici uyarısı C4426 yayınlar. Bu uyarı, yalnızca değişiklikler derlemeye komut satırı bağımsız değişkenleri tarafından ayarlanan en iyi duruma getirilmesi bayraklarıyla çakışacaksa verilir.

    ```Output
    warning C4426: optimization flags changed after including header, may be due to #pragma optimize()
    ```

   Örnek (daha önce)

    ```cpp
    // C4426.h
    #pragma optimize("g", off)
    ...
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"  // warning C4426
    ```

   Örnek (sonra)

    ```cpp
    // C4426.h
    #pragma optimize("g", off)
                ...
    #pragma optimize("", on)  // restores optimization flags set via command-line arguments
    // C4426.h ends

    // C4426.cpp
    #include "C4426.h"
    ```

- **Uyumsuz #pragma uyarı(itme)** ve **#pragma uyarı(pop)** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümleri, `#pragma warning(push)` nadiren amaçlanan `#pragma warning(pop)` farklı bir kaynak dosyadaki durum değişiklikleriyle eşleştirilmiş durum değişikliklerini algılamadı. Bu eski davranış, programın programcının amaçladığından farklı bir uyarı kümesiyle derlenme riski oluşturarak, büyük olasılıkla sessiz kötü çalışma zamanı davranışıyla sonuçlanmıştır. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinse, eşleşen `#pragma warning(pop)`konumda isteğe bağlı derleyici uyarısı C5031'i yayınlar. Bu uyarı, ilgili #pragma uyarı (push) konumunu başvuran bir not içerir.

    ```Output
    warning C5031: #pragma warning(pop): likely mismatch, popping warning state pushed in different file
    ```

   Örnek (daha önce)

    ```cpp
    // C5031_part1.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    // C5031_part1.h ends without #pragma warning(pop)

    // C5031_part2.h
    ...
    #pragma warning(pop)  // pops a warning state not pushed in this source file
    ...
    // C5031_part1.h ends

    // C5031.cpp
    #include "C5031_part1.h" // leaves #pragma warning(push) 'dangling'
    ...
    #include "C5031_part2.h" // matches 'dangling' #pragma warning(push), resulting in warning C5031
    ...
    ```

   Örnek (sonra)

    ```cpp
    // C5031_part1.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    #pragma warning(pop)  // pops the warning state pushed in this source file
    // C5031_part1.h ends without #pragma warning(pop)

    // C5031_part2.h
    #pragma warning(push)  // pushes the warning state pushed in this source file
    #pragma warning(disable:####)
    ...
    #pragma warning(pop)
    // C5031_part1.h ends

    // C5031.cpp
    #include "C5031_part1.h" // #pragma warning state changes are self-contained and independent of other source files or their #include order.
    ...
    #include "C5031_part2.h"
    ...
    ```

   Nadir olsa da, bu şekilde yazılmış kod bazen kasıtlı. Bu şekilde yazılan kod, sıralı `#include` değişikliklere karşı hassastır; mümkün olduğunda, kaynak kod dosyalarının uyarı durumunu bağımsız bir şekilde yönetmesini öneririz.

- **Eşleşmemiş #pragma uyarı(push)** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin önceki sürümleri, çeviri biriminin sonunda eşleşmemiş `#pragma warning(push)` durum değişikliklerini algılamadı. Derleyici şimdi bu şekilde yazılmış kodun programcısını algılar ve uyarır ve etkinleştirilirse, eşleşmeyen `#pragma warning(push)`konumda isteğe bağlı bir derleyici uyarısı C5032 yayınlar. Bu uyarı yalnızca çeviri biriminde derleme hatası yoksa verilir.

    ```Output
    warning C5032: detected #pragma warning(push) with no corresponding #pragma warning(pop)
    ```

   Örnek (daha önce)

    ```cpp
    // C5032.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    // C5032.h ends without #pragma warning(pop)

    // C5032.cpp
    #include "C5032.h"
    ...
    // C5032.cpp ends -- the translation unit is completed without #pragma warning(pop), resulting in warning C5032 on line 1 of C5032.h
    ```

   Örnek (sonra)

    ```cpp
    // C5032.h
    #pragma warning(push)
    #pragma warning(disable:####)
    ...
    #pragma warning(pop) // matches #pragma warning (push) on line 1
    // C5032.h ends

    // C5032.cpp
    #include "C5032.h"
    ...
    // C5032.cpp ends -- the translation unit is completed without unmatched #pragma warning(push)
    ```

- **Geliştirilmiş #pragma uyarı durumu izleme sonucunda ek uyarılar verilebilir**

   Derleyicinin önceki sürümleri, uyarı durumu #pragma tüm amaçlanan uyarıları vermek için yetersiz olarak iyi değişiklikler izler. Bu davranış, programcının amaçladığından farklı durumlarda belirli uyarıların etkili bir şekilde bastırılması riski oluşturmıştır. Derleyici artık `#pragma warning` durumu daha sağlam bir `#pragma warning` şekilde takip ediyor - özellikle şablonların içindeki durum değişiklikleriyle ilgili -- ve isteğe bağlı olarak programcının `#pragma warning(push)` istenmeyen `#pragma warning(pop)`kullanımları bulmasına yardımcı olmak amacıyla c5031 ve C5032 gibi yeni uyarılar veriyor.

   Durum değişikliği izlemenin iyileştirilmesi `#pragma warning` sonucunda, eskiden yanlış bastırılmış uyarılar veya daha önce yanlış tanı konulan sorunlarla ilgili uyarılar şimdi verilebilir.

- **Erişilemeyen kodun geliştirilmiş tanımlaması**

   C++ Standart Kitaplığı değişiklikleri ve derleyicinin önceki sürümlerinde işlev çağrılarının satır arayla yükseltilebilmesi, derleyicinin belirli kodun artık erişilemez olduğunu kanıtlamasına olanak sağlayabilir. Bu yeni davranış, c4720 uyarı yeni ve daha sık verilen örnekleri neden olabilir.

    ```Output
    warning C4720: unreachable code
    ```

   Çoğu durumda, bu uyarı yalnızca etkin leştirilmiş en iyi duruma getirimle derlendiğinde verilebilir, çünkü optimizasyonlar daha fazla işlev çağrısı nı sıralayabilir, gereksiz kodu ortadan kaldırabilir veya belirli kodun erişilemez olduğunu belirlemeyi mümkün kılabilir. C4720'nin yeni uyarı örneklerinin özellikle std kullanımı ile ilgili olarak **try/catch** bloklarında sık sık meydana geldiğini [gözlemledik::bul](../standard-library/algorithm-functions.md#find).

   Örnek (daha önce)

    ```cpp
    try
    {
        auto iter = std::find(v.begin(), v.end(), 5);
    }
    catch (...)
    {
        do_something();   // ok
    }
    ```

   Örnek (sonra)

    ```cpp
    try
    {
        auto iter = std::find(v.begin(), v.end(), 5);
    }
    catch (...)
    {
        do_something();   // warning C4702: unreachable code
    }
    ```

### <a name="conformance-improvements-in-update-2"></a><a name="VS_Update2"></a>Güncelleme 2'deki Uygunluk Geliştirmeleri

- **Ek uyarılar ve hatalar ifade SFINAE için kısmi destek sonucu verilebilir**

   Derleyicinin önceki sürümleri, SFINAE ifadesi için destek olmaması nedeniyle **decltype** belirteçleri içindeki belirli türde ifadeleri ayrışturmadı. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici şimdi bu ifadeleri ayrıştırır ve devam eden uygunluk iyileştirmeleri nedeniyle SFINAE ifadesi için kısmi destek vardır. Sonuç olarak, derleyici şimdi derleyicinin önceki sürümleriayrıştur olmadığını ifadelerde bulunan uyarılar ve hatalar sorunları.

   Bu yeni davranış, henüz bildirilmemiş bir tür içeren bir **decltype** ifadesini ayrışturduğunda, derleyici hatasını bir sonucu olarak c2039 olarak dağır.

    ```Output
    error C2039: 'type': is not a member of '`global namespace''
    ```

   Örnek 1: bildirilmemiş bir tür (daha önce) kullanımı

    ```cpp
    struct s1
    {
        template < typename T>
        auto f() - > decltype(s2< T> ::type::f());  // error C2039

        template< typename>
        struct s2 {};
    }
    ```

   Örnek 1 (sonra)

    ```cpp
    struct s1
    {
        template < typename>  // forward declare s2struct s2;

            template < typename T>
        auto f() - > decltype(s2< T> ::type::f());

        template< typename>
        struct s2 {};
    }
    ```

   Bu yeni davranış, bağımlı bir adın bir tür olduğunu belirtmek için **daktiladı** anahtar sözcüğünün gerekli bir kullanımını eksik olan bir **decltype** ifadesini ayrıştırdığında, derleyici c4346'yı derleyici hatası C2923 ile birlikte derleyici uyarısı yapar.

    ```Output
    warning C4346: 'S2<T>::Type': dependent name is not a type
    ```

    ```Output
    error C2923: 's1': 'S2<T>::Type' is not a valid template type argument for parameter 'T'
    ```

   Örnek 2: bağımlı ad bir tür değildir (önce)

    ```cpp
    template < typename T>
    struct s1
    {
        typedef T type;
    };

    template < typename T>
    struct s2
    {
        typedef T type;
    };

    template < typename T>
    T declval();

    struct s
    {
        template < typename T>
        auto f(T t) - > decltype(t(declval< S1< S2< T> ::type> ::type> ()));  // warning C4346, error C2923
    };
    ```

   Örnek 2 (sonra)

    ```cpp
    template < typename T> struct s1 { ... };  // as above
    template < typename T> struct s2 { ... };  // as above

    template < typename T>
    T declval();

    struct s
    {
        template < typename T>
        auto f(T t) - > decltype(t(declval< S1< typename S2< T> ::type> ::type> ()));
    };
    ```

- `volatile`**üye değişkenler örtülü olarak tanımlanmış yapıcıları ve atama işleçlerini önler**

   Derleyicinin önceki sürümleri, **geçici** üye değişkenleri olan bir sınıfın varsayılan kopya/taşıma oluşturucularına ve varsayılan kopyalama/taşıma atama işleçlerinin otomatik olarak oluşturulmasına izin verdi. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Derleyici artık **geçici** üye değişkenleri olan bir sınıfı önemsiz olmayan yapı ve atama işleçleri olarak kabul eder ve bu da bu işleçlerin varsayılan uygulamalarının otomatik olarak oluşturulmasını önler. Böyle bir sınıf bir birliğin (veya sınıfın içindeki anonim bir birliğin) üyesi olduğunda, birleşimin kopyalanması/taşınması ve kopyalama/taşıma atama işleçleri (veya anonim birliği içeren sınıf) dolaylı olarak silinmiş olarak tanımlanır. Açıkça tanımlamadan birleşim (veya anonim birliği içeren sınıf) oluşturmaya veya kopyalamaya çalışmak bir hatadır ve derleyici hatası C2280'i bir sonucu olarak sorun.

    ```Output
    error C2280: 'B::B(const B &)': attempting to reference a deleted function
    ```

   Örnek (daha önce)

    ```cpp
    struct A
    {
        volatile int i;
        volatile int j;
    };

    extern A* pa;

    struct B
    {
        union
        {
            A a;
            int i;
        };
    };

    B b1{ *pa };
    B b2(b1);  // error C2280
    ```

   Örnek (sonra)

    ```cpp
    struct A
    {
        int i; int j;
    };

    extern volatile A* pa;

    A getA()  // returns an A instance copied from contents of pa
    {
        A a;
        a.i = pa - > i;
        a.j = pa - > j;
        return a;
    }

    struct B;  // as above

    B b1{ GetA() };
    B b2(b1);  // error C2280
    ```

- **Statik üye işlevler cv-qualifiers desteklemez.**

   Visual Studio 2015'in önceki sürümleri statik üye işlevlerin cv elemelerine sahip olmasını sağladı. Bu davranış Visual Studio 2015 ve Visual Studio 2015 Güncelleme 1'deki gerilemeden kaynaklanmaktadır; Visual Studio 2013 ve derleyicinin önceki sürümleri bu şekilde yazılmış kodu reddeder. Visual Studio 2015 ve Visual Studio 2015 Update 1'in davranışları yanlıştır ve C++ standardına uymuyor.  Visual Studio 2015 Update 2 bu şekilde yazılmış kodu reddeder ve bunun yerine derleyici hatası C2511 sorunları.

    ```Output
    error C2511: 'void A::func(void) const': overloaded member function not found in 'A'
    ```

   Örnek (daha önce)

    ```cpp
    struct A
    {
        static void func();
    };

    void A::func() const {}  // C2511
    ```

   Örnek(sonrası)

    ```cpp
    struct A
    {
        static void func();
    };

    void A::func() {}  // removed const
    ```

- **WinRT kodunda enum'un forward bildirimine izin verilmez** (yalnızca etkiler) `/ZW`

   Windows Runtime (WinRT) için derlenen kod, `/clr` derleyici anahtarı nı kullanarak .Net Framework için yönetilen C++ kodunun derlendiğinde olduğu gibi, **enum** türlerinin iledilmesine izin vermez. Bu davranış, numaralandırmanın boyutunun her zaman bilinmesini ve WinRT türü sistemine doğru şekilde yansıtılmasını sağlar. Derleyici bu şekilde yazılmış kodu reddeder ve derleyici hatası C2599'u derleyici hatası C3197 ile birlikte soruna neden eder.

    ```Output
    error C2599: 'CustomEnum': the forward declaration of a WinRT enum is not allowed
    ```

    ```Output
    error C3197: 'public': can only be used in definitions
    ```

   Örnek (daha önce)

    ```cpp
    namespace A {
        public enum class CustomEnum : int32;  // forward declaration; error C2599, error C3197
    }

    namespace A {
        public enum class CustomEnum : int32
        {
            Value1
        };
    }

    public ref class Component sealed
    {
    public:
        CustomEnum f()
        {
            return CustomEnum::Value1;
        }
    };
    ```

   Örnek (sonra)

    ```cpp
              // forward declaration of CustomEnum removed
    namespace A {
        public enum class CustomEnum : int32
        {
            Value1
        };
    }

    public ref class Component sealed
    {
    public:
        CustomEnum f()
        {
            return CustomEnum::Value1;
        }
    };
    ```

- **Aşırı yüklenen üye olmayan operatör yeni ve operatör silme satır içi olarak ilan edilemez** (Düzey 1 (`/W1`) on-by-default)

   Derleyicinin önceki sürümleri, üye olmayan operatör yeni ve operatör silme işlevleri satır içi olarak beyan edildiğinde bir uyarı yayınlamaz. Bu şekilde yazılan kod kötü biçimlendirilmiştir (tanı lama gerektirmez) ve uyumsuz yeni ve silme işleçlerinden kaynaklanan bellek sorunlarına neden olabilir (özellikle boyutlandırmayla birlikte kullanıldığında) tanılanması zor olabilir. Derleyici şimdi derleyici uyarı C4595 bu şekilde yazılmış kodu belirlemeye yardımcı olmak için sorunları.

    ```Output
    warning C4595: 'operator new': non-member operator new or delete functions may not be declared inline
    ```

   Örnek (daha önce)

    ```cpp
    inline void* operator new(size_t sz)  // warning C4595
    {
        ...
    }
    ```

   Örnek (sonra)

    ```cpp
    void* operator new(size_t sz)  // removed inline
    {
        ...
    }
    ```

   Bu şekilde yazılmış kodun düzeltilmesi, işleç tanımlarının üstbilgi dosyasından ve ilgili kaynak dosyasına taşınmasını gerektirebilir.

### <a name="conformance-improvements-in-update-3"></a><a name="VS_Update3"></a>Güncelleme 3'te Uygunluk Geliştirmeleri

- **std::is_convertable şimdi kendini atama** algılar (standart kütüphane)

   Tür özelliğinin `std::is_convertable` önceki sürümleri, kopya oluşturucusu silindiğinde veya özel olduğunda bir sınıf türünün kendi kendini atamasını doğru şekilde algılamadı. Şimdi, `std::is_convertable<>::value` silinmiş veya özel kopya oluşturucu ile bir sınıf türüne **uygulandığında** doğru false olarak ayarlanır.

   Bu değişiklikle ilişkili derleyici tanılama yoktur.

   Örnek

    ```cpp
    #include <type_traits>

    class X1
    {
                public:
                X1(const X1&) = delete;
                };

    class X2
    {
                private:
                X2(const X2&);
                };

    static_assert(std::is_convertible<X1&, X1>::value, "BOOM");static_assert(std::is_convertible<X2&, X2>::value, "BOOM");
    ```

   Derleyicinin önceki sürümlerinde, bu örneğin altındaki statik bağımsız `std::is_convertable<>::value` değişkenler yanlış **olarak doğru**olarak ayarlandığı için geçer. Şimdi, `std::is_convertable<>::value` doğru **yanlış**olarak ayarlanır , statik iddiaları başarısız neden.

- **Varsayılan veya silinmiş önemsiz kopyalama ve taşıma oluşturucular erişim belirticilerine saygı**

   Derleyicinin önceki sürümleri, varsayılan veya silinen önemsiz kopyanın erişim belirteçlerini denetlemedi ve çağrılmasını izin vermeden önce oluşturucuları taşıdı. Bu eski davranış yanlıştı ve C++ standardına uymuyor. Bazı durumlarda, bu eski davranış sessiz kötü kod oluşturma riski yaratarak öngörülemeyen çalışma zamanı davranışıyla sonuçlanır. Derleyici şimdi varsayılan veya silinen önemsiz kopyanın erişim belirticini denetler ve çağrılan ve değilse, sonuç olarak derleyici uyarısı C2248'i sorunlayıp çözemeyeceğini belirlemek için oluşturucuları taşır.

    ```Output
    error C2248: 'S::S' cannot access private member declared in class 'S'
    ```

   Örnek (daha önce)

    ```cpp
    class S {
    public:
        S() = default;
    private:
        S(const S&) = default;
    };

    void f(S);  // pass S by value

    int main()
    {
        S s;
        f(s);  // error C2248, can't invoke private copy constructor
    }
    ```

   Örnek (sonra)

    ```cpp
    class S {
    public:
        S() = default;
    private:
        S(const S&) = default;
    };

    void f(const S&);  // pass S by reference

    int main()
    {
        S s;
        f(s);
    }
    ```

- **Atfedilen ATL kod desteğinin amortismanı** (Düzey 1 (`/W1`) varsayılan olarak)

   Derleyicinin önceki sürümleri desteklenen ATL kodu atfedilen. [Visual Studio 2008'de başlayan](../porting/visual-cpp-what-s-new-2003-through-2015.md#whats-new-for-c-in-visual-studio-2008)atfedilen ATL kodu için destek kaldırmanın bir sonraki aşaması olarak, ATL kodunun amortismana sokulmuş olması. Derleyici şimdi derleyici uyarı C4467 bu tür amortismanlı kodu belirlemeye yardımcı olmak için sorunları.

    ```Output
    warning C4467: Usage of ATL attributes is deprecated
    ```

   Destek derleyiciden kaldırılana kadar atfedilen ATL kodunu kullanmaya devam etmek istiyorsanız, `/Wv:18` derleyiciye veya `/wd:4467` komut satırı bağımsız değişkenlerini derleyiciye geçirerek veya kaynak kodunuza ekleyerek `#pragma warning(disable:4467)` bu uyarıyı devre dışı kullanabilirsiniz.

   Örnek 1 (önce)

    ```cpp
              [uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")]
    class A {};
    ```

   Örnek 1 (sonra)

    ```cpp
    __declspec(uuid("594382D9-44B0-461A-8DE3-E06A3E73C5EB")) A {};
    ```

   Bazen aşağıdaki örnek kodda olduğu gibi, amortismana nalan ATL özniteliklerinin kullanılmasını önlemek için bir IDL dosyasına ihtiyaç duyabilir veya oluşturmak isteyebilirsiniz

   Örnek 2 (önce)

    ```cpp
    [emitidl];
    [module(name = "Foo")];

    [object, local, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb")]
    __interface ICustom {
        HRESULT Custom([in] long l, [out, retval] long *pLong);
        [local] HRESULT CustomLocal([in] long l, [out, retval] long *pLong);
    };

    [coclass, appobject, uuid("9e66a294-4365-11d2-a997-00c04fa37ddb")]
    class CFoo : public ICustom
    {
        // ...
    };
    ```

   İlk olarak, *.idl dosyasını oluşturun; vc140.idl oluşturulan dosya arayüzleri ve \*ek açıklamaları içeren bir .idl dosyası elde etmek için kullanılabilir.

   Ardından, C++ arabirim tanımlarının oluşturulduğundan emin olmak için yapınıza bir MIDL adımı ekleyin.

   Örnek 2 IDL (sonra)

    ```cpp
    import "docobj.idl";

    [
        object, local, uuid(9e66a290 - 4365 - 11d2 - a997 - 00c04fa37ddb)
    ]

    interface ICustom : IUnknown {
        HRESULT  Custom([in] long l, [out, retval] long *pLong);
        [local] HRESULT  CustomLocal([in] long l, [out, retval] long *pLong);
    };

    [version(1.0), uuid(29079a2c - 5f3f - 3325 - 99a1 - 3ec9c40988bb)]
    library Foo
    {
        importlib("stdole2.tlb");
    importlib("olepro32.dll");
    [
        version(1.0),
        appobject,uuid(9e66a294 - 4365 - 11d2 - a997 - 00c04fa37ddb)
    ]

    coclass CFoo {
        interface ICustom;
    };
    }
    ```

   Ardından, aşağıdaki örnek kodda olduğu gibi ATL'yi doğrudan uygulama dosyasında kullanın.

   Örnek 2 Uygulama (sonra)

    ```cpp
    #include <idl.header.h>
    #include <atlbase.h>

    class ATL_NO_VTABLE CFooImpl :
        public ICustom,
        public ATL::CComObjectRootEx< CComMultiThreadModel>
    {
    public:
        BEGIN_COM_MAP(CFooImpl)
            COM_INTERFACE_ENTRY(ICustom)
        END_COM_MAP()
    };
    ```

- **Önceden derlenmiş üstbilgi (PCH) dosyaları ve eşleşmemiş** #include `/Wall` `/WX`yönergeleri (yalnızca etkiler)

   Derleyicinin önceki sürümleri, önceden derlenmiş üstbilgi (PCH) dosyaları kullanırken kaynak dosyalar ile `#include` `-Yc` `-Yu` derlemeler arasındaki uyumsuz yönergeleri kabul etti. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez.   Derleyici şimdi PCH dosyalarını kullanırken uyumsuz `#include` yönergeleri belirlemeye yardımcı olmak için derleyici uyarı CC4598 sorunları.

    ```Output
    warning C4598: 'b.h': included header file specified for Ycc.h at position 2 does not match Yuc.h at that position
    ```

   Örnek (önce):

   X.cpp (-Ycc.h)

    ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
    ```

   Z.cpp (-Yuc.h)

    ```cpp
    #include "b.h"
    #include "a.h"  // mismatched order relative to X.cpp
    #include "c.h"
    ```

   Örnek (sonra)

   X.cpp (-Ycc.h)

    ```cpp
    #include "a.h"
    #include "b.h"
    #include "c.h"
    ```

   Z.cpp (-Yuc.h)

    ```cpp
    #include "a.h"
    #include "b.h" // matched order relative to X.cpp
    #include "c.h"
    ```

- **Önceden derlenmiş üstbilgi (PCH) dosyaları ve eşleşmemiş dizinler içerir** (yalnızca etkiler) `/Wall` `/WX`

   Derleyicinin kabul edilen önceki sürümleri, önceden derlenmiş üstbilgi (PCH)`-I` `-Yc` dosyaları `-Yu` kullanırken derleyici ile derlemeler arasındaki komut satırı bağımsız değişkenlerini içerir. Bu şekilde yazılan kod artık derleyici tarafından kabul edilmez. Derleyici şimdi, PCH dosyalarını kullanırken eşleşmez dizin (`-I`) komut satırı bağımsız değişkenlerini belirlemeye yardımcı olmak için derleyici uyarı CC4599'u sorunları.

    ```Output
    warning C4599: '-I..' : specified for Ycc.h at position 1 does not match Yuc.h at that position
    ```

   Örnek (daha önce)

    ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h Z.cpp
    ```

   Örnek (sonra)

    ```ms-dos
    cl /c /Wall /Ycc.h -I.. X.cpp
    cl /c /Wall /Yuc.h -I.. Z.cpp
    ```

## <a name="visual-studio-2013-conformance-changes"></a>Visual Studio 2013 Uygunluk Değişiklikleri

### <a name="compiler"></a>Derleyici

- **Son** anahtar kelime şimdi daha önce derlenmiş olurdu çözülmemiş bir sembol hatası oluşturur:

    ```cpp
    struct S1 {
        virtual void f() = 0;
    };

    struct S2 final : public S1 {
        virtual void f();
    };

    int main(S2 *p)
    {
        p->f();
    }
    ```

   Önceki sürümlerde, arama **sanal** bir arama olduğu için bir hata verilmedi; yine de, program çalışma zamanında çökecek. Artık, sınıfın son olduğu bilindiğinden bir bağlayıcı hatası verilmektedir. Bu örnekte, hatayı düzeltmek için, 'nin `S2::f`tanımını içeren obj karşı bağlantı olur.

- Ad alanlarında arkadaş işlevlerini kullandığınızda, başvurudan önce arkadaş işlevini yeniden bildirmeniz gerekir veya derleyici artık ISO C++ Standardına uyduğundan bir hata alırsınız. Örneğin, bu örnek artık derlemez:

    ```cpp
    namespace NS {
        class C {
            void func(int);
            friend void func(C* const) {}
        };

        void C::func(int) {
            NS::func(this);  // error
        }
    }
    ```

   Bu kodu düzeltmek için **arkadaş** işlevini bildirin:

    ```cpp
    namespace NS {
        class C {
            void func(int);
            friend void func(C* const) {}
        };

        void func(C* const);  // conforming fix

        void C::func(int) {
            NS::func(this);
        }
    ```

- C++ Standardı, bir sınıfta açık uzmanlık almasına izin vermez. Microsoft C++ derleyicisi bazı durumlarda buna izin vermesine rağmen, aşağıdaki örnek gibi durumlarda, derleyici ikinci işlevi ilkinin uzmanlık alanı olarak kabul etmediğinden bir hata oluşturulur.

    ```cpp
    template < int N>
    class S {
    public:
        template  void f(T& val);
        template < > void f(char val);
    };

    template class S< 1>;
    ```

   Bu kodu düzeltmek için ikinci işlevi değiştirin:

    ```cpp
    template <> void f(char& val);
    ```

- Derleyici artık aşağıdaki örnekte iki işlevi ayrıştırmaya çalışmıyor ve şimdi bir hata yayıyorum:

    ```cpp
    template< typename T> void Func(T* t = nullptr);
    template< typename T> void Func(...);

    int main() {
        Func< int>(); // error
    }
    ```

   Bu kodu düzeltmek için çağrıyı netleştirin:

    ```cpp
    template< typename T> void Func(T* t = nullptr);
    template< typename T> void Func(...);

    int main() {
        Func< int>(nullptr); // ok
    }
    ```

- Derleyici ISO C++11 ile uyumlu hale getirilmeden önce, aşağıdaki `x` kod derlenmiş ve **int**yazmaya çözümlenmesine neden olur:

    ```cpp
    auto x = {0};
    int y = x;
    ```

   Bu kod artık `x` bir türe `std::initializer_list<int>` giderir ve sonraki satırda `x` **int**yazına atamaya çalışan bir hataya neden olur. (Varsayılan olarak dönüşüm yoktur.) Bu kodu düzeltmek için **otomatik**değiştirmek için **int** kullanın:

    ```cpp
    int x = {0};
    int y = x;
    ```

- IsO C++11 Standardı dönüşümleri daraltmadan çalışmak için tek tip başlatma gerektirdiğinden, sağ değer türü başharfe çevrilen sol değertürüyle eşleşmediğinde ve bir hata verildiğinde, toplu başlatmaya artık izin verilmez. Daha önce, daraltma dönüştürme sayılsaydı, bir [Derleyici Uyarısı (düzey 4) C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) uyarısı hata yerine verilirdi.

    ```cpp
    int i = 0;
    char c = {i}; // error
    ```

   Bu kodu düzeltmek için açık bir daraltma dönüşümü ekleyin:

    ```cpp
    int i = 0;
    char c = {static_cast<char>(i)};
    ```

- Aşağıdaki başlatmaya artık izin verilmez:

    ```cpp
    void *p = {{0}};
    ```

   Bu kodu düzeltmek için şu formlardan birini kullanın:

    ```cpp
    void *p = 0;
    // or
    void *p = {0};
    ```

- Ad araması değişti. Visual Studio 2012 ve Visual Studio 2013'teki C++ derleyicisinde aşağıdaki kod farklı şekilde çözülür:

    ```cpp
    enum class E1 { a };
    enum class E2 { b };

    int main()
    {
        typedef E2 E1;
        E1::b;
    }
    ```

   Visual Studio `E1` `E1::b` `::E1` 2012'de, in ifadesi genel kapsamda çözüldü. Visual Studio `E1` 2013'te `E1::b` `typedef E2` `main()` ifade tanımına göre çözülür ve türü `::E2`vardır.

- Nesne düzeni değişti. x64 üzerinde, bir sınıfın nesne düzeni önceki sürümlere göre değişebilmektedir. **Sanal** bir işlevi varsa ancak **sanal** işlevi olan bir taban sınıfı yoksa, derleyicinin nesne modeli veri üyesi düzeninden sonra bir işaretçiyi **sanal** işlev tablosuna ekler. Başka bir deyişle, ilgili düzen her durumda en uygun düzen olmayabilir. Önceki sürümlerde, x64 için bir optimizasyon sizin için düzeni geliştirmek için çalışacağız, ancak karmaşık kod durumlarda doğru çalışmabaşarısız olduğundan, Visual Studio 2013 kaldırıldı. Örneğin, aşağıdaki kodu düşünün:

    ```cpp
    __declspec(align(16)) struct S1 {
    };

    struct S2 {
        virtual ~S2();
        void *p;
        S1 s;
    };
    ```

- Visual Studio 2013'te `sizeof(S2)` x64'ün sonucu 48'dir, ancak önceki sürümlerde 32 olarak değerlendirilmiştir. Bu değerlendirmeyi Visual Studio 2013 C++ x64 için derleyicide 32'ye çıkarmak **için, sanal** işlevi olan bir kukla taban sınıfı ekleyin:

    ```cpp
    __declspec(align(16)) struct S1 {
    };

    struct dummy {
        virtual ~dummy() {}
    };
    struct S2 : public dummy {
        virtual ~S2();
        void *p;
        S1 s;
    };
    ```

   Kodunuzda daha önceki bir sürümün en iyi duruma getirmeyi denediği yerleri `/W3` bulmak için, derleyici seçeneğiyle birlikte bu sürümden bir derleyici kullanın ve C4370 uyarısını açın. Örneğin:

    ```cpp
    #pragma warning(default:4370)

    __declspec(align(16)) struct S1 {
    };

    struct S2 {
        virtual ~S2();
        void *p;
        S1 s;
    };
    ```

   Visual Studio 2013'ten önce, bu kod şu mesajı yayınlar: "Uyarı C4370: 'S2' : sınıfın düzeni daha iyi paketleme nedeniyle derleyicinin önceki sürümünden değişti".

   x86 derleyicisi derleyicinin tüm sürümlerinde aynı suboptimal düzen sorunu vardır. Örneğin, bu kod x86 için derlenirse:

    ```cpp
    struct S {
        virtual ~S();
        int i;
        double d;
    };
    ```

   Sonuç `sizeof(S)` 24. Ancak, x64 için belirtilen geçici çözüm kullanırsanız 16'ya indirilebilir:

    ```cpp
    struct dummy {
        virtual ~dummy() {}
    };

    struct S : public dummy {
        virtual ~S();
        int i;
        double d;
    };
    ```

### <a name="standard-library"></a>Standart Kitaplık

Visual Studio 2013'teki C++ derleyicisi, Visual Studio 2010'da uygulanan _ITERATOR_DEBUG_LEVEL ve RuntimeLibrary uyuşmazlıklarında uyuşmazlıkları algılar. Bu uyuşmazlıklar derleyici seçenekleri `/MT` (statik `/MTd` sürüm), (statik `/MD` hata ayıklama), (dinamik sürüm) ve `/MDd` (dinamik hata ayıklama) karışık olduğunda oluşur.

- Kodunuz önceki sürümün benzetimli diğer ad şablonlarını kabul ederse, bunu değiştirmeniz gerekir. Örneğin, bunun `allocator_traits<A>::rebind_alloc<U>::other`yerine , şimdi `allocator_traits<A>::rebind_alloc<U>`söylemek zorunda . Artık `ratio_add<R1, R2>::type` gerekli olmasına rağmen ve şimdi `ratio_add<R1, R2>`denizi öneririz , `ratio<N, D>` eski zaten azaltılmış ise aynı tür olacak azaltılmış bir oran için bir "tip" typedef olması gereklidir, çünkü hala derlemek olacaktır.

- Ararken `#include <algorithm>` `std::min()` kullanmalısınız ya `std::max()`da .

- Varolan kodunuz, ad alanlarına sarılmış geleneksel kapsam dışı enumlar olan önceki sürümün benzetimli kapsamlı enumlarını kullanıyorsa, bunu değiştirmeniz gerekir. Örneğin, türüne `std::future_status::future_status`atıfta bulunduysanız, şimdi .' demeniz `std::future_status`gerekir. Ancak, çoğu kod etkilenmez(örneğin, `std::future_status::ready` yine de derlenir.

- `explicit operator bool()`işleci belirsiz-bool-tipi() daha sıkıdır. `explicit operator bool()`bool açık dönüşümler izin `shared_ptr<X> sp`verir-örneğin, `static_cast<bool>(sp)` verilen, hem de geçerli-ve `bool b(sp)` Boolean test edilebilir "bağlamsal dönüşümler" bool için-örneğin, `if (sp)`, ne `!sp` `sp &&` olursa olsun. Ancak, `explicit operator bool()` bool örtük dönüşümleri yasaklar, bu `bool b = sp;` yüzden söyleyemezsiniz ve bir bool `return sp`dönüş türü verilen, söyleyemezsiniz .

- Artık gerçek variadik şablonlar uygulandığına göre, _VARIADIC_MAX ve ilgili makroların hiçbir etkisi yoktur. Hala _VARIADIC_MAX tanımlıyorsanız, bu göz ardı edilir. Benzetilmiş değişen sayıda bağımsız değişken içeren şablonları farklı bir şekilde desteklemeye yönelik makro makinemizi kabul ettiyseniz, kodunuzu değiştirmeniz gerekir.

- Normal anahtar kelimelere ek olarak, C++ Standart Kitaplık üstbilgiler artık içeriğe duyarlı anahtar kelimelerin **geçersiz kılınmasını** ve **son**olarak makro değişimini yasakladı.

- `reference_wrapper`, `ref()`, `cref()` ve şimdi geçici nesnelere bağlamayı yasaklar.

- \<rasgele> şimdi kesinlikle derleme zamanı ön koşullarını uygular.

- Çeşitli C++ Standart Kitaplık türü özellikleri "T tam bir tür olacaktır" ön koşuluna sahiptir. Derleyici şimdi bu ön koşulu daha sıkı bir şekilde uygulasa da, her durumda zorlamayabilir. (C++ Standart Kitaplık ön koşul ihlalleri tanımlanmamış davranışı tetikledir, Standart zorlamayı garanti etmez.)

- C++ Standart Kitaplığı desteklemez. `/clr:oldSyntax`

- common_type<> için C++11 belirtimi beklenmeyen ve istenmeyen sonuçlar doğurdu; özellikle, common_type\<int yapar, int>::yazın dönüş int&&. Bu nedenle derleyici, common_type\<int, int="">::type return int yapar Kütüphane Çalışma Grubu sorunu 2141 için Önerilen Çözüm'u uygular.

   Bu değişikliğin bir yan etkisi olarak, kimlik durumu\<artık çalışmıyor (common_type T> her zaman T tipiyle sonuçlanmaz). Bu davranış Önerilen Çözümle uyumludur, ancak önceki davranışa dayanan tüm kodu bozar.

   Kimlik türü özelliğine ihtiyacınız varsa, geçersiz> için `std::identity` \<çalışmayamayacağından \<type_traits> tanımlanan standart dışı özelliği kullanmayın. Bunun yerine, gereksinimlerinize uyan kendi kimlik türü ayırt edici niteliğini uygulayın. Bir örneği aşağıda verilmiştir:

    ```cpp
    template < typename T> struct Identity {
        typedef T type;
    };
    ```

### <a name="mfc-and-atl"></a>MFC ve ATL

- **Visual Studio 2013 sadece**: Unicode çok popüler ve MBCS kullanımı önemli ölçüde azalmıştır çünkü MFC MBCS Kütüphanesi Visual Studio dahil değildir. Yeni denetimlerin ve iletilerin çoğu salt Unicode olduğundan, bu değişiklik aynı zamanda MFC'yi Windows SDK ile daha paralel halde tutar. Ancak, MFC MBCS kitaplığını kullanmaya devam ederseniz, [Visual Studio 2013 için Multibyte MFC Kütüphanesi'ndeki](https://www.microsoft.com/download/details.aspx?id=40770)MSDN İndirme Merkezi'nden indirebilirsiniz. Visual C++ Yeniden Dağıtılabilir Paketi'nde bu kitaplık halen yer almaktadır.  (Not: MBCS DLL, Visual Studio 2015 ve sonraki yıllarda C++ kurulum bileşenlerine dahildir.

- MFC şeridi için erişilebilirlik değiştirildi.  Tek düzeyli mimari yerine, artık hiyerarşik bir mimari vardır. Hala arayarak `CRibbonBar::EnableSingleLevelAccessibilityMode()`eski davranışı kullanabilirsiniz.

- `CDatabase::GetConnect`yöntem kaldırılır. Güvenliği artırmak için bağlantı dizesi artık şifreli olarak depolanır ve yalnızca gerektiğinde şifresi çözülür; düz metin olarak döndürülemez.  Dize `CDatabase::Dump` yöntemi kullanılarak elde edilebilir.

- `CWnd::OnPowerBroadcast` İmzası değiştirilir. Bu ileti işleyicisinin imzası ikinci parametre olarak bir LPARAM alacak şekilde değiştirilir.

- İmzalar ileti işleyicilerini barındıracak şekilde değiştirilir. Aşağıdaki işlevlerin parametre listeleri yeni eklenen ON_WM_* ileti işleyicilerini kullanacak şekilde değiştirilmiştir:

  - `CWnd::OnDisplayChange`yeni ON_WM_DISPLAYCHANGE makronun ileti haritasında kullanılabilmesi için (WPARAM, LPARAM) yerine (UINT, int, int) olarak değiştirilmiştir.

  - `CFrameWnd::OnDDEInitiate`yeni ON_WM_DDE_INITIATE makrosu ileti haritasında kullanılabilmesi için (WPARAM, LPARAM) yerine (CWnd*, UINT, UNIT) olarak değiştirilmiştir.

  - `CFrameWnd::OnDDEExecute`yeni ON_WM_DDE_EXECUTE makronun ileti haritasında kullanılabilmesi için (WPARAM, LPARAM) yerine (CWnd*, HANDLE) olarak değiştirilmiştir.

  - `CFrameWnd::OnDDETerminate`yeni ON_WM_DDE_TERMINATE makronun ileti haritasında kullanılabilmesi için (WPARAM, LPARAM) yerine parametre olarak (CWnd*) olarak değiştirilmiştir.

  - `CMFCMaskedEdit::OnCut`yeni ON_WM_CUT makronun ileti haritasında kullanılabilecek şekilde (WPARAM, LPARAM) yerine hiçbir parametreye dönüştürülebilir.

  - `CMFCMaskedEdit::OnClear`yeni ON_WM_CLEAR makrosu ileti haritasında kullanılabilsin diye (WPARAM, LPARAM) yerine hiçbir parametreye dönüştürülebilir.

  - `CMFCMaskedEdit::OnPaste`yeni ON_WM_PASTE makronun ileti haritasında kullanılabilecek şekilde (WPARAM, LPARAM) yerine hiçbir parametreye dönüştürülebilir.

- `#ifdef`MFC üstbilgi dosyalarındaki yönergeler kaldırılır. Windows'un desteklenmeyen sürümleriyle (WINVER `#ifdef` &lt; 0x0501) ilgili MFC üstbilgi dosyalarındaki çok sayıda yönerge kaldırılır.

- ATL DLL (atl120.dll) kaldırılır. ATL artık, üst bilgiler ve statik kitaplık (atls.lib) olarak sağlanmaktadır.

- Atlsd.lib, atlsn.lib ve atlsnd.lib kaldırılır. Atls.lib artık, karakter kümesi bağımlılıkları veya hata ayıklamaya/yayınlamaya özgü kod içermez. Unicode/ANSI ve hata ayıklama/yayınlama için aynı çalıştığından, kitaplığın yalnızca tek bir sürümü gereklidir.

- ATL/MFC İzleme aracı ATL DLL ile birlikte kaldırılır ve izleme mekanizması basitleştirilir. Oluşturucu `CTraceCategory` artık bir parametre (kategori adı) alır ve TRACE makroları CRT hata ayıklama raporlama işlevlerini çağırır.

## <a name="visual-studio-2012-breaking-changes"></a>Visual Studio 2012 Breaking Değişiklikler

### <a name="compiler"></a>Derleyici

- `/Yl` Derleyici seçeneği değişti. Varsayılan olarak, derleyici belirli koşullar altında LNK2011 hatalarına yol açabilir bu seçeneği kullanır. Daha fazla bilgi için bkz: [/Yl (Hata Ayıklama Kitaplığı için PCH Başvurusu Enjekte Edin)](../build/reference/yl-inject-pch-reference-for-debug-library.md).

- Enum sınıfı anahtar kelimesi `/clr`kullanılarak **enum** derlenen kodda, ortak bir dil çalışma süresi (CLR) enum değil, C++11 enum tanımlar. Bir CLR enum tanımlamak için, erişilebilirliği hakkında açık olması gerekir.

- Bağımlı bir adı (C++ Dil Standardı uyumluluğu) açıkça dağıtmak için şablon anahtar sözcüğükullanın. Aşağıdaki örnekte, belirsizliği gidermek için vurgulanan şablon anahtar sözcüğü zorunludur. Daha fazla bilgi [için, Bağımlı Türler için Ad Çözümlemesi'ne](../cpp/name-resolution-for-dependent-types.md)bakın.

    ```cpp
    template < typename X = "", typename = "" AY = "">
    struct Container { typedef typename AY::template Rebind< X> ::Other AX; };
    ```

- Aşağıdaki örnekte gösterildiği gibi, tür float sabit ifade artık bir şablon bağımsız değişkenolarak izin verilmez.

    ```cpp
    template<float n=3.14>
    struct B {};  // error C2993: 'float': illegal type for non-type template parameter 'n'
    ```

- `/GS` Komut satırı seçeneğini kullanarak derlenen ve bire bir güvenlik açığı olan kod, aşağıdaki sözde kod örneğinde gösterildiği gibi çalışma zamanında sonlandırma işlemine neden olabilir.

    ```cpp
    char buf[MAX]; int cch; ManipulateString(buf, &cch); // ... buf[cch] = '\0'; // if cch >= MAX, process will terminate
    ```

- x86 yapılar için varsayılan mimari SSE2 olarak değiştirilir; bu nedenle, derleyici SSE yönergeleri yontabilir ve kayan nokta hesaplamaları gerçekleştirmek için XMM kayıtları kullanır. Önceki davranışa geri dönmek istiyorsanız, mimariyi `/arch:IA32` IA32 olarak belirtmek için derleyici bayrağını kullanın.

- [Derleyici, derleyici uyarısı (düzey 4) C4703](../error-messages/compiler-warnings/compiler-warning-level-4-c4703.md) ve C4701 uyarıları daha önce yapmadığı durumlarda verebilir. Derleyici, işaretçi türünde başlatılmamış yerel değişkenlerin kullanımı için daha güçlü denetimler uygular.

- Yeni bağlayıcı bayrağı `/HIGHENTROPYVA` belirtildiğinde, Windows 8 genellikle bellek ayırmalarının 64 bit adresi döndürmesine neden olur. (Windows 8'den önce, bu tür ayırmalar daha sık 2 GB'dan az olan adreslerle döndürülür.) Bu değişiklik, varolan koddaki işaretçi truncation hatalarını ortaya çıkarabilir. Varsayılan olarak, bu anahtar açık. Bu davranışı devre dışı `/HIGHENTROPYVA:NO`kılabilir.

- Yönetilen derleyici (Visual Basic/C#) `/HIGHENTROPYVA` yönetilen yapılar için de destekler.  Ancak, bu durumda, `/HIGHENTROPYVAswitch` varsayılan olarak kapalıdır.

### <a name="ide"></a>IDE

- C++/CLI'de Windows Forms uygulamaları oluşturmamanızı öneririz, ancak varolan C++/CLI UI uygulamalarının bakımı desteklenir. Bir Windows Forms uygulaması veya başka bir .NET UI uygulaması oluşturmanız gerekiyorsa, C# veya Visual Basic'i kullanın. C++/CLI'yi yalnızca birlikte çalışabilirlik amacıyla kullanın.

### <a name="parallel-patterns-library-and-concurrency-runtime-library"></a>Paralel Desenler Kitaplığı ve Eşzamanlılık Çalışma Zamanı Kitaplığı

Numaralandırma `SchedulerType` `UmsThreadDefault` amortismana sokulmuş. Belirtimi, amortismana harcamış bir uyarı `UmsThreadDefault` üretir `ThreadScheduler`ve dahili olarak geri eşler.

### <a name="standard-library"></a>Standart Kitaplık

- C++98/03 ve C++11 standartları arasındaki son dakika değişikliğinin `make_pair()` ardından, `make_pair<int, int>(x, y)` çağırmak için açık şablon bağımsız değişkenleri kullanmak - görsel stüdyo 2012'de Visual C++'da genellikle derleme yapmaz. Çözüm her zaman `make_pair()` açık şablon bağımsız değişkenleri olmadan aramaktır - gibi `make_pair(x, y)`. Açık şablon bağımsız değişkenler sağlamak işlevin amacını yener. Ortaya çıkan tür üzerinde hassas denetime `pair` ihtiyaç `make_pair` duyuyorsanız, `pair<short, short>(int1, int2)`aşağıdaki gibi .

- C++98/03 ve C++11 standartları arasındaki bir diğer kırılma değişimi: A örtülü olarak B ve B'ye dönüştürülebilir olduğunda, A dolaylı olarak C,C++98/03 ve `pair<A, X>` Visual Studio 2010'a dönüştürülebilir değildir (örtülü veya açık olarak) `pair<C, X>`. (Diğer tip, X, burada ilgi değildir ve çifti ilk türüne özgü değildir.) Visual Studio 2012'deki C++ derleyicisi, A'nın dolaylı olarak C'ye dönüştürülemeyeceğini algılar ve çift dönüşümünü aşırı yük çözünürlüğünden kaldırır. Bu değişiklik birçok senaryo için olumludur. Örneğin, aşırı `func(const pair<int, int>&)` yükleme `func(const pair<string, string>&)`ve `func()` , `pair<const char *, const char *>` ve arama ile bu değişiklik ile derlenir. Ancak, bu değişiklik, agresif çift dönüşümlerine dayanan kodu bozar. Bu tür kod genellikle dönüştürmenin bir bölümünü açıkça gerçekleştirerek düzeltilebilir(örneğin, `make_pair(static_cast<B>(a), x)` bekleyen `pair<C, X>`bir işleve geçerek.

- Visual Studio 2010 simüle variadik şablonlar-örneğin, `make_shared<T>(arg1, arg2, argN)`- 10 bağımsız değişkenler sınırına kadar, önişlemci makine ile aşırı yükleri ve uzmanlıkları damgalayarak. Visual Studio 2012'de, bu sınır, kullanıcıların çoğu için derleme sürelerini ve derleyici bellek tüketimini iyileştirmek için beş bağımsız değişkene indirgenir. Ancak, _VARIADIC_MAX'yi proje genelinde 10 olarak açıkça tanımlayarak önceki sınırı ayarlayabilirsiniz.

- C++11 17.6.4.3.1 [makro.adlar]/2, C++ Standart Kitaplık üstbilgisi eksbazında anahtar kelimelerin makro değişimini yasaklar. Üstbilgi, makro değiştirilen anahtar kelimeleri algılarsa derleyici hataları yayıyor. (_ALLOW_KEYWORD_MACROS tanımlama, bu tür kodların derlenmesine izin verir, ancak bu kodun kullanımını şiddetle öneriz.) Bir istisna olarak, `new` üstbilgi kullanarak kendilerini `#pragma push_macro("new")` / `#undef new` / `#pragma pop_macro("new")`kapsamlı bir şekilde savunduklarından, makro formu varsayılan olarak izin verilir. _ENFORCE_BAN_OF_MACRO_NEW tanımlamak tam olarak adının ima ettiği şeyi yapar.

- Çeşitli optimizasyonlar ve hata ayıklama denetimleri uygulamak için, C++ Standart Kitaplığı uygulaması Visual Studio sürümleri arasında ikili uyumluluğu kasıtlı olarak bozar (2005, 2008, 2010, 2012). C++ Standart Kitaplığı kullanıldığında, farklı sürümler kullanılarak derlenen nesne dosyaları ve statik kitaplıkların tek bir ikili (EXE veya DLL) halinde karıştırılması yasaklanır ve C++ Standart Kitaplığı nesnelerinin farklı sürümler kullanılarak derlenen ikili dosyalar arasında geçişini yasaklar. Nesne dosyalarının ve statik kitaplıkların karıştırılması (Visual Studio 2010 kullanılarak derlenen C++ Standart Kitaplığı kullanılarak Visual Studio 2012'de C++ derleyicisi kullanılarak derlenen ler, _MSC_VER derleyicinin ana sürümünü içeren makronun (Studio Visual 2012'de Visual C++ için 1700) bulunduğu _MSC_VER uyumsuzluk hakkında bağlantı hataları yayır. Bu denetim DLL karıştırma algılayamadı ve Visual Studio 2008 veya daha önce içeren karıştırma algılayamıyor.

- Visual Studio 2010'da uygulanan _ITERATOR_DEBUG_LEVEL uyuşmazlıkları algılamanın yanı sıra Visual Studio 2012'deki C++ derleyicisi Runtime Library uyumsuzluklarını algılar. Bu uyuşmazlıklar derleyici `/MT` seçenekleri (statik sürüm), `/MTd` (statik `/MD` hata ayıklama), `/MDd` (dinamik sürüm) ve (dinamik hata ayıklama) karışık olduğunda oluşur.

- `operator<()`, `operator>()` `operator<=()`, `operator>=()` , ve daha `std::unordered_map` önce `stdext::hash_map` konteyner aileleri ve aileleri için kullanılabilir, ancak uygulamaları yararlı değildi. Bu standart dışı işleçler Visual Studio 2012'de Visual C++ ile kaldırılmıştır. `operator==()` Ayrıca, `operator!=()` `std::unordered_map` aile ve uygulama `stdext::hash_map` aile kapsayacak şekilde genişletilmiştir. `stdext::hash_map` (Ailenin yeni kodda kullanılmasını önlemenizi öneririz.)

- C++11 22.4.1.4 [locale.codecvt] bu `codecvt::length()` `codecvt::do_length()` ve değiştirilebilir `stateT&` parametreleri almalıdır belirtir, ancak Visual `const stateT&`Studio 2010 aldı . Visual Studio 2012'deki C++ `stateT&` derleyicisi standart olarak zorunlu olarak alır. Bu fark, sanal işlevi `do_length()`geçersiz kılmaya çalışan herkes için önemlidir.

### <a name="crt"></a>CRT

- Yeni ve malloc() için kullanılan C Runtime (CRT) yığını artık özel değildir. CRT artık işlem yığınını kullanır. Bu, bir DLL boşaltıldığında yığının yok olmadığı anlamına gelir, bu nedenle CRT'ye statik olarak bağlanan DLL'ler, DLL kodu tarafından ayrılan belleğin boşaltılmadan önce temizlendiğinden emin olmalıdır.

- İşlev `iscsymf()` negatif değerlerle öne sürer.

- Yapı, `threadlocaleinfostruct` yerel işlevlerde yapılan değişiklikleri karşılamak üzere değiştirildi.

- Gibi karşılık gelen içsel leri olan `memxxx()`CRT işlevleri intrin.h `strxxx()` kaldırılır. Yalnızca bu işlevler için intrin.h'yi dahil ettiyseniz, artık ilgili CRT üstbilgilerini eklemeniz gerekir.

### <a name="mfc-and-atl"></a>MFC ve ATL

- Kaldırıldı Fusion desteği (afxcomctl32.h); bu nedenle, \<afxcomctl32.h> tanımlanan tüm yöntemler kaldırılmıştır. Başlık dosyaları \<afxcomctl32.h \<> ve afxcomctl32.inl> silindi.

- Adını " `CDockablePane::RemoveFromDefaultPaneDividier` olarak `CDockablePane::RemoveFromDefaultPaneDivider`değiştirdim.

- LPCTSTR `CFileDialog::SetDefExt` kullanmak için imza değiştirildi; bu nedenle, Unicode yapılar etkilenir.

- Eski ATL izleme kategorileri kaldırıldı.

- Bir `const CRect`almak `CBasePane::MoveWindow` için imzadeğiştirildi .

- `CMFCEditBrowseCtrl::EnableBrowseButton`İmzadeğiştirildi.

- `CMFCBaseTabCtrl` içinden `m_fntTabs` ve `m_fntTabsBold` kaldırıldı.

- `CMFCRibbonStatusBarPane` Oluşturuculara bir parametre eklendi. (Varsayılan bir parametredir ve bu nedenle kaynak kırmıyor.)

- `CMFCRibbonCommandsListBox` Oluşturucuya bir parametre eklendi. (Varsayılan bir parametredir ve bu nedenle kaynak kırmıyor.)

- `AFXTrackMouse` API (ve ilgili zamanlayıcı proc) kaldırıldı. Bunun yerine Win32 `TrackMouseEvent` API'sını kullanın.

- `CFolderPickerDialog` Oluşturucuya bir parametre eklendi. (Varsayılan bir parametredir ve bu nedenle kaynak kırmıyor.)

- `CFileStatus`yapı boyutu değiştirildi: `m_attribute` Üye BYTE'den DWORD'ye (döndürülen `GetFileAttributes`değerle eşleşecek şekilde) değiştirildi.

- `CRichEditCtrl`ve `CRichEditView` Unicode oluşturur RICHEDIT_CLASS (RichEdit 3.0 kontrolü) yerine MSFTEDIT_CLASS (RichEdit 4.1 denetimi) kullanın.

- Windows `AFX_GLOBAL_DATA::IsWindowsThemingDrawParentBackground` Vista, Windows 7 ve Windows 8'de her zaman DOĞRU olduğu için kaldırıldı.

- Windows `AFX_GLOBAL_DATA::IsWindowsLayerSupportAvailable` Vista, Windows 7 ve Windows 8'de her zaman DOĞRU olduğu için kaldırıldı.

- Kaldırıldı. `AFX_GLOBAL_DATA::DwmExtendFrameIntoClientArea` Doğrudan Windows Vista, Windows 7 ve Windows 8'den Windows API'yi arayın.

- Kaldırıldı. `AFX_GLOBAL_DATA::DwmDefWindowProc` Doğrudan Windows Vista, Windows 7 ve Windows 8'den Windows API'yi arayın.

- Ad `AFX_GLOBAL_DATA::DwmIsCompositionEnabled` çakışmasını ortadan kaldırmak için `IsDwmCompositionEnabled` yeniden adlandırıldı.

- Bir dizi MFC dahili zamanlayıcıiçin tanımlayıcıları değiştirdi ve tanımları afxres.h'ye (AFX_TIMER_ID_*) taşıdı.

- ON_WM_EXITSIZEMOVE makrosuyla aynı fikirde olmak için yöntemin `OnExitSizeMove` imzasını değiştirdi:

  - `CFrameWndEx`

  - `CMDIFrameWndEx`

  - `CPaneFrameWnd`

- ON_WM_DWMCOMPOSITIONCHANGED makroile aynı `OnDWMCompositionChanged` fikirde olmak için adı ve imzası değiştirildi:

  - `CFrameWndEx`

  - `CMDIFrameWndEx`

  - `CPaneFrameWnd`

- ON_WM_MOUSELEAVE makrosuyla aynı fikirde olmak için yöntemin `OnMouseLeave` imzasını değiştirdi:

  - `CMFCCaptionBar`

  - `CMFCColorBar`

  - `CMFCHeaderCtrl`

  - `CMFCProperySheetListBox`

  - `CMFCRibbonBar`

  - `CMFCRibbonPanelMenuBar`

  - `CMFCRibbonRichEditCtrl`

  - `CMFCSpinButtonCtrl`

  - `CMFCToolBar`Bu Metni Değiştirme

  - `CMFCToolBarComboBoxEdit`

  - `CMFCToolBarEditCtrl`

  - `CMFCAutoHideBar`

- ON_WM_POWERBROADCAST makroile `OnPowerBroadcast` aynı fikirde imza değiştirildi:

  - `CFrameWndEx`

  - `CMDIFrameWndEx`

- ON_WM_STYLECHANGED makroile `OnStyleChanged` aynı fikirde imza değiştirildi:

  - `CMFCListCtrl`

  - `CMFCStatusBar`

- Dahili `FontFamilyProcFonts`yöntemin `FontFamalyProcFonts` adı .

- Bazı durumlarda `CString` bellek sızıntılarını ortadan kaldırmak için çok sayıda küresel statik nesne kaldırıldı (#defines ile değiştirildi) ve aşağıdaki sınıf üye değişkenleri:

  - `CKeyBoardManager::m_strDelimiter`

  - `CMFCPropertyGridProperty::m_strFormatChar`

  - `CMFCPropertyGridProperty::m_strFormatShort`

  - `CMFCPropertyGridProperty::m_strFormatLong`

  - `CMFCPropertyGridProperty::m_strFormatUShort`

  - `CMFCPropertyGridProperty::m_strFormatULong`

  - `CMFCPropertyGridProperty::m_strFormatFloat`

  - `CMFCPropertyGridProperty::m_strFormatDouble`

  - `CMFCToolBarImages::m_strPngResType`

  - `CMFCPropertyGridProperty::m_strFormat`

- Hızlandırıcı delimiter parametresinin imzasını `CKeyboardManager::ShowAllAccelerators` değiştirdi ve kaldırıldı.

- Eklendi `CPropertyPage::GetParentSheet`, ve `CPropertyPage` sınıfta, yerine `GetParent` ebeveyn veya bir büyükanne penceresi olabilir doğru üst sayfa `CPropertyPage`penceresi almak için çağrı . 'yi aramak `GetParentSheet` yerine `GetParent`kodunuzu değiştirmeniz gerekebilir

- ATLBASE'de dengesiz #pragma uyarısı(itme) düzeltildi. Uyarıların yanlış devre dışı bırakılmış olması nedeniyle H. Bu uyarılar Artık ATLBASE'den sonra doğru şekilde etkinleştirilir. H ayrıştı.

- D2D ile ilgili yöntemleri AFX_GLOBAL_DATA'dan _AFX_D2D_STATE taşıdı:

  - `GetDirectD2dFactory`

  - `GetWriteFactory`

  - `GetWICFactory`

  - `InitD2D`

  - `ReleaseD2DRefs`

  - `IsD2DInitialized`

  - `D2D1MakeRotateMatrix`

  - Aramak yerine, örneğin, `afxGlobalData.IsD2DInitialized`. `AfxGetD2DState->IsD2DInitialized`

- Eski ATL* kaldırıldı. \atlmfc\include\ klasöründen CPP dosyaları.

- Gereksinimleri `afxGlobalData` karşılamak `DLLMain` için, CRT başlatma zamanında yerine isteğe bağlı başlatma taşındı.

- `RemoveButtonByIndex` Yöntem sınıfa `CMFCOutlookBarPane` eklendi.

- `IsFrequentlyUsedCmd`Düzeltildi. `CMFCCmdUsageCount::IsFreqeuntlyUsedCmd`

- Için birkaç örnek `RestoreOriginalstate` `RestoreOriginalState (CMFCToolBar, CMFCMenuBar, CMFCOutlookBarPane)`düzeltildi.

- Kullanılmayan yöntemler : `CDockablePane` `SetCaptionStyle`, `IsDrawCaption` `IsHideDisabledButtons`, `GetRecentSiblingPaneInfo`, `CanAdjustLayout`, ve .

- Statik `CDockablePane` üye `m_bCaptionText` değişkenler `m_bHideDisabledButtons`kaldırıldı ve .

- 'ye `CMFCFontComboBox`geçersiz `DeleteString` kılma yöntemi eklendi

- Kullanılmayan yöntemler kaldırıldı `CPane` `GetMinLength` : `IsLastPaneOnLastRow`ve .

- Adı `CPane::GetDockSiteRow(CDockingPanesRow *)` `CPane::SetDockSiteRow`.

## <a name="visual-studio-2010-breaking-changes"></a>Visual Studio 2010 Breaking Değişiklikler

### <a name="compiler"></a>Derleyici

- **Otomatik** anahtar kelimenin yeni bir varsayılan anlamı vardır. Eski anlamın kullanımı nadir olduğundan, çoğu uygulama bu değişiklikten etkilenmez.

- Yeni **static_assert** anahtar kelimesi tanıtılır ve bu da kodunuzda bu ada göre zaten bir tanımlayıcı varsa bir ad çakışması neden olur.

- Yeni lambda gösterimi desteği, IDL uuid özniteliği içinde tırnak içinde tırnak içinde bir GUID kodlama desteği hariç tutar.

- .NET Framework 4, bir işlemi kurtarılamaz bozuk bir durumda bırakan istisnalar olan bozuk durum özel durumları kavramını tanımaktadır. Varsayılan olarak, diğer tüm özel durumları yakalayan /EHa derleyici seçeneğinde bile bozuk bir durum özel durum durumu yakalayamadığınızı.                 Bozuk bir durum özel durumunu açıkça yakalamak\_için __try _except deyimleri kullanın. Veya bozuk durum özel durumlarını yakalamak için bir işlevi etkinleştirmek için [HandledProcessCorruptedStateExceptions] özniteliğini uygulayın.  Bu değişiklik, öncelikle bozuk bir durum özel durum yakalamak zorunda kalabilir sistem programcıları etkiler. Sekiz istisna STATUS_ACCESS_VIOLATION, STATUS_STACK_OVERFLOW, EXCEPTION_ILLEGAL_INSTRUCTION, EXCEPTION_IN_PAGE_ERROR, EXCEPTION_INVALID_DISPOSITION, EXCEPTION_NONCONTINUABLE_EXCEPTION, EXCEPTION_PRIV_INSTRUCTION, STATUS_UNWIND_CONSOLIDATE.                 Bu özel durumlar hakkında daha fazla bilgi için [GetExceptionCode](/windows/win32/Debug/getexceptioncode) makrosu'na bakın.

- Arabelleğe karşı gözden geçirilmiş `/GS` derleyici seçeneği önceki sürümlerden daha kapsamlı taşmaları. Bu sürüm, performansı düşürebilecek yığına ek güvenlik denetimleri ekleyebilir. Derleyiciye `__declspec(safebuffers)` belirli bir işlev için güvenlik denetimleri eklememesi için talimat vermek için yeni anahtar sözcüğü kullanın.

- Hem `/GL` (Tüm Program Optimizasyonu) hem `/clr` de (Ortak Dil Çalışma Süresi Derlemesi) `/GL` derleyici seçenekleriyle derlerseniz, seçenek yoksayılır. Derleyici seçeneklerinin birleşimi çok az fayda sağladığından bu değişiklik yapıldı. Bu değişikliğin bir sonucu olarak, yapının performansı artırılır.

- Varsayılan olarak, visual studio 2010'da trigraphs desteği devre dışı bırakılır. Trigraphs desteğini etkinleştirmek için `/Zc:trigraphs` derleyici seçeneğini kullanın. Bir trigraph iki ardışık soru işaretleri ("??") ve ardından benzersiz bir üçüncü karakter oluşur. Derleyici, bir trigraph'ı karşılık gelen noktalama işareti karakteriyle değiştirir. Örneğin, derleyici trigraph'ı `??=` '#' karakteriyle değiştirir. C kaynak dosyalarında, bazı noktalama işaretleri için uygun grafik gösterimleri içermeyen bir karakter kümesi kullanan üç grafikler kullanın.

- Bağlayıcı artık Windows 98 için en iyi duruma iyiduruma desteklemez. (Optimizasyonlar) `/OPT` seçeneği, belirtirseniz `/OPT:WIN98` zaman derleme hatası `/OPT:NOWIN98`üretir veya .

- RuntimeLibrary ve DebugInformationFormat yapı sistemi özellikleri tarafından belirtilen varsayılan derleyici seçenekleri değiştirildi. Varsayılan olarak, bu yapı özellikleri Visual C++ sürümleri 7.0 ile 10.0 tarafından oluşturulan projelerde belirtilir. Visual C++ 6.0 tarafından oluşturulan bir projeyi geçişe çevirirseniz, bu özellikler için bir değer belirtip belirtmemeyi düşünün.

- Visual Studio 2010 yılında, RuntimeLibrary`/MD`= MultiThreaded ( )`/Zi`ve DebugInformationFormat = ProgramDatabase ( ). Visual C++ 9.0'da RuntimeLibrary =`/MT`MultiThreaded ( ) ve Hata AyıklamaBilgi Biçimi = Devre Dışı bırakılır.

### <a name="clr"></a>CLR

- Microsoft C# ve Visual Basic derleyicileri artık birincil interop derlemesi (no-PIA) üretebilir. No-PIA derlemesi, ilgili birincil interop derlemesi (PIA) dağıtımı olmadan COM türlerini kullanabilir. Visual C# veya Visual Basic tarafından üretilen NO-PIA derlemelerini tüketirken, kitaplığı kullanan herhangi bir PIA derlemesi göndermeden önce derleme komutundaki PIA derlemesi'ne başvurmanız gerekir.

### <a name="visual-studio-c-projects-and-msbuild"></a>Visual Studio C++ projeleri ve MSBuild

- Visual Studio C++ projeleri artık MSBuild aracına dayanmaktadır. Sonuç olarak, proje dosyaları yeni bir XML dosya biçimi ve .vcxproj dosya soneki kullanır. Visual Studio 2010, Visual Studio'nun önceki sürümlerindeki proje dosyalarını otomatik olarak yeni dosya biçimine dönüştürür. Varolan bir proje, önceki yapı aracına, VCBUILD.exe'ye veya proje dosyası sonekine, .vcproj'a bağlıysa etkilenir.

- Önceki sürümlerde, Visual C++ özellik sayfalarının geç değerlendirilmesini desteklemiştin. Örneğin, bir üst özellik sayfası bir alt özellik sayfasını içe aktarabilir ve üst öğe diğer değişkenleri tanımlamak için alt öğede tanımlanan bir değişken kullanabilir. Geç değerlendirme, alt özellik sayfası içe aktarılmadan önce bile ebeveynin alt değişkenini kullanmasını sağladı. Visual Studio 2010'da, MSBuild yalnızca erken değerlendirmeyi desteklediği için bir proje sayfası değişkeni tanımlanmadan kullanılamaz.

### <a name="ide"></a>IDE

- Uygulama sonlandırma iletişim kutusu artık bir uygulamayı sona erdirmez. Önceki sürümlerde, `abort()` veya `terminate()` işlev bir uygulamanın perakende oluşturma kapalı, C Run-Time Kitaplığı bir konsol penceresinde veya iletişim kutusunda bir uygulama sonlandırma iletisi görüntülenir. İletikısmen şöyle dedi: "Bu uygulama, Runtime'dan bunu alışılmadık bir şekilde sonlandırmasını istedi. Daha fazla bilgi için lütfen başvurunun destek ekibiyle iletişime geçin." Windows daha sonra genellikle Windows Hata Bildirimi (Dr. Watson) iletişim kutusu veya Visual Studio hata ayıklayıcı olan geçerli sonlandırma işleyicisi görüntülenen çünkü uygulama sonlandırma iletisi gereksiz oldu. Visual Studio 2010'dan itibaren C Run-Time Kitaplığı iletiyi görüntülemez. Ayrıca, çalışma zamanı hata ayıklama başlamadan önce uygulamanın sona ermesini engeller. Bu, yalnızca uygulama sonlandırma iletisinin önceki davranışına bağlıysanız bir kesme değişikliğidir.

- Özellikle Visual Studio 2010 için, IntelliSense C++/CLI kodu veya öznitelikleri için çalışmıyor, **Tüm Başvuruları Bul** yerel değişkenler için çalışmıyor ve Code Model, alınan derlemelerden tür adlarını almıyor veya tam nitelikli adlarına türleri çözümlemiyor.

### <a name="libraries"></a>Kitaplıklar

- SafeInt sınıfı Visual C++'a dahildir ve artık ayrı bir indirmede değildir. Bu, yalnızca "SafeInt" adında bir sınıf geliştirdiyseniz bir kırılma değişikliğidir.

- Kitaplıkdağıtım modeli artık dinamik bir bağlantı kitaplığı belirli bir sürümünü bulmak için bildirimleri kullanır. Bunun yerine, her dinamik bağlantı kitaplığı adını kendi sürüm numarasını içerir ve kitaplığı bulmak için bu adı kullanın.

- Visual Studio'nun önceki sürümlerinde çalışma zamanı kitaplıklarını yeniden oluşturabilirsiniz. Visual Studio 2010 artık C çalışma zamanı kitaplığı dosyalarının kendi kopyalarını oluşturmayı desteklemez.

### <a name="standard-library"></a>Standart Kitaplık

- Yineleyici \<> üstbilgi artık diğer birçok üstbilgi dosyası tarafından otomatik olarak dahil edilmiştir. Bunun yerine, üstbilgide tanımlanan bağımsız yinelemeler için destek gerekiyorsa, bu üstbilgi açıkça ekleyin. Varolan bir proje, önceki yapı aracına, VCBUILD.exe'ye veya proje dosyası sonekine, .vcproj.iterator'a bağlıysa etkilenir.

- \<Algoritma> üstbilgide, checked_*\* ve unchecked_ işlevleri kaldırılır. Ve \<yineleyici>> üstbilgide, `checked_iterator` sınıf kaldırılır ve `unchecked_array_iterator` sınıf eklenmiştir.

- Oluşturucu `CComPtr::CComPtr(int)` kaldırılır. Bu oluşturucu, `CComPtr` null makrodan bir nesnenin oluşturulmasına izin verdi, ancak gereksizdi ve sıfır olmayan tamsayılardan anlamsız yapılara izin verdi.

   A `CComPtr` hala 0 olarak tanımlanan NULL, inşa edilebilir, ancak gerçek 0 dışında bir tamsayı inşa edilirse başarısız olur. Bunun yerine **nullptr** kullanın.

- `ctype` Aşağıdaki üye işlevler `ctype::_Do_narrow_s`kaldırıldı: `ctype::_narrow_s`, , `ctype::_widen_s` `ctype::_Do_widen_s`, . Bir uygulama bu üye işlevlerden birini kullanıyorsa, bunu ilgili `ctype::do_narrow`güvenli `ctype::do_widen` `ctype::narrow`olmayan `ctype::widen`sürümle değiştirmeniz gerekir: , , .

### <a name="crt-mfc-and-atl-libraries"></a>CRT, MFC ve ATL Kitaplıkları

- Kullanıcıların CRT, MFC ve ATL kitaplıklarını oluşturması için destek kaldırıldı. Örneğin, uygun bir NMAKE dosyası sağlanmaz. Ancak, kullanıcılar hala bu kitaplıklar için kaynak koduna erişebilir. Microsoft'un bu kitaplıkları oluşturmak için kullandığı MSBuild seçeneklerini açıklayan bir belge büyük olasılıkla Visual C++ Team Blog'da yayınlanacaktır.

- IA64 için MFC desteği kaldırıldı. Ancak, IA64'te CRT ve ATL desteği hala sağlanmaktadır.

- Ordinals artık MFC modül tanımlı (.def) dosyalarında yeniden kullanılmaz. Bu değişiklik, ordinals küçük sürümleri arasında farklı olmayacak ve hizmet paketleri ve hızlı düzeltme mühendisliği sürümleri için ikili uyumluluk geliştirilecektir anlamına gelir.

- Sınıfa yeni bir `CDocTemplate` sanal işlev eklendi. Bu yeni sanal işlev [CDocTemplate](../mfc/reference/cdoctemplate-class.md)Sınıfı'dır. Önceki sürümü `OpenDocumentFile` nde iki parametre vardı. Yeni sürümüüç parametre vardır. Yeniden başlatma yöneticisini desteklemek için, `CDocTemplate` türetilen herhangi bir sınıfın üç parametreye sahip sürümü uygulaması gerekir. Yeni parametre `bAddToMRU`.

### <a name="macros-and-environment-variables"></a>Makrolar ve Çevre Değişkenleri

- ortam değişkeni __MSVCRT_HEAP_SELECT artık desteklenmiyordu. Bu ortam değişkeni kaldırılır ve değiştirme yoktur.

### <a name="microsoft-macro-assembler-reference"></a>Microsoft Macro Assembler Başvurusu

- Microsoft Makro Assembler Başvuru derleyicisinden çeşitli yönergeler kaldırıldı. Kaldırılan direktifler `.186`, `.286` `.286P`, `.287` `.8086`, `.8087`, `.NO87`, , ve .

## <a name="visual-studio-2008-breaking-changes"></a>Visual Studio 2008 Breaking Değişiklikler

### <a name="compiler"></a>Derleyici

- Windows 95, Windows 98, Windows ME ve Windows NT platformları artık desteklenmez. Bu işletim sistemleri hedeflenen platformlar listesinden kaldırıldı.

- Derleyici artık Doğrudan ATL Server ile ilişkili birden çok öznitelikleri destekler. Aşağıdaki öznitelikler artık desteklenmez:

  - perf_counter

  - perf_object

  - Perfmon

  - request_handler

  - soap_handler

  - soap_header

  - soap_method

  - tag_name

### <a name="visual-studio-c-projects"></a>Visual Studio C++ projeleri

- Visual Studio'nun önceki sürümlerinden projeleri yükseltirken, WINVER ve _WIN32_WINNT makrolarını 0x0500'den büyük veya eşit olacak şekilde değiştirmeniz gerekebilir.

- Visual Studio 2008'den başlayarak, yeni proje sihirbazınc++ SQL Server projesi oluşturma seçeneği yoktur. Visual Studio'nun önceki bir sürümünü kullanarak oluşturulan SQL Server projeleri yine de derlenecek ve doğru çalışacaktır.

- Windows API üstbilgi dosyası Winable.h kaldırıldı. Bunun yerine Winuser.h ekleyin.

- Windows API kitaplığı Rpcndr.lib kaldırıldı. Yerine rpcrt4.lib ile bağlantı.

### <a name="crt"></a>CRT

- Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 desteği kaldırıldı.

- Aşağıdaki genel değişkenler kaldırıldı:

  - _osplatform

  - _osver

  - _winmajor

  - _winminor

  - _winver

- Aşağıdaki işlevler kaldırıldı. Windows API `GetVersion` işlevlerini `GetVersionEx` kullanın veya bunun yerine:

  - _get_osplatform

  - _get_osver

  - _get_winmajor

  - _get_winminor

  - _get_winver

- SAL Ek Açıklamaları için sözdizimi değişti. Daha fazla bilgi için [SAL Ek Açıklamaları'na](../c-runtime-library/sal-annotations.md)bakın.

- IEEE filtresi artık SSE 4.1 yönerge setini destekler. Daha fazla bilgi için [_fpieee_flt](../c-runtime-library/reference/fpieee-flt.md)_fpieee_flt bakın.

- Visual Studio ile gönderi yapan C Run-Time Kitaplıkları artık DLL msvcrt.dll sistemine bağlı değildir.

### <a name="standard-library"></a>Standart Kitaplık

- Windows 95, Windows 98, Windows Millennium Edition ve Windows NT 4.0 desteği kaldırıldı.

- Tanımlı _HAS_ITERATOR_DEBUGGING hata ayıklama modunda derlenirken (Visual Studio 2010'dan sonra [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) tarafından yerini alan) bir uygulama, bir yineleyici temel kapsayıcının sınırlarını aşmaya veya decrement etmeye çalıştığında bunu ileri sürecektir.

- Yığın Sınıfının üye değişkeni c artık korumalı olarak bildirilir. Daha önce, bu üye değişken genel olarak ilan edildi.

- Davranışı `money_get::do_get` değişti. Daha önce, bir parasal tutarı, daha fazla kesir `frac_digits`basamaklı `do_get` ayrıştırken, hepsini tüketmek için kullanılır. Şimdi, `do_get` çoğu `frac_digits` karakter tükettikten sonra ayrışma durur.

### <a name="atl"></a>ATL

- ATL CRT'ye bağımlılık olmadan oluşturulamaz. Visual Studio'nun önceki sürümlerinde, bir ATL projesini CRT'ye en az bağımlı hale getirmek için #define ATL_MIN_CRT kullanabilirsiniz. Visual Studio 2008'de, ATL_MIN_CRT tanımlanıp tanımlanmadığına bakılmaksızın tüm ATL projeleri CRT'ye en az bağlıdır.

- ATL Server codebase CodePlex'te paylaşılan bir kaynak projesi olarak yayımlanmıştır ve Visual Studio'nun bir parçası olarak yüklenmemiştir. Atlenc.h'den veri kodlama ve kod çözme sınıfları ile atlutil.h ve atlpath.h'deki yardımcı işlevler ve sınıflar tutulmuştur ve artık ATL kitaplığının bir parçasıdır. ATL Server ile ilişkili çeşitli dosyalar artık Visual Studio'nun bir parçası değildir.

- Bazı işlevler artık DLL'ye dahil değildir. Bunlar hala alma kitaplığında bulunmaktadır. Bu, işlevleri statik olarak kullanan kodu etkilemez. Yalnızca bu işlevleri dinamik olarak kullanan kodu etkiler.

- makrolar PROP_ENTRY ve PROP_ENTRY_EX, güvenlik nedenleriyle PROP_ENTRY_TYPE ve PROP_ENTRY_TYPE_EX makrolarla değiştirildi.

### <a name="atlmfc-shared-classes"></a>ATL/MFC Paylaşılan Sınıfları

- ATL CRT'ye bağımlılık olmadan oluşturulamaz. Visual Studio'nun önceki sürümlerinde, bir ATL projesini CRT'ye en az bağımlı hale getirmek için kullanabilirsiniz. `#define ATL_MIN_CRT` Visual Studio 2008'de, ATL_MIN_CRT tanımlanıp tanımlanmadığına bakılmaksızın tüm ATL projeleri CRT'ye en az bağlıdır.

- ATL Server codebase CodePlex'te paylaşılan bir kaynak projesi olarak yayımlanmıştır ve Visual Studio'nun bir parçası olarak yüklenmemiştir. Atlenc.h'den veri kodlama ve kod çözme sınıfları ile atlutil.h ve atlpath.h'deki yardımcı işlevler ve sınıflar tutulmuştur ve artık ATL kitaplığının bir parçasıdır. ATL Server ile ilişkili çeşitli dosyalar artık Visual Studio'nun bir parçası değildir.

- Bazı işlevler artık DLL'ye dahil değildir. Bunlar hala alma kitaplığında bulunmaktadır. Bu, işlevleri statik olarak kullanan kodu etkilemez. Yalnızca bu işlevleri dinamik olarak kullanan kodu etkiler.

### <a name="mfc"></a>MFC

- `CTime`Sınıf: `CTime` Sınıf artık 1/1/1900 C.E.'den itibaren tarihleri kabul eder. yerine 1/1/1970 C.E.

- MFC iletişim kutularındaki denetimlerin sekme sırası: Sekme sırasına Bir MFC ActiveX denetimi eklenirse, MFC iletişim kutusundaki birden çok denetimin doğru sekme sırası bozulrılır. Bu değişiklik bu sorunu düzeltir.

   Örneğin, ActiveX denetimi ve birkaç denetim denetimi olan bir MFC iletişim uygulaması oluşturun. ActiveX denetimini düzen denetimlerinin sekme sırasının ortasına yerleştirin. Uygulamayı başlatın, sekme sırası ActiveX denetiminden sonra olan bir düzen denetimini tıklatın, ardından sekme. Bu değişiklikten önce, sekme sırasına göre bir sonraki düzen denetimi yerine ActiveX denetimini izleyen denetim edin denetimine gitti.

- `CFileDialog`Sınıf: `CFileDialog` Sınıf için özel şablonlar otomatik olarak Windows Vista'ya taşınabilir. Bunlar hala kullanılabilir, ancak ek işlevsellik veya Windows Vista tarzı iletişim kutuları görünüyor olmayacaktır.

- `CWnd`Sınıf `CFrameWnd` ve Sınıf: Yöntem `CWnd::GetMenuBarInfo` kaldırıldı.

   Yöntem `CFrameWnd::GetMenuBarInfo` artık sanal olmayan bir yöntemdir. Daha fazla bilgi için Windows SDK'daki **GetMenuBarInfo Fonksiyonu'na** bakın.

- MFC ISAPI desteği: MFC artık Internet Server Application Programming Interface (ISAPI) ile uygulama oluşturmayı desteklemez. Bir ISAPI uygulaması oluşturmak istiyorsanız, doğrudan ISAPI uzantılarını arayın.

- Deprecated ANSI API'leri: Çeşitli MFC yöntemlerinin ANSI sürümleri amortismana hazırdır. Gelecekteki uygulamalarınızda bu yöntemlerin Unicode sürümlerini kullanın. Daha fazla bilgi **için Windows Vista Ortak Denetimleri Için Gereksinimleri Oluştur'a**bakın.

## <a name="visual-studio-2005-breaking-changes"></a>Visual Studio 2005 Breaking Değişiklikler

### <a name="crt"></a>CRT

- Birçok işlev küçümsülmektedir. **Bkz. Amortismana Kılmış CRT Fonksiyonları.**

- Birçok işlev artık parametrelerini doğrulayarak geçersiz parametreler verilirse yürütmeyi durdurur. Bu doğrulama, geçersiz parametreleri geçen ve işlevleri yoksayan veya yalnızca bir hata kodu döndüren kod kırabilir. **Bkz. Parametre Doğrulama.**

- Dosya tanımlayıcı değeri -2 artık, konsol `stdout` penceresi `stderr` olmayan bir Windows uygulamasında, örneğin çıktı için kullanılamadı görülmek için kullanılır. Kullanılan önceki değer -1 idi. Daha fazla bilgi için [bkz. _fileno.](../c-runtime-library/reference/fileno.md)

- Tek iş parçacığı CRT kitaplıkları (libc.lib ve libcd.lib) kaldırıldı. Çok iş parçacığı CRT kitaplıklarını kullanın. `/ML` Derleyici bayrağı artık desteklenmeyecek. Çok iş parçacığı kodu ile tek iş parçacığı kodu arasındaki performans farkının büyük ölçüde önemli olduğu durumlarda, bazı işlevlerin kilitlenmemeyen sürümleri eklenmiştir.

- Pow aşırı yük, çift pow (int, int), daha iyi standart ile uyumlu kaldırıldı.

- %n biçim belirtici, doğal olarak güvensiz olduğundan, printf işlevailesinin hiçbirinde varsayılan olarak desteklenmez. %n ile karşılaşılırsa, varsayılan davranış geçersiz parametre işleyicisini çağırmaktır. %n desteğini etkinleştirmek `_set_printf_count_output` için `_get_printf_count_output`kullanın (ayrıca bkz. ).

- `sprintf`şimdi imzalı sıfırın negatif işaretini yazdırır.

- `swprintf`Standarda uygun olarak değiştirilmiştir; şimdi bir boyut parametresi gerektirir. Boyut parametresi `swprintf` olmayan form amortismana kaldırıldı.

- `_set_security_error_handler`Kaldırıldı. Bu işleve yapılan çağrıları kaldırın; varsayılan işleyici, güvenlik hatalarıyla başa çıkmanın çok daha güvenli bir yoludur.

- `time_t`artık 64 bitlik bir değerdir (_USE_32BIT_TIME_T tanımlanmadıkça).

- , Fonksiyonlar `errno` artık C Standardı'nda belirtildiği gibi başarıya dokunulmaz. `_wspawn` `_spawn`

- RTC artık varsayılan olarak geniş karakterler kullanır.

- Kayan nokta denetimi sözcük destek işlevleri derlenmiş `/CLR` veya . `/CLR:PURE` Etkilenen fonksiyonlar `_clear87` `_clearfp`, `_control87` `_controlfp`, `_fpreset` `_status87`, `_statusfp`, , , . _CRT_MANAGED_FP_NO_DEPRECATE tanımlayarak amortisman uyarısını devre dışı atabilirsiniz, ancak yönetilen kodda bu işlevlerin kullanımı öngörülemez ve desteklenmemektedir.

- Bazı işlevler artık const işaretçileri döndürmektedir. Eski, const olmayan davranış _CONST_RETURN tanımlayarak geri olabilir. Etkilenen fonksiyonlar

  - memchr, wmemchr

  - strchr, wcschr, _mbschr, _mbschr_l

  - strpbrk, wcspbrk, _mbspbrk, _mbspbrk_l

  - strrchr, wcsrchr, _mbsrchr, _mbsrchr_l

  - strstr, wcsstr, _mbsstr, _mbsstr_l

- Setargv.obj veya Wsetargv.obj ile bağlantı kurarak, komut satırında bir joker karakterin genişlemesini çift tırnak içinde ekleyerek bastırmak artık mümkün değildir. Daha fazla bilgi için Bkz. [Joker Karakter Bağımsız Değişkenlerini Genişletme.](../c-language/expanding-wildcard-arguments.md)

### <a name="standard-library-2005"></a>Standart Kütüphane (2005)

- Özel durum sınıfı \<(özel> üstbilgide bulunan) `std` ad alanına taşındı. Önceki sürümlerde, bu sınıf genel ad alanındaydı. Özel durum sınıfının bulunamamasını belirten hataları gidermek için kodunuza aşağıdaki ifadesini ekleyin:`using namespace std;`

- Arama `valarray::resize()`yaparken, içeriği `valarray` kaybolur ve varsayılan değerlerle değiştirilir. Yöntem, `resize()` bir vektör gibi `valarray` dinamik olarak büyümek yerine yeniden başlatmayı amaçlamaktadır.

- Hata Ayıklayıcılar: C-Runtime Kitaplığı'nın hata ayıklama sürümüyle oluşturulmuş ve doğrulayıcıları yanlış kullanan uygulamalar çalışma zamanında ileri gelenleri görmeye başlayabilir. Bu ileri sürüştürülmek için, _HAS_ITERATOR_DEBUGGING (Visual Studio 2010' dan sonra [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md) günün yerini alan) ile 0 olarak tanımlamanız gerekir. Daha fazla bilgi için Hata [Ayıklayıcı Desteği'ne](../standard-library/debug-iterator-support.md) bakın

## <a name="visual-c-net-2003-breaking-changes"></a>Visual C++ .NET 2003 Son Dakika Değişiklikleri

### <a name="compiler"></a>Derleyici

- Tanımlanan önişlemci yönergesi (C2004) için şimdi parantez kapatma gereklidir.

- Açık uzmanlıklar artık birincil şablondan şablon parametrelerini bulamaz[(Derleyici Hatası C2146).](../error-messages/compiler-errors-1/compiler-error-c2146.md)

- Korunan üye (n) yalnızca (B) sınıfının (A) üyesi olduğu sınıfın (A) üyesi olan bir üye işlevi aracılığıyla erişilebilir ([Derleyici Hatası C2247).](../error-messages/compiler-errors-1/compiler-error-c2247.md)

- Derleyicide geliştirilmiş erişilebilirlik denetimleri artık erişilemeyen temel sınıfları algılar[(Derleyici Hatası C2248).](../error-messages/compiler-errors-1/compiler-error-c2248.md)

- Yıkıcı ve/veya kopya oluşturucuya erişilemiyorsa (C2316) bir özel durum yakalanamaz.

- Artık izin verilmeyen işlevlere işaretçiler üzerinde varsayılan bağımsız değişkenler ([Derleyici Hatası C2383](../error-messages/compiler-errors-1/compiler-error-c2383.md)).

- Statik bir veri üyesi türemiş sınıf[(Derleyici Hatası C2477)](../error-messages/compiler-errors-1/compiler-error-c2477.md)aracılığıyla başharfe aktarılamaz.

- Typedef'in **typedef** başlatılmasına standart tarafından izin verilmez ve şimdi derleyici hatası oluşturur[(Derleyici Hatası C2513).](../error-messages/compiler-errors-2/compiler-error-c2513.md)

- **bool** artık uygun bir türüdür ([Derleyici Hatası C2632](../error-messages/compiler-errors-2/compiler-error-c2632.md)).

- Bir UDC artık aşırı yüklü işleçleri[(C2666)](../error-messages/compiler-errors-2/compiler-error-c2666.md)ile belirsizlik oluşturabilirsiniz.

- Daha fazla ifade artık geçerli null işaretçi sabitleri olarak kabul edilir[(Derleyici Hatası C2668](../error-messages/compiler-errors-2/compiler-error-c2668.md)).

- şablon<> artık derleyicinin daha önce ima edeceği yerlerde gereklidir ([Derleyici Hatası C2768](../error-messages/compiler-errors-2/compiler-error-c2768.md)).

- Bir üye işlevin sınıf dışında açık uzmanlık özelliği, işlev zaten şablon sınıfı uzmanlığı[(Derleyici Hatası C2910)](../error-messages/compiler-errors-2/compiler-error-c2910.md)aracılığıyla açıkça özelleştirilmişse geçerli değildir.

- Kayan nokta türü olmayan şablon parametrelerine artık izin verilmiyor ([Derleyici Hatası C2993](../error-messages/compiler-errors-2/compiler-error-c2993.md)).

- Sınıf şablonlarına şablon türü bağımsız değişkenleri (C3206) olarak izin verilmez.

- Arkadaş işlev adları artık ad alanı içeren[(Derleyici Hatası C3767)](../error-messages/compiler-errors-2/compiler-error-c3767.md)girilmemaktadır.

- Derleyici artık makroda (C4002) ekstra virgül kabul etmez.

- Formun () başharfi () ile oluşturulmuş POD türündeki bir nesne varsayılan olarak başharfe (C4345) olur.

- bağımlı bir ad bir tür[(Derleyici Uyarısı (düzey 1) C4346)](../error-messages/compiler-warnings/compiler-warning-level-1-c4346.md)olarak ele alınacaksa artık yazı adı gereklidir.

- Şablon uzmanlıkları olarak yanlış kabul edilen işlevler artık bu şekilde kabul edilmez (C4347).

- Statik veri üyeleri türemiş sınıf (C4356) aracılığıyla başharfe aktarılamaz.

- Bir sınıf şablonu uzmanlık bir dönüş türü[(Derleyici Uyarı (düzey 3) C4686)](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md)kullanılmadan önce tanımlanması gerekir.

- Derleyici artık erişilemeyen kodu (C4702) bildiriyor.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da Visual C++ İçin Yenilikler](../overview/what-s-new-for-visual-cpp-in-visual-studio.md)
