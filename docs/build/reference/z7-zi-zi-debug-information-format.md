---
title: /Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)
ms.date: 04/08/2019
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
ms.openlocfilehash: aeaf435874b6d6b9dbc8a3d12ec06d38bf33aaae
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078258"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)

Programınız için oluşturulan hata ayıklama bilgilerinin türünü ve bu bilgilerin nesne dosyalarında mı yoksa bir program veritabanı (PDB) dosyasında tutulup tutulmadığını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Z**{**7**|**i**|**ı**}

## <a name="remarks"></a>Açıklamalar

Kod derlendiğinde ve hata ayıklama modunda yapılandırıldığında, derleyici, hata ayıklayıcı tarafından kullanılmak üzere işlevler ve değişkenler, tür bilgileri ve satır numarası konumları için sembol adları üretir. Bu sembolik hata ayıklama bilgileri, derleyici tarafından üretilen nesne dosyalarında (. obj dosyaları) veya yürütülebilir dosyanın ayrı bir PDB dosyasında (bir. pdb dosyası) bulunabilir.  Hata ayıklama bilgileri biçim seçenekleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="none"></a>Yok

Varsayılan olarak, hata ayıklama bilgileri biçim seçeneği belirtilmemişse, derleyici hata ayıklama bilgisi üretmez, bu nedenle derleme daha hızlıdır.

### <a name="z7"></a>/Z7

**/Z7** seçeneği, hata ayıklayıcı ile kullanılmak üzere tam sembolik hata ayıklama bilgilerini de içeren nesne dosyaları oluşturur. Bu nesne dosyaları ve oluşturulan yürütülebilir dosya, hata ayıklama bilgisi olmayan dosyalardan önemli ölçüde daha büyük olabilir. Simgesel hata ayıklama bilgileri, işlevlerin ve satır numaralarının adlarının yanı sıra değişkenlerini ve türlerini içerir. Hiçbir PDB dosyası üretilmedi.

Üçüncü taraf kitaplıklarının hata ayıklama sürümlerinin dağıtımcıları için PDB dosyasına sahip olmanın bir avantajı vardır. Ancak, önceden derlenmiş üstbilgilerin nesne dosyaları kitaplık bağlantı aşamasında ve hata ayıklama sırasında gereklidir. . Pch nesne dosyasında yalnızca tür bilgileri varsa (kod yok), kitaplığı oluştururken varsayılan olarak etkinleştirilen [/Rivl (hata ayıklama kitaplığı IÇIN PCH başvurusu Ekle)](yl-inject-pch-reference-for-debug-library.md) seçeneğini de kullanmalısınız.

Geçersiz kılmak üzere kullanım dışı olan [/g/(en az yeniden derlemeyi etkinleştir)](gm-enable-minimal-rebuild.md) seçeneği, **/Z7** belirtildiğinde kullanılamaz.

### <a name="zi"></a>/Zi

**/Zı** seçeneği, hata ayıklayıcıyla birlikte kullanılmak üzere tüm sembolik hata ayıklama bilgilerini içeren ayrı bir PDB dosyası oluşturur. Hata ayıklama bilgileri nesne dosyalarına veya yürütülebilir dosyaya dahil değildir ve bu da çok daha küçük hale gelir.

**/Zi** kullanımı iyileştirmeleri etkilemez. Ancak, **/Zi** , **/Debug**; daha fazla bilgi için bkz. [/Debug (hata ayıklama bilgileri üret)](debug-generate-debug-info.md) .

Hem **/Zi** hem de **/clr**belirttiğinizde, <xref:System.Diagnostics.DebuggableAttribute> özniteliği derleme meta verilerine yerleştirilmez. İsterseniz, bunu kaynak kodunda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. **Hata ayıklanabilir** özniteliğinin performansı nasıl etkilediği ve performans etkisini nasıl değiştirebileceğiniz hakkında daha fazla bilgi için bkz. [bir görüntüyü hata ayıklamayı kolaylaştırın](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

Derleyici PDB dosyasını *Project*. pdb olarak adlandırır. Bir projenin dışında bir dosya derlerseniz, derleyici VC*x*. pdb ADLı bir PDB dosyası oluşturur; burada *x* , kullanımdaki derleyici sürümünün ana ve alt sürüm numarası birleşimi olur. Derleyici PDB adını ve bu seçenek kullanılarak oluşturulan her nesne dosyasında, hata ayıklayıcıyı sembolik ve satır numarası bilgilerinin bulunduğu konuma gösteren bir tanımlayıcı zaman damgası olarak ekler. PDB dosyasındaki ad ve imza, hata ayıklayıcıda yüklenecek sembollerin yürütülebilir dosyasıyla eşleşmelidir. WinDBG hata ayıklayıcısı, `.symopt+0x40` komutunu kullanarak eşleşmeyen sembolleri yükleyebilir. Visual Studio eşleşmeyen sembolleri yüklemek için benzer bir seçeneğe sahip değildir.

**/Zi**kullanılarak derlenen nesnelerden bir kitaplık oluşturursanız, kitaplık bir programa bağlandığında ilişkili. pdb dosyası kullanılabilir olmalıdır. Bu nedenle, kitaplığı dağıtırsanız PDB dosyasını da dağıtmanız gerekir. PDB dosyalarını kullanmadan hata ayıklama bilgilerini içeren bir kitaplık oluşturmak için **/Z7** seçeneğini seçmeniz gerekir. Ön derlenmiş üstbilgiler seçeneklerini kullanırsanız, hem ön derlenmiş üst bilgi için hata ayıklama bilgileri hem de kaynak kodun geri kalanı PDB dosyasına yerleştirilir.

### <a name="zi"></a>/ZI

**/Zi** seçeneği **/Zi**Ile benzerdir, ancak [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) özelliğini destekleyen bir biçimde pdb dosyası oluşturur. Düzenle ve devam et hata ayıklama özelliklerini kullanmak için bu seçeneği kullanmanız gerekir. Düzenle ve devam et özelliği, geliştirici üretkenliği için yararlıdır, ancak kod boyutu, performans ve derleyici uyumluluğu konularında sorunlara yol açabilir. Çoğu iyileştirme Düzenle ve devam et ile uyumlu olmadığından, **/Zi** kullanmak kodunuzda `#pragma optimize` deyimlerini devre dışı bırakır. **/Zi** seçeneği Ayrıca, [ &#95; &#95;satır&#95; &#95; önceden tanımlanmış makro](../../preprocessor/predefined-macros.md)kullanımıyla uyumlu değildir; **/Zi** ile derlenen kod, tür olmayan bir şablon bağımsız değişkeni olarak **&#95; &#95;Line&#95;** kullanamaz, ancak **&#95; &#95;satır&#95;** makro genişletmeleri içinde kullanılabilir.

**/Zi** seçeneği, derlemede kullanılmak üzere hem [/GY (Işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md) hem de [/FC (Tanılama 'Da kaynak kodu dosyası tam yolu)](fc-full-path-of-source-code-file-in-diagnostics.md) seçeneğini zorlar.

**/Zi** [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)ile uyumlu değil.

> [!NOTE]
> **/Zı** seçeneği yalnızca x86 ve x64 işlemcileri hedefleyen derleyicilerde kullanılabilir; Bu derleyici seçeneği ARM işlemcilerini hedefleyen derleyicilerde kullanılamaz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **C/C++**  > **genel** Özellik sayfası ' nı açın.

1. **Hata ayıklama bilgi biçimi** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
