---
title: Visual Studio 2017’deki C++ yenilikleri
description: Visual Studio 2019 ' de Microsoft C/C++ derleyicisinde ve araçlarındaki yeni özellikler ve düzeltmeler.
ms.date: 03/03/2021
ms.technology: cpp-ide
ms.openlocfilehash: c48b733ad18d57917220b443bd18830441dc693c
ms.sourcegitcommit: f8ba5db09d05683b24c58505f0e57c21f85545dc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103087187"
---
# <a name="whats-new-for-c-in-visual-studio"></a>Visual Studio 2017’deki C++ yenilikleri

Visual Studio 2019, Microsoft C++ ortamına birçok güncelleştirme ve düzeltme getirir. Derleyicide ve araçlarda birçok hata ve sorunu düzelttik. Bu sorunların birçoğu, müşteriler tarafından [bir sorun bildir](/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019&preserve-view=true) ve **geri bildirim gönder** altında [bir öneri](https://aka.ms/feedback/suggest?space=62) seçenekleri sunarak gönderilmiştir. Hataları bildirdiğiniz için teşekkür ederiz!

Visual Studio 'nun tüm yenilikleri hakkında daha fazla bilgi için [Visual studio 2019 'deki](/visualstudio/ide/whats-new-visual-studio-2019)yenilikler sayfasını ziyaret edin. Visual Studio 2017 ' de C++ yenilikleri hakkında daha fazla bilgi için bkz. [Visual studio 2017 ' de c++](what-s-new-for-cpp-2017.md)yenilikleri. Visual Studio 2015 ve önceki sürümlerde C++ yenilikleri hakkında daha fazla bilgi için, bkz. yenilikler [2003 ile 2015 Visual C++](../porting/visual-cpp-what-s-new-2003-through-2015.md). C++ docs 'taki yenilikler hakkında daha fazla bilgi için bkz. [Microsoft C++ docs: yenilikler](whats-new-cpp-docs.md).

## <a name="whats-new-for-c-in-visual-studio-version-169"></a>Visual Studio sürüm 16,9 ' de C++ yenilikleri

Visual Studio sürüm 16,9 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,9 ' deki](/visualstudio/releases/2019/release-notes#--visual-studio-2019-version-1690-)yenilikler.

- [Adres Temizleme](../sanitizers/asan.md):

  - Windows 'daki adres Temizleme desteğiniz deneysel moddadır ve genel kullanıma ulaştı.

  - Genişletilmiş `RtlAllocateHeap` destek, `RtlCreateHeap` `RtlAllocateHeap` yürütülebilir bellek havuzları oluştururken ve yakalayıcılar ile ilgili bir uyumluluk sorunu düzeltildi.

  - Eski `GlobalAlloc` ve `LocalAlloc` bellek ailesi işlevleri için destek eklendi. Ortam bayrağını ayarlayarak bu yakalayıcılar etkinleştirebilirsiniz `ASAN_OPTIONS=windows_hook_legacy_allocators=true` .

  - Sorunların ve çözümlerinin açıkça görülebilmesi için araya gölge bellek alma ve iletim hatasına işaret eden hata iletileri güncelleştirildi.

  - IDE tümleştirmesi şimdi ASan tarafından raporlanabilen özel durum koleksiyonunun tamamını işleyebiliyor.

  - Derleyici ve bağlayıcı, ASan ile derleme yaptığınız ancak hata ayıklama bilgilerini yayma işlemlerini tespit ederken hata ayıklama bilgilerini yayma önerisinde bulunur.

- Artık, OpenMP çalışma zamanının LLVM sürümünü yeni CL anahtarıyla hedefleyebilirsiniz **`/openmp:llvm`** . Bu, `lastprivate` `#pragma omp` bölümlere ve paralel Döngülerde imzasız Dizin değişkenlerine yönelik yan tümce için destek ekler `for` . **`/openmp:llvm`** Anahtar şu anda yalnızca AMD64 hedefi için kullanılabilir ve hala deneysel bir değer.

- Visual Studio CMake projeleri artık uzak Windows geliştirme için birinci sınıf desteğe sahiptir. Bu destek CMake projesini Windows ARM64'ü hedefleyecek şekilde yapılandırmayı, projeyi uzak Windows makinesine dağıtmayı ve uzak Windows makinesindeki projede Visual Studio'dan hata ayıklaması yapmayı içeriyor.

- Windows üzerinde Visual Studio ile gönderilen Ninja sürümü 1.10'a güncelleştirildi. Nelerin dahil olduğu hakkında daha fazla bilgi için bkz. [Dokja 1,10 sürüm notları](https://groups.google.com/g/ninja-build/c/piOltAhywFA/m/zPfkrTtRCwAJ?pli=1).

- Visual Studio ile gönderilen CMake sürümü 3.19'a güncelleştirildi. Dahil olanlar hakkında daha fazla bilgi için [CMake 3,19 sürüm notlarına](https://cmake.org/cmake/help/latest/release/3.19.html)bakın.

