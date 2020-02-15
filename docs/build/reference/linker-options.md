---
title: MSVC bağlayıcı seçenekleri
description: Microsoft bağlantı Bağlayıcısı tarafından desteklenen seçeneklerin bir listesi.
ms.date: 02/09/2020
f1_keywords:
- link
helpviewer_keywords:
- linker [C++]
- linker [C++], options listed
- libraries [C++], linking to COFF
- LINK tool [C++], linker options
ms.assetid: c1d51b8a-bd23-416d-81e4-900e02b2c129
ms.openlocfilehash: 12710aff1cf833e277e48ab2f13abc702c7d6c14
ms.sourcegitcommit: 8414cd91297dea88c480e208c7b5301db9972f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77257552"
---
# <a name="linker-options"></a>Bağlayıcı seçenekleri

LINK. exe, yürütülebilir (. exe) dosya veya dinamik bağlantı kitaplığı (DLL) oluşturmak için ortak nesne dosyası biçimi (COFF) nesne dosyalarını ve kitaplıklarını bağlar.

Aşağıdaki tabloda LINK. exe seçenekleri listelenmektedir. BAĞLANTı hakkında daha fazla bilgi için bkz.

- [Derleyici Denetimindeki LINK Seçenekleri](compiler-controlled-link-options.md)

- [LINK Giriş Dosyaları](link-input-files.md)

- [LINK Çıktısı](link-output.md)

- [Ayrılmış Sözcükler](reserved-words.md)

Komut satırında bağlayıcı seçenekleri büyük/küçük harfe duyarlı değildir; Örneğin, `/base` ve `/BASE` aynı şeyi ifade ederler. Her bir seçeneğin komut satırında veya Visual Studio 'da nasıl belirtilme hakkındaki ayrıntılar için bu seçeneğe yönelik belgelere bakın.

Bazı bağlayıcı seçeneklerini belirtmek için, pragma [açıklamasını](../../preprocessor/comment-c-cpp.md) kullanabilirsiniz.

## <a name="linker-options-listed-alphabetically"></a>Alfabetik olarak listelenen bağlayıcı seçenekleri

