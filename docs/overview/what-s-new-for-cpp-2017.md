---
title: Visual Studio 2017'deki C++ yenilikleri
description: Visual Studio 2017 ' de Microsoft C/C++ derleyicisinde ve araçlarındaki yeni özellikler ve düzeltmeler.
ms.date: 03/08/2021
ms.technology: cpp-ide
ms.openlocfilehash: bb99f98482484f46824d16f4e202989b0ec6b8ca
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103147307"
---
# <a name="whats-new-for-c-in-visual-studio-2017"></a>Visual Studio 2017'deki C++ yenilikleri

Visual Studio 2017, C++ ortamına birçok güncelleştirme ve düzeltme getirir. Derleyici ve araçlarındaki 250 hatayı ve bildirilen sorunları düzelttik. Müşteriler tarafından [bir sorun bildirin ve](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2017&preserve-view=true) **geri bildirim gönder** altında bir öneri seçenekleri sağlayın. Hataları bildirdiğiniz için teşekkür ederiz!

Visual Studio 'nun tüm yenilikleri hakkında daha fazla bilgi için bkz. [visual 2017 Studio 'daki](/visualstudio/ide/whats-new-visual-studio-2017?view=vs-2017&preserve-view=true)yenilikler. Visual Studio 2019 ' de C++ yenilikleri hakkında daha fazla bilgi için bkz. [Visual Studio 'Da c++](what-s-new-for-visual-cpp-in-visual-studio.md?preserve-view=true&view=msvc-160)yenilikleri. Visual Studio 2015 ve önceki sürümlerde C++ yenilikleri hakkında daha fazla bilgi için, bkz. yenilikler [2003 ile 2015 Visual C++](../porting/visual-cpp-what-s-new-2003-through-2015.md). C++ docs 'taki yenilikler hakkında daha fazla bilgi için bkz. [Microsoft C++ docs: yenilikler](whats-new-cpp-docs.md).

## <a name="visual-studio-2017-c-compiler"></a>Visual Studio 2017 C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uygunluk iyileştirmeleri

Bu sürümdeki C++ derleyicisini ve standart kitaplığı, C++ 11 ve C++ 14 özellikleri için gelişmiş destek ile güncelleştirdik. Ayrıca, C++ 17 standardında olması beklenen belirli özellikler için ön destek içerir. Ayrıntılı bilgi için bkz. [Visual Studio 2017 ' de C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Derleyici, yapılandırılmış bağlamalar, **`constexpr`** Lambdalar, `if constexpr` satır içi değişkenler, katlama ifadeleri ve tür sistemine ekleme gibi c++ 17 ' de yeni olan özelliklerin %75 ' sini destekler **`noexcept`** . Bu özellikler seçeneğinin altında bulunur **`/std:c++17`** . Daha fazla bilgi için bkz. [Visual Studio 'da C++ uyumluluk geliştirmeleri 2017](cpp-conformance-improvements.md)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

Visual Studio sürüm 15,7 ' deki MSVC derleyici araç takımı artık C++ standardına uyar. Daha fazla bilgi için bkz. [duyuruldu: MSVC uyumlu, C++ standardı](https://devblogs.microsoft.com/cppblog/announcing-msvc-conforms-to-the-c-standard/) ve [Microsoft C++ dil uyumu](./visual-cpp-language-conformance.md).

##### <a name="visual-studio-2017-version-158"></a>Visual Studio 2017 sürüm 15,8

