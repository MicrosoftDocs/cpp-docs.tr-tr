---
description: Hakkında daha fazla bilgi edinin:/Y-(önceden derlenmiş üst bilgi seçeneklerini yoksay)
title: /Y (Önceden Derlenmiş Başlık Seçeneklerini Yoksay)
ms.date: 11/04/2016
f1_keywords:
- /y-
helpviewer_keywords:
- Y- compiler option [C++]
- -Y- compiler option [C++]
- /Y- compiler option [C++]
ms.assetid: cfaecb36-58db-46b8-b04d-cca6072b1b7a
ms.openlocfilehash: b3d1eb6d404e0463ee547c1905f792b485bf65f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260845"
---
# <a name="y--ignore-precompiled-header-options"></a>/Y (Önceden Derlenmiş Başlık Seçeneklerini Yoksay)

Diğer tüm `/Y` derleyici seçeneklerinin yoksayılmasına neden olur (ve kendisi geçersiz kılınamaz).

## <a name="syntax"></a>Syntax

```
/Y-
```

## <a name="remarks"></a>Açıklamalar

Önceden derlenmiş üstbilgiler hakkında daha fazla bilgi için bkz.

- [/Y (önceden derlenmiş üst bilgiler)](y-precompiled-headers.md)

- [Ön derlenmiş üstbilgi dosyaları](../creating-precompiled-header-files.md)

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