|Seçenek|Amaç|
|------------|-------------|
|[@](at-specify-a-linker-response-file.md)|Bir yanıt dosyası belirtir.|
|[/ALıGN](align-section-alignment.md)|Her bölümün hizalamasını belirtir.|
|[/ALLOWBIND](allowbind-prevent-dll-binding.md)|DLL 'nin bağlanolamayacağını belirtir.|
|[/ALLOWISOLATION](allowisolation-manifest-lookup.md)|Bildirim arama için davranışı belirtir.|
|[/APPCONTAINER](appcontainer-windows-store-app.md)|Uygulamanın bir AppContainer işlem ortamı içinde çalıştırılması gerekip gerekmediğini belirtir.|
|[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md)|Yönetilen bir görüntüye <xref:System.Diagnostics.DebuggableAttribute> ekler.|
|[/ASSEMBLYLıNKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md)|Yönetilen bir kaynağa bir bağlantı oluşturur.|
|[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md)|Bir Microsoft ara dili (MSIL) modülünün derlemeye içeri aktarılması gerektiğini belirtir.|
|[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md)|Bir derlemede yönetilen bir kaynak dosyası katıştırır.|
|[/BASE](base-base-address.md)|Program için bir temel adres ayarlar.|
|[/CGTHREADS](cgthreads-compiler-threads.md)|Bağlama zamanı kod üretimi belirtildiğinde iyileştirme ve kod oluşturma için kullanılacak CL. exe iş parçacığı sayısını ayarlar.|
|[/CLRıMAGETYPE](clrimagetype-specify-type-of-clr-image.md)|CLR görüntüsünün türünü (ıJW, saf veya güvenli) ayarlar.|
|[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md)|P/Invoke mekanizması aracılığıyla çağrılan işlevlerin son hata kodunu korur.|
|[/CLRTHREADATTRıBUTE](clrthreadattribute-set-clr-thread-attribute.md)|CLR programınızın giriş noktasına uygulanacak iş parçacığı oluşturma özniteliğini belirtir.|
|[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md)|Bağlayıcının SuppressUnmanagedCodeSecurity özniteliğini yönetilen koddan yerel dll 'Lere çağıran, bağlayıcı tarafından oluşturulan PInvoke saplamalarının uygulayıp uygulayamayacağını belirtir.|
|[Komutun](debug-generate-debug-info.md)|Hata ayıklama bilgileri oluşturur.|
|[/DEBUGTYPE](debugtype-debug-info-options.md)|Hata ayıklama bilgilerine hangi verilerin ekleneceğini belirtir.|
|[/DEF](def-specify-module-definition-file.md)|Bir modül tanım (. def) dosyasını bağlayıcıya geçirir.|
|[/DEFAULTLıB](defaultlib-specify-default-library.md)|Dış başvurular çözümlendiğinde belirtilen kitaplığı arar.|
|[/DELAY](delay-delay-load-import-settings.md)|Dll 'lerin gecikmeli yüklemesini denetler.|
|[/DELAYLOAD](delayload-delay-load-import.md)|Belirtilen DLL 'nin gecikmeli yüklenmesine neden olur.|
|[/DELAYSIGN](delaysign-partially-sign-an-assembly.md)|Bir derlemeyi kısmen imzalar.|
|[/DEPENDENTLOADFLAG](dependentloadflag.md)|Bağımlı DLL yüklerinin varsayılan bayraklarını ayarlar.|
|[/DLL](dll-build-a-dll.md)|Bir DLL oluşturur.|
|[/DRıVER](driver-windows-nt-kernel-mode-driver.md)|Çekirdek modu sürücüsü oluşturur.|
|[/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)|Adres alanı düzeni rastgele seçme (ASLR) özelliğini kullanarak yükleme zamanında yeniden temellendiren bir yürütülebilir görüntü oluşturulup oluşturulmayacağını belirtir.|
|[/ENTRY](entry-entry-point-symbol.md)|Başlangıç adresini ayarlar.|
|[/ERRORREPORT](errorreport-report-internal-linker-errors.md)| Kullanım dışı. Hata raporlama [Windows hata bildirimi (WER)](/windows/win32/wer/windows-error-reporting) ayarları tarafından denetlenir. |
|[/EXPORT](export-exports-a-function.md)|Bir işlevi dışa aktarır.|
|[/FILEALIGN](filealign.md)|Çıktı dosyasının içindeki bölümleri belirtilen değerin katları halinde hizalar.|
|[/FıXED](fixed-fixed-base-address.md)|Yalnızca tercih edilen temel adresinde yüklenebilen bir program oluşturur.|
|[/FORCE](force-force-file-output.md)|Çözülmemiş semboller veya bir defadan fazla tanımlanmış semboller içeren bir bağlantıyı tamamlamaya zorlar.|
|[/FUNCTıONPADMıN](functionpadmin-create-hotpatchable-image.md)|Etkin düzeltme eki uygulanabilir bir görüntü oluşturur.|
|[/GENPROFILE,/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)|Bu seçeneklerin her ikisi de profil temelli iyileştirme 'yi (PGO) desteklemek için bağlayıcı tarafından bir *`.pgd`* dosyası oluşturmayı belirtir. /GENPROFILE ve/FASTGENPROFILE farklı varsayılan parametreler kullanır.|
|[/GUARD](guard-enable-guard-checks.md)|Denetim akışı koruyucusu korumasını etkinleştir.|
|[/HEAP](heap-set-heap-size.md)|Yığının boyutunu bayt cinsinden ayarlar.|
|[/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)|Yüksek entropi 64 bit adres alanı düzeni rastgele seçme (ASLR) için desteği belirtir.|
|[/IDLOUT](idlout-name-midl-output-files.md)|*`.idl`* dosyasının ve DIĞER MIDL çıktı dosyalarının adını belirtir.|
|[/IGNORE](ignore-ignore-specific-warnings.md)|Belirtilen bağlayıcı uyarılarının çıkışını bastırır.|
|[/IGNOREıDL](ignoreidl-don-t-process-attributes-into-midl.md)|Öznitelik bilgilerinin *`.idl`* dosyasına işlenmesini önler.|
|[/IMPLıB](implib-name-import-library.md)|Varsayılan içeri aktarma kitaplığı adını geçersiz kılar.|
|[/INCLUDE](include-force-symbol-references.md)|Sembol başvurularını zorlar.|
|[/INCREMENTAL](incremental-link-incrementally.md)|Artımlı bağlamayı denetler.|
|[/INTEGRITYCHECK](integritycheck-require-signature-check.md)|Modülün yükleme zamanında imza denetimi gerektirdiğini belirtir.|
|[/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md)|Bir derlemeyi imzalamak için bir anahtar kapsayıcısı belirtir.|
|[/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)|Bir derlemeyi imzalamak için bir anahtar veya anahtar çiftini belirtir.|
|[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)|Derleyiciye uygulamanın iki gigabayt 'tan daha büyük adresler desteklediğini söyler|
|[/LıBPATH](libpath-additional-libpath.md)|Ortam kitaplığı yolundan önce aramak için bir yol belirtir.|
|[/LINKREPRO](linkrepro.md)|' Deki bağlantı yeniden üretme yapıtları oluşturmak için bir yol belirtir.|
|[/LINKREPROTARGET](linkreprotarget.md)|Yalnızca belirtilen hedef üretilirken bir bağlantı yeniden üretme oluşturur. <sup>16,1</sup>|
|[/LTCG](ltcg-link-time-code-generation.md)|Bağlantı zamanı kod oluşturmayı belirtir.|
|[/MACHıNE](machine-specify-target-platform.md)|Hedef platformu belirtir.|
|[/MANIFEST](manifest-create-side-by-side-assembly-manifest.md)|Yan yana bildirim dosyası oluşturur ve isteğe bağlı olarak ikiliye katıştırır.|
|[/MANıFESTDEPENDENCY](manifestdependency-specify-manifest-dependencies.md)|Bildirim dosyasında \<dependentAssembly > bölümünü belirtir.|
|[/MANıFESTFıLE](manifestfile-name-manifest-file.md)|Bildirim dosyasının varsayılan adını değiştirir.|
|[/MANıFESTıNPUT](manifestinput-specify-manifest-input.md)|Bağlayıcının işleme ve ikiliye katıştırılması için bir bildirim giriş dosyasını belirtir. Birden fazla bildirim giriş dosyası belirtmek için bu seçeneği birden çok kez kullanabilirsiniz.|
|[/MANıFESTUAC](manifestuac-embeds-uac-information-in-manifest.md)|Kullanıcı hesabı denetimi (UAC) bilgisinin program bildirimine katıştırılmadığını belirtir.|
|[/MAP](map-generate-mapfile.md)|Bir mapfile oluşturur.|
|[/MAPıNFO](mapinfo-include-information-in-mapfile.md)|Mapfile içinde belirtilen bilgileri içerir.|
|[/MERGE](merge-combine-sections.md)|Bölümleri birleştirir.|
|[/MıDL](midl-specify-midl-command-line-options.md)|MıDL komut satırı seçeneklerini belirtir.|
|[/NATVIS](natvis-add-natvis-to-pdb.md)|Natvis dosyasından program veritabanına (PDB) hata ayıklayıcı Görselleştiriciler ekler.|
|[/NOASSEMBLY](noassembly-create-a-msil-module.md)|.NET Framework derlemesinin oluşturulmasını engeller.|
|[/NODEFAULTLıB](nodefaultlib-ignore-libraries.md)|Dış başvurular çözümlendiğinde tüm (veya belirtilen) varsayılan kitaplıkları yoksayar.|
|[/NOENTRY](noentry-no-entry-point.md)|Yalnızca kaynak DLL 'SI oluşturur.|
|[/NOLOGO](nologo-suppress-startup-banner-linker.md)|Başlangıç başlığını bastırır.|
|[/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)|Windows Veri Yürütme Engellemesi özelliği ile uyumlu olması için bir yürütülebilir dosyayı doğrulanmış olarak işaretler.|
|[/OPT](opt-optimizations.md)|BAĞLANTı iyileştirmeleri denetler.|
|[/ORDER](order-put-functions-in-order.md)|Görüntüye, önceden belirlenmiş bir sırada göz atar.|
|[/OUT](out-output-file-name.md)|Çıkış dosyası adını belirtir.|
|[/PDB](pdb-use-program-database.md)|Bir PDB dosyası oluşturur.|
|[/PDBALTPATH](pdbaltpath-use-alternate-pdb-path.md)|Bir PDB dosyasını kaydetmek için alternatif bir konum kullanır.|
|[/PDBSTRıPPED](pdbstripped-strip-private-symbols.md)|Özel sembolleri olmayan bir PDB dosyası oluşturur.|
|[/PGD](pgd-specify-database-for-profile-guided-optimizations.md)|Profil temelli iyileştirmeler için bir *`.pgd`* dosyası belirtir.|
|[/POGOSAFEMODE](pogosafemode-linker-option.md)|**Kullanımdan kalktı** İş parçacığı güvenli PGO tarafından izlenen derleme oluşturur.|
|[PROFILE](profile-performance-tools-profiler.md)|Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.|
|[/RELEASE](release-set-the-checksum.md)|*`.exe`* üstbilgisindeki sağlama toplamını ayarlar.|
|[/SAFESEH](safeseh-image-has-safe-exception-handlers.md)|Görüntünün bir güvenli özel durum işleyicileri tablosu içerdiğini belirtir.|
|[/SECTıON](section-specify-section-attributes.md)|Bir bölümün özniteliklerini geçersiz kılar.|
|[/SOURCELINK](sourcelink.md)|PDB 'ye eklenecek bir SourceLink dosyası belirtir.|
|[/STACK](stack-stack-allocations.md)|Yığının boyutunu bayt cinsinden ayarlar.|
|[/STUB](stub-ms-dos-stub-file-name.md)|Bir Win32 programına bir MS-DOS saplama programı ekler.|
|[/SUBSYSTEM](subsystem-specify-subsystem.md)|İşletim sistemine *`.exe`* dosyasının nasıl çalıştırılacağını söyler.|
|[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md)|İşletim sistemine, çalıştırmadan önce bağlayıcı çıkışını bir takas dosyasına kopyalamasını söyler.|
|[/TLBıD](tlbid-specify-resource-id-for-typelib.md)|Bağlayıcı tarafından oluşturulan tür kitaplığının kaynak KIMLIĞINI belirtir.|
|[/TLBOUT](tlbout-name-dot-tlb-file.md)|*`.tlb`* dosyasının ve DIĞER MIDL çıktı dosyalarının adını belirtir.|
|[/TSAWARE](tsaware-create-terminal-server-aware-application.md)|Özellikle Terminal Server altında çalışacak şekilde tasarlanan bir uygulama oluşturur.|
|[/USEPROFILE](useprofile.md)|İyileştirilmiş bir görüntü oluşturmak için profil temelli iyileştirme eğitimi verilerini kullanır.|
|[/VERBOSE](verbose-print-progress-messages.md)|Bağlayıcı ilerleme iletilerini yazdırır.|
|[/VERSION](version-version-information.md)|Bir sürüm numarası atar.|
|[/WHOLEARCHIVE](wholearchive-include-all-library-object-files.md)|Belirtilen statik kitaplıklardan her nesne dosyasını içerir.|
|[/WıNMD](winmd-generate-windows-metadata.md)|Windows Çalışma Zamanı meta veri dosyası oluşturmayı mümkün bir şekilde sunar.|
|[/WıNMDFıLE](winmdfile-specify-winmd-file.md)|[/Winmd](winmd-generate-windows-metadata.md) bağlayıcı seçeneği tarafından oluşturulan Windows çalışma zamanı meta veri (WinMD) çıkış dosyası için dosya adını belirtir.|
|[/WıNMDKEYFıLE](winmdkeyfile-specify-winmd-key-file.md)|Bir Windows Çalışma Zamanı meta veri dosyasını imzalamak için bir anahtar veya anahtar çiftini belirtir.|
|[/WıNMDKEYCONTAıNER](winmdkeycontainer-specify-key-container.md)|Bir Windows meta veri dosyasını imzalamak için bir anahtar kapsayıcısı belirtir.|
|[/WıNMDDELAYSıGN](winmddelaysign-partially-sign-a-winmd.md)|Ortak anahtarı winmd dosyasına yerleştirerek bir Windows Çalışma Zamanı meta veri (. winmd) dosyasını kısmen imzalar.|
|[/WX](wx-treat-linker-warnings-as-errors.md)|Bağlayıcı uyarılarını hata olarak değerlendirir.|

<sup>16,1</sup> Bu seçenek, Visual Studio 2019 sürüm 16,1 ' den başlayarak kullanılabilir.

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ oluşturma başvurusu](c-cpp-building-reference.md)\
[MSVC bağlayıcı başvurusu](linking.md)
