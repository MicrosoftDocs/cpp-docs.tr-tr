---
title: -arch (ARM) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a411d0c7d07fb7392baaaa4fb8a8377fcb36598
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369870"
---
# <a name="arch-arm"></a>/arch (ARM)
ARM üzerinde kod oluşturma için Mimari belirtir. Ayrıca bkz. [/(x86) arch](../../build/reference/arch-x86.md) ve [/(x64) arch](../../build/reference/arch-x64.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## <a name="arguments"></a>Arguments  
 **/arch:ARMv7VE**  
 ARMv7VE sanallaştırma uzantıları yönergeleri kullanımını etkinleştirir.  
  
 **/arch:VFPv4**  
 ARM VFPv4 yönergeleri kullanımını etkinleştirir. Bu seçenek belirtilmezse, VFPv3 varsayılandır.  
  
## <a name="remarks"></a>Açıklamalar  
 `_M_ARM_FP` Makrosu (için yalnızca ARM) gösterir, varsa, **/arch** derleyici seçeneği kullanıldı. Daha fazla bilgi için bkz: [önceden tanımlanmış makrolar](../../preprocessor/predefined-macros.md).  
  
 Kullandığınızda [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derlemek için **/arch** kod oluşturma için yönetilen işlevler üzerinde etkisi yoktur. **/ arch** etkiler kod oluşturmayı yerel işlevler için yalnızca.  
  
### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Visual Studio'da /arch:ARMv7VE veya /arch:VFPv4 derleyici seçeneği ayarlamak için  
  
1.  Açık **özellik sayfaları** projesi için iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  İçinde **ek seçenekler** kutusunda, eklemek `/arch:ARMv7VE` veya `/arch:VFPv4`.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ arch (en düşük CPU Mimarisi)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)