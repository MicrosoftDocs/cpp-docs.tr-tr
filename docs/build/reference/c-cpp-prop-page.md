---
title: C/C++ proje özellikleri (Visual Studio)
ms.date: 7/18/2019
ms.topic: article
ms.assetid: 16375038-4917-4bd0-9a2a-26343c1708b7
ms.openlocfilehash: 91edf30ef0e5f38088727c0280d2edf07cdebfa5
ms.sourcegitcommit: 7b039b5f32f6c59be6c6bb1cffafd69c3bfadd35
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/26/2019
ms.locfileid: "68537573"
---
# <a name="cc-property-pages"></a>C/C++ Özellik sayfaları

Aşağıdaki özellik sayfaları **Proje** > **özellikleri** > **yapılandırma özellikleri** > **C/C++** altında bulunur:

## <a name="cc-general-properties"></a>C/C++ Genel Özellikler

### <a name="additional-include-directories"></a>Ek Içerme dizinleri

Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazlaysa noktalı virgülle ayırın. [/İ (ek içerme dizinleri)](i-additional-include-directories.md)ayarlar.

### <a name="additional-using-directories"></a>Ek #using dizinleri

Bir #using yönergesine geçirilen adları çözümlemek için aranacak bir veya daha fazla dizini (virgülle ayrılmış ayrı Dizin adları) belirtir. [/AI](ai-specify-metadata-directories.md)'yi ayarlar.

