---
title: "-P (dosyaya Önişle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFile
- /p
- VC.Project.VCCLWCECompilerTool.GeneratePreprocessedFile
dev_langs: C++
helpviewer_keywords:
- /P compiler option [C++]
- -P compiler option [C++]
- P compiler option [C++]
- output files, preprocessor
- preprocessing output files
ms.assetid: 123ee54f-8219-4a6f-9876-4227023d83fc
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9812f54e4fb886c721f2162aeac620ec4a02acd6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="p-preprocess-to-a-file"></a>/P (Dosyaya Önişle)
C ve C++ kaynak dosyalarını preprocesses ve önceden işlenmiş çıktıyı bir dosyaya yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/P  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Dosya kaynak dosyasını ve .i uzantı temel aynı ada sahip. İşlemdeki tüm önişlemci yönergeleri gerçekleştirilir, makrosu genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıkış açıklamaları korumak için kullanmak [/C (korumak açıklamaları sırasındaki)](../../build/reference/c-preserve-comments-during-preprocessing.md) ile birlikte seçeneği **/P**.  
  
 **/P** ekler `#line` başında ve son eklenen her dosya ve koşullu derleme için önişlemci yönergeleri tarafından kaldırılan satırları geçici çıkış yönergeleri. Bu yönergeleri önceden işlenmiş dosyasındaki satırları numaralandırmak. Sonuç olarak, özgün kaynak dosyası yerine önceden işlenmiş dosyasına satır satır numaralarını işleme sonraki aşamaları sırasında oluşturulan hatalar bakın. Oluşturulmasını gizlemek için `#line` yönergeleri kullanın [/EP (#line yönergeleri olmadan stdout'ta Önişle)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) yanı **/P**.  
  
 **/P** seçeneği derleme gizler. Kullansanız bile bir .obj dosyası üretmez [/Fo (nesne dosya adı)](../../build/reference/fo-object-file-name.md). Derleme önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/P** de çıktı dosyalarını bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için bkz: [/FA, /Fa (listeleme dosyası)](../../build/reference/fa-fa-listing-file.md) ve [(/FM eşlem dosyasını Adlandır)](../../build/reference/fm-name-mapfile.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **önişlemci** özellik sayfası.  
  
4.  Değiştirme **ön işlemesi yapılan dosya oluşturmak** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını preprocesses `ADD.C`, Yorumlar korur, ekler `#line` yönergeleri ve sonucu bir dosyaya yazar `ADD.I`:  
  
```  
CL /P /C ADD.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [/Fi (çıktı dosyası adını önişle)](../../build/reference/fi-preprocess-output-file-name.md)