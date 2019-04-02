---
title: Visual Studio'da C++ için Yenilikler
ms.date: 11/15/2017
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: bdf9775702b2c7099bcacc82fd462e3c1ff245bc
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787659"
---
# <a name="whats-new-for-c-in-visual-studio-2017"></a>Visual Studio 2017'de C++ için Yenilikler

Visual Studio 2017 birçok güncelleştirme ve C++ ortamına giderir. Biz 250'den fazla hatalar düzeltildi ve bildirilen sorunları derleyici ve araçları, aracılığıyla müşteriler tarafından birçok gönderilen [sorun bildir](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) ve [bir öneride](https://visualstudio.uservoice.com/) altında seçenekleri **geri bildirim gönder** . Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio'nun tüm yenilikler hakkında daha fazla bilgi için lütfen [Visual Studio 2017'deki yenilikler](/visualstudio/ide/whats-new-in-visual-studio).

<!--The compiler and tools version number in Visual Studio 2017 is 14.10.24629. -->

## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uyumluluk geliştirmeleri

Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için bkz. [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md).

**Visual Studio 2017 sürüm 15.5**: Derleyici, yaklaşık %75 yapılandırılmış bağlamalar dahil olmak üzere C ++ 17'de yeni özellikleri destekler `constexpr` lambda ifadeleri, `if constexpr`, satır içi değişkenler, katlama ifadeleri ve ekleme `noexcept` tür sistemine. Bunlar altında kullanılabilir **/Std: c ++ 17** seçeneği. Daha fazla bilgi için [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md)

**Visual Studio 2017 sürüm 15.7**: Visual Studio'da sürüm 15.7 MSVC derleyici araç takımı artık C++ standardı ile uyumludur. Daha fazla bilgi için [Announcing: MSVC C++ standartlarına uyup](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/) ve [Microsoft C++ dil uyumluluğu](visual-cpp-language-conformance.md).

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [/ permissive-](../build/reference/permissive-standards-conformance.md): Tüm katı standartlar uyumluluk derleyici seçenekleri etkinleştirin ve çoğu özel Microsoft derleyici uzantılarını devre dışı bırak (ama `__declspec(dllimport)`, örneğin). Bu seçenek varsayılan olarak Visual Studio 2017 sürüm 15.5 açıktır.  **/ Permissive-** uyumluluk modu, iki aşamalı ad aramayı için destek içerir. Daha fazla bilgi için [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md).

- [/ Diagnostics](../build/reference/diagnostics-compiler-diagnostic-options.md): Satır numarası, satır numarası ve sütun veya satır numarasını ve sütun ve şapka işareti tanılama hata veya uyarı bulunduğu kod satırının altında görüntülenmesini sağlar.

- [/debug:fastlink](../build/reference/debug-generate-debug-info.md): Etkinleştirme % 30 daha hızlı artımlı bağlantı süreleri (vs. Visual Studio 2015) değil kopyalayarak tüm PDB dosyasına hata ayıklama bilgileri. PDB dosyası, yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplığı dosyaları için hata ayıklama bilgileri için bunun yerine işaret eder. Bkz: [daha hızlı C++ derleme/debug: fastlink ile VS "15" döngüsünde](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) ve [derlemeler Visual Studio'da C++ önerileri hızına](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

- Visual Studio 2017 sağlayan kullanarak [/SDL](../build/reference/sdl-enable-additional-security-checks.md) ile [/ await](../build/reference/await-enable-coroutine-support.md). Kaldırdık [/RTC](../build/reference/rtc-run-time-error-checks.md) eş yordamlar sınırlama.

   **Visual Studio 2017 sürüm 15.3**:

- [/ Std: c ++ 14 ve/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md): Bu derleyici seçeneklerinin bir proje ISO C++ programlama dilinde belirli sürümlerine katılımı olanak sağlar. Standart özellikler tarafından korunan yeni taslak çoğu **/Std: c ++ Son** seçeneği.

- [/ Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) derleyici tarafından uygulanan C ++ 17 özellikleri kümesini sağlar. Bu seçenek, C ++ 17 sonra derleyici ve değiştirilen özellikler veya yeni sürümlerinde C++ standart çalışma taslak ve hata güncelleştirmeleri standart kitaplığı desteği devre dışı bırakır. Bu özellikleri etkinleştirmek için **/Std: c ++ Son**.

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Bu sürüm, iyileştirme, kod oluşturma, araç takımı sürümü oluşturma ve tanılama çeşitli iyileştirmeler getirir. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: Otomatik vektörleştirme sabit tamsayı, memset desenlerinin daha iyi kimlik için destek.
- Geliştirilmiş kod güvenliği: Geliştirilmiş arabellek taşma derleyici Tanılaması, arabellek ve [/Guard: cf](../build/reference/guard-enable-control-flow-guard.md) artık atlama tablosu oluşturan deyimleri cf switch.
- Sürüm oluşturma: Yerleşik önişlemci makrosu değerini  **\_MSC\_VER** şu anda tekdüze her Visual C++ araç takımı güncelleştirmeyi güncelleştiriliyor. Daha fazla bilgi için [Visual C++ Derleyici sürümü](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Yeni araç takımı düzeni: Derleyici ve ilgili derleme araçları, geliştirme makinenizde yeni bir konum ve dizin yapısı sahip. Yeni düzen derleyici birden çok sürümünü yan yana yüklemesini sağlar. Daha fazla bilgi için [derleyici araçları Visual Studio "15" düzende](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Gelişmiş Tanılama: Çıkış penceresi bir hata oluştuğu sütunu artık gösterir. Daha fazla bilgi için [C++ Derleyici tanılama geliştirmeleri VS "15" Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Deneysel anahtar sözcüğü ortak yordamlar kullanılırken **yield** (altında kullanılabilir **/ await** seçeneği) kaldırıldı. Kodunuzu kullanacak şekilde güncelleştirilmesi `co_yield` yerine. Daha fazla bilgi için [Visual C++ Ekip bloguna](https://blogs.msdn.microsoft.com/vcblog/) bakın.

**Visual Studio 2017 sürüm 15.3**:

Ek derleyici tanılama iyileştirmeleri. Daha fazla bilgi için [Visual Studio 2017 ' 15.3.0 tanılama geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/).

**Visual Studio 2017 sürüm 15.5**:

Visual C++ çalışma zamanı performans nedeniyle daha iyi oluşturulan kod kalitesini iyileştirmeye devam eder. Bunun anlamı, basitçe kodunuzu derleyebilirsiniz ve uygulamanızı daha hızlı çalışır. Derleyici iyileştirmelerini bazıları yepyeni, koşullu skaler depoları, birleştirme çağrılarının vektörleştirme gibi `sin(x)` ve `cos(x)` içine yeni bir `sincos(x)`ve yedekli SSA İyileştiricisine ilişkin yönergeleri saydamlığından. Diğer derleyici iyileştirmeleri koşullu ifadeler, daha iyi döngü en iyi duruma getirme ve float min/maks codegen vektör hale getirici buluşsal yöntemler gibi mevcut işlevine geliştirmeleridir. Yeni bir ve daha hızlı bağlayıcı sahip **/OPT: ICF** % 9 sonuçta uygulama zaman hızlanma bağlantısını ve artımlı bağlamayı diğer performans düzeltmeleri olan. Daha fazla bilgi için [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md) ve [/Incremental (artımlı bağlantı)](../build/reference/incremental-link-incrementally.md).

Microsoft C++ derleyicisi, Intel AVX-512 AVX-512 ile birlikte 128 ve 256 bit genişliğinde kayıtlara yönelik yeni işlevler getiren sunan vektör uzunluğu yönergeleri de dahil olmak üzere, destekler.

[/Zc:noexceptTypes-](../build/reference/zc-noexcepttypes.md) seçeneği, C ++ 14 sürümüne geri almak için kullanılabilir `noexcept` genel C ++ 17 modunda kullanırken. Bu, tüm yeniden yazmak zorunda kalmadan C ++ 17'ye uyması için kaynak kodunuzu güncelleştirmenizi sağlar, `throw()` aynı zamanda kod. Daha fazla bilgi için [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements-2017.md#noexcept_removal).

**Visual Studio 2017 sürüm 15.7**:

- Yeni derleyici anahtarı [/qspectre ](../build/reference/qspectre.md) kurgusal yürütme yan kanal saldırıları önlemeye yardımcı olmak için. Bkz: [Spectre azaltmaları MSVC içinde](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc/) daha fazla bilgi için.
- Spectre migitation için yeni tanılama uyarı. Bkz: [Spectre Visual Studio 2017 sürüm 15.7 Önizleme 4'te tanılama](https://blogs.msdn.microsoft.com/vcblog/2018/04/20/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/) daha fazla bilgi için.
- /Zc için yeni bir değer **/ZC: __cplusplus**, etkinleştirir C++ Standart Destek Raporlama düzeltin. Örneğin, ne zaman geçiş ayarlanmışsa ve derleyici/Std: c ++ 17 modunda değeri genişletilir **201703 L**. Bkz: [MSVC artık __cplusplus doğru şekilde rapor](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/msvc-now-correctly-reports-__cplusplus/) daha fazla bilgi için.

## <a name="c-standard-library-improvements"></a>C++ Standart Kitaplığı geliştirmeleri

- Küçük `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` tanılama geliştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- Performans iyileştirmesi: yapılan `basic_string::find(char)` yalnızca çağrı aşırı `traits::find` sonra. Daha önce bu, 1 uzunluğunda bir dizenin genel dize araması olarak uygulanıyordu.
- Performans iyileştirmesi: `basic_string::operator==` artık dizelerin içeriklerini karşılaştırmadan önce dizenin boyutunu denetler.
- Performans iyileştirmesi: içinde zorlandığı denetim ilişkilendirme kaldırıldı `basic_string`, analiz etmek için derleyici iyileştiricisi zor olduğu. Çağırarak tüm kısa dizeler için unutmayın `reserve` hala hiçbir şey yapma sıfır olmayan bir maliyeti vardır.
- Eklediğimiz \<herhangi\>, \<string_view\>, `apply()`, `make_from_tuple()`.
- `std::vector` doğruluk ve performans açısından bakımdan geçirildi: ekleme ve yerleştirme sırasında diğer ad oluşturma artık doğru şekilde ele alınır olarak standart tarafından gerekli güçlü özel durum garantisi artık standart tarafından gerekli olduğunda sağlanan `move_if_noexcept()` ve başka bir mantık ve ekleme/yerleştirme daha az öğe işlemi gerçekleştirir.
- C++ Standart Kitaplığı, artık null karmaşık işaretçilere başvurmaktan kaçınır.
- Eklenen \<isteğe bağlı\>, \<değişken\>, `shared_ptr::weak_type`, ve \<cstdalign\>.
- C ++ 14 etkin `constexpr` içinde `min(initializer_list)`, `max(initializer_list)`, ve `minmax(initializer_list)`, ve `min_element()`, `max_element()`, ve `minmax_element()`.
- Geliştirilmiş `weak_ptr::lock()` performans.
- Sabit `std::promise` taşıma atama işlecini daha önce kod engellenmesine neden olabilir.
- Derleyici hataları düzeltildi `atomic<T*>` örtük olarak dönüştürülmesine `T*`.
- `pointer_traits<Ptr>` artık doğru şekilde algılıyor `Ptr::rebind<U>`.
- Eksik bir sabit `const` niteleyicisi `move_iterator` çıkarma işleci.
- İsteyen durum bilgisi olan kullanıcı tanımlı ayırıcılar için sessiz hatalı codegen düzeltildi `propagate_on_container_copy_assignment` ve `propagate_on_container_move_assignment`.
- `atomic<T>` artık göstereceği aşırı `operator&()`.
- Derleyici verimliliğini artırmak için bildirimler için gerekli olmayan derleyici iç bilgileri dahil olmak üzere standart C++ Kitaplığı üstbilgilerini artık kaçının.
- Biraz daha geliştirilmiş derleyici tanılama için yanlış `bind()` çağırır.
- Performansı geliştirildi `std::string` ve `std::wstring` taşıma oluşturucuları üçten fazla sürelerine göre.

Standart Kitaplığı tam bir listesi için bkz: geliştirmelerin [standart kitaplığı düzeltmeleri, VS 2017 RTM'de](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/).

### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

#### <a name="c17-features"></a>C ++ 17 özellikleri

Birkaç ek C ++ 17 özellikleri uygulanmıştır. Daha fazla bilgi için [Visual C++ dil uyumluluğu](cpp-conformance-improvements-2017.md#improvements_153).

#### <a name="other-new-features"></a>Diğer yeni özellikler

- Uygulanan P0602R0 "değişken ve isteğe bağlı kopyalama/taşıma triviality yayılması".
- Standart kitaplık artık resmi olarak aracılığıyla devre dışı bırakılmasını dinamik RTTI göstereceği [denetleyen](../build/reference/gr-enable-run-time-type-information.md) seçeneği. Her ikisi de `dynamic_pointer_cast()` ve `rethrow_if_nested()` kendiliğinden gerektiren `dynamic_cast`, standart kitaplık artık olarak işaretler `=delete` altında **denetleyen**.
- Hatta, dinamik RTTI aracılığıyla devre dışı bırakıldı **denetleyen**, "statik RTTI" (biçiminde `typeid(SomeType)`) hala kullanılabilir ve birkaç standart kitaplık bileşeni güçlendirir. Standart kitaplık artık, bunu devre dışı bırakma destekler aracılığıyla **/D\_HAS\_statik\_RTTI = 0**. Bu devre dışı bırakır Not `std::any`, `target()` ve `target_type()` üye işlevleri `std::function`ve `get_deleter()` arkadaş üye işlevinin `std::shared_ptr` ve `std::weak_ptr`.

#### <a name="correctness-fixes-in-visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3 doğruluk giderir

- Standart Kitaplığı kapsayıcıları şimdi clamp kendi `max_size()` için `numeric_limits<difference_type>::max()` yerine `max()` , `size_type`. Bu sonucu sağlar `distance()` yineleyiciler bu kapsayıcısından dönüş türü içinde gösterilebilir olan `distance()`.
- Eksik özelleştirmesi sabit `auto_ptr<void>`.
- `for_each_n()`, `generate_n()`, Ve `search_n()` algoritmaları daha önce başarısız uzunluk değişkeni integral türünde değildi derlemeniz; bunlar artık yineleyicileriyle tamsayı olmayan uzunlukları dönüştürmeyi denemeden `difference_type`.
- `normal_distribution<float>` artık kaydırmak için standart çift daraltma hakkında kitaplığı içinde uyarılar gönderir.
- Bazı sabit `basic_string` ile karşılaştırma işlemleri `npos` yerine `max_size()` için en büyük boyutu taştı denetlenirken.
- `condition_variable::wait_for(lock, relative_time, predicate)` sahte Uyandırma durumunda tüm göreli süre beklemeniz gerekir. Artık, yalnızca bir tek göreli zaman aralığı için bekler.
- `future::get()` artık geçersiz kılar `future`gibi standart gerektirir.
- `iterator_traits<void *>` Forma çalıştığı için bir donanım hatası kullanılan `void&`; artık düzgün bir şekilde kullanımına olanak tanımak için boş bir yapı olur `iterator_traits` "yineleyici olduğunu" SFINAE koşulları.
- Bazı uyarılar bildirdi Clang tarafından **- Wsystem-headers** düzeltilmiştir.
- Ayrıca "özel durum belirtimi bildiriminde önceki bildirimi Clang tarafından bildirilen eşleşmiyor" sabit **- Wmicrosoft özel durum belirtimi**.
- Clang C1XX tarafından bildirilen ve bellek başlatıcı listesi sıralama uyarıları da düzelttik.
- Kapsayıcıları değiştirildi, sırasız hashers ya da doğrulamaları takas değil. Bunlar şimdi yapın.
- Çok sayıda kapsayıcı değiştirme işlemleri artık işaretlendi `noexcept` (standart Kitaplığımızı hiçbir zaman bir özel dışı tespit edilirken durum amaçlayan gibi`propagate_on_container_swap` eşit ayırıcı olmayan tanımsız davranış koşul).
- Birçok `vector<bool>` işlemleri artık işaretlenmiş `noexcept`.
- Standart kitaplık artık eşleşen ayırıcı zorlar `value_type` (, C ++ 17 modunda) ile bir geri çevirme kaçış noktası.
- Bazı koşullar self range INSERT burada içine sabit `basic_string` dizeleri içeriğini karıştırmak. (Not: self-range-insert into'nun vektörleri hala standart tarafından kullanılamaz.)
- `basic_string::shrink_to_fit()` ayırıcı tarafından 's artık etkilenir `propagate_on_container_swap`.
- `std::decay` artık abominable işlevi türleri (cv nitelenmiş ve/veya ref koşullu olan başka bir deyişle işlevi türleri) işler.
- Değiştirilen doğru büyük/küçük harf duyarlılığı ve taşınabilirlik geliştirme eğik kullanmak için yönergeleri içerir.
- Uyarı C4061 sabit "Numaralandırıcı '*Numaralandırıcı*'numaralandırıcısının switch' ın*numaralandırma*' case etiketi tarafından açıkça işlenmiyor". Bu uyarı devre dışı varsayılan olarak ve standart kitaplık Genel İlke Uyarıları için bir özel durum olarak düzeltildi. (Standart kitaplık **/W4** temizlemek, ancak olacak şekilde denemez **/Wall** temiz. Çok sayıda kapalı varsayılan olarak uyarı çok gürültülü ve düzenli olarak kullanılmaya yönelik değildir.)
- Geliştirilmiş `std::list` hata ayıklama denetler. Liste yineleyiciler şimdi onay `operator->()`, ve `list::unique()` artık yineleyiciler geçersiz olarak işaretler.
- Ayırıcı olarak azaltılarak kullanan sabit `tuple`.

#### <a name="performancethroughput-fixes"></a>Performans/aktarım hızı düzeltmeleri

- Etkileşim etrafında çalışılan `noexcept` inlining'i engelleyen `std::atomic` yapılandırılmış özel durum işleme (SEH) kullanan bir işlev uygulamasına.
- Standart kitaplık iç değiştirilen `_Deallocate()` daha fazla yerde eklenmesini izin veren, daha küçük bir kodun içine iyileştirmek için işlevi.
- Değiştirilen `std::try_lock()` paket genişletmesi özyineleme yerine kullanılacak.
- Geliştirilmiş `std::lock()` kullanılacak kilitlenme kaçınma algoritmasını `lock()` işlemleri üzerinde dönen yerine `try_lock()` kilitleri üzerinde.
- Adlı dönüş değeri iyileştirme etkin `system_category::message()`.
- `conjunction` ve `disjunction` N + 1 türleri, 2N + 2 türleri yerine örneği şimdi oluşturun.
- `std::function` artık her tür silinmiş çağrılabilir, iyileştirme aktarım hızı ve geçirmek için birçok farklı lambdalar programlarda azalan .obj boyutu ayırıcı desteği makineler başlatır `std::function`.
- `allocator_traits<std::allocator>` el ile satır içine alınmış içeren `std::allocator` etkileşimde kodda kod boyutunu küçültme işlemlerini `std::allocator` aracılığıyla `allocator_traits` yalnızca (diğer bir deyişle, içinde çoğu kod).
- C ++ 11 minimal ayırıcılar arabiriminin artık standart kitaplığı tarafından işlenen çağırma `allocator_traits` bir iç sınıf ayırıcısı sarmalama yerine doğrudan `_Wrap_alloc`. Bu ayırıcı desteği için oluşturulan kod boyutunu azaltır, bazı durumlarda standart kitaplığı kapsayıcıları hakkında neden iyileştirici'nin olanağı artırır ve daha iyi hata ayıklama deneyimi sağlar (ayırıcı türünüz artık gördüğünüz gibi yerine `_Wrap_alloc<your_allocator_type>` içinde hata ayıklayıcı).
- Özelleştirilmiş azaltılarak kaldırıldı `allocator::reference`, hangi ayırıcılar gerçekten izin verilmiyor özelleştirmek için. (Ayırıcılar karmaşık işaretçilere başvurmaktan ancak değil başvurmaktan başvuruları kapsayıcıları yapabilirsiniz.)
- Derleyici ön ucu, hata ayıklama Yineleyicilerde aralık tabanlı for-döngüleri, hata ayıklama yapıları performansını iyileştirme açılacak verilen.
- `basic_string` İç küçültme yolu `shrink_to_fit()` ve `reserve()` artık mutating tüm üyeler için kod boyutunu küçültme işlemlerini tahsis yolunda değil.
- `basic_string` İç Büyüt yoldur artık yolunda `shrink_to_fit()`.
- `basic_string` Diziyi operations artık hızlı yolu olmayan ayırma ve çağıranlar eklenmesini sağlamak ve ortak Hayır yeniden ayırma çalışması için büyük olasılıkla yapma, ayırma yavaş yola işlevleri factored.
- `basic_string` Yerinde yeniden boyutlandırma yerine yapısı bir arabellek istenen durumda yeniden artık operations diziyi. (Örneğin, başında bir dize artık ekleme içeriği ekleme (aşağı veya yeni ayrılan arabelleğin), sonra tam bir kez yerine iki kez reallocating durumda yeni ayrılan arabelleğin ve sonra aşağı) taşır.
- Standart C Kitaplığı arayan operations \<dize\> artık önbelleğe `errno` TLS ile yinelenen etkileşimleri kaldırmak için adres.
- Basitleştirilmiş `is_pointer` uygulaması.
- İşlev tabanlı ifade SFINAE için değiştirme işlemi tamamlandı `struct` ve `void_t`-tabanlı.
- Standart Kitaplığı algoritmalarıdır artık yineleyiciler postincrementing kaçının.
- 32-bit ayırıcılar 64-bit sistemlerde kullanırken sabit kesilmesi uyarıları.
- `std::vector` taşıma ataması artık mümkün olduğunda arabellek yeniden kullanarak POCMA olmayan eşit ayırıcı durumda daha verimli olur.

#### <a name="readability-and-other-improvements"></a>Okunabilirlik ve diğer iyileştirmeler

- Standart kitaplık artık C ++ 14 kullanan `constexpr` koşulsuz olarak, koşullu olarak tanımlı makrolar yerine.
- Standart kitaplık artık diğer ad şablonları dahili olarak kullanır.
- Standart kitaplık artık kullanan `nullptr` dahili olarak yerine, `nullptr_t{}`. (İç kullanım null eradicated. İç kullanım 0 olarak null kademeli olarak Temizlenen.)
- Standart kitaplık artık kullanan `std::move()` stylistically kötüye yerine dahili olarak `std::forward()`.
- Değiştirilen `static_assert(false, "message")` için `#error message`. Bu derleyici tanılaması için artırır `#error` derleme hemen durdurur.
- Standart kitaplık artık işlev olarak işaretler `__declspec(dllimport)`. Modern bağlayıcı teknolojisi, artık bu gerektirir.
- Dönüş türleri ve işlev bağımsız değişken türleri için karşılaştırma dağınıklığı azaltan ayıklanan SFINAE için varsayılan şablon bağımsız değişkenleri.
- Hata ayıklama iade \<rastgele\> artık standart kitaplığının her zamanki makineler yerine iç işlevini kullanın `_Rng_abort()` olarak adlandırılan `fputs()` için **stderr**. Bu işlevin uygulama ikili uyumluluk için tutulmaktadır, ancak standart Kitaplığı'nın sonraki ikili uyumsuz sürümünde kaldırılmıştır.

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Birçok standart kitaplık özellikleri eklenmiş, kullanım dışı veya C ++ 17 standardına uygun olarak kaldırıldı. Daha fazla bilgi için [Visual Studio'da C++ uyumluluk geliştirmeleri](cpp-conformance-improvements-2017.md#improvements_155).

#### <a name="new-experimental-features"></a>Yeni bir Deneysel Özellikler

- Aşağıdaki paralel algoritmalar için Deneysel desteği:
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- Aşağıdaki paralel algoritmalar imzaları eklendi ancak şu anda paralelleştirilmedi; Profil oluşturma, taşıma veya öğeleri permute algoritmalar paralelleştirmek içinde hiçbir avantajı gösterilmiştir:
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

#### <a name="performance-fixes-and-improvements"></a>Performans düzeltmeleri ve geliştirmeleri

- `basic_string<char16_t>` artık aynı ilgilenir `memcmp`, `memcpy`ve benzer iyileştirmeler, `basic_string<wchar_t>` ilgilenir.
- Visual Studio 2015 güncelleştirme 3'te kullanıma sunduğumuz "işlevleri kopyalamama tarafından" engeller önlenmiş işlev işaretçileri satır içine alınmış çalışan bir iyileştirici sınırlaması geçici, geri yükleme performansını çalışmıştır `lower_bound(iter, iter, function pointer)`.
- Yineleyici hata ayıklama ek yükü girişleri siparişi doğrulaması kullanıcının `includes`, `set_difference`, `set_symmetric_difference`, ve `set_union` açma yineleyiciler tarafından sipariş denetlemeden önce düşürüldü.
- `std::inplace_merge` artık konumda zaten olan öğeler üzerinden atlar.
- Oluşturma `std::random_device` artık oluşturur ve ardından yok eder bir `std::string`.
- `std::equal` ve `std::partition` bir yineleyici karşılaştırma kaydedileceği bir atlama iş parçacığı oluşturma en iyi duruma getirme geçişi vardı.
- Zaman `std::reverse` işaretçileri için artık önemsiz olarak kopyalanabilir geçirilen `T`, artık el ile yazılmış bir vektör haline getirilmiş uygulamasına gönderir.
- `std::fill`, `std::equal`, ve `std::lexicographical_compare` gönderilmesi için nasıl verilen `memset` ve `memcmp` için `std::byte` ve `gsl::byte` (diğer char benzeri sabit listeleri ve enum sınıfları). Unutmayın `std::copy` kullanarak dağıtır `is_trivially_copyable` ve bu nedenle herhangi bir değişiklik ihtiyacım kalmadı.
- Standart kitaplık artık, tür olmayan-basit bir şekilde-yıkıcı yapmak, yalnızca bir davranış olduğu boş küme ayraçları Yıkıcılar içerir.

#### <a name="correctness-fixes-in-visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5 doğruluk giderir

- `std::partition` artık aramalar standart koşul N kez yerine N + 1 kez gerektirir.
- Sürüm 15.5 sürüm 15.3 Sihirli İstatistikler önlemek için deneme onarıldı.
- `std::atomic<T>` artık gerektirmez `T` atmamalıdır varsayılan olarak kullanılacak.
- Artık Logaritmik zaman yığın algoritmaları yineleyici hata ayıklama etkinleştirildiğinde giriş aslında yığın olduğunu bir doğrusal zaman onaylama işlemi yapın.
- `__declspec(allocator)` Şimdi, bu declspec anlamıyor Clang gelen uyarıları önlemek yalnızca C1XX için korunur.
- `basic_string::npos` bir derleme zamanı sabiti kullanıma sunulmuştur.
- `std::allocator` doğru aşırı hizalanmış türlere tanıtıcıları ayrılması hizalamasını diğer bir deyişle, türleri artık C ++ 17 modunda büyüktür `max_align_t`devre dışı sürece **/Zc:alignedNew-**.  Örneğin, 16 veya 32 bayt hizalama nesneleriyle vektörleri artık düzgün şekilde için SSE ve AVX yönerge hizalanır.

### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- \<memory_resource >
- Kitaplık temelleri V1
- Polymorphic_allocator ataması siliniyor
- Sınıf şablonu bağımsız değişkeni kesintisi geliştirme

### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- Destek için paralel algoritmalar experiemental artık değil
- Yeni bir uygulamasını \<filesystem >
- temel dize dönüştürme (kısmi)
- Std::launder()
- Std::byte
- hypot(x,y,z)
- gereksiz decay kaçınma
- Özel matematik işlevleri
- constexpr char_traits
- STL için çıkarım kılavuzları

Bkz: [Visual C++ dil uyumluluğu](visual-cpp-language-conformance.md) daha fazla bilgi için.

## <a name="other-libraries"></a>Diğer kitaplıkları

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg** alınıyor ve açık kaynak C++ statik kitaplıklar ve Visual Studio'da DLL'leri oluşturma işlemini büyük ölçüde basitleştiren bir açık kaynak komut satırı aracıdır. Daha fazla bilgi için [vcpkg: C++ için Paket Yöneticisi](../build/vcpkg.md).

**Visual Studio 2017 sürüm 15.5**:

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0'da

C++, platformlar arası web API'si CPPRestSDK 2.9.0'da sürümüne güncelleştirildi. Daha fazla bilgi için [CppRestSDK 2.9.0'da Github'da kullanılabilir](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

- Henüz başka bir ad arama uyumluluğu düzeltmeleri kümesi
- Mevcut taşıma oluşturucuları ve taşıma atama işleçleri artık doğru biçimde olarak oluşturmayan işaretlendi
- Kaldırma bastır geçerli C4640 hakkında uyarı iş parçacığı güvenli atlstr.h'de yerel statiklerin yönelik baskılamayı kaldırma
- Yerel statiklerin iş parçacığı güvenli başlatmanın otomatik olarak kapatılıyordu XP araç kümesinde olduğunda [ATL DLL oluşturma ve kullanma]. Bu durum artık geçerli değildir. Ekleyebileceğiniz **/ZC: threadsafeınit** iş parçacığı sorun durumunda proje ayarlarınızın güvenli başlatmanın kapalı istenildiği gibi.

### <a name="visual-c-runtime"></a>Visual C++ çalışma zamanı

- Yeni üstbilgi denetim akışı koruyucusu sembolleri için "cfguard.h".

## <a name="c-ide"></a>C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Artık bir çözüm yapılandırması ilk defa etkinleştirildiğinde daha hızlı çalışır ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında gerçekleşir.

**Visual Studio 2017 sürüm 15.3**:

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf ekleme** artık doğrudan Sınıf Ekle sihirbazını başlatır. Diğer öğeler daha önce burada olan tüm artık altında kullanılabilir **Ekle > Yeni öğe**.
- Win32 projeleri kullanıma altında **Windows Masaüstü** kategorisinde **yeni proje** iletişim.
- **Windows Konsolu** ve **masaüstü uygulaması** şablonları hemen bir sihirbaz görüntülemeden proje oluşturun. Yeni bir **Windows Masaüstü Sihirbazı'nı** eski aynı seçenekleri görüntüleyen aynı kategori altında **Win32 konsol uygulaması** Sihirbazı.

**Visual Studio 2017 sürüm 15.5**:

Yeniden düzenleme ve kod gezintisi için IntelliSense Altyapısı'nı kullanan çeşitli C++ işlemleri çok daha hızlı çalıştırın. Aşağıdaki numaralarını 3500 projeleri Visual Studio Chromium çözümüyle dayanır:

|||
|-|-|
|Özellik|Performansı geliştirme|
|Rename|5.3 x|
|İmzayı Değiştir |4.5 x|
|Tüm Başvuruları Bul|4.7 x|

C++ artık CTRL tuşuna basıp tıklayarak destekliyor **tanıma**, fare gezinme tanımları kolaylaştırın. Yapı Görselleştirici verimlilik güç araçları paketi artık de ürün içinde varsayılan olarak dahil edilir.

## <a name="intellisense"></a>IntelliSense

- Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Bu gibi veritabanı işlemlerini hızlandıracak **tanıma** ve **tüm başvuruları Bul**ve ilk çözüm ayrıştırma süresini önemli ölçüde artırır. Ayar taşındı **Araçlar > Seçenekler > Metin Düzenleyicisi > C/C++ > Gelişmiş** (eski adıyla altında olduğu... C/C++ | Deneysel).

- Projelerinde IntelliSense performansını geliştirdik ve önceden derlenmiş üst bilgiler kullanmayan dosyaları - geçerli dosyadaki üst bilgiler için bir otomatik önceden derlenmiş üst bilgi oluşturulur.

- Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Filtrelenmiş Hata Listesi](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

- Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye Listesi Filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

- Üye Listesi’nde görünenleri bağlama duyarlı olarak filtreleyen yeni bir deneysel Tahmine Dayalı IntelliSense özelliği eklendi. Bkz: [C++ IntelliSense geliştirmeleri - Tahmine dayalı IntelliSense ve filtreleme](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)
- **Tüm başvuruları Bul** (Shift + yardımcı olur, raporlamanızı kolayca bile karmaşık kod tabanlarında artık F12). Gelişmiş gruplandırma, filtreleme, sıralama, (için bazı diller için) ve sonuçları içinde arama sağlar, böylece, başvurularınızı NET bir anlayış renklendirme. C++ için yeni UI olup olmadığını biz okuma veya yazma için bir değişken hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyici özelliklerini **kapsamları genişletme** ve **önceliği genişletme** de gelen için Deneysel Gelişmiş taşınmıştır.
- Deneysel yeniden düzenleme özellikleri **değişiklik imzası** ve **işlevi ayıklama** varsayılan olarak kullanıma sunulmuştur.
- Deneysel 'Hızlı Proje Yükleme' özelliğini C++ projeleri için. Artık açtığınız C++ projesi daha hızlı yüklenir. Aynı projeyi daha sonra tekrar açtığınızda çok daha hızlı yüklenir!
- Bu özelliklerin bazıları diğer diller için ortaktır ve C++ için belirli bazılarıdır. Bu yeni özellikler hakkında daha fazla bilgi için bkz. [Duyurusu Visual Studio "15"](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/).

**Visual Studio 1027 sürüm 15.7**: Destek için ClangFormat eklendi. Daha fazla bilgi için [Visual Studio 2017'de ClangFormat desteği](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>MSBuild dışındaki projeleriyle klasörü aç

Visual Studio 2017'yi tanıtır **Klasör Aç** kodlayın, oluşturun ve bir klasördeki tüm çözümlerin veya projelerin oluşturmaya gerek olmadan kaynak kodu içeren hata ayıklama olanak tanıyan özellik. Projenize bir MSBuild tabanlı proje olmasa bile Visual Studio ile başlamak çok daha kolay getirir. İle **Klasör Aç** anlama, düzenleme, derleme ve hata ayıklama özelliklerini Visual Studio MSBuild projeleri için zaten sağlayan güçlü kod erişim elde edersiniz. Daha fazla bilgi için [C++ açık klasörü projelerde](../build/open-folder-projects-cpp.md).

- Klasör Aç deneyimi geliştirmeleri. Bu .json dosyaları deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

**Visual Studio 2017 sürüm 15.3**:

- Alternatif derleyicileri ve MinGW ve Cygwin gibi yapı ortamları için geliştirilmiş destek. Daha fazla bilgi için [kullanarak MinGW ve Cygwin Visual C++ ve klasör Aç](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
- Genel ve yapılandırmaya özgü ortam değişkenlerini CMakeSettings.json CppProperties.json de tanımlamak için destek eklendi. Bu ortam değişkenleri, launch.vs.json ve tasks.vs.json Görevler içinde tanımlanan hata ayıklama yapılandırmaları tarafından tüketilebilir. Daha fazla bilgi için [Visual C++ ve klasör Aç ortamınızla özelleştirme](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/customizing-your-environment-with-visual-c-and-open-folder/).
- 64 bit platformlarını kolayca hedefleme yeteneği de dahil olmak üzere, CMake Ninja oluşturucusunu için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Klasör Aç üzerinden CMake desteği

Visual Studio 2017 CMake projeleri için MSBuild proje dosyaları (.vcxproj) dönüştürme olmadan kullanma için destek sunuyor. Daha fazla bilgi için [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md). CMake projeleri ile açma **Klasör Aç** ortamı için düzenleme, derleme ve hata ayıklama C++ otomatik olarak yapılandırır.

- C++ IntelliSense, kök klasörde CppProperties.json dosyası oluşturmaya gerek kalmadan çalışır. Bunun yanı sıra kullanıcıların CMake ve CppProperties.json dosyalarıyla sağlanan yapılandırmalar arasında kolayca geçiş yapması için yeni bir açılır menü ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![Cmake Klasör Aç](media/cmake_cpp.png "CMake Klasör Aç")

**Visual Studio 2017 sürüm 15.3**: Destek için CMake Ninja oluşturucusunu eklendi.

**Visual Studio 2017 sürüm 15.5**: Mevcut CMake önbellekleri almak için eklenen destek.

**Visual Studio 2017 sürüm 15.7**: Önbellek oluşturma ve tek dosyalı derleme için CMake 3.11, CMake projelerini kod analizi, Çözüm Gezgini, seçenekleri hedefleri görünümü için destek eklendi. Daha fazla bilgi için [Visual Studio'da CMake desteği](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md).

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik.  Yükleyici kullanıcı arabiriminde bileşenler için listelenen yükleme boyutlarının doğru olmadığını ve toplam boyutu düşük gösterdiğini lütfen aklınızda bulundurun.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Önerilen (Seçilen) bileşenlerini yükleme **VC ++ 2017 v141 araç takımı (x86, x64)** ve **Windows 10 SDK (10.0.nnnnn)** Bunun çalışmasını sağlar. Gerekli araçlar yüklenmezse, projeler başarıyla oluşturulamaz ve sihirbaz yanıt vermemeye başlar.

**Visual Studio 2017 sürüm 15.5**:

Visual C++ derleme Araçları (daha önce tek başına bir ürün kullanılabilir) artık olan Visual Studio Yükleyicisi'nde bir iş yükü olarak dahil. Bu iş yükü, yalnızca C++ projeleri Visual Studio IDE yüklemeden derlemek için gereken araçları yükler. V140 hem v141 araç takımları dahil edilir. Visual Studio 2017 sürüm 15.5 kullanılabileceği en son yenilikleri v141 araç kümesini içerir. Daha fazla bilgi için [Visual Studio derleme araçları artık içeren VS2017 ve VS2015 MSVC araç takımları](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/).

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

**Visual Studio 2017 sürüm 15.2**:

Platformlar arası kod paylaşımı ve türü görselleştirmede iyileştirmeler yapılmıştır. Daha fazla bilgi için [Linux C++ geliştirmeleri için platformlar arası kod paylaşımı ve görselleştirme türü](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/).

**Visual Studio 2017 sürüm 15.5**:

- Linux iş yükü için destek eklemiştir **rsync** alternatif olarak **sftp** uzak Linux makineleri dosyalar için.
- Derleme mikrodenetleyici ARM hedefleme için destek eklenir. Bu yüklemeyi etkinleştirmek için seçin **C++ ile Linux geliştirme** iş yükü ve seçeneğini **katıştırılmış ve IOT geliştirmesi**. Bu seçenek, ARM GCC çapraz derleme araçlarını ve marka yüklemenize ekler. Daha fazla bilgi için [ARM GCC çapraz derleme Visual Studio'da](https://blogs.msdn.microsoft.com/vcblog/2017/10/23/arm-gcc-cross-compilation-in-visual-studio/).
- CMake için eklenen destek. Artık, mevcut CMake kod üzerinde temel bir Visual Studio projesine dönüştürmek zorunda kalmadan çalışabilirsiniz. Daha fazla bilgi için [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).
- Uzak görevleri çalıştırmak için eklenen destek. Bu özellik, Visual Studio'nun Bağlantı Yöneticisi'nde tanımlanan bir uzak sistem üzerindeki herhangi bir komutu çalıştırmak olanak tanır. Uzak görevler, dosyaları uzak sisteme kopyalama olanağı da sağlar.
Daha fazla bilgi için [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

**Visual Studio 2017 sürüm 15.7**:

- Linux iş yükü senaryoları için çeşitli geliştirmeler. Daha fazla bilgi için [proje sistemi, Linux konsol penceresi, rsync ve işleme İliştir Linux C++ iş yükünde geliştirmeler](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- Uzak Linux bağlantıları üstbilgileri için IntelliSense. Daha fazla bilgi için [uzak Linux üst bilgiler için IntelliSense](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/intellisense-for-remote-linux-headers/) ve [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ (Android ve iOS) ile Mobil Geliştirme

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017’de v140 hedefli bir UWP projesi açtığınızda, sisteminizde Visual Studio 2015 yüklü değilse proje özelliği sayfalarından v141 platformu araç kümesini seçmeniz gerekiyor.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>C++ için yeni seçenekler Evrensel Windows Platformu (UWP) üzerinde
Şimdi, yazma ve C++ uygulamaları Evrensel Windows platformu ve Windows Store için paketleme yeni seçeneğiniz de vardır: Masaüstü köprüsü altyapı, mevcut masaüstü uygulamasını veya Windows Store veya dışarıdan yükleme aracılığıyla var olan kanallarınız üzerinden dağıtımı için COM nesnesi paketlemek için kullanabilirsiniz. Windows 10'daki yeni özellikler Masaüstü uygulamanızı çeşitli yollarla UWP işlevselliği eklemek etkinleştirin. Daha fazla bilgi için [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

**Visual Studio 2017 sürüm 15.5**: A **Windows uygulaması paketleme projesi** proje şablonu, büyük ölçüde basitleştirir, Masaüstü Köprüsü'nü kullanarak ile Masaüstü uygulamaları paketleme işi eklenir. Altında kullanılabilir **dosya | Yeni | Proje | Yüklü | Visual C++ | Evrensel Windows platformu**. Daha fazla bilgi için [Visual Studio (Masaüstü köprüsü) kullanarak bir uygulama paketini](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

Yeni kod yazarken artık C + kullanabilirsiniz +/ WinRT, standart bir C++ dil projeksiyonu yalnızca üstbilgi dosyalarında uygulanan Windows çalışma zamanı. Her iki Yazar sağlar ve Windows çalışma zamanı API'leri kullanarak standartlara uygun herhangi bir C++ derleyicisi. C + +/ WinRT, C++ geliştiricileri için modern Windows API ile birinci sınıf erişim sağlamak için tasarlanmıştır. Daha fazla bilgi için [C + +/ WinRT github'da kullanılabilir](https://moderncpp.com/).

Sürümünden başlayarak Windows SDK'sı Insider Önizleme, C + 17025 derleme +/ WinRT Windows SDK içinde dahil edilmiştir. Daha fazla bilgi için [C + +/ WinRT, artık Windows SDK'da](https://blogs.msdn.microsoft.com/vcblog/2017/11/01/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Visual Studio 2017 artık destekliyor ile birlikte gönderilen Clang/C2 araç **/bigobj** geçiş, hangi büyük projeler oluşturma açısından önemlidir. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ Kod Analizi

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Kutusundan denetleyicileri etkinleştirmeniz yeterlidir **Kod Analizi uzantıları** kod analizini çalıştırdığınızda projenin özellik sayfalarındaki ve uzantılar sayfasında dahil edilecektir. Daha fazla bilgi için [C++ temel yönergeleri denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikler sayfası")

**Visual Studio 2017 sürüm 15.3**: Kaynak yönetimi ile ilgili kuralları için eklenen destek.

**Visual Studio 2017 sürüm 15.5**: Yeni C++ temel yönergeleri denetimi kapsayan akıllı işaretçi doğruluğu, genel başlatıcıların doğru kullanımı ve bayrak kullanır gibi yapıları, `goto` ve hatalı atamaları.

15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

**Visual Studio 2017 sürüm 15.6**:

- Destek için tek dosyalı analizi ve analiz çalıştırma performans geliştirmeleri eklendi. Daha fazla bilgi için [C++ statik analizi iyileştirmeleri Visual Studio 2017 15.6 Preview 2](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

**Visual Studio 2017 sürüm 15.7**:

- İçin eklenen Destek [/ analyze: ruleset](../build/reference/analyze-code-analysis.md) çalıştırmak için hangi kod analizi kuralları belirtmenize olanak sağlar.
- Desteği için ek C++ temel yönergeleri kuralları eklendi.  Daha fazla bilgi için [C++ temel yönergeleri denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Birim testi

**Visual Studio 2017 sürüm 15.5**:

Google Test bağdaştırıcısı ve Boost.Test bağdaştırıcısı bileşenleri olarak kullanılabilir olduğuna **C++ ile masaüstü geliştirme** çalıştırdığınız ve iş yükü ile tümleştirilmiştir **Test Gezgini**. CTest desteği (Klasör Aç'ı kullanarak) Cmake projeleri için eklenir, ancak ile tam tümleştirme **Test Gezgini** henüz kullanıma sunulmamıştır. Daha fazla bilgi için [C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

**Visual Studio 2017 sürüm 15.6**:

- Destek Boost.Test dinamik kitaplık desteği eklendi.
- Boost.Test öğe şablonu IDE içinde kullanıma sunuldu.

Daha fazla bilgi için [Boost.Test birim testi: Dinamik kitaplık desteği ve yeni öğe şablonu](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/boost-test-unit-testing-dynamic-library-support-and-new-item-template/).

**Visual Studio 2017 sürüm 15.7**:

[CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) desteklenen C++ birim testi projeleri için eklendi. Daha fazla bilgi için [C++ birim testi için CodeLens Duyurusu](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/announcing-codelens-for-c-unit-testing/).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio grafik Tanılama, kaydetme ve Direct3D uygulamalar oluşturma ve performans sorunları çözümleme için araç kümesidir. Grafik tanılama özelliği, Windows PC, bir Windows cihaz öykünücüsü veya bir uzak bilgisayar veya cihaz üzerinde yerel olarak çalışan uygulamaları ile kullanılabilir.

- **Giriş ve çıkış köşe ve geometri gölgelendirici için:** Giriş ve çıkış köşe gölgelendiricileri geometri gölgelendirici ve görüntüleme olanağı en çok istenen özelliklerden biri olmuştur ve araçları artık desteklenmektedir. Yalnızca kendi giriş inceleyerek başlatmak için ardışık düzen aşamaları görünümünde VS veya GS aşama seçin ve aşağıdaki tabloda çıkış.

  ![Gölgelendirici için giriş/çıkış](media/io-shaders.png)

- **Arama ve nesne tablosu Filtresi:** Aradığınız kaynakları bulmak için hızlı ve kolay bir yol sağlar.

  ![Ara](media/search.png)

- **Kaynak geçmişi:** Bu yeni görünüm, yakalanan çerçeve işlenmesi sırasında kullanıldı gibi bir kaynak tüm değişiklik geçmişini görmenizi, kolaylaştırılmış bir yol sağlar. Herhangi bir kaynak için geçmiş çağırmak için herhangi bir kaynak köprüye yanındaki saat simgesine tıklamanız yeterlidir.

  ![Kaynak geçmişi](media/resource-history.png)

  Bu yeni görüntüler **kaynak geçmişi** araç penceresi, değişiklik geçmişini kaynağı ile doldurulur.

  ![Kaynak geçmişi değiştir](media/resource-history-change.png)

  Çerçevenizi tam çağrı yığınını yakalama etkin yakalandıysa unutmayın (**Visual Studio > Araçlar > Seçenekler** altında **grafik tanılama**), sonra her değişikliği olayının bağlamı hızlı bir şekilde olabilir atanan ve Visual Studio projenize içinde inceledi.

- **API istatistikleri:** Çerçeveniz içinde üst düzey API kullanımının özetini görüntüleyin. Bu, tüm yapıyorsanız bilmiyor olabilirler çağrıları veya çok fazla kuran çağrıları keşfetme kullanışlı olabilir. Bu pencere aracılığıyla kullanılabilir **Görüntüle > API istatistikleri** Visual Studio grafik Çözümleyicisi.

  ![API istatistikleri](media/api-stats.png)

- **Bellek istatistikleri:** Sürücü, kaynaklar için ayırma ne kadar bellek çerçevede oluşturduğunuz görüntüleyin. Bu pencere aracılığıyla kullanılabilir **Görüntüle > bellek istatistikleri** içinde **Visual Studio grafik Çözümleyicisi**. Veri kopyalanabilir Elektronik tablolardaki görüntülemek için bir CSV dosyasına sağ tıklayıp seçerek **Tümünü Kopyala**.

  ![Bellek istatistikleri](media/memory-stats.png)

- **Çerçeve doğrulama:** Yeni hataları ve Uyarıları listesi, Direct3D hata ayıklama katmanı tarafından algılanan olası sorunları göre olay listenize gitmek için kolay bir yol sağlar. Tıklayın **Görüntüle > Çerçeve doğrulama** , Visual Studio grafik Çözümleyicisi aygıtını penceresini açın. Ardından **doğrulama çalışması** analiz başlatmak için. Bu çerçeve karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **Çerçeve analizi D3D12 için:** Çerçeve Analizi ile yönlendirilen "what-if" denemeleri çizim çağrısı performansını analiz etmek için kullanın. Çerçeve analizi sekmesine gidin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için izleme [GoingNative 25: Visual Studio grafik çerçevesi analizi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) video.

  ![Çerçeve analizi](media/frame-analysis.png)

- **GPU kullanımı geliştirmeleri:** GPU görünümü ya da daha ayrıntılı analiz için Windows Performans Çözümleyicisi (WPA) aracı ile Visual Studio GPU kullanımı profiler aracılığıyla gerçekleştirilen izlemeleri açabilir. Varsa, Windows Performans Araç Seti yüklü WPA, diğeri GPU görünümünde, sağ alt köşesindeki oturum genel bakış için iki köprüler olacaktır.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı desteği GPU Görünümü'nde açtığınız izlemeleri, yakınlaştırma ve kaydırma VS ile GPU görünümü zaman çizelgesinde eşitlendi. Vs'de bir onay kutusu, eşitleme etkin'in etkin olup olmadığını denetlemek için kullanılır.

  ![GPU görüntüle](media/gpu-view.png)
