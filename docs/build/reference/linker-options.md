---
title: MSVC bağlayıcı seçenekleri
ms.date: 08/20/2018
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 7ff8ecd6a607aac59fca6d32fa2784e7e3e4268f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817367"
---
# <a name="linker-options"></a>Bağlayıcı Seçenekleri

Ortak nesne dosyası biçimi (COFF) nesne dosyaları ve kitaplıkları bir yürütülebilir (.exe) dosyası oluşturmak için veya bir dinamik bağlantı kitaplığı (DLL) LINK.exe bağlar.

Aşağıdaki tabloda LINK.exe seçeneklerini listeler. BAĞLANTI hakkında daha fazla bilgi için bkz:

- [Derleyici Denetimindeki LINK Seçenekleri](compiler-controlled-link-options.md)

- [LINK Giriş Dosyaları](link-input-files.md)

- [LINK Çıktısı](link-output.md)

- [Ayrılmış Sözcükler](reserved-words.md)

Komut satırında bağlayıcı seçenekleri büyük küçük harfe duyarlı değildir; Örneğin, / base ve/Base aynı anlama. Her seçeneğin komut satırında veya Visual Studio'da belirtme hakkında daha fazla ayrıntı için bu seçeneği belgelerine bakın.

Kullanabileceğiniz [yorum](../../preprocessor/comment-c-cpp.md) bazı bağlayıcı seçenekleri belirtmek için.

