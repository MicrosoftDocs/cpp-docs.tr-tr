---
title: Visual Studio 2017’deki C++ yenilikleri
ms.date: 07/02/2019
ms.technology: cpp-ide
ms.assetid: 8801dbdb-ca0b-491f-9e33-01618bff5ae9
author: mikeblome
ms.author: mblome
ms.openlocfilehash: bde8b8e17c3186d22493f099a5f7d1b5a2646a67
ms.sourcegitcommit: 2362d15b5eb18d27773c3f7522da3d0eed9e2571
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73754139"
---
# <a name="whats-new-for-c-in-visual-studio"></a>Visual Studio 2017’deki C++ yenilikleri

::: moniker range=">=vs-2019"

Visual Studio 2019, Microsoft C++ ortamına birçok güncelleştirme ve düzeltme getirir. Derleyicide ve araçlarda birçok hata ve sorunu düzelttik. Bu sorunların birçoğu, müşteriler tarafından [bir sorun bildir](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019) ve **geri bildirim gönder**altında [bir öneri](https://developercommunity.visualstudio.com/spaces/62/index.html) seçenekleri sunarak gönderilmiştir. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio 'nun tüm yenilikleri hakkında daha fazla bilgi için [Visual studio 2019 'deki](/visualstudio/ide/whats-new-visual-studio-2019)yenilikler sayfasını ziyaret edin. Visual Studio 2017 ' C++ deki yenilikler hakkında daha fazla bilgi için bkz. [Visual Studio 2017 ' C++ deki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017)yenilikler. Visual Studio 2015 ve önceki sürümlerindeki yenilikleri C++ hakkında daha fazla bilgi için bkz. [Visual C++ Studio 'nun yenilikler 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="c-compiler"></a>C++ derleyicisi

- C++ 17 özellikleri ve doğruluk düzeltmeleri için geliştirilmiş destek, ayrıca modüller ve eş yordamlar gibi C++ 20 özellikleri için deneysel destek. Ayrıntılı bilgi için bkz [ C++ . Visual Studio 2019 uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- `/std:c++latest` seçeneği artık, üç yönlü karşılaştırma için C++ 20 işleci \<= > ("Spaceship") için ilk destek dahil olmak üzere tam olarak tamamlanmamış C++ 20 özelliklerini içerir.

- C++ Derleyici anahtarı `/Gm` artık kullanım dışıdır. Açıkça tanımlanmışsa, derleme betiklerinizde `/Gm` anahtarını devre dışı bırakmayı düşünün. Ancak, "uyarıları hata olarak değerlendir" (`/WX`) kullanılırken bir hata olarak değerlendirilmediği için, `/Gm`için kullanımdan kaldırma uyarısını güvenle yoksayabilirsiniz.

- MSVC, C++ 20 Standart taslağındaki `/std:c++latest` bayrağı altında özellikleri uygulamaya başladıktan sonra, `/std:c++latest` artık `/clr` (tüm özellikler), `/ZW`ve `/Gm`ile uyumsuzdur. Visual Studio 2019 ' de, `/clr`, `/ZW`veya `/Gm` ile derlerken `/std:c++17` veya `/std:c++14` modlarını kullanın (ancak önceki madde işaretine bakın).

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

### <a name="codegen-security-diagnostics-and-versioning"></a>CodeGen, güvenlik, tanılama ve sürüm oluşturma

Spectre varyant 1 (CVE-2017-5753) için azaltma yardımı sağlamak üzere `/Qspectre` ile iyileştirilmiş analiz. Daha fazla bilgi için bkz. [Spectre AZALTMALARı MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

## <a name="c-standard-library-improvements"></a>C++Standart Kitaplık geliştirmeleri

- Ek C++ 17 ve C++ 20 kitaplığı özelliklerinin ve doğruluk düzeltmelerinin uygulanması. Ayrıntılı bilgi için bkz [ C++ . Visual Studio 2019 uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- Gelişmiş okunabilirlik için C++ standart kitaplık başlıklarına Clang-Format uygulandı.

- Visual Studio artık için C++yalnızca kendi kodum desteklediğinden, standart kitaplığın artık `std::function` için özel makineler sağlaması gerekmez ve aynı etkiyi elde etmek için `std::visit`. Bu makinelerin büyük ölçüde Kullanıcı tarafından görülemeyen etkileri yoktur. Tek bir istisna, derleyicinin artık \<type_traits > veya \<varyant > 'deki 15732480 veya 16707566. satırdaki sorunları belirten tanılama oluşturmayacağı anlamına gelebilir.

## <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Derleyici ve standart kitaplıkta performans/aktarım hızı iyileştirmeleri

- Bağlayıcının dosya g/ç 'yi işleme şekli ve PDB türü birleştirme ve oluşturma sırasında bağlantı süresi de dahil olmak üzere derleme işleme iyileştirmeleri.

- OpenMP SıMD vektörleştirme için temel destek eklendi. Bunu, yeni derleyici anahtarı `-openmp:experimental`kullanarak etkinleştirebilirsiniz. Bu seçenek, büyük olasılıkla vektörleştirilmiş `#pragma omp simd` için açıklama eklenmiş döngülere izin verir. Vektörleştirme garanti edilmez ve vektörleştirilmiş ancak vektörleştirilmemiş döngüler bildirilen bir uyarı alır. SıMD yan tümceleri desteklenmez; Bunlar yok sayılır ve bir uyarı bildirilir.

- `-Ob2`daha agresif bir sürümü olan yeni bir satır içi komut satırı anahtarı `-Ob3`eklendi. `-O2` (hızı hız için en iyi hale getirin) varsayılan olarak `-Ob2` de gerektirir. Derleyicinin satır içi olarak yeterince gözetmediğini fark ederseniz `-O2 -Ob3`geçirmeyi düşünün.

- Matematik kitaplığı işlevlerine yapılan çağrılar ve tamsayı bölme gibi diğer diğer işlemler ile döngülerin birlikte vektörleştirilmesini desteklemek için, kısa vektör matematik kitaplığı (SVML) iç işlevlerine yönelik destek ekledik. Bu işlevler 128 bit, 256 bit veya 512 bit vektör eşdeğerlerini hesaplar. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - Hem float hem de Integer formlarında SıMD vektör iç bilgileri kullanan ifadeler için sabit katlamalı ve aritmetik basitleştirmeleri.

  - Her zaman doğru veya yanlış olarak kanıtlanmış olan dalları kaldırmak için denetim akışından (if/else/Switch deyimleri) bilgi ayıklamasına yönelik daha güçlü bir analizler.

  - SSE2 vektör yönergeleri kullanılarak geliştirilmiş memset kullanımı.

  - Özellikle değere göre geçen programlar için C++ , çok sayıda struct/Class kopyasının daha iyi kaldırılması.

  - `std::copy` veya `std::vector` ve `std::string` oluşturma gibi `memmove`kullanarak kodun iyileştirilmiş iyileştirmesi.

- Standart kitaplığın, doğrudan dahil edilmemiş parçalar derlenmekten kaçınmak için standart kitaplık fiziksel tasarımını en iyi duruma getirilmiştir. Bu değişiklik, yalnızca \<vektör > yarısını içeren boş bir dosyanın derleme süresini keser. Sonuç olarak, daha önce dolaylı olarak dahil edilen üst bilgiler için `#include` yönergeleri eklemeniz gerekebilir. Örneğin, `std::out_of_range` kullanan kodun artık `#include <stdexcept>`eklemesi gerekebilir. Stream ekleme işlecini kullanan kodun artık `#include <ostream>`eklemesi gerekebilir. Avantaj, yalnızca \<stdexcept > veya \<ostream > bileşenleri kullanan çeviri birimlerinin, bunları derlemek için üretilen iş maliyetini ödemesidir.

- `if constexpr`, gelişmiş aktarım hızı ve kopyalama işlemlerinde daha fazla kod boyutu, ters ve döndürme gibi permütasyon ve paralel algoritmalar kitaplığındaki daha fazla yere uygulandı.

- Standart kitaplık artık, C++ 14 modunda bile derleme sürelerini azaltmak için `if constexpr` dahili olarak kullanır.

- Paralel algoritmalar kitaplığı için çalışma zamanı dinamik bağlama algılaması, artık işlev işaretçisi dizisini depolamak için bir sayfanın tamamını kullanmaz. Bu belleği salt okunurdur olarak işaretlemek artık güvenlik amaçları için uygun değildir.

- `std::thread`Oluşturucusu artık iş parçacığının başlamasını beklemez ve artık temel alınan C Kitaplığı `_beginthreadex` ve sağlanan çağrılabilir nesne arasında işlev çağrılarının birçok katmanını eklememe. Daha önce `std::thread`, yalnızca 3 ' e (yalnızca `std::invoke`) indirgenmiş olan `_beginthreadex` ve sağlanan çağrılabilir nesne arasında 6 işlev koyun. Bu değişiklik Ayrıca sistem saatinin `std::thread` oluşturulduğu anda değişmesi durumunda bir `std::thread` oluşturucusunun askıda kalması halinde, kesin bir zamanlama hatasını giderir.

- `std::hash<std::filesystem::path>`uygularken tanıtıldığımız `std::hash` bir performans gerileme düzeltildi.

- Standart kitaplık artık, doğruluk düzeyine ulaşmak için birkaç yerde catch blokları yerine Yıkıcılar kullanır. Bu değişiklik, daha iyi hata ayıklayıcı etkileşimine neden olur: etkilenen konumlarda standart kitaplık aracılığıyla oluşturduğunuz özel durumlar artık, yeniden oluşturma işleminden önce orijinal throw sitesinden oluşturulmuş olarak gösterilir. Tüm standart kitaplık yakalama blokları ortadan kaldırılmıştır; MSVC 'in sonraki sürümlerinde, catch bloklarının sayısının azaltıldığı tahmin ederiz.

- Noexcept işlevinin içindeki koşullu bir throw 'un neden olduğu `std::bitset`, oluşturma yolu düzenleme tarafından düzeltildi.

- `std::list` ve `std::unordered_*` ailesi, daha fazla yerde hata ayıklama olmayan yineleyiciler kullanır.

- Birkaç `std::list` üye, liste düğümlerini serbest bırakmak ve yeniden konumlandırmak yerine mümkün olduğunca yeniden kullanmak üzere değiştirilmiştir. Örneğin, zaten 3 boyutunda bir `list<int>` verildiğinde, bir `assign(4, 1729)` çağrısı artık ilk 3 liste düğümündeki boyutları geçersiz kılar ve 1729 değerine sahip bir yeni liste düğümü ayırır.

- `erase(begin(), end())` için tüm standart kitaplık çağrıları `clear()`olarak değiştirilmiştir.

- `std::vector` artık bazı durumlarda öğeleri daha verimli bir şekilde başlatır ve siler.

- Daha iyi hale getirmek için `std::variant` iyileştirmeler, daha iyi üretilen koda neden olur. Kod satır içi `std::visit`artık çok daha iyidir.

## <a name="c-ide"></a>C++ IDE

### <a name="live-share-c-support"></a>Live Share C++ desteği

[Live share](/visualstudio/liveshare/) artık C++, Visual Studio veya Visual Studio Code kullanan geliştiricilerin gerçek zamanlı olarak işbirliği yapmasına olanak sağlar. Daha fazla bilgi için bkz [ C++. duyurusu Live Share: gerçek zamanlı paylaşım ve işbirliği](https://devblogs.microsoft.com/cppblog/cppliveshare/)

### <a name="intellicode-for-c"></a>İçin ıntellicodeC++

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

Intellicode, tamamlanma listenizin en üstünde en büyük olasılıkla kullandıklarınızı yerleştirmek için kendi kapsamlı eğitimini ve kod bağlamını kullanan isteğe bağlı bir uzantıdır. Genellikle listede aşağı kaydırma gereğini ortadan kaldırabilir. İçin C++, standart kitaplık gibi popüler kitaplıkları kullanırken ıntellicode en fazla yardımı sunar. Bu, yükleyicide bir iş yükü bileşeni olarak sunulmaktadır. Daha fazla bilgi için bkz. [AI destekli kod tamamlama önerileri ıntellicode C++ aracılığıyla sunulur](https://devblogs.microsoft.com/cppblog/cppintellicode/).

### <a name="template-intellisense"></a>Şablon IntelliSense

**Şablon çubuğu** artık, kalıcı bir pencere yerine bir **pencere göz atma** Kullanıcı arabirimini kullanır, iç içe geçmiş şablonları destekler ve varsayılan bağımsız değişkenleri **göz atma penceresinde**önceden doldurur. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 Için şablon IntelliSense geliştirmeleri](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/). **Şablon çubuğunda** **en son kullanılan** bir açılan liste, önceki örnek bağımsız değişken kümeleri arasında hızlıca geçiş yapmanızı sağlar.

### <a name="new-start-window-experience"></a>Yeni başlangıç penceresi deneyimi

IDE 'yi başlatırken, son projeleri açma, kaynak denetiminden kod kopyalama, yerel kodu çözüm veya klasör olarak açma veya yeni bir proje oluşturma seçenekleri içeren yeni bir başlangıç penceresi görüntülenir. Yeni proje iletişim kutusu ayrıca arama sırasında, filtrelenebilir bir deneyime de sahiptir.

### <a name="new-names-for-some-project-templates"></a>Bazı proje şablonları için yeni adlar

Çeşitli proje şablonu adlarını ve açıklamalarını güncelleştirilmiş yeni proje iletişim kutusuyla sığacak şekilde değiştirdik.

### <a name="various-productivity-improvements"></a>Çeşitli verimlilik geliştirmeleri

Visual Studio 2019, kodlamayı daha kolay ve daha sezgisel hale getirmeye yardımcı olacak aşağıdaki özellikleri içerir:

- İçin hızlı düzeltmeler:
  - Eksik #include Ekle
  - Nullptr için NULL
  - Eksik noktalı virgül Ekle
  - Eksik ad alanı veya kapsamı çözümle
  - Hatalı yöneltme işlenenlerini (\* & ve \*&) değiştirin
- Kapatma küme ayracı üzerine gelindiğinde bir blok için hızlı bilgi
- Üst bilgi/kod dosyasına göz at
- #İnclude ' de tanımına git dosyayı açar

Daha fazla bilgi için bkz [ C++ . Visual Studio 2019 Preview 2 ' de üretkenlik iyileştirmeleri](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/).

### <a name="quickinfo-improvements"></a>Hızlı bilgi iyileştirmeleri

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

Hızlı Bilgi ipucu artık Düzenleyicinizde anlam renklendirme için uyar. Ayrıca, vurgulanan kod yapısı hakkında daha fazla bilgi edinmek için çevrimiçi belgeleri arayacak yeni bir **arama çevrimiçi** bağlantısına sahiptir. Kırmızı renkli bir kod için, hızlı bilgi tarafından sağlanmış olan bağlantı, hatayı çevrimiçi olarak arar. Bu şekilde, iletiyi tarayıcınıza yeniden yazmanız gerekmez. Daha fazla bilgi için bkz. [Visual Studio 2019 'de hızlı bilgi iyileştirmeleri: renklendirme ve çevrimiçi arama](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/).

### <a name="intellicode-available-in-c-workload"></a>C++ Iş yükünde ıntellicode kullanılabilir

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

Intellicode artık iş yüküyle **Masaüstü geliştirmede C++**  isteğe bağlı bir bileşen olarak dağıtılır. Daha fazla bilgi için bkz [. C++ gelişmiş ıntellicode artık Visual Studio 2019 ile birlikte gelir](https://devblogs.microsoft.com/cppblog/improved-c-intellicode-now-ships-with-visual-studio-2019/).

## <a name="cmake-support"></a>CMake desteği

- CMake 3,14 desteği

- Visual Studio artık Cmakeguı, özelleştirilmiş meta derleme sistemleri veya CMake. exe ' yi çağıran derleme betikleri gibi dış araçlar tarafından oluşturulan mevcut CMake önbelleklerini açabilir.

- Geliştirilmiş IntelliSense performansı.

- Yeni bir ayar Düzenleyicisi, CMakeSettings. json dosyasını el ile düzenlemeyle ilgili bir alternatif sağlar ve Cmakeguı ile bir eşlik sağlar.

- Visual Studio, Linux makinenizde uyumlu bir CMake sürümü olup olmadığını algılayarak Linux üzerinde CMake ile C++ geliştirmenizin önyüklemesine yardımcı oluyor. Uyumlu bir sürüm yoksa, sizin için yüklemeyi öneriyor.

- CMakeSettings içinde eşleşmeyen mimariler veya uyumsuz CMake Oluşturucu ayarları gibi uyumsuz ayarlar, JSON düzenleyicisinde dalgalı çizgiler ve hata listesindeki hataları gösterir.

- `vcpkg integrate install` çalıştırıldıktan sonra IDE'de açılmış olan CMake projeleri için vcpkg araç zinciri otomatik olarak algılanıyor ve etkinleştiriliyor. Bu davranış, CMakeSettings'de boş bir araç zinciri dosyası belirtilerek kapatılabilir.

- CMake projeleri artık varsayılan olarak Yalnızca Kendi Kodum hata ayıklamasını etkinleştiriyor.

- CMake projelerinde statik analiz uyarıları şimdi arka planda işlenebiliyor ve düzenleyicide görüntülenebiliyor.

- CMake projeleri ve Visual Studio 'nun derleme ilerlemesi Kullanıcı arabirimine yönelik destek için ' begin' ve ' End ' iletilerini daha net hale getirin ve yapılandırın. Ayrıca, **araçlar > seçeneklerinde** CMake yapı ve yapılandırma çıkış penceresi iletilerinin ayrıntı düzeyini özelleştirmek için artık bir CMake ayrıntı ayarı vardır.

- CMake komut satırını el ile değiştirmeden araç zincirlerini belirtmek için `cmakeToolchain` ayarı artık CMakeSettings. json ' da desteklenir.

- Yeni bir **Yapı Oluştur** Menü kısayolu **CTRL + SHIFT + B**.

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

- Clang/LLVM ile CMake projelerini düzenlemeyle, oluşturmaya ve hata ayıklamaya yönelik tümleşik destek. Daha fazla bilgi için bkz. [Visual Studio 'Da Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/).

## <a name="linux-and-the-windows-subsystem-for-linux"></a>Linux için Linux ve Windows alt sistemi

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

- Linux ve CMake platformlar arası projelerde [Addresstemizleme (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) desteği. Daha fazla bilgi için bkz. [Visual Studio 2019 ' de Linux Iş yükü Için Addresstemizleme (ASan)](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/).

- Linux için Windows alt sistemi ( C++ WSL) ile birlikte kullanmak Için tümleşik Visual Studio desteği. Daha fazla bilgi için bkz [ C++ . Visual Studio 2019 ve Linux için Windows alt sistemi (WSL)](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

## <a name="incredibuild-integration"></a>IncrediBuild tümleştirmesi

IncrediBuild, bir isteğe bağlı bileşen olarak iş yüküne **sahip C++ masaüstü geliştirmeye** dahildir. IncrediBuild derleme Izleyicisi, Visual Studio IDE 'de tamamen tümleşiktir. Daha fazla bilgi için bkz. [IncrediBuild 'In derleme İzleyicisi ve Visual Studio 2019 ile derlemenizi görselleştirme](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/).

## <a name="debugging"></a>Hata Ayıklama

- Windows C++ üzerinde çalışan uygulamalar için pdb dosyaları artık ayrı bir 64 bit işlemde yüklenir. Bu değişiklik, çok sayıda modül ve PDB dosyası içeren uygulamalarda hata ayıklarken hata ayıklayıcı tarafından oluşan bir kilitlenme aralığını giderir.

- Arama, **izleme**, **oto**ve **Yereller** pencerelerinde etkinleştirilmiştir.

## <a name="windows-desktop-development-with-c"></a>İle Windows masaüstü geliştirmeC++

- Bu C++ ATL/MFC sihirbazları artık kullanılamaz:

  - ATL COM+ 1.0 Bileşeni Sihirbazı
  - ATL Active Server Pages Bileşen Sihirbazı
  - ATL OLE DB sağlayıcı Sihirbazı
  - ATL Özellik Sayfası Sihirbazı
  - ATL OLE DB Tüketici Sihirbazı
  - MFC ODBC Tüketicisi
  - ActiveX denetiminden MFC sınıfı
  - Tür lib 'den MFC sınıfı.

  Bu teknolojiler için örnek kod Microsoft Docs ve VCSamples GitHub deposunda arşivlenir.

- Windows 8.1 SDK'sı artık Visual Studio yükleyicisinde sağlanmıyor. C++ Projelerinizi en son Windows 10 SDK 'sına yükseltmenizi öneririz. 8,1 üzerinde sabit bir bağımlılıktan sahipseniz Windows SDK arşivden indirebilirsiniz.

- En son C++ araç takımında artık Windows XP hedeflemesi sağlanmıyor. VS 2017-Level MSVC derleyicisi & kitaplıkları ile hedefleme, hala desteklenmektedir ve "bağımsız bileşenler" aracılığıyla yüklenebilir.

- Belgelerimizde şu anda Visual C++ Çalışma Zamanı dağıtımı için Modülleri Birleştirme kullanımı hiç önerilmiyor. Bu sürümden, MSMs 'nin kullanım dışı olarak işaretlenme konusunda daha fazla adımla karşılaşıyoruz. VCRuntime merkezi dağıtımınızı MSM'lerden yeniden dağıtılabilir pakete geçirmeyi göz önünde bulundurun.

## <a name="mobile-development-with-c-android-and-ios"></a>İle C++ mobil geliştirme (Android ve iOS)

C++ Android deneyimi artık varsayılan olarak Android SDK 25 ve Android NDK 16b olur.

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Clang/C2 bileşeni kaldırıldı. `/permissive-` ve `/std:c++17`veya Windows için C++ Clang/LLVM araç zinciri ile tam standartlar uyumluluğu için MSVC araç takımını kullanın.

## <a name="code-analysis"></a>Kod analizi

- Kod analizi artık otomatik olarak arka planda çalıştırılıyor. Siz yazdıkça düzenleyicinin içinde uyarılar yeşil dalgalı çizgilerle gösteriliyor. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 ' deki düzenleyici kod analizi](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/).

- \<mutex > üstbilgisinden iyi bilinen standart kitaplık türleri için yeni deneysel ConcurrencyCheck kuralları. Daha fazla bilgi için bkz. [Visual Studio 2019 'de eşzamanlılık kodu analizi](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/).

- Etkinlik işaretçilerini ve başvuruları algılayan [ömür profili denetleyicisi](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)'nin güncelleştirilmiş kısmi bir uygulamasıdır. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 ' de ömür profili güncelleştirmesi](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/).

- C26138, C26810, C26811 ve deneysel kural C26800 dahil olmak üzere daha fazla Corine ilişkin denetimler. Daha fazla bilgi için bkz. [Visual Studio 2019 'de yeni kod analizi denetimleri: Use-After-Move ve eş yordam olamaz](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/).

##### <a name="visual-studio-2019-version-161"></a>Visual Studio 2019 sürüm 16,1

- Başlatılmamış Değişken denetimleri için yeni hızlı düzeltmeler. Daha fazla bilgi için bkz. [Başlatılmamış bellek Için yeni kod analizi hızlı düzeltmeleri (C6001) ve init (C26494) uyarılarını kullanma](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/).

## <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Varolan projelerinizde yönetilen C++ test çerçevesini kullanmaya devam edebilirsiniz. Yeni birim testleri için, Visual Studio 'nun şablonlar (MSTest, Google Test) veya yönetilen C# test projesi şablonu sağladığı yerel test çerçevelerinden birini kullanmayı düşünün.

::: moniker-end

::: moniker range="=vs-2017"

Visual Studio 2017, C++ ortama birçok güncelleştirme ve düzeltme getirir. Derleyici ve araçlarındaki 250 hatayı ve bildirilen sorunları çözdük ve [bir sorun bildir ve](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2017) **geri bildirim gönder**bölümünde öneri seçenekleri sağlar. Hataları bildirdiğiniz için teşekkür ederiz! Visual Studio 'nun tüm yenilikleri hakkında daha fazla bilgi için bkz. [visual 2017 Studio 'daki](/visualstudio/ide/whats-new-visual-studio-2017?view=vs-2017)yenilikler. Visual Studio 2019 ' C++ deki yenilikler hakkında daha fazla bilgi için bkz. [Visual Studio C++ 'daki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019)yenilikler. Visual Studio 2015 ve önceki sürümlerindeki yenilikleri C++ hakkında daha fazla bilgi için bkz. [Visual C++ Studio 'nun yenilikler 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015).

## <a name="c-compiler"></a>C++ derleyicisi

### <a name="c-conformance-improvements"></a>C++uyumluluk geliştirmeleri

Bu sürümde, C++ derleyicisini ve standart kitaplığını C++11 ve C++14 özellikleri için desteği iyileştirecek, ayrıca C++17 standardına eklenmesi beklenen bazı özellikler için ön destek sağlayacak şekilde güncelleştirdik. Ayrıntılı bilgi için bkz [ C++ . Visual Studio 2017 uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Derleyici, yapılandırılmış bağlamalar, `constexpr` Lambdalar, `if constexpr`, satır içi değişkenler, katlama ifadeleri ve tür sistemine `noexcept` ekleme dahil olmak üzere C++ 17 ' de yeni olan özelliklerin %75 ' sini destekler. Bu özellikler **/std: c++ 17** seçeneği altında bulunur. Daha fazla bilgi için bkz [ C++ . Visual Studio 'da uyumluluk geliştirmeleri 2017](cpp-conformance-improvements.md)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

Visual Studio sürüm 15,7 ' deki MSVC derleyici araç takımı artık C++ standart ile uyumlu. Daha fazla bilgi için bkz. [duyuruldu: MSVC uyumlu C++ ve standart](https://devblogs.microsoft.com/cppblog/announcing-msvc-conforms-to-the-c-standard/) ve [ C++ Microsoft dil uyumluluğu](../visual-cpp-language-conformance.md).

##### <a name="visual-studio-2017-version-158"></a>Visual Studio 2017 sürüm 15,8

[/Deneysel: Önişlemci](../build/reference/experimental-preprocessor.md) derleyici anahtarı, geçerli tüm C ve C++ standartlarla uyumlu olacak şekilde yeni deneysel MSVC ön işlemcisi 'ni sunar. Daha fazla bilgi için bkz. [MSVC deneysel Önişlemci genel bakış](../preprocessor/preprocessor-experimental-overview.md).

### <a name="new-compiler-options"></a>Yeni derleyici seçenekleri

- [/Permissive-](../build/reference/permissive-standards-conformance.md): tüm katı standartlar uygunluk derleyicisi seçeneklerini etkinleştirin ve Microsoft 'a özgü çoğu derleyici uzantısını devre dışı bırakın (örneğin `__declspec(dllimport)`değil). Bu seçenek, varsayılan olarak Visual Studio 2017 sürüm 15,5 ' de bulunur.  **/Permissive-** uygunluk modu, iki aşamalı ad arama desteği içerir. Daha fazla bilgi için bkz [ C++ . Visual Studio 'da uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- [/Diagnostics](../build/reference/diagnostics-compiler-diagnostic-options.md): satır numarasını, satır numarasını ve sütunu ya da satır numarasını ve sütununu ve tanılama hatasının veya uyarısının bulunduğu kod satırı altındaki bir giriş işaretini görüntülemeyi etkinleştirin.

- [/Debug: fastlink](../build/reference/debug-generate-debug-info.md): tüm hata ayıklama bilgilerini pdb dosyasına kopyalamadığınızda, %30 ' a kadar daha hızlı artımlı bağlantı süresini (vs. Visual Studio 2015) etkinleştirin. Bunun yerine PDB dosyası, yürütülebilir dosyayı oluşturmak için kullanılan nesne ve kitaplık dosyaları için hata ayıklama bilgilerini gösterir. [Visual Studio 'da C++ ](https://devblogs.microsoft.com/cppblog/recommendations-to-speed-c-builds-in-visual-studio/)bkz. [/Debug: fastlink ile vs "15" içinde derleme döngüsüne daha hızlı C++ ](https://devblogs.microsoft.com/cppblog/faster-c-build-cycle-in-vs-15-with-debugfastlink/) bakın.

- Visual Studio 2017, [/SDL](../build/reference/sdl-enable-additional-security-checks.md) ile [/await](../build/reference/await-enable-coroutine-support.md)kullanılmasına izin verir. Coroutines ile [/RTC](../build/reference/rtc-run-time-error-checks.md) sınırlamasını kaldırdık.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- [/std: c++ 14 ve/std: c + + en son](../build/reference/std-specify-language-standard-version.md): Bu derleyici seçenekleri BIR projede ISO C++ programlama dilinin belirli sürümlerini kabul etkinleştirmenizi sağlar. Yeni taslak standart özelliklerinin çoğu **/std: c + + en son** seçeneği tarafından korunuyor.

- [/std: c++ 17](../build/reference/std-specify-language-standard-version.md) , derleyici tarafından uygulanan c++ 17 özelliklerinin kümesini sunar. Bu seçenek, C++ 17 ' den sonra C++ standart 'ın çalışma taslağı ve hata güncelleştirmeleri sürümlerinde değiştirilen veya yeni olan özellikler için derleyici ve standart kitaplık desteğini devre dışı bırakır. Bu özellikleri etkinleştirmek için **/std: c + + en son**' u kullanın.

### <a name="codegen-security-diagnostics-and-versioning"></a>CodeGen, güvenlik, tanılama ve sürüm oluşturma

Bu sürüm, iyileştirme, kod oluşturma, araç takımı sürümü oluşturma ve tanılama konularında çeşitli geliştirmeler sunar. Bazı önemli geliştirmeler şunlardır:

- Döngüler için geliştirilmiş kod oluşturma: sabit tam sayıları bölme işlemleri için otomatik vektörleştirme desteği, memset desenlerinin daha iyi tanınması.
- Geliştirilmiş kod güvenliği: arabellek taşması derleyici tanılamaları ve [/Guard: CF](../build/reference/guard-enable-control-flow-guard.md) , artık doğrudan geçiş tabloları üreten anahtar deyimlerini korumıştır.
- Sürüm oluşturma: yerleşik Önişlemci makrosunun **\_MSC\_ver** değeri artık her görsel C++ araç takımı güncelleştirmesinde tek bir şekilde güncelleştirildi. Daha fazla bilgi için bkz [. C++ Visual derleyicisi sürümü](https://devblogs.microsoft.com/cppblog/visual-c-compiler-version/).
- Yeni araç takımı düzeni: derleyici ve ilgili derleme araçlarının geliştirme makinenizde yeni bir konum ve dizin yapısı vardır. Yeni düzen derleyicinin birden çok sürümünün yan yana yüklemelerine izin vermez. Daha fazla bilgi için bkz. [Visual Studio 2017 ' de derleyici araçları düzeni](https://devblogs.microsoft.com/cppblog/compiler-tools-layout-in-visual-studio-15/).
- Geliştirilmiş Tanılamalar: çıkış penceresinde artık hata oluşan sütun görüntülenir. Daha fazla bilgi için bkz [ C++ . vs "15" Preview 5 ' te derleyici tanılama geliştirmeleri](https://devblogs.microsoft.com/cppblog/c-compiler-diagnostics-improvements-in-vs-15-rc/).
- Ortak yordamlar kullanılırken deneysel anahtar sözcük **yield** ( **/await** seçeneği altında kullanılabilir) kaldırılmıştır. Kodunuzun `co_yield` kullanacak şekilde güncellenmesi gerekir. Daha fazla bilgi için, bkz. [VS 2017 'de `co_yield` olmak için`yield` anahtar sözcüğü](https://devblogs.microsoft.com/cppblog/yield-keyword-to-become-co_yield-in-vs-2017/).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

Derleyicide Tanılama için ek geliştirmeler. Daha fazla bilgi için bkz. [Visual Studio 'Da tanılama geliştirmeleri 2017 15.3.0](https://devblogs.microsoft.com/cppblog/diagnostic-improvements-in-vs2017-15-3-0/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Visual C++ Runtime performansı, daha iyi oluşturulmuş kod kalitesi nedeniyle gelişmeye devam etmektedir. Artık kodunuzu yeniden derleyebilirsiniz ve uygulamanız daha hızlı çalışır. Derleyici iyileştirmelerinden bazıları koşullu skaler mağazaların vektörleştirmesi, çağrıların birleştirilmesi `sin(x)` ve `cos(x)` yeni bir `sincos(x)`içine ve SSA iyileştiricisinden gereksiz yönergelerin yok etme gibi yepyeni bir şekilde yenidir. Diğer derleyici iyileştirmeleri, Koşullu ifadeler için vektörtorizer buluşsal yöntemler, daha iyi döngü iyileştirmeleri ve float Min/Max CodeGen gibi mevcut işlevlere yönelik geliştirmelerdir. Bağlayıcı yeni ve daha hızlı bir **/OPT: ICF** uygulamasına sahiptir. Bu, %9 bağlantı süresi hızlandırmalı ve artımlı bağlamada başka performans düzeltmeleri de olabilir. Daha fazla bilgi için bkz. [/opt (iyileştirmeler)](../build/reference/opt-optimizations.md) ve [/artımlı (artımlı bağlantı)](../build/reference/incremental-link-incrementally.md).

Microsoft C++ derleyicisi, avx-512 ' deki yeni işlevleri 128-bit ve 256-bit geniş kayıt defterlerine getiren vektör uzunluğu yönergeleri dahil olmak üzere Intel avx-512 ' ü destekler.

[/Zc: noexceptTypes-](../build/reference/zc-noexcepttypes.md) seçeneği, c++ 17 modu genel olarak kullanılırken `noexcept` c++ 14 sürümüne dönmek için kullanılabilir. Bu seçenek, tüm `throw()` kodunuzu aynı anda yeniden yazmak zorunda kalmadan, kaynak kodunuzu C++ 17 ile uyumlu olacak şekilde güncelleştirmenizi sağlar. Daha fazla bilgi için bkz. [dinamik özel durum belirtimi kaldırma ve noexcept](cpp-conformance-improvements.md#noexcept_removal).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

- Yeni derleyici anahtarı [/Qspectre](../build/reference/qspectre.md) , öngörülebilir yürütme yan kanal saldırılarına karşı azaltmaya yardımcı olur. Daha fazla bilgi için bkz. [Spectre AZALTMALARı MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).
- Spectre azaltma için yeni tanılama uyarısı. Daha fazla bilgi için bkz. [Spectre Diagnostic for Visual Studio 2017 sürüm 15,7 Preview 4](https://devblogs.microsoft.com/cppblog/spectre-diagnostic-in-visual-studio-2017-version-15-7-preview-4/).
- /ZC için yeni bir değer olan **/Zc: __cplusplus**, C++ standart desteğin doğru şekilde raporlanmasına izin vermez. Örneğin, anahtar ayarlandığında ve derleyici/std: c++ 17 modunda olduğunda değer **201703L**olarak genişletilir. Daha fazla bilgi için bkz. [MSVC artık __cplusplus 'ı doğru şekilde bildiriyor](https://devblogs.microsoft.com/cppblog/msvc-now-correctly-reports-__cplusplus/).

## <a name="c-standard-library"></a>C++Standart Kitaplık

### <a name="correctness-improvements"></a>Doğruluk Iyileştirmeleri

##### <a name="visual-studio-2017-rtm-version-150"></a>Visual Studio 2017 RTM (sürüm 15,0)

- İkincil `basic_string` `_ITERATOR_DEBUG_LEVEL != 0` tanılama geliştirmeleri. Dize makinesinde IDL denetiminin kesilmesi, artık kesintiye neden olan davranışı rapor edecektir. Örneğin, "dize yineleyici başvurulabilir değil" yerine "aralıkta olmadığı için dize yineleyicisine başvurulamıyor (ör. bitiş yineleyicisi)" görünür.
- Daha önce kodun sürekli olarak engellenmesine neden olabilecek `std::promise` taşıma atama işleci düzeltildi.
- `T*``atomic<T*>` örtük dönüşümle derleyici hataları düzeltildi.
- `pointer_traits<Ptr>` artık `Ptr::rebind<U>`doğru şekilde algılar.
- `move_iterator` çıkarma işlecinde eksik `const` niteleyicisi düzeltildi.
- `propagate_on_container_copy_assignment` ve `propagate_on_container_move_assignment`isteyen durum bilgisi olan Kullanıcı tanımlı ayrıcılar için sessiz hatalı CodeGen düzeltildi.
- `atomic<T>` artık aşırı yüklenmiş `operator&()`tolerans gösterir.
- Yanlış `bind()` çağrıları için biraz daha geliştirilmiş derleyici tanılaması.

Visual Studio 2017 RTM 'de standart kitaplık geliştirmelerinden oluşan kapsamlı bir liste için bkz. C++ [vs 2017 RTM 'de takım blogu girişi standart kitaplık düzeltmeleri](https://devblogs.microsoft.com/cppblog/stl-fixes-in-vs-2017-rtm/).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- Standart Kitaplık kapsayıcıları artık `size_type``max()` yerine `numeric_limits<difference_type>::max()` `max_size()` çakışıyor. Bu değişiklik, bu kapsayıcıdaki Yineleyicilerde `distance()` sonucunun `distance()`dönüş türünde gösterilebilir olmasını sağlar.
- Eksik özelleştirme `auto_ptr<void>`düzeltildi.
- Length bağımsız değişkeni bir tamsayı türü değilse, daha önce `for_each_n()`, `generate_n()`ve `search_n()` algoritmaları derlenemedi; Artık İntegral olmayan uzunlukları yineleyiciler ' `difference_type`dönüştürmeye çalışır.
- `normal_distribution<float>`, standart kitaplık içinde Double-float ile daraltma hakkında artık uyarı vermez.
- En büyük boyut taşması denetlenirken `max_size()` yerine `npos` kullanılan bazı `basic_string` işlemler düzeltildi.
- `condition_variable::wait_for(lock, relative_time, predicate)`, büyük bir uyanma durumunda tüm göreli zamanın tamamlanmasını bekler. Artık, göreli saatin yalnızca tek bir aralığını bekler.
- `future::get()` artık, standart gerektirdiğinden `future`geçersiz kılar.
- `iterator_traits<void *>`, `void&`ayarlamaya çalıştığı için bir sabit hata olması için kullanılır; Artık, "bir yineleyici" SFINAE koşullarında `iterator_traits` kullanılmasına izin veren boş bir yapı haline gelir.
- Clang **-wsystem-Headers** tarafından bildirilen bazı uyarılar düzeltildi.
- Ayrıca, bildirimde bulunan özel durum belirtimi, Clang **-wmicrosoft-Exception-spec**tarafından bildirilen bir önceki bildirimle eşleşmez.
- Ayrıca, Clang ve C1XX tarafından bildirilen sabit bir bellek-başlatıcı-liste sıralama uyarıları.
- Sıralanmamış kapsayıcılar, kapsayıcılar kendilerini takas edildiğinde karma işlevlerini veya koşullarını değiştirmedi. Şimdi.
- Birçok kapsayıcı takas işlemi artık `noexcept` olarak işaretlenmiş (Standart kitaplığımız,`propagate_on_container_swap` olmayan eşit ayırıcı olmayan tanımsız davranış koşulunu algıladığında hiçbir zaman bir özel durum oluşturmak üzere değildir).
- Birçok `vector<bool>` işlem artık `noexcept`olarak işaretlenir.
- Standart kitaplık artık, bir opt çıkış taraması ile eşleşen ayırıcıyı `value_type` (C++ 17 modunda) zorlayacaktır.
- Kendi kendine Aralık-ekleme `basic_string` dizelerin içeriğini karıştıran bazı koşullar düzeltildi. (Note: kendinden aralığa ekleme, standart tarafından hala yasaktır.)
- `basic_string::shrink_to_fit()` artık ayırıcı `propagate_on_container_swap`tarafından etkilenmemektedir.
- `std::decay` artık, diğer bir deyişle, cv-qualified ve/veya ref-Qualified işlev türlerini, diğer bir deyişle, daha sonra işliyor.
- Değiştirilen büyük/küçük harfe duyarlılık ve eğik çizgi kullanma, taşınabilirliği artırma yönergeleri dahil.
- '*Enumeration*' numaralandırmasının anahtarındaki "Numaralandırıcı '*Numaralandırıcı*' sabit uyarı C4061, bir Case etiketi tarafından açıkça işlenmiyor. Bu uyarı varsayılan olarak kapalıdır ve uyarılar için standart kitaplığın genel ilkesinde özel bir durum olarak düzeltildi. (Standart Kitaplık **/W4** temiz, ancak **/duvar** temizleme yapmayı denemez. Birçok varsayılan uyarı son derece gürültülü ve düzenli olarak kullanılmak üzere tasarlanmamıştır.)
- `std::list` hata ayıklama denetimleri geliştirildi. Yineleyiciler listesi artık `operator->()`kontrol edin ve `list::unique()` artık yineleyiciler geçersiz kılındı olarak işaretler.
- `tuple`içinde sabit kullanımlar-ayırıcı meta programlama.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- `std::partition`, standart gerektiğinden, N + 1 kez değil, koşul N kez çağrı gerektirir.
- Sürüm 15,3 ' de sihirli statiği 'dan kaçınmaya yönelik girişimler, sürüm 15,5 ' de onarıldı.
- `std::atomic<T>` artık `T` varsayılan oluşturulabilir olmasını gerektirmez.
- Logaritmik hata ayıklama etkinken, girişin aslında bir yığında olduğu doğrusal bir zaman onaylama işlemi olmayan yığın algoritmaları.
- `__declspec(allocator)` artık, bu declspec anlayan, Clang uyarılarını engellemek için yalnızca C1XX için korunuyor.
- `basic_string::npos` artık derleme zamanı sabiti olarak kullanılabilir.
- C++ 17 modundaki `std::allocator`, artık daha fazla hizalanmış türlerin ayrılmasını, diğer bir deyişle, **/Zc: alignedNew-** tarafından devre dışı bırakılmadığı takdirde hizalama `max_align_t`daha büyük olan türler.  Örneğin, 16 baytlık veya 32 baytlık hizalamadaki nesne vektörleri artık SSE ve AVX yönergelerine göre doğru şekilde hizalanmıştır.

### <a name="conformance-improvements"></a>Uyumluluk geliştirmeleri

- \<\>, \<string_view\>, `apply()`, `make_from_tuple()`ekledik.
- İsteğe bağlı \<\>, \<varyant\>, `shared_ptr::weak_type`ve \<cstdalıgn\>eklendi.
- `min(initializer_list)`, `max(initializer_list)`ve `minmax(initializer_list)`ve `min_element()`, `max_element()`ve `minmax_element()`içinde C++ 14 `constexpr` etkinleştirildi.

Daha fazla bilgi için bkz [. C++ Microsoft dil uygunluk tablosu](../visual-cpp-language-conformance.md).

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- Birkaç ek C++ 17 özelliği uygulandı. Daha fazla bilgi için bkz [. C++ Microsoft dil uygunluk tablosu](cpp-conformance-improvements.md#improvements_153).
- Uygulanan P0602R0 "varyant ve isteğe bağlı, kopyalama/taşıma üç aylık dönemi yaymalıdır.
- Standart kitaplık artık, [/gr-](../build/reference/gr-enable-run-time-type-information.md) seçeneği aracılığıyla dinamik RTTI 'nin devre dışı bırakılmakta olduğunu gösterir. Hem `dynamic_pointer_cast()` hem de `rethrow_if_nested()` kendiliğinden `dynamic_cast`gerektirir, bu nedenle standart kitaplık artık bunları **/gr-** altında `=delete` olarak işaretler.
- Dinamik RTTı, "static RTTI" ile **/gr-** arasında devre dışı bırakılsa bile, `typeid(SomeType)` biçiminde hala kullanılabilir ve çeşitli standart kitaplık bileşenlerini güçlendirir. Standart kitaplık artık bu özelliğin devre dışı bırakılmasını destekler, **/d\_,\_statik\_RTTI = 0 ' dır**. Bu bayrak Ayrıca, `std::function``target()` ve `target_type()` üye işlevlerini ve `get_deleter()` ve `std::shared_ptr` `std::weak_ptr`arkadaş üye işlevini `std::any`devre dışı bırakır.
- Standart kitaplık artık, koşullu olarak tanımlanmış makrolar yerine koşulsuz olarak C++ 14 `constexpr` kullanır.
- Standart kitaplık artık dahili olarak diğer ad şablonlarını kullanır.
- Standart kitaplık artık `nullptr_t{}`yerine dahili olarak `nullptr` kullanır. (NULL 'in iç kullanımı eradkıdı. 0-null olarak iç kullanımı, yavaş bir şekilde temizleniyor.)
- Standart kitaplık artık `std::move()` `std::forward()`, stillistik yanlış kullanımı yerine dahili olarak kullanır.
- `static_assert(false, "message")` `#error message`olarak değiştirildi. Bu değişiklik, derlemeyi hemen durdurduğundan `#error` derleyici tanılamayı geliştirir.
- Standart kitaplık artık işlevleri `__declspec(dllimport)`olarak işaretler. Modern bağlayıcı teknolojisine artık gerek yoktur.
- SFıNAE 'yi, dönüş türleri ve işlev bağımsız değişken türleri ile karşılaştırıldığında dağınıklığı azaltılan varsayılan şablon bağımsız değişkenlerine ayıklandı.
- \<rastgele\> içindeki hata ayıklama denetimleri, `fputs()` **stderr**'e `_Rng_abort()` iç işlev yerine standart kitaplığın olağan makineleri kullanın. Bu işlevin uygulanması ikili uyumluluk için tutulmakta, ancak standart kitaplığın sonraki ikili uyumsuz sürümünde kaldırılmıştır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- Birkaç standart kitaplık özelliği, C++ 17 standardına uygun olarak eklenmiştir, kullanımdan kaldırılmıştır veya kaldırılmıştır. Daha fazla bilgi için bkz [ C++ . Visual Studio 'da uyumluluk geliştirmeleri](cpp-conformance-improvements.md#improvements_155).
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
- Aşağıdaki paralel algoritmaların imzaları Şu anda eklendi ancak paralelleştirilmedi; profil oluşturma, yalnızca öğeleri taşımanın veya persessize eden paralelleştirme algoritmalarında hiç avantaj bulunmadığını gösterdi:
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

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15,6

- \<memory_resource >
- Kitaplık temelleri v1
- `polymorphic_allocator` atamasını silme
- Sınıf şablonu bağımsız değişken kesintiyi geliştirme

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

- Paralel algoritmalar için destek artık deneysel değildir
- \<dosya sistemi > yeni bir uygulama
- Elemensel dize dönüştürmeleri (kısmi)
- `std::launder()`
- `std::byte`
- `hypot(x,y,z)`
- Gereksiz Decay önleme
- Matematik özel işlevleri
- `constexpr char_traits`
- Standart Kitaplık için kesinti Kılavuzu

Daha fazla bilgi için bkz [. C++ Microsoft dil uygunluk tablosu](../visual-cpp-language-conformance.md).

### <a name="performance-and-throughput-fixes"></a>Performans ve verimlilik düzeltmeleri

- `basic_string::find(char)` aşırı yükleme yalnızca bir kez `traits::find` çağrı yaptı. Daha önce, 1 uzunluğunda bir dize için genel bir dize araması olarak uygulanmıştır.
- `basic_string::operator==` artık dizelerin içeriğini karşılaştırmadan önce dizenin boyutunu denetler.
- Derleyici iyileştiricinin çözümlenmesi zor olan `basic_string`denetim bağlantısı kaldırıldı. Tüm kısa dizeler için `reserve` çağrılması, hiçbir şey yapmaz.
- `std::vector`, doğruluk ve performans açısından aşırı kullanılabilir: ekleme ve emplace işlemleri sırasında diğer ad artık standart için gereken şekilde doğru şekilde işlenmiştir, güçlü özel durum garantisi artık standart için `move_if_noexcept()` ve diğer aracılığıyla gerekli olduğunda sağlanır Logic, ve INSERT ve emplace daha az sayıda öğe işlemi gerçekleştirir.
- C++ Standart kitaplık artık null süslü işaretçilerin başvurusunu önler.
- İyileştirilmiş `weak_ptr::lock()` performansı.
- Derleyici aktarım hızını artırmak için C++ , standart kitaplık üstbilgileri artık gereksiz derleyici iç bilgileri için bildirimleri de bulundurmaktan kaçının.
- Üç defadan fazla `std::string` ve `std::wstring` taşıma oluşturucularının performansı geliştirildi.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- `std::atomic` uygulamasının yapılandırılmış özel durum Işleme (SEH) kullanan işlevlere uygulanmasını önleyen `noexcept` etkileşimleri etrafında çalışmıştır.
- Standart kitaplığın iç `_Deallocate()` işlevi, daha küçük bir koda en iyileştirmek için değiştirilmiştir ve bunun daha fazla yere satır içine alınmış olmasını sağlar.
- `std::try_lock()` özyineleme yerine paket genişletmesi kullanacak şekilde değiştirildi.
- `std::lock()` kilitlenme engelleme algoritması, tüm kilitlere `try_lock()` dönmek yerine `lock()` işlemleri kullanacak şekilde geliştirildi.
- `system_category::message()`' de adlandırılmış dönüş değeri Iyileştirmesi etkinleştirildi.
- `conjunction` ve `disjunction` artık 2N + 2 türleri yerine N + 1 tür bir örneği oluşturur.
- `std::function`, her tür silinmiş çağrılabilir için ayırıcı destek makineleri örneklemelerine, üretilen iş verimini artırarak ve birçok farklı lambdayı `std::function`bir şekilde geçiren programlarda. obj boyutunu azaltmasına artık izin vermez.
- `allocator_traits<std::allocator>` el ile satır içine alınmış `std::allocator` işlemleri içerir ve yalnızca `allocator_traits` `std::allocator` ile etkileşime geçen koddaki kod boyutunu azaltır (çoğu kodda).
- C++ 11 minimum ayırıcı arabirimi artık `allocator_traits` doğrudan çağrı yapan standart kitaplık tarafından işlenir. Bu, ayırıcıyı iç sınıf `_Wrap_alloc`sarmalama yerine Bu değişiklik, ayırıcı desteği için oluşturulan kod boyutunu azaltır, iyileştiricinin bazı durumlarda standart kitaplık kapsayıcıları hakkında neden olma yeteneğini geliştirir ve daha iyi bir hata ayıklama deneyimi sağlar (artık `_Wrap_alloc<your_allocator_type>` yerine ayırıcı türünü gördüğünüz için hata ayıklayıcı).
- , Ayırıcıların gerçekte özelleştirilmesine izin verilmeyen özelleştirilmiş `allocator::reference`için meta programlama kaldırıldı. (Ayrıcılar kapsayıcıların süslü işaretçiler kullanmasına karşın daha fazla başvuru yapamaz.)
- Derleyici ön ucu, hata ayıklama derlemelerinin performansını artırmak için Aralık tabanlı Döngülerde hata ayıklama yineleyicilerini sarmalandırmıştı.
- `shrink_to_fit()` ve `reserve()` için `basic_string` iç küçültme yolu artık, yeniden konumlandırma işlemlerinin yolunda değildir ve tüm Üyeler için kod boyutunu azaltır.
- `basic_string` iç büyüme yolu artık `shrink_to_fit()`yolunda değil.
- `basic_string` değiştirici işlemleri artık ayırılamayan hızlı yola ve yavaş yol işlevlerine bölünmüştür ve bu da yaygın olmayan bir servis talebinin çağıranlar halinde yer alınmasına neden olur.
- `basic_string` değiştirme işlemleri artık yeniden boyutlandırma yerine istenen durumda yeniden ayrılmış arabellekler oluşturur. Örneğin, bir dizenin başlangıcında ekleme artık içeriği yeniden ekleme işleminden sonra (aşağı veya yeni ayrılmış arabelleğe), yeniden konumlandırma durumunda (yeni ayrılan arabelleğe ve daha sonra aşağı) iki kez bir kez taşımıştır.
- \<dize\> C standart kitaplığını çağıran işlemler artık TLS ile yinelenen etkileşimi kaldırmak için `errno` adresini önbelleğe almak üzere.
- `is_pointer` uygulamasını basitleşme.
- İşlev tabanlı Ifade SFINAE ' nin `struct` ve `void_t`tabanlı olarak değiştirilmesi bitti.
- Standart Kitaplık algoritmaları artık, geri artan yineleyiciler yapmaktan kaçınır.
- 64-bit sistemlerde 32 bit ayırıcılar kullanılırken düzeltilen kesme uyarıları.
- `std::vector` taşıma ataması, mümkün olduğunda arabelleği yeniden kullanmak için artık eşit olmayan non-as-POSANMA olmayan durumda daha etkilidir.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- `basic_string<char16_t>` artık aynı `memcmp`, `memcpy`ve benzer iyileştirmelerin `basic_string<wchar_t>` englikleri.
- İşlev işaretçilerinin satır içine alınmış olmasını önleyen, Visual Studio 2015 güncelleştirme 3 ' te "işlevlerden kopyalanmaktan kaçının" çalışmamız tarafından sunulan bir iyileştirici sınırlaması, `lower_bound(iter, iter, function pointer)`, performansı geri yükleniyor.
- `includes`, `set_difference`, `set_symmetric_difference`ve `set_union` girişlerinin sıra doğrulama yükü, sıralamadan önce yineleyiciler sarmalanmadan düşürüldü.
- `std::inplace_merge` artık zaten konumunda olan öğeleri atlar.
- Artık `std::random_device` oluşturup `std::string`yok eder.
- `std::equal` ve `std::partition` bir yineleyici karşılaştırmayı kaydeden bir geçiş iş parçacığı iyileştirme geçişine sahipti.
- `std::reverse`, üç aylık kopyalanabilir `T`işaretçiler geçirildiğinde, artık el yazısı vektör haline getirilmiş bir uygulamaya gönderim yapılır.
- `std::fill`, `std::equal`ve `std::lexicographical_compare`, `memcmp` ve `std::byte` (ve diğer karakter benzeri numaralandırmalar ve Enum sınıfları) için `memset` ve `gsl::byte` gönderme hakkında daha fazla. `std::copy` `is_trivially_copyable`kullanarak dağıtımı yaptığından, hiçbir değişiklik gerektirmez.
- Standart Kitaplık, yalnızca bir davranışı, türlerin daha duyarlı olmayan bir şekilde geri dönüşlü hale getirmek için olduğu boş küme ayraçları yok.

## <a name="other-libraries"></a>Diğer Kitaplıklar

### <a name="open-source-library-support"></a>Açık kaynak kitaplık desteği

**Vcpkg** , Visual Studio 'da açık kaynaklı C++ STATIK-BS ve DLL 'ler alma ve oluşturma sürecini büyük ölçüde kolaylaştıran açık kaynaklı bir komut satırı aracıdır. Daha fazla bilgi için bkz. [vcpkg: Için C++bir paket yöneticisi ](../build/vcpkg.md).

### <a name="cpprest-sdk-290"></a>CPPRest SDK 2.9.0

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

İçin C++platformlar arası Web API 'Si olan CPPRestSDK, 2.9.0 sürümüne güncelleştirilmiştir. Daha fazla bilgi için bkz: [Cpprestsdk 2.9.0 GitHub 'da kullanılabilir](https://devblogs.microsoft.com/cppblog/cpprestsdk-2-9-0-is-available-on-github/).

### <a name="atl"></a>ATL

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- Ancak başka bir ad arama uyumluluğu düzeltmeleri kümesi
- Mevcut taşıma oluşturucuları ve taşıma atama işleçleri artık atma olarak düzgün şekilde işaretlendi
- Atlstr. h 'de yerel lekelerde iş parçacığı güvenli başlatması hakkında geçerli uyarı C4640
- Yerel statiklerin iş parçacığı güvenli başlatması, bir DLL oluşturmak için ATL kullanılırken otomatik olarak XP araç takımı 'nda devre dışı bırakıldı, ancak artık bu değil. İş parçacığı güvenli başlatma kapalıysa, proje ayarlarınıza **/Zc: threadSafeInit-** ekleyebilirsiniz.

### <a name="visual-c-runtime"></a>Görsel C++ çalışma zamanı

- Denetim akışı koruyucusu sembolleri için yeni "cfguard. h" üstbilgisi.

## <a name="c-ide"></a>C++ IDE

- Yapılandırma değiştirme performansı, C++ yerel projeleri için daha iyi, C++/CLI projeleri için ise çok daha iyi bir duruma geldi. Bir çözüm yapılandırması ilk kez etkinleştirildiğinde, artık daha hızlı olur ve bu çözüm yapılandırmasının sonraki tüm etkinleştirmeleri neredeyse anında gerçekleşir.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- Çeşitli proje ve kod sihirbazları, imza iletişim kutusu stilinde yeniden yazıldı.
- **Sınıf Ekle** artık doğrudan sınıf ekleme Sihirbazı 'nı başlatır. Daha önce burada olan diğer tüm öğeler artık > Ekle ' nin altında **Yeni öğe Ekle**' nin altında bulunabilir.
- Win32 projeleri artık **Yeni proje** Iletişim kutusunda **Windows Masaüstü** kategorisi altındadır.
- **Windows konsolu** ve **Masaüstü uygulama** şablonları artık bir sihirbaz görüntülemeden projeler oluşturur. Aynı kategoride, eski **Win32 konsol uygulaması** sihirbazıyla aynı seçenekleri görüntüleyen yeni bir **Windows Masaüstü Sihirbazı** var.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Yeniden C++ düzenleme ve kod gezintisi için IntelliSense altyapısını kullanan birkaç işlem çok daha hızlı çalışır. Aşağıdaki sayılar, 3500 projeleriyle Visual Studio Jmıum çözümüne dayalıdır:

|||
|-|-|
|Özellik|Performans Iyileştirmesi|
|Rename|5.3 x|
|Imzayı Değiştir |4.5 x|
|Tüm Başvuruları Bul|4.7 x|

C++Artık CTRL + tıklama **tanımına git**' i destekler. böylece, tanımlara kolay bir şekilde gezinme yapabilirsiniz. Üretkenlik güç araçları paketinden yapı görselleştiricisi, artık varsayılan olarak ürüne de dahildir.

## <a name="intellisense"></a>IntelliSense

- Yeni SQLite tabanlı veritabanı altyapısı artık varsayılan olarak kullanılıyor. Bu, **Tanıma Git** ve **tüm başvuruları bul**gibi veritabanı işlemlerini hızlandıracak ve ilk çözüm ayrıştırma süresini önemli ölçüde iyileştirmenize olanak sağlar. Ayar, **> metin düzenleyicisi > C/C++ > gelişmiş ' e > seçeneklere** taşındı (daha önce... C/C++ | Deneysel).

- Önceden derlenmiş üst bilgiler kullanmayan projelerde ve dosyalarda IntelliSense performansını geliştirdik. Geçerli dosyadaki üst bilgiler için otomatik önceden derlenmiş üst bilgi oluşturulur.

- Hata listesindeki IntelliSense hataları için hata filtreleme ve yardım özelliği ekledik. Şimdi hata sütununa tıklandığında filtreleme sağlanıyor. Ayrıca, belirli hatalara tıklandığında veya F1’e basıldığında, hata iletisi için bir çevrimiçi arama başlatılacak.

  ![Hata Listesi](media/ErrorList1.png "Hata Listesi")

  ![Hata Listesi filtrelenmiş](media/ErrorList2.png "Filtrelenmiş Hata Listesi")

- Üye Listesi öğelerini türe göre filtreleme özelliği eklendi.

  ![Üye listesi filtreleme](media/mlfiltering.png "Üye Listesi Filtreleme")

- Üye listesinde görüntülendiklere bağlamsal olarak uyumlu filtreleme sağlayan yeni bir deneysel tahmine dayalı IntelliSense özelliği eklendi. Daha fazla bilgi için bkz [ C++ . IntelliSense geliştirmeleri-tahmine dayalı IntelliSense & filtreleme](https://devblogs.microsoft.com/cppblog/c-intellisense-improvements-predictive-intellisense-filtering/).
- **Tüm başvuruları bul** (Shift + F12) artık karmaşık kod tabanlarında bile kolay bir şekilde yararlanmanıza yardımcı olur. Gelişmiş gruplandırma, filtreleme, sıralama, sonuçları içinde arama ve (bazı diller için) renklendirme sağlar, böylece başvurularınızı net bir şekilde anlayabilmenizi sağlayabilirsiniz. İçin C++yeni kullanıcı arabirimi, bir değişkene okuduğumuz veya bir değişkene yazma yapılıp yaptığımız hakkında bilgi içerir.
- Daha önce deneme sürecinde olan Noktadan Oka Dönüştürme IntelliSense özelliği artık gelişmiş düzeye gelmiştir ve varsayılan olarak etkindir. Düzenleyici özellikleri **kapsamlar ' ı genişletin** ve **genişletilmiş öncelik** de deneysel ' dan Gelişmiş ' e taşınmıştır.
- Deneysel yeniden düzenleme özellikleri **Imza değiştirme** ve **ayıklama işlevi** artık varsayılan olarak kullanılabilir.
- Projeler için C++ deneysel ' daha hızlı proje yükü ' özelliği eklendi. Bir projeyi bir C++ sonraki açışınızda daha hızlı yüklenir ve bu süre sonra *çok* daha hızlı yüklenecektir!
- Bu özelliklerden bazıları diğer dillerde ortaktır ve bazıları için C++özeldir. Bu yeni özellikler hakkında daha fazla bilgi için bkz. [Visual Studio "15" Preview 5 duyurusu](https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-15-preview-5/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

- ClangFormat için destek eklendi. Daha fazla bilgi için bkz. [Visual Studio 2017 ' de Clangformat desteği](https://devblogs.microsoft.com/cppblog/clangformat-support-in-visual-studio-2017-15-7-preview-1/).

## <a name="non-msbuild-projects-with-open-folder"></a>Açık klasörü olan MSBuild olmayan projeler

Visual Studio 2017, hiçbir çözüm veya proje oluşturmak zorunda kalmadan kaynak kodu içeren bir klasörde kodlamanıza, oluşturmanıza ve hata ayıklamanıza olanak sağlayan **açık klasör** özelliğini tanıtır. Artık, projeniz MSBuild tabanlı bir proje olmasa bile Visual Studio 'Yu kullanmaya başlamak çok basittir. **Açık klasör**sayesinde, Visual Studio 'nun MSBuild projeleri için zaten sağladığı güçlü kod anlama, düzenlemesi, derleme ve hata ayıklama özelliklerine erişebilirsiniz. Daha fazla bilgi için bkz. [klasör projelerini C++açın ](../build/open-folder-projects-cpp.md).

- Klasör Aç deneyimi geliştirmeleri. Bu. JSON dosyaları aracılığıyla deneyimi özelleştirebilirsiniz:
  - IntelliSense ve göz atma deneyimini özelleştirmek için CppProperties.json.
  - Derleme adımlarını özelleştirmek için Tasks.json.
  - Hata ayıklama deneyimini özelleştirmek için Launch.json.

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- Alternatif derleyiciler ve MinGW ve Cygwin gibi yapı ortamları için geliştirilmiş destek. Daha fazla bilgi için bkz. [MinGW ve Cygwin 'Yi Visual C++ ve açık klasörü kullanma](https://devblogs.microsoft.com/cppblog/using-mingw-and-cygwin-with-visual-cpp-and-open-folder/).
- CppProperties. JSON ve CMakeSettings. JSON içinde genel ve yapılandırmaya özgü ortam değişkenlerini tanımlamaya yönelik destek eklendi. Bu ortam değişkenleri, Launch. vs. JSON ve Tasks. vs. JSON içinde tanımlanan hata ayıklama yapılandırmalarına göre tüketilebilir. Daha fazla bilgi için bkz. [ortamınızı görsel C++ ve açık klasör ile özelleştirme](https://devblogs.microsoft.com/cppblog/customizing-your-environment-with-visual-c-and-open-folder/).
- 64 bitlik platformları kolayca hedefleyebilme özelliği de dahil olmak üzere CMake Dokja üreticisi için geliştirilmiş destek.

## <a name="cmake-support-via-open-folder"></a>Açık klasör aracılığıyla CMake desteği

Visual Studio 2017, MSBuild proje dosyalarına (. vcxproj) dönüştürülmeksizin CMake projelerini kullanma desteği sunar. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md). **Açık klasörü** olan CMake projelerini açmak, ortamı düzenlenmek, oluşturmak C++ ve hata ayıklama için otomatik olarak yapılandırır.

- C++IntelliSense, kök klasörde CppProperties. JSON dosyası oluşturmaya gerek kalmadan işe yarar. Ayrıca, kullanıcıların CMake ve CppProperties. JSON dosyaları tarafından verilen yapılandırmalara kolayca geçiş yapmasına olanak tanımak için yeni bir açılan menü ekledik.

- CMakeLists.txt dosyasıyla aynı klasörde yer alan CMakeSettings.json dosyasıyla ek yapılandırma gerçekleştirilmesi desteklenir.

  ![CMake klasör aç](media/cmake-cpp.png "CMake klasör aç")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- CMake Dokja Oluşturucu için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- Mevcut CMake önbellekleri içeri aktarılmaya yönelik destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- CMake 3,11 için destek eklendi, CMake projelerinde kod analizi, Çözüm Gezgini içinde hedefleri, önbellek oluşturma seçeneklerini ve tek dosya derlemesini destekler. Daha fazla bilgi için bkz. Visual [Studio 'Da CMake desteği](https://devblogs.microsoft.com/cppblog/cmake-support-in-visual-studio-targets-view-single-file-compilation-and-cache-generation-settings/) ve [Visual Studio 'da CMake projeleri](../build/cmake-projects-in-visual-studio.md).

## <a name="windows-desktop-development-with-c"></a>İle Windows masaüstü geliştirmeC++

Özgün C++ iş yükünü yüklemek için şimdi daha ayrıntılı bir yükleme deneyimi sağlıyoruz. Tam olarak ihtiyacınız olan araçları yükleyebilmenizi sağlayan, seçilebilir bileşenler ekledik. Yükleyici Kullanıcı arabiriminde listelenen bileşenlerin belirtilen yükleme boyutları doğru değil ve toplam boyutu düşük olarak tahmin ediyor.

C++ masaüstü iş yükünde Win32 projelerini başarıyla oluşturabilmek için, hem araç takımını hem de Windows SDK’yi yüklemelisiniz. Çalıştığından emin olmak için önerilen (seçili) bileşenleri **VC + + 2017 v141 araç takımı (x86, x64)** ve **Windows 10 SDK (10.0.** Gerekli araçlar yüklü değilse, projeler başarıyla oluşturulmaz ve sihirbaz askıda kalır.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Visual C++ derleme araçları (daha önce tek başına bir ürün olarak kullanılabilir) artık Visual Studio yükleyicisi bir iş yükü olarak eklenmiştir. Bu iş yükü, yalnızca Visual Studio IDE 'yi C++ yüklemeden projeler oluşturmak için gereken araçları kurar. Hem v140 hem de v141 araç takımları dahil edilmiştir. V141 araç takımı, Visual Studio 2017 sürüm 15,5 ' deki en son geliştirmeleri içerir. Daha fazla bilgi için bkz. [şimdi VISUAL STUDIO derleme araçları VS2017 ve VS2015 MSVC Toolsets](https://devblogs.microsoft.com/cppblog/visual-studio-build-tools-now-include-the-vs2017-and-vs2015-msvc-toolsets/)' i içerir.

## <a name="linux-development-with-c"></a>İle Linux geliştirmeC++

Popüler [Linux Geliştirme için Visual C++](https://visualstudiogallery.msdn.microsoft.com/725025cf-7067-45c2-8d01-1e0fd359ae6e) eklentisi artık Visual Studio’nun bir parçasıdır. Bu yükleme, Linux ortamında çalışan C++ uygulamalarını geliştirmek ve hatalarını ayıklamak için ihtiyacınız olan her şeyi sağlar.

##### <a name="visual-studio-2017-version-152"></a>Visual Studio 2017 sürüm 15,2

Platformlar arası kod paylaşımı ve tür görselleştirmede geliştirmeler yapılmıştır. Daha fazla bilgi için bkz [. C++ platformlar arası kod paylaşımı ve tür görselleştirme için Linux geliştirmeleri](https://devblogs.microsoft.com/cppblog/linux-cross-platform-and-type-visualization/).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- Linux iş yükü, uzak Linux makinelerine dosya eşitlemek için **SFTP** 'ye alternatif olarak **rsync** desteği eklemiştir.
- ARM mikro denetleyicileri hedefleyen çapraz derleme için destek eklendi. Yükleme sırasında etkinleştirmek için, iş yüküyle **Linux geliştirmeyi C++**  seçin ve **katıştırılmış ve IoT geliştirme**seçeneğini belirleyin. Bu seçenek, ARM GCC çapraz derleme araçlarını ekler ve yüklemenize yapılır. Daha fazla bilgi için bkz. [Visual Studio 'Da ARM GCC çapraz derlemesi](https://devblogs.microsoft.com/cppblog/arm-gcc-cross-compilation-in-visual-studio/).
- CMake için destek eklendi. Artık, Visual Studio projesine dönüştürmek zorunda kalmadan mevcut CMake kod tabanınız üzerinde çalışabilirsiniz. Daha fazla bilgi için bkz. [Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md).
- Uzak görevleri çalıştırmaya yönelik destek eklendi. Bu özellik, Visual Studio 'nun bağlantı Yöneticisi 'nde tanımlanmış uzak bir sistemde herhangi bir komutu çalıştırmanızı sağlar. Uzak görevler Ayrıca uzak sisteme dosya kopyalama özelliğini de sağlar.
Daha fazla bilgi için bkz. [Linux CMake projesini yapılandırma](../linux/cmake-linux-project.md).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

- Linux iş yükü senaryolarında çeşitli geliştirmeler. Daha fazla bilgi için bkz [. C++ proje sisteminde Linux iş yükü geliştirmeleri, Linux konsol penceresi, rsync ve işleme iliştirme](https://devblogs.microsoft.com/cppblog/linux-c-workload-improvements-to-the-project-system-linux-console-window-rsync-and-attach-to-process/).
- Uzak Linux bağlantılarında üst bilgiler için IntelliSense. Daha fazla bilgi için bkz. [uzak Linux üstbilgileri Için IntelliSense](https://devblogs.microsoft.com/cppblog/intellisense-for-remote-linux-headers/) ve [bir Linux CMake projesi yapılandırma](../linux/cmake-linux-project.md).

## <a name="game-development-with-c"></a>İle oyun geliştirmeC++

C++’ın gücünü kullanarak DirectX veya Cocos2d tarafından desteklenen profesyonel oyunlar oluşturun.

## <a name="mobile-development-with-c-android-and-ios"></a>İle C++ mobil geliştirme (Android ve iOS)

Artık Visual Studio kullanarak Android ve iOS platformlarını hedefleyebilen mobil uygulamalar geliştirebilir ve hatalarını ayıklayabilirsiniz.

## <a name="universal-windows-apps"></a>Evrensel Windows Uygulamaları

C++, Evrensel Windows Uygulaması iş yükü için isteğe bağlı bir bileşen olarak sağlanır.  C++ projelerinin şu anda el ile yükseltilmesi gerekiyor. Visual Studio 2017 ' de v140 hedefli bir Evrensel Windows Platformu Projesi açarsanız, Visual Studio 2015 ' in yüklü olmadığı durumlarda proje özellik sayfalarında v141 platform araç takımını seçmeniz gerekir.

## <a name="new-options-for-c-on-universal-windows-platform-uwp"></a>Evrensel Windows Platformu (UWP C++ ) için yeni seçenekler

Artık Evrensel Windows Platformu ve Windows Mağazası için uygulama yazma ve C++ paketlemeye yönelik yeni seçenekleriniz vardır: mevcut masaüstü UYGULAMANıZı veya com nesnesini dağıtım için şu şekilde paketlemek üzere masaüstü köprü altyapısını kullanabilirsiniz: Dışarıdan yükleme yoluyla Windows Mağazası veya mevcut kanallarınız aracılığıyla. Windows 10 ' daki yeni yetenekler, masaüstü uygulamanıza çeşitli yollarla UWP işlevselliği eklemenize olanak tanır. Daha fazla bilgi için bkz. [Masaüstü Köprüsü](/windows/uwp/porting/desktop-to-uwp-root).

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Masaüstü ile masaüstü uygulamalarının paketlenmesi büyük ölçüde basitleşerek bir **Windows uygulaması paketleme projesi** proje şablonu eklenmiştir. Dosya | altında kullanılabilir  **Yeni | Proje | Yüklendi | Görsel C++ | Evrensel Windows Platformu**. Daha fazla bilgi için bkz. [Visual Studio (Masaüstü Köprüsü) kullanarak bir uygulamayı paketleme](/windows/uwp/porting/desktop-to-uwp-packaging-dot-net).

Yeni kod yazarken artık yalnızca başlık dosyalarında uygulanan Windows Çalışma Zamanı C++için standart C++ bir dil projeksiyonu olan/wınrt 'yi kullanabilirsiniz. Her iki standartlara uyumlu C++ derleyici kullanarak Windows çalışma zamanı API 'leri yazar ve kullanmanızı sağlar. C++/Wınrt, geliştiricilere modern Windows C++ API 'sine ilk sınıf erişim sağlayacak şekilde tasarlanmıştır. Daha fazla bilgi için bkz [ C++./wınrt: C++ modern Windows çalışma zamanı](https://moderncpp.com/).

Windows SDK Insider Preview 'ın derleme 17025 itibariyle, C++/wınrt Windows SDK dahil edilmiştir. Daha fazla bilgi için bkz [ C++./wınrt artık Windows SDK içeriyor](https://devblogs.microsoft.com/cppblog/cppwinrt-is-now-included-the-windows-sdk/).

## <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Visual Studio 2017 ile birlikte gelen Clang/C2 araç takımı artık büyük projeler oluşturmak için önemli olan **/bigobj** anahtarını destekliyor. Ayrıca, derleyicinin hem ön ucunda hem de arka ucunda bazı önemli hata düzeltmeleri de içerir.

## <a name="c-code-analysis"></a>C++Kod Analizi

[C++ Temel Yönergeleri](https://github.com/isocpp/CppCoreGuidelines)’nin uygulanmasını sağlayan C++ Temel Denetleyicileri artık Visual Studio ile dağıtılmaktadır. Projenin özellik sayfalarındaki **Kod Analizi uzantıları** sayfasında bulunan denetleyicileri etkinleştirmek yeterlidir ve Kod analizini çalıştırdığınızda uzantılar dahil edilir. Daha fazla bilgi için bkz. [ C++ temel yönergeler denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

![CppCoreCheck](media/CppCoreCheck.png "CppCoreCheck özellikleri sayfası")

##### <a name="visual-studio-2017-version-153"></a>Visual Studio 2017 sürüm 15,3

- Kaynak yönetimiyle ilgili kurallar için destek eklendi.

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

- Yeni C++ temel kılavuz denetimleri, akıllı işaretçi doğruluğunu, genel başlatıcıların doğru kullanımını ve `goto` ve hatalı yayınlar gibi yapıların kullanımları işaretlerinin ele alınmaktadır.

- 15.3 sürümünde karşılaşabileceğiniz bazı uyarı numaraları 15.5 sürümünde artık mevcut değil. Bu uyarıların yerine daha belirgin denetimler kullanıma sunuldu.

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15,6

- Tek Dosya Analizi için destek eklendi ve çözümleme çalışma zamanı performansı geliştirmeleri. Daha fazla bilgi için bkz [ C++ . Visual Studio için statik analiz geliştirmeleri 2017 15,6 Preview 2](https://devblogs.microsoft.com/cppblog/c-static-analysis-improvements-for-visual-studio-2017-15-6-preview-2/)

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

- Çalıştırılacak kod analizi kurallarını belirtmenize imkan tanıyan [/Analyze: RuleSet](../build/reference/analyze-code-analysis.md)için destek eklendi.
- Ek C++ temel kılavuz kuralları için destek eklendi.  Daha fazla bilgi için bkz. [ C++ temel yönergeler denetleyicilerini kullanma](/visualstudio/code-quality/using-the-cpp-core-guidelines-checkers).

## <a name="unit-testing"></a>Birim testi

##### <a name="visual-studio-2017-version-155"></a>Visual Studio 2017 sürüm 15,5

Google test bağdaştırıcı ve Boost. test bağdaştırıcısı artık iş yüküyle **Masaüstü geliştirmenin C++**  bileşenleri olarak kullanılabilir ve **Test Gezgini**ile tümleşiktir. **Test Gezgini** ile tam tümleştirme henüz mevcut olmasa da CMake projeleri Için ctest desteği eklendi (açık klasör kullanılarak). Daha fazla bilgi için bkz. [C/C++Için birim testleri yazma](/visualstudio/test/writing-unit-tests-for-c-cpp).

##### <a name="visual-studio-2017-version-156"></a>Visual Studio 2017 sürüm 15,6

- Boost. test dinamik kitaplık desteği için destek eklendi.
- Bir Boost. test öğe şablonu artık IDE 'de kullanılabilir.

Daha fazla bilgi için bkz [. Boost. test birim testi: dinamik kitaplık desteği ve yeni öğe şablonu](https://devblogs.microsoft.com/cppblog/boost-test-unit-testing-dynamic-library-support-and-new-item-template/).

##### <a name="visual-studio-2017-version-157"></a>Visual Studio 2017 sürüm 15,7

Birim testi projeleri için C++ [CodeLens](/visualstudio/ide/find-code-changes-and-other-history-with-codelens) desteği eklendi. Daha fazla bilgi için bkz. [birim testi Için C++ CodeLens duyurusu](https://devblogs.microsoft.com/cppblog/announcing-codelens-for-c-unit-testing/).

## <a name="visual-studio-graphics-diagnostics"></a>Visual Studio grafik tanılama

Visual Studio Grafik Tanılama, Direct3D uygulamalarında işleme ve performans sorunlarını kaydetmek ve analiz etmek için bir araç kümesidir. Grafik Tanılama özellikler, Windows bilgisayarınızda, Windows cihaz öykünücüsünde veya uzak bir bılgısayarda veya cihazda yerel olarak çalışan uygulamalarla kullanılabilir.

- **Köşe ve geometri gölgelendiriciler Için giriş & çıkışı:** Köşe gölgelendiricilerinin ve geometri gölgelendiricilerin giriş ve çıkışını görüntüleyebilme özelliği, en çok istenen özelliklerden biridir ve artık araçlarda destekleniyor. Aşağıdaki tabloda giriş ve çıkışını inceleyerek, işlem hattı aşamaları görünümünde VS veya GS aşamasını seçmeniz yeterlidir.

  ![Gölgelendiriciler için giriş/çıkış](media/io-shaders.png)

- **Nesne tablosunda arama ve filtreleme:** Aradığınız kaynakları bulmanın hızlı ve kolay bir yolunu sağlar.

  ![Ara](media/search.png)

- **Kaynak geçmişi:** Bu yeni görünüm, yakalanan bir çerçevenin işlenmesi sırasında kullanılan bir kaynağın tüm değişiklik geçmişini görmenin kolaylaştırılmış bir yolunu sunar. Herhangi bir kaynak için geçmişi çağırmak üzere herhangi bir kaynak köprüsü yanındaki saat simgesine tıklamanız yeterlidir.

  ![Kaynak geçmişi](media/resource-history.png)

  Bu işlem, kaynağın değişiklik geçmişiyle doldurulan yeni **kaynak geçmişi** araç penceresini gösterir.

  ![Kaynak geçmişi değişikliği](media/resource-history-change.png)

  Çerçevesanınızın tam çağrı yığını yakalaması etkin (**Visual studio > araçları >** **Grafik tanılama**) ile yakalandıysa, her bir değişiklik olayının bağlamı hızlı bir şekilde ele alınabilir ve Visual Studio projeniz içinde incelenebilir.

- **API İstatistikleri:** Çerçeveinizdeki API kullanımının üst düzey özetini görüntüleyin. Her seferinde yaptığınız fark etmediğiniz veya çok fazla yaptığınız çağrılardan oluşan çağrıları bulmak için kullanışlıdır. Bu pencere, Visual Studio Grafik Çözümleyicisi içindeki **View > API istatistikleri** aracılığıyla kullanılabilir.

  ![API istatistikleri](media/api-stats.png)

- **Bellek İstatistikleri:** Çerçevede oluşturduğunuz kaynaklar için sürücünün ne kadar bellek ayırıyor olduğunu görüntüleyin. Bu pencere, **Visual Studio grafik Çözümleyicisi**' de **Görüntüleme > bellek istatistikleri** aracılığıyla kullanılabilir. Veriler, bir elektronik tabloda görüntülenmek üzere sağ tıklayıp **Tümünü Kopyala**' yı seçerek bir CSV dosyasına kopyalanabilir.

  ![Bellek İstatistikleri](media/memory-stats.png)

- **Çerçeve doğrulaması:** Yeni hatalar ve uyarılar listesi, Direct3D hata ayıklama katmanının algıladığı olası sorunlara göre olay listenizde gezinmek için kolay bir yol sağlar. Pencereyi açmak için Visual Studio Grafik Çözümleyicisi **> çerçeve doğrulamayı görüntüle** ' ye tıklayın. Ardından, çözümlemeyi başlatmak için **doğrulamayı Çalıştır** ' a tıklayın. Çerçevenin karmaşıklığına bağlı olarak tamamlanması birkaç dakika sürebilir.

  ![Çerçeve doğrulama](media/frame-validation.png)

- **D3D12 Için Çerçeve Analizi:** Çerçeve analizini, yönlendirilmiş "durum" denemeleri ile çizilen çağrı performansını çözümlemek için kullanın. Çerçeve Analizi sekmesine geçin ve raporu görüntülemek için analiz çalıştırın. Daha fazla ayrıntı için, [Goingnative 25: Visual Studio grafik çerçeve çözümlemesi](https://channel9.msdn.com/Shows/C9-GoingNative/GoingNative-25-Offline-Analysis-Graphics-Tool) videosunu izleyin.

  ![Çerçeve Analizi](media/frame-analysis.png)

- **GPU kullanımı iyileştirmeleri:** Açık izlemeler, daha ayrıntılı analizler için GPU görünümü veya Windows Performans Çözümleyicisi (WPA) aracıyla Visual Studio GPU kullanımı profil oluşturucu aracılığıyla alınabilir. Windows performans araç seti yüklüyse, bir diğeri, bir WPA ve GPU için başka bir deyişle, oturum genel bakış ' a kadar olmak üzere iki köprü bulunur.

  ![GPU kullanımı](media/gpu-usage.png)

  Bu bağlantı aracılığıyla GPU görünümünde açılan izlemeler, VS ve GPU görünümü arasındaki zaman çizelgesinde eşitlenmiş yakınlaştırma ve yatay kaydırmayı destekler. VS 'deki bir onay kutusu, eşitlemenin etkin olup olmadığını denetlemek için kullanılır.

  ![GPU görünümü](media/gpu-view.png)

::: moniker-end

::: moniker range="=vs-2015"

Visual Studio 2015 güncelleştirme 3 ' ten yeniliklerin tamamı hakkında bilgi için bkz. [Visual C++ Studio 'nun yenilikler 2003-2015](/cpp/porting/visual-cpp-what-s-new-2003-through-2015). Visual Studio 2015 ' deki yenilikler hakkında daha fazla bilgi için bkz. [Visual studio 2015 Sürüm notları geçmişinden](/visualstudio/releasenotes/vs2015-version-history)bağlantılı sürüm notları. Visual Studio 2019 ' C++ deki yenilikler hakkında daha fazla bilgi için bkz. [Visual Studio C++ 'daki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2019)yenilikler. Visual Studio 2017 ' C++ deki yenilikler hakkında daha fazla bilgi için bkz. [Visual Studio 2017 ' C++ deki](/cpp/overview/what-s-new-for-visual-cpp-in-visual-studio?view=vs-2017)yenilikler.

::: moniker-end
