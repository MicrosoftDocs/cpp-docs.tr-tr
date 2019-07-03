---
title: Visual Studio 2017’deki C++ yenilikleri
ms.date: 07/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: f02c5878f5f741c216499f619bfd1392483bfa86
ms.sourcegitcommit: 9b904e490b1e262293a602bd1291a8f3045e755b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/03/2019
ms.locfileid: "67552352"
---
# <a name="whats-new-for-c-in-visual-studio"></a>Visual Studio 2017’deki C++ yenilikleri

::: moniker range=">=vs-2019"

Visual Studio 2019 birçok güncelleştirme ve Microsoft C++ ortamına giderir. Birçok hataları ve derleyici ve Araçları'ndaki sorunları düzelttik. Bu sorunların çoğu, aracılığıyla müşteriler tarafından gönderilen [sorun bildir](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019) ve [bir öneride](https://developercommunity.visualstudio.com/spaces/62/index.html) altında seçenekleri **geri bildirim gönder**. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio'nun tüm yenilikler hakkında daha fazla bilgi için ziyaret [içinde Visual Studio 2019 yenilikler](/visualstudio/ide/whats-new-visual-studio-2019). Yenilikler hakkında bilgi C++ Visual Studio 2017'de bkz [yenilikler C++ Visual Studio 2017'de](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017). Yenilikler hakkında bilgi C++ Visual Studio 2015 veya önceki sürümlerinde, bkz. [Visual C++ 2015 tarihine kadar yeni 2003 nedir](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="c-compiler"></a>C++ derleyicisi

- C ++ 17 özellikleri ve doğruluk düzeltmeleri için gelişmiş destek, ayrıca C ++ 20 özellikleri gibi modülleri ve eş yordamlar için Deneysel destek. Ayrıntılı bilgi için bkz. [Visual Studio 2019'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- `/std:c++latest` Seçeneği artık ilk destekler ve C ++ 20 işleci mutlaka tam olmayan C ++ 20 özellikleri içerir \<= > ("savaş Gemisi") için üç yönlü karşılaştırma.

- C++ Derleyici anahtarı `/Gm` kullanım dışı bırakıldı. Devre dışı bırakmayı deneyin `/Gm` açıkça tanımlanmış olması durumunda derleme betiklerinizde geçin. Ancak, aynı zamanda için kullanımdan kaldırılma uyarısı yok sayabilirsiniz `/Gm`, hata olarak "uyarıları hata olarak değerlendir" kullanırken işlenmez çünkü (`/WX`).

- MSVC C ++ 20 standart taslak altında özelliklerini uygulama başladığında `/std:c++latest` bayrak `/std:c++latest` artık uyumlu olmayan `/clr` (tüm özellikleri) `/ZW`, ve `/Gm`. Visual Studio 2019 ' kullanmak `/std:c++17` veya `/std:c++14` ile derleme yaparken modları `/clr`, `/ZW`, veya `/Gm` (ancak önceki madde işaretinde bakın).

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Gelişmiş analiz ile `/Qspectre` değişken 1 (CVE-2017-5753) Spectre risk azaltma Yardım sağlamak için. Daha fazla bilgi için [Spectre azaltmaları MSVC içinde](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>C++Standart kitaplık iyileştirmeleri

- Ek C ++ 17 ve C ++ 20 kitaplığı özellikleri ve doğruluk uygulaması düzeltir. Ayrıntılı bilgi için bkz. [Visual Studio 2019'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- Clang-Format uygulandıktan C++ geliştirilmiş okunabilirlik için standart kitaplık üstbilgi.

- Visual Studio artık için sadece benim kodumu desteklediğinden C++, standart kitaplık artık için özel makine sağlaması gerekir `std::function` ve `std::visit` aynı etkiyi elde etmek için. Bu makine büyük ölçüde kaldırma, kullanıcıya görünen herhangi bir etkisi vardır. Bir özel durumdur derleyici artık satırında 15732480 veya 16707566, sorunların belirtisi tanılama üretecektir \<type_traits > veya \<değişken >.

## <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Performans/aktarım hızı geliştirmeleri derleyici ve standart kitaplığı

- Derleme Bağlayıcı dosya g/ç işleme dahil olmak üzere, aktarım hızı geliştirmeleri ve PDB birleştirme türü ve oluşturma zamanında bağlayabilirsiniz.

- OpenMP SIMD vektörleştirme için temel desteği eklendi. Yeni derleyici anahtarını kullanarak etkinleştirebilirsiniz `-openmp:experimental`. Bu seçenek ile açıklanan döngüler tanır `#pragma omp simd` potansiyel olarak vektörleştirildi için. Vektörleştirme garanti yoktur ve açıklamalı ancak getirilmemiş döngüleri bildirilen bir uyarı alırsınız. Hiçbir SIMD yan tümceleri desteklenir; Bunlar yoksayılır ve bir uyarı bildirilir.

- Yeni bir satır içi komut satırı anahtarı eklenen `-Ob3`, daha agresif bir sürümü olduğu `-Ob2`. `-O2` (ikili hız için İyileştir) hala gelir `-Ob2` varsayılan olarak. Derleyicinin satır içi kadar agresif değil bulursanız, geçirme göz önünde bulundurun `-O2 -Ob3`.

- Döngüler matematik kitaplığı işlevi ve Tamsayı bölme gibi diğer bazı işlem çağrıları ile elle vektörleştirme desteklemek için kısa vektör/matematik kitaplığı (SVML) iç işlevleri için destek ekledik. Bu işlevler, vektör 128-bit, 256 bit veya 512-bit eşdeğerleri işlem. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - Float hem tamsayı formları için yapı içleri sabiti Katlama ve aritmetik basitleştirme SIMD kullanarak ifadeler için vektör.

  - Her zaman true veya false olarak kanıtlanmış dalları kaldırmak için denetim akışı (if/else/switch deyimleri) bilgi ayıklamak için daha güçlü analiz.

  - Memset SSE2 vektör yönergelerini kullanmanız döngülerin Gelişmiş.

  - Gereksiz struct/class geliştirilmiş kaldırılmasını özellikle değişkeni değer olarak C++ programları için kopyalar.

  - Geliştirilmiş kod kullanmanın en iyi duruma getirme `memmove`, gibi `std::copy` veya `std::vector` ve `std::string` oluşturma.

- Standart kitaplık fiziksel tasarım doğrudan dahil standart kitaplık bölümlerini derleme önlemek için en iyi duruma getirilmiş. Bu değişiklik, yalnızca boş bir dosya, yapı süresini yarıya \<vektör > yarıya. Sonuç olarak eklemeniz gerekebilir `#include` önceden dolaylı olarak dahil edilen üst bilgileri için yönergeleri. Örneğin, kullanan kod `std::out_of_range` artık ihtiyaç duyabilirsiniz `#include <stdexcept>`. Bir akış ekleme operatörü kullanan kod artık eklemeniz gerekebilir `#include <ostream>`. Yalnızca bu çeviri avantajdır gerçekten kullanarak birimlerini \<stdexcept > veya \<ostream > bileşenleri, bunları derlemek için maliyet aktarım hızı ödeme yaparsınız.

- `if constexpr` Daha fazla yerde iyi aktarım hızı ve kopyalama işlemleri, ters ve döndürme gibi permütasyon ve paralel algoritmalar kitaplığı daha az kod boyutu standart Kitaplığı'nda uygulandı.

- Standart kitaplık artık düzenlenmemeli `if constexpr` C ++ 14 modu bile, derleme sürelerini kısaltmak için.

- Çalışma zamanı dinamik bağlama artık algılama paralel algoritma kitaplığı için bir sayfanın tamamını işlevi işaretçisi dizi depolamak için kullanır. Bu bellek salt okunur işaretleme artık güvenlik nedenleriyle ilgili olarak kabul edildi.

- `std::thread`ın Oluşturucusu artık, iş parçacığının başlatılmasını bekler ve artık ekler işlevi çok sayıda katmanları çağrıları arasında temel C Kitaplığı `_beginthreadex` ve sağlanan çağrılabilir nesne. Daha önce `std::thread` 6 işlevler arasında put `_beginthreadex` ve yalnızca 3'e azalır sağlanan çağrılabilir nesne (2 biri olan yalnızca `std::invoke`). Bu değişiklik ayrıca bir belirsiz zamanlama hata çözümler burada bir `std::thread` oluşturucusu, sistem saati tam o anda değiştirdiyseniz vermemesi `std::thread` oluşturulurken.

- İçinde bir performans gerilemesi düzeltildi `std::hash` , uygularken sunduk `std::hash<std::filesystem::path>`.

- Standart kitaplık artık yok ediciler catch blokları çeşitli yerlerde yerine doğruluk elde etmek için kullanır. Bu değişiklik, daha iyi hata ayıklayıcı etkileşiminde sonuçlanır: Gösteri, orijinal olandan oluşturulan olarak throw artık bizim rethrow yerine site özel, etkilenen konumlar standart kitaplıkta aracılığıyla durumlar. Tüm standart kitaplığı catch blokları kaldırıldı; MSVC daha sonraki sürümlerde azaltılmasına catch bloğu bekliyoruz.

- İçinde yetersiz codegen `std::bitset` neden bir noexcept içinde koşullu bir throw tarafından işlevi oluşturma yolu hesaba katacak şekilde tarafından düzeltildi.

- `std::list` Ve `std::unordered_*` ailesinin kullanılacağını hata ayıklama olmayan yineleyiciler dahili olarak daha fazla yerde.

- Birkaç `std::list` üyeleri listesi düğümleri mümkün olduğunda bunları yeniden ayırma ve serbest bırakma yerine yeniden değiştirildi. Örneğin, belirtilen bir `list<int>` , 3, çağrı boyutunu zaten `assign(4, 1729)` artık ilk 3 listesi düğümlerde tamsayılara üzerine yazar ve 1729 değerine sahip yeni bir liste düğümüne ayırır.

- Tüm standart kitaplık çağrıları `erase(begin(), end())` üzere değiştirilmiştir `clear()`.

- `std::vector` artık başlatır ve bazı durumlarda daha verimli bir şekilde öğelerini siler.

- Yapılan geliştirmeler `std::variant` daha iyileştirici kolay, daha iyi içinde elde edilen yapmak için oluşturulan kod. Satır içi kod ile çok daha iyi, artık `std::visit`.

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Canlı Paylaşım C++ desteği

[Paylaşım canlı](/visualstudio/liveshare/) C++, geliştiricilerin gerçek zamanlı olarak işbirliği yapmak için Visual Studio veya Visual Studio Code kullanarak artık desteklemektedir. Daha fazla bilgi için [Live Share C++ ile tanışın: Gerçek zamanlı paylaşım ve işbirliği](https://devblogs.microsoft.com/cppblog/cppliveshare/)

### <a name="intellicode-for-c"></a>Intellicode c++

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

Intellicode tamamlama listenizin en üstünde kullanma olasılığı en koymak için kendi kapsamlı eğitim ve kod Bağlamınızı kullanan bir isteğe bağlı bir uzantısıdır. Genellikle listede aşağı kaydırarak gereksinimini ortadan kaldırabilirsiniz. İçin C++, Intellicode standart kitaplığı gibi popüler kitaplıkları kullanırken en iyi yardım sağlar. Bir iş yükü bileşeni yükleyici olarak kullanılabilir. Daha fazla bilgi için [AI-Assisted kod tamamlama önerileri gelir Intellicode aracılığıyla C++](https://devblogs.microsoft.com/cppblog/cppintellicode/).

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

### <a name="quickinfo-improvements"></a>Quickınfo'da geliştirmeleri

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

Hızlı bilgi araç ipucu artık semantik renklendirme, düzenleyicinin dikkate alır. Ayrıca yeni bir sahip **çevrimiçi Ara** vurgulanan kod yapısı hakkında daha fazla bilgi edinmek çevrimiçi belgeleri arar bağlantı. Kırmızı-kıvrımlı çizgilerle desenler oluşturmaları kodunu hızlı bilgi tarafından sağlanan bağlantıyı hatayı çevrimiçi arama yapar. Bu şekilde tarayıcınıza ileti yeniden gerekmez. Daha fazla bilgi için [Visual Studio 2019 hızlı bilgi iyileştirmeleri: Renklendirme ve çevrimiçi arama](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/).

### <a name="intellicode-available-in-c-workload"></a>Intellicode bulunan C++ iş yükü

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

Intellicode artık birlikte gelen bir isteğe bağlı bir bileşen olarak **ile masaüstü geliştirme C++**  iş yükü. Daha fazla bilgi için [geliştirilmiş C++ Intellicode artık Visual Studio 2019 ile birlikte gelen](https://devblogs.microsoft.com/cppblog/improved-c-intellicode-now-ships-with-visual-studio-2019/).

## <a name="cmake-support"></a>CMake desteği

- CMake 3.14 desteği

- Visual Studio artık CMakeGUI, özelleştirilmiş meta-derleme sistemleri veya cmake.exe kendilerini çağırma derleme betikleri gibi dış araçları tarafından oluşturulan mevcut CMake önbellekleri açabilirsiniz.

- IntelliSense performansı İyileştirildi.

- Yeni bir ayarları Düzenleyicisi CMakeSettings.json dosyayı elle düzenlemeye alternatif sağlar ve CMakeGUI ile bazı eşlik sağlar.

- Visual Studio, Linux makinenizde uyumlu bir CMake sürümü olup olmadığını algılayarak Linux üzerinde CMake ile C++ geliştirmenizin önyüklemesine yardımcı oluyor. Uyumlu bir sürüm yoksa, sizin için yüklemeyi öneriyor.

- CMakeSettings, uyumsuz ayarları eşleşmeyen mimariler veya uyumsuz CMake Oluşturucu ayarları gibi dalgalı çizgiler JSON Düzenleyicisi, hata listesinde hatalar gösterir.

- `vcpkg integrate install` çalıştırıldıktan sonra IDE'de açılmış olan CMake projeleri için vcpkg araç zinciri otomatik olarak algılanıyor ve etkinleştiriliyor. Bu davranış, CMakeSettings'de boş bir araç zinciri dosyası belirtilerek kapatılabilir.

- CMake projeleri artık varsayılan olarak Yalnızca Kendi Kodum hata ayıklamasını etkinleştiriyor.

- CMake projelerinde statik analiz uyarıları şimdi arka planda işlenebiliyor ve düzenleyicide görüntülenebiliyor.

- Daha açık derleme ve 'begin' ve 'end' iletileri için CMake projeleri ve Visual Studio'nun derlemenizin ilerleme durumunu UI desteği yapılandırın. Ayrıca, artık CMake ayrıntı düzeyi ayarından alanında var. **Araçlar > Seçenekler** CMake derleme ve yapılandırma iletilerinin çıkış penceresinde ayrıntı düzeyi özelleştirmek için.

- `cmakeToolchain` Ayarı CMakeSettings.json araç zincirlerinden CMake komut satırı değiştirmeden el ile belirtmek için artık desteklenmektedir.

- Yeni bir **yapı tüm** menüsü kısayolundan **Ctrl + Shift + B**.

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

- Düzenleme, derleme ve hata ayıklama ile Clang/LLVM CMake projeleri için tümleşik destek. Daha fazla bilgi için [Visual Studio'da Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/).

## <a name="linux-and-the-windows-subsystem-for-linux"></a>Linux ve Linux için Windows alt sistemi

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

- Destek [AddressSanitizer (IsObject)](https://github.com/google/sanitizers/wiki/AddressSanitizer) Linux ve CMake platformlar arası projelerinde. Daha fazla bilgi için [AddressSanitizer (IsObject) Visual Studio 2019 Linux iş yükü için](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/).

- Tümleşik Visual Studio kullanma desteği C++ Linux (WSL) için Windows alt sistemi ile. Daha fazla bilgi için [ C++ Visual Studio 2019 ve Windows alt sistemi için Linux (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

## <a name="incredibuild-integration"></a>IncrediBuild tümleştirme

İsteğe bağlı olarak IncrediBuild dahildir **ile masaüstü geliştirme C++**  iş yükü. IncrediBuild yapı izleme, Visual Studio IDE içinde tamamen tümleşiktir. Daha fazla bilgi için [IncrediBuild'ın yapı İzleyici ve Visual Studio 2019 yapı görselleştirme](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/).

## <a name="debugging"></a>Hata Ayıklama

- Windows üzerinde çalışan C++ uygulamaları için PDB dosyalarını ayrı bir 64 bit işlemde şimdi yükleyin. Bu değişiklik, bir dizi kilitlenme nedeniyle bellek yetersiz sayıda modüller ve PDB dosyaları içeren uygulamalar hata ayıklama sırasında çalışan hata ayıklayıcı tarafından yöneliktir.

- Arama etkin **Watch**, **Otolar**, ve **Yereller** windows.

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme

- Bu C++ ATL/MFC sihirbazları artık kullanılabilir:

  - ATL COM+ 1.0 Bileşeni Sihirbazı
  - ATL Active Server Pages bileşeni Sihirbazı
  - ATL OLE DB sağlayıcısı Sihirbazı
  - ATL Özellik Sayfası Sihirbazı
  - ATL OLE DB Tüketicisi Sihirbazı
  - MFC ODBC Tüketicisi
  - ActiveX denetiminden MFC sınıfı
  - Tür kitaplığı kitaplığından MFC sınıfı.

  Bu teknolojiler için örnek kod Microsoft Docs ve VCSamples GitHub deposunu arşivlenir.

- Windows 8.1 SDK'sı artık Visual Studio yükleyicisinde sağlanmıyor. C++ projelerinizin en son Windows 10 SDK'sı için yükseltmeniz önerilir. 8\.1 sabit bir bağımlılık varsa, Windows SDK'sı arşivden indirebilirsiniz.

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

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 16.1 sürümü

- Yeni Hızlı düzeltmeler için değişken denetimleri başlatılmamış. Daha fazla bilgi için [başlatılmamış belleği (C6001) ve init (C26494) uyarıları kullanılabilmesi için yeni kod analizi hızlı düzeltmeler](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/).

## <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Yönetilen C++ Test Çerçevesi mevcut projelerinizi kullanmaya devam edebilirsiniz. Yeni birim testleri için Visual Studio sağlayan şablonlar (MSTest, Google Test) ya da yönetilen yerel test çerçevelerini kullanarak göz önünde bulundurun C# Test proje şablonu.

::: moniker-end

::: moniker range="=vs-2017"

Visual Studio 2017 birçok güncelleştirme ve C++ ortamına giderir. Biz 250'den fazla hatalar düzeltildi ve bildirilen sorunları derleyici ve araçları, aracılığıyla müşteriler tarafından birçok gönderilen [sorun bildirin ve bir öneride](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2017) altında seçenekleri **geri bildirim gönder**. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio'nun tüm yenilikler hakkında daha fazla bilgi için bkz: [Visual Studio 2017'deki yenilikler](/visualstudio/ide/whats-new-visual-studio-2017?view=vs-2017). Yenilikler hakkında bilgi C++ Visual Studio 2019 ' bkz [yenilikler C++ Visual Studio'daki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019). Yenilikler hakkında bilgi C++ Visual Studio 2015 veya önceki sürümlerinde, bkz. [Visual C++ 2015 tarihine kadar yeni 2003 nedir](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++ uyumluluk geliştirmeleri

Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için bkz. [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Derleyici, yaklaşık %75 yapılandırılmış bağlamalar dahil olmak üzere C ++ 17'de yeni özellikleri destekler `constexpr` lambda ifadeleri, `if constexpr`, satır içi değişkenler, katlama ifadeleri ve ekleme `noexcept` tür sistemine. Bu özellikler altında kullanılabilir **/Std: c ++ 17** seçeneği. Daha fazla bilgi için [Visual Studio 2017'deki C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

Visual Studio'da sürüm 15.7 MSVC derleyici araç takımı artık C++ standardı ile uyumludur. Daha fazla bilgi için [Announcing: MSVC C++ standartlarına uyup](https://devblogs.microsoft.com/cppblog/announcing-msvc-conforms-to-the-c-standard/) ve [Microsoft C++ dil uyumluluğu](../visual-cpp-language-conformance.md).

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [/ permissive-](../build/reference/permissive-standards-conformance.md): Tüm katı standartlar uyumluluk derleyici seçenekleri etkinleştirin ve çoğu özel Microsoft derleyici uzantılarını devre dışı bırak (ama `__declspec(dllimport)`, örneğin). Bu seçenek varsayılan olarak Visual Studio 2017 sürüm 15.5 açıktır.  **/ Permissive-** uyumluluk modu, iki aşamalı ad aramayı için destek içerir. Daha fazla bilgi için [Visual Studio'da C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- [/ Diagnostics](../build/reference/diagnostics-compiler-diagnostic-options.md): Satır numarası, satır numarası ve sütun veya satır numarasını ve sütun ve şapka işareti tanılama hata veya uyarı bulunduğu kod satırının altında görüntülenmesini sağlar.

- [/debug:fastlink](../build/reference/debug-generate-debug-info.md): Etkinleştirme % 30 daha hızlı artımlı bağlantı süreleri (vs. Visual Studio 2015) değil kopyalayarak tüm PDB dosyasına hata ayıklama bilgileri. PDB dosyası, yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplığı dosyaları için hata ayıklama bilgileri için bunun yerine işaret eder. Bkz: [daha hızlı C++ derleme/debug: fastlink ile VS "15" döngüsünde](https://devblogs.microsoft.com/cppblog/faster-c-build-cycle-in-vs-15-with-debugfastlink/) ve [derlemeler Visual Studio'da C++ önerileri hızına](https://devblogs.microsoft.com/cppblog/recommendations-to-speed-c-builds-in-visual-studio/).

- Visual Studio 2017 sağlayan kullanarak [/SDL](../build/reference/sdl-enable-additional-security-checks.md) ile [/ await](../build/reference/await-enable-coroutine-support.md). Kaldırdık [/RTC](../build/reference/rtc-run-time-error-checks.md) eş yordamlar sınırlama.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- [/ Std: c ++ 14 ve/Std: c ++ Son](../build/reference/std-specify-language-standard-version.md): Bu derleyici seçeneklerinin ISO belirli sürümleri için katılım etkinleştirmeniz C++ programlama dilinde bir proje. Standart özellikler tarafından korunan yeni taslak çoğu **/Std: c ++ Son** seçeneği.

- [/ Std: c ++ 17](../build/reference/std-specify-language-standard-version.md) derleyici tarafından uygulanan C ++ 17 özellikleri kümesini sağlar. Bu seçenek, C ++ 17 sonra derleyici ve değiştirilen özellikler veya yeni sürümlerinde C++ standart çalışma taslak ve hata güncelleştirmeleri standart kitaplığı desteği devre dışı bırakır. Bu özellikleri etkinleştirmek için **/Std: c ++ Son**.

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Bu sürüm, iyileştirme, kod oluşturma, araç takımı sürümü oluşturma ve tanılama çeşitli iyileştirmeler getirir. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: Otomatik vektörleştirme sabit tamsayı, memset desenlerinin daha iyi kimlik için destek.
- Geliştirilmiş kod güvenliği: Geliştirilmiş arabellek taşma derleyici Tanılaması, arabellek ve [/Guard: cf](../build/reference/guard-enable-control-flow-guard.md) artık atlama tablosu oluşturan deyimleri cf switch.
- Sürüm oluşturma: Yerleşik önişlemci makrosu değerini  **\_MSC\_VER** şu anda tekdüze her Visual C++ araç takımı güncelleştirmeyi güncelleştiriliyor. Daha fazla bilgi için [Visual C++ Derleyici sürümü](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/).
- Yeni araç takımı düzeni: Derleyici ve ilgili derleme araçları, geliştirme makinenizde yeni bir konum ve dizin yapısı sahip. Yeni düzen derleyici birden çok sürümünü yan yana yüklemesini sağlar. Daha fazla bilgi için [Visual Studio 2017 derleme araçları Düzen](https://devblogs.microsoft.com/cppblog/compiler-tools-layout-in-visual-studio-15/).
- Gelişmiş Tanılama: Çıkış penceresi bir hata oluştuğu sütunu artık gösterir. Daha fazla bilgi için [C++ Derleyici tanılama geliştirmeleri VS "15" Preview 5](https://devblogs.microsoft.com/cppblog/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Deneysel anahtar sözcüğü ortak yordamlar kullanılırken **yield** (altında kullanılabilir **/ await** seçeneği) kaldırıldı. Kodunuzu kullanacak şekilde güncelleştirilmesi `co_yield` yerine. Daha fazla bilgi için [ `yield` olacak anahtar sözcüğü `co_yield` VS 2017'de](https://devblogs.microsoft.com/cppblog/yield-keyword-to-become-co_yield-in-vs-2017/).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

Ek derleyici tanılama iyileştirmeleri. Daha fazla bilgi için [Visual Studio 2017 ' 15.3.0 tanılama geliştirmeleri](https://devblogs.microsoft.com/cppblog/diagnostic-improvements-in-vs2017-15-3-0/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Visual C++ çalışma zamanı performans nedeniyle daha iyi oluşturulan kod kalitesini iyileştirmeye devam eder. Artık yalnızca kodunuzu derleyebilirsiniz ve uygulamanızı daha hızlı çalışır. Derleyici iyileştirmelerini bazıları yepyeni, koşullu skaler depoları, birleştirme çağrılarının vektörleştirme gibi `sin(x)` ve `cos(x)` içine yeni bir `sincos(x)`ve yedekli SSA İyileştiricisine ilişkin yönergeleri saydamlığından. Diğer derleyici iyileştirmeleri koşullu ifadeler, daha iyi döngü en iyi duruma getirme ve float min/maks codegen vektör hale getirici buluşsal yöntemler gibi mevcut işlevine geliştirmeleridir. Yeni bir ve daha hızlı bağlayıcı sahip **/OPT: ICF** uygulaması 9 adede kadar % bağlama zamanı hızlanma sonuçlanabilir ve başka bir diğer performans düzeltmeleri artımlı bağlama. Daha fazla bilgi için [OPT (iyileştirmeler)](../build/reference/opt-optimizations.md) ve [/Incremental (artımlı bağlantı)](../build/reference/incremental-link-incrementally.md).

Microsoft C++ derleyici Intel AVX-512 AVX-512 ile birlikte 128-bit ve 256 bit genişliğinde kayıtlara yönelik yeni işlevler getiren sunan vektör uzunluğu yönergeleri de dahil olmak üzere, destekler.

[/Zc:noexceptTypes-](../build/reference/zc-noexcepttypes.md) seçeneği, C ++ 14 sürümüne geri almak için kullanılabilir `noexcept` genel C ++ 17 modunda kullanırken. Bu seçenek, tüm yeniden yazmak zorunda kalmadan C ++ 17'ye uyması için kaynak kodunuzu güncelleştirmenizi sağlar, `throw()` aynı zamanda kod. Daha fazla bilgi için [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements.md#noexcept_removal).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- Yeni derleyici anahtarı [/qspectre](../build/reference/qspectre.md) kurgusal yürütme yan kanal saldırıları önlemeye yardımcı olmak için. Daha fazla bilgi için [Spectre azaltmaları MSVC içinde](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).
- Spectre risk azaltma için yeni tanılama uyarı. Daha fazla bilgi için [Spectre Visual Studio 2017 sürüm 15.7 Önizleme 4'te tanılama](https://devblogs.microsoft.com/cppblog/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/).
- /Zc için yeni bir değer **/ZC: __cplusplus**, etkinleştirir düzeltin, Raporlama C++ standart destek. Örneğin, ne zaman geçiş ayarlanmışsa ve derleyici/Std: c ++ 17 modunda değeri genişletilir **201703 L**. Daha fazla bilgi için [MSVC artık __cplusplus doğru şekilde rapor](https://devblogs.microsoft.com/cppblog/msvc-now-correctly-reports-__cplusplus/).

## <a name="c-standard-library"></a>C++Standart Kitaplığı

### <a name="correctness-improvements"></a>Doğruluk geliştirmeleri

##### <a name="visual-studio-2017-rtm-version-150"></a>Visual Studio 2017 RTM (sürüm 15.0)

- Küçük `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` tanılama geliştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- Sabit `std::promise` taşıma atama işlecini daha önce kod engellenmesine neden olabilir.
- Derleyici hataları düzeltildi `atomic<T*>` örtük olarak dönüştürülmesine `T*`.
- `pointer_traits<Ptr>` artık doğru şekilde algılıyor `Ptr::rebind<U>`.
- Eksik bir sabit `const` niteleyicisi `move_iterator` çıkarma işleci.
- İsteyen durum bilgisi olan kullanıcı tanımlı ayırıcılar için sessiz hatalı codegen düzeltildi `propagate_on_container_copy_assignment` ve `propagate_on_container_move_assignment`.
- `atomic<T>` artık göstereceği aşırı `operator&()`.
- Biraz daha geliştirilmiş derleyici tanılama için yanlış `bind()` çağırır.

Visual Studio 2017 RTM standart kitaplık iyileştirmeleri tam bir listesi için bkz. C++ Team Blog girişine [standart kitaplığı düzeltmeleri, VS 2017 RTM'de](https://devblogs.microsoft.com/cppblog/stl-fixes-in-vs-2017-rtm/).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Standart Kitaplığı kapsayıcıları artık clamp kendi `max_size()` için `numeric_limits<difference_type>::max()` yerine `max()` , `size_type`. Bu değişikliğin sonucu sağlar `distance()` yineleyiciler bu kapsayıcısından dönüş türü içinde gösterilebilir olan `distance()`.
- Eksik özelleştirmesi sabit `auto_ptr<void>`.
- `for_each_n()`, `generate_n()`, Ve `search_n()` algoritmaları daha önce başarısız uzunluk değişkeni integral türünde değildi derlemeniz; bunlar artık yineleyicileriyle tamsayı olmayan uzunlukları dönüştürmeyi denemeden `difference_type`.
- `normal_distribution<float>` kaydırmak için uyarıları içinde çift daraltma hakkında standart kitaplık artık yayar.
- Bazı sabit `basic_string` kullanılan işlemleri `npos` yerine `max_size()` için en büyük boyutu taştı denetlenirken.
- `condition_variable::wait_for(lock, relative_time, predicate)` sahte Uyandırma söz konusu olduğunda tüm göreli süre beklemeniz gerekir. Artık, yalnızca bir tek göreli zaman aralığı için bekler.
- `future::get()` artık geçersiz kılar `future`gibi standart gerektirir.
- `iterator_traits<void *>` Forma çalıştığı için bir donanım hatası kullanılan `void&`; artık düzgün bir şekilde kullanımına olanak tanımak için boş bir yapı olur `iterator_traits` "yineleyici olduğunu" SFINAE koşulları.
- Bazı uyarılar bildirdi Clang tarafından **- Wsystem-headers** düzeltilmiştir.
- Ayrıca "özel durum belirtimi bildiriminde önceki bildirimi Clang tarafından bildirilen eşleşmiyor" sabit **- Wmicrosoft özel durum belirtimi**.
- Clang C1XX tarafından bildirilen ve bellek başlatıcı listesi sıralama uyarıları da düzelttik.
- Kapsayıcıları değiştirildi, sırasız karma işlevlerinin veya koşulları takas kaydetmedi. Bunlar şimdi yapın.
- Çok sayıda kapsayıcı değiştirme işlemleri artık işaretlendi `noexcept` (standart kitaplığımızı hiçbir zaman bir özel dışı tespit edilirken durum amaçlayan gibi`propagate_on_container_swap` eşit ayırıcı olmayan tanımsız davranış koşul).
- Birçok `vector<bool>` işlemleri artık işaretlenmiş `noexcept`.
- Standart kitaplık artık eşleşen ayırıcı zorlar `value_type` (, C ++ 17 modunda) ile bir geri çevirme kaçış noktası.
- Bazı koşullar self range INSERT burada içine sabit `basic_string` dizeleri içeriğini karıştırmak. (Not: self-range-insert into'nun vektörleri hala standart tarafından kullanılamaz.)
- `basic_string::shrink_to_fit()` ayırıcı tarafından 's artık etkilenir `propagate_on_container_swap`.
- `std::decay` artık tanıtıcıları abominable işlev türleri, diğer bir deyişle, cv nitelenmiş ve/veya ref koşullu türlere işlev.
- Değiştirilen doğru büyük/küçük harf duyarlılığı ve taşınabilirlik geliştirme eğik kullanmak için yönergeleri içerir.
- Uyarı C4061 sabit "Numaralandırıcı '*Numaralandırıcı*'numaralandırıcısının switch' ın*numaralandırma*' case etiketi tarafından açıkça işlenmiyor". Bu uyarı devre dışı varsayılan olarak ve standart kitaplık Genel İlke Uyarıları için bir özel durum olarak düzeltildi. (Standart kitaplık **/W4** temizlemek, ancak olmasını çalışmaz **/Wall** temiz. Çok sayıda kapalı varsayılan olarak uyarı çok gürültülü ve düzenli olarak kullanılmaya yönelik değildir.)
- Geliştirilmiş `std::list` hata ayıklama denetler. Liste yineleyiciler şimdi onay `operator->()`, ve `list::unique()` artık yineleyiciler geçersiz olarak işaretler.
- Ayırıcı olarak azaltılarak kullanan sabit `tuple`.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `std::partition` artık aramalar standart koşul N kez yerine N + 1 kez gerektirir.
- Sürüm 15.5 sürüm 15.3 Sihirli İstatistikler önlemek için deneme onarıldı.
- `std::atomic<T>` artık gerektirmez `T` atmamalıdır varsayılan olarak kullanılacak.
- Artık Logaritmik zaman yığın algoritmaları yineleyici hata ayıklama etkinleştirildiğinde giriş aslında yığın olduğunu bir doğrusal zaman onaylama işlemi yapın.
- `__declspec(allocator)` artık bu declspec anlamıyor Clang, gelen uyarıları önlemek yalnızca C1XX için korunur.
- `basic_string::npos` bir derleme zamanı sabiti kullanıma sunulmuştur.
- `std::allocator` doğru aşırı hizalanmış türlere tanıtıcıları ayrılması hizalamasını diğer bir deyişle, türleri artık C ++ 17 modunda büyüktür `max_align_t`devre dışı sürece **/Zc:alignedNew-** .  Örneğin, 16 bayt veya 32 bayt hizalama nesneleriyle vektörleri artık düzgün şekilde için SSE ve AVX yönerge hizalanır.

### <a name="conformance-improvements"></a>Uyumluluk geliştirmeleri

- Eklediğimiz \<herhangi\>, \<string_view\>, `apply()`, `make_from_tuple()`.
- Eklenen \<isteğe bağlı\>, \<değişken\>, `shared_ptr::weak_type`, ve \<cstdalign\>.
- C ++ 14 etkin `constexpr` içinde `min(initializer_list)`, `max(initializer_list)`, ve `minmax(initializer_list)`, ve `min_element()`, `max_element()`, ve `minmax_element()`.

Daha fazla bilgi için [Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Birkaç ek C ++ 17 özellikleri uygulanmıştır. Daha fazla bilgi için [Visual C++ dil uyumluluğu](cpp-conformance-improvements.md#improvements_153).
- Uygulanan P0602R0 "değişken ve isteğe bağlı kopyalama/taşıma triviality yayılması".
- Standart kitaplık artık resmi olarak aracılığıyla devre dışı bırakılmasını dinamik RTTI göstereceği [denetleyen](../build/reference/gr-enable-run-time-type-information.md) seçeneği. Her ikisi de `dynamic_pointer_cast()` ve `rethrow_if_nested()` kendiliğinden gerektiren `dynamic_cast`, standart kitaplık artık olarak işaretler `=delete` altında **denetleyen**.
- Hatta, dinamik RTTI aracılığıyla devre dışı bırakıldı **denetleyen**, "statik RTTI" biçiminde `typeid(SomeType)` hala kullanılabilir ve birkaç standart kitaplık bileşeni güçlendirir. Standart kitaplık artık, bu özelliği devre dışı bırakma destekler aracılığıyla **/D\_HAS\_statik\_RTTI = 0**. Bu bayrak de devre dışı bırakır `std::any`, `target()` ve `target_type()` üye işlevleri `std::function`ve `get_deleter()` arkadaş üye işlevinin `std::shared_ptr` ve `std::weak_ptr`.
- Standart kitaplık artık C ++ 14 kullanan `constexpr` koşulsuz olarak, koşullu olarak tanımlı makroları yerine.
- Standart kitaplık artık diğer ad şablonları dahili olarak kullanır.
- Standart kitaplık artık kullanan `nullptr` dahili olarak yerine, `nullptr_t{}`. (İç kullanım null eradicated. İç kullanım 0 olarak null kademeli olarak Temizlenen.)
- Standart kitaplık artık kullanan `std::move()` stylistically kötüye yerine dahili olarak `std::forward()`.
- Değiştirilen `static_assert(false, "message")` için `#error message`. Bu değişiklik derleyici tanılaması için artırır `#error` derleme hemen durdurur.
- Standart kitaplık artık işlev olarak işaretler `__declspec(dllimport)`. Modern bağlayıcı teknolojisi, artık bunu gerektirmez.
- Ayıklanan SFINAE dağınıklığı dönüş türleri ve işlev bağımsız değişken türleri ile karşılaştırıldığında sınırlı varsayılan şablon bağımsız için.
- Hata ayıklama iade \<rastgele\> artık standart kitaplığının her zamanki makineler yerine iç işlevini kullanın `_Rng_abort()` olarak adlandırılan `fputs()` için **stderr**. Bu işlevin uygulama ikili uyumluluk için tutulmaktadır, ancak standart Kitaplığı'nın sonraki ikili uyumsuz sürümünde kaldırılmıştır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Birçok standart kitaplık özellikleri eklenmiş, kullanım dışı veya C ++ 17 uygun olarak standart kaldırıldı. Daha fazla bilgi için [ C++ Visual Studio'da uyumluluk geliştirmeleri](cpp-conformance-improvements.md#improvements_155).
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

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- \<memory_resource >
- Kitaplık temelleri V1
- Silme `polymorphic_allocator` atama
- Sınıf şablonu bağımsız değişkeni kesintisi geliştirme

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- paralel algoritmalar artık için Deneysel desteği
- Yeni bir uygulamasını \<filesystem >
- temel dize dönüştürme (kısmi)
- `std::launder()`
- `std::byte`
- `hypot(x,y,z)`
- gereksiz decay kaçınma
- Özel matematik işlevleri
- `constexpr char_traits`
- Standart kitaplık için çıkarım kılavuzları

Daha fazla bilgi için [Visual C++ dil uyumluluğu](../visual-cpp-language-conformance.md).

### <a name="performance-and-throughput-fixes"></a>Performans ve aktarım hızı düzeltmeleri

- Yapılan `basic_string::find(char)` yalnızca çağrı aşırı `traits::find` sonra. Daha önce 1 uzunluğunda bir dizenin genel dize araması olarak uygulanıyordu.
- `basic_string::operator==` artık dizelerin içeriklerini karşılaştırmadan önce dizenin boyutunu denetler.
- İçinde zorlandığı denetim ilişkilendirme kaldırıldı `basic_string`, analiz etmek için derleyici iyileştiricisi zor olduğu. Çağırarak tüm kısa dizeler için `reserve` hala hiçbir şey yapma sıfır olmayan bir maliyeti vardır.
- `std::vector` doğruluk ve performans açısından bakımdan geçirildi: diğer ad kullanımı sırasında yerleştirin ve işlemleri emplace olan standart tarafından gerekli olarak doğru bir şekilde ele artık güçlü özel durum garantisi artık standart tarafından gerekli olduğunda sağlanan `move_if_noexcept()` ve diğer mantığı ekleyin ve emplace daha az öğe işlemi gerçekleştirin.
- C++ Standart kitaplık artık kaçınır null karmaşık işaretçilere başvurmaktan.
- Geliştirilmiş `weak_ptr::lock()` performans.
- Derleyici verimliliğini artırmak için C++ standart kitaplığı üst bilgileri artık önlemek için gerekli olmayan derleyici iç bilgileri bildirimi dahil olmak üzere.
- Performansı geliştirildi `std::string` ve `std::wstring` taşıma oluşturucuları üçten fazla sürelerine göre.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Etkileşim etrafında çalışılan `noexcept` inlining'i engelleyen `std::atomic` yapılandırılmış özel durum işleme (SEH) kullanan bir işlev uygulamasına.
- Standart kitaplık iç değiştirilen `_Deallocate()` daha fazla yerde eklenmesini izin veren, daha küçük bir kodun içine iyileştirmek için işlevi.
- Değiştirilen `std::try_lock()` paket genişletmesi özyineleme yerine kullanılacak.
- Geliştirilmiş `std::lock()` kullanılacak kilitlenme kaçınma algoritmasını `lock()` işlemleri üzerinde dönen yerine `try_lock()` kilitleri üzerinde.
- Adlı dönüş değeri iyileştirme etkin `system_category::message()`.
- `conjunction` ve `disjunction` N + 1 türleri, 2N + 2 türleri yerine örneği şimdi oluşturun.
- `std::function` artık her tür silinmiş çağrılabilir, iyileştirme aktarım hızı ve geçirmek için birçok farklı lambdalar programlarda azalan .obj boyutu ayırıcı desteği makineler başlatır `std::function`.
- `allocator_traits<std::allocator>` el ile satır içine alınmış içeren `std::allocator` etkileşimde kodda kod boyutunu küçültme işlemlerini `std::allocator` aracılığıyla `allocator_traits` yalnızca (diğer bir deyişle, içinde çoğu kod).
- C ++ 11 minimal ayırıcılar arabiriminin artık standart Kitaplığı arama tarafından işlenen `allocator_traits` bir iç sınıf ayırıcısı sarmalama yerine doğrudan `_Wrap_alloc`. Bu değişiklik ayırıcı desteği için oluşturulan kod boyutunu azaltır, bazı durumlarda standart kitaplığı kapsayıcıları hakkında neden iyileştirici'nin olanağı artırır ve daha iyi hata ayıklama deneyimi sağlar (artık, ayırıcı türü yerine gördüğünüz`_Wrap_alloc<your_allocator_type>`hata ayıklayıcısı).
- Özelleştirilmiş azaltılarak kaldırıldı `allocator::reference`, hangi ayırıcılar gerçekten izin verilmiyor özelleştirmek için. (Ayırıcılar karmaşık işaretçilere başvurmaktan ancak değil başvurmaktan başvuruları kapsayıcıları yapabilirsiniz.)
- Derleyici ön uç hata ayıklama yineleyiciler açılacak verilen de aralık tabanlı for döngüleri, hata ayıklama performansını iyileştirme oluşturur.
- `basic_string` İç küçültme yolu `shrink_to_fit()` ve `reserve()` artık mutating tüm üyeler için kod boyutunu küçültme işlemlerini tahsis yolunda değil.
- `basic_string` İç Büyüt yoldur artık yolunda `shrink_to_fit()`.
- `basic_string` Diziyi operations artık hızlı yolu olmayan ayırma ve çağıranlar eklenmesini sağlamak ve ortak Hayır yeniden ayırma çalışması için büyük olasılıkla yapma, ayırma yavaş yola işlevleri factored.
- `basic_string` Yerinde yeniden boyutlandırma yerine yapısı bir arabellek istenen durumda yeniden artık operations diziyi. (Örneğin, başında bir dize artık ekleme içeriği ekleme (aşağı veya yeni ayrılan arabelleğin), sonra tam bir kez yerine iki kez reallocating durumda yeni ayrılan arabelleğin ve sonra aşağı) taşır.
- Standart C Kitaplığı arayan operations \<dize\> artık önbelleğe `errno` TLS ile yinelenen etkileşimleri kaldırmak için adres.
- Basitleştirilmiş `is_pointer` uygulaması.
- İşlev tabanlı ifade SFINAE için değiştirme işlemi tamamlandı `struct` ve `void_t`-tabanlı.
- Algoritmalar standart kitaplık artık yineleyiciler postincrementing kaçının.
- 32-bit ayırıcılar 64-bit sistemlerde kullanırken sabit kesilmesi uyarıları.
- `std::vector` taşıma ataması artık mümkün olduğunda arabellek yeniden kullanarak POCMA olmayan eşit ayırıcı durumda daha verimli olur.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- `basic_string<char16_t>` artık aynı ilgilenir `memcmp`, `memcpy`ve benzer iyileştirmeler, `basic_string<wchar_t>` ilgilenir.
- Engeller işlev işaretçileri satır içine alınmış engelledi, "işlevleri kopyalamama" İşimizi Visual Studio 2015 güncelleştirme 3 açığa, çevresinde, geri yükleme performansını çalışmıştır bir iyileştirici sınırlaması `lower_bound(iter, iter, function pointer)`.
- Yineleyici hata ayıklama ek yükü girişleri siparişi doğrulaması kullanıcının `includes`, `set_difference`, `set_symmetric_difference`, ve `set_union` açma yineleyiciler tarafından sipariş denetlemeden önce düşürüldü.
- `std::inplace_merge` artık konumda zaten olan öğeler üzerinden atlar.
- Oluşturma `std::random_device` artık oluşturur ve ardından yok eder bir `std::string`.
- `std::equal` ve `std::partition` kaydeden bir yineleyici karşılaştırma atlama iş parçacığı oluşturma en iyi duruma getirme geçiş vardı.
- Zaman `std::reverse` işaretçileri için artık önemsiz olarak kopyalanabilir geçirilen `T`, artık el ile yazılmış bir vektör haline getirilmiş uygulamasına gönderir.
- `std::fill`, `std::equal`, ve `std::lexicographical_compare` gönderilmesi için nasıl verilen `memset` ve `memcmp` için `std::byte` ve `gsl::byte` (diğer char benzeri sabit listeleri ve enum sınıfları). Bu yana `std::copy` kullanarak dağıtır `is_trivially_copyable`, herhangi bir değişiklik ihtiyacım kalmadı.
- Standart kitaplık artık, tür olmayan-basit bir şekilde-yıkıcı yapmak, yalnızca bir davranış olduğu boş küme ayraçları Yıkıcılar içerir.

## <a name="other-libraries"></a>Diğer kitaplıkları

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg** alınıyor ve açık kaynak oluşturma işlemini büyük ölçüde basitleştiren bir açık kaynak komut satırı aracıdır C++ statik kitaplıklar ve Visual Studio'da DLL'ler. Daha fazla bilgi için [vcpkg: C++ için Paket Yöneticisi](../build/vcpkg.md).

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0'da

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

C++, platformlar arası web API'si CPPRestSDK 2.9.0'da sürümüne güncelleştirildi. Daha fazla bilgi için [CppRestSDK 2.9.0'da Github'da kullanılabilir](https://devblogs.microsoft.com/cppblog/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Henüz başka bir ad arama uyumluluğu düzeltmeleri kümesi
- Mevcut taşıma oluşturucuları ve taşıma atama işleçleri artık doğru biçimde olarak oluşturmayan işaretlendi
- İş parçacığı güvenli atlstr.h'de yerel statiklerin yönelik baskılamayı kaldırma ilgili C4640 geçerli uyarı unsuppress
- Yerel statiklerin iş parçacığı açısından güvenli başlatma otomatik olarak XP araç kümesinde ATL DLL oluşturmak için kullanırken kapatıldı, ancak artık böyle değildir. Ekleyebileceğiniz **/ZC: threadsafeınit** devre dışı iş parçacığı açısından güvenli başlatma olması isteniyorsa proje ayarlarınızda.

### <a name="visual-c-runtime"></a>Visual C++ çalışma zamanı

- Yeni üstbilgi denetim akışı koruyucusu sembolleri için "cfguard.h".

## <a name="c-ide"></a>C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Bir çözüm yapılandırması ilk defa etkinleştirildiğinde, artık bunu daha hızlı olacak ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında olacaktır.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf ekleme** artık doğrudan Sınıf Ekle sihirbazını başlatır. Diğer öğeler daha önce burada olan tüm artık altında kullanılabilir **Ekle > Yeni öğe**.
- Win32 projeleri kullanıma altında **Windows Masaüstü** kategorisinde **yeni proje** iletişim.
- **Windows Konsolu** ve **masaüstü uygulaması** şablonları hemen bir sihirbaz görüntülemeden proje oluşturun. Yeni bir **Windows Masaüstü Sihirbazı'nı** eski aynı seçenekleri görüntüleyen aynı kategori altında **Win32 konsol uygulaması** Sihirbazı.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

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

- Üye listesinde görünür bağlam filtrelemeyi sağlayan yeni bir Deneysel Tahmine dayalı IntelliSense özelliği eklendi. Daha fazla bilgi için [ C++ IntelliSense geliştirmeleri - Tahmine dayalı IntelliSense'i & filtreleme](https://devblogs.microsoft.com/cppblog/c-intellisense-improvements-predictive-intellisense-filtering/).
- **Tüm başvuruları Bul** (Shift + yardımcı olur, raporlamanızı kolayca bile karmaşık kod tabanlarında artık F12). Gelişmiş gruplandırma, filtreleme, sıralama, (için bazı diller için) ve sonuçları içinde arama sağlar, böylece, başvurularınızı NET bir anlayış renklendirme. İçin C++, yeni kullanıcı Arabirimi olup olmadığını biz okuma veya yazma için bir değişken hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyici özelliklerini **kapsamları genişletme** ve **önceliği genişletme** de gelen için Deneysel Gelişmiş taşınmıştır.
- Deneysel yeniden düzenleme özellikleri **değişiklik imzası** ve **işlevi ayıklama** varsayılan olarak kullanıma sunulmuştur.
- Deneysel 'Hızlı Proje Yükleme' özelliği için eklenen C++ projeleri. Bir sonraki açışınızda bir C++ projesi daha hızlı yüklenecektir ve BT'nin yükleyecek sonra zaman *çok* daha hızlı!
- Bu özelliklerin bazıları diğer diller için ortaktır ve C++ için belirli bazılarıdır. Bu yeni özellikler hakkında daha fazla bilgi için bkz. [Duyurusu Visual Studio "15" Preview 5](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-15-preview-5/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- Destek için ClangFormat eklendi. Daha fazla bilgi için [Visual Studio 2017'de ClangFormat desteği](https://devblogs.microsoft.com/cppblog/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>MSBuild dışındaki projeleriyle klasörü aç

Visual Studio 2017'yi tanıtır **Klasör Aç** kodlayın, oluşturun ve bir klasördeki tüm çözümlerin veya projelerin oluşturmaya gerek olmadan kaynak kodu içeren hata ayıklama olanak tanıyan özellik. Artık projenize bir MSBuild tabanlı proje olmasa bile Visual Studio ile çalışmaya başlamak çok daha kolaydır. İle **Klasör Aç**, güçlü kod anlama, düzenleme, derleme ve hata ayıklama Visual Studio MSBuild projeleri için zaten sağlayan özelliklerini erişim elde edersiniz. Daha fazla bilgi için [C++ açık klasörü projelerde](../build/open-folder-projects-cpp.md).

- Klasör Aç deneyimi geliştirmeleri. Bu .json dosyaları deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Alternatif derleyicileri ve MinGW ve Cygwin gibi yapı ortamları için geliştirilmiş destek. Daha fazla bilgi için [kullanarak MinGW ve Cygwin Visual C++ ve klasör Aç](https://devblogs.microsoft.com/cppblog/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
- Genel ve yapılandırmaya özgü ortam değişkenlerini CMakeSettings.json CppProperties.json de tanımlamak için destek eklendi. Bu ortam değişkenleri, launch.vs.json ve tasks.vs.json Görevler içinde tanımlanan hata ayıklama yapılandırmaları tarafından tüketilebilir. Daha fazla bilgi için [Visual C++ ve klasör Aç ortamınızla özelleştirme](https://devblogs.microsoft.com/cppblog/customizing-your-environment-with-visual-c-and-open-folder/).
- 64 bit platformlarını kolayca hedefleme yeteneği de dahil olmak üzere, CMake Ninja oluşturucusunu için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Klasör Aç üzerinden CMake desteği

Visual Studio 2017 CMake projeleri için MSBuild proje dosyaları (.vcxproj) dönüştürme olmadan kullanma için destek sunuyor. Daha fazla bilgi için [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md). CMake projeleri ile açma **Klasör Aç** ortamı için düzenleme, derleme ve hata ayıklama C++ otomatik olarak yapılandırır.

- C++ IntelliSense, kök klasörde CppProperties.json dosyası oluşturmaya gerek kalmadan çalışır. Ayrıca kullanıcıların CMake ve CppProperties.json dosyalarıyla sağlanan yapılandırmalar arasında kolayca geçiş izin vermek için yeni bir açılır menü ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![Cmake Klasör Aç](media/cmake-cpp.png "CMake Klasör Aç")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Destek için CMake Ninja oluşturucusunu eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Mevcut CMake önbellekleri almak için eklenen destek.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Önbellek oluşturma ve tek dosyalı derleme için CMake 3.11, CMake projelerini kod analizi, Çözüm Gezgini, seçenekleri hedefleri görünümü için destek eklendi. Daha fazla bilgi için [Visual Studio'da CMake desteği](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [Visual Studio'daki CMake projeleri](../build/cmake-projects-in-visual-studio.md).

## <a name="windows-desktop-development-with-c"></a>C++ ile Windows Masaüstü geliştirme

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik. Kullanıcı Arabirimi doğru değildir ve toplam boyutu düşük gösterdiğini yükleyicide listelenen bileşenleri için belirtilen yükleme boyutları.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Önerilen (Seçilen) bileşenleri yüklemek **VC ++ 2017 v141 araç takımı (x86, x64)** ve **Windows 10 SDK (10.0.nnnnn)** çalıştığından emin olmak için. Gerekli araçlar yüklü değilse, projeler başarıyla oluşturulamaz ve sihirbaz kapanır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Visual C++ derleme Araçları (daha önce tek başına bir ürün kullanılabilir) artık olan Visual Studio Yükleyicisi'nde bir iş yükü olarak dahil. Bu iş yükü, yalnızca C++ projeleri Visual Studio IDE yüklemeden derlemek için gereken araçları yükler. V140 hem v141 araç takımları dahil edilir. Visual Studio 2017 sürüm 15.5 en son iyileştirmelerden v141 araç kümesini içerir. Daha fazla bilgi için [Visual Studio derleme araçları artık içeren VS2017 ve VS2015 MSVC araç takımları](https://devblogs.microsoft.com/cppblog/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/).

## <a name="linux-development-with-c"></a>C++ ile Linux geliştirme

Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

##### <a name="visual-studio-2017-version-152"></a>Visual Studio 2017 sürüm 15.2

Platformlar arası kod paylaşımı ve türü görselleştirmede iyileştirmeler yapılmıştır. Daha fazla bilgi için [Linux C++ geliştirmeleri için platformlar arası kod paylaşımı ve görselleştirme türü](https://devblogs.microsoft.com/cppblog/linux-cross-platform-and-type-visualization/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Linux iş yükü için destek eklemiştir **rsync** alternatif olarak **sftp** uzak Linux makineleri dosyalar için.
- Derleme mikrodenetleyici ARM hedefleme için destek eklenir. Yüklemeyi etkinleştirmek için seçin **ile Linux geliştirme C++**  iş yükü ve seçeneğini **katıştırılmış ve IOT geliştirmesi**. Bu seçenek, ARM GCC çapraz derleme araçlarını ve marka yüklemenize ekler. Daha fazla bilgi için [ARM GCC çapraz derleme Visual Studio'da](https://devblogs.microsoft.com/cppblog/arm-gcc-cross-compilation-in-visual-studio/).
- CMake için eklenen destek. Artık, mevcut CMake kod üzerinde temel bir Visual Studio projesine dönüştürmek zorunda kalmadan çalışabilirsiniz. Daha fazla bilgi için [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).
- Uzak görevleri çalıştırmak için eklenen destek. Bu özellik, Visual Studio'nun Bağlantı Yöneticisi'nde tanımlanan bir uzak sistem üzerindeki herhangi bir komutu çalıştırmak olanak tanır. Uzak görevler, dosyaları uzak sisteme kopyalama olanağı da sağlar.
Daha fazla bilgi için [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- Linux iş yükü senaryoları için çeşitli geliştirmeler. Daha fazla bilgi için [proje sistemi, Linux konsol penceresi, rsync ve işleme İliştir Linux C++ iş yükünde geliştirmeler](https://devblogs.microsoft.com/cppblog/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- Uzak Linux bağlantıları üstbilgileri için IntelliSense. Daha fazla bilgi için [uzak Linux üst bilgiler için IntelliSense](https://devblogs.microsoft.com/cppblog/intellisense-for-remote-linux-headers/) ve [Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>C++ ile oyun geliştirme

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-android-and-ios"></a>C++ (Android ve iOS) ile Mobil Geliştirme

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017'de v140 hedefli bir evrensel Windows platformu projesi açarsanız, Visual Studio 2015 yüklü yoksa, proje özelliği sayfalarından v141 platformu araç kümesini seçmek gerekir.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>C++ için yeni seçenekler Evrensel Windows Platformu (UWP) üzerinde

Şimdi, yazma ve C++ uygulamaları Evrensel Windows platformu ve Windows Store için paketleme yeni seçeneğiniz de vardır: Masaüstü köprüsü altyapı, mevcut masaüstü uygulamasını veya Windows Store veya dışarıdan yükleme aracılığıyla var olan kanallarınız üzerinden dağıtımı için COM nesnesi paketlemek için kullanabilirsiniz. Windows 10'daki yeni özellikler Masaüstü uygulamanızı çeşitli yollarla UWP işlevselliği eklemek etkinleştirin. Daha fazla bilgi için [Masaüstü köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

A **Windows uygulaması paketleme projesi** proje şablonu eklendiğinde, Desktop Bridge ile masaüstü uygulamalarının paketlenmesi, büyük ölçüde basitleştirir. Altında kullanılabilir **dosya | Yeni | Proje | Yüklü | Görsel C++ | Evrensel Windows platformu**. Daha fazla bilgi için [Visual Studio (Masaüstü köprüsü) kullanarak bir uygulama paketini](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

Yeni kod yazarken artık C + kullanabilirsiniz +/ WinRT, standart bir C++ dil projeksiyonu yalnızca üstbilgi dosyalarında uygulanan Windows çalışma zamanı. Her iki Yazar sağlar ve Windows çalışma zamanı API'leri kullanarak standartlara uygun herhangi bir C++ derleyicisi. C++/ WinRT sağlamak için tasarlanmıştır C++ birinci sınıf erişim modern Windows API ile geliştiriciler. Daha fazla bilgi için [ C++/WinRT: Modern C++ Windows çalışma zamanı için](https://moderncpp.com/).

Sürümünden başlayarak Windows SDK'sı Insider Önizleme, C + 17025 derleme +/ WinRT Windows SDK içinde dahil edilmiştir. Daha fazla bilgi için [ C++/WinRT, artık Windows SDK'da](https://devblogs.microsoft.com/cppblog/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Visual Studio 2017 artık destekliyor ile birlikte gönderilen Clang/C2 araç **/bigobj** geçiş, hangi büyük projeler oluşturma açısından önemlidir. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++ Kod Analizi

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Kutusundan denetleyicileri etkinleştirmeniz yeterlidir **Kod Analizi uzantıları** kod analizini çalıştırdığınızda projenin özellik sayfalarındaki ve uzantılar sayfasında dahil edilecektir. Daha fazla bilgi için [C++ temel yönergeleri denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikler sayfası")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15.3

- Kaynak yönetimi ile ilgili kuralları için eklenen destek.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

- Yeni C++ temel yönergeleri denetimi kapsayan akıllı işaretçi doğruluğu, genel başlatıcıların doğru kullanımı ve bayrak kullanır gibi yapıları, `goto` ve hatalı atamaları.

- 15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- Destek için tek dosyalı analizi ve analiz çalıştırma performans geliştirmeleri eklendi. Daha fazla bilgi için [C++ statik analizi iyileştirmeleri Visual Studio 2017 15.6 Preview 2](https://devblogs.microsoft.com/cppblog/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

- İçin eklenen Destek [/ analyze: ruleset](../build/reference/analyze-code-analysis.md), olanak sağlayan çalıştırılacak Kod Analizi kuralları belirtin.
- Desteği için ek C++ temel yönergeleri kuralları eklendi.  Daha fazla bilgi için [C++ temel yönergeleri denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Birim testi

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15.5

Google Test bağdaştırıcısı ve Boost.Test bağdaştırıcısı bileşenleri olarak kullanılabilir olduğuna **C++ ile masaüstü geliştirme** çalıştırdığınız ve iş yükü ile tümleştirilmiştir **Test Gezgini**. CTest desteği (Klasör Aç'ı kullanarak) Cmake projeleri için eklenir, ancak ile tam tümleştirme **Test Gezgini** henüz desteklenmiyor. Daha fazla bilgi için [C/C++ için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15.6

- Destek Boost.Test dinamik kitaplık desteği eklendi.
- Boost.Test öğe şablonu IDE içinde kullanıma sunuldu.

Daha fazla bilgi için [Boost.Test birim testi: Dinamik kitaplık desteği ve yeni öğe şablonu](https://devblogs.microsoft.com/cppblog/boost-test-unit-testing-dynamic-library-support-and-new-item-template/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15.7

[CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) için eklenen Destek C++ birim testi projeleri. Daha fazla bilgi için [C++ birim testi için CodeLens Duyurusu](https://devblogs.microsoft.com/cppblog/announcing-codelens-for-c-unit-testing/).

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

  Çerçevenizi tam çağrı yığınını yakalama etkin yakalanan (**Visual Studio > Araçlar > Seçenekler** altında **grafik tanılama**), her değişikliği olayının bağlamı hızlıca çıkarılabildiği sonra ve Visual Studio projenize içinde inceledi.

- **API istatistikleri:** Çerçeveniz içinde üst düzey API kullanımının özetini görüntüleyin. Bu, sizin fark ettiğinizden değil çağrıları hiç yapıyorsanız bulma veya çok fazla kuran çağrıları için kullanışlıdır. Bu pencere aracılığıyla kullanılabilir **Görüntüle > API istatistikleri** Visual Studio grafik Çözümleyicisi.

  ![API istatistikleri](media/api-stats.png)

- **Bellek istatistikleri:** Sürücü, kaynaklar için ayırma ne kadar bellek çerçevede oluşturduğunuz görüntüleyin. Bu pencere aracılığıyla kullanılabilir **Görüntüle > bellek istatistikleri** içinde **Visual Studio grafik Çözümleyicisi**. Veri kopyalanabilir Elektronik tablolardaki görüntülemek için bir CSV dosyasına sağ tıklayıp seçerek **Tümünü Kopyala**.

  ![Bellek istatistikleri](media/memory-stats.png)

- **Çerçeve doğrulama:** Yeni hataları ve Uyarıları listesi, Direct3D hata ayıklama katmanı tarafından algılanan olası sorunları göre olay listenize gitmek için kolay bir yol sağlar. Tıklayın **Görüntüle > Çerçeve doğrulama** , Visual Studio grafik Çözümleyicisi aygıtını penceresini açın. Ardından **doğrulama çalışması** analiz başlatmak için. Bu çerçeve karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **Çerçeve analizi D3D12 için:** Çerçeve Analizi ile yönlendirilen "what-if" denemeleri çizim çağrısı performansını analiz etmek için kullanın. Çerçeve analizi sekmesine gidin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için izleme [GoingNative 25: Visual Studio grafik çerçevesi analizi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) video.

  ![Çerçeve analizi](media/frame-analysis.png)

- **GPU kullanımı geliştirmeleri:** Açık izlemeleri GPU görünümü ya da daha ayrıntılı analiz için Windows Performans Çözümleyicisi (WPA) aracı ile Visual Studio GPU kullanımı profiler aracılığıyla alınabilir. Windows Performans Araç Seti yüklü varsa, iki köprüler, WPA diğeri GPU görünümünde, sağ alt köşesindeki oturum genel bakış için vardır.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı desteği GPU Görünümü'nde açtığınız izlemeleri, yakınlaştırma ve kaydırma VS ile GPU görünümü zaman çizelgesinde eşitlendi. Vs'de bir onay kutusu, eşitleme etkin'in etkin olup olmadığını denetlemek için kullanılır.

  ![GPU görüntüle](media/gpu-view.png)

::: moniker-end

::: moniker range="=vs-2015"

Visual Studio 2015 güncelleştirme 3'ten yeniliklerin tam listesi için bkz. [Visual C++ 2015 tarihine kadar yeni 2003 nedir](/cpp/porting/visual-cpp-what-s-new-2003-through-2015). Visual Studio 2015'in tüm yenilikler hakkında daha fazla bilgi için bağlantı sürüm notlarına bakın [Visual Studio 2015 sürüm notları geçmişi](/visualstudio/releasenotes/vs2015-version-history). Yenilikler hakkında bilgi C++ Visual Studio 2019 ' bkz [yenilikler C++ Visual Studio'daki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019). Yenilikler hakkında bilgi C++ Visual Studio 2017'de bkz [yenilikler C++ Visual Studio 2017'de](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017).

::: moniker-end
