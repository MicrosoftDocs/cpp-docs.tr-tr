---
title: Kategorilere Göre Listelenen Derleyici Seçenekleri
description: Microsoft C/C++ derleyicisi komut satırı seçeneklerinin kategorisine göre başvuru listesi.
ms.date: 07/29/2020
helpviewer_keywords:
- compiler options, C++
ms.assetid: c4750dcf-dba0-4229-99b6-45cdecc11729
ms.openlocfilehash: bf12948658b5f7e3211c423b5302bc52d1b87729
ms.sourcegitcommit: 48b897797b3132ae934b1d191e3870c3c2466335
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/15/2020
ms.locfileid: "97514569"
---
# <a name="compiler-options-listed-by-category"></a>Kategorilere göre listelenen derleyici seçenekleri

Bu makale, derleyici seçeneklerinin kategorik bir listesini içerir. Alfabetik bir liste için bkz. [alfabetik olarak listelenen derleyici seçenekleri](compiler-options-listed-alphabetically.md).

## <a name="optimization"></a>İyileştirme

| Seçenek | Amaç |
|--|--|
| [`/O1`](o1-o2-minimize-size-maximize-speed.md) | Küçük kod oluşturur. |
| [`/O2`](o1-o2-minimize-size-maximize-speed.md) | Hızlı kod oluşturur. |
| [`/Ob`](ob-inline-function-expansion.md) | Satır içi genişletmeyi denetler. |
| [`/Od`](od-disable-debug.md) | İyileştirmeyi devre dışı bırakır. |
| [`/Og`](og-global-optimizations.md) | Kullanım dışı. Genel iyileştirmeleri kullanır. |
| [`/Oi`](oi-generate-intrinsic-functions.md) | İç işlevleri oluşturur. |
| [`/Os`](os-ot-favor-small-code-favor-fast-code.md) | Küçük koda öncelik verir. |
| [`/Ot`](os-ot-favor-small-code-favor-fast-code.md) | Hızlı koda öncelik verir. |
| [`/Ox`](ox-full-optimization.md) | /O2 ' nin/GF veya/gi içermeyen bir alt kümesi. |
| [`/Oy`](oy-frame-pointer-omission.md) | Çerçeve işaretçisini atlar. (yalnızca x86) |
| [`/favor`](favor-optimize-for-architecture-specifics.md) | Belirtilen bir mimari veya bir dizi mimaride en iyi duruma getirilmiş kodu üretir. |

## <a name="code-generation"></a>Kod oluşturma