### <a name="debug-information-format"></a>Hata ayıklama bilgi biçimi

Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir.  Bu, uyumlu bağlayıcı ayarları gerektirir. [/Z7,/Zi,/ZI (hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md)ayarlar.

**Yapabileceği**

- **Hiçbiri** -hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlı olabilir.
- **C7 uyumlu** -programınız için oluşturulan hata ayıklama bilgileri türünü ve bu bilgilerin nesne (. obj) dosyalarında mi yoksa bir program VERITABANı (pdb) içinde tutulup tutulmadığını seçin.
- **Program veritabanı** -hata ayıklayıcı ile kullanılmak üzere tür bilgilerini ve simgesel hata ayıklama bilgilerini içeren bir program VERITABANı (pdb) oluşturur. Simgesel hata ayıklama bilgileri, işlevlerin ve satır numaralarının adlarının yanı sıra değişkenlerini ve türlerini içerir.
- **Düzenle ve devam et Için program veritabanı** -yukarıda açıklanan şekilde, [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue) özelliğini destekleyen bir biçimde bir program veritabanı oluşturur.

### <a name="support-just-my-code-debugging"></a>Yalnızca kendi kodum hata ayıklama desteği

Bu derleme biriminde [yalnızca kendi kodum](/visualstudio/debugger/just-my-code) hata ayıklamayı etkinleştirmek için destekleyici kod ekler. [/JMC](jmc.md)'yi ayarlar.

### <a name="common-language-runtime-support"></a>Ortak dil çalışma zamanı desteği

.NET çalışma zamanı hizmetini kullanın.  Bu anahtar, başka bazı anahtarlarla uyumsuzdur; Ayrıntılar için anahtarlar ailesinin [/clr](clr-common-language-runtime-compilation.md) ailesi belgelerine bakın.

**Yapabileceği**

- **Ortak dil çalışma zamanı desteği yok** -ortak dil çalışma zamanı desteği yok
- **Ortak dil çalışma zamanı desteği** -uygulamanız IÇIN diğer CLR uygulamaları tarafından tüketilen meta verileri oluşturur ve UYGULAMANıZıN diğer CLR bileşenlerinin Meta verilerdeki türleri ve verileri kullanmasına izin verir.
- **Saf MSIL ortak dil çalışma zamanı desteği** -MSIL 'e derlenmiş yerel türler içerse de, yerel yürütülebilir kodu olmayan bir [MSIL](/dotnet/standard/managed-code)çıkış dosyası oluşturur.
- **GÜVENLI MSIL ortak dil çalışma zamanı desteği** -salt MSIL (yerel yürütülebilir kod içermeyen) ve doğrulanabilir çıkış dosyası oluşturur.

### <a name="consume-windows-runtime-extension"></a>Windows Çalışma Zamanı uzantısını tüketme

Windows çalışma zamanı dillerini kullanın uzantıları. [/ZW](zw-windows-runtime-compilation.md)ayarlar.

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

Derleyici başlatıldığında ve derleme sırasında bilgilendirici iletileri görüntülerken oturum açma başlığının görüntülenmesini önler.

### <a name="warning-level"></a>Uyarı düzeyi

Derleyicinin kod hataları hakkında ne kadar sıkı olmasını istediğinizi seçin. [/W0-/W4](compiler-option-warning-level.md)' ü ayarlar.

**Yapabileceği**

- **Tüm uyarıları** kapat-düzey 0 tüm uyarıları devre dışı bırakır.
- **Level1** -Level 1 ciddi uyarıları görüntüler. Düzey 1, komut satırındaki varsayılan uyarı düzeyidir.
- **Level2** -Level 2, 1. düzey tüm uyarıları ve uyarıları düzey 1 ' den daha az önem gösterir.
- **Level3** -Level 3, tüm düzey 2 uyarılarını ve üretim amaçları için önerilen tüm diğer uyarıları görüntüler.
- **Level4** -Level 4, tüm düzey 3 uyarılarını ve bilgilendirici uyarıları görüntüler, bu durum çoğu durumda güvenle yoksayılabilir.
- **Enablealluyarılar** -varsayılan olarak devre dışı bırakılan tüm uyarıları etkin şekilde sunar.

### <a name="treat-warnings-as-errors"></a>Uyarıları hata olarak değerlendir

Tüm derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde [/WX](wx-treat-linker-warnings-as-errors.md) kullanılması en iyi yöntem olabilir; Tüm uyarıların çözümlenmesi, en az olası bulma kod kusurlarını güvence altına alacak.

### <a name="warning-version"></a>Uyarı sürümü

Derleyicinin belirli bir sürümünden sonra tanıtılan uyarıları gizleyin. [/WV: xx\[.\]yy\[\]. zzzzz](wx-treat-linker-warnings-as-errors.md)ayarlar.

### <a name="diagnostics-format"></a>Tanılama biçimi

Tanılama iletilerinde sütun bilgisi ve kaynak bağlamı ile zengin tanılamayı mümkün bir şekilde sunar.

**Yapabileceği**

- Giriş **işareti** -tanılama iletisinde sütun bilgileri sağlar ve ilgili kaynak kodu satırını, sorunlu sütunu gösteren bir giriş işaretine göre verir.
- **Sütun bilgisi** -ek olarak, varsa, Tanılamanın verildiği satırdaki sütun numarasını da sağlar.
- **Klasik** -önceki ve kısa tanılama iletilerini satır numarasıyla korur.

### <a name="sdl-checks"></a>SDL denetimleri

Ek güvenlik geliştirme yaşam döngüsü (SDL) önerilen denetimler; ek güvenli kod oluşturma özelliklerini etkinleştirmeyi içerir ve hata olarak güvenlikle ilgili ek uyarıları etkinleştirir. [/SDL,/SDL-](sdl-enable-additional-security-checks.md)ayarlar.

### <a name="multi-processor-compilation"></a>Çok işlemcili derleme

Çok işlemcili derleme.

## <a name="cc-optimization-properties"></a>C/C++ optimizasyon özellikleri

### <a name="optimization"></a>İyileştirme

Kod iyileştirmesi için seçenek belirleyin; belirli iyileştirme seçeneklerini kullanmak için özel ' i seçin. [/Od](od-disable-debug.md), [/O1,/O2](o-options-optimize-code.md)ayarlar.

**Yapabileceği**

- **Özel** -özel iyileştirme.
- **Devre dışı** -iyileştirmeyi devre dışı bırak.
- **En fazla iyileştirme (boyut kullanımı)** -/OG/OS/oy/Ob2/GS/GF/gy ile eşdeğer
- **En fazla iyileştirme (hız kullanımı)** -/OG/Oi/ot/oy/Ob2/GS/GF/gy ile eşdeğer
- **İyileştirmeler (hıza öncelik)** -/OG/Oi/ot/oy/Ob2 ile eşdeğer

### <a name="inline-function-expansion"></a>Satır içi Işlev genişletmesi

Yapı için [satır içi işlev](../../cpp/inline-functions-cpp.md) genişletmesinin düzeyini seçin. [/OB1,/Ob2](ob-inline-function-expansion.md)ayarlar.

**Yapabileceği**

- **Default**
- **Devre dışı** -varsayılan olarak açık olan satır içi genişletmeyi devre dışı bırakır.
- **Yalnızca __inline** -yalnızca satır içi, __inline, __forceinline veya __inline olarak işaretlenen işlevleri genişletir veya bir sınıf C++ bildiriminde tanımlanan bir üye işlevinde.
- **Herhangi bir uygun** -satır içi veya __inline olarak işaretlenen işlevleri ve derleyicinin seçtiği diğer işlevleri genişletir (genişletme derleyicinin kararına (genellikle otomatik olarak ifade edilir) olur).

### <a name="enable-intrinsic-functions"></a>Iç Işlevleri etkinleştir

İç işlevleri sunar.  İç işlevleri kullanmak daha hızlı, ancak muhtemelen daha büyük bir kod üretir. [/Oi](oi-generate-intrinsic-functions.md)ayarlar.

### <a name="favor-size-or-speed"></a>Boyut veya hız kullanmayı tercih edin

Kod boyutu veya kod hızının tercih edilip edilmeyeceğini belirtir; ' Genel Iyileştirme ' açık olmalıdır. [/Ot,/OS](os-ot-favor-small-code-favor-fast-code.md)ayarlar.

**Yapabileceği**

- **Küçük kod** kullanımı küçük kodu tercih edin. Derleyicinin boyut hızını tercih etmek üzere karşılaştırarak, EXEs ve DLL 'lerin boyutunu en aza indirir.
- **Hızlı kod** kullanımı hızlı kodu tercih edin. , Derleyicisini boyut hızını artırmak üzere karşılaştırarak, EXEs ve DLL 'Lerin hızını en üst düzeye çıkarır. (Bu varsayılandır.)
- **Ne** -boyut yok ne de hız iyileştirmesi.

### <a name="omit-frame-pointers"></a>Çerçeve Işaretçilerini atla

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

### <a name="enable-fiber-safe-optimizations"></a>Fiber güvenli Iyileştirmeleri etkinleştir

Lifleri görmeyin ve iş parçacığı yerel depolama erişimi kullanılırken bellek alanı iyileştirmesini sunar. [/Gt](gt-support-fiber-safe-thread-local-storage.md)'yi ayarlar.

### <a name="whole-program-optimization"></a>Tüm program Iyileştirmesi

Kod oluşturmayı bağlantı zamanına erteleyerek modüller arası iyileştirmeleri sağlar; ' bağlama zamanı kodu oluşturma ' bağlayıcı seçeneğinin açık olmasını gerektirir. [/GL](gl-whole-program-optimization.md)'yi ayarlar.

## <a name="cc-preprocessor-properties"></a>C/C++ Önişlemci özellikleri

### <a name="preprocessor-definitions"></a>Önişlemci tanımları

Kaynak dosyanız için bir ön işleme sembolleri tanımlar.

### <a name="undefine-preprocessor-definitions"></a>Önişlemci tanımlarının tanımı kaldırılıyor

Bir veya daha fazla önişlemci tarafından tanımlanabileceğini belirtir. [/U](u-u-undefine-symbols.md)ayarlar.

### <a name="undefine-all-preprocessor-definitions"></a>Tüm önişlemci tanımlarının tanımlanunlarını kaldır

Önceden tanımlanmış tüm Önişlemci değerlerini tanımlayın. [/U](u-u-undefine-symbols.md)ayarlar.

### <a name="ignore-standard-include-paths"></a>Standart Içerme yollarını yoksay

Derleyicinin INCLUDE ortam değişkenlerinde belirtilen dizinlerde içerme dosyalarını aramasını engeller.

### <a name="preprocess-to-a-file"></a>Bir dosyaya ön işlem

C ve C++ kaynak dosyalarını ön işler ve önceden işlenmiş çıktıyı bir dosyaya yazar. Bu seçenek derlemeyi bastırır, bu nedenle bir. obj dosyası oluşturmaz.

### <a name="preprocess-suppress-line-numbers"></a>Satır numaralarını gösterme öncesi işlem

#Line yönergeleri olmadan ön işleme.

### <a name="keep-comments"></a>Açıklamaları tut

Kaynak koddan açıklama şeridinin görüntülenmesini önler; ' ön Işleme ' seçeneklerinden birinin ayarlanmasını gerektirir. [/C](c-preserve-comments-during-preprocessing.md)ayarlar.

## <a name="cc-code-generation-properties"></a>C/C++ kod oluşturma özellikleri

### <a name="enable-string-pooling"></a>Dize havuzunu etkinleştir

Derleyicinin program görüntüsünde ve yürütme sırasında bellekte özdeş dizelerin tek bir salt okunurdur kopyasını oluşturmasını sağlar, böylece daha küçük programlar, dize havuzu oluşturma adlı bir iyileştirme olur. [/O1,/O2](o-options-optimize-code.md)ve [/Zi](z7-zi-zi-debug-information-format.md) , [/GF](gf-eliminate-duplicate-strings.md) seçeneğini otomatik olarak ayarlar.

### <a name="enable-minimal-rebuild"></a>En az yeniden derlemeyi etkinleştir

Değiştirilen C++ sınıf tanımlarının (üst bilgi ( C++ . h) dosyalarında depolanan) yeniden derlenmesi gerekip gerekmediğini belirleyen en az yeniden oluşturmayı sağlar.

### <a name="enable-c-exceptions"></a>Özel C++ durumları etkinleştir

Derleyici tarafından kullanılacak özel durum işleme modelini belirtir.

**Yapabileceği**

- **SEH özel durumlarıyla Evet** -zaman uyumsuz (yapılandırılmış) ve zaman uyumlu (C++) özel durumları yakalayan özel durum işleme modeli. [/EHa](eh-exception-handling-model.md)ayarlar.
- **Evet** -özel durumları yakalayan C++ özel durum işleme modeli ve derleyiciye extern ' ın hiçbir C++ özel durum oluşturmadığını varsaymasını söyler. [/EHsc](eh-exception-handling-model.md)'yi ayarlar.
- ' **Extern ' Işlevleriyle Evet** -özel durumları yakalayan C++ özel durum işleme modeli ve derleyiciye extern r işlevlerinin bir özel durum oluşturduğunu varsaymasını söyler. [/EHS](eh-exception-handling-model.md)'yi ayarlar.
- **Hayır** -özel durum işleme yok.

### <a name="smaller-type-check"></a>Daha küçük tür denetimi

Daha küçük türlere dönüştürme için, hata ayıklama dışında herhangi bir iyileştirme türüyle uyumlu olmayan şekilde denetlemeyi etkinleştirin. [/RTCC](rtc-run-time-error-checks.md)'yi ayarlar.

### <a name="basic-runtime-checks"></a>Temel çalışma zamanı denetimleri

Hata ayıklama dışında herhangi bir iyileştirme türüyle uyumlu olmayan temel çalışma zamanı hata denetimleri gerçekleştirin. [/RTCs,/RTCu,/RTC1](rtc-run-time-error-checks.md)ayarlar.

**Yapabileceği**

- **Yığın çerçeveleri** -yığın çerçevesi çalışma zamanı hata denetimini mümkün.
- **Başlatılmamış değişkenler** -bir değişken başlatılmadan kullanıldığında raporlar.
- **Her ikisi (/RTC1, EQUIV. to/RTCsu)** -/RTCsu. 'ın eşdeğeri
- Varsayılan **-varsayılan** çalışma zamanı denetimleri.

### <a name="runtime-library"></a>Çalışma zamanı kitaplığı

Bağlama için çalışma zamanı kitaplığını belirtin. [/MT,/MTd,/MD,/MDd](md-mt-ld-use-run-time-library.md)ayarlar.

**Yapabileceği**

- **Çoklu iş parçacıklı** -uygulamanızın iş parçacığı, çalışma zamanı kitaplığının statik sürümünü kullanmasına neden olur.
- **Çok iş parçacıklı hata ayıklama** -_DEBUG ve _MT tanımlar. Bu seçenek, aynı zamanda, derleyicinin LIBCMTD.lib kitaplık adını .obj dosyasına koyarak bağlayıcının dış simgeleri çözme sırasında LIBCMTD.lib kullanmasını sağlar.
- **Çok iş PARÇACıKLı dll** -uygulamanızın çalışma zamanı kitaplığının çoklu iş PARÇACıKLı ve DLL 'ye özgü sürümünü kullanmasına neden olur. _MT ve _DLL tanımlar ve derleyicinin MSVCRT. lib kitaplık adını. obj dosyasına yerleştirmesini sağlar.
- **Çok iş parçacıklı hata ayıklama DLL 'si** -_DEBUG, _MT ve _DLL öğelerini tanımlar ve uygulamanızın çalışma zamanı kitaplığı 'nın çoklu iş parçacığı ve DLL 'ye özgü sürümünü kullanmasına neden olur. Ayrıca, derleyicinin MSVCRTD.lib kitaplık adını .obj dosyasına yerleştirmesini sağlar.

### <a name="struct-member-alignment"></a>Struct üye hizalaması

Struct üye hizalaması için 1, 2, 4 veya 8 baytlık sınırları belirtir. [/ZP](zp-struct-member-alignment.md)'yi ayarlar.

**Yapabileceği**

- 1 baytlık sınırlardaki **1 baytlık** paketler yapıları. /ZP. ile aynı
- **2 bayt** -2 baytlık sınırlardaki yapıları paketler.
- 4 baytlık sınırlardaki **4 baytlık** paketler yapıları.
- 8 **bayt** -8 baytlık sınırlar üzerinde (varsayılan) yapı paketleri.
- 16 baytlık, 16 baytlık sınırlardaki yapı paketleri.
- **Varsayılan** hizalama ayarları.

### <a name="security-check"></a>Güvenlik denetimi

Güvenlik denetimi, bir programın güvenliği üzerinde yaygın olarak gerçekleştirilen bir saldırıya karşı yığın arabelleğinin çalıştırılmaların algılanmasına yardımcı olur. 

**Yapabileceği**

- **Güvenlik denetimini devre** dışı bırak-güvenlik denetimini devre dışı bırak. [/GS-](gs-buffer-security-check.md)ayarlar.
- **Güvenlik denetimini etkinleştirin** -güvenlik denetimini etkinleştirin. [/GS](gs-buffer-security-check.md)ayarlar.

### <a name="control-flow-guard"></a>Denetim akışı koruyucusu

Guard güvenlik denetimi, geçersiz kod bloğuna gönderim girişimlerini algılamaya yardımcı olur. 

**Yapabileceği**

- **Evet** -koruma kümeleri [/Guard: CF](guard-enable-control-flow-guard.md)ile güvenlik denetimini etkinleştirin.
- **Eşleşen**

### <a name="enable-function-level-linking"></a>Işlev düzeyinde bağlamayı etkinleştir

Derleyicinin paketlenmiş işlevler (Compts) biçiminde tek tek işlevleri paketetmesine olanak tanır. Düzenle ve çalışmaya devam etmek için gereklidir. [/GY](gy-enable-function-level-linking.md)ayarlar.

### <a name="enable-parallel-code-generation"></a>Paralel kod oluşturmayı etkinleştir

Derleyicinin, iyileştirme etkinleştirildiğinde #pragma loop (hint_parallel\[(n)]) kullanılarak tanımlanan döngüler için paralel kod oluşturmasını sağlar.

### <a name="enable-enhanced-instruction-set"></a>Gelişmiş yönerge kümesini etkinleştir

Gelişmiş yönerge kümelerini destekleyen işlemcilerde bulunan yönergelerin kullanımını etkinleştirin; Örneğin, SSE, SSE2, AVX ve AVX2 geliştirmeleri IA-32; AVX ve AVX2 to x64. Şu anda **/Arch: SSE** ve **/Arch: SSE2** yalnızca x86 mimarisi oluşturulurken kullanılabilir. Hiçbir seçenek belirtilmemişse, derleyici SSE2 destekleyen işlemcilerde bulunan yönergeleri kullanır. Gelişmiş yönergelerin kullanımı,/Arch: ıA32 ile devre dışı bırakılabilir. Daha fazla bilgi için bkz. [/Arch (x86)](arch-x86.md), [/Arch (x64)](arch-x64.md) ve [/Arch (ARM)](arch-arm.md) .

**Yapabileceği**

- **Streaming SIMD Extensions** Streaming SIMD Extensions. Ayarlar **/Arch: SSE**
- **Streaming SIMD Extensions 2** -Streaming SIMD Extensions 2. Ayarlar **/Arch: SSE2**
- **Gelişmiş vektör Uzantıları** -gelişmiş vektör uzantıları. Ayarlar **/Arch: AVX**
- **Gelişmiş vektör uzantıları 2** -gelişmiş vektör uzantıları 2. Ayarlar **/Arch: AVX2**
- **Gelişmiş yönerge yok** -gelişmiş yönerge yok. Ayarlar **/Arch: IA32**
- **Ayarlanmadı** -ayarlanmadı.

### <a name="floating-point-model"></a>Kayan nokta modeli

Kayan nokta modelini ayarlar. [/FP: kesin,/fp: Strict,/fp: Fast](fp-specify-floating-point-behavior.md)ayarlar.

**Yapabileceği**

- **Kesin** -varsayılan. Eşitlik ve eşitsizlik için kayan nokta testlerinin tutarlılığını geliştirir.
- **Strict** -en katı kayan nokta modeli. /FP: Strict, fp_contract 'in kapalı ve fenv_access olmasını sağlar. /FP: except kapsanıyor ve açıkça/FP: except-belirtilerek devre dışı bırakılabilir. /FP: except-,/fp: Strict ile kullanıldığında, kesin kayan nokta semantiğini uygular, ancak olağanüstü olaylar için uygun değildir.
- **Hızlı** -çoğu durumda en hızlı kodu oluşturur.

### <a name="enable-floating-point-exceptions"></a>Kayan nokta özel durumlarını etkinleştir

Güvenilir kayan nokta özel durumu modeli. Özel durumlar, tetiklendikten hemen sonra oluşturulur.  [/FP: except](fp-specify-floating-point-behavior.md)olarak ayarlar.

### <a name="create-hotpatchable-image"></a>Düzeltme eki eklenebilir görüntü oluşturma

Düzeltme Eki açık olduğunda, derleyici, her işlevin ilk yönergesinin, sık yama için gerekli olan iki bayt olmasını sağlar.  [/Hotpatch](hotpatch-create-hotpatchable-image.md)ayarlar.

### <a name="spectre-mitigation"></a>Spectre azaltma

CVE 2017-5753 için Spectre azaltmaları. [/Qspectre](qspectre.md)ayarlar.

**Yapabileceği**

- **Etkin** -CVE 2017-5753 için Spectre azaltma özelliğini etkinleştir
- **Devre dışı** -ayarlı değil.

## <a name="cc-language-properties"></a>C/C++ dil özellikleri

### <a name="disable-language-extensions"></a>Dil uzantılarını devre dışı bırak

Dil uzantılarını bastırır veya izin vermez. [/Za](za-ze-disable-language-extensions.md)ayarlar.

### <a name="conformance-mode"></a>Uyumluluk modu

Uygunluk modunu etkinleştirilir veya gizler. [/Permissive-](permissive-standards-conformance.md)ayarlar.

### <a name="treat-wchart-as-built-in-type"></a>WChar_t 'yi yerleşik tür olarak değerlendir

Belirtildiğinde, wchar_t türü __wchar_t ile eşlenen yerel bir tür olur ve bu, __int16 ile aynı şekilde eşlenir. [/Zc: wchar_t](zc-wchar-t-wchar-t-is-native-type.md) varsayılan olarak açık.

### <a name="force-conformance-in-for-loop-scope"></a>Döngü kapsamında uygunluğu zorla

Microsoft uzantılarıyla for ifadesinin C++ döngüleri için standart davranışı uygulamak üzere kullanılır. [/Za,/Ze (dil uzantılarını devre dışı bırak](za-ze-disable-language-extensions.md)) ayarlar. [/Zc: forScope](zc-forscope-force-conformance-in-for-loop-scope.md) varsayılan olarak açık.

### <a name="remove-unreferenced-code-and-data"></a>Başvurulmayan kod ve verileri Kaldır

Belirtildiğinde, derleyici artık başvurulmayan kod ve veriler için sembol bilgisi oluşturmaz.

### <a name="enforce-type-conversion-rules"></a>Tür dönüştürme kurallarını zorlama

Bir rvalue başvuru türünü C++ 11 standardına uygun bir dönüştürme işleminin sonucu olarak belirlemek için kullanılır.

### <a name="enable-run-time-type-information"></a>Çalışma zamanı türü bilgilerini etkinleştir

Çalışma zamanında nesne türlerini C++ denetlemek için kod ekler (çalışma zamanı türü bilgileri). [/Gr,/GR-](gr-enable-run-time-type-information.md)ayarlar.

### <a name="open-mp-support"></a>MP desteğini açın

OpenMP 2,0 dil uzantılarını etkinleştirin. [/OpenMP](openmp-enable-openmp-2-0-support.md)ayarlar.

### <a name="c-language-standard"></a>C++Dil standardı

Derleyicinin zorlayacağı C++ dil standardını belirler. Mümkün olduğunda en son sürümü kullanmanız önerilir. Ayarlar [/std: c++ 14,/std: c++ 17,/std: c + + latest](std-specify-language-standard-version.md).

**Yapabileceği**

- **Default**
- **ISO C++ 14 standart**
- **ISO C++ 17 Standart**
- **Önizleme-son C++ çalışma taslağındaki Özellikler**

### <a name="enable-c-modules-experimental"></a>Modülleri C++ etkinleştir (deneysel)

C++ Modüller ve standart kitaplık modülleri için deneysel destek.

## <a name="cc-precompiled-headers-properties"></a>C/C++ ön derlenmiş üstbilgiler özellikleri

### <a name="precompiled-header"></a>Ön derlenmiş üstbilgi

Önceden derlenmiş üst bilgi oluştur/kullan: Derleme sırasında önceden derlenmiş üst bilgi oluşturmayı veya kullanmayı mümkün. [/Yıc](yc-create-precompiled-header-file.md), [/yu](yu-use-precompiled-header-file.md)ayarlar.

**Yapabileceği**

- **Oluşturma** -derleyicinin belirli bir noktada derlemenin durumunu temsil eden ön derlenmiş üst bilgi (. pch) dosyası oluşturmasını söyler.
- **Use** -derleyicinin geçerli derlemede var olan bir ön derlenmiş üstbilgi (. pch) dosyasını kullanmasını söyler.
- Önceden derlenmiş üst bilgiler **kullanılmıyor-önceden** derlenmiş üst bilgiler kullanmıyor.

### <a name="precompiled-header-file"></a>Önceden derlenmiş üst bilgi dosyası

Önceden derlenmiş bir üstbilgi dosyası oluştururken veya kullanılırken kullanılacak üst bilgi dosyası adını belirtir. [/Yıc](yc-create-precompiled-header-file.md), [/yu]] (Yu-Use-önceden derlenmiş-header-File.MD) ayarlar.

