---
title: /w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)
ms.date: 01/31/2018
f1_keywords:
- VC.Project.VCCLCompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarningLevel
- VC.Project.VCCLWCECompilerTool.DisableSpecificWarnings
- VC.Project.VCCLCompilerTool.WarnAsError
- VC.Project.VCCLWCECompilerTool.WarnAsError
- /wx
- VC.Project.VCCLWCECompilerTool.WarningLevel
- /wall
- VC.Project.VCCLCompilerTool.TreatSpecificWarningsAsErrors
- /Wv
- /w0
- /w1
- /w2
- /w3
- /w4
- /wd
- /we
- /wo
helpviewer_keywords:
- /W1 compiler option [C++]
- w compiler option [C++]
- -wo compiler option [C++]
- Warning Level compiler option
- W1 compiler option [C++]
- -we compiler option [C++]
- /WX compiler option [C++]
- -wd compiler option [C++]
- WX compiler option [C++]
- wo compiler option [C++]
- Wall compiler option [C++]
- /w compiler option
- W2 compiler option [C++]
- -W2 compiler option [C++]
- wd compiler option [C++]
- /we compiler option [C++]
- we compiler option [C++]
- -W1 compiler option [C++]
- -W4 compiler option [C++]
- -Wall compiler option [C++]
- /Wall compiler option [C++]
- -W0 compiler option [C++]
- W0 compiler option [C++]
- -WX compiler option [C++]
- /wo compiler option [C++]
- W4 compiler option [C++]
- W3 compiler option [C++]
- /wd compiler option [C++]
- warnings, as errors compiler option
- /W3 compiler option [C++]
- /W0 compiler option [C++]
- /W4 compiler option [C++]
- -W3 compiler option [C++]
- -w compiler option [C++]
- /W2 compiler option [C++]
- /Wv compiler option [C++]
ms.openlocfilehash: 7d2fd21c476ef4346aa86e682047ea644183b2f3
ms.sourcegitcommit: d0504e2337bb671e78ec6dd1c7b05d89e7adf6a7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/02/2019
ms.locfileid: "74683052"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/duvar,/WD,/we,/Wo,/WV,/WX (uyarı düzeyi)

Derleyicinin belirli bir derleme için nasıl uyarı üretmediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/w**\
> **/W0**\
> **/W1**\
> **/W2**\
> **/W3**\
> **/W4**\
> **/Duvar**\
> **/WV**\[ **:** _Sürüm_] \
> **/WX**\
> **/W1**_Uyarı_\
> **/W2**_Uyarı_\
> **/w3**_Uyarı_\
> **/W4**_Uyarı_\
> **/WD**_uyarısı_\
> **/we**_uyarısı_\
> **/Wo**_uyarısı_

## <a name="remarks"></a>Açıklamalar

Uyarı seçenekleri hangi derleyici uyarılarının gösterileceğini ve tüm derleme için uyarı davranışını belirtir.

Uyarı seçenekleri ve ilgili bağımsız değişkenler aşağıdaki tabloda açıklanmıştır:

