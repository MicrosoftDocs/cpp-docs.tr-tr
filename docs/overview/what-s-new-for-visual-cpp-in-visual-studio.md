---
title: Visual Studio 2017’deki C++ yenilikleri
ms.date: 07/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
ms.openlocfilehash: 9b656d4e13fe241c22a9c555d1c597016c5353d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366815"
---
# <a name="whats-new-for-c-in-visual-studio"></a>Visual Studio 2017’deki C++ yenilikleri

::: moniker range=">=vs-2019"

Visual Studio 2019, Microsoft C++ ortamına birçok güncelleştirme ve düzeltme getiriyor. Derleyici ve araçlardaki birçok hatayı ve sorunları düzelttin. Bu sorunların çoğu, müşteriler tarafından [Bir Sorun Bildir](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019) ve **Geri Bildirim Gönder**altında Öneri seçenekleri [sağlayın](https://developercommunity.visualstudio.com/spaces/62/index.html) aracılığıyla gönderildi. Hataları bildirdiğiniz için teşekkür ederiz! Tüm Visual Studio'daki yenilikler hakkında daha fazla bilgi için [Visual Studio 2019'daki yenilikleri](/visualstudio/ide/whats-new-visual-studio-2019)ziyaret edin. Visual Studio 2017'de C++ için yenilikler hakkında bilgi için [Visual Studio 2017'de C++ için yeniliklere](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017)bakın. Visual Studio 2015 ve önceki sürümlerde C++ için yenilikler hakkında bilgi için [Visual C++ What's New 2003 ile 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)'e bakın.

## <a name="c-compiler"></a>C++ derleyicisi

- C++17 özellikleri ve doğruluk düzeltmeleri için geliştirilmiş destek ve modüller ve ortak yordamlar gibi C++20 özellikleri için deneysel destek. Ayrıntılı bilgi için Visual [Studio 2019'da C++ Uygunluk Geliştirmeleri'ne](cpp-conformance-improvements.md)bakın.

- Bu `/std:c++latest` seçenek, c++20 işleci \<=> ("uzay gemisi") için üç yönlü karşılaştırma için ilk destek de dahil olmak üzere, mutlaka tam olmayan C++20 özelliklerini içerir.

- C++ derleyici `/Gm` anahtarı artık amortismana hazır. Açıkça `/Gm` tanımlanmışsa, yapı komut dosyalarınızdaki anahtarı devre dışı bırakmayı düşünün. Ancak, "Uyarıları hata olarak ele alırken `/Gm`hata olarak kabul edilmediğinden" için amortisman uyarısını da`/WX`güvenle yok sayabilirsiniz.

- `/std:c++latest` MSVC bayrağın altında C++20 standart taslak özellikleri `/std:c++latest` uygulamaya başlar gibi, şimdi (tüm tatlar) ile `/clr` uyumsuz, `/ZW`ve `/Gm`. Visual `/std:c++17` Studio 2019'da `/std:c++14` , , `/clr` `/ZW`veya (önceki `/Gm` madde işaretini görmek) ile derlerken kullanın veya modları kullanın.

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, güvenlik, tanılama ve sürüm

Spectre Variant `/Qspectre` 1 (CVE-2017-5753) için azaltma yardımı sağlamak için geliştirilmiş analiz. Daha fazla bilgi için [MSVC'deki Spectre Azaltıcı Etkenler'e](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)bakın.

## <a name="c-standard-library-improvements"></a>C++ standart kitaplık iyileştirmeleri

- Ek C++17 ve C++20 kitaplık özelliklerinin ve doğruluk düzeltmelerinin uygulanması. Ayrıntılı bilgi için Visual [Studio 2019'da C++ Uygunluk Geliştirmeleri'ne](cpp-conformance-improvements.md)bakın.

- Clang-Format, daha iyi okunabilirlik için C++ standart kitaplık üstbilgilerine uygulanmıştır.

- Visual Studio artık C++için Just My Code'u desteklediği için, standart `std::function` `std::visit` kitaplığın artık aynı etkiyi elde etmek için özel makineler sağlaması na gerek yok. Bu makinenin çıkarılmasının büyük ölçüde kullanıcı tarafından görülebilen bir etkisi yoktur. Bir istisna derleyici artık satır 15732480 veya type_traits> veya \< \<varyant> 16707566 üzerinde sorunları gösteren tanılama üretecek olmasıdır.

## <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Derleyici ve standart kitaplıktaki performans/iş iş geliştirmeleri

- Bağlayıcının Dosya G/Ç'yi işleme şekli ve PDB türü birleştirme ve oluşturmada bağlantı süresi de dahil olmak üzere iş yaratma geliştirmeleri oluşturun.

- OpenMP SIMD vektörelleştirme için temel destek eklendi. Yeni derleyici anahtarını `-openmp:experimental`kullanarak etkinleştirebilirsiniz. Bu seçenek, açıklamalı döngülerin `#pragma omp simd` potansiyel olarak vektörelleştirilmesine olanak tanır. Vektörelleştirme garanti edilmez ve döngüler açıklamalı ancak vektörel olmayan bir uyarı bildirilir. SIMD yan tümceleri desteklenmez; bunlar göz ardı edilir ve bir uyarı bildirilir.

- Daha agresif bir versiyonu olan `-Ob3`yeni bir satır içi `-Ob2`komut satırı anahtarı eklendi. `-O2`(hız için ikili optimize) `-Ob2` hala varsayılan olarak ima eder. Derleyicinin yeterince agresif bir şekilde hizalamadığını fark ederseniz, geçmeyi `-O2 -Ob3`düşünün.

- Matematik kitaplığı işlevlerine yapılan çağrılar ve sonda bölümü gibi diğer bazı işlemlerle döngülerin el vektörelleştirilmesini desteklemek için, Kısa Vektör Matematik Kitaplığı (SVML) içsel işlevleri için destek ekledik. Bu işlevler 128 bit, 256-bit veya 512-bit vektör eşdeğerlerini hesaplar. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - SimD vektör içsellerini kullanan ifadeler için hem şamandıra hem de tamsayı formları için sürekli katlama ve aritmetik basitleştirmeler.

  - Her zaman doğru veya yanlış olduğu kanıtlanmış dalları kaldırmak için kontrol akışından (if/else/switch deyimleri) bilgi ayıklamak için daha güçlü bir analiz.

  - SSE2 vektör yönergelerini kullanmak için geliştirilmiş memset unrolling.

  - Özellikle değere göre geçen C++ programları için yararsız yapı/sınıf kopyalarının geliştirilmiş kaldırması.

  - `memmove`Kod kullanımının geliştirilmiş optimizasyonu `std::copy` , `std::vector` `std::string` gibi veya ve inşaat.

- Standart kitaplığın doğrudan dahil olmayan bölümlerini derlememek için standart kitaplık fiziksel tasarımı optimize edilmiştir. Bu değişiklik, yalnızca \<vektör> içeren boş bir dosyanın oluşturma süresini yarıya indirdi. Sonuç olarak, daha önce `#include` dolaylı olarak dahil edilmiş üstbilgi için yönergeler eklemeniz gerekebilir. Örneğin, kullanan `std::out_of_range` kodun artık ekleyebileceği `#include <stdexcept>`. Akış ekleme işleci kullanan kodun artık eklemesi `#include <ostream>`gerekebilir. Bunun yararı, yalnızca stdhariç> \<veya \<ostream> bileşenlerikullanan çeviri birimlerinin bunları derlemek için iş maliyeti ödemesidir.

- `if constexpr`kopya işlemlerinde gelişmiş iş ortası ve azaltılmış kod boyutu, ters çevirme ve döndürme gibi permütasyonlar ve paralel algoritmalar kitaplığında daha fazla yerde uygulanmıştır.

- Standart kitaplık artık `if constexpr` C++14 modunda bile derleme sürelerini azaltmak için dahili olarak kullanılır.

- Paralel algoritmalar kitaplığı için çalışma zamanı dinamik bağlantı algılaması artık işlev işaretçisi dizisini depolamak için tüm sayfayı kullanmaz. Bu bellek salt okunur işaretleme artık güvenlik amaçları için ilgili olarak kabul edildi.

- `std::thread`'nin oluşturucusu artık iş parçacığının başlamasını beklemez ve artık temel C kitaplığı `_beginthreadex` ile sağlanan çağrılabilir nesne arasında bu kadar çok işlev katmanı eklemez. Daha `std::thread` önce sadece `_beginthreadex` 3 (2'si sadece) `std::invoke`düşürüldü ve verilen çağrılabilir nesne arasında 6 işlevleri koymak. Bu değişiklik, sistem saati oluşturulduğu `std::thread` anda değiştirilirse bir oluşturucunun asıldığı belirsiz bir zamanlama hatasını `std::thread` da çözer.

- Uygularken sunduğumuz performans `std::hash` regresyonu düzeltildi. `std::hash<std::filesystem::path>`

- Standart kitaplık artık doğruluğa ulaşmak için çeşitli yerlerdeki blokları yakalamak yerine yıkıcılar kullanır. Bu değişiklik daha iyi hata ayıklama etkileşimi ile sonuçlanır: Etkilenen konumlardaki standart kitaplığı atdığınız özel durumlar, artık yeniden atmamız yerine orijinal atma sitelerinden atılmış gibi görünür. Tüm standart kitaplık yakalama blokları ortadan kaldırılmamamıştır; msvc'nin sonraki sürümlerinde yakalama bloklarının sayısının azaltılmasını bekliyoruz.

- Noexcept fonksiyonunun `std::bitset` içindeki koşullu bir fırlatmanın neden olduğu suboptimal codegen, fırlatma yolunun çarpanflanmasıyla düzeltildi.