| Seçenek | Amaç |
|--|--|
| [`/arch`](arch-x86.md) | Kod oluşturmada SSE veya SSE2 yönergelerini kullanın. (yalnızca x86) |
| [`/clr`](clr-common-language-runtime-compilation.md) | Ortak dil çalışma zamanında çalışacak bir çıktı dosyası üretir. |
| [`/EH`](eh-exception-handling-model.md) | Özel durum işleme modelini belirtir. |
| [`/fp`](fp-specify-floating-point-behavior.md) | Kayan nokta davranışını belirtir. |
| [`/GA`](ga-optimize-for-windows-application.md) | Windows uygulamaları için iyileştirir. |
| [`/Gd`](gd-gr-gv-gz-calling-convention.md) | **`__cdecl`** Çağırma kuralını kullanır. (yalnızca x86) |
| [`/Ge`](ge-enable-stack-probes.md) | Kullanım dışı. Yığın araştırmalarını etkinleştirir. |
| [`/GF`](gf-eliminate-duplicate-strings.md) | Dize havuzunu izin vermez. |
| [`/Gh`](gh-enable-penter-hook-function.md) | Kanca işlevini çağırır `_penter` . |
| [`/GH`](gh-enable-pexit-hook-function.md) | Kanca işlevini çağırır `_pexit` . |
| [`/GL`](gl-whole-program-optimization.md) | Tüm program iyileştirmesini mümkün hale getirme. |
| [`/Gm`](gm-enable-minimal-rebuild.md) | Kullanım dışı. En az yeniden derlemeyi mümkün. |
| [`/GR`](gr-enable-run-time-type-information.md) | Çalışma zamanı tür bilgilerini (RTTı) etkinleştir. |
| [`/Gr`](gd-gr-gv-gz-calling-convention.md) | **`__fastcall`** Çağırma kuralını kullanır. (yalnızca x86) |
| [`/GS`](gs-buffer-security-check.md) | Arabellek güvenliğini denetler. |
| [`/Gs`](gs-control-stack-checking-calls.md) | Yığın araştırmalarını denetler. |
| [`/GT`](gt-support-fiber-safe-thread-local-storage.md) | Statik iş parçacığı yerel depolama alanı kullanılarak ayrılan veriler için fiber güvenliği destekler. |
| [`/guard:cf`](guard-enable-control-flow-guard.md) | Denetim akışı koruyucusu güvenlik denetimleri ekler. |
| [`/guard:ehcont`](guard-enable-eh-continuation-metadata.md) | EH devamlılık meta verilerini etkinleştirilir. |
| [`/Gv`](gd-gr-gv-gz-calling-convention.md) | **`__vectorcall`** Çağırma kuralını kullanır. (yalnızca x86 ve x64) |
| [`/Gw`](gw-optimize-global-data.md) | Tam program genel veri iyileştirmesini mümkün hale getirme. |
| [`/GX`](gx-enable-exception-handling.md) | Kullanım dışı. Zaman uyumlu özel durum işlemeyi mümkün. [`/EH`](eh-exception-handling-model.md)Bunun yerine kullanın. |
| [`/Gy`](gy-enable-function-level-linking.md) | İşlev düzeyinde bağlamayı mümkün. |
| [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) | Kullanım dışı. Hızlı denetimleri mümkün. (Aynı [`/RTC1`](rtc-run-time-error-checks.md) ) |
| [`/Gz`](gd-gr-gv-gz-calling-convention.md) | **`__stdcall`** Çağırma kuralını kullanır. (yalnızca x86) |
| [`/homeparams`](homeparams-copy-register-parameters-to-stack.md) | , Yazmaçlarda geçirilen parametreleri işlev girişi üzerine yığındaki konumlarına yazılacak şekilde zorlar. Bu derleyici seçeneği yalnızca x64 derleyicileri için geçerlidir (yerel ve çapraz derleme). |
| [`/hotpatch`](hotpatch-create-hotpatchable-image.md) | Düzeltme Eki eklenebilen bir görüntü oluşturur. |
| [`/Qfast_transcendentals`](qfast-transcendentals-force-fast-transcendentals.md) | Hızlı bir şekilde daha fazla işlem oluşturur. |
| [`/QIfist`](qifist-suppress-ftol.md) | Kullanım dışı. `_ftol`Bir kayan nokta türünden integral türüne dönüştürme gerektiğinde yardımcı işlevin çağrısını bastırır. (yalnızca x86) |
| [`/Qimprecise_fwaits`](qimprecise-fwaits-remove-fwaits-inside-try-blocks.md) | `fwait`Bloklar içindeki komutları kaldırır **`try`** . |
| [`/QIntel-jcc-erratum`](qintel-jcc-erratum.md) | Intel JCC ermıtum mikro kod güncelleştirmesinin performans etkisini azaltır. |
| [`/Qpar`](qpar-auto-parallelizer.md) | Döngülerin otomatik paralelleştirilmesini mümkün hale getirme. |
| [`/Qpar-report`](qpar-report-auto-parallelizer-reporting-level.md) | Otomatik paralelleştirme için raporlama düzeylerini mümkün hale getirme. |
| [`/Qsafe_fp_loads`](qsafe-fp-loads.md) | Kayan nokta değerleri için tamsayı taşıma yönergelerini kullanır ve belirli kayan nokta yükleme iyileştirmelerini devre dışı bırakır. |
| [`/Qspectre`](qspectre.md) | Spectre saldırılarına yönelik bir sınıf için CVE 2017-5753 için azaltıcı etkenleri etkinleştirin. |
| [`/Qspectre-load`](qspectre-load.md) | Her yük yönergesi için serileştirme yönergeleri oluşturun. |
| [`/Qspectre-load-cf`](qspectre-load-cf.md) | Belleği yükleyen her denetim akışı yönergesi için serileştirme yönergeleri oluşturun. |
| [`/Qvec-report`](qvec-report-auto-vectorizer-reporting-level.md) | Otomatik vektörleştirme için raporlama düzeylerine izin vermez. |
| [`/RTC`](rtc-run-time-error-checks.md) | Çalışma zamanı hata denetimini etkinleştirilir. |
| [`/volatile`](volatile-volatile-keyword-interpretation.md) | Volatile anahtar sözcüğünün nasıl yorumlandığını seçer. |