|Seçenek|Açıklama|
------------|-----------------|
|**aralıkları**|Tüm derleyici uyarılarını bastırır.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/W2**<br /><br /> **/W3**<br /><br /> **/W4**|Derleyici tarafından üretilecek uyarı düzeyini belirtir. Geçerli uyarı düzeyleri 0 ile 4 arasındadır:<br />**/W0** tüm uyarıları bastırır. Bu, **/w**ile eşdeğerdir.<br />**/W1** düzey 1 (ciddi) uyarıları görüntüler. **/W1** , komut satırı derleyicisinde varsayılan ayardır.<br />**/W2** düzey 1 ve düzey 2 (önemli) uyarılarını görüntüler.<br />**/W3** düzey 1, düzey 2 ve düzey 3 (üretim kalitesi) uyarılarını görüntüler. **/W3** , IDE 'deki varsayılan ayardır.<br />**/W4** düzey 1, düzey 2 ve düzey 3 uyarılarını ve varsayılan olarak kapalı olmayan tüm düzey 4 (bilgilendirici) uyarılarını görüntüler. Bu seçeneği, Lint benzeri uyarılar sağlamak için kullanmanızı öneririz. Yeni bir proje için tüm derlemelerde **/W4** kullanılması en iyi yöntem olabilir; Bu, mümkün olan en az sayıda kod kusurlarını güvence altına alacak.|
|**/Wall**|**/W4** tarafından görüntülenen tüm uyarıları ve **/W4 ' ün** içermediği tüm diğer uyarıları görüntüler; Örneğin, varsayılan olarak kapalı olan uyarılar. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|**/WV**\[ **:** _Sürüm_]|Yalnızca derleyici sürümü *sürümü* ve önceki sürümlerde tanıtılan uyarıları görüntüler. Bu seçeneği, derleyicinin daha yeni bir sürümüne geçiş yaptığınızda ve var olan derleme sürecinizi düzelttikten sonra, koddaki yeni uyarıları bastırmak için kullanabilirsiniz. İsteğe bağlı parametre *sürümü* *nn*[biçimini alır. *dd*[. *bbbbb*]]/ *nn* ana sürüm numarası, *mm* ise isteğe bağlı alt sürüm numarasıdır ve *bbbbb* , derleyicinin isteğe bağlı yapı numarasıdır. Örneğin, Visual Studio 2012 (yani, ana sürüm numarası 17 olan herhangi bir derleyicinin sürümü) veya önceki sürümlerde tanıtılan uyarıları göstermek için */WV: 17* kullanın, ancak Visual Studio 2013 (ana sürüm 18) ve sonraki sürümlerde bulunan uyarıları gizleyin. Varsayılan olarak, **/WV** geçerli derleyici sürüm numarasını kullanır ve hiçbir uyarı gösterilmez. Derleyici sürümü tarafından hangi uyarıların bastırıldıkları hakkında bilgi için bkz. derleyici [sürümüne göre derleyici uyarıları](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Tüm derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için tüm derlemelerde **/WX** kullanılması en iyi yöntem olabilir; Tüm uyarıların çözümlenmesi, en az olası bulma kod kusurlarını sağlar.<br /><br /> Bağlayıcının bir **/WX** seçeneği de vardır. Daha fazla bilgi için bkz. [/WX (bağlayıcı uyarılarını hata olarak işle)](wx-treat-linker-warnings-as-errors.md).|
|**/W1**_nnnn_<br /><br /> **/W2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/W4**_nnnn_|_Nnnn_tarafından belirtilen uyarı numarası için uyarı düzeyini ayarlar. Bu, belirli bir uyarı düzeyi ayarlandığında söz konusu uyarının derleyici davranışını değiştirmenize olanak sağlar. Bu seçenekleri diğer uyarı seçenekleriyle birlikte kullanarak, Visual Studio tarafından sağlananlara değil, uyarılar için kendi kodlama standartlarınızı zorunlu kılabilirsiniz.<br /><br /> Örneğin, **/w34326** , C4326 'in düzey 1 yerine bir düzey 3 uyarısı olarak oluşturulmasına neden olur. Hem **/w34326** seçeneğini hem de **/W2** seçeneğini kullanarak derlerseniz, uyarı C4326 oluşturulmaz.|
|**/WD**_nnnn_|_Nnnn_tarafından belirtilen derleyici uyarısını bastırır.<br /><br /> Örneğin, **/WD4326** derleyici uyarısı C4326 ' ı bastırır.|
|**/we**_nnnn_|_Nnnn_ tarafından belirtilen derleyici uyarısını bir hata olarak değerlendirir.<br /><br /> Örneğin, **/we4326** , C4326 uyarı numarası olarak derleyicinin hata olarak işlenmesine neden olur.|
|**/Wo**_nnnn_|Yalnızca bir kez _nnnn_ tarafından belirtilen derleyici uyarısını raporlar.<br /><br /> Örneğin, **/wo4326** , uyarı C4326 'in yalnızca bir kez bildirilmesine neden olur. Bu, derleyici tarafından ilk kez karşılaşacaktır.|

