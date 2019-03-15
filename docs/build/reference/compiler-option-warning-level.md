---
title: /w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)
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
ms.openlocfilehash: 997a73541ab95a393bda4ebf5412c11f025b03a3
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820695"
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, / W1, / w2, / W3, / W4, / W1, / w2, / W3, / W4, /Wall, WD, / we Wo, wv, /WX (uyarı düzeyi)

Derleyici belirli bir derleme için uyarıları nasıl oluşturur belirtir.

## <a name="syntax"></a>Sözdizimi

> **/w**
>  **/W0**
>  **/W1**
>  **/w2**
>  **/W3** 
>  **/W4**
>  **/wall**
>  **/Wv**\[**:**_sürümü _] **Wx**
>  **/W1**_uyarı_
>  **/w2** _ Uyarı_
>  **/W3**_uyarı_
>  **/W4**_uyarı_ 
>  **/wd**_uyarı_
>  **/we**_uyarı_ 
>  **/wo**_Uyarısı_

## <a name="remarks"></a>Açıklamalar

Hangi Derleyici uyarılarını görüntüleme ve tüm derleme uyarısı davranışını uyarı seçeneklerini belirtin.

Uyarı seçeneklerini ve ilişkili bağımsız değişkenler aşağıdaki tabloda açıklanmıştır:

