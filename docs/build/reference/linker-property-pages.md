---
title: Bağlayıcı Özellik Sayfaları
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 55fcefd826ec6ecb153adad495e21ce97aa432f1
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927711"
---
# <a name="linker-property-pages"></a>Bağlayıcı Özellik Sayfaları

Aşağıdaki özellikler **Proje** > **özellikleri** > **yapılandırma**özellikleriBağlayıcısı > altında bulunur. Bağlayıcı hakkında daha fazla bilgi için bkz. [CL 'Yi bağlayıcı](cl-invokes-the-linker.md) ve [bağlayıcı seçeneklerini](linker-options.md)çağırır.

## <a name="general-property-page"></a>Genel özellik sayfası

### <a name="output-file"></a>Çıkış dosyası

[/Out](out-output-file-name.md) seçeneği, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar.

### <a name="show-progress"></a>Ilerlemeyi göster

Bağlayıcı Ilerleme Iletilerini yazdırır

**Yapabileceği**

- **Ayarlanmadı** ; ayrıntı düzeyi yok.
- **Tüm ilerleme Iletilerini görüntüle** -tüm ilerleme iletilerini görüntüler. 
- **Aranan kitaplıklar için** -yalnızca aranan kitaplıkları gösteren ilerleme mesajlarını görüntüler.
- **İyileştirilmiş bağlama SıRASıNDA COMDAT katlama hakkında** -iyileştirilmiş bağlama sırasında COMDAT katlaması hakkındaki bilgileri görüntüler.
- **İyileştirilmiş bağlantı sırasında kaldırılan veriler hakkında** -iyileştirilmiş bağlama sırasında kaldırılan işlevler ve veriler hakkındaki bilgileri görüntüler.
- **SEH ile uyumsuz modüller hakkında** -güvenli özel durum işleme ile uyumsuz modüllerle ilgili bilgileri görüntüler.
- **Yönetilen kodla ilişkili bağlayıcı etkinliği hakkında** -yönetilen kodla ilişkili bağlayıcı etkinliği hakkında bilgi görüntüle.

### <a name="version"></a>Sürüm

[/Version](version-version-information.md) seçeneği, bağlayıcının. exe veya. dll dosyasının üstbilgisine bir sürüm numarası vermesini söyler. **/Version**'nin etkisini görmek IÇIN, Isteğe bağlı üst bilgi değerlerinin görüntü sürümü alanını görmek IÇIN dumpbin/Headers komutunu kullanın.

### <a name="enable-incremental-linking"></a>Artımlı bağlamayı etkinleştir

Artımlı bağlamayı mümkün. ([/INCREINCRE/INCREINCRE:](incremental-link-incrementally.md)NO)

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

[/Nologo](nologo-suppress-startup-banner-linker.md) seçeneği telif hakkı iletisi ve sürüm numarasını görüntülemeyi önler. 

### <a name="ignore-import-library"></a>Içeri aktarma kitaplığını yoksay

Bu özellik, bağlayıcının bu derlemeden oluşturulan herhangi bir. lib çıkışını herhangi bir bağımlı projeye bağmayacağını söyler. Proje sisteminin, inşa edildiğinde. lib dosyası üretmeyen. dll dosyalarını işlemesini sağlar. Bir proje DLL üreten başka bir projeye bağımlıysa, proje sistemi otomatik olarak bu alt proje tarafından oluşturulan. lib dosyasını bağlar. Bu dll 'Ler anlamlı dışarı aktarmalar olmadığından, bu özellik COM DLL 'Leri veya yalnızca kaynak dll 'Leri üreten projelerde gereksiz olabilir. Bir DLL 'nin dışarı aktarmaları yoksa, bağlayıcı bir. lib dosyası oluşturmaz. Export. lib dosyası yoksa ve proje sistemi bağlayıcıya eksik DLL ile bağlantı oluşturmasını söyler, bağlantı başarısız olur. Bu sorunu çözmek için **Içeri aktarma kitaplığını yoksay** özelliğini kullanın. **Evet**olarak ayarlandığında, proje sistemi. lib dosyasının varlığını veya yokluğunu yok sayar ve bu projeye bağımlı tüm projenin varolmayan. lib dosyasıyla bağlantı kurma izni vermesine neden olur.

Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>bkz.

### <a name="register-output"></a>Çıktıyı Kaydet

Yalnızca `regsvr32.exe /s $(TargetPath)` . dll projelerinde geçerli olan yapı çıkışında çalışır. . Exe projeleri için bu özellik yok sayılır. Bir. exe çıkışını kaydetmek için, her zaman kayıtlı. exe dosyaları için gereken özel kaydı yapmak üzere yapılandırmada bir postbuild olayı ayarlayın.

Bu özelliğe programlı bir şekilde erişmek için <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>bkz.

### <a name="per-user-redirection"></a>Kullanıcı başına yeniden yönlendirme

Visual Studio 'da kayıt genellikle HKEY_CLASSES_ROOT (HKCR) içinde yapılır. Windows Vista ve sonraki işletim sistemleriyle, HKCR 'ye erişmek için Visual Studio 'Yu Yükseltilmiş modda çalıştırmalısınız. Geliştiriciler her zaman Yükseltilmiş modda çalıştırmak istemiyor, ancak yine de kayıt ile çalışmak zorunda değildir. Kullanıcı başına yeniden yönlendirme, yükseltilmiş modda çalıştırmak zorunda kalmadan kaydetmenize izin verir.

Kullanıcı başına yeniden yönlendirme, HKCR 'ye yapılan yazmaları HKEY\_Current\_kullanıcısına (HKCU) yeniden yönlendirilecek şekilde zorlar. Kullanıcı başına yeniden yönlendirme kapatılmışsa, program HKCR 'ye yazmaya çalıştığında [proje derleme hatası PRJ0050](../../error-messages/tool-errors/project-build-error-prj0050.md) neden olabilir.

### <a name="additional-library-directories"></a>Ek kitaplık dizinleri

Kullanıcının ortam kitaplık yolunu geçersiz kılmasına izin verir. ([/LIBPATH](libpath-additional-libpath.md): klasör)

### <a name="link-library-dependencies"></a>Bağlantı kitaplığı bağımlılıkları

Bağımlı projeler tarafından üretilen. lib dosyalarının bağlantısının yapılıp yapılmayacağını belirtir. Genellikle,. lib dosyalarında bağlamak istersiniz, ancak belirli dll 'Ler için bu durum olmayabilir.

Ayrıca, dosya adı ve göreli yol (örneğin, ") sağlayarak bir. obj dosyası da belirtebilirsiniz. \\. \Mylibproject\myobjfile.exe ". . Obj dosyasının kaynak kodu önceden derlenmiş bir üst bilgi #includes (örneğin, pch. h), pch. obj dosyası MyObjFile. obj ile aynı klasörde bulunur. Ayrıca, pch. obj ' i ek bir bağımlılık olarak eklemeniz gerekir.

### <a name="use-library-dependency-inputs"></a>Kitaplık Bağımlılığı Girişlerini Kullan

Proje bağımlılıklarının kitaplık çıkışları arasında bağlantı sırasında, kitaplık dosyasının kendisi yerine kütüphaneian aracında girişlerin kullanılıp kullanılmayacağını belirtir. Büyük bir projede, bağımlı bir proje. lib dosyası üretdiğinde, artımlı bağlama devre dışıdır. . Lib dosyaları üreten çok sayıda bağımlı proje varsa, uygulamayı oluşturmak uzun sürebilir. Bu özellik **Evet**olarak ayarlandığında, proje sistemi bağımlı projeler tarafından üretilen. LIBS için. obj dosyalarında, artımlı bağlamayı etkinleştirerek bağlantı sağlar.

**Genel** bağlayıcı özellik sayfasına erişme hakkında daha fazla bilgi için bkz. [Visual Studio C++ 'Da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

### <a name="link-status"></a>Bağlantı durumu

Bağlayıcının bağlantının yüzdesinin tamamlandığını gösteren bir ilerleme göstergesi görüntüleyip görüntülemeyeceği meyeceğini belirtir. Varsayılan değer bu durum bilgilerini göstermemelidir. ([/LTCG](ltcg-link-time-code-generation.md): DURUM | LTCG: NOSTATUS)

### <a name="prevent-dll-binding"></a>DLL bağlamasını engelle

[/Allowbind](allowbind-prevent-dll-binding.md): No, dll 'nin üst bilgisinde, görüntünün bağlı olmasına izin verilmediğini belirten bir bit belirler. Dijital olarak imzalanmışsa DLL 'nin bağlanmasını istemeyebilirsiniz (bağlama imzayı geçersiz kılar).

### <a name="treat-linker-warning-as-errors"></a>Bağlayıcı uyarısını hata olarak değerlendir

[/WX](wx-treat-linker-warnings-as-errors.md) , bağlayıcı bir uyarı oluşturursa hiçbir çıkış dosyası oluşturulmasına neden olur.

### <a name="force-file-output"></a>Dosya çıkışını zorla

[/Force](force-force-file-output.md) seçeneği bağlayıcıya bir. exe dosyası veya dll oluşturulmasını söyler, ancak tanımlanmamış ya da tanımlanmış çarpma olur. Geçersiz. exe dosyası oluşturabilir.

**Yapabileceği**

- **Enabled** -/Force bağımsız değişken olmadan hem birden çok hem de çözülmemiş anlamına gelir.
- **Yalnızca tanımlanmış sembolü çarpın** -bağlantı, bir sembol için birden fazla tanım bulsa bile, çıkış dosyası oluşturmak için/Force: MULTIPLE kullanın.
- **Yalnızca tanımsız sembol** -bağlantının tanımsız bir sembol bulmadığını bir çıkış dosyası oluşturmak için/Force: çözümlenmemiş kullanın. /FORCE: giriş noktası simgesi çözülmedi ise ÇÖZÜMLENMEMIŞ yok sayılır.

### <a name="create-hot-patchable-image"></a>Etkin bir Patchımage oluştur

Anında düzeltme için bir görüntü hazırlar.

**Yapabileceği**

- **Enabled** -bir görüntüyü anında düzeltme için hazırlar.
- **Yalnızca x86 görüntüsü** -anında düzeltme Için bir x86 görüntüsü hazırlar.
- **Yalnızca x64 görüntüsü** -anında düzeltme Için bir x64 görüntüsü hazırlar.
- **Yalnızca Itanium görüntüsü** -anında düzeltme için Itanium görüntüsü hazırlar.

### <a name="specify-section-attributes"></a>Bölüm özniteliklerini belirt

[/Section](section-specify-section-attributes.md) seçeneği bir bölümün özniteliklerini değiştirir, bölüm için. obj dosyası derlendiğinde ayarlanan öznitelikleri geçersiz kılar.

## <a name="input-property-page"></a>Giriş özellik sayfası

### <a name="additional-dependencies"></a>{1&gt;Ek Bağımlılıklar&lt;1}

Bağlantı komut satırına eklenecek ek öğeleri belirtir, örneğin *Kernel32. lib*.

### <a name="ignore-all-default-libraries"></a>Tüm varsayılan kitaplıkları Yoksay

[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) seçeneği bağlayıcıya, dış başvuruları çözümlerken aradığı kitaplık listesinden bir veya daha fazla varsayılan kitaplığı kaldırmasını söyler. 

### <a name="ignore-specific-default-libraries"></a>Belirli varsayılan kitaplıkları Yoksay

Yoksayılacak bir veya daha fazla varsayılan kitaplık adını belirtir. Birden çok kitaplığı noktalı virgülle ayırın. (/NODEFAULTLıB: [ad, ad,...])

### <a name="module-definition-file"></a>Modül tanım dosyası

[/Def](def-specify-module-definition-file.md) seçeneği bir modül tanım dosyasını (. def) bağlayıcıya geçirir. BAĞLAMAK için yalnızca bir. def dosyası belirtilebilir. 

### <a name="add-module-to-assembly"></a>Modülü derlemeye Ekle

[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md) seçeneği bir derlemeye modül başvurusu eklemenize olanak tanır. Modüldeki tür bilgileri, modül başvurusunu ekleyen derleme programı tarafından kullanılamaz. Ancak, modüldeki tür bilgileri derlemeye başvuran tüm programlar için kullanılabilir olacaktır.

### <a name="embed-managed-resource-file"></a>Yönetilen kaynak dosyasını katıştır

[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) bir kaynak dosyasını çıkış dosyasına katıştırır.

### <a name="force-symbol-references"></a>Sembol başvurularını zorla

[/Include](include-force-symbol-references.md) seçeneği bağlayıcıya sembol tablosuna belirtilen bir sembol eklemesini söyler.

### <a name="delay-loaded-dlls"></a>Yüklenen dll 'Leri geciktir

[/Delayload](delayload-delay-load-import.md) seçeneği dll 'lerin gecikmeli yüklenmesine neden olur. DLL adı, yükü geciktirmek için bir DLL belirtir. 

### <a name="assembly-link-resource"></a>Derleme bağlantısı kaynağı

[/Assemblylinkresource](assemblylinkresource-link-to-dotnet-framework-resource.md) seçeneği, çıkış dosyasında bir .NET Framework kaynağına bir bağlantı oluşturur; kaynak dosyası çıkış dosyasına yerleştirilmez.

## <a name="manifest-file-property-page"></a>Bildirim dosyası özellik sayfası

### <a name="generate-manifest"></a>Bildirim oluştur

[/Manifest](manifest-create-side-by-side-assembly-manifest.md) bağlayıcının yan yana bildirim dosyası oluşturması gerektiğini belirtir.

### <a name="manifest-file"></a>Bildirim dosyası

[/ManifestFile](manifestfile-name-manifest-file.md) bildirim dosyasının varsayılan adını değiştirmenize olanak sağlar. Bildirim dosyasının varsayılan adı. manifest eklenmiş dosya adıdır.

### <a name="additional-manifest-dependencies"></a>Ek bildirim bağımlılıkları

[/Manifestdependency](manifestdependency-specify-manifest-dependencies.md) , bildirim dosyasının bağımlılık bölümüne yerleştirilecek öznitelikleri belirtmenize olanak tanır.

### <a name="allow-isolation"></a>Yalıtıma izin ver

Bildirim arama için davranışı belirtir. ([/ALLOWISOLATION](allowisolation-manifest-lookup.md): NO)

### <a name="enable-user-account-control-uac"></a>Kullanıcı hesabı denetimini etkinleştir (UAC)

Kullanıcı hesabı denetiminin etkinleştirilip etkinleştirilmeyeceğini belirtir.  ([/LİMESTUAC](manifestuac-embeds-uac-information-in-manifest.md),/MANIFESTUAC: NO)

### <a name="uac-execution-level"></a>UAC yürütme düzeyi

Kullanıcı hesabı denetimiyle çalışırken uygulama için istenen yürütme düzeyini belirtir.  (/BILDIRIMLI estuac: Level = [değer])

**Yapabileceği**

- **asInvoker** -UAC yürütme düzeyi: başlatıcı olarak.
- **highestAvailable** -UAC yürütme düzeyi: en yüksek kullanılabilir.
- **requireAdministrator** -UAC yürütme düzeyi: yönetici gerektir.

### <a name="uac-bypass-ui-protection"></a>UAC UI korumasını atla

Masaüstündeki diğer pencereler için Kullanıcı arabirimi koruma düzeylerinin atlanıp atlanmayacağını belirtir.  Bu özelliği yalnızca erişilebilirlik uygulamaları için ' Yes ' olarak ayarlayın.  ([/Bildirimli estuac](manifestuac-embeds-uac-information-in-manifest.md): UIAccess = [true | false])

## <a name="debugging-property-page"></a>Özellik sayfasında hata ayıklama

### <a name="generate-debug-info"></a>Hata ayıklama bilgisi oluştur

Bu seçenek,. exe dosyası veya DLL için hata ayıklama bilgisi oluşturmayı sağlar.

**Yapabileceği**

- **Hayır** -hata ayıklama bilgisi üretmez.
- **Hata ayıklama bilgileri oluştur** -Microsoft sembol sunucusu 'na dağıtım için ideal olan tam bir program VERITABANı (pdb) oluşturun.
- **Daha hızlı bağlantılar için Iyileştirilmiş hata ayıklama bilgileri oluştur** -düzenleme-bağlantı-hata ayıklama çevrimi için ideal bir program VERITABANı (pdb) oluşturur. 
- **Paylaşım ve yayımlama için Iyileştirilmiş hata ayıklama bilgileri oluştur** -düzenleme-bağlantı-hata ayıklama çevrimi için ideal bir program VERITABANı (pdb) oluşturur. 

### <a name="generate-program-database-file"></a>Program veritabanı dosyası oluştur

Varsayılan olarak, [/Debug](debug-generate-debug-info.md) belirtildiğinde, bağlayıcı hata ayıklama bilgilerini tutan bir program VERITABANı (pdb) oluşturur. PDB için varsayılan dosya adı programın temel adına ve. pdb uzantısına sahiptir.

### <a name="strip-private-symbols"></a>Özel sembolleri sök

[/Pdbçıkarıldı](pdbstripped-strip-private-symbols.md) seçeneği, bir PDB dosyası (/Debug,/Z7,/ZD veya/Zi) oluşturan derleyici veya bağlayıcı seçeneklerinden herhangi biriyle program görüntünüzü oluştururken ikinci program VERITABANı (pdb) dosyası oluşturur.

### <a name="generate-map-file"></a>Eşleme dosyası oluştur

[/Map](map-generate-mapfile.md) seçeneği, bağlayıcıya bir mapfile oluşturmasını söyler.

### <a name="map-file-name"></a>Eşleme dosyası adı

Mapfile için Kullanıcı tarafından belirtilen bir ad. Varsayılan adı değiştirir.

### <a name="map-exports"></a>Eşleme dışarı aktarmaları

[/MapInfo](mapinfo-include-information-in-mapfile.md) seçeneği, bağlayıcıya,/Map seçeneğini belirtirseniz oluşturulan bir mapfile öğesine belirtilen bilgileri dahil etmek üzere söyler. Dışarı aktarmalar, bağlayıcıya dışarı aktarılan işlevleri eklemesini söyler.

### <a name="debuggable-assembly"></a>Hata ayıklanabilir derlemesi

[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md) hata ayıklama bilgileri izleme ile hata ayıklayıcı ggableattribute özniteliğini yayar ve JIT iyileştirmelerini devre dışı bırakır.

## <a name="system-property-page"></a>Sistem özellik sayfası

### <a name="subsystem"></a>Sistemin

[/Subsystem](subsystem-specify-subsystem.md) seçeneği işletim sistemine. exe dosyasını nasıl çalıştıracağını söyler. Alt sistem seçimi, bağlayıcının seçim kullanacağı giriş noktası sembolünü (veya giriş noktası işlevini) etkiler.

**Yapabileceği**

- **Ayarlanmadı** -alt sistem ayarlanmadı.
- **Konsol** -Win32 karakter modu uygulaması. Konsol uygulamalarına, işletim sistemi tarafından bir konsol verilir. Main veya wmain tanımlanmışsa, konsol varsayılandır.
- **Windows** -uygulama, büyük olasılıkla Kullanıcı etkileşimi için kendi pencerelerini oluşturduğundan, bir konsol gerektirmez. WinMain veya wWinMain tanımlanmışsa, WINDOWS varsayılandır.
- Windows NT için **Yerel** cihaz sürücüleri. /DRıVER: WDM belirtilmişse, yerel varsayılandır.
- **EFI uygulaması** -EFI uygulaması.
- **EFI Önyükleme hizmeti sürücüsü** -EFI Önyükleme hizmeti sürücüsü.
- **EFI ROM** -EFI ROM 'U.
- **EFI çalışma zamanı** -EFI çalışma zamanı.
- **POSIX** -Windows NT 'de POSIX alt sistemi ile çalışan uygulama.

### <a name="minimum-required-version"></a>Gerekli en düşük sürüm

Alt sistemin gerekli en düşük sürümünü belirtin. Bağımsız değişkenler 0 ile 65.535 aralığındaki ondalık sayılardır.

### <a name="heap-reserve-size"></a>Yığın ayırma boyutu

Sanal bellekte toplam yığın ayırma boyutunu belirtir. Varsayılan değer 1 MB 'tır.    ([/Heap](heap-set-heap-size.md): Reserve)

### <a name="heap-commit-size"></a>Yığın kayıt boyutu

Fiziksel bellekte toplam yığın ayırma boyutunu belirtir. Varsayılan değer 4 KB 'tır.    ([/Heap](heap-set-heap-size.md): Reserve, COMMIT)

### <a name="stack-reserve-size"></a>Yığın ayırma boyutu

Sanal bellekteki toplam yığın ayırma boyutunu belirtir. Varsayılan değer 1 MB 'tır.     ([/Stack](stack-stack-allocations.md): Reserve)

### <a name="stack-commit-size"></a>Yığın kayıt boyutu

Fiziksel bellekte toplam yığın ayırma boyutunu belirtir. Varsayılan değer 4 KB 'tır.     ([/Stack](stack-stack-allocations.md): Reserve, COMMIT)

### <a name="enable-large-addresses"></a>Büyük adresleri etkinleştir

[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md) seçeneği, bağlayıcıya uygulamanın 2 gigabayt 'tan daha büyük adresler işleyebileceğini söyler. Varsayılan olarak, bağlayıcı satırında/LARGEADDRESSAWARE belirtilmemişse,/LARGEADDRESSAWARE: NO etkin değildir.

### <a name="terminal-server"></a>Terminal Sunucusu

[/TSAWARE](tsaware-create-terminal-server-aware-application.md) seçeneği, program görüntüsünün isteğe bağlı üstbilgisindeki IMAGE_OPTIONAL_HEADER dllözellikler alanında bir bayrak ayarlar. Bu bayrak ayarlandığında, Terminal sunucusu uygulamada belirli değişiklikler yapmayacak.

### <a name="swap-run-from-cd"></a>CD 'Den takas Çalıştır

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) seçeneği işletim sistemine ilk olarak bağlayıcı çıkışını bir takas dosyasına kopyalamasını söyler ve sonra görüntüyü oradan çalıştırır. Bu seçenek bir Windows NT 4,0 (ve üzeri) özelliğidir. **CD** belirtildiğinde, işletim sistemi çıkarılabilir bir diskteki görüntüyü bir sayfa dosyasına kopyalar ve ardından yükler.

### <a name="swap-run-from-network"></a>Ağdan takas çalıştırması

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) seçeneği işletim sistemine ilk olarak bağlayıcı çıkışını bir takas dosyasına kopyalamasını söyler ve sonra görüntüyü oradan çalıştırır. Bu seçenek bir Windows NT 4,0 (ve üzeri) özelliğidir. **Net** belirtilirse, işletim sistemi ilk olarak ağdan ikili görüntüyü bir takas dosyasına kopyalar ve buradan yükler. Bu seçenek, ağ üzerinden uygulama çalıştırmak için yararlıdır.

### <a name="driver"></a>Sürücü

Windows NT Çekirdek modu sürücüsü oluşturmak için [/Driver](driver-windows-nt-kernel-mode-driver.md) bağlayıcı seçeneğini kullanın.

**Yapabileceği**

- **Ayarlanmadı** -varsayılan sürücü ayarı.
- **Sürücü** sürücüsü
- **Yalnızca yukarı** -/sürücü: uponly, bağlayıcının bir tek IŞLEMCILI (up) sürücü olduğunu belirtmek için çıkış ÜSTBILGISINDEKI özelliklere IMAGE_FILE_UP_SYSTEM_ONLY bitini eklemesine neden olur. İşletim sistemi, çok işlemcili (MP) bir sisteme bir UP sürücüsü yüklemeyi reddeder.
- **WDM** -/Driver: WDM, bağlayıcının, isteğe bağlı üstbilginin DLLÖZELLIKLER alanındaki IMAGE_DLLCHARACTERISTICS_WDM_DRIVER bitini ayarlamaya neden olur.

## <a name="optimization-property-page"></a>İyileştirme Özellik sayfası

### <a name="references"></a>Referanslar

[/Opt](opt-optimizations.md): ref hiçbir şekilde başvurulmayan işlevleri ve/veya verileri ortadan kaldırır; ancak hiçbir şekilde başvurulmayan işlevleri ve/veya verileri tutar.

### <a name="enable-comdat-folding"></a>COMDAT Katlamasını Etkinleştir

Aynı COMDAT katlamayı\[gerçekleştirmek için [/opt](opt-optimizations.md): ICF = yineleme] kullanın.

### <a name="function-order"></a>İşlev sırası

[/Order](order-put-functions-in-order.md)seçeneği, belirli Comtts 'yi önceden belirlenmiş bir sırada görüntüye YERLEŞTIREREK, bağlantıyı programınızı iyileştirmenize söyler. BAĞLANTı, işlevleri görüntüdeki her bölüm içinde belirtilen sırada koyar.

### <a name="profile-guided-database"></a>Profil temelli veritabanı

Profil temelli iyileştirmeler için. pgd dosyası belirtin. ([/PGD](pgd-specify-database-for-profile-guided-optimizations.md))

### <a name="link-time-code-generation"></a>Bağlama zaman kodu oluşturma

Bağlantı zamanı kod oluşturmayı belirtir. ([/LTCG](ltcg-link-time-code-generation.md))

**Yapabileceği**

- **Varsayılan** -varsayılan LTCG ayarı.
- **Hızlı bağlama zaman kodu oluşturma kullan** - [/Fastgenprofile](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)Ile bağlama zaman kodu üretimini kullanın.
- **Bağlama sırasında kod oluşturmayı kullan** - [bağlantı zaman kodu oluşturmayı](ltcg-link-time-code-generation.md)kullan.
- **Profil temelli iyileştirme-gereç** -:P gınstrumle [Profil temelli iyileştirme](../profile-guided-optimizations.md) kullanın.
- **Profil temelli iyileştirme-iyileştirme** -en iyi duruma getirilmiş bir görüntü oluşturmak için, bağlayıcının izlenen ikiliyi çalıştırdıktan sonra oluşturulan profil verilerini kullanması gerektiğini belirtir.
- **Profil temelli iyileştirme-Güncelleştir** -:P gınstrumm aşamasında belirtilenden eklenecek veya değiştirilecek giriş dosyalarının listesine izin verir ve bunları izler.

## <a name="embedded-idl-property-page"></a>Katıştırılmış IDL özellik sayfası

### <a name="midl-commands"></a>MıDL komutları

MıDL komut satırı seçeneklerini belirtin. ([/MIDL](midl-specify-midl-command-line-options.md):@responsefile)

### <a name="ignore-embedded-idl"></a>Gömülü IDL 'yi yoksay

[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md) seçeneği, kaynak KODUNDAKI tüm IDL özniteliklerinin bir. IDL dosyasına işlenmediğini belirtir.

### <a name="merged-idl-base-file-name"></a>Birleştirilmiş IDL taban dosyası adı

[/IDLOUT](idlout-name-midl-output-files.md) seçeneği,. IDL dosyasının adını ve uzantısını belirtir.

### <a name="type-library"></a>Tür kitaplığı

[/Tlhakkında](tlbout-name-dot-tlb-file.md) seçeneği. tlb dosyasının adını ve uzantısını belirtir.

### <a name="typelib-resource-id"></a>Tür kitaplığı kaynak KIMLIĞI

Bağlayıcı tarafından oluşturulan tür kitaplığının kaynak KIMLIĞINI belirtmenize olanak tanır. ([/Tldeklarasyon](tlbid-specify-resource-id-for-typelib.md): kimlik)

## <a name="windows-metadata-property-page"></a>Windows meta verileri özellik sayfası

### <a name="generate-windows-metadata"></a>Windows meta verileri oluştur

Windows meta verilerinin oluşturulmasını etkinleştirilir veya devre dışı bırakır.

**Yapabileceği**

- **Evet** -Windows meta veri dosyalarının oluşturulmasını etkinleştirin.
- **Hayır** -Windows meta veri dosyalarının oluşturulmasını devre dışı bırak.

### <a name="windows-metadata-file"></a>Windows meta veri dosyası

[/WinMDFile](winmdfile-specify-winmd-file.md) seçenek anahtarı.

### <a name="windows-metadata-key-file"></a>Windows meta verileri anahtar dosyası

Bir Windows meta verilerini imzalamak için anahtar veya anahtar çiftini belirtin. ([/Winmdkeyfile](winmdkeyfile-specify-winmd-key-file.md): filename)

### <a name="windows-metadata-key-container"></a>Windows meta verileri anahtar kapsayıcısı

Windows meta verilerini imzalamak için bir anahtar kapsayıcısı belirtin. ([/Winmdkeycontainer](winmdkeycontainer-specify-key-container.md): ad)

### <a name="windows-metadata-delay-sign"></a>Windows meta veri gecikmesi Işareti

Windows meta verilerini kısmen imzala. Yalnızca ortak anahtarı Windows meta verilerine yerleştirmek istiyorsanız [/Winmddelaysign](winmddelaysign-partially-sign-a-winmd.md) kullanın. Varsayılan değer/WINMDDELAYSIGN: NO ' dır.

## <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

### <a name="entry-point"></a>Girdi Noktası

[/Entry](entry-entry-point-symbol.md) seçeneği bir. exe dosyası veya dll için başlangıç adresi olarak bir giriş noktası işlevi belirtir.

### <a name="no-entry-point"></a>Giriş noktası yok

Yalnızca kaynak DLL oluşturmak için [/NOENTRY](noentry-no-entry-point.md)seçeneği gereklidir. Bağlantının dll `_main` 'ye başvuru bağlamasını engellemek için bu seçeneği kullanın.

### <a name="set-checksum"></a>Sağlama toplamını ayarla

[/Release](release-set-the-checksum.md) seçeneği,. exe dosyasının üst bilgisindeki sağlama toplamını ayarlar.

### <a name="base-address"></a>Temel adres

Program için bir temel adres ayarlar. ([/Base](base-base-address.md): {Adres\[, boyut] | @filename, anahtar})

### <a name="randomized-base-address"></a>Rastgele temel adres

Rastgele temel adres. ([/DYNAMİCBASE](dynamicbase-use-address-space-layout-randomization.md)\[: NO])

### <a name="fixed-base-address"></a>Sabit temel adres

Yalnızca tercih edilen temel adresinde yüklenebilen bir program oluşturur. ([/FİXED](fixed-fixed-base-address.md)\[: NO])

### <a name="data-execution-prevention-dep"></a>Veri Yürütme Engellemesi (DEP)

Bir yürütülebilir dosyayı Windows Veri Yürütme Engellemesi özelliği ile uyumlu olacak şekilde işaretler. ([/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)\[: NO])

### <a name="turn-off-assembly-generation"></a>Derleme oluşturmayı kapat

[/NoAssembly](noassembly-create-a-msil-module.md) seçeneği, bağlayıcıya .NET Framework bütünleştirilmiş kodu olmadan geçerli çıkış dosyası için bir görüntü oluşturmasını söyler.

### <a name="unload-delay-loaded-dll"></a>Yüklenen DLL 'yi kaldırma gecikmesi

**Kaldırma** niteleyicisi, gecikme Yükleme Yardımcısı işlevine dll 'nin açıkça kaldırılmasını desteklememesini söyler. ([/DELAY](delay-delay-load-import-settings.md): UNLOAD)

### <a name="nobind-delay-loaded-dll"></a>Nobind gecikmeli yüklendi DLL

**Nobind** niteleyicisi, bağlayıcının son görüntüde bağlanabilir bir IAT içermeyeceğini söyler. Varsayılan olarak, Gecikmeli yüklenen dll 'Ler için bağlanabilir ıAT oluşturulur. ([/DELAY](delay-delay-load-import-settings.md): NOBİND)

### <a name="import-library"></a>Kitaplığı İçeri Aktar

Varsayılan içeri aktarma kitaplığı adını geçersiz kılar. ([/IMPLIB](implib-name-import-library.md): filename)

### <a name="merge-sections"></a>Bölümleri Birleştir

[/Merge](merge-combine-sections.md) seçeneği, ilk bölümü (öğesinden) ikinci bölümle birleştirir, sonuç bölümünü olarak adlandırın. Örneğin,/merge:. rdata =. Text.

### <a name="target-machine"></a>Hedef makine

[/MACHINE](machine-specify-target-platform.md) seçeneği program için hedef platformu belirtir.

**Yapabileceği**

- **Ayarlanmadı**
- **Machineard**
- **MachineARM64**
- **MachineEBC**
- **MachineIA64**
- **Machinemıps**
- **MachineMIPS16**
- **Machinemıpsfpu**
- **MachineMIPSFPU16**
- **MachineSH4**
- **MachineTHUMB**
- **MachineX64**
- **MachineX86**

### <a name="profile"></a>Profil

Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir. GenerateDebugInformation (/[/Debug](debug-generate-debug-info.md)) ayarlanmasını gerektirir. ([/PROFİLE](profile-performance-tools-profiler.md))

### <a name="clr-thread-attribute"></a>CLR Iş parçacığı özniteliği

CLR programınızın giriş noktası için iş parçacığı oluşturma özniteliğini açıkça belirtin.

**Yapabileceği**

- **MTA iş parçacığı özniteliği** -MTAThreadAttribute özniteliğini programınızın giriş noktasına uygular.
- **STA iş parçacığı özniteliği** -, programınızın giriş noktasına STAThreadAttribute özniteliğini uygular.
- **Varsayılan iş parçacığı özniteliği** - [/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)Belirtmemeye benzer. Ortak dil çalışma zamanının (CLR) varsayılan iş parçacığı özniteliğini ayarlamaya izin verir.

### <a name="clr-image-type"></a>CLR görüntü türü

CLR görüntüsünün türünü (ıJW, saf veya güvenli) ayarlar.

**Yapabileceği**

- **IJW görüntüsünü zorla**
- **Saf Il görüntüsünü zorla**
- **Güvenli Il görüntüsünü zorla**
- **Varsayılan görüntü türü**

### <a name="key-file"></a>Anahtar dosyası

Bir derlemeyi imzalamak için anahtar veya anahtar çiftini belirtin. ([/Keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md): filename)

### <a name="key-container"></a>Anahtar kapsayıcısı

Bir derlemeyi imzalamak için bir anahtar kapsayıcısı belirtin. ([/Keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md): ad)

### <a name="delay-sign"></a>Gecikmeli Imza

Bir derlemeyi kısmen imzalayın. Yalnızca ortak anahtarı derlemeye koymak istiyorsanız [/delaysign](delaysign-partially-sign-an-assembly.md) kullanın. Varsayılan değer/DELAYSIGN: NO ' dır.

### <a name="clr-unmanaged-code-check"></a>CLR yönetilmeyen kod denetimi

[/CLRUNMANAGEDCODECHECK](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md) , bağlayıcının SuppressUnmanagedCodeSecurityAttribute ' i yönetilen koddan yerel dll 'lere, bağlayıcı tarafından oluşturulan PInvoke çağrılarına uygulayıp uygulayamayacağını belirtir.

### <a name="error-reporting"></a>Hata Raporlama

İç derleyici hatası (ıCE) bilgilerini doğrudan görsel C++ ekibe sağlamanıza olanak tanır.

**Yapabileceği**

- **Hemen sor** -hemen sor.
- Sonraki oturum açma kuyruğunun **sonraki oturum açma** sırası.
- **Hata raporu gönder** -hata raporu gönder.
- **Hata raporu yok** -hata raporu yok.

### <a name="sectionalignment"></a>Sectionhizalaması

[/ALIGN](align-section-alignment.md) seçeneği, programın doğrusal adres alanındaki her bölümün hizalamasını belirtir. Sayı bağımsız değişkeni bayt cinsinden ve ikinin üssü olmalıdır.

### <a name="preserve-last-error-code-for-pinvoke-calls"></a>PInvoke çağrıları için son hata kodunu koru

Varsayılan olarak açık olan [/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md), P/Invoke mekanizması aracılığıyla çağrılan işlevlerin son hata kodunu korur, bu da/clrile derlenen koddan dll 'lerde yerel işlevleri çağırmanıza olanak sağlar.

**Yapabileceği**

- **Etkin** -CLRSUPPORTLASTERROR 'ü etkinleştirin.
- **Devre dışı** -CLRSUPPORTLASTERROR 'ü devre dışı bırakın.
- **Yalnızca sistem dll** 'leri-yalnızca sistem dll 'Leri için CLRSUPPORTLASTERROR 'ü 'ı etkinleştirin.

### <a name="image-has-safe-exception-handlers"></a>Görüntüde güvenli özel durum Işleyicileri vardır

[/SafeSEH](safeseh-image-has-safe-exception-handlers.md) belirtildiğinde, bağlayıcı yalnızca görüntünün güvenli özel durum işleyicilerinin bir tablosunu oluşturmak için bir görüntü oluşturur. Bu tablo, görüntü için geçerli olan özel durum işleyicilerinin hangi işletim sistemini belirtir.