## <a name="output-files"></a>Çıkış dosyaları

| Seçenek | Amaç |
|--|--|
| [`/doc`](doc-process-documentation-comments-c-cpp.md) | Belge açıklamalarını bir XML dosyasına işler. |
| [`/FA`](fa-fa-listing-file.md) | Bir derleme listeleme dosyası yapılandırır. |
| [`/Fa`](fa-fa-listing-file.md) | Bir derleme listeleme dosyası oluşturur. |
| [`/Fd`](fd-program-database-file-name.md) | Program veritabanı dosyasını yeniden adlandırır. |
| [`/Fe`](fe-name-exe-file.md) | Yürütülebilir dosyayı yeniden adlandırır. |
| [`/Fi`](fi-preprocess-output-file-name.md) | Önceden işlenmiş çıkış dosyası adını belirtir. |
| [`/Fm`](fm-name-mapfile.md) | Bir mapfile oluşturur. |
| [`/Fo`](fo-object-file-name.md) | Bir nesne dosyası oluşturur. |
| [`/Fp`](fp-name-dot-pch-file.md) | Önceden derlenmiş üst bilgi dosyası adını belirtir. |
| [`/FR`, `/Fr`](fr-fr-create-dot-sbr-file.md) | Oluşturulan *`.sbr`* tarayıcı dosyalarını adlandırın. |

## <a name="preprocessor"></a>Ön işlemci

