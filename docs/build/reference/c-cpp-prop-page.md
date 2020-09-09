---
title: C/C++ proje özellikleri (Visual Studio)
description: Visual Studio Microsoft C/C++ proje özellik sayfaları özelliklerine yönelik başvuru kılavuzu.
ms.date: 09/03/2020
ms.topic: article
ms.assetid: 16375038-4917-4bd0-9a2a-26343c1708b7
ms.openlocfilehash: a96400e27b48b734d4002d9cef13fd52f9ccc7a5
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609169"
---
# <a name="cc-property-pages"></a>C/C++ Özellik sayfaları

Aşağıdaki özellik sayfaları **Proje**  >  **özellikleri**  >  **yapılandırma özellikleri**  >  **C/C++** altında bulunur:

## <a name="cc-general-properties"></a>C/C++ genel özellikleri

### <a name="additional-include-directories"></a>Ek Içerme dizinleri

Ekleme yoluna eklenecek bir veya daha fazla dizin belirtir; birden fazlaysa noktalı virgülle ayırın. Ayarlar [ `/I` (ek ekleme dizinleri)](i-additional-include-directories.md).

### <a name="additional-using-directories"></a>Ek #using dizinleri

Bir #using yönergesine geçirilen adları çözümlemek için aranacak bir veya daha fazla dizini (virgülle ayrılmış ayrı Dizin adları) belirtir. Ayarlar [`/AI`](ai-specify-metadata-directories.md) .

### <a name="debug-information-format"></a>Hata ayıklama bilgi biçimi

Derleyici tarafından oluşturulan hata ayıklama bilgilerinin türünü belirtir.  Bu özellik uyumlu bağlayıcı ayarları gerektirir. , [ `/Z7` `/Zi` , `/ZI` (Hata ayıklama bilgileri biçimi)](z7-zi-zi-debug-information-format.md)ayarlar.

#### <a name="choices"></a>Seçenekler

- **Hiçbiri** -hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlı olabilir.
- **C7 uyumlu** -programınız için oluşturulan hata ayıklama bilgileri türünü ve bu bilgilerin nesne (. obj) dosyalarında mi yoksa bir program VERITABANı (pdb) içinde tutulup tutulmadığını seçin.
- **Program veritabanı** -hata ayıklayıcı ile kullanılmak üzere tür bilgilerini ve simgesel hata ayıklama bilgilerini içeren bir program VERITABANı (pdb) oluşturur. Simgesel hata ayıklama bilgileri, değişkenlerin ve işlevlerin adlarını ve türlerini ve satır numaralarını içerir.
- **Düzenle ve devam et Için program veritabanı** -yukarıda açıklanan şekilde, [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue) özelliğini destekleyen bir biçimde bir program veritabanı oluşturur.

### <a name="support-just-my-code-debugging"></a>Yalnızca kendi kodum hata ayıklama desteği

Bu derleme biriminde [yalnızca kendi kodum](/visualstudio/debugger/just-my-code) hata ayıklamayı etkinleştirmek için destekleyici kod ekler. Ayarlar [`/JMC`](jmc.md) .

### <a name="common-language-runtime-support"></a>Ortak dil çalışma zamanı desteği

.NET çalışma zamanı hizmetini kullanın.  Bu anahtar, başka bazı anahtarlarla uyumsuzdur; [`/clr`](clr-common-language-runtime-compilation.md) Ayrıntılar için anahtarlar ailesiyle ilgili belgelere bakın.

#### <a name="choices"></a>Seçenekler

- **Ortak dil çalışma zamanı desteği yok** -ortak dil çalışma zamanı desteği yok
- **Ortak dil çalışma zamanı desteği** -uygulamanız IÇIN diğer CLR uygulamaları tarafından tüketilen meta verileri oluşturur. Ayrıca, uygulamanızın diğer CLR bileşenlerinin meta verilerinde türleri ve verileri kullanmasına izin verir.
- **Saf MSIL ortak dil çalışma zamanı desteği** -MSIL 'e derlenmiş yerel türler içerse de, yerel yürütülebilir kodu olmayan bir [MSIL](/dotnet/standard/managed-code)çıkış dosyası oluşturur.
- **GÜVENLI MSIL ortak dil çalışma zamanı desteği** -salt MSIL (yerel yürütülebilir kod içermeyen) ve doğrulanabilir çıkış dosyası oluşturur.

### <a name="consume-windows-runtime-extension"></a>Windows Çalışma Zamanı uzantısını tüketme

Windows çalışma zamanı dillerini kullanın uzantıları. Ayarlar [`/ZW`](zw-windows-runtime-compilation.md) .

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

