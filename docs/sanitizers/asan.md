---
title: Addresstemizleme
description: Microsoft C/C++ için Addresstemizleme özelliğinin en üst düzey açıklaması.
ms.date: 03/05/2021
f1_keywords:
- AddressSanitizer
helpviewer_keywords:
- ASan
- AddressSanitizer
- Address Sanitizer
- compiling for AddressSanitizer
ms.openlocfilehash: db1760a37c610493cd3a3d95ab5e77b29bf89400
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470786"
---
# <a name="addresssanitizer"></a>Addresstemizleme

## <a name="overview"></a>Genel Bakış

C & C++ dilleri güçlü, ancak program doğruluğu ve program güvenliğini etkileyen bir hata sınıfından zarar verebilir. Visual Studio 2019 sürüm 16,9 ' den başlayarak, Microsoft C/C++ derleyicisi (MSVC) ve IDE, *Addresstemizleme*'yi destekler. Addresstemizleme (ASan), **sıfır** hatalı pozitif sonuçlar ile çok sayıda sabit-bulma hatası sunan bir derleyici ve çalışma zamanı teknolojisidir:

- [Ayırma/ayırma uyuşmazlığı](error-alloc-dealloc-mismatch.md) ve [ `new` / `delete` tür uyuşmazlıkları](error-new-delete-type-mismatch.md)
- [Yığın için ayırmalar çok büyük](error-allocation-size-too-big.md)
- [ `calloc` taşma](error-calloc-overflow.md) ve [ `alloca` taşma](error-dynamic-stack-buffer-overflow.md)
- [Double ücretsiz](error-double-free.md) ve [ücretsiz olarak kullan](error-heap-use-after-free.md)
- [Genel değişken taşması](error-global-buffer-overflow.md)
- [Yığın arabelleği taşması](error-heap-buffer-overflow.md)
- [Hizalanmış değerlerin geçersiz hizalaması](error-invalid-allocation-alignment.md)
- [`memcpy`](error-memcpy-param-overlap.md)ve [ `strncat` parametre çakışması](error-strncat-param-overlap.md)
- [Yığın arabelleği taşması](error-stack-buffer-overflow.md) ve [yetersiz kalması](error-stack-buffer-underflow.md)
- [Sonra `return` yığın kullanımı](error-stack-use-after-return.md) ve [kapsamından sonra kullan](error-stack-use-after-scope.md)
- [Bellek kirledikten sonra bellek kullanımı](error-use-after-poison.md)

Şu saatte harcanan süreyi azaltmak için Addresstemizleme 'yi kullanın:

- Temel doğruluk
- Platformlar arası taşınabilirlik
- Güvenlik
- Stres testi
- Yeni kodu tümleştirme

