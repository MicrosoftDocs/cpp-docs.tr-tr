---
description: Daha fazla bilgi edinin:/doc (Işlem belgeleri açıklamaları) (C/C++)
title: /doc (İşlem Belgeleri Açıklamaları) (C/C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
ms.openlocfilehash: ed811edff544c4b5b28baa67ed216fa09ea51092
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192882"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (İşlem Belgeleri Açıklamaları) (C/C++)

Derleyicinin, kaynak kodu dosyalarındaki belge açıklamalarını işlemesini ve belge açıklamalarını içeren her kaynak kodu dosyası için bir. xdc dosyası oluşturmasını sağlar.

## <a name="syntax"></a>Syntax

> **/doc**[*ad*]

## <a name="arguments"></a>Arguments

*ada*<br/>
Derleyicinin oluşturmayacak. xdc dosyasının adı. Yalnızca bir. cpp dosyası derlemede geçirildiğinde geçerlidir.

## <a name="remarks"></a>Açıklamalar

. Xdc dosyaları xdcmake.exe bir. xml dosyasına işlenir. Daha fazla bilgi için bkz. [XDCMake başvurusu](xdcmake-reference.md).

Kaynak kodu dosyalarınıza belge açıklamaları ekleyebilirsiniz. Daha fazla bilgi için bkz. [belge açıklamaları Için önerilen Etiketler](recommended-tags-for-documentation-comments-visual-cpp.md).

Oluşturulan. xml dosyasını IntelliSense ile kullanmak için,. xml dosyasının adını, desteklemek istediğiniz derleme ile aynı ve. xml dosyasını, derlemeyle aynı dizinde olacak şekilde oluşturun. Visual Studio projesinde derlemeye başvuruluyorsa. xml dosyası da bulunur. Daha fazla bilgi için bkz. [IntelliSense kullanma](/visualstudio/ide/using-intellisense) ve [XML kodu açıklamaları sağlama](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **çıkış dosyaları** özellik sayfasını seçin.

1. **XML belgesi dosyalarını oluştur** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici Command-Line sözdizimi](compiler-command-line-syntax.md)
