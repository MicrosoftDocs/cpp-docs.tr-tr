---
title: "-GX (özel durum işlemeyi etkinleştir) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3013b4233621e63de0230e088dfc10ff65a5705d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="gx-enable-exception-handling"></a>/GX (Özel Durum İşlemeyi Etkinleştir)
Kullanım dışı. Zaman uyumlu özel durum işleme işlevleri varsayımına kullanarak bildirilen kullanarak etkinleştirir `extern "C"` hiçbir zaman bir özel durum.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/GX  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/GX** kullanım dışı bırakılmıştır. Eşdeğer kullanmak [/EHsc](../../build/reference/eh-exception-handling-model.md) bunun yerine seçeneği. Kullanım dışı derleyici seçeneklerinin listesi için bkz: **kullanım dışı ve kaldırılmış derleyici seçenekleri** bölümüne [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
 Varsayılan olarak, **/EHsc**, karşılığıdır **/GX**, Visual Studio geliştirme ortamı kullanarak derlediğinizde etkili olur. Komut satırı araçlarını kullanırken, hiçbir özel durum işleme belirtilir. Bu eşdeğerdir **/GX-**.  
  
 Daha fazla bilgi için bkz: [C++ özel durum işleme](../../cpp/cpp-exception-handling.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti Bölmesi'nde seçin **yapılandırma özellikleri**, **C/C++**, **komut satırı**.  
  
3.  Derleyici seçeneği yazın **ek seçenekler** kutusu.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/EH (özel durum işleme modeli)](../../build/reference/eh-exception-handling-model.md)