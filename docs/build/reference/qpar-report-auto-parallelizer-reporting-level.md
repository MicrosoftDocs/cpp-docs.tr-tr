---
title: -Qpar-rapor (otomatik paralel hale getirici raporlama düzeyi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 562673b9-02da-4bf8-bb64-70bc25ef4651
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a9db6d02b9233c51a49cf506a664c9be0f821e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376020"
---
# <a name="qpar-report-auto-parallelizer-reporting-level"></a>/Qpar-rapor (Otomatik Paralel Hale Getirici Raporlama Düzeyi)
Derleyicinin raporlama özelliğini etkinleştirir [otomatik paralel hale getirici](../../parallel/auto-parallelization-and-auto-vectorization.md) ve derleme sırasında bilgilendirici iletileri çıktı düzeyini belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Qpar-report:{1}{2}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **/ Qpar-Rapor: 1**  
 Bir bilgi iletisidir paralel birkaç ölçeklendirin döngüler için çıkarır.  
  
 **/ Qpar-Rapor: 2**  
 Bir bilgilendirme iletisi paralel birkaç ölçeklendirin döngüler ve ayrıca, neden kodu ile birlikte paralel birkaç ölçeklendirin değil döngüler çıkarır.  
  
 Stdout bildirilen iletileri. Bildirilen hiçbir bilgilendirici iletileri, ardından hiçbir döngüler kodunu içerir ya da raporlama düzeyi değil paralel birkaç ölçeklendirin rapor döngüler ayarlanmadı. Neden kodları ve iletileri hakkında daha fazla bilgi için bkz: [vektör yapıcı ve paralel hale getirici iletileri](../../error-messages/tool-errors/vectorizer-and-parallelizer-messages.md).  
  
### <a name="to-set-the-qpar-report-compiler-option-in-visual-studio"></a>Visual Studio'da /Qpar-report derleyici seçeneği ayarlamak için  
  
1.  İçinde **Çözüm Gezgini**, proje için kısayol menüsünü açın ve ardından **özellikleri**.  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda **C/C++** seçin **komut satırı**.  
  
3.  İçinde **ek seçenekler** kutusuna `/Qpar-report:1` veya `/Qpar-report:2`.  
  
### <a name="to-set-the-qpar-report-compiler-option-programmatically"></a>/Qpar-report derleyici seçeneği programlı olarak ayarlamak için  
  
-   Aşağıdaki kod örneğinde kullanmak <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/Q Seçenekler (düşük düzey işlemler)](../../build/reference/q-options-low-level-operations.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yerel kodda paralel programlama](http://go.microsoft.com/fwlink/p/?linkid=263662)