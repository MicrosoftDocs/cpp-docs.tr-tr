---
title: "-MIDL (MIDL komut satırı seçeneklerini belirt) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /midl
- VC.Project.VCLinkerTool.MidlCommandFile
dev_langs:
- C++
helpviewer_keywords:
- -MIDL linker option
- MIDL
- /MIDL linker option
- MIDL linker option
- MIDL, command line options
ms.assetid: 22dc259e-b34c-4ed3-a380-4beb734482c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8e842f4cf0f9c52945c04739879d0132eb34171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="midl-specify-midl-command-line-options"></a>/MIDL (MIDL Komut Satırı Seçeneklerini Belirt)
```  
/MIDL:@file  
```  
  
## <a name="remarks"></a>Açıklamalar  
 burada:  
  
 `file`  
 İçeren dosyanın adını [MIDL komut satırı seçenekleri](http://msdn.microsoft.com/library/windows/desktop/aa366839).  
  
## <a name="remarks"></a>Açıklamalar  
 IDL dosya dönüştürme TLB dosyası için tüm seçenekleri verilmelidir `file`; MIDL komut satırı seçenekleri bağlayıcı'nın komut satırında belirtilemez. /MIDL belirtilmezse, yalnızca IDL dosya adı ve başka hiçbir seçenek MIDL derleyici çağrılır.  
  
 Dosya her satırda bir MIDL komut satırı seçeneği içermelidir.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).  
  
2.  Tıklatın **bağlayıcı** klasör.  
  
3.  Tıklatın **katıştırılmış IDL** özellik sayfası.  
  
4.  Değiştirme **MIDL komutları** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MidlCommandFile%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [/ IDLOUT (MIDL çıktı dosyalarını Adlandır)](../../build/reference/idlout-name-midl-output-files.md)   
 [/ IGNOREIDL (öznitelikleri Mıdl'ye işleme)](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ TLBOUT (adı. TLB dosyası)](../../build/reference/tlbout-name-dot-tlb-file.md)   
 [Öznitelikli Program Derleme](../../windows/building-an-attributed-program.md)