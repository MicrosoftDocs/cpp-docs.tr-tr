---
description: Daha fazla bilgi edinin:/GA (Windows uygulaması için Iyileştir)
title: /GA (Windows Uygulaması için İyileştir)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: f9d65dce26e80b585abc4d67e2eef55f10cb365b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191985"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows Uygulaması için İyileştir)

İş parçacığı yerel depolama (TLS) değişkenlerine erişmek için bir. exe dosyası için daha verimli kod sağlar.

## <a name="syntax"></a>Syntax

```
/GA
```

## <a name="remarks"></a>Açıklamalar

**/Ga** Windows tabanlı bir programda [__declspec (thread)](../../cpp/declspec.md) ile belirtilen verilere erişimi hızlandırır. Bu seçenek ayarlandığında, [__tls_index](/windows/win32/ProcThread/thread-local-storage) makrosunun 0 olduğu varsayılır.

Bir DLL için **/ga** kullanmak, hatalı kod oluşturulmasına neden olabilir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **C/C++** klasörünü tıklatın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. **Ek seçenekler** kutusuna derleyici seçeneğini yazın.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
