---
title: Visual Studio'da Visual C++ yenilikler | Microsoft Docs
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9927726585572f69bdf121c4ed71e8b034fc1ed3
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="whats-new-for-visual-c-in-includevsdev15mdmiscincludesvsdev15mdmd"></a>Visual c++'ta için yenilikler nelerdir?[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]çok sayıda güncelleştirme getirir ve Visual C++ ortamına giderir. Çoğu [Microsoft Connect](https://connect.microsoft.com/VisualStudio "Microsoft Connect") aracılığıyla müşteriler tarafından gönderilen, derleyici ve araçlarla ilgili 250’den fazla hatayı ve bildirilen sorunu düzelttik. Hataları bildirdiğiniz için teşekkür ederiz!  Tüm Visual Studio yenilikler hakkında daha fazla bilgi için lütfen ziyaret [yenilikler [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] ](https://go.microsoft.com/fwlink/?linkid=834481).

<!--The compiler and tools version number in [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] is 14.10.24629. -->


## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uygunluk geliştirmeleri
Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md).

### <a name="new-compiler-switches"></a>Yeni derleyici anahtarları  

 -**/ Std: c ++ 14** ve **/Std: c ++ Son**: Bu derleyici anahtarları ISO C++ programlama dili projesinde belirli sürümlerine katılımı olanak sağlar. Daha fazla bilgi için bkz: [-std (dil standart sürümünü belirtin)](build/reference/std-specify-language-standard-version.md). Standart Özellikler/Std: c tarafından korumalı yeni taslak çoğu ++ son anahtar. 

**Visual Studio 2017 sürüm 15.3**: **/Std: c ++ 17** seçeneği Visual C++ derleyicisi tarafından uygulanan C ++ 17 özellikler kümesi sağlar. Bu seçenek derleyicisi ve standart kitaplığı desteği değiştirilen özellikler için veya yeni C++ standart çalışma taslak ve hatasını güncelleştirmeleri, daha yeni sürümlerinde devre dışı bırakır.

-[/ izin veren-](build/reference/permissive-standards-conformance.md): tüm katı standartları uyumluluk derleyici seçenekleri etkinleştirmek ve en Microsoft'a özgü derleyici Uzantıları (ancak örneğin değil __declspec(dllimport)) devre dışı bırakın. (Varsayılan olarak kapalı ancak üzerinde varsayılan olarak, belirli bir noktada gelecekte görüntülenir.)

-[/Diagnostics](build/reference/diagnostics-compiler-diagnostic-options.md): satır numarası, satır numarası ve sütun veya satır numarasını ve sütun ve burada tanılama hata veya uyarı bulundu kod satırı altında bir şapka görüntüsünü etkinleştirin.

-[/Debug:fastlink](build/reference/debug-generate-debug-info.md):  
% 30 etkinleştirmek daha hızlı artımlı bağlantı zaman (vs. Visual Studio 2015) değil kopyalayarak tüm PDB dosyasına hata ayıklama bilgileri. PDB dosyası yerine yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplık dosyaları için hata ayıklama bilgileri işaret eder. Bkz: [daha hızlı C++ derleme /Debug:fastlink ile VS "15" döngüsünde](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/faster-c-build-cycle-in-vs-15-with-debugfastlink/) ve [derlemeler Visual Studio'da C++ önerileri hızı](https://blogs.msdn.microsoft.com/vcblog/2016/10/26/recommendations-to-speed-c-builds-in-visual-studio/).

[!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)]await / ile/SDL kullanarak sağlar. Biz, eş yordamlarla/RTC sınırlamasını kaldırıldı. 

**Visual Studio 2017 sürüm 15,5**: Visual C++ Derleyici destekleyen yaklaşık %75 yapılandırılmış bağlamaları dahil olmak üzere C ++ 17 özellikleri, `constexpr` Lambda'lar, `if constexpr`, satır içi değişkenleri Katlama ifadeleri ve ekleme `noexcept` türü Sistem. / Std: c altında kullanılabilir bunlar ++ 17 anahtar. /Permissive-conformance modu, iki aşamalı ad arama kısmi destekler. Daha fazla bilgi için bkz: [C++ uygunluk Visual Studio 2017 yenilikleri](cpp-conformance-improvements-2017.md). 

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma
Bu sürümdeki yenilikleri en iyi duruma getirme, kod oluşturma, araç takımı sürüm oluşturma ve tanılama getirir. Bazı önemli geliştirmeler şunlardır:  

