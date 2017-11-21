---
title: "-w,-W0,-W1, - W2,-W3, - W4,-w1,-w2,-w3,-w4,-Wall, -wd,-biz -wo, -Wv, - WX (uyarı düzeyi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
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
dev_langs: C++
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
ms.assetid: d6bc7bf5-c754-4879-909c-8e3a67e2629f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5504c3d726feda499fb4b63f68d7784291308694
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="w-w0-w1-w2-w3-w4-w1-w2-w3-w4-wall-wd-we-wo-wv-wx-warning-level"></a>/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, wln, /wd, / biz, /wo, /Wv, /WX (uyarı düzeyi)
Derleyici belirli bir derleme için uyarıları nasıl oluşturur belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/w  
/W0  
/W1  
/W2  
/W3  
/W4  
/Wall  
/Wv[<version>]  
/WX  
/w1<warning>   
/w2<warning>   
/w3<warning>   
/w4<warning>   
/wd<warning>   
/we<warning>   
/wo<warning>  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Hangi Derleyici uyarılarını görüntüleme ve tüm derleme için uyarı davranışı uyarı seçeneklerini belirtin.  
  
 Uyarı seçenekleri ve ilişkili bağımsız değişkenler aşağıdaki tabloda açıklanmıştır:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**/w**|Tüm derleyici uyarıları bastırır.|  
