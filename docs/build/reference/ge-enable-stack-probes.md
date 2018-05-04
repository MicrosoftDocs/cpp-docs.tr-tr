---
title: -Ge (yığın yoklamalarını etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ge
dev_langs:
- C++
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce8b049426eb403e4bc41e842fe1ff2db1617dfc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ge-enable-stack-probes"></a>/Ge (Yığın Yoklamalarını Etkinleştir)
Yığın yoklamalarını yerel değişkenler için depolama gerektiren her işlev çağrısı için etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Ge  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu düzenek, yığın araştırma işlevselliğini yeniden yararlıdır. Kullanmanız önerilir [/Gh (_penter kanca işlevini etkinleştir)](../../build/reference/gh-enable-penter-hook-function.md) yığın araştırma yeniden yazma işlemi yerine.  
  
 [/GS (Denetim yığını denetleme çağrı)](../../build/reference/gs-control-stack-checking-calls.md) aynı etkiye sahiptir.  
  
 **/Ge** olduğu; Visual Studio 2005'te sürümünden itibaren kullanımdan kaldırılmıştır derleyici otomatik olarak yığın denetimi oluşturur. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** içinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)