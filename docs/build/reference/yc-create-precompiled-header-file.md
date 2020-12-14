---
description: Daha fazla bilgi edinin:/Yc (önceden derlenmiş üst bilgi dosyası oluştur)
title: /Yc (Önceden Derlenmiş Başlık Dosyası Oluştur)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.UsePrecompiledHeader
- /yc
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderThrough
- VC.Project.VCCLWCECompilerTool.UsePrecompiledHeader
- VC.Project.VCCLCompilerTool.PrecompiledHeaderThrough
helpviewer_keywords:
- precompiled header files, creating
- PCH files, creating
- .pch files, creating
- -Yc compiler option [C++]
- /Yc compiler option [C++]
- Yc compiler option [C++]
ms.assetid: 47c2e555-b4f5-46e6-906e-ab5cf21f0678
ms.openlocfilehash: eba045c3148d0caceee3ca6f9d5352ea61726757
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243659"
---
# <a name="yc-create-precompiled-header-file"></a>/Yc (Önceden Derlenmiş Başlık Dosyası Oluştur)

Derleyiciye belirli bir noktada derlemenin durumunu temsil eden önceden derlenmiş üst bilgi (. pch) dosyası oluşturmasını söyler.

## <a name="syntax"></a>Syntax

> __/YC__\
> __/Rivc__*dosya adı*

## <a name="arguments"></a>Arguments

*filename*<br/>
Üst bilgi (. h) dosyasını belirtir. Bu bağımsız değişken kullanıldığında, derleyici. h dosyasını ve dahil olmak üzere tüm kodu derler.

## <a name="remarks"></a>Açıklamalar

**/Rivc** bir bağımsız değişken olmadan belirtildiğinde, derleyici tüm kodu temel kaynak dosyanın sonuna kadar veya bir [hdrstop](../../preprocessor/hdrstop.md) yönergesinin gerçekleştiği taban dosyasındaki noktaya derler. **Hdrstop** pragmasını veya **/FP** seçeneğini kullanarak farklı bir dosya adı belirtmediğiniz sürece, elde edilen. pch dosyası temel kaynak dosyanız ile aynı temel ada sahiptir.

Önceden derlenmiş kod, **/i** ve. pch uzantısıyla belirtilen dosyanın temel adından oluşturulmuş bir ada sahip bir dosyaya kaydedilir. [/FP (adı) da kullanabilirsiniz. PCH dosyası)](fp-name-dot-pch-file.md) seçeneği, ön derlenmiş üstbilgi dosyası için bir ad belirtmek üzere.

__/YC__*dosya adı* kullanırsanız, derleyici tüm kodu, [/yu (önceden derlenmiş üst bilgi dosyası kullan)](yu-use-precompiled-header-file.md) seçeneğiyle birlikte, sonraki kullanım için, belirtilen dosya dahil olmak üzere derler.

__/Yıc__*filename* ve __/yu__*Dosya* adı seçenekleri aynı komut satırında gerçekleşse ve her iki başvuru ya da bir deyişle, aynı dosya adı __/rivc__*filename* öncelik kazanır. Bu özellik, makefiles 'ın yazılmasını basitleştirir.

Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz.

- [/Y (önceden derlenmiş üst bilgiler)](y-precompiled-headers.md)

- [Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Bir. cpp dosyası seçin. . Cpp dosyası, ön derlenmiş üstbilgi bilgilerini içeren. h dosyasını #include olmalıdır. Projenin **/Yıc** ayarı dosya düzeyinde geçersiz kılınabilir.

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **C/C++**, **önceden derlenmiş üstbilgiler** özellik sayfasını açın.

1. **Ön derlenmiş üstbilgi** özelliğini değiştirin.

1. Dosya adını ayarlamak için **ön derlenmiş üstbilgi dosyası** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderThrough%2A> <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UsePrecompiledHeader%2A> . ve.

## <a name="example"></a>Örnek

Aşağıdaki kodu inceleyin:

```cpp
// prog.cpp
// compile with: cl /c /Ycmyapp.h prog.cpp
#include <afxwin.h>   // Include header for class library
#include "resource.h" // Include resource definitions
#include "myapp.h"    // Include information specific to this app
// ...
```

Bu kod komutla derlendiğinde `CL /YcMYAPP.H PROG.CPP` , derleyici, MyApp. pch adlı önceden derlenmiş bir üstbilgi dosyasında AFXWIN. h, Resource. h ve MyApp. h için tüm ön işleme kaydeder.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)<br/>
[Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)
