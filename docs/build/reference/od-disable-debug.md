---
title: "-Od (devre dışı bırak (Hata Ayıkla)) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /od
dev_langs:
- C++
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0956493184f6c2322bc6838049472e90ad0c1985
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="od-disable-debug"></a>/Od (Devre Dışı Bırak (Hata Ayıkla))
Programı tüm iyileştirmeler kapatır ve derleme hızlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Od  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu seçenek varsayılandır. Çünkü **/Od** kodu taşıma bastırır hata ayıklama işlemi basitleştirir. Hata ayıklama için derleyici seçenekleri hakkında daha fazla bilgi için bkz: [/Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **en iyi duruma getirme** özellik sayfası.  
  
4.  Değiştirme **en iyi duruma getirme** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/ Z7, / zi, /zı (hata ayıklama bilgileri biçimi)](../../build/reference/z7-zi-zi-debug-information-format.md)