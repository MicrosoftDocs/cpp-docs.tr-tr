---
title: Alfabetik listelenmiş derleyici seçenekleri
description: Microsoft C/C++ derleyicisi komut satırı seçeneklerinin alfabetik düzeninde başvuru listesi.
ms.date: 07/08/2020
helpviewer_keywords:
- compiler options, C++
ms.openlocfilehash: 46c6f7009c840c83db2f945de2e504f08172fca2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223895"
---
# <a name="compiler-options-listed-alphabetically"></a>Alfabetik listelenmiş derleyici seçenekleri

Bu tablo, derleyici seçeneklerinin alfabetik bir listesini içerir. Kategoriye göre derleyici seçeneklerinin bir listesi için, [kategoriye göre listelenen derleyici seçenekleri](compiler-options-listed-by-category.md) bölümüne bakın.

## <a name="compiler-options"></a>Derleyici seçenekleri

| Seçenek | Amaç |
|--|--|
| [`@`](at-specify-a-compiler-response-file.md) | Bir yanıt dosyası belirtir. |
| [`/?`](help-compiler-command-line-help.md) | Derleyici seçeneklerini listeler. |
| [`/AI`](ai-specify-metadata-directories.md) | Yönergeye geçirilen dosya başvurularını çözümlemek için arama yapılacak bir dizin belirtir [`#using`](../../preprocessor/hash-using-directive-cpp.md) . |
| [`/analyze`](analyze-code-analysis.md) | Kod analizini etkinleştirin. |
| [`/arch`](arch-minimum-cpu-architecture.md) | Kod oluşturma mimarisini belirtir. |
| [`/await`](await-enable-coroutine-support.md) | Eş yordamlar (sürdürülebilir Functions) uzantılarını etkinleştirin. |
| [`/bigobj`](bigobj-increase-number-of-sections-in-dot-obj-file.md) | Bir. obj dosyasındaki adreslenebilir bölüm sayısını artırır. |
| [`/C`](c-preserve-comments-during-preprocessing.md) | Ön işleme sırasında açıklamaları korur. |
| [`/c`](c-compile-without-linking.md) | Bağlama olmadan derler. |
| [`/cgthreads`](cgthreads-code-generation-threads.md) | İyileştirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını belirtir. |
| [`/clr`](clr-common-language-runtime-compilation.md) | Ortak dil çalışma zamanında çalışacak bir çıktı dosyası üretir. |
| [`/constexpr`](constexpr-control-constexpr-evaluation.md) | **`constexpr`** Derleme zamanında değerlendirmeyi denetleyin. |
| [`/D`](d-preprocessor-definitions.md) | Sabitleri ve makroları tanımlar. |
| [`/diagnostics`](diagnostics-compiler-diagnostic-options.md) | Tanılama iletilerinin biçimini denetler. |
| [`/doc`](doc-process-documentation-comments-c-cpp.md) | Belge açıklamalarını bir XML dosyası ile işleyin. |
| [`/E`](e-preprocess-to-stdout.md) | Önişlemci çıkışını standart çıktıya kopyalar. |
| [`/EH`](eh-exception-handling-model.md) | Özel durum işleme modelini belirtir. |
| [`/EP`](ep-preprocess-to-stdout-without-hash-line-directives.md) | Önişlemci çıkışını standart çıktıya kopyalar. |
| [`/errorReport`](errorreport-report-internal-compiler-errors.md) | Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
| [`/execution-charset`](execution-charset-set-execution-character-set.md) | Yürütme karakter kümesini ayarlayın. |
| [`/experimental:module`](experimental-module.md) | Deneysel modül desteğini izin vermez. |
| [`/experimental:preprocessor`](experimental-preprocessor.md) | Deneysel uyumsuz Önişlemci desteğini sunar. |
| [`/F`](f-set-stack-size.md) | Yığın boyutunu ayarlar. |
| [`/favor`](favor-optimize-for-architecture-specifics.md) | Belirli bir x64 mimarisi için en iyi duruma getirilmiş kodu üretir. Ya da AMD64 ve EM64T mimarilerinde belirli mikro mimariler için. |
| [`/FA`](fa-fa-listing-file.md) | Bir listeleme dosyası oluşturur. |
| [`/Fa`](fa-fa-listing-file.md) | Listeleme dosyası adını ayarlar. |
| [`/FC`](fc-full-path-of-source-code-file-in-diagnostics.md) | Tanılama metninde cl.exe geçirilen kaynak kodu dosyalarının tam yolunu görüntüleyin. |
| [`/Fd`](fd-program-database-file-name.md) | Program veritabanı dosyasını yeniden adlandırır. |
| [`/Fe`](fe-name-exe-file.md) | Yürütülebilir dosyayı yeniden adlandırır. |
| [`/FI`](fi-name-forced-include-file.md) | Belirtilen içerme dosyasını önceden işler. |
| [`/Fi`](fi-preprocess-output-file-name.md) | Önceden işlenmiş çıkış dosyası adını ayarlar. |
| [`/Fm`](fm-name-mapfile.md) | Bir harita dosyası oluşturur. |
| [`/Fo`](fo-object-file-name.md) | Bir nesne dosyası oluşturur. |
| [`/fp`](fp-specify-floating-point-behavior.md) | Kayan nokta davranışını belirtin. |
| [`/Fp`](fp-name-dot-pch-file.md) | Önceden derlenmiş üst bilgi dosyası adını belirtir. |
| [`/FR`](fr-fr-create-dot-sbr-file.md)<br /><br /> [`/Fr`](fr-fr-create-dot-sbr-file.md) | Tarayıcı dosyaları oluşturur. **`/Fr`** kullanım dışıdır. |
| [`/FS`](fs-force-synchronous-pdb-writes.md) | Tüm yazma işlemlerini program veritabanı (PDB) dosyasına MSPDBSRV.EXE aracılığıyla Serileştirmeye zorlar. |
| [`/FU`](fu-name-forced-hash-using-file.md) | Bir dosya adının, yönergesine geçirilmiş gibi kullanılmasını zorlar [`#using`](../../preprocessor/hash-using-directive-cpp.md) . |
| [`/Fx`](fx-merge-injected-code.md) | Eklenen kodu kaynak dosyayla birleştirir. |
| [`/GA`](ga-optimize-for-windows-application.md) | Windows uygulaması için kodu iyileştirir. |
| [`/Gd`](gd-gr-gv-gz-calling-convention.md) | **`__cdecl`** Çağırma kuralını kullanır (yalnızca x86). |
| [`/Ge`](ge-enable-stack-probes.md) | Kullanım dışı. Yığın araştırmalarını etkinleştirir. |
| [`/GF`](gf-eliminate-duplicate-strings.md) | Dize havuzunu izin vermez. |
| [`/GH`](gh-enable-pexit-hook-function.md) | Kanca işlevini çağırır `_pexit` . |
| [`/Gh`](gh-enable-penter-hook-function.md) | Kanca işlevini çağırır `_penter` . |
| [`/GL`](gl-whole-program-optimization.md) | Tüm program iyileştirmesini mümkün hale getirme. |
| [`/Gm`](gm-enable-minimal-rebuild.md) | Kullanım dışı. En az yeniden derlemeyi mümkün. |
| [`/GR`](gr-enable-run-time-type-information.md) | Çalışma zamanı tür bilgilerini (RTTı) etkinleştir. |
| [`/Gr`](gd-gr-gv-gz-calling-convention.md) | **`__fastcall`** Çağırma kuralını kullanır (yalnızca x86). |
| [`/GS`](gs-buffer-security-check.md) | Güvenlik denetimini arabelleğe alır. |
| [`/Gs`](gs-control-stack-checking-calls.md) | Yığın araştırmalarını denetler. |
| [`/GT`](gt-support-fiber-safe-thread-local-storage.md) | Statik iş parçacığı yerel depolama kullanılarak ayrılan veri için fiber güvenliğini destekler. |
| [`/guard:cf`](guard-enable-control-flow-guard.md) | Denetim akışı koruyucusu güvenlik denetimleri ekler. |
| [`/guard:ehcont`](guard-enable-eh-continuation-metadata.md) | EH devamlılık meta verilerini etkinleştirilir. |
| [`/Gv`](gd-gr-gv-gz-calling-convention.md) | **`__vectorcall`** Çağırma kuralını kullanır. (yalnızca x86 ve x64) |
| [`/Gw`](gw-optimize-global-data.md) | Tam program genel veri iyileştirmesini mümkün hale getirme. |
| [`/GX`](gx-enable-exception-handling.md) | Kullanım dışı. Zaman uyumlu özel durum işlemeyi mümkün. [`/EH`](eh-exception-handling-model.md)Bunun yerine kullanın. |
| [`/Gy`](gy-enable-function-level-linking.md) | İşlev düzeyinde bağlamayı mümkün. |
| [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) | Kullanım dışı. Aynı [`/RTC1`](rtc-run-time-error-checks.md) . |
| [`/Gz`](gd-gr-gv-gz-calling-convention.md) | **`__stdcall`** Çağırma kuralını kullanır (yalnızca x86). |
| [`/H`](h-restrict-length-of-external-names.md) | Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar. |
| [`/HELP`](help-compiler-command-line-help.md) | Derleyici seçeneklerini listeler. |
| [`/homeparams`](homeparams-copy-register-parameters-to-stack.md) | , Yazmaçlarda geçirilen parametreleri işlev girişi üzerine yığındaki konumlarına yazılacak şekilde zorlar. Bu derleyici seçeneği yalnızca x64 derleyicileri için geçerlidir (yerel ve çapraz derleme). |
| [`/hotpatch`](hotpatch-create-hotpatchable-image.md) | Hot-patchable bir görüntü oluşturur. |
| [`/I`](i-additional-include-directories.md) | İçerme dosyaları için bir dizin arar. |
| [`/J`](j-default-char-type-is-unsigned.md) | Varsayılan türü değiştirir **`char`** . |
| [`/JMC`](jmc.md) | Yerel C++ Yalnızca kendi kodum hata ayıklamayı destekler. |
| [`/kernel`](kernel-create-kernel-mode-binary.md) | Derleyici ve bağlayıcı, Windows çekirdeğinde yürütülebilecek bir ikili oluşturacak. |
| [`/LD`](md-mt-ld-use-run-time-library.md) | Dinamik bağlantı kitaplığı oluşturur. |
| [`/LDd`](md-mt-ld-use-run-time-library.md) | Bir hata ayıklama dinamik bağlantı kitaplığı oluşturur. |
| [`/link`](link-pass-options-to-linker.md) | BAĞLAMA için belirtilen seçeneği geçirir. |
| [`/LN`](ln-create-msil-module.md) | MSIL Modülü oluşturur. |
| [`/MD`](md-mt-ld-use-run-time-library.md) | MSVCRT. lib kullanarak çok iş parçacıklı bir DLL oluşturur. |
| [`/MDd`](md-mt-ld-use-run-time-library.md) | MSVCRTD. lib kullanarak bir hata ayıklama çok iş parçacıklı DLL oluşturur. |
| [`/MP`](mp-build-with-multiple-processes.md) | Birden çok işlem kullanarak birden çok kaynak dosyayı derler. |
| [`/MT`](md-mt-ld-use-run-time-library.md) | LıBCMT. lib kullanarak çok iş parçacıklı yürütülebilir dosya oluşturur. |
| [`/MTd`](md-mt-ld-use-run-time-library.md) | LıBCMTD. lib kullanarak çok iş parçacıklı yürütülebilir dosya oluşturur. |
| [`/nologo`](nologo-suppress-startup-banner-c-cpp.md) | Oturum açma başlığının görüntülenmesini önler. |
| [`/O1`](o1-o2-minimize-size-maximize-speed.md) | Küçük kod oluşturur. |
| [`/O2`](o1-o2-minimize-size-maximize-speed.md) | Hızlı kod oluşturur. |
| [`/Ob`](ob-inline-function-expansion.md) | Satır içi genişletmeyi denetler. |
| [`/Od`](od-disable-debug.md) | İyileştirmeyi devre dışı bırakır. |
| [`/Og`](og-global-optimizations.md) | Kullanım dışı. Genel iyileştirmeleri kullanır. |
| [`/Oi`](oi-generate-intrinsic-functions.md) | İç işlevleri oluşturur. |
| [`/openmp`](openmp-enable-openmp-2-0-support.md) | [`#pragma omp`](../../preprocessor/omp.md)Kaynak kodundaki yönergeyi izin vermez. |
| [`/Os`](os-ot-favor-small-code-favor-fast-code.md) | Küçük koda öncelik verir. |
| [`/Ot`](os-ot-favor-small-code-favor-fast-code.md) | Hızlı koda öncelik verir. |
| [`/Ox`](ox-full-optimization.md) | /O2 ' nin/GF veya/gi içermeyen bir alt kümesi. |
| [`/Oy`](oy-frame-pointer-omission.md) | Çerçeve işaretçisini atlar (yalnızca x86). |
| [`/P`](p-preprocess-to-a-file.md) | Önişlemci çıkışını bir dosyaya yazar. |
| [`/permissive-`](permissive-standards-conformance.md) | Standart uyumluluk modunu ayarlayın. |
| [`/Qfast_transcendentals`](qfast-transcendentals-force-fast-transcendentals.md) | Hızlı bir şekilde daha fazla işlem oluşturur. |
| [`/QIfist`](qifist-suppress-ftol.md) | Kullanım dışı. `_ftol`Bir kayan nokta türünden integral türüne dönüştürmenin gerekli olduğu durumlarda (yalnızca x86) bastırır. |
| [`/Qimprecise_fwaits`](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md) | `fwait`Bloklar içindeki komutları kaldırır **`try`** . |
| [`/QIntel-jcc-erratum`](qintel-jcc-erratum.md) | Intel JCC ermıtum mikro kod güncelleştirmesinin performans etkisini azaltır. |
| [/Qpar (otomatik paralel hale getirici)](qpar-auto-parallelizer.md) | [#Pragma loop ()](../../preprocessor/loop.md) yönergesiyle işaretlenen döngülerin otomatik paralelleştirilmesini mümkün hale getirme. |
| [`/Qsafe_fp_loads`](qsafe-fp-loads.md) | Kayan nokta değerleri için tamsayı taşıma yönergelerini kullanır ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır. |
| [`/Qspectre`](qspectre.md) | Belirli Spectre varyant 1 güvenlik açıklarına karşı hafifletmek için derleyici oluşturma yönergelerinin belirtir. |
| [`/Qspectre-load`](qspectre-load.md) | Yük yönergelerine göre Spectre güvenlik açıklarını hafifletmek için, serileştirme yönergelerinin derleme üretilmesini belirtir. |
| [`/Qspectre-load-cf`](qspectre-load-cf.md) | Belleği yükleyen denetim akışı yönergelerine göre Spectre güvenlik açıklarını azaltmak için derleyici oluşturma talimatlarını belirtir. |
| [`/Qvec-report`(Otomatik Vektörleştirici raporlama düzeyi)](qvec-report-auto-vectorizer-reporting-level.md) | Otomatik vektörleştirme için raporlama düzeylerine izin vermez. |
| [`/RTC`](rtc-run-time-error-checks.md) | Çalışma zamanı hata denetimini etkinleştirilir. |
| [`/sdl`](sdl-enable-additional-security-checks.md) | Ek güvenlik özellikleri ve uyarılar sunar. |
| [`/showIncludes`](showincludes-list-include-files.md) | Derleme sırasında içerme dosyaları listesini görüntüler. |
| [`/source-charset`](source-charset-set-source-character-set.md) | Kaynak karakter kümesini ayarla. |
| [`/std`](std-specify-language-standard-version.md) | C++ standart sürüm uyumluluk Seçicisi. |
| [`/Tc`](tc-tp-tc-tp-specify-source-file-type.md) | C kaynak dosyasını belirtir. |
| [`/TC`](tc-tp-tc-tp-specify-source-file-type.md) | Tüm kaynak dosyalarının C olduğunu belirtir. |
| [`/Tp`](tc-tp-tc-tp-specify-source-file-type.md) | Bir C++ kaynak dosyasını belirtir. |
| [`/TP`](tc-tp-tc-tp-specify-source-file-type.md) | Tüm kaynak dosyaları C++ olduğunu belirtir. |
| [`/U`](u-u-undefine-symbols.md) | Önceden tanımlanmış bir makroyu kaldırır. |
| [`/u`](u-u-undefine-symbols.md) | Önceden tanımlanmış tüm makroları kaldırır. |
| [`/utf-8`](utf-8-set-source-and-executable-character-sets-to-utf-8.md) | Kaynak ve yürütme karakter kümelerini UTF-8 olarak ayarlayın. |
| [`/V`](v-version-number.md) | Kullanım dışı. . Obj dosya sürümü dizesini ayarlar. |
| [`/validate-charset`](validate-charset-validate-for-compatible-characters.md) | UTF-8 dosyalarını yalnızca uyumlu karakterler için doğrulayın. |
| [`/vd`](vd-disable-construction-displacements.md) | Gizli vtordisp sınıf üyelerini bastırır veya etkinleştirirler. |
| [`/vmb`](vmb-vmg-representation-method.md) | Üye işaretçileri için en iyi temeli kullanır. |
| [`/vmg`](vmb-vmg-representation-method.md) | Üye işaretçileri için tam olarak kullanım sağlar. |
| [`/vmm`](vmm-vms-vmv-general-purpose-representation.md) | Birden çok devralma bildirir. |
| [`/vms`](vmm-vms-vmv-general-purpose-representation.md) | Tek devralma bildirir. |
| [`/vmv`](vmm-vms-vmv-general-purpose-representation.md) | Sanal devralmayı bildirir. |
| [`/volatile`](volatile-volatile-keyword-interpretation.md) | Volatile anahtar sözcüğünün nasıl yorumlandığını seçer. |
| [`/w`](compiler-option-warning-level.md) | Tüm uyarıları devre dışı bırakır. |
| [`/W0`, `/W1`, `/W2`, `/W3`, `/W4`](compiler-option-warning-level.md) | Hangi uyarı düzeyini çıkış için ayarlar. |
| [`/w1`, `/w2`, `/w3`, `/w4`](compiler-option-warning-level.md) | Belirtilen uyarının uyarı düzeyini ayarlar. |
| [`/Wall`](compiler-option-warning-level.md) | Varsayılan olarak devre dışı bırakılan uyarılar da dahil olmak üzere tüm uyarıları sunar. |
| [`/wd`](compiler-option-warning-level.md) | Belirtilen uyarıyı devre dışı bırakır. |
| [`/we`](compiler-option-warning-level.md) | Belirtilen uyarıyı hata olarak değerlendirir. |
| [`/WL`](wl-enable-one-line-diagnostics.md) | Komut satırından C++ kaynak kodunu derlerken hata ve uyarı iletileri için tek satırlık tanılamayı mümkün bir şekilde sunar. |
| [`/wo`](compiler-option-warning-level.md) | Belirtilen uyarıyı yalnızca bir kez görüntüler. |
| [`/Wp64`](wp64-detect-64-bit-portability-issues.md) | Kullanımdan kalktı. 64-bit taşınabilirlik sorunlarını algılar. |
| [`/Wv`](compiler-option-warning-level.md) | Derleyicinin belirtilen sürümünden sonra gelen uyarıları görüntüler. |
| [`/WX`](compiler-option-warning-level.md) | Tüm uyarıları hata olarak değerlendirir. |
| [`/X`](x-ignore-standard-include-paths.md) | Standart içerme dizinini yoksayar. |
| [`/Y-`](y-ignore-precompiled-header-options.md) | Geçerli derlemede tüm önceden derlenmiş üst bilgi derleyici seçeneklerini yoksayar. |
| [`/Yc`](yc-create-precompiled-header-file.md) | Önceden derlenmiş bir üstbilgi dosyası oluşturur. |
| [`/Yd`](yd-place-debug-information-in-object-file.md) | Kullanım dışı. Tüm nesne dosyalarındaki hata ayıklama bilgilerini tamamlar. [`/Zi`](z7-zi-zi-debug-information-format.md)Bunun yerine kullanın. |
| [`/Yl`](yl-inject-pch-reference-for-debug-library.md) | Hata ayıklama kitaplığı oluştururken bir PCH başvurusunu çıkartır |
| [`/Yu`](yu-use-precompiled-header-file.md) | Derleme sırasında önceden derlenmiş bir üstbilgi dosyası kullanır. |
| [`/Z7`](z7-zi-zi-debug-information-format.md) | C 7,0 uyumlu hata ayıklama bilgileri üretir. |
| [`/Za`](za-ze-disable-language-extensions.md) | Dil uzantılarını devre dışı bırakır. |
| [`/Zc`](zc-conformance.md) | Standart davranışları belirtir. |
| [`/Ze`](za-ze-disable-language-extensions.md) | Kullanım dışı. Dil uzantılarını izin vermez. |
| [`/Zf`](zf.md) | Paralel derlemelerde PDB oluşturma süresini geliştirir. |
| [`/Zg`](zg-generate-function-prototypes.md) | Visual Studio 2015 ' de kaldırıldı. İşlev prototipleri oluşturur. |
| [`/ZH`](zh.md) | Hata ayıklama bilgilerinde sağlama toplamı için MD5, SHA-1 veya SHA-256 belirtir. |
| [`/ZI`](z7-zi-zi-debug-information-format.md) | Düzenle ve devam et ile uyumlu bir program veritabanındaki hata ayıklama bilgilerini içerir. |
| [`/Zi`](z7-zi-zi-debug-information-format.md) | Tüm hata ayıklama bilgileri üretir. |
| [`/Zl`](zl-omit-default-library-name.md) | Varsayılan kitaplık adını. obj dosyasından kaldırır (yalnızca x86). |
| [`/Zm`](zm-specify-precompiled-header-memory-allocation-limit.md) | Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir. |
| [`/Zo`](zo-enhance-optimized-debugging.md) | İyileştirilmiş kod için gelişmiş hata ayıklama bilgileri oluşturur. |
| [`/Zp`](zp-struct-member-alignment.md) | Paketler yapısı üyeleri. |
| [`/Zs`](zs-syntax-check-only.md) | Yalnızca söz dizimini denetler. |
| [`/ZW`](zw-windows-runtime-compilation.md) | Windows Çalışma Zamanı çalıştırmak için bir çıkış dosyası üretir. |

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
