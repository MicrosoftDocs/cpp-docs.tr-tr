---
title: /Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)
ms.date: 07/06/2020
f1_keywords:
- VC.Project.VCCLCompilerTool.DebugInformationFormat
- /ZI
- /Zi
- /Z7
- VC.Project.VCCLWCECompilerTool.DebugInformationFormat
helpviewer_keywords:
- C7 compatible compiler option [C++]
- Debug Information Format compiler option
- ZI compiler option
- -Zi compiler option [C++]
- /ZI compiler option [C++]
- Z7 compiler option [C++]
- debugging [C++], debug information files
- Zi compiler option [C++]
- /Zi compiler option [C++]
- program database compiler option [C++]
- full symbolic debugging information
- /Z7 compiler option [C++]
- line numbers only compiler option [C++]
- cl.exe compiler, debugging options
- -Z7 compiler option [C++]
ms.openlocfilehash: bc3fd9c065219a128e29290084b1e1fb51fc773e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: tr-TR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058600"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)

**`/Z7`**, **`/Zi`** Ve **`/ZI`** derleyici seçenekleri, programınız için oluşturulan hata ayıklama bilgilerinin türünü ve bu bilgilerin nesne dosyalarında mı yoksa bir program veritabanı (pdb) dosyasında tutulup tutulmadığını belirtir.

## <a name="syntax"></a>Syntax

> **`/Z7`**\
> **`/Zi`**\
> **`/ZI`**

## <a name="remarks"></a>Açıklamalar

Bir hata ayıklama seçeneği belirttiğinizde, derleyici, hata ayıklayıcı tarafından kullanılmak üzere işlevler ve değişkenler, tür bilgileri ve satır konumları için sembol adları üretir. Bu sembolik hata ayıklama bilgileri *`.obj`* , derleyici tarafından üretilen nesne dosyalarına (dosyalar) veya yürütülebilir dosya için ayrı bır pdb dosyasında (bir *`.pdb`* dosya) bulunabilir. Hata ayıklama bilgileri biçim seçenekleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="none"></a>Hiçbiri

Varsayılan olarak, hata ayıklama bilgileri biçim seçeneği belirtilmemişse, derleyici hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlıdır.

### <a name="z7"></a>/Z7

**`/Z7`** Seçeneği, hata ayıklayıcıyla birlikte kullanılmak üzere tam sembolik hata ayıklama bilgilerini de içeren nesne dosyaları üretir. Bu nesne dosyaları ve bunlardan oluşturulan kitaplıklar, hata ayıklama bilgilerine sahip olmayan dosyalardan önemli ölçüde daha büyük olabilir. Simgesel hata ayıklama bilgileri, değişkenlerin, işlevlerin ve satır numaralarının adlarını ve türlerini içerir. Derleyici tarafından hiçbir PDB dosyası üretilmedi. Ancak, bağlayıcı seçeneği geçmişse, bu nesne dosyalarından veya kitaplıklarından bir PDB dosyası yine de oluşturulabilir **`/DEBUG`** .

Üçüncü taraf kitaplıklarının hata ayıklama sürümlerinin dağıtımcıları için PDB dosyasına sahip olmanın bir avantajı vardır. Ancak, önceden derlenmiş üstbilgilerin nesne dosyaları kitaplık bağlantı aşamasında ve hata ayıklama sırasında gereklidir. Nesne dosyasında yalnızca tür bilgileri (kod yok) varsa *`.pch`* , kitaplığı oluştururken varsayılan olarak etkinleştirilen [ `/Yl` (hata ayıklama kitaplığı için PCH başvurusu Ekle)](yl-inject-pch-reference-for-debug-library.md) seçeneğini de kullanmalısınız.

Kullanım dışı [ `/Gm` (en az yeniden derlemeyi etkinleştir)](gm-enable-minimal-rebuild.md) seçeneği **`/Z7`** belirtildiğinde kullanılamaz.

### <a name="zi"></a>/Zi

**`/Zi`** Seçeneği, hata ayıklayıcıyla birlikte kullanılmak üzere tüm sembolik hata ayıklama bilgilerini içeren ayrı bır pdb dosyası oluşturur. Hata ayıklama bilgileri nesne dosyalarına veya yürütülebilir dosyaya dahil değildir ve bu da çok daha küçük hale gelir.

Kullanımı **`/Zi`** iyileştirmeleri etkilemez. Ancak, anlamına **`/Zi`** gelmez **`/debug`** . Daha fazla bilgi için bkz. [ `/DEBUG` (hata ayıklama bilgisi oluştur)](debug-generate-debug-info.md).