Derleyici başlatıldığında ve derleme sırasında bilgilendirici iletileri görüntülerken oturum açma başlığının görüntülenmesini önler.

### <a name="warning-level"></a>Uyarı düzeyi

Derleyicinin kod hataları hakkında ne kadar sıkı olmasını istediğinizi seçin. Ayarlar [`/W0` - `/W4`](compiler-option-warning-level.md) .

#### <a name="choices"></a>Seçenekler

- **Tüm uyarıları** kapat-düzey 0 tüm uyarıları devre dışı bırakır.
- **Level1** -Level 1 ciddi uyarıları görüntüler. Düzey 1, komut satırındaki varsayılan uyarı düzeyidir.
- **Level2** -Level 2, 1. düzey tüm uyarıları ve uyarıları düzey 1 ' den daha az önem gösterir.
- **Level3** -Level 3, tüm düzey 2 uyarılarını ve üretim amaçları için önerilen tüm diğer uyarıları görüntüler.
- **Level4** -Level 4, tüm düzey 3 uyarılarını ve bilgilendirici uyarıları görüntüler, bu durum çoğu durumda güvenle yoksayılabilir.
- **Enablealluyarılar** -varsayılan olarak devre dışı bırakılmış olanlar da dahil olmak üzere tüm uyarıları etkinleştirilir.

### <a name="treat-warnings-as-errors"></a>Uyarıları hata olarak değerlendir

Derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için, her derlemede kullanılması en iyi yöntem olabilir [`/WX`](wx-treat-linker-warnings-as-errors.md) . Sabit-bulma kod hatalarını en aza indirmek için tüm uyarıları çözün.

### <a name="warning-version"></a>Uyarı sürümü

Derleyicinin belirli bir sürümünden sonra tanıtılan uyarıları gizleyin. Ayarlar [`/Wv:xx[.yy[.zzzzz]]`](wx-treat-linker-warnings-as-errors.md) .

### <a name="diagnostics-format"></a>Tanılama biçimi

Tanılama iletilerinde sütun bilgisi ve kaynak bağlamı ile zengin tanılamayı mümkün bir şekilde sunar.

#### <a name="choices"></a>Seçenekler

- **Şapka** -tanılama iletisinde sütun bilgilerini sağlar. Ve, ilgili kaynak kodu satırını, sorunlu sütunu gösteren bir giriş işaretine göre çıkarır.
- **Sütun bilgisi** -ek olarak, varsa, Tanılamanın verildiği satırdaki sütun numarasını da sağlar.
- **Klasik** -satır numarası ile yalnızca önceki, kısa tanılama iletilerini çıkarır.

### <a name="sdl-checks"></a>SDL denetimleri

Ek güvenlik geliştirme yaşam döngüsü (SDL) önerilen denetimler; ek güvenli kod oluşturma özelliklerini etkinleştirmeyi içerir ve hata olarak güvenlikle ilgili ek uyarıları etkinleştirir. Ayarlar [ `/sdl` , `/sdl-` ](sdl-enable-additional-security-checks.md).

### <a name="multi-processor-compilation"></a>Çok işlemcili derleme

Çok işlemcili derleme.

## <a name="cc-optimization-properties"></a>C/C++ Iyileştirme özellikleri

### <a name="optimization"></a>İyileştirme

Kod iyileştirmesi için seçenek belirleyin; belirli iyileştirme seçeneklerini kullanmak için özel ' i seçin. Ayarlar [`/Od`](od-disable-debug.md) , [ `/O1` , `/O2` ](o-options-optimize-code.md).

#### <a name="choices"></a>Seçenekler

- **Özel** -özel iyileştirme.
- **Devre dışı** -iyileştirmeyi devre dışı bırak.
- **En fazla iyileştirme (boyut kullanımı)** -eşdeğeri **`/Os /Oy /Ob2 /Gs /GF /Gy`**
- **En fazla iyileştirme (hız düzeyi)** -eşdeğeri **`/Oi /Ot /Oy /Ob2 /Gs /GF /Gy`**
- **İyileştirmeler (hıza öncelik)** -eşdeğeri **`/Oi /Ot /Oy /Ob2`**

### <a name="inline-function-expansion"></a>Satır içi Işlev genişletmesi

Yapı için [satır içi işlev](../../cpp/inline-functions-cpp.md) genişletmesinin düzeyini seçin. Ayarlar [`/Ob`](ob-inline-function-expansion.md) .

#### <a name="choices"></a>Seçenekler

