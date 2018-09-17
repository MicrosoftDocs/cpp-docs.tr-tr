---
title: -doc (işlem belgeleri açıklamaları) (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 488ee353cf245303b5ea73be139a262aea5be49d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706582"
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (İşlem Belgeleri Açıklamaları) (C/C++)

Derleyicinin işlem belgeleri açıklamaları için kaynak kodu dosyalarında ve belge açıklamaları olan her kaynak kodu dosyası için bir .xdc dosyasını oluşturmak için neden olur.

## <a name="syntax"></a>Sözdizimi

> **/ doc**[*adı*]

## <a name="arguments"></a>Arguments

*Adı*<br/>
Derleyici oluşturacak .xdc dosyasının adı. Yalnızca bir .cpp dosyası derlemede geçirildiğinde geçerlidir.

## <a name="remarks"></a>Açıklamalar

.Xdc dosyalarının bir .xml dosyasına xdcmake.exe'yi ile işlenir. Daha fazla bilgi için [XDCMake başvurusu](../../ide/xdcmake-reference.md).

Belge açıklamaları için kaynak kod dosyalarınızı ekleyebilirsiniz. Daha fazla bilgi için [belge açıklamaları için önerilen etiketler](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).

IntelliSense ile oluşturulan .xml dosyasını kullanmak için destek ve .xml dosyasını yerleştirmek istediğiniz derleme ile aynı derleme olarak aynı dizinde olduğu .xml dosyasının dosya adını olun. Visual Studio projesinde derlemeye başvurulduğundan, .xml dosyasını da bulunur. Daha fazla bilgi için [IntelliSense kullanarak](/visualstudio/ide/using-intellisense) ve [XML kodu açıklamalarını sağlama](/visualstudio/ide/supplying-xml-code-comments).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **Çıkış dosyalarını** özellik sayfası.

1. Değiştirme **XML belge dosyaları oluştur** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)