|Seçenek|Açıklama|
------------|-----------------|
|**/w**|Tüm derleyici uyarıları bastırır.|
|**/ W0**<br /><br /> **/ W1**<br /><br /> **/ W2**<br /><br /> **/ W3**<br /><br /> **/ W4**|Derleyici tarafından oluşturulan bir uyarı düzeyini belirtir. Geçerli uyarı düzeylerini aralığı 0-4:<br />**/ W0** tüm uyarıları bastırır. Bunun eşdeğeri olan **/w**.<br />**/ W1** düzey 1 (Önemli) uyarıları görüntüler. **/ W1** komut satırı derleyicisini varsayılan ayardır.<br />**/ W2** düzey 1 ve Düzey 2 (Önemli) uyarıları görüntüler.<br />**/ W3** görüntüler düzey 1 Düzey 2 ve 3 (üretim kalitesinde) uyarıları düzeyi. **/ W3** IDE içindeki varsayılan ayardır.<br />**/ W4** düzey 1 Düzey 2 ve 3 uyarılar düzey görüntüler ve tüm varsayılan olarak kapalı değil 4 (bilgilendirme) uyarıları düzeyi. Lint benzeri uyarılar sağlamak için bu seçeneği kullanmanızı öneririz. Yeni bir proje için en iyi yöntem olabilir **/W4** tüm derlemelerde; Bunun en olası bulunur zor kod kusurlarını olmanızı sağlar.|
|**/ Wall**|Tarafından görüntülenen tüm uyarıları görüntüler **/W4** ve diğer tüm uyarılar, **/W4** içermemesi — Örneğin, varsayılan olarak kapalı olan uyarılar. Daha fazla bilgi için [derleyici uyarıları emin olan tarafından varsayılan olarak kapalıdır](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|**/Wv**\[**:**_sürüm_]|Yalnızca derleyici sürümü xx.yy.zzzz görüntüler *sürüm* ve önceki sürümleri. Derleyici daha yeni bir sürümüne geçiş yaptığınızda, kod içinde yeni uyarıları bastırmak için ve var olan yapı işlemi bunları düzeltilmesi üzerinde çalışırken korumak için bu seçeneği kullanabilirsiniz. İsteğe bağlı parametre *sürüm* alır *nn*[. *aa*[. *bbbbb*]] burada *nn* ana sürüm numarası *mm* isteğe bağlı alt sürüm numarası ve *bbbbb* isteğe bağlı derleme sayısı Derleyici. Örneğin, */Wv:17* Visual Studio 2012 (diğer bir deyişle, herhangi bir ana sürüm numarası 17 derleyici sürümü) veya önceki xx.yy.zzzz görüntüler, ancak Visual Studio 2013 (ana sürüm uyarıları bastırmak için 18) ve üzeri. Varsayılan olarak, **/Wv** geçerli derleyici sürüm numarasını ve uyarı özelliği kullanır. Hangi uyarıların derleyici sürümü tarafından gizlenir daha fazla bilgi için bkz [derleyici sürümüne göre derleyici uyarıları](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Tüm Derleyici uyarılarını hata olarak değerlendirir. Yeni bir proje için en iyi yöntem olabilir **wx** tüm derlemelerde; tüm uyarıların çözümlenmesi en az sayıda olası bulunur zor kod kusurlarını sağlar.<br /><br /> Bağlayıcı ayrıca sahip bir **wx** seçeneği. Daha fazla bilgi için [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](wx-treat-linker-warnings-as-errors.md).|
|**/ W1**_nnnn_<br /><br /> **/ w2**_nnnn_<br /><br /> **/ W3**_nnnn_<br /><br /> **/ W4**_nnnn_|Uyarı düzeyi tarafından belirtilen uyarı numarasını ayarlar _nnnn_. Bu, belirli bir uyarı düzeyi ayarlandığında bu uyarı için derleyici davranışını değiştirmesini sağlar. Varsayılan Visual Studio tarafından sağlanan değerleri yerine uyarılar için kendi kodlama standartları zorlamak için bu seçenekleri diğer uyarı seçenekleri ile birlikte kullanabilirsiniz.<br /><br /> Örneğin, **/w34326** C4326 yerine düzey 1 Düzey 3 uyarı oluşturulmasına neden olur. Her ikisini de kullanarak derleme yaparsanız **/w34326** seçeneği ve **/w2** C4326 oluşturulmuyor uyarı seçeneği.|
|**/WD**_nnnn_|Tarafından belirtilen derleyici uyarı bastırılır _nnnn_.<br /><br /> Örneğin, **/wd4326** derleyici C4326 uyarı bastırır.|
|**/We**_nnnn_|Tarafından belirtilen derleyici uyarı işler _nnnn_ hata olarak.<br /><br /> Örneğin, **/we4326** uyarı numarası C4326 derleyici tarafından hata olarak kabul edilmesine neden olur.|
|**/Wo**_nnnn_|Raporlar tarafından belirtilen diğer bir deyişle Derleyici Uyarı _nnnn_ yalnızca bir kez.<br /><br /> Örneğin, **/wo4326** nedenler, yalnızca bir kez bildirilecek C4326 uyarı ilk kez, karşılaşıldığında derleyici tarafından.|

Önceden derlenmiş üstbilgi kullanarak oluşturduğunuzda uyarı seçeneklerden herhangi birini kullanırsanız, [/Yc](yc-create-precompiled-header-file.md) seçeneğini kullanarak önceden derlenmiş üstbilgi kullanımı [/Yu](yu-use-precompiled-header-file.md) seçeneği geçerli olması bu aynı uyarı seçeneklerini neden olur yeniden. Komut satırında başka bir uyarı seçeneğini kullanarak önceden derlenmiş üst bilgisinde ayarlanmış uyarı seçeneklerini geçersiz kılabilirsiniz.

Kullanabileceğiniz bir [#pragma Uyarısı](../../preprocessor/warning.md) diğer bir deyişle uyarı düzeyini denetlemek için derleme zamanında belirli kaynak dosyalarında bildirdi.

Kaynak kodunda uyarı pragma yönergeleri tarafından etkilenmemesini **/w** seçeneği.

[Hataları belgelerinizi oluşturma](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) uyarılar ve uyarı düzeylerini açıklar ve istediğiniz gibi neden belirli deyimleri derleme değil gösterir.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında derleyici seçeneklerini ayarlama

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Ayarlanacak **/W0**, **/W1**, **/w2**, **/W3**, **/W4**, **/Wall**m **/Wv**, **wx** veya **/WX-** seçenekleri, select **yapılandırma özellikleri** > **C / C++** > **genel** özellik sayfası.

   - Ayarlanacak **/W0**, **/W1**, **/w2**, **/W3**, **/W4**, veya **/Wall** Seçenekleri Değiştir **uyarı düzeyi** özelliği.

   - Ayarlanacak **wx** veya **/WX-** seçenekleri değiştirme **uyarıları hata olarak değerlendir** özelliği.

   - Sürüm için ayarlanacak **/Wv** seçeneğinde, derleme sürüm numarası girin **uyarı sürümü** özelliği.

1. Ayarlanacak **/wd** veya **/we** seçenekleri, select **yapılandırma özellikleri** > **C/C++**  >   **Gelişmiş** özellik sayfası.

   - Ayarlanacak **/wd** seçeneği için **belirli uyarıları devre dışı** özellik açılan menü denetimi ve ardından **Düzenle**. Düzenleme kutusuna **belirli uyarıları devre dışı** iletişim kutusunda, uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül kullanarak ayırın (**;**). Örneğin, C4001 hem C4010 devre dışı bırakmak için girin **4001; 4010**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek ve geri dönmek için **özellik sayfaları** iletişim.

   - Ayarlanacak **/we** seçeneğini seçin **kabul belirli uyarıları olarak hataları** özellik açılan menü denetimi ve ardından **Düzenle**. Düzenleme kutusuna **kabul belirli uyarıları olarak hataları** iletişim kutusunda, uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül kullanarak ayırın (**;**). Örneğin, C4001 hem C4010 de hata olarak değerlendirilecek girin **4001; 4010**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek ve geri dönmek için **özellik sayfaları** iletişim.

1. Ayarlanacak **/wo** seçeneği için **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası. Derleyici seçeneğini girin **ek seçenekler** kutusu.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-the-compiler-option-programmatically"></a>Derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>, ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)
