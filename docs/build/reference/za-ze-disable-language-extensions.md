---
title: -Za, - Ze (dil uzantılarını devre dışı bırak) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
dev_langs:
- C++
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2949a3d60af6d9058f02d12aac1fd86dead5affa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="za-ze-disable-language-extensions"></a>/Za, /Ze (Dil Uzantılarını Devre Dışı Bırak)
**/Za** derleyici seçeneği ANSI C89 veya ISO C ++ 11 ile uyumlu olmayan dil yapıları için bir hata gösterir. **/Ze** varsayılan olarak etkindir, derleyici seçeneği Microsoft uzantıları sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Za  
/Ze  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  **/Ze** davranışını varsayılan olarak açık olduğundan seçeneği kullanım dışıdır. Şunu kullanmanızı öneririz [/Zc (Uyumluluk)](../../build/reference/zc-conformance.md) belirli bir dil uzantısı özellikleri denetlemek için derleyici seçenekleri. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** bölümüne [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Derleyici ANSI C89, ISO C99 veya ISO C++ standartlarını belirtilenler dışında birçok özellik sunar. Bu özellikler, topluca C ve C++ için Microsoft uzantıları olarak bilinir. Varsayılan olarak kullanılabilir ve kullanılamıyorsa bu uzantıları ne zaman **/Za** seçeneği belirtildi. Belirli uzantıları hakkında daha fazla bilgi için bkz: [C ve C++ için Microsoft Extensions](../../build/reference/microsoft-extensions-to-c-and-cpp.md).  
  
 Belirterek dil uzantılarını devre dışı öneririz **/Za** programınızı diğer ortamlara bağlantı noktası planlıyorsanız seçeneği. Zaman **/Za** belirtilirse, derleyici değerlendirir basit tanımlayıcıları olarak anahtar sözcükler genişletilmiş Microsoft, diğer Microsoft uzantıları devre dışı bırakır ve otomatik olarak tanımlayan `__STDC__` C programları için önceden tanımlanmış makrosu.  
  
 İle kullanılan diğer derleyici seçenekleri **/Za** nasıl derleyici standartlara uyum sağlar etkileyebilir. Örneğin, **/Za** ve [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md) uymuyor kayan nokta türü yükseltme davranışındaki ISO C99 veya C ++ 11 standartları neden olabilir.  
  
 Belirli standartlarla davranış ayarları belirtmek için daha fazla yol için bkz: [/Zc](../../build/reference/zc-conformance.md) derleyici seçeneği.  
  
 Uyumluluk sorunları hakkında daha fazla bilgi için [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)], bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti Bölmesi'nde seçin **yapılandırma özellikleri**, **C/C++**, **dil**.  
  
3.  Değiştirme **dil uzantılarını devre dışı** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)