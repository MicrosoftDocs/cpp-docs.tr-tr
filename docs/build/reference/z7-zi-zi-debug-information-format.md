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
ms.openlocfilehash: e809c7af7465cde98db11eac8628b76d04f7e8b5
ms.sourcegitcommit: 39debf8c525c3951af6913ee5e514617658f8859
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59424085"
---
# <a name="z7-zi-zi-debug-information-format"></a>/Z7, /Zi, /ZI (Hata Ayıklama Bilgileri Biçimi)

Programınız ve bu bilgileri nesne dosyalarında veya program veritabanı (PDB) dosyası tutulur için oluşturulan hata ayıklama bilgilerinin türünü belirtir.

## <a name="syntax"></a>Sözdizimi

> **/Z**{**7**|**i**|**I**}

## <a name="remarks"></a>Açıklamalar

Derleyici, kod derlenir ve hata ayıklama modunda yerleşik işlevleri ve değişkenler, tür bilgilerini ve satır numarası konumları hata ayıklayıcı tarafından kullanılmak için Sembol adlarını üretir. Bu sembolik hata ayıklama bilgileri, derleyici tarafından üretilen nesne dosyalarında (.obj dosyaları) veya yürütülebilir dosya için ayrı bir PDB dosyası (.pdb dosyası) eklenebilir.  Hata ayıklama bilgi biçimi seçenekleri aşağıdaki bölümlerde açıklanmıştır.

### <a name="none"></a>Yok.

Hata ayıklama bilgi biçimi seçeneği belirtilmezse, varsayılan olarak, derleyici derleme daha hızlı, bu nedenle, hata ayıklama bilgisi üretir.

### <a name="z7"></a>/Z7

**/Z7** seçeneği de kullanmak için hata ayıklayıcısı ile tam sembolik hata ayıklama bilgilerini içeren bir nesne dosyaları üretir. Bu nesne dosyaları ve yerleşik yürütülebilir dosya hata ayıklama bilgisi dosyalardan önemli ölçüde daha büyük olabilir. Sembolik hata ayıklama bilgileri, adlarını ve türlerini değişkenlerin, hem de işlevler ve satır numaralarını içerir. Hiç PDB dosyası oluşturulur.

Hata ayıklama sürümleri, üçüncü taraf kitaplıkların dağıtıcıları için bir PDB dosyası olmaması bir avantajı yoktur. Ancak, önceden derlenmiş üst bilgileri için nesne dosyaları kitaplığı bağlantı aşaması sırasında ve hata ayıklama için gereklidir. Varsa yalnızca .pch nesne dosyasında bilgi (ve kod) yazın, ayrıca kullanmalısınız [/Yl (ekleme PCH başvurusu hata ayıklama kitaplığı için)](yl-inject-pch-reference-for-debug-library.md) seçeneği kitaplığı derlerken, varsayılan olarak etkindir.

Kullanım dışı [/GM derlemeyi (etkinleştirme en az yeniden derlemeyi)](gm-enable-minimal-rebuild.md) seçeneği kullanılamaz olduğunda **/z7** belirtilir.

### <a name="zi"></a>/Zi

**/Zi** seçenek sembolik hata ayıklama bilgilerini kullanmak için hata ayıklayıcısı ile içeren ayrı bir PDB dosyası oluşturur. Hata ayıklama bilgilerini nesne dosyalarında bulunmayan veya yürütülebilir dosyası, hangi bunları çok daha küçük yapar.

Kullanım **/zi** iyileştirmeleri etkilemez. Ancak, **/zi** gelmez **/debug**; bkz [/Debug (hata ayıklama bilgisi Oluştur)](debug-generate-debug-info.md) daha fazla bilgi için.

Belirtirseniz her ikisi de **/zi** ve **/CLR**, <xref:System.Diagnostics.DebuggableAttribute> özniteliği derleme metaverisine yerleştirilmez değil yerleştirilir. İsterseniz, kaynak kodda belirtmeniz gerekir. Bu öznitelik, uygulamanın çalışma zamanı performansını etkileyebilir. Nasıl hakkında daha fazla bilgi için **Debuggable** özniteliği performansını etkiler ve performans etkisini değiştirebileceğiniz edinmek bkz [bir görüntü için hata ayıklama kolaylaştıracak](/dotnet/framework/debug-trace-profile/making-an-image-easier-to-debug).