- [STL `nodiscard` as 'de çok sayıda kilit/koruma türü işaretlenmiş ](https://github.com/microsoft/STL/pull/1495).

- IntelliSense:

  - IntelliSense'de içeri aktarılan modüllerin ve üst bilgi birimlerinin tamamlanmasını sağlama kararlılığı ve işlevselliği geliştirildi.

  - Modül içeri aktarmaları, için dizin oluşturma desteği `export {...}` ve aynı ada sahip modüller için daha doğru modül başvurusu eklendi.

  - [Başvuru doğrudan başlatmasında geçici bir kopyalama başlatma](https://wg21.link/P1358R0)desteği ekleyerek C++ IntelliSense 'in dil uyumluluğu geliştirildi `__builtin_memcpy` ve `__builtin_memmove` [İşlevler, `constexpr` ve `consteval` işlevleri arasındaki tutarsızlıkları düzeltme](https://wg21.link/P1937R2), [sabit ifadelerde yaşam süresi genişletilmiş geçiciler](https://wg21.link/P1968R0)ve [benzer türler ve başvuru bağlama](https://wg21.link/P1358R0).

  - make_unique, make_shared, emplace ve emplace_back için belirtilen tür parametresi temelinde tamamlama sağlayan tamamlama işlevselliği eklendi.

- MSVC artık ikili dosyalarınız için gerekli olan doğru adres temizleyici çalışma zamanlarını belirliyor. Yeni değişiklikler Visual Studio projenize otomatik olarak uygulanacak. Komut satırında adres Temizleme 'yi kullanırken, artık yalnızca derleyiciye geçiş yapmanız gerekir [`/fsanitize=address`](../build/reference/fsanitize.md) .

- Visual Studio Bağlantı Yöneticisi artık ECDSA ortak anahtar algoritmasını kullanan özel anahtarları destekliyor.

- 11 sürümüne ait yükleyici ile gelen LLVM ve Clang sürümleri güncelleştirildi. Daha fazla bilgi için [LLVM](https://releases.llvm.org/11.0.0/docs/ReleaseNotes.html) ve [Clang](https://releases.llvm.org/11.0.0/tools/clang/docs/ReleaseNotes.html) sürüm notlarına bakın.

- Visual Studio artık IntelliSense yapılandırması için araç zinciri dosyalarındaki CMake değişkenlerini kullanacak. Bu, katıştırılmış kaynaklar ve Android geliştirme için daha iyi bir deneyim sunacak.

- Yok edicilerin ve yeni ifadelerin olmasına izin veren [daha fazla constexpr kapsayıcıları teklifinin](https://wg21.link/P0784R7)uygulanması **`constexpr`** . Bu, ve gibi yardımcı programların yolunu alır **`constexpr`** `std::vector` `std::string` .

- Tanıma Git, Modüle Git ve üye tamamlaması dahil olmak üzere IntelliSense C++20 modüllerine yönelik genişletilmiş destek.

- [Kısaltılmış işlev şablonları](https://en.cppreference.com/w/cpp/language/function_template#Abbreviated_function_template) artık MSVC derleyicisinde desteklenmektedir.

## <a name="whats-new-for-c-in-visual-studio-version-168"></a>Visual Studio sürüm 16,8 ' de C++ yenilikleri

Visual Studio sürüm 16,8 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,8 ' deki](/visualstudio/releases/2019/release-notes-v16.8)yenilikler.

- C++ 20 eş değerleri artık altında [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) ve \<coroutine> üst bilgisinde desteklenmektedir.

- IntelliSense şimdi C++20 \<concepts> ve \<ranges> üst bilgileri için destek ve kavram tanımlarına yönelik yeniden adlandırma ve göz atma deneyimi sağlar.

- STL’miz şimdi C++20 Aralıklarının çoğu için destek sunar.

- [Koşullu basit özel üye işlevleri](https://wg21.link/P0848R3) artık MSVC’de desteklenmektedir.

- C11 ve C17 artık [ `/std:c11` ve `/std:c17` ](../build/reference/std-specify-language-standard-version.md) anahtarları altında destekleniyor.

- Ek STL geliştirmeleri [`std::atomic_ref`](https://wg21.link/p0019r8) , [ `std::midpoint` `std::lerp` ve için](https://wg21.link/p0811r3) tam destek [`std::execution::unseq`](https://wg21.link/p1001r2) ve için iyileştirmeler içerir [`std::reverse_copy`](../standard-library/algorithm-functions.md#reverse_copy) .

- Visual Studio ile birlikte gelen CMake sürümünü [CMake 3.18](https://cmake.org/cmake/help/latest/release/3.18.html)’e yükselttik.

- Kod analizi araçlarımız şimdi endüstri standardı statik analiz günlük biçimi olan SARIF 2.1 standardını destekler.

- Linux projelerinde derleme araçları eksik olduğunda artık araç çubuğunda bir uyarı verilir ve hata listesinde eksik araçların net bir açıklaması sunulur.

- Artık doğrudan Visual Studio’dan WSL veya uzak bir Linux sisteminde Linux çekirdek dökümlerinin hata ayıklamasını yapabilirsiniz.

- C++ doxygen açıklama oluşturma için, ek açıklama stili seçenekleri ekledik ( `/*!` ve `//!` ).

- Ek [vcpkg duyuruları](https://aka.ms/vcpkg/team).

- Değerlendirilmeyecek bağlamlarda Lambdalar için derleyici desteği.

- [`/DEBUG:FULL`](../build/reference/debug-generate-debug-info.md) Çoklu iş parçacığı PDB oluşturma tarafından geliştirilmiş bağlantı performansı. Çeşitli büyük uygulamalar ve AAA oyunları bağlantı oluşturmaya kıyasla 2 ila 4 kat daha hızlı görüntüleniyor.

- Visual Studio hata ayıklayıcısı artık için destek içerir **`char8_t`** .

- clang-cl kullanarak ARM64 projelerine yönelik destek eklendi.

- [Intel AMX iç bilgileri](https://software.intel.com/content/www/us/en/develop/documentation/cpp-compiler-developer-guide-and-reference/top/compiler-reference/intrinsics/intrinsics-for-intel-advanced-matrix-extensions-intel-amx-instructions.html) desteği.

## <a name="whats-new-for-c-in-visual-studio-version-167"></a>Visual Studio sürüm 16,7 ' de C++ yenilikleri

Visual Studio sürüm 16,7 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,7 ' deki](/visualstudio/releases/2019/release-notes-v16.7)yenilikler.

- Uzaktan C++ desteğiniz artık sh, csh, bash, tsch, ksh, zsh ve dash dahil olmak üzere daha geniş kapsamlı Linux dağıtımlarını ve kabuklarını destekler. ConnectionManager.exe aracılığıyla yeni "shell" özelliğini değiştirerek uzaktan bağlantı için kabuk seçimini geçersiz kılabilirsiniz. Bu destek hem MSBuild tabanlı Linux projeleri hem de uzak bir Linux sistemini veya WSL’yi hedefleyen CMake projeleri ile test edilmiştir.

- Şimdi, MSBuild tabanlı Linux projeleri için artımlı derleme sürelerini kısaltmak amacıyla Ninja’yı (artımlı derlemeleri çok hızlı şekilde değerlendiren bir derleme sistemi) kullanabilirsiniz. Genel Özellik Sayfasında "Artımlı Derlemeyi Etkinleştir" seçeneğini "Ninja ile" olarak ayarlayarak bu özelliği kabul edebilirsiniz. Ninja (ninja derlemesi), uzak Linux sisteminizde veya WSL’de yüklü olmalıdır.

- Yeni C++20 Standart Kitaplık özellikleri uygulandı. Ayrıntılı liste için lütfen [GitHub’daki STL Değişim Günlüğü](https://github.com/microsoft/STL/wiki/Changelog)’ne başvurun.

- Artık [Bağlantı Yöneticisi](../linux/connect-to-your-remote-linux-computer.md#set-up-the-remote-connection)’nde varsayılan uzak SSH bağlantılarını düzenleyip ayarlayabilirsiniz. Bu, var olan bir uzak bağlantıyı (örneğin, IP adresi değiştiyse) düzenleyebilmeniz ve CMakeSettings.json ve launch.vs.jsüzerinde kullanılacak varsayılan bağlantıları ayarlamanız anlamına gelir. Uzak SSH bağlantıları, doğrudan Visual Studio’dan uzak bir Linux sisteminde C++ projeleri oluşturup bunlarda hata ayıklamanıza olanak verir.

- Visual Studio’da Windows üzerinde Clang (clang-cl) için geliştirilmiş IntelliSense desteği. Clang ekleme yolunda artık clang kitaplıkları yer alıyor. Standart kitaplığı kullanırken düzenleyicide görüntülenen dalgalı çizgileri iyileştirdik ve clang modundaki C++2a için destek ekledik.

- Şimdi, kod hatalarının altını çizme özelliğini deneyebilir ve C++ projelerinde daha fazla önerilen hızlı düzeltme görebilirsiniz. **Araçlar > seçenekler > metin düzenleyicisi > C/C++ > deneysel**' da bu özelliği etkinleştirin. **Deneysel kodu devre dışı bırak özelliğini** false olarak ayarlayın. [C++ Ekip Blogunda](https://aka.ms/cpp/isensecodelinter) daha fazla bilgi edinin.

- C++’a ek güvenlik özellikleri dahil etmek amacıyla dört yeni kod analizi kuralı ekledik: [C26817](../code-quality/c26817.md), [C26818](../code-quality/c26818.md), [C26819](../code-quality/c26819.md) ve [C26820](../code-quality/c26820.md).

- gdbserver’a sahip uzak sistemlerdeki CMake projelerinde hata ayıklamaya yönelik birinci sınıf destek ekledik.

- Visual Studio’da C++ için deneysel AddressSanitizer uygulaması sayesinde bellek bozulma hatalarını bulma özelliği artık x64 yerel projeleri için de kullanıma sunuldu. Ayrıca artık hata ayıklama çalışma zamanlarının ( **`/MTd`** ,,) kullanımını destekliyoruz **`/MDd`** **`/LDd`** .

- IntelliSense'te şimdi Concepts, belirlenen başlatıcılar ve diğer bazı C++20 özellilkeri için temel destek sağlanıyor.

- *`.ixx`* ve *`.cppm`* dosyaları artık C++ olarak tanınır ve sözdizimi vurgulayıcı ve IntelliSense gibi kabul edilir.

## <a name="whats-new-for-c-in-visual-studio-version-166"></a>Visual Studio sürüm 16,6 ' de C++ yenilikleri

Visual Studio sürüm 16,6 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,6 ' deki](/visualstudio/releases/2019/release-notes-v16.6)yenilikler.

- **Geliştirilmiş doxygen/XML açıklama oluşturma:** `///` İşlevlerini yazarak veya yukarıdaki işlevleri otomatik olarak doxygen veya XML belgesi Açıklama saplamaları oluşturun `/**` . Bunlar artık Hızlı Bilgi araç ipuçlarında da görüntülenir.

- **Linux/WSL için CMake’e yönelik Ninja desteği:** WSL veya bir uzak sistemde CMake projeleri oluştururken temel alınan oluşturucu olarak Ninja’yı kullanın. Yeni bir Linux veya WSL yapılandırması eklenirken kullanılan varsayılan oluşturucu artık Ninja’dır.

- **CMake’te uzaktan hata ayıklama gerçekleştirmeye yönelik hata ayıklama şablonları**: Uzak bir Linux sistemi veya WSL üzerinde gdp kullanarak CMake projelerinde hata ayıklamaya yönelik şablonları basitleştirdik.

- **C++20 kavramları için ilk destek:** IntelliSense şimdi [C++ 20 kavramlarını](https://devblogs.microsoft.com/cppblog/c20-concepts-are-here-in-visual-studio-2019-version-16-3/) tanır ve bunları üye listesinde önerir.

## <a name="whats-new-for-c-in-visual-studio-version-165"></a>Visual Studio sürüm 16,5 ' de C++ yenilikleri

Visual Studio sürüm 16,5 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,5 ' deki](/visualstudio/releases/2019/release-notes-v16.5)yenilikler.

- **Intellicode ekibi tamamlama modeli ve üye değişkenleri desteği:**  C++ geliştiricileri artık kendi kod tabanlarında ıntellicode modellerini eğitebilir. Takımınızın uygulamalarından faydalandığınız için bu modeli Takım Tamamlamaları modeli olarak adlandırdık. Ayrıca, üye değişkenleri için IntelliCode önerilerini geliştirdik.

- **IntelliSense geliştirmeleri:**
  -  IntelliSense artık Standart Kitaplık ile çalışırken daha okunaklı tür adları görüntülüyor.
  - **ENTER**, **Space** ve **Tab** işlevinin, COMMIT karakterleri olarak değiştirme ve kod parçacığı eklemek için **sekme** kullanılıp kullanılmayacağını değiştirme özelliğini ekledik. Bu ayarları **araçlar > seçenekler > metin düzenleyicisi > C/C++ > gelişmiş > IntelliSense**' in altında bulabilirsiniz.

- **Komut satırı üzerinden bağlantı Yöneticisi:**  Artık, depolanan uzak bağlantılarınızla komut satırı üzerinden etkileşim kurabilirsiniz. Yeni bir geliştirme makinesi sağlama veya sürekli tümleştirmede Visual Studio 'Yu ayarlama gibi görevler için yararlıdır.

- **WSL Için hata ayıklama ve dağıtma:** Visual Studio 'nun, derleme sisteminizi uzak dağıtım sisteminizden ayırmak için WSL 'nin yerel desteğini kullanın. Artık WSL üzerinde yerel olarak derleyebilir ve hata ayıklama için derleme yapıtlarını ikinci bir uzak sisteme dağıtabilirsiniz. Bu iş akışı hem CMake projeleri hem de MSBuild temelli Linux projeleri tarafından desteklenir.

- **Fıps 140-2 uyumluluk modu desteği:** Visual Studio artık uzak bir Linux sistemini hedefleyen C++ uygulamaları geliştirirken FIPS 140-2 uyumluluk modunu desteklemektedir.

- **CMake dil dosyaları için dil Hizmetleri ve daha iyi CMake proje düzenlemesi:**
  - Uzak bir Linux sistemini hedefleyen CMake projelerinin kaynak dosya kopyası iyileştirildi. Visual Studio artık uzaktan kopyalanan kaynakların son kümesine ilişkin “parmak izi dosyası” tutar ve değiştirilen dosya sayısını temel alarak davranışı iyileştirir.
  -  CMake betik dosyalarındaki işlevler, değişkenler ve hedefler için Tanıma Git ve Tüm Başvuruları Bul gibi kod gezintisi özellikleri artık destekleniyor.

  - CMake betiklerinizi el ile düzenlemeden, CMake projelerinizdeki kaynak dosyaları ve hedefleri IDE’de ekleyin, kaldırın ve yeniden adlandırın. Çözüm Gezgini’yle dosyaları eklediğiniz veya kaldırdığınızda, Visual Studio CMake projenizi otomatik olarak düzenleyecek. Ayrıca Çözüm Gezgini’nin Hedefler Görünümünde projenin hedeflerini ekleyebilir, kaldırabilir ve yeniden adlandırabilirsiniz.

- **Linux projesi geliştirmeleri:** Visual Studio Linux projeleri artık daha doğru IntelliSense 'e sahiptir ve bir proje temelinde uzaktan başlık eşitlemesini denetlemenize olanak tanır.

## <a name="whats-new-for-c-in-visual-studio-version-164"></a>Visual Studio sürüm 16,4 ' de C++ yenilikleri

Visual Studio sürüm 16,4 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,4 ' deki](/visualstudio/releases/2019/release-notes-v16.4)yenilikler.

- Kod Analizi artık [`Clang-Tidy`](https://aka.ms/cpp/clangtidy) hem MSBuild hem de CMake projeleri için bir Clang veya MSVC araç kümesi kullanıp kullanmayacağınızı yerel olarak destekler. clang-tidy denetimleri, arka plan kodu analizinin parçası olarak çalıştırılabilir, düzenleyici içi uyarılar (ilişkilendirmeler) olarak görüntülenir ve Hata Listesinde görüntülenir.

- Visual Studio CMake projeleri artık platformlar arası geliştirmeyi kullanmaya başlamanıza yardımcı olacak [Genel Bakış](https://devblogs.microsoft.com/cppblog/usability-improvements-for-cmake-in-visual-studio-2019-version-16-4-launch-target-selection-and-overview-pages/) Sayfalarını içeriyor. Dinamik olan bu sayfalar bir Linux sistemine bağlanmanıza ve CMake projenize bir Linux veya WSL yapılandırması eklemenize yardımcı olur.

- [CMake projeleri için başlatma açılan menüsü](https://devblogs.microsoft.com/cppblog/usability-improvements-for-cmake-in-visual-studio-2019-version-16-4-launch-target-selection-and-overview-pages/) artık en son kullanılan hedefleri görüntülüyor ve filtrelenebilir.

- [C++/CLI](https://devblogs.microsoft.com/cppblog/an-update-on-cpp-cli-and-dotnet-core/) artık Windows üzerinde .NET Core 3.1 ve üstü ile birlikte çalışma desteği sunuyor.

- Bellek hatalarının algılanmasına yardımcı olan C++ koduna yönelik çalışma zamanı izleme özeliği için Windows üzerinde MSVC ile derlenen projelerde [ASan](https://aka.ms/cpp/asanmsvc)’ı etkinleştirebilirsiniz.

- MSVC C++ Standart Kitaplık güncelleştirmeleri:
  - C++17: `to_chars()` genel duyarlılık, tamamlama [P0067R5](https://wg21.link/P0067R5) Temel Dize Dönüştürmeleri (charconv) uygulandı. Bu, C++ 17 Standart’ta tüm kitaplık özelliklerinin uygulanmasını tamamlar.
  - C++20: [P1754R1](https://wg21.link/P1754R1) Kavramların standard_case olarak yeniden adlandırılması uygulandı. En son C++ çalışma taslağının Önizleme özelliklerini dahil etmek için **`/std:c++latest`** derleyici seçeneğini kullanın. Bu seçenek, **C++ dil standardı** özelliği kullanılarak **yapılandırma özellikleri > C/C++ > dil** projesi Özellik sayfasında de ayarlanabilir.

- [C++ derleme öngörüleri](../build-insights/get-started-with-cpp-build-insights.md) adlı yeni bir araçlar koleksiyonu kullanıma sunulmuştur. Duyuru hakkında daha fazla bilgi için bkz. [C++ ekip blogu](https://devblogs.microsoft.com/cppblog/introducing-c-build-insights/).

## <a name="whats-new-for-c-in-visual-studio-version-163"></a>Visual Studio sürüm 16,3 ' de C++ yenilikleri

Visual Studio sürüm 16,3 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,3 ' deki](/visualstudio/releases/2019/release-notes-v16.3)yenilikler.

- C++ geliştiricileri artık **CTRL + K**, **CTRL +/** klavye kısayolunu kullanarak satır açıklamalarını değiştirebilir.

- IntelliSense üye listeleri artık tür niteleyicilerine göre filtrelenmiştir. Örneğin, `const std::vector` artık gibi yöntemleri filtreler `push_back` .

- Bu C++ 20 standart kitaplık Önizleme özelliklerini ekledik (altında bulunur **`/std:c++latest`** ):
  - [P0487R1](https://wg21.link/P0487R1): `operator>>(basic_istream&, CharT*)` öğesini düzeltme
  - [P0616R0](https://wg21.link/P0616R0): `<numeric>` öğesinde `move()` kullanma
  - [P0758R1](https://wg21.link/P0758R1): `is_nothrow_convertible`
  - [P0734R0](https://wg21.link/P0734R0): Kavramlar için C++ uzantıları
  - [P0898R3](https://wg21.link/P0898R3): Standart Kitaplık Kavramları
  - [P0919R3](https://wg21.link/P0919R3): Sıralanmamış Kapsayıcılar için Heterojen Arama

- Yeni "Enum kuralları" kural kümesi ve ek, ve tür kuralları dahil [Yeni C++ temel kılavuz denetimleri](https://devblogs.microsoft.com/cppblog/new-c-core-check-rules/) `const` `enum` .

- Yeni bir varsayılan anlam renklendirme şeması kullanıcıların kodlarını bir bakışta daha iyi anlamasına olanak tanır. Çağrı yığını penceresi, şablon bağımsız değişkenlerini gizleyecek şekilde yapılandırılabilir ve C++ IntelliCode varsayılan olarak açıktır.

- CMakeSettings.json veya CppProperties.json dosyalarını veya ayrı hedeflerde “env” etiketini ve launch.vs.json ve tasks.vs.json dosyalarını kullanarak hata ayıklama hedeflerini ve özel görevleri ortam değişkenleriyle yapılandırın.

- Kullanıcılar, otomatik olarak bir konsol açıp varsayılan vcpkg yüklemesini yüklemek için artık eksik vcpkg paketlerinde hızlı bir eylem kullanabilir.

- Linux projeleri ([CMake](../linux/cmake-linux-project.md) ve [MSBuild](../linux/configure-a-linux-project.md)) tarafından yapılan uzak üst bilgi kopyası iyileştirildi ve artık paralel olarak çalışıyor.

- Visual Studio’nun [WSL için yerel desteği](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/) artık MSBuild tabanlı Linux projeleri için paralel derlemeyi destekliyor.

- Kullanıcılar, artık Linux Derleme Görevleri Dosyası projeleri ile bir uzak sisteme dağıtmak için yerel derlemelerin bir listesini belirtebilir.

- [CMake Ayarları Düzenleyicisi](https://devblogs.microsoft.com/cppblog/introducing-the-new-cmake-project-settings-ui/)’ndeki ayar açıklamaları, artık yararlı belgeler için daha fazla bağlam ve bağlantı içeriyor.

- Intellicode için C++ temel modeli artık varsayılan olarak etkinleştirilmiştir. **Araçlar** > **Ayarlar** > **IntelliCode**’a giderek bu ayarı değiştirebilirsiniz.

## <a name="whats-new-for-c-in-visual-studio-version-162"></a>Visual Studio sürüm 16,2 ' de C++ yenilikleri

Visual Studio sürüm 16,2 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,2 ' deki](/visualstudio/releases/2019/release-notes-v16.2)yenilikler.

- Clang ile yapılandırılan yerel CMake projeleri için, Kod Analizi şimdi düzenleyici içinde uyarılar (dalgalı çizgiler) olarak ve Hata Listesinde görüntülenen bir arka plan kod analizinin parçası olarak clang-tidy denetimleri çalıştırır.

- C++17'deki [P0067R5](https://wg21.link/P0067R5) Temel dize dönüştürmeleri için `<charconv>` üst bilgisi güncelleştirildi:
  - `chars_format::fixed` ve `chars_format::scientific` duyarlığı için kayan nokta `to_chars()` aşırı yüklemeleri eklendi (`chars_format::general precision` henüz uygulanmamış olan tek bölümdür)
  - `chars_format::fixed` en kısa şekilde iyileştirildi

- Bu C++ 20 Standart Kitaplığı Önizleme özellikleri eklendi:
  - Şu koşullarda kullanılabilir **`/std:c++latest`** :
    - [P0020R6](https://wg21.link/P0020R6): `atomic<floating-point>`
    - [P0463R1](https://wg21.link/P0463R1): endian sabit listesi
    - [P0482R6](https://wg21.link/P0482R6): UTF-8 karakterleri ve dizeleri için `char8_t` türü
    - [P0653R2](https://wg21.link/P0653R2): işaretçiyi ham işaretçiye dönüştürmek için `to_address()`
  - `/std:c++17` ve `/std:c++latest` altında kullanılabilir:
    - [P0600R1](https://wg21.link/P0600R1): kitaplıkta `[[nodiscard]]`
  - Koşulsuz olarak kullanılabilir:
    - [P0754R2](https://wg21.link/P0754R2): `<version>` üst bilgisi
    - [P0771R1](https://wg21.link/P0771R1): `std::function` taşıma oluşturucusu `noexcept` olmalıdır

- Windows SDK’sı artık Windows için CMake ve Linux için CMake bileşenleri için bir bağımlılık değil.

- [C++ bağlayıcısında](https://aka.ms/cpp/162linker) en büyük giriş için yineleme derleme sürelerini önemli ölçüde iyileştiren geliştirmeler. **`/DEBUG:FAST`** ve **`/INCREMENTAL`** süreler hızlı bir şekilde **`/DEBUG:FULL`** hızlıdır ve artık üç ile altı kat daha hızlıdır.

## <a name="whats-new-for-c-in-visual-studio-version-161"></a>Visual Studio sürüm 16,1 ' de C++ yenilikleri

Visual Studio sürüm 16,1 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,1 ' deki](/visualstudio/releases/2019/release-notes-v16.1)yenilikler.

### <a name="c-compiler"></a>C++ derleyicisi

- Bu C++ 20 Önizleme özellikleri şu koşullarda sunulan C++ derleyicisinde uygulanmıştır **`/std:c++latest`** :
  - Açık şablon bağımsız değişkenleri ([P0846R0](http://wg21.link/p0846r0)) ile işlev çağrısı ifadeleri için bağımsız değişkenler aracılığıyla işlev şablonlarını bulabilme yeteneği artırıldı.
  - Belirlenmiş başlatma ([P0329R4](https://wg21.link/p0329r4)) (örneğin, sözdizimi kullanılarak) toplu başlatma işleminde belirli üyelerin seçilebileceği `Type t { .member = expr }` .

- Lambda desteği bakımdan geçirilerek uzun süredir devam eden çok sayıda hata giderildi. Bu değişiklik, kullanılırken varsayılan olarak etkindir **`/std:c++latest`** . **`/std:c++17`** Dil modunda ve varsayılan ( **`/std:c++14`** ) modunun altında yeni ayrıştırıcı, **`/experimental:newLambdaProcessor`** Örneğin, kullanılarak etkinleştirilebilir `/std:c++17 /experimental:newLambdaProcessor` .

### <a name="c-standard-library-improvements"></a>C++ standart kitaplığı geliştirmeleri

- Bu C++ 20 Önizleme özellikleri, aşağıda bulunan C++ standart kitaplığı uygulamamıza eklenmiştir **`/std:c++latest`** :
  - `starts_with` ve `ends_with` için `basic_string` `basic_string_view` .
  - İlişkili kapsayıcılar için `contains`.
  - `list` ve `forward_list` için `remove`, `remove_if` ve `unique` artık `size_type` değerini döndürüyor.
  - `shift_left` ve `shift_right``<algorithm>` üzerine eklendi.

### <a name="c-ide"></a>C++ IDE

#### <a name="intellicode-for-c"></a>C++ için ıntellicode

Intellicode artık C++ iş yüküyle **Masaüstü geliştirmede** isteğe bağlı bir bileşen olarak dağıtılır. Daha fazla bilgi için bkz. [Gelişmiş C++ ıntellicode artık Visual Studio 2019 Ile birlikte gelir](https://devblogs.microsoft.com/cppblog/improved-c-intellicode-now-ships-with-visual-studio-2019/).

Intellicode, tamamlanma listenizin en üstünde en büyük olasılıkla kullandıklarınızı yerleştirmek için kendi kapsamlı eğitimini ve kod bağlamını kullanır. Genellikle listede aşağı kaydırma gereğini ortadan kaldırabilir. C++ için, standart kitaplık gibi popüler kitaplıkları kullanırken ıntellicode en fazla yardımı sunar.

Önizleme ıntellicode özellikleri (özel modeller, C++ desteği ve EditorConfig çıkarımı) varsayılan olarak devre dışıdır. Bunları etkinleştirmek için **araçlar > seçenekler > ıntellicode > Genel**' e gidin. IntelliCode’un bu sürümünde doğruluk geliştirildi ve boş işlev desteği eklendi. Daha fazla bilgi için bkz. [AI destekli kod tamamlama önerileri ıntellicode aracılığıyla C++](https://devblogs.microsoft.com/cppblog/cppintellicode/)' a gelir.

#### <a name="quick-info-improvements"></a>Hızlı bilgi geliştirmeleri

- Hızlı Bilgi ipucu artık Düzenleyicinizde anlam renklendirme için uyar. Ayrıca, vurgulanan kod yapısı hakkında daha fazla bilgi edinmek için çevrimiçi belgeleri arayacak yeni bir **arama çevrimiçi** bağlantısına sahiptir. Kırmızı renkli bir kod için hızlı bilgi sağlayan bağlantı, hatayı çevrimiçi olarak arar. Böylece iletiyi tarayıcınıza yeniden yazmanız gerekmez. Daha fazla bilgi için bkz. [Visual Studio 2019 'de hızlı bilgi iyileştirmeleri: renklendirme ve çevrimiçi arama](https://devblogs.microsoft.com/cppblog/quick-info-improvements-in-visual-studio-2019-colorization-and-search-online/).

#### <a name="general-improvements"></a>Genel geliştirmeler

- Şablon Çubuğu artık kod temelinizdeki şablonun örneklemelerini temel alarak açılır menüyü doldurabilir.

- `#include`Vcpkg 'nın, CMake yönergesi için kullanılabilir paketlerin yükleyebileceği ve otomatik olarak tamamlanmasının eksik yönergelerinin açık olması `find_package` .

- C++ projeleri için **genel** Özellik sayfası düzeltildi. Bazı seçenekler artık yeni bir **Gelişmiş** sayfanın altında listelenmiştir. **Gelişmiş** sayfa ayrıca tercih ettiğiniz araç seti mimarisine, hata ayıklama KITAPLıKLARıNA, MSVC araç takımı alt sürümüne ve Unity (Jumbo) derlemelerinizin yeni özelliklerini içerir.

### <a name="cmake-support"></a>CMake desteği

- Visual Studio ile birlikte gelen CMake sürümünü 3,14 'e güncelleştirdik. Bu sürüm, Visual Studio 2019 projelerini ve dosya tabanlı IDE tümleştirme API’leri hedefleyen MSBuild oluşturucuları için yerleşik destek ekler.

- CMake ayarları düzenleyicisine, Linux için Windows alt sistemi (WSL) ve var olan önbelleklerden gelen yapılandırmalara yönelik geliştirmeler, varsayılan derleme ve yapılandırma köklerine yapılan değişiklikler ve Linux CMake yapılandırmalarında ortam değişkenleri için destek dahil olmak üzere geliştirmeler ekledik.

- Yerleşik CMake komutları, değişkenleri ve özellikleri için tamamlama ve hızlı bilgi, dosyalarınızı düzenlemeyi kolaylaştırır *`CMakeLists.txt`* .

- Clang/LLVM ile CMake projelerini düzenlemeyle, oluşturmaya ve hata ayıklamaya yönelik olarak tümleştirdik. Daha fazla bilgi için bkz. [Visual Studio 'Da Clang/LLVM desteği](https://devblogs.microsoft.com/cppblog/clang-llvm-support-in-visual-studio/).

### <a name="linux-and-the-windows-subsystem-for-linux"></a>Linux için Linux ve Windows alt sistemi

- Artık Linux 'ta [Addresstemizleme (ASan)](https://github.com/google/sanitizers/wiki/AddressSanitizer) ve CMake platformlar arası projelerini destekliyoruz. Daha fazla bilgi için bkz. [Visual Studio 2019 ' de Linux Iş yükü Için Addresstemizleme (ASan)](https://devblogs.microsoft.com/cppblog/addresssanitizer-asan-for-the-linux-workload-in-visual-studio-2019/).

- Linux için Windows alt sistemi (WSL) ile C++ kullanmaya yönelik Visual Studio desteğini tümleştirdik. Artık, Visual Studio 'da Linux için yerel Windows alt sistemi (WSL) yüklemenizi ek yapılandırma veya SSH bağlantısı olmadan kullanabilirsiniz. Daha fazla bilgi için bkz. [Visual Studio 2019 ve Linux Için Windows alt sistemi (WSL) ile C++](https://devblogs.microsoft.com/cppblog/c-with-visual-studio-2019-and-windows-subsystem-for-linux-wsl/).

### <a name="code-analysis"></a>Kod Çözümleme

- Başlatılmamış Değişken denetimleri için yeni hızlı düzeltmeler eklendi. Kod Analizi uyarıları [C6001: Başlatılmamış bellek &lt; değişkeni &gt; ](../code-quality/c6001.md) ve [C26494 VAR_USE_BEFORE_INIT](../code-quality/c26494.md) kullanmak ilgili satırlardaki ampul menüsünde mevcuttur. Bunlar, sırasıyla Microsoft yerel minimum RuleSet ve C++ Temel Denetimi Type RuleSets ' de varsayılan olarak etkinleştirilmiştir. Daha fazla bilgi için bkz. [Başlatılmamış bellek Için yeni kod analizi hızlı düzeltmeleri (C6001) ve init (C26494) uyarılarını kullanma](https://devblogs.microsoft.com/cppblog/new-code-analysis-quick-fixes-for-uninitialized-memory-c6001-and-use-before-init-c26494-warnings/).

### <a name="remote-builds"></a>Uzak derlemeler

- Kullanıcılar hem MSBuild hem de CMake projelerinde Linux’ı hedeflerken uzaktan derleme makinenizi uzaktan hata ayıklama makinelerinden ayırabilir.

- Uzak bağlantılar için iyileştirilmiş günlüğe kaydetme, platformlar arası geliştirmede sorunları tanılamayı kolaylaştırır.

## <a name="whats-new-for-c-in-visual-studio-version-160"></a>Visual Studio sürüm 16,0 ' de C++ yenilikleri

Visual Studio sürüm 16,0 ' deki yeni özelliklerin ve hata düzeltmelerinin Özeti için bkz. [Visual studio 2019 sürüm 16,0 ' deki](/visualstudio/releases/2019/release-notes-v16.0)yenilikler.

### <a name="c-compiler"></a>C++ derleyicisi

- C++ 17 özellikleri ve doğruluk düzeltmeleri için geliştirilmiş destek, ayrıca modüller ve eş yordamlar gibi C++ 20 özellikleri için deneysel destek. Ayrıntılı bilgi için bkz. [Visual Studio 2019 ' de C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- Bu [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) seçenek artık, **`<=>`** üç yönlü karşılaştırma için c++ 20 işleci ("Spaceship") için başlangıç desteği dahil olmak üzere tam olmayan c++ 20 özelliklerini içerir.

- C++ derleyici anahtarı [`/Gm`](../build/reference/gm-enable-minimal-rebuild.md) artık kullanım dışıdır. **`/Gm`** Derleme betiklerinizde açıkça tanımlanmış olan anahtarı devre dışı bırakmayı düşünün. Bununla birlikte, **`/Gm`** "uyarıları hata olarak değerlendir" () kullanılırken hata olarak değerlendirilmediği için, için kullanımdan kaldırma uyarısını güvenle yoksayabilirsiniz [`/WX`](../build/reference/compiler-option-warning-level.md) .

- MSVC olarak, bayrak altındaki C++ 20 Standart taslağındaki özellikleri uygulamaya başladıktan sonra, **`/std:c++latest`** **`/std:c++latest`** artık **`/clr`** (tüm özellikler), ve ile uyumlu değildir **`/ZW`** **`/Gm`** . Visual Studio 2019 ' de `/std:c++17` `/std:c++14` , veya ile derlerken, veya modları kullanın `/clr` `/ZW` `/Gm` (ancak önceki madde işaretine bakın).

- C++ konsol ve masaüstü uygulamaları için önceden derlenmiş üst bilgiler artık varsayılan olarak oluşturulmuyor.

#### <a name="codegen-security-diagnostics-and-versioning"></a>CodeGen, güvenlik, tanılama ve sürüm oluşturma

[`/Qspectre`](../build/reference/qspectre.md)Spectre varyant 1 ([CVE-2017-5753](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-5753)) için azaltma yardımı sağlamak üzere ile birlikte geliştirilmiş analiz. Daha fazla bilgi için bkz. [Spectre AZALTMALARı MSVC](https://devblogs.microsoft.com/cppblog/spectre-mitigations-in-msvc/).

### <a name="c-standard-library-improvements"></a>C++ standart kitaplığı geliştirmeleri

- Ek C++ 17 ve C++ 20 kitaplığı özelliklerinin ve doğruluk düzeltmelerinin uygulanması. Ayrıntılı bilgi için bkz. [Visual Studio 2019 ' de C++ uyumluluk geliştirmeleri](cpp-conformance-improvements.md).

- Clang-Format, gelişmiş okunabilirlik için C++ standart kitaplığı üst bilgilerine uygulandı.

- Visual Studio artık C++ için Yalnızca kendi kodum desteklediğinden, standart kitaplığın artık için özel makineler sağlaması `std::function` ve aynı etkiyi elde etmek için ihtiyacı yoktur `std::visit` . Bu makinelerin büyük ölçüde Kullanıcı tarafından görülemeyen etkileri yoktur. Tek bir istisna derleyicinin artık 15732480 veya 16707566 satırındaki sorunları belirten tanılamayı oluşturmayacağı durumdur \<type_traits> \<variant> .

### <a name="performancethroughput-improvements-in-the-compiler-and-standard-library"></a>Derleyici ve standart kitaplıkta performans/aktarım hızı iyileştirmeleri

- Bağlayıcının dosya g/ç 'yi işleme şekli ve PDB türü birleştirme ve oluşturma sırasında bağlantı süresi de dahil olmak üzere derleme işleme iyileştirmeleri.

- OpenMP SıMD vektörleştirme için temel destek eklendi. Bunu, yeni derleyici anahtarını kullanarak etkinleştirebilirsiniz **`/openmp:experimental`** . Bu seçenek, `#pragma omp simd` büyük olasılıkla vektörleştirilmiş olarak açıklanan döngülere izin verir. Vektörleştirme garanti edilmez ve vektörleştirilmiş ancak vektörleştirilmemiş döngüler bildirilen bir uyarı alır. SıMD yan tümceleri desteklenmez; Bunlar yok sayılır ve bir uyarı bildirilir.

- **`/Ob3`** Daha agresif bir sürümü olan yeni bir satır içi komut satırı anahtarı eklendi **`/Ob2`** . **`/O2`** (hızı hız için en iyi hale getirin) hala **`/Ob2`** Varsayılan olarak anlamına gelir. Derleyicinin satır içi olarak yeterince gözetmediğini fark ederseniz, geçirmeyi düşünün **`/O2 -Ob3`** .

- Kısa vektör matematik kitaplığı (SVML) iç işlevleri için destek ekledik. Bu işlevler 128 bit, 256 bit veya 512 bit vektör eşdeğerlerini hesaplar. Bunları matematik kitaplığı işlevlerine yapılan çağrılar ve tamsayı bölme gibi diğer diğer işlemler için birlikte vektörleştirmeyi destekleyecek şekilde ekledik. Desteklenen işlevlerin tanımları için [Intel Intrinsic Guide](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#!=undefined&techs=SVML) belgesine bakın.

- Yeni ve geliştirilmiş iyileştirmeler:

  - Hem float hem de Integer formlarında SıMD vektör iç bilgileri kullanan ifadeler için sabit katlamalı ve aritmetik basitleştirmeleri.

  - Her zaman doğru veya yanlış olarak kanıtlanmış olan dalları kaldırmak için denetim akışından (if/else/Switch deyimleri) bilgi ayıklamasına yönelik daha güçlü bir analizler.

  - SSE2 vektör yönergeleri kullanılarak geliştirilmiş memset kullanımı.

  - Özellikle değere göre geçen C++ programları için, çok sayıda struct/Class kopyasının daha iyi kaldırılması.

  - `memmove` `std::copy` Veya ve oluşturma gibi kullanılarak kodun geliştirilmiş iyileştirmesi `std::vector` `std::string` .

- Standart kitaplığın, doğrudan dahil edilmemiş parçalar derlenmekten kaçınmak için standart kitaplık fiziksel tasarımını en iyi duruma getirilmiştir. Bu değişiklik, yalnızca yarısında yer alan boş bir dosyanın derleme süresini keser \<vector> . Sonuç olarak, `#include` daha önce dolaylı olarak dahil edilen üst bilgiler için yönergeler eklemeniz gerekebilir. Örneğin, tarafından kullanılan kodun `std::out_of_range` artık eklemesi gerekebilir `#include <stdexcept>` . Stream ekleme işlecini kullanan kodun artık eklemesi gerekebilir `#include <ostream>` . Avantaj, yalnızca veya bileşenleri kullanan çeviri birimlerinin \<stdexcept> \<ostream> , bunları derlemek için üretilen iş maliyetini ödemesidir.

- `if constexpr` Standart kitaplıkta daha fazla yerde daha fazla yere uygulanmış ve kopyalama işlemlerinde daha fazla kod boyutu, ters ve aşağı döndürme gibi permütasyon ve paralel algoritmalar kitaplığında uygulandı.

- Standart kitaplık artık `if constexpr` , c++ 14 modunda bile derleme sürelerini azaltmak için dahili olarak kullanılır.

- Paralel algoritmalar kitaplığı için çalışma zamanı dinamik bağlama algılaması, artık işlev işaretçisi dizisini depolamak için bir sayfanın tamamını kullanmaz. Bu belleği salt okunurdur olarak işaretlemek artık güvenlik amaçları için uygun değildir.

- `std::thread`Oluşturucu artık iş parçacığının başlamasını beklemez ve artık temel alınan C Kitaplığı `_beginthreadex` ve sağlanan çağrılabilir nesne arasında işlev çağrılarının birçok katmanını eklememe. Daha önce `std::thread` `_beginthreadex` ve sağlanan çağrılabilir nesne arasına altı işlev yerleştirin. Bu sayı yalnızca üçüne düşürüldü, ikisi de yalnızca üç `std::invoke` . Bu değişiklik Ayrıca, `std::thread` sistem saati oluşturulduğu anda tam olarak değiştirilirse bir oluşturucunun yanıt vermemesine neden olan, kesin bir zamanlama hatasını giderir `std::thread` .

- `std::hash`Uygulamamız sırasında tanıtıldığımız bir performans gerileme düzeltildi `std::hash<std::filesystem::path>` .

- Standart kitaplık artık, doğruluk düzeyine ulaşmak için birkaç yerde catch blokları yerine Yıkıcılar kullanır. Bu değişiklik, daha iyi hata ayıklayıcı etkileşimine neden olur: etkilenen konumlarda standart kitaplık aracılığıyla oluşturduğunuz özel durumlar artık, yeniden oluşturma işleminden önce orijinal throw sitesinden oluşturulmuş olarak gösterilir. Tüm standart kitaplık yakalama blokları ortadan kaldırılmadı. MSVC 'in sonraki sürümlerinde, catch bloklarının sayısının azaltıldığı tahmin ederiz.

- `std::bitset`Bir işlevin içindeki koşullu bir throw tarafından neden olan alt ptimal CodeGen `noexcept` , oluşturma yolu düzenleme tarafından düzeltildi.

- `std::list`Ve `std::unordered_*` ailesi, daha fazla yerde hata ayıklama olmayan yineleyiciler kullanır.

- Birçok `std::list` üye, mümkün olduğunda liste düğümlerini yeniden kullanmak için değiştirilmiştir ve bunları yeniden tahsis etmek yerine mümkündür. Örneğin, `list<int>` zaten 3 boyutuna sahip olan bir öğesine yapılan bir çağrı, `assign(4, 1729)` `int` ilk üç liste düğümündeki değerlerin üzerine yazar ve 1729 değerine sahip bir yeni liste düğümü ayırır.

- İçin tüm standart kitaplık çağrıları `erase(begin(), end())` olarak değiştirilmiştir `clear()` .

- `std::vector` Artık bazı durumlarda öğeleri daha verimli bir şekilde başlatır ve siler.

- `std::variant`Daha basit hale getirmek için ' de iyileştirmeler yapın, daha iyi üretilen koda yol açar. Code ıntıl artık ile çok daha iyidir `std::visit` .

### <a name="c-ide"></a>C++ IDE

#### <a name="live-share-c-support"></a>Live Share C++ desteği

[Live share](/visualstudio/liveshare/) artık C++ ' ı desteklediğinden, Visual Studio veya Visual Studio Code kullanan geliştiricilerin gerçek zamanlı olarak işbirliği yapmasına olanak tanır. Daha fazla bilgi için bkz [. C++ için Live Share duyurusu: Real-Time paylaşımı ve işbirliği](https://devblogs.microsoft.com/cppblog/cppliveshare/)

#### <a name="template-intellisense"></a>Şablon IntelliSense

**Şablon çubuğu** artık, kalıcı bir pencere yerine bir **pencere göz atma** Kullanıcı arabirimini kullanır, iç içe geçmiş şablonları destekler ve varsayılan bağımsız değişkenleri **göz atma penceresinde** önceden doldurur. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 Için şablon IntelliSense geliştirmeleri](https://devblogs.microsoft.com/cppblog/template-intellisense-improvements-for-visual-studio-2019-preview-2/). **Şablon çubuğunda** **en son kullanılan** bir açılan liste, önceki örnek bağımsız değişken kümeleri arasında hızlıca geçiş yapmanızı sağlar.

#### <a name="new-start-window-experience"></a>Yeni başlangıç penceresi deneyimi

IDE 'yi başlatırken yeni bir başlangıç penceresi görüntülenir. Son projeleri açma, kaynak denetiminden kod kopyalama, yerel kodu çözüm veya klasör olarak açma ya da yeni bir proje oluşturma seçenekleri vardır. Yeni proje iletişim kutusu ayrıca arama sırasında, filtrelenebilir bir deneyime de sahiptir.

#### <a name="new-names-for-some-project-templates"></a>Bazı proje şablonları için yeni adlar

Çeşitli proje şablonu adlarını ve açıklamalarını güncelleştirilmiş yeni proje iletişim kutusuyla sığacak şekilde değiştirdik.

#### <a name="various-productivity-improvements"></a>Çeşitli verimlilik geliştirmeleri

Visual Studio 2019, kodlamayı daha kolay ve daha sezgisel hale getirmeye yardımcı olacak aşağıdaki özellikleri içerir:

- İçin hızlı düzeltmeler:
  - Eksik Ekle `#include`
  - `NULL` Hedef `nullptr`
  - Eksik noktalı virgül Ekle
  - Eksik ad alanı veya kapsamı çözümle
  - Hatalı yöneltme işlenenlerini Değiştir (ile `*` `&` ve arasında `&` `*` )
- Kapatma küme ayracı üzerine gelindiğinde bir blok için hızlı bilgi
- Üst bilgi/kod dosyasına göz at
- Tanıma Git `#include` , dosyayı açar

Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 ' deki C++ üretkenlik geliştirmeleri](https://devblogs.microsoft.com/cppblog/c-productivity-improvements-in-visual-studio-2019-preview-2/).

### <a name="cmake-support"></a>CMake desteği

- CMake 3,14 desteği

- Visual Studio artık, Cmakeguı, özelleştirilmiş meta-Build sistemleri veya cmake.exe kendilerini çağıran derleme betikleri gibi dış araçlar tarafından oluşturulan mevcut CMake önbelleklerini açabilir.

- Geliştirilmiş IntelliSense performansı.

- Yeni bir ayar Düzenleyicisi, dosyadaki CMakeSettings.jsel ile düzenleme için alternatif sağlar ve Cmakeguı ile bazı eşlik sağlar.

- Visual Studio, Linux makinenizde uyumlu bir CMake sürümü olup olmadığını algılayarak Linux üzerinde CMake ile C++ geliştirmenizin önyüklemesine yardımcı oluyor. Uyumlu bir sürüm yoksa, sizin için yüklemeyi öneriyor.

- CMakeSettings içinde eşleşmeyen mimariler veya uyumsuz CMake Oluşturucu ayarları gibi uyumsuz ayarlar, JSON düzenleyicisinde dalgalı çizgiler ve hata listesindeki hataları gösterir.

- `vcpkg integrate install` çalıştırıldıktan sonra IDE'de açılmış olan CMake projeleri için vcpkg araç zinciri otomatik olarak algılanıyor ve etkinleştiriliyor. Bu davranış, CMakeSettings'de boş bir araç zinciri dosyası belirtilerek kapatılabilir.

- CMake projeleri artık varsayılan olarak Yalnızca Kendi Kodum hata ayıklamasını etkinleştiriyor.

- Statik analiz uyarıları artık arka planda işlenir ve CMake projelerine ilişkin düzenleyicide görüntülenir.

- CMake projeleri ve Visual Studio 'nun derleme ilerlemesi Kullanıcı arabirimine yönelik destek için ' begin' ve ' End ' iletilerini daha net hale getirin ve yapılandırın. Ayrıca, **araçlar > seçeneklerinde** CMake yapı ve yapılandırma çıkış penceresi iletilerinin ayrıntı düzeyini özelleştirmek için artık bir CMake ayrıntı ayarı vardır.

- Bu `cmakeToolchain` ayar artık CMake komut satırını el ile değiştirmeden araç zincirlerini belirtmek için üzerinde CMakeSettings.jsdesteklenir.

- Yeni bir **Yapı Oluştur** Menü kısayolu **CTRL + SHIFT + B**.

### <a name="incredibuild-integration"></a>IncrediBuild tümleştirmesi

IncrediBuild, C++ iş yüküne **sahip masaüstü geliştirmeye** isteğe bağlı bir bileşen olarak dahildir. IncrediBuild derleme Izleyicisi, Visual Studio IDE 'de tamamen tümleşiktir. Daha fazla bilgi için bkz. [IncrediBuild 'In derleme İzleyicisi ve Visual Studio 2019 ile derlemenizi görselleştirme](https://devblogs.microsoft.com/cppblog/visualize-your-build-with-incredibuilds-build-monitor-and-visual-studio-2019/).

### <a name="debugging"></a>Hata Ayıklama

- Windows üzerinde çalışan C++ uygulamaları için PDB dosyaları artık ayrı bir 64 bit işlemde yüklenir. Bu değişiklik, hata ayıklayıcının bellek tükenmesinin neden olduğu bir kilitlenme aralığına yöneliktir. Örneğin, çok sayıda modül ve PDB dosyası içeren uygulamalarda hata ayıklarken.

- Arama, **izleme**, **oto** ve **Yereller** pencerelerinde etkinleştirilmiştir.

### <a name="windows-desktop-development-with-c"></a>C++ ile Windows masaüstü geliştirme

- Bu C++ ATL/MFC sihirbazları artık kullanılamaz:

  - ATL COM+ 1.0 Bileşeni Sihirbazı
  - ATL Active Server Pages Bileşen Sihirbazı
  - ATL OLE DB Sağlayıcısı Sihirbazı
  - ATL Özellik Sayfası Sihirbazı
  - ATL OLE DB Tüketicisi Sihirbazı
  - MFC ODBC Tüketicisi
  - ActiveX denetiminden MFC sınıfı
  - Tür lib 'den MFC sınıfı.

  Bu teknolojilerin örnek kodu Microsoft Docs'ta ve VCSamples GitHub deposunda arşivlendi.

- Windows 8.1 yazılım geliştirme seti (SDK) artık Visual Studio yükleyicisi 'nde kullanılamaz. C++ projelerinizi en son Windows 10 SDK 'sına yükseltmenizi öneririz. 8\.1'e katı bir bağımlılığınız varsa, bunu Windows SDK arşivinden indirebilirsiniz.

- En son C++ araç takımında artık Windows XP hedeflemesi sağlanmıyor. VS 2017-Level MSVC derleyicisi & kitaplıkları ile hedefleme, hala desteklenmektedir ve "bağımsız bileşenler" aracılığıyla yüklenebilir.

- Belgelerimizde şu anda Visual C++ Çalışma Zamanı dağıtımı için Modülleri Birleştirme kullanımı hiç önerilmiyor. Bu sürümden, MSMs 'nin kullanım dışı olarak işaretlenme konusunda daha fazla adımla karşılaşıyoruz. VCRuntime merkezi dağıtımınızı MSM'lerden yeniden dağıtılabilir pakete geçirmeyi göz önünde bulundurun.

### <a name="mobile-development-with-c-android-and-ios"></a>C++ ile mobil geliştirme (Android ve iOS)

C++ Android deneyimi artık varsayılan olarak Android SDK 25 ve Android NDK 16b olur.

### <a name="clangc2-platform-toolset"></a>Clang/C2 platform araç takımı

Clang/C2 bileşeni kaldırıldı. `/permissive-`Ve `/std:c++17` , veya Windows Için Clang/LLVM araç zinciri Ile tam C++ standartları uyumluluğu için MSVC araç takımını kullanın.

### <a name="code-analysis"></a>Kod analizi

- Kod analizi artık otomatik olarak arka planda çalıştırılıyor. Siz yazdıkça düzenleyicinin içinde uyarılar yeşil dalgalı çizgilerle gösteriliyor. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 ' deki düzenleyici kod analizi](https://devblogs.microsoft.com/cppblog/in-editor-code-analysis-in-visual-studio-2019-preview-2/).

- Üst bilgiden tanınmış standart kitaplık türleri için yeni deneysel ConcurrencyCheck kuralları \<mutex> . Daha fazla bilgi için bkz. [Visual Studio 2019 'de eşzamanlılık kodu analizi](https://devblogs.microsoft.com/cppblog/concurrency-code-analysis-in-visual-studio-2019/).

- Etkinlik işaretçilerini ve başvuruları algılayan [ömür profili denetleyicisi](https://herbsutter.com/2018/09/20/lifetime-profile-v1-0-posted/)'nin güncelleştirilmiş kısmi bir uygulamasıdır. Daha fazla bilgi için bkz. [Visual Studio 2019 Preview 2 ' de ömür profili güncelleştirmesi](https://devblogs.microsoft.com/cppblog/lifetime-profile-update-in-visual-studio-2019-preview-2/).

- [C26138](../code-quality/c26138.md), [C26810](../code-quality/c26810.md), [C26811](../code-quality/c26811.md)ve deneysel kural [C26800](../code-quality/c26800.md)dahil olmak üzere daha fazla Corine ilişkin denetimler. Daha fazla bilgi için bkz. [Visual Studio 2019 'de yeni kod analizi denetimleri: Use-After-Move ve eş yordam olamaz](https://devblogs.microsoft.com/cppblog/new-code-analysis-checks-in-visual-studio-2019-use-after-move-and-coroutine/).

### <a name="unit-testing"></a>Birim testi

Yönetilen C++ Test Projesi şablonu artık sağlanmıyor. Mevcut projelerinizde yönetilen C++ test çerçevesini kullanmaya devam edebilirsiniz. Yeni birim testleri için, Visual Studio 'nun şablonlar (MSTest, Google Test) veya yönetilen C# Test projesi şablonu sağladığı yerel test çerçevelerinden birini kullanmayı düşünün.
