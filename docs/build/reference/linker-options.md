---
title: Bağlayıcı seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 08/20/2018
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
ms.openlocfilehash: e5a091a4301a107fb820f63c357c4e7f43c35948
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721298"
---
# <a name="linker-options"></a>Bağlayıcı Seçenekleri

Ortak nesne dosyası biçimi (COFF) nesne dosyaları ve kitaplıkları bir yürütülebilir (.exe) dosyası oluşturmak için veya bir dinamik bağlantı kitaplığı (DLL) LINK.exe bağlar.

Aşağıdaki tabloda LINK.exe seçeneklerini listeler. BAĞLANTI hakkında daha fazla bilgi için bkz:

- [Derleyici Denetimindeki LINK Seçenekleri](../../build/reference/compiler-controlled-link-options.md)

- [LINK Giriş Dosyaları](../../build/reference/link-input-files.md)

- [LINK Çıktısı](../../build/reference/link-output.md)

- [Ayrılmış Sözcükler](../../build/reference/reserved-words.md)

Komut satırında bağlayıcı seçenekleri büyük küçük harfe duyarlı değildir; Örneğin, / base ve/Base aynı anlama. Her seçeneğin komut satırında veya Visual Studio'da belirtme hakkında daha fazla ayrıntı için bu seçeneği belgelerine bakın.

Kullanabileceğiniz [yorum](../../preprocessor/comment-c-cpp.md) bazı bağlayıcı seçenekleri belirtmek için.