### <a name="precompiled-header-output-file"></a>Ön derlenmiş üst bilgi çıkış dosyası

Oluşturulan ön derlenmiş üstbilgi dosyasının yolunu ve/veya adını belirtir. [/FP](fp-name-dot-pch-file.md)'yi ayarlar.

## <a name="cc-output-files-properties"></a>C/C++ çıkış dosyaları özellikleri

### <a name="expand-attributed-source"></a>Öznitelikli kaynağı Genişlet

Kaynak dosyasına eklenen genişletilmiş özniteliklere sahip listeleme dosyası oluşturma. [/FX](fx-merge-injected-code.md)ayarlar.

### <a name="assembler-output"></a>Derleyici çıkışı

Derleme dili çıkış dosyasının içeriğini belirtir. [/FA,/fac,/FAs,/FAcs](fa-fa-listing-file.md)ayarlar.

**Yapabileceği**

- **Listeleme yok** -liste yok.
- **Yalnızca bütünleştirilmiş kod Listeleme** -derleme kodu;. asm
- **Makine kodlu bütünleştirilmiş** kod-makine ve derleme kodu;. cod
- **Kaynak kodlu bütünleştirilmiş** kod-kaynak ve derleme kodu;. asm
- **Bütünleştirilmiş kod, makine kodu ve kaynak** derleme, makine kodu ve kaynak kodu;. cod

