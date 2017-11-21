---
title: "-Qvec-report (otomatik vektör hale getirici raporlama düzeyi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4778c9a3-0692-4085-9b05-1bfeadf4c74a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e0df8e487f2f79029c73adfbf44cb3873bcfcaa3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="qvec-report-auto-vectorizer-reporting-level"></a>/Qvec-report (Otomatik Vektör Hale Getirici Raporlama Düzeyi)
Derleyici raporlama özelliğini etkinleştirir [otomatik vektör hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) ve derleme sırasında bilgilendirici iletileri çıktı düzeyini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qvec-report:{1}{2}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ Qvec-report: 1**  
 Bir bilgi iletisidir vectorized döngüler için çıkarır.  
  
 **/ Qvec-report: 2**  
 Bir bilgilendirme iletisi, neden kodu ile birlikte vectorized değil döngüler ve vectorized döngüler için çıkarır.  
  
 Neden kodları ve iletileri hakkında daha fazla bilgi için bkz: [vektör yapıcı ve paralel hale getirici iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qvec-report-compiler-option-in-visual-studio"></a>Visual Studio'da /Qvec-report derleyici seçeneği ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda **C/C++**seçin **komut satırı**.  
  
3.  İçinde **ek seçenekler** kutusuna `/Qvec-report:1` veya `/Qvec-report:2`.  
  
### <a name="to-set-the-qvec-report-compiler-option-programmatically"></a>/Qvec-report derleyici seçeneği programlı olarak ayarlamak için  
  
-   Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/?LinkId=263662)