Hem hem de belirttiğinizde **`/Zi`** **`/clr`** , <xref:System.Diagnostics.DebuggableAttribute> öznitelik derleme meta verilerine yerleştirilmez. İsterseniz, bunu kaynak kodunda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. `Debuggable`Özniteliğin performansı nasıl etkilediği ve performans etkisini nasıl değiştirebileceğiniz hakkında daha fazla bilgi için bkz. [bir görüntüyü hata ayıklamayı kolaylaştırın](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

Derleyici PDB dosyasını adlandırır *`<project>.pdb`* , burada *`<project>`* projenizin adıdır. Bir projenin dışında bir dosya derlerseniz, derleyici adlı bir PDB dosyası oluşturur; *`VC<x>.pdb`* burada, *`<x>`* Kullanımdaki derleyici sürümünün ana ve alt sürüm numarasının bir birleşimi bulunur. Derleyici, bu seçenek kullanılarak oluşturulan her nesne dosyasında PDB 'nin adını ve bir tanımlayıcı zaman damgası kümesini gömer. Bu ad ve imza, hata ayıklayıcıyı sembolik ve satır numarası bilgilerinin konumuna işaret edin. PDB dosyasındaki ad ve imza, hata ayıklayıcıda yüklenecek sembollerin yürütülebilir dosyasıyla eşleşmelidir. WinDBG hata ayıklayıcı, komutu kullanarak eşleşmeyen sembolleri yükleyebilir **`.symopt+0x40`** . Visual Studio eşleşmeyen sembolleri yüklemek için benzer bir seçeneğe sahip değildir.

Kullanılarak derlenen nesnelerden bir kitaplık oluşturursanız **`/Zi`** , kitaplık bir programa bağlandığında ILIŞKILI pdb dosyası kullanılabilir olmalıdır. Yani, kitaplığı dağıtırsanız PDB dosyasını da dağıtmanız gerekir. PDB dosyalarını kullanmadan hata ayıklama bilgilerini içeren bir kitaplık oluşturmak için, seçeneğini seçmeniz gerekir **`/Z7`** . Ön derlenmiş üstbilgiler seçeneklerini kullanırsanız, hem ön derlenmiş üst bilgi için hata ayıklama bilgileri hem de kaynak kodun geri kalanı PDB dosyasına yerleştirilir.

### <a name="zi"></a>/ZI

**`/ZI`** Seçeneği ile benzerdir **`/Zi`** , ancak [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) ÖZELLIĞINI destekleyen bir biçimde pdb dosyası oluşturur. Düzenle ve devam et hata ayıklama özelliklerini kullanmak için bu seçeneği kullanmanız gerekir. Düzenle ve devam et özelliği, geliştirici üretkenliği için yararlıdır, ancak kod boyutu, performans ve derleyici uyumluluğu konularında sorunlara yol açabilir. Çoğu iyileştirme Düzenle ve devam et ile uyumlu olmadığından, kullanmak **`/ZI`** kodunuzdaki deyimleri devre dışı bırakır `#pragma optimize` . **`/ZI`** Seçeneği, [ `__LINE__` önceden tanımlanmış makronun](../../preprocessor/predefined-macros.md)kullanımıyla de uyumsuzdur; ile derlenen kod **`/ZI`** `__LINE__` , tür olmayan bir şablon bağımsız değişkeni olarak kullanılamaz, ancak `__LINE__` makro genişletmeleri içinde kullanılabilir.

**`/ZI`** Seçeneği, derinizde kullanılmak üzere hem [ `/Gy` (işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md) hem de [ `/FC` (Tanılama 'da kaynak kodu dosyası tam yolu)](fc-full-path-of-source-code-file-in-diagnostics.md) seçeneklerini zorlar.

**`/ZI`**, [ `/clr` (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)ile uyumsuzdur.

> [!NOTE]
> **`/ZI`** Seçeneği yalnızca x86 ve x64 işlemcileri hedefleyen derleyicilerde kullanılabilir. Bu derleyici seçeneği ARM işlemcilerini hedefleyen derleyicilerde kullanılamaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **genel** özellik sayfasını açın.

1. **Hata ayıklama bilgi biçimi** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyicisi seçenekleri](compiler-options.md)<br/>
[MSVC derleyicisi komut satırı söz dizimi](compiler-command-line-syntax.md)
