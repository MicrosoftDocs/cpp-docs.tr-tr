---
title: -(x64) arch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27a453601988c22ed03ae9cb267480d88d6a1cc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="arch-x64"></a>/arch (x64)
X64 üzerinde kod oluşturma için Mimari belirtir. Ayrıca bkz. [/(x86) arch](../../build/reference/arch-x86.md) ve [/arch (ARM)](../../build/reference/arch-arm.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/arch:[AVX|AVX2]  
```  
  
## <a name="arguments"></a>Arguments  
 **/arch:AVX**  
 Intel Gelişmiş vektör uzantıları yönergeleri kullanımını etkinleştirir.  
  
 **/arch:AVX2**  
 Intel Gelişmiş vektör Extensions 2 yönergeleri kullanımını etkinleştirir.  
  
## <a name="remarks"></a>Açıklamalar  
 **/ arch** etkiler kod oluşturmayı yerel işlevler için yalnızca. Kullandığınızda [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur.  
  
 `__AVX__` Önişlemci sembolü tanımlanmış zaman **/arch:AVX** derleyici seçeneği belirtildi. `__AVX2__` Önişlemci sembolü tanımlanmış zaman **/arch:AVX2** derleyici seçeneği belirtildi. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md). **/Arch:AVX2** seçeneği, Visual Studio 2013 güncelleştirme 2 ', sürüm 12.0.34567.1 sunulmuştur.  
  
### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>Visual Studio'da /arch:AVX veya /arch:AVX2 derleyici seçeneği ayarlamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **yapılandırma özellikleri**, **C/C++** klasör.  
  
3.  Seçin **kod oluşturma** özellik sayfası.  
  
4.  İçinde **etkinleştirmek gelişmiş yönerge kümesi** açılır kutusunda, seçin **Gelişmiş vektör Uzantıları (/ arch: AVX)** veya **Gelişmiş vektör uzantıları 2 (/ arch: AVX2)**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)