PDB dosyası derleme adları *proje*.pdb. Proje dışındaki dosyasını derlerseniz derleyici, VC adlı bir PDB dosyası oluşturur.*x*.pdb, burada *x* derleyici sürümü kullanılıyor büyük ve küçük sürüm numarasını bir yapıdır. Derleyici hata ayıklayıcıyı sembolik bilgilere ve satır numarası bilgileri konumuna işaret bu seçenek kullanılarak oluşturulan her bir nesne dosyası adını PDB ve tanımlayıcı bir zaman damgalı imzası katıştırır. Ada ve imzaya PDB dosyasında hata ayıklayıcıda yüklenecek semboller çalıştırılabilir dosyanın eşleşmesi gerekir. WinDBG hata ayıklayıcısını kullanarak eşleşmeyen sembolleri yükleyebilir `.symopt+0x40` komutu. Visual Studio eşleşmeyen simgeleri yüklemek için benzer bir seçeneği yok.

Kullanılarak derlenmiş nesnelerden bir kitaplık oluşturursanız **/zi**, kitaplık bir programa bağlandığında ilgili .pdb dosyası kullanılabilir olmalıdır. Bu nedenle, kitaplığı dağıtırsanız, PDB dosyası da dağıtmanız gerekir. PDB dosyası kullanmadan hata ayıklama bilgilerini içeren bir kitaplık oluşturmak için seçmelisiniz **/z7** seçeneği. Önceden derlenmiş üstbilgiler seçenekleri kullanıyorsanız, hem önceden derlenmiş üst bilgi hem de kaynak kodunun kalanı için hata ayıklama bilgisi PDB dosyası içinde yer alır.

### <a name="zi"></a>/ZI

**/Zi** seçeneği benzer **/zi**, ancak destekleyen biçimde bir PDB dosyası oluşturan [Düzenle ve devam et](/visualstudio/debugger/edit-and-continue-visual-cpp) özelliği. Düzenle ve devam et hata ayıklama özellikleri kullanmak için bu seçeneği kullanmanız gerekir. Düzenle ve devam et özelliğini Geliştirici üretkenliğini için yararlıdır, ancak kod boyutuna, performans ve derleyici uyumluluğu sorunlarına neden olabilir. Çoğu iyileştirme Düzenle ve devam et ile uyumlu olmadığından kullanarak **/zi** herhangi `#pragma optimize` kodunuzda deyimleri. **/Zi** seçeneği kullanımıyla uyumlu ayrıca [ &#95; &#95;satırı&#95; &#95; önceden tanımlanmış makro](../../preprocessor/predefined-macros.md); derlenmiş kodu **/zi** kullanamazsınız **&#95; &#95;Satırı&#95; &#95;** bir tür olmayan şablon bağımsız değişkeni olarak rağmen **&#95; &#95;satırı&#95; &#95;** makro genişletme içinde kullanılabilir.

**/Zi** seçeneği hem de zorlar [/Gy (işlev düzeyi bağlamayı etkinleştir)](gy-enable-function-level-linking.md) ve [/FC (tam yol, kaynak kodu dosyasında tanılama)](fc-full-path-of-source-code-file-in-diagnostics.md) öğelerinin derlemenizde kullanılacak Seçenekler.

**/Zı** ile uyumlu olmayan [/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md).

> [!NOTE]
> **/Zi** seçeneği, yalnızca x86 ve x64 işlemcileri hedefleyen derleyicilerde kullanılabilir; Bu derleyici seçeneğini ARM işlemcileri hedefleyen derleyicilerde kullanılabilir değil.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **C/C++** > **genel** özellik sayfası.

1. Değiştirme **hata ayıklama bilgi biçimi** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DebugInformationFormat%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)