### <a name="use-unicode-for-assembler-listing"></a>Assembler listesi Için Unicode kullan

Çıkış dosyasının UTF-8 biçiminde oluşturulmasına neden olur.

### <a name="asm-list-location"></a>ASM liste konumu

ASM listeleme dosyasının göreli yolunu ve/veya adını belirtir; dosya veya dizin adı olabilir. [/FA](fa-fa-listing-file.md)'yi ayarlar.

### <a name="object-file-name"></a>Nesne dosyası adı

Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir; dosya veya dizin adı olabilir. [/Fo](fo-object-file-name.md)'ı ayarlar.

### <a name="program-database-file-name"></a>Program veritabanı dosya adı

Derleyici tarafından oluşturulan PDB dosyası için bir ad belirtir; Ayrıca, gerekli derleyici tarafından oluşturulan ıDB dosyası için temel adı belirtir; dosya veya dizin adı olabilir. [/FD](fd-program-database-file-name.md)ayarlar.

### <a name="generate-xml-documentation-files"></a>XML belge dosyaları oluştur

Derleyicinin XML belgesi Açıklama dosyaları (. XDC). [/Doc](doc-process-documentation-comments-c-cpp.md)ayarlar.

### <a name="xml-documentation-file-name"></a>XML belgesi dosya adı

