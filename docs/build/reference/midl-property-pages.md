---
description: 'Daha fazla bilgi edinin: MıDL Özellik sayfaları'
title: MıDL derleyici Özellik sayfaları
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
ms.openlocfilehash: 12cc0791bfadf7611d62ab16fc788081f4c7b7e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137832"
---
# <a name="midl-property-pages"></a>MIDL Özellik Sayfaları

MıDL Özellik sayfaları, öğesinde bir öğe özelliği olarak kullanılabilir. COM kullanan bir C++ projesinde IDL dosyası. [MIDL derleyicisini](/windows/win32/midl/using-the-midl-compiler-2)yapılandırmak için bunları kullanın. C++ projeleri için MıDL seçeneklerine programlamayla erişme hakkında daha fazla bilgi için bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCMidlTool> . nesnesi. Ayrıca bkz. [genel MIDL komut satırı sözdizimi](/windows/win32/midl/general-midl-command-line-syntax).

## <a name="general-property-page"></a>Genel özellik sayfası

### <a name="preprocessor-definitions"></a>Önişlemci tanımları

MıDL makroları ([/d](/windows/win32/midl/-d)) makroları dahil bir veya daha fazla tanımlar \[ belirtir \] ).

### <a name="additional-include-directories"></a>Ek Içerme dizinleri

Ekleme yoluna ([/i](/windows/win32/midl/-i)yolu) eklenecek bir veya daha fazla dizini belirtir \[ \] .

### <a name="additional-metadata-directories"></a>Ek meta veri dizinleri

Windows. Foundation. WinMD dosyasını içeren dizini belirtin ([/metadata_dir](/windows/win32/midl/-metadata-dir) \[ yolu \] ).

### <a name="enable-windows-runtime"></a>Windows Çalışma Zamanı etkinleştir

Windows meta veri dosyası ([/wınrt](/windows/win32/midl/-winrt)) oluşturmak için Windows çalışma zamanı semantiğini etkinleştirin.

### <a name="ignore-standard-include-path"></a>Standart ekleme yolunu yoksay

Geçerli ve ekleme dizinlerini yoksayın ([/no_def_idir](/windows/win32/midl/-no-def-idir)).

### <a name="mktyplib-compatible"></a>MkTypLib uyumlu

mktyplib.exe sürüm 2,03 ile uyumluluğu zorlar ([/mktyplib203](/windows/win32/midl/-mktyplib203)).

### <a name="warning-level"></a>Uyarı düzeyi

MıDL kod hatalarının ([/w](/windows/win32/midl/-w)) stricaklığını seçer.

**Seçenekler**

- **1**
- **1**
- **2**
- **3**
- **4**

### <a name="treat-warnings-as-errors"></a>Uyarıları hata olarak değerlendir

MıDL 'nin tüm uyarıları hata ([/WX](/windows/win32/midl/-wx)) olarak kabul etmesini sağlar.

### <a name="suppress-startup-banner"></a>Başlangıç başlığını gösterme

Başlangıç başlığının ve bilgi iletisinin ([/nologo](/windows/win32/midl/-nologo)) görüntülenmesini gizleyin.

### <a name="c-compiler-char-type"></a>C derleyicisi char türü

Oluşturulan kodu derlemek için kullanılacak olan C derleyicisinin varsayılan karakter türünü belirtir. ([/char](/windows/win32/midl/-char) imzalı | işaretsiz | ascii7).

**Seçenekler**

- **İmzalanmış** imzalı
- **İşaretsiz** -işaretsiz
- **ASCII** -ASCII

### <a name="target-environment"></a>Hedef Ortam

Hangi ortamın hedeflenecek olduğunu belirtir ([/env](/windows/win32/midl/-env) ARM32 | Win32 | ia64 | x64).

**Seçenekler**

- **Ayarlanmadı** -Win32
- **Microsoft Windows 32-bit** -Win32
- **Itanium-IA64 üzerinde Microsoft Windows 64-bit**
- **Microsoft WINDOWS ARM** -ARM
- **Microsoft WINDOWS ARM64** -ARM64
- **X64-x64 üzerinde Microsoft Windows 64-bit**

### <a name="generate-stubless-proxies"></a>Saplamasız proxy oluşturma

Nesne arabirimleri için Uzantılar ve saplamasız proxy 'leriyle tamamen yorumlanan saplamalar oluşturun ([/Oıcf](/windows/win32/midl/-oi), [/OIF](/windows/win32/midl/-oi) ).

### <a name="suppress-compiler-warnings"></a>Derleyici Uyarılarını Engelleme

Derleyici uyarı iletilerini gizleyin ([/no_warn](/windows/win32/midl/-no-warn)).

### <a name="application-configuration-mode"></a>Uygulama yapılandırma modu

IDL dosyasında seçilen ACF özniteliklerine izin ver ([/app_config](/windows/win32/midl/-app-config)).

### <a name="locale-id"></a>Yerel Ayar Kimliği

Giriş dosyaları, dosya adları ve dizin yolları için LCıD 'yi belirtir ([/LCID](/windows/win32/midl/-lcid) ondalık).

### <a name="multi-processor-compilation"></a>Çok Işlemcili derleme

Aynı anda birden çok örnek çalıştırın.

## <a name="output-property-page"></a>Çıkış Özellik sayfası

### <a name="output-directory"></a>Çıkış dizini

Çıkış dizinini belirtir ([/Out](/windows/win32/midl/-out) [Dizin]).

### <a name="metadata-file"></a>Meta veri dosyası

