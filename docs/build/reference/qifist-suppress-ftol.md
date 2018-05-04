---
title: -Qıfist (_ftol bastırmak) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /qifist
dev_langs:
- C++
helpviewer_keywords:
- QIfist compiler option [C++]
- -QIfist compiler option [C++]
- /QIfist compiler option [C++]
ms.assetid: 1afd32a5-f658-4b66-85f4-e0ce4cb955bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77ec65e330cebb1de718330ba129e960383b31c6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="qifist-suppress-ftol"></a>/QIfist (Suppress _ftol)
Kullanım dışı. Yardımcı işlevi çağrısı bastırır `_ftol` bir kayan nokta türüne dönüştürme tamsayı türü için ne zaman gereklidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/QIfist  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  **/ Qıfist** yalnızca kullanılabilir x86; hedefleme derleyici Bu derleyici seçeneği hedefleme derleyicileri kullanılamıyor [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] orARM.  
  
 Kayan nokta türünden tam sayı türüne dönüştürme yanı sıra `_ftol` işlevi sağlar (FPU) kayan nokta biriminin yuvarlama modu sıfır (kesme), BITS 10 ve 11 denetim word'ün ayarlayarak. Bu, bir kayan nokta türünden bir tam sayı türüne dönüştürme (sayının kesirli kısmı atılır) ANSI C standardı tarafından açıklanan oluştuğunu garanti eder. Kullanırken **/QIfist**, artık bu garantisi uygular. Yuvarlama modu dört biri Intel başvuru kılavuzlarına anlatıldığı şekilde olacaktır:  
  
-   Yakın (rakamdan doğru equidistant varsa) yuvarlar  
  
-   Negatif sonsuz doğru yuvarlar  
  
-   Pozitif sonsuzluk doğru yuvarlar  
  
-   Sıfıra doğru yuvarlar  
  
 Kullanabileceğiniz [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) FPU yuvarlama davranışını değiştirmek için C çalışma zamanı işlevi. "Yuvarlak doğru en yakın." yuvarlama modu FPU, varsayılan değer Kullanarak **/QIfist** uygulamanızın ancak değil riski olmadan performansı artırabilir. İle koduna bağlıdır bağlı olan yerleşik önce modları yuvarlama hassas kodunuzu bölümlerini sınamanız gerekir **/QIfist** üretim ortamlarında.  
  
 [/ arch (x86)](../../build/reference/arch-x86.md) ve **/QIfist** aynı derlenecek üzerinde kullanılamaz.  
  
> [!NOTE]
>  **/ Qıfist** olan yürürlükte varsayılan yuvarlama de etkiler kayan nokta kayan için BITS olduğundan göstermiyor yuvarlama (her hesaplamasından sonraki oluştuğu), C-style (sıfır doğru) yuvarlama bayrakları ayarladığınızda, kayan nokta şekilde hesaplamaları farklı olabilir. **/ Qıfist** kodunuzu kayan noktalı sayının kesirli kısmını kesilmesiyle, beklenen davranışı bağımlıysa kullanılmamalıdır. Emin değilseniz, kullanmayın **/QIfist**.  
  
 **/QIfist** seçeneği Visual Studio 2005'ten başlayarak kullanım dışıdır. Derleyici önemli geliştirmeler float int dönüştürme hızını yaptı. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)