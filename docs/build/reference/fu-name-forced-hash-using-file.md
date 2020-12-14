---
description: 'Şu konuda daha fazla bilgi edinin:/FU (Zorlanan #using dosya adı)'
title: '/FU (Zorlanan #using Dosyasını Adlandır)'
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ForcedUsingFiles
- /FU
- VC.Project.VCNMakeTool.ForcedUsingAssemblies
helpviewer_keywords:
- -FU compiler option [C++]
- FU compiler option [C++]
- /FU compiler option [C++]
ms.assetid: 698f8603-457f-435a-baff-5ac9243d6ca1
ms.openlocfilehash: 458369e7ff1322d2d2fa2fb37e8915c5a39c8446
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200383"
---
# <a name="fu-name-forced-using-file"></a>/FU (Zorlanan #using Dosyasını Adlandır)

Kaynak kodundaki [#using yönergesine](../../preprocessor/hash-using-directive-cpp.md) bir dosya adı geçirmek için alternatif olarak kullanabileceğiniz bir derleyici seçeneği.

## <a name="syntax"></a>Syntax

> **/Fu** *dosyası*

## <a name="arguments"></a>Arguments

*dosyasýný*<br/>
Bu derlemede başvurulacak meta veri dosyasını belirtir.

## <a name="remarks"></a>Açıklamalar

/FU anahtarı yalnızca bir dosya adı alır. Birden çok dosya belirtmek için, her biri ile/FU kullanın.

C++/CLı kullanıyorsanız ve [arkadaş derlemeleri](../../dotnet/friend-assemblies-cpp.md) özelliğini kullanmak için meta verilere başvuruyorsa, **/Fu** kullanamazsınız. Kullanarak koddaki meta verilere `#using` (özniteliğiyle birlikte) başvurmanız gerekir `[as friend]` . Friend derlemeleri Visual C++ bileşen uzantıları C++/CX'DE desteklenmez.

Ortak dil çalışma zamanı (CLR) için derleme veya modül oluşturma hakkında daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md). C++/CX ' te nasıl derleme yapılacağı hakkında daha fazla bilgi için bkz. [uygulama ve kitaplık oluşturma](../../cppcx/building-apps-and-libraries-c-cx.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Zorla #using** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedUsingFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Çıktı dosyası (/F) seçenekleri](output-file-f-options.md)<br/>
[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
