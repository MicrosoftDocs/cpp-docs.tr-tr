---
title: -Qpar (otomatik paralel hale getirici) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs:
- C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 073c906e7ecdfcf933e4b91cbcf8d6a77324df76
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (Otomatik Paralel Hale Getirici)
Etkinleştirir [otomatik paralel hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) otomatik olarak kodunuzda döngüler paralel hale derleyici özelliğidir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleyici otomatik olarak kod Döngülerde parallelizes, hesaplama birden çok işlemci çekirdeği arasında yayar. Bunu yapmak için uygundur ve o paralelleştirme performansı Derleyici yalnızca belirlerse, döngü paralel birkaç ölçeklendirin.  
  
 `#pragma loop()` Yönergeleri belirli döngüler paralel hale iyileştirici yardımcı olmak için kullanılabilir. Daha fazla bilgi için bkz: [döngü](../../preprocessor/loop.md).  
  
 Otomatik paralel hale getirici için çıktı iletileri etkinleştirme hakkında daha fazla bilgi için bkz: [/Qpar-report (otomatik paralel hale getirici raporlama düzeyi)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md).  
  
### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio'da /Qpar derleyici seçeneği ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda **C/C++**seçin **komut satırı**.  
  
3.  İçinde **ek seçenekler** kutusuna `/Qpar`.  
  
### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar derleyici seçeneği programlı olarak ayarlamak için  
  
-   Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [/ Qpar (otomatik paralel hale getirici düzeyi raporlama) raporu](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [#pragma loop()](../../preprocessor/loop.md)   
 [Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=263662)