[`/experimental:preprocessor`](../build/reference/experimental-preprocessor.md)Derleyici anahtarı, geçerli tüm C ve C++ standartlarına uyum sağlayacak yeni deneysel MSVC ön işlemcisi sağlar. Daha fazla bilgi için bkz. [MSVC New Önişlemci Overview](../preprocessor/preprocessor-experimental-overview.md).

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [`/permissive-`](../build/reference/permissive-standards-conformance.md): Tüm katı standartlar uygunluk derleyicisi seçeneklerini etkinleştirin ve Microsoft 'a özgü çoğu derleyici uzantısını devre dışı bırakın ( `__declspec(dllimport)` Örneğin,). Bu seçenek, varsayılan olarak Visual Studio 2017 sürüm 15,5 ' de bulunur.  **`/permissive-`** Uyumluluk modu, iki aşamalı ad arama desteği içerir. Daha fazla bilgi için bkz. [Visual Studio 'da C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- [`/diagnostics`](../build/reference/diagnostics-compiler-diagnostic-options.md): Bir tanılama hatası veya uyarı konumunun üç farklı şekilde görüntülenmesini mümkün değildir: yalnızca satır numarası, satır numarası ve sütun ya da satır numarası ve sütun, sorunlu kod satırı altında bir giriş işareti ile.

- [`/debug:fastlink`](../build/reference/debug-generate-debug-info.md): Tüm hata ayıklama bilgilerini PDB dosyasına kopyalamadığınızda, %30 ' a kadar daha hızlı artımlı bağlantı süresini (vs. Visual Studio 2015) etkinleştirin. Bunun yerine PDB dosyası, yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplık dosyaları için hata ayıklama bilgilerini gösterir. [Visual Studio 'Da c++ derlemelerini hızlandırmak için](https://devblogs.microsoft.com/cppblog/recommendations-to-speed-c-builds-in-visual-studio/) [ile birlikte "15 `/Debug:fastlink` " ve önerileri içeren daha hızlı c++ derleme döngüsüne](https://devblogs.microsoft.com/cppblog/faster-c-build-cycle-in-vs-15-with-debugfastlink/) bakın.

- Visual Studio 2017, ile kullanılmasına izin verir [`/sdl`](../build/reference/sdl-enable-additional-security-checks.md) [`/await`](../build/reference/await-enable-coroutine-support.md) . Eş yordamın sınırlamasını kaldırdık [`/RTC`](../build/reference/rtc-run-time-error-checks.md) .

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- [ `/std:c++14` ve `/std:c++latest` ](../build/reference/std-specify-language-standard-version.md): Bu DERLEYICI seçenekleri bir projedeki ISO C++ programlama dilinin belirli sürümlerini kabul etkinleştirmenizi sağlar. Yeni taslak standart özelliklerinin çoğu, **`/std:c++latest`** seçeneğiyle korunuyor.

- [`/std:c++17`](../build/reference/std-specify-language-standard-version.md) derleyici tarafından uygulanan C++ 17 özelliklerinin kümesini sunar. Bu seçenek C++ 17 sonrasındaki özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır: sonraki çalışma taslağı sürümlerinde değiştirilen veya yeni ve C++ standardının hata güncelleştirmeleri. Bu özellikleri etkinleştirmek için kullanın **`/std:c++latest`** .

### <a name="codegen-security-diagnostics-and-versioning"></a>CodeGen, güvenlik, tanılama ve sürüm oluşturma

Bu sürüm, iyileştirme, kod oluşturma, araç takımı sürümü oluşturma ve tanılama konularında çeşitli geliştirmeler sunar. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: sabit tam sayıları bölme işlemleri için otomatik vektörleştirme desteği, memset desenlerinin daha iyi tanınması.
- Geliştirilmiş kod güvenliği: arabellek taşması derleyici tanılamalarının artmasının yanı sıra [`/guard:cf`](../build/reference/guard-enable-control-flow-guard.md) doğrudan geçiş tabloları üreten anahtar deyimlerini koruurun.
- Sürüm oluşturma: yerleşik önişlemci makrosu **\_ msc \_ sürümünün** değeri artık her Visual C++ araç takımı güncelleştirmesinde tek bir şekilde güncelleştirildi. Daha fazla bilgi için bkz. [Visual C++ derleyici sürümü](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/).
- Yeni araç takımı düzeni: derleyici ve ilgili derleme araçlarının geliştirme makinenizde yeni bir konum ve dizin yapısı vardır. Yeni düzen derleyicinin birden çok sürümünün yan yana yüklemelerine izin vermez. Daha fazla bilgi için bkz. [Visual Studio 2017 ' de derleyici araçları düzeni](https://devblogs.microsoft.com/cppblog/compiler-tools-layout-in-visual-studio-15/).
- Geliştirilmiş Tanılamalar: çıkış penceresinde artık hata oluşan sütun görüntülenir. Daha fazla bilgi için bkz. [vs "15" Preview 5 ' te C++ derleyicisi tanılama geliştirmeleri](https://devblogs.microsoft.com/cppblog/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Coroutines kullanırken deneysel anahtar sözcük **yield** ( **`/await`** seçeneğinde kullanılabilir) kaldırılmıştır. Kodunuzun kullanılması için güncelleştirilmeleri gerekir `co_yield` . Daha fazla bilgi için bkz. [ `yield` `co_yield` vs 2017 ' de olacak anahtar sözcük](https://devblogs.microsoft.com/cppblog/yield-keyword-to-become-co_yield-in-vs-2017/).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

Derleyicide Tanılama için ek geliştirmeler. Daha fazla bilgi için bkz. [Visual Studio 'Da tanılama geliştirmeleri 2017 15.3.0](https://devblogs.microsoft.com/cppblog/diagnostic-improvements-in-vs2017-15-3-0/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Visual C++ çalışma zamanı performansı, daha iyi oluşturulan kod kalitesiyle iyileşmeye devam etmektedir. Artık kodunuzu yeniden derleyebilirsiniz ve uygulamanız daha hızlı çalışır. Derleyici iyileştirmelerinden bazıları koşullu skaler mağazaların vektörleştirmesi, çağrıların birleştirilmesi `sin(x)` ve `cos(x)` Yeni bir IÇIN `sincos(x)` ve SSA iyileştiricisinden gereksiz yönergelerin ortadan kaldırılması gibi yepyeni bir yenilikler. Diğer derleyici iyileştirmeleri, var olan işlevlere yönelik geliştirmelerdir, örneğin Koşullu ifadeler için vektörtorizer buluşsal yöntemler, daha iyi döngü iyileştirmeleri ve float Min/Max CodeGen. Bağlayıcı yeni ve daha hızlı bir **`/OPT:ICF`** uygulamaya sahiptir ve bu, %9 bağlantı süresi hızlandırmalı ve artımlı bağlamada başka performans düzeltmeleri de olabilir. Daha fazla bilgi için bkz. [/opt (iyileştirmeler)](../build/reference/opt-optimizations.md) ve [/artımlı (artımlı bağlantı)](../build/reference/incremental-link-incrementally.md).

Microsoft C++ derleyicisi, Intel 'in AVX-512 ' i destekler. Bu, AVX-512 ' deki yeni işlevleri 128 bit ve 256 bit geniş yazmaçlara getiren vektör uzunluğu yönergelerine sahiptir.

[`/Zc:noexceptTypes-`](../build/reference/zc-noexcepttypes.md)Seçeneği, **`noexcept`** genel olarak c++ 17 modu kullanılırken c++ 14 sürümüne dönmek için kullanılabilir. Bu seçenek `throw()` , tüm kodunuzu aynı anda yeniden yazmak zorunda kalmadan, kaynak kodunuzu c++ 17 ' ye uyacak şekilde güncelleştirmenizi sağlar. Daha fazla bilgi için bkz. [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements-2017.md#noexcept_removal).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Yeni derleyici anahtarı [/Qspectre](../build/reference/qspectre.md) , öngörülebilir yürütme yan kanal saldırılarına karşı azaltmaya yardımcı olur. Daha fazla bilgi için bkz. [Spectre AZALTMALARı MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).
- Spectre azaltma için yeni tanılama uyarısı. Daha fazla bilgi için bkz. [Spectre Diagnostic for Visual Studio 2017 sürüm 15,7 Preview 4](https://devblogs.microsoft.com/cppblog/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/).
- /ZC için yeni bir değer **`/Zc:__cplusplus`** olan, C++ standart desteğinin doğru raporlanmasını mümkün. Örneğin, anahtar ayarlandığında ve derleyici **`/std:c++17`** değeri olarak genişletilir **`201703L`** . Daha fazla bilgi için bkz. [MSVC Now reports __cplusplus](https://devblogs.microsoft.com/cppblog/msvc-now-correctly-reports-__cplusplus/).

## <a name="c-standard-library"></a>C++ standart kütüphanesi

### <a name="correctness-improvements"></a>Doğruluk Iyileştirmeleri

##### <a name="visual-studio-2017-rtm-version-150"></a>Visual Studio 2017 RTM (sürüm 15,0)

- Küçük `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` Tanılama geliştirmeleri. Dize makinelerimizde bir IDL denetimi yapıldığında, bu, yolculuğa neden olan belirli bir davranışı rapor eder. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- `std::promise`Daha önce kodun sürekli olarak engellenmesine neden olabilecek taşıma atama işleci düzeltildi.
- `atomic<T*>`Örtülü dönüşümle derleyici hataları düzeltildi `T*` .
- `pointer_traits<Ptr>` Şimdi doğru şekilde algılar `Ptr::rebind<U>` .
- **`const`** Çıkarma işlecinde eksik niteleyici düzeltildi `move_iterator` .
- Ve isteyen durum bilgisi olan Kullanıcı tanımlı ayrıcılar için sessiz hatalı CodeGen düzeltildi `propagate_on_container_copy_assignment` `propagate_on_container_move_assignment` .
- `atomic<T>` Şimdi aşırı yüklenmiş `operator&()` .
- Hatalı çağrılar için biraz daha geliştirilmiş derleyici tanılaması `bind()` .

Visual Studio 2017 RTM 'de daha standart kitaplık geliştirmeleri vardır. Tüm liste için bkz. [VS 2017 RTM 'de](https://devblogs.microsoft.com/cppblog/stl-fixes-in-vs-2017-rtm/)C++ ekip blogu girişi standart kitaplık düzeltmeleri.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Standart Kitaplık kapsayıcıları, ' dan ' a değil, artık ' a `max_size()` `numeric_limits<difference_type>::max()` `max()` sahip `size_type` . Bu değişiklik, bu `distance()` kapsayıcıdaki yineleyicilerin sonucunun dönüş türünde gösterilebilir olmasını sağlar `distance()` .
- Eksik özelleştirme düzeltildi `auto_ptr<void>` .
- `for_each_n()` `generate_n()` `search_n()` Length bağımsız değişkeni bir tamsayı türü değilse,, ve algoritmaları daha önce derleyemedi. Artık İntegral olmayan uzunlukları yineleyiciler ' a dönüştürmeye çalışır `difference_type` .
- `normal_distribution<float>` Artık, standart kitaplık içinde Double-float ile daraltma hakkında uyarı vermez.
- `basic_string` `npos` `max_size()` En büyük boyut taşması denetlenirken yerine kullanılan bazı işlemler düzeltildi.
- `condition_variable::wait_for(lock, relative_time, predicate)` , bir veya daha fazla uyanma varsa, tüm göreli zamanın tamamlanmasını bekler. Artık, göreli saatin yalnızca tek bir aralığını bekler.
- `future::get()` Artık, standart gerektiğinden, öğesini geçersiz kılar `future` .
- `iterator_traits<void *>` Form oluşturulmaya çalıştığı için bir sabit hata olması için kullanılır `void&` ; Şimdi `iterator_traits` "bir yineleyici" SFINAE koşullarından kullanılmasına izin veren boş bir yapı haline gelir.
- Clang **-wsystem-Headers** tarafından bildirilen bazı uyarılar düzeltildi.
- Ayrıca, bildirimde bulunan özel durum belirtimi, Clang **-wmicrosoft-Exception-spec** tarafından bildirilen bir önceki bildirimle eşleşmez.
- Ayrıca, Clang ve C1XX tarafından bildirilen sabit bir bellek-başlatıcı-liste sıralama uyarıları.
- Sıralanmamış kapsayıcılar, kapsayıcılar kendilerini takas edildiğinde karma işlevlerini veya koşullarını değiştirmedi. Şimdi.
- Çok sayıda kapsayıcı takas işlemi artık işaretlenmiş **`noexcept`** (Standart kitaplığımızda, eşit olmayan Ayırıcısız davranış koşulu algılanırken bir özel durum oluşturma hiçbir zaman yoktur `propagate_on_container_swap` ).
- Birçok `vector<bool>` işlem artık işaretlendi **`noexcept`** .
- Standart kitaplık artık, `value_type` bir opt çıkış taraması ile eşleşen ayırıcıyı (c++ 17 modunda) zorlayacaktır.
- Kendi kendine Aralık-INSERT işlevinin `basic_string` dizelerin içeriğini karıştıran bazı koşullar düzeltildi. (Note: kendinden aralığa ekleme, standart tarafından hala yasaktır.)
- `basic_string::shrink_to_fit()` Artık ayırıcı tarafından etkilenmemektedir `propagate_on_container_swap` .
- `std::decay` Artık aboınable işlev türlerini, diğer bir deyişle, MF nitelenmiş, ref nitelenmiş veya her ikisi de olan işlev türlerini işler.
- Değiştirilen büyük/küçük harfe duyarlılık ve eğik çizgi kullanma, taşınabilirliği artırma yönergeleri dahil.
- '*Enumeration*' numaralandırmasının anahtarındaki "Numaralandırıcı '*Numaralandırıcı*' sabit uyarı C4061, bir Case etiketi tarafından açıkça işlenmiyor. Bu uyarı varsayılan olarak kapalıdır ve uyarılar için standart kitaplığın genel ilkesinde özel bir durum olarak düzeltildi. (Standart Kitaplık **`/W4`** temiz, ancak temiz bir şekilde denenmez **`/Wall`** . Birçok varsayılan uyarı çok gürültülü ve düzenli olarak kullanılmak üzere tasarlanmamıştır.)
- Geliştirilmiş `std::list` hata ayıklama denetimleri. Yineleyiciler şimdi listeleyin `operator->()` ve `list::unique()` yineleyiciler geçersiz kılındı olarak işaretler.
- İçinde sabit kullanımlar-ayırıcı meta programlama `tuple` .

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `std::partition` Artık, standart gerektiğinden `N` , her zaman yerine koşul sürelerini çağırır `N + 1` .
- Sürüm 15,3 ' de sihirli statiği 'dan kaçınmaya yönelik girişimler, sürüm 15,5 ' de onarıldı.
- `std::atomic<T>` Artık `T` varsayılan oluşturulabilir olmasını gerektirmez.
- Yineleyici bir zaman alan yığın algoritmaları, Yineleyici hata ayıklama etkinken farklı davranır. Artık girişin aslında bir yığında olduğunu belirten doğrusal bir zaman onaylama işlemi yapılmaz.
- `__declspec(allocator)` Artık yalnızca C1XX için korunuyor, bu declspec anlayan olan Clang uyarılarını önler.
- `basic_string::npos` Artık derleme zamanı sabiti olarak kullanılabilir.
- `std::allocator` C++ 17 modunda, artık, `max_align_t` tarafından devre dışı bırakılmadığı takdirde hizalama daha büyük olan türler, diğer bir deyişle, daha fazla hizalanmış türlerin ayrılmasını doğru şekilde işler **`/Zc:alignedNew-`** .  Örneğin, 16 baytlık veya 32 baytlık hizalamadaki nesne vektörleri artık SSE ve AVX yönergelerine göre doğru şekilde hizalanmıştır.

### <a name="conformance-improvements"></a>Uyumluluk geliştirmeleri

- Ekledik, \<any\> , \<string_view\> `apply()` , `make_from_tuple()` .
- , \<optional\> , \<variant\> `shared_ptr::weak_type` Ve eklendi \<cstdalign\> .
- ,, Ve, ve, ve içinde C++ 14 etkindir **`constexpr`** `min(initializer_list)` `max(initializer_list)` `minmax(initializer_list)` `min_element()` `max_element()` `minmax_element()` .

Daha fazla bilgi için bkz. [Microsoft C++ dil uygunluğu tablosu](./visual-cpp-language-conformance.md).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Birkaç ek C++ 17 özelliği uygulandı. Daha fazla bilgi için bkz. [Microsoft C++ dil uygunluğu tablosu](cpp-conformance-improvements-2017.md#improvements_153).
- Uygulanan P0602R0 "varyant ve isteğe bağlı, kopyalama/taşıma üç aylık dönemi yaymalıdır.
- Standart kitaplık artık, [/gr-](../build/reference/gr-enable-run-time-type-information.md) seçeneği aracılığıyla dinamik RTTI 'nin devre dışı bırakılmakta olduğunu gösterir. Hem hem de `dynamic_pointer_cast()` `rethrow_if_nested()` kendiliğinden gerektirir **`dynamic_cast`** , bu nedenle standart kitaplık artık bunları altında olarak işaretler `=delete` **`/GR-`** .
- Dinamik RTTı aracılığıyla devre dışı bırakılmış olsa bile **`/GR-`** , biçiminde "STATIC RTTI" `typeid(SomeType)` de kullanılabilir ve çeşitli standart kitaplık bileşenlerini güçlendirir. Standart kitaplık artık bu özelliği aracılığıyla devre dışı bırakmayı desteklemektedir **`/D_HAS_STATIC_RTTI=0`** . Bu bayrak Ayrıca ve ' ın ve üye işlevlerini devre dışı bırakır, ve ' ın `std::any` `target()` `target_type()` `std::function` `get_deleter()` arkadaş üye işlevi `std::shared_ptr` `std::weak_ptr` .
- Standart kitaplık artık **`constexpr`** koşullu olarak tanımlanmış makrolar yerine, c++ 14 ' i koşullu olarak kullanır.
- Standart kitaplık artık dahili olarak diğer ad şablonlarını kullanır.
- Standart kitaplık artık **`nullptr`** , yerine dahili olarak kullanılmaktadır `nullptr_t{}` . (NULL 'in iç kullanımı eradkıdı. 0-null olarak iç kullanımı, yavaş bir şekilde temizleniyor.)
- Standart kitaplık artık `std::move()` , stillistik yanlış kullanımı yerine dahili olarak kullanılmaktadır `std::forward()` .
- `static_assert(false, "message")`Olarak değiştirildi `#error message` . Bu değişiklik, `#error` derlemeyi hemen durdurduğu için derleyici tanılamayı geliştirir.
- Standart kitaplık artık işlevleri olarak işaretler `__declspec(dllimport)` . Modern bağlayıcı teknolojisine artık gerek yoktur.
- SFıNAE 'yi, dönüş türleri ve işlev bağımsız değişken türleri ile karşılaştırıldığında dağınıklığı azaltılan varsayılan şablon bağımsız değişkenlerine ayıklandı.
- ' Deki hata ayıklama denetimleri, \<random\> artık `_Rng_abort()` `fputs()` **stderr**'e çağrılan iç işlev yerine standart kitaplığın olağan makineler ' i kullanır. Bu işlevin uygulanması, ikili uyumluluk için tutulmuştur. Standart kitaplığın sonraki ikili uyumsuz sürümünde bu sürümü kaldıracağız.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- C++ 17 standardına göre birkaç standart kitaplık özelliği eklenmiştir, kullanım dışıdır veya kaldırıldı. Daha fazla bilgi için bkz. [Visual Studio 'da C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md#improvements_155).
- Aşağıdaki paralel algoritmalar için deneysel destek:
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- Aşağıdaki paralel algoritmaların imzaları şu an eklendi ancak paralelleştirilmedi. Profil oluşturma, yalnızca öğeleri taşımanın veya persessize eden paralelleştirme algoritmalarında hiç avantaj bulunmadığını gösterdi:
  - `copy`
  - `copy_n`
  - `fill`
  - `fill_n`
  - `move`
  - `reverse`
  - `reverse_copy`
  - `rotate`
  - `rotate_copy`
  - `swap_ranges`

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- \<memory_resource>
- Kitaplık temelleri v1
- `polymorphic_allocator`Atama siliniyor
- Sınıf şablonu bağımsız değişken kesintiyi geliştirme

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Paralel algoritmalar için destek artık deneysel değildir
- Yeni bir uygulama \<filesystem>
- Elemensel dize dönüştürmeleri (kısmi)
- `std::launder()`
- `std::byte`
- `hypot(x,y,z)`
- Gereksiz Decay önleme
- Matematik özel işlevleri
- `constexpr char_traits`
- Standart Kitaplık için kesinti Kılavuzu

Daha fazla bilgi için bkz. [Microsoft C++ dil uygunluğu tablosu](./visual-cpp-language-conformance.md).

### <a name="performance-and-throughput-fixes"></a>Performans ve verimlilik düzeltmeleri

- `basic_string::find(char)`Aşırı yüklemeler yalnızca `traits::find` bir kez çağrı yaptı. Daha önce, 1 uzunluğunda bir dize için genel bir dize araması olarak uygulanmıştır.
- `basic_string::operator==` Şimdi dizelerin içeriğini karşılaştırmadan önce dizenin boyutunu denetler.
- `basic_string`Derleyici iyileştiricinin çözümlenmesi zor olan denetim bağlantısı kaldırıldı. Tüm kısa dizeler için hala çağrı `reserve` yapma hiçbir şey yapmaz.
- `std::vector` doğruluk ve performans açısından daha fazla bakış: ekleme ve emplace işlemleri sırasında diğer ad artık standart için gereken şekilde doğru şekilde işlendiğinden, güçlü özel durum garantisi artık standart ile ve diğer mantığın gerektirdiği durumlarda sağlanır ve `move_if_noexcept()` daha az sayıda öğe işlemi ekler ve emplace.
- C++ standart kitaplığı artık null süslü işaretçilerin başvurusunu önler.
- Gelişmiş `weak_ptr::lock()` performans.
- Derleyici aktarım hızını artırmak için, C++ standart kitaplık üstbilgileri artık gereksiz derleyici iç bilgileri için bildirimleri dahil önleyin.
- `std::string` `std::wstring` Üç defadan fazla bir performans ve taşıma oluşturucuları geliştirildi.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- **`noexcept`** `std::atomic` Uygulamasının, yapılandırılmış özel durum Işleme (SEH) kullanan işlevlere uygulamayı önleyen, ile etkileşimlere geçici bir şekilde çalışmıştır.
- Standart kitaplığın iç `_Deallocate()` işlevi, daha küçük koda optimize edilecek şekilde değiştirildi ve bu da daha fazla yere satır içine alınmış olabilir.
- `std::try_lock()`Özyineleme yerine paket genişletmesi kullanılacak şekilde değiştirildi.
- Kilitleme `std::lock()` engelleme algoritması, `lock()` Tüm kilitlere dönme yerine işlemleri kullanmak için geliştirildi `try_lock()` .
- İçinde adlandırılmış dönüş değeri Iyileştirmesi etkinleştirildi `system_category::message()` .
- `conjunction` ve `disjunction` artık türler `N + 1` yerine türleri örnekleyin `2N + 2` .
- `std::function` Artık, her tür silinmiş çağrılabilir için ayırıcı destek makineleri örneklamayacak, üretilen iş miktarını artırma ve birçok farklı lambdaya geçiş yapan programlarda. obj boyutunu `std::function` azaltma.
- `allocator_traits<std::allocator>` el ile satır içine alınmış `std::allocator` işlemleri içerir ve yalnızca üzerinden etkileşim kuran kodda kod boyutunu azaltır `std::allocator` `allocator_traits` (çoğu kodda).
- C++ 11 minimal ayırıcı arabirimi artık `allocator_traits` , bir iç sınıfta ayırıcıyı sarmalama yerine doğrudan çağıran standart kitaplık tarafından işlenir `_Wrap_alloc` . Bu değişiklik, ayırıcı desteği için oluşturulan kod boyutunu azaltır, iyileştiricinin bazı durumlarda standart kitaplık kapsayıcıları hakkında neden olma yeteneğini geliştirir ve daha iyi bir hata ayıklama deneyimi sağlar (artık hata ayıklayıcı yerine ayırıcı türünü görürsünüz `_Wrap_alloc<your_allocator_type>` ).
- Özelleştirilmiş için meta programlama kaldırıldı `allocator::reference` , bu ayırıcıları özelleştirmeye izin verilmiyor. (Ayrıcılar kapsayıcıların süslü işaretçiler kullanmasına karşın daha fazla başvuru yapamaz.)
- Derleyici ön ucu, hata ayıklama derlemelerinin performansını artırmak için Aralık tabanlı Döngülerde hata ayıklama yineleyicilerini sarmalandırmıştı.
- `basic_string`Ve için iç küçültme yolu `shrink_to_fit()` artık, yeniden `reserve()` konumlandırma işlemlerinin yolunda değil, tüm Üyeler için kod boyutunu azaltmaktadır.
- `basic_string`İç büyüme yolu artık yolunda değildir `shrink_to_fit()` .
- `basic_string`İşlev azaltma işlemleri artık, ayırılamayan hızlı yola ve yavaş yol işlevlerine bölünmüştür ve bu da yaygın olmayan bir servis talebi arayanlara satır içine alınmayacak.
- `basic_string`Değiştirme işlemleri artık yeniden boyutlandırma yerine tercih edilen durumda yeniden ayrılmış arabellekler oluşturur. Örneğin, bir dizenin başındaki bir INSERT artık, içeriği tam olarak bir kez eklendikten sonra taşımıştır. Aşağı ya da yeni ayrılmış arabelleğe taşınır. Bu durumda, ilk olarak yeni ayrılan arabelleğe ve ardından aşağı doğru bir şekilde bir kez taşınmaz.
- İçindeki C standart kitaplığını çağıran işlemler, \<string\> artık `errno` TLS ile yinelenen etkileşimi kaldırmak için adresi önbelleğe alma işlemini kaldırır.
- Uygulamayı basitleşme `is_pointer` .
- İşlev tabanlı Ifadenin SFıNAE 'ye ve tabanlı olarak değiştirilmesi bitti **`struct`** `void_t` .
- Standart Kitaplık algoritmaları artık, geri artan yineleyiciler yapmaktan kaçınır.
- 64-bit sistemlerde 32 bit ayırıcılar kullanılırken düzeltilen kesme uyarıları.
- `std::vector` Bunu yapmak, mümkün olduğunda arabelleği yeniden kullanmak için artık, POCıMA dışı olmayan eşit ayırıcı durumunda daha etkilidir.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `basic_string<char16_t>` Şimdi de aynı `memcmp` , `memcpy` ve benzer iyileştirmelere sahiptir `basic_string<wchar_t>` .
- İşlev işaretçilerinin satır içine alınmış olmasını önleyen bir iyileştirici sınırlaması, Visual Studio 2015 güncelleştirme 3 ' te "işlevlerden kopyalanmaktan kaçının" işi tarafından sunulan, performansı geri yükleniyor `lower_bound(iter, iter, function pointer)` .
- ,, Ve için girişlerin hata ayıklamasının sıra doğrulaması, `includes` , `set_difference` `set_symmetric_difference` ve `set_union` sırası denetlenmeden önce yineleyiciler tarafından düşürüldü.
- `std::inplace_merge` Şimdi zaten konumunda olan öğeleri atlar.
- `std::random_device`Artık yapı oluşturup yok eder `std::string` .
- `std::equal` ve `std::partition` Yineleyici karşılaştırmayı kaydeden bir geçiş iş parçacığı iyileştirme geçişine sahipti.
- `std::reverse`, Üç aylık kopyalanabilir için işaretçiler geçirildiğinde `T` , artık el yazısı vektör haline getirilmiş bir uygulamaya gönderim yapılır.
- `std::fill`, ve `std::equal` `std::lexicographical_compare` için ve için ve `memset` `memcmp` `std::byte` `gsl::byte` (ve diğer karakter benzeri Enum ve Enum sınıfları) için ve için nasıl dağıtım yapılacağını taöğrettin. `std::copy`' Yi kullanarak dağıtım yaptığından `is_trivially_copyable` hiçbir değişiklik gerektirmez.
- Standart Kitaplık, yalnızca bir davranışı, türlerin daha duyarlı olmayan bir şekilde geri dönüşlü hale getirmek için olduğu boş küme ayraçları yok.

## <a name="other-libraries"></a>Diğer Kitaplıklar

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg** , Visual Studio 'da açık kaynaklı C++ statik-BS ve DLL 'leri edinme ve oluşturma sürecini büyük ölçüde kolaylaştıran açık kaynaklı bir komut satırı aracıdır. Daha fazla bilgi için bkz. [vcpkg: C++ için Paket Yöneticisi](../build/vcpkg.md).

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

C++ için platformlar arası Web API 'SI olan CPPRestSDK, 2.9.0 sürümüne güncelleştirilmiştir. Daha fazla bilgi için bkz: [Cpprestsdk 2.9.0 GitHub 'da kullanılabilir](https://devblogs.microsoft.com/cppblog/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Ancak başka bir ad arama uyumluluğu düzeltmeleri kümesi
- Mevcut taşıma oluşturucuları ve taşıma atama işleçleri artık atma olarak düzgün şekilde işaretlendi
- Atlstr. h 'de yerel lekelerde iş parçacığı güvenli başlatması hakkında geçerli uyarı C4640
- Yerel statiklerin iş parçacığı güvenli başlatması, bir DLL oluşturmak için ATL kullanılırken otomatik olarak XP araç takımı 'nda devre dışı bırakıldı. Artık bu değil. **`/Zc:threadSafeInit-`** İş parçacığı güvenli başlatma istemiyorsanız, proje ayarlarınıza ekleyebilirsiniz.

### <a name="visual-c-runtime"></a>Visual C++ çalışma zamanı

- Denetim akışı koruyucusu sembolleri için yeni "cfguard. h" üstbilgisi.

## <a name="visual-studio-2017-c-ide"></a>Visual Studio 2017 C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Bir çözüm yapılandırması ilk kez etkinleştirildiğinde, artık daha hızlı olur ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında gerçekleşir.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf Ekle** artık doğrudan sınıf ekleme Sihirbazı 'nı başlatır. Daha önce burada olan diğer tüm öğeler artık > Ekle ' nin altında **Yeni öğe Ekle**' nin altında bulunabilir.
- Win32 projeleri artık **Yeni proje** Iletişim kutusunda **Windows Masaüstü** kategorisi altındadır.
- **Windows konsolu** ve **Masaüstü uygulama** şablonları artık bir sihirbaz görüntülemeden projeler oluşturur. Aynı kategoride, eski **Win32 konsol uygulaması** sihirbazıyla aynı seçenekleri görüntüleyen yeni bir **Windows Masaüstü Sihirbazı** var.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Yeniden düzenleme ve kod gezintisi için IntelliSense altyapısını kullanan birkaç C++ işlemi çok daha hızlı çalışır. Aşağıdaki sayılar, 3500 projeleriyle Visual Studio Jmıum çözümüne dayalıdır:

| Özellik | Performans Iyileştirmesi |
|--|--|
| Rename | 5.3 x |
| Imzayı Değiştir | 4.5 x |
| Tüm Başvuruları Bul | 4.7 x |

C++ artık CTRL + tıklama **tanımına git**' i destekliyor ve tanımlara kolayca gidilme yapıyor. Üretkenlik güç araçları paketinden yapı görselleştiricisi, artık varsayılan olarak ürüne de dahildir.

## <a name="intellisense"></a>IntelliSense

- Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Yeni motor, **Tanıma Git** ve **tüm başvuruları bul** gibi veritabanı işlemlerini hızlandırır. İlk çözüm ayrıştırma süresini önemli ölçüde geliştirir. Ayar, **araçlar > seçenekler > metin düzenleyicisi > C/C++ > gelişmiş**' e taşınmıştır. (Daha önce... C/C++ > deneysel.)

- Önceden derlenmiş üst bilgiler kullanmayan projelerde ve dosyalarda IntelliSense performansını geliştirdik. Geçerli dosyadaki üst bilgiler için otomatik önceden derlenmiş üst bilgi oluşturulur.

- Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Filtrelenmiş Hata Listesi](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

- Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye Listesi Filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

- Üye listesinde görüntülendiklere bağlamsal olarak uyumlu filtreleme sağlayan yeni bir deneysel tahmine dayalı IntelliSense özelliği eklendi. Daha fazla bilgi için bkz. [C++ IntelliSense geliştirmeleri-tahmine dayalı ıntellisense & filtreleme](https://devblogs.microsoft.com/cppblog/c-intellisense-improvements-predictive-intellisense-filtering/).
- **Tüm başvuruları bul** (Shift + F12) artık karmaşık kod tabanlarında bile kolay bir şekilde yararlanmanıza yardımcı olur. Gelişmiş gruplandırma, filtreleme, sıralama, sonuçları içinde arama ve (bazı diller için) renklendirme sağlar, böylece başvurularınızı net bir şekilde anlayabilmenizi sağlayabilirsiniz. C++ için yeni kullanıcı arabirimi, bir değişkene okuduğumuz veya bir değişkene yazma yapılıp yaptığımız hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyici özellikleri **kapsamlar ' ı genişletin** ve **genişletilmiş öncelik** de deneysel ' dan Gelişmiş ' e taşınmıştır.
- Deneysel yeniden düzenleme özellikleri **Imza değiştirme** ve **ayıklama işlevi** artık varsayılan olarak kullanılabilir.
- C++ projeleri için deneysel ' daha hızlı proje yükü ' özelliği eklendi. Bir sonraki sefer bir C++ projesi açtığınızda daha hızlı yüklenir ve bu süre sonra *çok* daha hızlı yüklenecektir!
- Bu özelliklerden bazıları diğer dillerde ortaktır ve bazıları C++ ' a özeldir. Bu yeni özellikler hakkında daha fazla bilgi için bkz. [Visual Studio "15" Preview 5 duyurusu](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-15-preview-5/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- ClangFormat için destek eklendi. Daha fazla bilgi için bkz. [Visual Studio 2017 ' de Clangformat desteği](https://devblogs.microsoft.com/cppblog/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>Açık klasörü olan MSBuild olmayan projeler

Visual Studio 2017, **klasörü aç** özelliğini tanıtır. Herhangi bir çözüm veya proje oluşturmak zorunda kalmadan kaynak kodu içeren bir klasörde kodlamanıza, oluşturmanıza ve hata ayıklamanıza olanak sağlar. Artık, projeniz MSBuild tabanlı bir proje olmasa bile Visual Studio 'Yu kullanmaya başlamak çok basittir. **Klasörü aç** özelliği, güçlü kod anlama, düzenlemesi, derleme ve hata ayıklama özelliklerine erişmenizi sağlar. Bunlar, Visual Studio 'nun zaten MSBuild projeleri için sağladığı aynı olanlarlar. Daha fazla bilgi için bkz. [C++ Için klasör projelerini açma](../build/open-folder-projects-cpp.md).

- Klasör Aç deneyimi geliştirmeleri. Bu. JSON dosyaları aracılığıyla deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Alternatif derleyiciler ve MinGW ve Cygwin gibi yapı ortamları için geliştirilmiş destek. Daha fazla bilgi için bkz. [MinGW ve Cygwin 'yi Visual C++ ve açık klasör kullanma](https://devblogs.microsoft.com/cppblog/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
- Üzerinde CppProperties.jsve CMakeSettings.jsüzerinde genel ve yapılandırmaya özgü ortam değişkenlerini tanımlamaya yönelik destek eklendi. Bu ortam değişkenleri, launch.vs.json ve tasks.vs.jsiçindeki görevlerde tanımlanan hata ayıklama yapılandırmalarına göre tüketilebilir. Daha fazla bilgi için bkz. [Visual C++ ve klasörü açmak Için ortamınızı özelleştirme](https://devblogs.microsoft.com/cppblog/customizing-your-environment-with-visual-c-and-open-folder/).
- 64 bitlik platformları kolayca hedefleyebilme özelliği de dahil olmak üzere CMake Dokja üreticisi için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Açık klasör aracılığıyla CMake desteği

Visual Studio 2017, MSBuild proje dosyalarına (. vcxproj) dönüştürülmeksizin CMake projelerini kullanma desteği sunar. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md). **Açık klasörle** birlikte CMake projelerini açmak, C++ düzenlemesi, oluşturulması ve hata ayıklaması için ortamı otomatik olarak yapılandırır.

- C++ IntelliSense, kök klasörde bir CppProperties.jsdosyası oluşturmaya gerek kalmadan işe yarar. Ayrıca, kullanıcıların dosyalardaki CMake ve CppProperties.jstarafından verilen yapılandırmalara kolayca geçiş yapmasına olanak tanımak için yeni bir açılan menü ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![CMake klasör aç](media/cmake-cpp.png "CMake klasör aç")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- CMake Dokja Oluşturucu için destek eklendi.

##### <a name="visual-studio-2017-version-154"></a>Visual Studio 2017 sürüm 15.4

- Mevcut CMake önbellekleri içeri aktarılmaya yönelik destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- CMake 3,11 için destek eklendi, CMake projelerinde kod analizi, Çözüm Gezgini içinde hedefleri, önbellek oluşturma seçeneklerini ve tek dosya derlemesini destekler. Daha fazla bilgi için bkz. Visual [Studio 'Da CMake desteği](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [Visual Studio 'da CMake projeleri](../build/cmake-projects-in-visual-studio.md).

## <a name="windows-desktop-development"></a>Windows masaüstü geliştirme

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik. Yükleyici Kullanıcı arabiriminde listelenen bileşenlere ilişkin belirtilen yükleme boyutları yanlış ve toplam boyutu düşük olarak tahmin edilir.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Çalıştığından emin olmak için önerilen (seçili) bileşenleri **VC + + 2017 v141 araç takımı (x86, x64)** ve **Windows 10 SDK (10.0.** Gerekli araçlar yüklü değilse, projeler başarıyla oluşturulmaz ve sihirbaz yanıt vermeyi durdurur.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Visual C++ derleme araçları (daha önce tek başına bir ürün olarak kullanılabilir) artık Visual Studio Yükleyicisi iş yükü olarak eklenmiştir. Bu iş yükü, yalnızca Visual Studio IDE 'yi yüklemeden C++ projelerini derlemek için gereken araçları kurar. Hem v140 hem de v141 araç takımları dahil edilmiştir. V141 araç takımı, Visual Studio 2017 sürüm 15,5 ' deki en son geliştirmeleri içerir. Daha fazla bilgi için bkz. [şimdi VISUAL STUDIO derleme araçları VS2017 ve VS2015 MSVC Toolsets](https://devblogs.microsoft.com/cppblog/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)' i içerir.

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Popüler [Linux Geliştirme için Visual C++](https://marketplace.visualstudio.com/items?itemName=VisualCppDevLabs.VisualCforLinuxDevelopment) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

##### <a name="visual-studio-2017-version-152"></a>Visual Studio 2017 sürüm 15.2

Platformlar arası kod paylaşımı ve tür görselleştirmede geliştirmeler yapılmıştır. Daha fazla bilgi için bkz. [platformlar arası kod paylaşımı ve tür görselleştirme Için Linux C++ geliştirmeleri](https://devblogs.microsoft.com/cppblog/linux-cross-platform-and-type-visualization/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Linux iş yükü, uzak Linux makinelerine dosya eşitlemek için **SFTP** 'ye alternatif olarak **rsync** desteği eklemiştir.
- ARM mikro denetleyicileri hedefleyen çapraz derleme için destek eklendi. Yükleme sırasında etkinleştirmek için, C++ iş yüküyle **Linux geliştirmeyi** seçin ve **katıştırılmış ve IoT geliştirme** seçeneğini belirleyin. Bu seçenek, ARM GCC çapraz derleme araçlarını ekler ve yüklemenize yapılır. Daha fazla bilgi için bkz. [Visual Studio 'Da ARM GCC çapraz derlemesi](https://devblogs.microsoft.com/cppblog/arm-gcc-cross-compilation-in-visual-studio/).
- CMake için destek eklendi. Artık, Visual Studio projesine dönüştürmek zorunda kalmadan mevcut CMake kod tabanınız üzerinde çalışabilirsiniz. Daha fazla bilgi için bkz. [Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md).
- Uzak görevleri çalıştırmaya yönelik destek eklendi. Bu özellik, Visual Studio 'nun bağlantı Yöneticisi 'nde tanımlanmış uzak bir sistemde herhangi bir komutu çalıştırmanızı sağlar. Uzak görevler Ayrıca uzak sisteme dosya kopyalama özelliğini de sağlar.
Daha fazla bilgi için bkz. [Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Linux iş yükü senaryolarında çeşitli geliştirmeler. Daha fazla bilgi için bkz. [proje sisteminde Linux C++ Iş yükü geliştirmeleri, Linux konsol penceresi, rsync ve Işleme iliştirme](https://devblogs.microsoft.com/cppblog/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- Uzak Linux bağlantılarında üst bilgiler için IntelliSense. Daha fazla bilgi için bkz. [uzak Linux üstbilgileri Için IntelliSense](https://devblogs.microsoft.com/cppblog/intellisense-for-remote-linux-headers/) ve [bir Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-for-android-and-ios"></a>Android ve iOS için C++ ile mobil geliştirme

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır. Şu anda C++ projelerini el ile yükseltmeniz gerekir. Visual Studio 2017 ' de v140 hedefli bir Evrensel Windows Platformu Projesi açabilirsiniz. Ancak, Visual Studio 2015 yüklü değilse proje özelliği sayfalarında v141 platform araç takımını seçmeniz gerekir.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>Evrensel Windows Platformu C++ için yeni seçenekler (UWP)

Artık Evrensel Windows Platformu ve Windows Mağazası için C++ uygulamaları yazmak ve paketlemeye yönelik yeni seçenekleriniz vardır: Masaüstü köprü altyapısı, mevcut masaüstü uygulamanızı veya COM nesnesini Windows Mağazası aracılığıyla dağıtım için paketlemenizi sağlar. Ya da, dışarıdan yükleme yoluyla mevcut kanallarınız aracılığıyla dağıtım için. Windows 10 ' daki yeni yetenekler, masaüstü uygulamanıza çeşitli yollarla UWP işlevselliği eklemenize olanak tanır. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Masaüstü ile masaüstü uygulamalarının paketlenmesi büyük ölçüde basitleşerek bir **Windows uygulaması paketleme projesi** proje şablonu eklenmiştir. Dosya | altında kullanılabilir **Yeni | Proje | Yüklendi | Visual C++ | Evrensel Windows Platformu**. Daha fazla bilgi için bkz. [Visual Studio (Masaüstü Köprüsü) kullanarak bir uygulamayı paketleme](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

Yeni kod yazarken artık yalnızca başlık dosyalarında uygulanan Windows Çalışma Zamanı için standart bir C++ dil projeksiyonu olan C++/Wınrt ' i kullanabilirsiniz. Standartlara uygun C++ derleyicisini kullanarak Windows Çalışma Zamanı API 'Leri kullanmanıza ve yazmanıza olanak sağlar. C++/Wınrt, C++ geliştiricilerine modern Windows API 'sine birinci sınıf erişim sağlayacak şekilde tasarlanmıştır. Daha fazla bilgi için bkz. [C++/Wınrt](/windows/uwp/cpp-and-winrt-apis/).

Windows SDK Insider Preview 'ın derleme 17025 ' den başlayarak, C++/Wınrt Windows SDK dahil edilmiştir. Daha fazla bilgi için bkz. [C++/Wınrt artık Windows SDK içeriyor](https://devblogs.microsoft.com/cppblog/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="the-clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Visual Studio 2017 ile birlikte gelen Clang/C2 araç takımı artık **`/bigobj`** büyük projeler oluşturmak için önemli olan anahtarı desteklemektedir. Ayrıca, hem derleyici ön ucu hem de arka uçta bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ kod analizi

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Projenin özellik sayfalarındaki **Kod Analizi uzantıları** sayfasında bulunan denetleyicileri etkinleştirin. Uzantılar daha sonra kod analizini çalıştırdığınızda dahil edilir. Daha fazla bilgi için bkz. [C++ temel yönergeleri denetleyicileri kullanma](../code-quality/using-the-cpp-core-guidelines-checkers.md).

![Yapılandırma özelliklerini gösteren özellik sayfaları iletişim kutusunun ekran görüntüsü > kod analizi > genel seçili ve bu kural kümesini çalıştır bölümünde listelenen birtakım çekirdek denetimleri.](media/CppCoreCheck.png "CppCoreCheck özellikleri sayfası")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Kaynak yönetimiyle ilgili kurallar için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Yeni C++ Temel Yönergeleri denetimleri, akıllı işaretçi doğruluğunu, genel başlatıcıların doğru kullanımını ve benzer yapıların kullanımını **`goto`** ve hatalı yayınları kapsamasını kapsar.

- 15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- Tek Dosya Analizi için destek eklendi ve çözümleme çalışma zamanı performansı geliştirmeleri. Daha fazla bilgi için bkz. [Visual Studio için C++ statik analiz geliştirmeleri 2017 15,6 Preview 2](https://devblogs.microsoft.com/cppblog/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- İçin destek eklendi [`/analyze:ruleset`](../build/reference/analyze-code-analysis.md) , bu, çalıştırılacak kod analizi kurallarını belirtmenize olanak tanır.
- Ek C++ Temel Yönergeleri kuralları için destek eklendi.  Daha fazla bilgi için bkz. [C++ temel yönergeleri denetleyicileri kullanma](../code-quality/using-the-cpp-core-guidelines-checkers.md).

## <a name="unit-testing-in-visual-studio-2017"></a>Visual Studio 2017 ' de birim testi

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Google Test bağdaştırıcı ve Boost. test bağdaştırıcısı artık C++ iş yükü **Ile masaüstü geliştirmenin** bileşenleri olarak sunulmaktadır. **Test Gezgini** ile tümleştirilebilir. CMake projeleri için CTest desteği eklenmiştir (açık klasör kullanılarak), ancak **Test Gezgini** ile tam tümleştirme henüz kullanılamaz. Daha fazla bilgi için bkz. [C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- `Boost.Test`Dinamik kitaplık desteği için destek eklendi.
- Bir `Boost.Test` öğe şablonu artık IDE 'de kullanılabilir.

Daha fazla bilgi için bkz. [ `Boost.Test` birim testi: dinamik kitaplık desteği ve yeni öğe şablonu](https://devblogs.microsoft.com/cppblog/boost-test-unit-testing-dynamic-library-support-and-new-item-template/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

C++ birim testi projeleri için [CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) desteği eklendi. Daha fazla bilgi için bkz. [C++ birim testi Için CodeLens duyurusu](https://devblogs.microsoft.com/cppblog/announcing-codelens-for-c-unit-testing/).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio Grafik Tanılama araçları: bunları, Direct3D uygulamalarında işleme ve performans sorunlarını kaydetmek ve analiz etmek için kullanabilirsiniz. Bunları Windows bilgisayarınızda, Windows cihaz öykünücüsünde veya uzak bir bılgısayarda veya cihazda yerel olarak çalışan uygulamalarda kullanın.

- **Köşe ve geometri gölgelendiriciler Için giriş & çıkışı:** Köşe Gölgelendiricileri ve geometri gölgelendiricilerin giriş ve çıkışını görüntüleyebilme özelliği, en çok istenen özelliklerden biridir. Artık araçlar 'da desteklenmektedir. Giriş ve çıkışını aşağıdaki tabloda inceleyerek başlamak için ardışık düzen aşamaları görünümünde VS veya GS aşamasını seçin.

  ![Gölgelendiriciler için giriş/çıkış](media/io-shaders.png)

- **Nesne tablosunda arama ve filtreleme:** Aradığınız kaynakları bulmanın hızlı ve kolay bir yolunu sağlar.

  ![Tür açılan listesi ve arama metin kutusu olarak adlandırılan nesne tablosu bölümünün ekran görüntüsü.](media/search.png)

- **Kaynak geçmişi:** Bu yeni görünüm, yakalanan bir çerçevenin işlenmesi sırasında kullanılan bir kaynağın tüm değişiklik geçmişini görmenin kolaylaştırılmış bir yolunu sunar. Herhangi bir kaynak için geçmişi çağırmak üzere herhangi bir kaynak köprüsü yanındaki saat simgesine tıklayın.

  ![Kaynak geçmişi](media/resource-history.png)

  Kaynağın değişiklik geçmişiyle doldurulan yeni **kaynak geçmişi** araç penceresini görüntüler.

  ![Kaynak geçmişi değişikliği](media/resource-history-change.png)

  Tam çağrı yığını yakalamanın etkin olduğu kareleri yakalayabilirsiniz. Bu, her değişiklik olayının bağlamını hızlı bir şekilde düzenlemenizi ve Visual Studio projeniz içinde incelemenizi sağlar. **Grafik tanılama** altındaki Visual Studio **araçları > seçenekleri** iletişim kutusunda tam yığın yakalama seçeneğini ayarlayın.

- **API İstatistikleri:** Çerçeveinizdeki API kullanımının üst düzey özetini görüntüleyin. Her seferinde yaptığınız fark etmeyebilirsiniz ya da çok sık yaptığınız çağrıları bulmak için, aramaları keşfetmek yararlı olur. Bu pencere, Visual Studio Grafik Çözümleyicisi içindeki **View > API istatistikleri** aracılığıyla kullanılabilir.

  ![API istatistikleri](media/api-stats.png)

- **Bellek İstatistikleri:** Çerçevede oluşturduğunuz kaynaklar için sürücünün ne kadar bellek ayırdığını görüntüleyin. Bu pencere, **Visual Studio grafik Çözümleyicisi**' de **görüntüleme > bellek istatistikleri** aracılığıyla kullanılabilir. Bir elektronik tabloda görüntülenmek üzere bir CSV dosyasına veri kopyalamak için sağ tıklayın ve **Tümünü Kopyala**' yı seçin.

  ![Bellek istatistikleri](media/memory-stats.png)

- **Çerçeve doğrulaması:** Yeni hatalar ve uyarılar listesi, Direct3D hata ayıklama katmanının algıladığı olası sorunlara göre olay listenizde gezinmek için kolay bir yol sağlar. Pencereyi açmak için Visual Studio Grafik Çözümleyicisi **> çerçeve doğrulamayı görüntüle** ' ye tıklayın. Ardından, çözümlemeyi başlatmak için **doğrulamayı Çalıştır** ' a tıklayın. Çerçevenin karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **D3D12 Için Çerçeve Analizi:** Çerçeve analizini, yönlendirilmiş "durum" denemeleri ile çizilen çağrı performansını çözümlemek için kullanın. Çerçeve Analizi sekmesine geçin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için, [Goingnative 25: Visual Studio grafik çerçeve çözümlemesi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) videosunu izleyin.

  ![Çerçeve Analizi](media/frame-analysis.png)

- **GPU kullanımı iyileştirmeleri:** Açık izlemeler, daha ayrıntılı analizler için GPU görünümü veya Windows Performans Çözümleyicisi (WPA) aracıyla Visual Studio GPU kullanımı profil oluşturucu aracılığıyla alınabilir. Windows performans araç seti yüklüyse, oturum genel bakış ' a yönelik olarak bir WPA ve GPU görünümü için bir tane olmak üzere iki köprü bulunur.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı aracılığıyla GPU görünümünde açtığınız izlemeler, eşitlenen VS ve GPU görünümü zaman çizelgesi yakınlaştırmasını ve yatay kaydırmayı destekler. VS 'deki bir onay kutusu, eşitlemenin etkin olup olmadığını denetler.

  ![GPU görünümü](media/gpu-view.png)