[/Yıc](yc-create-precompiled-header-file.md) seçeneğini kullanarak önceden derlenmiş bir üst bilgi oluşturduğunuzda herhangi bir uyarı seçeneğini kullanırsanız, [/yu](yu-use-precompiled-header-file.md) seçeneğini kullanarak önceden derlenmiş üstbilginin herhangi bir kullanımı, aynı uyarı seçeneklerinin yeniden etkin olmasına neden olur. Ön derlenmiş üst bilgide ayarlanan uyarı seçeneklerini, komut satırında başka bir uyarı seçeneği kullanarak geçersiz kılabilirsiniz.

Belirli kaynak dosyalardaki derleme zamanında bildirilen uyarı düzeyini denetlemek için [#pragma uyarı](../../preprocessor/warning.md) yönergesini kullanabilirsiniz.

Kaynak kodundaki Uyarı pragma yönergeleri **/w** seçeneğinden etkilenmez.

[Derleme hataları belgeleri](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) , uyarıları ve uyarı düzeylerini açıklar ve bazı deyimleriniz istediğiniz gibi derlenmeyebilir.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki derleyici seçeneklerini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **/W0**, **/W1**, **/W2**, **/w3**, **/W4**, **/duvar**, **/WV**, **/WX** veya **/WX-** Options seçeneklerini ayarlamak için **yapılandırma özellikleri** > **C/C++**  > **genel** Özellik sayfası ' nı seçin.

   - **/W0**, **/W1**, **/W2**, **/w3**, **/W4**veya **/duvar** seçeneklerini ayarlamak için, **Uyarı düzeyi** özelliğini değiştirin.

   - **/WX** veya **/WX-** Options ' ı ayarlamak Için **uyarıları hata olarak değerlendir** özelliğini değiştirin.

   - **/WV** seçeneğinin sürümünü ayarlamak Için, **Uyarı sürümü** özelliğinde derleyici sürüm numarasını girin.

1. **/WD** veya **/we** seçeneklerini ayarlamak için **yapılandırma özellikleri** > **C/C++**  > **Gelişmiş** Özellik sayfası ' nı seçin.

   - **/WD** seçeneğini ayarlamak Için, **belirli uyarıları devre dışı bırak** Özellik açılan denetimini seçin ve ardından **Düzenle**' yi seçin. **Belirli uyarıları devre dışı bırak** iletişim kutusundaki Düzenle kutusunda uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül ( **;** ) kullanarak ayırın. Örneğin, hem C4001 hem de C4010 'yi devre dışı bırakmak için, **4001; 4010**girin. Değişikliklerinizi kaydetmek ve **Özellik sayfaları** iletişim kutusuna dönmek için **Tamam** ' ı seçin.

   - **/We** seçeneğini ayarlamak Için, **belirli uyarıları hata olarak işle** özelliği açılan denetim ' i seçin ve ardından **Düzenle**' yi seçin. **Belirli uyarıları hata olarak işle** iletişim kutusundaki Düzenle kutusunda, uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül ( **;** ) kullanarak ayırın. Örneğin, hem C4001 hem de C4010 hata olarak değerlendirmek için, **4001; 4010**girin. Değişikliklerinizi kaydetmek ve **Özellik sayfaları** iletişim kutusuna dönmek için **Tamam** ' ı seçin.

1. **/Wo** seçeneğini ayarlamak için **yapılandırma özellikleri** > **C++ C/**  > **komut satırı** Özellik sayfası ' nı seçin. **Ek seçenekler** kutusunda derleyici seçeneğini girin.

1. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-the-compiler-option-programmatically"></a>Derleyici seçeneğini programlı olarak ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
