---
title: "-Oi (iç işlevler üret) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs:
- C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0a24830dbc67466e52f3f3c488dda7ac5b4778d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (İç İşlevler Üret)
Uygulamanızı yardımcı iç veya aksi halde özel formlarla işlevinin bazı işlevi çağırır değiştirir daha hızlı çalışır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Oi[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşlev çağrıları yükü gerekmez ancak oluşturulan ek kod nedeniyle daha büyük olduğundan iç işlevler kullanan programlar daha hızlıdır.  
  
 Bkz: [iç](../../preprocessor/intrinsic.md) işlevler üzerinde iç forms sahip daha fazla bilgi için.  
  
 **/Oi** iç bilgileri ile; bazı işlev çağrıları değiştirmek için yalnızca bir istek derleyici derleyici işlevi çağırma (ve işlev çağrısı bir iç yerini almak için değil) daha iyi performans verecekse.  
  
 **x86 belirli**  
  
 İç kayan nokta işlevleri değil giriş değerleri üzerinde herhangi bir özel denetim gerçekleştirmek ve bu nedenle giriş kısıtlı aralıklarına çalışır ve farklı bir özel durum işleme ve aynı ada sahip kitaplık yordamları sınır koşullarından sahip. True iç formları kullanarak gelir kaybına IEEE özel durum işleme ve kaybı `_matherr` ve `errno` işlevselliği; ikinci ANSI uyumluluğu kaybı anlamına gelir. Ancak, iç forms floating point yoğunluklu programları önemli ölçüde hızlandırılabilir ve birçok programlar için çok az pratik değerini uygunluk sorunlardır.  
  
 Kullanabileceğiniz [Za](../../build/reference/za-ze-disable-language-extensions.md) true iç kayan nokta seçenekleri nesil geçersiz kılmak için derleyici seçeneği. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.  
  
 **Son x86 belirli**  
  
 Aynı zamanda [iç](../../preprocessor/intrinsic.md) iç işlevler oluşturmak için veya [işlevi (C/C++)](../../preprocessor/function-c-cpp.md) açıkça bir işlev çağrısı zorlamak için.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **en iyi duruma getirme** özellik sayfası.  
  
4.  Değiştirme **etkinleştirmek iç işlevler** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/O seçenekler (kodu İyileştir)](../../build/reference/o-options-optimize-code.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Derleyici İç Bilgileri](../../intrinsics/compiler-intrinsics.md)