Oluşturulan XML belgesi dosyalarının adını belirtir; dosya veya dizin adı olabilir. [/Doc:\<name >](doc-process-documentation-comments-c-cpp.md)ayarlar.

## <a name="cc-browse-information-properties"></a>C/C++ zat bilgi özellikleri

### <a name="enable-browse-information"></a>Tarama bilgilerini etkinleştir

Tarama bilgilerini etkinleştir: . Bsc dosyasındaki tarama bilgilerinin düzeyini belirtir. [/Fr](fr-fr-create-dot-sbr-file.md)'yi ayarlar.

### <a name="browse-information-file"></a>Bilgi dosyasına gözatamıyorum

Dosyaya gözatılamıyor: Tarayıcı bilgisi dosyası için isteğe bağlı ad belirtir. [/Fr\<name >](fr-fr-create-dot-sbr-file.md)ayarlar.

## <a name="cc-advanced-properties"></a>C/C++ gelişmiş özellikler

### <a name="calling-convention"></a>Çağırma Kuralı

Uygulamanız için varsayılan çağırma kuralını seçin (işlev tarafından geçersiz kılınabilir). [/GD,/gr,/GZ,/GV](gd-gr-gv-gz-calling-convention.md)ayarlar.

**Yapabileceği**

- **__cdecl** -üye işlevleri ve __stdcall veya __fastcall olarak işaretlenmiş C++ işlevler dışındaki tüm işlevler için __cdecl çağırma kuralını belirtir.
- **__fastcall** -__cdecl veya __stdcall olarak işaretlenmiş üye işlevleri ve C++ işlevler hariç tüm işlevler için __fastcall çağırma kuralını belirtir. Tüm __fastcall işlevleri prototiptürlerine sahip olmalıdır.
- **__stdcall** -üye işlevleri ve __cdecl veya __fastcall C++ olarak işaretlenmiş işlevler dışındaki tüm işlevler için __stdcall çağırma kuralını belirtir. Tüm __stdcall işlevleri prototiptürlerine sahip olmalıdır.
- **__vectorcall** -üye işlevleri ve __cdecl, __fastcall veya __stdcall olarak işaretlenmiş işlevler dışındaki C++ tüm işlevler için __vectorcall çağırma kuralını belirtir. Tüm __vectorcall işlevlerinin Prototiplerde olması gerekir.

