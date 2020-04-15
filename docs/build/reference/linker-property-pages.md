---
title: Bağlayıcı Özellik Sayfaları
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 7e7671e5-a35a-4e67-9bdb-661d75c4d11e
ms.openlocfilehash: 2f2068c6c51fc6bf4e4104213e946e243fc6df2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336582"
---
# <a name="linker-property-pages"></a>Bağlayıcı Özellik Sayfaları

Aşağıdaki özellikler **Project** > **Properties** > **Configuration Properties** > **Linker**altında bulunur. Bağlayıcı hakkında daha fazla bilgi için, [cl Linker](cl-invokes-the-linker.md) ve [Bağlayıcı Seçenekleri](linker-options.md)çağırır bakın.

## <a name="general-property-page"></a>Genel Özellik Sayfası

### <a name="output-file"></a>Çıktı Dosyası

[/OUT](out-output-file-name.md) seçeneği, bağlayıcının oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar.

### <a name="show-progress"></a>İlerlemeyi Göster

Bağlayıcı İlerleme Mesajlarını Yazdırır

**Seçenekler**

- **Set değil** - Hayır ayrıntılılık.
- **Tüm ilerleme iletilerini görüntüler** - Tüm ilerleme iletilerini görüntüler.
- **Aranan Kütüphaneler İçin** - Yalnızca aranan kitaplıkları gösteren ilerleme iletilerini görüntüler.
- **Optimize edilmiş bağlantı sırasında COMDAT katlama hakkında** - Optimize edilmiş bağlantı sırasında COMDAT katlama hakkındaki bilgileri görüntüler.
- **En iyi duruma getirilmiş bağlantı sırasında kaldırılan veriler hakkında** - En iyi duruma getirilmiş bağlantı sırasında kaldırılan işlevler ve veriler le ilgili bilgileri görüntüler.
- **SEH ile uyumsuz modüller hakkında** - Güvenli Özel Durum Kullanımıyla uyumsuz modüller hakkındaki bilgileri görüntüler.
- **Yönetilen kodla ilgili bağlayıcı etkinliği hakkında** - Yönetilen kodla ilgili bağlayıcı etkinliği hakkında bilgi görüntüleyin.

### <a name="version"></a>Sürüm

[/VERSION](version-version-information.md) seçeneği, bağlayıcıya .exe veya .dll dosyasının üstbilgisine bir sürüm numarası koymasını söyler. **/VERSION'un**etkisini görmek için İsteğE BAĞLI ÜSTBILGI DEĞERLerinin görüntü sürüm alanını görmek için DUMPBIN /HEADERS'ı kullanın.

### <a name="enable-incremental-linking"></a>Artımlı Bağlamayı Etkinleştir

Artımlı bağlantı sağlar. ([/ARTıMLı](incremental-link-incrementally.md), /ArtıMLı:HAYıR)

### <a name="suppress-startup-banner"></a>Başlangıç Banner'ı bastır

[/NOLOGO](nologo-suppress-startup-banner-linker.md) seçeneği, telif hakkı iletisinin ve sürüm numarasının görüntülenmesini engeller.

### <a name="ignore-import-library"></a>Alma Kitaplığını Yoksay

Bu özellik, bağlayıcıya bu yapıdan oluşturulan herhangi bir .lib çıktısını bağımlı bir projeye bağlamamasını söyler. Proje sisteminin ,.lib dosyası oluşturmadığında .lib dosyasını oluşturmayan .dll dosyalarını işlemesini sağlar. Bir proje DLL üreten başka bir projeye bağlıysa, proje sistemi otomatik olarak o alt proje tarafından üretilen .lib dosyasını bağlar. Bu özellik, com dls veya kaynak yalnızca DLLs üreten projelerde gereksiz olabilir, bu DLs anlamlı bir dışa aktarma yok çünkü. Bir DLL'nin dışa aktarımları yoksa, bağlayıcı .lib dosyası oluşturmaz. Dışa aktarma .lib dosyası yoksa ve proje sistemi bağlantıcıya eksik DLL ile bağlantı kurmasını söylüyorsa, bağlantı başarısız olur. Bu sorunu gidermek için **İçe Aktarma Özelliği'ni** kullanın. **Evet**olarak ayarlandığında, proje sistemi .lib dosyasının varlığını veya yokluğunu yoksayarlar ve bu projeye bağlı olan herhangi bir projenin var olmayan .lib dosyasıyla bağlantı kurmamasını sağlar.

Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.IgnoreImportLibrary%2A>erişmek için bkz.

### <a name="register-output"></a>Kayıt Çıktısı

Yalnızca `regsvr32.exe /s $(TargetPath)` .dll projelerinde geçerli olan yapı çıktısı üzerinde çalışır. .exe projeleri için bu özellik yoksayılır. Bir .exe çıktısı kaydetmek için, kayıtlı .exe dosyaları için her zaman gerekli olan özel kaydı yapmak için yapılandırmada bir postbuild olayı ayarlayın.

