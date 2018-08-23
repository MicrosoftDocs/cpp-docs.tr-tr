---
title: Alfabetik olarak listelenen derleyici seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 08/20/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 985232af68daebe924cd51300974d614bf6d6756
ms.sourcegitcommit: 7f3df9ff0310a4716b8136ca20deba699ca86c6c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/21/2018
ms.locfileid: "42466190"
---
# <a name="compiler-options-listed-alphabetically"></a>Alfabetik Listelenmiş Derleyici Seçenekleri

Derleyici Seçenekleri kapsamlı bir alfabetik listesi verilmiştir. Kategorisel liste için bkz: [kategoriye göre listelenmiş derleyici seçenekleri](compiler-options-listed-by-category.md).

|Seçenek|Amaç|
|------------|-------------|
|[@](at-specify-a-compiler-response-file.md)|Bir yanıt dosyası belirtir.|
|[/?](help-compiler-command-line-help.md)|Derleme seçeneklerini listeler.|
|[/AI](ai-specify-metadata-directories.md)|Geçirilen dosya başvurularını çözümlemek için aranacak dizini belirtir [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/ analyze](analyze-code-analysis.md)|Kod analizini etkinleştirir.|
|[/ arch:](arch-minimum-cpu-architecture.md)|İçin kod oluşturma mimarisini belirtir.|
|[/ await](await-enable-coroutine-support.md)|Eş yordamlar (sürdürülebilir işlevler) uzantılarını etkinleştir.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Bir .obj dosyasında adreslenebilir bölüm sayısı artar.|
|[/C](c-preserve-comments-during-preprocessing.md)|Ön işlem sırasında yorumları korur.|
|[/c](c-compile-without-linking.md)|Bağlanmadan derler.|
|[/ cgthreads](cgthreads-code-generation-threads.md)|En iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını belirtir.|
|[/ CLR](clr-common-language-runtime-compilation.md)|Ortak dil çalışma zamanı üzerinde çalıştırılacak bir çıktı dosyası üretir.|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Constexpr değerlendirmesini derleme zamanında.|
|[/D](d-preprocessor-definitions.md)|Sabitleri ve makroları tanımlar.|
|[/ Diagnostics](diagnostics-compiler-diagnostic-options.md)|Tanılama iletilerinin biçimini denetler.|
|[/doc](doc-process-documentation-comments-c-cpp.md)|İşlem belge yorumlarını bir XML dosyası.|
|[/E](e-preprocess-to-stdout.md)|Önişlemci çıktısını standart çıktıya kopyalar.|
|[/EH](eh-exception-handling-model.md)|Özel durum işleme modelini belirtir.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısını standart çıktıya kopyalar.|
|[/ errorreport](errorreport-report-internal-compiler-errors.md)|Derleyici iç hatası (ICE) bilgisini doğrudan Visual C++ ekibine göndermenizi sağlar.|
|[/ Execution-Charset](execution-charset-set-execution-character-set.md)|Yürütme karakter kümesini Ayarla.|
|[/F](f-set-stack-size.md)|Yığın boyutunu ayarlar.|
|[/ favor](favor-optimize-for-architecture-specifics.md)|Belirli bir x64 için en iyi duruma getirilmiş kodu üretir mimarisi ya da hem AMD64 hem de Extended Memory 64 Technology (EM64T) mimarileri mikro mimariler.|
|[/FA](fa-fa-listing-file.md)|Bir listeleme dosyası oluşturur.|
|[/FA](fa-fa-listing-file.md)|Listeleme dosya adını ayarlar.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Tanı metninde cl.exe dosyasına geçirilen kaynak kodu dosyalarının tam yolunu görüntüleyin.|
|[/FD](fd-program-database-file-name.md)|Program veritabanı dosyası yeniden adlandırır.|
|[/FE](fe-name-exe-file.md)|Yürütülebilir dosyayı yeniden adlandırır.|
|[/FI](fi-name-forced-include-file.md)|Belirtilen içerik dosyasını ön işlemden geçirir.|
|[/FI](fi-preprocess-output-file-name.md)|Önceden işlenmiş çıkış dosyası adını ayarlar.|
|[/FM](fm-name-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/FO](fo-object-file-name.md)|Bir nesne dosyası oluşturur.|
|[/ FP](fp-specify-floating-point-behavior.md)|Kayan nokta davranışını belirtin.|
|[/ FP](fp-name-dot-pch-file.md)|Önceden derlenmiş üst bilgi dosyası adını belirtir.|
|[/FR](fr-fr-create-dot-sbr-file.md)<br /><br /> [/FR](fr-fr-create-dot-sbr-file.md)|Tarayıcı dosyaları üretir. **/FR** kullanım dışı bırakılmıştır.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Program veritabanı (PDB) dosyası MSPDBSRV serileştirilecek zorlar yazar. EXE.|
|[/FU](fu-name-forced-hash-using-file.md)|Bu geçirilmiş gibi bir dosya adı kullanımını zorlar [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/FX](fx-merge-injected-code.md)|Eklenen kodu kaynak dosyasıyla birleştirir.|
|[/GA](ga-optimize-for-windows-application.md)|Kodu Windows uygulaması için en iyi duruma getirir.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Kullanan `__cdecl` çağırma kuralı (yalnızca x86).|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın araştırmaları etkinleştirir.|
|[/GF](gf-eliminate-duplicate-strings.md)|Dize havuzunu etkinleştirir.|
|[/GH](gh-enable-pexit-hook-function.md)|Kanca işlevini çağırır `_pexit`.|
|[/GH](gh-enable-penter-hook-function.md)|Kanca işlevini çağırır `_penter`.|
|[/GL](gl-whole-program-optimization.md)|Tüm programın iyileştirilmesini etkinleştirir.|
|[/Gm](gm-enable-minimal-rebuild.md)|Minimum yeniden oluşturmayı etkinleştirir.|
|[GR](gr-enable-run-time-type-information.md)|Çalışma zamanı tür bilgisini (RTTI) etkinleştirir.|
|[Gr](gd-gr-gv-gz-calling-convention.md)|Kullanan `__fastcall` çağırma kuralı (yalnızca x86).|
|[/GS](gs-buffer-security-check.md)|Güvenlik denetimini arabelleğe alır.|
|[/GS](gs-control-stack-checking-calls.md)|Yığın araştırmalarını denetler.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|İş parçacığı-yerel statik depolama alanı kullanılarak yer ayrılmış veri için Fiber güvenliğini destekler.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Denetim akışı koruyucusu güvenlik denetimleri ekler.|
|[/GV](gd-gr-gv-gz-calling-convention.md)|Kullanan `__vectorcall` çağırma kuralı. (x86 ve yalnızca x64)|
|[/GW](gw-optimize-global-data.md)|Tüm program Genel veri en iyi duruma getirme sağlar.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/Gy](gy-enable-function-level-linking.md)|Etkinleştirir işlev seviyesinde bağlamayı.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Aynı [rtc1](rtc-run-time-error-checks.md).|
|[/GZ](gd-gr-gv-gz-calling-convention.md)|Kullanan `__stdcall` çağırma kuralı (yalnızca x86).|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar.|
|[/HELP](help-compiler-command-line-help.md)|Derleme seçeneklerini listeler.|
|[/ homeparams](homeparams-copy-register-parameters-to-stack.md)|Yazmaçlarında işlev girişi ile birlikte kendi konumlarına yazılmasını zorlar parametreler geçildi. Bu derleyici seçeneğini yalnızca x64 için olan derleyicileri (yerel ve çapraz derleme).|
|[/ hotpatch](hotpatch-create-hotpatchable-image.md)|Bir hotpatchable görüntü oluşturur.|
|[/I](i-additional-include-directories.md)|Dosyaları bir dizini arar.|
|[/J](j-default-char-type-is-unsigned.md)|Varsayılan değişiklikleri `char` türü.|
|[/ JMC](jmc.md)|Yerel C++ Yalnızca benim kodum hata ayıklamayı destekler.|
|[/ Kernel](kernel-create-kernel-mode-binary.md)|Derleyici ve bağlayıcı Windows çekirdeğinde yürütülebilecek bir ikili oluşturur.|
|[/LD](md-mt-ld-use-run-time-library.md)|Bir dinamik bağlantı kitaplığı oluşturur.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Hata ayıklama dinamik bağlantı kitaplığı oluşturur.|
|[/link](link-pass-options-to-linker.md)|Belirtilen seçeneği LINK'e geçirir.|
|[/LN](ln-create-msil-module.md)|Bir MSIL modülü oluşturur.|
|[/MD](md-mt-ld-use-run-time-library.md)|MSVCRT.lib kullanarak bir çok iş parçacıklı DLL oluşturur.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Oluşturur bir hata ayıklama çok iş parçacıklı DLL'yi MSVCRTD.lib kullanarak.|
|[/MP](mp-build-with-multiple-processes.md)|Birden çok kaynak dosyaları, birden çok işlem kullanarak derler.|
|[/MT](md-mt-ld-use-run-time-library.md)|Bir çok iş parçacıklı yürütülebilir dosyasını LIBCMT.lib kullanarak oluşturur.|
|[/MTd](md-mt-ld-use-run-time-library.md)|Lıbcmtd.lib kullanarak hata ayıklama çok iş parçacıklı yürütülebilir dosyası oluşturur.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Oturum açma başlığının görüntülenmesini bastırır.|
|[/ O1](o1-o2-minimize-size-maximize-speed.md)|Küçük kod oluşturur.|
|[/ O2](o1-o2-minimize-size-maximize-speed.md)|Hızlı kod oluşturur.|
|[/OB](ob-inline-function-expansion.md)|Satır içi genişlemeyi denetler.|
|[/Od](od-disable-debug.md)|İyileştirme devre dışı bırakır.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Küresel iyileştirmeleri kullanır.|
|[/Oi](oi-generate-intrinsic-functions.md)|İç işlevler üretir.|
|[/ OpenMP](openmp-enable-openmp-2-0-support.md)|Sağlar [#pragma omp](../../preprocessor/omp.md) kaynak kodundaki.|
|[/OS](os-ot-favor-small-code-favor-fast-code.md)|Küçük koda ayrıcalık tanır.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Hızlı koda ayrıcalık tanır.|
|[/Ox](ox-full-optimization.md)|Maksimum iyileştirmeyi kullanır (/ Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|(Yalnızca x86) çerçeve işaretçisini atlar.|
|[/P](p-preprocess-to-a-file.md)|Önişlemci çıktısını bir dosyaya yazar.|
|[/ permissive-](permissive-standards-conformance.md)|Standart uyumluluk modu olarak ayarlayın.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Hızlı transcendentals üretir.|
|[/QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Bastırır `_ftol` gerekli (yalnızca x86) olduğunda bir kayan nokta türünden bir tamsayı türüne dönüştürme.|
|[/ Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Kaldırır `fwait` içindeki komutları `try` engeller.|
|[/Qpar (Otomatik Paralel Hale Getirici)](qpar-auto-parallelizer.md)|Otomatik paralelleştirilmesini ile işaretlenmiş etkinleştirir [#pragma loop()](../../preprocessor/loop.md) yönergesi.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Kayan nokta yükleme iyileştirmelerini kayan nokta değerleri ve devre dışı bırakır belirli için tamsayı taşıma yönergelerini kullanır.|
|[/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)](qvec-report-auto-vectorizer-reporting-level.md)|Otomatik vektörleştirme için raporlama seviyelerini etkinleştirir.|
|[/ RTC](rtc-run-time-error-checks.md)|Çalışma zamanı hata denetimini etkinleştirir.|
|[/ SDL](sdl-enable-additional-security-checks.md)|Ek güvenlik özelliklerini ve uyarılarını etkinleştirir.|
|[/ showıncludes](showincludes-list-include-files.md)|Derleme sırasında ekleme kodu dosyalarının bir listesini görüntüler.|
|[/ Source-Charset](source-charset-set-source-character-set.md)|Kaynak karakter kümesini Ayarla.|
|[/ Std](std-specify-language-standard-version.md)|C++ Standart sürüm uyumluluğu Seçici.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Bir C kaynak dosyasını belirtir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|C kaynak dosyalarının tümünü belirtir|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyasını belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyalarının tümünü olduğunu belirtir.|
|[/U](u-u-undefine-symbols.md)|Önceden tanımlanmış makroyu kaldırır.|
|[/u](u-u-undefine-symbols.md)|Tüm ön tanımlı makroları kaldırır.|
|[/ UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Kaynak ve yürütme karakter kümesini UTF-8'e ayarlar.|
|[/V](v-version-number.md)|Kullanım dışı. .Obj dosya sürüm dizesini ayarlar.|
|[/ Validate-Charset](validate-charset-validate-for-compatible-characters.md)|UTF-8 dosyalarını yalnızca uyumlu karakterler için Doğrula.|
|[/vd](vd-disable-construction-displacements.md)|Engeller ya da vtordisp sınıfının gizli üyelerini etkinleştirir.|
|[/vmb](vmb-vmg-representation-method.md)|Üye işaretçileri için en iyi temel kullanır.|
|[/vmg](vmb-vmg-representation-method.md)|Üye işaretçileri için tam genellik kullanır.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Birden çok devralma bildirir.|
|[/ VMs](vmm-vms-vmv-general-purpose-representation.md)|Tek devralma bildirir.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Sanal devralma bildirir.|
|[/ volatile](volatile-volatile-keyword-interpretation.md)|Uçucu sözcüğünün nasıl yorumlanacağını seçer.|
|[/w](compiler-option-warning-level.md)|Tüm uyarıları devre dışı bırakır.|
|[/ W0, / W1, / W2, / W3, / W4](compiler-option-warning-level.md)|Çıkış için hangi uyarı düzeyini ayarlar.|
|[/ W1, / w2, / W3, / W4](compiler-option-warning-level.md)|Belirtilen uyarı için uyarı düzeyini ayarlar.|
|[/ Wall](compiler-option-warning-level.md)|Varsayılan olarak devre dışıdır uyarılar dahil olmak üzere tüm uyarıları etkinleştirir.|
|[/WD](compiler-option-warning-level.md)|Belirtilen uyarı devre dışı bırakır.|
|[/We](compiler-option-warning-level.md)|Belirtilen uyarı hata olarak değerlendirir.|
|[/WL TEK](wl-enable-one-line-diagnostics.md)|C++ kaynak kodunu komut satırından derlerken hata ve uyarı iletilerini tek satırlık tanılarını etkinleştirir.|
|[/Wo](compiler-option-warning-level.md)|Belirtilen uyarı yalnızca bir kez görüntüler.|
|[/ Wp64](wp64-detect-64-bit-portability-issues.md)|Kullanımdan kalktı. 64 bitlik olasılık sorularını algılar.|
|[/Wv](compiler-option-warning-level.md)|Sonra belirtilen derleyici sürümü xx.yy.zzzz hiçbir görüntüler.|
|[/WX](compiler-option-warning-level.md)|Tüm uyarıları hata olarak değerlendirir.|
|[/X](x-ignore-standard-include-paths.md)|Standart yoksayar içeren dizin.|
|[/Y-](y-ignore-precompiled-header-options.md)|Geçerli derleme diğer tüm önceden derlenmiş üstbilgi derleyici seçeneklerini yok sayar.|
|[/Yc](yc-create-precompiled-header-file.md)|Önceden derlenmiş üst bilgi dosyası oluşturur.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Basamak tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zi](z7-zi-zi-debug-information-format.md) yerine.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Hata ayıklama kitaplığı oluştururken bir PCH başvurusunu ekler|
|[/Yu](yu-use-precompiled-header-file.md)|Derleme sırasında önceden derlenmiş üst bilgi dosyası kullanır.|
|[/Z7](z7-zi-zi-debug-information-format.md)|C 7.0 uyumlu hata ayıklama bilgileri oluşturur.|
|[/Za](za-ze-disable-language-extensions.md)|Dil uzantılarını devre dışı bırakır.|
|[/Zc](zc-conformance.md)|Uyarınca standart davranışı belirtir [/Ze](za-ze-disable-language-extensions.md).[ / Za, /Ze (dil uzantılarını devre dışı bırak)](za-ze-disable-language-extensions.md)|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantılarını etkinleştirir.|
|[/ZF](zf.md)|PDB oluşturma zamanında paralel yapılar artırır.|
|[/Zg](zg-generate-function-prototypes.md)|Visual C++ 2015'te kaldırıldı. İşlev prototipleri üretir.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Düzenle ve devam et ile uyumlu bir program veritabanı'nda hata ayıklama bilgilerini içerir.|
|[/Zi](z7-zi-zi-debug-information-format.md)|Tam hata ayıklama bilgisi üretir.|
|[/Zl](zl-omit-default-library-name.md)|Varsayılan kitaplık adını .obj dosyasından (yalnızca x86) kaldırır.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.|
|[/ZP](zp-struct-member-alignment.md)|Yapı üyelerini paketler.|
|[/ZS](zs-syntax-check-only.md)|Yalnızca söz dizimini denetler.|
|[/ZW](zw-windows-runtime-compilation.md)|Windows çalışma zamanında çalışacak bir çıktı dosyası üretir.|

## <a name="see-also"></a>Ayrıca Bkz.
 [C/C++ oluşturma başvurusu](c-cpp-building-reference.md) [derleyici seçenekleri](compiler-options.md) [derleyici seçeneklerini ayarlama](setting-compiler-options.md)