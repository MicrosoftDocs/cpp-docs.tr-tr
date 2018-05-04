---
title: -Wp64 (64 Bit taşınabilirlik sorunlarını Algıla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLWCECompilerTool.Detect64BitPortabilityProblems
- VC.Project.VCCLCompilerTool.Detect64BitPortabilityProblems
- /wp64
dev_langs:
- C++
helpviewer_keywords:
- 64-bit compiler [C++], detecting portability problems
- /Wp64 compiler option [C++]
- -Wp64 compiler option [C++]
- Wp64 compiler option [C++]
ms.assetid: 331ae5aa-e627-4d03-8f63-dd2c2d76dadd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 295f2f690cb3c9db17a410cea1f23d04e54b0054
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="wp64-detect-64-bit-portability-issues"></a>/Wp64 (64 Bit Taşınabilirlik Sorunlarını Algıla)

Bu derleyici seçeneği kullanımdan kalkmıştır. Visual Studio 2013 önce Visual Studio sürümlerinde, bu da işaretlenir türleri üzerinde 64 bit taşınabilirlik sorunlarını algılar [__w64](../../cpp/w64.md) anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Wp64  
```  
  
## <a name="remarks"></a>Açıklamalar  

Varsayılan olarak, Visual Studio 2013 önce Visual Studio sürümlerinde **/Wp64** derleyici seçeneği Visual C++ derleyicinin 32-bit x86 derlemeler kapalıdır kod, üzerinde Visual C++ derleyicisi 64-bit, x64 yapılara ve kod.  
  
> [!IMPORTANT]
>  [/Wp64](../../build/reference/wp64-detect-64-bit-portability-issues.md) derleyici seçeneği ve [__w64](../../cpp/w64.md) anahtar sözcüğü Visual Studio 2010 ve Visual Studio 2012'de kullanım dışı bırakılmış ve Visual Studio 2013'te başlangıç desteklenmiyor. Bu anahtarı kullanan bir proje dönüştürürseniz, anahtar dönüştürme sırasında geçirilmez. Visual Studio 2010 veya Visual Studio 2012 bu seçeneği kullanmak için derleyici anahtarı altındaki yazın **ek seçenekler** içinde **komut satırı** proje özelliklerini bölümü. Kullanırsanız **/Wp64** derleyici seçeneği komut satırında derleyici komut satırı uyarısı D9002 verir. Bu seçenek ve anahtar sözcüğü 64 bit taşınabilirlik sorunlarını algılamak için kullanmak yerine, bir 64-bit platformu hedefleyen Visual C++ Derleyici kullanın ve belirtin [/W4](../../build/reference/compiler-option-warning-level.md) seçeneği. Daha fazla bilgi için bkz: [yapılandırma Visual C++ 64-bit, x64 için hedefleri](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
Aşağıdaki türlerde değişkenleri bir 64-bit işletim sisteminde kullanılmakta gibi bir 32 bit işletim sisteminde test edildiğini:  
  
-   int  
  
-   long  
  
-   pointer  
  
 Düzenli olarak 64-bit, x64 derlemeler derleyici kullanarak uygulamanızı derleyin, kod, yalnızca devre dışı bırakabilirsiniz **/Wp64** , 32-bit derlemelerde çünkü 64 bit derleyici tüm sorunları algılar. Hedef Windows 64-bit işletim sistemine hakkında daha fazla bilgi için bkz: [yapılandırma Visual C++ 64-bit, x64 için hedefleri](../../build/configuring-programs-for-64-bit-visual-cpp.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu.  
  
     Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** dahil etmek için kutusunu **/Wp64**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Detect64BitPortabilityProblems%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
[Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
[Visual C++’ı 64 bit, x64 hedefler için yapılandırma](../../build/configuring-programs-for-64-bit-visual-cpp.md)