- Ve `std::list` `std::unordered_*` aile daha fazla yerde dahili olarak hata ayıklama olmayan yinelemeler kullanın.

- Birkaç `std::list` üye, liste düğümlerini ayırmak ve yeniden ayırmak yerine mümkün olan yerlerde yeniden kullanmak üzere değiştirildi. Örneğin, zaten `list<int>` 3 boyutu olan bir çağrı verildiğinde, şimdi ilk 3 liste düğümlerinde ints üzerine yazmak için `assign(4, 1729)` bir çağrı ve değeri 1729 ile yeni bir liste düğümü ayırır.

- Tüm standart kitaplık `erase(begin(), end())` çağrıları `clear()`' na değiştirildi.

- `std::vector`şimdi bazı durumlarda öğeleri daha verimli bir şekilde başharfve siler.

- Daha optimize `std::variant` edici dostu hale getirmek için iyileştirmeler, daha iyi oluşturulan kod elde. Kod inlining şimdi çok `std::visit`daha iyi .

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Live Share C++ desteği

[Live Share](/visualstudio/liveshare/) artık C++'ı destekleyerek Visual Studio veya Visual Studio Code'u kullanan geliştiricilerin gerçek zamanlı olarak işbirliği yapmasına olanak sağlıyor. Daha fazla bilgi [için C++: Gerçek Zamanlı Paylaşım ve İşbirliği için Canlı Paylaşım Duyurusu'na](https://devblogs.microsoft.com/cppblog/cppliveshare/) bakın

### <a name="intellicode-for-c"></a>C++ için IntelliCode

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

IntelliCode, tamamlama listenizin en üstünde kullanabileceğiniz şeyi koymak için kendi kapsamlı eğitimini ve kod bağlamınızı kullanan isteğe bağlı bir uzantıdır. Genellikle listede aşağı kaydırma ihtiyacını ortadan kaldırabilir. C++'da IntelliCode, standart kitaplık gibi popüler kitaplıkları kullanırken en çok yardımı sağlar. Yükleyicide iş yükü bileşeni olarak kullanılabilir. Daha fazla bilgi için, [IntelliCode üzerinden C++'a Gel'e AI Destekli Kod Tamamlama Önerileri'ne](https://devblogs.microsoft.com/cppblog/cppintellicode/)bakın.

### <a name="template-intellisense"></a>Şablon IntelliSense

**Şablon Çubuğu** artık modal pencere yerine **Peek Pencere** Arabirimi'ni kullanır, iç içe olan şablonları destekler ve varsayılan bağımsız değişkenleri **Peek Penceresi'ne**önceden doldurur. Daha fazla bilgi için Visual [Studio 2019 Önizleme 2 için Şablon IntelliSense Geliştirmeleri'ne](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/)bakın. **Şablon Çubuğu'nda** **en son kullanılan** açılır bırakma, önceki örnek bağımsız değişken kümeleri arasında hızlı bir şekilde geçiş yapmanızı sağlar.

### <a name="new-start-window-experience"></a>Yeni Başlangıç penceresi deneyimi

IDE'yi başlatırken, yeni bir Başlat penceresi, son projeleri açmak, kaynak denetiminden kodu klonlama, yerel kodu çözüm veya klasör olarak açma veya yeni bir proje oluşturma seçenekleriyle birlikte görüntülenir. Yeni Proje iletişim kutusu, ilk arama yla ilgili, filtrelenebilir bir deneyime dönüştürülür.

### <a name="new-names-for-some-project-templates"></a>Bazı proje şablonları için yeni adlar

Güncelleştirilmiş Yeni Proje iletişim kutusuna uyacak şekilde birkaç proje şablonu adını ve açıklamasını değiştirdik.

### <a name="various-productivity-improvements"></a>Çeşitli verimlilik iyileştirmeleri

Visual Studio 2019, kodlamayı daha kolay ve sezgisel hale getirmeye yardımcı olacak aşağıdaki özellikleri içerir:

- Hızlı düzeltmeler:
  - Eksik #include ekle
  - NULL için nullptr
  - Eksik semicolon ekle
  - Eksik ad alanını veya kapsamı çözme
  - Kötü yönlendirme operands\* değiştirin ( \*& ve & için )
- Kapatma ayracında gezinmek için bir blok için Hızlı Bilgi
- Peek Üstbilgi / Kod Dosyası
- Dosyayı açar #include Tanım'a git

Daha fazla bilgi için Visual [Studio 2019 Önizleme 2'de C++ Verimlilik Geliştirmeleri'ne](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/)bakın.

### <a name="quickinfo-improvements"></a>QuickInfo iyileştirmeleri

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

Hızlı Bilgi araç ucu artık düzenleyicinizin anlamsal renklendirmeye saygı duyar. Ayrıca, havada gezinilen kod yapısı hakkında daha fazla bilgi edinmek için çevrimiçi dokümanlar arayacak yeni bir **Arama Çevrimiçi** bağlantısı vardır. Kırmızı dalgalı kod için, Hızlı Bilgi tarafından sağlanan bağlantı hata çevrimiçi arayacaktır. Bu şekilde iletiyi tarayıcınıza yeniden yazmanız gerekmez. Daha fazla bilgi için [Visual Studio 2019: Colorization and Search Online'da Hızlı Bilgi Geliştirmeleri'ne](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/)bakın.

### <a name="intellicode-available-in-c-workload"></a>IntelliCode C++ iş yükü nde kullanılabilir

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

IntelliCode artık C++ iş **yüküyle Masaüstü Geliştirme'de** isteğe bağlı bir bileşen olarak yer alıyor. Daha fazla bilgi için Visual [Studio 2019 ile Geliştirilmiş C++ IntelliCode now Ships for Visual Studio 2019'a](https://devblogs.microsoft.com/cppblog/improved-c-intellicode-now-ships-with-visual-studio-2019/)bakın.

## <a name="cmake-support"></a>CMake desteği

- CMake 3.14 desteği

- Visual Studio artık CMakeGUI, özelleştirilmiş meta-yapı sistemleri gibi harici araçlar tarafından oluşturulan mevcut CMake önbellekleri açabilir veya cmake.exe kendilerini çağırmak komut dosyaları oluşturabilirsiniz.

- Geliştirilmiş IntelliSense performansı.

- Yeni ayarlar düzenleyicisi CMakeSettings.json dosyasını el ile düzenlemeye bir alternatif sağlar ve CMakeGUI ile bazı parite sağlar.

- Visual Studio, Linux makinenizde uyumlu bir CMake sürümü olup olmadığını algılayarak Linux üzerinde CMake ile C++ geliştirmenizin önyüklemesine yardımcı oluyor. Uyumlu bir sürüm yoksa, sizin için yüklemeyi öneriyor.

- Uyumsuz mimariler veya uyumsuz CMake jeneratör ayarları gibi CMakeSettings uyumsuz ayarları, JSON düzenleyicisinde dalgalı ve hata listesindeki hataları gösterir.

- `vcpkg integrate install` çalıştırıldıktan sonra IDE'de açılmış olan CMake projeleri için vcpkg araç zinciri otomatik olarak algılanıyor ve etkinleştiriliyor. Bu davranış, CMakeSettings'de boş bir araç zinciri dosyası belirtilerek kapatılabilir.

- CMake projeleri artık varsayılan olarak Yalnızca Kendi Kodum hata ayıklamasını etkinleştiriyor.

- CMake projelerinde statik analiz uyarıları şimdi arka planda işlenebiliyor ve düzenleyicide görüntülenebiliyor.

- CMake projeleri için 'başlangıç' ve 'son' iletilerini daha net oluşturun ve yapılandırın ve Visual Studio'nun geliştirme ilerleme UI'si için destek olun. Ayrıca, Artık Araçlar > Seçenekleri'nde, Çıkış **Tools > Options** Penceresinde CMake yapı ve yapılandırma iletilerinin ayrıntı düzeyini özelleştirmek için bir CMake ayrıntılı ayar var.

- Ayar `cmakeToolchain` artık CMakeSettings.json'da cmake komut satırını el ile değiştirmeden araç zincirlerini belirtmek için desteklenir.

- Yeni Yapı **Tüm** menü kısayolu **Ctrl+Shift+B**.

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

- Clang/LLVM ile CMake projelerinin düzenlenmesi, oluşturulması ve hata ayıklanması için entegre destek. Daha fazla bilgi için [Visual Studio'da Clang/LLVM Desteği'ne](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/)bakın.

## <a name="linux-and-the-windows-subsystem-for-linux"></a>Linux ve Linux için Windows Alt Sistemi

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

- Linux ve CMake platform ötesi projelerde [AddressSanitizer (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) desteği. Daha fazla bilgi için [Visual Studio 2019'da Linux İş Yükü için AddressSanitizer (ASan)](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/)adresine bakın.

- Linux için Windows Alt Sistemi (WSL) ile C++ kullanmak için entegre Visual Studio desteği. Daha fazla bilgi için Visual [Studio 2019 ile C++ ve Linux için Windows Alt Sistemi (WSL) 'ye](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/)bakın.

## <a name="incredibuild-integration"></a>IncrediBuild tümleştirmesi

IncrediBuild, C++ iş **yüküyle Masaüstü geliştirmesinde** isteğe bağlı bir bileşen olarak eklenmiştir. IncrediBuild Build Monitor, Visual Studio IDE'ye tamamen entegre edilmiştir. Daha fazla bilgi için, [IncrediBuild'in Build Monitor ve Visual Studio 2019 ile yapınızı Görselleştir'e](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/)bakın.

## <a name="debugging"></a>Hata Ayıklama

- Windows'da çalışan C++ uygulamaları için PDB dosyaları artık ayrı bir 64 bit işlemde yüklenir. Bu değişiklik, çok sayıda modül ve PDB dosyası içeren uygulamaları hata ayıklarken hata ayıklamanın bellekten tükenmesinin neden olduğu çeşitli kilitlenmeleri giderır.

- **Arama, Watch,** **Autos**ve **Locals** pencerelerinde etkinleştirilir.

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows masaüstü geliştirme

- Bu C++ ATL/MFC sihirbazları artık kullanılamıyor:

  - ATL COM+ 1.0 Bileşeni Sihirbazı
  - ATL Etkin Sunucu Sayfaları Bileşen Sihirbazı
  - ATL OLE DB Sağlayıcısı Sihirbazı
  - ATL Özellik Sayfası Sihirbazı
  - ATL OLE DB Tüketicisi Sihirbazı
  - MFC ODBC Tüketici
  - ActiveX kontrolünden MFC sınıfı
  - Tip Lib'den MFC sınıfı.

  Bu teknolojilerin örnek kodu Microsoft Docs'ta ve VCSamples GitHub deposunda arşivlendi.

- Windows 8.1 SDK'sı artık Visual Studio yükleyicisinde sağlanmıyor. C++ projelerinizi en son Windows 10 SDK'ya yükseltmenizi öneririz. 8.1'e katı bir bağımlılığınız varsa, bunu Windows SDK arşivinden indirebilirsiniz.

- En son C++ araç takımında artık Windows XP hedeflemesi sağlanmıyor. VS 2017 düzeyindeMSVC derleyicisi ile XP hedeflemesi & kütüphaneleri hala destekleniyor ve "Tek tek bileşenler" üzerinden yüklenebilir.

- Belgelerimizde şu anda Visual C++ Çalışma Zamanı dağıtımı için Modülleri Birleştirme kullanımı hiç önerilmiyor. MSM'lerimizi küçümseyen olarak işaretlemenin ekstra bir adımını atıyoruz. VCRuntime merkezi dağıtımınızı MSM'lerden yeniden dağıtılabilir pakete geçirmeyi göz önünde bulundurun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ ile mobil geliştirme (Android ve iOS)

C++ Android deneyimi artık varsayılan olarak Android SDK 25 ve Android NDK 16b olur.

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç seti

Clang/C2 deneysel bileşeni kaldırıldı. MsVC araç kümesini tam C++ standartlarına `/std:c++17`uygunluk ve Windows için Clang/LLVM araç zinciri için `/permissive-` kullanın.

## <a name="code-analysis"></a>Kod analizi

- Kod analizi artık otomatik olarak arka planda çalıştırılıyor. Siz yazdıkça düzenleyicinin içinde uyarılar yeşil dalgalı çizgilerle gösteriliyor. Daha fazla bilgi için [Visual Studio 2019 Preview 2'deki Editör İçi kod analizine](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/)bakın.

- \<Mutex> üstbilgisinden iyi bilinen standart kitaplık türleri için yeni deneysel ConcurrencyCheck kuralları. Daha fazla bilgi için [Visual Studio 2019'da Eşzamanlılık Kod Analizi'ne](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/)bakın.

- Sarkan işaretçileri ve başvuruları algılayan [Ömür Boyu profil denetleyicisinin](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)güncelleştirilmiş kısmi uygulaması. Daha fazla bilgi için [Visual Studio 2019 Önizleme 2'de Yaşam Boyu Profil Güncellemesi'ne](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/)bakın.

- C26138, C26810, C26811 ve deneysel kural C26800 dahil olmak üzere daha fazla ortak kontrol. Daha fazla bilgi için [Visual Studio 2019'da Yeni Kod Analizi Denetimleri'ne bakın: taşıma sonrası ve birlikte yordam.](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/)

##### <a name="visual-studio-2019-version-161"></a> Visual Studio 2019 sürüm 16.1

- Başlatlanmamış değişken denetimleri için yeni hızlı düzeltmeler. Daha fazla bilgi için, [başlamayan bellek (C6001) için Yeni kod analizi hızlı düzeltmeleri ve init (C26494) uyarıları önce kullanın](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/)bakın.

## <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Varolan projelerinizde Yönetilen C++ Test çerçevesini kullanmaya devam edebilirsiniz. Yeni birim testleri için Visual Studio'nun şablon (MSTest, Google Test) veya Yönetilen C# Test Projesi şablonu sağladığı yerel test çerçevelerinden birini kullanmayı düşünün.

::: moniker-end

::: moniker range="=vs-2017"

Visual Studio 2017, C++ ortamına birçok güncelleme ve düzeltme getiriyor. Derleyici ve araçlarda 250'den fazla hata düzeltildik ve sorunları bildirdik, çoğu müşteriler tarafından [Bir Sorun Bildir ve](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2017) Geri Bildirim **Gönder**altında Öneri seçenekleri sağlayın yoluyla gönderildi. Hataları bildirdiğiniz için teşekkür ederiz! Tüm Visual Studio'daki yenilikler hakkında daha fazla bilgi için [Visual Studio 2017'deki yeniliklere](/visualstudio/ide/whats-new-visual-studio-2017?view=vs-2017)bakın. Visual Studio 2019'da C++ için yenilikler hakkında bilgi için [Visual Studio'da C++ için yeniliklere](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019)bakın. Visual Studio 2015 ve önceki sürümlerde C++ için yenilikler hakkında bilgi için [Visual C++ What's New 2003 ile 2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)'e bakın.

## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uygunluk iyileştirmeleri

Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için Visual [Studio 2017'de C++ Uygunluk Geliştirmeleri'ne](cpp-conformance-improvements.md)bakın.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Derleyici, yapılandırılmış bağlamalar, lambdas, `constexpr` `if constexpr`satır satır değişkenleri, kat ifadeleri ve tür sistemine ekleme `noexcept` dahil olmak üzere C++17'de yeni olan özelliklerin yaklaşık %75'ini destekler. Bu özellikler **/std:c++17** seçeneği altında mevcuttur. Daha fazla bilgi için Visual [Studio 2017'de C++ Uygunluk Geliştirmeleri](cpp-conformance-improvements.md)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

Visual Studio sürüm 15.7'deki MSVC derleyici araç seti artık C++ Standardına uygundur. Daha fazla bilgi için [bkz: Duyuru: MSVC C++ Standardına](https://devblogs.microsoft.com/cppblog/announcing-msvc-conforms-to-the-c-standard/) ve [Microsoft C++ Dil Uygunluğuna](../visual-cpp-language-conformance.md)Uygundur.

##### <a name="visual-studio-2017-version-158"></a>Visual Studio 2017 sürümü 15.8

[/experimental:preprocessor](../build/reference/experimental-preprocessor.md) derleyici anahtarı, geçerli tüm C ve C++ standartlarına uygun olacak yeni deneysel MSVC önişlemcisini etkinleştiri. Daha fazla bilgi için [MSVC deneysel ön işlemciye genel bakış adabına](../preprocessor/preprocessor-experimental-overview.md)bakın.

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [/izin-](../build/reference/permissive-standards-conformance.md): Tüm katı standartlara uygunluk derleyici seçeneklerini etkinleştirin ve Microsoft'a özgü `__declspec(dllimport)`derleyici uzantılarının çoğunu devre dışı edin (örneğin). Bu seçenek Varsayılan olarak Visual Studio 2017 sürüm 15.5'te açıktır.  **/izin verilen** uygunluk modu, iki aşamalı ad araması desteği içerir. Daha fazla bilgi için [Visual Studio'da C++ Uyumluluk Geliştirmeleri'ne](cpp-conformance-improvements.md)bakın.

- [/diagnostics](../build/reference/diagnostics-compiler-diagnostic-options.md): Satır numarasının, satır numarasının ve sütununun veya satır numarasının ve sütununun ve tanılama hatasının veya uyarısının bulunduğu kod satırının altındaki bir bakım

- [/debug:fastlink](../build/reference/debug-generate-debug-info.md): Tüm hata ayıklama bilgilerini PDB dosyasına kopyalamayarak %30'a kadar daha hızlı artımlı bağlantı süreleri (Visual Studio 2015'e karşı) etkinleştirin. PDB dosyası bunun yerine yürütülebilir oluşturmak için kullanılan nesne ve kitaplık dosyaları için hata ayıklama bilgilerine işaret ediyor. /Debug:fastlink ve [Visual Studio'da C++'ı hızlandırmak için öneriler](https://devblogs.microsoft.com/cppblog/recommendations-to-speed-c-builds-in-visual-studio/)içeren VS ["15"te Daha Hızlı C++ yapı döngüsüne](https://devblogs.microsoft.com/cppblog/faster-c-build-cycle-in-vs-15-with-debugfastlink/) bakın.

- Visual Studio 2017 [/sdl](../build/reference/sdl-enable-additional-security-checks.md) [ile /await](../build/reference/await-enable-coroutine-support.md)ile kullanılmasına izin verir. Coroutines ile [/RTC](../build/reference/rtc-run-time-error-checks.md) sınırlamasını kaldırdık.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- [/std:c++14 ve /std:c++latest](../build/reference/std-specify-language-standard-version.md): Bu derleyici seçenekleri, bir projede ISO C++ programlama dilinin belirli sürümlerini seçmenizi sağlar. Yeni taslak standart özelliklerin çoğu **/std:c++en son** seçeneği tarafından korunur.

- [/std:c++17](../build/reference/std-specify-language-standard-version.md) derleyici tarafından uygulanan C++17 özellikleri kümesini sağlar. Bu seçenek, Çalışma Taslağı'nın sürümlerinde değiştirilen veya yeni olan özellikler için derleyiciyi ve standart kitaplık desteğini devre dışı kılabilir ve C++17'den sonra C++ Standardının hata güncelleştirmelerini. Bu özellikleri etkinleştirmek için **/std:c++en son**kullanın.

### <a name="codegen-security-diagnostics-and-versioning"></a>Codegen, güvenlik, tanılama ve sürüm

Bu sürüm, optimizasyon, kod oluşturma, araç seti sürümü ve tanılama da çeşitli iyileştirmeler getirir. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: sabit tam sayıları bölme işlemleri için otomatik vektörleştirme desteği, memset desenlerinin daha iyi tanınması.
- Geliştirilmiş kod güvenliği: Arabellek taşma derleyici tanılama geliştirilmiş emisyon ve [/ guard:cf](../build/reference/guard-enable-control-flow-guard.md) şimdi atlama tabloları oluşturmak ifadeleri geçiş.
- Sürüm: Yerleşik önişlemci makro ** \_SU CC\_VER'in** değeri artık her Visual C++ araç setinde monoton olarak güncellenmektedir. Daha fazla bilgi için [Visual C++ Derleyici Sürümü'ne](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/)bakın.
- Yeni araç seti düzeni: Derleyici ve ilgili yapı araçları geliştirme makinenizde yeni bir konum ve dizin yapısına sahiptir. Yeni düzen, derleyicinin birden çok sürümüyan yan yana yüklemeleri sağlar. Daha fazla bilgi için Visual [Studio 2017'de Derleyici Araçları Düzeni'ne](https://devblogs.microsoft.com/cppblog/compiler-tools-layout-in-visual-studio-15/)bakın.
- Geliştirilmiş tanılama: Çıktı penceresi artık bir hatanın oluştuğu sütunu gösterir. Daha fazla bilgi için VS ["15" Preview 5'teki C++ derleyici tanılama geliştirmelerine](https://devblogs.microsoft.com/cppblog/c-compiler-diagnostics-improvements-in-vs-15-rc/)bakın.
- Ortak yordamlar kullanırken, deneysel anahtar kelime **verimi** **(/bekleme** seçeneği altında kullanılabilir) kaldırıldı. Kodunuz bunun yerine `co_yield` kullanmak için güncelleştirilmelidir. Daha fazla bilgi [ `yield` için VS `co_yield` 2017'de yer almak için anahtar kelimeye](https://devblogs.microsoft.com/cppblog/yield-keyword-to-become-co_yield-in-vs-2017/)bakın.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

Derleyicideki tanılamada ek iyileştirmeler. Daha fazla bilgi için Visual [Studio 2017 15.3.0'da Tanısal İyileştirmeler'e](https://devblogs.microsoft.com/cppblog/diagnostic-improvements-in-vs2017-15-3-0/)bakın.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Görsel C++ çalışma zamanı performansı, daha iyi oluşturulan kod kalitesi nedeniyle iyileşmeye devam ediyor. Artık kodunuzu yeniden derleyebilirsiniz ve uygulamanız daha hızlı çalışır. Derleyici optimizasyonlarının bazıları, koşullu skaler mağazaların vektörelleştirilmesi, aramaların `sin(x)` birleştirilmesi ve `cos(x)` yeni bir `sincos(x)`"yeni" ve SSA optimize edicisinden gereksiz talimatların ortadan kaldırılması gibi yepyenidir. Diğer derleyici optimizasyonları, koşullu ifadeler için vektörel sezgisel, daha iyi döngü optimizasyonları ve float min/max codegen gibi varolan işlevlerde iyileştirmelerdir. Bağlayıcı, %9'a varan bağlantı süresi hızlarına neden olabilecek yeni ve daha hızlı **/OPT:ICF** uygulamasına sahiptir ve artımlı bağlantıda başka perf düzeltmeleri de vardır. Daha fazla bilgi için bkz: [/OPT (Optimizasyonlar)](../build/reference/opt-optimizations.md) ve [/INCREMENTAL (Bağlantı Aşamalı)](../build/reference/incremental-link-incrementally.md).

Microsoft C++ derleyicisi, AVX-512'de 128 bit ve 256 bit geniş kasalarda yeni işlevler getiren Vektör Uzunluğu yönergeleri de dahil olmak üzere Intel'in AVX-512'sini destekler.

[/Zc:noexceptTypes-](../build/reference/zc-noexcepttypes.md) seçeneği, genel olarak C++17 modunu `noexcept` kullanırken C++14 sürümüne dönmek için kullanılabilir. Bu seçenek, tüm kodunuzu aynı anda yeniden yazmak zorunda kalmadan `throw()` kaynak kodunuzu C++17'ye uyacak şekilde güncelleştirmenizi sağlar. Daha fazla bilgi için Dinamik [özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements.md#noexcept_removal)bakın.

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Spekülatif yürütme yan kanal saldırılarına karşı azaltmaya yardımcı olmak için yeni derleyici anahtarı [/Qspectre.](../build/reference/qspectre.md) Daha fazla bilgi için [MSVC'deki Spectre azaltıcı etkenleri](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/)ne bürünme.
- Spectre azaltma için yeni tanılama uyarısı. Daha fazla bilgi için [Visual Studio 2017 Sürüm 15.7 Önizleme 4'teki Spectre diagnostik](https://devblogs.microsoft.com/cppblog/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/)bakın.
- /Zc, **/Zc:__cplusplus**için yeni bir değer, C++ standart desteğinin doğru raporlanmasını sağlar. Örneğin, anahtar ayarlandığında ve derleyici /std:c++17 modunda olduğunda değer **201703L'ye**kadar genişler. Daha fazla bilgi için, [MSVC şimdi doğru __cplusplus raporlar](https://devblogs.microsoft.com/cppblog/msvc-now-correctly-reports-__cplusplus/)bakın.

## <a name="c-standard-library"></a>C++ standart kitaplığı

### <a name="correctness-improvements"></a>Doğruluk Geliştirmeleri

##### <a name="visual-studio-2017-rtm-version-150"></a>Visual Studio 2017 RTM (sürüm 15.0)

- Küçük `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` tanı lama iyileştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- Daha `std::promise` önce kodusonsuza kadar engellemeye neden olabilir taşıma atama işleci düzeltildi.
- `atomic<T*>` Örtülü dönüştürme ile derleyici `T*`hataları düzeltildi.
- `pointer_traits<Ptr>`şimdi doğru `Ptr::rebind<U>`algılar.
- `move_iterator` Çıkarma işlecinde eksik `const` bir niteleyici düzeltildi.
- Kullanıcı tanımlı tahsisatçıların istediği `propagate_on_container_copy_assignment` ve `propagate_on_container_move_assignment`.
- `atomic<T>`şimdi aşırı yüklenmesini `operator&()`tolere eder.
- Yanlış `bind()` aramalar için biraz geliştirilmiş derleyici tanılama.

Visual Studio 2017 RTM'deki standart kütüphane geliştirmelerinin tam listesi için C++ Team Blog girişi [Standart Kütüphane Düzeltmeleri VS 2017 RTM'ye](https://devblogs.microsoft.com/cppblog/stl-fixes-in-vs-2017-rtm/)bakın.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Standart kütüphane kapsayıcıları `max_size()` `numeric_limits<difference_type>::max()` şimdi yerine `max()` `size_type`onların kelepçe . Bu değişiklik, bu kapsayıcıdaki yineleyicilerin `distance()` sonucunun `distance()`geri dönüş türünde temsil edilebilir olmasını sağlar.
- Eksik uzmanlık `auto_ptr<void>`düzeltildi.
- Uzunluk `for_each_n()` `generate_n()`bağımsız `search_n()` değişkeni integral bir tür değilse, , ve algoritmalar daha önce derlemek için başarısız oldu; şimdi ayrılmaz olmayan uzunlukları yineleyicilere dönüştürmeye `difference_type`çalışırlar.
- `normal_distribution<float>`artık standart kitaplık içinde çiftten float'a daraltma konusunda uyarılar yayılmaz.
- Maksimum `basic_string` boyut taşma `max_size()` larını denetlerken yerine kullanılan `npos` bazı işlemler düzeltildi.
- `condition_variable::wait_for(lock, relative_time, predicate)`sahte bir uyanış durumunda tüm göreceli süre için bekleyecekti. Şimdi göreli zaman sadece tek bir aralık için bekleyecek.
- `future::get()``future`şimdi, standart gerektirdiği gibi geçersiz kılması.
- `iterator_traits<void *>`oluşturmak `void&`için çalıştı çünkü zor bir hata olarak kullanılır ; şimdi temiz "iterator" SFINAE koşullarında kullanımına `iterator_traits` izin vermek için boş bir yapı haline gelir.
- Clang **-Wsystem-headers** tarafından bildirilen bazı uyarılar düzeltildi.
- Ayrıca clang **-Wmicrosoft-exception-spec**tarafından bildirilen "beyannamedeki özel durum belirtimi önceki bildirimle eşleşmiyor" sabittir.
- Ayrıca Clang ve C1XX tarafından bildirilen mem-initializer-list sipariş uyarıları sabit.
- Sıralanmamış kapsayıcılar, kaplar takas edildiğinde karma işlevlerini veya yüklemlerini değiştirmedi. Şimdi biliyorlar.
- Birçok kapsayıcı değiştirme işlemi `noexcept` artık işaretlenmiştir (standart kitaplığımız eşit`propagate_on_container_swap` olmayan veya tanımlanmamış davranış durumunu algılarken hiçbir zaman bir özel durum oluşturmayı planlamayın).
- Birçok `vector<bool>` işlem artık `noexcept`işaretlenmiştir.
- Standart kitaplık artık eşleşen `value_type` ayırıcıyı (C++17 modunda) bir çıkış çıkış kapağıyla uygular.
- Kendi kendine ara eklemedizeli içeriğini `basic_string` karıştıracak bazı koşullar düzeltildi. (Not: vektörlere self-range-insert hala Standart tarafından yasaktır.)
- `basic_string::shrink_to_fit()`artık `propagate_on_container_swap`tahsisatçının.
- `std::decay`şimdi, cv nitelikli ve/veya ref nitelikli işlev türlerini, yani işlev türlerini işler.
- Değiştirilen, taşınabilirliği artıran uygun servis talebi hassasiyeti ve ileri eğik çizgileri kullanma yönergelerini içerir.
- Sabit uyarı C4061 "enumerator '*enumerator*' ' in switch of enum '*numaralandırma*' açıkça bir servis talebi etiketi tarafından ele alınmaz.) Bu uyarı varsayılan olarak kapalıdır ve standart kitaplığın uyarılar için genel ilkesinin bir istisnası olarak düzeltildi. (Standart kitaplık **/W4** temizdir, ancak **/Duvar** temiz olmaya çalışmaz. Birçok off-by-default uyarılar son derece gürültülü ve düzenli olarak kullanılmak üzere tasarlanmamıştır.)
- Geliştirilmiş `std::list` hata ayıklama denetimleri. Liste yineleyicileri `operator->()`şimdi `list::unique()` denetleyin ve şimdi geçersiz olarak yineleyicileri işaretler.
- 'de `tuple`sabit kullanım-ayırıcı metaprogramming

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `std::partition`şimdi, standardın gerektirdiği gibi, yüklem N kez N + 1 katı yerine çağırır.
- Sürüm 15.3'teki sihirli statikten kaçınma girişimleri sürüm 15.5'te onarılmıştır.
- `std::atomic<T>`artık varsayılan `T` olarak yapılabilir olması gerekir.
- Logaritmik zamanı alan yığın algoritmalar, yineleyici hata ayıklama etkinleştirildiğinde girişin aslında bir yığın olduğunu doğrusal bir zaman iddiaetmez.
- `__declspec(allocator)`şimdi c1xx sadece, Bu declspec anlamıyor Clang, uyarıları önlemek için korunur.
- `basic_string::npos`derleme zaman sabiti olarak kullanılabilir.
- `std::allocator`C++17 modunda artık aşırı hizalanmış türlerin, yani hizalamalarının `max_align_t` **/Zc:alignedNew tarafından**devre dışı bırakılmadıkça, hizalamadaha büyük olan türlerin tahsisini düzgün bir şekilde işler.  Örneğin, 16 bayt veya 32 bayt hizalama ile nesnelerin vektörleri artık Düzgün SSE ve AVX yönergeleri için hizalanır.

### <a name="conformance-improvements"></a>Uygunluk iyileştirmeleri

- Biz \<herhangi\> \<bir\> `apply()`ekledi `make_from_tuple()`, string_view , .
- Eklenen \<\>isteğe\> `shared_ptr::weak_type`bağlı \<, \<varyant\>, ve cstdalign .
- Etkin `constexpr` C++14 `min(initializer_list)` `max(initializer_list)`içinde `minmax(initializer_list)`, `min_element()`, `max_element()`ve `minmax_element()`, ve , ve .

Daha fazla bilgi için [Microsoft C++ dil uygunluk tablosuna](../visual-cpp-language-conformance.md)bakın.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Birkaç ek C++17 özelliği uygulanmıştır. Daha fazla bilgi için [Microsoft C++ dil uygunluk tablosuna](cpp-conformance-improvements.md#improvements_153)bakın.
- Uygulanan P0602R0 "varyant ve isteğe bağlı kopyalama / taşıma önemsizlik yaymak gerekir".
- Standart kütüphane artık dinamik RTTI'nin [/GR-](../build/reference/gr-enable-run-time-type-information.md) seçeneği ile devre dışı bırakılmasını resmen tolere ediyor. Hem `dynamic_pointer_cast()` `rethrow_if_nested()` de doğal `dynamic_cast`olarak gerektirir, bu yüzden `=delete` standart kütüphane şimdi / GR altında olarak **işaretler-**.
- Dinamik RTTI **/GR-**, "statik RTTI" şeklinde `typeid(SomeType)` devre dışı bırakılmış olsa bile hala mevcuttur ve çeşitli standart kitaplık bileşenlerine güç verir. Standart kitaplık artık **/D\_HAS\_STATIC\_RTTI=0**ile bu özelliğin devre dışı bırakılmasını da destekler. Bu bayrak da devre `std::any`dışı `target()` `target_type()` kalır `std::function`, ve `get_deleter()` üye işlevleri `std::shared_ptr` `std::weak_ptr`, ve arkadaş üye işlevi ve .
- Standart kitaplık artık koşullu `constexpr` olarak tanımlanmış makrolar yerine koşulsuz C++14 kullanır.
- Standart kitaplık artık dahili diğer ad şablonlarını kullanır.
- Standart kitaplık `nullptr` artık `nullptr_t{}`dahili olarak, yerine kullanır. (NULL'un dahili kullanımı ortadan kaldırılmıştır. 0-as-null'un dahili kullanımı yavaş yavaş temizlenmektedir.)
- Standart kitaplık `std::move()` şimdi, stilistik olarak kötüye `std::forward()`kullanmak yerine dahili olarak kullanır.
- Olarak `static_assert(false, "message")` `#error message`değiştirildi. Bu değişiklik derleyici tanılamayı geliştirir, çünkü `#error` derlemeyi hemen durdurur.
- Standart kitaplık işlevleri artık `__declspec(dllimport)`" olarak işaretlemez. Modern bağlayıcı teknolojisi artık bunu gerektirmez.
- İade türleri ve işlev bağımsız değişken iþlemi türleri ile karþılaştırılan dağıtımı azaltan varsayılan şablon argümanlarına SFINAE ayıklanmıştır.
- Rasgele hata \<ayıklama denetimleri\> şimdi **stderr**çağırdı `fputs()` iç fonksiyonu `_Rng_abort()` yerine, standart kitaplığın olağan makine kullanın. Bu işlevin uygulaması ikili uyumluluk için korunur, ancak standart kitaplığın bir sonraki ikili uyumsuz sürümünde kaldırılmıştır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- C++17 standardına uygun olarak çeşitli standart kitaplık özellikleri eklendi, amortismana alındı veya kaldırıldı. Daha fazla bilgi için [Visual Studio'daki C++ uyumluluk iyileştirmelerine](cpp-conformance-improvements.md#improvements_155)bakın.
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
- Aşağıdaki paralel algoritmaların imzaları eklenir ancak şu anda paralelleştirilemez; profil oluşturma, yalnızca öğeleri hareket ettiren veya permute eden algoritmaları paralelleştirmede hiçbir fayda göstermedi:
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
- Kütüphane Temelleri V1
- Atama silme `polymorphic_allocator`
- Sınıf şablonu bağımsız değişken çıkarımını geliştirme

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Paralel algoritmalar için destek artık deneysel değil
- Dosya sisteminin \<yeni bir uygulaması>
- Temel dize dönüşümleri (kısmi)
- `std::launder()`
- `std::byte`
- `hypot(x,y,z)`
- Gereksiz çürümeden kaçınma
- Matematiksel özel fonksiyonlar
- `constexpr char_traits`
- Standart kitaplık için kesinti kılavuzları

Daha fazla bilgi için [Microsoft C++ dil uygunluk tablosuna](../visual-cpp-language-conformance.md)bakın.

### <a name="performance-and-throughput-fixes"></a>Performans ve iş elde düzeltmeleri

- Aşırı `basic_string::find(char)` yüklemeler `traits::find` sadece bir kez arama yaptı. Daha önce, uzunluk 1 bir dize için genel bir dize arama olarak uygulanmıştır.
- `basic_string::operator==`dizeleri içeriğini karşılaştırmadan önce dize boyutunu denetler.
- Derleyici optimize `basic_string`edicinin analiz etmesi zor olan denetim bağlantısını kaldırdı. Tüm kısa dizeleri `reserve` için, arama hala hiçbir şey yapmak için sıfır olmayan bir maliyeti vardır.
- `std::vector`doğruluk ve performans için elden geçirildi: ekleme ve yerleştirme işlemleri sırasında takma adlama artık Standart tarafından gerekli olarak doğru şekilde işlenir, `move_if_noexcept()` güçlü özel durum garantisi şimdi Standart ve diğer mantık tarafından gerekli olduğunda sağlanır ve ekleme ve emplace daha az eleman işlemleri gerçekleştirmek.
- C++ standart kitaplığı artık null fantezi işaretçileri dereferencing önler.
- Geliştirilmiş `weak_ptr::lock()` performans.
- Derleyici çıktısını artırmak için, C++ standart kitaplık üstbilgisi artık gereksiz derleyici içselleri için bildirimler ilerleyerek kaçının.
- Yapıcıların `std::string` performansını `std::wstring` üç kattan fazla artırın ve hareket ettirin.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Yapılandırılmış Özel Durum `noexcept` İşleme (SEH) kullanan işlevlere `std::atomic` uygulamanın ayarlanmasını engelleyen etkileşimler etrafında çalıştı.
- Standart kitaplığın iç `_Deallocate()` işlevini daha küçük koda dönüştürmek için değiştirerek daha fazla yere inlined olmasını sağladı.
- Özyineleme yerine paket genişletme sn kullanmak üzere değiştirildi. `std::try_lock()`
- Tüm `std::lock()` kilitler `try_lock()` üzerinde dönen `lock()` yerine işlemleri kullanmak için kilitlenme kaçınma algoritması geliştirilmiş.
- Adlandırılmış İade Değeri Optimizasyonu'nu ' da `system_category::message()`etkinleştirildi.
- `conjunction`ve `disjunction` şimdi 2N + 2 türleri yerine N + 1 türlerini anında
- `std::function`artık her tür silinmiş çağrılabilir için allocator destek makineleri anında, iş ve çok farklı lambdas `std::function`geçmek programlarda .obj boyutunu azaltarak.
- `allocator_traits<std::allocator>`yalnızca (diğer `std::allocator` bir deyişle, çoğu kodda) `std::allocator` etkileşimde `allocator_traits` bulunan kod boyutunu azaltarak el ile inlined işlemleri içerir.
- C++11 minimal ayırıcı arabirimi artık ayırıcıyı bir iç sınıfa `allocator_traits` `_Wrap_alloc`sarmak yerine doğrudan çağıran standart kitaplık tarafından işlenir. Bu değişiklik, ayırıcı desteği için oluşturulan kod boyutunu azaltır, bazı durumlarda standart kitaplık kapsayıcıları hakkında muhakeme en iyi duruma getirici yeteneğini geliştirir ve `_Wrap_alloc<your_allocator_type>` daha iyi bir hata ayıklama deneyimi sağlar (şimdi hata ayıklayıcı yerine allocator türünü gördüğünüz gibi).
- Özelleştirilmiş `allocator::reference`meta programlama kaldırıldı, hangi ayırıcılar aslında özelleştirmek için izin verilmez. (Ayırıcılar kapsayıcılar süslü işaretçiler kullanmak, ancak fantezi referanslar yapabilirsiniz.)
- Derleyici ön uç hata ayıklama devreleri döngüler için aralık tabanlı hata ayıklayıcıları açmak için öğretildi, hata ayıklama oluşturur performansını artırmak.
- İç `basic_string` küçültme yolu `shrink_to_fit()` `reserve()` için ve artık işlemleri yeniden ayırma yolunda, tüm mutasyona uğrayan üyeler için kod boyutunu azaltarak.
- Dahili `basic_string` büyüme yolu artık. `shrink_to_fit()`
- `basic_string` Mutasyonişlemleri artık hızlı yol ayırmama ve yavaş yol işlevlerinin ayrılması na faktoringlere dahil edilme olasılığı na sahiptir.
- Mutasyona `basic_string` uğrama işlemleri artık yeniden boyutlandırma yerine istenilen durumda yeniden ayrılmış arabellekler oluşturuyor. Örneğin, bir dize başında ekleme şimdi ekleme tam olarak bir kez (aşağı veya yeni ayrılan arabellek için), yerine iki kez yeniden ayırma durumda (yeni tahsis arabellek ve sonra aşağı) ekleme sonra içeriği taşır.
- String'teki \<\> C standart kitaplığını çağıran `errno` işlemler artık TLS ile tekrarlanan etkileşimi kaldırmak için adresi önbelleğe alın.
- `is_pointer` Uygulama basitleştirilmiş.
- İşlev tabanlı İfade SFINAE'yi `struct` ve `void_t`-tabanlıyı değiştirmeyi bitirdi.
- Standart kitaplık algoritmaları artık postincrementing yineleyiciler kaçının.
- 64 bit sistemlerde 32 bit ayırıcılar kullanırken kesilme uyarıları düzeltildi.
- `std::vector`taşıma ataması, mümkün olduğunda arabelleği yeniden kullanarak POCMA olmayan eşit tahsisatçı olmayan durumda artık daha verimlidir.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `basic_string<char16_t>`şimdi aynı `memcmp` `memcpy`, ve benzer optimizasyonlar `basic_string<wchar_t>` meşgul yürüter.
- Visual Studio 2015 Update 3'teki "kopyalama işlevlerinden kaçınma" çalışmamıztarafından ortaya çıkarılan işlev işaretçilerin inlined olmasını engelleyen en `lower_bound(iter, iter, function pointer)`iyi duruma getirici sınırlaması, 'ın performansını geri kazandı.
- Yineleme `includes`hata ayıklamanın girişlerin sipariş doğrulamasının yükü , , `set_difference` `set_symmetric_difference`, `set_union` ve siparişi denetlemeden önce yineleyicilerin paketlemesi azaltıldı.
- `std::inplace_merge`şimdi zaten konumda olan öğeler üzerinden atlar.
- Yapı `std::random_device` landırma artık inşa etmez ve `std::string`sonra bir .
- `std::equal`ve `std::partition` bir yineleyici karşılaştırma kaydeder bir atlama iş parçacığı optimizasyonu geçiş vardı.
- Önemsiz `std::reverse` kopyalanabilir `T`işaretçiler geçirildiğinde, şimdi bir el yazısı vektörel uygulamaya sevk edecektir.
- `std::fill`, `std::equal`ve `std::lexicographical_compare` `memset` nasıl ve `memcmp` için `std::byte` ve `gsl::byte` (ve diğer char gibi enums ve enum sınıfları) sevk öğretildi. Gönderiler `std::copy` kullanarak `is_trivially_copyable`bu yana, herhangi bir değişiklik gerek yoktu.
- Standart kitaplık artık tek davranışı türleri önemsiz olmayan yok edilemez hale getirmek olan boş ayraç yıkıcılar içermez.

## <a name="other-libraries"></a>Diğer Kütüphaneler

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg,** Visual Studio'da açık kaynak kodlu C++ statik libs ve DLLS edinme ve oluşturma işlemini büyük ölçüde kolaylaştıran bir açık kaynak komut satırı aracıdır. Daha fazla bilgi için [vcpkg: C++ için bir paket yöneticisi.](../build/vcpkg.md)

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

C++'ın platformötesi web API'si cpprestsdk, sürüm 2.9.0 olarak güncelleştirildi. Daha fazla bilgi için [Bkz. CppRestSDK 2.9.0 GitHub'da mevcuttur.](https://devblogs.microsoft.com/cppblog/cpprestsdk-2-9-0-is-available-on-github/)

### <a name="atl"></a>ATL

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Henüz başka bir isim arama uygunluk düzeltmeleri kümesi
- Varolan hareket oluşturucuları ve taşıma atama işleçleri artık atmayan olarak düzgün bir şekilde işaretlenmiştir
- Unsuppress geçerli uyarı C4640 atlstr.h yerel statik iplik güvenli init hakkında
- Yerel statiklerin iş parçacığı güvenli başlatma otomatik olarak bir DLL oluşturmak için ATL kullanırken XP araç kümesi kapatıldı, ama şimdi değil. İş parçacığı için güvenli bir başlatma isteniyorsa Proje ayarlarınıza **/Zc:threadSafeInit-** ekleyebilirsiniz.

### <a name="visual-c-runtime"></a>Görsel C++ çalışma zamanı

- Kontrol Akış Koruması sembolleri için yeni başlık "cfguard.h".

## <a name="c-ide"></a>C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Bir çözüm yapılandırması ilk kez etkinleştirildiğinde, artık daha hızlı olacaktır ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anlık olacaktır.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf Ekle** şimdi doğrudan Sınıf Ekle sihirbazı başlattı. Daha önce burada olan diğer öğelerin tümü artık **Yeni Öğe ekle**> altında kullanılabilir.
- Win32 projeleri artık **Yeni Proje** iletişim kutusunda **Windows Masaüstü** kategorisi altında.
- **Windows Console** ve **Masaüstü Uygulaması** şablonları artık bir sihirbaz görüntülemeden projeleri oluşturur. Eski **Win32 Konsol Uygulaması** sihirbazıyla aynı seçenekleri görüntüleyen aynı kategori altında yeni bir **Windows Masaüstü Sihirbazı** vardır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Refactoring ve kod navigasyonu için IntelliSense altyapısını kullanan birkaç C++ işlemi çok daha hızlı çalışır. Aşağıdaki sayılar 3500 projeile Visual Studio Krom çözümdayanmaktadır:

|||
|-|-|
|Özellik|Performans Geliştirme|
|Rename|5.3 x|
|İmzayı Değiştir |4.5 x|
|Tüm Başvuruları Bul|4.7x|

C++ artık Ctrl+Click **To Definition'ı**destekleyip, tanımlara fare gezinmeyi kolaylaştırıyor. Verimlilik Elektrikli Araçlar paketinden Yapı Görselleştiricisi artık varsayılan olarak ürüne de dahil edilmiştir.

## <a name="intellisense"></a>IntelliSense

- Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Bu, **Tanıya Git** ve **Tüm Başvuruları Bul**gibi veritabanı işlemlerini hızlandıracak ve ilk çözüm ayrıştırmanı önemli ölçüde artıracaktır. Ayar, Metin Düzenleyicisi > > Araçlar > Seçenekleri'ne taşınmış **> C/C++ gelişmiş** (eskiden ... C/C++ | Deneysel).

- Önceden derlenmiş üstbilgi kullanmayan projeler ve dosyalarda IntelliSense performansını artırdık - geçerli dosyadaki üstbilgi için Otomatik Önceden Derlenmiş Üstbilgi oluşturulacaktır.

- Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Filtrelenmiş Hata Listesi](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

- Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye Listesi Filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

- Üye Listesinde görünenlerin bağlamsal olarak farkında filtreleme sağlayan yeni bir deneysel Predictive IntelliSense özelliği eklendi. Daha fazla bilgi için [Bkz. C++ IntelliSense Geliştirmeler - Predictive IntelliSense & Filtreleme](https://devblogs.microsoft.com/cppblog/c-intellisense-improvements-predictive-intellisense-filtering/).
- **Tüm Referansları Bul** (Shift+F12) artık karmaşık codebase'lerde bile kolayca gezinmenize yardımcı olur. Gelişmiş gruplandırma, filtreleme, sıralama, sonuçlar içinde arama ve (bazı diller için) renklendirme sağlar, böylece başvurularınızı net bir şekilde anlayabilirsiniz. C++'da yeni kullanıcı arabirimi, bir değişkenden okuyup okumadığımız veya bir değişkene yazıp yazmadığımız hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyici özellikleri **Genişletme Kapsamları** ve **Genişletme Önceliği** de deneyselden gelişmişe taşınmıştır.
- Deneysel yeniden düzenleme özellikleri **İmzayı Değiştir** ve **Ayıklama İşlevini** Değiştir artık varsayılan olarak kullanılabilir.
- C++ projeleri için deneysel bir 'Daha hızlı proje yükü' özelliği eklendi. Bir dahaki sefere bir C++ projesini açtığınızda daha hızlı yüklenir ve bundan sonraki zaman *çok* daha hızlı yüklenir!
- Bu özelliklerden bazıları diğer dillerde yaygındır ve bazıları C++'a özgüdür. Bu yeni özellikler hakkında daha fazla bilgi için Visual [Studio "15" Preview 5'i duyurmak](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-15-preview-5/)için bkz.

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- ClangFormat için destek eklendi. Daha fazla bilgi için [Visual Studio 2017'de ClangFormat Desteği'ne](https://devblogs.microsoft.com/cppblog/clangformat-support-in-visual-studio-2017-15-7-preview-1/)bakın.

## <a name="non-msbuild-projects-with-open-folder"></a>Açık Klasörlü MSBuild olmayan projeler

Visual Studio 2017, herhangi bir çözüm veya proje oluşturmaya gerek kalmadan kaynak kodu içeren bir klasörde kodlamanızı, oluşturmanızı ve hata ayıklamanızı sağlayan **Açık Klasör** özelliğini sunar. Projeniz MSBuild tabanlı bir proje olmasa bile Visual Studio'ya başlamak artık çok daha kolay. **Open Folder**ile Visual Studio'nun MSBuild projeleri için sağladığı güçlü kod anlama, düzenleme, oluşturma ve hata ayıklama özelliklerine erişebilirsiniz. Daha fazla bilgi için [C++ için Klasör Aç projelerine](../build/open-folder-projects-cpp.md)bakın.

- Klasör Aç deneyimi geliştirmeleri. Bu .json dosyaları aracılığıyla deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- MinGW ve Cygwin gibi alternatif derleyiciler ve yapı ortamları için geliştirilmiş destek. Daha fazla bilgi için Bkz. [Görsel C++ ve Open Klasörü ile MinGW ve Cygwin'i kullanma.](https://devblogs.microsoft.com/cppblog/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/)
- CppProperties.json ve CMakeSettings.json'da genel ve yapılandırmaya özgü ortam değişkenlerini tanımlamak için destek eklendi. Bu ortam değişkenleri launch.vs.json'da tanımlanan hata ayıklama yapılandırmaları ve görevler.vs.json'daki görevler tarafından tüketilebilir. Daha fazla bilgi için Bkz. [Visual C++ ve Open Folder ile Ortamınızı Özelleştirme.](https://devblogs.microsoft.com/cppblog/customizing-your-environment-with-visual-c-and-open-folder/)
- Kolayca 64-bit platformlar hedef yeteneği de dahil olmak üzere CMake Ninja jeneratör için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>COpen Klasörü üzerinden destek yap

Visual Studio 2017, MSBuild proje dosyalarına (.vcxproj) geçmeden CMake projelerini kullanmak için destek sunar. Daha fazla bilgi için [Visual Studio'daki CMake projelerine](../build/cmake-projects-in-visual-studio.md)bakın. **CMake** projelerini Open Folder ile açmak, C++ düzenleme, oluşturma ve hata ayıklama için ortamı otomatik olarak yapılandırır.

- C++ IntelliSense kök klasöründe bir CppProperties.json dosyası oluşturmaya gerek kalmadan çalışır. Ayrıca, kullanıcıların CMake ve CppProperties.json dosyaları tarafından sağlanan yapılandırmalar arasında kolayca geçiş yapabilmelerini sağlamak için yeni bir açılır bilgi ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![Cmake Klasör Aç](media/cmake-cpp.png "CMake Açık Klasör")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- CMake Ninja jeneratörü için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Varolan CMake önbelleklerini almak için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- CMake 3.11 için eklenen destek, CMake projelerinde kod analizi, Çözüm Gezgini'nde Hedefler görünümü, önbellek oluşturma seçenekleri ve tek dosya derlemesi. Daha fazla bilgi için [Visual Studio'da CMake Desteği](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [Visual Studio'daki CMake projelerine](../build/cmake-projects-in-visual-studio.md)bakın.

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows masaüstü geliştirme

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik. Yükleyici Ara Birimi'nde listelenen bileşenler için belirtilen yükleme boyutları doğru değildir ve toplam boyutu hafife alır.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Önerilen (seçili) bileşenleri **VC++ 2017 v141 araç setini (x86, x64)** ve **Windows 10 SDK'yı (10.0.nnnnnn)** yükleyin. Gerekli araçlar yüklenmezse, projeler başarıyla oluşturulmaz ve sihirbaz askıda olur.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Visual C++ Build araçları (daha önce bağımsız bir ürün olarak kullanılabilir) artık Visual Studio Yükleyici'de iş yükü olarak eklenmiştir. Bu iş yükü, Visual Studio IDE'yi yüklemeden yalnızca C++ projeleri oluşturmak için gereken araçları yükler. Hem v140 hem de v141 araç setleri dahildir. v141 araç seti Visual Studio 2017 sürüm 15.5'teki en son geliştirmeleri içerir. Daha fazla bilgi için Visual Studio Build Tools'a bakın şimdi [VS2017 ve VS2015 MSVC Araç Setleri'ni ekleyin.](https://devblogs.microsoft.com/cppblog/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

##### <a name="visual-studio-2017-version-152"></a>Visual Studio 2017 sürüm 15.2

Platformlar arası kod paylaşımı ve tür görselleştirmesinde iyileştirmeler yapılmıştır. Daha fazla bilgi için, [platformlar arası kod paylaşımı ve tür görselleştirmeiçin Linux C++ geliştirmelerine](https://devblogs.microsoft.com/cppblog/linux-cross-platform-and-type-visualization/)bakın.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Linux iş yükü uzak Linux makineleri dosyaları senkronize etmek için **sftp** alternatif olarak **rsync** için destek ekledi.
- ARM mikrodenetleyicilerini hedefleyen çapraz derleme için destek eklenir. Yüklemede etkinleştirmek için C++ iş **yüküne sahip Linux geliştirmeyi** seçin ve **Gömülü ve IoT Geliştirme**seçeneğini seçin. Bu seçenek ARM GCC çapraz derleme araçlarını ve kurulumunuza yap'ı ekler. Daha fazla bilgi için [Visual Studio'da ARM GCC Cross Derlemesi'ne](https://devblogs.microsoft.com/cppblog/arm-gcc-cross-compilation-in-visual-studio/)bakın.
- CMake için destek eklendi. Artık bir Visual Studio projesine dönüştürmek zorunda kalmadan varolan CMake kod tabanı üzerinde çalışabilirsiniz. Daha fazla bilgi için bkz: [Linux CMake Projesini Yapılandır.](../linux/cmake-linux-project.md)
- Uzak görevleri çalıştırmak için destek eklendi. Bu özellik, Visual Studio'nun Bağlantı Yöneticisi'nde tanımlanan uzak bir sistemde herhangi bir komut çalıştırmanızı sağlar. Uzak görevler de uzak sisteme dosyaları kopyalamak için yeteneği sağlar.
Daha fazla bilgi için bkz: [Linux CMake Projesini Yapılandır.](../linux/cmake-linux-project.md)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- Linux iş yükü senaryolarında çeşitli iyileştirmeler. Daha fazla bilgi için, [Proje Sistemi, Linux Console Penceresi, rsync ve İşleme Ekle'de Linux C++ İş Yükü geliştirmelerine](https://devblogs.microsoft.com/cppblog/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/)bakın.
- Uzak Linux bağlantılarındaki başlıklar için IntelliSense. Daha fazla bilgi [için, Uzak Linux Başlıkları için IntelliSense'e](https://devblogs.microsoft.com/cppblog/intellisense-for-remote-linux-headers/) bakın ve [Bir Linux CMake Projesi'ni yapılandırın.](../linux/cmake-linux-project.md)

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ ile mobil geliştirme (Android ve iOS)

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017'de v140 hedefli bir Evrensel Windows Platformu projesi açarsanız, Visual Studio 2015 yüklü değilse proje özelliği sayfalarındaki v141 platform araç kümesini seçmeniz gerekir.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>Evrensel Windows Platformu'nda C++ için yeni seçenekler (UWP)

Artık Evrensel Windows Platformu ve Windows Mağazası için C++ uygulamalarını yazmak ve paketlemek için yeni seçenekleriniz var: Mevcut masaüstü uygulamanızı veya COM nesnenizi Windows Mağazası üzerinden veya yan yükleme yoluyla mevcut kanallarınız aracılığıyla dağıtım için paketlemek için Desktop Bridge altyapısını kullanabilirsiniz. Windows 10'daki yeni özellikler, masaüstü uygulamanıza çeşitli şekillerde UWP işlevselliği eklemenize olanak tanır. Daha fazla bilgi için [Desktop Bridge'e](/windows/uwp/porting/desktop-to-uwp-root)bakın.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Masaüstü Köprüsü ile masaüstü uygulamalarının paketletini büyük ölçüde kolaylaştıran bir **Windows Uygulama Paketleme Projesi** proje şablonu eklenir. Dosya altında mevcuttur **| Yeni | Proje | Yüklü | Görsel C++ | Evrensel Windows Platformu**. Daha fazla bilgi için [Visual Studio (Desktop Bridge) kullanarak bir uygulamayı paketle'ye](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)bakın.

Yeni kod yazarken, artık yalnızca üstbilgi dosyalarında uygulanan Windows Runtime için standart bir C++ dil projeksiyonu olan C++/WinRT'yi kullanabilirsiniz. Standartlara uygun C++ derleyicisini kullanarak Windows Runtime API'lerini hem yazar hem de tüketmenizi sağlar. C++/WinRT, C++ geliştiricilerinin modern Windows API'sine birinci sınıf erişim sağlamasını sağlamak üzere tasarlanmıştır. Daha fazla bilgi için [Bkz. C++/WinRT: Windows Runtime için Modern C++](https://moderncpp.com/).

Windows SDK Insider Preview'un 17025'inin oluşturulması ndan itibaren C++/WinRT Windows SDK'ya dahildir. Daha fazla bilgi için [C++/WinRT'ye bakın windows sdk'ya dahil edildi.](https://devblogs.microsoft.com/cppblog/cppwinrt-is-now-included-the-windows-sdk/)

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç seti

Visual Studio 2017 ile birlikte gönderilen Clang/C2 araç seti, büyük projeler oluşturmak için çok önemli olan **/bigobj** anahtarını destekliyor. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ kod analizi

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Projenin özellik sayfalarındaki **Kod Analizi Uzantıları** sayfasındaki damaları etkinleştirmeniz yeterlidir ve kod çözümlemesi çalıştırdığınızda uzantılar eklenecektir. Daha fazla bilgi için [Bkz. C++ Çekirdek Yönergeleri denetleyicilerini kullanma.](/cpp/code-quality/using-the-cpp-core-guidelines-checkers)

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikleri sayfası")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Kaynak yönetimiyle ilgili kurallar için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Yeni C++ Çekirdek Yönergeleri akıllı işaretçi doğruluğunu, genel başlatıcıların doğru kullanımını `goto` ve kötü ve kötü dökümler gibi yapıların kullanımını işaretlemeyi kapsar.

- 15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- Tek dosya çözümlemesi için destek ve analiz çalışma zamanı performansındaki iyileştirmeler eklendi. Daha fazla bilgi için bkz: [Visual Studio 2017 15.6 Önizleme 2 için C++ Statik Analiz Geliştirmeleri](https://devblogs.microsoft.com/cppblog/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

- [/analyze:ruleset](../build/reference/analyze-code-analysis.md)için eklenen destek, çalışacak kod çözümleme kurallarını belirtmenizi sağlar.
- Ek C++ Temel Yönergeleri kuralları için destek eklendi.  Daha fazla bilgi için [Bkz. C++ Çekirdek Yönergeleri denetleyicilerini kullanma.](/cpp/code-quality/using-the-cpp-core-guidelines-checkers)

## <a name="unit-testing"></a>Birim testi

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Google Test Bağdaştırıcısı ve Boost.Test Adaptörü artık C++ iş **yüküne sahip Masaüstü Geliştirme** bileşenleri olarak kullanılabilir ve Test **Explorer**ile entegre edilmiştir. Cmake projeleri için CTest desteği (Açık Klasör kullanılarak) eklenir, ancak **Test Gezgini** ile tam tümleştirme henüz kullanılamıyor. Daha fazla bilgi için [C/C++ için yazı birimi testlerine](/visualstudio/test/writing-unit-tests-for-c-cpp)bakın.

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- Boost.Test dinamik kitaplık desteği için destek eklendi.
- Bir Boost.Test öğesi şablonu artık IDE'de kullanılabilir.

Daha fazla bilgi için [Bkz. Boost.Test Unit Test: Dinamik Kitaplık desteği ve Yeni Öğe Şablonu.](https://devblogs.microsoft.com/cppblog/boost-test-unit-testing-dynamic-library-support-and-new-item-template/)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7 Sürüm Notları

[C++](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) birim test projeleri için CodeLens desteği eklendi. Daha fazla bilgi için [C++ Birim Testi için CodeLens'i Duyur'a](https://devblogs.microsoft.com/cppblog/announcing-codelens-for-c-unit-testing/)bakın.

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio Graphics Diagnostics, Direct3D uygulamalarında render ve performans sorunlarını kaydetmek ve analiz etmek için bir araç kümesidir. Grafik Tanılama özellikleri, Windows bilgisayarınızda, Windows aygıt emülatörlerinde veya uzak bir bilgisayarda veya aygıtta yerel olarak çalışan uygulamalarla kullanılabilir.

- **Vertex ve Geometri gölgeleyiciler için Giriş & Çıktı:** Vertex gölgeleyicilerin ve geometri gölgelilerinin giriş ve çıktılarını görüntüleme yeteneği en çok istenen özelliklerden biri olmuştur ve artık araçlarda desteklenmiştir. Aşağıdaki tabloda giriş ve çıktısını incelemeye başlamak için Boru Hattı Aşamaları görünümündeki VS veya GS aşamasını seçmeniz yeterlidir.

  ![Gölgeliler için giriş/Çıkış](media/io-shaders.png)

- **Nesne tablosunda arama ve filtreleme:** Aradığınız kaynakları bulmanın hızlı ve kolay bir yolunu sağlar.

  ![Arama](media/search.png)

- **Kaynak Geçmişi:** Bu yeni görünüm, yakalanan bir çerçevenin işlenmesi sırasında kullanıldığı gibi bir kaynağın tüm değişiklik geçmişini görmenin kolaylaştırılmış bir yolunu sağlar. Herhangi bir kaynak için geçmişi çağırmak için, herhangi bir kaynak köprü yanındaki saat simgesini tıklatın.

  ![Kaynak geçmişi](media/resource-history.png)

  Bu, kaynağın değişiklik geçmişiyle doldurulan yeni **Kaynak Geçmişi** araç penceresini görüntüler.

  ![Kaynak geçmişi değişikliği](media/resource-history-change.png)

  Çerçeveniz tam çağrı yığını yakalama etkin **(Visual Studio > Araçları > Seçenekleri** Grafik **Tanılama**altında) ile yakalandıysa, her değişiklik olayının bağlamı Visual Studio projenizde hızla çıkarılabilir ve denetlenebilir.

- **API İstatistikleri:** Çerçevenizde API kullanımının üst düzey bir özetini görüntüleyin. Yaptığınız ın farkında olmadığınız aramaları veya çok fazla yaptığınız aramaları keşfetmek için kullanışlıdır. Bu pencere, Visual Studio Graphics **Analyzer'da > API İstatistikleri görüntüle** ile kullanılabilir.

  ![API istatistikleri](media/api-stats.png)

- **Bellek İstatistikleri:** Sürücünün çerçevede oluşturduğunuz kaynaklar için ne kadar bellek ayırdığını görüntüleyin. Bu pencere, **Visual Studio Grafik Analizörü'nde**> Bellek **İstatistikleri Görüntüle** ile kullanılabilir. Veriler, elektronik tabloda görüntülemek için bir CSV dosyasına sağ tıklayarak ve **Tümlerini**Kopyala'yı seçerek kopyalanabilir.

  ![Bellek istatistikleri](media/memory-stats.png)

- **Çerçeve Doğrulama:** Yeni hatalar ve uyarılar listesi, Direct3D hata ayıklama katmanı tarafından algılanan olası sorunlara bağlı olarak etkinlik listenizde gezinmenin kolay bir yolunu sağlar. Pencereyi açmak için Visual Studio Graphics Analyzer'da **Çerçeve Doğrulama>** görüntüleyin'i tıklatın. Ardından çözümlemesi başlatmak için **Doğrulamayı Çalıştır'ı** tıklatın. Çerçevenin karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **D3D12 için Çerçeve Analizi:** Yönlendirilmiş "ne olur" denemeleri ile draw-call performansını analiz etmek için Çerçeve Analizi'ni kullanın. Raporu görüntülemek için Çerçeve Analizi sekmesine geçin ve çözümlemeyi çalıştırın. Daha fazla bilgi için [GoingNative 25: Visual Studio Graphics Frame Analysis](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) videosunu izleyin.

  ![Çerçeve analizi](media/frame-analysis.png)

- **GPU Kullanım Geliştirmeleri:** Açık izlemeler, daha ayrıntılı analiz için GPU Görünümü veya Windows Performans Çözümleyicisi (WPA) aracıyla Visual Studio GPU Kullanım profilleyicisi aracılığıyla alınabilir. Windows Performance Toolkit yüklüyse, biri WPA diğeri GPU Görünümü için olmak üzere iki köprü vardır.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı aracılığıyla GPU Görünümü'nde açılan izler, VS ve GPU View arasındaki zaman çizelgesinde senkronize yakınlaştırmayı ve kaydırmayı destekler. Eşitlemenin etkin olup olmadığını denetlemek için VS'deki bir onay kutusu kullanılır.

  ![GPU Görünümü](media/gpu-view.png)

::: moniker-end

::: moniker range="=vs-2015"

Visual Studio 2015 Update 3 ile yeniliklerin tam listesi için [Visual C++ What's New 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015)bölümüne bakın. Visual Studio 2015'in tümindeki yenilikler hakkında daha fazla bilgi için [Visual Studio 2015 Release Notes History](/visualstudio/releasenotes/vs2015-version-history)ile bağlantılı sürüm notlarına bakın. Visual Studio 2019'da C++ için yenilikler hakkında bilgi için [Visual Studio'da C++ için yeniliklere](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019)bakın. Visual Studio 2017'de C++ için yenilikler hakkında bilgi için [Visual Studio 2017'de C++ için yeniliklere](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017)bakın.

::: moniker-end
