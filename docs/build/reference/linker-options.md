---
title: Bağlayıcı seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7a7fe51c6f49af4fdd232b860b1f9243c1ea462
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753636"
---
# <a name="linker-options"></a>Bağlayıcı Seçenekleri

Genel nesne dosya biçimi (COFF) nesne dosyaları ve kitaplıkları bir yürütülebilir dosyanın (.exe) dosyayı oluşturmak için veya bir dinamik bağlantı kitaplığı (DLL) LINK.exe bağlar.

Aşağıdaki tabloda LINK.exe seçeneklerini listeler. BAĞLANTI hakkında daha fazla bilgi için bkz:

- [Derleyici Denetimindeki LINK Seçenekleri](../../build/reference/compiler-controlled-link-options.md)

- [LINK Giriş Dosyaları](../../build/reference/link-input-files.md)

- [LINK Çıktısı](../../build/reference/link-output.md)

- [Ayrılmış Sözcükler](../../build/reference/reserved-words.md)

Komut satırında bağlayıcı seçenekleri büyük küçük harfe duyarlı değildir; Örneğin, / temel ve /BASE aynı şeyi anlamına gelir. Komut satırında veya Visual Studio'da her seçenek belirtme hakkında daha fazla bilgi için bu seçeneği belgelerine bakın.

Kullanabileceğiniz [açıklama](../../preprocessor/comment-c-cpp.md) pragma bazı bağlayıcı seçeneklerini belirtin.

