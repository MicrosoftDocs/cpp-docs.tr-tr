---
title: Alfabetik Listelenmiş Derleyici Seçenekleri
ms.date: 08/08/2019
helpviewer_keywords:
- compiler options, C++
ms.openlocfilehash: 90c7ee5637a5d1e0f9d48c0f128364ee0df73dab
ms.sourcegitcommit: fd0f8839da5c6a3663798a47c6b0bb6e63b518bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70273642"
---
# <a name="compiler-options-listed-alphabetically"></a>Alfabetik Listelenmiş Derleyici Seçenekleri

Derleyici seçeneklerinin kapsamlı alfabetik bir listesi aşağıda verilmiştir. Kategorik bir liste için, [kategoriye göre listelenen derleyici seçeneklerine](compiler-options-listed-by-category.md)bakın.

|Seçenek|Amaç|
|------------|-------------|
|[@](at-specify-a-compiler-response-file.md)|Bir yanıt dosyası belirtir.|
|[/?](help-compiler-command-line-help.md)|Derleyici seçeneklerini listeler.|
|[/AI](ai-specify-metadata-directories.md)|[#Using](../../preprocessor/hash-using-directive-cpp.md) yönergesine geçirilen dosya başvurularını çözümlemek için arama yapılacak bir dizin belirtir.|
|[/Analyze](analyze-code-analysis.md)|Kod analizini etkinleştirin.|
|[/Arch](arch-minimum-cpu-architecture.md)|Kod oluşturma mimarisini belirtir.|
|[/await](await-enable-coroutine-support.md)|Eş yordamlar (sürdürülebilir Functions) uzantılarını etkinleştirin.|
|[/bigobj](bigobj-increase-number-of-sections-in-dot-obj-file.md)|Bir. obj dosyasındaki adreslenebilir bölüm sayısını artırır.|
|[/C](c-preserve-comments-during-preprocessing.md)|Ön işleme sırasında açıklamaları korur.|
|[/c](c-compile-without-linking.md)|Bağlama olmadan derler.|
|[/cgthreads](cgthreads-code-generation-threads.md)|İyileştirme ve kod oluşturma için kullanılacak CL. exe iş parçacıklarının sayısını belirtir.|
|[clr](clr-common-language-runtime-compilation.md)|Ortak dil çalışma zamanında çalışacak bir çıktı dosyası üretir.|
|[/constexpr](constexpr-control-constexpr-evaluation.md)|Derleme zamanında constexpr değerlendirmesini denetleyin.|
|[BELİRTİLMEDİYSE](d-preprocessor-definitions.md)|Sabitleri ve makroları tanımlar.|
|[/Diagnostics](diagnostics-compiler-diagnostic-options.md)|Tanılama iletilerinin biçimini denetler.|
|[/doc](doc-process-documentation-comments-c-cpp.md)|Belge açıklamalarını bir XML dosyası ile işleyin.|
|[/E](e-preprocess-to-stdout.md)|Önişlemci çıkışını standart çıktıya kopyalar.|
|[/EH](eh-exception-handling-model.md)|Özel durum işleme modelini belirtir.|
|[/EP](ep-preprocess-to-stdout-without-hash-line-directives.md)|Önişlemci çıkışını standart çıktıya kopyalar.|
|[/errorReport](errorreport-report-internal-compiler-errors.md)|İç derleyici hatası (ıCE) bilgilerini doğrudan Microsoft C++ ekibine sağlamanıza olanak tanır.|
|[/Execution-charset](execution-charset-set-execution-character-set.md)|Yürütme karakter kümesini ayarlayın.|
|[/Deneysel: modül](experimental-module.md)|Deneysel modül desteğini izin vermez.|
|[/Deneysel: Önişlemci](experimental-preprocessor.md)|Deneysel uyumsuz Önişlemci desteğini sunar.|
|[/F](f-set-stack-size.md)|Yığın boyutunu ayarlar.|
|[/Favor](favor-optimize-for-architecture-specifics.md)|Yalnızca AMD64 ve genişletilmiş bellek 64 Technology (EM64T) mimarilerinde mikro mimarilerin özellikleri için veya belirli bir x64 mimarisi için optimize edilmiş kodu üretir.|
|[/FA](fa-fa-listing-file.md)|Bir listeleme dosyası oluşturur.|
|[/FA](fa-fa-listing-file.md)|Listeleme dosyası adını ayarlar.|
|[/FC](fc-full-path-of-source-code-file-in-diagnostics.md)|Tanılama metninde CL. exe ' ye geçirilen kaynak kodu dosyalarının tam yolunu görüntüler.|
|[/FD](fd-program-database-file-name.md)|Program veritabanı dosyasını yeniden adlandırır.|
|[/Fe](fe-name-exe-file.md)|Yürütülebilir dosyayı yeniden adlandırır.|
|[FI](fi-name-forced-include-file.md)|Belirtilen içerme dosyasını önceden işler.|
|[FI](fi-preprocess-output-file-name.md)|Önceden işlenmiş çıkış dosyası adını ayarlar.|
|[/FM](fm-name-mapfile.md)|Bir harita dosyası oluşturur.|
|[/Fo](fo-object-file-name.md)|Bir nesne dosyası oluşturur.|
|[/FP](fp-specify-floating-point-behavior.md)|Kayan nokta davranışını belirtin.|
|[/FP](fp-name-dot-pch-file.md)|Önceden derlenmiş üst bilgi dosyası adını belirtir.|
|[/FR](fr-fr-create-dot-sbr-file.md)<br /><br /> [/Fr](fr-fr-create-dot-sbr-file.md)|Tarayıcı dosyaları oluşturur. **/Fr** kullanım dışıdır.|
|[/FS](fs-force-synchronous-pdb-writes.md)|, MSPDBSRV aracılığıyla serileştirilmesi için program veritabanı (PDB) dosyasına yazmaları zorlar. EXE.|
|[/FU](fu-name-forced-hash-using-file.md)|Dosya adının [#using](../../preprocessor/hash-using-directive-cpp.md) yönergesine geçirilmiş gibi kullanılmasını zorlar.|
|[/FX](fx-merge-injected-code.md)|Eklenen kodu kaynak dosyayla birleştirir.|
|[/GA](ga-optimize-for-windows-application.md)|Windows uygulaması için kodu iyileştirir.|
|[/GD](gd-gr-gv-gz-calling-convention.md)|`__cdecl` Çağırma kuralını kullanır (yalnızca x86).|
|[/GE](ge-enable-stack-probes.md)|Kullanım dışı. Yığın araştırmalarını etkinleştirir.|
|[/GF](gf-eliminate-duplicate-strings.md)|Dize havuzunu izin vermez.|
|[/GH](gh-enable-pexit-hook-function.md)|Kanca işlevini `_pexit`çağırır.|
|[/Gh](gh-enable-penter-hook-function.md)|Kanca işlevini `_penter`çağırır.|
|[/GL](gl-whole-program-optimization.md)|Tüm program iyileştirmesini mümkün hale getirme.|
|[/Gm](gm-enable-minimal-rebuild.md)|Kullanım dışı. En az yeniden derlemeyi mümkün.|
|[/GR](gr-enable-run-time-type-information.md)|Çalışma zamanı tür bilgilerini (RTTı) etkinleştir.|
|[/Gr](gd-gr-gv-gz-calling-convention.md)|`__fastcall` Çağırma kuralını kullanır (yalnızca x86).|
|[/GS](gs-buffer-security-check.md)|Güvenlik denetimini arabelleğe alır.|
|[/GS](gs-control-stack-checking-calls.md)|Yığın araştırmalarını denetler.|
|[/GT](gt-support-fiber-safe-thread-local-storage.md)|Statik iş parçacığı yerel depolama kullanılarak ayrılan veri için fiber güvenliğini destekler.|
|[/guard:cf](guard-enable-control-flow-guard.md)|Denetim akışı koruyucusu güvenlik denetimleri ekler.|
|[/GV](gd-gr-gv-gz-calling-convention.md)|`__vectorcall` Çağırma kuralını kullanır. (yalnızca x86 ve x64)|
|[/GW](gw-optimize-global-data.md)|Tam program genel veri iyileştirmesini mümkün hale getirme.|
|[/GX](gx-enable-exception-handling.md)|Kullanım dışı. Zaman uyumlu özel durum işlemeyi mümkün. Bunun yerine [/Eh](eh-exception-handling-model.md) kullanın.|
|[/GY](gy-enable-function-level-linking.md)|İşlev düzeyinde bağlamayı mümkün.|
|[/GZ](gz-enable-stack-frame-run-time-error-checking.md)|Kullanım dışı. [/RTC1](rtc-run-time-error-checks.md)ile aynı.|
|[/Gz](gd-gr-gv-gz-calling-convention.md)|`__stdcall` Çağırma kuralını kullanır (yalnızca x86).|
|[/H](h-restrict-length-of-external-names.md)|Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar.|
|[/HELP](help-compiler-command-line-help.md)|Derleyici seçeneklerini listeler.|
|[/homeparams](homeparams-copy-register-parameters-to-stack.md)|, Yazmaçlarda geçirilen parametreleri işlev girişi üzerine yığındaki konumlarına yazılacak şekilde zorlar. Bu derleyici seçeneği yalnızca x64 derleyicileri için geçerlidir (yerel ve çapraz derleme).|
|[/hotpatch](hotpatch-create-hotpatchable-image.md)|Hot-patchable bir görüntü oluşturur.|
|[/I](i-additional-include-directories.md)|İçerme dosyaları için bir dizin arar.|
|[/J](j-default-char-type-is-unsigned.md)|Varsayılan `char` türü değiştirir.|
|[/JMC](jmc.md)|Yerel C++ yalnızca kendi kodum hata ayıklamayı destekler.|
|[/Kernel](kernel-create-kernel-mode-binary.md)|Derleyici ve bağlayıcı, Windows çekirdeğinde yürütülebilecek bir ikili oluşturacak.|
|[/LD](md-mt-ld-use-run-time-library.md)|Dinamik bağlantı kitaplığı oluşturur.|
|[/LDd](md-mt-ld-use-run-time-library.md)|Bir hata ayıklama dinamik bağlantı kitaplığı oluşturur.|
|[/link](link-pass-options-to-linker.md)|BAĞLAMA için belirtilen seçeneği geçirir.|
|[/LN](ln-create-msil-module.md)|MSIL Modülü oluşturur.|
|[/MD](md-mt-ld-use-run-time-library.md)|MSVCRT. lib kullanarak çok iş parçacıklı bir DLL oluşturur.|
|[/MDd](md-mt-ld-use-run-time-library.md)|MSVCRTD. lib kullanarak bir hata ayıklama çok iş parçacıklı DLL oluşturur.|
|[/MP](mp-build-with-multiple-processes.md)|Birden çok işlem kullanarak birden çok kaynak dosyayı derler.|
|[/MT](md-mt-ld-use-run-time-library.md)|LıBCMT. lib kullanarak çok iş parçacıklı yürütülebilir dosya oluşturur.|
|[/MTd](md-mt-ld-use-run-time-library.md)|LıBCMTD. lib kullanarak çok iş parçacıklı yürütülebilir dosya oluşturur.|
|[/nologo](nologo-suppress-startup-banner-c-cpp.md)|Oturum açma başlığının görüntülenmesini önler.|
|[/O1](o1-o2-minimize-size-maximize-speed.md)|Küçük kod oluşturur.|
|[/O2](o1-o2-minimize-size-maximize-speed.md)|Hızlı kod oluşturur.|
|[/OB](ob-inline-function-expansion.md)|Satır içi genişletmeyi denetler.|
|[/Od](od-disable-debug.md)|İyileştirmeyi devre dışı bırakır.|
|[/OG](og-global-optimizations.md)|Kullanım dışı. Genel iyileştirmeleri kullanır.|
|[/Oi](oi-generate-intrinsic-functions.md)|İç işlevleri oluşturur.|
|[/OpenMP](openmp-enable-openmp-2-0-support.md)|Kaynak kodundaki [`#pragma omp`](../../preprocessor/omp.md) yönergeyi izin vermez.|
|[/OS](os-ot-favor-small-code-favor-fast-code.md)|Küçük koda öncelik verir.|
|[/Ot](os-ot-favor-small-code-favor-fast-code.md)|Hızlı koda öncelik verir.|
|[/Ox](ox-full-optimization.md)|/O2 ' nin/GF veya/gi içermeyen bir alt kümesi.|
|[/Oy](oy-frame-pointer-omission.md)|Çerçeve işaretçisini atlar (yalnızca x86).|
|[/P](p-preprocess-to-a-file.md)|Önişlemci çıkışını bir dosyaya yazar.|
|[/Permissive-](permissive-standards-conformance.md)|Standart uyumluluk modunu ayarlayın.|
|[/Qfast_transcendentals](qfast-transcendentals-force-fast-transcendentals.md)|Hızlı bir şekilde daha fazla işlem oluşturur.|
|[/QIfist](qifist-suppress-ftol.md)|Kullanım dışı. Bir `_ftol` kayan nokta türünden integral türüne dönüştürmenin gerekli olduğu durumlarda (yalnızca x86) bastırır.|
|[/Qımprecise_fwait](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md)|Bloklar `fwait` içindeki`try` komutları kaldırır.|
|[/Qpar (Otomatik Paralel Hale Getirici)](qpar-auto-parallelizer.md)|[#Pragma loop ()](../../preprocessor/loop.md) yönergesiyle işaretlenen döngülerin otomatik paralelleştirilmesini mümkün hale getirme.|
|[/Qsafe_fp_loads](qsafe-fp-loads.md)|Kayan nokta değerleri için tamsayı taşıma yönergelerini kullanır ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır.|
|[/Qspectre](qspectre.md)|Belirli Spectre varyant 1 güvenlik açıklarına karşı hafifletmek için derleyici oluşturma yönergelerinin belirtir.|
|[/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)](qvec-report-auto-vectorizer-reporting-level.md)|Otomatik vektörleştirme için raporlama düzeylerine izin vermez.|
|[/RTC](rtc-run-time-error-checks.md)|Çalışma zamanı hata denetimini etkinleştirilir.|
|[/SDL](sdl-enable-additional-security-checks.md)|Ek güvenlik özellikleri ve uyarılar sunar.|
|[/showIncludes](showincludes-list-include-files.md)|Derleme sırasında içerme dosyaları listesini görüntüler.|
|[/Source-charset](source-charset-set-source-character-set.md)|Kaynak karakter kümesini ayarla.|
|[/STD](std-specify-language-standard-version.md)|C++Standart sürüm uyumluluğu Seçicisi.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|C kaynak dosyasını belirtir.|
|[/TC](tc-tp-tc-tp-specify-source-file-type.md)|Tüm kaynak dosyalarının C olduğunu belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Bir C++ kaynak dosyasını belirtir.|
|[/TP](tc-tp-tc-tp-specify-source-file-type.md)|Tüm kaynak dosyaları belirtir C++.|
|[P](u-u-undefine-symbols.md)|Önceden tanımlanmış bir makroyu kaldırır.|
|[/u](u-u-undefine-symbols.md)|Önceden tanımlanmış tüm makroları kaldırır.|
|[/UTF-8 belirtildiğinde](utf-8-set-source-and-executable-character-sets-to-utf-8.md)|Kaynak ve yürütme karakter kümelerini UTF-8 olarak ayarlayın.|
|[ÇIKTIDA](v-version-number.md)|Kullanım dışı. . Obj dosya sürümü dizesini ayarlar.|
|[/Validate-charset](validate-charset-validate-for-compatible-characters.md)|UTF-8 dosyalarını yalnızca uyumlu karakterler için doğrulayın.|
|[/vd](vd-disable-construction-displacements.md)|Gizli vtordisp sınıf üyelerini bastırır veya etkinleştirirler.|
|[/vmb](vmb-vmg-representation-method.md)|Üye işaretçileri için en iyi temeli kullanır.|
|[/vmg](vmb-vmg-representation-method.md)|Üye işaretçileri için tam olarak kullanım sağlar.|
|[/vmm](vmm-vms-vmv-general-purpose-representation.md)|Birden çok devralma bildirir.|
|[/VMs](vmm-vms-vmv-general-purpose-representation.md)|Tek devralma bildirir.|
|[/vmv](vmm-vms-vmv-general-purpose-representation.md)|Sanal devralmayı bildirir.|
|[/volatile](volatile-volatile-keyword-interpretation.md)|Volatile anahtar sözcüğünün nasıl yorumlandığını seçer.|
|[aralıkları](compiler-option-warning-level.md)|Tüm uyarıları devre dışı bırakır.|
|[/W0,/W1,/W2,/W3,/W4](compiler-option-warning-level.md)|Hangi uyarı düzeyini çıkış için ayarlar.|
|[/W1,/W2,/W3,/W4](compiler-option-warning-level.md)|Belirtilen uyarının uyarı düzeyini ayarlar.|
|[/Wall](compiler-option-warning-level.md)|Varsayılan olarak devre dışı bırakılan uyarılar da dahil olmak üzere tüm uyarıları sunar.|
|[/WD](compiler-option-warning-level.md)|Belirtilen uyarıyı devre dışı bırakır.|
|[/we](compiler-option-warning-level.md)|Belirtilen uyarıyı hata olarak değerlendirir.|
|[/WL](wl-enable-one-line-diagnostics.md)|Komut satırından kaynak kodu derlenirken C++ hata ve uyarı iletileri için tek satırlık tanılamayı mümkün bir şekilde sunar.|
|[/Wo](compiler-option-warning-level.md)|Belirtilen uyarıyı yalnızca bir kez görüntüler.|
|[/Wp64](wp64-detect-64-bit-portability-issues.md)|Kullanımdan kalktı. 64-bit taşınabilirlik sorunlarını algılar.|
|[/WV](compiler-option-warning-level.md)|Derleyicinin belirtilen sürümünden sonra gelen uyarıları görüntüler.|
|[/WX](compiler-option-warning-level.md)|Tüm uyarıları hata olarak değerlendirir.|
|[/X](x-ignore-standard-include-paths.md)|Standart içerme dizinini yoksayar.|
|[/Y-](y-ignore-precompiled-header-options.md)|Geçerli derlemede tüm önceden derlenmiş üst bilgi derleyici seçeneklerini yoksayar.|
|[/Yc](yc-create-precompiled-header-file.md)|Önceden derlenmiş bir üstbilgi dosyası oluşturur.|
|[/Yd](yd-place-debug-information-in-object-file.md)|Kullanım dışı. Tüm nesne dosyalarındaki hata ayıklama bilgilerini tamamlar. Bunun yerine [/Zi](z7-zi-zi-debug-information-format.md) kullanın.|
|[/Yl](yl-inject-pch-reference-for-debug-library.md)|Hata ayıklama kitaplığı oluştururken bir PCH başvurusunu çıkartır|
|[/Yu](yu-use-precompiled-header-file.md)|Derleme sırasında önceden derlenmiş bir üstbilgi dosyası kullanır.|
|[/Z7](z7-zi-zi-debug-information-format.md)|C 7,0 uyumlu hata ayıklama bilgileri üretir.|
|[/Za](za-ze-disable-language-extensions.md)|Dil uzantılarını devre dışı bırakır.|
|[/Zc](zc-conformance.md)|[/Ze](za-ze-disable-language-extensions.md)altında Standart davranışı belirtir. [/Za,/Ze (dil uzantılarını devre dışı bırak)](za-ze-disable-language-extensions.md)|
|[/Ze](za-ze-disable-language-extensions.md)|Kullanım dışı. Dil uzantılarını izin vermez.|
|[/ZF](zf.md)|Paralel derlemelerde PDB oluşturma süresini geliştirir.|
|[/Zg](zg-generate-function-prototypes.md)|Visual Studio 2015 ' de kaldırıldı. İşlev prototipleri oluşturur.|
|[/ZI](z7-zi-zi-debug-information-format.md)|Düzenle ve devam et ile uyumlu bir program veritabanındaki hata ayıklama bilgilerini içerir.|
|[/Zi](z7-zi-zi-debug-information-format.md)|Tüm hata ayıklama bilgileri üretir.|
|[/Zl](zl-omit-default-library-name.md)|Varsayılan kitaplık adını. obj dosyasından kaldırır (yalnızca x86).|
|[/Zm](zm-specify-precompiled-header-memory-allocation-limit.md)|Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir.|
|[/Zo](zo-enhance-optimized-debugging.md)|İyileştirilmiş kod için gelişmiş hata ayıklama bilgileri oluşturur.|
|[/ZP](zp-struct-member-alignment.md)|Paketler yapısı üyeleri.|
|[/ZS](zs-syntax-check-only.md)|Yalnızca söz dizimini denetler.|
|[/ZW](zw-windows-runtime-compilation.md)|Windows Çalışma Zamanı çalıştırmak için bir çıkış dosyası üretir.|

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