### <a name="compile-as"></a>Farklı derle

. C ve. cpp dosyaları için derleme dil seçeneğini belirleyin. [/TC,/TP](tc-tp-tc-tp-specify-source-file-type.md)ayarlar.

**Yapabileceği**

- **Varsayılan** -varsayılan.
- **C** kodu olarak derle-c kodu olarak derleyin.
- **C++**  Kod olarak C++ derle-kod olarak derle.

### <a name="disable-specific-warnings"></a>Belirli uyarıları devre dışı bırak

İstenen uyarı numaralarını devre dışı bırakın; sayıları noktalı virgülle ayrılmış bir listeye koyun. [/WD\<NUM >](compiler-option-warning-level.md)ayarlar.

### <a name="forced-include-file"></a>Zorunlu Içerme dosyası

bir veya daha fazla zorunlu ekleme dosyası. [/FI\<ad >](fi-name-forced-include-file.md)ayarlar.

### <a name="forced-using-file"></a>Zorunlu #using dosyası

Bir veya daha fazla zorlamalı #using dosyası belirtir. [/Fu\<name >](fu-name-forced-hash-using-file.md)ayarlar.

### <a name="show-includes"></a>Eklemeleri göster

Derleyici çıkışı içeren ekleme dosyalarının bir listesini oluşturur. [/ShowIncludes](showincludes-list-include-files.md)'i ayarlar.