Başlangıçta [Google tarafından tanıtılan](https://www.usenix.org/conference/atc12/technical-sessions/presentation/serebryany)addresstemizleme, hem [ `/RTC` (çalışma zamanı hata denetimleri)](../build/reference/rtc-run-time-error-checks.md) hem de [ `/analyze` (statik analiz)](../build/reference/analyze-code-analysis.md)için güçlü bir alternatiftir. Mevcut derleme sistemlerinizi ve mevcut test varlıklarınızı doğrudan kullanan çalışma zamanı hata bulma teknolojileri sağlar.

Addresstemizleme, Visual Studio proje sistemi, CMake derleme sistemi ve IDE ile tümleşiktir. Projeler bir proje özelliğini ayarlayarak veya bir ek derleyici seçeneği kullanarak Addresstemizleyerek izin verebilir: **`/fsanitize=address`** . Yeni seçenek, x86 ve x64 'un tüm iyileştirme ve yapılandırmalarına sahiptir. Ancak, [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp), [artımlı bağlama](../build/reference/incremental-link-incrementally.md)ve ile uyumlu değildir [`/RTC`](../build/reference/rtc-run-time-error-checks.md) .

Visual Studio 2019 sürüm 16,9 ' den başlayarak, Microsoft 'un Addresstemizleme teknolojisi, Visual Studio IDE ile tümleştirmeyi mümkün hale getirmenizi sunar. Temizleme, çalışma zamanında bir hata bulduğunda, isteğe bağlı olarak bir kilitlenme bilgi döküm dosyası oluşturabilir. `ASAN_SAVE_DUMPS=MyFileName.dmp`Programınızı çalıştırmadan önce ortam değişkenini ayarlarsanız, kesin bir şekilde tanıdığımız hata [ayıklama sonrası hata ayıklama](#crash-dumps) için ek meta verilerle bir kilitlenme bilgi dökümü dosyası oluşturulur. Bu döküm dosyaları şu şekilde Addresstemizlüklerin genişletilmiş kullanımını kolaylaştırır:

- Yerel makine testi,
- Şirket içi dağıtılmış test ve
- Test için bulut tabanlı iş akışları.

### <a name="install-the-addresssanitizer"></a>Addresstemizleme 'yi yükler

Addresstemizleme IDE tümleştirmesi ve kitaplıkları, Visual Studio Yükleyicisi C++ iş yükleri ile varsayılan olarak yüklenir. Ancak, Visual Studio 2019 ' nin eski bir sürümünden yükseltme yapıyorsanız, yükseltmeden sonra ASan desteğini etkinleştirmek için yükleyiciyi kullanın:

:::image type="content" source="media/asan-installer-option.png" alt-text="C++ Addresstemizleme bileşeni vurgulanması Visual Studio Yükleyicisi ekran görüntüsü":::

Yukarıdaki ekrana ulaşmak için Visual Studio Yükleyicisi var olan Visual Studio yüklemenizde **Değiştir** seçeneğini belirleyebilirsiniz.

> [!NOTE]
> Yeni güncelleştirmede Visual Studio 'Yu çalıştırırsanız ancak ASan 'ı yüklemediyseniz, kodunuzu çalıştırdığınızda bir hata alırsınız:
>
> LNK1356: ' clang_rt. asan_dynamic-i386. lib ' kitaplığı bulunamıyor

### <a name="use-the-addresssanitizer"></a><a name="using-asan"></a> Addresstemizleme 'yi kullanma

**`/fsanitize=address`** Aşağıdaki genel geliştirme yöntemlerinden herhangi birini kullanarak, derleyici seçeneğiyle yürütülebilir dosyaları oluşturmaya başlayın:

- Komut satırı derlemeleri
- Visual Studio proje sistemi
- Visual Studio CMake tümleştirmesi

 Yeniden derleyin ve ardından programınızı normal olarak çalıştırın. Bu kod üretimi [, birçok kesin hata](#error-types)türünü gösterir. Bu hatalar üç şekilde raporlanır: hata ayıklayıcı IDE 'de, komut satırında veya kesin satır dışı işleme için [Yeni bir döküm dosyası türünde](#crash-dumps) depolanır.

Microsoft bu üç standart iş akışı içinde Addresstemizleme kullanımını önerir:

- **Geliştirici iç döngüsü**
  - Visual Studio- [komut satırı](#command-prompt)
  - Visual Studio- [Proje sistemi](#ide-msbuild)
  - Visual Studio- [CMake](#ide-cmake)

- **CI/CD** -sürekli tümleştirme/sürekli geliştirme
  - Hata raporlama- [Yeni Adrestemizleme döküm dosyaları](#crash-dumps)

- Uyarlama [cihaz](https://llvm.org/docs/LibFuzzer.html) **sarmalayıcısı ile derleme**
  - [Azure OneFuzz](https://www.microsoft.com/security/blog/2020/09/15/microsoft-onefuzz-framework-open-source-developer-tool-fix-bugs/)
  - Yerel Makine

Bu makale, yukarıda listelenen üç iş akışını etkinleştirmek için gereken bilgileri içerir. Bilgiler, Addresstemizleme 'nin **platforma bağımlı** Windows 10 uygulamasına özgüdür. Bu belge, [Google, Apple ve GCC](#external-docs) 'nin zaten yayınlanmış olan harika belgelerini tamamlar.

> [!NOTE]
> Windows 10 ' da geçerli destek x86 ve x64 ile sınırlıdır. Gelecek sürümlerde görmek istediğiniz gibi [bize geri bildirim gönderin](https://aka.ms/vsfeedback/browsecpp) . Geri bildiriminiz,,,, veya gibi diğer temizleme için diğer temizleyiciler önceliklendirmemize yardımcı olur **`/fsanitize=thread`** **`/fsanitize=leak`** **`/fsanitize=memory`** **`/fsanitize=undefined`** **`/fsanitize=hwaddress`** . Sorunlarla karşılaşırsanız, [hataları buraya bildirebilirsiniz](https://aka.ms/feedback/report?space=62) .

## <a name="use-the-addresssanitizer-from-a-developer-command-prompt"></a><a name="command-prompt"></a> Bir geliştirici komut isteminden Addresstemizleme 'yi kullanma

**`/fsanitize=address`** Addresstemizleme çalışma zamanı için derlemeyi etkinleştirmek üzere bir [Geliştirici komut isteminde](../build/building-on-the-command-line.md#developer_command_prompt_shortcuts) derleyici seçeneğini kullanın. **`/fsanitize=address`** Seçeneği, var olan tüm C++ veya C optimizasyon düzeyleriyle uyumludur (örneğin,,, `/Od` , `/O1` `/O2` `/O2 /GL` ve `PGO` ). Seçeneği statik ve dinamik CRTS (örneğin,,, ve) ile birlikte kullanılır `/MD` `/MDd` `/MT` `/MTd` . Bir EXE veya DLL oluşturup oluşturamayacağını belirtir. Çağrı yığınlarının en iyi şekilde biçimlendirilmesi için hata ayıklama bilgileri gereklidir. Aşağıdaki örnekte, `cl /fsanitize=address /Zi` komut satırına geçirilir.

Addresstemizleme kitaplıkları (. lib dosyaları) sizin için otomatik olarak bağlanır. Daha fazla bilgi için bkz. [Addresstemizleme dili, derleme ve hata ayıklama başvurusu](asan-building.md).

### <a name="example---basic-global-buffer-overflow"></a>Örnek-temel genel arabellek taşması

```cpp
// basic-global-overflow.cpp
#include <stdio.h>
int x[100];
int main() {
    printf("Hello!\n");
    x[100] = 5; // Boom!
    return 0;
}
```

Visual Studio 2019 için geliştirici komut istemi kullanma, kullanarak derleme *`main.cpp`*`/fsanitize=address /Zi`

:::image type="content" source="media/asan-command-basic-global-overflow.png" alt-text="Addresstemizleme seçenekleriyle derlemek için komutu gösteren komut isteminin ekran görüntüsü.":::

Komut satırında ortaya çıkan sonucu çalıştırdığınızda *`main.exe`* , aşağıda görülen biçimli hata raporunu oluşturur.

Yedi önemli bilgi parçasını vurgulayan, yer alan ve kırmızı kutuları göz önünde bulundurun:

:::image type="content" source="media/asan-basic-global-overflow.png" alt-text="Temel genel taşma hatasını gösteren hata ayıklayıcının ekran görüntüsü.":::

### <a name="red-highlights-from-top-to-bottom"></a>Yukarıdan aşağıya kırmızı vurgular

1. Bellek güvenliği hatası, genel arabelleğe yönelik bir taşma olur.
2. Kullanıcı tanımlı herhangi bir değişken dışında **depolanan** **4 bayt** (32 bit) vardı.
3. Mağaza, `main()` 7. satırdaki dosyada tanımlanan işlevde yer `basic-global-overflow.cpp` alır.
4. Adlı değişken, `x` 1. satırda Basic-Global-overflow. cpp içinde tanımlanır ve 8. sütundan başlayarak
5. Bu genel değişken `x` 400 bayt boyutlardır
6. Deponun hedeflediği adresi açıklayan tam [Gölge bayt](./asan-shadow-bytes.md) değeri `0xf9`
7. Gölge bayt göstergesi şöyle `0xf9` bir doldurma alanıdır `int x[100]`

> [!NOTE]
> Çağrı yığınındaki işlev adları, hata sonrasında çalışma zamanı tarafından çağrılan [LLVM sembobir](https://llvm.org/docs/CommandGuide/llvm-symbolizer.html) şekilde oluşturulur.

## <a name="use-the-addresssanitizer-in-visual-studio"></a><a name="ide-msbuild"></a> Visual Studio 'da Addresstemizbir cihaz kullanma

Addresstemizleme, Visual Studio IDE ile tümleşiktir. Bir MSBuild projesi için Addresstemizme özelliğini açmak için Çözüm Gezgini içinde projeye sağ tıklayın ve **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**  >  **C/C++**  >  **genel**' i seçin ve ardından **addresstemizbir özelliği etkinleştir** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

:::image type="content" source="media/asan-project-system-dialog.png" alt-text="Addresstemizleme özelliğini etkinleştir özelliğinin gösterildiği Özellik sayfaları iletişim kutusunun ekran görüntüsü.":::

IDE 'den derlemek için, herhangi bir [uyumsuz seçenekten](./asan-known-issues.md#incompatible-options)vazgeçin. **`/Od`**(Veya hata ayıklama modu) kullanılarak derlenen mevcut bir proje için, bu seçenekleri kapatmanız gerekebilir:

- [Düzenle ve devam et 'i](/visualstudio/debugger/how-to-enable-and-disable-edit-and-continue) kapat
- Kapat [ `/RTC1` (çalışma zamanı denetimleri)](../build/reference/rtc-run-time-error-checks.md)
- Kapat [ `/INCREMENTAL` (artımlı bağlama)](../build/reference/incremental-link-incrementally.md)

Hata ayıklayıcıyı derlemek ve çalıştırmak için **F5** girin. Visual Studio 'da bu pencere görüntülenir:

:::image type="content" source="media/asan-global-buffer-overflow-F5.png" alt-text="Genel bir arabellek taşması hatası gösteren hata ayıklayıcının ekran görüntüsü.":::

## <a name="using-the-addresssanitizer-from-visual-studio-cmake"></a><a name="ide-cmake"></a> Visual Studio 'dan Addresstemizleme 'yi kullanma: CMake

[Hedef Windows için oluşturulan bir CMake projesi Için addresstemizlemesini](../build/cmake-projects-in-visual-studio.md)etkinleştirmek üzere şu adımları uygulayın:

1. IDE 'nin en üstündeki araç çubuğunda bulunan **Konfigürasyonlar** açılan menüsünü açın ve **konfigürasyonları Yönet**' i seçin.

   :::image type="content" source="media/asan-cmake-configuration-dropdown.png" alt-text="CMake yapılandırma açılır listesinin ekran görüntüsü.":::

   Bu seçim, dosyadaki bir CMakeSettings.jskaydedilen CMake proje ayarları düzenleyicisini açar.

1. Düzenleyicide **JSON bağlantısını Düzenle** ' yi seçin. Bu seçim görünümü ham JSON olarak değiştirir.

1. Özelliği ekleyin: **"Addresstemizzerenabled": true**

   Bu görüntü, bu değişiklikten sonra CMakeSettings.js:

   :::image type="content" source="media/asan-cmake-json.png" alt-text="CMakeSettings.jsmetin düzenleyici görünümünün ekran görüntüsü.":::

1. Bu JSON dosyasını kaydetmek için **CTRL + S tuşlarına** basın, ardından hata ayıklayıcı altında yeniden derlemek ve çalıştırmak için **F5** girin.

Bu ekran görüntüsü CMake derlemeden hatayı yakalar.

:::image type="content" source="media/asan-cmake-error-f5.png" alt-text="CMake derleme hata iletisinin ekran görüntüsü.":::

## <a name="addresssanitizer-crash-dumps"></a><a name="crash-dumps"></a> Addresstemizleme kilitlenme dökümleri

Bulut ve dağıtılmış iş akışlarıyla kullanılmak üzere Addresstemizleme için yeni işlevler sunuyoruz. Bu işlevsellik, IDE 'de bir Addresstemizleme hatasının çevrimdışı görüntülenmesine izin verir. Canlı bir hata ayıklama oturumunda deneydiklerinizi yaptığınız gibi, hata kaynağınızın üst kısmında yer alır.

Bu yeni döküm dosyaları bir hata analiz edilirken verimliliklere yol açabilir. Yeniden çalıştırmanız veya uzak verileri bulmanız veya çevrimdışı olan bir makineyi aramanız gerekmez.

Daha sonraki bir tarihte, başka bir makinede Visual Studio 'da görüntülenebilen yeni bir döküm dosyası türü oluşturmak için:

```cmd
set ASAN_SAVE_DUMPS=MyFileName.dmp
```

Visual Studio 16,9 ' den itibaren, dosyanızda kaynak kodunuzun en üstünde depolanan, **tam olarak tanılanan bir hatayı** görüntüleyebilirsiniz *`*.dmp`* .

[Bu yeni kilitlenme bilgi döküm işlevselliği](./asan-offline-crash-dumps.md) , bulut tabanlı iş akışlarını veya dağıtılmış sınamayı mümkün bir şekilde sunar. Ayrıca, herhangi bir senaryoda ayrıntılı, eyleme dönüştürülebilir bir hata vermek için kullanılabilir.

## <a name="example-errors"></a><a name="error-types"></a> Örnek hatalar

Addresstemizleme, çok sayıda bellek kötüye kullanımı hatasını algılayabilir. Addresstemizleme () derleyici seçeneği kullanılarak derlenen ikililerini çalıştırdığınızda raporlanan çalışma zamanı hatalarının birçoğu aşağıda verilmiştir **`/fsanitize=address`** :

- [`alloc-dealloc-mismatch`](error-alloc-dealloc-mismatch.md)
- [`allocation-size-too-big`](error-allocation-size-too-big.md)
- [`calloc-overflow`](error-calloc-overflow.md)
- [`double-free`](error-double-free.md)
- [`dynamic-stack-buffer-overflow`](error-dynamic-stack-buffer-overflow.md)
- [`global-buffer-overflow`](error-global-buffer-overflow.md)
- [`heap-buffer-overflow`](error-heap-buffer-overflow.md)
- [`heap-use-after-free`](error-heap-use-after-free.md)
- [`invalid-allocation-alignment`](error-invalid-allocation-alignment.md)
- [`memcpy-param-overlap`](error-memcpy-param-overlap.md)
- [`new-delete-type-mismatch`](error-new-delete-type-mismatch.md)
- [`stack-buffer-overflow`](error-stack-buffer-overflow.md)
- [`stack-buffer-underflow`](error-stack-buffer-underflow.md)
- [`stack-use-after-return`](error-stack-use-after-return.md)
- [`stack-use-after-scope`](error-stack-use-after-scope.md)
- [`strncat-param-overlap`](error-strncat-param-overlap.md)
- [`use-after-poison`](error-use-after-poison.md)

Örnekler hakkında daha fazla bilgi için bkz. [Addresstemizleme hatası örnekleri](./asan-error-examples.md).

## <a name="differences-with-clang-120"></a><a name="differences"></a> Clang 12,0 farkları

MSVC Şu anda, Clang 12,0 'den iki işlevsel alanda farklılık gösterir:

- **yığın kullanımı** -sonrası-kapsam-bu ayar varsayılan olarak açıktır ve kapatılamaz.
- **Stack-RETURN-RETURN-RETURN** -Bu işlevsellik, ek bir derleyici seçeneği gerektirir ve yalnızca ayarı ile kullanılamaz `ASAN_OPTIONS` .

Bu kararlar, bu ilk sürümü sunmak için gerekli olan test matrisini azaltmak için yapılmıştır.

Visual Studio 2019 16,9 ' de hatalı pozitif sonuçlar oluşmasına neden olabilecek özellikler dahil değildir. Bu disiplin, var olan kodun dekiyle birlikte çalışabilirlik için gereken etkili test bütünlüğünü zorlüyor. Daha sonraki sürümlerde daha fazla özellik göz önünde bulundurulmalıdır:

- [Başlatma sırası Fiasco](https://github.com/google/sanitizers/wiki/AddressSanitizerInitializationOrderFiasco)
- [İçi nesne taşması](https://github.com/google/sanitizers/wiki/AddressSanitizerIntraObjectOverflow)
- [Kapsayıcı taşması](https://github.com/google/sanitizers/wiki/AddressSanitizerContainerOverflow)
- [İşaretçi çıkarma/karşılaştırma](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html)

Daha fazla bilgi için bkz. [MSVC Ile Addresstemizleme Için derleme](./asan-building.md).

## <a name="existing-industry-documentation"></a><a name="external-docs"></a> Mevcut sektör belgeleri

Bu dil ve Addresstemizleme teknolojisinin platforma bağımlı uygulamaları için kapsamlı belgeler zaten var.

- [Google](https://github.com/google/sanitizers/wiki/AddressSanitizer)
- [Apple](https://developer.apple.com/documentation/xcode/diagnosing_memory_thread_and_crash_issues_early)
- [GCC](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html)

[Addresstemizleme](https://www.usenix.org/system/files/conference/atc12/atc12-final39.pdf) için bu kağıt, uygulamayı açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hata ayıklayıcısı tümleştirmesi](./asan-debugger-integration.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
