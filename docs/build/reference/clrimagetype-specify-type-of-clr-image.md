---
title: "-CLRIMAGETYPE (CLR görüntü türünü belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /CLRIMAGETYPE
- VC.Project.VCLinkerTool.CLRImageType
dev_langs:
- C++
helpviewer_keywords:
- /CLRIMAGETYPE linker option
- -CLRIMAGETYPE linker option
ms.assetid: 04c60ee6-9dd7-4391-bc03-6926ad0fa116
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d8de8abb1602499cea0b1412d4199ea54b3bf601
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="clrimagetype-specify-type-of-clr-image"></a>/CLRIMAGETYPE (CLR Görüntü Türünü Belirt)
```  
/CLRIMAGETYPE:{IJW|PURE|SAFE|SAFE32BITPREFERRED}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bağlayıcı yerel nesneleri kabul eder ve ayrıca kullanarak derlenen MSIL nesneleri [/CLR](../../build/reference/clr-common-language-runtime-compilation.md). **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı. Karma nesneleri aynı derlemede geçirildiğinde, sonuçta elde edilen çıktı dosyası verifiability, varsayılan olarak, en düşük düzeyde verifiability giriş modüllerin eşit olur. Örneğin, yerel bir görüntü ve karma mod görüntü geçirirseniz (kullanarak derlenmiş **/CLR**), elde edilen görüntü bir karma mod görüntüsü olacaktır.  
  
 Bu ihtiyacınız olursa, /CLRIMAGETYPE verifiability, daha düşük düzeyde belirtmek için kullanabilirsiniz.  
  
 Bir dosya CLR görüntü türünü belirleme hakkında daha fazla bilgi için bkz: [/CLRHEADER](../../build/reference/clrheader.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **Gelişmiş** özellik sayfası.  
  
5.  Değiştirme **CLR görüntü türünü** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
1.  Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.CLRImageType%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)