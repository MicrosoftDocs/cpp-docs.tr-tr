---
title: -Qsafe_fp_loads | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 2b2ce52d-ba57-4bd3-a739-47a7f8bfaba9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a9e572c8a4d353aaee4e82e8c7bdc3f719475c03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="qsafefploads"></a>/Qsafe_fp_loads
Kayan nokta değerlerini tamsayı taşıma yönergeleri gerektirir ve belirli kayan nokta yük iyileştirmeleri devre dışı bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qsafe_fp_loads  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ Qsafe_fp_loads** yalnızca derleyicileri kullanılabilir x86 hedef; x64 veya ARM hedef derleyicileri içinde kullanılabilir değil.  
  
 **/ Qsafe_fp_loads** tamsayı taşıma yönergeleri kayan nokta taşıma yönergeler yerine bellek ve MMX arasında veri taşımak için kullanılacak derleyici zorlar kaydeder. Bu seçenek ayrıca kayıt yük iyileştirme değeri bir özel durum yüküne neden olabilir, birden çok denetim yollarında yüklenebilir kayan nokta değerleri için devre dışı bırakır — Örneğin, bir NaN değeri.  
  
 Bu seçenek tarafından geçersiz kılınır [/fp: dışında](../../build/reference/fp-specify-floating-point-behavior.md). **/ Qsafe_fp_loads** tarafından belirtilen derleyici davranışı kümesini belirtir **/fp: dışında**.  
  
 **/ Qsafe_fp_loads** uyumlu değil. [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) ve [/fp:fast](../../build/reference/fp-specify-floating-point-behavior.md). Kayan nokta derleyici seçenekleri hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)