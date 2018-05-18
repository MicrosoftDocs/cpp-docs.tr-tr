---
title: Visual Studio'da Visual C++ yenilikler | Microsoft Docs
ms.date: 11/15/2017
ms.technology:
- cpp-ide
ms.topic: conceptual
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f280ed28a65db4aa71ee6dea36521b1b8606b190
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Visual c++'ta için yenilikler nelerdir? [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] çok sayıda güncelleştirme getirir ve Visual C++ ortamına giderir. 250'den fazla düzeltilen artık ve derleyici ve araçlarını sorunlar bildirildiğinde, müşteriler tarafından birçok gönderilen [bir sorun bildirmek](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) ve [bir öneride bulunmak](https://visualstudio.uservoice.com/) altında seçenekleri **geri bildirim gönder** . Hataları bildirdiğiniz için teşekkür ederiz! Tüm Visual Studio yenilikler hakkında daha fazla bilgi için lütfen ziyaret [yenilikler [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] ](https://go.microsoft.com/fwlink/p/?linkid=834481).

<!--The compiler and tools version number in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] is 14.10.24629. -->

## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uygunluk geliştirmeleri

Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md).
**Visual Studio 2017 sürüm 15,5**:  

   Derleyici yaklaşık %75 yapılandırılmış bağlamaları dahil olmak üzere C ++ 17'de yeni özellikleri destekleyen `constexpr` Lambda'lar, `if constexpr`, satır içi değişkenleri Katlama ifadeleri ve ekleme `noexcept` türü sisteme. Bunlar altında kullanılabilir **/Std: c ++ 17** seçeneği. Daha fazla bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md)

**Visual Studio 2017 sürüm 15.7**:  

Visual Studio sürümü 15.7 MSVC derleyici araç setini şimdi C++ standart ile uyumludur. Daha fazla bilgi için bkz: [Announcing: MSVC uyumlu C++ standart](https://blogs.msdn.microsoft.com/vcblog/2018/05/07/announcing-msvc-conforms-to-the-c-standard/) ve [Visual C++ dili uygunluk](visual-cpp-language-conformance.md).

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [/ izin veren-](build/reference/permissive-standards-conformance.md): tüm katı standartları uyumluluk derleyici seçenekleri etkinleştirip çoğu Microsoft özgü derleyici uzantıları devre dışı bırakmak (ama `__declspec(dllimport)`, örneğin). Bu seçenek varsayılan olarak Visual Studio 2017 sürüm 15,5 açıktır.  **/ İzin veren-** uyumluluk modu iki aşamalı ad araması için destek içerir. Daha fazla bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md).

- [/Diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): satır numarası, satır numarası ve sütun veya satır numarasını ve sütun ve burada tanılama hata veya uyarı bulundu kod satırı altında bir şapka görüntüsünü etkinleştirin.