- **Varsayılanını**
- **Devre dışı** -varsayılan olarak açık olan satır içi genişletmeyi devre dışı bırakır.
- **Yalnızca __inline** -yalnızca, veya olarak işaretlenen işlevleri genişletir **`inline`** **`__forceinline`** **`__inline`** . Ya da bir C++ üye işlevinde bir sınıf bildiriminde tanımlanır.
- **Herhangi bir uygun** - **`inline`** ya da **`__inline`** ve derleyicinin seçtiği diğer herhangi bir işlev olarak işaretlenen işlevleri genişletir. (Genişletme derleyicinin kararına (genellikle *Otomatik*olarak ifade edilir) oluşur.)

### <a name="enable-intrinsic-functions"></a>Iç Işlevleri etkinleştir

İç işlevleri sunar.  İç işlevleri kullanmak daha hızlı, ancak muhtemelen daha büyük bir kod üretir. Ayarlar [`/Oi`](oi-generate-intrinsic-functions.md) .

### <a name="favor-size-or-speed"></a>Boyut veya hız kullanmayı tercih edin

Kod boyutu veya kod hızının tercih edilip edilmeyeceğini belirtir; ' Genel Iyileştirme ' açık olmalıdır. Ayarlar [ `/Ot` , `/Os` ](os-ot-favor-small-code-favor-fast-code.md).

#### <a name="choices"></a>Seçenekler

- **Küçük kodu tercih** et-derleyicinin boyut hızını tercih etmek üzere karşılaştırarak, exes ve DLL 'lerin boyutunu en aza indirir.
- **Hızlı kodu tercih** et-derleyiciyi boyut hızını artırmak üzere yapılandırarak, exes ve DLL 'lerin hızını en üst düzeye çıkarır. (Bu değer varsayılandır.)
- **Hiçbiri** -boyut ve hız iyileştirmesi yoktur.

### <a name="omit-frame-pointers"></a>Çerçeve Işaretçilerini atla

Çağrı yığınında çerçeve işaretçilerinin oluşturulmasını engeller.

### <a name="enable-fiber-safe-optimizations"></a>Fiber güvenli Iyileştirmeleri etkinleştir

Lifleri görmeyin ve iş parçacığı yerel depolama erişimi kullanılırken bellek alanı iyileştirmesini sunar. Ayarlar [`/GT`](gt-support-fiber-safe-thread-local-storage.md) .

### <a name="whole-program-optimization"></a>Tüm program Iyileştirmesi

Kod oluşturmayı bağlantı zamanına erteleyerek modüller arası iyileştirmeleri sağlar. Bağlayıcı seçeneği **bağlama zamanı kodu oluşturma**gerektirir. Ayarlar [`/GL`](gl-whole-program-optimization.md) .

## <a name="cc-preprocessor-properties"></a>C/C++ Önişlemci özellikleri

### <a name="preprocessor-definitions"></a>Önişlemci tanımları

Kaynak dosyanız için ön işleme sembollerini tanımlar.

### <a name="undefine-preprocessor-definitions"></a>Önişlemci tanımlarının tanımı kaldırılıyor

Bir veya daha fazla önişlemci tarafından tanımlanabileceğini belirtir. Ayarlar [`/U`](u-u-undefine-symbols.md) .

### <a name="undefine-all-preprocessor-definitions"></a>Tüm önişlemci tanımlarının tanımlanunlarını kaldır

Önceden tanımlanmış tüm Önişlemci değerlerini tanımlayın. Ayarlar [`/u`](u-u-undefine-symbols.md) .

### <a name="ignore-standard-include-paths"></a>Standart Içerme yollarını yoksay

Derleyicinin INCLUDE ortam değişkenlerinde belirtilen dizinlerde içerme dosyalarını aramasını engeller.

### <a name="preprocess-to-a-file"></a>Bir dosyaya ön işlem

C ve C++ kaynak dosyalarını önceden işler ve önceden işlenmiş çıktıyı bir dosyaya yazar. Bu seçenek derlemeyi bastırır ve bir *`.obj`* dosya oluşturmaz.

### <a name="preprocess-suppress-line-numbers"></a>Satır numaralarını gösterme öncesi işlem

#Line yönergeleri olmadan ön işleme.

### <a name="keep-comments"></a>Açıklamaları tut

Kaynak koddan açıklama şeridinin görüntülenmesini önler; **ön işleme** seçeneklerinden en az birini ayarlamayı gerektirir. Ayarlar [`/C`](c-preserve-comments-during-preprocessing.md) .

## <a name="cc-code-generation-properties"></a>C/C++ kod üretme özellikleri

### <a name="enable-string-pooling"></a>Dize havuzunu etkinleştir