Bu özelliğe programlı olarak <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RegisterOutput%2A>erişmek için bkz.

### <a name="per-user-redirection"></a>Kullanıcı Başına Yeniden Yönlendirme

Visual Studio'ya kayıt geleneksel olarak HKEY_CLASSES_ROOT 'de (HKCR) yapılmıştır. Windows Vista ve daha sonraki işletim sistemleri ile HKCR'a erişmek için Visual Studio'yı yüksek modda çalıştırmanız gerekir. Geliştiriciler her zaman yükseltilmiş modda çalıştırmak istemiyorum, ancak yine de kayıt ile çalışması gerekir. Kullanıcı başına yeniden yönlendirme, yükseltilmiş modda çalıştırmak zorunda kalmadan kaydolmanıza olanak tanır.

Kullanıcı başına yeniden yönlendirme, herhangi bir yazının HKEY\_CURRENT\_USER'a (HKCU) yönlendirilmesi için HKCR'ye yönlendirilmesine zorlar. Kullanıcı başına yeniden yönlendirme kapatılırsa, program HKCR'a yazmaya çalıştığında [Proje Oluşturma Hatası PRJ0050'ye](../../error-messages/tool-errors/project-build-error-prj0050.md) neden olabilir.

### <a name="additional-library-directories"></a>Ek Kütüphane Dizinleri

Kullanıcının çevre kitaplığı yolunu geçersiz kılmasına olanak tanır. ([/LIBPATH](libpath-additional-libpath.md):klasör)

### <a name="link-library-dependencies"></a>Bağlantı Kitaplığı Bağımlılıkları

Bağımlı projeler tarafından üretilen .lib dosyalarının bağlanıp bağlanmayacağını belirtir. Genellikle,.lib dosyalarına bağlanmak istersiniz, ancak belirli DL'ler için durum böyle olmayabilir.

Ayrıca, dosya adı ve göreli yol sağlayarak bir .obj dosyası belirtebilirsiniz, örneğin "... \\.. \MyLibProject\MyObjFile.obj". .obj dosyasının kaynak kodu önceden derlenmiş bir üstbilgi #includes varsa, örneğin pch.h, pch.obj dosyası MyObjFile.obj ile aynı klasörde bulunur. Ayrıca ek bir bağımlılık olarak pch.obj eklemeniz gerekir.

### <a name="use-library-dependency-inputs"></a>Kitaplık Bağımlılık Girişlerini Kullanma

Proje bağımlılıklarının kitaplık çıktılarına bağlantı verirken, girişleri kitaplık dosyasının kendisi yerine kütüphaneci aracına kullanıp kullanmayacağımı belirtir. Büyük bir projede, bağımlı bir proje bir .lib dosyası üretirken, artımlı bağlantı devre dışı bırakılır. .lib dosyaları üreten çok sayıda bağımlı proje varsa, uygulamanın oluşturulması uzun sürebilir. Bu özellik **Evet**olarak ayarlandığında, proje sistemi .obj dosyalarına bağımlı projeler tarafından üretilen .libs'i bağlar ve artımlı bağlamayı sağlar.

