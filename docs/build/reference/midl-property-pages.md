---
title: MIDL Derleyici Özellik Sayfaları
ms.date: 07/24/2019
ms.topic: article
ms.assetid: 57498a01-fccc-4a0e-a036-6ff702f83126
f1_keywords:
- VC.Project.VCMidlTool.PreprocessorDefinitions
- VC.Project.VCMidlTool.AdditionalIncludeDirectories
- VC.Project.VCMidlTool.AdditionalMetadataDirectories
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.IgnoreStandardIncludePath
- VC.Project.VCMidlTool.MkTypLibCompatible
- VC.Project.VCMidlTool.WarningLevel
- VC.Project.VCMidlTool.WarnAsError
- VC.Project.VCMidlTool.SuppressStartupBanner
- VC.Project.VCMidlTool.DefaultCharType
- VC.Project.VCMidlTool.TargetEnvironment
- VC.Project.VCMidlTool.GenerateStublessProxies
- VC.Project.VCMidlTool.SuppressCompilerWarnings
- VC.Project.VCMidlTool.ApplicationConfigurationMode
- VC.Project.VCMidlTool.LocaleID
- VC.Project.VCMidlTool.MultiProcMIDL
- VC.Project.VCMidlTool.OutputDirectory
- VC.Project.VCMidlTool.WinmdFileName
- VC.Project.VCMidlTool.HeaderFileName
- VC.Project.VCMidlTool.DLLDataFileName
- VC.Project.VCMidlTool.InterfaceIdentifierFileName
- VC.Project.VCMidlTool.ProxyFileName
- VC.Project.VCMidlTool.GenerateTypeLibrary
- VC.Project.VCMidlTool.TypeLibraryName
- VC.Project.VCMidlTool.GenerateClientFiles
- VC.Project.VCMidlTool.GenerateServerFiles
- VC.Project.VCMidlTool.ClientStubFile
- VC.Project.VCMidlTool.ServerStubFile
- VC.Project.VCMidlTool.TypeLibFormat
- VC.Project.VCMidlTool.CPreprocessOptions
- VC.Project.VCMidlTool.UndefinePreprocessorDefinitions
- VC.Project.VCMidlTool.EnableErrorChecks
- VC.Project.VCMidlTool.ErrorCheckAllocations
- VC.Project.VCMidlTool.ErrorCheckBounds
- VC.Project.VCMidlTool.ErrorCheckEnumRange
- VC.Project.VCMidlTool.ErrorCheckRefPointers
- VC.Project.VCMidlTool.ErrorCheckStubData
- VC.Project.VCMidlTool.PreendWithABINamepsace
- VC.Project.VCMidlTool.ValidateParameters
- VC.Project.VCMidlTool.StructMemberAlignment
- VC.Project.VCMidlTool.RedirectOutputAndErrors
- VC.Project.VCMidlTool.MinimumTargetSystem
- vc.project.AdditionalOptionsPage
ms.openlocfilehash: d6833230baca892836c187799df7f0658aa16772
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336249"
---
# <a name="midl-property-pages"></a>MIDL Özellik Sayfaları

MIDL özellik sayfaları bir öğe özelliği olarak kullanılabilir. COM kullanan bir C++ projesindeki IDL dosyası. [MIDL Derleyicisini](/windows/win32/midl/using-the-midl-compiler-2)yapılandırmak için bunları kullanın. C++ projeleri için MIDL seçeneklerine programlı olarak <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> nasıl erişilisüreceğiniz hakkında bilgi için nesneye bakın. Ayrıca bakınız [Genel MIDL Komut satırı Sözdizimi.](/windows/win32/midl/general-midl-command-line-syntax)

## <a name="general-property-page"></a>Genel Özellik Sayfası

### <a name="preprocessor-definitions"></a>Önişlemci Tanımları

MIDL makroları ([/D](/windows/win32/midl/-d))\[makroları\]da dahil olmak üzere bir veya daha fazla tanım belirtir.

### <a name="additional-include-directories"></a>Ek Dahil Dizinler