### <a name="use-full-paths"></a>Tam yolları kullan

Tanılama iletilerinde tam yolları kullanın. [/FC](fc-full-path-of-source-code-file-in-diagnostics.md)ayarlar.

### <a name="omit-default-library-name"></a>Varsayılan kitaplık adını atla

Varsayılan kitaplık adlarını. obj dosyalarına eklemeyin. [/Zl](zl-omit-default-library-name.md)ayarlar.

### <a name="internal-compiler-error-reporting"></a>İç derleyici hata bildirimi

İç araç hatalarının Microsoft 'a nasıl geri bildirilmesi gerektiğini belirtir.  IDE 'de varsayılan değer Prompt ' dir.  Komut satırı Derlemeleriyle varsayılan değer Queue ' dir. Ayarlar [/errorreport:\[Yöntem]] (errorreport-Report-Internal-Compiler-Errors.MD).

**Yapabileceği**

- **Rapor gönderme** -iç derleyici hataları hakkında raporlar toplanmayacak veya Microsoft 'a gönderilmez.
- **Istem hemen** , iç derleyici hatası aldığınızda rapor göndermenizi ister.
- **Sonraki oturum açma sırası** -hata raporunu sıralar. Yönetici ayrıcalıklarıyla oturum açtığınızda, bir açılır pencere görüntülenir ve en son oturum açışınızda oluşan tüm sorunları raporlayabilmeniz gerekir (her üç günde birden çok kez rapor göndermeniz istenmez). kuyruk, komut satırında bir uygulama derlenirken varsayılandır.
- **Otomatik olarak gönder** -iç derleyici hatalarının raporlarını otomatik olarak Microsoft 'a gönderir. Bu seçeneği etkinleştirmek için öncelikle Microsoft% 27s veri toplama ilkesini kabul etmelisiniz. /ErrorReport: bir bilgisayara Gönder ' i ilk kez belirttiğinizde, bir derleyici iletisi sizi Microsoft% 27s veri toplama ilkesini içeren bir Web sitesine başvuracaktır.

### <a name="treat-specific-warnings-as-errors"></a>Belirli uyarıları hata olarak değerlendir

Belirli bir derleyici uyarısını n bir derleyici uyarısında hata olarak değerlendirir.

### <a name="additional-options"></a>Ek seçenekler

Ek seçenekler.