**Genel** bağlayıcı özellik sayfasına nasıl erişici görünebilirsiniz hakkında bilgi için [Bkz. C++ derleyicisi ayarlanın ve Visual Studio'da özellikler oluşturun.](../working-with-project-properties.md)

### <a name="link-status"></a>Bağlantı Durumu

Bağlayıcının bağlantının yüzde kaçının tamamolduğunu gösteren bir ilerleme göstergesi gösterip göstermeyeceğini belirtir. Varsayılan olarak bu durum bilgilerini görüntülememektir. ([/LTCG](ltcg-link-time-code-generation.md):DURUM| LTCG:NOSTATUS)

### <a name="prevent-dll-binding"></a>DLL Bağlanmasını Önleme

[/ALLOWBIND](allowbind-prevent-dll-binding.md):NO, Bind.exe'ye görüntünün bağlanmasına izin verilmediğini gösteren bir DLL başlığında biraz ayarlar. Dijital olarak imzalanmışsa (bağlama imzayı geçersiz kılar) bir DLL'nin bağlanmasını istemeyebilirsiniz.

### <a name="treat-linker-warning-as-errors"></a>Bağlayıcı Uyarıyı Hata Olarak Ele

[/WX,](wx-treat-linker-warnings-as-errors.md) bağlayıcı bir uyarı oluşturursa hiçbir çıktı dosyasının oluşturulmasına neden olur.

### <a name="force-file-output"></a>Kuvvet Dosyası Çıktısı

[/FORCE](force-force-file-output.md) seçeneği, bir sembol başvurulsa ancak tanımlanmamış olsa veya tanımlanan çarpsa bile bağlayıcıya bir .exe dosyası veya DLL oluşturmasını söyler. Geçersiz .exe dosyası oluşturabilir.

**Seçenekler**

- **Etkin** - /FORCE bağımsız değişkeni olmadan hem birden çok hem de çözümlenmemiş anlamına gelir.
- **Yalnızca Tanımlı Simgeyi Çarpın** - LINK bir sembol için birden fazla tanım bulsa bile çıktı dosyası oluşturmak için /FORCE:MULTIPLE kullanın.
- **Tanımsız Sembol Yalnızca** - LINK tanımsız bir sembol bulunup bulunmadığını bir çıktı dosyası oluşturmak için /FORCE:UNRESOLVED kullanın. /FORCE:Giriş noktası simgesi çözülmezse ÇÖZÜMSÜZ dür.

### <a name="create-hot-patchable-image"></a>Sıcak Yamalanabilir Görüntü Oluşturma

Hotpatching için bir görüntü hazırlar.

**Seçenekler**

- **Etkin** - Hotpatching için bir görüntü hazırlar.
- **Yalnızca X86 Image** - Hotpatching için bir X86 görüntüsü hazırlar.
- **Yalnızca X64 Image** - Hotpatching için bir X64 görüntüsü hazırlar.
- **Sadece Itanium Image** - Hotpatching için bir Itanium görüntü hazırlar.

### <a name="specify-section-attributes"></a>Bölüm Özniteliklerini Belirt

[/SECTION](section-specify-section-attributes.md) seçeneği, bölümün .obj dosyası derlendiğinde ayarlanan öznitelikleri geçersiz kılarak bir bölümün özniteliklerini değiştirir.

## <a name="input-property-page"></a>Giriş Özelliği Sayfası

### <a name="additional-dependencies"></a>Ek Bağımlılıklar

Bağlantı komut satırına eklemek için ek öğeler belirtir, örneğin *kernel32.lib*.

### <a name="ignore-all-default-libraries"></a>Tüm Varsayılan Kitaplıkları Yoksay

[/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) seçeneği, bağlayıcıya dış başvuruları çözerken aradığı kitaplıklar listesinden bir veya daha fazla varsayılan kitaplık kaldırmasını söyler.

### <a name="ignore-specific-default-libraries"></a>Belirli Varsayılan Kitaplıkları Yoksay

Varsayılan kitaplıkların bir veya daha fazla adını yoksaymak için belirtir. Birden çok kitaplıkları yarı iki nokta lı olarak ayırın. (/NODEFAULTLIB:[isim, isim, ...])

### <a name="module-definition-file"></a>Modül Tanım Dosyası

[/DEF](def-specify-module-definition-file.md) seçeneği bir modül tanımlı dosyayı (.def) bağlayıcıya geçirir. LINK'e yalnızca bir .def dosyası belirtilebilir.

### <a name="add-module-to-assembly"></a>Derlemeye Modül Ekle

[/ASSEMBLYMODULE](assemblymodule-add-a-msil-module-to-the-assembly.md) seçeneği, bir derlemeye modül referansı eklemenize olanak tanır. Modüldeki tür bilgileri, modül referansını ekleyen montaj programında kullanılamaz. Ancak, modüldeki tür bilgileri derlemeye başvuran herhangi bir program için kullanılabilir olacaktır.

### <a name="embed-managed-resource-file"></a>Yönetilen Kaynak Dosyayı Gömme

[/ASSEMBLYRESOURCE](assemblyresource-embed-a-managed-resource.md) çıktı dosyasına bir kaynak dosyası gömer.

### <a name="force-symbol-references"></a>Kuvvet Sembolü Referansları

[/INCLUDE](include-force-symbol-references.md) seçeneği, bağlayıcıya sembol tablosuna belirli bir sembol eklemesini söyler.

### <a name="delay-loaded-dlls"></a>Gecikme Yüklü DL'ler

[/DELAYLOAD](delayload-delay-load-import.md) seçeneği, DL'lerin gecikmeli yüklenmesine neden olur. DLL adı, yükü geciktirmek için bir DLL belirtir.

### <a name="assembly-link-resource"></a>Derleme Bağlantı Kaynağı

[/ASSEMBLYLINKRESOURCE](assemblylinkresource-link-to-dotnet-framework-resource.md) seçeneği, çıktı dosyasındaki bir .NET Framework kaynağına bağlantı oluşturur; kaynak dosyası çıktı dosyasına yerleştirilmez.

## <a name="manifest-file-property-page"></a>Manifest Dosya Özelliği Sayfası

### <a name="generate-manifest"></a>Manifesto Oluştur

[/MANIFEST,](manifest-create-side-by-side-assembly-manifest.md) bağlayıcının yan yana bir bildirim dosyası oluşturması gerektiğini belirtir.

### <a name="manifest-file"></a>Manifesto Dosyası

[/MANIFESTFILE,](manifestfile-name-manifest-file.md) bildirim dosyasının varsayılan adını değiştirmenize olanak tanır. Bildirim dosyasının varsayılan adı .manifest eklenen dosya adıdır.

### <a name="additional-manifest-dependencies"></a>Ek Bildirim Bağımlılıkları

[/MANIFESTDEPENDENCY,](manifestdependency-specify-manifest-dependencies.md) bildirim dosyasının bağımlılık bölümüne yerleştirilecek öznitelikleri belirtmenizi sağlar.

### <a name="allow-isolation"></a>Yalıtıma İzin Ver

Bildirim araması için davranışı belirtir. ([/İzOLASYON](allowisolation-manifest-lookup.md):NO)

### <a name="enable-user-account-control-uac"></a>Kullanıcı Hesabı Denetimini Etkinleştir (UAC)

Kullanıcı Hesabı Denetimi'nin etkin olup olmadığını belirtir.  ([/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md), /MANIFESTUAC:NO)

### <a name="uac-execution-level"></a>UAC Yürütme Düzeyi

Kullanıcı Hesabı Denetimi ile çalışırken uygulama için istenen yürütme düzeyini belirtir.  (/MANIFESTUAC:level=[değer])

**Seçenekler**

- **asInvoker** - UAC Yürütme Düzeyi: invoker olarak.
- **en yüksek Kullanılabilir** - UAC Yürütme Düzeyi: en yüksek kullanılabilir.
- **administrator** gerektirir - UAC Yürütme Düzeyi: yönetici gerektirir.

### <a name="uac-bypass-ui-protection"></a>UAC Bypass UI Koruması

Masaüstündeki diğer pencereler için kullanıcı arabirimi koruma düzeylerini atlayıp atlamayacağı belirtir.  Bu özelliği yalnızca erişilebilirlik uygulamaları için 'Evet' olarak ayarlayın.  ([/MANIFESTUAC](manifestuac-embeds-uac-information-in-manifest.md):uiAccess=[true | false])

## <a name="debugging-property-page"></a>Hata Ayıklama Özellik Sayfası

### <a name="generate-debug-info"></a>Hata Ayıklama Bilgileri Oluştur

Bu seçenek,.exe dosyası veya DLL için hata ayıklama bilgilerinin oluşturulmasını sağlar.

**Seçenekler**

- **Hayır** - Hata ayıklama bilgisi üretmez.
- **Hata Ayıklama Bilgileri Oluşturma** - Microsoft Symbol Server'a dağıtım için ideal olan tam bir Program Veritabanı (PDB) oluşturun.
- **Daha hızlı bağlantılar için optimize edilmiş Hata Ayıklama Bilgileri oluşturma** - Edit-link hata ayıklama döngüsü için ideal bir program veritabanı (PDB) üretir.
- **Paylaşım ve yayımlama için en iyi duruma getirilmiş Hata Ayıklama Bilgileri oluşturma** - Edit-link hata ayıklama döngüsü için ideal bir program veritabanı (PDB) üretir.

### <a name="generate-program-database-file"></a>Program Veritabanı Dosyası Oluştur

Varsayılan olarak, [/DEBUG](debug-generate-debug-info.md) belirtildiğinde, bağlayıcı hata ayıklama bilgilerini tutan bir program veritabanı (PDB) oluşturur. PDB için varsayılan dosya adı programın temel adı ve uzantısı .pdb vardır.

### <a name="strip-private-symbols"></a>Şerit Özel Semboller

[/PDBSTRIPPED](pdbstripped-strip-private-symbols.md) seçeneği, program görselinizi bir PDB dosyası (/DEBUG, /Z7, /Zd veya /Zi) oluşturan derleyici veya bağlayıcı seçeneklerinden herhangi biriyle oluşturduğunuzda ikinci bir program veritabanı (PDB) dosyası oluşturur.

### <a name="generate-map-file"></a>Harita Dosyası Oluştur

[/MAP](map-generate-mapfile.md) seçeneği bağlayıcıya bir mapfile oluşturmasını söyler.

### <a name="map-file-name"></a>Harita Dosya Adı

Harita dosyası için kullanıcı tarafından belirtilen bir ad. Varsayılan adın yerini alır.

### <a name="map-exports"></a>Harita İhracat

[/MAPINFO](mapinfo-include-information-in-mapfile.md) seçeneği, /MAP seçeneğini belirtirseniz oluşturulan bir mapfile'ye belirtilen bilgileri eklemesini bağlayıcıya bildirir. İhRACAT bağlayıcıya dışa aktarılan işlevleri eklemesini söyler.

### <a name="debuggable-assembly"></a>Hata Ayıklanabilir Montaj

[/ASSEMBLYDEBUG](assemblydebug-add-debuggableattribute.md) hata ayıklama bilgi izleme ile Hata Ayıklama Özniteliği yayar ve JIT optimizasyonları devre dışı kılabilir.

## <a name="system-property-page"></a>Sistem Özelliği Sayfası

### <a name="subsystem"></a>Alt

[/SUBSYSTEM](subsystem-specify-subsystem.md) seçeneği işletim sistemine .exe dosyasının nasıl çalıştırılabildiğini söyler. Alt sistem seçimi, bağlayıcının seçeceği giriş noktası simgesini (veya giriş noktası işlevini) etkiler.

**Seçenekler**

- **Ayarlı Değil** - Alt sistem kümesi yok.
- **Konsol** - Win32 karakter modu uygulaması. Konsol uygulamalarına işletim sistemi tarafından bir konsol verilir. Main veya wmain tanımlanırsa, CONSOLE varsayılandır.
- **Windows** - Uygulama, kullanıcıyla etkileşim için kendi pencerelerini oluşturduğundan, büyük olasılıkla bir konsol gerektirmez. WinMain veya wWinMain tanımlanırsa, WINDOWS varsayılandır.
- **Yerel** - Windows NT için aygıt sürücüleri. /DRIVER:WDM belirtilirse, varsayılan yereldir.
- **EFI Uygulaması** - EFI Uygulaması.
- **EFI Boot Service Driver** - EFI Boot Servis Sürücüsü.
- **EFI ROM** - EFI ROM.
- **EFI Çalışma Zamanı** - EFI Çalışma Zamanı.
- **POSIX** - Windows NT'deki POSIX alt sistemiyle çalışan uygulama.

### <a name="minimum-required-version"></a>Minimum Gerekli Sürüm

Alt sistemin en az gerekli sürümünü belirtin. Bağımsız değişkenler 0 ile 65.535 aralığındaki ondalık sayılardır.

### <a name="heap-reserve-size"></a>Yığın Rezerv Boyutu

Sanal bellekte toplam yığın ayırma boyutunu belirtir. Varsayılan değer 1 MB'dır.    ([/HEAP](heap-set-heap-size.md):rezerv)

### <a name="heap-commit-size"></a>Yığın Commit Boyutu

Fiziksel bellekte toplam yığın ayırma boyutunu belirtir. Varsayılan değer 4 KB'dir.    ([/HEAP](heap-set-heap-size.md):rezerv,taahhüt)

### <a name="stack-reserve-size"></a>Yığın Rezerv Boyutu

Sanal bellekteki toplam yığın ayırma boyutunu belirtir. Varsayılan değer 1 MB'dır.     ([/STACK](stack-stack-allocations.md):rezerv)

### <a name="stack-commit-size"></a>Yığın Commit Boyutu

Fiziksel bellekteki toplam yığın ayırma boyutunu belirtir. Varsayılan değer 4 KB'dir.     ([/STACK](stack-stack-allocations.md):rezerv,taahhüt)

### <a name="enable-large-addresses"></a>Büyük Adresleri Etkinleştir

[/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md) seçeneği, bağlantı cının 2 gigabayttan daha büyük adresleri işleyebilir olduğunu söyler. Varsayılan olarak, /LARGEADDRESSAWARE:/LARGEADDRESSAWARE bağlantı satırında aksi belirtilmemişse NO etkindir.

### <a name="terminal-server"></a>Terminal Sunucusu

[/TSAWARE](tsaware-create-terminal-server-aware-application.md) seçeneği, program görüntüsünün isteğe bağlı üstbilgisinde IMAGE_OPTIONAL_HEADER DllCharacteristics alanına bir bayrak ayarlar. Bu bayrak ayarlandığında, Terminal Server uygulamada belirli değişiklikler yapmaz.

### <a name="swap-run-from-cd"></a>CD'den Çalıştır'ı değiştir

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) seçeneği, işletim sistemine önce bağlayıcı çıktısını bir takas dosyasına kopyalamasını ve ardından görüntüyü oradan çalıştırmasını söyler. Bu seçenek bir Windows NT 4.0 (ve sonrası) özelliğidir. **CD** belirtildiğinde, işletim sistemi çıkarılabilir bir diskteki görüntüyü bir sayfa dosyasına kopyalar ve sonra yükler.

