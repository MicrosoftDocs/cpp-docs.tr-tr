---
title: "-EP (#line yönergeleri olmadan stdout'ta Önişle) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ep
- VC.Project.VCCLCompilerTool.GeneratePreprocessedFileNoLines
dev_langs:
- C++
helpviewer_keywords:
- copy preprocessor output to stdout
- preprocessor output, copy to stdout
- -EP compiler option [C++]
- EP compiler option [C++]
- /EP compiler option [C++]
ms.assetid: 6ec411ae-e33d-4ef5-956e-0054635eabea
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9d7b2a64ec8fa7565d17ab04683fec07c48aea3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ep-preprocess-to-stdout-without-line-directives"></a>/EP (#line Yönergeleri Olmadan stdout'ta Önişle)
C ve C++ kaynak dosyalarını preprocesses ve standart çıktı aygıtına önceden işlenmiş dosyalarını kopyalar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/EP  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşlemdeki tüm önişlemci yönergeleri gerçekleştirilir, makrosu genişletmeleri gerçekleştirilir ve açıklamaları kaldırılır. Önceden işlenmiş çıkış açıklamaları korumak için kullanmak [/C (korumak açıklamaları sırasındaki)](../../build/reference/c-preserve-comments-during-preprocessing.md) seçeneğini **/EP**.  
  
 **/EP** seçeneği derleme gizler. Derleme önceden işlenmiş dosyayı yeniden göndermeniz gerekir. **/EP** de çıktı dosyalarını bastırır **/FA**, **/Fa**, ve **/Fm** seçenekleri. Daha fazla bilgi için bkz: [/FA, /Fa (listeleme dosyası)](../../build/reference/fa-fa-listing-file.md) ve [(/FM eşlem dosyasını Adlandır)](../../build/reference/fm-name-mapfile.md).  
  
 İşleme sonraki aşamaları sırasında oluşturulan hatalar özgün kaynak dosya yerine önceden işlenmiş dosya satır numaralarını bakın. Özgün kaynak dosyasına başvurmak için satır numaralarını istiyorsanız kullanın [/E (Stdout'a Önişle)](../../build/reference/e-preprocess-to-stdout.md) yerine. **/E** seçeneği ekler `#line` bu amaç için çıktıyı yönergeleri.  
  
 İle önceden işlenmiş çıkış göndermek için `#line` yönergeleri, bir dosyaya kullanmak [/P (dosyaya Önişle)](../../build/reference/p-preprocess-to-a-file.md) bunun yerine seçeneği.  
  
 İle stdout önceden işlenmiş çıkış göndermek için `#line` yönergeleri kullanın **/P** ve **/EP** birlikte.  
  
 Önceden derlenmiş üst bilgileri ile kullanamazsınız **/EP** seçeneği.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **C/C++** klasör.  
  
3.  Tıklatın **önişlemci** özellik sayfası.  
  
4.  Değiştirme **ön işlemesi yapılan dosya oluşturmak** özelliği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile%2A>.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki komut satırını dosya preprocesses `ADD.C`açıklamaları korur ve standart çıktı aygıtında sonucu görüntüler:  
  
```  
CL /EP /C ADD.C  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)