Derleyici, program görüntüsünde özdeş dizelerin yalnızca bir salt okunurdur kopyasını oluşturur. En iyi duruma getirme *dize havuzu*olarak adlandırılan küçük programlarla sonuçlanır. [ `/O1` , `/O2` ](o-options-optimize-code.md)ve [`/ZI`](z7-zi-zi-debug-information-format.md) otomatik olarak ayarla [`/GF`](gf-eliminate-duplicate-strings.md) seçeneği.

### <a name="enable-minimal-rebuild"></a>En az yeniden derlemeyi etkinleştir

, Üst bilgi dosyalarında depolanan değiştirilen C++ sınıf tanımlarını içeren C++ kaynak dosyalarının yeniden derlenip derlenmeyeceğini belirleyen en az yeniden oluşturmayı sağlar *`.h`* .

### <a name="enable-c-exceptions"></a>C++ özel durumlarını etkinleştir

Derleyici tarafından kullanılacak özel durum işleme modelini belirtir.

#### <a name="choices"></a>Seçenekler

- **SEH özel durumlarıyla Evet** -zaman uyumsuz (yapılandırılmış) ve zaman uyumlu (C++) özel durumları yakalayan özel durum işleme modeli. Ayarlar [`/EHa`](eh-exception-handling-model.md) .
- **Evet** -yalnızca c++ özel durumlarını yakalayan özel durum işleme modeli ve derleyiciye extern ' ın hiçbir şekilde bir C++ özel durumu oluşturmadığını varsaymasını söyler. Ayarlar [`/EHsc`](eh-exception-handling-model.md) .
- **, Extern c Işlevleriyle Evet** -yalnızca C++ özel durumlarını yakalayan özel durum işleme modeli ve derleyiciye dış C işlevlerinin özel durum oluşturduğunu varsaymasını söyler. Ayarlar [`/EHs`](eh-exception-handling-model.md) .
- **Hayır** -özel durum işleme yok.

### <a name="smaller-type-check"></a>Daha küçük tür denetimi

Daha küçük türlere dönüştürme için, hata ayıklama dışında herhangi bir iyileştirme türüyle uyumlu olmayan şekilde denetlemeyi etkinleştirin. Ayarlar [`/RTCc`](rtc-run-time-error-checks.md) .

### <a name="basic-runtime-checks"></a>Temel çalışma zamanı denetimleri

Hata ayıklama dışında herhangi bir iyileştirme türüyle uyumlu olmayan temel çalışma zamanı hata denetimlerini etkinleştirin. Ayarlar [ `/RTCs` , `/RTCu` , `/RTC1` ](rtc-run-time-error-checks.md).

#### <a name="choices"></a>Seçenekler

- **Yığın çerçeveleri** -yığın çerçevesi çalışma zamanı hata denetimini mümkün.
- **Başlatılmamış değişkenler** -bir değişken başlatılmadan kullanıldığında raporlar.
- **Her ikisi (/RTC1, EQUIV. to/RTCsu)** -eşdeğeri **`/RTCsu`** .
- **Varsayılan-varsayılan** çalışma zamanı denetimleri.

### <a name="runtime-library"></a>Çalışma zamanı kitaplığı

Bağlama için çalışma zamanı kitaplığını belirtin. Ayarlar,, [ `/MT` `/MTd` `/MD` , `/MDd` ](md-mt-ld-use-run-time-library.md).

#### <a name="choices"></a>Seçenekler

- **Çoklu iş parçacıklı** -uygulamanızın iş parçacığı, çalışma zamanı kitaplığının statik sürümünü kullanmasına neden olur.
- **Çok iş parçacıklı hata ayıklama** -_DEBUG ve _MT tanımlar. Bu seçenek ayrıca derleyicinin *libcmtd. lib* kitaplık adını, *`.obj`* dış sembolleri çözümlemek Için *libcmtd. lib* kullanmasını sağlayacak şekilde dosyasına yerleştirmesini sağlar.
- **Çok iş PARÇACıKLı dll** -uygulamanızın çalışma zamanı kitaplığının çoklu iş PARÇACıKLı ve DLL 'ye özgü sürümünü kullanmasına neden olur. `_MT`Ve `_DLL` derleyicisinin, *Msvcrt. lib* kitaplık adını dosyaya yerleştirmesini sağlar *`.obj`* .
- **Çok iş parçacıklı hata ayıklama DLL 'si** ,, ve ' i tanımlar ve `_DEBUG` `_MT` `_DLL` uygulamanızın çalışma zamanı kitaplığı 'NıN çoklu iş parçacığı ve DLL 'ye özgü sürümünü kullanmasını sağlar. Ayrıca derleyicinin *msvcrtd. lib* kitaplık adını dosyaya yerleştirmesini sağlar *`.obj`* .