### <a name="swap-run-from-network"></a>Ağdan Çalıştır'ı Değiştir

[/SWAPRUN](swaprun-load-linker-output-to-swap-file.md) seçeneği, işletim sistemine önce bağlayıcı çıktısını bir takas dosyasına kopyalamasını ve ardından görüntüyü oradan çalıştırmasını söyler. Bu seçenek bir Windows NT 4.0 (ve sonrası) özelliğidir. **NET** belirtilirse, işletim sistemi önce ikili görüntüyü ağdan bir takas dosyasına kopyalar ve oradan yükler. Bu seçenek, uygulamaları ağ üzerinden çalıştırmak için yararlıdır.

### <a name="driver"></a>Sürücü

Windows NT çekirdek modu sürücüsü oluşturmak için [/DRIVER](driver-windows-nt-kernel-mode-driver.md) bağlayıcı seçeneğini kullanın.

**Seçenekler**

- **Ayarlı Değil** - Varsayılan sürücü ayarı.
- **Sürücü** - Sürücü
- **Yalnızca UP** - /DRIVER:UPONLY, bağlayıcının çıkış başlığındaki özelliklere IMAGE_FILE_UP_SYSTEM_ONLY bitini eklemesine ve tek işlemcili (UP) bir sürücü olduğunu belirtilmesine neden olur. İşletim sistemi, bir UP sürücüsünü çok işlemcili (MP) sisteme yüklemeyi reddeder.
- **WDM** - /DRIVER:WDM, bağlayıcının isteğe bağlı üstbilginin DllCharacteristics alanında IMAGE_DLLCHARACTERISTICS_WDM_DRIVER bitini ayarlamasına neden olur.

