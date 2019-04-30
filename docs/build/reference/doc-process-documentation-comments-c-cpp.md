---
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
ms.openlocfilehash: 90f63a972245114424b64d4131420dcb4e1e925a
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64342918"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (İşlem Belgeleri Açıklamaları) (C/C++)

Derleyicinin işlem belgeleri açıklamaları için kaynak kodu dosyalarında ve belge açıklamaları olan her kaynak kodu dosyası için bir .xdc dosyasını oluşturmak için neden olur.

## <a name="syntax"></a>Sözdizimi

> **/ doc**[*adı*]

## <a name="arguments"></a>Arguments

*Adı*<br/>
Derleyici oluşturacak .xdc dosyasının adı. Yalnızca bir .cpp dosyası derlemede geçirildiğinde geçerlidir.

## <a name="remarks"></a>Açıklamalar

.Xdc dosyalarının bir .xml dosyasına xdcmake.exe'yi ile işlenir. Daha fazla bilgi için [XDCMake başvurusu](xdcmake-reference.md).

Belge açıklamaları için kaynak kod dosyalarınızı ekleyebilirsiniz. Daha fazla bilgi için [belge açıklamaları için önerilen etiketler](recommended-tags-for-documentation-comments-visual-cpp.md).

IntelliSense ile oluşturulan .xml dosyasını kullanmak için destek ve .xml dosyasını yerleştirmek istediğiniz derleme ile aynı derleme olarak aynı dizinde olduğu .xml dosyasının dosya adını olun. Visual Studio projesinde derlemeye başvurulduğundan, .xml dosyasını da bulunur. Daha fazla bilgi için [IntelliSense kullanarak](/visualstudio/ide/using-intellisense) ve [XML kodu açıklamalarını sağlama](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Çıkış dosyalarını** özellik sayfası.

1. Değiştirme **XML belge dosyaları oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