- [/Debug:fastlink](build/reference/debug-generate-debug-info.md): % 30 etkinleştirmek daha hızlı artımlı bağlantı zaman (vs. Visual Studio 2015) değil kopyalayarak tüm PDB dosyasına hata ayıklama bilgileri. PDB dosyası yerine yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplık dosyaları için hata ayıklama bilgileri işaret eder. Bkz: [daha hızlı C++ derleme /Debug:fastlink ile VS "15" döngüsünde](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) ve [derlemeler Visual Studio'da C++ önerileri hızı](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

- [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] kullanarak verir [/SDL](build/reference/sdl-enable-additional-security-checks.md) ile [/ await](build/reference/await-enable-coroutine-support.md). Biz kaldırılan [eş yordamlarla/RTC](build/reference/rtc-run-time-error-checks.md) sınırlamasını.

   **Visual Studio 2017 sürüm 15.3**:  
- [/ Std: c ++ 14 ve/Std: c ++ Son](build/reference/std-specify-language-standard-version.md): Bu derleyici seçenekleri ISO C++ programlama dili projesinde belirli sürümlerine katılımı olanak sağlar. Standart özellikler tarafından korumalı yeni taslak çoğu **/Std: c ++ Son** seçeneği.

- [/ Std: c ++ 17](build/reference/std-specify-language-standard-version.md) derleyici tarafından uygulanan C ++ 17 özellikler kümesi sağlar. Bu seçenek, C ++ 17 sonra derleyicisi ve standart kitaplığı desteği değiştirilen özellikler için veya yeni C++ standart çalışma taslak ve hatasını güncelleştirmeleri sürümlerinde devre dışı bırakır. Bu özellikleri etkinleştirmek için **/Std: c ++ Son**.


### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Bu sürümdeki yenilikleri en iyi duruma getirme, kod oluşturma, araç takımı sürüm oluşturma ve tanılama getirir. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: sabit tam sayıları bölme işlemleri için otomatik vektörleştirme desteği, memset desenlerinin daha iyi tanınması.
- Geliştirilmiş kod güvenliği: Geliştirilmiş çıkması taşması derleyici tanılama ve [/guard:cf](build/reference/guard-enable-control-flow-guard.md) atlama tablolar oluşturmak deyimleri koruyucuları geçiş artık.
- Sürüm oluşturma: Yerleşik önişlemci makrosu değerini  **\_MSC\_VER** şimdi tekdüze her Visual C++ araç takımını güncelleştirmeyi güncelleştiriliyor. Daha fazla bilgi için bkz: [Visual C++ Derleyici sürümü](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Yeni araç takımı Düzen: derleyici ve ilgili derleme araçları geliştirme makinenizde yeni bir konum ve dizin yapısına sahip. Yeni düzen derleyici birden fazla sürümünü yan yana yüklemesini sağlar. Daha fazla bilgi için bkz: [derleyici araçları Visual Studio "15" düzende](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Gelişmiş Tanılama: artık çıktı penceresi bir hata oluştuğu sütun gösterir. Daha fazla bilgi için bkz: [C++ Derleyici tanılama geliştirmeleri VS "15" Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Ortak yordamları, Deneysel anahtar sözcüğü kullanırken **verim** (altında kullanılabilir **/ await** seçeneği) kaldırılmıştır. Kodunuzu kullanacak şekilde güncelleştirilmesi `co_yield` yerine. Daha fazla bilgi için [Visual C++ Ekip bloguna](https://blogs.msdn.microsoft.com/vcblog/) bakın.

**Visual Studio 2017 sürüm 15.3**:

Derleyici tanılamada ek geliştirmeler. Daha fazla bilgi için bkz: [Visual Studio 2017 15.3.0 tanılama geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/).

**Visual Studio 2017 sürüm 15,5**:

Visual C++ çalışma zamanı performans nedeniyle daha iyi oluşturulan kod kalitesini artırmak devam eder. Bu, yalnızca kodunuzu derleyin ve uygulamanızı daha hızlı çalışır anlamına gelir. Derleyici iyileştirmesi bazıları yepyeni, koşullu skaler depoları, çağrıları Birleşen vectorization gibi `sin(x)` ve `cos(x)` içine yeni bir `sincos(x)`ve SSA iyileştirici yedekli yönergeleri ortadan kaldırılması. Diğer derleyici iyileştirmelerini vektör yapıcı buluşsal yöntemler koşullu ifadeler, daha iyi döngü en iyi duruma getirme ve float min/max codegen gibi varolan işlevine geliştirmeleri eklenmiştir. Yeni bir ve daha hızlı bağlayıcı sahip **/OPT:ICF** % 9 sonucunda uygulama artımlı bağlantılandırma diğer perf düzeltmeleri olan ve zaman speedups bağlantısı. Daha fazla bilgi için bkz: [OPT (iyileştirmeler)](https://docs.microsoft.com/en-us/cpp/build/reference/opt-optimizations) ve [/INCREMENTAL (artımlı bağlantı)](https://docs.microsoft.com/en-us/cpp/build/reference/incremental-link-incrementally).

Visual C++ Intel'in AVX-512 yeni işlevler AVX-512 128 ve 256 bit geniş yazmaçlar Getir vektör uzunluğu yönergeleri de dahil olmak üzere, destekler.

[/Zc:noexceptTypes-](build/reference/zc-noexcepttypes.md) seçeneği, C ++ 14 sürümüne geri dönmek için kullanılabilir `noexcept` genel C ++ 17 modu kullanırken. Bu, C ++ 17'ye tüm yeniden yazmaya gerek kalmadan uygun olması için kaynak kodu güncelleştirmenizi sağlar, `throw()` aynı anda kodu. Daha fazla bilgi için bkz: [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements-2017.md#noexcept_removal).

**Visual Studio 2017 sürüm 15.7**:

- Yeni derleyici anahtar [/Qspectre ](build/reference/qspectre.md) kurgusal yürütme yan kanal saldırılarına karşı azaltmaya yardımcı olmak için. Bkz: [Spectre Azaltıcı MSVC içinde](https://blogs.msdn.microsoft.com/vcblog/2018/01/15/spectre-mitigations-in-msvc/) daha fazla bilgi için.
- Spectre migitation için yeni tanılama uyarı. Bkz: [Spectre Visual Studio 2017 sürüm 15.7 Preview 4'te tanılama](https://blogs.msdn.microsoft.com/vcblog/2018/04/20/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/) daha fazla bilgi için.
- /Zc için yeni bir değer **/Zc:__cplusplus**, etkinleştirir düzeltin C++ Standart Destek Raporlama. Örneğin, ne zaman anahtar ayarlandığında ve derleyici içinde/Std: c ++ 17 modu değeri genişletir için **201703 L**. Bkz: [MSVC şimdi __cplusplus doğru raporları](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/msvc-now-correctly-reports-__cplusplus/) daha fazla bilgi için.

## <a name="c-standard-library-improvements"></a>C++ Standart Kitaplığı geliştirmeleri

- Küçük `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` tanılama geliştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- Performans geliştirmesi: yapılan `basic_string::find(char)` yalnızca çağrı overloads `traits::find` sonra. Daha önce bu, 1 uzunluğunda bir dizenin genel dize araması olarak uygulanıyordu.
- Performans geliştirmesi: `basic_string::operator==` şimdi dizeleri içeriği karşılaştırılmadan önce dizenin boyutunu denetler.
- Performans geliştirmesi: içinde Kuplaj denetim kaldırılan `basic_string`, analiz etmek için derleyici iyileştirici zor olduğu. Çağrılırken, kısa tüm dizeleri unutmayın `reserve` yapmamak için sıfır olmayan bir maliyet hala vardır.
- Eklediğimiz \<herhangi\>, \<string_view\>, `apply()`, `make_from_tuple()`.
- `std::vector` doğruluk ve performans için overhauled: ekleme ve emplacement sırasında yumuşatma artık doğru şekilde ele alınır olarak standardına göre gerekli, güçlü özel durum garantisi şimdi standart tarafından istendiğinde sağlanan `move_if_noexcept()` ve diğer mantığı ve ekleme/emplacement daha az öğe işlemleri gerçekleştirin.
- C++ Standart Kitaplığı, şimdi null süslü işaretçileri başvurusunun kaldırılmasının önler.
- Eklenen \<isteğe bağlı\>, \<değişken\>, `shared_ptr::weak_type`, ve \<cstdalign\>.
- C ++ 14 etkin `constexpr` içinde `min(initializer_list)`, `max(initializer_list)`, ve `minmax(initializer_list)`, ve `min_element()`, `max_element()`, ve `minmax_element()`.
- Geliştirilmiş `weak_ptr::lock()` performans.
- Sabit `std::promise` devamlı engellemek kod daha önce neden olabilecek taşıma atama işleci.
- Derleyici hatalarıyla sabit `atomic<T*>` örtük dönüştürmeye `T*`.
- `pointer_traits<Ptr>` artık doğru şekilde algılar `Ptr::rebind<U>`.
- Eksik sabit `const` niteleyicisinde `move_iterator` çıkarma işleci.
- Sessiz hatalı codegen isteyen durum bilgisi olan kullanıcı tanımlı allocators için sabit `propagate_on_container_copy_assignment` ve `propagate_on_container_move_assignment`.
- `atomic<T>` Şimdi göstereceği aşırı `operator&()`.
- Derleyici verimliliğini artırmak için gereksiz derleyici iç bilgileri için bildirimleri de dahil olmak üzere standart C++ Kitaplığı üstbilgilerini şimdi kaçının.
- Biraz, derleyici tanılama için geliştirilmiş yanlış `bind()` çağrıları.
- Performansını geliştirilmiş `std::string` ve `std::wstring` oluşturucular tarafından birden fazla üç kez taşıyın.

Standart Kitaplığı tam bir listesi için bkz: geliştirmelerin [standart kitaplığı düzeltmeler de VS 2017 RTM](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/).

### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

#### <a name="c17-features"></a>C ++ 17 özellikleri

Birkaç ek C ++ 17 özellikleri uygulanmıştır. Daha fazla bilgi için bkz: [Visual C++ dili uygunluk](cpp-conformance-improvements-2017.md#improvements_153).

#### <a name="other-new-features"></a>Diğer yeni özellikler

- Uygulanan P0602R0 "değişken ve isteğe bağlı copy/move triviality yayılması".
- Standart Kitaplığı şimdi resmi olarak aracılığıyla devre dışı bırakılıyor dinamik RTTI göstereceği [/GR-](build/reference/gr-enable-run-time-type-information.md) seçeneği. Her ikisi de `dynamic_pointer_cast()` ve `rethrow_if_nested()` kendiliğinden gerektiren `dynamic_cast`, standart kitaplığı artık bunları olarak işaretler `=delete` altında **/GR-**.
- Hatta zaman dinamik RTTI aracılığıyla devre dışı bırakıldı. **/GR-**, "statik RTTI" (biçiminde `typeid(SomeType)`) hala kullanılabilir olduğundan ve birkaç standart Kitaplığı bileşenleri çalıştırır. Standart Kitaplığı, şimdi de bu devre dışı bırakma destekler aracılığıyla **/D\_HAS\_statik\_RTTI = 0**. Bu devre dışı bırakır Not `std::any`, `target()` ve `target_type()` üye işlevlerini `std::function`ve `get_deleter()` arkadaş üye işlevini `std::shared_ptr` ve `std::weak_ptr`.

#### <a name="correctness-fixes-in-visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3 doğruluk giderir

- Standart Kitaplığı kapsayıcıları şimdi clamp kendi `max_size()` için `numeric_limits<difference_type>::max()` yerine `max()` , `size_type`. Bu sonucu sağlar `distance()` bu kapsayıcısından yineleyiciler içinde dönüş türü gösterilebilir açıktır `distance()`.
- Eksik uzmanlık sabit `auto_ptr<void>`.
- `for_each_n()`, `generate_n()`, Ve `search_n()` algoritmaları daha önce başarısız length bağımsız bir tam sayı türde değildi derlemeniz; bunlar artık integral olmayan uzunlukları yineleyiciler için dönüştürmeyi denemeden `difference_type`.
- `normal_distribution<float>` artık float uyarıları standart çift daraltma hakkında kitaplığı içinde yayar.
- Bazı sabit `basic_string` ile karşılaştırma işlemleri `npos` yerine `max_size()` için en büyük boyutu taşma denetlerken.
- `condition_variable::wait_for(lock, relative_time, predicate)` alacaklardır Uyandırma durumunda tüm göreli zaman beklemeniz. Şimdi, yalnızca bir tek göreli zaman aralığı için bekler.
- `future::get()` artık geçersiz kılar `future`, standart gerektirir.
- `iterator_traits<void *>` Forma çalıştığı için sabit bir hata olması için kullanılan `void&`; bu artık düzgün bir şekilde kullanılmasına izin vermek için boş bir yapı duruma `iterator_traits` "yineleyici olduğunu" SFINAE koşulları.
- Bazı uyarılar bildirdi tarafından Clang **- Wsystem-headers** düzeltilmiştir.
- Ayrıca "özel durum belirtimi bildiriminde önceki bildirimi Clang tarafından bildirilen eşleşmiyor" sabit **- Wmicrosoft özel durum belirtimi**.
- Clang C1XX tarafından bildirilen ve ayrıca sabit mem başlatıcı listesi sıralama uyarılar.
- Kapsayıcıları kendilerini değiştirildi, sırasız kapsayıcılar kendi hashers veya koşulları takas değil. Şimdi bunların yapın.
- Çok sayıda kapsayıcı değiştirme işlemleri şimdi işaretlenmiş `noexcept` (bizim standart kitaplığına hiçbir zaman olmayan tespit edilirken bir özel durum amaçlayan gibi`propagate_on_container_swap` eşittir ayırıcı olmayan tanımsız davranış koşulu).
- Birçok `vector<bool>` operations şimdi işaretlenmiş `noexcept`.
- Standart Kitaplığı şimdi eşleşen ayırıcısı zorunlu kılacak `value_type` (modunda C ++ 17) vazgeçme kaçış tarama ile.
- Bazı koşullar kendi range Ekle burada içine sabit `basic_string` dizeleri içeriği karıştırmak. (Not: self-range-insert into'nun vektörlerinin standardına göre hala Yasak.)
- `basic_string::shrink_to_fit()` ayırıcı tarafından 's artık etkilenen `propagate_on_container_swap`.
- `std::decay` Şimdi abominable işlev türleri (MS-tam ve/veya ref tam yani işlevi türleri) işler.
- Değiştirilen uygun büyük küçük harfe duyarlılığın ve taşınabilirlik geliştirme eğik kullanmak için yönergeleri içerir.
- Uyarı C4061 sabit "Numaralandırıcı '*Numaralandırıcı*'ın enum anahtar'*numaralandırma*' açıkça bir servis talebi etiketle işlenmemiş". Bu uyarı-varsayılan olarak kapalı ve bir özel durum uyarılarını standart kitaplığın Genel ilke olarak düzeltildi. (Standart Kitaplığı **/W4** temiz ancak olmasını denemez **/duvar** temiz. Birçok-varsayılan olarak kapalı uyarılar son derece gürültülü ve düzenli aralıklarla kullanılmaya yönelik değildir.)
- Geliştirilmiş `std::list` debug denetler. Liste yineleyiciler şimdi onay `operator->()`, ve `list::unique()` şimdi yineleyiciler geçersiz kılınan olarak işaretler.
- Ayırıcı olarak meta kullanır sabit `tuple`.

#### <a name="performancethroughput-fixes"></a>Performans/verimlilik düzeltmeleri

- İle etkileşim geçici çalışılan `noexcept` satır içi kullanım engelleyen `std::atomic` yapılandırılmış özel durum işleme (SEH) kullanan işlevler uygulamasına.
- Değiştirilen standart kitaplığı iç `_Deallocate()` fazla yerde içermesinden olmasını sağlayan küçük koda en iyi duruma getirme işlevi.
- Değiştirilen `std::try_lock()` paketi genişletme özyineleme yerine kullanılacak.
- Geliştirilmiş `std::lock()` kullanabilmek için kilitlenme kaçınma algoritmasını `lock()` operations dönen üzerinde yerine `try_lock()` üzerindeki tüm kilitler.
- Adlandırılmış dönüş değeri iyileştirme etkin `system_category::message()`.
- `conjunction` ve `disjunction` şimdi örneği N + 2N + 2 türleri yerine 1 türleri.
- `std::function` artık her tür silinmesi aranabilir, iyileştirme performans ve geçirmek için birçok farklı Lambda'lar programları azalan .obj boyutunda ayırıcısı destek makineler başlatır `std::function`.
- `allocator_traits<std::allocator>` el ile içermesinden içeren `std::allocator` işlemleri ile etkileşime giren kodu kodu boyutunun azaltılması, `std::allocator` aracılığıyla `allocator_traits` yalnızca (diğer bir deyişle, içinde çoğu kodu).
- C ++ 11 en az ayırıcısı arabirimi şimdi standart kitaplığı tarafından işlenen çağırma `allocator_traits` bir iç sınıf ayırıcı sarmalama yerine doğrudan `_Wrap_alloc`. Bu ayırıcısı desteği oluşturulan kod boyutunu azaltır, bazı durumlarda standart kitaplığı kapsayıcıları hakkında neden iyileştirici'nin yeteneği artırır ve hata ayıklama daha iyi bir deneyim sağlar (ayırıcısı türünüz şimdi gördüğünüz gibi yerine `_Wrap_alloc<your_allocator_type>` içinde hata ayıklayıcı).
- Özelleştirilmiş meta kaldırılan `allocator::reference`, hangi allocators gerçekte izin verilmiyor özelleştirmek için. (Allocators süslü işaretçileri ancak değil süslü başvuruları kullanamazsınız kapsayıcıları yapabilirsiniz.)
- Ön uç derleyici hata ayıklama yapıları performansını iyileştirme hata ayıklama yineleyiciler aralık tabanlı için-döngüler içinde açılacak öğrettin.
- `basic_string` İç küçültme yolu `shrink_to_fit()` ve `reserve()` artık mutating tüm üyeleri için kod boyutunun azaltılması, işlemlerini yeniden ayırma yolunda değil.
- `basic_string` İç büyümesine yol olduğu artık yolunda `shrink_to_fit()`.
- `basic_string` Diziyi operations şimdi ayırma hızlı yolu ve arayanlar içermesinden olması ortak Hayır yeniden ayırma çalışması için büyük olasılıkla yapmadan ayırma yavaş işlevleri oluşturmak.
- `basic_string` Yerinde yeniden boyutlandırma yerine yapı arabellekleri istenen durumda bırakılan artık operations diziyi. Örneğin, başında bir dize şimdi ekleniyor içerik ekleme (aşağı veya yeni ayrılmış arabelleğe), sonra tam olarak bir kez yerine iki kez reallocating durumda (yeni ayrılmış arabelleğe ve sonra aşağı) taşınır.
- C Standart Kitaplığı arayan işlemleri \<dize\> şimdi önbelleğe `errno` TLS yinelenen etkileşim kaldırmak için adres.
- Basitleştirilmiş `is_pointer` uygulaması.
- İşlev tabanlı ifade SFINAE değiştirme tamamlandı `struct` ve `void_t`-tabanlı.
- Standart Kitaplığı algoritmaları şimdi yineleyiciler postincrementing kaçının.
- 32-bit allocators 64 bitlik sistemlerde kullanırken sabit kesilmesi uyarılar.
- `std::vector` taşıma atama şimdi arabellek mümkün olduğunca yeniden kullanarak POCMA olmayan eşittir ayırıcısı durumda daha verimli olur.

#### <a name="readability-and-other-improvements"></a>Okunabilirlik ve diğer geliştirmeler

- Standart kitaplığını C ++ 14 şimdi kullanan `constexpr` koşulsuz olarak, koşullu tanımlı makrolar yerine.
- Standart Kitaplığı şimdi diğer şablonları dahili olarak kullanır.
- Standart Kitaplığı artık kullanır `nullptr` dahili olarak, yerine, `nullptr_t{}`. (Null iç kullanım eradicated. İç kullanım null olarak 0 kademeli olarak temizleniyor.)
- Standart Kitaplığı artık kullanır `std::move()` stylistically kötüye yerine dahili olarak `std::forward()`.
- Değiştirilen `static_assert(false, "message")` için `#error message`. Bunun nedeni derleyici tanılama artırır `#error` hemen derleme durdurur.
- Standart Kitaplığı artık işlev olarak işaretler `__declspec(dllimport)`. Modern bağlayıcı teknolojisi artık bu gerektirir.
- Türleri ve işlevi bağımsız değişken türleri döndürülecek karşılaştırıldığında dağınıklığı azaltır ayıklanan SFINAE varsayılan şablon değişkenlerini için.
- Hata ayıklama denetler \<rastgele\> şimdi standart kitaplığının her zamanki makineler, iç yerine işlevini `_Rng_abort()` çağırıldığı `fputs()` için **stderr**. Bu işlevin uygulama ikili uyumluluk için korunur, ancak standart kitaplığı sonraki ikili uyumsuz sürümünde kaldırılmıştır.

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Birkaç standart kitaplığı özellikleri eklenmiş, kullanım dışı veya C ++ 17 standardına uygun olarak kaldırıldı. Daha fazla bilgi için bkz: [Visual Studio'da C++ uygunluk geliştirmeleri](cpp-conformance-improvements-2017.md#improvements_155).

#### <a name="new-experimental-features"></a>Yeni Deneysel özellikleri

- Aşağıdaki paralel algoritmalar Deneysel desteği:
  - `all_of`
  - `any_of`
  - `for_each`
  - `for_each_n`
  - `none_of`
  - `reduce`
  - `replace`
  - `replace_if`
  - `sort`
- Aşağıdaki paralel algoritmalar imzaları eklendi ancak şu anda paralel birkaç ölçeklendirin değil; Profil oluşturma fayda yalnızca taşımak veya öğeleri permute algoritmaları parallelizing gösterilmiştir:
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

- `basic_string<char16_t>` Şimdi aynı prosese `memcmp`, `memcpy`ve benzer en iyi duruma getirme, `basic_string<wchar_t>` ilgilenir.
- Bizim "işlevleri kopyalama kaçının tarafından" sunulan engeller önlenmiş işlev işaretçileri içermesinden Visual Studio 2015 güncelleştirme 3'te çalışan bir iyileştirici sınırlaması geçici performansını geri çalışmıştır `lower_bound(iter, iter, function pointer)`.
- Hata ayıklama yineleyici yükü sipariş doğrulama girdi için kullanıcının `includes`, `set_difference`, `set_symmetric_difference`, ve `set_union` tarafından açma yineleyiciler sipariş denetlemeden önce azaltılmıştır.
- `std::inplace_merge` Şimdi, zaten konumda öğelerini üzerinden atlar.
- Oluşturma `std::random_device` artık oluşturur ve ardından bozar bir `std::string`.
- `std::equal` ve `std::partition` yineleyici karşılaştırma kaydedileceği bir atlama iş parçacığı oluşturma en iyi duruma getirme geçişi vardı.
- Zaman `std::reverse` işaretçileri trivially copyable geçirilen `T`, elle yazılmış bir vectorized uygulama artık dağıtacağı.
- `std::fill`, `std::equal`, ve `std::lexicographical_compare` için gönderme nasıl öğrettin `memset` ve `memcmp` için `std::byte` ve `gsl::byte` (ve diğer char benzeri numaralandırmaları ve enum sınıfları). Unutmayın `std::copy` kullanarak gönderir `is_trivially_copyable` ve bu nedenle herhangi bir değişiklik ihtiyacım kalmadı.
- Standart Kitaplığı artık türleri olmayan-trivially-destructible yapmak için yalnızca davranış olduğu boş küme ayraçları Yıkıcılar içerir.

#### <a name="correctness-fixes-in-visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5 doğruluk giderir

- `std::partition` Şimdi çağrıları koşulu N kez N yerine + 1 kez standart olarak gerektirir.
- Sürümünde 15.3 Sihirli istatistikleri önlemek için deneme sürümü 15,5 onarıldı.
- `std::atomic<T>` artık gerektirmez `T` oluşturulabilir varsayılan olarak kullanılacak.
- Logaritmik artık zaman yığın algoritmaları hata ayıklama yineleyici etkinleştirildiğinde giriş aslında bir yığın olduğunu doğrusal zaman onaylama işlemi yapın.
- `__declspec(allocator)` Şimdi bu declspec anlamıyor Clang gelen uyarıları önlemek yalnızca C1XX için korunur.
- `basic_string::npos` derleme zamanı sabit değer olarak kullanıma sunulmuştur.
- `std::allocator` diğer bir deyişle, hizalamasını düzgün aşırı hizalanmış türlerinin tanıtıcıları ayırma türleri artık C ++ 17 modunda değerinden daha büyük `max_align_t`tarafından devre dışı sürece **/Zc:alignedNew-**.  Örneğin, 16 veya 32 baytlık hizalama nesneleriyle vektörlerinin şimdi düzgün SSE ve AVX yönergeleri için hizalanır.

### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15,6

- \<memory_resource >
- Kitaplık temelleri V1
- Silme polymorphic_allocator atama
- Sınıf şablon bağımsız değişken kesintisi artırma

### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- Destek için paralel algoritmalar experiemental artık değil
- Yeni bir uyarlamasını \<filesystem >
- Başlangıç dize dönüştürmeleri (kısmi)
- Std::launder()
- Std::byte
- hypot(x,y,z)
- gereksiz decay önleme
- Matematik özel işlevler
- constexpr char_traits
- STL için kesintiyi kılavuzları

Bkz: [Visual C++ dili uygunluğu](visual-cpp-language-conformance.md) daha fazla bilgi için.

## <a name="other-libraries"></a>Diğer kitaplıkları

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg** alınırken ve açık kaynak C++ statik kitaplıklar ve DLL'ler Visual Studio'da oluşturma işleminin büyük ölçüde basitleştirir bir açık kaynak komut satırı aracıdır. Daha fazla bilgi için bkz: [vcpkg: C++ için bir paket Yöneticisi](vcpkg.md).

**Visual Studio 2017 sürüm 15,5**:

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

C++ için platformlar arası web API'si CPPRestSDK 2.9.0 sürümüne güncelleştirildi. Daha fazla bilgi için bkz: [CppRestSDK 2.9.0 Github'da kullanılabilir](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

- Henüz başka bir ad arama uygunluk düzeltmeleri kümesi
- Taşıma oluşturucuları var ve atama işleçleri şimdi düzgün olarak atma olmayan işaretlenmiş taşıma
- Kaydını bastırmak geçerli C4640 hakkında uyarı atlstr.h içinde yerel istatistikleri, iş parçacığı güvenli başlatma
- İş parçacığı güvenli başlatma yerel İstatistikleri otomatik olarak devre dışı XP araç takımında yer olduğunda [ATL DLL oluşturma ve kullanma]. Bu durum artık geçerli değildir. Ekleyebileceğiniz **/Zc:threadSafeInit-** kapalı güvenli başlatma iş parçacığı olması durumunda, proje ayarlarınızı istenen.

### <a name="visual-c-runtime"></a>Visual C++ çalışma zamanı

- Yeni üstbilgi denetim akışı koruma sembolleri "cfguard.h".

## <a name="c-ide"></a>C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Artık bir çözüm yapılandırması ilk defa etkinleştirildiğinde daha hızlı çalışır ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında gerçekleşir.

**Visual Studio 2017 sürüm 15.3**:

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf ekleme** şimdi sınıfı Ekle Sihirbazı'nı doğrudan başlatır. Öğelerin tümünü olan diğer daha önce burada şu anda kullanılabilir durumda altında **Ekle > Yeni öğe**.
- Win32 Proje yoksa şimdi altında **Windows Masaüstü** kategorisinde **yeni proje** iletişim.
- **Windows konsol** ve **masaüstü uygulaması** şablonları artık bir sihirbaz görüntülemeden projeleri oluşturma. Yeni bir **Windows Masaüstü Sihirbazı'nı** eski aynı seçeneklerini görüntüler aynı kategorisi altında **Win32 konsol uygulaması** Sihirbazı.

**Visual Studio 2017 sürüm 15,5**:

Yeniden düzenleme ve kod gezinti için IntelliSense Altyapısı'nı kullanan birkaç C++ işlemleri çok daha hızlı çalıştırın. Şu sayıları 3500 projeleri Visual Studio Chromium çözümüyle dayanır:

|||
|-|-|
|Özellik|Performansı geliştirme|
|Rename|5.3 x|
|Değişiklik imza |4.5 x|
|Tüm Başvuruları Bul|4.7 x|

C++ artık Ctrl + Click destekler **Tanıma Git**, fare Gezinti tanımlarına kolaylaşır. Üretkenlik Güç Araçları Paketi yapısı Görselleştirici şimdi de ürünün varsayılan olarak bulunmaktadır.

## <a name="intellisense"></a>IntelliSense

- Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Bu gibi veritabanı işlemlerini yukarı hızlandırır **Tanıma Git** ve **tüm başvuruları Bul**ve ilk çözüm ayrıştırma süresini önemli ölçüde geliştirecektir. Ayar taşındı **Araçlar > Seçenekler > Metin Düzenleyicisi > C/C++ > Gelişmiş** (önceki adıyla altında olduğu... C/C++ | Deneysel).

- Biz projelerinde IntelliSense performansı geliştirildi ve önceden derlenmiş üstbilgi dosyaları kullanmıyorsa - otomatik önceden derlenmiş üst bilgi üstbilgilerinin geçerli dosyasında oluşturulur.

- Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Filtrelenmiş Hata Listesi](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

- Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye Listesi Filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

- Üye Listesi’nde görünenleri bağlama duyarlı olarak filtreleyen yeni bir deneysel Tahmine Dayalı IntelliSense özelliği eklendi. Bkz: [C++ IntelliSense geliştirmeleri - Tahmine dayalı IntelliSense & filtreleme](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)
- **Tüm başvuruları Bul** (Shift + elde kolayca bile karmaşık yardımcı olarak kullanılabilecek kod temeli artık F12). Filtreleme, sıralama, arama sonuçları içindeki ve (bazı diller için) Gelişmiş gruplandırma sağlar, başvuruları NET bir anlayış sınıflandırıp renklendirme. C++ için yeni kullanıcı arabirimini olup olmadığını biz okuma veya yazma için bir değişken hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyicisi özellikleri **genişletin kapsamları** ve **genişletin öncelik** de gelen Deneysel için Gelişmiş taşınmıştır.
- Deneysel düzenleme özellikleri **değişiklik imza** ve **ayıklamak işlevi** artık varsayılan olarak kullanılabilir.
- Deneysel 'Daha hızlı yük proje' özelliği C++ projeleri için. Artık açtığınız C++ projesi daha hızlı yüklenir. Aynı projeyi daha sonra tekrar açtığınızda çok daha hızlı yüklenir!
- Bu özelliklerden bazıları diğer diller için ortaktır ve C++ için belirli bazılarıdır. Bu yeni özellikler hakkında daha fazla bilgi için bkz: [tanışın Visual Studio "15"](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/).

**Visual Studio 1027 sürüm 15.7**: ClangFormat için ek destek. Daha fazla bilgi için bkz: [Visual Studio 2017 ClangFormat desteği](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>Klasör Aç sahip olmayan MSBuild projeler

Visual Studio 2017 tanıtır **Klasör Aç** , kod, derleme ve herhangi bir çözüm veya projeleri oluşturmak zorunda kalmadan kaynak kodu içeren bir klasör içinde hata ayıklama olanak tanıyan özellik. Projenizi MSBuild tabanlı projesinde olmasa bile, Visual Studio ile çalışmaya başlamak daha kolay yapar. İle **Klasör Aç** anlama, düzenleme, derleme ve hata ayıklama sağlayan Visual Studio zaten MSBuild projelerine yetenekleri güçlü kodu erişin. Daha fazla bilgi için bkz: [Klasör Aç Visual C++ projelerinde](ide/non-msbuild-projects.md).

- Klasör Aç deneyimi geliştirmeleri. Bu .json dosyaların yoluyla deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

**Visual Studio 2017 sürüm 15.3**:

- Alternatif derleyicileri ve MinGW ve Cygwin gibi derleme ortamları için geliştirilmiş destek. Daha fazla bilgi için bkz: [kullanarak MinGW ve Visual C++ ve klasör Aç Cygwin](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
- Genel ve özel yapılandırma ortam değişkenleri CppProperties.json ve CMakeSettings.json tanımlamak için destek eklendi. Bu ortam değişkenleri launch.vs.json ve tasks.vs.json görevlerinde tanımlanan hata ayıklama yapılandırmaları tarafından kullanılabilecek. Daha fazla bilgi için bkz: [ortamınızı Visual C++ ve klasör Aç ile özelleştirme](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/customizing-your-environment-with-visual-c-and-open-folder/).
- Kolayca 64 bit platformları hedeflemesi yeteneği dahil olmak üzere CMake'nın Ninja Oluşturucu için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Klasör Aç üzerinden CMake desteği

Visual Studio 2017 CMake projeleri MSBuild proje dosyalarına (.vcxproj) dönüştürmeden kullanmaya yönelik destek sunar. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](ide/cmake-tools-for-visual-cpp.md). CMake projelerle açma **Klasör Aç** ortam düzenleme, derleme ve hata ayıklama C++ için otomatik olarak yapılandırır.

- C++ IntelliSense CppProperties.json dosyası kök klasöründe oluşturmak zorunda kalmadan çalışır. Bunun yanı sıra kullanıcıların CMake ve CppProperties.json dosyalarıyla sağlanan yapılandırmalar arasında kolayca geçiş yapması için yeni bir açılır menü ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![Cmake Klasör Aç](media/cmake_cpp.png "CMake Klasör Aç")

**Visual Studio 2017 sürüm 15.3**: CMake Ninja Oluşturucu için ek destek. 

**Visual Studio 2017 sürüm 15,5**: Varolan CMake içeri aktarmak için eklenen destek önbelleğe alır. 

**Visual Studio 2017 sürüm 15.7**: Destek CMake 3.11, CMake projelerinde kod analizi için eklenmiştir. Çözüm Gezgininde önbellek oluşturma ve tek dosyalı derleme seçenekleri görünümü hedefler. Daha fazla bilgi için bkz: [CMake desteği Visual Studio](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [CMake Visual C++ projelerinde](ide/cmake-tools-for-visual-cpp.md).

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik.  Yükleyici kullanıcı arabiriminde bileşenler için listelenen yükleme boyutlarının doğru olmadığını ve toplam boyutu düşük gösterdiğini lütfen aklınızda bulundurun.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Önerilen (Seçili) bileşenlerini yükleme **VC ++ 2017 v141 araç takımı (x86, x64)** ve **Windows 10 SDK (10.0.nnnnn)** bu çalışır sağlar. Gerekli araçlar yüklenmezse, projeler başarıyla oluşturulamaz ve sihirbaz yanıt vermemeye başlar.

**Visual Studio 2017 sürüm 15,5**:

Visual C++ derleme Araçları (daha önce tek başına bir ürün kullanılabilir) sunulmuştur Visual Studio yükleyicisi iş yükünü olarak dahil. Bu iş yükü yalnızca Visual Studio IDE yüklemeden C++ projeleri oluşturmak için gerekli Araçları'nı yükler. V140 ve v141 toolsets dahil edilir. Visual Studio 2017 sürüm 15,5 en son yenilikleri v141 araç takımı içerir. Daha fazla bilgi için bkz: [Visual Studio derleme araçları şimdi dahil VS2017 ve VS2015 MSVC Toolsets](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/).

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirmesi

Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

**Visual Studio 2017 sürüm 15.2**:

Platformlar arası kod paylaşımı ve türü görüntüsü iyileştirmeler yapılmıştır. Daha fazla bilgi için bkz: [platformlar arası için Linux C++ geliştirmeleri kod paylaşımı ve yazın görselleştirme](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/).

**Visual Studio 2017 sürüm 15,5**:

- Linux iş yükü için destek eklemiştir **rsync** alternatif olarak **sftp** uzak Linux makineler dosyalar için.
- Destek için ARM mikrodenetleyici hedefleme derleme eklenir. Bu yüklemede etkinleştirmeyi tercih **C++ ile Linux geliştirme** iş yükü ve seçeneğini belirleyin **katıştırılmış ve IOT geliştirme**. Bu seçenek, derleme araçlarını çapraz ARM GCC ve marka yüklemenize ekler. Daha fazla bilgi için bkz: [arası ARM GCC derleme Visual Studio'da](https://blogs.msdn.microsoft.com/vcblog/2017/10/23/arm-gcc-cross-compilation-in-visual-studio/).
- Destek CMake için eklenmiştir. Varolan CMake kodunuz üzerinde temel bir Visual Studio projesi dönüştürmek zorunda kalmadan şimdi çalışabilir. Daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma](linux/cmake-linux-project.md).
- Destek uzak görevleri çalıştırmak için eklenmiştir. Bu özellik, Visual Studio'nun Bağlantı Yöneticisi'nde tanımlı bir uzak sistemde herhangi bir komut çalıştırmanızı sağlar. Uzak görevler, dosyaları uzak sisteme kopyalama olanağı da sağlar.
Daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma](linux/cmake-linux-project.md).

**Visual Studio 2017 sürüm 15.7**:

- Linux iş yükü senaryoları çeşitli iyileştirmeler. Daha fazla bilgi için bkz: [proje sistemi, Linux konsol penceresi, rsync ve işleme Ekle Linux C++ iş yükü geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2018/03/13/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- Uzak Linux bağlantıları üstbilgilerinde için IntelliSense. Daha fazla bilgi için bkz: [uzak Linux üstbilgileri için IntelliSense](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/intellisense-for-remote-linux-headers/) ve [bir Linux CMake proje yapılandırma](linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ (Android ve iOS) ile Mobil Geliştirme

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017’de v140 hedefli bir UWP projesi açtığınızda, sisteminizde Visual Studio 2015 yüklü değilse proje özelliği sayfalarından v141 platformu araç kümesini seçmeniz gerekiyor.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>C++ için yeni seçenekler Evrensel Windows Platformu (UWP) üzerinde

Şimdi, yazma ve C++ uygulamaları Evrensel Windows platformu ve Microsoft Store için paketleme yeni seçeneğiniz de vardır. Masaüstü uygulaması dönüştürücü varolan Masaüstü uygulamanızı Microsoft Store aracılığıyla dağıtım paketi için kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/) ve [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](/windows/uwp/porting/desktop-to-uwp-root).

**Visual Studio 2017 sürüm 15,5**:

A **Windows Uygulama paketleme projesi** proje şablonu, Masaüstü uygulamaları, Masaüstü köprüsü kullanarak paketleme destekleyen eklenir. Altında kullanılabilir **Dosya > Yeni > Proje** altında **yüklü > Visual C++ > Evrensel Windows platformu** Evrensel Windows uygulaması iş yükü yüklü olduğunda.

Yeni kod yazarken, artık C + kullanabilirsiniz +/ WinRT, standart bir C++ dili projeksiyonu yalnızca üstbilgi dosyalarında uygulanan Windows çalışma zamanı için. Her iki Yazar sağlar ve Windows çalışma zamanı standartlarıyla uyumlu tüm C++ derleyicisi kullanarak API'larını kullanabilir. C + +/ WinRT C++ geliştiricilerin modern Windows API için birinci sınıf erişimi sağlamak için tasarlanmıştır. Daha fazla bilgi için bkz: [C + +/ WinRT Github'da](https://moderncpp.com/).

Sürümünden başlayarak [17025 Windows SDK Insider Önizleme yapı](https://blogs.windows.com/buildingapps/2017/11/01/windows-10-sdk-preview-build-17025/#ryPH3zAy6yk2cIRX.97), C + +/ WinRT Windows SDK'da yer almaktadır. Daha fazla bilgi için bkz: [C + +/ WinRT olan artık Windows SDK'sını dahil](https://blogs.msdn.microsoft.com/vcblog/2017/11/01/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

İle birlikte Clang/C2 araç [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] artık destekliyor **/bigobj** geçiş, hangi büyük projeler oluşturma açısından önemlidir. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ kod çözümleme

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Yalnızca denetleyicileri etkinleştirmek **kod çözümleme uzantıları** Kod Analizi çalıştırdığınızda, projenin özellik sayfaları ve uzantıları sayfası dahil olacaktır. Daha fazla bilgi için bkz: [C++ çekirdek yönergeleri denetleyicileri kullanarak](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikler sayfası")

**Visual Studio 2017 sürüm 15.3**: kaynak yönetimiyle ilgili kuralları için ek destek.

**Visual Studio 2017 sürüm 15,5**: yeni bir C++ çekirdek Kılavuzu denetimleri kapak akıllı işaretçi doğruluk, doğru kullanımı genel başlatıcıları ve yapıları gibi bayrak kullanımlarını `goto` ve hatalı atamaları.

15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

**Visual Studio 2017 sürüm 15,6**:  
Destek tek dosya çözümleme ve analiz çalışma zamanı performans geliştirmeleri eklenmiştir. Daha fazla bilgi için bkz: [C++ statik çözümleme geliştirmeleri için Visual Studio 2017 15,6 Önizleme 2](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

**Visual Studio 2017 sürüm 15.7**:  

- Eklenen Destek [/ analyze: ruleset](build/reference/analyze-code-analysis.md) çalıştırmak için hangi kod çözümleme kurallarını belirtmenize olanak sağlar.
- Destek için ek C++ çekirdek yönergeleri kurallar eklenmiştir.  Daha fazla bilgi için bkz: [C++ çekirdek yönergeleri denetleyicileri kullanarak](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Birim testi

**Visual Studio 2017 sürüm 15,5**:

Google Test bağdaştırıcısı ve Boost.Test bağdaştırıcısı şimdi bileşenleri olarak kullanılabilir **C++ ile masaüstü geliştirme** tümleşik iş yükü ve misiniz **Test Gezgini**. CTest desteği (Klasör Aç kullanarak) Cmake projeleri için eklenir, ancak ile tam tümleştirme **Test Gezgini** henüz kullanılabilir değil. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

**Visual Studio 2017 sürüm 15,6**:

- Destek Boost.Test dinamik kitaplık desteği eklendi.
- Boost.Test öğe şablonu IDE içinde kullanıma sunulmuştur.

Daha fazla bilgi için bkz: [Boost.Test birim testi: dinamik kitaplık desteği ve yeni öğe şablonu](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/boost-test-unit-testing-dynamic-library-support-and-new-item-template/). 

**Visual Studio 2017 sürüm 15.7**:

[CodeLens](https://docs.microsoft.com/en-us/visualstudio/ide/find-code-changes-and-other-history-with-codelens) desteklenen C++ birim testi projelerini için eklendi. Daha fazla bilgi için bkz: [tanışın CodeLens C++ birim testi için](https://blogs.msdn.microsoft.com/vcblog/2018/04/09/announcing-codelens-for-c-unit-testing/).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio grafik Tanılama, kaydetme ve Direct3D uygulamalar oluşturma ve performans sorunları çözümlemek için araç kümesidir. Grafik tanılama özellikleri, Windows bilgisayarınızdaki bir Windows aygıt benzeticisi veya bir uzak bilgisayar veya cihaz üzerinde yerel olarak çalışan uygulamalar ile kullanılabilir.

- **Giriş ve çıkış köşe ve geometri gölgelendiriciler için:** giriş ve çıkış köşe gölgelendiriciler ve geometri gölgelendiriciler görüntüleme olanağı en çok istenen özelliklerden biri olmuştur ve araçları artık desteklenmektedir. Yalnızca kendi giriş inceleniyor başlatmak için ardışık düzen aşamaları görünümünde VS veya GS aşamayı seçin ve aşağıdaki tabloda çıktı.

  ![Giriş/Çıkış gölgelendiriciler için](media/io-shaders.png)

- **Arama ve filtreleme nesne tablosundaki:** sunar kaynaklarını bulmak için hızlı ve kolay bir yol aradığınız.

  ![Ara](media/search.png)

- **Kaynak geçmişi:** bu yeni görünüm, yakalanan çerçeve işleme sırasında kullanılan gibi bir kaynak tüm değişiklik geçmişini görmesini bir kolaylaştırılmış bir yolunu sunar. Herhangi bir kaynak için geçmiş çağırmak için herhangi bir kaynak köprüye yanındaki saati simgesine tıklamanız yeterlidir.

  ![Kaynak geçmişi](media/resource-history.png)

  Bu yeni görüntüler **kaynak geçmiş** araç penceresi, kaynak değişiklik geçmişi ile doldurulur.

  ![Kaynak geçmiş değişikliği](media/resource-history-change.png)

  Çerçevenizi tam çağrı yığını yakalama etkin yakalandıysa unutmayın (**Visual Studio > Araçlar > Seçenekler** altında **grafik tanılama**), sonra her değişiklik olayı bağlamında hızla olabilir anlaşılan ve Visual Studio projesi içinde sahip denetlenir.

- **API istatistikleri:** , çerçevede API kullanımı üst düzey bir özetini görüntüleyin. Bu, hiç değişiklik yapıyorsunuz bilmiyor olabilirler çağrıları ya da çok fazla kuran çağrıları keşfetme de kullanışlı olabilir. Bu pencere aracılığıyla kullanılabilir **Görünüm > API istatistikleri** Visual Studio grafik Çözümleyicisi.

  ![API istatistikleri](media/api-stats.png)

- **Bellek istatistikleri:** çerçevede oluşturduğunuz sürücü için kaynakları ayırma ne kadar bellek görüntüleyin. Bu pencere aracılığıyla kullanılabilir **Görünüm > bellek istatistikleri** içinde **Visual Studio grafik Çözümleyicisi**. Veri kopyalanabileceği bir elektronik tabloda görüntülemek için bir CSV dosyasına sağ tıklayıp seçerek **Tümünü Kopyala**.

  ![Bellek istatistiği](media/memory-stats.png)

- **Çerçeve doğrulaması:** yeni hataları ve Uyarıları listesi Direct3D hata ayıklama katman tarafından algılanan olası sorunları göre olay listenize gitmek için kolay bir yol sağlar. Tıklatın **Görünüm > Çerçeve doğrulama** , Visual Studio grafik Çözümleyicisi aygıtını penceresini açın. Ardından **doğrulama çalışması** analiz başlatmak için. Çerçeve karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **Çerçeve analizi için D3D12:** ile çizim çağrısı performansını çözümlemek için kullanım çerçeve analizi yönlendirilmiş "what-if" denemeler. Çerçeve analizi sekmesine geçin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için izleme [GoingNative 25: Visual Studio Grafik Çerçeve Çözümlemesi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) video.

  ![Çerçeve analizi](media/frame-analysis.png)

- **GPU kullanımı iyileştirmeleri:** GPU görünümü ya da Windows Performans Çözümleyicisi (WPA) aracını ile Visual Studio GPU kullanım profil oluşturucu aracılığıyla daha ayrıntılı çözümleme için gerçekleştirilecek izlemeleri açın. Varsa, Windows Performans Araç Seti yüklü WPA, diğeri GPU görünümünde, sağ alt köşesindeki oturum genel bakış için iki köprüler olacaktır.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı destek GPU görünümünde açılan izlemeleri yakınlaştırma ve zaman çizelgesi VS ve GPU görünümü arasında kaydırma eşitlendi. Vs'de bir onay kutusu eşitleme veya etkin olup olmadığını denetlemek için kullanılır.

  ![GPU görünümü](media/gpu-view.png)
