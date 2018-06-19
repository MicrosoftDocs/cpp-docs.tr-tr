---
title: -GX (özel durum işlemeyi etkinleştir) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ee2d3d31a9f091e6aa3fbed39f702471047a01dd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376721"
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
 [/EH (Özel Durum İşleme Modeli)](../../build/reference/eh-exception-handling-model.md)