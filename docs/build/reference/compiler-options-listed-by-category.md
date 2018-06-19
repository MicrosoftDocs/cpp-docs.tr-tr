---
title: Kategoriye göre listelenen derleyici seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fff661bf573ca30a5b0e7550c2e53b00a7ff3d8f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379334"
---
# <a name="compiler-options-listed-by-category"></a>Kategoriye göre listelenen derleyici seçenekleri

Bu makalede kategorik derleyici seçenekleri listesini içerir. Alfabetik bir listesi için bkz: [seçenekleri alfabetik listelenmiş derleyici](compiler-options-listed-alphabetically.md).

### <a name="optimization"></a>En iyi duruma getirme

|Seçenek|Amaç|
|------------|-------------|
|[/ O1](o1-o2-minimize-size-maximize-speed.md)|Küçük kod oluşturur.|
|[/ O2](o1-o2-minimize-size-maximize-speed.md)|Hızlı kod oluşturur.|
|[/OB](ob-inline-function-expansion.md)|Satır içi genişletme denetler.|
|[/Od](od-disable-debug.md)|En iyi duruma getirme devre dışı bırakır.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Global iyileştirmeler kullanır.|
|[/Oi](oi-generate-intrinsic-functions.md)|İç işlevler oluşturur.|
|[/OS](os-ot-favor-small-code-favor-fast-code.md)|Küçük kod korur.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Favors kod hızlı.|
|[/Ox](ox-full-optimization.md)|En fazla iyileştirme kullanır (/ Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Çerçeve işaretçisi atlar. (yalnızca x86)|
|[/ favor](favor-optimize-for-architecture-specifics.md)|Belirtilen bir mimari için veya bir dizi mimarileri için iyileştirilmiş kodu oluşturur.|

### <a name="code-generation"></a>Kod oluşturma

|Seçenek|Amaç|
|------------|-------------|
|[/ arch](arch-x86.md)|Kod oluşturma SSE veya SSE2 yönergeleri kullanın. (yalnızca x86)|
|[/ CLR](clr-common-language-runtime-compilation.md)|Ortak dil çalışma zamanı üzerinde çalıştırmak için bir çıktı dosyası oluşturur.|
|[/EH](eh-exception-handling-model.md)|Özel durum işleme modeli belirtir.|
|[/FP](fp-specify-floating-point-behavior.md)|Kayan nokta davranışını belirtir.|
|[/GA](ga-optimize-for-windows-application.md)|Windows uygulamaları için en iyi duruma getirir.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Kullanan `__cdecl` çağırma. (yalnızca x86)|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın yoklamalarını etkinleştirir.|
|[/GF](gf-eliminate-duplicate-strings.md)|Etkinleştirir dize havuzu.|
|[/GH](gh-enable-penter-hook-function.md)|Çağrıları kanca işlevi `_penter`.|
|[/GH](gh-enable-pexit-hook-function.md)|Çağrıları kanca işlevi `_pexit`.|
|[/GL](gl-whole-program-optimization.md)|Bütün program iyileştirmesi sağlar.|
|[/Gm](gm-enable-minimal-rebuild.md)|En az etkinleştirir yeniden oluşturun.|
|[/GR](gr-enable-run-time-type-information.md)|Çalışma zamanı türü bilgileri (RTTI) sağlar.|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Kullanan `__fastcall` çağırma. (yalnızca x86)|
|[/GS](gs-buffer-security-check.md)|Güvenlik denetimleri arabellek.|
|[/GS](gs-control-stack-checking-calls.md)|Denetimleri yığın yoklamaları.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Statik iş parçacığı yerel depolama kullanarak ayrılan veriler için Fiber güvenliği destekler.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Denetim akışı koruyucu güvenlik denetimlerini ekler.|
|[/ GV](gd-gr-gv-gz-calling-convention.md)|Kullanan `__vectorcall` çağırma. (x86 hem yalnızca x64)|
|[/GW](gw-optimize-global-data.md)|Genel veri bütün program iyileştirmesi sağlar.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/Gy](gy-enable-function-level-linking.md)|Etkinleştirir işlev bağlama düzeyi.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Etkinleştirir denetimleri hızlı. (Aynı [/RTC1](rtc-run-time-error-checks.md))|
|[/GZ](gd-gr-gv-gz-calling-convention.md)|Kullanan `__stdcall` çağırma. (yalnızca x86)|
|[/ homeparams](homeparams-copy-register-parameters-to-stack.md)|İşlevi girişte yığında konumlarına yazılacak yazmaçlar zorlar parametre geçirildi. Yalnızca Bu derleyici seçeneği olan [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyicileri (yerel ve derleme).|
|[/ hotpatch](hotpatch-create-hotpatchable-image.md)|Bir düzeltme eki eklenebilen görüntü oluşturur.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Hızlı soyutları oluşturur.|
|[QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Yardımcı işlevi çağrısı bastırır `_ftol` bir kayan nokta türüne dönüştürme tamsayı türü için ne zaman gereklidir. (yalnızca x86)|
|[/ Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Kaldırır `fwait` içindeki komutları `try` engeller.|
|[/ Qpar](qpar-auto-parallelizer.md)|Otomatik paralelleştirme döngüsü sağlar.|
|[/ Qpar-rapor](qpar-report-auto-parallelizer-reporting-level.md)|Otomatik paralelleştirme düzeylerini raporlama etkinleştirir.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Kayan nokta değerlerini ve devre dışı bırakır belirli için kullandığı tamsayı taşıma yönergeleri noktası yük iyileştirmeler kayan.|
|[/Qspectre](qspectre.md)|CVE 2017-5753, bir sınıf Spectre saldırıları için bunları azaltmanın yollarını etkinleştirin.|
|[/ Qvec-report](qvec-report-auto-vectorizer-reporting-level.md)|Otomatik vectorization düzeylerini raporlama etkinleştirir.|
|[/ RTC](rtc-run-time-error-checks.md)|Çalışma zamanı hata denetimini etkinleştirir.|
|[/ volatile](volatile-volatile-keyword-interpretation.md)|Volatile anahtar sözcüğü nasıl yorumlanacağını seçer.|

### <a name="output-files"></a>Çıkış dosyaları

|Seçenek|Amaç|
|------------|-------------|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Belge açıklamaları bir XML dosyasına işler.|
|[/FA](fa-fa-listing-file.md)|Bir derleme listeleme dosyası yapılandırır.|
|[/FA](fa-fa-listing-file.md)|Bir derleme listeleme dosyası oluşturur.|
|[/FD](fd-program-database-file-name.md)|Program veritabanı dosyayı yeniden adlandırır.|
|[/FE](fe-name-exe-file.md)|Yürütülebilir dosyayı yeniden adlandırır.|
|[/FI](fi-preprocess-output-file-name.md)|Önceden işlenmiş çıktı dosyası adını belirtir.|
|[/FM](fm-name-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/FO](fo-object-file-name.md)|Bir nesne dosyası oluşturur.|
|[/FP](fp-name-dot-pch-file.md)|Önceden derlenmiş üst bilgi dosyası adını belirtir.|
|[/ FR, /Fr](fr-fr-create-dot-sbr-file.md)|.Sbr tarayıcı dosyaları oluşturulan ad.|

### <a name="preprocessor"></a>Ön işlemci

|Seçenek|Amaç|
|------------|-------------|
|[/AI](ai-specify-metadata-directories.md)|Bir dizin dosyası başvuruları geçirilen çözümlemek için aranacak belirtir [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/C](c-preserve-comments-during-preprocessing.md)|Ön işleme sırasında açıklamaları korur.|
|[/D](d-preprocessor-definitions.md)|Sabitler ve makroları tanımlar.|
|[/E](e-preprocess-to-stdout.md)|Önişlemci çıktısı için standart çıktı kopyalar.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısı için standart çıktı kopyalar.|
|[/FI](fi-name-forced-include-file.md)|Belirtilen içerme dosyası preprocesses.|
|[/FU](fu-name-forced-hash-using-file.md)|Bir dosya adı kullanımı için geçildikten gibi zorlar [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/FX](fx-merge-injected-code.md)|Kaynak dosya ile eklenen kodu birleştirme.|
|[/I](i-additional-include-directories.md)|İçerme dosyaları için bir dizin arar.|
|[/P](p-preprocess-to-a-file.md)|Önişlemci çıktısı bir dosyaya yazar.|
|[/U](u-u-undefine-symbols.md)|Önceden tanımlanmış makrosu kaldırır.|
|[/u](u-u-undefine-symbols.md)|Tüm önceden tanımlı makrolar kaldırır.|
|[/X](x-ignore-standard-include-paths.md)|Standart yoksayar dizini içerir.|

### <a name="language"></a>Dil

|Seçenek|Amaç|
|------------|-------------|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Derleme zamanında constexpr değerlendirme denetler.|
|[/ OpenMP](openmp-enable-openmp-2-0-support.md)|Etkinleştirir [#pragma omp](../../preprocessor/omp.md) kaynak kodunda.|
|[/vd](vd-disable-construction-displacements.md)|Gizler veya etkinleştirir gizli `vtordisp` sınıfı üyeleri.|
|[/vmb](vmb-vmg-representation-method.md)|Üye işaretçileri için en iyi temel kullanır.|
|[/vmg](vmb-vmg-representation-method.md)|Kullandığı tam sayılanların genel üyeleri işaretçileri için.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Birden çok devralma bildirir.|
|[/ VMs](vmm-vms-vmv-general-purpose-representation.md)|Tek devralma bildirir.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Sanal devralma bildirir.|
|[/Z7](z7-zi-zi-debug-information-format.md)|C 7.0 uyumlu hata ayıklama bilgisi oluşturur.|
|[/Za](za-ze-disable-language-extensions.md)|Dil uzantılarını devre dışı bırakır.|
|[/Zc](zc-conformance.md)|Standart davranışını altında belirten [/Ze](za-ze-disable-language-extensions.md).|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantıları sağlar.|
|[/ZF](zf.md)|PDB oluşturma zamanı paralel derlemelerde artırır.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Düzenle ve devam et ile uyumlu bir program veritabanında hata ayıklama bilgilerini içerir. (yalnızca x86)|
|[/Zi](z7-zi-zi-debug-information-format.md)|Tam hata ayıklama bilgisi oluşturur.|
|[/Zl](zl-omit-default-library-name.md)|Varsayılan kitaplık adını .obj dosyasından kaldırır.|
|[/ZP](zp-struct-member-alignment.md) *n*|Paketleri üyeleri yapılandırın.|
|[/ZS](zs-syntax-check-only.md)|Yalnızca sözdizimi denetler.|
|[/ZW](zw-windows-runtime-compilation.md)|Windows çalışma zamanı'çalıştırmak için bir çıktı dosyası oluşturur.|

### <a name="linking"></a>Bağlama

|Seçenek|Amaç|
|------------|-------------|
|[/F](f-set-stack-size.md)|Ayarlar boyutu yığın.|
|[/LD](md-mt-ld-use-run-time-library.md)|Bir dinamik bağlantı kitaplığı oluşturur.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Hata ayıklama dinamik bağlantı kitaplığı oluşturur.|
|[/link](link-pass-options-to-linker.md)|Belirtilen seçenek bağlantı geçirir.|
|[/LN](ln-create-msil-module.md)|MSIL modülü oluşturur.|
|[/MD](md-mt-ld-use-run-time-library.md)|Birden çok iş parçacıklı DLL MSVCRT.lib kullanarak oluşturmak için derler.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Bir hata ayıklama oluşturmak için derlerken MSVCRTD.lib kullanarak birden çok iş parçacıklı DLL.|
|[/MT](md-mt-ld-use-run-time-library.md)|LIBCMT.lib kullanarak birden çok iş parçacıklı bir yürütülebilir dosya oluşturmak için derler.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Hata ayıklama birden çok iş parçacıklı yürütülebilir dosyası, LIBCMTD.lib kullanarak oluşturmak için derler.|

### <a name="miscellaneous"></a>Çeşitli

|Seçenek|Amaç|
|------------|-------------|
|[/?](help-compiler-command-line-help.md)|Derleyici seçenekleri listeler.|
|[@](at-specify-a-compiler-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ analyze](analyze-code-analysis.md)|Kod çözümlemesi sağlar.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|.Obj dosyasında adreslenebilir bölümlerini sayısını artırır.|
|[/c](c-compile-without-linking.md)|Bağlantılandırmadan derler.|
|[/ cgthreads](cgthreads-code-generation-threads.md)|En iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını belirtir.|
|[/ errorreport](errorreport-report-internal-compiler-errors.md)|Derleyici iç hatası (çok) bilgileri doğrudan Visual C++ ekip vermenizi sağlar.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Kaynak kodu dosyaları için cl.exe tanılama metinde geçirilen tam yolunu görüntüler.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Zorlar MSPDBSRV serileştirilmesi için program veritabanı (PDB) dosyasına yazar. EXE.|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (Genel) adların uzunluğunu kısıtlar.|
|[/HELP](help-compiler-command-line-help.md)|Derleyici seçenekleri listeler.|
|[/J](j-default-char-type-is-unsigned.md)|Varsayılan değişiklikleri `char` türü.|
|[/ Kernel](kernel-create-kernel-mode-binary.md)|Derleyicide ve bağlayıcıda Windows Çekirdeği'nde yürütülebilir bir ikili oluşturur.|
|[/MP](mp-build-with-multiple-processes.md)|Aynı anda birden çok kaynak dosyaları oluşturur.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Oturum açma başlık görüntülenmesini engeller.|
|[/ SDL](sdl-enable-additional-security-checks.md)|Ek güvenlik özellikleri ve uyarılar sağlar.|
|[/ showıncludes](showincludes-list-include-files.md)|Tüm listesini görüntüler derleme sırasında dosyaları içerir.|
|[TP](tc-tp-tc-tp-specify-source-file-type.md)|Bir C kaynak dosyasını belirtir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|C. tüm kaynak dosyaların belirtir|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyasını belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Tüm kaynak dosyaların C++ belirtir.|
|[/V](v-version-number.md)|Kullanım dışı. Sürüm dizesi ayarlar.|
|[/w](compiler-option-warning-level.md)|Tüm uyarıları devre dışı bırakır.|
|[/ W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Ayarlar uyarı düzeyi çıktı.|
|[/W1, /w2, /w3, /w4](compiler-option-warning-level.md)|Belirtilen uyarı düzeyini uyarı ayarlar.|
|[/ Wall](compiler-option-warning-level.md)|Varsayılan olarak devre dışıdır uyarılar dahil olmak üzere tüm uyarıları sağlar.|
|[/WD](compiler-option-warning-level.md)|Belirtilen uyarı devre dışı bırakır.|
|[/We](compiler-option-warning-level.md)|Belirtilen uyarıyı hata olarak değerlendirir.|
|[/WL](wl-enable-one-line-diagnostics.md)|C++ kaynak kodu komut satırından derlerken hata ve uyarı iletileri için tek satır tanılamayı sağlar.|
|[/Wo](compiler-option-warning-level.md)|Belirtilen uyarı yalnızca bir kez görüntüler.|
|[/Wv](compiler-option-warning-level.md)|Sonraki derleyici sürümler tarafından sunulan uyarılarını devre dışı bırakır.|
|[/WX](compiler-option-warning-level.md)|Uyarıları hata olarak değerlendirir.|
|[/Yc](yc-create-precompiled-header-file.md)|Oluşturun. PCH dosyası.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Yerler tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zı](z7-zi-zi-debug-information-format.md) yerine.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Hata ayıklama kitaplığı oluştururken PCH başvurusu yerleştirir.|
|[/Yu](yu-use-precompiled-header-file.md)|Önceden derlenmiş üst bilgi dosyasını sırasında derleme kullanır.|
|[/Y-](y-ignore-precompiled-header-options.md)|Diğer tüm önceden derlenmiş üstbilgi derleyici seçenekleri geçerli derlemede yok sayar.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.|
|[/ bekleme](await-enable-coroutine-support.md)|Eş yordamlar (sürdürülebilir işlevler) uzantıları sağlar.|
|[/Source-Charset](source-charset-set-source-character-set.md)|Küme kaynak karakter kümesi.|
|[/Execution-Charset](execution-charset-set-execution-character-set.md)|Set yürütme karakter kümesi.|
|[/UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Kaynak ve yürütme karakter kümesi UTF-8'e ayarlar.|
|[/Validate-Charset](validate-charset-validate-for-compatible-characters.md)|Yalnızca uyumlu karakterler için UTF-8 dosyaları doğrulayın.|
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Tanılama iletileri biçimini denetler.|
|[/ izin veren-](permissive-standards-conformance.md)|Standart Uyumluluk modunu ayarlayın.|
|[/Std](std-specify-language-standard-version.md)|C++ Standart sürümünü uyumluluk Seçici.|

### <a name="deprecated-and-removed-compiler-options"></a>Kullanım dışı ve kaldırılan derleyici seçenekleri

|Seçenek|Amaç|
|------------|-------------|
|[/clr:noAssembly](clr-common-language-runtime-compilation.md)|Kullanım dışı. Kullanım [/LN (MSIL modülü Oluştur)](ln-create-msil-module.md) yerine.|
|[/FR](fr-fr-create-dot-sbr-file.md)|Kullanım dışı. Yerel değişkenler olmadan gözatma bilgileri dosyası oluşturur.|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın yoklamalarını etkinleştirir. Üzerinde varsayılan olarak.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Etkinleştirir denetimleri hızlı. Kullanım [/RTC1](rtc-run-time-error-checks.md) yerine.|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (Genel) adların uzunluğunu kısıtlar.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Global iyileştirmeler kullanır.|
|[QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Kayan nokta türünden bir tam sayı türüne dönüştürmek nasıl belirtmek için bir kez kullanılır.|
|[/V](v-version-number.md)|Kullanım dışı. .Obj dosya sürümü dizesini ayarlar.|
|[/ Wp64](wp64-detect-64-bit-portability-issues.md)|Kullanımdan kalktı. 64 bit taşınabilirlik sorunları algılar.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Yerler tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zı](z7-zi-zi-debug-information-format.md) yerine.|
|[/ZC:forScope-](zc-forscope-force-conformance-in-for-loop-scope.md)|Kullanım dışı. Döngü kapsamında uyumluluğu devre dışı bırakır.|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantıları sağlar.|
|[/Zg](zg-generate-function-prototypes.md)|Visual C++ 2015'te kaldırıldı. İşlev prototipleri oluşturur.|

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[Derleyici Seçenekleri](compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](setting-compiler-options.md)<br/>
