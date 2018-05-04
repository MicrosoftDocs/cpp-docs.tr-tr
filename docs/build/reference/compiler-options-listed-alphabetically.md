---
title: Alfabetik olarak listelenen derleyici seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 02/22/2018
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
ms.openlocfilehash: 259958d789ed189c38b75fe708034fb0d76fc35c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-options-listed-alphabetically"></a>Alfabetik Listelenmiş Derleyici Seçenekleri

Derleyici Seçenekleri kapsamlı alfabetik bir listesi verilmiştir. Kategorik bir listesi için bkz: [derleyici seçenekleri kategoriye göre listelenen](compiler-options-listed-by-category.md).

|Seçenek|Amaç|
|------------|-------------|
|[@](at-specify-a-compiler-response-file.md)|Bir yanıt dosyası belirtir.|
|[/?](help-compiler-command-line-help.md)|Derleyici seçenekleri listeler.|
|[/AI](ai-specify-metadata-directories.md)|Bir dizin dosyası başvuruları geçirilen çözümlemek için aranacak belirtir [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/ analyze](analyze-code-analysis.md)|Kod çözümleme etkinleştirin.|
|[/ arch](arch-minimum-cpu-architecture.md)|Kod oluşturma için Mimari belirtir.|
|[/ bekleme](await-enable-coroutine-support.md)|Eş yordamlar (sürdürülebilir işlevler) uzantıları sağlar.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|.Obj dosyasında adreslenebilir bölümlerini sayısını artırır.|
|[/C](c-preserve-comments-during-preprocessing.md)|Ön işleme sırasında açıklamaları korur.|
|[/c](c-compile-without-linking.md)|Bağlantılandırmadan derler.|
|[/ cgthreads](cgthreads-code-generation-threads.md)|En iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını belirtir.|
|[/ CLR](clr-common-language-runtime-compilation.md)|Ortak dil çalışma zamanı üzerinde çalıştırmak için bir çıktı dosyası oluşturur.|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Derleme zamanında constexpr değerlendirme denetler.|
|[/D](d-preprocessor-definitions.md)|Sabitler ve makroları tanımlar.|
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Tanılama iletileri biçimini denetler.|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Bir XML dosyasına işlem belgeleri açıklamaları.|
|[/E](e-preprocess-to-stdout.md)|Önişlemci çıktısı için standart çıktı kopyalar.|
|[/EH](eh-exception-handling-model.md)|Özel durum işleme modeli belirtir.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıktısı için standart çıktı kopyalar.|
|[/ errorreport](errorreport-report-internal-compiler-errors.md)|Derleyici iç hatası (çok) bilgileri doğrudan Visual C++ ekip sağlamanıza izin verir.|
|[/Execution-Charset](execution-charset-set-execution-character-set.md)|Set yürütme karakter kümesi.|
|[/F](f-set-stack-size.md)|Ayarlar boyutu yığın.|
|[/ favor](favor-optimize-for-architecture-specifics.md)|Özel bir en iyi duruma getirilmiş kod üretmez [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] mimarisi veya AMD64 ve genişletilmiş bellek 64 Technology (EM64T) mimarilerindeki mikro mimari özellikleri için.|
|[/FA](fa-fa-listing-file.md)|Bir listeyi dosyası oluşturur.|
|[/FA](fa-fa-listing-file.md)|Listeleme dosya adını ayarlar.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Kaynak kodu dosyaları tam yolunu görüntü cl.exe tanılama metin geçirildi.|
|[/FD](fd-program-database-file-name.md)|Program veritabanı dosyayı yeniden adlandırır.|
|[/FE](fe-name-exe-file.md)|Yürütülebilir dosyayı yeniden adlandırır.|
|[/FI](fi-name-forced-include-file.md)|Belirtilen içerme dosyası preprocesses.|
|[/FI](fi-preprocess-output-file-name.md)|Önceden işlenmiş çıktı dosyası adını ayarlar.|
|[/FM](fm-name-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/FO](fo-object-file-name.md)|Bir nesne dosyası oluşturur.|
|[/FP](fp-specify-floating-point-behavior.md)|Kayan nokta davranışını belirt.|
|[/FP](fp-name-dot-pch-file.md)|Önceden derlenmiş üst bilgi dosyası adını belirtir.|
|[/FR](fr-fr-create-dot-sbr-file.md)<br /><br /> [/FR](fr-fr-create-dot-sbr-file.md)|Tarayıcı dosyaları oluşturur. **/FR** kullanım dışı bırakılmıştır.|
|[/FS](fs-force-synchronous-pdb-writes.md)|Zorlar MSPDBSRV serileştirilmesi için program veritabanı (PDB) dosyasına yazar. EXE.|
|[/FU](fu-name-forced-hash-using-file.md)|Bir dosya adı kullanımı için geçildikten gibi zorlar [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesi.|
|[/FX](fx-merge-injected-code.md)|Kaynak dosya ile eklenen kodu birleştirme.|
|[/GA](ga-optimize-for-windows-application.md)|Windows uygulaması için kod en iyi duruma getirir.|
|[/Gd](gd-gr-gv-gz-calling-convention.md)|Kullanan `__cdecl` çağırma kuralı (yalnızca x86).|
|[/Ge](ge-enable-stack-probes.md)|Kullanım dışı. Yığın yoklamalarını etkinleştirir.|
|[/GF](gf-eliminate-duplicate-strings.md)|Etkinleştirir dize havuzu.|
|[/GH](gh-enable-pexit-hook-function.md)|Çağrıları kanca işlevi `_pexit`.|
|[/GH](gh-enable-penter-hook-function.md)|Çağrıları kanca işlevi `_penter`.|
|[/GL](gl-whole-program-optimization.md)|Bütün program iyileştirmesi sağlar.|
|[/Gm](gm-enable-minimal-rebuild.md)|En az etkinleştirir yeniden oluşturun.|
|[/GR](gr-enable-run-time-type-information.md)|Çalışma zamanı türü bilgileri (RTTI) sağlar.|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|Kullanan `__fastcall` çağırma kuralı (yalnızca x86).|
|[/GS](gs-buffer-security-check.md)|Güvenlik denetimi arabelleğe alır.|
|[/GS](gs-control-stack-checking-calls.md)|Denetimleri yığın yoklamaları.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Fiber güvenliği için statik iş parçacığı yerel depolama kullanılarak ayrılmış verileri destekler.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Denetim akışı koruyucu güvenlik denetimlerini ekler.|
|[/ GV](gd-gr-gv-gz-calling-convention.md)|Kullanan `__vectorcall` çağırma. (x86 hem yalnızca x64)|
|[/GW](gw-optimize-global-data.md)|Genel veri bütün program iyileştirmesi sağlar.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işleme sağlar. Kullanım [/EH](eh-exception-handling-model.md) yerine.|
|[/Gy](gy-enable-function-level-linking.md)|Etkinleştirir işlev bağlama düzeyi.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. Aynı [/RTC1](rtc-run-time-error-checks.md).|
|[/GZ](gd-gr-gv-gz-calling-convention.md)|Kullanan `__stdcall` çağırma kuralı (yalnızca x86).|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (Genel) adların uzunluğunu kısıtlar.|
|[/HELP](help-compiler-command-line-help.md)|Derleyici seçenekleri listeler.|
|[/ homeparams](homeparams-copy-register-parameters-to-stack.md)|İşlevi girişte yığında konumlarına yazılacak yazmaçlar zorlar parametre geçirildi. Yalnızca Bu derleyici seçeneği olan [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] derleyicileri (yerel ve derleme).|
|[/ hotpatch](hotpatch-create-hotpatchable-image.md)|Bir düzeltme eki eklenebilen görüntü oluşturur.|
|[/I](i-additional-include-directories.md)|İçerme dosyaları için bir dizin arar.|
|[/J](j-default-char-type-is-unsigned.md)|Varsayılan değişiklikleri `char` türü.|
|[/ Kernel](kernel-create-kernel-mode-binary.md)|Derleyicide ve bağlayıcıda Windows Çekirdeği'nde yürütülebilir bir ikili oluşturur.|
|[/LD](md-mt-ld-use-run-time-library.md)|Bir dinamik bağlantı kitaplığı oluşturur.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Hata ayıklama dinamik bağlantı kitaplığı oluşturur.|
|[/link](link-pass-options-to-linker.md)|Belirtilen seçenek bağlantı geçirir.|
|[/LN](ln-create-msil-module.md)|MSIL modülü oluşturur.|
|[/MD](md-mt-ld-use-run-time-library.md)|MSVCRT.lib kullanarak birden çok iş parçacıklı DLL oluşturur.|
|[/MDd](md-mt-ld-use-run-time-library.md)|Bir hata ayıklama oluşturur MSVCRTD.lib kullanarak birden çok iş parçacıklı DLL.|
|[/MP](mp-build-with-multiple-processes.md)|Birden çok işlemleri kullanarak birden çok kaynak dosyalarını derler.|
|[/MT](md-mt-ld-use-run-time-library.md)|LIBCMT.lib kullanarak birden çok iş parçacıklı yürütülebilir bir dosya oluşturur.|
|[/MTd](md-mt-ld-use-run-time-library.md)|LIBCMTD.lib kullanarak hata ayıklama birden çok iş parçacıklı yürütülebilir dosyası oluşturur.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Oturum açma başlık görüntülenmesini engeller.|
|[/ O1](o1-o2-minimize-size-maximize-speed.md)|Küçük kod oluşturur.|
|[/ O2](o1-o2-minimize-size-maximize-speed.md)|Hızlı kod oluşturur.|
|[/OB](ob-inline-function-expansion.md)|Satır içi genişletme denetler.|
|[/Od](od-disable-debug.md)|En iyi duruma getirme devre dışı bırakır.|
|[/Og](og-global-optimizations.md)|Kullanım dışı. Global iyileştirmeler kullanır.|
|[/Oi](oi-generate-intrinsic-functions.md)|İç işlevler oluşturur.|
|[/ OpenMP](openmp-enable-openmp-2-0-support.md)|Etkinleştirir [#pragma omp](../../preprocessor/omp.md) kaynak kodunda.|
|[/OS](os-ot-favor-small-code-favor-fast-code.md)|Küçük kod korur.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Favors kod hızlı.|
|[/Ox](ox-full-optimization.md)|En fazla iyileştirme kullanır (/ Ob2gity /Gs).|
|[/Oy](oy-frame-pointer-omission.md)|Çerçeve işaretçisi (yalnızca x86) atlar.|
|[/P](p-preprocess-to-a-file.md)|Önişlemci çıktısı bir dosyaya yazar.|
|[/ izin veren-](permissive-standards-conformance.md)|Standart Uyumluluk modunu ayarlayın.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Hızlı soyutları oluşturur.|
|[/QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Bastırır `_ftol` bir kayan nokta türüne dönüştürme tamsayı türü için gerekli (yalnızca x86) olduğunda.|
|[/ Qimprecise_fwaits](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Kaldırır `fwait` içindeki komutları `try` engeller.|
|[/Qpar (Otomatik Paralel Hale Getirici)](qpar-auto-parallelizer.md)|Otomatik paralelleştirme işaretlenir döngüsü sağlar [#pragma loop()](../../preprocessor/loop.md) yönergesi.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Kayan nokta değerlerini ve devre dışı bırakır belirli için kullandığı tamsayı taşıma yönergeleri noktası yük iyileştirmeler kayan.|
|[/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)](qvec-report-auto-vectorizer-reporting-level.md)|Otomatik vectorization düzeylerini raporlama etkinleştirir.|
|[/ RTC](rtc-run-time-error-checks.md)|Çalışma zamanı hata denetimini etkinleştirir.|
|[/ SDL](sdl-enable-additional-security-checks.md)|Ek güvenlik özellikleri ve uyarılar sağlar.|
|[/ showıncludes](showincludes-list-include-files.md)|Derleme sırasında INCLUDE dosyaların bir listesini görüntüler.|
|[/Source-Charset](source-charset-set-source-character-set.md)|Küme kaynak karakter kümesi.|
|[/Std](std-specify-language-standard-version.md)|C++ Standart sürümünü uyumluluk Seçici.|
|[TP](tc-tp-tc-tp-specify-source-file-type.md)|Bir C kaynak dosyasını belirtir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|C. tüm kaynak dosyaların belirtir|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|C++ kaynak dosyasını belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Tüm kaynak dosyaların C++ belirtir.|
|[/U](u-u-undefine-symbols.md)|Önceden tanımlanmış makrosu kaldırır.|
|[/u](u-u-undefine-symbols.md)|Tüm önceden tanımlı makrolar kaldırır.|
|[/UTF-8](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Kaynak ve yürütme karakter kümesi UTF-8'e ayarlar.|
|[/V](v-version-number.md)|Kullanım dışı. .Obj dosya sürümü dizesini ayarlar.|
|[/Validate-Charset](validate-charset-validate-for-compatible-characters.md)|Yalnızca uyumlu karakterler için UTF-8 dosyaları doğrulayın.|
|[/vd](vd-disable-construction-displacements.md)|Gizler veya gizli vtordisp sınıf üyeleri etkinleştirir.|
|[/vmb](vmb-vmg-representation-method.md)|Üye işaretçileri için en iyi temel kullanır.|
|[/vmg](vmb-vmg-representation-method.md)|Kullandığı tam sayılanların genel üyeleri işaretçileri için.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Birden çok devralma bildirir.|
|[/ VMs](vmm-vms-vmv-general-purpose-representation.md)|Tek devralma bildirir.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Sanal devralma bildirir.|
|[/ volatile](volatile-volatile-keyword-interpretation.md)|Volatile anahtar sözcüğü nasıl yorumlanacağını seçer.|
|[/w](compiler-option-warning-level.md)|Tüm uyarıları devre dışı bırakır.|
|[/ W0, /W1, /W2, /W3, /W4](compiler-option-warning-level.md)|Hangi uyarı düzeyini çıktı olarak ayarlar.|
|[/W1, /w2, /w3, /w4](compiler-option-warning-level.md)|Belirtilen uyarı uyarı düzeyini belirler.|
|[/ Wall](compiler-option-warning-level.md)|Varsayılan olarak devre dışıdır uyarılar dahil olmak üzere tüm uyarıları sağlar.|
|[/WD](compiler-option-warning-level.md)|Belirtilen uyarı devre dışı bırakır.|
|[/We](compiler-option-warning-level.md)|Belirtilen uyarıyı hata olarak değerlendirir.|
|[/WL](wl-enable-one-line-diagnostics.md)|C++ kaynak kodu komut satırından derlerken hata ve uyarı iletileri için tek satır tanılamayı sağlar.|
|[/Wo](compiler-option-warning-level.md)|Belirtilen uyarı yalnızca bir kez görüntüler.|
|[/ Wp64](wp64-detect-64-bit-portability-issues.md)|Kullanımdan kalktı. 64 bit taşınabilirlik sorunları algılar.|
|[/Wv](compiler-option-warning-level.md)|Derleyici belirtilen sürüm sonra çıkan hiçbir uyarıları görüntüler.|
|[/WX](compiler-option-warning-level.md)|Tüm uyarıları hata olarak değerlendirir.|
|[/X](x-ignore-standard-include-paths.md)|Standart yoksayar dizini içerir.|
|[/Y-](y-ignore-precompiled-header-options.md)|Diğer tüm önceden derlenmiş üstbilgi derleyici seçenekleri geçerli derlemede yok sayar.|
|[/Yc](yc-create-precompiled-header-file.md)|Önceden derlenmiş üst bilgi dosyası oluşturur.|
|[/YD](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Yerler tüm nesne dosyalarında hata ayıklama bilgileri tamamlayın. Kullanım [/zı](z7-zi-zi-debug-information-format.md) yerine.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Hata ayıklama kitaplığı oluştururken PCH başvurusu yerleştirir|
|[/Yu](yu-use-precompiled-header-file.md)|Önceden derlenmiş üst bilgi dosyasını sırasında derleme kullanır.|
|[/Z7](z7-zi-zi-debug-information-format.md)|C 7.0 uyumlu hata ayıklama bilgisi oluşturur.|
|[/Za](za-ze-disable-language-extensions.md)|Dil uzantılarını devre dışı bırakır.|
|[/Zc](zc-conformance.md)|Standart davranışını altında belirten [/Ze](za-ze-disable-language-extensions.md).[ / Za, /Ze (dil uzantılarını devre dışı bırak)](za-ze-disable-language-extensions.md)|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantıları sağlar.|
|[/ZF](zf.md)|PDB oluşturma zamanı paralel derlemelerde artırır.|
|[/Zg](zg-generate-function-prototypes.md)|Visual C++ 2015'te kaldırıldı. İşlev prototipleri oluşturur.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Düzenle ve devam et ile uyumlu bir program veritabanında hata ayıklama bilgilerini içerir.|
|[/Zi](z7-zi-zi-debug-information-format.md)|Tam hata ayıklama bilgisi oluşturur.|
|[/Zl](zl-omit-default-library-name.md)|Varsayılan kitaplık adını (yalnızca x86) .obj dosyasından kaldırır.|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.|
|[/ZP](zp-struct-member-alignment.md)|Paketleri üyeleri yapılandırın.|
|[/ZS](zs-syntax-check-only.md)|Yalnızca sözdizimi denetler.|
|[/ZW](zw-windows-runtime-compilation.md)|Windows çalışma zamanı'çalıştırmak için bir çıktı dosyası oluşturur.|

## <a name="see-also"></a>Ayrıca Bkz.
 [C/C++ oluşturma başvurusu](c-cpp-building-reference.md) [derleyici seçenekleri](compiler-options.md) [derleyici seçeneklerini ayarlama](setting-compiler-options.md)