### <a name="struct-member-alignment"></a>Struct üye hizalaması

Struct üye hizalaması için 1, 2, 4 veya 8 baytlık sınırları belirtir. Ayarlar [`/Zp`](zp-struct-member-alignment.md) .

#### <a name="choices"></a>Seçenekler

- 1 baytlık sınırlardaki **1 baytlık** paketler yapıları. Aynı **`/Zp`** .
- **2 bayt** -2 baytlık sınırlardaki yapıları paketler.
- **4 bayt** -4 baytlık sınırlardaki yapıları paketler.
- 8 **bayt** -8 baytlık sınırlar üzerinde (varsayılan) yapı paketleri.
- **16 baytlık** , 16 baytlık sınırlardaki yapı paketleri.
- **Varsayılan** hizalama ayarları.

### <a name="security-check"></a>Güvenlik denetimi

Güvenlik denetimi, bir programın güvenliği üzerinde yaygın olarak gerçekleştirilen bir saldırıya karşı yığın arabelleğinin çalıştırılmaların algılanmasına yardımcı olur.

#### <a name="choices"></a>Seçenekler

- **Güvenlik denetimini devre** dışı bırak-güvenlik denetimini devre dışı bırak. Ayarlar [`/GS-`](gs-buffer-security-check.md) .
- **Güvenlik denetimini etkinleştirin** -güvenlik denetimini etkinleştirin. Ayarlar [`/GS`](gs-buffer-security-check.md) .

### <a name="control-flow-guard"></a>Denetim Akışı Koruyucusu

Guard güvenlik denetimi, geçersiz kod bloğuna gönderim girişimlerini algılamaya yardımcı olur.

#### <a name="choices"></a>Seçenekler

- **Evet** -koruma kümeleriyle güvenlik denetimini etkinleştirin [`/guard:cf`](guard-enable-control-flow-guard.md) .
- **Hayır**

### <a name="enable-function-level-linking"></a>Işlev düzeyinde bağlamayı etkinleştir

Derleyicinin paketlenmiş işlevler (Compts) biçiminde tek tek işlevleri paketetmesine olanak tanır. Düzenle ve çalışmaya devam etmek için gereklidir. Ayarlar [`/Gy`](gy-enable-function-level-linking.md) .

### <a name="enable-parallel-code-generation"></a>Paralel kod oluşturmayı etkinleştir

Derleyicinin, iyileştirme etkinleştirildiğinde kullanılarak tanımlanan döngüler için paralel kod oluşturmasını sağlar `#pragma loop(hint_parallel[(n)])` .

### <a name="enable-enhanced-instruction-set"></a>Gelişmiş yönerge kümesini etkinleştir

Gelişmiş yönerge kümelerini destekleyen işlemcilerde bulunan yönergelerin kullanımını etkinleştirin. Örneğin, SSE, SSE2, AVX ve AVX2 geliştirmeleri IA-32 ' a yöneliktir. Ve, AVX ve AVX2 geliştirmeleri x64 ile yapılır. Şu anda **`/arch:SSE`** ve **`/arch:SSE2`** yalnızca x86 mimarisi için oluşturulurken kullanılabilir. Hiçbir seçenek belirtilmemişse, derleyici SSE2 destekleyen işlemcilerde bulunan yönergeleri kullanır. Gelişmiş yönergelerin kullanımı ile devre dışı bırakılabilir **`/arch:IA32`** . Daha fazla bilgi için bkz [`/arch (x86)`](arch-x86.md) [`/arch (x64)`](arch-x64.md) ., ve [`/arch (ARM)`](arch-arm.md) .

#### <a name="choices"></a>Seçenekler

- **Streaming SIMD Extensions** Streaming SIMD Extensions. Yapar  **`/arch:SSE`**
- **Streaming SIMD Extensions 2** -Streaming SIMD Extensions 2. Yapar  **`/arch:SSE2`**
- **Gelişmiş vektör Uzantıları** -gelişmiş vektör uzantıları. Yapar  **`/arch:AVX`**
- **Gelişmiş vektör uzantıları 2** -gelişmiş vektör uzantıları 2. Yapar  **`/arch:AVX2`**
- **Gelişmiş yönerge yok** -gelişmiş yönerge yok. Yapar  **`/arch:IA32`**
- **Ayarlanmadı** -ayarlanmadı.

### <a name="floating-point-model"></a>Kayan nokta modeli

Kayan nokta modelini ayarlar. Ayarlar [ `/fp:precise` , `/fp:strict` , `/fp:fast` ](fp-specify-floating-point-behavior.md).

#### <a name="choices"></a>Seçenekler