|Seçenek|Amaç|
|------------|-------------|
|[@](../../build/reference/at-specify-a-linker-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ ALIGN](../../build/reference/align-section-alignment.md)|Her bölümün hizalamasını belirtir.|
|[/ALLOWBIND](../../build/reference/allowbind-prevent-dll-binding.md)|Bir DLL'in bağlı olamayacağını belirtir.|
|[/ALLOWISOLATION](../../build/reference/allowisolation-manifest-lookup.md)|Bildirim arama davranışını belirtir.|
|[/APPCONTAINER](../../build/reference/appcontainer-windows-store-app.md)|Uygulamanın bir appcontainer işlem ortamında çalışmasının gerekip gerekmediğini belirtir.|
|[/ ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)|Ekler <xref:System.Diagnostics.DebuggableAttribute> yönetilen bir görüntü için.|
|[/ ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)|Yönetilen kaynağa bağlantı oluşturur.|
|[/ ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)|Bir Microsoft Ara dili (MSIL) modülünün derlemeye içe aktarılması gerekip gerekmediğini belirtir.|
|[/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)|Yönetilen kaynak dosyasını bir derlemeye gömer.|
|[/ BASE](../../build/reference/base-base-address.md)|Program için temel adres ayarlar.|
|[/ CGTHREADS](../../build/reference/cgthreads-compiler-threads.md)|Bağlama sırasında kod oluşturma belirtildiği zaman iyileştirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.|
|[/ CLRIMAGETYPE](../../build/reference/clrimagetype-specify-type-of-clr-image.md)|Bir CLR imajının (IJW, saf veya güvenli) türünü ayarlar.|
|[/ CLRSUPPORTLASTERROR](../../build/reference/clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke mekanizmasıyla çağrılan işlevlerin son hata kodunu korur.|
|[/ CLRTHREADATTRIBUTE](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md)|CLR programınızın Giriş noktasına uygulanacak iş parçacığı oluşturma özniteliğini belirtir.|
|[/ CLRUNMANAGEDCODECHECK](../../build/reference/clrunmanagedcodecheck-add-supressunmanagedcodesecurityattribute.md)|Yönetilen koddan yerel DLL'lere yapılan bağlayıcı tarafından oluşturulan PInvoke saptamalar için bağlayıcının SuppressUnmanagedCodeSecurity özniteliğine uygulanıp uygulanmayacağını belirtir.|
|[/ DEBUG](../../build/reference/debug-generate-debug-info.md)|Hata ayıklama bilgileri oluşturur.|
|[/ DEBUGTYPE](../../build/reference/debugtype-debug-info-options.md)|Hata ayıklama bilgilerini dahil etmek için hangi veri belirtir.|
|[/ DEF](../../build/reference/def-specify-module-definition-file.md)|Modül tanım (.def) dosyasını bağlayıcıya iletir.|
|[/ DEFAULTLIB](../../build/reference/defaultlib-specify-default-library.md)|Dış başvuruları çözümlendiğinde belirtilen kitaplıklarda arama yapar.|
|[/ DELAY](../../build/reference/delay-delay-load-import-settings.md)|DLL'leri Gecikmeli yüklemeyi denetler.|
|[/ DELAYLOAD](../../build/reference/delayload-delay-load-import.md)|Belirtilen DLL için Gecikmeli yüklemeye neden olur.|
|[/ DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)|Bir derlemeyi kısmen imzalar.|
|[/ DEPENDENTLOADFLAG](dependentloadflag.md)|Varsayılan bayrakları bağımlı DLL yükleri ayarlar.|
|[/ DLL](../../build/reference/dll-build-a-dll.md)|Bir DLL oluşturur.|
|[/ DRIVER](../../build/reference/driver-windows-nt-kernel-mode-driver.md)|Çekirdek modlu sürücü oluşturur.|
|[/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md)|Rastgele yükleme zamanında adres alanı düzenini (ASLR) rastgele özelliği temellendirilebilen yürütülebilir bir imaj oluşturulup oluşturulmayacağını belirtir.|
|[/ ENTRY](../../build/reference/entry-entry-point-symbol.md)|Başlangıç adresini ayarlar.|
|[/ errorreport](../../build/reference/errorreport-report-internal-linker-errors.md)|İç bağlayıcı hatalarını Microsoft'a bildirir.|
|[/ DIŞARI AKTARMA](../../build/reference/export-exports-a-function.md)|İşlevi dışarı aktarır.|
|[/ FILEALIGN](../../build/reference/filealign.md)|Belirli bir değerin katları çıkış dosyasını bölümlere hizalar.|
|[/ FIXED](../../build/reference/fixed-fixed-base-address.md)|Yalnızca tercih edilen kendi temel adresinde yüklenebilen bir program oluşturur.|
|[/ FORCE](../../build/reference/force-force-file-output.md)|Çözülmemiş simgeler veya birden çok kez tanımlanan simgeler ile tamamlamak için bir bağlantı zorlar.|
|[/ FUNCTIONPADMIN](../../build/reference/functionpadmin-create-hotpatchable-image.md)|Sıcak yama uygulanabilen bir görüntü oluşturur.|
|[/ GENPROFILE, FASTGENPROFILE](../../build/reference/genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Bu iki seçenek nesil profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyası belirtin. / GENPROFILE ve fastgenprofıle farklı varsayılan parametreler kullanır.|
|[/ GUARD](../../build/reference/guard-enable-guard-checks.md)|Denetim akışı koruyucusu koruma sağlar.|
|[/HEAP](../../build/reference/heap-set-heap-size.md)|Yığın boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](../../build/reference/highentropyva-support-64-bit-aslr.md)|Yüksek entropili 64-bit rastgele adres alanı düzenini (ASLR) için destek belirtir.|
|[/ IDLOUT](../../build/reference/idlout-name-midl-output-files.md)|.İdl dosyasının ve diğer MIDL çıktı dosyalarının adını belirtir.|
|[/ IGNORE](../../build/reference/ignore-ignore-specific-warnings.md)|Belirtilen bağlayıcı uyarılarını çıkışı bastırır.|
|[/ IGNOREIDL](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)|Öznitelik bilgilerinin bir .idl dosyasında işlenmesini engeller.|
|[/ IMPLIB](../../build/reference/implib-name-import-library.md)|Varsayılan içe aktarma kitaplığı adını geçersiz kılar.|
|[/ INCLUDE](../../build/reference/include-force-symbol-references.md)|Simge başvurularını zorlar.|
|[/ INCREMENTAL](../../build/reference/incremental-link-incrementally.md)|Artımlı bağlamayı denetler.|
|[/INTEGRITYCHECK](../../build/reference/integritycheck-require-signature-check.md)|Modül yükleme zamanında bir imza denetimi gerektiğini belirtir.|
|[/ KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Bir derlemeyi imzalamak için bir anahtar kapsayıcı belirtir.|
|[/ KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Bir anahtar veya bir derlemeyi imzalamak için anahtar çiftini belirtir.|
|[/LARGEADDRESSAWARE](../../build/reference/largeaddressaware-handle-large-addresses.md)|Derleyiciye uygulamanın iki gigabayttan daha büyük adresleri desteklediğini söyler.|
|[/ LIBPATH](../../build/reference/libpath-additional-libpath.md)|Kullanıcının ortam kitaplık yolunu önce aramak için bir yol belirtir.|
|[/LTCG](../../build/reference/ltcg-link-time-code-generation.md)|Bağlama zamanı kod oluşturmayı belirtir.|
|[/ MACHINE](../../build/reference/machine-specify-target-platform.md)|Hedef platformu belirtir.|
|[/ BİLDİRİM](../../build/reference/manifest-create-side-by-side-assembly-manifest.md)|Yan yana bildirim dosyası oluşturur ve isteğe bağlı olarak ikili sisteme katıştırır.|
|[/ MANIFESTDEPENDENCY](../../build/reference/manifestdependency-specify-manifest-dependencies.md)|Belirtir bir \<dependentAssembly > bölümünde bildirim dosyası.|
|[/ MANIFESTFILE](../../build/reference/manifestfile-name-manifest-file.md)|Bildirim dosyasının varsayılan adını değiştirir.|
|[/ MANIFESTINPUT](../../build/reference/manifestinput-specify-manifest-input.md)|İşlem ve ikili dosyada eklemek bağlayıcı için bir bildirim giriş dosyası belirtir. Birden fazla bildirim giriş dosyası belirtmek için bu seçeneği birden çok kez kullanabilirsiniz.|
|[/ MANIFESTUAC](../../build/reference/manifestuac-embeds-uac-information-in-manifest.md)|Kullanıcı Hesabı Denetimi (UAC) bilgisinin program bildiriminde gömülü olup olmadığını belirtir.|
|[/MAP](../../build/reference/map-generate-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/ MAPINFO](../../build/reference/mapinfo-include-information-in-mapfile.md)|Mapfile içinde belirtilen bilgileri içerir.|
|[/ MERGE](../../build/reference/merge-combine-sections.md)|Bölümleri birleştirir.|
|[/ MIDL](../../build/reference/midl-specify-midl-command-line-options.md)|MIDL komut satırı seçeneklerini belirtir.|
|[/ NATVIS](../../build/reference/natvis-add-natvis-to-pdb.md)|Hata ayıklama görselleştiricileri PDB'ye Natvis dosyasından ekler.|
|[/ NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)|Bir .NET Framework derlemesinin oluşturulmasını engeller.|
|[/ NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md)|Tüm yok sayar (veya belirtilenleri) varsayılan kitaplığı dış başvuruları çözümlendiğinde.|
|[/ NOENTRY](../../build/reference/noentry-no-entry-point.md)|Yalnızca kaynak DLL oluşturur.|
|[/ NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)|Başlangıç başlığını göstermez.|
|[/NXCOMPAT](../../build/reference/nxcompat-compatible-with-data-execution-prevention.md)|Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde doğrulanmış olarak işaretler.|
|[/ OPT](../../build/reference/opt-optimizations.md)|LINK iyileştirmelerini denetler.|
|[/ ORDER](../../build/reference/order-put-functions-in-order.md)|Comdat'ları önceden belirlenmiş bir sırada görüntüye yerleştirir.|
|[/ OUT](../../build/reference/out-output-file-name.md)|Çıkış dosyası adını belirtir.|
|[/PDB](../../build/reference/pdb-use-program-database.md)|Program veritabanı (PDB) dosyası oluşturur.|
|[/ PDBALTPATH](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)|Bir PDB dosyası kaydetmek için alternatif bir konum kullanır.|
|[/ PDBSTRIPPED](../../build/reference/pdbstripped-strip-private-symbols.md)|Hiçbir özel sembol içermeyen bir program veritabanı (PDB) dosyası oluşturur.|
|[/ PGD](../../build/reference/pgd-specify-database-for-profile-guided-optimizations.md)|Profil temelli iyileştirmeler için bir .pgd dosyası belirtir.|
|[/POGOSAFEMODE](../../build/reference/pogosafemode-linker-option.md)|**Eski** bir iş parçacığı izleme eklenmiş PGO derleme oluşturur.|
|[/ PROFILE](../../build/reference/profile-performance-tools-profiler.md)|Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.|
|[/RELEASE](../../build/reference/release-set-the-checksum.md)|.Exe üstbilgisindeki sağlama toplamını ayarlar.|
|[/ SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md)|Görüntü güvenli özel durum işleyicileri tablosu içereceğini belirtir.|
|[/ SECTION](../../build/reference/section-specify-section-attributes.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/ SOURCELINK](../../build/reference/sourcelink.md)|PDB'ye eklenecek SourceLink dosyasını belirtir.|
|[/STACK](../../build/reference/stack-stack-allocations.md)|Yığın boyunu bayt cinsinden ayarlar.|
|[/ STUB](../../build/reference/stub-ms-dos-stub-file-name.md)|MS-DOS saplama programını Win32 programına iliştirir.|
|[/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md)|İşletim sistemine .exe dosyasını nasıl çalıştırması gerektiğini belirtir.|
|[/SWAPRUN](../../build/reference/swaprun-load-linker-output-to-swap-file.md)|İşletim sistemine, çalıştırmadan önce bağlayıcı çıktısını bir takas dosyasına kopyalaması söyler.|
|[/ TLBID](../../build/reference/tlbid-specify-resource-id-for-typelib.md)|Bağlayıcı tarafından oluşturulan tür kitaplığının kaynak Kimliğini belirtir.|
|[/ TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md)|.Tlb dosyasının ve diğer MIDL çıktı dosyalarının adını belirtir.|
|[/TSAWARE](../../build/reference/tsaware-create-terminal-server-aware-application.md)|Özellikle Terminal Server altında çalışacak biçimde tasarlanmış bir uygulama oluşturur.|
|[/USEPROFILE](../../build/reference/useprofile.md)|İyileştirilmiş görüntü oluşturmak için kullandığı profil temelli iyileştirme eğitim verileri.|
|[/ VERBOSE](../../build/reference/verbose-print-progress-messages.md)|Bağlayıcı ilerleme iletilerini yazdırır.|
|[/VERSION](../../build/reference/version-version-information.md)|Bir sürüm numarası atar.|
|[/ WHOLEARCHIVE](../../build/reference/wholearchive-include-all-library-object-files.md)|Belirtilen statik kitaplıkların her nesne dosyası içerir.|
|[/ WINMD](../../build/reference/winmd-generate-windows-metadata.md)|Bir Windows çalışma zamanı meta veri dosyasının oluşturulmasını etkinleştirir.|
|[/ WINMDFILE](../../build/reference/winmdfile-specify-winmd-file.md)|Tarafından oluşturulan Windows Runtime Metadata (winmd) çıkış dosyası için dosya adını belirtir [/WINMD](../../build/reference/winmd-generate-windows-metadata.md) bağlayıcı seçeneği.|
|[/ WINMDKEYFILE](../../build/reference/winmdkeyfile-specify-winmd-key-file.md)|Bir anahtar veya bir Windows Runtime Metadata dosyasını imzalamak için anahtar çiftini belirtir.|
|[/ WINMDKEYCONTAINER](../../build/reference/winmdkeycontainer-specify-key-container.md)|Windows Metadata dosyasını imzalamak için bir anahtar kapsayıcı belirtir.|
|[/ WINMDDELAYSIGN DOSYASINI](../../build/reference/winmddelaysign-partially-sign-a-winmd.md)|Winmd dosyasındaki ortak anahtarı yerleştirerek Windows çalışma zamanı meta veri (.winmd) dosyasını kısmen imzalar.|
|[/WX](../../build/reference/wx-treat-linker-warnings-as-errors.md)|Bağlayıcı uyarılarını hata olarak değerlendirir.|

Daha fazla bilgi için [Compiler-Controlled bağlantı seçenekleri](../../build/reference/compiler-controlled-link-options.md).

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Derleme Başvurusu](../../build/reference/c-cpp-building-reference.md)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)