---
title: Visual Studio 2019'teki c++ yenilikleri
ms.date: 04/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 493b96a8ce3359cc18287adbae8cbd6c374671ec
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779503"
---
<!--NOTE all https:// links to docs.microsoft.com need to be converted to site-relative links prior to publishing-->

# <a name="whats-new-for-c-in-visual-studio-2019"></a>Visual Studio 2019'teki c++ yenilikleri

Visual Studio 2019 birçok güncelleştirme ve Microsoft C++ ortamına giderir. Biz birçok hatalar düzeltildi ve bildirilen sorunları derleyici ve araçları, aracılığıyla müşteriler tarafından birçok gönderilen [sorun bildir](/visualstudio/how-to-report-a-problem-with-visual-studio-2017) ve [bir öneride](https://developercommunity.visualstudio.com/spaces/62/index.html) altında seçenekleri **geri bildirim gönder**. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio'nun tüm yenilikler hakkında daha fazla bilgi için ziyaret [Visual Studio'daki yenilikler](/visualstudio/ide/whats-new-visual-studio-2019).

## <a name="c-compiler"></a>C++ derleyicisi

- `/std:c++latest` Seçeneği artık C ++ 20 işleci <> = ("savaş Gemisi") için üç yönlü karşılaştırma ilk desteği dahil olmak üzere mutlaka tam olmayan C ++ 20 özellikleri içerir.

- [P0941R2 - özellik testi makroları](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p0941r2.html) desteğiyle tamamlandı `__has_cpp_attribute`. Özellik testi makroları, tüm standart modlarında desteklenir.

- [Kullanıcı olarak bildirilen oluşturuculara sahip toplamalar yasaklanması c ++ 20 P1008R1 -](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2018/p1008r1.pdf) de tamamlanır.

- C ++ 17 özellikleri için gelişmiş destek, ayrıca C ++ 20 özellikleri gibi modülleri ve eş yordamlar için Deneysel destek. Ayrıntılı bilgi için bkz. [Visual Studio 2019'deki C++ uyumluluk geliştirmeleri](../cpp-conformance-improvements.md).

- C++ derleyici anahtarı `/Gm` kullanım dışı bırakıldı. Devre dışı bırakmayı deneyin `/Gm` açıkça tanımlanmış olması durumunda derleme betiklerinizde geçin. Ancak, aynı zamanda için kullanımdan kaldırılma uyarısı yok sayabilirsiniz `/Gm`, hata olarak "uyarıları hata olarak değerlendir" kullanırken işlenmez çünkü (`/WX`).

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

### <a name="codegen-security-diagnostics-and-versioning"></a>CODEGEN, güvenlik, tanılama ve sürüm oluşturma

Gelişmiş analiz ile `/Qspectre` değişken 1 (CVE-2017-5753) Spectre risk azaltma Yardım sağlamak için. Daha fazla bilgi için [Spectre azaltmaları MSVC içinde](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>C++ Standart Kitaplığı geliştirmeleri

- [C++ 20 P0550R2 \(remove_cvref)](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2017/p0550r2.pdf) tamamlandı.

- C ++ 17 \<charconv > kayan nokta to_chars() geliştirildi: kısa chars_format::fixed 60-% 80 daha hızlı ve en kısa/duyarlık chars_format::hex tamamlandı.

- Daha fazla bir algoritmalar uygulamaları paralelleştirildi: is_sorted(), is_sorted_until(), is_partitioned(), set_difference(), set_intersection(), is_heap(), is_heap_until().

- Yapılan geliştirmeler `std::variant` daha iyileştirici kolay, daha iyi içinde elde edilen yapmak için oluşturulan kod. Satır içi kod ile çok daha iyi, artık `std::visit`.

- C++ Standart Kitaplığı üst bilgilerine geliştirilmiş okunabilirlik için clang-format uyguladık.

- Birçok standart kitaplık özellikleri kullanılarak derlenmiş iyi aktarım hızı `if constexpr`.

- Standart kitaplık bölümlerini derleme değil önlemek için standart kitaplık fiziksel tasarım en iyi duruma getirilmiş # yarım derleme zamanında yalnızca içeren boş bir dosya kesme #include \<vektör >.

## <a name="performancethroughput-fixes"></a>Performans/aktarım hızı düzeltmeleri

- Derleme Bağlayıcı dosya g/ç işleme dahil olmak üzere, aktarım hızı geliştirmeleri ve PDB birleştirme türü ve oluşturma zamanında bağlayabilirsiniz.

- OpenMP SIMD vektörleştirme için temel desteği eklendi. Yeni CL anahtar kullanarak etkinleştirebilirsiniz `-openmp:experimental`. Bu seçenek ile açıklanan döngüler tanır `#pragma omp simd` potansiyel olarak vektörleştirildi için. Vektörleştirme garanti yoktur ve açıklamalı ancak getirilmemiş döngüleri bildirilen bir uyarı alırsınız. Hiçbir SIMD yan tümceleri desteklenir, bunlar yalnızca bildirilen bir uyarıyla göz.

- Yeni bir satır içi komut satırı anahtarı eklenen `-Ob3`, daha agresif bir sürümü olduğu `-Ob2`. `-O2` (ikili hız için İyileştir) hala gelir `-Ob2` varsayılan olarak. Derleyicinin satır içi kadar agresif değil bulursanız, geçirme göz önünde bulundurun `-O2 -Ob3`.

- Döngüler matematik kitaplığı işlevi ve Tamsayı bölme gibi diğer bazı işlem çağrıları ile elle vektörleştirme desteklemek için kısa vektör/matematik kitaplığı (SVML) iç işlevleri için destek ekledik. Bu işlevler, vektör 128-bit, 256 bit veya 512-bit eşdeğerleri işlem. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - Float hem tamsayı formları için yapı içleri sabiti Katlama ve aritmetik basitleştirme SIMD kullanarak ifadeler için vektör.

  - Her zaman true veya false olarak kanıtlanmış dalları kaldırmak için denetim akışı (if/else/switch deyimleri) bilgi ayıklamak için daha güçlü analiz.

  - Memset SSE2 vektör yönergelerini kullanmanız döngülerin Gelişmiş.

  - Gereksiz struct/class geliştirilmiş kaldırılmasını özellikle değişkeni değer olarak C++ programları için kopyalar.

  - Geliştirilmiş kod kullanmanın en iyi duruma getirme `memmove`, gibi `std::copy` veya `std::vector` ve `std::string` oluşturma.

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Canlı Paylaşım C++ desteği

[Paylaşım canlı](/visualstudio/liveshare/) C++, geliştiricilerin gerçek zamanlı olarak işbirliği yapmak için Visual Studio veya Visual Studio Code kullanarak artık desteklemektedir. Daha fazla bilgi için [Live Share C++ ile tanışın: Gerçek zamanlı paylaşım ve işbirliği](https://devblogs.microsoft.com/cppblog/cppliveshare/)

### <a name="intellicode-for-c"></a>Intellicode c++

Intellicode tamamlama listenizin en üstünde kullanma olasılığı en koymak için kendi kapsamlı eğitim ve kod Bağlamınızı kullanan bir isteğe bağlı bir uzantısıdır. Genellikle listede aşağı kaydırarak gereksinimini ortadan kaldırabilirsiniz. C++ için Intellicode popüler kitaplıkları gibi standart Kitaplığı kullanıldığında çoğu Yardım sunar. Daha fazla bilgi için [AI-Assisted kod tamamlama önerileri gelir Intellicode aracılığıyla C++](https://devblogs.microsoft.com/cppblog/cppintellicode/).

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

## <a name="cmake-support"></a>CMake desteği

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

## <a name="debugging"></a>Hata Ayıklama

- Windows üzerinde çalışan C++ uygulamaları için PDB dosyalarını ayrı bir 64 bit işlemde şimdi yükleyin. Bu değişiklik, bir dizi kilitlenme nedeniyle bellek yetersiz sayıda modüller ve PDB dosyaları içeren uygulamalar hata ayıklama sırasında çalışan hata ayıklayıcı tarafından yöneliktir.

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

## <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Yönetilen C++ Test Çerçevesi mevcut projelerinizi kullanmaya devam edebilirsiniz. Yeni birim testleri için Visual Studio sağlayan şablonlar (MSTest, Google Test) ya da yönetilen yerel test çerçevelerini kullanarak göz önünde bulundurun C# Test proje şablonu.
