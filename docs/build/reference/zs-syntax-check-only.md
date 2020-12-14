---
description: Şu konuda daha fazla bilgi edinin:/ZS (yalnızca sözdizimi denetimi)
title: /Zs (Yalnızca Sözdizimi Denetimi)
ms.date: 11/04/2016
f1_keywords:
- /zs
helpviewer_keywords:
- -Zs compiler option [C++]
- Syntax Check Only compiler option
- Zs compiler option
- /Zs compiler option [C++]
ms.assetid: b4b41e6a-3f41-4d09-9cb6-fde5aa2cfecf
ms.openlocfilehash: a4f5e2227104003a637db1d921fd959ea0a11ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224302"
---
# <a name="zs-syntax-check-only"></a>/Zs (Yalnızca Sözdizimi Denetimi)

Derleyiciye yalnızca komut satırındaki kaynak dosyaların söz dizimini denetlemesini söyler.

## <a name="syntax"></a>Syntax

```
/Zs
```

## <a name="remarks"></a>Açıklamalar

Bu seçenek kullanılırken, çıkış dosyası oluşturulmaz ve standart çıktıya hata iletileri yazılır.

**/ZS** seçeneği, bir kaynak dosyayı derleyip paylaşmadan önce sözdizimi hataları bulmak ve düzeltmek için hızlı bir yol sağlar.

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