## <a name="optimization-property-page"></a>Optimizasyon Özellik Sayfası

### <a name="references"></a>Başvurular

[/OPT](opt-optimizations.md):REF, /OPT:NOREF hiç başvurulamayan işlevleri ve/veya verileri tutarken hiç başvurulamayan işlevleri ve/veya verileri ortadan kaldırır.

### <a name="enable-comdat-folding"></a>COMDAT Katlamasını Etkinleştir

Aynı COMDAT\[katlama gerçekleştirmek için [/OPT](opt-optimizations.md):ICF =yinelemeler' kullanın.

### <a name="function-order"></a>İşlev Sırası

[/ORDER](order-put-functions-in-order.md)seçeneği, belirli COMDAT'ları görüntüye önceden belirlenmiş bir sırada yerleştirerek programınızı optimize etmesi için LINK'e söyler. LINK, görüntüdeki her bölümdeki işlevleri belirtilen sırada yerleştirir.

### <a name="profile-guided-database"></a>Profil Rehberli Veritabanı

Profil kılavuzlu optimizasyonlar için .pgd dosyalarını belirtin. ([/PGD](pgd-specify-database-for-profile-guided-optimizations.md))

### <a name="link-time-code-generation"></a>Bağlantı Zaman Kodu Oluşturma

Bağlantı zamanı kodu oluşturmayı belirtir. ([/LTCG](ltcg-link-time-code-generation.md))

**Seçenekler**

- **Varsayılan** - Varsayılan LTCG ayarı.
- **Hızlı Bağlantı Zaman Kodu Oluşturma kullanın** - / [FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)ile Bağlantı Zaman Kodu Oluşturma kullanın.
- **Bağlantı Zaman Kodu Oluşturma kullanın** - Bağlantı Zaman Kodu [Oluşturma](ltcg-link-time-code-generation.md)kullanın.
- **Profil Güdümlü Optimizasyon - Enstrüman** - :PGINSTRUMENT ile profil güdümlü [optimizasyon](../profile-guided-optimizations.md) kullanın.
- **Profil Güdümlü Optimizasyon - Optimizasyon** - Bağlayıcının en iyi duruma getirilmiş bir görüntü oluşturmak için enstrümantize ikiliyi çalıştırdıktan sonra oluşturulan profil verilerini kullanması gerektiğini belirtir.
- **Profil Güdümlü Optimizasyon - Güncelleme -** :PGINSTRUMENT aşamasında belirtilenlerden eklenecek veya değiştirilecek giriş dosyalarının listesini verir ve izler.

## <a name="embedded-idl-property-page"></a>Gömülü IDL Özellik Sayfası

### <a name="midl-commands"></a>MIDL Komutları

MIDL komut satırı Seçenekleri belirtin. ([/MIDL](midl-specify-midl-command-line-options.md):@responsefile)

### <a name="ignore-embedded-idl"></a>Gömülü IDL'yi Yoksay

[/IGNOREIDL](ignoreidl-don-t-process-attributes-into-midl.md) seçeneği, kaynak kodundaki herhangi bir IDL özniteliklerinin .idl dosyasında işlenmemesi gerektiğini belirtir.

### <a name="merged-idl-base-file-name"></a>Birleştirilmiş IDL Temel Dosya Adı

[/IDLOUT](idlout-name-midl-output-files.md) seçeneği .idl dosyasının adını ve uzantısını belirtir.

### <a name="type-library"></a>Tür Kitaplığı

[/TLBOUT](tlbout-name-dot-tlb-file.md) seçeneği .tlb dosyasının adını ve uzantısını belirtir.

### <a name="typelib-resource-id"></a>TypeLib Kaynak Kimliği

Bağlayıcı tarafından oluşturulan tür kitaplığın kaynak kimliğini belirtmenizi sağlar. ([/TLBID](tlbid-specify-resource-id-for-typelib.md):id)

## <a name="windows-metadata-property-page"></a>Windows Metadata Özellik Sayfası

### <a name="generate-windows-metadata"></a>Windows Meta verileri oluşturma

Windows Meta verilerinin oluşumuna olanak tanır veya devre dışı kılabilir.

**Seçenekler**

- **Evet** - Windows Meta veri dosyalarının oluşumuna olanak sağlar.
- **Hayır** - Windows Meta veri dosyalarının oluşumunu devre dışı kınayın.

### <a name="windows-metadata-file"></a>Windows Meta veri dosyası

[/WINMDFILE](winmdfile-specify-winmd-file.md) seçenek anahtarı.

### <a name="windows-metadata-key-file"></a>Windows Metadata Anahtar Dosyası

Windows Meta verilerini imzalamak için anahtar veya anahtar çiftini belirtin. ([/WINMDKEYFILE](winmdkeyfile-specify-winmd-key-file.md):dosya adı)

### <a name="windows-metadata-key-container"></a>Windows Metaveri Anahtar Kapsayıcısı

Windows Meta verilerini imzalamak için bir anahtar kapsayıcı belirtin. ([/WINMDKEYCONTAINER](winmdkeycontainer-specify-key-container.md):isim)

### <a name="windows-metadata-delay-sign"></a>Windows Meta veri gecikme işareti

Kısmen bir Windows Meta verisi imzalayın. Ortak anahtarı yalnızca Windows Meta verilerine yerleştirmek istiyorsanız [/WINMDDELAYSIGN'ı](winmddelaysign-partially-sign-a-winmd.md) kullanın. Varsayılan /WINMDDELAYSIGN:NO.

## <a name="advanced-property-page"></a>Gelişmiş Özellik Sayfası

### <a name="entry-point"></a>Girdi Noktası

[/ENTRY](entry-entry-point-symbol.md) seçeneği, bir .exe dosyasının veya DLL'nin başlangıç adresi olarak bir giriş noktası işlevini belirtir.

### <a name="no-entry-point"></a>Giriş Noktası Yok

[/NOENTRY](noentry-no-entry-point.md)seçeneği yalnızca kaynak DLL oluşturmak için gereklidir. LINK'in bir başvuruyu DLL'ye bağlamasını önlemek için `_main` bu seçeneği kullanın.

### <a name="set-checksum"></a>Checksum'u ayarla

[/RELEASE](release-set-the-checksum.md) seçeneği, Checksum'u bir .exe dosyasının üstbilgisinde ayarlar.

### <a name="base-address"></a>Taban Adresi

Programın temel adresini ayarlar. ([/BASE](base-base-address.md):{adres\[,boyut] | @filename,anahtar})

### <a name="randomized-base-address"></a>Randomize Taban Adresi

Randomize Üs Adresi. ([/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)\[:NO])

### <a name="fixed-base-address"></a>Sabit Taban Adresi

Yalnızca tercih ettiği temel adrese yüklenebilen bir program oluşturur. ([/SABIT](fixed-fixed-base-address.md)\[:NO])

### <a name="data-execution-prevention-dep"></a>Veri Yürütme Önleme (DEP)

Yürütülebilir bir özelliği, Windows Veri Yürütme Önleme özelliğiyle uyumlu olacak şekilde sınanmış olarak işaretler. ([/NXCOMPAT](nxcompat-compatible-with-data-execution-prevention.md)\[:NO])

### <a name="turn-off-assembly-generation"></a>Montaj Oluşturmayı Kapat

[/NOASSEMBLY](noassembly-create-a-msil-module.md) seçeneği, bağlayıcıya .NET Framework derlemesi olmadan geçerli çıktı dosyası için bir görüntü oluşturmasını söyler.

### <a name="unload-delay-loaded-dll"></a>DLL yüklü boşaltma gecikmesi

**UNLOAD** niteleyicisi, DLL'nin açık bir şekilde boşaltılmasını desteklemek için gecikme yükü yardımcı işlevini söyler. ([/DELAY](delay-delay-load-import-settings.md):BOŞALT)

### <a name="nobind-delay-loaded-dll"></a>Nobind gecikme dll yüklü

**NOBIND** niteleyici, bağlayıcıya son görüntüye bağlanabilir bir IAT eklememesi gerektiğini söyler. Varsayılan, gecikme yüklü DL'ler için bağlanabilir IAT'yi oluşturmaktır. ([/DELAY](delay-delay-load-import-settings.md):NOBIND)

### <a name="import-library"></a>İthalat Kütüphanesi

Varsayılan içe aktarma kitaplığı adını geçersiz kılar. ([/IMPLIB](implib-name-import-library.md):dosya adı)

### <a name="merge-sections"></a>Bölümleri Birleştirme

[/MERGE](merge-combine-sections.md) seçeneği, birinci bölümü (from) ikinci bölümle (to) birleştirerek, elde edilen bölümü Örneğin, /merge:.rdata=.text.

### <a name="target-machine"></a>Hedef Makine

[/MACHINE](machine-specify-target-platform.md) seçeneği, programın hedef platformını belirtir.

**Seçenekler**

- **Ayarlanmadı**
- **MakineARM**
- **MakineARM64**
- **MachineEBC**
- **MakineIA64**
- **MakineMIPS**
- **MakineMIPS16**
- **MakineMIPSFPU**
- **MakineMIPSFPU16**
- **MakineSH4**
- **MakineBAŞPARMAK**
- **MakineX64**
- **MakineX86**

### <a name="profile"></a>Profil

Performans Araçları profilleyicisiyle kullanılabilecek bir çıktı dosyası üretir. Generate DebugInformation (/[HATA Hata)](debug-generate-debug-info.md)ayarlanmalıdır. ([/PROFIL](profile-performance-tools-profiler.md))

### <a name="clr-thread-attribute"></a>CLR Konu Özniteliği

CLR programınızın giriş noktası için iş parçacığı özniteliğini açıkça belirtin.

**Seçenekler**

- **MTA iş parçacığı özniteliği** - MTAThreadÖzöz özniteliğini programınızın giriş noktasına uygular.
- **STA iş parçacığı özniteliği** - STAThreadÖz özniteliğini programınızın giriş noktasına uygular.
- **Varsayılan iş parçacığı özniteliği** - [/CLRTHREADATTRIBUTE](clrthreadattribute-set-clr-thread-attribute.md)belirtmeme gibi. Ortak Dil Çalışma Süresi'nin (CLR) varsayılan iş parçacığı özniteliğini ayarlamasına izin verir.

### <a name="clr-image-type"></a>CLR Görüntü Türü

CLR görüntüsünün türünü (IJW, saf veya güvenli) ayarlar.

**Seçenekler**

- **Force IJW görüntü**
- **Force Pure IL Görüntü**
- **Force Safe IL Görüntü**
- **Varsayılan görüntü türü**

### <a name="key-file"></a>Anahtar Dosyası

Derlemeyi imzalamak için anahtar veya anahtar çiftini belirtin. ([/KEYFILE](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md):dosya adı)

### <a name="key-container"></a>Anahtar Konteyner

Derlemeyi imzalamak için anahtar kapsayıcı belirtin. ([/KEYCONTAINER](keycontainer-specify-a-key-container-to-sign-an-assembly.md):isim)

### <a name="delay-sign"></a>Gecikme İşareti

Kısmen bir derleme imzalayın. Ortak anahtarı yalnızca derlemeye yerleştirmek istiyorsanız [/DELAYSIGN'ı](delaysign-partially-sign-an-assembly.md) kullanın. Varsayılan /DELAYSIGN:NO.

### <a name="clr-unmanaged-code-check"></a>CLR Yönetilmeyen Kod Denetimi

[/CLRUNMANAGEDCODECHECK,](clrunmanagedcodecheck-add-suppressunmanagedcodesecurityattribute.md) bağlayıcının yönetilen koddan yerel DL'lere bağlı olarak oluşturulan PInvoke çağrılarına SuppressUnmanagedCodeSecurityAttribute uygulayıp uygulamayacağı belirtir.

### <a name="error-reporting"></a>Hata Raporlama

İç derleyici hatası (ICE) bilgilerini doğrudan Visual C++ ekibine sağlamanızı sağlar.

**Seçenekler**

- **PromptImmediately** - Hemen istem.
- **Sonraki Giriş İçin Sıra** - Sonraki giriş için sıra.
- **Hata Raporu Gönder** - Hata raporu gönder.
- **Hata Raporu Yok** - Hata raporu yok.

### <a name="sectionalignment"></a>Bölüm Hizalama

[/ALIGN](align-section-alignment.md) seçeneği, programın doğrusal adres alanı içindeki her bölümün hizalanmasını belirtir. Sayı bağımsız değişkeni baytlardadır ve iki güç olmalıdır.

### <a name="preserve-last-error-code-for-pinvoke-calls"></a>PInvoke Çağrıları için Son Hata Kodunu Koru

[/CLRSUPPORTLASTERROR](clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls.md), varsayılan olarak, /clr ile derlenen koddan, DLLS'de yerel işlevleri aramanızı sağlayan P/Invoke mekanizması aracılığıyla çağrılan işlevlerin son hata kodunu korur.

**Seçenekler**

- **Etkin** - CLRSupportLastError'ı etkinleştirin.
- **Devre Dışı -** CLRSupportLastError'ı devre dışı.
- **Yalnızca Sistem Dlls** - Yalnızca sistem dlls için CLRSupportLastError etkinleştirin.

### <a name="image-has-safe-exception-handlers"></a>Görüntü Güvenli Özel Durum İşleyicileri var

[/SAFESEH](safeseh-image-has-safe-exception-handlers.md) belirtildiğinde, bağlayıcı yalnızca görüntünün güvenli özel durum işleyicilerinin tablosunu da oluşturabiliyorsa bir görüntü oluşturur. Bu tablo, görüntü için geçerli olan özel durum işleyicilerinin işletim sistemi için geçerli olduğunu belirtir.