- **Kesin** -varsayılan. Eşitlik ve eşitsizlik için kayan nokta testlerinin tutarlılığını geliştirir.
- **Strict** -en katı kayan nokta modeli. **`/fp:strict`****`fp_contract`** kapalı ve açık olmasına neden olur **`fenv_access`** . **`/fp:except`** açık ve açıkça belirtilerek devre dışı bırakılabilir **`/fp:except-`** . İle birlikte kullanıldığında **`/fp:except-`** , **`/fp:strict`** kesin kayan nokta semantiğini uygular, ancak olağanüstü olaylar için dikkate almadan.
- **Hızlı** -çoğu durumda en hızlı kodu oluşturur.

### <a name="enable-floating-point-exceptions"></a>Kayan nokta özel durumlarını etkinleştir

Güvenilir kayan nokta özel durumu modeli. Özel durumlar, tetiklendikten hemen sonra oluşturulur. Ayarlar [`/fp:except`](fp-specify-floating-point-behavior.md) .

### <a name="create-hotpatchable-image"></a>Düzeltme eki eklenebilir görüntü oluşturma

Anında Düzeltme açık olduğunda, derleyici, her işlevin ilk yönergesinin, sık yama için gereken iki bayt olmasını sağlar. Ayarlar [`/hotpatch`](hotpatch-create-hotpatchable-image.md) .

### <a name="spectre-mitigation"></a>Spectre azaltma

CVE 2017-5753 için Spectre azaltmaları. Ayarlar [`/Qspectre`](qspectre.md) .

#### <a name="choices"></a>Seçenekler

- **Etkin** -CVE 2017-5753 için Spectre azaltma özelliğini etkinleştir
- **Devre dışı** -ayarlı değil.

## <a name="cc-language-properties"></a>C/C++ dil özellikleri

### <a name="disable-language-extensions"></a>Dil uzantılarını devre dışı bırak

Dil uzantılarını bastırır veya izin vermez. Ayarlar [`/Za`](za-ze-disable-language-extensions.md) .

### <a name="conformance-mode"></a>Uyumluluk modu

Uygunluk modunu etkinleştirilir veya gizler. Ayarlar [`/permissive-`](permissive-standards-conformance.md) .

### <a name="treat-wchar_t-as-built-in-type"></a>Wchar_t yerleşik tür olarak değerlendir

Belirtildiğinde, türü **`wchar_t`** ile eşleyen yerel bir tür olur **`__wchar_t`** **`short`** **`__int16`** . [`/Zc:wchar_t`](zc-wchar-t-wchar-t-is-native-type.md) Varsayılan olarak açık olur.

### <a name="force-conformance-in-for-loop-scope"></a>Döngü kapsamında uygunluğu zorla