- Döngüler için geliştirilmiş kod oluşturma: sabit tam sayıları bölme işlemleri için otomatik vektörleştirme desteği, memset desenlerinin daha iyi tanınması.
- Geliştirilmiş kod güvenliği: Geliştirilmiş arabellek taşma derleyici tanılaması verme; ayrıca /guard:cf, artık atlama tablosu oluşturan switch deyimlerini korur.
- Sürüm oluşturma: Yerleşik önişlemci makrosu _MSC_VER değerini şimdi tekdüze her Visual C++ araç takımını güncelleştirmeyi güncelleştiriliyor. Daha fazla bilgi için bkz: [Visual C++ Derleyici sürümü](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/visual-c-compiler-version/).
- Yeni araç takımı Düzen: derleyici ve ilgili derleme araçları geliştirme makinenizde yeni bir konum ve dizin yapısına sahip. Yeni düzen derleyici birden fazla sürümünü yan yana yüklemesini sağlar. Daha fazla bilgi için bkz: [derleyici araçları Visual Studio "15" düzende](https://blogs.msdn.microsoft.com/vcblog/2016/10/07/compiler-tools-layout-in-visual-studio-15/).
- Gelişmiş Tanılama: artık çıktı penceresi bir hata oluştuğu sütun gösterir. Daha fazla bilgi için bkz: [C++ Derleyici tanılama geliştirmeleri VS "15" Preview 5](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Ortak yordamları, Deneysel anahtar sözcüğü "Verim" kullanırken (altında kullanılabilir / anahtar bekleme) kaldırılmıştır. Kodunuzu kullanacak şekilde güncelleştirilmesi `co_yield` yerine. Daha fazla bilgi için [Visual C++ Ekip bloguna](https://blogs.msdn.microsoft.com/vcblog/) bakın. 

**Visual Studio 2017 sürüm 15.3**: derleyici tanılamada ek iyileştirmeler. Daha fazla bilgi için bkz: [Visual Studio 2017 15.3.0 tanılama geliştirmeleri](https://blogs.msdn.microsoft.com/vcblog/2017/07/21/diagnostic-improvements-in-vs2017-15-3-0/).

**Visual Studio 2017 sürüm 15,5**: Visual C++ çalışma zamanı performans nedeniyle daha iyi oluşturulan kod kalitesini arttırma denemeye devam eder. Bunun anlamı yalnızca kodunuzu derleyin ve yalnızca uygulamanızı daha hızlı çalışır. Yepyeni, SSA iyileştirici yedekli yönergeleri eleme ve birleştirme çağrıları sin(x) ve yeni sincos(x) içine cos(x) vectorization koşullu skaler depoları gibi derleyici iyileştirmelerini bazılarıdır. Diğer derleyici iyileştirmelerini vektör yapıcı buluşsal yöntemler koşullu ifadeler, daha iyi döngü en iyi duruma getirme ve float min/max codegen gibi varolan işlevine geliştirmeleri eklenmiştir. Bağlayıcı 9 adede kadar % bağlantı zaman speedups sonucunda bir yeni ve hızlı /OPT:ICF uygulaması sahiptir ve "artımlı bağlantılandırma içinde" diğer perf düzeltmeleri olan. Daha fazla bilgi için bkz: [OPT (iyileştirmeler)](https://docs.microsoft.com/en-us/cpp/build/reference/opt-optimizations) ve [/INCREMENTAL (artımlı bağlantı)](https://docs.microsoft.com/en-us/cpp/build/reference/incremental-link-incrementally).

Visual C++ Intel'in AVX-512 yeni işlevler AVX-512 128 ve 256 bit geniş yazmaçlar Getir vektör uzunluğu yönergeleri de dahil olmak üzere, destekler.

**/Zc:noexceptTypes-** anahtar, C ++ 14 sürümüne geri dönmek için kullanılabilir `noexcept` genel C ++ 17 modu kullanırken. Bu, C ++ 17'ye tüm yeniden yazmaya gerek kalmadan uygun olması için kaynak kodu güncelleştirmenizi sağlar, `throw()` aynı anda kodu. Daha fazla bilgi için bkz: [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements-2017.md#noexcept_removal).


## <a name="c-standard-library-improvements"></a>C++ Standart Kitaplığı geliştirmeleri

* Küçük basic_string _ITERATOR_DEBUG_LEVEL != 0 tanılama iyileştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
* Performans iyileştirmesi: basic_string::find(char) aşırı yüklemelerinin traits::find’ı yalnızca bir kez araması sağlandı. Daha önce bu, 1 uzunluğunda bir dizenin genel dize araması olarak uygulanıyordu.
* Performans iyileştirmesi: basic_string::operator== artık dizelerin içeriklerini karşılaştırmadan önce dizenin boyutunu denetler.
* Performans iyileştirmesi: basic_string’de derleyici iyileştiricisinin analiz etmekte zorlandığı denetim ilişkilendirme kaldırıldı. VSO # 262848 çözümler "\<dize\>: reserve() mu çok fazla iş". Tüm kısa dizeler için reserve’in çağrılması, hiçbir şey yapmamak için yine de sıfır olmayan bir etkide bulunur.
* \<any\>, \<string_view\>, apply(), make_from_tuple() eklenmiştir.
* std::vector, doğruluk ve performans sağlayacak şekilde yenilendi: Ekleme/yerleştirme sırasında diğer ad oluşturma artık Standartlara uygun olarak doğru şekilde yapılır, move_if_noexcept() ve başka bir mantık aracılığıyla Standart tarafından gerekli kılındığında artık güçlü özel durum garantisi sağlanır ve ekleme/yerleştirme daha az öğe işlemi gerçekleştirir.
* C++ Standart Kitaplığı, şimdi null süslü işaretçileri başvurusunun kaldırılmasının önler.
* \<optional\>, \<variant\>, shared_ptr::weak_type ve \<cstdalign\> eklendi.
* min/max/minmax(initializer_list) ve min_element/max_element/minmax_element() içinde C++14 constexpr etkinleştirildi.
* weak_ptr::lock() performansı geliştirildi.
* Daha önce kodun sürekli olarak engellenmesine neden olabilen std::promise taşıma atama işleci düzeltildi.
* atomic\<T \*\> öğelerinin T \* öğesine örtük olarak dönüştürülmesine ilişkin derleyici hataları düzeltildi.
* pointer_traits\<Ptr\> artık Ptr::rebind\<U\>’ları doğru algılar.
* move_iterator’ın çıkarma işlecindeki eksik bir const niteleyicisi düzeltildi.
* propagate_on_container_copy_assignment ve propagate_on_container_move_assignment isteyen, durum bilgisi olan kullanıcı tanımlı ayırıcılar için sessiz hatalı codegen düzeltildi.
* atomic\<T\> artık aşırı yüklenmiş operator&() öğesine tolerans gösterir.
* Derleyici verimliliğini artırmak için gereksiz derleyici iç bilgileri için bildirimleri de dahil olmak üzere standart C++ Kitaplığı üstbilgilerini şimdi kaçının.
* Yanlış bind() çağrıları için biraz daha geliştirilmiş derleyici tanılaması.
* Std::string performansını geliştirilmiş / 3'ten fazla x std::wstring'ın taşıma oluşturucuları
* Standart Kitaplığı tam bir listesi için bkz: geliştirmelerin [standart kitaplığı düzeltmeler de VS 2017 RTM](https://blogs.msdn.microsoft.com/vcblog/2017/02/06/stl-fixes-in-vs-2017-rtm/).

### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

#### <a name="c17-features"></a>C ++ 17 özellikleri 
Birkaç ek C ++ 17 özellikleri uygulanmıştır. Daha fazla bilgi için bkz: [Visual C++ dili uygunluk](cpp-conformance-improvements-2017.md#improvements_153).

#### <a name="other-new-features"></a>Diğer yeni özellikler
* Uygulanan P0602R0 "değişken ve isteğe bağlı copy/move triviality yayılması".
* Standart Kitaplığı şimdi /GR-devre dışı bırakılıyor dinamik RTTI resmi olarak göstereceği. Standart Kitaplığı artık bunları = /GR-altında Sil gibi işaretler bunu dynamic_pointer_cast() ve rethrow_if_nested() kendiliğinden dynamic_cast gerektirir.
* Hatta zaman dinamik RTTI "statik RTTI" /GR-devre dışı bırakıldı (typeid(SomeType)) biçiminde hala kullanılabilir olduğundan ve birkaç standart Kitaplığı bileşenleri çalıştırır. Standart Kitaplığı, şimdi de bu devre dışı bırakma destekler /D_HAS_STATIC_RTTI = 0. *Bu std::any, std::function'ın target() ve target_type() ve shared_ptr'ın get_deleter() devre dışı bıraktığını unutmayın.*

#### <a name="correctness-fixes"></a>Doğruluk düzeltmeleri
* Standart Kitaplığı kapsayıcıları şimdi numeric_limits için kendi max_size() clamp\<difference_type\>:: size_type yerine max() maks. Bu, kapsayıcısından yineleyiciler üzerinde distance() sonucunu distance() dönüş türü gösterilebilir olmasını sağlar.
* Eksik uzmanlık auto_ptr sabit\<void\>.
* Length bağımsız bir tam sayı türde değildi derlemeniz daha önce başarısız meow_n() algoritmaları; Bunlar artık integral olmayan uzunlukları yineleyiciler difference_type dönüştürmeyi dener.
* normal_distribution\<float\> artık float uyarıları standart çift daraltma hakkında kitaplığı içinde yayar.
* Npos max_size() yerine ile en büyük boyutu taşma için Denetim yapılırken karşılaştırma bazı basic_string işlemleri sabit.
* condition_variable::wait_for (kilitleme, relative_time, koşul) alacaklardır Uyandırma durumunda tüm göreli zaman beklemeniz. Şimdi, yalnızca bir tek göreli zaman aralığı için bekler.
* Standart gerektirdiği şekilde gelecekteki:: get() şimdi gelecekteki geçersiz kılar.
* iterator_traits\<void \* \> void form çalıştığı için sabit bir hata olması için kullanılan&; bu şimdi düzgün bir şekilde SFINAE koşulları "yineleyici olduğunu" iterator_traits kullanımına izin vermek için boş bir yapı olur.
* Clang - Wsystem-headers tarafından bildirilen bazı uyarılar düzeltilmiştir.
* Ayrıca "özel durum belirtimi bildiriminde önceki bildirimi Clang - Wmicrosoft-özel-spec tarafından bildirilen eşleşmiyor" sabit.
* Clang C1XX tarafından bildirilen ve ayrıca sabit mem başlatıcı listesi sıralama uyarılar.
* Kapsayıcıları kendilerini değiştirildi, sırasız kapsayıcılar kendi hashers veya koşulları takas değil. Şimdi bunların yapın.
* (Bizim standart kitaplığına hiçbir zaman propagate_on_container_swap olmayan eşittir ayırıcısı tanımsız davranış koşul algılama, bir özel durum amaçlayan gibi) çok sayıda kapsayıcı değiştirme işlemleri şimdi noexcept işaretlenir.
* Birçok vektör\<bool\> işlemleri şimdi noexcept olarak işaretlenmiş.
* Standart Kitaplığı şimdi vazgeçme kaçış tarama ile eşleşen ayırıcısı value_types (modunda C ++ 17) zorlar.
* Bazı koşullar burada self-range-insert into'nun basic_strings dizeleri içeriği karıştırmak sabit. (Not: self-range-insert into'nun vektörlerinin standardına göre hala Yasak.)
* basic_string::shrink_to_fit() artık ayırıcı'nın propagate_on_container_swap tarafından etkilenir.
* Std::decay şimdi abominable işlev türleri (MS-tam ve/veya ref tam yani işlevi türleri) işler.
* Değiştirilen uygun büyük küçük harfe duyarlılığın ve taşınabilirlik geliştirme eğik kullanmak için yönergeleri içerir.
* Uyarı C4061 "Numaralandırıcı 'Meow' Enum 'Kedi yavrusu' servis talebi etiket tarafından açıkça işlenmemiş anahtarda" sabit. Bu uyarı-varsayılan olarak kapalı ve bir özel durum uyarılarını standart kitaplığın Genel ilke olarak düzeltildi. (Standart Kitaplığı /W4 temiz olmakla birlikte wln temiz olarak denemez. Birçok-varsayılan olarak kapalı uyarılar son derece gürültülü ve düzenli aralıklarla kullanılmaya yönelik değildir.)
* Geliştirilmiş std::list ait hata ayıklama denetler. Liste yineleyiciler şimdi -> işleci () ve liste:: unique() artık geçersiz kılınan olarak yineleyiciler işaretler denetleyin.
* Sabit kullanır-ayırıcısı tanımlama grubu meta.

#### <a name="performancethroughput-fixes"></a>Performans/verimlilik düzeltmeleri
* Satır içi kullanım std engelleyen noexcept ile etkileşim geçici çalışılan:: yapılandırılmış özel durum işleme (SEH) kullanan işlevler uygulamasına atomik.
* Küçük koda fazla yerde içermesinden olmasını sağlayan en iyi duruma getirmek için standart kitaplığın iç _Deallocate() işlevi değiştirildi.
* Paketi genişletme yerine özyineleme kullanacak şekilde std::try_lock() değiştirildi.
* Kilitleri try_lock () s dönen yerine LOCK() işlemlerini kullanmak için geliştirilmiş std::lock ('s) kilitlenme kaçınma algoritması.
* System_category::message() adlandırılmış dönüş değeri iyileştirme etkin.
* birlikte ve ayrım şimdi örneği N + 2N + 2 türleri yerine 1 türleri.
* Std::Function ayırıcısı destek makineler her tür silinmesi aranabilir, iyileştirme üretilen iş ve std::function için birçok farklı Lambda'lar geçirmek programlarda azalan .obj boyutu için artık başlatır.
* allocator_traits\<std::allocator\> std::allocator yalnızca allocator_traits (yani çoğu kodu) ile etkileşimde kodda kod boyutunun azaltılması, el ile içermesinden std::allocator işlemlerini içerir.
* C ++ 11 en az ayırıcısı arabirimi şimdi standart bir iç sınıf _Wrap_alloc ayırıcı sarmalama yerine allocator_traits doğrudan çağırma kitaplığı tarafından işlenir. Bu ayırıcısı desteği oluşturulan kod boyutunu azaltır, bazı durumlarda standart kitaplığı kapsayıcıları hakkında neden iyileştirici'nin yeteneği artırır ve (Şimdi, ayırıcı türü yerine _Wrap_allocgördüğünüzgibihataayıklamadahaiyibirdeneyimsağlar\<ayırıcısı türünüz\> hata ayıklayıcı).
* Hangi allocators gerçekten özelleştirmek için izin verilmeyen özelleştirilmiş allocator::reference için meta kaldırıldı. (Allocators süslü işaretçileri ancak değil süslü başvuruları kullanamazsınız kapsayıcıları yapabilirsiniz.)
* Ön uç derleyici hata ayıklama yapıları performansını iyileştirme hata ayıklama yineleyiciler aralık tabanlı için-döngüler içinde açılacak öğrettin.
* basic_string'ın iç küçültme shrink_to_fit() ve reserve() artık mutating tüm üyeleri için kod boyutunun azaltılması, işlemlerini yeniden ayırma yolunda yoludur.
* basic_string iç büyümesine yol shrink_to_fit() yolunda artık değil.
* basic_string'ın diziyi operations ayırma hızlı yolu ve arayanlar içermesinden olması ortak Hayır yeniden ayırma çalışması için büyük olasılıkla yapmadan ayırma yavaş işlevleri şimdi oluşturmak.
* basic_string'ın diziyi işlemleri şimdi yapı içindeki arabellekler istenen durum yerine yeniden boyutlandırma yerinde yeniden ayrılır. Örneğin, başında bir dize şimdi ekleniyor içerik ekleme (aşağı veya yeni ayrılmış arabelleğe), sonra tam olarak bir kez yerine iki kez reallocating durumda (yeni ayrılmış arabelleğe ve sonra aşağı) taşınır.
* C Standart Kitaplığı arayan işlemleri \<dize\> şimdi TLS yinelenen etkileşim kaldırmak için errno'nın adresi önbelleğe.
* İs_pointer'ın uygulama Basitleştirilmiş.
* Struct/void_t tabanlı için işlevi tabanlı ifade SFINAE değiştirme işlemi tamamlandı.
* Standart Kitaplığı algoritmaları şimdi yineleyiciler postincrementing kaçının.
* 32-bit allocators 64 bitlik sistemlerde kullanırken sabit kesilmesi uyarılar.
* Std::Vector taşıma atama şimdi arabellek mümkün olduğunca yeniden kullanarak POCMA olmayan eşittir ayırıcısı durumda daha verimli olur.

#### <a name="readability-and-other-improvements"></a>Okunabilirlik ve diğer geliştirmeler
* Standart Kitaplığı şimdi C ++ 14 constexpr koşulsuz olarak, koşullu tanımlı makrolar yerine kullanır.
* Standart Kitaplığı şimdi diğer şablonları dahili olarak kullanır.
* Standart Kitaplığı şimdi nullptr dahili olarak kullandığı yerine nullptr_t {}. (Null iç kullanım eradicated. İç kullanım null olarak 0 kademeli olarak temizleniyor.)
* Standart Kitaplığı şimdi std::move() dahili olarak, stylistically std::forward() kötüye yerine kullanır.
* (False, "iletisi") değiştirilmiş static_assert #error iletisi. #Error derleme derhal sona erer çünkü bu derleyici tanılama artırır.
* Standart Kitaplığı, artık işlevleri __declspec(dllimport) olarak işaretler. Modern bağlayıcı teknolojisi artık bu gerektirir.
* Türleri ve işlevi bağımsız değişken türleri döndürülecek karşılaştırıldığında dağınıklığı azaltır ayıklanan SFINAE varsayılan şablon değişkenlerini için.
* Hata ayıklama denetler \<rastgele\> şimdi stderr'e fputs() olarak adlandırılan iç işlev _Rng_abort() yerine standart kitaplığının her zamanki makine kullanın. Bu işlevin uygulama ikili uyumluluk için korunur, ancak standart kitaplığı sonraki ikili uyumsuz sürümünde kaldırılmıştır. 

### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5
Birkaç standart kitaplığı özellikleri eklenmiş, kullanım dışı veya C ++ 17 standardına uygun olarak kaldırıldı. Daha fazla bilgi için bkz: [Visual Studio'da C++ uygunluk geliştirmeleri](cpp-conformance-improvements-2017.md#improvements_155).

#### <a name="new-experimental-features"></a>Yeni Deneysel özellikleri
* Aşağıdaki paralel algoritmalar Deneysel desteği:
  * all_of
  * any_of
  * for_each
  * for_each_n
  * none_of
  * Azaltma
  * replace
  * replace_if
  * sort
* Aşağıdaki paralel algoritmalar imzaları eklendi ancak şu anda paralel birkaç ölçeklendirin değil; Profil oluşturma fayda yalnızca taşımak veya öğeleri permute algoritmaları parallelizing gösterilmiştir:
  * copy
  * copy_n
  * fill
  * fill_n
  * move
  * reverse
  * reverse_copy
  * rotate
  * rotate_copy
  * swap_ranges

#### <a name="performance-fixes-and-improvements"></a>Performans düzeltmeleri ve geliştirmeleri
* basic_string\<char16_t > artık bu basic_string memcmp memcpy vb. iyileştirmeler prosese\<wchar_t > ilgilenir.
* Visual Studio 2015 güncelleştirme 3'te bizim "işlevleri kopyalama kaçının" iş tarafından sunulan engeller işlev işaretçileri içermesinden engelleyen bir iyileştirici sınırlaması geçici lower_bound (iter, iter, işlev işaretçisi) performansını geri çalışmıştır.
* Hata ayıklama yineleyici yükü sipariş doğrulama girişleri içerir, set_difference, set_symmetric_difference kullanıcının ve set_union sipariş denetlemeden önce tarafından açma yineleyiciler azaltılmıştır.
* Std::inplace_merge şimdi zaten konumda olan öğeler üzerinde atlar.
* Std::random_device artık oluşturma, oluşturur ve bir std::string yok eder.
* Std::Equal ve std::partition yineleyici karşılaştırma kaydedileceği bir atlama iş parçacığı oluşturma en iyi duruma getirme geçişi vardı.
* Std::reverse trivially copyable T işaretçileri geçirildiğinde, artık bir el yazısı vectorized uygulama gönderir.
* Std::Fill, std::equal ve std::lexicographical_compare memset için gönderme nasıl öğrettin / memcmp std::byte gsl::byte (ve diğer char-ish numaralandırmaları ve enum sınıfları) için. Bu std::copy is_trivially_copyable kullanarak gönderir ve bu nedenle herhangi bir değişiklik ihtiyacım kalmadı unutmayın.
* STL artık türleri olmayan-trivially-destructible yapmak için yalnızca davranış olduğu boş küme ayraçları Yıkıcılar içerir.

#### <a name="correctness-fixes"></a>Doğruluk düzeltmeleri
* Standart gerektirdiği şekilde std::partition şimdi koşulu N kez N yerine + 1 kez çağırır.
* 15.3 içinde Sihirli istatistikleri önlemek için deneme 15,5 onarıldı.
* Std::atomic\<T > artık T varsayılan oluşturulabilir olmasını gerektirir.
* Logaritmik artık zaman yığın algoritmaları hata ayıklama yineleyici etkinleştirildiğinde giriş aslında bir yığın olduğunu doğrusal zaman onaylama işlemi yapın.
* __declspec(Allocator) bu declspec anlamıyor Clang gelen uyarıları önlemek yalnızca C1XX için artık korunuyor.
* basic_string::npos bir derleme zamanı sabiti kullanıma sunulmuştur.
* Şimdi Std::Allocator aşırı hizalanmış türleri - hizalamasını (/Zc:alignedNew-tarafından devre dışı bırakılmamışsa) max_align_t – C ++ 17 modunda büyüktür türleri ayrılması düzgün bir şekilde işler.  Örneğin, 16 veya 32 baytlık hizalama nesneleriyle vektörlerinin şimdi düzgün için SSE hizalanır / AVX yönergeler.


## <a name="other-libraries"></a>Diğer kitaplıkları

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği  
Vcpkg alınırken ve açık kaynak C++ statik kitaplıklar ve DLL'ler Visual Studio'da oluşturma işleminin büyük ölçüde kolaylaştıran bir açık kaynak komut satırı aracıdır. Daha fazla bilgi için bkz: [vcpkg: C++ için bir paket Yöneticisi](vcpkg.md).

**Visual Studio 2017 sürüm 15,5** 

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0  
C++ için platformlar arası web API'si CPPRestSDK 2.9.0 sürümüne güncelleştirildi. Daha fazla bilgi için bkz: [CppRestSDK 2.9.0 Github'da kullanılabilir](https://blogs.msdn.microsoft.com/vcblog/2016/10/21/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL
* Henüz başka bir ad arama uygunluk düzeltmeleri kümesi
* Taşıma oluşturucuları var ve atama işleçleri şimdi düzgün olarak atma olmayan işaretlenmiş taşıma
* Kaydını bastırmak geçerli C4640 hakkında uyarı atlstr.h içinde yerel istatistikleri, iş parçacığı güvenli başlatma
* İş parçacığı güvenli başlatma yerel İstatistikleri otomatik olarak devre dışı XP araç takımında yer olduğunda [ATL DLL oluşturma ve kullanma]. Bu durum artık geçerli değildir. İş parçacığı güvenli başlatmanın kapalı olması isteniyorsa Proje ayarlarınıza /Zc:threadSafeInit- ekleyebilirsiniz. 

### <a name="visual-c-runtime"></a>Visual C++ çalışma zamanı
* Yeni üstbilgi denetim akışı koruma sembolleri "cfguard.h". 

## <a name="c-ide"></a>C++ IDE

* Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Artık bir çözüm yapılandırması ilk defa etkinleştirildiğinde daha hızlı çalışır ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında gerçekleşir.

**Visual Studio 2017 sürüm 15.3**:
* Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
* **Sınıf ekleme** şimdi sınıfı Ekle Sihirbazı'nı doğrudan başlatır. Öğelerin tümünü olan diğer daha önce burada şu anda kullanılabilir durumda altında **Ekle > Yeni öğe**.
* Win32 Proje yoksa artık Windows Masaüstü kategorisi altında **yeni proje** iletişim.
* Windows Konsolu ve Masaüstü Uygulaması şablonları artık, bir sihirbaz görüntülemeden proje oluşturuyor. Aynı kategori altında, öncekiyle aynı seçenekleri görüntüleyen yeni bir Windows Masaüstü Sihirbazı var.

**Visual Studio 2017 sürüm 15,5**: için yeniden düzenleme ve kod gezintisi IntelliSense Altyapısı'nı kullanan birkaç C++ işlemleri çok daha hızlı çalıştırın. Şu sayıları 3500 projeleri Visual Studio Chromium çözümüyle dayanır: 
|||
|-|-|
|Özellik|Performansı geliştirme| 
|Rename|5.3 x| 
|Değişiklik imza |4.5 x| 
|Tüm Başvuruları Bul|4.7 x| 

 
 
C++ artık Ctrl + Click GoTo tanımı, fare Gezinti tanımlarına kolaylaşır destekler. Üretkenlik Güç Araçları Paketi yapısı Görselleştirici şimdi de ürünün varsayılan olarak bulunmaktadır.

## <a name="intellisense"></a>IntelliSense  
Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Bu, Tanıma Git ve Tüm Başvuruları Bul gibi veritabanı işlemlerini hızlandıracak ve ilk çözüm ayrıştırma süresini önemli ölçüde geliştirecektir. Ayar taşındı **Araçlar | Seçenekleri | Metin Düzenleyici | C/C++ | Gelişmiş** (önceki adıyla altında olduğu... C/C++ | Deneysel).

* Biz projelerinde IntelliSense performansı geliştirildi ve önceden derlenmiş üstbilgi dosyaları kullanmıyorsa - otomatik önceden derlenmiş üst bilgi üstbilgilerinin geçerli dosyasında oluşturulur.

* Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Filtrelenmiş Hata Listesi](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

* Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye Listesi Filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

* Üye Listesi’nde görünenleri bağlama duyarlı olarak filtreleyen yeni bir deneysel Tahmine Dayalı IntelliSense özelliği eklendi. Bkz: [C++ IntelliSense geliştirmeleri - Tahmine dayalı IntelliSense & filtreleme](https://blogs.msdn.microsoft.com/vcblog/2016/10/05/c-intellisense-improvements-predictive-intellisense-filtering/)

* Daha karmaşık içinde kolayca, almak yardımcı olarak kullanılabilecek kod temeli şimdi tüm başvurular (Shift + F12) bulun. Filtreleme, sıralama, arama sonuçları içindeki ve (bazı diller için) Gelişmiş gruplandırma sağlar, başvuruları NET bir anlayış sınıflandırıp renklendirme. C++ için yeni kullanıcı arabirimini olup olmadığını biz okuma veya yazma için bir değişken hakkında bilgi içerir.

* Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Yine deneme sürecinde olan Düzenleyici özellikleri Kapsamları Genişletme ve Önceliği Genişletme de gelişmiş hale gelmiştir.

* Deneysel yeniden düzenleme özellikleri İmzayı Değiştirme ve İşlevi Ayıklama, artık varsayılan olarak kullanılabilir.

* C++ Deneysel özelliği 'Hızlı Proje yük' projeleri. Artık açtığınız C++ projesi daha hızlı yüklenir. Aynı projeyi daha sonra tekrar açtığınızda çok daha hızlı yüklenir!

Bu özelliklerden bazıları diğer diller için ortaktır ve C++ için belirli bazılarıdır. Bu yeni özellikler hakkında daha fazla bilgi için bkz: [tanışın Visual Studio "15"](https://blogs.msdn.microsoft.com/visualstudio/2016/10/05/announcing-visual-studio-15-preview-5/). 


## <a name="non-msbuild-projects-with-open-folder"></a>Klasör Aç sahip olmayan MSBuild projeler
Visual Studio 2017, kod, derleme ve herhangi bir çözüm veya projeleri oluşturmak zorunda kalmadan klasörü içeren kaynak kodu hatalarını ayıklama olanak tanıyan "Klasör Aç" özelliği sunmaktadır. Projenizi MSBuild tabanlı projesinde olmasa bile, Visual Studio ile çalışmaya başlamak daha kolay yapar. "İle Klasör Aç" anlama, düzenleme, derleme ve hata ayıklama sağlayan Visual Studio zaten MSBuild projelerine yetenekleri güçlü kodu erişin. Daha fazla bilgi için bkz: [Klasör Aç Visual C++ projelerinde](ide/non-msbuild-projects.md).

* Klasör Aç deneyimi geliştirmeleri. Bu json dosyaları deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json. 
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

**Visual Studio 2017 sürüm 15.3**: 
* Alternatif derleyicileri ve MinGW ve Cygwin gibi derleme ortamları için geliştirilmiş destek. Daha fazla bilgi için bkz: [kullanarak MinGW ve Visual C++ ve klasör Aç Cygwin](https://blogs.msdn.microsoft.com/vcblog/2017/07/19/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
* Genel tanımlamak için destek eklendi ve "CppProperties.json" ve "CMakeSettings.json" yapılandırma özel ortam değişkenleri. Bu ortam değişkenleri “launch.vs.json” içinde tanımlanan hata ayıklama yapılandırmaları ve “tasks.vs.json” içindeki görevler tarafından kullanılabilir. Daha fazla bilgi için bkz: [ortamınızı Visual C++ ve klasör Aç ile özelleştirme](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/customizing-your-environment-with-visual-c-and-open-folder/).
* Kolayca 64 bit platformları hedeflemesi yeteneği dahil olmak üzere CMake'nın Ninja Oluşturucu için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Klasör Aç üzerinden CMake desteği
Visual Studio 2017 CMake projeleri MSBuild proje dosyalarına (.vcxproj) dönüştürmeden kullanmaya yönelik destek sunar. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](ide/cmake-tools-for-visual-cpp.md). "İle Klasör Aç" CMake projeler açıldığında otomatik olarak ortamı düzenleme, derleme ve hata ayıklama C++ için yapılandırır.

* C++ IntelliSense, kök klasörde CppProperties.json dosyası oluşturmaya gerek kalmadan çalışır. Bunun yanı sıra kullanıcıların CMake ve CppProperties.json dosyalarıyla sağlanan yapılandırmalar arasında kolayca geçiş yapması için yeni bir açılır menü ekledik.

* CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![Cmake Klasör Aç](media/cmake_cpp.png "CMake Klasör Aç")

**Visual Studio 2017 sürüm 15.3**: CMake Ninja Oluşturucu için ek destek. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](ide/cmake-tools-for-visual-cpp.md).  

**Visual Studio 2017 sürüm 15,5**: Varolan CMake içeri aktarmak için eklenen destek önbelleğe alır. Daha fazla bilgi için bkz: [CMake Visual C++ projelerinde](ide/cmake-tools-for-visual-cpp.md).  

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme  
Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik.  Yükleyici kullanıcı arabiriminde bileşenler için listelenen yükleme boyutlarının doğru olmadığını ve toplam boyutu düşük gösterdiğini lütfen aklınızda bulundurun.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Önerilen (seçilen) “VC++ 2017 v141 araç takımı (x86, x64)” ve “Windows 10 SDK (10.0.14393)” bileşenlerinin yüklenmesi, bunun çalışmasını güvence altına alır. Gerekli araçlar yüklenmezse, projeler başarıyla oluşturulamaz ve sihirbaz yanıt vermemeye başlar.

**Visual Studio 2017 sürüm 15,5**: Visual C++ derleme Araçları (daha önce tek başına bir ürün kullanılabilir) olan artık Visual Studio yükleyicisi iş yükünü olarak dahil. Bu iş yükü yalnızca Visual Studio IDE yüklemeden C++ projeleri oluşturmak için gerekli Araçları'nı yükler. V140 ve v141 toolsets dahil edilir. V141 araç takımı, Visual Studio 2015'te sürüm 15,5 en son geliştirmeleri içerir. Daha fazla bilgi için bkz: [Visual Studio derleme araçları şimdi dahil VS2017 ve VS2015 MSVC Toolsets](https://blogs.msdn.microsoft.com/vcblog/2017/11/02/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/).

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirmesi  
Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.  

**Visual Studio 2017 sürüm 15.2**: platformlar arası yönelik geliştirmeler kod paylaşımı ve görselleştirme yazın. Daha fazla bilgi için bkz: [platformlar arası için Linux C++ geliştirmeleri kod paylaşımı ve yazın görselleştirme](https://blogs.msdn.microsoft.com/vcblog/2017/05/10/linux-cross-platform-and-type-visualization/).

**Visual Studio 2017 sürüm 15,5**:
1. Linux iş yükü sftp uzak Linux makineler dosyalar için alternatif olarak rsync için destek eklemiştir.  
2. Destek için ARM mikrodenetleyici hedefleme derleme eklenir. Etkinleştirmek için bu yüklemeyi C++ iş yükü ve katıştırılmış seçeneği ile Linux geliştirme ve IOT geliştirme seçin. Bu seçenek, derleme araçlarını çapraz ARM GCC ve marka yüklemenize ekler. Daha fazla bilgi için bkz: [arası ARM GCC derleme Visual Studio'da](https://blogs.msdn.microsoft.com/vcblog/2017/10/23/arm-gcc-cross-compilation-in-visual-studio/).
3. Destek CMake için eklenmiştir. Varolan CMake kodunuz üzerinde temel bir Visual Studio projesi dönüştürmek zorunda kalmadan şimdi çalışabilir. Daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma](linux/cmake-linux-project.md).
4. Destek uzak görevleri çalıştırmak için eklenmiştir. Bu özellik, Visual Studio'nun Bağlantı Yöneticisi'nde tanımlı bir uzak sistemde herhangi bir komut çalıştırmanızı sağlar. Uzak görevler, dosyaları uzak sisteme kopyalama olanağı da sağlar. 


## <a name="game-development-with-c"></a>C++ ile oyun geliştirme  
C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.  

## <a name="mobile-development-with-c-android-and-ios"></a>C++ (Android ve iOS) ile Mobil Geliştirme  
Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.  

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları  
C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017’de v140 hedefli bir UWP projesi açtığınızda, sisteminizde Visual Studio 2015 yüklü değilse proje özelliği sayfalarından v141 platformu araç kümesini seçmeniz gerekiyor.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>C++ için yeni seçenekler Evrensel Windows Platformu (UWP) üzerinde
Artık yazma ve C++ Evrensel Windows platformu ve Windows mağazası uygulamalarını paketleme için yeni seçenekler vardır: Varolan Masaüstü uygulamanızı Windows mağazası yoluyla dağıtılmak paketlemek için masaüstü uygulaması dönüştürücü kullanabilirsiniz. Daha fazla bilgi için bkz: [kullanarak Visual C++ çalışma zamanı Centennial projesinde](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project/) ve [Masaüstü uygulamanız için evrensel Windows Platformu (UWP) Masaüstü Köprüsü ile Getir](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

**Visual Studio 2017 sürüm 15,5**  
A **Windows Uygulama paketleme projesi** proje şablonu, Masaüstü uygulamaları, Masaüstü köprüsü kullanarak paketleme destekleyen eklenir. Altında kullanılabilir **dosya | Yeni | Proje | Yüklü | Visual C++ | Evrensel Windows platformu**.

Yeni kod yazarken, artık C + kullanabilirsiniz +/ WinRT, standart bir C++ dili projeksiyonu yalnızca üstbilgi dosyalarında uygulanan Windows çalışma zamanı için. Her iki Yazar sağlar ve Windows çalışma zamanı standartlarıyla uyumlu tüm C++ derleyicisi kullanarak API'larını kullanabilir. C + +/ WinRT C++ geliştiricilerin modern Windows API için birinci sınıf erişimi sağlamak için tasarlanmıştır. Daha fazla bilgi için bkz: [C + +/ WinRT Github'da](https://moderncpp.com/). 

Sürümünden başlayarak [17025 Windows SDK Insider Önizleme yapı](https://blogs.windows.com/buildingapps/2017/11/01/windows-10-sdk-preview-build-17025/#ryPH3zAy6yk2cIRX.97), C + +/ WinRT Windows SDK'da yer almaktadır. Daha fazla bilgi için bkz: [C + +/ WinRT olan artık Windows SDK'sını dahil](https://blogs.msdn.microsoft.com/vcblog/2017/11/01/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı
İle birlikte Clang/C2 araç [!INCLUDE[vs_dev15_md](misc/includes/vs_dev15_md.md)] artık büyük projeler oluşturma açısından kritik önem taşıyan/bigobj anahtarını destekler. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ kod çözümleme

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Projenin özellik sayfalarındaki Kod Analizi Uzantıları iletişim kutusundan denetleyicileri etkinleştirmeniz yeterlidir, böylece kod analizini çalıştırdığınızda uzantılar dahil edilir. Daha fazla bilgi için bkz: [C++ çekirdek yönergeleri denetleyicileri kullanarak](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikler sayfası") 

**Visual Studio 2017 sürüm 15.3**: kaynak yönetimiyle ilgili kuralları için ek destek. 

**Visual Studio 2017 sürüm 15,5**: yeni bir C++ çekirdek Kılavuzu denetimleri kapak akıllı işaretçi doğruluk, doğru kullanımı genel başlatıcıları ve yapıları gibi bayrak kullanımlarını `goto` ve hatalı atamaları.  
Bazı uyarı numaralarını 15.3 içinde bulabilirsiniz, artık 15,5 içinde kullanılabilir. Bu uyarılar daha belirli denetimleri ile değiştirilmiştir.

## <a name="unit-testing"></a>Birim testi

**Visual Studio 2017 sürüm 15,5**: Google Test bağdaştırıcısı ve Boost.Test bağdaştırıcısı şimdi bileşenleri olarak kullanılabilir **C++ ile masaüstü geliştirme** ve ile tümleşik **Test Gezgini**. CTest desteği (Klasör Aç kullanarak) Cmake projeleri için eklenir, ancak ile tam tümleştirme **Test Gezgini** henüz kullanılabilir değil. Daha fazla bilgi için bkz: [C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio grafik Tanılama, kaydetme ve Direct3D uygulamalar oluşturma ve performans sorunları çözümlemek için araç kümesidir. Grafik tanılama özellikleri, Windows bilgisayarınızdaki bir Windows aygıt benzeticisi veya bir uzak bilgisayar veya cihaz üzerinde yerel olarak çalışan uygulamalar ile kullanılabilir.

* **Giriş ve çıkış köşe ve geometri gölgelendiriciler için:** giriş ve çıkış köşe gölgelendiriciler ve geometri gölgelendiriciler görüntüleme olanağı en çok istenen özelliklerden biri olmuştur ve araçları artık desteklenmektedir. Yalnızca kendi giriş inceleniyor başlatmak için ardışık düzen aşamaları görünümünde VS veya GS aşamayı seçin ve aşağıdaki tabloda çıktı.

  ![Giriş/Çıkış gölgelendiriciler için](media/io-shaders.png)

* **Arama ve filtreleme nesne tablosundaki:** sunar kaynaklarını bulmak için hızlı ve kolay bir yol aradığınız.

  ![Ara](media/search.png)
   
* **Kaynak geçmişi:** bu yeni görünüm, yakalanan çerçeve işleme sırasında kullanılan gibi bir kaynak tüm değişiklik geçmişini görmesini bir kolaylaştırılmış bir yolunu sunar. Herhangi bir kaynak için geçmiş çağırmak için herhangi bir kaynak köprüye yanındaki saati simgesine tıklamanız yeterlidir.

  ![Kaynak geçmişi](media/resource-history.png)

  Bu kaynak değişiklik geçmişi ile doldurulan yeni kaynak geçmiş araç penceresi görüntülenir.

  ![Kaynak geçmiş değişikliği](media/resource-history-change.png)

  Çerçevenizi tam çağrı yığını yakalama etkin yakalandıysa unutmayın (**Visual Studio | Araçlar | Seçenekleri | Grafik tanılama**), her değişiklik olayı bağlamında kullanılabilir hızla anlaşılan ve Visual Studio projesi içinde Denetlenmekte sonra.  

* **API istatistikleri:** , çerçevede API kullanımı üst düzey bir özetini görüntüleyin. Bu, hiç değişiklik yapıyorsunuz bilmiyor olabilirler çağrıları ya da çok fazla kuran çağrıları keşfetme de kullanışlı olabilir. Bu pencere aracılığıyla kullanılabilir **View | API istatistikleri** Visual Studio grafik Çözümleyicisi.

  ![API istatistikleri](media/api-stats.png)

* **Bellek istatistikleri:** çerçevede oluşturduğunuz sürücü için kaynakları ayırma ne kadar bellek görüntüleyin. Bu pencere aracılığıyla kullanılabilir **View | Bellek istatistikleri** içinde **Visual Studio grafik Çözümleyicisi**. Veri kopyalanabileceği bir elektronik tabloda görüntülemek için bir CSV dosyasına sağ tıklayarak ve seçme **Tümünü Kopyala**.

  ![Bellek istatistiği](media/memory-stats.png)
 
* **Çerçeve doğrulaması:** yeni hataları ve Uyarıları listesi Direct3D hata ayıklama katman tarafından algılanan olası sorunları göre olay listenize gitmek için kolay bir yol sağlar. Tıklatın **View | Çerçeve doğrulama** , Visual Studio grafik Çözümleyicisi aygıtını penceresini açın. Ardından **doğrulama çalışması** analiz başlatmak için. Çerçeve karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)
 
* **Çerçeve analizi için D3D12:** ile çizim çağrısı performansını çözümlemek için kullanım çerçeve analizi yönlendirilmiş "what-if" denemeler. Çerçeve analizi sekmesine geçin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için izleme [GoingNative 25: Visual Studio Grafik Çerçeve Çözümlemesi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) video.

  ![Çerçeve analizi](media/frame-analysis.png)

* **GPU kullanımı iyileştirmeleri:** GPU görünümü ya da Windows Performans Çözümleyicisi (WPA) aracını ile Visual Studio GPU kullanım profil oluşturucu aracılığıyla daha ayrıntılı çözümleme için gerçekleştirilecek izlemeleri açın. Varsa, Windows Performans Araç Seti yüklü WPA, diğeri GPU görünümünde, sağ alt köşesindeki oturum genel bakış için iki köprüler olacaktır.

  ![GPU kullanımı](media/gpu-usage.png)
 
  Bu bağlantı destek GPU görünümünde açılan izlemeleri yakınlaştırma ve zaman çizelgesi VS ve GPU görünümü arasında kaydırma eşitlendi. Vs'de bir onay kutusu eşitleme veya etkin olup olmadığını denetlemek için kullanılır. 

  ![GPU görünümü](media/gpu-view.png) 


