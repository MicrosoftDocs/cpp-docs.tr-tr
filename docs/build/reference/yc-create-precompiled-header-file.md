---
title: "-Yc (önceden derlenmiş üst bilgi dosyası oluştur) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
dev_langs:
- C++
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 865b5e0fa7039a0b60f524c2f13a367569757d92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (Önceden Derlenmiş Üst Bilgi Dosyası Oluştur)
Belirli bir noktada derleme durumunu temsil eden bir önceden derlenmiş üst bilgi (.pch) dosyası oluşturmak için derleyiciye.  
  
## <a name="syntax"></a>Sözdizimi  
  
> __/Yc__
> __/Yc__*dosya adı*  
  
  
## <a name="arguments"></a>Arguments  
*Dosya adı*  
 Bir başlık (.h) dosyası belirtir. Bu bağımsız değişken kullanıldığında, derleyici ve .h dosyası olan tüm kodu derler.  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman **/Yc** belirtilen bir bağımsız değişken olmadan derleyici derler bitiş temel kaynak dosyasının veya temel dosyanın noktaya kadar tüm kod burada bir [hdrstop](../../preprocessor/hdrstop.md) yönergesi oluşur. Farklı bir dosya adıyla belirtmediğiniz sürece elde edilen .pch dosyası temel kaynak dosyası olarak aynı taban adına sahip **hdrstop** pragma veya **/Fp** seçeneği.  
  
 Önceden derlenmiş kod ile belirtilen dosyayı temel adından oluşturulmuş bir ada sahip bir dosyaya kaydedilir **/Yc** seçeneği ve .pch uzantısı. Aynı zamanda [/Fp (adı. PCH dosyası)](../../build/reference/fp-name-dot-pch-file.md) seçeneği önceden derlenmiş üst bilgi dosyası için bir ad belirtin.  
  
 Kullanırsanız __/Yc__*filename*, derleyici ve ile sonraki kullanım için belirtilen dosya olan tüm kodu derler [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) seçeneği.  
  
 Varsa seçenekleri __/Yc__*filename* ve __/Yu__*filename* aynı komut satırında oluşur ve her ikisi de başvuru veya, aynı dosya adına kapsıyor __/Yc__*filename* önceliklidir. Bu özellik, derleme görevleri dosyaları yazma basitleştirir.  
  
 Önceden derlenmiş üst bilgileri hakkında daha fazla bilgi için bkz:  
  
-   [/Y (önceden derlenmiş başlıklar)](../../build/reference/y-precompiled-headers.md)  
  
-   [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  .Cpp dosyasını seçin. .Cpp dosya # önceden derlenmiş üst bilgileri içeren .h dosyasını include. Projenin **/Yc** ayarı dosya düzeyinde geçersiz.  
  
2.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
3.  Açık **yapılandırma özellikleri**, **C/C++**, **önceden derlenmiş üstbilgiler** özellik sayfası.  
  
4.  Değiştirme **önceden derlenmiş üstbilgi** özelliği.  
  
5.  Dosya adı ayarlamak için değiştirme **önceden derlenmiş üstbilgi dosyası** özelliği.
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod göz önünde bulundurun:  
  
```cpp  
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library  
#include "resource.h" // Include resource definitions  
#include "myapp.h"    // Include information specific to this app  
// ...  
```  
  
Bu kod komutuyla derlenmiş zaman `CL /YcMYAPP.H PROG.CPP`, AFXWIN.h, RESOURCE.h, tüm önişleme derleyici kaydeder ve önceden derlenmiş üstbilgi dosyasında MYAPP.h MYAPP.pch çağrılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md) [önceden derlenmiş üst bilgi dosyaları oluşturma](../../build/reference/creating-precompiled-header-files.md)