, `for` Microsoft uzantılarına sahip deyimlere yönelik standart C++ davranışını uygular. Ayarlar [ `/Za` , `/Ze` (dil uzantılarını devre dışı bırakır](za-ze-disable-language-extensions.md). [`/Zc:forScope`](zc-forscope-force-conformance-in-for-loop-scope.md) Varsayılan olarak açık olur.

### <a name="remove-unreferenced-code-and-data"></a>Başvurulmayan kod ve verileri Kaldır

Belirtildiğinde, derleyici artık başvurulmayan kod ve veriler için sembol bilgisi oluşturmaz.

### <a name="enforce-type-conversion-rules"></a>Tür dönüştürme kurallarını zorlama

Bir rvalue başvuru türünü C++ 11 standardına göre bir dönüştürme işleminin sonucu olarak belirlemek için kullanılır.

### <a name="enable-run-time-type-information"></a>Çalışma zamanı türü bilgilerini etkinleştir

Çalışma zamanında C++ nesne türlerini denetlemek için kod ekler (*çalışma zamanı türü bilgileri*veya RTTI). Ayarlar [ `/GR` , `/GR-` ](gr-enable-run-time-type-information.md).

### <a name="open-mp-support"></a>MP desteğini açın

OpenMP 2,0 dil uzantılarını etkinleştirilir. Ayarlar [`/openmp`](openmp-enable-openmp-2-0-support.md) .

### <a name="c-language-standard"></a>C++ dil standardı

Derleyicinin izin aldığı C++ dil standardını belirler. Mümkün olduğunda en son sürümü kullanın. Ayarlar [ `/std:c++14` , `/std:c++17` , `/std:c++latest` ](std-specify-language-standard-version.md).

#### <a name="choices"></a>Seçenekler

- **Varsayılanını**
- **ISO C++ 14 standart**
- **ISO C++ 17 Standart**
- **Önizleme-en son C++ çalışma taslağındaki Özellikler**

### <a name="enable-c-modules-experimental"></a>C++ modüllerini etkinleştir (deneysel)

C++ modülleri TS ve standart kitaplık modülleri için deneysel destek.

## <a name="cc-precompiled-headers-properties"></a>C/C++ ön derlenmiş üst bilgi özellikleri

### <a name="createuse-precompiled-header"></a>Önceden derlenmiş üst bilgi oluştur/kullan

Derleme sırasında önceden derlenmiş üst bilgi oluşturmayı veya kullanmayı mümkün. Ayarlar [`/Yc`](yc-create-precompiled-header-file.md) , [`/Yu`](yu-use-precompiled-header-file.md) .

#### <a name="choices"></a>Seçenekler

- **Create** -derleyicinin *`.pch`* belirli bir noktada derlemenin durumunu temsil eden ön derlenmiş üst bilgi () dosyası oluşturmasını söyler.
- **Use** -derleyiciye geçerli derlemede mevcut bir önceden derlenmiş üst bilgi ( *`.pch`* ) dosyası kullanmasını söyler.
- Önceden derlenmiş **üst bilgiler kullanılmıyor-önceden** derlenmiş üst bilgiler kullanmıyor.

### <a name="precompiled-header-file"></a>Önceden derlenmiş üst bilgi dosyası

Önceden derlenmiş bir üstbilgi dosyası oluştururken veya kullanılırken kullanılacak üst bilgi dosyası adını belirtir. Ayarlar [`/Yc`](yc-create-precompiled-header-file.md) , [`/Yu`](yu-use-precompiled-header-file.md) .

### <a name="precompiled-header-output-file"></a>Ön derlenmiş üst bilgi çıkış dosyası

Oluşturulan ön derlenmiş üstbilgi dosyasının yolunu veya adını belirtir. Ayarlar [`/Fp`](fp-name-dot-pch-file.md) .

## <a name="cc-output-files-properties"></a>C/C++ çıkış dosyaları özellikleri

### <a name="expand-attributed-source"></a>Öznitelikli kaynağı Genişlet

Kaynak dosyasına eklenen genişletilmiş özniteliklere sahip listeleme dosyası oluşturma. Ayarlar [`/Fx`](fx-merge-injected-code.md) .

### <a name="assembler-output"></a>Derleyici çıkışı

Derleme dili çıkış dosyasının içeriğini belirtir. Ayarlar,, [ `/FA` `/FAc` `/FAs` , `/FAcs` ](fa-fa-listing-file.md).

#### <a name="choices"></a>Seçenekler

- **Listeleme yok** -liste yok.
- **Yalnızca bütünleştirilmiş kod Listeleme** -derleme kodu; *`.asm`*
- **Makine kodlu bütünleştirilmiş** kod-makine ve derleme kodu; *`.cod`*
- **Kaynak kodlu bütünleştirilmiş** kod-kaynak ve derleme kodu; *`.asm`*
- **Bütünleştirilmiş kod, makine kodu ve kaynak** derleme, makine kodu ve kaynak kodu; *`.cod`*

### <a name="use-unicode-for-assembler-listing"></a>Assembler listesi Için Unicode kullan

Çıkış dosyasının UTF-8 biçiminde oluşturulmasına neden olur.

### <a name="asm-list-location"></a>ASM liste konumu

ASM listeleme dosyası için göreli yolu veya adı belirtir; dosya veya dizin adı olabilir. Ayarlar [`/Fa`](fa-fa-listing-file.md) .

### <a name="object-file-name"></a>Nesne dosyası adı

Varsayılan nesne dosyası adını geçersiz kılacak bir ad belirtir; dosya veya dizin adı olabilir. Ayarlar [`/Fo`](fo-object-file-name.md) .

### <a name="program-database-file-name"></a>Program veritabanı dosya adı

Derleyici tarafından oluşturulan PDB dosyası için bir ad belirtir; Ayrıca, gerekli derleyici tarafından oluşturulan ıDB dosyası için temel adı belirtir; dosya veya dizin adı olabilir. Ayarlar [`/Fd`](fd-program-database-file-name.md) .

### <a name="generate-xml-documentation-files"></a>XML belge dosyaları oluştur

Derleyicinin XML belgesi Açıklama dosyaları (. XDC). Ayarlar [`/doc`](doc-process-documentation-comments-c-cpp.md) .

### <a name="xml-documentation-file-name"></a>XML belgesi dosya adı

Oluşturulan XML belgesi dosyalarının adını belirtir; dosya veya dizin adı olabilir. Ayarlar [`/doc:`\<name>](doc-process-documentation-comments-c-cpp.md) .

## <a name="cc-browse-information-properties"></a>C/C++ tarayıcı bilgileri özellikleri

### <a name="enable-browse-information"></a>Tarama bilgilerini etkinleştir

Dosyadaki tarama bilgilerinin düzeyini belirtir *`.bsc`* . Ayarlar [`/FR`](fr-fr-create-dot-sbr-file.md) .

### <a name="browse-information-file"></a>Bilgi dosyasına gözatamıyorum

Tarayıcı bilgisi dosyası için isteğe bağlı ad belirtir. Ayarlar [`/FR`\<name>](fr-fr-create-dot-sbr-file.md) .

## <a name="cc-advanced-properties"></a>C/C++ Gelişmiş özellikleri

### <a name="calling-convention"></a>Çağırma Kuralı

Uygulamanız için varsayılan çağırma kuralını seçin (işlev tarafından geçersiz kılınabilir). Ayarlar,, [ `/Gd` `/Gr` `/Gz` , `/Gv` ](gd-gr-gv-gz-calling-convention.md).

#### <a name="choices"></a>Seçenekler

- **`__cdecl`** - **`__cdecl`** C++ üye işlevleri ve veya olarak işaretli işlevler hariç tüm işlevler için çağrı kuralını **`__stdcall`** belirtir **`__fastcall`** .
- **`__fastcall`** - **`__fastcall`** C++ üye işlevleri ve veya olarak işaretli işlevler hariç tüm işlevler için çağrı kuralını **`__cdecl`** belirtir **`__stdcall`** . Tüm **`__fastcall`** işlevlerin Prototiplerde olması gerekir.
- **`__stdcall`** - **`__stdcall`** C++ üye işlevleri ve veya olarak işaretli işlevler hariç tüm işlevler için çağrı kuralını **`__cdecl`** belirtir **`__fastcall`** . Tüm **`__stdcall`** işlevlerin Prototiplerde olması gerekir.
- **`__vectorcall`** - **`__vectorcall`** C++ üye işlevleri ve, veya olarak işaretli işlevler hariç tüm işlevler için çağırma kuralını belirtir **`__cdecl`** **`__fastcall`** **`__stdcall`** . Tüm **`__vectorcall`** işlevlerin Prototiplerde olması gerekir.

### <a name="compile-as"></a>Farklı derle

Ve dosyaları için derleme dil seçeneğini belirleyin *`.c`* *`.cpp`* . Ayarlar [ `/TC` , `/TP` ](tc-tp-tc-tp-specify-source-file-type.md).

#### <a name="choices"></a>Seçenekler

- **Varsayılan** -varsayılan.
- **C** kodu olarak derle-c kodu olarak derleyin.
- **C++ kodu olarak derle** -c++ kodu olarak derleyin.

### <a name="disable-specific-warnings"></a>Belirli uyarıları devre dışı bırak

Belirtilen uyarı numaralarını devre dışı bırakın. Uyarı numaralarını noktalı virgülle ayrılmış bir listeye koyun. Ayarlar [`/wd`\<number>](compiler-option-warning-level.md) .

### <a name="forced-include-file"></a>Zorunlu Içerme dosyası

bir veya daha fazla zorunlu ekleme dosyası. Ayarlar [`/FI`\<name>](fi-name-forced-include-file.md) .

### <a name="forced-using-file"></a>Zorunlu #using dosyası

Bir veya daha fazla zorlamalı #using dosyası belirtir. Ayarlar [`/FU`\<name>](fu-name-forced-hash-using-file.md) .

### <a name="show-includes"></a>Eklemeleri göster

Derleyici çıkışı içeren ekleme dosyalarının bir listesini oluşturur. Ayarlar [`/showIncludes`](showincludes-list-include-files.md) .

### <a name="use-full-paths"></a>Tam yolları kullan

Tanılama iletilerinde tam yolları kullanın. Ayarlar [`/FC`](fc-full-path-of-source-code-file-in-diagnostics.md) .

### <a name="omit-default-library-name"></a>Varsayılan kitaplık adını atla

, Dosyalarda varsayılan kitaplık adlarını içermez *`.obj`* . Ayarlar [`/Zl`](zl-omit-default-library-name.md) .

### <a name="internal-compiler-error-reporting"></a>İç derleyici hata bildirimi

> [!NOTE]
> Bu seçenek kullanım dışıdır. Windows Vista 'Dan başlayarak hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir.

### <a name="treat-specific-warnings-as-errors"></a>Belirli uyarıları hata olarak değerlendir

Belirli bir derleyici uyarısını n bir derleyici uyarısında hata olarak değerlendirir.

### <a name="additional-options"></a>Ek Seçenekler

Ek seçenekler.
