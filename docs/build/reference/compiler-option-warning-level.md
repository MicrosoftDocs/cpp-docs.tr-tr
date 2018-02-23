---
title: -w, -W0, -W1, -W2, -W3, -W4, -w1, -w2, -w3, -w4, -Wall, -wd, -we, -wo, -Wv, -WX (Warning Level) | Microsoft Docs
ms.custom: 
ms.date: 01/31/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee6ac53bd92873279c08dc7458114612d00ff791
ms.sourcegitcommit: a5a69d2dc3513261e9e28320e4e067aaf40d2ef2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/21/2018
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warning Level)

Derleyici belirli bir derleme için uyarıları nasıl oluşturur belirtir.

## <a name="syntax"></a>Sözdizimi

> **/w**  
> **/W0**  
> **/W1**  
> **/ W2**  
> **/W3**  
> **/ W4**  
> **/ Wall**  
> **/Wv**\[**:**_sürüm_]  
> **/WX**  
> **/W1**_uyarı_  
> **/w2**_uyarı_  
> **/W3**_uyarı_  
> **/W4**_uyarı_  
> **/WD**_uyarı_  
> **/We**_uyarı_  
> **/Wo**_uyarı_  

## <a name="remarks"></a>Açıklamalar

Hangi Derleyici uyarılarını görüntüleme ve tüm derleme için uyarı davranışı uyarı seçeneklerini belirtin.

Uyarı seçenekleri ve ilişkili bağımsız değişkenler aşağıdaki tabloda açıklanmıştır:

|Seçenek|Açıklama|
------------|-----------------|
|**/w**|Tüm derleyici uyarıları bastırır.|
|**/W0**<br /><br /> **/W1**<br /><br /> **/ W2**<br /><br /> **/W3**<br /><br /> **/ W4**|Derleyici tarafından üretilen uyarılar düzeyini belirtir. Geçerli uyarı düzeylerini aralığı 0'dan 4:<br />**/ W0** tüm uyarıları bastırır. Bu eşdeğer olan **/w**.<br />**/ W1** düzey 1 (ciddi) uyarıları görüntüler. **/ W1** komut satırı derleyicisini varsayılan ayardır.<br />**/ W2** düzey 1 ve Düzey 2 (Önemli) uyarıları görüntüler.<br />**/ W3** görüntüler düzey 1, Düzey 2 ve 3 (üretim kalite) uyarıları düzeyi. **/ W3** IDE içinde varsayılan ayardır.<br />**/ W4** düzey 1, Düzey 2 ve 3 uyarıları düzey görüntüler ve tüm varsayılan olarak kapalı değil 4 (bilgilendirme) uyarıları düzeyi. Tüy benzeri uyarıları sağlamak için bu seçeneği kullanmanızı öneririz. Yeni bir proje için en iyi yöntem olabilir **/W4** tüm derlemeleri içinde; bu en az olası Bul sabit kod kusurları güvence altına alır.|
|**/ Wall**|Tarafından görüntülenen tüm uyarıları görüntüler **/W4** ve diğer tüm uyarıları, **/W4** içermemesi — Örneğin, varsayılan olarak kapalı olan uyarılar. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz tarafından varsayılan olarak kapalıdır](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|
|**/Wv**\[**:**_sürüm_]|Yalnızca derleyici sürümünde sunulan uyarıları görüntüler *sürüm* ve önceki sürümleri. Derleyici daha yeni bir sürüme geçiş yaparken kodda yeni uyarıları bastırma ve bunları düzeltmek sırada mevcut yapı işleminizin korumak için bu seçeneği kullanabilirsiniz. İsteğe bağlı bir parametre *sürüm* formundadır  *nn* [. *aa*[. *bbbbb*]] burada  *nn*  ana sürüm numarası *mm* isteğe bağlı ikincil sürüm numarası ve *bbbbb* olduğu İsteğe bağlı yapılandırma derleyici sayısı. Örneğin, */Wv:17* Visual Studio 2012 (diğer bir deyişle, herhangi bir ana sürüm numarası 17 derleyici sürümü) veya daha önceki sürümlerde sunulan uyarılar, ancak Visual Studio 2013 (ana sürüm sunulan uyarıları bastırma 18) ve üstü. Varsayılan olarak, **/Wv** geçerli derleyici sürüm numarasını ve hiçbir uyarılar gizlenir kullanır. Hakkında uyarı derleyici sürümü tarafından gizlenir daha fazla bilgi için bkz [derleyici uyarıları derleyici sürümüne göre](../../error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|
|**/WX**|Tüm derleyici uyarıları hata olarak değerlendirir. Yeni bir proje için en iyi yöntem olabilir **/WX** tüm derlemeleri içinde; tüm uyarıları çözümleme en az olası Bul sabit kod kusurları sağlar.<br /><br /> Bağlayıcı ayrıca sahip bir **/WX** seçeneği. Daha fazla bilgi için bkz: [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|
|**/w1**_nnnn_<br /><br /> **/w2**_nnnn_<br /><br /> **/w3**_nnnn_<br /><br /> **/w4**_nnnn_|Uyarı düzeyi tarafından belirtilen uyarı sayısını ayarlar  _nnnn_ . Bu, belirli bir uyarı düzeyi olarak ayarlandığında bu uyarı için derleyici davranışı değiştirmenize olanak sağlar. Visual Studio tarafından sağlanan olanları varsayılan yerine uyarılar için kendi kodlama standartları zorlamak için bu seçenekleri diğer uyarı seçenekleri ile birlikte kullanabilirsiniz.<br /><br /> Örneğin, **/w34326** C4326 düzey 1 yerine Düzey 3 uyarı oluşturulmasına neden olur. Her ikisini de kullanarak derleme yaparsanız **/w34326** seçeneği ve **/W2** C4326 oluşturulmuyor uyarı seçeneği.|
|**/wd**_nnnn_|Tarafından belirtilen derleyici uyarısı bastırır  _nnnn_ .<br /><br /> Örneğin, **/wd4326** C4326 uyarı derleyici gizler.|
|**/we**_nnnn_|Tarafından belirtilen derleyici uyarısı değerlendirir  _nnnn_  hata olarak.<br /><br /> Örneğin, **/we4326** uyarı numarası hata olarak derleyici tarafından kabul edilmesi için C4326 neden olur.|
|**/wo**_nnnn_|Tarafından belirtilen diğer bir deyişle derleyici uyarı raporları  _nnnn_  yalnızca bir kez.<br /><br /> Örneğin, **/wo4326** nedenleri, yalnızca bir kez bildirilecek C4326 uyarı ilk kez karşılaştığından derleyici tarafından.|

Önceden derlenmiş üst bilgi kullanarak oluşturduğunuzda uyarı seçeneklerinden herhangi birini kullanırsanız, [/Yc](../../build/reference/yc-create-precompiled-header-file.md) seçeneğini kullanarak önceden derlenmiş üst bilgi herhangi bir kullanımından [/Yu](../../build/reference/yu-use-precompiled-header-file.md) seçenek etkili olması bu aynı uyarı seçenekleri neden olur yeniden. Önceden derlenmiş üst bilgi komut satırında başka bir uyarı seçeneği kullanılarak ayarlanmış uyarı seçeneklerini geçersiz kılabilirsiniz.

Kullanabileceğiniz bir [#pragma Uyarısı](../../preprocessor/warning.md) olan uyarı düzeyini denetlemek için yönergesi belirli bir kaynak dosyaları derleme zamanında bildirdi.

Uyarı pragma yönergeleri kaynak kodundaki tarafından etkilenmemesini **/w** seçeneği.

[Hataları belge yapı](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) uyarıları ve uyarı düzeylerini tanımlar ve istediğiniz gibi neden belirli deyimleri derleme değil gösterir.

### <a name="to-set-the-compiler-options-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında derleyici seçeneklerini ayarlama

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Ayarlamak için **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, **/duvar**m **/Wv**, **/WX** veya **/WX-** seçenekleri, select **yapılandırma özellikleri** > **C / C++** > **genel** özellik sayfası.

   - Ayarlamak için **/W0**, **/W1**, **/W2**, **/W3**, **/W4**, veya **/duvar** Seçenekler, değişiklik **uyarı düzeyi** özelliği.

   - Ayarlamak için **/WX** veya **/WX-** seçenekleri değiştirme **uyarıları hata olarak değerlendir** özelliği.

   - İçin sürüm ayarlamak için **/Wv** seçeneği, derleme sürüm numarası girin **uyarı sürüm** özelliği.

1. Ayarlamak için **/wd** veya **/we** seçenekleri, select **yapılandırma özellikleri** > **C/C++**  >   **Gelişmiş** özellik sayfası.

   - Ayarlamak için **/wd** seçeneği için **belirli uyarıları devre dışı** özelliği aşağı denetimini bırakın ve ardından **Düzenle**. Düzenleme kutusuna **belirli uyarıları devre dışı** iletişim kutusunda, uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül kullanarak ayırın (**;**). Örneğin, C4001 ve C4010 devre dışı bırakmak için girin **4001; 4010**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek ve geri dönmek için **özellik sayfaları** iletişim.

   - Ayarlamak için **/we** seçeneğini seçin **kabul belirli uyarılar olarak hataları** özelliği aşağı denetimini bırakın ve ardından **Düzenle**. Düzenleme kutusuna **kabul belirli uyarılar olarak hataları** iletişim kutusunda, uyarı numarasını girin. Birden fazla uyarı girmek için değerleri noktalı virgül kullanarak ayırın (**;**). Örneğin, C4001 ve C4010 hata olarak değerlendirmek için girin **4001; 4010**. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek ve geri dönmek için **özellik sayfaları** iletişim.

1. Ayarlamak için **/wo** seçeneği için **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası. Derleyici seçeneği girin **ek seçenekler** kutusu.

1. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-the-compiler-option-programmatically"></a>Derleyici seçeneği programlı olarak ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>, ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)  
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)  