Oluşturulan meta veri dosyasının adını belirtir ([/WINMD](/windows/win32/midl/-winmd) filename).

### <a name="header-file"></a>Üst bilgi dosyası

Oluşturulan üst bilgi dosyasının adını belirtir ([/h](/windows/win32/midl/-h) filename).

### <a name="dlldata-file"></a>DllData dosyası

DLLDATA dosyasının adını belirtir ([/dlldata](/windows/win32/midl/-dlldata) filename).

### <a name="iid-file"></a>IID dosyası

Arabirim tanımlayıcı dosyasının adını belirtir ([/IID](/windows/win32/midl/-iid) dosya adı).

### <a name="proxy-file"></a>Proxy dosyası

Proxy dosyasının adını belirtir ([/proxy](/windows/win32/midl/-proxy) filename).

### <a name="generate-type-library"></a>Tür kitaplığı oluştur

Bir tür kitaplığı oluşturmama ([/notlb] for No) belirtin.

### <a name="type-library"></a>Tür kitaplığı

Tür kitaplığı dosyasının adını belirtir ([/tlb](/windows/win32/midl/-tlb) filename).

### <a name="generate-client-stub-files"></a>Istemci saplama dosyaları oluştur

Yalnızca istemci saplama dosyası oluştur ([/Client](/windows/win32/midl/-client) [stub | None]).

**Seçenekler**

- **Saplama** -saplama
- **Yok** -hiçbiri

### <a name="generate-server-stub-files"></a>Sunucu saplama dosyaları oluştur

Yalnızca sunucu saplama dosyası oluştur ([/Server](/windows/win32/midl/-server) [stub | None]).

**Seçenekler**

- **Saplama** -saplama
- **Yok** -hiçbiri

### <a name="client-stub-file"></a>İstemci saplama dosyası

İstemci Saplama dosyasını belirt ([/cstub](/windows/win32/midl/-cstub) [dosya]).

### <a name="server-stub-file"></a>Sunucu saplama dosyası

Sunucu Saplama dosyasını belirtin ([/sstub](/windows/win32/midl/-sstub) [dosya]).

### <a name="type-library-format"></a>Tür kitaplığı biçimi

Tür kitaplığı dosya biçimini belirtir ([/oldtlb |/newtlb]).

**Seçenekler**

- **NewFormat** -yeni biçim
- **Eskibiçim** -eski biçim

## <a name="advanced-property-page"></a>Gelişmiş özellik sayfası

### <a name="c-preprocess-options"></a>C ön Işleme seçenekleri

C derleyicisi önişlemcisi 'ne geçirilecek anahtarları belirtir ([/cpp_opt](/windows/win32/midl/-cpp-opt) anahtarlar).

### <a name="undefine-preprocessor-definitions"></a>Önişlemci tanımlarının tanımı kaldırılıyor

MıDL makroları ([/u](/windows/win32/midl/-U)  [makrolar]) dahil olmak üzere bir veya daha fazla tanımişaretini belirtir.

### <a name="enable-error-checking"></a>Hata denetimini etkinleştir

Hata denetimi seçeneğini belirleyin ([/Error All | None]).

**Seçenekler**

- **Enablecustom** -tümü
- **Tümü** -tümü
- **Yok** -hiçbiri

### <a name="check-allocations"></a>Ayırmaları denetle

Yetersiz bellek hatalarını denetle ([/Error](/windows/win32/midl/-error) Allocation).

### <a name="check-bounds"></a>Sınırları denetle

Denetim boyutu vs iletim uzunluğu belirtimi ([/Error](/windows/win32/midl/-error) bounds_check).

### <a name="check-enum-range"></a>Sabit Listesi aralığını denetle

Sabit listesi değerlerinin izin verilen aralıkta ([/Error](/windows/win32/midl/-error) enum) olup olmadığını denetleyin.

### <a name="check-reference-pointers"></a>Başvuru Işaretçilerini denetle

Başvuru işaretçilerini null olmayan ([/Error](/windows/win32/midl/-error) ref) olarak denetleyin.

### <a name="check-stub-data"></a>Saplama verilerini denetle

Sunucu tarafı saplama verileri geçerliliği için ek denetim yayma ([/Error](/windows/win32/midl/-error) stub_data).

### <a name="prepend-with-abi-namespace"></a>' ABı ' ad alanıyla Prepend

' ABı ' ad alanını tüm türlere ekleyin.  ([/ns_prefix](/windows/win32/midl/-ns-prefix)).

### <a name="validate-parameters"></a>Parametreleri doğrula

Parametreleri doğrulamak için ek bilgi oluşturun ([/dayanıklı](/windows/win32/midl/-robust)  |  [/no_robust](/windows/win32/midl/-no-robust)).

### <a name="struct-member-alignment"></a>Struct üye hizalaması

Hedef sistemdeki yapıların paket düzeyini belirtir (/ZpN).

**Seçenekler**

- **Ayarlanmadı-ayarlanmadı**
- **1 bayt** -ZP1
- **2 bayt** -ZP2
- **4 bayt** -ZP4
- **8 bayt** -ZP8

### <a name="redirect-output"></a>Çıktıyı yeniden yönlendir

Çıktıyı ekrandan bir dosyaya ([/o](/windows/win32/midl/-o) dosya) yönlendirir.

### <a name="minimum-target-system"></a>En düşük hedef sistem

En düşük hedef sistemi ([/target](/windows/win32/midl/-target) STRING) ayarlayın.