|Seçenek|Amaç|
|------------|-------------|
|[@](../../build/reference/at-specify-a-linker-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ ALIGN](../../build/reference/align-section-alignment.md)|Her bölüm hizalamasını belirtir.|
|[/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|DLL bağlanamaz belirtir.|
|[/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|Bildirim arama davranışını belirtir.|
|[/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|Uygulama bir appcontaıner işlem ortamında çalıştırma olup olmadığını belirtir.|
|[/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)|Ekler <xref:System.Diagnostics.DebuggableAttribute> yönetilen görüntüsüne.|
|[/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|Yönetilen kaynak bağlantısını oluşturur.|
|[/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|Bir Microsoft Ara dili (MSIL) modülü derlemeye içeri aktarılması gerektiğini belirtir.|
|[/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|Yönetilen kaynak dosyasını, bir derlemede katıştırır.|
|[/ BASE](../../build/reference/base-base-address.md)|Program için bir taban adresi ayarlar.|
|[/ CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|Bağlama zamanı kodu oluşturma belirtildiğinde en iyi duruma getirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.|
|[/ CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)|Bir CLR görüntü türünü (IJW, saf ya da güvenli) ayarlar.|
|[/ CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|Son hata kodu P/Invoke mekanizma adlı işlevlerin korur.|
|[/ CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|CLR programınızın giriş noktası uygulamak için iş parçacığı özniteliği belirtir.|
|[/ CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute.md)|Yönetilen koddan yerel DLL'leri çağrı bağlayıcı oluşturulan PInvoke saplamalar için bağlayıcı SuppressUnmanagedCodeSecurity özniteliğine uygulanıp uygulanmayacağını belirtir.|
|[/ DEBUG](../../build/reference/debug-generate-debug-info.md)|Hata ayıklama bilgisi oluşturur.|
|[/ DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|Hata ayıklama bilgileri dahil etmek için hangi verilerin belirtir.|
|[/ DEF](../../build/reference/def-specify-module-definition-file.md)|Bir modül-tanımlama (.def) dosyası için bağlayıcı geçirir.|
|[/ DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|Dış başvurular çözümlenmiş olduğunda Belirtilen kitaplık arar.|
|[/ DELAY](../../build/reference/delay-delay-load-import-settings.md)|DLL'leri Gecikmeli yüklenmesini denetler.|
|[/ DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|Belirtilen DLL Gecikmeli yüklenmesini neden olur.|
|[/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|Bir derlemeyi kısmen imzalar.|
|[/ DEPENDENTLOADFLAG](dependentloadflag.md)|Varsayılan bayrakları bağımlı DLL yükleri ayarlar.|
|[/ DLL](../../build/reference/dll-build-a-dll.md)|DLL oluşturur.|
|[/ DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|Çekirdek modu sürücüsü oluşturur.|
|[/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|Rastgele yükleme zamanında adres alanı düzeni rastgele seçimini (ASLR) özelliğini kullanarak rebased yürütülebilir bir görüntü oluşturulup oluşturulmayacağını belirtir.|
|[/ ENTRY](../../build/reference/entry-entry-point-symbol.md)|Başlangıç adresini ayarlar.|
|[/ errorreport](../../build/reference/errorreport-report-internal-linker-errors.md)|Dahili bağlayıcı hatalarını Microsoft'a raporlar.|
|[/ DIŞARI AKTARMA](../../build/reference/export-exports-a-function.md)|İşlevi dışarı aktarır.|
|[/ FILEALIGN](../../build/reference/filealign.md)|Belirtilen değer'ün katları çıkış dosyada bölümlere hizalar.|
|[/ SABİT](../../build/reference/fixed-fixed-base-address.md)|Yüklenebilir bir program, yalnızca kendi tercih edilen temel adres oluşturur.|
|[/ FORCE](../../build/reference/force-force-file-output.md)|Hatta çözümlenmemiş simgeler veya birden fazla kez tanımlanmış simgelerle tamamlamak için bir bağlantı zorlar.|
|[/ FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|Çalışırken düzeltme bir görüntü oluşturur.|
|[/ GENPROFILE, /FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Bu seçeneklerin ikisi de profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyasının üretilmesi belirtin. / GENPROFILE ve /FASTGENPROFILE farklı varsayılan parametrelerini kullanın.|
|[/ GUARD](../../build/reference/guard-enable-guard-checks.md)|Denetim akışı koruyucu koruması sağlar.|
|[/HEAP](../../build/reference/heap-set-heap-size.md)|Yığın boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md)|Yüksek entropi 64-bit adres boşluğu düzeni rastgele seçimini (ASLR) için destek belirtir.|
|[/ IDLOUT](../../build/reference/idlout-name-midl-output-files.md)|.İdl dosya ve diğer MIDL çıktı dosyalarını adını belirtir.|
|[/ IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|Belirtilen bağlayıcı uyarılarını çıktısını gizler.|
|[/ IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|Öznitelik bilgileri .idl dosyasına işlenmesini önler.|
|[/ IMPLIB](../../build/reference/implib-name-import-library.md)|Varsayılan içeri aktarma kitaplığı adı geçersiz kılar.|
|[/ INCLUDE](../../build/reference/include-force-symbol-references.md)|Zorlar başvuruları simge.|
|[/ INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|Denetimleri artımlı bağlanıyor.|
|[/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|Modül yükleme zamanında imza denetimi gerekli belirtir.|
|[/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Derlemeyi imzalamak için anahtar kapsayıcısını belirtir.|
|[/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Bir anahtar ya da derlemeyi imzalamak için anahtar çifti belirtir.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|Uygulama adresleri iki gigabayttan büyük desteklediğini derleyici bildirir|
|[/ LIBPATH](../../build/reference/libpath-additional-libpath.md)|Ortam Kitaplığı yol önce aramak için bir yol belirtir.|
|[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|Bağlama zamanı kodu oluşturma belirtir.|
|[/ MACHINE](../../build/reference/machine-specify-target-platform.md)|Hedef platformu belirtir.|
|[/ BİLDİRİMİ](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|Yan yana bildirim dosyası oluşturur ve isteğe bağlı olarak ikili katıştırır.|
|[/ MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|Belirten bir \<dependentAssembly > bildirim dosyası bölümünde.|
|[/ MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|Bildirim dosyası varsayılan adını değiştirir.|
|[/ MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|Bir bildirim giriş dosyası işlemek ve ikili katıştırmak bağlayıcı için belirtir. Birden fazla bildirim giriş dosyası belirtmek için bu seçeneği birden çok kez kullanabilirsiniz.|
|[/ MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|Kullanıcı Hesabı Denetimi (UAC) bilgisi program bildiriminde ekli olup olmadığını belirtir.|
|[/MAP](../../build/reference/map-generate-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/ MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|Belirtilen bilgileri eşlem dosyasına içerir.|
|[/ MERGE](../../build/reference/merge-combine-sections.md)|Bölümler birleştirir.|
|[/ MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|MIDL komut satırı seçeneklerini belirtir.|
|[/ NATVIS](../../build/reference/natvis-add-natvis-to-pdb.md)|Hata ayıklayıcı görselleştiriciler Natvis dosyasından PDB ekler.|
|[/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|.NET Framework derleme oluşturulmasını önler.|
|[/ NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|Tüm yoksayar (veya belirtilen) dış başvuruları çözümlendiği zaman kitaplıkları varsayılan.|
|[/ NOENTRY](../../build/reference/noentry-no-entry-point.md)|Yalnızca kaynak DLL oluşturur.|
|[/ NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|Başlangıç başlığını gizler.|
|[/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde doğrulanmış olarak işaretler.|
|[/ OPT](../../build/reference/opt-optimizations.md)|BAĞLANTI iyileştirmeler denetler.|
|[/ ORDER](../../build/reference/order-put-functions-in-order.md)|COMDATs önceden belirlenmiş bir sırayla görüntüye yerleştirir.|
|[/ OUT](../../build/reference/out-output-file-name.md)|Çıktı dosyası adını belirtir.|
|[/PDB](../../build/reference/pdb-use-program-database.md)|Program veritabanı (PDB) dosyası oluşturur.|
|[/ PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|PDB dosyası kaydetmek için farklı bir konuma kullanır.|
|[/ PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|Hiçbir özel sembolleri sahip bir program veritabanı (PDB) dosyası oluşturur.|
|[/ PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|Profil temelli iyileştirmeler için .pgd dosyasını belirtir.|
|[/POGOSAFEMODE](../../build/reference/pogosafemode-linker-option.md)|**Artık kullanılmayan** bir iş parçacığı izlenmiş PGO yapı oluşturur.|
|[/ PROFİL](../../build/reference/profile-performance-tools-profiler.md)|Performans araçları Profil Oluşturucu ile kullanılan bir çıktı dosyası oluşturur.|
|[/RELEASE](../../build/reference/release-set-the-checksum.md)|Sağlama toplamı .exe üstbilgisinde ayarlar.|
|[/ SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)|Görüntünün güvenli özel durum işleyicileri tablosu içerecek belirtir.|
|[/ SECTION](../../build/reference/section-specify-section-attributes.md)|Bir bölüm özniteliklerini geçersiz kılar.|
|[/STACK](../../build/reference/stack-stack-allocations.md)|Yığın boyutunu bayt cinsinden ayarlar.|
|[/ STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|MS-DOS saplama programını bir Win32 programı ekler.|
|[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|İşletim sistemi .exe dosyasını çalıştırın anlatır.|
|[/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|Bunu çalıştırılmadan önce bağlayıcı çıktısı için takas dosyası kopyalamak için işletim sistemi söyler.|
|[/ TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|Bağlayıcı tarafından oluşturulan tür kitaplığı kaynak Kimliğini belirtir.|
|[/ TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|.Tlb dosyası ve diğer MIDL çıktı dosyalarını adını belirtir.|
|[/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|Özellikle Terminal sunucusu altında çalışması için tasarlanmış bir uygulama oluşturur.|
|[/USEPROFILE](../../build/reference/useprofile.md)|En iyi duruma getirilmiş bir görüntü oluşturmak için en iyi duruma getirme eğitim verileri profil temelli kullanır.|
|[/ VERBOSE](../../build/reference/verbose-print-progress-messages.md)|Bağlayıcı ilerleme iletilerini yazdırır.|
|[/VERSION](../../build/reference/version-version-information.md)|Sürüm numarası atar.|
|[/ WHOLEARCHIVE](../../build/reference/wholearchive-include-all-library-object-files.md)|Belirtilen statik kitaplıklarından her nesne dosyası içerir.|
|[/ WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Windows çalışma zamanı meta veri dosyasının oluşturulmasını sağlar.|
|[/ WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)|Tarafından oluşturulan Windows çalışma zamanı meta verileri (winmd) çıktı dosyası için dosya adını belirten [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) bağlayıcı seçeneği.|
|[/ WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Bir anahtar ya da Windows çalışma zamanı meta veri dosyasını imzalamak için anahtar çifti belirtir.|
|[/ WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Bir Windows meta veri dosyasını imzalamak için anahtar kapsayıcısını belirtir.|
|[/ WINMDDELAYSIGN](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|Kısmen Windows çalışma zamanı meta veri (.winmd) dosyası winmd dosyasında ortak anahtarı koyarak imzalar.|
|[/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|Bağlayıcı uyarılarını hata olarak değerlendirir.|

Daha fazla bilgi için bkz: [Compiler-Controlled bağlantı seçenekleri](../../build/reference/compiler-controlled-link-options.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)  
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  