|Seçenek|Amaç|
|------------|-------------|
|[@](at-specify-a-linker-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ ALIGN](align-section-alignment.md)|Her bölümün hizalamasını belirtir.|
|[/ALLOWBIND](allowbind-prevent-dll-binding.md)|Bir DLL'in bağlı olamayacağını belirtir.|
|[/ALLOWISOLATION](allowisolation-manifest-lookup.md)|Bildirim arama davranışını belirtir.|
|[/APPCONTAINER](appcontainer-windows-store-app.md)|Uygulamanın bir appcontainer işlem ortamında çalışmasının gerekip gerekmediğini belirtir.|
|[/ ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)|Ekler <xref:System.Diagnostics.DebuggableAttribute> yönetilen bir görüntü için.|
|[/ ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)|Yönetilen kaynağa bağlantı oluşturur.|
|[/ ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)|Bir Microsoft Ara dili (MSIL) modülünün derlemeye içe aktarılması gerekip gerekmediğini belirtir.|
|[/ ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)|Yönetilen kaynak dosyasını bir derlemeye gömer.|
|[/ BASE](base-base-address.md)|Program için temel adres ayarlar.|
|[/ CGTHREADS](cgthreads-compiler-threads.md)|Bağlama sırasında kod oluşturma belirtildiği zaman iyileştirme ve kod oluşturma için kullanılacak cl.exe iş parçacığı sayısını ayarlar.|
|[/ CLRIMAGETYPE](clrimagetype-specify-type-of-clr-image.md)|Bir CLR imajının (IJW, saf veya güvenli) türünü ayarlar.|
|[/ CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke mekanizmasıyla çağrılan işlevlerin son hata kodunu korur.|
|[/ CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)|CLR programınızın Giriş noktasına uygulanacak iş parçacığı oluşturma özniteliğini belirtir.|
|[/ CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|Yönetilen koddan yerel DLL'lere yapılan bağlayıcı tarafından oluşturulan PInvoke saptamalar için bağlayıcının SuppressUnmanagedCodeSecurity özniteliğine uygulanıp uygulanmayacağını belirtir.|
|[/ DEBUG](debug-generate-debug-info.md)|Hata ayıklama bilgileri oluşturur.|
|[/ DEBUGTYPE](debugtype-debug-info-options.md)|Hata ayıklama bilgilerini dahil etmek için hangi veri belirtir.|
|[/DEF](def-specify-module-definition-file.md)|Modül tanım (.def) dosyasını bağlayıcıya iletir.|
|[/ DEFAULTLIB](defaultlib-specify-default-library.md)|Dış başvuruları çözümlendiğinde belirtilen kitaplıklarda arama yapar.|
|[/ DELAY](delay-delay-load-import-settings.md)|DLL'leri Gecikmeli yüklemeyi denetler.|
|[/ DELAYLOAD](delayload-delay-load-import.md)|Belirtilen DLL için Gecikmeli yüklemeye neden olur.|
|[/ DELAYSIGN](delaysign-partially-sign-an-assembly.md)|Bir derlemeyi kısmen imzalar.|
|[/ DEPENDENTLOADFLAG](dependentloadflag.md)|Varsayılan bayrakları bağımlı DLL yükleri ayarlar.|
|[/DLL](dll-build-a-dll.md)|Bir DLL oluşturur.|
|[/ DRIVER](driver-windows-nt-kernel-mode-driver.md)|Çekirdek modlu sürücü oluşturur.|
|[/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)|Rastgele yükleme zamanında adres alanı düzenini (ASLR) rastgele özelliği temellendirilebilen yürütülebilir bir imaj oluşturulup oluşturulmayacağını belirtir.|
|[/ ENTRY](entry-entry-point-symbol.md)|Başlangıç adresini ayarlar.|
|[/ errorreport](errorreport-report-internal-linker-errors.md)|İç bağlayıcı hatalarını Microsoft'a bildirir.|
|[/ DIŞARI AKTARMA](export-exports-a-function.md)|İşlevi dışarı aktarır.|
|[/ FILEALIGN](filealign.md)|Belirli bir değerin katları çıkış dosyasını bölümlere hizalar.|
|[/ FIXED](fixed-fixed-base-address.md)|Yalnızca tercih edilen kendi temel adresinde yüklenebilen bir program oluşturur.|
|[/ FORCE](force-force-file-output.md)|Çözülmemiş simgeler veya birden çok kez tanımlanan simgeler ile tamamlamak için bir bağlantı zorlar.|
|[/ FUNCTIONPADMIN](functionpadmin-create-hotpatchable-image.md)|Sıcak yama uygulanabilen bir görüntü oluşturur.|
|[/ GENPROFILE, FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Bu iki seçenek nesil profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyası belirtin. / GENPROFILE ve fastgenprofıle farklı varsayılan parametreler kullanır.|
|[/ GUARD](guard-enable-guard-checks.md)|Denetim akışı koruyucusu koruma sağlar.|
|[/HEAP](heap-set-heap-size.md)|Yığın boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)|Yüksek entropili 64-bit rastgele adres alanı düzenini (ASLR) için destek belirtir.|
|[/ IDLOUT](idlout-name-midl-output-files.md)|.İdl dosyasının ve diğer MIDL çıktı dosyalarının adını belirtir.|
|[/ IGNORE](ignore-ignore-specific-warnings.md)|Belirtilen bağlayıcı uyarılarını çıkışı bastırır.|
|[/ IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md)|Öznitelik bilgilerinin bir .idl dosyasında işlenmesini engeller.|
|[/ IMPLIB](implib-name-import-library.md)|Varsayılan içe aktarma kitaplığı adını geçersiz kılar.|
|[/ INCLUDE](include-force-symbol-references.md)|Simge başvurularını zorlar.|
|[/ INCREMENTAL](incremental-link-incrementally.md)|Artımlı bağlamayı denetler.|
|[/INTEGRITYCHECK](integritycheck-require-signature-check.md)|Modül yükleme zamanında bir imza denetimi gerektiğini belirtir.|
|[/ KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Bir derlemeyi imzalamak için bir anahtar kapsayıcı belirtir.|
|[/ KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Bir anahtar veya bir derlemeyi imzalamak için anahtar çiftini belirtir.|
|[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)|Derleyiciye uygulamanın iki gigabayttan daha büyük adresleri desteklediğini söyler.|
|[/ LIBPATH](libpath-additional-libpath.md)|Kullanıcının ortam kitaplık yolunu önce aramak için bir yol belirtir.|
|[/LTCG](ltcg-link-time-code-generation.md)|Bağlama zamanı kod oluşturmayı belirtir.|
|[/ MACHINE](machine-specify-target-platform.md)|Hedef platformu belirtir.|
|[/ BİLDİRİM](manifest-create-side-by-side-assembly-manifest.md)|Yan yana bildirim dosyası oluşturur ve isteğe bağlı olarak ikili sisteme katıştırır.|
|[/ MANIFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md)|Belirtir bir \<dependentAssembly > bölümünde bildirim dosyası.|
|[/ MANIFESTFILE](manifestfile-name-manifest-file.md)|Bildirim dosyasının varsayılan adını değiştirir.|
|[/ MANIFESTINPUT](manifestinput-specify-manifest-input.md)|İşlem ve ikili dosyada eklemek bağlayıcı için bir bildirim giriş dosyası belirtir. Birden fazla bildirim giriş dosyası belirtmek için bu seçeneği birden çok kez kullanabilirsiniz.|
|[/ MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md)|Kullanıcı Hesabı Denetimi (UAC) bilgisinin program bildiriminde gömülü olup olmadığını belirtir.|
|[/MAP](map-generate-mapfile.md)|Bir eşlem dosyası oluşturur.|
|[/ MAPINFO](mapinfo-include-information-in-mapfile.md)|Mapfile içinde belirtilen bilgileri içerir.|
|[/ MERGE](merge-combine-sections.md)|Bölümleri birleştirir.|
|[/ MIDL](midl-specify-midl-command-line-options.md)|MIDL komut satırı seçeneklerini belirtir.|
|[/ NATVIS](natvis-add-natvis-to-pdb.md)|Hata ayıklama görselleştiricileri PDB'ye Natvis dosyasından ekler.|
|[/ NOASSEMBLY](noassembly-create-a-msil-module.md)|Bir .NET Framework derlemesinin oluşturulmasını engeller.|
|[/ NODEFAULTLIB](nodefaultlib-ignore-libraries.md)|Tüm yok sayar (veya belirtilenleri) varsayılan kitaplığı dış başvuruları çözümlendiğinde.|
|[/ NOENTRY](noentry-no-entry-point.md)|Yalnızca kaynak DLL oluşturur.|
|[/ NOLOGO](nologo-suppress-startup-banner-linker.md)|Başlangıç başlığını göstermez.|
|[/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)|Bir yürütülebilir dosya Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde doğrulanmış olarak işaretler.|
|[/ OPT](opt-optimizations.md)|LINK iyileştirmelerini denetler.|
|[/ ORDER](order-put-functions-in-order.md)|Comdat'ları önceden belirlenmiş bir sırada görüntüye yerleştirir.|
|[/ OUT](out-output-file-name.md)|Çıkış dosyası adını belirtir.|
|[/PDB](pdb-use-program-database.md)|Program veritabanı (PDB) dosyası oluşturur.|
|[/ PDBALTPATH](pdbaltpath-use-alternate-pdb-path.md)|Bir PDB dosyası kaydetmek için alternatif bir konum kullanır.|
|[/ PDBSTRIPPED](pdbstripped-strip-private-symbols.md)|Hiçbir özel sembol içermeyen bir program veritabanı (PDB) dosyası oluşturur.|
|[/ PGD](pgd-specify-database-for-profile-guided-optimizations.md)|Profil temelli iyileştirmeler için bir .pgd dosyası belirtir.|
|[/POGOSAFEMODE](pogosafemode-linker-option.md)|**Eski** bir iş parçacığı izleme eklenmiş PGO derleme oluşturur.|
|[/ PROFILE](profile-performance-tools-profiler.md)|Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.|
|[/RELEASE](release-set-the-checksum.md)|.Exe üstbilgisindeki sağlama toplamını ayarlar.|
|[/ SAFESEH](safeseh-image-has-safe-exception-handlers.md)|Görüntü güvenli özel durum işleyicileri tablosu içereceğini belirtir.|
|[/ SECTION](section-specify-section-attributes.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/ SOURCELINK](sourcelink.md)|PDB'ye eklenecek SourceLink dosyasını belirtir.|
|[/STACK](stack-stack-allocations.md)|Yığın boyunu bayt cinsinden ayarlar.|
|[/ STUB](stub-ms-dos-stub-file-name.md)|MS-DOS saplama programını Win32 programına iliştirir.|
|[/SUBSYSTEM](subsystem-specify-subsystem.md)|İşletim sistemine .exe dosyasını nasıl çalıştırması gerektiğini belirtir.|
|[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)|İşletim sistemine, çalıştırmadan önce bağlayıcı çıktısını bir takas dosyasına kopyalaması söyler.|
|[/TLBID](tlbid-specify-resource-id-for-typelib.md)|Bağlayıcı tarafından oluşturulan tür kitaplığının kaynak Kimliğini belirtir.|
|[/ TLBOUT](tlbout-name-dot-tlb-file.md)|.Tlb dosyasının ve diğer MIDL çıktı dosyalarının adını belirtir.|
|[/TSAWARE](tsaware-create-terminal-server-aware-application.md)|Özellikle Terminal Server altında çalışacak biçimde tasarlanmış bir uygulama oluşturur.|
|[/USEPROFILE](useprofile.md)|İyileştirilmiş görüntü oluşturmak için kullandığı profil temelli iyileştirme eğitim verileri.|
|[/ VERBOSE](verbose-print-progress-messages.md)|Bağlayıcı ilerleme iletilerini yazdırır.|
|[/VERSION](version-version-information.md)|Bir sürüm numarası atar.|
|[/ WHOLEARCHIVE](wholearchive-include-all-library-object-files.md)|Belirtilen statik kitaplıkların her nesne dosyası içerir.|
|[/WINMD](winmd-generate-windows-metadata.md)|Bir Windows çalışma zamanı meta veri dosyasının oluşturulmasını etkinleştirir.|
|[/ WINMDFILE](winmdfile-specify-winmd-file.md)|Tarafından oluşturulan Windows Runtime Metadata (winmd) çıkış dosyası için dosya adını belirtir [/WINMD](winmd-generate-windows-metadata.md) bağlayıcı seçeneği.|
|[/ WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md)|Bir anahtar veya bir Windows Runtime Metadata dosyasını imzalamak için anahtar çiftini belirtir.|
|[/ WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md)|Windows Metadata dosyasını imzalamak için bir anahtar kapsayıcı belirtir.|
|[/ WINMDDELAYSIGN DOSYASINI](winmddelaysign-partially-sign-a-winmd.md)|Winmd dosyasındaki ortak anahtarı yerleştirerek Windows çalışma zamanı meta veri (.winmd) dosyasını kısmen imzalar.|
|[/WX](wx-treat-linker-warnings-as-errors.md)|Bağlayıcı uyarılarını hata olarak değerlendirir.|

Daha fazla bilgi için [Compiler-Controlled bağlantı seçenekleri](compiler-controlled-link-options.md).

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Derleme Başvurusu](c-cpp-building-reference.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)
