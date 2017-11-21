---
title: "-FR, -Fr (oluşturun. SBR dosyası) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.BrowseInformation
- VC.Project.VCCLCompilerTool.BrowseInformation
- /fr
- VC.Project.VCCLCompilerTool.BrowseInformationFile
- VC.Project.VCCLWCECompilerTool.BrowseInformationFile
dev_langs: C++
helpviewer_keywords:
- /FR compiler option [C++]
- -FR compiler option [C++]
- FR compiler option [C++]
- symbolic browser information
ms.assetid: 3fd8f88b-3924-4feb-9393-287036a28896
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 61c5b42ab8d9d76f68977d156be5ee037b376711
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fr-fr-create-sbr-file"></a>/FR, /Fr (.Sbr Dosyası Oluştur)
.SBR dosyaları oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/FR[pathname[\filename]]  
/Fr[pathname[\filename]]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme işlemi sırasında Microsoft Gözat bilgi dosyası bakım yardımcı programı (BSCMAKE) oluşturmak için bu dosyaları kullanan bir. Gözatma bilgileri görüntülemek için kullanılan BSC dosyası.  
  
 **/FR** tam simgesel bilgilerle .sbr dosyası oluşturur.  
  
 **/FR** yerel değişkenlerde bilgisi olmadan .sbr dosyası oluşturur.  
  
 Belirtmezseniz, `filename`, temel kaynak dosya adıyla aynı .sbr dosyası alır.  
  
 **/FR** kullanım dışıdır; kullanın **/FR** yerine. Daha fazla bilgi için bkz: kullanım dışı ve kaldırılmış derleyici seçeneklerinde [derleyici seçenekleri kategoriye göre listelenen](../../build/reference/compiler-options-listed-by-category.md).  
  
> [!NOTE]
>  .Sbr uzantısını değiştirmeyin. BSCMAKE Ara dosyaların uzantıya sahip olmasını gerektirir.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Gezinti Bölmesi'nde seçin **C/C++**, **Gözat bilgi** özellik sayfası.  
  
3.  Değiştirme **bilgi dosyaya Gözat** veya **Gözat bilgi etkinleştirmek** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformation%2A> ve <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.BrowseInformationFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çıktı dosyası (/ F) seçenekleri](../../build/reference/output-file-f-options.md)   
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Yol adını belirtme](../../build/reference/specifying-the-pathname.md)