| Seçenek | Amaç |
|--|--|
| [`/AI`](ai-specify-metadata-directories.md) | [#Using](../../preprocessor/hash-using-directive-cpp.md) yönergesine geçirilen dosya başvurularını çözümlemek için arama yapılacak bir dizin belirtir. |
| [`/C`](c-preserve-comments-during-preprocessing.md) | Ön işleme sırasında açıklamaları korur. |
| [`/D`](d-preprocessor-definitions.md) | Sabitleri ve makroları tanımlar. |
| [`/E`](e-preprocess-to-stdout.md) | Önişlemci çıkışını standart çıktıya kopyalar. |
| [`/EP`](ep-preprocess-to-stdout-without-hash-line-directives.md) | Önişlemci çıkışını standart çıktıya kopyalar. |
| [`/FI`](fi-name-forced-include-file.md) | Belirtilen içerme dosyasını önceden işler. |
| [`/FU`](fu-name-forced-hash-using-file.md) | [#Using](../../preprocessor/hash-using-directive-cpp.md) yönergesine geçirilmiş gibi bir dosya adının kullanımını zorlar. |
| [`/Fx`](fx-merge-injected-code.md) | Eklenen kodu kaynak dosyayla birleştirir. |
| [`/I`](i-additional-include-directories.md) | İçerme dosyaları için bir dizin arar. |
| [`/P`](p-preprocess-to-a-file.md) | Önişlemci çıkışını bir dosyaya yazar. |
| [`/U`](u-u-undefine-symbols.md) | Önceden tanımlanmış bir makroyu kaldırır. |
| [`/u`](u-u-undefine-symbols.md) | Önceden tanımlanmış tüm makroları kaldırır. |
| [`/X`](x-ignore-standard-include-paths.md) | Standart içerme dizinini yoksayar. |

## <a name="language"></a>Dil

| Seçenek | Amaç |
|--|--|
| [`/constexpr`](constexpr-control-constexpr-evaluation.md) | **`constexpr`** Derleme zamanında değerlendirmeyi denetleyin. |
| [`/openmp`](openmp-enable-openmp-2-0-support.md) | [`#pragma omp`](../../preprocessor/omp.md)Kaynak kodunda etkinleştirilir. |
| [`/vd`](vd-disable-construction-displacements.md) | Gizli sınıf üyelerini bastırır veya izin vermez `vtordisp` . |
| [`/vmb`](vmb-vmg-representation-method.md) | Üye işaretçileri için en iyi temeli kullanır. |
| [`/vmg`](vmb-vmg-representation-method.md) | Üye işaretçileri için tam olarak kullanım sağlar. |
| [`/vmm`](vmm-vms-vmv-general-purpose-representation.md) | Birden çok devralma bildirir. |
| [`/vms`](vmm-vms-vmv-general-purpose-representation.md) | Tek devralma bildirir. |
| [`/vmv`](vmm-vms-vmv-general-purpose-representation.md) | Sanal devralmayı bildirir. |
| [`/Z7`](z7-zi-zi-debug-information-format.md) | C 7,0 uyumlu hata ayıklama bilgileri üretir. |
| [`/Za`](za-ze-disable-language-extensions.md) | C89 Language Extensions 'ı devre dışı bırakır. |
| [`/Zc`](zc-conformance.md) | Altında Standart davranışı belirtir [`/Ze`](za-ze-disable-language-extensions.md) . |
| [`/Ze`](za-ze-disable-language-extensions.md) | Kullanım dışı. C89 Language Extensions 'ı sunar. |
| [`/Zf`](zf.md) | Paralel derlemelerde PDB oluşturma süresini geliştirir. |
| [`/ZH`](zh.md) | Hata ayıklama bilgilerinde sağlama toplamı için MD5, SHA-1 veya SHA-256 belirtir. |
| [`/ZI`](z7-zi-zi-debug-information-format.md) | Düzenle ve devam et ile uyumlu bir program veritabanındaki hata ayıklama bilgilerini içerir. (yalnızca x86) |
| [`/Zi`](z7-zi-zi-debug-information-format.md) | Tüm hata ayıklama bilgileri üretir. |
| [`/Zl`](zl-omit-default-library-name.md) | Varsayılan kitaplık adını *`.obj`* dosyadan kaldırır. |
| [`/Zp`](zp-struct-member-alignment.md)*n* | Paketler yapısı üyeleri. |
| [`/Zs`](zs-syntax-check-only.md) | Yalnızca söz dizimini denetler. |
| [`/ZW`](zw-windows-runtime-compilation.md) | Windows Çalışma Zamanı çalıştırmak için bir çıkış dosyası üretir. |

## <a name="linking"></a>Bağlama

| Seçenek | Amaç |
|--|--|
| [`/F`](f-set-stack-size.md) | Yığın boyutunu ayarlar. |
| [`/LD`](md-mt-ld-use-run-time-library.md) | Dinamik bağlantı kitaplığı oluşturur. |
| [`/LDd`](md-mt-ld-use-run-time-library.md) | Bir hata ayıklama dinamik bağlantı kitaplığı oluşturur. |
| [`/link`](link-pass-options-to-linker.md) | BAĞLAMA için belirtilen seçeneği geçirir. |
| [`/LN`](ln-create-msil-module.md) | MSIL Modülü oluşturur. |
| [`/MD`](md-mt-ld-use-run-time-library.md) | *Msvcrt. lib* kullanarak çok iş PARÇACıKLı bir dll oluşturmak için derler. |
| [`/MDd`](md-mt-ld-use-run-time-library.md) | *Msvcrtd. lib* kullanarak bir hata ayıklama çok Iş parçacıklı DLL oluşturmak için derler. |
| [`/MT`](md-mt-ld-use-run-time-library.md) | *LIBCMT. lib* kullanarak çok iş parçacıklı yürütülebilir dosya oluşturmak için derler. |
| [`/MTd`](md-mt-ld-use-run-time-library.md) | *LIBCMTD. lib* kullanarak bir hata ayıklama çok iş parçacıklı yürütülebilir dosyası oluşturmak için derler. |

## <a name="miscellaneous"></a>Çeşitli

| Seçenek | Amaç |
|--|--|
| [`/?`](help-compiler-command-line-help.md) | Derleyici seçeneklerini listeler. |
| [`@`](at-specify-a-compiler-response-file.md) | Bir yanıt dosyası belirtir. |
| [`/analyze`](analyze-code-analysis.md) | Kod analizini sunar. |
| [`/bigobj`](bigobj-increase-number-of-sections-in-dot-obj-file.md) | Bir. obj dosyasındaki adreslenebilir bölüm sayısını artırır. |
| [`/c`](c-compile-without-linking.md) | Bağlama olmadan derler. |
| [`/cgthreads`](cgthreads-code-generation-threads.md) | İyileştirme ve kod oluşturma için kullanılacak *cl.exe* iş parçacığı sayısını belirtir. |
| [`/errorReport`](errorreport-report-internal-compiler-errors.md) | Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
| [`/FC`](fc-full-path-of-source-code-file-in-diagnostics.md) | Tanılama metninde *cl.exe* geçirilen kaynak kodu dosyalarının tam yolunu görüntüler. |
| [`/FS`](fs-force-synchronous-pdb-writes.md) | *MSPDBSRV.EXE* aracılığıyla SERILEŞTIRILMESI için pdb dosyasına yazmaları zorlar. |
| [`/H`](h-restrict-length-of-external-names.md) | Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar. |
| [`/HELP`](help-compiler-command-line-help.md) | Derleyici seçeneklerini listeler. |
| [`/J`](j-default-char-type-is-unsigned.md) | Varsayılan türü değiştirir **`char`** . |
| [`/JMC`](jmc.md) | Yerel C++ Yalnızca kendi kodum hata ayıklamayı destekler. |
| [`/kernel`](kernel-create-kernel-mode-binary.md) | Derleyici ve bağlayıcı, Windows çekirdeğinde yürütülebilecek bir ikili oluşturacak. |
| [`/MP`](mp-build-with-multiple-processes.md) | Aynı anda birden fazla kaynak dosyası oluşturur. |
| [`/nologo`](nologo-suppress-startup-banner-c-cpp.md) | Oturum açma başlığının görüntülenmesini önler. |
| [`/sdl`](sdl-enable-additional-security-checks.md) | Ek güvenlik özellikleri ve uyarılar sunar. |
| [`/showIncludes`](showincludes-list-include-files.md) | Derleme sırasında tüm içerme dosyalarının listesini görüntüler. |
| [`/sourceDependencies`](sourcedependencies.md) | Üst bilgileri, modülleri ve diğer Kaynak bağımlılıklarını listeleyin. |
| [`/Tc`](tc-tp-tc-tp-specify-source-file-type.md) | C kaynak dosyasını belirtir. |
| [`/TC`](tc-tp-tc-tp-specify-source-file-type.md) | Tüm kaynak dosyalarının C olduğunu belirtir. |
| [`/Tp`](tc-tp-tc-tp-specify-source-file-type.md) | Bir C++ kaynak dosyasını belirtir. |
| [`/TP`](tc-tp-tc-tp-specify-source-file-type.md) | Tüm kaynak dosyaları C++ olduğunu belirtir. |
| [`/V`](v-version-number.md) | Kullanım dışı. Sürüm dizesini ayarlar. |
| [`/w`](compiler-option-warning-level.md) | Tüm uyarıları devre dışı bırakır. |
| [`/W0`, `/W1`, `/W2`, `/W3`, `/W4`](compiler-option-warning-level.md) | Çıkış uyarı düzeyini ayarlar. |
| [`/w1`, `/w2`, `/w3`, `/w4`](compiler-option-warning-level.md) | Belirtilen uyarı için uyarı düzeyini ayarlar. |
| [`/Wall`](compiler-option-warning-level.md) | Varsayılan olarak devre dışı bırakılan uyarılar da dahil olmak üzere tüm uyarıları sunar. |
| [`/wd`](compiler-option-warning-level.md) | Belirtilen uyarıyı devre dışı bırakır. |
| [`/we`](compiler-option-warning-level.md) | Belirtilen uyarıyı hata olarak değerlendirir. |
| [`/WL`](wl-enable-one-line-diagnostics.md) | Komut satırından C++ kaynak kodunu derlerken hata ve uyarı iletileri için tek satırlık tanılamayı mümkün bir şekilde sunar. |
| [`/wo`](compiler-option-warning-level.md) | Belirtilen uyarıyı yalnızca bir kez görüntüler. |
| [`/Wv`](compiler-option-warning-level.md) | Derleyicinin sonraki sürümlerinde tanıtılan uyarıları devre dışı bırakır. |
| [`/WX`](compiler-option-warning-level.md) | Uyarıları hata olarak değerlendirir. |
| [`/Yc`](yc-create-precompiled-header-file.md) | *`.PCH`* Dosya oluşturun. |
| [`/Yd`](yd-place-debug-information-in-object-file.md) | Kullanım dışı. Tüm nesne dosyalarındaki hata ayıklama bilgilerini tamamlar. [`/Zi`](z7-zi-zi-debug-information-format.md)Bunun yerine kullanın. |
| [`/Yl`](yl-inject-pch-reference-for-debug-library.md) | Bir hata ayıklama kitaplığı oluştururken PCH başvurusunu çıkartır. |
| [`/Yu`](yu-use-precompiled-header-file.md) | Derleme sırasında önceden derlenmiş bir üstbilgi dosyası kullanır. |
| [`/Y-`](y-ignore-precompiled-header-options.md) | Geçerli derlemede tüm önceden derlenmiş üst bilgi derleyici seçeneklerini yoksayar. |
| [`/Zm`](zm-specify-precompiled-header-memory-allocation-limit.md) | Önceden derlenmiş üst bilgi bellek ayırma sınırını belirtir. |
| [`/await`](await-enable-coroutine-support.md) | Eş yordamlar (sürdürülebilir Functions) uzantılarını etkinleştirin. |
| [`/source-charset`](source-charset-set-source-character-set.md) | Kaynak karakter kümesini ayarla. |
| [`/execution-charset`](execution-charset-set-execution-character-set.md) | Yürütme karakter kümesini ayarlayın. |
| [`/utf-8`](utf-8-set-source-and-executable-character-sets-to-utf-8.md) | Kaynak ve yürütme karakter kümelerini UTF-8 olarak ayarlayın. |
| [`/validate-charset`](validate-charset-validate-for-compatible-characters.md) | UTF-8 dosyalarını yalnızca uyumlu karakterler için doğrulayın. |
| [`/diagnostics`](diagnostics-compiler-diagnostic-options.md) | Tanılama iletilerinin biçimini denetler. |
| [`/permissive-`](permissive-standards-conformance.md) | Standart uyumluluk modunu ayarlayın. |
| [`/std`](std-specify-language-standard-version.md) | C++ standart sürüm uyumluluk Seçicisi. |

## <a name="experimental-options"></a>Deneysel seçenekler

Deneysel seçenekler yalnızca derleyicinin belirli sürümleri tarafından desteklenir. Ayrıca farklı derleyici sürümlerinde farklı davranabilir. Genellikle, deneysel seçeneklere yönelik belgeler yalnızca en iyi veya yalnızca [Microsoft C++ ekip blogu](https://devblogs.microsoft.com/cppblog/)' nda bulunur.

| Seçenek | Amaç |
|--|--|
| [`/experimental:module`](experimental-module.md) | Deneysel modül desteğini izin vermez. |
| [`/experimental:preprocessor`](experimental-preprocessor.md) | Kullanım dışı. Deneysel uyumsuz Önişlemci desteğini sunar. Kullanırsınız [`/Zc:preprocessor`](zc-preprocessor.md) |

## <a name="deprecated-and-removed-compiler-options"></a>Kullanım dışı ve kaldırılmış derleyici seçenekleri

| Seçenek | Amaç |
|--|--|
| [`/clr:noAssembly`](clr-common-language-runtime-compilation.md) | Kullanım dışı. Bunun yerine [ `/LN` (MSIL Modülü Oluştur)](ln-create-msil-module.md) kullanın. |
| [`/errorReport`](errorreport-report-internal-compiler-errors.md) | Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
| [`/Fr`](fr-fr-create-dot-sbr-file.md) | Kullanım dışı. Yerel değişkenler olmadan bir tarama bilgisi dosyası oluşturur. |
| [`/Ge`](ge-enable-stack-probes.md) | Kullanım dışı. Yığın araştırmalarını etkinleştirir. Varsayılan olarak açık. |
| [`/Gm`](gm-enable-minimal-rebuild.md) | Kullanım dışı. En az yeniden derlemeyi mümkün. |
| [`/GX`](gx-enable-exception-handling.md) | Kullanım dışı. Zaman uyumlu özel durum işlemeyi mümkün. [`/EH`](eh-exception-handling-model.md)Bunun yerine kullanın. |
| [`/GZ`](gz-enable-stack-frame-run-time-error-checking.md) | Kullanım dışı. Hızlı denetimleri mümkün. [`/RTC1`](rtc-run-time-error-checks.md)Bunun yerine kullanın. |
| [`/H`](h-restrict-length-of-external-names.md) | Kullanım dışı. Dış (ortak) adların uzunluğunu kısıtlar. |
| [`/Og`](og-global-optimizations.md) | Kullanım dışı. Genel iyileştirmeleri kullanır. |
| [`/QIfist`](qifist-suppress-ftol.md) | Kullanım dışı. Bir kayan nokta türünden integral türüne nasıl dönüştüreceğiniz belirlemek için kullanılır. |
| [`/V`](v-version-number.md) | Kullanım dışı. *`.obj`* Dosya sürümü dizesini ayarlar. |
| [`/Wp64`](wp64-detect-64-bit-portability-issues.md) | Kullanımdan kalktı. 64-bit taşınabilirlik sorunlarını algılar. |
| [`/Yd`](yd-place-debug-information-in-object-file.md) | Kullanım dışı. Tüm nesne dosyalarındaki hata ayıklama bilgilerini tamamlar. [`/Zi`](z7-zi-zi-debug-information-format.md)Bunun yerine kullanın. |
| [`/Zc:forScope-`](zc-forscope-force-conformance-in-for-loop-scope.md) | Kullanım dışı. For döngüsü kapsamında uygunluğu devre dışı bırakır. |
| [`/Ze`](za-ze-disable-language-extensions.md) | Kullanım dışı. Dil uzantılarını izin vermez. |
| [`/Zg`](zg-generate-function-prototypes.md) | Visual Studio 2015 ' de kaldırıldı. İşlev prototipleri oluşturur. |

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ oluşturma başvurusu](c-cpp-building-reference.md)\
[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
