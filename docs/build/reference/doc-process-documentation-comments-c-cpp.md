---
title: -doc (işlem belgesi açıklamaları) (C/C++) | Microsoft Docs
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
ms.openlocfilehash: 899ff6b774c365ce9df3019ef5ba6d08d0d7b93d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (İşlem Belgeleri Açıklamaları) (C/C++)
Kaynak kodu dosyaları ve belge açıklamaları olan her kaynak kodu dosyasının bir .xdc dosyası oluşturmak için işlem belgesi açıklamaları derleyiciye neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>Arguments  
 `name`  
 Derleyici oluşturacak .xdc dosyasının adı. Yalnızca bir .cpp dosya derlemede geçirildiğinde geçerli.  
  
## <a name="remarks"></a>Açıklamalar  
 .Xdc dosyaları xdcmake.exe ile bir .xml dosyasına işlenir. Daha fazla bilgi için bkz: [XDCMake başvurusu](../../ide/xdcmake-reference.md).  
  
 Belge açıklamaları için kaynak kodu dosyaları ekleyebilirsiniz. Daha fazla bilgi için bkz: [belge açıklamaları için önerilen etiketler](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 IntelliSense ile oluşturulmuş .xml dosyasını kullanmak için destek ve .xml dosyasını yerleştirmek istediğiniz derleme derlemeyle aynı dizinde aynıdır .xml dosyasının dosya adını olun. Visual Studio projesini derleme başvurulduğunda .xml dosyası da bulunur. Daha fazla bilgi için bkz: [kullanarak IntelliSense](/visualstudio/ide/using-intellisense) ve [XML kodu açıklamalarını sağlama](/visualstudio/ide/supplying-xml-code-comments).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **C/C++** düğümü.  
  
4.  Seçin **çıktı dosyaları** özellik sayfası.  
  
5.  Değiştirme **XML belge dosyalarını oluşturmak** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)