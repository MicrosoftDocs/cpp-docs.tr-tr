---
title: -Yc (önceden derlenmiş üst bilgi dosyası oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5288e748956a405073697ddd7331a73b95d8650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714252"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (Önceden Derlenmiş Üst Bilgi Dosyası Oluştur)

Derleme belli bir noktadaki durumunu gösteren önceden derlenmiş üst bilgi (.pch) dosyasını oluşturmak için derleyicinin sağlar.

## <a name="syntax"></a>Sözdizimi

> __/Yc__
>  __/Yc__*dosya adı*

## <a name="arguments"></a>Arguments

*Dosya adı*<br/>
Bir üstbilgi (.h) dosyası belirtir. Bu bağımsız değişken kullanıldığında, derleyici ve .h dosyası olan tüm kodu derler.

## <a name="remarks"></a>Açıklamalar

Zaman **/Yc** belirtilen bağımsız değişken derleyici, temel kaynak dosyasının veya temel dosya noktasına kadar tüm kodu derler burada bir [hdrstop](../../preprocessor/hdrstop.md) yönergesi gerçekleşir. Farklı dosya adını kullanarak belirtmediğiniz sürece elde edilen .pch dosyası aynı temel ada, temel kaynak dosyası sahiptir. **hdrstop** pragma veya **/FP** seçeneği.

Önceden derlenmiş kod ile belirtilen dosyanın temel adı oluşturulan bir ada sahip bir dosyaya kaydedilir **/Yc** seçeneği ve .pch uzantısı. Ayrıca [FP (adı. PCH dosyası)](../../build/reference/fp-name-dot-pch-file.md) seçeneği önceden derlenmiş üst bilgi dosyası için bir ad belirtin.

Kullanırsanız __/Yc__*filename*, derleyici ve belirtilen dosya ile kullanmak için olan tüm kodu derler [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md) seçeneği.

Varsa seçenekleri __/Yc__*filename* ve __/Yu__*filename* aynı komut satırında oluşur ve her ikisi de başvuru veya yaptığından, aynı dosya adına __/Yc__*filename* önceliklidir. Bu özellik, derleme görevleri dosyalarını yazımını basitleştirir.

Önceden derlenmiş üst bilgiler hakkında daha fazla bilgi için bkz:

- [/Y (Önceden Derlenmiş Üst Bilgiler)](../../build/reference/y-precompiled-headers.md)

- [Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. .Cpp dosyası seçin. .Cpp dosyası gerekir #include önceden derlenmiş üst bilgileri içerip .h dosyası. Projenin **/Yc** ayarı dosya düzeyinde geçersiz kılınabilir.

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri**, **C/C++**, **önceden derlenmiş üst bilgiler** özellik sayfası.

1. Değiştirme **önceden derlenmiş üst bilgi** özelliği.

1. Dosya adı ayarlamak için değişiklik **önceden derlenmiş üst bilgi dosyası** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A>.

## <a name="example"></a>Örnek

Aşağıdaki kodu göz önünde bulundurun:

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

Bu kod komutu ile derlenmiş zaman `CL /YcMYAPP.H PROG.CPP`, derleyicinin tüm AFXWIN.h, RESOURCE.h, ön işleme kaydeder ve önceden derlenmiş üst bilgi dosyasında MYAPP.h MYAPP.pch çağrılır.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[Önceden Derlenmiş Üst Bilgi Dosyaları Oluşturma](../../build/reference/creating-precompiled-header-files.md)