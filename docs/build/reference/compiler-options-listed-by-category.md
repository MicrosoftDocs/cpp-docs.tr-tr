---
title: Kategorilere Göre Listelenen Derleyici Seçenekleri
ms.date: 11/12/2018
helpviewer_keywords:
- compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
ms.openlocfilehash: d3ebfbc3661ba648c2fdb73c697db42735faf422
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62294167"
---
# <a name="compiler-options-listed-by-category"></a>Kategorilere göre listelenen derleyici seçenekleri

Bu makale derleyici seçeneklerinin Kategorik bir listesini içerir. Alfabetik liste için bkz: [seçenekleri alfabetik listelenmiş derleyici](compiler-options-listed-alphabetically.md).

## <a name="optimization"></a>İyileştirme

|Seçenek|Amaç|
|------------|-------------|
|[/ O1](o1-o2-minimize-size-maximize-speed.md)|Küçük kod oluşturur.|
|[/ O2](o1-o2-minimize-size-maximize-speed.md)|Hızlı kod oluşturur.|
|[/OB](ob-inline-function-expansion.md)|Satır içi genişlemeyi denetler.|
|[/Od](od-disable-debug.md)|İyileştirme devre dışı bırakır.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Küresel iyileştirmeleri kullanır.|
|[/Oi](oi-generate-intrinsic-functions.md)|İç işlevler üretir.|
|[/OS](os-ot-favor-small-code-favor-fast-code.md)|Küçük koda ayrıcalık tanır.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Hızlı koda ayrıcalık tanır.|
|[/Ox](ox-full-optimization.md)|Maksimum iyileştirmeyi kullanır (/ Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Çerçeve işaretçisini atlar. (yalnızca x86)|
|[/ favor](favor-optimize-for-architecture-specifics.md)|Belirli bir mimari ya da bir dizi mimari için iyileştirilmiş kod oluşturur.|

## <a name="code-generation"></a>Kod oluşturma

|Seçenek|Amaç|
|------------|-------------|
|[/ arch:](arch-x86.md)|Kod oluşturma SSE veya SSE2 yönergelerini kullanın. (yalnızca x86)|
|[/ CLR](clr-common-language-runtime-compilation.md)|Ortak dil çalışma zamanı üzerinde çalıştırılacak bir çıktı dosyası üretir.|
|[/EH](eh-exception-handling-model.md)|Özel durum işleme modelini belirtir.|
|[/ FP](fp-specify-floating-point-behavior.md)|Kayan nokta davranışını belirtir.|
|[/GA](ga-optimize-for-windows-application.md)|Windows uygulamaları için iyileştirir.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Kullanan `__cdecl` çağırma kuralı. (yalnızca x86)|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın araştırmaları etkinleştirir.|
|[/GF](gf-eliminate-duplicate-strings.md)|Dize havuzunu etkinleştirir.|
|[/GH](gh-enable-penter-hook-function.md)|Kanca işlevini çağırır `_penter`.|
|[/GH](gh-enable-pexit-hook-function.md)|Kanca işlevini çağırır `_pexit`.|
|[/GL](gl-whole-program-optimization.md)|Tüm programın iyileştirilmesini etkinleştirir.|
|[/Gm](gm-enable-minimal-rebuild.md)|Kullanım dışı. Minimum yeniden oluşturmayı etkinleştirir.|
|[GR](gr-enable-run-time-type-information.md)|Çalışma zamanı tür bilgisini (RTTI) etkinleştirir.|
|[Gr](gd-gr-gv-gz-calling-convention.md)|Kullanan `__fastcall` çağırma kuralı. (yalnızca x86)|
|[/GS](gs-buffer-security-check.md)|Tampon güvenliğini denetler.|
|[/GS](gs-control-stack-checking-calls.md)|Yığın araştırmalarını denetler.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|İş parçacığı-yerel statik depolama alanı kullanılarak yer ayrılan veri için Fiber güvenliğini destekler.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Denetim akışı koruyucusu güvenlik denetimleri ekler.|
|[/Gv](gd-gr-gv-gz-calling-convention.md)|Kullanan `__vectorcall` çağırma kuralı. (x86 ve yalnızca x64)|
|[/Gw](gw-optimize-global-data.md)|Tüm program Genel veri en iyi duruma getirme sağlar.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/Gy](gy-enable-function-level-linking.md)|Etkinleştirir işlev seviyesinde bağlamayı.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Hızlı kontrolleri etkinleştirir. (Aynı [rtc1](rtc-run-time-error-checks.md))|
|[/GZ](gd-gr-gv-gz-calling-convention.md)|Kullanan `__stdcall` çağırma kuralı. (yalnızca x86)|
|[/ homeparams](homeparams-copy-register-parameters-to-stack.md)|Yazmaçlarında işlev girişi ile birlikte kendi konumlarına yazılmasını zorlar parametreler geçildi. Bu derleyici seçeneğini yalnızca x64 için olan derleyicileri (yerel ve çapraz derleme).|
|[/ hotpatch](hotpatch-create-hotpatchable-image.md)|Bir hotpatchable görüntü oluşturur.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Hızlı transcendentals üretir.|
|[/QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Yardımcı işlevini çağrısının bastırır `_ftol` bir kayan nokta türünden bir tamsayı türüne dönüştürme zaman gereklidir. (yalnızca x86)|
|[/ Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Kaldırır `fwait` içindeki komutları `try` engeller.|
|[/ Qpar](qpar-auto-parallelizer.md)|Otomatik paralelleştirilmesini etkinleştirir.|
|[/ Qpar-report](qpar-report-auto-parallelizer-reporting-level.md)|Otomatik paralelleştirme için raporlama seviyelerini etkinleştirir.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Kayan nokta yükleme iyileştirmelerini kayan nokta değerleri ve devre dışı bırakır belirli için tamsayı taşıma yönergelerini kullanır.|
|[/Qspectre](qspectre.md)|CVE 2017-5753 için Spectre saldırı sınıfı için azaltıcı etkenleri etkinleştir.|
|[/ Qvec-report](qvec-report-auto-vectorizer-reporting-level.md)|Otomatik vektörleştirme için raporlama seviyelerini etkinleştirir.|
|[/ RTC](rtc-run-time-error-checks.md)|Çalışma zamanı hata denetimini etkinleştirir.|
|[/ volatile](volatile-volatile-keyword-interpretation.md)|Uçucu sözcüğünün nasıl yorumlanacağını seçer.|

## <a name="output-files"></a>Çıktı dosyaları

|Seçenek|Amaç|
|------------|-------------|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Belge yorumlarını bir XML dosyasına işler.|
|[/FA](fa-fa-listing-file.md)|Bir derleme listeleme dosyası oluşturur.|
|[/FA](fa-fa-listing-file.md)|Bir derleme listeleme dosyası oluşturur.|
|[/FD](fd-program-database-file-name.md)|Program veritabanı dosyası yeniden adlandırır.|
|[/FE](fe-name-exe-file.md)|Yürütülebilir dosyayı yeniden adlandırır.|
|[/FI](fi-preprocess-output-file-name.md)|Önceden işlenmiş çıkış dosyası adını belirtir.|
|[/FM](fm-name-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/FO](fo-object-file-name.md)|Bir nesne dosyası oluşturur.|
|[/ FP](fp-name-dot-pch-file.md)|Önceden derlenmiş üst bilgi dosyası adını belirtir.|
|[/ FR, /Fr](fr-fr-create-dot-sbr-file.md)|Oluşturulan .sbr tarayıcı dosyaları olarak adlandırın.|

## <a name="preprocessor"></a>Ön işlemci

|Seçenek|Amaç|
|------------|-------------|
|[/AI](ai-specify-metadata-directories.md)|Geçirilen dosya başvurularını çözümlemek için aranacak dizini belirtir [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/C](c-preserve-comments-during-preprocessing.md)|Ön işlem sırasında yorumları korur.|
|[/D](d-preprocessor-definitions.md)|Sabitleri ve makroları tanımlar.|
|[/E](e-preprocess-to-stdout.md)|Önişlemci çıktısını standart çıktıya kopyalar.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısını standart çıktıya kopyalar.|
|[/FI](fi-name-forced-include-file.md)|Belirtilen içerik dosyasını ön işlemden geçirir.|
|[/FU](fu-name-forced-hash-using-file.md)|Bu geçirilmiş gibi bir dosya adı kullanımını zorlar [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/FX](fx-merge-injected-code.md)|Eklenen kodu kaynak dosyasıyla birleştirir.|
|[/I](i-additional-include-directories.md)|Dosyaları bir dizini arar.|
|[/P](p-preprocess-to-a-file.md)|Önişlemci çıktısını bir dosyaya yazar.|
|[/U](u-u-undefine-symbols.md)|Önceden tanımlanmış makroyu kaldırır.|
|[/u](u-u-undefine-symbols.md)|Tüm ön tanımlı makroları kaldırır.|
|[/X](x-ignore-standard-include-paths.md)|Standart yoksayar içeren dizin.|

## <a name="language"></a>Dil

|Seçenek|Amaç|
|------------|-------------|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Constexpr değerlendirmesini derleme zamanında.|
|[/ OpenMP](openmp-enable-openmp-2-0-support.md)|Sağlar [#pragma omp](../../preprocessor/omp.md) kaynak kodundaki.|
|[/vd](vd-disable-construction-displacements.md)|Bastırır veya etkinleştirir gizli `vtordisp` sınıf üyeleri.|
|[/vmb](vmb-vmg-representation-method.md)|Üye işaretçileri için en iyi temel kullanır.|
|[/vmg](vmb-vmg-representation-method.md)|Üye işaretçileri için tam genellik kullanır.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Birden çok devralma bildirir.|
|[/ VMs](vmm-vms-vmv-general-purpose-representation.md)|Tek devralma bildirir.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Sanal devralma bildirir.|
|[/Z7](z7-zi-zi-debug-information-format.md)|C 7.0 uyumlu hata ayıklama bilgileri oluşturur.|
|[/Za](za-ze-disable-language-extensions.md)|C89 dil uzantılarını devre dışı bırakır.|
|[/Zc](zc-conformance.md)|Uyarınca standart davranışı belirtir [/Ze](za-ze-disable-language-extensions.md).|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. C89 dil uzantılarını etkinleştirir.|
|[/ZF](zf.md)|PDB oluşturma zamanında paralel yapılar artırır.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Düzenle ve devam et ile uyumlu bir program veritabanı'nda hata ayıklama bilgilerini içerir. (yalnızca x86)|
|[/Zi](z7-zi-zi-debug-information-format.md)|Tam hata ayıklama bilgisi üretir.|
|[/Zl](zl-omit-default-library-name.md)|Varsayılan kitaplık adını .obj dosyasından kaldırır.|
|[/ZP](zp-struct-member-alignment.md) *n*|Yapı üyelerini paketler.|
|[/ZS](zs-syntax-check-only.md)|Yalnızca söz dizimini denetler.|
|[/ZW](zw-windows-runtime-compilation.md)|Windows çalışma zamanında çalışacak bir çıktı dosyası üretir.|

## <a name="linking"></a>Bağlama

|Seçenek|Amaç|
|------------|-------------|
|[/F](f-set-stack-size.md)|Yığın boyutunu ayarlar.|
|[/LD](md-mt-ld-use-run-time-library.md)|Bir dinamik bağlantı kitaplığı oluşturur.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Hata ayıklama dinamik bağlantı kitaplığı oluşturur.|
|[/link](link-pass-options-to-linker.md)|Belirtilen seçeneği LINK'e geçirir.|
|[/LN](ln-create-msil-module.md)|Bir MSIL modülü oluşturur.|
|[/MD](md-mt-ld-use-run-time-library.md)|Bir çok iş parçacıklı DLL'yi MSVCRT.lib kullanarak oluşturmak için derler.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Bir hata ayıklama oluşturmak için derler birden çok iş parçacıklı DLL'yi MSVCRTD.lib kullanarak.|
|[/MT](md-mt-ld-use-run-time-library.md)|Bir çok iş parçacıklı yürütülebilir dosyasını LIBCMT.lib kullanarak oluşturmak için derler.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Bir hata ayıklama çok iş parçacıklı yürütülebilir dosyasını Lıbcmtd.lib kullanarak oluşturmak için derler.|

## <a name="miscellaneous"></a>Çeşitli

|Seçenek|Amaç|
|------------|-------------|
|[/?](help-compiler-command-line-help.md)|Derleme seçeneklerini listeler.|
|[@](at-specify-a-compiler-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ analyze](analyze-code-analysis.md)|Kod analizini etkinleştirir.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Bir .obj dosyasında adreslenebilir bölüm sayısı artar.|
|[/c](c-compile-without-linking.md)|Bağlanmadan derler.|
|[/ cgthreads](cgthreads-code-generation-threads.md)|En iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını belirtir.|
|[/ errorreport](errorreport-report-internal-compiler-errors.md)|Derleyici iç hatası (ICE) bilgisini doğrudan Visual C++ ekibine vermenizi sağlar.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Tanı metninde cl.exe dosyasına geçirilen kaynak kodu dosyalarının tam yolunu görüntüler.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Program veritabanı (PDB) dosyası MSPDBSRV serileştirilecek zorlar yazar. EXE.|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar.|
|[/HELP](help-compiler-command-line-help.md)|Derleme seçeneklerini listeler.|
|[/J](j-default-char-type-is-unsigned.md)|Varsayılan değişiklikleri `char` türü.|
|[/ JMC](jmc.md)|Yerel C++ Yalnızca benim kodum hata ayıklamayı destekler.|
|[/ Kernel](kernel-create-kernel-mode-binary.md)|Derleyici ve bağlayıcı Windows çekirdeğinde yürütülebilecek bir ikili oluşturur.|
|[/MP](mp-build-with-multiple-processes.md)|Aynı anda birden fazla kaynak dosyası oluşturur.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Oturum açma başlığının görüntülenmesini bastırır.|
|[/sdl](sdl-enable-additional-security-checks.md)|Ek güvenlik özelliklerini ve uyarılarını etkinleştirir.|
|[/ showıncludes](showincludes-list-include-files.md)|Bir listesini görüntüler, derleme sırasında dosyaları içerir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Bir C kaynak dosyasını belirtir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|C kaynak dosyalarının tümünü belirtir|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyasını belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyalarının tümünü olduğunu belirtir.|
|[/V](v-version-number.md)|Kullanım dışı. Sürüm dizesini ayarlar.|
|[/w](compiler-option-warning-level.md)|Tüm uyarıları devre dışı bırakır.|
|[/ W0, / W1, / W2, / W3, / W4](compiler-option-warning-level.md)|Uyarı düzeyi kümeleri çıktı.|
|[/ W1, / w2, / W3, / W4](compiler-option-warning-level.md)|Uyarı için belirtilen uyarı seviyesini ayarlar.|
|[/ Wall](compiler-option-warning-level.md)|Varsayılan olarak devre dışıdır uyarılar dahil olmak üzere tüm uyarıları etkinleştirir.|
|[/WD](compiler-option-warning-level.md)|Belirtilen uyarı devre dışı bırakır.|
|[/We](compiler-option-warning-level.md)|Belirtilen uyarı hata olarak değerlendirir.|
|[/WL TEK](wl-enable-one-line-diagnostics.md)|C++ kaynak kodunu komut satırından derlerken hata ve uyarı iletilerini tek satırlık tanılarını etkinleştirir.|
|[/Wo](compiler-option-warning-level.md)|Belirtilen uyarı yalnızca bir kez görüntüler.|
|[/Wv](compiler-option-warning-level.md)|Uyarıları derleyicinin sonraki sürümler tarafından devre dışı bırakır.|
|[/WX](compiler-option-warning-level.md)|Uyarıları hata olarak değerlendirir.|
|[/Yc](yc-create-precompiled-header-file.md)|Oluşturun. PCH dosyası.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Basamak tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zi](z7-zi-zi-debug-information-format.md) yerine.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Hata ayıklama kitaplığı oluştururken bir PCH başvurusunu ekler.|
|[/Yu](yu-use-precompiled-header-file.md)|Derleme sırasında önceden derlenmiş üst bilgi dosyası kullanır.|
|[/Y-](y-ignore-precompiled-header-options.md)|Geçerli derleme diğer tüm önceden derlenmiş üstbilgi derleyici seçeneklerini yok sayar.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.|
|[/ await](await-enable-coroutine-support.md)|Eş yordamlar (sürdürülebilir işlevler) uzantılarını etkinleştir.|
|[/ Source-Charset](source-charset-set-source-character-set.md)|Kaynak karakter kümesini Ayarla.|
|[/ Execution-Charset](execution-charset-set-execution-character-set.md)|Yürütme karakter kümesini Ayarla.|
|[/ UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Kaynak ve yürütme karakter kümesini UTF-8'e ayarlar.|
|[/ Validate-Charset](validate-charset-validate-for-compatible-characters.md)|UTF-8 dosyalarını yalnızca uyumlu karakterler için Doğrula.|
|[/ Diagnostics](diagnostics-compiler-diagnostic-options.md)|Tanılama iletilerinin biçimini denetler.|
|[/ permissive-](permissive-standards-conformance.md)|Standart uyumluluk modu olarak ayarlayın.|
|[/ Std](std-specify-language-standard-version.md)|C++ Standart sürüm uyumluluğu Seçici.|

## <a name="deprecated-and-removed-compiler-options"></a>Kullanım dışı ve kaldırılan derleyici seçenekleri

|Seçenek|Amaç|
|------------|-------------|
|[/clr:noAssembly](clr-common-language-runtime-compilation.md)|Kullanım dışı. Kullanım [/LN (MSIL modülü Oluştur)](ln-create-msil-module.md) yerine.|
|[/FR](fr-fr-create-dot-sbr-file.md)|Kullanım dışı. Gözatma bilgisi dosyası olmadan yerel değişkenler oluşturur.|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın araştırmaları etkinleştirir. Üzerinde varsayılan olarak.|
|[/Gm](gm-enable-minimal-rebuild.md)|Kullanım dışı. Minimum yeniden oluşturmayı etkinleştirir.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Hızlı kontrolleri etkinleştirir. Kullanım [rtc1](rtc-run-time-error-checks.md) yerine.|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Küresel iyileştirmeleri kullanır.|
|[/QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Kayan nokta türünden bir integral türe dönüştürme belirtmek için bir kez kullanıldı.|
|[/V](v-version-number.md)|Kullanım dışı. .Obj dosya sürüm dizesini ayarlar.|
|[/ Wp64](wp64-detect-64-bit-portability-issues.md)|Kullanımdan kalktı. 64 bitlik olasılık sorularını algılar.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Basamak tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zi](z7-zi-zi-debug-information-format.md) yerine.|
|[/Zc:forScope-](zc-forscope-force-conformance-in-for-loop-scope.md)|Kullanım dışı. Döngü kapsamında uyumluluğu devre dışı bırakır.|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantılarını etkinleştirir.|
|[/Zg](zg-generate-function-prototypes.md)|Visual C++ 2015'te kaldırıldı. İşlev prototipleri üretir.|

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