|**/ W0**<br /><br /> **/ W1**<br /><br /> **/ W2**<br /><br /> **/ W3**<br /><br /> **/ W4**|Derleyici tarafından üretilen uyarılar düzeyini belirtir. Geçerli uyarı düzeylerini aralığı 0'dan 4:<br /><br /> -   **/ W0** tüm uyarıları bastırır.<br />-   **/ W1** düzey 1 (ciddi) uyarıları görüntüler. **/ W1** varsayılan ayardır.<br />-   **/ W2** düzey 1 ve Düzey 2 (Önemli) uyarıları görüntüler.<br />-   **/ W3** görüntüler düzey 1, Düzey 2 ve 3 (üretim kalite) uyarıları düzeyi.<br />-   **/ W4** düzey 1, Düzey 2 ve 3 uyarıları düzey görüntüler ve tüm varsayılan olarak kapalı değil 4 (bilgilendirme) uyarıları düzeyi. Yalnızca tüy benzeri uyarıları sağlamak için bu seçeneği kullanmanızı öneririz. Ancak, yeni bir proje için en iyi yöntem olabilir **/W4** tüm derlemeleri içinde; bu en az olası Bul sabit kod kusurları güvence altına alır.|  
|**/ Wall**|Tarafından görüntülenen tüm uyarıları görüntüler **/W4** ve diğer tüm uyarıları, **/W4** içermemesi — Örneğin, varsayılan olarak kapalı olan uyarılar. Daha fazla bilgi için bkz: [derleyici uyarıları emin olduğunuz tarafından varsayılan olarak kapalıdır](../../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|**/Wv**`:version`|Derleyici sürümler daha yeni sürümünde sunulan uyarıları bastırma `version`. Uyarılar olmadan derleyici daha eski bir sürümünü kullanırken derlenmiş kod yeni uyarılar olup olmadığını belirlemek ve bunları düzeltme sırasında geçici olarak, yapı işleminden yeni uyarıları gizlemek için bu seçeneği kullanabilirsiniz. İsteğe bağlı bir parametre `version` formundadır `nn`[.`mm` [. `bbbbb`]] burada `nn` ana sürüm numarası `mm` isteğe bağlı ikincil sürüm numarası ve `bbbbb` derleyici isteğe bağlı yapı numarasıdır. Örneğin, `/Wv:17.00.00000` Visual C++ 2012 ve daha sonra kullanılmaya uyarıları gizlemek için. Varsayılan olarak, **/Wv** geçerli derleyici sürüm numarasını ve hiçbir uyarılar gizlenir kullanır. Hakkında uyarı derleyici sürümü tarafından gizlenir daha fazla bilgi için bkz [derleyici uyarıları derleyici sürümüne göre](../..//error-messages/compiler-warnings/compiler-warnings-by-compiler-version.md).|  
|**/WX**|Tüm derleyici uyarıları hata olarak değerlendirir. Yeni bir proje için en iyi yöntem olabilir **/WX** tüm derlemeleri içinde; tüm uyarıları çözümleme en az olası Bul sabit kod kusurları sağlar.<br /><br /> Bağlayıcı ayrıca sahip bir **/WX** seçeneği. Daha fazla bilgi için bkz: [/WX (Bağlayıcı uyarıları hata olarak değerlendir)](../../build/reference/wx-treat-linker-warnings-as-errors.md).|  
|**/W1**`n`<br /><br /> **/w2**`n`<br /><br /> **/W3**`n`<br /><br /> **/W4**`n`|Uyarı düzeyi tarafından belirtilen uyarı sayısını ayarlar `n`. Bu, belirli bir uyarı düzeyi olarak ayarlandığında bu uyarı için derleyici davranışı değiştirmenize olanak sağlar. Visual Studio tarafından sağlanan olanları varsayılan yerine uyarılar için kendi kodlama standartları zorlamak için bu seçenekleri diğer uyarı seçenekleri ile birlikte kullanabilirsiniz.<br /><br /> Örneğin, `/w34326` C4326 düzey 1 yerine Düzey 3 uyarı oluşturulmasına neden olur. Her ikisini de kullanarak derleme yaparsanız `/w34326` seçeneği ve `/W2` C4326 oluşturulmuyor uyarı seçeneği.|  
|**/WD**`n`|Tarafından belirtilen derleyici uyarısı bastırır `n`.<br /><br /> Örneğin, `/wd4326` C4326 uyarı derleyici gizler.|  
|**/We**`n`|Tarafından belirtilen derleyici uyarısı değerlendirir `n` hata olarak.<br /><br /> Örneğin, `/we4326` uyarı numarası hata olarak derleyici tarafından kabul edilmesi için C4326 neden olur.|  
|**/Wo**`n`|Tarafından belirtilen diğer bir deyişle derleyici uyarı raporları `n` yalnızca bir kez.<br /><br /> Örneğin, `/wo4326` nedenleri, yalnızca bir kez bildirilecek C4326 uyarı ilk kez karşılaştığından derleyici tarafından.|  
  
 Önceden derlenmiş üst bilgi kullanarak oluşturduğunuzda uyarı seçeneklerinden herhangi birini kullanırsanız, [/Yc](../../build/reference/yc-create-precompiled-header-file.md) seçeneğini kullanarak önceden derlenmiş üst bilgi herhangi bir kullanımından [/Yu](../../build/reference/yu-use-precompiled-header-file.md) seçenek etkili olması bu aynı uyarı seçenekleri neden olur yeniden. Önceden derlenmiş üst bilgi komut satırında başka bir uyarı seçeneği kullanılarak ayarlanmış uyarı seçeneklerini geçersiz kılabilirsiniz.  
  
 Kullanabileceğiniz bir [#pragma Uyarısı](../../preprocessor/warning.md) olan uyarı düzeyini denetlemek için yönergesi belirli bir kaynak dosyaları derleme zamanında bildirdi.  
  
 Pragma uyarısı yönergeleri kaynak kodundaki tarafından etkilenmemesini **/w** seçeneği.  
  
 [Hataları belge yapı](../../error-messages/compiler-errors-1/c-cpp-build-errors.md) uyarıları ve uyarı düzeylerini tanımlar ve istediğiniz gibi neden belirli deyimleri derleme değil gösterir.  
  
### <a name="to-set-the-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında derleyici seçeneği ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++**.  
  
3.  Üzerinde **genel** özellik sayfasında, değişiklik **uyarı düzeyi** veya **uyarıları hata olarak değerlendir** özellikleri.  
  
4.  Üzerinde **Gelişmiş** özellik sayfasında, değişiklik **belirli uyarıları devre dışı** özelliği.  
  
5.  Geri kalan seçenekler için üzerinde **komut satırı** özellik sayfasında, derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-the-compiler-option-programmatically"></a>Derleyici seçeneği programlı olarak ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarningLevel%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WarnAsError%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableSpecificWarnings%2A>, ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)