Ekle yoluna eklemek için bir veya daha fazla dizin\]belirtir ([/I](/windows/win32/midl/-i)\[yolu).

### <a name="additional-metadata-directories"></a>Ek Meta veri dizinleri

Windows.Foundation.WinMD dosyasını içeren dizini belirtin\]([/metadata_dir](/windows/win32/midl/-metadata-dir) \[yolu).

### <a name="enable-windows-runtime"></a>Windows Çalışma Süresini Etkinleştir

Windows meta veri dosyası ([/winrt)](/windows/win32/midl/-winrt)oluşturmak için Windows Runtime semantiği etkinleştirin.

### <a name="ignore-standard-include-path"></a>Standardı Yoksay yolu Ekle

Geçerli ve INCLUDE dizinlerini yoksay ([/no_def_idir](/windows/win32/midl/-no-def-idir)).

### <a name="mktyplib-compatible"></a>MkTypLib Uyumlu

Kuvvetler uyumluluk mktyplib.exe sürüm 2.03 ([/mktyplib203](/windows/win32/midl/-mktyplib203)) ile.

### <a name="warning-level"></a>Uyarı Düzeyi

MIDL kod hatalarının[(/W)](/windows/win32/midl/-w)katılığını seçer.

**Seçenekler**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>Uyarıları Hata Olarak Değerlendirin

MIDL'in tüm uyarıları hata olarak ele almalarını sağlar ([/WX).](/windows/win32/midl/-wx)

### <a name="suppress-startup-banner"></a>Başlangıç Banner'ı bastır

Başlangıç afişi ve bilgi iletisinin[(/nologo)](/windows/win32/midl/-nologo)görüntülenmesini bastırın.

### <a name="c-compiler-char-type"></a>C Derleyici Char Türü

Oluşturulan kodu derlemek için kullanılacak C derleyicisinin varsayılan karakter türünü belirtir. ([/char](/windows/win32/midl/-char) imzalı|imzasız|ascii7).

**Seçenekler**

- **İmzalı** - İmzalı
- **İmzasız** - İmzasız
- **Ascii** - Ascii

### <a name="target-environment"></a>Hedef Ortam

Hangi ortamın hedeflenerene kadar ([/env](/windows/win32/midl/-env) arm32|win32|ia64|x64) belirtir.

**Seçenekler**

- **Set Değil** - Win32
- **Microsoft Windows 32-bit** - Win32
- **Itanium Microsoft Windows 64-bit** - IA64
- **Microsoft Windows ARM** - ARM
- **Microsoft Windows ARM64** - ARM64
- **Microsoft Windows 64-bit üzerinde x64** - X64

### <a name="generate-stubless-proxies"></a>Saplamaz Proxies oluşturun

Nesne arabirimleri ([/Oicf](/windows/win32/midl/-oi), [/Oif](/windows/win32/midl/-oi) ) için uzantılı ve sapsız yakınlıklarla tam olarak yorumlanmış saplamalar oluşturun.

### <a name="suppress-compiler-warnings"></a>Derleyici Uyarılarını Engelleme

Derleyici uyarı iletilerini bastırma ([/no_warn](/windows/win32/midl/-no-warn)).

### <a name="application-configuration-mode"></a>Uygulama Yapılandırma Modu

IDL dosyasında seçili ACF özniteliklerine izin ver ([/app_config).](/windows/win32/midl/-app-config)

### <a name="locale-id"></a>Yerel Ayar Kimliği

Giriş dosyaları, dosya adları ve dizin yolları[(/lcid](/windows/win32/midl/-lcid) DECIMAL) için LCID'i belirtir.

### <a name="multi-processor-compilation"></a>Çok İşlemli Derleme

Aynı anda birden çok örnek çalıştırın.

## <a name="output-property-page"></a>Çıktı Özellik Sayfası

### <a name="output-directory"></a>Çıktı Dizini

Çıktı dizini[(/out](/windows/win32/midl/-out) [directory]) belirtir.

### <a name="metadata-file"></a>Meta veri dosyası

Oluşturulan meta veri dosyasının adını belirtir ([/winmd](/windows/win32/midl/-winmd) dosya adı).

### <a name="header-file"></a>Üstbilgi Dosyası

Oluşturulan üstbilgi dosyasının adını belirtir ([/h](/windows/win32/midl/-h) dosya adı).

### <a name="dlldata-file"></a>DllData Dosyası

DLLDATA dosyasının adını belirtir ([/dlldata](/windows/win32/midl/-dlldata) dosya adı).

### <a name="iid-file"></a>IID Dosyası

Arabirim Tanımlayıcı dosyasının adını belirtir ([/iid](/windows/win32/midl/-iid) dosya adı).

### <a name="proxy-file"></a>Proxy Dosyası

Proxy dosyasının adını belirtir ([/proxy](/windows/win32/midl/-proxy) dosya adı).

### <a name="generate-type-library"></a>Tür Kitaplığı Oluştur

Bir tür kitaplığı ([/notlb] hayır için oluşturmayın belirtin).

### <a name="type-library"></a>Tür Kitaplığı

Tür kitaplığı dosyasının adını belirtir ([/tlb](/windows/win32/midl/-tlb) dosya adı).

### <a name="generate-client-stub-files"></a>İstemci Saplama Dosyaları Oluşturma

Yalnızca istemci saplama dosyalarını oluşturun ([/istemci](/windows/win32/midl/-client) [stub|none]).

**Seçenekler**

- **Saplama** - Saplama
- **Yok** - Yok

### <a name="generate-server-stub-files"></a>Sunucu Saplama Dosyaları Oluşturma

Yalnızca sunucu saplama dosyalarını oluşturun ([/server](/windows/win32/midl/-server) [stub|none]).

**Seçenekler**

- **Saplama** - Saplama
- **Yok** - Yok

### <a name="client-stub-file"></a>İstemci Saplama Dosyası

İstemci saplama dosyasını belirtin ([/cstub](/windows/win32/midl/-cstub) [dosya]).

### <a name="server-stub-file"></a>Sunucu Saplama Dosyası

Sunucu saplama dosyasını belirtin ([/sstub](/windows/win32/midl/-sstub) [dosya]).

### <a name="type-library-format"></a>Tür Kitaplığı Biçimi

Tür kitaplığı dosya biçimini belirtir ([/oldtlb|/newtlb]).

**Seçenekler**

- **NewFormat** - Yeni Biçim
- **Eski Biçim** - Eski Biçim

## <a name="advanced-property-page"></a>Gelişmiş Özellik Sayfası

### <a name="c-preprocess-options"></a>C Ön İşlem Seçenekleri

C derleyici önişlemcisine geçmek için anahtarları belirtir[(/cpp_opt](/windows/win32/midl/-cpp-opt) anahtarları).

### <a name="undefine-preprocessor-definitions"></a>Tanımsız Önİşlemci Tanımları

MIDL makroları[(/U](/windows/win32/midl/-U) [makrolar]) dahil olmak üzere bir veya daha fazla tanımlanmamış belirtir.

### <a name="enable-error-checking"></a>Hata Denetlemeyi Etkinleştir

Hata denetleme seçeneğini seçin ([/hata tümü|yok]).

**Seçenekler**

- **EnableCustom** - Tümü
- **Tümü** - Tümü
- **Yok** - Yok

### <a name="check-allocations"></a>Tahsisatları Kontrol Et

Bellek hataları[(/hata](/windows/win32/midl/-error) ayırma) dışında denetleyin.

### <a name="check-bounds"></a>Sınırları Kontrol Et

Boyutu ve iletim uzunluğu belirtimini kontrol edin ([/hata](/windows/win32/midl/-error) bounds_check).

### <a name="check-enum-range"></a>Enum Aralığını Kontrol Et

İzin verilebilen aralıkta[(/hata](/windows/win32/midl/-error) enum) olmak üzere enum değerlerini denetleyin.

### <a name="check-reference-pointers"></a>Referans İşaretçileri Denetle

Ref işaretçilerin null olmayan[(/hata](/windows/win32/midl/-error) ref) olup olmayacağını kontrol edin.

### <a name="check-stub-data"></a>Saplama Verilerini Kontrol Et

Sunucu tarafı saplama veri geçerliliği[(/hata](/windows/win32/midl/-error) stub_data) için ek denetim yayan.

### <a name="prepend-with-abi-namespace"></a>'ABI' ad alanı ile prepend

'ABI' ad alanını her türe hazırlayın.  ([/ns_prefix](/windows/win32/midl/-ns-prefix)).

### <a name="validate-parameters"></a>Parametreleri Doğrula

Parametreleri doğrulamak için ek bilgi oluşturun ([/robust](/windows/win32/midl/-robust) | [/no_robust](/windows/win32/midl/-no-robust)).

### <a name="struct-member-alignment"></a>Struct Üye Hizalaması

Hedef sistemdeki (/ZpN) yapıların paketleme düzeyini belirtir.

**Seçenekler**

- **Ayarlı Değil** - Ayarlı Değil
- **1 Bayt** - Zp1
- **2 Bayt** - Zp2
- **4 Bayt** - Zp4
- **8 Bayt** - Zp8

### <a name="redirect-output"></a>Çıkışı Yeniden Yönlendirme

Çıktıyı ekrandan dosyaya[(/o](/windows/win32/midl/-o) dosyası) yönlendirir.

### <a name="minimum-target-system"></a>Minimum Hedef Sistemi

Minimum hedef sistemi[(/target](/windows/win32/midl/-target) STRING) ayarlayın.
