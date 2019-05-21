---
title: Visual Studio 2019'teki c++ yenilikleri
ms.date: 05/13/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 19eaa9d4ed1cf12e721825f998fa674363eda488
ms.sourcegitcommit: 61121faf879cc581a4d39e4baccabf7cf1f673a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/20/2019
ms.locfileid: "65934128"
---
# <a name="whats-new-for-c-in-visual-studio-2019"></a>Visual Studio 2019'teki c++ yenilikleri

Visual Studio 2019 birçok güncelleştirme ve Microsoft C++ ortamına giderir. Düzelttik birçok hatalar ve sorunlar derleyici ve araçları, çoğu aracılığıyla müşteriler tarafından gönderilen [sorun bildir](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) ve [bir öneride](https://developercommunity.visualstudio.com/spaces/62/index.html) altında seçenekleri **geri bildirim gönder**. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio'nun tüm yenilikler hakkında daha fazla bilgi için ziyaret [Visual Studio'daki yenilikler](/visualstudio/ide/whats-new-visual-studio-2019).

## <a name="c-compiler"></a>C++ derleyicisi

- C ++ 17 özellikleri ve doğruluk düzeltmeleri için gelişmiş destek, ayrıca C ++ 20 özellikleri gibi modülleri ve eş yordamlar için Deneysel destek. Ayrıntılı bilgi için bkz. [Visual Studio 2019'deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements.md).

- `/std:c++latest` Seçeneği artık ilk destekler ve C ++ 20 işleci mutlaka tam olmayan C ++ 20 özellikleri içerir \<= > ("savaş Gemisi") için üç yönlü karşılaştırma.

- C++ derleyici anahtarı `/Gm` kullanım dışı bırakıldı. Devre dışı bırakmayı deneyin `/Gm` açıkça tanımlanmış olması durumunda derleme betiklerinizde geçin. Ancak, aynı zamanda için kullanımdan kaldırılma uyarısı yok sayabilirsiniz `/Gm`, hata olarak "uyarıları hata olarak değerlendir" kullanırken işlenmez çünkü (`/WX`).

- MSVC C ++ 20 standart taslak altında özelliklerini uygulama başladığında `/std:c++latest` bayrak `/std:c++latest` artık uyumlu olmayan `/clr` (tüm özellikleri) `/ZW`, ve `/Gm`. Visual Studio 2019 ' kullanmak `/std:c++17` veya `/std:c++14` ile derleme yaparken modları `/clr`, `/ZW` veya `/Gm` (ancak önceki madde işaretinde bakın).

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Gelişmiş analiz ile `/Qspectre` değişken 1 (CVE-2017-5753) Spectre risk azaltma Yardım sağlamak için. Daha fazla bilgi için [Spectre azaltmaları MSVC içinde](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>C++ Standart Kitaplığı geliştirmeleri

- Ek C ++ 17 ve C ++ 20 kitaplığı özellikleri ve doğruluk uygulaması düzeltir. Ayrıntılı bilgi için bkz. [Visual Studio 2019'deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements.md).

- Clang-Format uygulandıktan C++ geliştirilmiş okunabilirlik için standart kitaplık üstbilgi.

- Visual Studio artık için sadece benim kodumu desteklediğinden C++, standart kitaplık artık için özel makine sağlaması gerekir `std::function` ve `std::visit` aynı etkiyi elde etmek için. Bu makine büyük ölçüde kaldırma olduğunu herhangi bir kullanıcıya görünen etkisi derleyici artık satırında 15732480 veya 16707566, sorunların belirtisi tanılama üretecektir dışında \<type_traits > veya \<değişken >.

## <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Performans/aktarım hızı geliştirmeleri derleyici ve standart kitaplığı

- Derleme Bağlayıcı dosya g/ç işleme dahil olmak üzere, aktarım hızı geliştirmeleri ve PDB birleştirme türü ve oluşturma zamanında bağlayabilirsiniz.

- OpenMP SIMD vektörleştirme için temel desteği eklendi. Yeni derleyici anahtarını kullanarak etkinleştirebilirsiniz `-openmp:experimental`. Bu seçenek ile açıklanan döngüler tanır `#pragma omp simd` potansiyel olarak vektörleştirildi için. Vektörleştirme garanti yoktur ve açıklamalı ancak getirilmemiş döngüleri bildirilen bir uyarı alırsınız. Hiçbir SIMD yan tümceleri desteklenir, bunlar yalnızca bildirilen bir uyarıyla göz.

- Yeni bir satır içi komut satırı anahtarı eklenen `-Ob3`, daha agresif bir sürümü olduğu `-Ob2`. `-O2` (ikili hız için İyileştir) hala gelir `-Ob2` varsayılan olarak. Derleyicinin satır içi kadar agresif değil bulursanız, geçirme göz önünde bulundurun `-O2 -Ob3`.

- Döngüler matematik kitaplığı işlevi ve Tamsayı bölme gibi diğer bazı işlem çağrıları ile elle vektörleştirme desteklemek için kısa vektör/matematik kitaplığı (SVML) iç işlevleri için destek ekledik. Bu işlevler, vektör 128-bit, 256 bit veya 512-bit eşdeğerleri işlem. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - Float hem tamsayı formları için yapı içleri sabiti Katlama ve aritmetik basitleştirme SIMD kullanarak ifadeler için vektör.

  - Her zaman true veya false olarak kanıtlanmış dalları kaldırmak için denetim akışı (if/else/switch deyimleri) bilgi ayıklamak için daha güçlü analiz.

  - Memset SSE2 vektör yönergelerini kullanmanız döngülerin Gelişmiş.

  - Gereksiz struct/class geliştirilmiş kaldırılmasını özellikle değişkeni değer olarak C++ programları için kopyalar.

  - Geliştirilmiş kod kullanmanın en iyi duruma getirme `memmove`, gibi `std::copy` veya `std::vector` ve `std::string` oluşturma.

- Standart kitaplık bölümlerini derleme değil önlemek için standart kitaplık fiziksel tasarım en iyi duruma getirilmiş # yarım derleme zamanında yalnızca içeren boş bir dosya kesme #include \<vektör >. Bu değişikliğin ardından eklemek gerekebilir #include daha önce dolaylı olarak dahil edilen üst bilgileri için. Örneğin, kullanan kod `std::out_of_range` artık gerekebilir #include \<stdexcept >. Bir akış ekleme operatörü kullanan kod artık gerekebilir #include \<ostream >. Yalnızca bu çeviri avantajdır gerçekten kullanarak birimlerini \<stdexcept > veya \<ostream > bileşenleri, bunları derlemek için maliyet aktarım hızı ödeme yaparsınız.

- `if constexpr` Daha fazla yerde iyi aktarım hızı ve kopyalama işlemleri, ters ve döndürme gibi permütasyon ve paralel algoritmalar kitaplığı daha az kod boyutu standart Kitaplığı'nda uygulandı. 

- Standart kitaplık artık düzenlenmemeli `if constexpr` C ++ 14 modu bile, derleme sürelerini kısaltmak için.

- Çalışma zamanı dinamik bağlama artık algılama paralel algoritma kitaplığı için bir sayfanın tamamını işlevi işaretçisi dizi depolamak için kullanır. Bu bellek salt okunur işaretleme artık güvenlik nedenleriyle ilgili olarak kabul edilen.

- `std::thread`ın Oluşturucusu artık, iş parçacığının başlatılmasını bekler ve artık ekler işlevi çok sayıda katmanları çağrıları arasında temel C Kitaplığı `_beginthreadex` ve sağlanan çağrılabilir nesne. Daha önce `std::thread` 6 işlevler arasında put `_beginthreadex` ve yalnızca 3'e azalır sağlanan çağrılabilir nesne (2 biri olan yalnızca `std::invoke`). Bu da belirsiz zamanlama hatayı giderip burada `std::thread`'s oluşturucusu, sistem saati tam o anda değiştirdiyseniz vermemesi bir `std::thread` oluşturulurken.

- İçinde bir performans gerilemesi düzeltildi `std::hash` , uygularken sunduk `std::hash<std::filesystem::path>`.

- Standart kitaplık artık kullanır, çeşitli yerlerde yok ediciler yerine catch blokları doğruluk elde etmek için'ü tıklatın. Bu, daha iyi hata ayıklayıcı etkileşiminde sonuçlanır; Etkilenen konumlar standart kitaplıkta aracılığıyla throw özel durumlar, kendi özgün throw site yerine bizim rethrow durum olarak artık görünür. Tüm standart kitaplığı catch blokları kaldırıldı; MSVC sonraki sürümlerde azaltılmasına catch bloğu bekliyoruz.

- İçinde yetersiz codegen `std::bitset` neden bir noexcept içinde koşullu bir throw tarafından işlevi oluşturma yolu hesaba katacak şekilde tarafından düzeltildi.

- `std::list` Ve `std::unordered_*` ailesinin kullanılacağını hata ayıklama olmayan yineleyiciler dahili olarak daha fazla yerde.

- Birkaç `std::list` üyeleri listesi düğümleri mümkün olduğunda bunları yeniden ayırma ve serbest bırakma yerine yeniden değiştirildi. Örneğin, belirtilen bir `list<int>` , 3, çağrı boyutunu zaten `assign(4, 1729)` şimdi ilk 3 listesi düğümlerde tamsayılara üzerine ve yerine tüm 3 listesi düğüm ayırmasını kaldırma ve ardından 4'ü yeni ayırma düğüm listesi 1729, değeri olan bir yeni liste düğümüne Ayır s 1729 değerine sahip.

- Tüm standart kitaplık çağrıları `erase(begin(), end())` üzere değiştirilmiştir `clear()`.

- `std::vector` artık başlatır ve bazı durumlarda daha verimli bir şekilde öğelerini siler.

- Yapılan geliştirmeler `std::variant` daha iyileştirici kolay, daha iyi içinde elde edilen yapmak için oluşturulan kod. Satır içi kod ile çok daha iyi, artık `std::visit`.

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Canlı Paylaşım C++ desteği

[Paylaşım canlı](/visualstudio/liveshare/) C++, geliştiricilerin gerçek zamanlı olarak işbirliği yapmak için Visual Studio veya Visual Studio Code kullanarak artık desteklemektedir. Daha fazla bilgi için [Live Share C++ ile tanışın: Gerçek zamanlı paylaşım ve işbirliği](https://devblogs.microsoft.com/cppblog/cppliveshare/)

### <a name="intellicode-for-c"></a>Intellicode c++

Intellicode olan isteğe bağlı (bir iş yükü bileşeni 16.1 olarak eklenir) uzantısı, kendi kapsamlı eğitim ve kod Bağlamınızı tamamlama listenizin en üstünde kullanma olasılığı en koymak için kullanır. Genellikle listede aşağı kaydırarak gereksinimini ortadan kaldırabilirsiniz. C++ için Intellicode popüler kitaplıkları gibi standart Kitaplığı kullanıldığında çoğu Yardım sunar. Daha fazla bilgi için [AI-Assisted kod tamamlama önerileri gelir Intellicode aracılığıyla C++](https://devblogs.microsoft.com/cppblog/cppintellicode/).

### <a name="template-intellisense"></a>Şablon IntelliSense

**Şablon çubuğu** artık kullanan **Özet penceresinde** kalıcı bir pencere yerine kullanıcı Arabiriminde iç içe geçmiş Şablonları destekleyen ve herhangi bir varsayılan bağımsız değişken içine önceden doldurur **Özet penceresinde**. Daha fazla bilgi için [şablon IntelliSense geliştirmesi için Visual Studio 2019 Önizleme 2](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/). A **en son kullanılan** açılır menüde **şablon çubuğu** önceki örnek bağımsız değişkenleri kümesi arasında kolayca geçiş yapmanızı sağlar.

### <a name="new-start-window-experience"></a>Yeni başlangıç penceresi deneyimi

Son Projeler açmak için yeni başlangıç penceresi seçenekler yer alır IDE başlatma sırasında kaynak denetiminden kodunu kopyalama, yerel kod bir çözüm ya da klasör açmak veya yeni bir proje oluşturun. Yeni Proje iletişim kutusu arama ve filtrelenebilir bir deneyimi de bakımdan geçirildi.

### <a name="new-names-for-some-project-templates"></a>Bazı proje şablonları için yeni adlar

Birden çok proje şablonu adları ve açıklamaları içeren güncelleştirilmiş yeni proje iletişim kutusu uyacak şekilde değişiklik.

### <a name="various-productivity-improvements"></a>Çeşitli üretkenliğine yönelik geliştirmeler

Visual Studio 2019 kodlamayı daha kolay ve daha sezgisel hale getirmek yardımcı olacak aşağıdaki özellikleri içerir:

- Hızlı düzeltmeler için:
  - Eksik Ekle #include
  - Nullptr NULL
  - Eksik noktalı virgül Ekle
  - Eksik ad alanı veya kapsam çözümleme
  - Geçersiz yöneltme işlenenler değiştirin (\* için & ve & \*)
- Kapanış ayracı bekleyerek bir blok için hızlı bilgi
- Özet üst bilgi / kod dosyası
- Tanıma Git #include dosyayı açar

Daha fazla bilgi için [C++ üretkenlik geliştirmeleri Visual Studio 2019 Preview 2 sürümündeki](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/).

**Visual Studio 2019 16.1 sürümü**

### <a name="quickinfo-improvements"></a>Quickınfo'da geliştirmeleri

Hızlı bilgi araç ipucu artık semantik renklendirme, düzenleyicinin dikkate alır. Ayrıca yeni bir sahip **çevrimiçi Ara** vurgulanan kod yapısı hakkında daha fazla bilgi edinmek çevrimiçi belgeleri arar bağlantı. Kırmızı-kıvrımlı çizgilerle desenler oluşturmaları kodunu hızlı bilgi tarafından sağlanan bağlantıyı hatayı çevrimiçi arama yapar. Bu şekilde tarayıcınıza ileti yeniden gerekmez. Daha fazla bilgi için [Visual Studio 2019 hızlı bilgi iyileştirmeleri: Renklendirme ve çevrimiçi arama](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/).

### <a name="intellicode-available-in-c-workload"></a>Intellicode bulunan C++ iş yükü

Intellicode artık birlikte gelen bir isteğe bağlı bir bileşen olarak **ile masaüstü geliştirme C++**  iş yükü. Daha fazla bilgi için [geliştirilmiş C++ Intellicode artık Visual Studio 2019 ile birlikte gelen](https://devblogs.microsoft.com/cppblog/).

## <a name="cmake-support"></a>CMake desteği

- CMake 3.14 desteği

- Visual Studio artık CMakeGUI, özelleştirilmiş meta-derleme sistemleri veya cmake.exe kendilerini çağırma derleme betikleri gibi dış araçları tarafından oluşturulan mevcut CMake önbellekleri açabilirsiniz.

- IntelliSense performansı İyileştirildi.

- Yeni bir ayarları Düzenleyicisi CMakeSettings.json dosyayı elle düzenlemeye alternatif sağlar ve CMakeGUI ile bazı eşlik sağlar.

- Visual Studio sizin için yüklememizi ister Linux makinenizde CMake uyumlu bir sürümünün yüklü olmadığını ve değilse algılayarak Linux'ta CMake ile C++ geliştirme sunar önyükleme yardımcı olur.

- CMakeSettings, uyumsuz ayarları eşleşmeyen mimariler veya uyumsuz CMake Oluşturucu ayarları gibi dalgalı çizgiler JSON Düzenleyicisi, hata listesinde hatalar gösterir.

- `vcpkg integrate install` çalıştırıldıktan sonra IDE'de açılmış olan CMake projeleri için vcpkg araç zinciri otomatik olarak algılanıyor ve etkinleştiriliyor. Bu davranış, CMakeSettings'de boş bir araç zinciri dosyası belirtilerek kapatılabilir.

- CMake projeleri artık varsayılan olarak Yalnızca Kendi Kodum hata ayıklamasını etkinleştiriyor.

- CMake projelerinde statik analiz uyarıları şimdi arka planda işlenebiliyor ve düzenleyicide görüntülenebiliyor.

- Daha açık derleme ve 'begin' ve 'end' iletileri için CMake projeleri ve Visual Studio'nun derlemenizin ilerleme durumunu UI desteği yapılandırın. Ayrıca, artık CMake ayrıntı düzeyi ayarından alanında var. **Araçlar > Seçenekler** CMake derleme ve yapılandırma iletilerinin çıkış penceresinde ayrıntı düzeyi özelleştirmek için.

- `cmakeToolchain` Ayarı CMakeSettings.json araç zincirlerinden CMake komut satırı değiştirmeden el ile belirtmek için artık desteklenmektedir.

- Yeni bir **yapı tüm** menüsü kısayolundan **Ctrl + Shift + B**.

**Visual Studio 2019 16.1 sürümü**

- Düzenleme, derleme ve hata ayıklama ile Clang/LLVM CMake projeleri için tümleşik destek. Daha fazla bilgi için [Visual Studio'da Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/).

## <a name="linux-and-wsl"></a>Linux ve WSL

**Visual Studio 2019 16.1 sürümü**

- Destek [AddressSanitizer (IsObject)](https://github.com/google/sanitizers/wiki/AddressSanitizer) Linux ve CMake platformlar arası projelerinde. Daha fazla bilgi için [AddressSanitizer (IsObject) Visual Studio 2019 Linux iş yükü için](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/).

- Tümleşik Visual Studio kullanma desteği C++ Linux (WSL) için Windows alt sistemi ile. Daha fazla bilgi için [ C++ Visual Studio 2019 ve Windows alt sistemi için Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

## <a name="incredibuild-integration"></a>IncrediBuild tümleştirme

İsteğe bağlı olarak IncrediBuild dahildir **ile masaüstü geliştirme C++**  iş yükü. IncrediBuild yapı izleme, Visual Studio IDE içinde tamamen tümleşiktir. Daha fazla bilgi için [IncrediBuild'ın yapı İzleyici ve Visual Studio 2019 yapı görselleştirme](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/).
 
## <a name="debugging"></a>Hata Ayıklama

- Windows üzerinde çalışan C++ uygulamaları için PDB dosyalarını ayrı bir 64 bit işlemde şimdi yükleyin. Bu değişiklik, bir dizi kilitlenme nedeniyle bellek yetersiz sayıda modüller ve PDB dosyaları içeren uygulamalar hata ayıklama sırasında çalışan hata ayıklayıcı tarafından yöneliktir.

- Arama etkin **Watch**, **Otolar**, ve **Yereller** windows.

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme

- Bu C++ ATL/MFC sihirbazları artık kullanılabilir:

  - ATL COM + 1.0 bileşeni Sihirbazı
  - ATL Active Server Pages bileşeni Sihirbazı
  - ATL OLE DB sağlayıcısı Sihirbazı
  - ATL Özellik Sayfası Sihirbazı
  - ATL OLE DB Tüketicisi Sihirbazı
  - MFC ODBC Tüketicisi
  - ActiveX denetiminden MFC sınıfı
  - Tür kitaplığı kitaplığından MFC sınıfı.

  Bu teknolojiler için örnek kod Microsoft Docs ve VCSamples GitHub deposunu arşivlenir.

- Windows 8.1 SDK'sı artık Visual Studio yükleyicisinde sağlanmıyor. C++ projelerinizin en son Windows 10 SDK'sı için yükseltmeniz önerilir. 8.1 sabit bir bağımlılık varsa, Windows SDK'sı arşivden indirebilirsiniz.

- En son C++ araç takımında artık Windows XP hedeflemesi sağlanmıyor. VS 2017 düzeyi MSVC derleyici ve kitaplıkları ile XP hedefleyen hala desteklenmektedir ve "Tek tek bileşenler" yüklenebilir

- Belgelerimizde şu anda Visual C++ Çalışma Zamanı dağıtımı için Modülleri Birleştirme kullanımı hiç önerilmiyor. Bizim MSMs kullanım dışı bırakıldı olarak işaretlemek, bu sürüm sizi fazladan adım yönlendiriyoruz. VCRuntime merkezi dağıtımınızı MSM'lerden yeniden dağıtılabilir pakete geçirmeyi göz önünde bulundurun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ (Android ve iOS) ile Mobil Geliştirme

C++ Android deneyimi artık varsayılan olarak Android SDK 25 ve Android NDK 16b olur.

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Clang/C2 Deneysel bileşeni kaldırıldı. MSVC araç takımı ile tam C++ standartlarına uyum kullanmak `/permissive-` ve `/std:c++17`, veya Windows için Clang/LLVM araç zinciri.

## <a name="code-analysis"></a>Kod Analizi

- Kod analizi artık otomatik olarak arka planda çalıştırılıyor. Siz yazdıkça düzenleyicinin içinde uyarılar yeşil dalgalı çizgilerle gösteriliyor. Daha fazla bilgi için [Düzenleyici içinde kod analizi Visual Studio 2019 Preview 2 sürümündeki](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/).

- İyi bilinen standart kitaplık türleri için yeni Deneysel ConcurrencyCheck kuralları \<mutex > Üstbilgi. Daha fazla bilgi için [Visual Studio 2019 eşzamanlılık Kod Analizi](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/).

- Güncelleştirilmiş kısmi uygulaması [ömür profili denetleyicisi](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/), Sallantıdaki işaretçileri ve başvuruları algılar. Daha fazla bilgi için [ömür profili güncelleştirme Visual Studio 2019 Preview 2 sürümündeki](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/).

- C26138, C26810 C26811 ve Deneysel kural C26800 dahil olmak üzere daha fazla eş yordam ilgili denetimleri. Daha fazla bilgi için [yeni kod analizi iade Visual Studio 2019: taşıma sonra kullanın ve eş yordam](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/).

**Visual Studio 2019 16.1 sürümü**

Yeni Hızlı düzeltmeler için değişken denetimleri başlatılmamış. Daha fazla bilgi için [başlatılmamış belleği (C6001) ve init (C26494) uyarıları kullanılabilmesi için yeni kod analizi hızlı düzeltmeler](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/).

## <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Yönetilen C++ Test Çerçevesi mevcut projelerinizi kullanmaya devam edebilirsiniz. Yeni birim testleri için Visual Studio sağlayan şablonlar (MSTest, Google Test) ya da yönetilen yerel test çerçevelerini kullanarak göz önünde bulundurun C# Test proje şablonu.
